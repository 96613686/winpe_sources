# GetDomainMachineNameOnDC

- ea: `0x180079950`
- end: `0x180079b51`
- name: `GetDomainMachineNameOnDC`
- size: `513`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180079e20`
- `0x18007b3d0`

## callees

- `0x180005665`
- `0x18001ad74`
- `0x18001aea4`
- `0x180078f54`
- `0x180079950`
- `0x1800a0fb0`

## import_xrefs

- `NETAPI32!DsRoleGetPrimaryDomainInformation` at `0x18007999e`
- `NETAPI32!DsRoleGetPrimaryDomainInformation` at `0x18007999e`
- `NETAPI32!DsRoleFreeMemory` at `0x180079af3`
- `NETAPI32!DsRoleFreeMemory` at `0x180079af3`
- `KERNEL32!GetComputerNameW` at `0x180079a43`
- `KERNEL32!GetComputerNameW` at `0x180079a43`
- `KERNEL32!GetLastError` at `0x180079a53`
- `KERNEL32!GetLastError` at `0x180079a53`
- `KERNEL32!LocalFree` at `0x180079b07`
- `KERNEL32!LocalFree` at `0x180079b1b`
- `KERNEL32!LocalFree` at `0x180079b07`
- `KERNEL32!LocalFree` at `0x180079b1b`

## pseudocode

```c
__int64 __fastcall GetDomainMachineNameOnDC(__int64 a1)
{
  void *v1; // rsi
  void *v3; // rdi
  signed int PrimaryDomainInformation; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  PBYTE Buffer; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-C8h] BYREF
  void *v10; // [rsp+40h] [rbp-C0h] BYREF
  void *v11; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v12[264]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  Buffer = 0;
  v3 = 0;
  v11 = 0;
  v10 = 0;
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  v5 = PrimaryDomainInformation;
  if ( PrimaryDomainInformation > 0 )
    v5 = (unsigned __int16)PrimaryDomainInformation | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    if ( !Buffer )
      return v5;
    if ( (unsigned int)(*(_DWORD *)Buffer - 4) <= 1 )
    {
      nSize = 260;
      memset_0(v12, 0, 0x208u);
      if ( GetComputerNameW(v12, &nSize) )
      {
        ComposeString(&v11, *((_QWORD *)Buffer + 1), L"\\");
        ComposeString(&v10, v12, L"$");
        v3 = v10;
        v1 = v11;
        ComposeString(a1, v11, v10);
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, v5);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
      (unsigned int)L"\"DsRoleGetPrimaryDomainInformation\"",
      v5);
  }
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  if ( v1 )
    LocalFree(v1);
  if ( v3 )
    LocalFree(v3);
  return v5;
}

```

## disassembly

```asm
0x180079950  mov     [rsp-8+arg_8], rbx
0x180079955  mov     [rsp-8+arg_10], rsi
0x18007995a  push    rbp
0x18007995b  push    rdi
0x18007995c  push    r14
0x18007995e  lea     rbp, [rsp-170h]
0x180079966  sub     rsp, 270h
0x18007996d  mov     rax, cs:__security_cookie
0x180079974  xor     rax, rsp
0x180079977  mov     [rbp+180h+var_20], rax
0x18007997e  xor     esi, esi
0x180079980  lea     r8, [rsp+280h+Buffer]; Buffer
0x180079985  and     [rsp+280h+Buffer], rsi
0x18007998a  mov     r14, rcx
0x18007998d  xor     edi, edi
0x18007998f  mov     [rsp+280h+var_238], rsi
0x180079994  xor     ecx, ecx; lpServer
0x180079996  mov     [rsp+280h+var_240], rdi
0x18007999b  lea     edx, [rsi+1]; InfoLevel
0x18007999e  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800799a5  nop     dword ptr [rax+rax+00h]
0x1800799aa  mov     ebx, eax
0x1800799ac  test    eax, eax
0x1800799ae  jle     short loc_1800799B9
0x1800799b0  movzx   ebx, ax
0x1800799b3  or      ebx, 80070000h
0x1800799b9  test    ebx, ebx
0x1800799bb  jns     short loc_180079A03
0x1800799bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800799c4  lea     rax, WPP_GLOBAL_Control
0x1800799cb  cmp     rcx, rax
0x1800799ce  jz      loc_180079AE9
0x1800799d4  cmp     byte ptr [rcx+19h], 2
0x1800799d8  jb      loc_180079AE9
0x1800799de  mov     rcx, [rcx+10h]
0x1800799e2  lea     r9, aDsrolegetprima; "\"DsRoleGetPrimaryDomainInformation\""
0x1800799e9  mov     edx, 66h ; 'f'
0x1800799ee  mov     [rsp+280h+var_260], ebx
0x1800799f2  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x1800799f9  call    WPP_SF_SD
0x1800799fe  jmp     loc_180079AE9
0x180079a03  mov     rcx, [rsp+280h+Buffer]
0x180079a08  test    rcx, rcx
0x180079a0b  jz      loc_180079B27
0x180079a11  mov     eax, [rcx]
0x180079a13  sub     eax, 4
0x180079a16  cmp     eax, 1
0x180079a19  ja      loc_180079AE9
0x180079a1f  xor     edx, edx; Val
0x180079a21  mov     [rsp+280h+nSize], 104h
0x180079a29  mov     r8d, 208h; Size
0x180079a2f  lea     rcx, [rsp+280h+var_230]; void *
0x180079a34  call    memset_0
0x180079a39  lea     rdx, [rsp+280h+nSize]; nSize
0x180079a3e  lea     rcx, [rsp+280h+var_230]; lpBuffer
0x180079a43  call    cs:__imp_GetComputerNameW
0x180079a4a  nop     dword ptr [rax+rax+00h]
0x180079a4f  test    eax, eax
0x180079a51  jnz     short loc_180079AA1
0x180079a53  call    cs:__imp_GetLastError
0x180079a5a  nop     dword ptr [rax+rax+00h]
0x180079a5f  mov     ebx, eax
0x180079a61  test    eax, eax
0x180079a63  jle     short loc_180079A6E
0x180079a65  movzx   ebx, ax
0x180079a68  or      ebx, 80070000h
0x180079a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a75  lea     rax, WPP_GLOBAL_Control
0x180079a7c  cmp     rcx, rax
0x180079a7f  jz      short loc_180079AE9
0x180079a81  cmp     byte ptr [rcx+19h], 2
0x180079a85  jb      short loc_180079AE9
0x180079a87  mov     rcx, [rcx+10h]
0x180079a8b  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079a92  mov     edx, 67h ; 'g'
0x180079a97  mov     r9d, ebx
0x180079a9a  call    WPP_SF_D
0x180079a9f  jmp     short loc_180079AE9
0x180079aa1  mov     rdx, [rsp+280h+Buffer]
0x180079aa6  lea     r8, Delimiter; "\\"
0x180079aad  lea     rcx, [rsp+280h+var_238]
0x180079ab2  mov     rdx, [rdx+8]
0x180079ab6  call    ComposeString
0x180079abb  lea     r8, asc_1800BFD90; "$"
0x180079ac2  lea     rdx, [rsp+280h+var_230]
0x180079ac7  lea     rcx, [rsp+280h+var_240]
0x180079acc  call    ComposeString
0x180079ad1  mov     rdi, [rsp+280h+var_240]
0x180079ad6  mov     rcx, r14
0x180079ad9  mov     rsi, [rsp+280h+var_238]
0x180079ade  mov     r8, rdi
0x180079ae1  mov     rdx, rsi
0x180079ae4  call    ComposeString
0x180079ae9  mov     rcx, [rsp+280h+Buffer]; Buffer
0x180079aee  test    rcx, rcx
0x180079af1  jz      short loc_180079AFF
0x180079af3  call    cs:__imp_DsRoleFreeMemory
0x180079afa  nop     dword ptr [rax+rax+00h]
0x180079aff  test    rsi, rsi
0x180079b02  jz      short loc_180079B13
0x180079b04  mov     rcx, rsi; hMem
0x180079b07  call    cs:__imp_LocalFree
0x180079b0e  nop     dword ptr [rax+rax+00h]
0x180079b13  test    rdi, rdi
0x180079b16  jz      short loc_180079B27
0x180079b18  mov     rcx, rdi; hMem
0x180079b1b  call    cs:__imp_LocalFree
0x180079b22  nop     dword ptr [rax+rax+00h]
0x180079b27  mov     eax, ebx
0x180079b29  mov     rcx, [rbp+180h+var_20]
0x180079b30  xor     rcx, rsp; StackCookie
0x180079b33  call    __security_check_cookie
0x180079b38  lea     r11, [rsp+280h+var_10]
0x180079b40  mov     rbx, [r11+28h]
0x180079b44  mov     rsi, [r11+30h]
0x180079b48  mov     rsp, r11
0x180079b4b  pop     r14
0x180079b4d  pop     rdi
0x180079b4e  pop     rbp
0x180079b4f  retn
```
