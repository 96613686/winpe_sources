# GetLocalComputerObject

- ea: `0x180079e20`
- end: `0x18007a045`
- name: `GetLocalComputerObject`
- size: `549`
- prototype: `__int64 __fastcall(void **ppObject)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18007c0e0`
- `0x18007c368`

## callees

- `0x18001ad74`
- `0x18001aea4`
- `0x180078f54`
- `0x180079950`
- `0x180079e20`
- `0x1800a0fb0`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x180079fa2`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180079fa2`
- `KERNEL32!GetLastError` at `0x180079e84`
- `KERNEL32!GetLastError` at `0x180079e84`
- `KERNEL32!LocalFree` at `0x180079ffa`
- `KERNEL32!LocalFree` at `0x18007a00e`
- `KERNEL32!LocalFree` at `0x180079ffa`
- `KERNEL32!LocalFree` at `0x18007a00e`
- `Secur32!GetComputerObjectNameW` at `0x180079e74`
- `Secur32!GetComputerObjectNameW` at `0x180079e74`

## string_xrefs

- `0x180079f1f`: `"ComposeString"`
- `0x180079fd2`: `"ADsOpenObject"`

## pseudocode

```c
__int64 __fastcall GetLocalComputerObject(void **ppObject)
{
  WCHAR *v1; // rdi
  signed int LastError; // eax
  int DomainMachineNameOnDC; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  const wchar_t *v7; // r9
  LPCWSTR lpszUserName; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpszPathName; // [rsp+40h] [rbp-C8h] BYREF
  ULONG nSize[4]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR NameBuffer[264]; // [rsp+58h] [rbp-B0h] BYREF

  lpszPathName = 0;
  v1 = 0;
  nSize[0] = 260;
  lpszUserName = 0;
  if ( !GetComputerObjectNameW(NameFullyQualifiedDN, NameBuffer, nSize) )
  {
    LastError = GetLastError();
    DomainMachineNameOnDC = LastError;
    if ( LastError > 0 )
      DomainMachineNameOnDC = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)DomainMachineNameOnDC);
    return (unsigned int)DomainMachineNameOnDC;
  }
  DomainMachineNameOnDC = ComposeString(&lpszPathName, L"LDAP://", NameBuffer);
  if ( DomainMachineNameOnDC < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_21;
    v6 = 93;
    v7 = L"\"ComposeString\"";
    goto LABEL_20;
  }
  DomainMachineNameOnDC = GetDomainMachineNameOnDC(&lpszUserName);
  if ( DomainMachineNameOnDC < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)L"\"GetDomainMachineNameOnDC\"",
        DomainMachineNameOnDC);
    v1 = (WCHAR *)lpszUserName;
    goto LABEL_21;
  }
  v1 = (WCHAR *)lpszUserName;
  DomainMachineNameOnDC = ADsOpenObject(lpszPathName, lpszUserName, 0, 1u, &IID_IDirectoryObject, ppObject);
  if ( DomainMachineNameOnDC < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 95;
      v7 = L"\"ADsOpenObject\"";
LABEL_20:
      WPP_SF_SD(
        v5[2],
        v6,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (_DWORD)v7,
        DomainMachineNameOnDC);
    }
  }
LABEL_21:
  if ( lpszPathName )
    LocalFree((HLOCAL)lpszPathName);
  if ( v1 )
    LocalFree(v1);
  return (unsigned int)DomainMachineNameOnDC;
}

```

## disassembly

```asm
0x180079e20  mov     rax, rsp
0x180079e23  mov     [rax+10h], rbx
0x180079e27  mov     [rax+18h], rdi
0x180079e2b  mov     [rax+20h], r14
0x180079e2f  push    rbp
0x180079e30  lea     rbp, [rax-178h]
0x180079e37  sub     rsp, 270h
0x180079e3e  mov     rax, cs:__security_cookie
0x180079e45  xor     rax, rsp
0x180079e48  mov     [rbp+170h+var_10], rax
0x180079e4f  and     [rsp+270h+lpszPathName], 0
0x180079e55  lea     r8, [rsp+270h+nSize]; nSize
0x180079e5a  xor     edi, edi
0x180079e5c  mov     [rsp+270h+nSize], 104h
0x180079e64  mov     r14, rcx
0x180079e67  mov     [rsp+270h+lpszUserName], rdi
0x180079e6c  lea     rdx, [rsp+270h+NameBuffer]; lpNameBuffer
0x180079e71  lea     ecx, [rdi+1]; NameFormat
0x180079e74  call    cs:__imp_GetComputerObjectNameW
0x180079e7b  nop     dword ptr [rax+rax+00h]
0x180079e80  test    al, al
0x180079e82  jnz     short loc_180079EDD
0x180079e84  call    cs:__imp_GetLastError
0x180079e8b  nop     dword ptr [rax+rax+00h]
0x180079e90  mov     ebx, eax
0x180079e92  test    eax, eax
0x180079e94  jle     short loc_180079E9F
0x180079e96  movzx   ebx, ax
0x180079e99  or      ebx, 80070000h
0x180079e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ea6  lea     rax, WPP_GLOBAL_Control
0x180079ead  cmp     rcx, rax
0x180079eb0  jz      loc_18007A01A
0x180079eb6  cmp     byte ptr [rcx+19h], 2
0x180079eba  jb      loc_18007A01A
0x180079ec0  mov     rcx, [rcx+10h]
0x180079ec4  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079ecb  mov     edx, 5Ch ; '\'
0x180079ed0  mov     r9d, ebx
0x180079ed3  call    WPP_SF_D
0x180079ed8  jmp     loc_18007A01A
0x180079edd  lea     r8, [rsp+270h+NameBuffer]
0x180079ee2  lea     rdx, aLdap; "LDAP://"
0x180079ee9  lea     rcx, [rsp+270h+lpszPathName]
0x180079eee  call    ComposeString
0x180079ef3  mov     ebx, eax
0x180079ef5  test    eax, eax
0x180079ef7  jns     short loc_180079F2B
0x180079ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f00  lea     rax, WPP_GLOBAL_Control
0x180079f07  cmp     rcx, rax
0x180079f0a  jz      loc_180079FED
0x180079f10  cmp     byte ptr [rcx+19h], 2
0x180079f14  jb      loc_180079FED
0x180079f1a  mov     edx, 5Dh ; ']'
0x180079f1f  lea     r9, aComposestring; "\"ComposeString\""
0x180079f26  jmp     loc_180079FD9
0x180079f2b  lea     rcx, [rsp+270h+lpszUserName]
0x180079f30  call    GetDomainMachineNameOnDC
0x180079f35  mov     ebx, eax
0x180079f37  test    eax, eax
0x180079f39  jns     short loc_180079F7B
0x180079f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f42  lea     rax, WPP_GLOBAL_Control
0x180079f49  cmp     rcx, rax
0x180079f4c  jz      short loc_180079F74
0x180079f4e  cmp     byte ptr [rcx+19h], 2
0x180079f52  jb      short loc_180079F74
0x180079f54  mov     rcx, [rcx+10h]
0x180079f58  lea     r9, aGetdomainmachi; "\"GetDomainMachineNameOnDC\""
0x180079f5f  mov     edx, 5Eh ; '^'
0x180079f64  mov     dword ptr [rsp+270h+riid], ebx
0x180079f68  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079f6f  call    WPP_SF_SD
0x180079f74  mov     rdi, [rsp+270h+lpszUserName]
0x180079f79  jmp     short loc_180079FED
0x180079f7b  mov     rdi, [rsp+270h+lpszUserName]
0x180079f80  lea     rax, IID_IDirectoryObject
0x180079f87  mov     rcx, [rsp+270h+lpszPathName]; lpszPathName
0x180079f8c  mov     rdx, rdi; lpszUserName
0x180079f8f  mov     [rsp+270h+ppObject], r14; ppObject
0x180079f94  mov     r9d, 1; dwReserved
0x180079f9a  xor     r8d, r8d; lpszPassword
0x180079f9d  mov     [rsp+270h+riid], rax; riid
0x180079fa2  call    cs:__imp_ADsOpenObject
0x180079fa9  nop     dword ptr [rax+rax+00h]
0x180079fae  mov     ebx, eax
0x180079fb0  test    eax, eax
0x180079fb2  jns     short loc_180079FED
0x180079fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180079fbb  lea     rax, WPP_GLOBAL_Control
0x180079fc2  cmp     rcx, rax
0x180079fc5  jz      short loc_180079FED
0x180079fc7  cmp     byte ptr [rcx+19h], 2
0x180079fcb  jb      short loc_180079FED
0x180079fcd  mov     edx, 5Fh ; '_'
0x180079fd2  lea     r9, aAdsopenobject; "\"ADsOpenObject\""
0x180079fd9  mov     rcx, [rcx+10h]
0x180079fdd  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079fe4  mov     dword ptr [rsp+270h+riid], ebx
0x180079fe8  call    WPP_SF_SD
0x180079fed  cmp     [rsp+270h+lpszPathName], 0
0x180079ff3  jz      short loc_18007A006
0x180079ff5  mov     rcx, [rsp+270h+lpszPathName]; hMem
0x180079ffa  call    cs:__imp_LocalFree
0x18007a001  nop     dword ptr [rax+rax+00h]
0x18007a006  test    rdi, rdi
0x18007a009  jz      short loc_18007A01A
0x18007a00b  mov     rcx, rdi; hMem
0x18007a00e  call    cs:__imp_LocalFree
0x18007a015  nop     dword ptr [rax+rax+00h]
0x18007a01a  mov     eax, ebx
0x18007a01c  mov     rcx, [rbp+170h+var_10]
0x18007a023  xor     rcx, rsp; StackCookie
0x18007a026  call    __security_check_cookie
0x18007a02b  lea     r11, [rsp+270h+var_s0]
0x18007a033  mov     rbx, [r11+18h]
0x18007a037  mov     rdi, [r11+20h]
0x18007a03b  mov     r14, [r11+28h]
0x18007a03f  mov     rsp, r11
0x18007a042  pop     rbp
0x18007a043  retn
```
