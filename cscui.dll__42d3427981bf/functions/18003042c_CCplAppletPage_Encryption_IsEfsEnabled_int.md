# CCplAppletPage_Encryption::_IsEfsEnabled(int *)

- ea: `0x18003042c`
- end: `0x1800304ee`
- name: `?_IsEfsEnabled@CCplAppletPage_Encryption@@CAJPEAH@Z`
- size: `194`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f5f0`

## callees

- `0x18003042c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030468`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030468`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800304a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800304a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800304cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800304cc`

## string_xrefs

- `0x18003047f`: `EfsConfiguration`

## pseudocode

```c
__int64 __fastcall CCplAppletPage_Encryption::_IsEfsEnabled(int *a1)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 1;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\EFS",
         0,
         1u,
         &hKey);
  if ( !v2 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"EfsConfiguration", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 )
    {
      if ( Type == 4 )
        *a1 = (Data & 1) == 0;
      else
        v2 = 13;
    }
    RegCloseKey(hKey);
  }
  result = 0;
  if ( v2 != 2 )
    result = v2;
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003042c  push    rbp
0x18003042e  push    rbx
0x18003042f  push    rdi
0x180030430  mov     rbp, rsp
0x180030433  sub     rsp, 30h
0x180030437  mov     rdi, rcx
0x18003043a  mov     dword ptr [rcx], 1
0x180030440  lea     rax, [rbp+hKey]
0x180030444  mov     [rbp+hKey], 0
0x18003044c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030453  mov     [rsp+30h+phkResult], rax; phkResult
0x180030458  mov     r9d, 1; samDesired
0x18003045e  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180030465  xor     r8d, r8d; ulOptions
0x180030468  call    cs:__imp_RegOpenKeyExW
0x18003046e  mov     ebx, eax
0x180030470  test    eax, eax
0x180030472  jnz     short loc_1800304D2
0x180030474  mov     rcx, [rbp+hKey]; hKey
0x180030478  lea     r9, [rbp+Type]; lpType
0x18003047c  mov     [rbp+Data], eax
0x18003047f  lea     rdx, aEfsconfigurati; "EfsConfiguration"
0x180030486  mov     [rbp+Type], eax
0x180030489  xor     r8d, r8d; lpReserved
0x18003048c  lea     rax, [rbp+cbData]
0x180030490  mov     [rbp+cbData], 4
0x180030497  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003049c  lea     rax, [rbp+Data]
0x1800304a0  mov     [rsp+30h+phkResult], rax; lpData
0x1800304a5  call    cs:__imp_RegQueryValueExW
0x1800304ab  mov     ebx, eax
0x1800304ad  test    eax, eax
0x1800304af  jnz     short loc_1800304C8
0x1800304b1  cmp     [rbp+Type], 4
0x1800304b5  jnz     short loc_1800304C3
0x1800304b7  mov     eax, [rbp+Data]
0x1800304ba  not     eax
0x1800304bc  and     eax, 1
0x1800304bf  mov     [rdi], eax
0x1800304c1  jmp     short loc_1800304C8
0x1800304c3  mov     ebx, 0Dh
0x1800304c8  mov     rcx, [rbp+hKey]; hKey
0x1800304cc  call    cs:__imp_RegCloseKey
0x1800304d2  xor     eax, eax
0x1800304d4  cmp     ebx, 2
0x1800304d7  cmovnz  eax, ebx
0x1800304da  test    eax, eax
0x1800304dc  jle     short loc_1800304E6
0x1800304de  movzx   eax, ax
0x1800304e1  or      eax, 80070000h
0x1800304e6  add     rsp, 30h
0x1800304ea  pop     rdi
0x1800304eb  pop     rbx
0x1800304ec  pop     rbp
0x1800304ed  retn
```
