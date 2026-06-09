# CTSScpRegister::IsSCPRegistered(ushort const *,int *)

- ea: `0x18007b3d0`
- end: `0x18007b702`
- name: `?IsSCPRegistered@CTSScpRegister@@UEAAJPEBGPEAH@Z`
- size: `818`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18001ad74`
- `0x18001aea4`
- `0x180078bbc`
- `0x180078f54`
- `0x180079950`
- `0x18007b3d0`
- `0x1800a0fb0`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x18007b624`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x18007b624`
- `KERNEL32!GetLastError` at `0x18007b448`
- `KERNEL32!GetLastError` at `0x18007b448`
- `KERNEL32!LocalFree` at `0x18007b681`
- `KERNEL32!LocalFree` at `0x18007b695`
- `KERNEL32!LocalFree` at `0x18007b6ab`
- `KERNEL32!LocalFree` at `0x18007b6bf`
- `KERNEL32!LocalFree` at `0x18007b681`
- `KERNEL32!LocalFree` at `0x18007b695`
- `KERNEL32!LocalFree` at `0x18007b6ab`
- `KERNEL32!LocalFree` at `0x18007b6bf`
- `Secur32!GetComputerObjectNameW` at `0x18007b438`
- `Secur32!GetComputerObjectNameW` at `0x18007b438`

## string_xrefs

- `0x18007b4e1`: `"ComposeString"`
- `0x18007b53f`: `"ComposeString"`
- `0x18007b662`: `"ADsOpenObject"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSScpRegister::IsSCPRegistered(CTSScpRegister *this, const unsigned __int16 *a2, int *a3)
{
  void *v5; // rdi
  WCHAR *v6; // rsi
  int v7; // r15d
  signed int LastError; // eax
  int DomainMachineNameOnDC; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  const wchar_t *v12; // r9
  void *v14; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpszUserName; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  ULONG nSize; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpszPathName; // [rsp+50h] [rbp-B0h] BYREF
  void *ppObject; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  hMem = 0;
  v5 = 0;
  v14 = 0;
  lpszPathName = 0;
  v6 = 0;
  lpszUserName = 0;
  ppObject = 0;
  v7 = 0;
  nSize = 260;
  if ( !GetComputerObjectNameW(NameFullyQualifiedDN, NameBuffer, &nSize) )
  {
    LastError = GetLastError();
    DomainMachineNameOnDC = LastError;
    if ( LastError > 0 )
      DomainMachineNameOnDC = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)DomainMachineNameOnDC);
    goto LABEL_42;
  }
  DomainMachineNameOnDC = ComposeString(&hMem, L"LDAP://CN=", a2);
  if ( DomainMachineNameOnDC < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_34;
    v11 = 39;
    goto LABEL_11;
  }
  DomainMachineNameOnDC = ComposeString(&v14, L",", NameBuffer);
  if ( DomainMachineNameOnDC < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)L"\"ComposeString\"",
        DomainMachineNameOnDC);
    v5 = v14;
    goto LABEL_34;
  }
  v5 = v14;
  DomainMachineNameOnDC = ComposeString(&lpszPathName, hMem, v14);
  if ( DomainMachineNameOnDC < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_34;
    v11 = 41;
LABEL_11:
    v12 = L"\"ComposeString\"";
    goto LABEL_12;
  }
  DomainMachineNameOnDC = GetDomainMachineNameOnDC(&lpszUserName);
  if ( DomainMachineNameOnDC < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)L"\"GetDomainMachineNameOnDC\"",
        DomainMachineNameOnDC);
    v6 = (WCHAR *)lpszUserName;
    goto LABEL_34;
  }
  v6 = (WCHAR *)lpszUserName;
  DomainMachineNameOnDC = ADsOpenObject(lpszPathName, lpszUserName, 0, 1u, &IID_IDirectoryObject, &ppObject);
  if ( (_WORD)DomainMachineNameOnDC == 8240 )
  {
    DomainMachineNameOnDC = 0;
    goto LABEL_34;
  }
  if ( DomainMachineNameOnDC >= 0 )
  {
    v7 = 1;
    goto LABEL_34;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_34;
  v11 = 43;
  v12 = L"\"ADsOpenObject\"";
LABEL_12:
  WPP_SF_SD(
    v10[2],
    v11,
    (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
    (_DWORD)v12,
    DomainMachineNameOnDC);
LABEL_34:
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    LocalFree(v5);
  if ( lpszPathName )
    LocalFree((HLOCAL)lpszPathName);
  if ( v6 )
    LocalFree(v6);
LABEL_42:
  *a3 = v7;
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&ppObject);
  return (unsigned int)DomainMachineNameOnDC;
}

```

## disassembly

```asm
0x18007b3d0  mov     [rsp-8+arg_0], rbx
0x18007b3d5  push    rbp
0x18007b3d6  push    rsi
0x18007b3d7  push    rdi
0x18007b3d8  push    r12
0x18007b3da  push    r15
0x18007b3dc  lea     rbp, [rsp-180h]
0x18007b3e4  sub     rsp, 280h
0x18007b3eb  mov     rax, cs:__security_cookie
0x18007b3f2  xor     rax, rsp
0x18007b3f5  mov     [rbp+1A0h+var_30], rax
0x18007b3fc  mov     r12, r8
0x18007b3ff  mov     rbx, rdx
0x18007b402  and     [rsp+2A0h+hMem], 0
0x18007b408  xor     edi, edi
0x18007b40a  mov     [rsp+2A0h+var_270], rdi
0x18007b40f  and     [rsp+2A0h+lpszPathName], rdi
0x18007b414  xor     esi, esi
0x18007b416  mov     [rsp+2A0h+lpszUserName], rsi
0x18007b41b  and     [rsp+2A0h+var_248], rsi
0x18007b420  xor     r15d, r15d
0x18007b423  mov     [rsp+2A0h+nSize], 104h
0x18007b42b  lea     r8, [rsp+2A0h+nSize]; nSize
0x18007b430  lea     rdx, [rsp+2A0h+NameBuffer]; lpNameBuffer
0x18007b435  lea     ecx, [rdi+1]; NameFormat
0x18007b438  call    cs:__imp_GetComputerObjectNameW
0x18007b43f  nop     dword ptr [rax+rax+00h]
0x18007b444  test    al, al
0x18007b446  jnz     short loc_18007B4A1
0x18007b448  call    cs:__imp_GetLastError
0x18007b44f  nop     dword ptr [rax+rax+00h]
0x18007b454  mov     ebx, eax
0x18007b456  test    eax, eax
0x18007b458  jle     short loc_18007B463
0x18007b45a  movzx   ebx, ax
0x18007b45d  or      ebx, 80070000h
0x18007b463  lea     rax, WPP_GLOBAL_Control
0x18007b46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b471  cmp     rcx, rax
0x18007b474  jz      loc_18007B6CB
0x18007b47a  cmp     byte ptr [rcx+19h], 2
0x18007b47e  jb      loc_18007B6CB
0x18007b484  mov     edx, 26h ; '&'
0x18007b489  mov     r9d, ebx
0x18007b48c  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b493  mov     rcx, [rcx+10h]
0x18007b497  call    WPP_SF_D
0x18007b49c  jmp     loc_18007B6CB
0x18007b4a1  mov     r8, rbx
0x18007b4a4  lea     rdx, aLdapCn; "LDAP://CN="
0x18007b4ab  lea     rcx, [rsp+2A0h+hMem]
0x18007b4b0  call    ComposeString
0x18007b4b5  mov     ebx, eax
0x18007b4b7  test    eax, eax
0x18007b4b9  jns     short loc_18007B501
0x18007b4bb  lea     rax, WPP_GLOBAL_Control
0x18007b4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b4c9  cmp     rcx, rax
0x18007b4cc  jz      loc_18007B674
0x18007b4d2  cmp     byte ptr [rcx+19h], 2
0x18007b4d6  jb      loc_18007B674
0x18007b4dc  mov     edx, 27h ; '''
0x18007b4e1  lea     r9, aComposestring; "\"ComposeString\""
0x18007b4e8  mov     dword ptr [rsp+2A0h+riid], ebx
0x18007b4ec  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b4f3  mov     rcx, [rcx+10h]
0x18007b4f7  call    WPP_SF_SD
0x18007b4fc  jmp     loc_18007B674
0x18007b501  lea     r8, [rsp+2A0h+NameBuffer]
0x18007b506  lea     rdx, asc_1800BA394; ","
0x18007b50d  lea     rcx, [rsp+2A0h+var_270]
0x18007b512  call    ComposeString
0x18007b517  mov     ebx, eax
0x18007b519  test    eax, eax
0x18007b51b  jns     short loc_18007B560
0x18007b51d  lea     rax, WPP_GLOBAL_Control
0x18007b524  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b52b  cmp     rcx, rax
0x18007b52e  jz      short loc_18007B556
0x18007b530  cmp     byte ptr [rcx+19h], 2
0x18007b534  jb      short loc_18007B556
0x18007b536  mov     edx, 28h ; '('
0x18007b53b  mov     dword ptr [rsp+2A0h+riid], ebx
0x18007b53f  lea     r9, aComposestring; "\"ComposeString\""
0x18007b546  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b54d  mov     rcx, [rcx+10h]
0x18007b551  call    WPP_SF_SD
0x18007b556  mov     rdi, [rsp+2A0h+var_270]
0x18007b55b  jmp     loc_18007B674
0x18007b560  mov     rdi, [rsp+2A0h+var_270]
0x18007b565  mov     r8, rdi
0x18007b568  mov     rdx, [rsp+2A0h+hMem]
0x18007b56d  lea     rcx, [rsp+2A0h+lpszPathName]
0x18007b572  call    ComposeString
0x18007b577  mov     ebx, eax
0x18007b579  test    eax, eax
0x18007b57b  jns     short loc_18007B5A8
0x18007b57d  lea     rax, WPP_GLOBAL_Control
0x18007b584  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b58b  cmp     rcx, rax
0x18007b58e  jz      loc_18007B674
0x18007b594  cmp     byte ptr [rcx+19h], 2
0x18007b598  jb      loc_18007B674
0x18007b59e  mov     edx, 29h ; ')'
0x18007b5a3  jmp     loc_18007B4E1
0x18007b5a8  lea     rcx, [rsp+2A0h+lpszUserName]
0x18007b5ad  call    GetDomainMachineNameOnDC
0x18007b5b2  mov     ebx, eax
0x18007b5b4  test    eax, eax
0x18007b5b6  jns     short loc_18007B5F8
0x18007b5b8  lea     rax, WPP_GLOBAL_Control
0x18007b5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b5c6  cmp     rcx, rax
0x18007b5c9  jz      short loc_18007B5F1
0x18007b5cb  cmp     byte ptr [rcx+19h], 2
0x18007b5cf  jb      short loc_18007B5F1
0x18007b5d1  mov     edx, 2Ah ; '*'
0x18007b5d6  mov     dword ptr [rsp+2A0h+riid], ebx
0x18007b5da  lea     r9, aGetdomainmachi; "\"GetDomainMachineNameOnDC\""
0x18007b5e1  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b5e8  mov     rcx, [rcx+10h]
0x18007b5ec  call    WPP_SF_SD
0x18007b5f1  mov     rsi, [rsp+2A0h+lpszUserName]
0x18007b5f6  jmp     short loc_18007B674
0x18007b5f8  lea     rax, [rsp+2A0h+var_248]
0x18007b5fd  mov     [rsp+2A0h+ppObject], rax; ppObject
0x18007b602  lea     rax, IID_IDirectoryObject
0x18007b609  mov     [rsp+2A0h+riid], rax; riid
0x18007b60e  mov     r9d, 1; dwReserved
0x18007b614  xor     r8d, r8d; lpszPassword
0x18007b617  mov     rsi, [rsp+2A0h+lpszUserName]
0x18007b61c  mov     rdx, rsi; lpszUserName
0x18007b61f  mov     rcx, [rsp+2A0h+lpszPathName]; lpszPathName
0x18007b624  call    cs:__imp_ADsOpenObject
0x18007b62b  nop     dword ptr [rax+rax+00h]
0x18007b630  mov     ebx, eax
0x18007b632  mov     eax, 2030h
0x18007b637  cmp     ax, bx
0x18007b63a  jnz     short loc_18007B640
0x18007b63c  xor     ebx, ebx
0x18007b63e  jmp     short loc_18007B674
0x18007b640  test    ebx, ebx
0x18007b642  jns     short loc_18007B66E
0x18007b644  lea     rax, WPP_GLOBAL_Control
0x18007b64b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b652  cmp     rcx, rax
0x18007b655  jz      short loc_18007B674
0x18007b657  cmp     byte ptr [rcx+19h], 2
0x18007b65b  jb      short loc_18007B674
0x18007b65d  mov     edx, 2Bh ; '+'
0x18007b662  lea     r9, aAdsopenobject; "\"ADsOpenObject\""
0x18007b669  jmp     loc_18007B4E8
0x18007b66e  mov     r15d, 1
0x18007b674  cmp     [rsp+2A0h+hMem], 0
0x18007b67a  jz      short loc_18007B68D
0x18007b67c  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18007b681  call    cs:__imp_LocalFree
0x18007b688  nop     dword ptr [rax+rax+00h]
0x18007b68d  test    rdi, rdi
0x18007b690  jz      short loc_18007B6A1
0x18007b692  mov     rcx, rdi; hMem
0x18007b695  call    cs:__imp_LocalFree
0x18007b69c  nop     dword ptr [rax+rax+00h]
0x18007b6a1  mov     rcx, [rsp+2A0h+lpszPathName]; hMem
0x18007b6a6  test    rcx, rcx
0x18007b6a9  jz      short loc_18007B6B7
0x18007b6ab  call    cs:__imp_LocalFree
0x18007b6b2  nop     dword ptr [rax+rax+00h]
0x18007b6b7  test    rsi, rsi
0x18007b6ba  jz      short loc_18007B6CB
0x18007b6bc  mov     rcx, rsi; hMem
0x18007b6bf  call    cs:__imp_LocalFree
0x18007b6c6  nop     dword ptr [rax+rax+00h]
0x18007b6cb  mov     [r12], r15d
0x18007b6cf  lea     rcx, [rsp+2A0h+var_248]
0x18007b6d4  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x18007b6d9  mov     eax, ebx
0x18007b6db  mov     rcx, [rbp+1A0h+var_30]
0x18007b6e2  xor     rcx, rsp; StackCookie
0x18007b6e5  call    __security_check_cookie
0x18007b6ea  mov     rbx, [rsp+2A0h+arg_0]
0x18007b6f2  add     rsp, 280h
0x18007b6f9  pop     r15
0x18007b6fb  pop     r12
0x18007b6fd  pop     rdi
0x18007b6fe  pop     rsi
0x18007b6ff  pop     rbp
0x18007b700  retn
```
