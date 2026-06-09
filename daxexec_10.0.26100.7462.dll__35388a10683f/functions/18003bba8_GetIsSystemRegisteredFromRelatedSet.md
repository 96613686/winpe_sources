# GetIsSystemRegisteredFromRelatedSet

- ea: `0x18003bba8`
- end: `0x18003bf2f`
- name: `GetIsSystemRegisteredFromRelatedSet`
- size: `903`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, PSID userSid)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007c5a0`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x180009484`
- `0x180010a84`
- `0x180013100`
- `0x180038450`
- `0x18003bba8`
- `0x18003ddd0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bd34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003bd34`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003bc20`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003bc84`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003bc20`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003bc84`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003bdf7`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003be7d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003bdf7`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003be7d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003bbe5`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003bbe5`

## string_xrefs

- `0x18003beeb`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall GetIsSystemRegisteredFromRelatedSet(PCWSTR packageFullName, PSID userSid)
{
  unsigned int v2; // eax
  wil::details::in1diag3 *v3; // rcx
  int PackageInfo; // eax
  char v5; // cl
  UINT32 v6; // ebx
  void *v7; // rsi
  unsigned int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // r14
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  int v21; // eax
  unsigned int count; // [rsp+20h] [rbp-49h]
  int counta; // [rsp+20h] [rbp-49h]
  _BYTE v25[4]; // [rsp+30h] [rbp-39h] BYREF
  UINT32 v26; // [rsp+34h] [rbp-35h] BYREF
  UINT32 bufferLength; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v31[3]; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  packageInfoReference = 0;
  v2 = OpenPackageInfoByFullNameForUser(userSid, packageFullName, 0, &packageInfoReference);
  v3 = retaddr;
  if ( v2 )
LABEL_40:
    wil::details::in1diag3::Throw_Win32(
      v3,
      (void *)0x312,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v2,
      count);
  bufferLength = 0;
  v26 = 0;
  PackageInfo = GetPackageInfo(packageInfoReference, 0x40110u, &bufferLength, 0, &v26);
  if ( PackageInfo == 122 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  v5 = 1;
  if ( PackageInfo > 0 )
LABEL_6:
    PackageInfo = (unsigned __int16)PackageInfo | 0x80070000;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)PackageInfo,
      counta);
  v6 = bufferLength;
  v7 = operator new[](bufferLength);
  memset_0(v7, 0, v6);
  v31[2] = v7;
  v8 = GetPackageInfo(packageInfoReference, 0x40110u, &bufferLength, (BYTE *)v7, &v26);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v8,
      count);
  wil::GetActivationFactory<IInspectable>(v31);
  v30 = 0;
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v31[0])(
         v31[0],
         &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419,
         &v30);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v9,
      count);
  v12 = 0;
  if ( !v26 )
  {
LABEL_22:
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v31[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
    operator delete(v7, v10);
    if ( packageInfoReference )
      ClosePackageInfo(packageInfoReference);
    return 0;
  }
  while ( 1 )
  {
    v28 = 0;
    v13 = v30;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v30 + 176LL);
    v28 = 0;
    string = 0;
    v15 = (const WCHAR *)*((_QWORD *)v7 + 10 * v12 + 2);
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
      goto LABEL_40;
    }
    if ( (int)v16 + 1 < (unsigned int)v16 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
      __debugbreak();
    }
    v17 = WindowsCreateStringReference(v15, v16, &hstringHeader, &string);
    if ( v17 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
      JUMPOUT(0x18003BF2ELL);
    }
    v20 = v14(v13, string, &v28);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x327,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v20,
        count);
    v25[0] = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v28 + 728LL))(v28, v25);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v21,
        count);
    if ( v25[0] )
      break;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( ++v12 >= v26 )
      goto LABEL_22;
  }
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
  operator delete(v7, v10);
  if ( packageInfoReference )
    ClosePackageInfo(packageInfoReference);
  return 1;
}

```

## disassembly

```asm
0x18003bba8  mov     [rsp-8+arg_10], rbx
0x18003bbad  push    rbp
0x18003bbae  push    rsi
0x18003bbaf  push    rdi
0x18003bbb0  push    r14
0x18003bbb2  push    r15
0x18003bbb4  lea     rbp, [rsp-37h]
0x18003bbb9  sub     rsp, 0A0h
0x18003bbc0  mov     rax, cs:__security_cookie
0x18003bbc7  xor     rax, rsp
0x18003bbca  mov     [rbp+57h+var_30], rax
0x18003bbce  mov     rax, rdx
0x18003bbd1  xor     r15d, r15d
0x18003bbd4  mov     [rbp+57h+packageInfoReference], r15
0x18003bbd8  lea     r9, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003bbdc  xor     r8d, r8d; reserved
0x18003bbdf  mov     rdx, rcx; packageFullName
0x18003bbe2  mov     rcx, rax; userSid
0x18003bbe5  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003bbec  nop     dword ptr [rax+rax+00h]
0x18003bbf1  mov     rcx, [rbp+5Fh]
0x18003bbf5  test    eax, eax
0x18003bbf7  jnz     loc_18003BEA6
0x18003bbfd  mov     [rbp+57h+bufferLength], r15d
0x18003bc01  mov     [rbp+57h+var_8C], r15d
0x18003bc05  lea     rax, [rbp+57h+var_8C]
0x18003bc09  mov     qword ptr [rsp+0C0h+count], rax; int
0x18003bc0e  xor     r9d, r9d; buffer
0x18003bc11  lea     r8, [rbp+57h+bufferLength]; bufferLength
0x18003bc15  mov     edi, 40110h
0x18003bc1a  mov     edx, edi; flags
0x18003bc1c  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003bc20  call    cs:__imp_GetPackageInfo
0x18003bc27  nop     dword ptr [rax+rax+00h]
0x18003bc2c  cmp     eax, 7Ah ; 'z'
0x18003bc2f  jz      short loc_18003BC39
0x18003bc31  mov     cl, 1
0x18003bc33  test    eax, eax
0x18003bc35  jg      short loc_18003BC3C
0x18003bc37  jmp     short loc_18003BC44
0x18003bc39  mov     cl, r15b
0x18003bc3c  movzx   eax, ax
0x18003bc3f  or      eax, 80070000h
0x18003bc44  mov     r10, [rbp+5Fh]
0x18003bc48  test    cl, cl
0x18003bc4a  jnz     loc_18003BEBB
0x18003bc50  mov     ebx, [rbp+57h+bufferLength]
0x18003bc53  mov     ecx, ebx; unsigned __int64
0x18003bc55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003bc5a  mov     rsi, rax
0x18003bc5d  mov     r8d, ebx; Size
0x18003bc60  xor     edx, edx; Val
0x18003bc62  mov     rcx, rax; void *
0x18003bc65  call    memset_0
0x18003bc6a  mov     [rbp+57h+var_58], rsi
0x18003bc6e  lea     rax, [rbp+57h+var_8C]
0x18003bc72  mov     qword ptr [rsp+0C0h+count], rax; int
0x18003bc77  mov     r9, rsi; buffer
0x18003bc7a  lea     r8, [rbp+57h+bufferLength]; bufferLength
0x18003bc7e  mov     edx, edi; flags
0x18003bc80  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003bc84  call    cs:__imp_GetPackageInfo
0x18003bc8b  nop     dword ptr [rax+rax+00h]
0x18003bc90  mov     rcx, [rbp+5Fh]; this
0x18003bc94  test    eax, eax
0x18003bc96  jnz     loc_18003BED3
0x18003bc9c  lea     rcx, [rbp+57h+var_68]
0x18003bca0  call    ??$GetActivationFactory@UIInspectable@@@wil@@YA?AV?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<IInspectable>(ushort const *)
0x18003bca5  nop
0x18003bca6  mov     [rbp+57h+var_70], r15
0x18003bcaa  mov     rcx, [rbp+57h+var_68]
0x18003bcae  mov     rax, [rcx]
0x18003bcb1  lea     r8, [rbp+57h+var_70]
0x18003bcb5  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18003bcbc  mov     rax, [rax]
0x18003bcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcc4  mov     rcx, [rbp+5Fh]; this
0x18003bcc8  test    eax, eax
0x18003bcca  js      loc_18003BEE8
0x18003bcd0  mov     edi, r15d
0x18003bcd3  cmp     [rbp+57h+var_8C], r15d
0x18003bcd7  jbe     loc_18003BDB9
0x18003bcdd  mov     [rbp+57h+var_80], r15
0x18003bce1  mov     rbx, [rbp+57h+var_70]
0x18003bce5  mov     rax, [rbx]
0x18003bce8  mov     r14, [rax+0B0h]
0x18003bcef  mov     [rbp+57h+var_80], r15
0x18003bcf3  mov     [rbp+57h+string], r15
0x18003bcf7  mov     eax, edi
0x18003bcf9  lea     rcx, [rax+rax*4]
0x18003bcfd  add     rcx, rcx
0x18003bd00  mov     rcx, [rsi+rcx*8+10h]; sourceString
0x18003bd05  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003bd09  inc     rdx; int
0x18003bd0c  cmp     [rcx+rdx*2], r15w
0x18003bd11  jnz     short loc_18003BD09
0x18003bd13  mov     eax, 0FFFFFFFFh
0x18003bd18  cmp     rdx, rax
0x18003bd1b  ja      loc_18003BE9B
0x18003bd21  lea     eax, [rdx+1]
0x18003bd24  cmp     eax, edx
0x18003bd26  jb      loc_18003BE90
0x18003bd2c  lea     r9, [rbp+57h+string]; string
0x18003bd30  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003bd34  call    cs:__imp_WindowsCreateStringReference
0x18003bd3b  nop     dword ptr [rax+rax+00h]
0x18003bd40  test    eax, eax
0x18003bd42  js      loc_18003BF27
0x18003bd48  lea     r8, [rbp+57h+var_80]
0x18003bd4c  mov     rdx, [rbp+57h+string]
0x18003bd50  mov     rcx, rbx
0x18003bd53  mov     rax, r14
0x18003bd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd5b  mov     rcx, [rbp+5Fh]; this
0x18003bd5f  test    eax, eax
0x18003bd61  js      loc_18003BF12
0x18003bd67  mov     [rbp+57h+var_90], r15b
0x18003bd6b  mov     rcx, [rbp+57h+var_80]
0x18003bd6f  mov     rax, [rcx]
0x18003bd72  lea     rdx, [rbp+57h+var_90]
0x18003bd76  mov     rax, [rax+2D8h]
0x18003bd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd82  mov     rcx, [rbp+5Fh]; this
0x18003bd86  test    eax, eax
0x18003bd88  js      loc_18003BEFD
0x18003bd8e  cmp     [rbp+57h+var_90], r15b
0x18003bd92  jnz     loc_18003BE29
0x18003bd98  mov     rcx, [rbp+57h+var_80]
0x18003bd9c  test    rcx, rcx
0x18003bd9f  jz      short loc_18003BDAE
0x18003bda1  mov     rax, [rcx]
0x18003bda4  mov     rax, [rax+10h]
0x18003bda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdad  nop
0x18003bdae  inc     edi
0x18003bdb0  cmp     edi, [rbp+57h+var_8C]
0x18003bdb3  jb      loc_18003BCDD
0x18003bdb9  mov     rcx, [rbp+57h+var_70]
0x18003bdbd  test    rcx, rcx
0x18003bdc0  jz      short loc_18003BDCF
0x18003bdc2  mov     rax, [rcx]
0x18003bdc5  mov     rax, [rax+10h]
0x18003bdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdce  nop
0x18003bdcf  mov     rcx, [rbp+57h+var_68]
0x18003bdd3  test    rcx, rcx
0x18003bdd6  jz      short loc_18003BDE5
0x18003bdd8  mov     rax, [rcx]
0x18003bddb  mov     rax, [rax+10h]
0x18003bddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bde4  nop
0x18003bde5  mov     rcx, rsi; void *
0x18003bde8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003bded  nop
0x18003bdee  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003bdf2  test    rcx, rcx
0x18003bdf5  jz      short loc_18003BE03
0x18003bdf7  call    cs:__imp_ClosePackageInfo
0x18003bdfe  nop     dword ptr [rax+rax+00h]
0x18003be03  xor     al, al
0x18003be05  mov     rcx, [rbp+57h+var_30]
0x18003be09  xor     rcx, rsp; StackCookie
0x18003be0c  call    __security_check_cookie
0x18003be11  mov     rbx, [rsp+0C0h+arg_10]
0x18003be19  add     rsp, 0A0h
0x18003be20  pop     r15
0x18003be22  pop     r14
0x18003be24  pop     rdi
0x18003be25  pop     rsi
0x18003be26  pop     rbp
0x18003be27  retn
0x18003be29  mov     rcx, [rbp+57h+var_80]
0x18003be2d  test    rcx, rcx
0x18003be30  jz      short loc_18003BE3F
0x18003be32  mov     rax, [rcx]
0x18003be35  mov     rax, [rax+10h]
0x18003be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be3e  nop
0x18003be3f  mov     rcx, [rbp+57h+var_70]
0x18003be43  test    rcx, rcx
0x18003be46  jz      short loc_18003BE55
0x18003be48  mov     rax, [rcx]
0x18003be4b  mov     rax, [rax+10h]
0x18003be4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be54  nop
0x18003be55  mov     rcx, [rbp+57h+var_68]
0x18003be59  test    rcx, rcx
0x18003be5c  jz      short loc_18003BE6B
0x18003be5e  mov     rax, [rcx]
0x18003be61  mov     rax, [rax+10h]
0x18003be65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be6a  nop
0x18003be6b  mov     rcx, rsi; void *
0x18003be6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003be73  nop
0x18003be74  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003be78  test    rcx, rcx
0x18003be7b  jz      short loc_18003BE89
0x18003be7d  call    cs:__imp_ClosePackageInfo
0x18003be84  nop     dword ptr [rax+rax+00h]
0x18003be89  mov     al, 1
0x18003be8b  jmp     loc_18003BE05
0x18003be90  mov     ecx, 80070216h; this
0x18003be95  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003be9a  int     3; Trap to Debugger
0x18003be9b  mov     ecx, 80070216h; this
0x18003bea0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003bea5  nop
0x18003bea6  mov     r9d, eax; char *
0x18003bea9  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003beb0  mov     edx, 312h; void *
0x18003beb5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003bebb  mov     r9d, eax; char *
0x18003bebe  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003bec5  mov     edx, 31Ah; void *
0x18003beca  mov     rcx, r10; this
0x18003becd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003bed3  mov     r9d, eax; char *
0x18003bed6  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003bedd  mov     edx, 31Dh; void *
0x18003bee2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003bee8  mov     r9d, eax; char *
0x18003beeb  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003bef2  mov     edx, 1C60h; void *
0x18003bef7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003befd  mov     r9d, eax; char *
0x18003bf00  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003bf07  mov     edx, 32Ah; void *
0x18003bf0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003bf12  mov     r9d, eax; char *
0x18003bf15  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003bf1c  mov     edx, 327h; void *
0x18003bf21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003bf27  mov     ecx, eax; this
0x18003bf29  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
