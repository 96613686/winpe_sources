# IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)

- ea: `0x180030674`
- end: `0x1800307d7`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct IDefinitionIdentity *, struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)`
- caller_count: `14`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800324fc`
- `0x1800326e4`
- `0x18006fc10`
- `0x1800a3ed8`
- `0x1800a44c0`
- `0x1800a7d38`
- `0x1800aaeb0`
- `0x1800ab568`
- `0x1800ac460`
- `0x1800ac7bc`
- `0x1800ad878`
- `0x1800adc58`
- `0x1800aed6c`
- `0x1800b08d0`

## callees

- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x180030674`
- `0x180043d48`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18003070c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030767`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18003070c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030767`

## string_xrefs

- `0x1800306b7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030715`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030770`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        __int64 (__fastcall ***this)(IsolationImplementation::Com *, GUID *, __int64 *),
        struct IDefinitionIdentity *a2,
        struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *a3)
{
  __int64 (__fastcall **v4)(IsolationImplementation::Com *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(IsolationImplementation::Com *, GUID *, __int64 *); // rax
  int v6; // eax
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 v9; // rcx
  void (*v10)(void); // rax
  int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // edx
  __int64 v20; // rcx
  void *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-28h] BYREF
  __int64 v24; // [rsp+28h] [rbp-20h]
  void *lpMem; // [rsp+30h] [rbp-18h]
  __int64 v26; // [rsp+70h] [rbp+28h] BYREF

  *(_QWORD *)a2 = 0;
  v4 = *this;
  v24 = 0;
  v23 = 0;
  lpMem = 0;
  v5 = *v4;
  v26 = 0;
  v6 = v5((IsolationImplementation::Com *)this, &GUID_94a00aba_2b94_4f0c_abf4_06149d3190cc, &v26);
  v8 = v6;
  if ( v6 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)0x9B,
      v6,
      v7);
LABEL_3:
    v9 = v26;
    if ( !v26 )
      goto LABEL_18;
    v26 = 0;
    v10 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
    goto LABEL_5;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v23);
  v13 = v11;
  if ( v11 >= 0 )
  {
    v17 = RtlParseDefinitionIdentity(v12, &v23, a2);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( v17 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
        (const char *)0x9D,
        v18,
        v23);
      v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v18, v19);
      goto LABEL_3;
    }
    v20 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v8 = 0;
  }
  else
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)0x9C,
      v13,
      v23);
    v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
    v16 = v26;
    v8 = v15;
    if ( v26 )
    {
      v26 = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
LABEL_5:
      v10();
    }
  }
LABEL_18:
  v21 = lpMem;
  if ( lpMem )
  {
    lpMem = 0;
    v23 = 0;
    v24 = 0;
    IsolationFreeStringRoutine(v21);
  }
  return v8;
}

```

## disassembly

```asm
0x180030674  push    rbp
0x180030676  push    rbx
0x180030677  push    rsi
0x180030678  push    rdi
0x180030679  mov     rbp, rsp
0x18003067c  sub     rsp, 48h
0x180030680  xor     esi, esi
0x180030682  lea     r8, [rbp+arg_0]
0x180030686  mov     [rdx], rsi
0x180030689  mov     rdi, rdx
0x18003068c  mov     rax, [rcx]
0x18003068f  lea     rdx, _GUID_94a00aba_2b94_4f0c_abf4_06149d3190cc
0x180030696  mov     [rbp+var_20], rsi
0x18003069a  mov     [rbp+var_28], rsi
0x18003069e  mov     [rbp+lpMem], rsi
0x1800306a2  mov     rax, [rax]
0x1800306a5  mov     [rbp+arg_0], rsi
0x1800306a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306ae  mov     ebx, eax
0x1800306b0  test    eax, eax
0x1800306b2  jns     short loc_1800306EA
0x1800306b4  mov     r8d, eax; int
0x1800306b7  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800306be  mov     edx, 9Bh; char *
0x1800306c3  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800306c8  mov     rcx, [rbp+arg_0]
0x1800306cc  test    rcx, rcx
0x1800306cf  jz      loc_1800307B2
0x1800306d5  mov     [rbp+arg_0], rsi
0x1800306d9  mov     rax, [rcx]
0x1800306dc  mov     rax, [rax+10h]
0x1800306e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e5  jmp     loc_1800307B2
0x1800306ea  mov     rcx, [rbp+arg_0]
0x1800306ee  lea     rdx, [rbp+var_28]
0x1800306f2  mov     rax, [rcx]
0x1800306f5  mov     rax, [rax+28h]
0x1800306f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306fe  mov     ebx, eax
0x180030700  test    eax, eax
0x180030702  jns     short loc_18003074D
0x180030704  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18003070a  jnz     short loc_180030712
0x18003070c  call    cs:__imp_DebugBreak
0x180030712  mov     r9d, ebx; int
0x180030715  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003071c  mov     r8d, 9Ch; char *
0x180030722  lea     rcx, aStatusPropagat; "Status propagated"
0x180030729  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18003072e  mov     ecx, ebx; this
0x180030730  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030735  mov     rcx, [rbp+arg_0]
0x180030739  mov     ebx, eax
0x18003073b  test    rcx, rcx
0x18003073e  jz      short loc_1800307B2
0x180030740  mov     [rbp+arg_0], rsi
0x180030744  mov     rdx, [rcx]
0x180030747  mov     rax, [rdx+10h]
0x18003074b  jmp     short loc_1800306E0
0x18003074d  mov     r8, rdi
0x180030750  lea     rdx, [rbp+var_28]
0x180030754  call    RtlParseDefinitionIdentity
0x180030759  mov     ebx, eax
0x18003075b  test    eax, eax
0x18003075d  jns     short loc_180030797
0x18003075f  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030765  jnz     short loc_18003076D
0x180030767  call    cs:__imp_DebugBreak
0x18003076d  mov     r9d, ebx; int
0x180030770  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030777  mov     r8d, 9Dh; char *
0x18003077d  lea     rcx, aStatusPropagat; "Status propagated"
0x180030784  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180030789  mov     ecx, ebx; this
0x18003078b  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030790  mov     ebx, eax
0x180030792  jmp     loc_1800306C8
0x180030797  mov     rcx, [rbp+arg_0]
0x18003079b  test    rcx, rcx
0x18003079e  jz      short loc_1800307B0
0x1800307a0  mov     [rbp+arg_0], rsi
0x1800307a4  mov     rax, [rcx]
0x1800307a7  mov     rax, [rax+10h]
0x1800307ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b0  mov     ebx, esi
0x1800307b2  mov     rcx, [rbp+lpMem]; lpMem
0x1800307b6  test    rcx, rcx
0x1800307b9  jz      short loc_1800307CC
0x1800307bb  mov     [rbp+lpMem], rsi
0x1800307bf  mov     [rbp+var_28], rsi
0x1800307c3  mov     [rbp+var_20], rsi
0x1800307c7  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800307cc  mov     eax, ebx
0x1800307ce  add     rsp, 48h
0x1800307d2  pop     rdi
0x1800307d3  pop     rsi
0x1800307d4  pop     rbx
0x1800307d5  pop     rbp
0x1800307d6  retn
```
