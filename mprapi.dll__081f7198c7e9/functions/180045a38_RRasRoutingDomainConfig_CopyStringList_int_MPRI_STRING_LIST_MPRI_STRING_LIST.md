# RRasRoutingDomainConfig::CopyStringList(int,_MPRI_STRING_LIST *,_MPRI_STRING_LIST *)

- ea: `0x180045a38`
- end: `0x180045c0b`
- name: `?CopyStringList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_STRING_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_STRING_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180044e6c`
- `0x18004da50`

## callees

- `0x180045a38`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180045bcf`
- `msvcrt!memcpy_s` at `0x180045bcf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045b16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045b16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045b1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045b1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045b2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045b2f`

## string_xrefs

- `0x180045ae0`: `RRasRoutingDomainConfig::CopyStringList`
- `0x180045b5b`: `RRasRoutingDomainConfig::CopyStringList`

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
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
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
      if ( (_QWORD)xmmword_180078C60 )
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
          xmmword_180078C60,
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
0x180045a38  mov     [rsp-8+arg_8], rbx
0x180045a3d  push    rbp
0x180045a3e  push    rsi
0x180045a3f  push    rdi
0x180045a40  push    r14
0x180045a42  push    r15
0x180045a44  lea     rbp, [rsp-7D0h]
0x180045a4c  sub     rsp, 8D0h
0x180045a53  mov     rax, cs:__security_cookie
0x180045a5a  xor     rax, rsp
0x180045a5d  mov     [rbp+7F0h+var_30], rax
0x180045a64  mov     rsi, r9
0x180045a67  mov     rdi, r8
0x180045a6a  mov     r15d, edx
0x180045a6d  mov     r14, rcx
0x180045a70  mov     [rsp+8F0h+var_8B0], 0
0x180045a78  xor     eax, eax
0x180045a7a  mov     [rbp+7F0h+var_830], eax
0x180045a7d  xor     edx, edx; Val
0x180045a7f  mov     r8d, 7FCh; Size
0x180045a85  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180045a89  call    memset_0
0x180045a8e  xor     eax, eax
0x180045a90  mov     [rbp+7F0h+var_860], eax
0x180045a93  xorps   xmm0, xmm0
0x180045a96  movups  [rbp+7F0h+var_85C], xmm0
0x180045a9a  movups  [rbp+7F0h+var_84C], xmm0
0x180045a9e  mov     [rbp+7F0h+var_83C], eax
0x180045aa1  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180045aa7  mov     [rsp+8F0h+var_8A8], rax
0x180045aac  xorps   xmm1, xmm1
0x180045aaf  movdqu  [rsp+8F0h+var_890], xmm1
0x180045ab5  mov     [rsp+8F0h+var_880], rax
0x180045aba  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x180045ac2  mov     [rsp+8F0h+var_874], eax
0x180045ac6  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x180045acd  jz      short loc_180045AF1
0x180045acf  lea     rax, [r14+204h]
0x180045ad6  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x180045adb  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180045ae0  lea     rdx, aRrasroutingdom_34; "RRasRoutingDomainConfig::CopyStringList"
0x180045ae7  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180045aec  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180045af1  xorps   xmm0, xmm0
0x180045af4  movups  xmmword ptr [rsi], xmm0
0x180045af7  mov     eax, [rdi]
0x180045af9  mov     [rsi], eax
0x180045afb  cmp     dword ptr [rdi], 0
0x180045afe  jz      loc_180045BD5
0x180045b04  imul    ebx, [rdi], 402h
0x180045b0a  test    r15d, r15d
0x180045b0d  jz      short loc_180045B1E
0x180045b0f  mov     edx, ebx; uBytes
0x180045b11  mov     ecx, 40h ; '@'; uFlags
0x180045b16  call    cs:__imp_LocalAlloc
0x180045b1c  jmp     short loc_180045B35
0x180045b1e  call    cs:__imp_GetProcessHeap
0x180045b24  mov     rcx, rax; hHeap
0x180045b27  mov     r8, rbx; dwBytes
0x180045b2a  mov     edx, 8; dwFlags
0x180045b2f  call    cs:__imp_HeapAlloc
0x180045b35  test    rax, rax
0x180045b38  jnz     loc_180045BBE
0x180045b3e  cmp     qword ptr cs:xmmword_180078C60, rax
0x180045b45  jz      short loc_180045BB4
0x180045b47  mov     word ptr [rbp+7F0h+var_830], ax
0x180045b4b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180045b52  movdqu  [rbp+7F0h+var_870], xmm0
0x180045b57  mov     word ptr [rbp+7F0h+var_860], ax
0x180045b5b  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::CopyStringList"
0x180045b62  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180045b69  lea     rcx, [rbp+7F0h+var_830]
0x180045b6d  call    FormatRRASErrorString
0x180045b72  lea     rcx, [r14+204h]
0x180045b79  lea     r9, [rbp+7F0h+var_870]
0x180045b7d  test    rcx, rcx
0x180045b80  cmovnz  r9, rcx
0x180045b84  lea     rax, [rbp+7F0h+var_860]
0x180045b88  mov     [rsp+8F0h+var_8C8], rax
0x180045b8d  mov     [rsp+8F0h+var_8D0], 0
0x180045b96  lea     r8, [rbp+7F0h+var_830]
0x180045b9a  mov     rdx, qword ptr cs:xmmword_180078C60
0x180045ba1  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180045ba8  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bb4  mov     [rsp+8F0h+var_8B0], 8
0x180045bbc  jmp     short loc_180045BD5
0x180045bbe  mov     [rsi+8], rax
0x180045bc2  mov     r9, rbx; SourceSize
0x180045bc5  mov     r8, [rdi+8]; Source
0x180045bc9  mov     rdx, rbx; DestinationSize
0x180045bcc  mov     rcx, rax; Destination
0x180045bcf  call    cs:__imp_memcpy_s
0x180045bd5  mov     ebx, [rsp+8F0h+var_8B0]
0x180045bd9  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180045bde  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180045be3  mov     eax, ebx
0x180045be5  mov     rcx, [rbp+7F0h+var_30]
0x180045bec  xor     rcx, rsp; StackCookie
0x180045bef  call    __security_check_cookie
0x180045bf4  mov     rbx, [rsp+8F0h+arg_8]
0x180045bfc  add     rsp, 8D0h
0x180045c03  pop     r15
0x180045c05  pop     r14
0x180045c07  pop     rdi
0x180045c08  pop     rsi
0x180045c09  pop     rbp
0x180045c0a  retn
```
