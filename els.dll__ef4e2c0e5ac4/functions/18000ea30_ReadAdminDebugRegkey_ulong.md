# ReadAdminDebugRegkey(ulong *)

- ea: `0x18000ea30`
- end: `0x18000eb26`
- name: `?ReadAdminDebugRegkey@@YAJPEAK@Z`
- size: `246`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c7e8`

## callees

- `0x18000ea30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000eb16`
- `ADVAPI32!RegCloseKey` at `0x18000eb16`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea75`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea75`
- `ADVAPI32!RegQueryValueExW` at `0x18000ead0`
- `ADVAPI32!RegQueryValueExW` at `0x18000ead0`

## string_xrefs

- `0x18000eac2`: `ADsOpenObjectFlags`

## pseudocode

```c
LSTATUS __fastcall ReadAdminDebugRegkey(unsigned int *a1)
{
  LSTATUS result; // eax
  HKEY v3; // rcx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  if ( !a1 )
    return -2147024809;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\AdminDebug", 0, 1u, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v3 = hKey;
    if ( hKey )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      v4 = RegQueryValueExW(hKey, L"ADsOpenObjectFlags", 0, &Type, (LPBYTE)&Data, &cbData);
      v5 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v5 = (unsigned __int16)v4 | 0x80070000;
        v3 = hKey;
      }
      else
      {
        v3 = hKey;
        if ( Type - 4 <= 1 )
        {
          v5 = 0;
          *a1 = Data;
        }
        else
        {
          v5 = -2147024895;
        }
      }
    }
    else
    {
      v5 = -2147467259;
    }
    if ( v3 )
      RegCloseKey(v3);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000ea30  push    rbp
0x18000ea32  push    rbx
0x18000ea33  push    rdi
0x18000ea34  mov     rbp, rsp
0x18000ea37  sub     rsp, 30h
0x18000ea3b  mov     [rbp+hKey], 0
0x18000ea43  mov     rdi, rcx
0x18000ea46  test    rcx, rcx
0x18000ea49  jnz     short loc_18000EA55
0x18000ea4b  mov     eax, 80070057h
0x18000ea50  jmp     loc_18000EB1E
0x18000ea55  lea     rax, [rbp+hKey]
0x18000ea59  mov     r9d, 1; samDesired
0x18000ea5f  xor     r8d, r8d; ulOptions
0x18000ea62  mov     [rsp+30h+phkResult], rax; phkResult
0x18000ea67  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ea6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea75  call    cs:__imp_RegOpenKeyExW
0x18000ea7b  test    eax, eax
0x18000ea7d  jz      short loc_18000EA92
0x18000ea7f  jle     loc_18000EB1E
0x18000ea85  movzx   eax, ax
0x18000ea88  or      eax, 80070000h
0x18000ea8d  jmp     loc_18000EB1E
0x18000ea92  mov     rcx, [rbp+hKey]; hKey
0x18000ea96  test    rcx, rcx
0x18000ea99  jz      short loc_18000EB0C
0x18000ea9b  lea     rax, [rbp+cbData]
0x18000ea9f  mov     [rbp+Type], 0
0x18000eaa6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000eaab  lea     r9, [rbp+Type]; lpType
0x18000eaaf  lea     rax, [rbp+Data]
0x18000eab3  mov     [rbp+Data], 0
0x18000eaba  xor     r8d, r8d; lpReserved
0x18000eabd  mov     [rsp+30h+phkResult], rax; lpData
0x18000eac2  lea     rdx, aAdsopenobjectf; "ADsOpenObjectFlags"
0x18000eac9  mov     [rbp+cbData], 4
0x18000ead0  call    cs:__imp_RegQueryValueExW
0x18000ead6  mov     ebx, eax
0x18000ead8  test    eax, eax
0x18000eada  jnz     short loc_18000EAFB
0x18000eadc  mov     eax, [rbp+Type]
0x18000eadf  mov     rcx, [rbp+hKey]
0x18000eae3  add     eax, 0FFFFFFFCh
0x18000eae6  cmp     eax, 1
0x18000eae9  jbe     short loc_18000EAF2
0x18000eaeb  mov     ebx, 80070001h
0x18000eaf0  jmp     short loc_18000EB11
0x18000eaf2  mov     eax, [rbp+Data]
0x18000eaf5  xor     ebx, ebx
0x18000eaf7  mov     [rdi], eax
0x18000eaf9  jmp     short loc_18000EB11
0x18000eafb  jle     short loc_18000EB06
0x18000eafd  movzx   ebx, ax
0x18000eb00  or      ebx, 80070000h
0x18000eb06  mov     rcx, [rbp+hKey]
0x18000eb0a  jmp     short loc_18000EB11
0x18000eb0c  mov     ebx, 80004005h
0x18000eb11  test    rcx, rcx
0x18000eb14  jz      short loc_18000EB1C
0x18000eb16  call    cs:__imp_RegCloseKey
0x18000eb1c  mov     eax, ebx
0x18000eb1e  add     rsp, 30h
0x18000eb22  pop     rdi
0x18000eb23  pop     rbx
0x18000eb24  pop     rbp
0x18000eb25  retn
```
