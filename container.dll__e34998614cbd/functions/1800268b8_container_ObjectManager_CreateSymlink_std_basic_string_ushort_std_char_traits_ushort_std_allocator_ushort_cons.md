# container::ObjectManager::CreateSymlink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,bool,Schema::Containers::Definition::ObjectSymlinkScope,ulong)

- ea: `0x1800268b8`
- end: `0x180026b60`
- name: `?CreateSymlink@ObjectManager@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX_NW4ObjectSymlinkScope@Definition@Containers@Schema@@K@Z`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027438`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000ca10`
- `0x18002666c`
- `0x180026830`
- `0x1800268b8`
- `0x180026b68`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800269db`
- `ntdll!RtlInitUnicodeString` at `0x1800269db`
- `ntdll!NtSetInformationSymbolicLink` at `0x180026a7e`
- `ntdll!NtSetInformationSymbolicLink` at `0x180026aad`
- `ntdll!NtSetInformationSymbolicLink` at `0x180026a7e`
- `ntdll!NtSetInformationSymbolicLink` at `0x180026aad`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180026a3d`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180026a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall container::ObjectManager::CreateSymlink(_QWORD *a1, const WCHAR *a2, int a3, __int64 a4, int a5, int a6)
{
  const WCHAR *v9; // rax
  _QWORD *v10; // rax
  void *v11; // rbx
  HANDLE v12; // rsi
  DWORD LastError; // edi
  NTSTATUS v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned __int64 v17; // rdx
  int result; // eax
  int v19; // [rsp+20h] [rbp-B9h]
  bool v20; // [rsp+30h] [rbp-A9h] BYREF
  bool v21; // [rsp+31h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-A1h] BYREF
  const WCHAR *v23; // [rsp+40h] [rbp-99h] BYREF
  void *v24; // [rsp+48h] [rbp-91h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-81h] BYREF
  _OWORD v27[2]; // [rsp+68h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-49h] BYREF
  char v29[32]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  hObject = 0;
  DestinationString = 0;
  v21 = a5 != 0;
  v20 = a5 == 2;
  v24 = 0;
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,unsigned short const *>(v27);
  container::ObjectManager::GetDirectorySecurityDescriptor(v27, &v24, 0);
  std::wstring::~wstring(v27);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v9 = a2;
  else
    v9 = *(const WCHAR **)a2;
  v23 = v9;
  if ( a1[3] <= 7u )
    v10 = a1;
  else
    v10 = (_QWORD *)*a1;
  v25 = v10;
  ContainerProvider::CreateObSymlink<unsigned short const *,unsigned short const *,bool &,bool &,unsigned long &>(
    (unsigned int)&v25,
    (unsigned int)&v23,
    (unsigned int)&v21,
    (unsigned int)&v20,
    (__int64)&a6);
  v11 = v24;
  windows_wrappers::ObjectAttributes::ObjectAttributes(
    (unsigned int)&ObjectAttributes,
    (_DWORD)a1,
    80,
    a3,
    (__int64)v24);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  RtlInitUnicodeString(&DestinationString, a2);
  v12 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v12);
    SetLastError(LastError);
  }
  hObject = 0;
  v14 = NtCreateSymbolicLinkObject(&hObject, 0xFFFFFu, &ObjectAttributes, &DestinationString);
  if ( v14 != -1073741771 )
  {
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
        (const char *)(unsigned int)v14,
        v19);
    if ( a5 )
    {
      LODWORD(v23) = a5 == 2;
      v15 = NtSetInformationSymbolicLink(hObject, 1, &v23, 4);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
          (const char *)(unsigned int)v15,
          v19);
    }
    if ( a6 )
    {
      v16 = NtSetInformationSymbolicLink(hObject, 2, &a6, 4);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
          (const char *)(unsigned int)v16,
          v19);
    }
  }
  std::wstring::~wstring(v29);
  if ( v11 )
    operator delete(v11, v17);
  result = (_DWORD)hObject - 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hObject);
  return result;
}

```

## disassembly

```asm
0x1800268b8  mov     [rsp-8+arg_10], rbx
0x1800268bd  mov     [rsp-8+arg_18], rsi
0x1800268c2  push    rbp
0x1800268c3  push    rdi
0x1800268c4  push    r12
0x1800268c6  push    r14
0x1800268c8  push    r15
0x1800268ca  lea     rbp, [rsp-27h]
0x1800268cf  sub     rsp, 100h
0x1800268d6  mov     rax, cs:__security_cookie
0x1800268dd  xor     rax, rsp
0x1800268e0  mov     [rbp+47h+var_30], rax
0x1800268e4  mov     r15, r8
0x1800268e7  mov     rdi, rdx
0x1800268ea  mov     rsi, rcx
0x1800268ed  mov     [rsp+120h+hObject], 0
0x1800268f6  xorps   xmm0, xmm0
0x1800268f9  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1800268fe  mov     eax, [rbp+47h+arg_20]
0x180026901  test    eax, eax
0x180026903  setnz   r14b
0x180026907  mov     [rsp+120h+var_EF], r14b
0x18002690c  cmp     eax, 2
0x18002690f  setz    r12b
0x180026913  mov     [rsp+120h+var_F0], r12b
0x180026918  mov     [rsp+120h+var_D8], 0
0x180026921  movups  [rbp+47h+var_B8], xmm0
0x180026925  xorps   xmm1, xmm1
0x180026928  movdqu  [rbp+47h+var_A8], xmm1
0x18002692d  mov     r8d, 1
0x180026933  lea     rdx, asc_180037DD0; "\\"
0x18002693a  lea     rcx, [rbp+47h+var_B8]
0x18002693e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026943  nop
0x180026944  xor     r8d, r8d
0x180026947  lea     rdx, [rsp+120h+var_D8]
0x18002694c  lea     rcx, [rbp+47h+var_B8]
0x180026950  call    ?GetDirectorySecurityDescriptor@ObjectManager@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVSecurityDescriptor@windows_wrappers@@_N@Z; container::ObjectManager::GetDirectorySecurityDescriptor(std::wstring const &,windows_wrappers::SecurityDescriptor &,bool)
0x180026955  nop
0x180026956  lea     rcx, [rbp+47h+var_B8]
0x18002695a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002695f  cmp     qword ptr [rdi+18h], 7
0x180026964  jbe     short loc_18002696B
0x180026966  mov     rax, [rdi]
0x180026969  jmp     short loc_18002696E
0x18002696b  mov     rax, rdi
0x18002696e  mov     [rsp+120h+var_E0], rax
0x180026973  cmp     qword ptr [rsi+18h], 7
0x180026978  jbe     short loc_18002697F
0x18002697a  mov     rax, [rsi]
0x18002697d  jmp     short loc_180026982
0x18002697f  mov     rax, rsi
0x180026982  mov     [rsp+120h+var_D0], rax
0x180026987  lea     rax, [rbp+47h+arg_28]
0x18002698b  mov     qword ptr [rsp+120h+var_100], rax
0x180026990  lea     r9, [rsp+120h+var_F0]
0x180026995  lea     r8, [rsp+120h+var_EF]
0x18002699a  lea     rdx, [rsp+120h+var_E0]
0x18002699f  lea     rcx, [rsp+120h+var_D0]
0x1800269a4  call    ??$CreateObSymlink@PEBGPEBGAEA_NAEA_NAEAK@ContainerProvider@@SAX$$QEAPEBG0AEA_N1AEAK@Z; ContainerProvider::CreateObSymlink<ushort const *,ushort const *,bool &,bool &,ulong &>(ushort const * &&,ushort const * &&,bool &,bool &,ulong &)
0x1800269a9  mov     rbx, [rsp+120h+var_D8]
0x1800269ae  mov     qword ptr [rsp+120h+var_100], rbx; int
0x1800269b3  mov     r9, r15
0x1800269b6  mov     r8d, 50h ; 'P'
0x1800269bc  mov     rdx, rsi
0x1800269bf  lea     rcx, [rbp+47h+ObjectAttributes]
0x1800269c3  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x1800269c8  nop
0x1800269c9  cmp     qword ptr [rdi+18h], 7
0x1800269ce  jbe     short loc_1800269D3
0x1800269d0  mov     rdi, [rdi]
0x1800269d3  mov     rdx, rdi; SourceString
0x1800269d6  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1800269db  call    cs:__imp_RtlInitUnicodeString
0x1800269e2  nop     dword ptr [rax+rax+00h]
0x1800269e7  mov     rsi, [rsp+120h+hObject]
0x1800269ec  lea     rax, [rsi-1]
0x1800269f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800269f4  ja      short loc_180026A21
0x1800269f6  call    cs:__imp_GetLastError
0x1800269fd  nop     dword ptr [rax+rax+00h]
0x180026a02  mov     edi, eax
0x180026a04  mov     rcx, rsi; hObject
0x180026a07  call    cs:__imp_CloseHandle
0x180026a0e  nop     dword ptr [rax+rax+00h]
0x180026a13  mov     ecx, edi; dwErrCode
0x180026a15  call    cs:__imp_SetLastError
0x180026a1c  nop     dword ptr [rax+rax+00h]
0x180026a21  mov     [rsp+120h+hObject], 0
0x180026a2a  lea     r9, [rsp+120h+DestinationString]; Name
0x180026a2f  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180026a33  mov     edx, 0FFFFFh; DesiredAccess
0x180026a38  lea     rcx, [rsp+120h+hObject]; SymbolicLinkHandle
0x180026a3d  call    cs:__imp_NtCreateSymbolicLinkObject
0x180026a44  nop     dword ptr [rax+rax+00h]
0x180026a49  cmp     eax, 0C0000035h
0x180026a4e  jz      short loc_180026AC1
0x180026a50  test    eax, eax
0x180026a52  js      loc_180026B32
0x180026a58  mov     edi, 4
0x180026a5d  test    r14b, r14b
0x180026a60  jz      short loc_180026A96
0x180026a62  xor     eax, eax
0x180026a64  test    r12b, r12b
0x180026a67  setnz   al
0x180026a6a  mov     dword ptr [rsp+120h+var_E0], eax
0x180026a6e  mov     r9d, edi
0x180026a71  lea     r8, [rsp+120h+var_E0]
0x180026a76  lea     edx, [rdi-3]
0x180026a79  mov     rcx, [rsp+120h+hObject]
0x180026a7e  call    cs:__imp_NtSetInformationSymbolicLink
0x180026a85  nop     dword ptr [rax+rax+00h]
0x180026a8a  mov     rcx, [rbp+4Fh]; this
0x180026a8e  test    eax, eax
0x180026a90  js      loc_180026B4B
0x180026a96  cmp     [rbp+47h+arg_28], 0
0x180026a9a  jz      short loc_180026AC1
0x180026a9c  mov     r9d, edi
0x180026a9f  lea     r8, [rbp+47h+arg_28]
0x180026aa3  mov     edx, 2
0x180026aa8  mov     rcx, [rsp+120h+hObject]
0x180026aad  call    cs:__imp_NtSetInformationSymbolicLink
0x180026ab4  nop     dword ptr [rax+rax+00h]
0x180026ab9  mov     rcx, [rbp+4Fh]; this
0x180026abd  test    eax, eax
0x180026abf  js      short loc_180026B1D
0x180026ac1  lea     rcx, [rbp+47h+var_50]
0x180026ac5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026aca  nop
0x180026acb  test    rbx, rbx
0x180026ace  jz      short loc_180026AD9
0x180026ad0  mov     rcx, rbx; void *
0x180026ad3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026ad8  nop
0x180026ad9  mov     rcx, [rsp+120h+hObject]; hObject
0x180026ade  lea     rax, [rcx-1]
0x180026ae2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026ae6  ja      short loc_180026AF4
0x180026ae8  call    cs:__imp_CloseHandle
0x180026aef  nop     dword ptr [rax+rax+00h]
0x180026af4  mov     rcx, [rbp+47h+var_30]
0x180026af8  xor     rcx, rsp; StackCookie
0x180026afb  call    __security_check_cookie
0x180026b00  lea     r11, [rsp+120h+var_20]
0x180026b08  mov     rbx, [r11+40h]
0x180026b0c  mov     rsi, [r11+48h]
0x180026b10  mov     rsp, r11
0x180026b13  pop     r15
0x180026b15  pop     r14
0x180026b17  pop     r12
0x180026b19  pop     rdi
0x180026b1a  pop     rbp
0x180026b1b  retn
0x180026b1d  mov     r9d, eax; char *
0x180026b20  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026b27  mov     edx, 1ECh; void *
0x180026b2c  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180026b32  mov     rcx, [rbp+4Fh]; this
0x180026b36  mov     r9d, eax; char *
0x180026b39  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026b40  mov     edx, 1D1h; void *
0x180026b45  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180026b4b  mov     r9d, eax; char *
0x180026b4e  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026b55  mov     edx, 1DFh; void *
0x180026b5a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
