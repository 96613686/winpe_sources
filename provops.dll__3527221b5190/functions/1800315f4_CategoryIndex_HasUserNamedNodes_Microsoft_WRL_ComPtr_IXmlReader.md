# CategoryIndex::HasUserNamedNodes(Microsoft::WRL::ComPtr<IXmlReader> &)

- ea: `0x1800315f4`
- end: `0x1800316f2`
- name: `?HasUserNamedNodes@CategoryIndex@@CA_NAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z`
- size: `254`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030bdc`

## callees

- `0x18001b388`
- `0x1800315f4`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003165c`
- `msvcrt!_wcsicmp` at `0x180031699`
- `msvcrt!_wcsicmp` at `0x18003165c`
- `msvcrt!_wcsicmp` at `0x180031699`

## pseudocode

```c
bool __fastcall CategoryIndex::HasUserNamedNodes(_QWORD *a1)
{
  int v2; // eax
  int v3; // eax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  wchar_t *String1; // [rsp+38h] [rbp+10h] BYREF
  wchar_t *v9; // [rsp+40h] [rbp+18h] BYREF

  String1 = 0;
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 72LL))(*a1);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v2,
      v6);
  v3 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a1 + 112LL))(*a1, &String1, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v3,
      v6);
  if ( _wcsicmp(String1, L"hasUserNamedNodes") )
    return 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a1 + 128LL))(*a1, &v9, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v5,
      v6);
  return _wcsicmp(v9, L"true") == 0;
}

```

## disassembly

```asm
0x1800315f4  push    rbx; int
0x1800315f6  sub     rsp, 20h
0x1800315fa  mov     rbx, rcx
0x1800315fd  mov     [rsp+28h+arg_0], 0
0x180031602  mov     [rsp+28h+String1], 0
0x18003160b  mov     [rsp+28h+arg_10], 0
0x180031614  mov     rcx, [rcx]
0x180031617  mov     rax, [rcx]
0x18003161a  mov     rax, [rax+48h]
0x18003161e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031623  mov     rcx, [rsp+28h]; this
0x180031628  test    eax, eax
0x18003162a  js      loc_1800316B4
0x180031630  mov     rcx, [rbx]
0x180031633  mov     rax, [rcx]
0x180031636  xor     r8d, r8d
0x180031639  lea     rdx, [rsp+28h+String1]
0x18003163e  mov     rax, [rax+70h]
0x180031642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031647  mov     rcx, [rsp+28h]; this
0x18003164c  test    eax, eax
0x18003164e  js      short loc_1800316C8
0x180031650  lea     rdx, aHasusernamedno; "hasUserNamedNodes"
0x180031657  mov     rcx, [rsp+28h+String1]; String1
0x18003165c  call    cs:__imp__wcsicmp
0x180031662  test    eax, eax
0x180031664  jz      short loc_18003166A
0x180031666  xor     al, al
0x180031668  jmp     short loc_1800316AE
0x18003166a  mov     rcx, [rbx]
0x18003166d  mov     rax, [rcx]
0x180031670  xor     r8d, r8d
0x180031673  lea     rdx, [rsp+28h+arg_10]
0x180031678  mov     rax, [rax+80h]
0x18003167f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031684  mov     rcx, [rsp+28h]; this
0x180031689  test    eax, eax
0x18003168b  js      short loc_1800316DC
0x18003168d  lea     rdx, aTrue; "true"
0x180031694  mov     rcx, [rsp+28h+arg_10]; String1
0x180031699  call    cs:__imp__wcsicmp
0x18003169f  test    eax, eax
0x1800316a1  setz    al
0x1800316a4  mov     [rsp+28h+arg_0], al
0x1800316a8  jmp     short loc_1800316AE
0x1800316aa  mov     al, [rsp+28h+arg_0]
0x1800316ae  add     rsp, 20h
0x1800316b2  pop     rbx
0x1800316b3  retn
0x1800316b4  mov     r9d, eax; char *
0x1800316b7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800316be  mov     edx, 0B3h; void *
0x1800316c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800316c8  mov     r9d, eax; char *
0x1800316cb  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800316d2  mov     edx, 0B4h; void *
0x1800316d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800316dc  mov     r9d, eax; char *
0x1800316df  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800316e6  mov     edx, 0B9h; void *
0x1800316eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
