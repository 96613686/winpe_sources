# DimCreateInterfaceEntry

- ea: `0x180035244`
- end: `0x1800353da`
- name: `DimCreateInterfaceEntry`
- size: `406`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014244`
- `0x180015490`

## callees

- `0x180035244`
- `0x18003a684`
- `0x18003d380`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x18003530a`: `%s: The config store is not available.`
- `0x1800352db`: `DimCreateInterfaceEntry`
- `0x1800352ff`: `DimCreateInterfaceEntry`
- `0x18003536c`: `DimCreateInterfaceEntry`
- `0x18003537a`: `%s: cfgStore->CreateInterfaceEntry failed: %d.`

## pseudocode

```c
__int64 __fastcall DimCreateInterfaceEntry(
        struct _GUID *a1,
        BYTE *a2,
        __int64 a3,
        struct _DIM_COMPARTMENT_INTERFACE *a4)
{
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *Instance; // rax
  enum _ROUTER_INTERFACE_TYPE v9; // r9d
  unsigned int v10; // ebx
  unsigned __int16 *v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  unsigned int InterfaceEntry; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+7Ch] [rbp-84h]
  int v21; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  InterfaceEntry = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"DimCreateInterfaceEntry",
      &InterfaceEntry,
      v7,
      a1,
      v12,
      v13);
  Instance = RRasConfigStore::GetInstance();
  if ( Instance )
  {
    InterfaceEntry = RRasConfigStore::CreateInterfaceEntry(Instance, a1, a2, v9, a4);
    v10 = InterfaceEntry;
    if ( InterfaceEntry && (_QWORD)xmmword_180071090 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"%s: cfgStore->CreateInterfaceEntry failed: %d.",
        L"DimCreateInterfaceEntry",
        InterfaceEntry);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v21);
      v10 = InterfaceEntry;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"%s: The config store is not available.", L"DimCreateInterfaceEntry");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v21);
    }
    v10 = 1003;
    InterfaceEntry = 1003;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v10;
}

```

## disassembly

```asm
0x180035244  mov     [rsp-8+arg_10], rbx
0x180035249  push    rbp
0x18003524a  push    rsi
0x18003524b  push    rdi
0x18003524c  lea     rbp, [rsp-790h]
0x180035254  sub     rsp, 890h
0x18003525b  mov     rax, cs:__security_cookie
0x180035262  xor     rax, rsp
0x180035265  mov     [rbp+7A0h+var_20], rax
0x18003526c  mov     rdi, rdx
0x18003526f  mov     [rsp+8A0h+var_860], 0
0x180035277  mov     rbx, rcx
0x18003527a  xor     eax, eax
0x18003527c  xor     edx, edx; Val
0x18003527e  mov     [rbp+7A0h+var_820], eax
0x180035281  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180035285  mov     r8d, 7FCh; Size
0x18003528b  mov     rsi, r9
0x18003528e  call    memset_0
0x180035293  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x18003529b  xorps   xmm0, xmm0
0x18003529e  xorps   xmm1, xmm1
0x1800352a1  mov     [rsp+8A0h+var_858], 0
0x1800352aa  movdqu  [rsp+8A0h+var_850], xmm0
0x1800352b0  mov     [rsp+8A0h+var_830], 0
0x1800352b9  movdqu  [rsp+8A0h+var_840], xmm1
0x1800352bf  mov     [rsp+8A0h+var_828], 0FFFFFFFFh
0x1800352c7  mov     [rsp+8A0h+var_824], 0
0x1800352cf  jz      short loc_1800352EC
0x1800352d1  lea     r8, [rsp+8A0h+var_860]; unsigned int *
0x1800352d6  mov     [rsp+8A0h+var_880], rbx; struct _GUID *
0x1800352db  lea     rdx, aDimcreateinter; "DimCreateInterfaceEntry"
0x1800352e2  lea     rcx, [rsp+8A0h+var_858]; this
0x1800352e7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800352ec  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x1800352f1  test    rax, rax
0x1800352f4  jnz     short loc_180035343
0x1800352f6  cmp     qword ptr cs:xmmword_180071090, rax
0x1800352fd  jz      short loc_180035338
0x1800352ff  lea     r8, aDimcreateinter; "DimCreateInterfaceEntry"
0x180035306  mov     word ptr [rbp+7A0h+var_820], ax
0x18003530a  lea     rdx, aSTheConfigStor_0; "%s: The config store is not available."
0x180035311  lea     rcx, [rbp+7A0h+var_820]
0x180035315  call    FormatRRASErrorString
0x18003531a  mov     rdx, qword ptr cs:xmmword_180071090
0x180035321  lea     r8, [rbp+7A0h+var_820]
0x180035325  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003532c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180035333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035338  mov     ebx, 3EBh
0x18003533d  mov     [rsp+8A0h+var_860], ebx
0x180035341  jmp     short loc_1800353AC
0x180035343  mov     r8, rdi; unsigned __int16 *
0x180035346  mov     [rsp+8A0h+var_880], rsi; struct _DIM_COMPARTMENT_INTERFACE *
0x18003534b  mov     rdx, rbx; struct _GUID *
0x18003534e  mov     rcx, rax; this
0x180035351  call    ?CreateInterfaceEntry@RRasConfigStore@@QEAAKPEAU_GUID@@PEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z; RRasConfigStore::CreateInterfaceEntry(_GUID *,ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)
0x180035356  mov     [rsp+8A0h+var_860], eax
0x18003535a  mov     ebx, eax
0x18003535c  test    eax, eax
0x18003535e  jz      short loc_1800353AC
0x180035360  cmp     qword ptr cs:xmmword_180071090, 0
0x180035368  jz      short loc_1800353AC
0x18003536a  xor     eax, eax
0x18003536c  lea     r8, aDimcreateinter; "DimCreateInterfaceEntry"
0x180035373  mov     r9d, ebx
0x180035376  mov     word ptr [rbp+7A0h+var_820], ax
0x18003537a  lea     rdx, aSCfgstoreCreat; "%s: cfgStore->CreateInterfaceEntry fail"...
0x180035381  lea     rcx, [rbp+7A0h+var_820]
0x180035385  call    FormatRRASErrorString
0x18003538a  mov     rdx, qword ptr cs:xmmword_180071090
0x180035391  lea     r8, [rbp+7A0h+var_820]
0x180035395  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003539c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800353a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353a8  mov     ebx, [rsp+8A0h+var_860]
0x1800353ac  lea     rcx, [rsp+8A0h+var_858]; this
0x1800353b1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800353b6  mov     eax, ebx
0x1800353b8  mov     rcx, [rbp+7A0h+var_20]
0x1800353bf  xor     rcx, rsp; StackCookie
0x1800353c2  call    __security_check_cookie
0x1800353c7  mov     rbx, [rsp+8A0h+arg_10]
0x1800353cf  add     rsp, 890h
0x1800353d6  pop     rdi
0x1800353d7  pop     rsi
0x1800353d8  pop     rbp
0x1800353d9  retn
```
