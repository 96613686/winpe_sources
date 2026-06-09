# IsolationImplementation::Com::ConvertIn(IReferenceIdentity *,Windows::Isolation::Rtl::_REFERENCE_IDENTITY *)

- ea: `0x18003094c`
- end: `0x180030aaf`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceIdentity@@PEAU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct IReferenceIdentity *, struct Windows::Isolation::Rtl::_REFERENCE_IDENTITY *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006ece0`
- `0x1800a3d0c`
- `0x1800ab568`
- `0x1800ac0f8`

## callees

- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18003094c`
- `0x180044e38`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800309e4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030a3f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800309e4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030a3f`

## string_xrefs

- `0x18003098f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x1800309ed`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030a48`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        __int64 (__fastcall ***this)(IsolationImplementation::Com *, GUID *, __int64 *),
        struct IReferenceIdentity *a2,
        struct Windows::Isolation::Rtl::_REFERENCE_IDENTITY *a3)
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
  v6 = v5((IsolationImplementation::Com *)this, &GUID_a839a2ad_dc04_4b0c_9195_c55b9098db5e, &v26);
  v8 = v6;
  if ( v6 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)0xAE,
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
    v17 = RtlParseReferenceIdentity(v12, &v23, a2);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( v17 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
        (const char *)0xB0,
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
      (const char *)0xAF,
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
0x18003094c  push    rbp
0x18003094e  push    rbx
0x18003094f  push    rsi
0x180030950  push    rdi
0x180030951  mov     rbp, rsp
0x180030954  sub     rsp, 48h
0x180030958  xor     esi, esi
0x18003095a  lea     r8, [rbp+arg_0]
0x18003095e  mov     [rdx], rsi
0x180030961  mov     rdi, rdx
0x180030964  mov     rax, [rcx]
0x180030967  lea     rdx, _GUID_a839a2ad_dc04_4b0c_9195_c55b9098db5e
0x18003096e  mov     [rbp+var_20], rsi
0x180030972  mov     [rbp+var_28], rsi
0x180030976  mov     [rbp+lpMem], rsi
0x18003097a  mov     rax, [rax]
0x18003097d  mov     [rbp+arg_0], rsi
0x180030981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030986  mov     ebx, eax
0x180030988  test    eax, eax
0x18003098a  jns     short loc_1800309C2
0x18003098c  mov     r8d, eax; int
0x18003098f  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030996  mov     edx, 0AEh; char *
0x18003099b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800309a0  mov     rcx, [rbp+arg_0]
0x1800309a4  test    rcx, rcx
0x1800309a7  jz      loc_180030A8A
0x1800309ad  mov     [rbp+arg_0], rsi
0x1800309b1  mov     rax, [rcx]
0x1800309b4  mov     rax, [rax+10h]
0x1800309b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309bd  jmp     loc_180030A8A
0x1800309c2  mov     rcx, [rbp+arg_0]
0x1800309c6  lea     rdx, [rbp+var_28]
0x1800309ca  mov     rax, [rcx]
0x1800309cd  mov     rax, [rax+28h]
0x1800309d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309d6  mov     ebx, eax
0x1800309d8  test    eax, eax
0x1800309da  jns     short loc_180030A25
0x1800309dc  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800309e2  jnz     short loc_1800309EA
0x1800309e4  call    cs:__imp_DebugBreak
0x1800309ea  mov     r9d, ebx; int
0x1800309ed  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800309f4  mov     r8d, 0AFh; char *
0x1800309fa  lea     rcx, aStatusPropagat; "Status propagated"
0x180030a01  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180030a06  mov     ecx, ebx; this
0x180030a08  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030a0d  mov     rcx, [rbp+arg_0]
0x180030a11  mov     ebx, eax
0x180030a13  test    rcx, rcx
0x180030a16  jz      short loc_180030A8A
0x180030a18  mov     [rbp+arg_0], rsi
0x180030a1c  mov     rdx, [rcx]
0x180030a1f  mov     rax, [rdx+10h]
0x180030a23  jmp     short loc_1800309B8
0x180030a25  mov     r8, rdi
0x180030a28  lea     rdx, [rbp+var_28]
0x180030a2c  call    RtlParseReferenceIdentity
0x180030a31  mov     ebx, eax
0x180030a33  test    eax, eax
0x180030a35  jns     short loc_180030A6F
0x180030a37  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030a3d  jnz     short loc_180030A45
0x180030a3f  call    cs:__imp_DebugBreak
0x180030a45  mov     r9d, ebx; int
0x180030a48  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030a4f  mov     r8d, 0B0h; char *
0x180030a55  lea     rcx, aStatusPropagat; "Status propagated"
0x180030a5c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180030a61  mov     ecx, ebx; this
0x180030a63  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030a68  mov     ebx, eax
0x180030a6a  jmp     loc_1800309A0
0x180030a6f  mov     rcx, [rbp+arg_0]
0x180030a73  test    rcx, rcx
0x180030a76  jz      short loc_180030A88
0x180030a78  mov     [rbp+arg_0], rsi
0x180030a7c  mov     rax, [rcx]
0x180030a7f  mov     rax, [rax+10h]
0x180030a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a88  mov     ebx, esi
0x180030a8a  mov     rcx, [rbp+lpMem]; lpMem
0x180030a8e  test    rcx, rcx
0x180030a91  jz      short loc_180030AA4
0x180030a93  mov     [rbp+lpMem], rsi
0x180030a97  mov     [rbp+var_28], rsi
0x180030a9b  mov     [rbp+var_20], rsi
0x180030a9f  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180030aa4  mov     eax, ebx
0x180030aa6  add     rsp, 48h
0x180030aaa  pop     rdi
0x180030aab  pop     rsi
0x180030aac  pop     rbx
0x180030aad  pop     rbp
0x180030aae  retn
```
