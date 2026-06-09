# DesktopAppXVFS::ACLWritablePackageRoot(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x18002d7b4`
- end: `0x18002d9d7`
- name: `?ACLWritablePackageRoot@DesktopAppXVFS@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX@Z`
- size: `547`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18003153c`

## callees

- `0x180005fac`
- `0x1800061cc`
- `0x18000c37c`
- `0x180010a84`
- `0x180013100`
- `0x18001432c`
- `0x1800156f0`
- `0x18002031c`
- `0x18002b308`
- `0x18002d7b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d916`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d916`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d936`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d80e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d80e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d894`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d894`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002d8f9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002d8f9`

## string_xrefs

- `0x18002d97e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall DesktopAppXVFS::ACLWritablePackageRoot(WCHAR *pObjectName, _QWORD *a2, __int64 a3)
{
  int token_information; // eax
  void *v6; // rbx
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r14
  const char *v10; // r9
  struct _ACL *pDacl; // rcx
  DWORD v12; // eax
  unsigned int v13; // eax
  int psidGroup; // [rsp+20h] [rbp-50h]
  int psidGroupa; // [rsp+20h] [rbp-50h]
  unsigned int psidGroupb; // [rsp+20h] [rbp-50h]
  LPWSTR StringSid; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  void *Block; // [rsp+50h] [rbp-20h] BYREF
  wchar_t *Buffer[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a3);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      psidGroup);
  StringSid = 0;
  v6 = Block;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x337,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v7);
  v8 = -1;
  do
    ++v8;
  while ( StringSid[v8] );
  v9 = v8 + a2[2];
  std::vector<unsigned short>::vector<unsigned short>(Buffer, v9 + 75);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( swprintf(
         Buffer[0],
         v9 + 75,
         L"D:AI(XA;OICI;0x1200A9;;;BU;(WIN://SYSAPPID Contains \"%s\"))(A;OICI;GA;;;%s)",
         a2,
         StringSid) < 0 )
  {
    v13 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      (const char *)v13,
      psidGroupa);
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(Buffer[0], 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v10);
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
  v12 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      (const char *)v12,
      psidGroupb);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  std::vector<unsigned short>::~vector<unsigned short>(Buffer);
  if ( StringSid )
    LocalFree(StringSid);
  operator delete(v6);
}

```

## disassembly

```asm
0x18002d7b4  mov     [rsp-18h+arg_0], rbx
0x18002d7b9  mov     [rsp-18h+arg_8], rsi
0x18002d7be  mov     [rsp-18h+arg_10], rdi
0x18002d7c3  push    rbp
0x18002d7c4  push    r14
0x18002d7c6  push    r15
0x18002d7c8  mov     rbp, rsp
0x18002d7cb  sub     rsp, 70h
0x18002d7cf  mov     rdi, rdx
0x18002d7d2  mov     rsi, rcx
0x18002d7d5  xor     r15d, r15d
0x18002d7d8  mov     [rbp+arg_18], r15d
0x18002d7dc  mov     [rbp+Block], r15
0x18002d7e0  mov     [rbp+arg_18], 2
0x18002d7e7  mov     rdx, r8
0x18002d7ea  lea     rcx, [rbp+Block]
0x18002d7ee  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002d7f3  mov     rcx, [rbp+18h]; this
0x18002d7f7  test    eax, eax
0x18002d7f9  js      loc_18002D97B
0x18002d7ff  mov     [rbp+StringSid], r15
0x18002d803  mov     rbx, [rbp+Block]
0x18002d807  lea     rdx, [rbp+StringSid]; StringSid
0x18002d80b  mov     rcx, [rbx]; Sid
0x18002d80e  call    cs:__imp_ConvertSidToStringSidW
0x18002d815  nop     dword ptr [rax+rax+00h]
0x18002d81a  mov     rcx, [rbp+18h]; this
0x18002d81e  test    eax, eax
0x18002d820  jz      loc_18002D990
0x18002d826  mov     rax, [rbp+StringSid]
0x18002d82a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002d82e  inc     rcx
0x18002d831  cmp     [rax+rcx*2], r15w
0x18002d836  jnz     short loc_18002D82E
0x18002d838  mov     r14, [rdi+10h]
0x18002d83c  add     r14, rcx
0x18002d83f  lea     rdx, [r14+4Bh]
0x18002d843  lea     rcx, [rbp+Buffer]
0x18002d847  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002d84c  nop
0x18002d84d  cmp     qword ptr [rdi+18h], 7
0x18002d852  jbe     short loc_18002D857
0x18002d854  mov     rdi, [rdi]
0x18002d857  mov     rax, [rbp+StringSid]
0x18002d85b  mov     [rsp+70h+psidGroup], rax; int
0x18002d860  mov     r9, rdi
0x18002d863  lea     r8, aDAiXaOici0x120; "D:AI(XA;OICI;0x1200A9;;;BU;(WIN://SYSAP"...
0x18002d86a  lea     rdx, [r14+4Bh]; BufferCount
0x18002d86e  mov     rcx, [rbp+Buffer]; Buffer
0x18002d872  call    swprintf
0x18002d877  test    eax, eax
0x18002d879  js      loc_18002D9A2
0x18002d87f  mov     [rbp+SecurityDescriptor], r15
0x18002d883  xor     r9d, r9d; SecurityDescriptorSize
0x18002d886  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002d88a  lea     edi, [r9+1]
0x18002d88e  mov     edx, edi; StringSDRevision
0x18002d890  mov     rcx, [rbp+Buffer]; StringSecurityDescriptor
0x18002d894  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002d89b  nop     dword ptr [rax+rax+00h]
0x18002d8a0  mov     rcx, [rbp+18h]; this
0x18002d8a4  test    eax, eax
0x18002d8a6  jz      loc_18002D9C5
0x18002d8ac  mov     rax, [rbp+SecurityDescriptor]
0x18002d8b0  lea     r8d, [rdi+3]; SecurityInfo
0x18002d8b4  test    [rax+2], r8b
0x18002d8b8  jnz     short loc_18002D8BF
0x18002d8ba  mov     rcx, r15
0x18002d8bd  jmp     short loc_18002D8D8
0x18002d8bf  cmp     [rax+2], r15w
0x18002d8c4  jge     short loc_18002D8D4
0x18002d8c6  cmp     [rax+10h], r15d
0x18002d8ca  jz      short loc_18002D8BA
0x18002d8cc  mov     ecx, [rax+10h]
0x18002d8cf  add     rcx, rax
0x18002d8d2  jmp     short loc_18002D8D8
0x18002d8d4  mov     rcx, [rax+20h]
0x18002d8d8  cmp     qword ptr [rsi+18h], 7
0x18002d8dd  jbe     short loc_18002D8E2
0x18002d8df  mov     rsi, [rsi]
0x18002d8e2  mov     [rsp+70h+pSacl], r15; pSacl
0x18002d8e7  mov     [rsp+70h+pDacl], rcx; pDacl
0x18002d8ec  mov     [rsp+70h+psidGroup], r15; unsigned int
0x18002d8f1  xor     r9d, r9d; psidOwner
0x18002d8f4  mov     edx, edi; ObjectType
0x18002d8f6  mov     rcx, rsi; pObjectName
0x18002d8f9  call    cs:__imp_SetNamedSecurityInfoW
0x18002d900  nop     dword ptr [rax+rax+00h]
0x18002d905  mov     rcx, [rbp+18h]; this
0x18002d909  test    eax, eax
0x18002d90b  jnz     short loc_18002D966
0x18002d90d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002d911  test    rcx, rcx
0x18002d914  jz      short loc_18002D923
0x18002d916  call    cs:__imp_LocalFree
0x18002d91d  nop     dword ptr [rax+rax+00h]
0x18002d922  nop
0x18002d923  lea     rcx, [rbp+Buffer]
0x18002d927  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002d92c  nop
0x18002d92d  mov     rcx, [rbp+StringSid]; hMem
0x18002d931  test    rcx, rcx
0x18002d934  jz      short loc_18002D943
0x18002d936  call    cs:__imp_LocalFree
0x18002d93d  nop     dword ptr [rax+rax+00h]
0x18002d942  nop
0x18002d943  mov     rcx, rbx; Block
0x18002d946  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d94b  lea     r11, [rsp+70h+var_s0]
0x18002d950  mov     rbx, [r11+20h]
0x18002d954  mov     rsi, [r11+28h]
0x18002d958  mov     rdi, [r11+30h]
0x18002d95c  mov     rsp, r11
0x18002d95f  pop     r15
0x18002d961  pop     r14
0x18002d963  pop     rbp
0x18002d964  retn
0x18002d966  mov     r9d, eax; char *
0x18002d969  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002d970  mov     edx, 348h; void *
0x18002d975  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002d97b  mov     r9d, eax; char *
0x18002d97e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002d985  mov     edx, 1C60h; void *
0x18002d98a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d990  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002d997  mov     edx, 337h; void *
0x18002d99c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d9a2  mov     ecx, 80070057h
0x18002d9a7  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18002d9ac  mov     r9d, eax; char *
0x18002d9af  mov     rcx, [rbp+18h]; this
0x18002d9b3  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002d9ba  mov     edx, 33Eh; void *
0x18002d9bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d9c5  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002d9cc  mov     edx, 342h; void *
0x18002d9d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
