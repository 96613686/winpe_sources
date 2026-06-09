# RRasRoutingDomainConfig::CopyStringList(int,_MPRI_STRING_LIST *,_MPRI_STRING_LIST *)

- ea: `0x18003a0a8`
- end: `0x18003a27b`
- name: `?CopyStringList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_STRING_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_STRING_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800394dc`
- `0x1800427d0`

## callees

- `0x18003a0a8`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003a23f`
- `msvcrt!memcpy_s` at `0x18003a23f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a19f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a19f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a186`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a186`
- `KERNEL32!GetProcessHeap` at `0x18003a18e`
- `KERNEL32!GetProcessHeap` at `0x18003a18e`

## string_xrefs

- `0x18003a150`: `RRasRoutingDomainConfig::CopyStringList`
- `0x18003a1cb`: `RRasRoutingDomainConfig::CopyStringList`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CopyStringList(
        RRasRoutingDomainConfig *this,
        int a2,
        const void *const *a3,
        struct _MPRI_STRING_LIST *a4)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  SIZE_T v9; // rbx
  HLOCAL v10; // rax
  HANDLE ProcessHeap; // rax
  GUID *v12; // r9
  unsigned int v13; // ebx
  unsigned __int16 *v15; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  GUID v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch]
  __int128 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+B4h] [rbp-4Ch]
  int v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v17 = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RRasRoutingDomainConfig::CopyStringList",
      &v17,
      v8,
      (struct _GUID *)((char *)this + 516),
      v15,
      v16);
  *(_OWORD *)a4 = 0;
  *(_DWORD *)a4 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 )
  {
    v9 = (unsigned int)(1026 * *(_DWORD *)a3);
    if ( a2 )
    {
      v10 = LocalAlloc(0x40u, (unsigned int)v9);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 8u, v9);
    }
    if ( v10 )
    {
      *((_QWORD *)a4 + 1) = v10;
      memcpy_s(v10, v9, a3[1], v9);
    }
    else
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v29) = 0;
        v24 = GUID_NULL;
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v29, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::CopyStringList");
        v12 = &v24;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v12 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v29,
          v12,
          0,
          &v25);
      }
      v17 = 8;
    }
  }
  v13 = v17;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v13;
}

```

## disassembly

```asm
0x18003a0a8  mov     [rsp-8+arg_8], rbx
0x18003a0ad  push    rbp
0x18003a0ae  push    rsi
0x18003a0af  push    rdi
0x18003a0b0  push    r14
0x18003a0b2  push    r15
0x18003a0b4  lea     rbp, [rsp-7D0h]
0x18003a0bc  sub     rsp, 8D0h
0x18003a0c3  mov     rax, cs:__security_cookie
0x18003a0ca  xor     rax, rsp
0x18003a0cd  mov     [rbp+7F0h+var_30], rax
0x18003a0d4  mov     rsi, r9
0x18003a0d7  mov     rdi, r8
0x18003a0da  mov     r15d, edx
0x18003a0dd  mov     r14, rcx
0x18003a0e0  mov     [rsp+8F0h+var_8B0], 0
0x18003a0e8  xor     eax, eax
0x18003a0ea  mov     [rbp+7F0h+var_830], eax
0x18003a0ed  xor     edx, edx; Val
0x18003a0ef  mov     r8d, 7FCh; Size
0x18003a0f5  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18003a0f9  call    memset_0
0x18003a0fe  xor     eax, eax
0x18003a100  mov     [rbp+7F0h+var_860], eax
0x18003a103  xorps   xmm0, xmm0
0x18003a106  movups  [rbp+7F0h+var_85C], xmm0
0x18003a10a  movups  [rbp+7F0h+var_84C], xmm0
0x18003a10e  mov     [rbp+7F0h+var_83C], eax
0x18003a111  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18003a117  mov     [rsp+8F0h+var_8A8], rax
0x18003a11c  xorps   xmm1, xmm1
0x18003a11f  movdqu  [rsp+8F0h+var_890], xmm1
0x18003a125  mov     [rsp+8F0h+var_880], rax
0x18003a12a  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18003a132  mov     [rsp+8F0h+var_874], eax
0x18003a136  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x18003a13d  jz      short loc_18003A161
0x18003a13f  lea     rax, [r14+204h]
0x18003a146  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x18003a14b  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18003a150  lea     rdx, aRrasroutingdom_35; "RRasRoutingDomainConfig::CopyStringList"
0x18003a157  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18003a15c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003a161  xorps   xmm0, xmm0
0x18003a164  movups  xmmword ptr [rsi], xmm0
0x18003a167  mov     eax, [rdi]
0x18003a169  mov     [rsi], eax
0x18003a16b  cmp     dword ptr [rdi], 0
0x18003a16e  jz      loc_18003A245
0x18003a174  imul    ebx, [rdi], 402h
0x18003a17a  test    r15d, r15d
0x18003a17d  jz      short loc_18003A18E
0x18003a17f  mov     edx, ebx; uBytes
0x18003a181  mov     ecx, 40h ; '@'; uFlags
0x18003a186  call    cs:__imp_LocalAlloc
0x18003a18c  jmp     short loc_18003A1A5
0x18003a18e  call    cs:__imp_GetProcessHeap
0x18003a194  mov     rcx, rax; hHeap
0x18003a197  mov     r8, rbx; dwBytes
0x18003a19a  mov     edx, 8; dwFlags
0x18003a19f  call    cs:__imp_HeapAlloc
0x18003a1a5  test    rax, rax
0x18003a1a8  jnz     loc_18003A22E
0x18003a1ae  cmp     qword ptr cs:xmmword_1800710A0, rax
0x18003a1b5  jz      short loc_18003A224
0x18003a1b7  mov     word ptr [rbp+7F0h+var_830], ax
0x18003a1bb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003a1c2  movdqu  [rbp+7F0h+var_870], xmm0
0x18003a1c7  mov     word ptr [rbp+7F0h+var_860], ax
0x18003a1cb  lea     r8, aRrasroutingdom_35; "RRasRoutingDomainConfig::CopyStringList"
0x18003a1d2  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18003a1d9  lea     rcx, [rbp+7F0h+var_830]
0x18003a1dd  call    FormatRRASErrorString
0x18003a1e2  lea     rcx, [r14+204h]
0x18003a1e9  lea     r9, [rbp+7F0h+var_870]
0x18003a1ed  test    rcx, rcx
0x18003a1f0  cmovnz  r9, rcx
0x18003a1f4  lea     rax, [rbp+7F0h+var_860]
0x18003a1f8  mov     [rsp+8F0h+var_8C8], rax
0x18003a1fd  mov     [rsp+8F0h+var_8D0], 0
0x18003a206  lea     r8, [rbp+7F0h+var_830]
0x18003a20a  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003a211  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003a218  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003a21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a224  mov     [rsp+8F0h+var_8B0], 8
0x18003a22c  jmp     short loc_18003A245
0x18003a22e  mov     [rsi+8], rax
0x18003a232  mov     r9, rbx; SourceSize
0x18003a235  mov     r8, [rdi+8]; Source
0x18003a239  mov     rdx, rbx; DestinationSize
0x18003a23c  mov     rcx, rax; Destination
0x18003a23f  call    cs:__imp_memcpy_s
0x18003a245  mov     ebx, [rsp+8F0h+var_8B0]
0x18003a249  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18003a24e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003a253  mov     eax, ebx
0x18003a255  mov     rcx, [rbp+7F0h+var_30]
0x18003a25c  xor     rcx, rsp; StackCookie
0x18003a25f  call    __security_check_cookie
0x18003a264  mov     rbx, [rsp+8F0h+arg_8]
0x18003a26c  add     rsp, 8D0h
0x18003a273  pop     r15
0x18003a275  pop     r14
0x18003a277  pop     rdi
0x18003a278  pop     rsi
0x18003a279  pop     rbp
0x18003a27a  retn
```
