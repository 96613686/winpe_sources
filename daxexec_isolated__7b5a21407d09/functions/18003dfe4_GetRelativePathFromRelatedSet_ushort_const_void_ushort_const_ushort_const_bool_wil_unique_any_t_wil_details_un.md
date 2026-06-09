# GetRelativePathFromRelatedSet(ushort const *,void *,ushort const *,ushort const *,bool,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18003dfe4`
- end: `0x18003e3d1`
- name: `?GetRelativePathFromRelatedSet@@YA_NPEBGPEAX00_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1005`
- prototype: `__int64 __usercall@<rax>(PCWSTR packageFullName@<rcx>, PSID Sid@<rdx>, char, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041a70`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800059a8`
- `0x18000afe4`
- `0x1800125f4`
- `0x180013510`
- `0x180014e74`
- `0x18003db44`
- `0x18003dfe4`
- `0x18003e974`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e1f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e1f8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003e075`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003e0e7`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003e075`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18003e0e7`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e222`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e24d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e28e`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e324`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e222`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e24d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e28e`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18003e324`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003e03d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003e128`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003e03d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18003e128`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003e155`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003e1c1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003e155`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18003e1c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall GetRelativePathFromRelatedSet(
        PCWSTR packageFullName,
        PSID Sid,
        const WCHAR *a3,
        const WCHAR *a4,
        char a5,
        LPVOID *a6)
{
  unsigned int v8; // esi
  unsigned int v9; // eax
  LONG PackageInfo; // eax
  bool v11; // cl
  unsigned __int64 v12; // r9
  UINT32 v13; // ebx
  void *v14; // rdi
  unsigned int v15; // eax
  unsigned __int64 v16; // rdx
  __int64 v17; // r14
  unsigned int v18; // eax
  LONG PackageApplicationIds; // eax
  bool v20; // cl
  unsigned __int64 v21; // r9
  UINT32 v22; // ebx
  void *v23; // rsi
  unsigned int v24; // eax
  unsigned __int64 v25; // rdx
  __int64 v26; // rbx
  LPVOID *v28; // rbx
  unsigned __int64 v29; // rdx
  char v30; // al
  const WCHAR *v31; // rdx
  unsigned int count; // [rsp+20h] [rbp-79h]
  int counta; // [rsp+20h] [rbp-79h]
  unsigned int countb; // [rsp+20h] [rbp-79h]
  UINT32 v35; // [rsp+30h] [rbp-69h] BYREF
  UINT32 v36; // [rsp+34h] [rbp-65h] BYREF
  UINT32 v37; // [rsp+38h] [rbp-61h] BYREF
  UINT32 bufferLength; // [rsp+3Ch] [rbp-5Dh] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+40h] [rbp-59h] BYREF
  PACKAGE_INFO_REFERENCE v40; // [rsp+48h] [rbp-51h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-49h]
  LPVOID *v42; // [rsp+58h] [rbp-41h]
  void *v43; // [rsp+60h] [rbp-39h]
  void *v44; // [rsp+68h] [rbp-31h]
  __int128 v45; // [rsp+70h] [rbp-29h] BYREF
  __int64 v46; // [rsp+80h] [rbp-19h]
  unsigned __int64 v47; // [rsp+88h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  lpString2 = a3;
  v42 = a6;
  v8 = a5 != 0 ? 0xFFFC0010 : 0;
  packageInfoReference = 0;
  v9 = OpenPackageInfoByFullNameForUser(Sid, packageFullName, 0, &packageInfoReference);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x251,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v9,
      count);
  bufferLength = 0;
  v36 = 0;
  PackageInfo = GetPackageInfo(packageInfoReference, v8 + 262400, &bufferLength, 0, &v36);
  if ( !PackageInfo )
    goto LABEL_24;
  if ( PackageInfo > 0 )
  {
    v12 = (unsigned __int16)PackageInfo | 0x80070000;
    v11 = PackageInfo == 122;
  }
  else
  {
    v11 = 0;
    v12 = (unsigned int)PackageInfo;
  }
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v12,
      counta);
  v13 = bufferLength;
  v14 = operator new[](bufferLength);
  memset_0(v14, 0, v13);
  v43 = v14;
  v15 = GetPackageInfo(packageInfoReference, v8 + 262400, &bufferLength, (BYTE *)v14, &v36);
  if ( v15 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)v15,
      countb);
  v17 = 0;
  if ( !v36 )
  {
LABEL_23:
    operator delete(v14, v16);
LABEL_24:
    if ( packageInfoReference )
      ClosePackageInfo(packageInfoReference);
    return 0;
  }
  while ( 1 )
  {
    v40 = 0;
    v18 = OpenPackageInfoByFullNameForUser(Sid, *((PCWSTR *)v14 + 10 * v17 + 2), 0, &v40);
    if ( v18 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v18,
        countb);
    v35 = 0;
    v37 = 0;
    PackageApplicationIds = GetPackageApplicationIds(v40, &v37, 0, &v35);
    if ( PackageApplicationIds == 15703 )
      goto LABEL_20;
    if ( PackageApplicationIds > 0 )
    {
      v21 = (unsigned __int16)PackageApplicationIds | 0x80070000;
      v20 = PackageApplicationIds == 122;
    }
    else
    {
      v20 = 0;
      v21 = (unsigned int)PackageApplicationIds;
    }
    if ( !v20 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v21,
        countb);
    v22 = v37;
    v23 = operator new[](v37);
    memset_0(v23, 0, v22);
    v44 = v23;
    v24 = GetPackageApplicationIds(v40, &v37, (BYTE *)v23, &v35);
    if ( v24 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x20A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v24,
        countb);
    v26 = 0;
    if ( v35 )
      break;
LABEL_19:
    operator delete(v23, v25);
LABEL_20:
    if ( v40 )
      ClosePackageInfo(v40);
    v17 = (unsigned int)(v17 + 1);
    if ( (unsigned int)v17 >= v36 )
      goto LABEL_23;
  }
  while ( CompareStringOrdinal(*((LPCWCH *)v23 + v26), -1, lpString2, -1, 1) != 2 )
  {
    v26 = (unsigned int)(v26 + 1);
    if ( (unsigned int)v26 >= v35 )
      goto LABEL_19;
  }
  operator delete(v23, v25);
  if ( v40 )
    ClosePackageInfo(v40);
  v28 = v42;
  if ( !MakeFullPathRelative(a4, *((const WCHAR **)v14 + 10 * v17 + 1), v42) )
  {
    v45 = 0;
    v46 = 0;
    v47 = 7;
    LOWORD(v45) = 0;
    GetMachineExternalLocation(Sid, (__int64)lpString2);
    if ( !v30 )
      goto LABEL_43;
    v31 = (const WCHAR *)&v45;
    if ( v47 > 7 )
      v31 = (const WCHAR *)v45;
    if ( !MakeFullPathRelative(a4, v31, v28) )
LABEL_43:
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x490,
        countb);
    std::wstring::~wstring(&v45);
  }
  operator delete(v14, v29);
  if ( packageInfoReference )
    ClosePackageInfo(packageInfoReference);
  return 1;
}

```

## disassembly

```asm
0x18003dfe4  push    rbp
0x18003dfe6  push    rbx
0x18003dfe7  push    rsi
0x18003dfe8  push    rdi
0x18003dfe9  push    r12
0x18003dfeb  push    r13
0x18003dfed  push    r14
0x18003dfef  push    r15
0x18003dff1  lea     rbp, [rsp-0Fh]
0x18003dff6  sub     rsp, 0A8h
0x18003dffd  mov     rax, cs:__security_cookie
0x18003e004  xor     rax, rsp
0x18003e007  mov     [rbp+47h+var_50], rax
0x18003e00b  mov     r13, r9
0x18003e00e  mov     [rbp+47h+lpString2], r8
0x18003e012  mov     r12, rdx
0x18003e015  mov     rax, [rbp+47h+arg_28]
0x18003e019  mov     [rbp+47h+var_88], rax
0x18003e01d  neg     [rbp+47h+arg_20]
0x18003e020  sbb     esi, esi
0x18003e022  and     esi, 0FFFC0010h
0x18003e028  mov     [rbp+47h+packageInfoReference], 0
0x18003e030  lea     r9, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003e034  xor     r8d, r8d; reserved
0x18003e037  mov     rdx, rcx; packageFullName
0x18003e03a  mov     rcx, r12; userSid
0x18003e03d  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003e044  nop     dword ptr [rax+rax+00h]
0x18003e049  mov     rcx, [rbp+4Fh]; this
0x18003e04d  test    eax, eax
0x18003e04f  jnz     loc_18003E361
0x18003e055  mov     [rbp+47h+bufferLength], eax
0x18003e058  mov     [rbp+47h+var_AC], eax
0x18003e05b  lea     rax, [rbp+47h+var_AC]
0x18003e05f  mov     qword ptr [rsp+0E0h+count], rax; int
0x18003e064  xor     r9d, r9d; buffer
0x18003e067  lea     r8, [rbp+47h+bufferLength]; bufferLength
0x18003e06b  lea     edx, [rsi+40100h]; flags
0x18003e071  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003e075  call    cs:__imp_GetPackageInfo
0x18003e07c  nop     dword ptr [rax+rax+00h]
0x18003e081  test    eax, eax
0x18003e083  jz      loc_18003E244
0x18003e089  jg      short loc_18003E092
0x18003e08b  xor     cl, cl
0x18003e08d  mov     r9d, eax
0x18003e090  jmp     short loc_18003E0A3
0x18003e092  movzx   r9d, ax
0x18003e096  or      r9d, 80070000h; char *
0x18003e09d  cmp     eax, 7Ah ; 'z'
0x18003e0a0  setz    cl
0x18003e0a3  mov     rax, [rbp+4Fh]
0x18003e0a7  test    cl, cl
0x18003e0a9  jz      loc_18003E376
0x18003e0af  mov     ebx, [rbp+47h+bufferLength]
0x18003e0b2  mov     ecx, ebx; unsigned __int64
0x18003e0b4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e0b9  mov     rdi, rax
0x18003e0bc  mov     r8d, ebx; Size
0x18003e0bf  xor     edx, edx; Val
0x18003e0c1  mov     rcx, rax; void *
0x18003e0c4  call    memset_0
0x18003e0c9  mov     [rbp+47h+var_80], rdi
0x18003e0cd  lea     rax, [rbp+47h+var_AC]
0x18003e0d1  mov     qword ptr [rsp+0E0h+count], rax; unsigned int
0x18003e0d6  mov     r9, rdi; buffer
0x18003e0d9  lea     r8, [rbp+47h+bufferLength]; bufferLength
0x18003e0dd  lea     edx, [rsi+40100h]; flags
0x18003e0e3  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003e0e7  call    cs:__imp_GetPackageInfo
0x18003e0ee  nop     dword ptr [rax+rax+00h]
0x18003e0f3  mov     rcx, [rbp+4Fh]; this
0x18003e0f7  test    eax, eax
0x18003e0f9  jnz     loc_18003E38B
0x18003e0ff  xor     r14d, r14d
0x18003e102  cmp     [rbp+47h+var_AC], r14d
0x18003e106  jbe     loc_18003E23B
0x18003e10c  lea     r15, [r14+r14*4]
0x18003e110  add     r15, r15
0x18003e113  xor     ebx, ebx
0x18003e115  mov     [rbp+47h+var_98], rbx
0x18003e119  lea     r9, [rbp+47h+var_98]; packageInfoReference
0x18003e11d  xor     r8d, r8d; reserved
0x18003e120  mov     rdx, [rdi+r15*8+10h]; packageFullName
0x18003e125  mov     rcx, r12; userSid
0x18003e128  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x18003e12f  nop     dword ptr [rax+rax+00h]
0x18003e134  mov     rcx, [rbp+4Fh]; this
0x18003e138  test    eax, eax
0x18003e13a  jnz     loc_18003E34C
0x18003e140  mov     [rbp+47h+var_B0], ebx
0x18003e143  mov     [rbp+47h+var_A8], ebx
0x18003e146  lea     r9, [rbp+47h+var_B0]; count
0x18003e14a  xor     r8d, r8d; buffer
0x18003e14d  lea     rdx, [rbp+47h+var_A8]; bufferLength
0x18003e151  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003e155  call    cs:__imp_GetPackageApplicationIds
0x18003e15c  nop     dword ptr [rax+rax+00h]
0x18003e161  cmp     eax, 3D57h
0x18003e166  jz      loc_18003E219
0x18003e16c  test    eax, eax
0x18003e16e  jg      short loc_18003E177
0x18003e170  mov     cl, bl
0x18003e172  mov     r9d, eax
0x18003e175  jmp     short loc_18003E188
0x18003e177  movzx   r9d, ax
0x18003e17b  or      r9d, 80070000h; char *
0x18003e182  cmp     eax, 7Ah ; 'z'
0x18003e185  setz    cl
0x18003e188  mov     rax, [rbp+4Fh]
0x18003e18c  test    cl, cl
0x18003e18e  jz      loc_18003E337
0x18003e194  mov     ebx, [rbp+47h+var_A8]
0x18003e197  mov     ecx, ebx; unsigned __int64
0x18003e199  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e19e  mov     rsi, rax
0x18003e1a1  mov     r8d, ebx; Size
0x18003e1a4  xor     edx, edx; Val
0x18003e1a6  mov     rcx, rax; void *
0x18003e1a9  call    memset_0
0x18003e1ae  mov     [rbp+47h+var_78], rsi
0x18003e1b2  lea     r9, [rbp+47h+var_B0]; count
0x18003e1b6  mov     r8, rsi; buffer
0x18003e1b9  lea     rdx, [rbp+47h+var_A8]; bufferLength
0x18003e1bd  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003e1c1  call    cs:__imp_GetPackageApplicationIds
0x18003e1c8  nop     dword ptr [rax+rax+00h]
0x18003e1cd  mov     rcx, [rbp+4Fh]; this
0x18003e1d1  test    eax, eax
0x18003e1d3  jnz     loc_18003E3BC
0x18003e1d9  xor     ebx, ebx
0x18003e1db  cmp     [rbp+47h+var_B0], ebx
0x18003e1de  jbe     short loc_18003E210
0x18003e1e0  mov     [rsp+0E0h+count], 1; unsigned int
0x18003e1e8  or      eax, 0FFFFFFFFh
0x18003e1eb  mov     r9d, eax; cchCount2
0x18003e1ee  mov     r8, [rbp+47h+lpString2]; lpString2
0x18003e1f2  mov     edx, eax; cchCount1
0x18003e1f4  mov     rcx, [rsi+rbx*8]; lpString1
0x18003e1f8  call    cs:__imp_CompareStringOrdinal
0x18003e1ff  nop     dword ptr [rax+rax+00h]
0x18003e204  cmp     eax, 2
0x18003e207  jz      short loc_18003E27C
0x18003e209  inc     ebx
0x18003e20b  cmp     ebx, [rbp+47h+var_B0]
0x18003e20e  jb      short loc_18003E1E0
0x18003e210  mov     rcx, rsi; void *
0x18003e213  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e218  nop
0x18003e219  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003e21d  test    rcx, rcx
0x18003e220  jz      short loc_18003E22E
0x18003e222  call    cs:__imp_ClosePackageInfo
0x18003e229  nop     dword ptr [rax+rax+00h]
0x18003e22e  inc     r14d
0x18003e231  cmp     r14d, [rbp+47h+var_AC]
0x18003e235  jb      loc_18003E10C
0x18003e23b  mov     rcx, rdi; void *
0x18003e23e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e243  nop
0x18003e244  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003e248  test    rcx, rcx
0x18003e24b  jz      short loc_18003E259
0x18003e24d  call    cs:__imp_ClosePackageInfo
0x18003e254  nop     dword ptr [rax+rax+00h]
0x18003e259  xor     al, al
0x18003e25b  mov     rcx, [rbp+47h+var_50]
0x18003e25f  xor     rcx, rsp; StackCookie
0x18003e262  call    __security_check_cookie
0x18003e267  add     rsp, 0A8h
0x18003e26e  pop     r15
0x18003e270  pop     r14
0x18003e272  pop     r13
0x18003e274  pop     r12
0x18003e276  pop     rdi
0x18003e277  pop     rsi
0x18003e278  pop     rbx
0x18003e279  pop     rbp
0x18003e27a  retn
0x18003e27c  mov     rcx, rsi; void *
0x18003e27f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e284  nop
0x18003e285  mov     rcx, [rbp+47h+var_98]; packageInfoReference
0x18003e289  test    rcx, rcx
0x18003e28c  jz      short loc_18003E29A
0x18003e28e  call    cs:__imp_ClosePackageInfo
0x18003e295  nop     dword ptr [rax+rax+00h]
0x18003e29a  mov     rbx, [rbp+47h+var_88]
0x18003e29e  mov     r8, rbx
0x18003e2a1  mov     rdx, [rdi+r15*8+8]
0x18003e2a6  mov     rcx, r13
0x18003e2a9  call    ?MakeFullPathRelative@@YA_NPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MakeFullPathRelative(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003e2ae  test    al, al
0x18003e2b0  jnz     short loc_18003E312
0x18003e2b2  xorps   xmm0, xmm0
0x18003e2b5  movups  [rbp+47h+var_70], xmm0
0x18003e2b9  mov     [rbp+47h+var_60], 0
0x18003e2c1  mov     [rbp+47h+var_58], 7
0x18003e2c9  xor     eax, eax
0x18003e2cb  mov     word ptr [rbp+47h+var_70], ax
0x18003e2cf  lea     r8, [rbp+47h+var_70]
0x18003e2d3  mov     rdx, [rbp+47h+lpString2]
0x18003e2d7  mov     rcx, r12; Sid
0x18003e2da  call    ?GetMachineExternalLocation@@YA_NPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMachineExternalLocation(void *,ushort const *,std::wstring &)
0x18003e2df  test    al, al
0x18003e2e1  jz      loc_18003E3A0
0x18003e2e7  lea     rdx, [rbp+47h+var_70]
0x18003e2eb  cmp     [rbp+47h+var_58], 7
0x18003e2f0  cmova   rdx, qword ptr [rbp+47h+var_70]
0x18003e2f5  mov     r8, rbx
0x18003e2f8  mov     rcx, r13
0x18003e2fb  call    ?MakeFullPathRelative@@YA_NPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MakeFullPathRelative(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003e300  test    al, al
0x18003e302  jz      loc_18003E3A0
0x18003e308  lea     rcx, [rbp+47h+var_70]; void *
0x18003e30c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e311  nop
0x18003e312  mov     rcx, rdi; void *
0x18003e315  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e31a  nop
0x18003e31b  mov     rcx, [rbp+47h+packageInfoReference]; packageInfoReference
0x18003e31f  test    rcx, rcx
0x18003e322  jz      short loc_18003E330
0x18003e324  call    cs:__imp_ClosePackageInfo
0x18003e32b  nop     dword ptr [rax+rax+00h]
0x18003e330  mov     al, 1
0x18003e332  jmp     loc_18003E25B
0x18003e337  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e33e  mov     edx, 207h; void *
0x18003e343  mov     rcx, rax; this
0x18003e346  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e34c  mov     r9d, eax; char *
0x18003e34f  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e356  mov     edx, 1FDh; void *
0x18003e35b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003e361  mov     r9d, eax; char *
0x18003e364  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e36b  mov     edx, 251h; void *
0x18003e370  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003e376  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e37d  mov     edx, 25Ch; void *
0x18003e382  mov     rcx, rax; this
0x18003e385  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e38b  mov     r9d, eax; char *
0x18003e38e  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e395  mov     edx, 25Fh; void *
0x18003e39a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003e3a0  mov     rcx, [rbp+4Fh]; this
0x18003e3a4  mov     r9d, 490h; char *
0x18003e3aa  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e3b1  mov     edx, 275h; void *
0x18003e3b6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003e3bc  mov     r9d, eax; char *
0x18003e3bf  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003e3c6  mov     edx, 20Ah; void *
0x18003e3cb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
