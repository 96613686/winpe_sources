# DesktopAppXVFS::ACLWritablePackageRoot(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x18002e3d4`
- end: `0x18002e5e5`
- name: `?ACLWritablePackageRoot@DesktopAppXVFS@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX@Z`
- size: `529`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180033100`

## callees

- `0x1800057fc`
- `0x180005a08`
- `0x18000e074`
- `0x1800125f4`
- `0x180014e74`
- `0x1800160a0`
- `0x18001732c`
- `0x1800210fc`
- `0x18002bb84`
- `0x18002e3d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e54c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e54c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e4aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e4aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002e423`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002e423`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002e50f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002e50f`

## string_xrefs

- `0x18002e58c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall DesktopAppXVFS::ACLWritablePackageRoot(WCHAR *pObjectName, _QWORD *a2, __int64 a3)
{
  int token_information; // eax
  void *v6; // rdi
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r14
  const char *v11; // r9
  struct _ACL *pDacl; // rcx
  DWORD v13; // eax
  unsigned int v14; // eax
  int psidGroup; // [rsp+20h] [rbp-58h]
  int psidGroupa; // [rsp+20h] [rbp-58h]
  unsigned int psidGroupb; // [rsp+20h] [rbp-58h]
  LPWSTR StringSid; // [rsp+40h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-30h] BYREF
  void *Block; // [rsp+50h] [rbp-28h] BYREF
  wchar_t *Buffer[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a3);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      psidGroup);
  StringSid = 0;
  v6 = Block;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v7);
  v8 = a2[2];
  v9 = -1;
  do
    ++v9;
  while ( StringSid[v9] );
  v10 = v8 + v9;
  std::vector<unsigned short>::vector<unsigned short>(Buffer, v8 + v9 + 75);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( swprintf(
         Buffer[0],
         v10 + 75,
         L"D:AI(XA;OICI;0x1200A9;;;BU;(WIN://SYSAPPID Contains \"%s\"))(A;OICI;GA;;;%s)",
         a2,
         StringSid) < 0 )
  {
    v14 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      (const char *)v14,
      psidGroupa);
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(Buffer[0], 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x43F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v11);
  if ( (*((_BYTE *)SecurityDescriptor + 2) & 4) == 0 )
    goto LABEL_10;
  if ( *((__int16 *)SecurityDescriptor + 1) >= 0 )
  {
    pDacl = (struct _ACL *)*((_QWORD *)SecurityDescriptor + 4);
  }
  else
  {
    if ( !*((_DWORD *)SecurityDescriptor + 4) )
    {
LABEL_10:
      pDacl = 0;
      goto LABEL_15;
    }
    pDacl = (struct _ACL *)((char *)SecurityDescriptor + *((unsigned int *)SecurityDescriptor + 4));
  }
LABEL_15:
  if ( *((_QWORD *)pObjectName + 3) > 7u )
    pObjectName = *(WCHAR **)pObjectName;
  v13 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x445,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      (const char *)v13,
      psidGroupb);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  std::vector<unsigned short>::~vector<unsigned short>(Buffer);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    operator delete(v6);
}

```

## disassembly

```asm
0x18002e3d4  push    rbp
0x18002e3d6  push    rbx
0x18002e3d7  push    rsi
0x18002e3d8  push    rdi
0x18002e3d9  push    r14
0x18002e3db  push    r15
0x18002e3dd  mov     rbp, rsp
0x18002e3e0  sub     rsp, 78h
0x18002e3e4  mov     rbx, rdx
0x18002e3e7  mov     rsi, rcx
0x18002e3ea  xor     r15d, r15d
0x18002e3ed  mov     [rbp+arg_18], r15d
0x18002e3f1  mov     [rbp+Block], r15
0x18002e3f5  mov     [rbp+arg_18], 2
0x18002e3fc  mov     rdx, r8
0x18002e3ff  lea     rcx, [rbp+Block]
0x18002e403  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002e408  mov     rcx, [rbp+30h]; this
0x18002e40c  test    eax, eax
0x18002e40e  js      loc_18002E589
0x18002e414  mov     [rbp+StringSid], r15
0x18002e418  lea     rdx, [rbp+StringSid]; StringSid
0x18002e41c  mov     rdi, [rbp+Block]
0x18002e420  mov     rcx, [rdi]; Sid
0x18002e423  call    cs:__imp_ConvertSidToStringSidW
0x18002e42a  nop     dword ptr [rax+rax+00h]
0x18002e42f  mov     rcx, [rbp+30h]; this
0x18002e433  test    eax, eax
0x18002e435  jz      loc_18002E59E
0x18002e43b  mov     rdx, [rbx+10h]
0x18002e43f  mov     rcx, [rbp+StringSid]
0x18002e443  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e447  inc     rax
0x18002e44a  cmp     [rcx+rax*2], r15w
0x18002e44f  jnz     short loc_18002E447
0x18002e451  lea     r14, [rdx+rax]
0x18002e455  lea     rdx, [r14+4Bh]
0x18002e459  lea     rcx, [rbp+Buffer]
0x18002e45d  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002e462  nop
0x18002e463  mov     rax, [rbp+StringSid]
0x18002e467  cmp     qword ptr [rbx+18h], 7
0x18002e46c  jbe     short loc_18002E471
0x18002e46e  mov     rbx, [rbx]
0x18002e471  mov     [rsp+78h+psidGroup], rax; int
0x18002e476  mov     r9, rbx
0x18002e479  lea     r8, aDAiXaOici0x120; "D:AI(XA;OICI;0x1200A9;;;BU;(WIN://SYSAP"...
0x18002e480  lea     rdx, [r14+4Bh]; BufferCount
0x18002e484  mov     rcx, [rbp+Buffer]; Buffer
0x18002e488  call    swprintf
0x18002e48d  test    eax, eax
0x18002e48f  js      loc_18002E5B0
0x18002e495  mov     [rbp+SecurityDescriptor], r15
0x18002e499  xor     r9d, r9d; SecurityDescriptorSize
0x18002e49c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002e4a0  lea     ebx, [r9+1]
0x18002e4a4  mov     edx, ebx; StringSDRevision
0x18002e4a6  mov     rcx, [rbp+Buffer]; StringSecurityDescriptor
0x18002e4aa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002e4b1  nop     dword ptr [rax+rax+00h]
0x18002e4b6  mov     rcx, [rbp+30h]; this
0x18002e4ba  test    eax, eax
0x18002e4bc  jz      loc_18002E5D3
0x18002e4c2  mov     rax, [rbp+SecurityDescriptor]
0x18002e4c6  lea     r8d, [rbx+3]; SecurityInfo
0x18002e4ca  test    [rax+2], r8b
0x18002e4ce  jnz     short loc_18002E4D5
0x18002e4d0  mov     rcx, r15
0x18002e4d3  jmp     short loc_18002E4EE
0x18002e4d5  cmp     [rax+2], r15w
0x18002e4da  jge     short loc_18002E4EA
0x18002e4dc  cmp     [rax+10h], r15d
0x18002e4e0  jz      short loc_18002E4D0
0x18002e4e2  mov     ecx, [rax+10h]
0x18002e4e5  add     rcx, rax
0x18002e4e8  jmp     short loc_18002E4EE
0x18002e4ea  mov     rcx, [rax+20h]
0x18002e4ee  cmp     qword ptr [rsi+18h], 7
0x18002e4f3  jbe     short loc_18002E4F8
0x18002e4f5  mov     rsi, [rsi]
0x18002e4f8  mov     [rsp+78h+pSacl], r15; pSacl
0x18002e4fd  mov     [rsp+78h+pDacl], rcx; pDacl
0x18002e502  mov     [rsp+78h+psidGroup], r15; unsigned int
0x18002e507  xor     r9d, r9d; psidOwner
0x18002e50a  mov     edx, ebx; ObjectType
0x18002e50c  mov     rcx, rsi; pObjectName
0x18002e50f  call    cs:__imp_SetNamedSecurityInfoW
0x18002e516  nop     dword ptr [rax+rax+00h]
0x18002e51b  mov     rcx, [rbp+30h]; this
0x18002e51f  test    eax, eax
0x18002e521  jnz     short loc_18002E574
0x18002e523  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002e527  test    rcx, rcx
0x18002e52a  jz      short loc_18002E539
0x18002e52c  call    cs:__imp_LocalFree
0x18002e533  nop     dword ptr [rax+rax+00h]
0x18002e538  nop
0x18002e539  lea     rcx, [rbp+Buffer]
0x18002e53d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002e542  nop
0x18002e543  mov     rcx, [rbp+StringSid]; hMem
0x18002e547  test    rcx, rcx
0x18002e54a  jz      short loc_18002E559
0x18002e54c  call    cs:__imp_LocalFree
0x18002e553  nop     dword ptr [rax+rax+00h]
0x18002e558  nop
0x18002e559  test    rdi, rdi
0x18002e55c  jz      short loc_18002E566
0x18002e55e  mov     rcx, rdi; Block
0x18002e561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002e566  add     rsp, 78h
0x18002e56a  pop     r15
0x18002e56c  pop     r14
0x18002e56e  pop     rdi
0x18002e56f  pop     rsi
0x18002e570  pop     rbx
0x18002e571  pop     rbp
0x18002e572  retn
0x18002e574  mov     r9d, eax; char *
0x18002e577  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002e57e  mov     edx, 445h; void *
0x18002e583  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002e589  mov     r9d, eax; char *
0x18002e58c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e593  mov     edx, 1CBEh; void *
0x18002e598  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e59e  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002e5a5  mov     edx, 434h; void *
0x18002e5aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002e5b0  mov     ecx, 80070057h
0x18002e5b5  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18002e5ba  mov     r9d, eax; char *
0x18002e5bd  mov     rcx, [rbp+30h]; this
0x18002e5c1  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002e5c8  mov     edx, 43Bh; void *
0x18002e5cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e5d3  lea     r8, aOnecoreBaseApp_43; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002e5da  mov     edx, 43Fh; void *
0x18002e5df  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
