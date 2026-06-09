# RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)

- ea: `0x180039cd8`
- end: `0x180039f25`
- name: `?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, struct _MPRI_IPV4_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038f98`
- `0x18003c810`

## callees

- `0x180039cd8`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e12`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039e2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039e2c`
- `KERNEL32!GetProcessHeap` at `0x180039e34`
- `KERNEL32!GetProcessHeap` at `0x180039e34`

## string_xrefs

- `0x180039d82`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x180039dbb`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x180039e6d`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x180039dc2`: `%s: No IPv4 address pool configured.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CopyIpv4AddrPool(
        RRasRoutingDomainConfig *this,
        int a2,
        struct _MPRI_IPV4_CONFIG_1 *a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v7; // eax
  GUID *v8; // r9
  unsigned int v9; // ebx
  unsigned int v10; // eax
  SIZE_T v11; // r14
  HLOCAL v12; // rax
  HANDLE ProcessHeap; // rax
  HLOCAL v14; // rdi
  GUID *v15; // r9
  unsigned __int16 *v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+7Ch] [rbp-84h]
  GUID v26; // [rsp+80h] [rbp-80h] BYREF
  int v27; // [rsp+90h] [rbp-70h] BYREF
  __int128 v28; // [rsp+94h] [rbp-6Ch]
  __int128 v29; // [rsp+A4h] [rbp-5Ch]
  int v30; // [rsp+B4h] [rbp-4Ch]
  int v31; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v19 = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = -1;
  v25 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v20,
      L"RRasRoutingDomainConfig::CopyIpv4AddrPool",
      &v19,
      v6,
      (struct _GUID *)((char *)this + 516),
      v17,
      v18);
  v7 = *((_DWORD *)this + 147);
  if ( v7 )
  {
    v10 = 8 * v7;
    v11 = v10;
    v9 = 8;
    if ( a2 )
    {
      v12 = LocalAlloc(0x40u, v10);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v12 = HeapAlloc(ProcessHeap, 8u, v11);
    }
    v14 = v12;
    if ( v12 )
    {
      memcpy_0(v12, *((const void **)this + 74), v11);
      *(_DWORD *)a3 = *((_DWORD *)this + 146);
      *((_DWORD *)a3 + 1) = *((_DWORD *)this + 147);
      *((_QWORD *)a3 + 1) = v14;
      v9 = v19;
    }
    else
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v31) = 0;
        v26 = GUID_NULL;
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v31, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::CopyIpv4AddrPool");
        v15 = &v26;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v15 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v31,
          v15,
          0,
          &v27);
      }
      v19 = 8;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v31) = *((_DWORD *)this + 147);
      v26 = GUID_NULL;
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v31, L"%s: No IPv4 address pool configured.", L"RRasRoutingDomainConfig::CopyIpv4AddrPool");
      v8 = &v26;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v8 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_1800710A0,
        &v31,
        v8,
        0,
        &v27);
    }
    v9 = 1168;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v20);
  return v9;
}

```

## disassembly

```asm
0x180039cd8  mov     [rsp-8+arg_8], rbx
0x180039cdd  mov     [rsp-8+arg_18], rsi
0x180039ce2  push    rbp
0x180039ce3  push    rdi
0x180039ce4  push    r12
0x180039ce6  push    r14
0x180039ce8  push    r15
0x180039cea  lea     rbp, [rsp-7D0h]
0x180039cf2  sub     rsp, 8D0h
0x180039cf9  mov     rax, cs:__security_cookie
0x180039d00  xor     rax, rsp
0x180039d03  mov     [rbp+7F0h+var_30], rax
0x180039d0a  mov     r15, r8
0x180039d0d  mov     edi, edx
0x180039d0f  mov     rsi, rcx
0x180039d12  mov     [rsp+8F0h+var_8B0], 0
0x180039d1a  xor     eax, eax
0x180039d1c  mov     [rbp+7F0h+var_830], eax
0x180039d1f  xor     edx, edx; Val
0x180039d21  mov     r8d, 7FCh; Size
0x180039d27  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180039d2b  call    memset_0
0x180039d30  xor     eax, eax
0x180039d32  mov     [rbp+7F0h+var_860], eax
0x180039d35  xorps   xmm0, xmm0
0x180039d38  movups  [rbp+7F0h+var_85C], xmm0
0x180039d3c  movups  [rbp+7F0h+var_84C], xmm0
0x180039d40  mov     [rbp+7F0h+var_83C], eax
0x180039d43  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180039d49  mov     [rsp+8F0h+var_8A8], rax
0x180039d4e  xorps   xmm1, xmm1
0x180039d51  movdqu  [rsp+8F0h+var_890], xmm1
0x180039d57  mov     [rsp+8F0h+var_880], rax
0x180039d5c  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x180039d64  mov     [rsp+8F0h+var_874], eax
0x180039d68  lea     r12, [rsi+204h]
0x180039d6f  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180039d76  jz      short loc_180039D93
0x180039d78  mov     [rsp+8F0h+var_8D0], r12; struct _GUID *
0x180039d7d  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180039d82  lea     rdx, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180039d89  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180039d8e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180039d93  mov     eax, [rsi+24Ch]
0x180039d99  test    eax, eax
0x180039d9b  jnz     short loc_180039E17
0x180039d9d  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180039da5  jz      short loc_180039E0D
0x180039da7  mov     word ptr [rbp+7F0h+var_830], ax
0x180039dab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039db2  movdqu  [rbp+7F0h+var_870], xmm0
0x180039db7  mov     word ptr [rbp+7F0h+var_860], ax
0x180039dbb  lea     r8, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180039dc2  lea     rdx, aSNoIpv4Address_0; "%s: No IPv4 address pool configured."
0x180039dc9  lea     rcx, [rbp+7F0h+var_830]
0x180039dcd  call    FormatRRASErrorString
0x180039dd2  lea     r9, [rbp+7F0h+var_870]
0x180039dd6  test    r12, r12
0x180039dd9  cmovnz  r9, r12
0x180039ddd  lea     rax, [rbp+7F0h+var_860]
0x180039de1  mov     [rsp+8F0h+var_8C8], rax
0x180039de6  mov     [rsp+8F0h+var_8D0], 0
0x180039def  lea     r8, [rbp+7F0h+var_830]
0x180039df3  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039dfa  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039e01  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e0d  mov     ebx, 490h
0x180039e12  jmp     loc_180039EEE
0x180039e17  shl     eax, 3
0x180039e1a  mov     r14d, eax
0x180039e1d  mov     ebx, 8
0x180039e22  test    edi, edi
0x180039e24  jz      short loc_180039E34
0x180039e26  mov     edx, r14d; uBytes
0x180039e29  lea     ecx, [rbx+38h]; uFlags
0x180039e2c  call    cs:__imp_LocalAlloc
0x180039e32  jmp     short loc_180039E48
0x180039e34  call    cs:__imp_GetProcessHeap
0x180039e3a  mov     rcx, rax; hHeap
0x180039e3d  mov     r8, r14; dwBytes
0x180039e40  mov     edx, ebx; dwFlags
0x180039e42  call    cs:__imp_HeapAlloc
0x180039e48  mov     rdi, rax
0x180039e4b  test    rax, rax
0x180039e4e  jnz     short loc_180039EC1
0x180039e50  cmp     qword ptr cs:xmmword_1800710A0, rax
0x180039e57  jz      short loc_180039EBB
0x180039e59  mov     word ptr [rbp+7F0h+var_830], ax
0x180039e5d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039e64  movdqu  [rbp+7F0h+var_870], xmm0
0x180039e69  mov     word ptr [rbp+7F0h+var_860], ax
0x180039e6d  lea     r8, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180039e74  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180039e7b  lea     rcx, [rbp+7F0h+var_830]
0x180039e7f  call    FormatRRASErrorString
0x180039e84  lea     r9, [rbp+7F0h+var_870]
0x180039e88  test    r12, r12
0x180039e8b  cmovnz  r9, r12
0x180039e8f  lea     rax, [rbp+7F0h+var_860]
0x180039e93  mov     [rsp+8F0h+var_8C8], rax
0x180039e98  mov     [rsp+8F0h+var_8D0], rdi
0x180039e9d  lea     r8, [rbp+7F0h+var_830]
0x180039ea1  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039ea8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039eaf  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ebb  mov     [rsp+8F0h+var_8B0], ebx
0x180039ebf  jmp     short loc_180039EEE
0x180039ec1  mov     r8, r14; Size
0x180039ec4  mov     rdx, [rsi+250h]; Src
0x180039ecb  mov     rcx, rdi; void *
0x180039ece  call    memcpy_0
0x180039ed3  mov     eax, [rsi+248h]
0x180039ed9  mov     [r15], eax
0x180039edc  mov     eax, [rsi+24Ch]
0x180039ee2  mov     [r15+4], eax
0x180039ee6  mov     [r15+8], rdi
0x180039eea  mov     ebx, [rsp+8F0h+var_8B0]
0x180039eee  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180039ef3  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180039ef8  mov     eax, ebx
0x180039efa  mov     rcx, [rbp+7F0h+var_30]
0x180039f01  xor     rcx, rsp; StackCookie
0x180039f04  call    __security_check_cookie
0x180039f09  lea     r11, [rsp+8F0h+var_20]
0x180039f11  mov     rbx, [r11+38h]
0x180039f15  mov     rsi, [r11+48h]
0x180039f19  mov     rsp, r11
0x180039f1c  pop     r15
0x180039f1e  pop     r14
0x180039f20  pop     r12
0x180039f22  pop     rdi
0x180039f23  pop     rbp
0x180039f24  retn
```
