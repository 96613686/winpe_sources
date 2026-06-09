# StartServiceExtension(_GUID const *,ushort *)

- ea: `0x180003490`
- end: `0x18000369b`
- name: `?StartServiceExtension@@YAJPEBU_GUID@@PEAG@Z`
- size: `523`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x180001008`
- `0x180003490`
- `0x180005010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003614`
- `ole32!CoCreateInstance` at `0x180003614`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003526`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000358a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800035f5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180003526`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000358a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800035f5`

## pseudocode

```c
__int64 __fastcall StartServiceExtension(IID *rclsid, unsigned __int16 *a2)
{
  __int64 v2; // rbx
  CEtwTracer *v5; // rcx
  LPVOID v6; // rbx
  __int64 v8; // rax
  HRESULT v9; // eax
  LPVOID v10; // rsi
  _QWORD *v11; // rax
  int v12; // [rsp+70h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF

  v2 = -1;
  v12 = 0;
  ppv = 0;
  if ( rclsid )
  {
    if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
      && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
      && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      CEtwTracer::EtwTraceEvent(
        (CEtwTracer *)g_pEtwGlobalTracer,
        (const struct _GUID *)IISAdminStatupGuid,
        0xDu,
        a2,
        2 * v8 + 2,
        0,
        0);
    }
    v9 = CoCreateInstance(rclsid, 0, 1u, &IID_IADMEXT, &ppv);
    v12 = v9;
    if ( v9 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
      if ( v12 >= 0 )
      {
        v10 = ppv;
        v11 = operator new(0x18u);
        if ( v11 )
        {
          *v11 = v10;
          v11[1] = g_piaecHead;
          v11[2] = a2;
          v12 = 0;
          g_piaecHead = v11;
          goto LABEL_11;
        }
        v12 = -2147024888;
      }
    }
    else
    {
      if ( v9 == -2147221164 )
      {
        v12 = 0;
        v9 = 0;
      }
      if ( v9 >= 0 )
        goto LABEL_8;
    }
  }
  else
  {
    v12 = -2147024809;
  }
  v5 = (CEtwTracer *)g_pEtwGlobalTracer;
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) )
  {
    do
      ++v2;
    while ( a2[v2] );
    CEtwTracer::EtwTraceEvent(
      (CEtwTracer *)g_pEtwGlobalTracer,
      (const struct _GUID *)IISAdminStatupGuid,
      0xEu,
      a2,
      2 * v2 + 2,
      &v12,
      4,
      0,
      0);
LABEL_8:
    v5 = (CEtwTracer *)g_pEtwGlobalTracer;
  }
  v6 = ppv;
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 40LL))(ppv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_11:
    v5 = (CEtwTracer *)g_pEtwGlobalTracer;
    ppv = 0;
  }
  if ( *((_DWORD *)v5 + 2) && (*((_BYTE *)v5 + 40) & 1) != 0 && *((_DWORD *)v5 + 11) >= 4u )
    CEtwTracer::EtwTraceEvent(v5, (const struct _GUID *)IISAdminStatupGuid, 0xFu);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003490  mov     [rsp-18h+arg_8], rbx
0x180003495  mov     [rsp-18h+arg_18], rsi
0x18000349a  push    rbp
0x18000349b  push    rdi
0x18000349c  push    r14
0x18000349e  mov     rbp, rsp
0x1800034a1  sub     rsp, 50h
0x1800034a5  xor     r14d, r14d
0x1800034a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800034ac  mov     [rbp+arg_0], r14d
0x1800034b0  mov     rdi, rdx
0x1800034b3  mov     [rbp+arg_10], r14
0x1800034b7  mov     rsi, rcx
0x1800034ba  test    rcx, rcx
0x1800034bd  jnz     loc_1800035A8
0x1800034c3  mov     [rbp+arg_0], 80070057h
0x1800034ca  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800034d1  cmp     [rcx+8], r14d
0x1800034d5  jz      short loc_180003533
0x1800034d7  test    byte ptr [rcx+28h], 1
0x1800034db  jz      short loc_180003533
0x1800034dd  cmp     dword ptr [rcx+2Ch], 1
0x1800034e1  jb      short loc_180003533
0x1800034e3  inc     rbx
0x1800034e6  cmp     [rdi+rbx*2], r14w
0x1800034eb  jnz     short loc_1800034E3
0x1800034ed  mov     [rsp+50h+var_10], r14
0x1800034f2  lea     rdx, [rbp+arg_0]
0x1800034f6  mov     [rsp+50h+var_18], r14
0x1800034fb  lea     rax, ds:2[rbx*2]
0x180003503  mov     [rsp+50h+var_20], 4
0x18000350c  mov     r9, rdi
0x18000350f  mov     [rsp+50h+var_28], rdx
0x180003514  mov     r8d, 0Eh
0x18000351a  lea     rdx, IISAdminStatupGuid
0x180003521  mov     [rsp+50h+ppv], rax
0x180003526  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000352c  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180003533  mov     rbx, [rbp+arg_10]
0x180003537  test    rbx, rbx
0x18000353a  jz      short loc_180003565
0x18000353c  mov     rax, [rbx]
0x18000353f  mov     rcx, rbx
0x180003542  mov     rax, [rax+28h]
0x180003546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354b  mov     rax, [rbx]
0x18000354e  mov     rcx, rbx
0x180003551  mov     rax, [rax+10h]
0x180003555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000355a  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180003561  mov     [rbp+arg_10], r14
0x180003565  cmp     [rcx+8], r14d
0x180003569  jz      short loc_180003590
0x18000356b  test    byte ptr [rcx+28h], 1
0x18000356f  jz      short loc_180003590
0x180003571  cmp     dword ptr [rcx+2Ch], 4
0x180003575  jb      short loc_180003590
0x180003577  xor     r9d, r9d
0x18000357a  mov     [rsp+50h+ppv], r14
0x18000357f  lea     rdx, IISAdminStatupGuid
0x180003586  lea     r8d, [r9+0Fh]
0x18000358a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180003590  mov     eax, [rbp+arg_0]
0x180003593  lea     r11, [rsp+50h+var_s0]
0x180003598  mov     rbx, [r11+28h]
0x18000359c  mov     rsi, [r11+38h]
0x1800035a0  mov     rsp, r11
0x1800035a3  pop     r14
0x1800035a5  pop     rdi
0x1800035a6  pop     rbp
0x1800035a7  retn
0x1800035a8  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800035af  cmp     [rcx+8], r14d
0x1800035b3  jz      short loc_1800035FB
0x1800035b5  test    byte ptr [rcx+28h], 1
0x1800035b9  jz      short loc_1800035FB
0x1800035bb  cmp     dword ptr [rcx+2Ch], 4
0x1800035bf  jb      short loc_1800035FB
0x1800035c1  mov     rax, rbx
0x1800035c4  inc     rax
0x1800035c7  cmp     [rdx+rax*2], r14w
0x1800035cc  jnz     short loc_1800035C4
0x1800035ce  lea     rax, ds:2[rax*2]
0x1800035d6  mov     [rsp+50h+var_20], r14
0x1800035db  mov     [rsp+50h+var_28], r14
0x1800035e0  lea     rdx, IISAdminStatupGuid
0x1800035e7  mov     r9, rdi
0x1800035ea  mov     [rsp+50h+ppv], rax
0x1800035ef  mov     r8d, 0Dh
0x1800035f5  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x1800035fb  xor     edx, edx; pUnkOuter
0x1800035fd  lea     rax, [rbp+arg_10]
0x180003601  lea     r9, IID_IADMEXT; riid
0x180003608  mov     [rsp+50h+ppv], rax; ppv
0x18000360d  mov     rcx, rsi; rclsid
0x180003610  lea     r8d, [rdx+1]; dwClsContext
0x180003614  call    cs:__imp_CoCreateInstance
0x18000361a  mov     [rbp+arg_0], eax
0x18000361d  test    eax, eax
0x18000361f  jns     short loc_18000363C
0x180003621  cmp     eax, 80040154h
0x180003626  jnz     short loc_18000362F
0x180003628  mov     [rbp+arg_0], r14d
0x18000362c  mov     eax, r14d
0x18000362f  test    eax, eax
0x180003631  js      loc_1800034CA
0x180003637  jmp     loc_18000352C
0x18000363c  mov     rcx, [rbp+arg_10]
0x180003640  mov     rax, [rcx]
0x180003643  mov     rax, [rax+18h]
0x180003647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364c  mov     [rbp+arg_0], eax
0x18000364f  test    eax, eax
0x180003651  js      loc_1800034CA
0x180003657  mov     rsi, [rbp+arg_10]
0x18000365b  mov     ecx, 18h; Size
0x180003660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003665  mov     rcx, rax
0x180003668  test    rax, rax
0x18000366b  jnz     short loc_180003679
0x18000366d  mov     [rbp+arg_0], 80070008h
0x180003674  jmp     loc_1800034CA
0x180003679  mov     [rax], rsi
0x18000367c  mov     rax, cs:?g_piaecHead@@3PEAU_IADMEXT_CONTAINER@@EA; _IADMEXT_CONTAINER * g_piaecHead
0x180003683  mov     [rcx+8], rax
0x180003687  mov     [rcx+10h], rdi
0x18000368b  mov     [rbp+arg_0], r14d
0x18000368f  mov     cs:?g_piaecHead@@3PEAU_IADMEXT_CONTAINER@@EA, rcx; _IADMEXT_CONTAINER * g_piaecHead
0x180003696  jmp     loc_18000355A
```
