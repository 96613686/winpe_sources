# RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)

- ea: `0x180045668`
- end: `0x1800458b5`
- name: `?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, int, struct _MPRI_IPV4_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180044888`
- `0x180047ff4`

## callees

- `0x180045668`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x180051112`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800457bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800457bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800457c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800457c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457d2`

## string_xrefs

- `0x180045712`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x18004574b`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x1800457fd`: `RRasRoutingDomainConfig::CopyIpv4AddrPool`
- `0x180045752`: `%s: No IPv4 address pool configured.`

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
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
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
      if ( (_QWORD)xmmword_180078C60 )
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
          xmmword_180078C60,
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
    if ( (_QWORD)xmmword_180078C60 )
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
        xmmword_180078C60,
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
0x180045668  mov     [rsp-8+arg_8], rbx
0x18004566d  mov     [rsp-8+arg_18], rsi
0x180045672  push    rbp
0x180045673  push    rdi
0x180045674  push    r12
0x180045676  push    r14
0x180045678  push    r15
0x18004567a  lea     rbp, [rsp-7D0h]
0x180045682  sub     rsp, 8D0h
0x180045689  mov     rax, cs:__security_cookie
0x180045690  xor     rax, rsp
0x180045693  mov     [rbp+7F0h+var_30], rax
0x18004569a  mov     r15, r8
0x18004569d  mov     edi, edx
0x18004569f  mov     rsi, rcx
0x1800456a2  mov     [rsp+8F0h+var_8B0], 0
0x1800456aa  xor     eax, eax
0x1800456ac  mov     [rbp+7F0h+var_830], eax
0x1800456af  xor     edx, edx; Val
0x1800456b1  mov     r8d, 7FCh; Size
0x1800456b7  lea     rcx, [rbp+7F0h+var_82C]; void *
0x1800456bb  call    memset_0
0x1800456c0  xor     eax, eax
0x1800456c2  mov     [rbp+7F0h+var_860], eax
0x1800456c5  xorps   xmm0, xmm0
0x1800456c8  movups  [rbp+7F0h+var_85C], xmm0
0x1800456cc  movups  [rbp+7F0h+var_84C], xmm0
0x1800456d0  mov     [rbp+7F0h+var_83C], eax
0x1800456d3  movdqu  [rsp+8F0h+var_8A0], xmm0
0x1800456d9  mov     [rsp+8F0h+var_8A8], rax
0x1800456de  xorps   xmm1, xmm1
0x1800456e1  movdqu  [rsp+8F0h+var_890], xmm1
0x1800456e7  mov     [rsp+8F0h+var_880], rax
0x1800456ec  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x1800456f4  mov     [rsp+8F0h+var_874], eax
0x1800456f8  lea     r12, [rsi+204h]
0x1800456ff  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x180045706  jz      short loc_180045723
0x180045708  mov     [rsp+8F0h+var_8D0], r12; struct _GUID *
0x18004570d  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180045712  lea     rdx, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180045719  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004571e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180045723  mov     eax, [rsi+24Ch]
0x180045729  test    eax, eax
0x18004572b  jnz     short loc_1800457A7
0x18004572d  cmp     qword ptr cs:xmmword_180078C60, 0
0x180045735  jz      short loc_18004579D
0x180045737  mov     word ptr [rbp+7F0h+var_830], ax
0x18004573b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180045742  movdqu  [rbp+7F0h+var_870], xmm0
0x180045747  mov     word ptr [rbp+7F0h+var_860], ax
0x18004574b  lea     r8, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180045752  lea     rdx, aSNoIpv4Address_0; "%s: No IPv4 address pool configured."
0x180045759  lea     rcx, [rbp+7F0h+var_830]
0x18004575d  call    FormatRRASErrorString
0x180045762  lea     r9, [rbp+7F0h+var_870]
0x180045766  test    r12, r12
0x180045769  cmovnz  r9, r12
0x18004576d  lea     rax, [rbp+7F0h+var_860]
0x180045771  mov     [rsp+8F0h+var_8C8], rax
0x180045776  mov     [rsp+8F0h+var_8D0], 0
0x18004577f  lea     r8, [rbp+7F0h+var_830]
0x180045783  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004578a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180045791  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004579d  mov     ebx, 490h
0x1800457a2  jmp     loc_18004587E
0x1800457a7  shl     eax, 3
0x1800457aa  mov     r14d, eax
0x1800457ad  mov     ebx, 8
0x1800457b2  test    edi, edi
0x1800457b4  jz      short loc_1800457C4
0x1800457b6  mov     edx, r14d; uBytes
0x1800457b9  lea     ecx, [rbx+38h]; uFlags
0x1800457bc  call    cs:__imp_LocalAlloc
0x1800457c2  jmp     short loc_1800457D8
0x1800457c4  call    cs:__imp_GetProcessHeap
0x1800457ca  mov     rcx, rax; hHeap
0x1800457cd  mov     r8, r14; dwBytes
0x1800457d0  mov     edx, ebx; dwFlags
0x1800457d2  call    cs:__imp_HeapAlloc
0x1800457d8  mov     rdi, rax
0x1800457db  test    rax, rax
0x1800457de  jnz     short loc_180045851
0x1800457e0  cmp     qword ptr cs:xmmword_180078C60, rax
0x1800457e7  jz      short loc_18004584B
0x1800457e9  mov     word ptr [rbp+7F0h+var_830], ax
0x1800457ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800457f4  movdqu  [rbp+7F0h+var_870], xmm0
0x1800457f9  mov     word ptr [rbp+7F0h+var_860], ax
0x1800457fd  lea     r8, aRrasroutingdom_5; "RRasRoutingDomainConfig::CopyIpv4AddrPo"...
0x180045804  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18004580b  lea     rcx, [rbp+7F0h+var_830]
0x18004580f  call    FormatRRASErrorString
0x180045814  lea     r9, [rbp+7F0h+var_870]
0x180045818  test    r12, r12
0x18004581b  cmovnz  r9, r12
0x18004581f  lea     rax, [rbp+7F0h+var_860]
0x180045823  mov     [rsp+8F0h+var_8C8], rax
0x180045828  mov     [rsp+8F0h+var_8D0], rdi
0x18004582d  lea     r8, [rbp+7F0h+var_830]
0x180045831  mov     rdx, qword ptr cs:xmmword_180078C60
0x180045838  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004583f  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004584b  mov     [rsp+8F0h+var_8B0], ebx
0x18004584f  jmp     short loc_18004587E
0x180045851  mov     r8, r14; Size
0x180045854  mov     rdx, [rsi+250h]; Src
0x18004585b  mov     rcx, rdi; void *
0x18004585e  call    memcpy_0
0x180045863  mov     eax, [rsi+248h]
0x180045869  mov     [r15], eax
0x18004586c  mov     eax, [rsi+24Ch]
0x180045872  mov     [r15+4], eax
0x180045876  mov     [r15+8], rdi
0x18004587a  mov     ebx, [rsp+8F0h+var_8B0]
0x18004587e  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180045883  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180045888  mov     eax, ebx
0x18004588a  mov     rcx, [rbp+7F0h+var_30]
0x180045891  xor     rcx, rsp; StackCookie
0x180045894  call    __security_check_cookie
0x180045899  lea     r11, [rsp+8F0h+var_20]
0x1800458a1  mov     rbx, [r11+38h]
0x1800458a5  mov     rsi, [r11+48h]
0x1800458a9  mov     rsp, r11
0x1800458ac  pop     r15
0x1800458ae  pop     r14
0x1800458b0  pop     r12
0x1800458b2  pop     rdi
0x1800458b3  pop     rbp
0x1800458b4  retn
```
