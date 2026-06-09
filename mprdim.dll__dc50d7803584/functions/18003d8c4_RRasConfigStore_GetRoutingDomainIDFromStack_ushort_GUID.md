# RRasConfigStore::GetRoutingDomainIDFromStack(ushort *,_GUID *)

- ea: `0x18003d8c4`
- end: `0x18003daf5`
- name: `?GetRoutingDomainIDFromStack@RRasConfigStore@@AEAAKPEAGPEAU_GUID@@@Z`
- size: `561`
- prototype: `unsigned int(RRasConfigStore *__hidden this, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003dafc`

## callees

- `0x18003d8c4`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003da24`
- `msvcrt!_wcsicmp` at `0x18003da24`
- `NSI!NsiFreeTable` at `0x18003daba`
- `NSI!NsiFreeTable` at `0x18003daba`
- `NSI!NsiAllocateAndGetTable` at `0x18003d9b4`
- `NSI!NsiAllocateAndGetTable` at `0x18003d9b4`

## string_xrefs

- `0x18003d952`: `RRasConfigStore::GetRoutingDomainIDFromStack`
- `0x18003d9db`: `RRasConfigStore::GetRoutingDomainIDFromStack`
- `0x18003da6a`: `RRasConfigStore::GetRoutingDomainIDFromStack`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasConfigStore::GetRoutingDomainIDFromStack(
        RRasConfigStore *this,
        unsigned __int16 *a2,
        struct _GUID *a3)
{
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int Table; // eax
  __int64 v7; // rdx
  unsigned int i; // ebx
  bool v9; // zf
  __int64 v10; // rdi
  unsigned int v11; // ebx
  __int64 v13; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v15; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  __int64 v21; // [rsp+B0h] [rbp-50h]
  int v22; // [rsp+B8h] [rbp-48h]
  int v23; // [rsp+BCh] [rbp-44h]
  int v24; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RRasConfigStore::GetRoutingDomainIDFromStack",
      &v14,
      v5);
  Table = NsiAllocateAndGetTable(1, &NPI_MS_NDIS_MODULEID, 7, &v17, 4, &v16, 1640, 0, 0, 0, 0, &v15, 0);
  v14 = Table;
  if ( Table )
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v24) = 0;
      LODWORD(v13) = Table;
      FormatRRASErrorString(
        &v24,
        L"%s: NsiGetParameter failed while finding ID for routing domain %ws: %d.",
        L"RRasConfigStore::GetRoutingDomainIDFromStack",
        a2,
        v13);
      v7 = xmmword_180071090;
LABEL_14:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        v7,
        &v24);
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v9 = i == v15;
      if ( i >= v15 )
        break;
      v10 = 1640LL * i;
      if ( !_wcsicmp((const wchar_t *)(v10 + v16 + 1098), a2) )
      {
        *a3 = *(struct _GUID *)(v10 + v16 + 1080);
        v9 = i == v15;
        break;
      }
    }
    if ( v9 )
    {
      v14 = 1168;
      if ( *((_QWORD *)&xmmword_180071090 + 1) )
      {
        LOWORD(v24) = 0;
        LODWORD(v13) = 1168;
        FormatRRASErrorString(
          &v24,
          L"%s: No routing domain was found in stack with name %ws (%d).",
          L"RRasConfigStore::GetRoutingDomainIDFromStack",
          a2,
          v13);
        v7 = *((_QWORD *)&xmmword_180071090 + 1);
        goto LABEL_14;
      }
    }
  }
  if ( v17 || v16 )
    NsiFreeTable(v17, v16, 0, 0);
  v11 = v14;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v11;
}

```

## disassembly

```asm
0x18003d8c4  mov     [rsp-8+arg_0], rbx
0x18003d8c9  push    rbp
0x18003d8ca  push    rsi
0x18003d8cb  push    rdi
0x18003d8cc  push    r14
0x18003d8ce  push    r15
0x18003d8d0  lea     rbp, [rsp-7D0h]
0x18003d8d8  sub     rsp, 8D0h
0x18003d8df  mov     rax, cs:__security_cookie
0x18003d8e6  xor     rax, rsp
0x18003d8e9  mov     [rbp+7F0h+var_30], rax
0x18003d8f0  mov     r14, r8
0x18003d8f3  mov     rsi, rdx
0x18003d8f6  xor     r15d, r15d
0x18003d8f9  mov     [rsp+8F0h+var_880], r15d
0x18003d8fe  mov     [rsp+8F0h+var_87C], r15d
0x18003d903  mov     [rsp+8F0h+var_878], r15
0x18003d908  mov     [rbp+7F0h+var_870], r15
0x18003d90c  mov     [rbp+7F0h+var_830], r15d
0x18003d910  xor     edx, edx; Val
0x18003d912  mov     r8d, 7FCh; Size
0x18003d918  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18003d91c  call    memset_0
0x18003d921  xorps   xmm0, xmm0
0x18003d924  movdqu  [rbp+7F0h+var_860], xmm0
0x18003d929  mov     [rbp+7F0h+var_868], r15
0x18003d92d  xorps   xmm1, xmm1
0x18003d930  movdqu  [rbp+7F0h+var_850], xmm1
0x18003d935  mov     [rbp+7F0h+var_840], r15
0x18003d939  mov     [rbp+7F0h+var_838], 0FFFFFFFFh
0x18003d940  mov     [rbp+7F0h+var_834], r15d
0x18003d944  cmp     qword ptr cs:xmmword_180071090+8, r15
0x18003d94b  jz      short loc_18003D962
0x18003d94d  lea     r8, [rsp+8F0h+var_880]; unsigned int *
0x18003d952  lea     rdx, aRrasconfigstor_24; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x18003d959  lea     rcx, [rbp+7F0h+var_868]; this
0x18003d95d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003d962  mov     [rsp+8F0h+var_890], r15b
0x18003d967  lea     rax, [rsp+8F0h+var_87C]
0x18003d96c  mov     [rsp+8F0h+var_898], rax
0x18003d971  mov     [rsp+8F0h+var_8A0], r15d
0x18003d976  mov     [rsp+8F0h+var_8A8], r15
0x18003d97b  mov     [rsp+8F0h+var_8B0], r15d
0x18003d980  mov     [rsp+8F0h+var_8B8], r15
0x18003d985  mov     [rsp+8F0h+var_8C0], 668h
0x18003d98d  lea     rax, [rsp+8F0h+var_878]
0x18003d992  mov     [rsp+8F0h+var_8C8], rax
0x18003d997  mov     dword ptr [rsp+8F0h+var_8D0], 4
0x18003d99f  lea     r9, [rbp+7F0h+var_870]
0x18003d9a3  mov     r8d, 7
0x18003d9a9  lea     rdx, NPI_MS_NDIS_MODULEID
0x18003d9b0  lea     ecx, [r8-6]
0x18003d9b4  call    cs:__imp_NsiAllocateAndGetTable
0x18003d9ba  mov     [rsp+8F0h+var_880], eax
0x18003d9be  test    eax, eax
0x18003d9c0  jz      short loc_18003D9FE
0x18003d9c2  cmp     qword ptr cs:xmmword_180071090, r15
0x18003d9c9  jz      loc_18003DA9F
0x18003d9cf  mov     word ptr [rbp+7F0h+var_830], r15w
0x18003d9d4  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18003d9d8  mov     r9, rsi
0x18003d9db  lea     r8, aRrasconfigstor_24; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x18003d9e2  lea     rdx, aSNsigetparamet; "%s: NsiGetParameter failed while findin"...
0x18003d9e9  lea     rcx, [rbp+7F0h+var_830]
0x18003d9ed  call    FormatRRASErrorString
0x18003d9f2  mov     rdx, qword ptr cs:xmmword_180071090
0x18003d9f9  jmp     loc_18003DA88
0x18003d9fe  mov     ebx, r15d
0x18003da01  mov     eax, [rsp+8F0h+var_87C]
0x18003da05  cmp     ebx, eax
0x18003da07  jnb     short loc_18003DA4A
0x18003da09  mov     eax, ebx
0x18003da0b  imul    rdi, rax, 668h
0x18003da12  mov     rcx, [rsp+8F0h+var_878]
0x18003da17  add     rcx, 44Ah
0x18003da1e  add     rcx, rdi; String1
0x18003da21  mov     rdx, rsi; String2
0x18003da24  call    cs:__imp__wcsicmp
0x18003da2a  test    eax, eax
0x18003da2c  jz      short loc_18003DA32
0x18003da2e  inc     ebx
0x18003da30  jmp     short loc_18003DA01
0x18003da32  mov     rax, [rsp+8F0h+var_878]
0x18003da37  movups  xmm0, xmmword ptr [rdi+rax+438h]
0x18003da3f  movdqu  xmmword ptr [r14], xmm0
0x18003da44  mov     eax, [rsp+8F0h+var_87C]
0x18003da48  cmp     ebx, eax
0x18003da4a  jnz     short loc_18003DA9F
0x18003da4c  mov     ecx, 490h
0x18003da51  mov     [rsp+8F0h+var_880], ecx
0x18003da55  cmp     qword ptr cs:xmmword_180071090+8, r15
0x18003da5c  jz      short loc_18003DA9F
0x18003da5e  mov     word ptr [rbp+7F0h+var_830], r15w
0x18003da63  mov     dword ptr [rsp+8F0h+var_8D0], ecx
0x18003da67  mov     r9, rsi
0x18003da6a  lea     r8, aRrasconfigstor_24; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x18003da71  lea     rdx, aSNoRoutingDoma_2; "%s: No routing domain was found in stac"...
0x18003da78  lea     rcx, [rbp+7F0h+var_830]
0x18003da7c  call    FormatRRASErrorString
0x18003da81  mov     rdx, qword ptr cs:xmmword_180071090+8
0x18003da88  lea     r8, [rbp+7F0h+var_830]
0x18003da8c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003da93  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003da9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da9f  mov     rcx, [rbp+7F0h+var_870]
0x18003daa3  test    rcx, rcx
0x18003daa6  jnz     short loc_18003DAAF
0x18003daa8  cmp     [rsp+8F0h+var_878], r15
0x18003daad  jz      short loc_18003DAC0
0x18003daaf  xor     r9d, r9d
0x18003dab2  xor     r8d, r8d
0x18003dab5  mov     rdx, [rsp+8F0h+var_878]
0x18003daba  call    cs:__imp_NsiFreeTable
0x18003dac0  mov     ebx, [rsp+8F0h+var_880]
0x18003dac4  lea     rcx, [rbp+7F0h+var_868]; this
0x18003dac8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003dacd  mov     eax, ebx
0x18003dacf  mov     rcx, [rbp+7F0h+var_30]
0x18003dad6  xor     rcx, rsp; StackCookie
0x18003dad9  call    __security_check_cookie
0x18003dade  mov     rbx, [rsp+8F0h+arg_0]
0x18003dae6  add     rsp, 8D0h
0x18003daed  pop     r15
0x18003daef  pop     r14
0x18003daf1  pop     rdi
0x18003daf2  pop     rsi
0x18003daf3  pop     rbp
0x18003daf4  retn
```
