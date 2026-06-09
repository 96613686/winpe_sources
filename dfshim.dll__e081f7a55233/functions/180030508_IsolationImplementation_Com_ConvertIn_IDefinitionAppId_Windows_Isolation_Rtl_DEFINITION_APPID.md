# IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)

- ea: `0x180030508`
- end: `0x18003066b`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct IDefinitionAppId *, struct Windows::Isolation::Rtl::_DEFINITION_APPID *)`
- caller_count: `14`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800316b4`
- `0x180031cec`
- `0x180031ea0`
- `0x180032214`
- `0x1800324fc`
- `0x1800326e4`
- `0x180032918`
- `0x180032acc`
- `0x1800abbcc`
- `0x1800ad1b4`
- `0x1800ad878`
- `0x1800adf54`
- `0x1800ae5d8`
- `0x1800b08d0`

## callees

- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x180030508`
- `0x18003d55c`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800305a0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800305fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800305a0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800305fb`

## string_xrefs

- `0x18003054b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x1800305a9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030604`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        __int64 (__fastcall ***this)(IsolationImplementation::Com *, GUID *, __int64 *),
        struct IDefinitionAppId *a2,
        struct Windows::Isolation::Rtl::_DEFINITION_APPID *a3)
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
  v6 = v5((IsolationImplementation::Com *)this, &GUID_1fc41db3_c19a_4fd1_bda2_7306e38ca72c, &v26);
  v8 = v6;
  if ( v6 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)0xD1,
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
    v17 = appid_ParseAppId<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppIdCD,Windows::Isolation::Rtl::_DEFINITION_APPID_DATA,_LUNICODE_STRING>(
            v12,
            &v23,
            a2);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( v17 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
        (const char *)0xD3,
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
      (const char *)0xD2,
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
0x180030508  push    rbp
0x18003050a  push    rbx
0x18003050b  push    rsi
0x18003050c  push    rdi
0x18003050d  mov     rbp, rsp
0x180030510  sub     rsp, 48h
0x180030514  xor     esi, esi
0x180030516  lea     r8, [rbp+arg_0]
0x18003051a  mov     [rdx], rsi
0x18003051d  mov     rdi, rdx
0x180030520  mov     rax, [rcx]
0x180030523  lea     rdx, _GUID_1fc41db3_c19a_4fd1_bda2_7306e38ca72c
0x18003052a  mov     [rbp+var_20], rsi
0x18003052e  mov     [rbp+var_28], rsi
0x180030532  mov     [rbp+lpMem], rsi
0x180030536  mov     rax, [rax]
0x180030539  mov     [rbp+arg_0], rsi
0x18003053d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030542  mov     ebx, eax
0x180030544  test    eax, eax
0x180030546  jns     short loc_18003057E
0x180030548  mov     r8d, eax; int
0x18003054b  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030552  mov     edx, 0D1h; char *
0x180030557  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18003055c  mov     rcx, [rbp+arg_0]
0x180030560  test    rcx, rcx
0x180030563  jz      loc_180030646
0x180030569  mov     [rbp+arg_0], rsi
0x18003056d  mov     rax, [rcx]
0x180030570  mov     rax, [rax+10h]
0x180030574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030579  jmp     loc_180030646
0x18003057e  mov     rcx, [rbp+arg_0]
0x180030582  lea     rdx, [rbp+var_28]
0x180030586  mov     rax, [rcx]
0x180030589  mov     rax, [rax+28h]
0x18003058d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030592  mov     ebx, eax
0x180030594  test    eax, eax
0x180030596  jns     short loc_1800305E1
0x180030598  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18003059e  jnz     short loc_1800305A6
0x1800305a0  call    cs:__imp_DebugBreak
0x1800305a6  mov     r9d, ebx; int
0x1800305a9  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800305b0  mov     r8d, 0D2h; char *
0x1800305b6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800305bd  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800305c2  mov     ecx, ebx; this
0x1800305c4  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800305c9  mov     rcx, [rbp+arg_0]
0x1800305cd  mov     ebx, eax
0x1800305cf  test    rcx, rcx
0x1800305d2  jz      short loc_180030646
0x1800305d4  mov     [rbp+arg_0], rsi
0x1800305d8  mov     rdx, [rcx]
0x1800305db  mov     rax, [rdx+10h]
0x1800305df  jmp     short loc_180030574
0x1800305e1  mov     r8, rdi
0x1800305e4  lea     rdx, [rbp+var_28]
0x1800305e8  call    ??$appid_ParseAppId@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCDefAppIdCD@@U_DEFINITION_APPID_DATA@234@U_LUNICODE_STRING@@@@YAJKPEBU_LUNICODE_STRING@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; appid_ParseAppId<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppIdCD,Windows::Isolation::Rtl::_DEFINITION_APPID_DATA,_LUNICODE_STRING>(ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800305ed  mov     ebx, eax
0x1800305ef  test    eax, eax
0x1800305f1  jns     short loc_18003062B
0x1800305f3  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800305f9  jnz     short loc_180030601
0x1800305fb  call    cs:__imp_DebugBreak
0x180030601  mov     r9d, ebx; int
0x180030604  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003060b  mov     r8d, 0D3h; char *
0x180030611  lea     rcx, aStatusPropagat; "Status propagated"
0x180030618  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18003061d  mov     ecx, ebx; this
0x18003061f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030624  mov     ebx, eax
0x180030626  jmp     loc_18003055C
0x18003062b  mov     rcx, [rbp+arg_0]
0x18003062f  test    rcx, rcx
0x180030632  jz      short loc_180030644
0x180030634  mov     [rbp+arg_0], rsi
0x180030638  mov     rax, [rcx]
0x18003063b  mov     rax, [rax+10h]
0x18003063f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030644  mov     ebx, esi
0x180030646  mov     rcx, [rbp+lpMem]; lpMem
0x18003064a  test    rcx, rcx
0x18003064d  jz      short loc_180030660
0x18003064f  mov     [rbp+lpMem], rsi
0x180030653  mov     [rbp+var_28], rsi
0x180030657  mov     [rbp+var_20], rsi
0x18003065b  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180030660  mov     eax, ebx
0x180030662  add     rsp, 48h
0x180030666  pop     rdi
0x180030667  pop     rsi
0x180030668  pop     rbx
0x180030669  pop     rbp
0x18003066a  retn
```
