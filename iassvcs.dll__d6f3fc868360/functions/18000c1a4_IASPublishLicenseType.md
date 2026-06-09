# IASPublishLicenseType

- ea: `0x18000c1a4`
- end: `0x18000c297`
- name: `IASPublishLicenseType`
- size: `243`
- prototype: `LSTATUS __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013280`

## callees

- `0x18000c1a4`
- `0x1800181a2`
- `0x1800181e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000c278`
- `ADVAPI32!RegSetValueExW` at `0x18000c278`
- `KERNEL32!GetVersionExW` at `0x18000c1e1`
- `KERNEL32!GetVersionExW` at `0x18000c1e1`
- `KERNEL32!GetLastError` at `0x18000c1eb`
- `KERNEL32!GetLastError` at `0x18000c1eb`

## pseudocode

```c
LSTATUS __fastcall IASPublishLicenseType(HKEY hKey)
{
  LSTATUS result; // eax
  int v3; // ecx
  BYTE Data[16]; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  unsigned __int16 v6; // [rsp+158h] [rbp-20h]
  char v7; // [rsp+15Ah] [rbp-1Eh]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( v7 == 1 )
    {
      v3 = (v6 >> 7) & 4;
    }
    else if ( (v6 & 0x80u) == 0 )
    {
      v3 = 2;
      if ( (v6 & 2) == 0 )
      {
        v3 = 5;
        if ( (v6 & 0x400) == 0 )
          v3 = (v6 & 0x20) != 0 ? 6 : 1;
      }
    }
    else
    {
      v3 = 3;
    }
    goto LABEL_11;
  }
  result = GetLastError();
  v3 = 0;
  if ( !result )
  {
LABEL_11:
    *(_DWORD *)Data = v3;
    return RegSetValueExW(hKey, L"LicenseType", 0, 4u, Data, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x18000c1a4  push    rbx
0x18000c1a6  sub     rsp, 170h
0x18000c1ad  mov     rax, cs:__security_cookie
0x18000c1b4  xor     rax, rsp
0x18000c1b7  mov     [rsp+178h+var_18], rax
0x18000c1bf  mov     rbx, rcx
0x18000c1c2  xor     edx, edx; Val
0x18000c1c4  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x18000c1c9  mov     r8d, 118h; Size
0x18000c1cf  call    memset_0
0x18000c1d4  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x18000c1d9  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000c1e1  call    cs:__imp_GetVersionExW
0x18000c1e7  test    eax, eax
0x18000c1e9  jnz     short loc_18000C1FC
0x18000c1eb  call    cs:__imp_GetLastError
0x18000c1f1  xor     ecx, ecx
0x18000c1f3  test    eax, eax
0x18000c1f5  jz      short loc_18000C24F
0x18000c1f7  jmp     loc_18000C27E
0x18000c1fc  cmp     [rsp+178h+var_1E], 1
0x18000c204  jnz     short loc_18000C216
0x18000c206  movzx   ecx, [rsp+178h+var_20]
0x18000c20e  shr     ecx, 7
0x18000c211  and     ecx, 4
0x18000c214  jmp     short loc_18000C24F
0x18000c216  mov     al, byte ptr [rsp+178h+var_20]
0x18000c21d  test    al, al
0x18000c21f  jns     short loc_18000C228
0x18000c221  mov     ecx, 3
0x18000c226  jmp     short loc_18000C24F
0x18000c228  mov     ecx, 2
0x18000c22d  test    cl, al
0x18000c22f  jnz     short loc_18000C24F
0x18000c231  mov     ecx, 400h
0x18000c236  test    [rsp+178h+var_20], cx
0x18000c23e  mov     ecx, 5
0x18000c243  jnz     short loc_18000C24F
0x18000c245  and     al, 20h
0x18000c247  neg     al
0x18000c249  sbb     eax, eax
0x18000c24b  and     ecx, eax
0x18000c24d  inc     ecx
0x18000c24f  mov     dword ptr [rsp+178h+Data], ecx
0x18000c253  lea     rax, [rsp+178h+Data]
0x18000c258  mov     rcx, rbx; hKey
0x18000c25b  mov     [rsp+178h+cbData], 4; cbData
0x18000c263  mov     r9d, 4; dwType
0x18000c269  mov     [rsp+178h+lpData], rax; lpData
0x18000c26e  xor     r8d, r8d; Reserved
0x18000c271  lea     rdx, ValueName; "LicenseType"
0x18000c278  call    cs:__imp_RegSetValueExW
0x18000c27e  mov     rcx, [rsp+178h+var_18]
0x18000c286  xor     rcx, rsp; StackCookie
0x18000c289  call    __security_check_cookie
0x18000c28e  add     rsp, 170h
0x18000c295  pop     rbx
0x18000c296  retn
```
