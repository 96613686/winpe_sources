# GetRelativePathFromRelatedSet(ushort const *,void *,ushort const *,ushort const *,bool,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18003c3dc`
- end: `0x18003c7d4`
- name: `?GetRelativePathFromRelatedSet@@YA_NPEBGPEAX00_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1016`
- prototype: `__int64 __usercall@<rax>(PCWSTR packageFullName@<rcx>, PSID userSid@<rdx>, char, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003fca0`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x180009484`
- `0x180010a84`
- `0x180011820`
- `0x180013100`
- `0x18003bf38`
- `0x18003c3dc`
- `0x18003cc84`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c602`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c602`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003c46e`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003c4e8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003c46e`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003c4e8`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c62c`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c657`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c69a`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c727`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c62c`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c657`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c69a`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003c727`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003c434`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003c52d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003c434`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003c52d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003c55a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003c5cb`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003c55a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003c5cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall GetRelativePathFromRelatedSet(
        PCWSTR packageFullName,
        PSID userSid,
        const WCHAR *a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  unsigned int v7; // esi
  unsigned int v8; // eax
  LONG PackageInfo; // eax
  bool v10; // cl
  unsigned __int64 v11; // r9
  UINT32 v12; // ebx
  void *v13; // rdi
  unsigned int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned int v16; // r14d
  unsigned int v17; // eax
  LONG PackageApplicationIds; // eax
  bool v19; // cl
  unsigned __int64 v20; // r9
  UINT32 v21; // ebx
  void *v22; // rsi
  unsigned int v23; // eax
  unsigned __int64 v24; // rdx
  __int64 v25; // rbx
  unsigned __int64 v27; // rdx
  char v28; // al
  __int128 *v29; // rdx
  unsigned int count; // [rsp+20h] [rbp-79h]
  int counta; // [rsp+20h] [rbp-79h]
  unsigned int countb; // [rsp+20h] [rbp-79h]
  UINT32 v33; // [rsp+30h] [rbp-69h] BYREF
  UINT32 v34; // [rsp+34h] [rbp-65h] BYREF
  UINT32 v35; // [rsp+38h] [rbp-61h] BYREF
  UINT32 bufferLength; // [rsp+3Ch] [rbp-5Dh] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+40h] [rbp-59h] BYREF
  PACKAGE_INFO_REFERENCE v38; // [rsp+48h] [rbp-51h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-49h]
  PSID userSida; // [rsp+58h] [rbp-41h]
  void *v41; // [rsp+60h] [rbp-39h]
  void *v42; // [rsp+68h] [rbp-31h]
  __int128 v43; // [rsp+70h] [rbp-29h] BYREF
  __int64 v44; // [rsp+80h] [rbp-19h]
  unsigned __int64 v45; // [rsp+88h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  lpString2 = a3;
  userSida = userSid;
  v7 = a5 != 0 ? 0xFFFC0010 : 0;
  packageInfoReference = 0;
  v8 = OpenPackageInfoByFullNameForUser(userSid, packageFullName, 0, &packageInfoReference);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x251,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v8,
      count);
  bufferLength = 0;
  v34 = 0;
  PackageInfo = GetPackageInfo(packageInfoReference, v7 + 262400, &bufferLength, 0, &v34);
  if ( !PackageInfo )
    goto LABEL_26;
  if ( PackageInfo == 122 || (v10 = 0, PackageInfo > 0) )
  {
    v11 = (unsigned __int16)PackageInfo | 0x80070000;
    v10 = PackageInfo == 122;
  }
  else
  {
    v11 = (unsigned int)PackageInfo;
  }
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v11,
      counta);
  v12 = bufferLength;
  v13 = operator new[](bufferLength);
  memset_0(v13, 0, v12);
  v41 = v13;
  v14 = GetPackageInfo(packageInfoReference, v7 + 262400, &bufferLength, (BYTE *)v13, &v34);
  if ( v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v14,
      countb);
  v16 = 0;
  if ( !v34 )
  {
LABEL_25:
    operator delete(v13, v15);
LABEL_26:
    if ( packageInfoReference )
      ClosePackageInfo(packageInfoReference);
    return 0;
  }
  while ( 1 )
  {
    v38 = 0;
    v17 = OpenPackageInfoByFullNameForUser(userSida, *((PCWSTR *)v13 + 10 * v16 + 2), 0, &v38);
    if ( v17 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v17,
        countb);
    v33 = 0;
    v35 = 0;
    PackageApplicationIds = GetPackageApplicationIds(v38, &v35, 0, &v33);
    if ( PackageApplicationIds == 15703 )
      goto LABEL_22;
    if ( PackageApplicationIds == 122 || (v19 = 0, PackageApplicationIds > 0) )
    {
      v20 = (unsigned __int16)PackageApplicationIds | 0x80070000;
      v19 = PackageApplicationIds == 122;
    }
    else
    {
      v20 = (unsigned int)PackageApplicationIds;
    }
    if ( !v19 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v20,
        countb);
    v21 = v35;
    v22 = operator new[](v35);
    memset_0(v22, 0, v21);
    v42 = v22;
    v23 = GetPackageApplicationIds(v38, &v35, (BYTE *)v22, &v33);
    if ( v23 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x20A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v23,
        countb);
    v25 = 0;
    if ( v33 )
      break;
LABEL_21:
    operator delete(v22, v24);
LABEL_22:
    if ( v38 )
      ClosePackageInfo(v38);
    if ( ++v16 >= v34 )
      goto LABEL_25;
  }
  while ( CompareStringOrdinal(*((LPCWCH *)v22 + v25), -1, lpString2, -1, 1) != 2 )
  {
    v25 = (unsigned int)(v25 + 1);
    if ( (unsigned int)v25 >= v33 )
      goto LABEL_21;
  }
  operator delete(v22, v24);
  if ( v38 )
    ClosePackageInfo(v38);
  if ( !(unsigned __int8)MakeFullPathRelative(a4, *((_QWORD *)v13 + 10 * v16 + 1), a6) )
  {
    v43 = 0;
    v44 = 0;
    v45 = 7;
    LOWORD(v43) = 0;
    GetMachineExternalLocation(userSida, (__int64)lpString2);
    if ( !v28 )
      goto LABEL_45;
    v29 = &v43;
    if ( v45 > 7 )
      v29 = (__int128 *)v43;
    if ( !(unsigned __int8)MakeFullPathRelative(a4, v29, a6) )
LABEL_45:
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x490,
        countb);
    std::wstring::~wstring(&v43);
  }
  operator delete(v13, v27);
  if ( packageInfoReference )
    ClosePackageInfo(packageInfoReference);
  return 1;
}

```

## disassembly

```asm
0x18003c3dc  push    rbp
0x18003c3de  push    rbx
0x18003c3df  push    rsi
0x18003c3e0  push    rdi
0x18003c3e1  push    r12
0x18003c3e3  push    r13
0x18003c3e5  push    r14
0x18003c3e7  push    r15
0x18003c3e9  lea     rbp, [rsp-0Fh]
0x18003c3ee  sub     rsp, 0A8h
0x18003c3f5  mov     rax, cs:__security_cookie
0x18003c3fc  xor     rax, rsp
0x18003c3ff  mov     [rbp+47h+var_50], rax
0x18003c403  mov     r12, r9
0x18003c406  mov     [rbp+47h+lpString2], r8
0x18003c40a  mov     rax, rdx
0x18003c40d  mov     [rbp+47h+userSid], rdx
0x18003c411  mov     r13, [rbp+47h+arg_28]
0x18003c415  xor     r15d, r15d
0x18003c418  neg     [rbp+47h+arg_20]
0x18003c41b  sbb     esi, esi
0x18003c41d  and     esi, 0FFFC0010h
0x18003c423  mov     [rbp+47h+packageInfoReference], r15
0x18003c427  lea     r9, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003c42b  xor     r8d, r8d; reserved
0x18003c42e  mov     rdx, rcx; packageFullName
0x18003c431  mov     rcx, rax; userSid
0x18003c434  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003c43b  nop     dword ptr [rax+rax+00h]
0x18003c440  mov     rcx, [rbp+4Fh]; this
0x18003c444  test    eax, eax
0x18003c446  jnz     loc_18003C764
0x18003c44c  mov     [rbp+47h+bufferLength], r15d
0x18003c450  mov     [rbp+47h+var_AC], r15d
0x18003c454  lea     rax, [rbp+47h+var_AC]
0x18003c458  mov     qword ptr [rsp+0E0h+count], rax; int
0x18003c45d  xor     r9d, r9d; buffer
0x18003c460  lea     r8, [rbp+47h+bufferLength]; bufferLength
0x18003c464  lea     edx, [rsi+40100h]; flags
0x18003c46a  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003c46e  call    cs:__imp_GetPackageInfo
0x18003c475  nop     dword ptr [rax+rax+00h]
0x18003c47a  test    eax, eax
0x18003c47c  jz      loc_18003C64E
0x18003c482  cmp     eax, 7Ah ; 'z'
0x18003c485  jz      short loc_18003C493
0x18003c487  mov     cl, r15b
0x18003c48a  test    eax, eax
0x18003c48c  jg      short loc_18003C493
0x18003c48e  mov     r9d, eax
0x18003c491  jmp     short loc_18003C4A4
0x18003c493  movzx   r9d, ax
0x18003c497  or      r9d, 80070000h; char *
0x18003c49e  cmp     eax, 7Ah ; 'z'
0x18003c4a1  setz    cl
0x18003c4a4  mov     rax, [rbp+4Fh]
0x18003c4a8  test    cl, cl
0x18003c4aa  jz      loc_18003C779
0x18003c4b0  mov     ebx, [rbp+47h+bufferLength]
0x18003c4b3  mov     ecx, ebx; unsigned __int64
0x18003c4b5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c4ba  mov     rdi, rax
0x18003c4bd  mov     r8d, ebx; Size
0x18003c4c0  xor     edx, edx; Val
0x18003c4c2  mov     rcx, rax; void *
0x18003c4c5  call    memset_0
0x18003c4ca  mov     [rbp+47h+var_80], rdi
0x18003c4ce  lea     rax, [rbp+47h+var_AC]
0x18003c4d2  mov     qword ptr [rsp+0E0h+count], rax; unsigned int
0x18003c4d7  mov     r9, rdi; buffer
0x18003c4da  lea     r8, [rbp+47h+bufferLength]; bufferLength
0x18003c4de  lea     edx, [rsi+40100h]; flags
0x18003c4e4  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003c4e8  call    cs:__imp_GetPackageInfo
0x18003c4ef  nop     dword ptr [rax+rax+00h]
0x18003c4f4  mov     rcx, [rbp+4Fh]; this
0x18003c4f8  test    eax, eax
0x18003c4fa  jnz     loc_18003C78E
0x18003c500  mov     r14d, r15d
0x18003c503  cmp     [rbp+47h+var_AC], r15d
0x18003c507  jbe     loc_18003C645
0x18003c50d  mov     eax, r14d
0x18003c510  lea     r15, [rax+rax*4]
0x18003c514  add     r15, r15
0x18003c517  xor     ebx, ebx
0x18003c519  mov     [rbp+47h+var_98], rbx
0x18003c51d  lea     r9, [rbp+47h+var_98]; packageInfoReference
0x18003c521  xor     r8d, r8d; reserved
0x18003c524  mov     rdx, [rdi+r15*8+10h]; packageFullName
0x18003c529  mov     rcx, [rbp+47h+userSid]; userSid
0x18003c52d  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003c534  nop     dword ptr [rax+rax+00h]
0x18003c539  mov     rcx, [rbp+4Fh]; this
0x18003c53d  test    eax, eax
0x18003c53f  jnz     loc_18003C74F
0x18003c545  mov     [rbp+47h+var_B0], ebx
0x18003c548  mov     [rbp+47h+var_A8], ebx
0x18003c54b  lea     r9, [rbp+47h+var_B0]; count
0x18003c54f  xor     r8d, r8d; buffer
0x18003c552  lea     rdx, [rbp+47h+var_A8]; bufferLength
0x18003c556  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003c55a  call    cs:__imp_GetPackageApplicationIds
0x18003c561  nop     dword ptr [rax+rax+00h]
0x18003c566  cmp     eax, 3D57h
0x18003c56b  jz      loc_18003C623
0x18003c571  cmp     eax, 7Ah ; 'z'
0x18003c574  jz      short loc_18003C581
0x18003c576  mov     cl, bl
0x18003c578  test    eax, eax
0x18003c57a  jg      short loc_18003C581
0x18003c57c  mov     r9d, eax
0x18003c57f  jmp     short loc_18003C592
0x18003c581  movzx   r9d, ax
0x18003c585  or      r9d, 80070000h; char *
0x18003c58c  cmp     eax, 7Ah ; 'z'
0x18003c58f  setz    cl
0x18003c592  mov     rax, [rbp+4Fh]
0x18003c596  test    cl, cl
0x18003c598  jz      loc_18003C73A
0x18003c59e  mov     ebx, [rbp+47h+var_A8]
0x18003c5a1  mov     ecx, ebx; unsigned __int64
0x18003c5a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c5a8  mov     rsi, rax
0x18003c5ab  mov     r8d, ebx; Size
0x18003c5ae  xor     edx, edx; Val
0x18003c5b0  mov     rcx, rax; void *
0x18003c5b3  call    memset_0
0x18003c5b8  mov     [rbp+47h+var_78], rsi
0x18003c5bc  lea     r9, [rbp+47h+var_B0]; count
0x18003c5c0  mov     r8, rsi; buffer
0x18003c5c3  lea     rdx, [rbp+47h+var_A8]; bufferLength
0x18003c5c7  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003c5cb  call    cs:__imp_GetPackageApplicationIds
0x18003c5d2  nop     dword ptr [rax+rax+00h]
0x18003c5d7  mov     rcx, [rbp+4Fh]; this
0x18003c5db  test    eax, eax
0x18003c5dd  jnz     loc_18003C7BF
0x18003c5e3  xor     ebx, ebx
0x18003c5e5  cmp     [rbp+47h+var_B0], ebx
0x18003c5e8  jbe     short loc_18003C61A
0x18003c5ea  mov     [rsp+0E0h+count], 1; unsigned int
0x18003c5f2  or      eax, 0FFFFFFFFh
0x18003c5f5  mov     r9d, eax; cchCount2
0x18003c5f8  mov     r8, [rbp+47h+lpString2]; lpString2
0x18003c5fc  mov     edx, eax; cchCount1
0x18003c5fe  mov     rcx, [rsi+rbx*8]; lpString1
0x18003c602  call    cs:__imp_CompareStringOrdinal
0x18003c609  nop     dword ptr [rax+rax+00h]
0x18003c60e  cmp     eax, 2
0x18003c611  jz      short loc_18003C686
0x18003c613  inc     ebx
0x18003c615  cmp     ebx, [rbp+47h+var_B0]
0x18003c618  jb      short loc_18003C5EA
0x18003c61a  mov     rcx, rsi; void *
0x18003c61d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c622  nop
0x18003c623  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003c627  test    rcx, rcx
0x18003c62a  jz      short loc_18003C638
0x18003c62c  call    cs:__imp_ClosePackageInfo
0x18003c633  nop     dword ptr [rax+rax+00h]
0x18003c638  inc     r14d
0x18003c63b  cmp     r14d, [rbp+47h+var_AC]
0x18003c63f  jb      loc_18003C50D
0x18003c645  mov     rcx, rdi; void *
0x18003c648  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c64d  nop
0x18003c64e  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003c652  test    rcx, rcx
0x18003c655  jz      short loc_18003C663
0x18003c657  call    cs:__imp_ClosePackageInfo
0x18003c65e  nop     dword ptr [rax+rax+00h]
0x18003c663  xor     al, al
0x18003c665  mov     rcx, [rbp+47h+var_50]
0x18003c669  xor     rcx, rsp; StackCookie
0x18003c66c  call    __security_check_cookie
0x18003c671  add     rsp, 0A8h
0x18003c678  pop     r15
0x18003c67a  pop     r14
0x18003c67c  pop     r13
0x18003c67e  pop     r12
0x18003c680  pop     rdi
0x18003c681  pop     rsi
0x18003c682  pop     rbx
0x18003c683  pop     rbp
0x18003c684  retn
0x18003c686  mov     rcx, rsi; void *
0x18003c689  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c68e  nop
0x18003c68f  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003c693  xor     ebx, ebx
0x18003c695  test    rcx, rcx
0x18003c698  jz      short loc_18003C6A6
0x18003c69a  call    cs:__imp_ClosePackageInfo
0x18003c6a1  nop     dword ptr [rax+rax+00h]
0x18003c6a6  mov     r8, r13
0x18003c6a9  mov     rdx, [rdi+r15*8+8]
0x18003c6ae  mov     rcx, r12
0x18003c6b1  call    ?MakeFullPathRelative@@YA_NPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MakeFullPathRelative(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003c6b6  test    al, al
0x18003c6b8  jnz     short loc_18003C715
0x18003c6ba  xorps   xmm0, xmm0
0x18003c6bd  movups  [rbp+47h+var_70], xmm0
0x18003c6c1  mov     [rbp+47h+var_60], rbx
0x18003c6c5  mov     [rbp+47h+var_58], 7
0x18003c6cd  mov     word ptr [rbp+47h+var_70], bx
0x18003c6d1  lea     r8, [rbp+47h+var_70]
0x18003c6d5  mov     rdx, [rbp+47h+lpString2]
0x18003c6d9  mov     rcx, [rbp+47h+userSid]; Sid
0x18003c6dd  call    ?GetMachineExternalLocation@@YA_NPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMachineExternalLocation(void *,ushort const *,std::wstring &)
0x18003c6e2  test    al, al
0x18003c6e4  jz      loc_18003C7A3
0x18003c6ea  lea     rdx, [rbp+47h+var_70]
0x18003c6ee  cmp     [rbp+47h+var_58], 7
0x18003c6f3  cmova   rdx, qword ptr [rbp+47h+var_70]
0x18003c6f8  mov     r8, r13
0x18003c6fb  mov     rcx, r12
0x18003c6fe  call    ?MakeFullPathRelative@@YA_NPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MakeFullPathRelative(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003c703  test    al, al
0x18003c705  jz      loc_18003C7A3
0x18003c70b  lea     rcx, [rbp+47h+var_70]; void *
0x18003c70f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c714  nop
0x18003c715  mov     rcx, rdi; void *
0x18003c718  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c71d  nop
0x18003c71e  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003c722  test    rcx, rcx
0x18003c725  jz      short loc_18003C733
0x18003c727  call    cs:__imp_ClosePackageInfo
0x18003c72e  nop     dword ptr [rax+rax+00h]
0x18003c733  mov     al, 1
0x18003c735  jmp     loc_18003C665
0x18003c73a  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c741  mov     edx, 207h; void *
0x18003c746  mov     rcx, rax; this
0x18003c749  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c74f  mov     r9d, eax; char *
0x18003c752  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c759  mov     edx, 1FDh; void *
0x18003c75e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c764  mov     r9d, eax; char *
0x18003c767  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c76e  mov     edx, 251h; void *
0x18003c773  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c779  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c780  mov     edx, 25Ch; void *
0x18003c785  mov     rcx, rax; this
0x18003c788  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c78e  mov     r9d, eax; char *
0x18003c791  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c798  mov     edx, 25Fh; void *
0x18003c79d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c7a3  mov     rcx, [rbp+4Fh]; this
0x18003c7a7  mov     r9d, 490h; char *
0x18003c7ad  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c7b4  mov     edx, 275h; void *
0x18003c7b9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c7bf  mov     r9d, eax; char *
0x18003c7c2  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c7c9  mov     edx, 20Ah; void *
0x18003c7ce  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
