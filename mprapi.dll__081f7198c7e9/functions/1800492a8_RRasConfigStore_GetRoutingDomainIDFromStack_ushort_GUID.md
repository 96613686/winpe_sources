# RRasConfigStore::GetRoutingDomainIDFromStack(ushort *,_GUID *)

- ea: `0x1800492a8`
- end: `0x1800494e1`
- name: `?GetRoutingDomainIDFromStack@RRasConfigStore@@AEAAKPEAGPEAU_GUID@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(RRasConfigStore *this, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800494e8`

## callees

- `0x1800492a8`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180049408`
- `msvcrt!_wcsicmp` at `0x180049408`
- `NSI!NsiAllocateAndGetTable` at `0x180049398`
- `NSI!NsiAllocateAndGetTable` at `0x180049398`
- `NSI!NsiFreeTable` at `0x1800494a6`
- `NSI!NsiFreeTable` at `0x1800494a6`

## string_xrefs

- `0x180049336`: `RRasConfigStore::GetRoutingDomainIDFromStack`
- `0x1800493bf`: `RRasConfigStore::GetRoutingDomainIDFromStack`
- `0x180049456`: `RRasConfigStore::GetRoutingDomainIDFromStack`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainIDFromStack(
        RRasConfigStore *this,
        unsigned __int16 *a2,
        struct _GUID *a3)
{
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int Table; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int v9; // eax
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

  v15 = 0;
  v14 = 0;
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
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RRasConfigStore::GetRoutingDomainIDFromStack",
      &v15,
      v5);
  Table = NsiAllocateAndGetTable(1, &NPI_MS_NDIS_MODULEID, 7, &v17, 4, &v16, 1640, 0, 0, 0, 0, &v14, 0);
  v15 = Table;
  if ( Table )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v24) = 0;
      LODWORD(v13) = Table;
      FormatRRASErrorString(
        &v24,
        L"%s: NsiGetParameter failed while finding ID for routing domain %ws: %d.",
        L"RRasConfigStore::GetRoutingDomainIDFromStack",
        a2,
        v13);
      v7 = xmmword_180078C50;
LABEL_14:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        v7,
        &v24);
    }
  }
  else
  {
    v8 = 0;
    v9 = v14;
    if ( v14 )
    {
      while ( 1 )
      {
        v10 = 1640LL * v8;
        if ( !_wcsicmp((const wchar_t *)(v10 + v16 + 1098), a2) )
          break;
        ++v8;
        v9 = v14;
        if ( v8 >= v14 )
          goto LABEL_11;
      }
      *a3 = *(struct _GUID *)(v10 + v16 + 1080);
      v9 = v14;
    }
LABEL_11:
    if ( v8 == v9 )
    {
      v15 = 1168;
      if ( *((_QWORD *)&xmmword_180078C50 + 1) )
      {
        LOWORD(v24) = 0;
        LODWORD(v13) = 1168;
        FormatRRASErrorString(
          &v24,
          L"%s: No routing domain was found in stack with name %ws (%d).",
          L"RRasConfigStore::GetRoutingDomainIDFromStack",
          a2,
          v13);
        v7 = *((_QWORD *)&xmmword_180078C50 + 1);
        goto LABEL_14;
      }
    }
  }
  if ( v17 || v16 )
    NsiFreeTable(v17, v16, 0, 0);
  v11 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v11;
}

```

## disassembly

```asm
0x1800492a8  mov     [rsp-8+arg_0], rbx
0x1800492ad  push    rbp
0x1800492ae  push    rsi
0x1800492af  push    rdi
0x1800492b0  push    r14
0x1800492b2  push    r15
0x1800492b4  lea     rbp, [rsp-7D0h]
0x1800492bc  sub     rsp, 8D0h
0x1800492c3  mov     rax, cs:__security_cookie
0x1800492ca  xor     rax, rsp
0x1800492cd  mov     [rbp+7F0h+var_30], rax
0x1800492d4  mov     r14, r8
0x1800492d7  mov     rsi, rdx
0x1800492da  xor     r15d, r15d
0x1800492dd  mov     [rsp+8F0h+var_87C], r15d
0x1800492e2  mov     [rsp+8F0h+var_880], r15d
0x1800492e7  mov     [rsp+8F0h+var_878], r15
0x1800492ec  mov     [rbp+7F0h+var_870], r15
0x1800492f0  mov     [rbp+7F0h+var_830], r15d
0x1800492f4  xor     edx, edx; Val
0x1800492f6  mov     r8d, 7FCh; Size
0x1800492fc  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180049300  call    memset_0
0x180049305  xorps   xmm0, xmm0
0x180049308  movdqu  [rbp+7F0h+var_860], xmm0
0x18004930d  mov     [rbp+7F0h+var_868], r15
0x180049311  xorps   xmm1, xmm1
0x180049314  movdqu  [rbp+7F0h+var_850], xmm1
0x180049319  mov     [rbp+7F0h+var_840], r15
0x18004931d  mov     [rbp+7F0h+var_838], 0FFFFFFFFh
0x180049324  mov     [rbp+7F0h+var_834], r15d
0x180049328  cmp     qword ptr cs:xmmword_180078C50+8, r15
0x18004932f  jz      short loc_180049346
0x180049331  lea     r8, [rsp+8F0h+var_87C]; unsigned int *
0x180049336  lea     rdx, aRrasconfigstor_19; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x18004933d  lea     rcx, [rbp+7F0h+var_868]; this
0x180049341  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180049346  mov     [rsp+8F0h+var_890], r15b
0x18004934b  lea     rax, [rsp+8F0h+var_880]
0x180049350  mov     [rsp+8F0h+var_898], rax
0x180049355  mov     [rsp+8F0h+var_8A0], r15d
0x18004935a  mov     [rsp+8F0h+var_8A8], r15
0x18004935f  mov     [rsp+8F0h+var_8B0], r15d
0x180049364  mov     [rsp+8F0h+var_8B8], r15
0x180049369  mov     [rsp+8F0h+var_8C0], 668h
0x180049371  lea     rax, [rsp+8F0h+var_878]
0x180049376  mov     [rsp+8F0h+var_8C8], rax
0x18004937b  mov     dword ptr [rsp+8F0h+var_8D0], 4
0x180049383  lea     r9, [rbp+7F0h+var_870]
0x180049387  mov     r8d, 7
0x18004938d  lea     rdx, NPI_MS_NDIS_MODULEID
0x180049394  lea     ecx, [r8-6]
0x180049398  call    cs:__imp_NsiAllocateAndGetTable
0x18004939e  mov     [rsp+8F0h+var_87C], eax
0x1800493a2  test    eax, eax
0x1800493a4  jz      short loc_1800493E2
0x1800493a6  cmp     qword ptr cs:xmmword_180078C50, r15
0x1800493ad  jz      loc_18004948B
0x1800493b3  mov     word ptr [rbp+7F0h+var_830], r15w
0x1800493b8  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x1800493bc  mov     r9, rsi
0x1800493bf  lea     r8, aRrasconfigstor_19; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x1800493c6  lea     rdx, aSNsigetparamet; "%s: NsiGetParameter failed while findin"...
0x1800493cd  lea     rcx, [rbp+7F0h+var_830]
0x1800493d1  call    FormatRRASErrorString
0x1800493d6  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800493dd  jmp     loc_180049474
0x1800493e2  mov     ebx, r15d
0x1800493e5  mov     eax, [rsp+8F0h+var_880]
0x1800493e9  test    eax, eax
0x1800493eb  jz      short loc_180049434
0x1800493ed  mov     eax, ebx
0x1800493ef  imul    rdi, rax, 668h
0x1800493f6  mov     rcx, [rsp+8F0h+var_878]
0x1800493fb  add     rcx, 44Ah
0x180049402  add     rcx, rdi; String1
0x180049405  mov     rdx, rsi; String2
0x180049408  call    cs:__imp__wcsicmp
0x18004940e  test    eax, eax
0x180049410  jz      short loc_18004941E
0x180049412  inc     ebx
0x180049414  mov     eax, [rsp+8F0h+var_880]
0x180049418  cmp     ebx, eax
0x18004941a  jb      short loc_1800493ED
0x18004941c  jmp     short loc_180049434
0x18004941e  mov     rax, [rsp+8F0h+var_878]
0x180049423  movups  xmm0, xmmword ptr [rdi+rax+438h]
0x18004942b  movdqu  xmmword ptr [r14], xmm0
0x180049430  mov     eax, [rsp+8F0h+var_880]
0x180049434  cmp     ebx, eax
0x180049436  jnz     short loc_18004948B
0x180049438  mov     ecx, 490h
0x18004943d  mov     [rsp+8F0h+var_87C], ecx
0x180049441  cmp     qword ptr cs:xmmword_180078C50+8, r15
0x180049448  jz      short loc_18004948B
0x18004944a  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004944f  mov     dword ptr [rsp+8F0h+var_8D0], ecx
0x180049453  mov     r9, rsi
0x180049456  lea     r8, aRrasconfigstor_19; "RRasConfigStore::GetRoutingDomainIDFrom"...
0x18004945d  lea     rdx, aSNoRoutingDoma_2; "%s: No routing domain was found in stac"...
0x180049464  lea     rcx, [rbp+7F0h+var_830]
0x180049468  call    FormatRRASErrorString
0x18004946d  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x180049474  lea     r8, [rbp+7F0h+var_830]
0x180049478  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004947f  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180049486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004948b  mov     rcx, [rbp+7F0h+var_870]
0x18004948f  test    rcx, rcx
0x180049492  jnz     short loc_18004949B
0x180049494  cmp     [rsp+8F0h+var_878], r15
0x180049499  jz      short loc_1800494AC
0x18004949b  xor     r9d, r9d
0x18004949e  xor     r8d, r8d
0x1800494a1  mov     rdx, [rsp+8F0h+var_878]
0x1800494a6  call    cs:__imp_NsiFreeTable
0x1800494ac  mov     ebx, [rsp+8F0h+var_87C]
0x1800494b0  lea     rcx, [rbp+7F0h+var_868]; this
0x1800494b4  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800494b9  mov     eax, ebx
0x1800494bb  mov     rcx, [rbp+7F0h+var_30]
0x1800494c2  xor     rcx, rsp; StackCookie
0x1800494c5  call    __security_check_cookie
0x1800494ca  mov     rbx, [rsp+8F0h+arg_0]
0x1800494d2  add     rsp, 8D0h
0x1800494d9  pop     r15
0x1800494db  pop     r14
0x1800494dd  pop     rdi
0x1800494de  pop     rsi
0x1800494df  pop     rbp
0x1800494e0  retn
```
