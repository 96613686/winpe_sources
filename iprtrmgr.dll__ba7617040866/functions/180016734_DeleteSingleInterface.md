# DeleteSingleInterface

- ea: `0x180016734`
- end: `0x180016b9f`
- name: `DeleteSingleInterface`
- size: `1131`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800017a0`
- `0x180002ac4`
- `0x180010b80`
- `0x18001121c`
- `0x180023b08`
- `0x180050b74`

## callees

- `0x18000ed70`
- `0x18000ef08`
- `0x180011790`
- `0x180013fe0`
- `0x180016560`
- `0x180016734`
- `0x18001a82c`
- `0x18001c74c`
- `0x18002ee20`
- `0x18002f06c`
- `0x18004002c`
- `0x1800401a0`
- `0x180057bac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800169cb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016b19`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800169cb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016b19`
- `ntdll!RtlReleaseResource` at `0x1800168c3`
- `ntdll!RtlReleaseResource` at `0x1800169e0`
- `ntdll!RtlReleaseResource` at `0x180016b2e`
- `ntdll!RtlReleaseResource` at `0x1800168c3`
- `ntdll!RtlReleaseResource` at `0x1800169e0`
- `ntdll!RtlReleaseResource` at `0x180016b2e`
- `ntdll!RtlAcquireResourceShared` at `0x180016872`
- `ntdll!RtlAcquireResourceShared` at `0x180016872`
- `KERNEL32!DeleteCriticalSection` at `0x180016b74`
- `KERNEL32!DeleteCriticalSection` at `0x180016b74`
- `KERNEL32!HeapFree` at `0x1800168f2`
- `KERNEL32!HeapFree` at `0x180016992`
- `KERNEL32!HeapFree` at `0x1800169f2`
- `KERNEL32!HeapFree` at `0x180016b45`
- `KERNEL32!HeapFree` at `0x180016b60`
- `KERNEL32!HeapFree` at `0x1800168f2`
- `KERNEL32!HeapFree` at `0x180016992`
- `KERNEL32!HeapFree` at `0x1800169f2`
- `KERNEL32!HeapFree` at `0x180016b45`
- `KERNEL32!HeapFree` at `0x180016b60`

## string_xrefs

- `0x1800167e5`: `Entered: DeleteSingleInterface`
- `0x18001691f`: `DeleteSingleInterface: Freeing memory for interface %ws of type %d at %X `

## pseudocode

```c
__int64 __fastcall DeleteSingleInterface(__int64 a1)
{
  unsigned int v1; // r12d
  __int64 v2; // r13
  __int64 InternalInterfaceForRoutingDomain; // r15
  __int128 *v5; // r9
  int v6; // eax
  __int64 *v7; // rcx
  _QWORD *v8; // rbx
  __int64 *v9; // r14
  void (__fastcall *v10)(_QWORD, __int64 *); // rax
  void *v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  __int128 *v14; // r9
  void *v15; // rbx
  void *v16; // rbx
  __int64 InterfaceBinding; // rsi
  int v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // r9
  __int128 *v21; // r9
  void *v22; // r8
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+64h] [rbp-9Ch]
  __int128 v31; // [rsp+74h] [rbp-8Ch]
  int v32; // [rsp+84h] [rbp-7Ch]
  int v33; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v1 = *(_DWORD *)(a1 + 516);
  v2 = a1 + 688;
  v33 = 0;
  InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain(
                                        (struct _GUID *)(a1 + 688),
                                        v1 != 0 ? 33 : 87);
  memset_0(v34, 0, sizeof(v34));
  v29 = 0;
  v32 = 0;
  LOBYTE(v25) = Microsoft_Windows_RRASEnableBits & 0x80;
  v30 = 0;
  v31 = 0;
  v26 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v29) = 0;
    v5 = &v26;
    if ( v2 )
      LODWORD(v5) = v2;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: DeleteSingleInterface",
      (_DWORD)v5,
      *(_QWORD *)(a1 + 72),
      (__int64)&v29);
  }
  v6 = *(_DWORD *)(a1 + 144);
  if ( !v6 )
  {
    if ( *(_DWORD *)(a1 + 512) )
    {
      v7 = *(__int64 **)(a1 + 712);
      v25 = 0;
      v28 = 0;
      v27 = 0;
      if ( v1 )
      {
        v25 = *v7;
      }
      else
      {
        v27 = *(_OWORD *)((char *)v7 + 4);
        v28 = *(_DWORD *)v7;
      }
      if ( InternalInterfaceForRoutingDomain )
      {
        RtlAcquireResourceShared(&stru_18008C4A0, 1u);
        v8 = *(_QWORD **)(InternalInterfaceForRoutingDomain + 56);
        if ( v8 != (_QWORD *)(InternalInterfaceForRoutingDomain + 56) )
        {
          v9 = (__int64 *)&v27;
          if ( v1 )
            v9 = &v25;
          do
          {
            v10 = *(void (__fastcall **)(_QWORD, __int64 *))(v8[3] + 192LL);
            if ( v10 )
              v10(*(unsigned int *)(InternalInterfaceForRoutingDomain + 16), v9);
            v8 = (_QWORD *)*v8;
          }
          while ( v8 != (_QWORD *)(InternalInterfaceForRoutingDomain + 56) );
        }
        RtlReleaseResource(&stru_18008C4A0);
        DeleteInterfaceFromAllProtocols(a1);
        DeleteAllClientRoutes(a1, *(unsigned int *)(InternalInterfaceForRoutingDomain + 16));
      }
      v11 = *(void **)(a1 + 504);
      if ( v11 )
      {
        HeapFree(IPRouterHeap, 0, v11);
        *(_QWORD *)(a1 + 504) = 0;
      }
    }
    if ( *(_QWORD *)(a1 + 712) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v12 = *(unsigned int *)(a1 + 516);
        v13 = *(_QWORD *)(a1 + 72);
        v24 = *(_QWORD *)(a1 + 712);
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        FormatRRASErrorString(
          &v33,
          L"DeleteSingleInterface: Freeing memory for interface %ws of type %d at %X ",
          v13,
          v12,
          v24);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v14 = &v26;
          if ( v2 )
            LODWORD(v14) = v2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v33,
            (_DWORD)v14,
            *(_QWORD *)(a1 + 72),
            (__int64)&v29);
        }
      }
      HeapFree(IPRouterHeap, 0, *(LPVOID *)(a1 + 712));
      *(_QWORD *)(a1 + 712) = 0;
    }
    DeleteFilterInterface(a1);
    goto LABEL_54;
  }
  if ( v6 == 7 )
  {
    v15 = *(void **)(a1 + 712);
    DeleteAllRoutes(a1, 0);
    RtlAcquireResourceExclusive(&stru_18008C500, 1u);
    RemoveBinding(a1);
    RtlReleaseResource(&stru_18008C500);
    HeapFree(IPRouterHeap, 0, v15);
    *(_QWORD *)(a1 + 712) = 0;
    goto LABEL_54;
  }
  DeleteAllRoutes(a1, 1);
  if ( (unsigned int)(*(_DWORD *)(a1 + 144) - 1) <= 1 )
  {
    v16 = *(void **)(a1 + 712);
    InterfaceBinding = GetInterfaceBinding(*(unsigned int *)(a1 + 16), v1);
  }
  else
  {
    v16 = 0;
    InterfaceBinding = 0;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 144) - 3) <= 2 )
    LanEtcInterfaceUpToDown(a1);
  else
    WanInterfaceInactiveToDown(a1, 1);
  DeleteInterfaceFromAllProtocols(a1);
  v18 = *(_DWORD *)(a1 + 144);
  if ( (unsigned int)(v18 - 1) <= 1 )
  {
    DeleteDemandFilterInterface(a1);
  }
  else if ( v18 != 4 )
  {
    goto LABEL_41;
  }
  DeleteInterfaceWithWanArp(a1);
LABEL_41:
  if ( (unsigned int)(*(_DWORD *)(a1 + 144) - 4) > 1 )
  {
    v19 = DeleteFilterInterface(a1);
    if ( v19 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v20 = *(_QWORD *)(a1 + 72);
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v33, L"Error %d deleting %ws from the filter driver", v19, v20);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v21 = &v26;
          if ( v2 )
            LODWORD(v21) = v2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v33,
            (_DWORD)v21,
            *(_QWORD *)(a1 + 72),
            (__int64)&v29);
        }
      }
    }
  }
  if ( InterfaceBinding )
  {
    RtlAcquireResourceExclusive(&stru_18008C500, 1u);
    RemoveBinding(a1);
    RtlReleaseResource(&stru_18008C500);
  }
  if ( v16 )
    HeapFree(IPRouterHeap, 0, v16);
  v22 = *(void **)(a1 + 296);
  if ( v22 )
  {
    HeapFree(IPRouterHeap, 0, v22);
    *(_QWORD *)(a1 + 296) = 0;
  }
LABEL_54:
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 720));
  return 0;
}

```

## disassembly

```asm
0x180016734  push    rbp
0x180016736  push    rbx
0x180016737  push    rsi
0x180016738  push    rdi
0x180016739  push    r12
0x18001673b  push    r13
0x18001673d  push    r14
0x18001673f  push    r15
0x180016741  lea     rbp, [rsp-7A8h]
0x180016749  sub     rsp, 8A8h
0x180016750  mov     rax, cs:__security_cookie
0x180016757  xor     rax, rsp
0x18001675a  mov     [rbp+7E0h+var_50], rax
0x180016761  mov     r12d, [rcx+204h]
0x180016768  lea     r13, [rcx+2B0h]
0x18001676f  mov     eax, r12d
0x180016772  mov     rdi, rcx
0x180016775  neg     eax
0x180016777  mov     rcx, r13; struct _GUID *
0x18001677a  sbb     edx, edx
0x18001677c  and     edx, 0FFFFFFCAh
0x18001677f  add     edx, 57h ; 'W'; unsigned int
0x180016782  call    GetInternalInterfaceForRoutingDomain
0x180016787  xor     r14d, r14d
0x18001678a  lea     rcx, [rbp+7E0h+var_84C]; void *
0x18001678e  xor     edx, edx; Val
0x180016790  mov     [rbp+7E0h+var_850], r14d
0x180016794  mov     r8d, 7FCh; Size
0x18001679a  mov     r15, rax
0x18001679d  call    memset_0
0x1800167a2  xor     eax, eax
0x1800167a4  mov     [rsp+8E0h+var_880], r14d
0x1800167a9  xorps   xmm0, xmm0
0x1800167ac  mov     [rbp+7E0h+var_85C], eax
0x1800167af  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x1800167b5  and     al, 80h
0x1800167b7  mov     byte ptr [rsp+8E0h+var_8B0], al
0x1800167bb  movups  [rsp+8E0h+var_87C], xmm0
0x1800167c0  movups  [rsp+8E0h+var_86C], xmm0
0x1800167c5  movups  [rsp+8E0h+var_8A8], xmm0
0x1800167ca  jz      short loc_18001680B
0x1800167cc  lea     rax, [rsp+8E0h+var_880]
0x1800167d1  mov     word ptr [rsp+8E0h+var_880], r14w
0x1800167d7  mov     [rsp+8E0h+var_8B8], rax
0x1800167dc  lea     r9, [rsp+8E0h+var_8A8]
0x1800167e1  mov     rax, [rdi+48h]
0x1800167e5  lea     r8, aEnteredDeletes; "Entered: DeleteSingleInterface"
0x1800167ec  test    r13, r13
0x1800167ef  mov     [rsp+8E0h+var_8C0], rax
0x1800167f4  lea     rdx, RasRtrmgrParamTraceInfo
0x1800167fb  cmovnz  r9, r13
0x1800167ff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016806  call    McTemplateU0zjzz_EventWriteTransfer
0x18001680b  mov     eax, [rdi+90h]
0x180016811  test    eax, eax
0x180016813  jnz     loc_1800169AC
0x180016819  cmp     [rdi+200h], r14d
0x180016820  jz      loc_1800168FF
0x180016826  mov     rcx, [rdi+2C8h]
0x18001682d  xor     eax, eax
0x18001682f  mov     [rsp+8E0h+var_8B0], r14
0x180016834  xorps   xmm0, xmm0
0x180016837  mov     [rsp+8E0h+var_888], eax
0x18001683b  movups  [rsp+8E0h+var_898], xmm0
0x180016840  test    r12d, r12d
0x180016843  jz      short loc_180016854
0x180016845  mov     eax, [rcx]
0x180016847  mov     dword ptr [rsp+8E0h+var_8B0], eax
0x18001684b  mov     eax, [rcx+4]
0x18001684e  mov     dword ptr [rsp+8E0h+var_8B0+4], eax
0x180016852  jmp     short loc_180016864
0x180016854  movups  xmm0, xmmword ptr [rcx+4]
0x180016858  movdqu  [rsp+8E0h+var_898], xmm0
0x18001685e  mov     eax, [rcx]
0x180016860  mov     [rsp+8E0h+var_888], eax
0x180016864  test    r15, r15
0x180016867  jz      short loc_1800168DD
0x180016869  mov     dl, 1; Wait
0x18001686b  lea     rcx, stru_18008C4A0; Resource
0x180016872  call    cs:__imp_RtlAcquireResourceShared
0x180016878  lea     rsi, [r15+38h]
0x18001687c  mov     rbx, [rsi]
0x18001687f  cmp     rbx, rsi
0x180016882  jz      short loc_1800168BC
0x180016884  test    r12d, r12d
0x180016887  lea     r14, [rsp+8E0h+var_898]
0x18001688c  lea     rax, [rsp+8E0h+var_8B0]
0x180016891  cmovnz  r14, rax
0x180016895  mov     rax, [rbx+18h]
0x180016899  mov     rax, [rax+0C0h]
0x1800168a0  test    rax, rax
0x1800168a3  jz      short loc_1800168B1
0x1800168a5  mov     ecx, [r15+10h]
0x1800168a9  mov     rdx, r14
0x1800168ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b1  mov     rbx, [rbx]
0x1800168b4  cmp     rbx, rsi
0x1800168b7  jnz     short loc_180016895
0x1800168b9  xor     r14d, r14d
0x1800168bc  lea     rcx, stru_18008C4A0; Resource
0x1800168c3  call    cs:__imp_RtlReleaseResource
0x1800168c9  mov     rcx, rdi
0x1800168cc  call    DeleteInterfaceFromAllProtocols
0x1800168d1  mov     edx, [r15+10h]
0x1800168d5  mov     rcx, rdi
0x1800168d8  call    DeleteAllClientRoutes
0x1800168dd  mov     r8, [rdi+1F8h]; lpMem
0x1800168e4  test    r8, r8
0x1800168e7  jz      short loc_1800168FF
0x1800168e9  mov     rcx, cs:IPRouterHeap; hHeap
0x1800168f0  xor     edx, edx; dwFlags
0x1800168f2  call    cs:__imp_HeapFree
0x1800168f8  mov     [rdi+1F8h], r14
0x1800168ff  mov     rcx, [rdi+2C8h]
0x180016906  test    rcx, rcx
0x180016909  jz      loc_18001699F
0x18001690f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180016916  jge     short loc_180016982
0x180016918  mov     r9d, [rdi+204h]
0x18001691f  lea     rdx, aDeletesinglein; "DeleteSingleInterface: Freeing memory f"...
0x180016926  mov     r8, [rdi+48h]
0x18001692a  mov     [rsp+8E0h+var_8C0], rcx
0x18001692f  lea     rcx, [rbp+7E0h+var_850]
0x180016933  mov     word ptr [rbp+7E0h+var_850], r14w
0x180016938  mov     word ptr [rsp+8E0h+var_880], r14w
0x18001693e  call    FormatRRASErrorString
0x180016943  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001694a  jge     short loc_180016982
0x18001694c  lea     rax, [rsp+8E0h+var_880]
0x180016951  test    r13, r13
0x180016954  mov     [rsp+8E0h+var_8B8], rax
0x180016959  lea     r9, [rsp+8E0h+var_8A8]
0x18001695e  mov     rax, [rdi+48h]
0x180016962  lea     r8, [rbp+7E0h+var_850]
0x180016966  cmovnz  r9, r13
0x18001696a  mov     [rsp+8E0h+var_8C0], rax
0x18001696f  lea     rdx, RasRtrmgrParamTraceInfo
0x180016976  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001697d  call    McTemplateU0zjzz_EventWriteTransfer
0x180016982  mov     r8, [rdi+2C8h]; lpMem
0x180016989  xor     edx, edx; dwFlags
0x18001698b  mov     rcx, cs:IPRouterHeap; hHeap
0x180016992  call    cs:__imp_HeapFree
0x180016998  mov     [rdi+2C8h], r14
0x18001699f  mov     rcx, rdi
0x1800169a2  call    DeleteFilterInterface
0x1800169a7  jmp     loc_180016B6D
0x1800169ac  mov     rcx, rdi
0x1800169af  cmp     eax, 7
0x1800169b2  jnz     short loc_180016A04
0x1800169b4  mov     rbx, [rdi+2C8h]
0x1800169bb  xor     edx, edx
0x1800169bd  call    DeleteAllRoutes
0x1800169c2  mov     dl, 1; Wait
0x1800169c4  lea     rcx, stru_18008C500; Resource
0x1800169cb  call    cs:__imp_RtlAcquireResourceExclusive
0x1800169d1  mov     rcx, rdi
0x1800169d4  call    RemoveBinding
0x1800169d9  lea     rcx, stru_18008C500; Resource
0x1800169e0  call    cs:__imp_RtlReleaseResource
0x1800169e6  mov     rcx, cs:IPRouterHeap; hHeap
0x1800169ed  mov     r8, rbx; lpMem
0x1800169f0  xor     edx, edx; dwFlags
0x1800169f2  call    cs:__imp_HeapFree
0x1800169f8  mov     [rdi+2C8h], r14
0x1800169ff  jmp     loc_180016B6D
0x180016a04  mov     edx, 1
0x180016a09  call    DeleteAllRoutes
0x180016a0e  mov     eax, [rdi+90h]
0x180016a14  dec     eax
0x180016a16  cmp     eax, 1
0x180016a19  jbe     short loc_180016A23
0x180016a1b  mov     rbx, r14
0x180016a1e  mov     rsi, r14
0x180016a21  jmp     short loc_180016A38
0x180016a23  mov     ecx, [rdi+10h]
0x180016a26  mov     edx, r12d
0x180016a29  mov     rbx, [rdi+2C8h]
0x180016a30  call    GetInterfaceBinding
0x180016a35  mov     rsi, rax
0x180016a38  mov     ecx, [rdi+90h]
0x180016a3e  sub     ecx, 3
0x180016a41  cmp     ecx, 2
0x180016a44  mov     rcx, rdi
0x180016a47  jbe     short loc_180016A55
0x180016a49  mov     edx, 1
0x180016a4e  call    WanInterfaceInactiveToDown
0x180016a53  jmp     short loc_180016A5A
0x180016a55  call    LanEtcInterfaceUpToDown
0x180016a5a  mov     rcx, rdi
0x180016a5d  call    DeleteInterfaceFromAllProtocols
0x180016a62  mov     ecx, [rdi+90h]
0x180016a68  lea     eax, [rcx-1]
0x180016a6b  cmp     eax, 1
0x180016a6e  jbe     short loc_180016A77
0x180016a70  cmp     ecx, 4
0x180016a73  jnz     short loc_180016A87
0x180016a75  jmp     short loc_180016A7F
0x180016a77  mov     rcx, rdi
0x180016a7a  call    DeleteDemandFilterInterface
0x180016a7f  mov     rcx, rdi
0x180016a82  call    DeleteInterfaceWithWanArp
0x180016a87  mov     eax, [rdi+90h]
0x180016a8d  sub     eax, 4
0x180016a90  cmp     eax, 1
0x180016a93  jbe     short loc_180016B0B
0x180016a95  mov     rcx, rdi
0x180016a98  call    DeleteFilterInterface
0x180016a9d  test    eax, eax
0x180016a9f  jz      short loc_180016B0B
0x180016aa1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016aa8  jz      short loc_180016B0B
0x180016aaa  mov     r9, [rdi+48h]
0x180016aae  lea     rdx, aErrorDDeleting; "Error %d deleting %ws from the filter d"...
0x180016ab5  mov     r8d, eax
0x180016ab8  mov     word ptr [rbp+7E0h+var_850], r14w
0x180016abd  lea     rcx, [rbp+7E0h+var_850]
0x180016ac1  mov     word ptr [rsp+8E0h+var_880], r14w
0x180016ac7  call    FormatRRASErrorString
0x180016acc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016ad3  jz      short loc_180016B0B
0x180016ad5  lea     rax, [rsp+8E0h+var_880]
0x180016ada  test    r13, r13
0x180016add  mov     [rsp+8E0h+var_8B8], rax
0x180016ae2  lea     r9, [rsp+8E0h+var_8A8]
0x180016ae7  mov     rax, [rdi+48h]
0x180016aeb  lea     r8, [rbp+7E0h+var_850]
0x180016aef  cmovnz  r9, r13
0x180016af3  mov     [rsp+8E0h+var_8C0], rax
0x180016af8  lea     rdx, RasRtrMgrParamTraceError
0x180016aff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016b06  call    McTemplateU0zjzz_EventWriteTransfer
0x180016b0b  test    rsi, rsi
0x180016b0e  jz      short loc_180016B34
0x180016b10  mov     dl, 1; Wait
0x180016b12  lea     rcx, stru_18008C500; Resource
0x180016b19  call    cs:__imp_RtlAcquireResourceExclusive
0x180016b1f  mov     rcx, rdi
0x180016b22  call    RemoveBinding
0x180016b27  lea     rcx, stru_18008C500; Resource
0x180016b2e  call    cs:__imp_RtlReleaseResource
0x180016b34  test    rbx, rbx
0x180016b37  jz      short loc_180016B4B
0x180016b39  mov     rcx, cs:IPRouterHeap; hHeap
0x180016b40  mov     r8, rbx; lpMem
0x180016b43  xor     edx, edx; dwFlags
0x180016b45  call    cs:__imp_HeapFree
0x180016b4b  mov     r8, [rdi+128h]; lpMem
0x180016b52  test    r8, r8
0x180016b55  jz      short loc_180016B6D
0x180016b57  mov     rcx, cs:IPRouterHeap; hHeap
0x180016b5e  xor     edx, edx; dwFlags
0x180016b60  call    cs:__imp_HeapFree
0x180016b66  mov     [rdi+128h], r14
0x180016b6d  lea     rcx, [rdi+2D0h]; lpCriticalSection
0x180016b74  call    cs:__imp_DeleteCriticalSection
0x180016b7a  xor     eax, eax
0x180016b7c  mov     rcx, [rbp+7E0h+var_50]
0x180016b83  xor     rcx, rsp; StackCookie
0x180016b86  call    __security_check_cookie
0x180016b8b  add     rsp, 8A8h
0x180016b92  pop     r15
0x180016b94  pop     r14
0x180016b96  pop     r13
0x180016b98  pop     r12
0x180016b9a  pop     rdi
0x180016b9b  pop     rsi
0x180016b9c  pop     rbx
0x180016b9d  pop     rbp
0x180016b9e  retn
```
