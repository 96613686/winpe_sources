# RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)

- ea: `0x180039970`
- end: `0x180039b43`
- name: `?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_IPV6_ADDRESS_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800394dc`
- `0x1800427d0`

## callees

- `0x180039970`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180039b07`
- `msvcrt!memcpy_s` at `0x180039b07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a4e`
- `KERNEL32!GetProcessHeap` at `0x180039a56`
- `KERNEL32!GetProcessHeap` at `0x180039a56`

## string_xrefs

- `0x180039a18`: `RRasRoutingDomainConfig::CopyIPv6AddressList`
- `0x180039a93`: `RRasRoutingDomainConfig::CopyIPv6AddressList`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CopyIPv6AddressList(
        RRasRoutingDomainConfig *this,
        int a2,
        const void *const *a3,
        struct _MPRI_IPV6_ADDRESS_LIST *a4)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v9; // eax
  SIZE_T v10; // rbx
  HLOCAL v11; // rax
  HANDLE ProcessHeap; // rax
  GUID *v13; // r9
  unsigned int v14; // ebx
  unsigned __int16 *v16; // [rsp+28h] [rbp-D8h]
  unsigned int v17; // [rsp+30h] [rbp-D0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  GUID v25; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+94h] [rbp-6Ch]
  __int128 v28; // [rsp+A4h] [rbp-5Ch]
  int v29; // [rsp+B4h] [rbp-4Ch]
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v18 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"RRasRoutingDomainConfig::CopyIPv6AddressList",
      &v18,
      v8,
      (struct _GUID *)((char *)this + 516),
      v16,
      v17);
  *(_OWORD *)a4 = 0;
  *(_DWORD *)a4 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 )
  {
    v9 = 16 * *(_DWORD *)a3;
    v10 = v9;
    if ( a2 )
    {
      v11 = LocalAlloc(0x40u, v9);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, v10);
    }
    if ( v11 )
    {
      *((_QWORD *)a4 + 1) = v11;
      memcpy_s(v11, v10, a3[1], v10);
    }
    else
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v30) = 0;
        v25 = GUID_NULL;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::CopyIPv6AddressList");
        v13 = &v25;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v13 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v30,
          v13,
          0,
          &v26);
      }
      v18 = 8;
    }
  }
  v14 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v14;
}

```

## disassembly

```asm
0x180039970  mov     [rsp-8+arg_8], rbx
0x180039975  push    rbp
0x180039976  push    rsi
0x180039977  push    rdi
0x180039978  push    r14
0x18003997a  push    r15
0x18003997c  lea     rbp, [rsp-7D0h]
0x180039984  sub     rsp, 8D0h
0x18003998b  mov     rax, cs:__security_cookie
0x180039992  xor     rax, rsp
0x180039995  mov     [rbp+7F0h+var_30], rax
0x18003999c  mov     rsi, r9
0x18003999f  mov     rdi, r8
0x1800399a2  mov     r15d, edx
0x1800399a5  mov     r14, rcx
0x1800399a8  mov     [rsp+8F0h+var_8B0], 0
0x1800399b0  xor     eax, eax
0x1800399b2  mov     [rbp+7F0h+var_830], eax
0x1800399b5  xor     edx, edx; Val
0x1800399b7  mov     r8d, 7FCh; Size
0x1800399bd  lea     rcx, [rbp+7F0h+var_82C]; void *
0x1800399c1  call    memset_0
0x1800399c6  xor     eax, eax
0x1800399c8  mov     [rbp+7F0h+var_860], eax
0x1800399cb  xorps   xmm0, xmm0
0x1800399ce  movups  [rbp+7F0h+var_85C], xmm0
0x1800399d2  movups  [rbp+7F0h+var_84C], xmm0
0x1800399d6  mov     [rbp+7F0h+var_83C], eax
0x1800399d9  movdqu  [rsp+8F0h+var_8A0], xmm0
0x1800399df  mov     [rsp+8F0h+var_8A8], rax
0x1800399e4  xorps   xmm1, xmm1
0x1800399e7  movdqu  [rsp+8F0h+var_890], xmm1
0x1800399ed  mov     [rsp+8F0h+var_880], rax
0x1800399f2  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x1800399fa  mov     [rsp+8F0h+var_874], eax
0x1800399fe  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180039a05  jz      short loc_180039A29
0x180039a07  lea     rax, [r14+204h]
0x180039a0e  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x180039a13  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180039a18  lea     rdx, aRrasroutingdom_9; "RRasRoutingDomainConfig::CopyIPv6Addres"...
0x180039a1f  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180039a24  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180039a29  xorps   xmm0, xmm0
0x180039a2c  movups  xmmword ptr [rsi], xmm0
0x180039a2f  mov     eax, [rdi]
0x180039a31  mov     [rsi], eax
0x180039a33  mov     eax, [rdi]
0x180039a35  test    eax, eax
0x180039a37  jz      loc_180039B0D
0x180039a3d  shl     eax, 4
0x180039a40  mov     ebx, eax
0x180039a42  test    r15d, r15d
0x180039a45  jz      short loc_180039A56
0x180039a47  mov     edx, ebx; uBytes
0x180039a49  mov     ecx, 40h ; '@'; uFlags
0x180039a4e  call    cs:__imp_LocalAlloc
0x180039a54  jmp     short loc_180039A6D
0x180039a56  call    cs:__imp_GetProcessHeap
0x180039a5c  mov     rcx, rax; hHeap
0x180039a5f  mov     r8, rbx; dwBytes
0x180039a62  mov     edx, 8; dwFlags
0x180039a67  call    cs:__imp_HeapAlloc
0x180039a6d  test    rax, rax
0x180039a70  jnz     loc_180039AF6
0x180039a76  cmp     qword ptr cs:xmmword_1800710A0, rax
0x180039a7d  jz      short loc_180039AEC
0x180039a7f  mov     word ptr [rbp+7F0h+var_830], ax
0x180039a83  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039a8a  movdqu  [rbp+7F0h+var_870], xmm0
0x180039a8f  mov     word ptr [rbp+7F0h+var_860], ax
0x180039a93  lea     r8, aRrasroutingdom_9; "RRasRoutingDomainConfig::CopyIPv6Addres"...
0x180039a9a  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180039aa1  lea     rcx, [rbp+7F0h+var_830]
0x180039aa5  call    FormatRRASErrorString
0x180039aaa  lea     rcx, [r14+204h]
0x180039ab1  lea     r9, [rbp+7F0h+var_870]
0x180039ab5  test    rcx, rcx
0x180039ab8  cmovnz  r9, rcx
0x180039abc  lea     rax, [rbp+7F0h+var_860]
0x180039ac0  mov     [rsp+8F0h+var_8C8], rax
0x180039ac5  mov     [rsp+8F0h+var_8D0], 0
0x180039ace  lea     r8, [rbp+7F0h+var_830]
0x180039ad2  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039ad9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039ae0  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aec  mov     [rsp+8F0h+var_8B0], 8
0x180039af4  jmp     short loc_180039B0D
0x180039af6  mov     [rsi+8], rax
0x180039afa  mov     r9, rbx; SourceSize
0x180039afd  mov     r8, [rdi+8]; Source
0x180039b01  mov     rdx, rbx; DestinationSize
0x180039b04  mov     rcx, rax; Destination
0x180039b07  call    cs:__imp_memcpy_s
0x180039b0d  mov     ebx, [rsp+8F0h+var_8B0]
0x180039b11  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180039b16  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180039b1b  mov     eax, ebx
0x180039b1d  mov     rcx, [rbp+7F0h+var_30]
0x180039b24  xor     rcx, rsp; StackCookie
0x180039b27  call    __security_check_cookie
0x180039b2c  mov     rbx, [rsp+8F0h+arg_8]
0x180039b34  add     rsp, 8D0h
0x180039b3b  pop     r15
0x180039b3d  pop     r14
0x180039b3f  pop     rdi
0x180039b40  pop     rsi
0x180039b41  pop     rbp
0x180039b42  retn
```
