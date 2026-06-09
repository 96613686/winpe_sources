# OsImageUtilities::Helpers::IsPreReleaseImage(ushort const *)

- ea: `0x18001dfe4`
- end: `0x18001e1f8`
- name: `?IsPreReleaseImage@Helpers@OsImageUtilities@@YA_NPEBG@Z`
- size: `532`
- prototype: `bool __fastcall(PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x180008fac`
- `0x18000a578`
- `0x18001dfe4`
- `0x180020858`
- `0x180021528`
- `0x18002c3ec`
- `0x18002d8a0`
- `0x18002e188`
- `0x18002e4a8`
- `0x18002e4fc`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001e03c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001e03c`
- `ntdll!RtlFreeUnicodeString` at `0x18001e15b`
- `ntdll!RtlFreeUnicodeString` at `0x18001e15b`

## string_xrefs

- `0x18001e1bc`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001e1d1`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001e1e6`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall OsImageUtilities::Helpers::IsPreReleaseImage(PCWSTR pszPathIn, const unsigned __int16 *a2)
{
  char **v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  char v6; // bl
  int v7; // eax
  int v8; // eax
  int v9; // r8d
  int ElementDataWithFlags; // eax
  unsigned int v11; // r8d
  bool v12; // r14
  int v13; // eax
  unsigned int v14; // r8d
  bool v15; // al
  int v17; // [rsp+20h] [rbp-29h]
  int v18; // [rsp+20h] [rbp-29h]
  int v19; // [rsp+20h] [rbp-29h]
  int v20; // [rsp+30h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-9h] BYREF
  char v23; // [rsp+50h] [rbp+7h]
  __int16 v24; // [rsp+58h] [rbp+Fh] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp+17h] BYREF
  char *Src[4]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Vml::CombineFilePath(Src, pszPathIn, L"Files\\EFI\\Microsoft\\Boot\\BCD");
  UnicodeString = 0;
  v2 = Src;
  if ( Src[3] > (char *)7 )
    v2 = (char **)Src[0];
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(v2, &UnicodeString, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v3,
      v17);
  v22[1] = &UnicodeString;
  v6 = 1;
  v23 = 1;
  v22[0] = 0;
  v7 = BiOpenStoreWithHash(&UnicodeString, v4, v5, v22);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v7,
      v17);
  Handle = 0;
  v8 = BcdOpenObject(v22[0], &GUID_DEFAULT_BOOT_ENTRY, &Handle);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v17);
  v24 = 0;
  v20 = 2;
  ElementDataWithFlags = BcdGetElementDataWithFlags((_DWORD)Handle, 369098878, v9, (unsigned int)&v24, (__int64)&v20);
  if ( ElementDataWithFlags < 0 )
  {
    if ( ElementDataWithFlags != -1073741275 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x1A3,
        v11,
        (const char *)(unsigned int)ElementDataWithFlags,
        v18);
    v12 = 0;
  }
  else
  {
    v12 = (_BYTE)v24 == 1;
  }
  v24 = 0;
  v20 = 2;
  v13 = BcdGetElementDataWithFlags((_DWORD)Handle, 369098825, v11, (unsigned int)&v24, (__int64)&v20);
  if ( v13 < 0 )
  {
    if ( v13 != -1073741275 )
      wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x1BE, v14, (const char *)(unsigned int)v13, v19);
    v15 = 0;
  }
  else
  {
    v15 = (_BYTE)v24 == 1;
  }
  if ( !v12 && !v15 )
    v6 = 0;
  if ( Handle )
    BcdCloseObject(Handle);
  if ( v22[0] )
    BcdCloseStore(v22[0]);
  RtlFreeUnicodeString(&UnicodeString);
  std::wstring::~wstring(Src);
  return v6;
}

```

## disassembly

```asm
0x18001dfe4  mov     [rsp-8+arg_8], rbx
0x18001dfe9  mov     [rsp-8+arg_10], r14
0x18001dfee  push    rbp
0x18001dfef  lea     rbp, [rsp-57h]
0x18001dff4  sub     rsp, 0A0h
0x18001dffb  mov     rax, cs:__security_cookie
0x18001e002  xor     rax, rsp
0x18001e005  mov     [rbp+57h+var_10], rax
0x18001e009  lea     r8, aFilesEfiMicros; "Files\\EFI\\Microsoft\\Boot\\BCD"
0x18001e010  mov     rdx, rcx; pszPathIn
0x18001e013  lea     rcx, [rbp+57h+Src]; Src
0x18001e017  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001e01c  nop
0x18001e01d  xorps   xmm0, xmm0
0x18001e020  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18001e024  lea     rcx, [rbp+57h+Src]
0x18001e028  cmp     [rbp+57h+var_18], 7
0x18001e02d  cmova   rcx, [rbp+57h+Src]
0x18001e032  xor     r9d, r9d
0x18001e035  xor     r8d, r8d
0x18001e038  lea     rdx, [rbp+57h+UnicodeString]
0x18001e03c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18001e043  nop     dword ptr [rax+rax+00h]
0x18001e048  mov     rcx, [rbp+5Fh]; this
0x18001e04c  test    eax, eax
0x18001e04e  js      loc_18001E1B9
0x18001e054  lea     rax, [rbp+57h+UnicodeString]
0x18001e058  mov     [rbp+57h+var_58], rax
0x18001e05c  mov     bl, 1
0x18001e05e  mov     [rbp+57h+var_50], bl
0x18001e061  mov     [rbp+57h+var_60], 0
0x18001e069  lea     r9, [rbp+57h+var_60]
0x18001e06d  lea     rcx, [rbp+57h+UnicodeString]
0x18001e071  call    BiOpenStoreWithHash
0x18001e076  mov     rcx, [rbp+5Fh]; this
0x18001e07a  test    eax, eax
0x18001e07c  js      loc_18001E1CE
0x18001e082  mov     [rbp+57h+Handle], 0
0x18001e08a  lea     r8, [rbp+57h+Handle]
0x18001e08e  lea     rdx, GUID_DEFAULT_BOOT_ENTRY
0x18001e095  mov     rcx, [rbp+57h+var_60]
0x18001e099  call    BcdOpenObject
0x18001e09e  mov     rcx, [rbp+5Fh]; this
0x18001e0a2  test    eax, eax
0x18001e0a4  js      loc_18001E1E3
0x18001e0aa  xor     eax, eax
0x18001e0ac  mov     [rbp+57h+var_48], ax
0x18001e0b0  mov     [rbp+57h+var_70], 2
0x18001e0b7  lea     rax, [rbp+57h+var_70]
0x18001e0bb  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18001e0c0  lea     r9, [rbp+57h+var_48]
0x18001e0c4  mov     edx, 1600007Eh
0x18001e0c9  mov     rcx, [rbp+57h+Handle]
0x18001e0cd  call    BcdGetElementDataWithFlags
0x18001e0d2  test    eax, eax
0x18001e0d4  js      short loc_18001E0DF
0x18001e0d6  cmp     byte ptr [rbp+57h+var_48], bl
0x18001e0d9  setz    r14b
0x18001e0dd  jmp     short loc_18001E0ED
0x18001e0df  cmp     eax, 0C0000225h
0x18001e0e4  jnz     loc_18001E1A7
0x18001e0ea  xor     r14b, r14b
0x18001e0ed  xor     eax, eax
0x18001e0ef  mov     [rbp+57h+var_48], ax
0x18001e0f3  mov     [rbp+57h+var_70], 2
0x18001e0fa  lea     rax, [rbp+57h+var_70]
0x18001e0fe  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18001e103  lea     r9, [rbp+57h+var_48]
0x18001e107  mov     edx, 16000049h
0x18001e10c  mov     rcx, [rbp+57h+Handle]
0x18001e110  call    BcdGetElementDataWithFlags
0x18001e115  test    eax, eax
0x18001e117  js      short loc_18001E121
0x18001e119  cmp     byte ptr [rbp+57h+var_48], bl
0x18001e11c  setz    al
0x18001e11f  jmp     short loc_18001E12A
0x18001e121  cmp     eax, 0C0000225h
0x18001e126  jnz     short loc_18001E195
0x18001e128  xor     al, al
0x18001e12a  test    r14b, r14b
0x18001e12d  jnz     short loc_18001E135
0x18001e12f  test    al, al
0x18001e131  jnz     short loc_18001E135
0x18001e133  xor     bl, bl
0x18001e135  cmp     [rbp+57h+Handle], 0
0x18001e13a  jz      short loc_18001E146
0x18001e13c  mov     rcx, [rbp+57h+Handle]; Handle
0x18001e140  call    BcdCloseObject
0x18001e145  nop
0x18001e146  cmp     [rbp+57h+var_60], 0
0x18001e14b  jz      short loc_18001E157
0x18001e14d  mov     rcx, [rbp+57h+var_60]
0x18001e151  call    BcdCloseStore
0x18001e156  nop
0x18001e157  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18001e15b  call    cs:__imp_RtlFreeUnicodeString
0x18001e162  nop     dword ptr [rax+rax+00h]
0x18001e167  nop
0x18001e168  lea     rcx, [rbp+57h+Src]
0x18001e16c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e171  mov     al, bl
0x18001e173  mov     rcx, [rbp+57h+var_10]
0x18001e177  xor     rcx, rsp; StackCookie
0x18001e17a  call    __security_check_cookie
0x18001e17f  lea     r11, [rsp+0A0h+var_s0]
0x18001e187  mov     rbx, [r11+18h]
0x18001e18b  mov     r14, [r11+20h]
0x18001e18f  mov     rsp, r11
0x18001e192  pop     rbp
0x18001e193  retn
0x18001e195  mov     rcx, [rbp+5Fh]; this
0x18001e199  mov     r9d, eax; char *
0x18001e19c  mov     edx, 1BEh; void *
0x18001e1a1  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001e1a7  mov     rcx, [rbp+5Fh]; this
0x18001e1ab  mov     r9d, eax; char *
0x18001e1ae  mov     edx, 1A3h; void *
0x18001e1b3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001e1b9  mov     r9d, eax; char *
0x18001e1bc  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001e1c3  mov     edx, 182h; void *
0x18001e1c8  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001e1ce  mov     r9d, eax; char *
0x18001e1d1  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001e1d8  mov     edx, 186h; void *
0x18001e1dd  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001e1e3  mov     r9d, eax; char *
0x18001e1e6  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001e1ed  mov     edx, 18Ah; void *
0x18001e1f2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
