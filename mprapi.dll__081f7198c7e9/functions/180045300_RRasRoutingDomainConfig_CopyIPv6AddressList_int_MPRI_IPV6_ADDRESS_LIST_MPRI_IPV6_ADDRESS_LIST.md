# RRasRoutingDomainConfig::CopyIPv6AddressList(int,_MPRI_IPV6_ADDRESS_LIST *,_MPRI_IPV6_ADDRESS_LIST *)

- ea: `0x180045300`
- end: `0x1800454d3`
- name: `?CopyIPv6AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV6_ADDRESS_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_IPV6_ADDRESS_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180044e6c`
- `0x18004da50`

## callees

- `0x180045300`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180045497`
- `msvcrt!memcpy_s` at `0x180045497`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800453de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800453de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800453f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800453f7`

## string_xrefs

- `0x1800453a8`: `RRasRoutingDomainConfig::CopyIPv6AddressList`
- `0x180045423`: `RRasRoutingDomainConfig::CopyIPv6AddressList`

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
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
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
      if ( (_QWORD)xmmword_180078C60 )
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
          xmmword_180078C60,
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
0x180045300  mov     [rsp-8+arg_8], rbx
0x180045305  push    rbp
0x180045306  push    rsi
0x180045307  push    rdi
0x180045308  push    r14
0x18004530a  push    r15
0x18004530c  lea     rbp, [rsp-7D0h]
0x180045314  sub     rsp, 8D0h
0x18004531b  mov     rax, cs:__security_cookie
0x180045322  xor     rax, rsp
0x180045325  mov     [rbp+7F0h+var_30], rax
0x18004532c  mov     rsi, r9
0x18004532f  mov     rdi, r8
0x180045332  mov     r15d, edx
0x180045335  mov     r14, rcx
0x180045338  mov     [rsp+8F0h+var_8B0], 0
0x180045340  xor     eax, eax
0x180045342  mov     [rbp+7F0h+var_830], eax
0x180045345  xor     edx, edx; Val
0x180045347  mov     r8d, 7FCh; Size
0x18004534d  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180045351  call    memset_0
0x180045356  xor     eax, eax
0x180045358  mov     [rbp+7F0h+var_860], eax
0x18004535b  xorps   xmm0, xmm0
0x18004535e  movups  [rbp+7F0h+var_85C], xmm0
0x180045362  movups  [rbp+7F0h+var_84C], xmm0
0x180045366  mov     [rbp+7F0h+var_83C], eax
0x180045369  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18004536f  mov     [rsp+8F0h+var_8A8], rax
0x180045374  xorps   xmm1, xmm1
0x180045377  movdqu  [rsp+8F0h+var_890], xmm1
0x18004537d  mov     [rsp+8F0h+var_880], rax
0x180045382  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18004538a  mov     [rsp+8F0h+var_874], eax
0x18004538e  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x180045395  jz      short loc_1800453B9
0x180045397  lea     rax, [r14+204h]
0x18004539e  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x1800453a3  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x1800453a8  lea     rdx, aRrasroutingdom_9; "RRasRoutingDomainConfig::CopyIPv6Addres"...
0x1800453af  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800453b4  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800453b9  xorps   xmm0, xmm0
0x1800453bc  movups  xmmword ptr [rsi], xmm0
0x1800453bf  mov     eax, [rdi]
0x1800453c1  mov     [rsi], eax
0x1800453c3  mov     eax, [rdi]
0x1800453c5  test    eax, eax
0x1800453c7  jz      loc_18004549D
0x1800453cd  shl     eax, 4
0x1800453d0  mov     ebx, eax
0x1800453d2  test    r15d, r15d
0x1800453d5  jz      short loc_1800453E6
0x1800453d7  mov     edx, ebx; uBytes
0x1800453d9  mov     ecx, 40h ; '@'; uFlags
0x1800453de  call    cs:__imp_LocalAlloc
0x1800453e4  jmp     short loc_1800453FD
0x1800453e6  call    cs:__imp_GetProcessHeap
0x1800453ec  mov     rcx, rax; hHeap
0x1800453ef  mov     r8, rbx; dwBytes
0x1800453f2  mov     edx, 8; dwFlags
0x1800453f7  call    cs:__imp_HeapAlloc
0x1800453fd  test    rax, rax
0x180045400  jnz     loc_180045486
0x180045406  cmp     qword ptr cs:xmmword_180078C60, rax
0x18004540d  jz      short loc_18004547C
0x18004540f  mov     word ptr [rbp+7F0h+var_830], ax
0x180045413  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004541a  movdqu  [rbp+7F0h+var_870], xmm0
0x18004541f  mov     word ptr [rbp+7F0h+var_860], ax
0x180045423  lea     r8, aRrasroutingdom_9; "RRasRoutingDomainConfig::CopyIPv6Addres"...
0x18004542a  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180045431  lea     rcx, [rbp+7F0h+var_830]
0x180045435  call    FormatRRASErrorString
0x18004543a  lea     rcx, [r14+204h]
0x180045441  lea     r9, [rbp+7F0h+var_870]
0x180045445  test    rcx, rcx
0x180045448  cmovnz  r9, rcx
0x18004544c  lea     rax, [rbp+7F0h+var_860]
0x180045450  mov     [rsp+8F0h+var_8C8], rax
0x180045455  mov     [rsp+8F0h+var_8D0], 0
0x18004545e  lea     r8, [rbp+7F0h+var_830]
0x180045462  mov     rdx, qword ptr cs:xmmword_180078C60
0x180045469  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180045470  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004547c  mov     [rsp+8F0h+var_8B0], 8
0x180045484  jmp     short loc_18004549D
0x180045486  mov     [rsi+8], rax
0x18004548a  mov     r9, rbx; SourceSize
0x18004548d  mov     r8, [rdi+8]; Source
0x180045491  mov     rdx, rbx; DestinationSize
0x180045494  mov     rcx, rax; Destination
0x180045497  call    cs:__imp_memcpy_s
0x18004549d  mov     ebx, [rsp+8F0h+var_8B0]
0x1800454a1  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800454a6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800454ab  mov     eax, ebx
0x1800454ad  mov     rcx, [rbp+7F0h+var_30]
0x1800454b4  xor     rcx, rsp; StackCookie
0x1800454b7  call    __security_check_cookie
0x1800454bc  mov     rbx, [rsp+8F0h+arg_8]
0x1800454c4  add     rsp, 8D0h
0x1800454cb  pop     r15
0x1800454cd  pop     r14
0x1800454cf  pop     rdi
0x1800454d0  pop     rsi
0x1800454d1  pop     rbp
0x1800454d2  retn
```
