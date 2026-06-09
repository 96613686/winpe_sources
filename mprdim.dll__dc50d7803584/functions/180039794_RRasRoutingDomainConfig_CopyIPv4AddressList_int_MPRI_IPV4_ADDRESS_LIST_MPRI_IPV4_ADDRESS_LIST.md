# RRasRoutingDomainConfig::CopyIPv4AddressList(int,_MPRI_IPV4_ADDRESS_LIST *,_MPRI_IPV4_ADDRESS_LIST *)

- ea: `0x180039794`
- end: `0x180039967`
- name: `?CopyIPv4AddressList@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_ADDRESS_LIST@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, const void *const *, struct _MPRI_IPV4_ADDRESS_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800394dc`
- `0x1800427d0`

## callees

- `0x180039794`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003992b`
- `msvcrt!memcpy_s` at `0x18003992b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003988b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003988b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039872`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039872`
- `KERNEL32!GetProcessHeap` at `0x18003987a`
- `KERNEL32!GetProcessHeap` at `0x18003987a`

## string_xrefs

- `0x18003983c`: `RRasRoutingDomainConfig::CopyIPv4AddressList`
- `0x1800398b7`: `RRasRoutingDomainConfig::CopyIPv4AddressList`

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
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
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
      if ( (_QWORD)xmmword_1800710A0 )
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
0x180039794  mov     [rsp-8+arg_8], rbx
0x180039799  push    rbp
0x18003979a  push    rsi
0x18003979b  push    rdi
0x18003979c  push    r14
0x18003979e  push    r15
0x1800397a0  lea     rbp, [rsp-7D0h]
0x1800397a8  sub     rsp, 8D0h
0x1800397af  mov     rax, cs:__security_cookie
0x1800397b6  xor     rax, rsp
0x1800397b9  mov     [rbp+7F0h+var_30], rax
0x1800397c0  mov     rsi, r9
0x1800397c3  mov     rdi, r8
0x1800397c6  mov     r15d, edx
0x1800397c9  mov     r14, rcx
0x1800397cc  mov     [rsp+8F0h+var_8B0], 0
0x1800397d4  xor     eax, eax
0x1800397d6  mov     [rbp+7F0h+var_830], eax
0x1800397d9  xor     edx, edx; Val
0x1800397db  mov     r8d, 7FCh; Size
0x1800397e1  lea     rcx, [rbp+7F0h+var_82C]; void *
0x1800397e5  call    memset_0
0x1800397ea  xor     eax, eax
0x1800397ec  mov     [rbp+7F0h+var_860], eax
0x1800397ef  xorps   xmm0, xmm0
0x1800397f2  movups  [rbp+7F0h+var_85C], xmm0
0x1800397f6  movups  [rbp+7F0h+var_84C], xmm0
0x1800397fa  mov     [rbp+7F0h+var_83C], eax
0x1800397fd  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180039803  mov     [rsp+8F0h+var_8A8], rax
0x180039808  xorps   xmm1, xmm1
0x18003980b  movdqu  [rsp+8F0h+var_890], xmm1
0x180039811  mov     [rsp+8F0h+var_880], rax
0x180039816  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18003981e  mov     [rsp+8F0h+var_874], eax
0x180039822  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180039829  jz      short loc_18003984D
0x18003982b  lea     rax, [r14+204h]
0x180039832  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x180039837  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18003983c  lea     rdx, aRrasroutingdom_21; "RRasRoutingDomainConfig::CopyIPv4Addres"...
0x180039843  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180039848  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003984d  xorps   xmm0, xmm0
0x180039850  movups  xmmword ptr [rsi], xmm0
0x180039853  mov     eax, [rdi]
0x180039855  mov     [rsi], eax
0x180039857  mov     eax, [rdi]
0x180039859  test    eax, eax
0x18003985b  jz      loc_180039931
0x180039861  shl     eax, 2
0x180039864  mov     ebx, eax
0x180039866  test    r15d, r15d
0x180039869  jz      short loc_18003987A
0x18003986b  mov     edx, ebx; uBytes
0x18003986d  mov     ecx, 40h ; '@'; uFlags
0x180039872  call    cs:__imp_LocalAlloc
0x180039878  jmp     short loc_180039891
0x18003987a  call    cs:__imp_GetProcessHeap
0x180039880  mov     rcx, rax; hHeap
0x180039883  mov     r8, rbx; dwBytes
0x180039886  mov     edx, 8; dwFlags
0x18003988b  call    cs:__imp_HeapAlloc
0x180039891  test    rax, rax
0x180039894  jnz     loc_18003991A
0x18003989a  cmp     qword ptr cs:xmmword_1800710A0, rax
0x1800398a1  jz      short loc_180039910
0x1800398a3  mov     word ptr [rbp+7F0h+var_830], ax
0x1800398a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800398ae  movdqu  [rbp+7F0h+var_870], xmm0
0x1800398b3  mov     word ptr [rbp+7F0h+var_860], ax
0x1800398b7  lea     r8, aRrasroutingdom_21; "RRasRoutingDomainConfig::CopyIPv4Addres"...
0x1800398be  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x1800398c5  lea     rcx, [rbp+7F0h+var_830]
0x1800398c9  call    FormatRRASErrorString
0x1800398ce  lea     rcx, [r14+204h]
0x1800398d5  lea     r9, [rbp+7F0h+var_870]
0x1800398d9  test    rcx, rcx
0x1800398dc  cmovnz  r9, rcx
0x1800398e0  lea     rax, [rbp+7F0h+var_860]
0x1800398e4  mov     [rsp+8F0h+var_8C8], rax
0x1800398e9  mov     [rsp+8F0h+var_8D0], 0
0x1800398f2  lea     r8, [rbp+7F0h+var_830]
0x1800398f6  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800398fd  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039904  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003990b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039910  mov     [rsp+8F0h+var_8B0], 8
0x180039918  jmp     short loc_180039931
0x18003991a  mov     [rsi+8], rax
0x18003991e  mov     r9, rbx; SourceSize
0x180039921  mov     r8, [rdi+8]; Source
0x180039925  mov     rdx, rbx; DestinationSize
0x180039928  mov     rcx, rax; Destination
0x18003992b  call    cs:__imp_memcpy_s
0x180039931  mov     ebx, [rsp+8F0h+var_8B0]
0x180039935  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18003993a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003993f  mov     eax, ebx
0x180039941  mov     rcx, [rbp+7F0h+var_30]
0x180039948  xor     rcx, rsp; StackCookie
0x18003994b  call    __security_check_cookie
0x180039950  mov     rbx, [rsp+8F0h+arg_8]
0x180039958  add     rsp, 8D0h
0x18003995f  pop     r15
0x180039961  pop     r14
0x180039963  pop     rdi
0x180039964  pop     rsi
0x180039965  pop     rbp
0x180039966  retn
```
