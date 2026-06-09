# RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)

- ea: `0x180045124`
- end: `0x1800452f7`
- name: `?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_IPV4_ADDRESS_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180044e6c`
- `0x18004da50`

## callees

- `0x180045124`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800452bb`
- `msvcrt!memcpy_s` at `0x1800452bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045202`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004520a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004520a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004521b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004521b`

## string_xrefs

- `0x1800451cc`: `RRasRoutingDomainConfig::CopyIPv4AddressList`
- `0x180045247`: `RRasRoutingDomainConfig::CopyIPv4AddressList`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CopyIPv4AddressList(
        RRasRoutingDomainConfig *this,
        int a2,
        const void *const *a3,
        struct _MPRI_IPV4_ADDRESS_LIST *a4)
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
      L"RRasRoutingDomainConfig::CopyIPv4AddressList",
      &v18,
      v8,
      (struct _GUID *)((char *)this + 516),
      v16,
      v17);
  *(_OWORD *)a4 = 0;
  *(_DWORD *)a4 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 )
  {
    v9 = 4 * *(_DWORD *)a3;
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
        FormatRRASErrorString(&v30, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::CopyIPv4AddressList");
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
0x180045124  mov     [rsp-8+arg_8], rbx
0x180045129  push    rbp
0x18004512a  push    rsi
0x18004512b  push    rdi
0x18004512c  push    r14
0x18004512e  push    r15
0x180045130  lea     rbp, [rsp-7D0h]
0x180045138  sub     rsp, 8D0h
0x18004513f  mov     rax, cs:__security_cookie
0x180045146  xor     rax, rsp
0x180045149  mov     [rbp+7F0h+var_30], rax
0x180045150  mov     rsi, r9
0x180045153  mov     rdi, r8
0x180045156  mov     r15d, edx
0x180045159  mov     r14, rcx
0x18004515c  mov     [rsp+8F0h+var_8B0], 0
0x180045164  xor     eax, eax
0x180045166  mov     [rbp+7F0h+var_830], eax
0x180045169  xor     edx, edx; Val
0x18004516b  mov     r8d, 7FCh; Size
0x180045171  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180045175  call    memset_0
0x18004517a  xor     eax, eax
0x18004517c  mov     [rbp+7F0h+var_860], eax
0x18004517f  xorps   xmm0, xmm0
0x180045182  movups  [rbp+7F0h+var_85C], xmm0
0x180045186  movups  [rbp+7F0h+var_84C], xmm0
0x18004518a  mov     [rbp+7F0h+var_83C], eax
0x18004518d  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180045193  mov     [rsp+8F0h+var_8A8], rax
0x180045198  xorps   xmm1, xmm1
0x18004519b  movdqu  [rsp+8F0h+var_890], xmm1
0x1800451a1  mov     [rsp+8F0h+var_880], rax
0x1800451a6  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x1800451ae  mov     [rsp+8F0h+var_874], eax
0x1800451b2  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x1800451b9  jz      short loc_1800451DD
0x1800451bb  lea     rax, [r14+204h]
0x1800451c2  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x1800451c7  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x1800451cc  lea     rdx, aRrasroutingdom_21; "RRasRoutingDomainConfig::CopyIPv4Addres"...
0x1800451d3  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800451d8  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800451dd  xorps   xmm0, xmm0
0x1800451e0  movups  xmmword ptr [rsi], xmm0
0x1800451e3  mov     eax, [rdi]
0x1800451e5  mov     [rsi], eax
0x1800451e7  mov     eax, [rdi]
0x1800451e9  test    eax, eax
0x1800451eb  jz      loc_1800452C1
0x1800451f1  shl     eax, 2
0x1800451f4  mov     ebx, eax
0x1800451f6  test    r15d, r15d
0x1800451f9  jz      short loc_18004520A
0x1800451fb  mov     edx, ebx; uBytes
0x1800451fd  mov     ecx, 40h ; '@'; uFlags
0x180045202  call    cs:__imp_LocalAlloc
0x180045208  jmp     short loc_180045221
0x18004520a  call    cs:__imp_GetProcessHeap
0x180045210  mov     rcx, rax; hHeap
0x180045213  mov     r8, rbx; dwBytes
0x180045216  mov     edx, 8; dwFlags
0x18004521b  call    cs:__imp_HeapAlloc
0x180045221  test    rax, rax
0x180045224  jnz     loc_1800452AA
0x18004522a  cmp     qword ptr cs:xmmword_180078C60, rax
0x180045231  jz      short loc_1800452A0
0x180045233  mov     word ptr [rbp+7F0h+var_830], ax
0x180045237  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004523e  movdqu  [rbp+7F0h+var_870], xmm0
0x180045243  mov     word ptr [rbp+7F0h+var_860], ax
0x180045247  lea     r8, aRrasroutingdom_21; "RRasRoutingDomainConfig::CopyIPv4Addres"...
0x18004524e  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180045255  lea     rcx, [rbp+7F0h+var_830]
0x180045259  call    FormatRRASErrorString
0x18004525e  lea     rcx, [r14+204h]
0x180045265  lea     r9, [rbp+7F0h+var_870]
0x180045269  test    rcx, rcx
0x18004526c  cmovnz  r9, rcx
0x180045270  lea     rax, [rbp+7F0h+var_860]
0x180045274  mov     [rsp+8F0h+var_8C8], rax
0x180045279  mov     [rsp+8F0h+var_8D0], 0
0x180045282  lea     r8, [rbp+7F0h+var_830]
0x180045286  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004528d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180045294  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004529b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452a0  mov     [rsp+8F0h+var_8B0], 8
0x1800452a8  jmp     short loc_1800452C1
0x1800452aa  mov     [rsi+8], rax
0x1800452ae  mov     r9, rbx; SourceSize
0x1800452b1  mov     r8, [rdi+8]; Source
0x1800452b5  mov     rdx, rbx; DestinationSize
0x1800452b8  mov     rcx, rax; Destination
0x1800452bb  call    cs:__imp_memcpy_s
0x1800452c1  mov     ebx, [rsp+8F0h+var_8B0]
0x1800452c5  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800452ca  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800452cf  mov     eax, ebx
0x1800452d1  mov     rcx, [rbp+7F0h+var_30]
0x1800452d8  xor     rcx, rsp; StackCookie
0x1800452db  call    __security_check_cookie
0x1800452e0  mov     rbx, [rsp+8F0h+arg_8]
0x1800452e8  add     rsp, 8D0h
0x1800452ef  pop     r15
0x1800452f1  pop     r14
0x1800452f3  pop     rdi
0x1800452f4  pop     rsi
0x1800452f5  pop     rbp
0x1800452f6  retn
```
