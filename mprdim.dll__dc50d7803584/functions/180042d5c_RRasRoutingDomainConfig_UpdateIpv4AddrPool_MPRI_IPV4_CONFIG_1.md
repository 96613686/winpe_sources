# RRasRoutingDomainConfig::UpdateIpv4AddrPool(_MPRI_IPV4_CONFIG_1 *)

- ea: `0x180042d5c`
- end: `0x180043064`
- name: `?UpdateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV4_CONFIG_1@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_IPV4_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800416fc`
- `0x180042398`

## callees

- `0x180042d5c`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e12`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042f55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042f55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004300a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004300a`
- `KERNEL32!GetProcessHeap` at `0x180042f44`
- `KERNEL32!GetProcessHeap` at `0x180042ffc`
- `KERNEL32!GetProcessHeap` at `0x180042f44`
- `KERNEL32!GetProcessHeap` at `0x180042ffc`

## string_xrefs

- `0x180042ee9`: `%s: No IPv4 address pool configured.`
- `0x180042dff`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x180042ee2`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x180042f82`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x180042e3f`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::UpdateIpv4AddrPool(
        RRasRoutingDomainConfig *this,
        struct _MPRI_IPV4_CONFIG_1 *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // r9d
  __int64 v6; // r9
  unsigned int i; // r8d
  void *v8; // rsi
  GUID *v9; // r9
  size_t v10; // r14
  HANDLE ProcessHeap; // rax
  void *v12; // rax
  GUID *v13; // r9
  void *v14; // r14
  HANDLE v15; // rax
  unsigned int v16; // ebx
  unsigned __int16 *v18; // [rsp+28h] [rbp-D8h]
  unsigned int v19; // [rsp+30h] [rbp-D0h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h]
  __int128 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+7Ch] [rbp-84h]
  GUID v27; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+94h] [rbp-6Ch]
  __int128 v30; // [rsp+A4h] [rbp-5Ch]
  int v31; // [rsp+B4h] [rbp-4Ch]
  int v32; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v33[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v20 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v21,
      L"RRasRoutingDomainConfig::UpdateIpv4AddrPool",
      &v20,
      v4,
      (struct _GUID *)((char *)this + 516),
      v18,
      v19);
  v5 = *((_DWORD *)a2 + 1);
  if ( !v5 || *((_QWORD *)a2 + 1) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= v5 )
      {
        if ( v5 )
        {
          v10 = 8 * v5;
          ProcessHeap = GetProcessHeap();
          v12 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v10);
          v8 = v12;
          if ( !v12 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v32) = 0;
              v27 = GUID_NULL;
              LOWORD(v28) = 0;
              FormatRRASErrorString(&v32, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::UpdateIpv4AddrPool");
              v13 = &v27;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v13 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_1800710A0,
                &v32,
                v13,
                0,
                &v28);
            }
            v20 = 8;
            goto LABEL_29;
          }
          memcpy_0(v12, *((const void **)a2 + 1), v10);
        }
        else
        {
          v8 = 0;
          if ( (_QWORD)xmmword_1800710A0 )
          {
            LOWORD(v32) = 0;
            v27 = GUID_NULL;
            LOWORD(v28) = 0;
            FormatRRASErrorString(
              &v32,
              L"%s: No IPv4 address pool configured.",
              L"RRasRoutingDomainConfig::UpdateIpv4AddrPool");
            v9 = &v27;
            if ( this != (RRasRoutingDomainConfig *)-516LL )
              v9 = (GUID *)((char *)this + 516);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_1800710A0,
              &v32,
              v9,
              0,
              &v28);
          }
        }
        v14 = (void *)*((_QWORD *)this + 74);
        if ( v14 )
        {
          v15 = GetProcessHeap();
          HeapFree(v15, 0, v14);
          *((_QWORD *)this + 74) = 0;
        }
        *((_QWORD *)this + 73) = 0;
        *((_DWORD *)this + 147) = *((_DWORD *)a2 + 1);
        *((_QWORD *)this + 74) = v8;
        goto LABEL_29;
      }
      if ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL * i + 4) <= *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL * i) )
        break;
    }
    v20 = 87;
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_29;
    v6 = 3364;
LABEL_7:
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::UpdateIpv4AddrPool", v6);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v32);
  }
  else
  {
    v20 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      v6 = 3358;
      goto LABEL_7;
    }
  }
LABEL_29:
  v16 = v20;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v21);
  return v16;
}

```

## disassembly

```asm
0x180042d5c  mov     [rsp-8+arg_10], rbx
0x180042d61  push    rbp
0x180042d62  push    rsi
0x180042d63  push    rdi
0x180042d64  push    r14
0x180042d66  push    r15
0x180042d68  lea     rbp, [rsp-7D0h]
0x180042d70  sub     rsp, 8D0h
0x180042d77  mov     rax, cs:__security_cookie
0x180042d7e  xor     rax, rsp
0x180042d81  mov     [rbp+7F0h+var_30], rax
0x180042d88  mov     rdi, rdx
0x180042d8b  mov     rbx, rcx
0x180042d8e  xor     r15d, r15d
0x180042d91  mov     [rsp+8F0h+var_8B0], r15d
0x180042d96  mov     [rbp+7F0h+var_830], r15d
0x180042d9a  xor     edx, edx; Val
0x180042d9c  mov     r8d, 7FCh; Size
0x180042da2  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180042da6  call    memset_0
0x180042dab  mov     [rbp+7F0h+var_860], r15d
0x180042daf  xorps   xmm0, xmm0
0x180042db2  xor     eax, eax
0x180042db4  movups  [rbp+7F0h+var_85C], xmm0
0x180042db8  movups  [rbp+7F0h+var_84C], xmm0
0x180042dbc  mov     [rbp+7F0h+var_83C], eax
0x180042dbf  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180042dc5  mov     [rsp+8F0h+var_8A8], r15
0x180042dca  xorps   xmm1, xmm1
0x180042dcd  movdqu  [rsp+8F0h+var_890], xmm1
0x180042dd3  mov     [rsp+8F0h+var_880], r15
0x180042dd8  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x180042de0  mov     [rsp+8F0h+var_874], r15d
0x180042de5  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x180042dec  jz      short loc_180042E10
0x180042dee  lea     rax, [rbx+204h]
0x180042df5  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x180042dfa  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180042dff  lea     rdx, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x180042e06  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180042e0b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180042e10  mov     r9d, [rdi+4]
0x180042e14  test    r9d, r9d
0x180042e17  jz      short loc_180042E79
0x180042e19  cmp     [rdi+8], r15
0x180042e1d  jnz     short loc_180042E79
0x180042e1f  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x180042e27  cmp     qword ptr cs:xmmword_180071090, r15
0x180042e2e  jz      loc_18004302E
0x180042e34  mov     r9d, 0D1Eh
0x180042e3a  mov     word ptr [rbp+7F0h+var_830], r15w
0x180042e3f  lea     r8, aRrasroutingdom_19; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x180042e46  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180042e4d  lea     rcx, [rbp+7F0h+var_830]
0x180042e51  call    FormatRRASErrorString
0x180042e56  lea     r8, [rbp+7F0h+var_830]
0x180042e5a  mov     rdx, qword ptr cs:xmmword_180071090
0x180042e61  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042e68  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e74  jmp     loc_18004302E
0x180042e79  mov     r8d, r15d
0x180042e7c  cmp     r8d, r9d
0x180042e7f  jnb     short loc_180042EB3
0x180042e81  mov     edx, r8d
0x180042e84  mov     rcx, [rdi+8]
0x180042e88  mov     eax, [rcx+rdx*8]
0x180042e8b  cmp     [rcx+rdx*8+4], eax
0x180042e8f  jbe     short loc_180042E96
0x180042e91  inc     r8d
0x180042e94  jmp     short loc_180042E7C
0x180042e96  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x180042e9e  cmp     qword ptr cs:xmmword_180071090, r15
0x180042ea5  jz      loc_18004302E
0x180042eab  mov     r9d, 0D24h
0x180042eb1  jmp     short loc_180042E3A
0x180042eb3  test    r9d, r9d
0x180042eb6  jnz     loc_180042F3C
0x180042ebc  mov     rsi, r15
0x180042ebf  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180042ec6  jz      loc_180042FF0
0x180042ecc  mov     word ptr [rbp+7F0h+var_830], r15w
0x180042ed1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042ed8  movdqu  [rbp+7F0h+var_870], xmm0
0x180042edd  mov     word ptr [rbp+7F0h+var_860], r15w
0x180042ee2  lea     r8, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x180042ee9  lea     rdx, aSNoIpv4Address_0; "%s: No IPv4 address pool configured."
0x180042ef0  lea     rcx, [rbp+7F0h+var_830]
0x180042ef4  call    FormatRRASErrorString
0x180042ef9  lea     rcx, [rbx+204h]
0x180042f00  lea     r9, [rbp+7F0h+var_870]
0x180042f04  test    rcx, rcx
0x180042f07  cmovnz  r9, rcx
0x180042f0b  lea     rax, [rbp+7F0h+var_860]
0x180042f0f  mov     [rsp+8F0h+var_8C8], rax
0x180042f14  mov     [rsp+8F0h+var_8D0], r15
0x180042f19  lea     r8, [rbp+7F0h+var_830]
0x180042f1d  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042f24  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042f2b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180042f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f37  jmp     loc_180042FF0
0x180042f3c  lea     r14d, ds:0[r9*8]
0x180042f44  call    cs:__imp_GetProcessHeap
0x180042f4a  mov     rcx, rax; hHeap
0x180042f4d  mov     r8d, r14d; dwBytes
0x180042f50  mov     edx, 8; dwFlags
0x180042f55  call    cs:__imp_HeapAlloc
0x180042f5b  mov     rsi, rax
0x180042f5e  test    rax, rax
0x180042f61  jnz     short loc_180042FE1
0x180042f63  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180042f6a  jz      short loc_180042FD7
0x180042f6c  mov     word ptr [rbp+7F0h+var_830], r15w
0x180042f71  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042f78  movdqu  [rbp+7F0h+var_870], xmm0
0x180042f7d  mov     word ptr [rbp+7F0h+var_860], r15w
0x180042f82  lea     r8, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x180042f89  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180042f90  lea     rcx, [rbp+7F0h+var_830]
0x180042f94  call    FormatRRASErrorString
0x180042f99  lea     rcx, [rbx+204h]
0x180042fa0  lea     r9, [rbp+7F0h+var_870]
0x180042fa4  test    rcx, rcx
0x180042fa7  cmovnz  r9, rcx
0x180042fab  lea     rax, [rbp+7F0h+var_860]
0x180042faf  mov     [rsp+8F0h+var_8C8], rax
0x180042fb4  mov     [rsp+8F0h+var_8D0], r15
0x180042fb9  lea     r8, [rbp+7F0h+var_830]
0x180042fbd  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042fc4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042fcb  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180042fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fd7  mov     [rsp+8F0h+var_8B0], 8
0x180042fdf  jmp     short loc_18004302E
0x180042fe1  mov     r8, r14; Size
0x180042fe4  mov     rdx, [rdi+8]; Src
0x180042fe8  mov     rcx, rax; void *
0x180042feb  call    memcpy_0
0x180042ff0  mov     r14, [rbx+250h]
0x180042ff7  test    r14, r14
0x180042ffa  jz      short loc_180043017
0x180042ffc  call    cs:__imp_GetProcessHeap
0x180043002  mov     r8, r14; lpMem
0x180043005  xor     edx, edx; dwFlags
0x180043007  mov     rcx, rax; hHeap
0x18004300a  call    cs:__imp_HeapFree
0x180043010  mov     [rbx+250h], r15
0x180043017  mov     [rbx+248h], r15
0x18004301e  mov     eax, [rdi+4]
0x180043021  mov     [rbx+24Ch], eax
0x180043027  mov     [rbx+250h], rsi
0x18004302e  mov     ebx, [rsp+8F0h+var_8B0]
0x180043032  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180043037  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004303c  mov     eax, ebx
0x18004303e  mov     rcx, [rbp+7F0h+var_30]
0x180043045  xor     rcx, rsp; StackCookie
0x180043048  call    __security_check_cookie
0x18004304d  mov     rbx, [rsp+8F0h+arg_10]
0x180043055  add     rsp, 8D0h
0x18004305c  pop     r15
0x18004305e  pop     r14
0x180043060  pop     rdi
0x180043061  pop     rsi
0x180043062  pop     rbp
0x180043063  retn
```
