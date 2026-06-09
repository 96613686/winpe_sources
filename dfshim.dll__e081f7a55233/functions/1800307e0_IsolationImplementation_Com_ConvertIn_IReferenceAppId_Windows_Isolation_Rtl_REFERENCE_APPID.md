# IsolationImplementation::Com::ConvertIn(IReferenceAppId *,Windows::Isolation::Rtl::_REFERENCE_APPID *)

- ea: `0x1800307e0`
- end: `0x180030943`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceAppId@@PEAU_REFERENCE_APPID@Rtl@Isolation@Windows@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct IReferenceAppId *, struct Windows::Isolation::Rtl::_REFERENCE_APPID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031800`
- `0x1800ac9e0`

## callees

- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800307e0`
- `0x1800420e0`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030878`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800308d3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030878`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800308d3`

## string_xrefs

- `0x180030823`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030881`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x1800308dc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        __int64 (__fastcall ***this)(IsolationImplementation::Com *, GUID *, __int64 *),
        struct IReferenceAppId *a2,
        struct Windows::Isolation::Rtl::_REFERENCE_APPID *a3)
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
  v6 = v5((IsolationImplementation::Com *)this, &GUID_bf1ec88f_5631_42a2_bbc1_0a57f23d8266, &v26);
  v8 = v6;
  if ( v6 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)0xE5,
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
    v17 = appid_ParseAppId<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppIdCD,Windows::Isolation::Rtl::_REFERENCE_APPID_DATA,_LUNICODE_STRING>(
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
        (const char *)0xE7,
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
      (const char *)0xE6,
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
0x1800307e0  push    rbp
0x1800307e2  push    rbx
0x1800307e3  push    rsi
0x1800307e4  push    rdi
0x1800307e5  mov     rbp, rsp
0x1800307e8  sub     rsp, 48h
0x1800307ec  xor     esi, esi
0x1800307ee  lea     r8, [rbp+arg_0]
0x1800307f2  mov     [rdx], rsi
0x1800307f5  mov     rdi, rdx
0x1800307f8  mov     rax, [rcx]
0x1800307fb  lea     rdx, _GUID_bf1ec88f_5631_42a2_bbc1_0a57f23d8266
0x180030802  mov     [rbp+var_20], rsi
0x180030806  mov     [rbp+var_28], rsi
0x18003080a  mov     [rbp+lpMem], rsi
0x18003080e  mov     rax, [rax]
0x180030811  mov     [rbp+arg_0], rsi
0x180030815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003081a  mov     ebx, eax
0x18003081c  test    eax, eax
0x18003081e  jns     short loc_180030856
0x180030820  mov     r8d, eax; int
0x180030823  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003082a  mov     edx, 0E5h; char *
0x18003082f  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180030834  mov     rcx, [rbp+arg_0]
0x180030838  test    rcx, rcx
0x18003083b  jz      loc_18003091E
0x180030841  mov     [rbp+arg_0], rsi
0x180030845  mov     rax, [rcx]
0x180030848  mov     rax, [rax+10h]
0x18003084c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030851  jmp     loc_18003091E
0x180030856  mov     rcx, [rbp+arg_0]
0x18003085a  lea     rdx, [rbp+var_28]
0x18003085e  mov     rax, [rcx]
0x180030861  mov     rax, [rax+28h]
0x180030865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003086a  mov     ebx, eax
0x18003086c  test    eax, eax
0x18003086e  jns     short loc_1800308B9
0x180030870  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030876  jnz     short loc_18003087E
0x180030878  call    cs:__imp_DebugBreak
0x18003087e  mov     r9d, ebx; int
0x180030881  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030888  mov     r8d, 0E6h; char *
0x18003088e  lea     rcx, aStatusPropagat; "Status propagated"
0x180030895  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18003089a  mov     ecx, ebx; this
0x18003089c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800308a1  mov     rcx, [rbp+arg_0]
0x1800308a5  mov     ebx, eax
0x1800308a7  test    rcx, rcx
0x1800308aa  jz      short loc_18003091E
0x1800308ac  mov     [rbp+arg_0], rsi
0x1800308b0  mov     rdx, [rcx]
0x1800308b3  mov     rax, [rdx+10h]
0x1800308b7  jmp     short loc_18003084C
0x1800308b9  mov     r8, rdi
0x1800308bc  lea     rdx, [rbp+var_28]
0x1800308c0  call    ??$appid_ParseAppId@U_REFERENCE_APPID@Rtl@Isolation@Windows@@VCRefAppIdCD@@U_REFERENCE_APPID_DATA@234@U_LUNICODE_STRING@@@@YAJKPEBU_LUNICODE_STRING@@PEAU_REFERENCE_APPID@Rtl@Isolation@Windows@@@Z; appid_ParseAppId<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppIdCD,Windows::Isolation::Rtl::_REFERENCE_APPID_DATA,_LUNICODE_STRING>(ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_REFERENCE_APPID *)
0x1800308c5  mov     ebx, eax
0x1800308c7  test    eax, eax
0x1800308c9  jns     short loc_180030903
0x1800308cb  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800308d1  jnz     short loc_1800308D9
0x1800308d3  call    cs:__imp_DebugBreak
0x1800308d9  mov     r9d, ebx; int
0x1800308dc  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800308e3  mov     r8d, 0E7h; char *
0x1800308e9  lea     rcx, aStatusPropagat; "Status propagated"
0x1800308f0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800308f5  mov     ecx, ebx; this
0x1800308f7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800308fc  mov     ebx, eax
0x1800308fe  jmp     loc_180030834
0x180030903  mov     rcx, [rbp+arg_0]
0x180030907  test    rcx, rcx
0x18003090a  jz      short loc_18003091C
0x18003090c  mov     [rbp+arg_0], rsi
0x180030910  mov     rax, [rcx]
0x180030913  mov     rax, [rax+10h]
0x180030917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091c  mov     ebx, esi
0x18003091e  mov     rcx, [rbp+lpMem]; lpMem
0x180030922  test    rcx, rcx
0x180030925  jz      short loc_180030938
0x180030927  mov     [rbp+lpMem], rsi
0x18003092b  mov     [rbp+var_28], rsi
0x18003092f  mov     [rbp+var_20], rsi
0x180030933  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180030938  mov     eax, ebx
0x18003093a  add     rsp, 48h
0x18003093e  pop     rdi
0x18003093f  pop     rsi
0x180030940  pop     rbx
0x180030941  pop     rbp
0x180030942  retn
```
