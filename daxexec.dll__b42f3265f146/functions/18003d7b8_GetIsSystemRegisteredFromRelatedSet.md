# GetIsSystemRegisteredFromRelatedSet

- ea: `0x18003d7b8`
- end: `0x18003db3c`
- name: `GetIsSystemRegisteredFromRelatedSet`
- size: `900`
- prototype: `char __fastcall(PCWSTR packageFullName, PSID userSid)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003fa14`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800059a8`
- `0x18000afe4`
- `0x1800125f4`
- `0x180014e74`
- `0x180039e58`
- `0x18003d7b8`
- `0x18003fd60`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d93d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003d830`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003d894`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003d830`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003d894`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003da04`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003da8a`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003da04`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003da8a`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003d7f5`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003d7f5`

## string_xrefs

- `0x18003daf8`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
char __fastcall GetIsSystemRegisteredFromRelatedSet(PCWSTR packageFullName, PSID userSid)
{
  unsigned int v2; // eax
  wil::details::in1diag3 *v3; // rcx
  int PackageInfo; // eax
  char v5; // cl
  UINT32 v6; // ebx
  void *v7; // rdi
  unsigned int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  __int64 *v13; // rsi
  __int64 v14; // r14
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  int v21; // eax
  unsigned int count; // [rsp+20h] [rbp-39h]
  int counta; // [rsp+20h] [rbp-39h]
  _BYTE v25[4]; // [rsp+30h] [rbp-29h] BYREF
  UINT32 v26; // [rsp+34h] [rbp-25h] BYREF
  UINT32 bufferLength; // [rsp+38h] [rbp-21h] BYREF
  __int64 v28; // [rsp+40h] [rbp-19h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v30; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

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
  v31[1] = v7;
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
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v31[0])(
         v31[0],
         &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419,
         &v30);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v9,
      count);
  v12 = 0;
  if ( !v26 )
  {
LABEL_22:
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
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
    v14 = *v30;
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
      JUMPOUT(0x18003DB3BLL);
    }
    v20 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v14 + 176))(v13, string, &v28);
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
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
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
0x18003d7b8  mov     [rsp-8+arg_10], rbx
0x18003d7bd  push    rbp
0x18003d7be  push    rsi
0x18003d7bf  push    rdi
0x18003d7c0  push    r14
0x18003d7c2  push    r15
0x18003d7c4  lea     rbp, [rsp-37h]
0x18003d7c9  sub     rsp, 90h
0x18003d7d0  mov     rax, cs:__security_cookie
0x18003d7d7  xor     rax, rsp
0x18003d7da  mov     [rbp+57h+var_28], rax
0x18003d7de  mov     rax, rdx
0x18003d7e1  xor     r15d, r15d
0x18003d7e4  mov     [rbp+57h+packageInfoReference], r15
0x18003d7e8  lea     r9, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003d7ec  xor     r8d, r8d; reserved
0x18003d7ef  mov     rdx, rcx; packageFullName
0x18003d7f2  mov     rcx, rax; userSid
0x18003d7f5  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003d7fc  nop     dword ptr [rax+rax+00h]
0x18003d801  mov     rcx, [rbp+5Fh]
0x18003d805  test    eax, eax
0x18003d807  jnz     loc_18003DAB3
0x18003d80d  mov     [rbp+57h+bufferLength], r15d
0x18003d811  mov     [rbp+57h+var_7C], r15d
0x18003d815  lea     rax, [rbp+57h+var_7C]
0x18003d819  mov     qword ptr [rsp+0B0h+count], rax; int
0x18003d81e  xor     r9d, r9d; buffer
0x18003d821  lea     r8, [rbp+57h+bufferLength]; bufferLength
0x18003d825  mov     esi, 40110h
0x18003d82a  mov     edx, esi; flags
0x18003d82c  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003d830  call    cs:__imp_GetPackageInfo
0x18003d837  nop     dword ptr [rax+rax+00h]
0x18003d83c  cmp     eax, 7Ah ; 'z'
0x18003d83f  jz      short loc_18003D849
0x18003d841  mov     cl, 1
0x18003d843  test    eax, eax
0x18003d845  jg      short loc_18003D84C
0x18003d847  jmp     short loc_18003D854
0x18003d849  mov     cl, r15b
0x18003d84c  movzx   eax, ax
0x18003d84f  or      eax, 80070000h
0x18003d854  mov     r10, [rbp+5Fh]
0x18003d858  test    cl, cl
0x18003d85a  jnz     loc_18003DAC8
0x18003d860  mov     ebx, [rbp+57h+bufferLength]
0x18003d863  mov     ecx, ebx; unsigned __int64
0x18003d865  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003d86a  mov     rdi, rax
0x18003d86d  mov     r8d, ebx; Size
0x18003d870  xor     edx, edx; Val
0x18003d872  mov     rcx, rax; void *
0x18003d875  call    memset_0
0x18003d87a  mov     [rbp+57h+var_50], rdi
0x18003d87e  lea     rax, [rbp+57h+var_7C]
0x18003d882  mov     qword ptr [rsp+0B0h+count], rax; int
0x18003d887  mov     r9, rdi; buffer
0x18003d88a  lea     r8, [rbp+57h+bufferLength]; bufferLength
0x18003d88e  mov     edx, esi; flags
0x18003d890  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003d894  call    cs:__imp_GetPackageInfo
0x18003d89b  nop     dword ptr [rax+rax+00h]
0x18003d8a0  mov     rcx, [rbp+5Fh]; this
0x18003d8a4  test    eax, eax
0x18003d8a6  jnz     loc_18003DAE0
0x18003d8ac  lea     rcx, [rbp+57h+var_58]
0x18003d8b0  call    ??$GetActivationFactory@UIInspectable@@@wil@@YA?AV?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<IInspectable>(ushort const *)
0x18003d8b5  nop
0x18003d8b6  mov     rcx, [rbp+57h+var_58]
0x18003d8ba  mov     [rbp+57h+var_60], r15
0x18003d8be  mov     rax, [rcx]
0x18003d8c1  lea     r8, [rbp+57h+var_60]
0x18003d8c5  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18003d8cc  mov     rax, [rax]
0x18003d8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8d4  mov     rcx, [rbp+5Fh]; this
0x18003d8d8  test    eax, eax
0x18003d8da  js      loc_18003DAF5
0x18003d8e0  mov     ebx, r15d
0x18003d8e3  cmp     [rbp+57h+var_7C], r15d
0x18003d8e7  jbe     loc_18003D9C6
0x18003d8ed  mov     [rbp+57h+var_70], r15
0x18003d8f1  mov     rsi, [rbp+57h+var_60]
0x18003d8f5  mov     r14, [rsi]
0x18003d8f8  mov     [rbp+57h+var_70], r15
0x18003d8fc  mov     [rbp+57h+string], r15
0x18003d900  mov     eax, ebx
0x18003d902  lea     rcx, [rax+rax*4]
0x18003d906  add     rcx, rcx
0x18003d909  mov     rcx, [rdi+rcx*8+10h]; sourceString
0x18003d90e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003d912  inc     rdx; int
0x18003d915  cmp     [rcx+rdx*2], r15w
0x18003d91a  jnz     short loc_18003D912
0x18003d91c  mov     eax, 0FFFFFFFFh
0x18003d921  cmp     rdx, rax
0x18003d924  ja      loc_18003DAA8
0x18003d92a  lea     eax, [rdx+1]
0x18003d92d  cmp     eax, edx
0x18003d92f  jb      loc_18003DA9D
0x18003d935  lea     r9, [rbp+57h+string]; string
0x18003d939  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003d93d  call    cs:__imp_WindowsCreateStringReference
0x18003d944  nop     dword ptr [rax+rax+00h]
0x18003d949  test    eax, eax
0x18003d94b  js      loc_18003DB34
0x18003d951  lea     r8, [rbp+57h+var_70]
0x18003d955  mov     rdx, [rbp+57h+string]
0x18003d959  mov     rcx, rsi
0x18003d95c  mov     rax, [r14+0B0h]
0x18003d963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d968  mov     rcx, [rbp+5Fh]; this
0x18003d96c  test    eax, eax
0x18003d96e  js      loc_18003DB1F
0x18003d974  mov     [rbp+57h+var_80], r15b
0x18003d978  mov     rcx, [rbp+57h+var_70]
0x18003d97c  mov     rax, [rcx]
0x18003d97f  lea     rdx, [rbp+57h+var_80]
0x18003d983  mov     rax, [rax+2D8h]
0x18003d98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d98f  mov     rcx, [rbp+5Fh]; this
0x18003d993  test    eax, eax
0x18003d995  js      loc_18003DB0A
0x18003d99b  cmp     [rbp+57h+var_80], r15b
0x18003d99f  jnz     loc_18003DA36
0x18003d9a5  mov     rcx, [rbp+57h+var_70]
0x18003d9a9  test    rcx, rcx
0x18003d9ac  jz      short loc_18003D9BB
0x18003d9ae  mov     rax, [rcx]
0x18003d9b1  mov     rax, [rax+10h]
0x18003d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9ba  nop
0x18003d9bb  inc     ebx
0x18003d9bd  cmp     ebx, [rbp+57h+var_7C]
0x18003d9c0  jb      loc_18003D8ED
0x18003d9c6  mov     rcx, [rbp+57h+var_60]
0x18003d9ca  test    rcx, rcx
0x18003d9cd  jz      short loc_18003D9DC
0x18003d9cf  mov     rax, [rcx]
0x18003d9d2  mov     rax, [rax+10h]
0x18003d9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9db  nop
0x18003d9dc  mov     rcx, [rbp+57h+var_58]
0x18003d9e0  test    rcx, rcx
0x18003d9e3  jz      short loc_18003D9F2
0x18003d9e5  mov     rax, [rcx]
0x18003d9e8  mov     rax, [rax+10h]
0x18003d9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9f1  nop
0x18003d9f2  mov     rcx, rdi; void *
0x18003d9f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003d9fa  nop
0x18003d9fb  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003d9ff  test    rcx, rcx
0x18003da02  jz      short loc_18003DA10
0x18003da04  call    cs:__imp_ClosePackageInfo
0x18003da0b  nop     dword ptr [rax+rax+00h]
0x18003da10  xor     al, al
0x18003da12  mov     rcx, [rbp+57h+var_28]
0x18003da16  xor     rcx, rsp; StackCookie
0x18003da19  call    __security_check_cookie
0x18003da1e  mov     rbx, [rsp+0B0h+arg_10]
0x18003da26  add     rsp, 90h
0x18003da2d  pop     r15
0x18003da2f  pop     r14
0x18003da31  pop     rdi
0x18003da32  pop     rsi
0x18003da33  pop     rbp
0x18003da34  retn
0x18003da36  mov     rcx, [rbp+57h+var_70]
0x18003da3a  test    rcx, rcx
0x18003da3d  jz      short loc_18003DA4C
0x18003da3f  mov     rax, [rcx]
0x18003da42  mov     rax, [rax+10h]
0x18003da46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da4b  nop
0x18003da4c  mov     rcx, [rbp+57h+var_60]
0x18003da50  test    rcx, rcx
0x18003da53  jz      short loc_18003DA62
0x18003da55  mov     rax, [rcx]
0x18003da58  mov     rax, [rax+10h]
0x18003da5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da61  nop
0x18003da62  mov     rcx, [rbp+57h+var_58]
0x18003da66  test    rcx, rcx
0x18003da69  jz      short loc_18003DA78
0x18003da6b  mov     rax, [rcx]
0x18003da6e  mov     rax, [rax+10h]
0x18003da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da77  nop
0x18003da78  mov     rcx, rdi; void *
0x18003da7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003da80  nop
0x18003da81  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18003da85  test    rcx, rcx
0x18003da88  jz      short loc_18003DA96
0x18003da8a  call    cs:__imp_ClosePackageInfo
0x18003da91  nop     dword ptr [rax+rax+00h]
0x18003da96  mov     al, 1
0x18003da98  jmp     loc_18003DA12
0x18003da9d  mov     ecx, 80070216h; this
0x18003daa2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003daa7  int     3; Trap to Debugger
0x18003daa8  mov     ecx, 80070216h; this
0x18003daad  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003dab2  nop
0x18003dab3  mov     r9d, eax; char *
0x18003dab6  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003dabd  mov     edx, 312h; void *
0x18003dac2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003dac8  mov     r9d, eax; char *
0x18003dacb  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003dad2  mov     edx, 31Ah; void *
0x18003dad7  mov     rcx, r10; this
0x18003dada  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003dae0  mov     r9d, eax; char *
0x18003dae3  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003daea  mov     edx, 31Dh; void *
0x18003daef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003daf5  mov     r9d, eax; char *
0x18003daf8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003daff  mov     edx, 1CBEh; void *
0x18003db04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003db0a  mov     r9d, eax; char *
0x18003db0d  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003db14  mov     edx, 32Ah; void *
0x18003db19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003db1f  mov     r9d, eax; char *
0x18003db22  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003db29  mov     edx, 327h; void *
0x18003db2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003db34  mov     ecx, eax; this
0x18003db36  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
