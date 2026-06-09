# OsImageUtilities::Helpers::UpdateBcdStore(ushort const *,PartitionInfo const &)

- ea: `0x180020880`
- end: `0x180020b37`
- name: `?UpdateBcdStore@Helpers@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@@Z`
- size: `695`
- prototype: `void __fastcall(PCWSTR pszPathIn, const unsigned __int16 *, const struct PartitionInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x180008fac`
- `0x18000a578`
- `0x180020880`
- `0x180021528`
- `0x18002c6b4`
- `0x18002d8a0`
- `0x18002e188`
- `0x18002e4a8`
- `0x18002e4fc`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800208db`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800208db`
- `ntdll!RtlFreeUnicodeString` at `0x180020a6f`
- `ntdll!RtlFreeUnicodeString` at `0x180020a6f`

## string_xrefs

- `0x180020aa7`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020abc`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020ad1`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020ae6`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020afb`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020b10`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180020b25`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall OsImageUtilities::Helpers::UpdateBcdStore(
        PCWSTR pszPathIn,
        const unsigned __int16 *a2,
        const struct PartitionInfo *a3)
{
  char **v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // r8d
  int v15; // eax
  int v16; // r8d
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+48h] [rbp-B8h]
  char v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  char *Src[4]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[60]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-38h] BYREF
  int v31; // [rsp+D8h] [rbp-28h]
  _BYTE v32[40]; // [rsp+DCh] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  Vml::CombineFilePath(Src, pszPathIn, L"EFI\\Microsoft\\Boot\\BCD");
  UnicodeString = 0;
  v4 = Src;
  if ( Src[3] > (char *)7 )
    v4 = (char **)Src[0];
  v5 = RtlDosPathNameToNtPathName_U_WithStatus(v4, &UnicodeString, 0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v5,
      v18);
  v24[1] = &UnicodeString;
  v25 = 1;
  v24[0] = 0;
  v8 = BiOpenStoreWithHash(&UnicodeString, v6, v7, v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v18);
  Handle = 0;
  v9 = BcdOpenObject(v24[0], &GUID_DEFAULT_BOOT_ENTRY, &Handle);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v9,
      v18);
  v30 = 0;
  v31 = 0;
  memset(&v32[12], 0, 28);
  LODWORD(v30) = 7;
  *(GUID *)v32 = GUID_VMBFS_BOOT_INSTANCE;
  v11 = BcdSetElementDataWithFlags((_DWORD)Handle, 285212673, v10, (unsigned int)&v30, 60);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v11,
      v19);
  v13 = BcdSetElementDataWithFlags((_DWORD)Handle, 553648129, v12, (unsigned int)&v30, 60);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v13,
      v20);
  memset(v29, 0, 48);
  *(_DWORD *)v29 = 6;
  *(_DWORD *)&v29[20] = 1;
  *(_OWORD *)&v29[28] = *((_OWORD *)a2 + 2);
  *(_OWORD *)&v29[44] = *((_OWORD *)a2 + 3);
  v15 = BcdSetElementDataWithFlags((_DWORD)Handle, 553648465, v14, (unsigned int)v29, 60);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v15,
      v21);
  v26 = 1;
  v17 = BcdSetElementDataWithFlags((_DWORD)Handle, 369098835, v16, (unsigned int)&v26, 1);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v17,
      v22);
  if ( Handle )
    BcdCloseObject(Handle);
  if ( v24[0] )
    BcdCloseStore(v24[0]);
  RtlFreeUnicodeString(&UnicodeString);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180020880  mov     [rsp-8+arg_10], rsi
0x180020885  push    rbp
0x180020886  lea     rbp, [rsp-10h]
0x18002088b  sub     rsp, 110h
0x180020892  mov     rax, cs:__security_cookie
0x180020899  xor     rax, rsp
0x18002089c  mov     [rbp+10h+var_8], rax
0x1800208a0  mov     rsi, rdx
0x1800208a3  lea     r8, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot\\BCD"
0x1800208aa  mov     rdx, rcx; pszPathIn
0x1800208ad  lea     rcx, [rsp+110h+Src]; Src
0x1800208b2  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800208b7  nop
0x1800208b8  xorps   xmm0, xmm0
0x1800208bb  movups  xmmword ptr [rsp+110h+UnicodeString.Length], xmm0
0x1800208c0  lea     rcx, [rsp+110h+Src]
0x1800208c5  cmp     [rbp+10h+var_90], 7
0x1800208ca  cmova   rcx, [rsp+110h+Src]
0x1800208d0  xor     r9d, r9d
0x1800208d3  xor     r8d, r8d
0x1800208d6  lea     rdx, [rsp+110h+UnicodeString]
0x1800208db  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800208e2  nop     dword ptr [rax+rax+00h]
0x1800208e7  mov     rcx, [rbp+18h]; this
0x1800208eb  test    eax, eax
0x1800208ed  js      loc_180020AB9
0x1800208f3  lea     rax, [rsp+110h+UnicodeString]
0x1800208f8  mov     [rsp+110h+var_D0], rax
0x1800208fd  mov     [rsp+110h+var_C8], 1
0x180020902  mov     [rsp+110h+var_D8], 0
0x18002090b  lea     r9, [rsp+110h+var_D8]
0x180020910  lea     rcx, [rsp+110h+UnicodeString]
0x180020915  call    BiOpenStoreWithHash
0x18002091a  mov     rcx, [rbp+18h]; this
0x18002091e  test    eax, eax
0x180020920  js      loc_180020ACE
0x180020926  mov     [rsp+110h+Handle], 0
0x18002092f  lea     r8, [rsp+110h+Handle]
0x180020934  lea     rdx, GUID_DEFAULT_BOOT_ENTRY
0x18002093b  mov     rcx, [rsp+110h+var_D8]
0x180020940  call    BcdOpenObject
0x180020945  mov     rcx, [rbp+18h]; this
0x180020949  test    eax, eax
0x18002094b  js      loc_180020AE3
0x180020951  xorps   xmm0, xmm0
0x180020954  movups  [rbp+10h+var_48], xmm0
0x180020958  movups  xmmword ptr [rbp+10h+var_38.Data1], xmm0
0x18002095c  movups  [rbp+10h+var_28], xmm0
0x180020960  movups  [rbp+10h+var_28+0Ch], xmm0
0x180020964  mov     dword ptr [rbp+10h+var_48], 7
0x18002096b  movups  xmm0, xmmword ptr cs:GUID_VMBFS_BOOT_INSTANCE.Data1
0x180020972  movdqu  xmmword ptr [rbp+10h+var_38.Data2], xmm0
0x180020977  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x18002097f  lea     r9, [rbp+10h+var_48]
0x180020983  mov     edx, 11000001h
0x180020988  mov     rcx, [rsp+110h+Handle]
0x18002098d  call    BcdSetElementDataWithFlags
0x180020992  mov     rcx, [rbp+18h]; this
0x180020996  test    eax, eax
0x180020998  js      loc_180020AF8
0x18002099e  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x1800209a6  lea     r9, [rbp+10h+var_48]
0x1800209aa  mov     edx, 21000001h
0x1800209af  mov     rcx, [rsp+110h+Handle]
0x1800209b4  call    BcdSetElementDataWithFlags
0x1800209b9  mov     rcx, [rbp+18h]; this
0x1800209bd  test    eax, eax
0x1800209bf  js      loc_180020B0D
0x1800209c5  xorps   xmm0, xmm0
0x1800209c8  movups  [rbp+10h+var_88], xmm0
0x1800209cc  movups  [rbp+10h+var_78], xmm0
0x1800209d0  movups  [rbp+10h+var_68], xmm0
0x1800209d4  mov     dword ptr [rbp+10h+var_88], 6
0x1800209db  mov     dword ptr [rbp+10h+var_78+4], 1
0x1800209e2  movups  xmm0, xmmword ptr [rsi+20h]
0x1800209e6  movdqu  [rbp+10h+var_78+0Ch], xmm0
0x1800209eb  movups  xmm1, xmmword ptr [rsi+30h]
0x1800209ef  movdqu  [rbp+10h+var_68+0Ch], xmm1
0x1800209f4  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x1800209fc  lea     r9, [rbp+10h+var_88]
0x180020a00  mov     edx, 21000151h
0x180020a05  mov     rcx, [rsp+110h+Handle]
0x180020a0a  call    BcdSetElementDataWithFlags
0x180020a0f  mov     rcx, [rbp+18h]; this
0x180020a13  test    eax, eax
0x180020a15  js      loc_180020B22
0x180020a1b  mov     [rsp+110h+var_C0], 1
0x180020a20  mov     [rsp+110h+var_F0], 1; int
0x180020a28  lea     r9, [rsp+110h+var_C0]
0x180020a2d  mov     edx, 16000053h
0x180020a32  mov     rcx, [rsp+110h+Handle]
0x180020a37  call    BcdSetElementDataWithFlags
0x180020a3c  mov     rcx, [rbp+18h]; this
0x180020a40  test    eax, eax
0x180020a42  js      short loc_180020AA4
0x180020a44  cmp     [rsp+110h+Handle], 0
0x180020a4a  jz      short loc_180020A57
0x180020a4c  mov     rcx, [rsp+110h+Handle]; Handle
0x180020a51  call    BcdCloseObject
0x180020a56  nop
0x180020a57  cmp     [rsp+110h+var_D8], 0
0x180020a5d  jz      short loc_180020A6A
0x180020a5f  mov     rcx, [rsp+110h+var_D8]
0x180020a64  call    BcdCloseStore
0x180020a69  nop
0x180020a6a  lea     rcx, [rsp+110h+UnicodeString]; UnicodeString
0x180020a6f  call    cs:__imp_RtlFreeUnicodeString
0x180020a76  nop     dword ptr [rax+rax+00h]
0x180020a7b  nop
0x180020a7c  lea     rcx, [rsp+110h+Src]
0x180020a81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020a86  mov     rcx, [rbp+10h+var_8]
0x180020a8a  xor     rcx, rsp; StackCookie
0x180020a8d  call    __security_check_cookie
0x180020a92  mov     rsi, [rsp+110h+arg_10]
0x180020a9a  add     rsp, 110h
0x180020aa1  pop     rbp
0x180020aa2  retn
0x180020aa4  mov     r9d, eax; char *
0x180020aa7  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020aae  mov     edx, 0CBh; void *
0x180020ab3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020ab9  mov     r9d, eax; char *
0x180020abc  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020ac3  mov     edx, 0A3h; void *
0x180020ac8  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020ace  mov     r9d, eax; char *
0x180020ad1  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020ad8  mov     edx, 0A7h; void *
0x180020add  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020ae3  mov     r9d, eax; char *
0x180020ae6  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020aed  mov     edx, 0AAh; void *
0x180020af2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020af8  mov     r9d, eax; char *
0x180020afb  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020b02  mov     edx, 0B3h; void *
0x180020b07  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020b0d  mov     r9d, eax; char *
0x180020b10  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020b17  mov     edx, 0B8h; void *
0x180020b1c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180020b22  mov     r9d, eax; char *
0x180020b25  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180020b2c  mov     edx, 0C3h; void *
0x180020b31  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
