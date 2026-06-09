# GetCLBSKeyInfo(ushort *,ulong,ushort *)

- ea: `0x18001dd1c`
- end: `0x18001deaa`
- name: `?GetCLBSKeyInfo@@YAJPEAGK0@Z`
- size: `398`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e744`

## callees

- `0x18000a01c`
- `0x18001dd1c`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dd89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dd89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001dddf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001dddf`

## string_xrefs

- `0x18001dd82`: `SOFTWARE\Microsoft\COM3\CLBS`

## pseudocode

```c
LSTATUS __fastcall GetCLBSKeyInfo(unsigned __int16 *a1, __int64 a2, char *a3)
{
  LSTATUS result; // eax
  DWORD v6; // ebx
  DWORD i; // edx
  WCHAR *v8; // rax
  int v9; // r8d
  int v10; // ecx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 Data[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  cchValueName = 260;
  cbData = 520;
  Type = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3\\CLBS", 0, 0x20019u, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      cchValueName = 260;
      cbData = 520;
      if ( RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
        break;
      if ( Type == 1 )
      {
        v8 = ValueName;
        do
        {
          v9 = *(WCHAR *)((char *)v8 + a3 - (char *)ValueName);
          v10 = *v8 - v9;
          if ( v10 )
            break;
          ++v8;
        }
        while ( v9 );
        if ( !v10 )
        {
          RegCloseKey(hKey);
          if ( (int)StringCchCopyW(a1, 0x104u, Data) < 0 )
            return -2147024774;
        }
      }
      ++v6;
    }
    RegCloseKey(hKey);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001dd1c  push    rbp
0x18001dd1e  push    rbx
0x18001dd1f  push    rsi
0x18001dd20  push    rdi
0x18001dd21  lea     rbp, [rsp-398h]
0x18001dd29  sub     rsp, 498h
0x18001dd30  mov     rax, cs:__security_cookie
0x18001dd37  xor     rax, rsp
0x18001dd3a  mov     [rbp+3B0h+var_30], rax
0x18001dd41  mov     rdi, r8
0x18001dd44  mov     [rsp+4B0h+hKey], 0
0x18001dd4d  mov     rsi, rcx
0x18001dd50  mov     [rsp+4B0h+cchValueName], 104h
0x18001dd58  lea     rax, [rsp+4B0h+hKey]
0x18001dd5d  mov     [rsp+4B0h+cbData], 208h
0x18001dd65  xor     r8d, r8d; ulOptions
0x18001dd68  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18001dd6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001dd74  mov     [rsp+4B0h+Type], 0
0x18001dd7c  mov     r9d, 20019h; samDesired
0x18001dd82  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\COM3\\CLBS"
0x18001dd89  call    cs:__imp_RegOpenKeyExW
0x18001dd8f  test    eax, eax
0x18001dd91  jnz     loc_18001DE85
0x18001dd97  lea     rax, [rsp+4B0h+cbData]
0x18001dd9c  xor     ebx, ebx
0x18001dd9e  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18001dda3  xor     edx, edx; dwIndex
0x18001dda5  lea     rax, [rsp+4B0h+Data]
0x18001ddaa  mov     [rsp+4B0h+lpData], rax; lpData
0x18001ddaf  lea     rax, [rsp+4B0h+Type]
0x18001ddb4  mov     [rsp+4B0h+lpType], rax; lpType
0x18001ddb9  mov     [rsp+4B0h+phkResult], rbx; lpReserved
0x18001ddbe  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18001ddc3  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x18001ddc8  lea     r8, [rbp+3B0h+ValueName]; lpValueName
0x18001ddcf  mov     [rsp+4B0h+cchValueName], 104h
0x18001ddd7  mov     [rsp+4B0h+cbData], 208h
0x18001dddf  call    cs:__imp_RegEnumValueW
0x18001dde5  test    eax, eax
0x18001dde7  jnz     loc_18001DE73
0x18001dded  cmp     [rsp+4B0h+Type], 1
0x18001ddf2  jnz     short loc_18001DE3C
0x18001ddf4  lea     rax, [rbp+3B0h+ValueName]
0x18001ddfb  mov     rdx, rdi
0x18001ddfe  sub     rdx, rax
0x18001de01  movzx   ecx, word ptr [rax]
0x18001de04  movzx   r8d, word ptr [rax+rdx]
0x18001de09  sub     ecx, r8d
0x18001de0c  jnz     short loc_18001DE17
0x18001de0e  add     rax, 2
0x18001de12  test    r8d, r8d
0x18001de15  jnz     short loc_18001DE01
0x18001de17  test    ecx, ecx
0x18001de19  jnz     short loc_18001DE3C
0x18001de1b  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18001de20  call    cs:__imp_RegCloseKey
0x18001de26  lea     r8, [rsp+4B0h+Data]; unsigned __int16 *
0x18001de2b  mov     edx, 104h; unsigned __int64
0x18001de30  mov     rcx, rsi; unsigned __int16 *
0x18001de33  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001de38  test    eax, eax
0x18001de3a  js      short loc_18001DE6C
0x18001de3c  lea     rax, [rsp+4B0h+cbData]
0x18001de41  inc     ebx
0x18001de43  mov     [rsp+4B0h+lpcbData], rax
0x18001de48  mov     edx, ebx
0x18001de4a  lea     rax, [rsp+4B0h+Data]
0x18001de4f  mov     [rsp+4B0h+lpData], rax
0x18001de54  lea     rax, [rsp+4B0h+Type]
0x18001de59  mov     [rsp+4B0h+lpType], rax
0x18001de5e  mov     [rsp+4B0h+phkResult], 0
0x18001de67  jmp     loc_18001DDBE
0x18001de6c  mov     eax, 8007007Ah
0x18001de71  jmp     short loc_18001DE8F
0x18001de73  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18001de78  call    cs:__imp_RegCloseKey
0x18001de7e  mov     eax, 1
0x18001de83  jmp     short loc_18001DE8F
0x18001de85  jle     short loc_18001DE8F
0x18001de87  movzx   eax, ax
0x18001de8a  or      eax, 80070000h
0x18001de8f  mov     rcx, [rbp+3B0h+var_30]
0x18001de96  xor     rcx, rsp; StackCookie
0x18001de99  call    __security_check_cookie
0x18001de9e  add     rsp, 498h
0x18001dea5  pop     rdi
0x18001dea6  pop     rsi
0x18001dea7  pop     rbx
0x18001dea8  pop     rbp
0x18001dea9  retn
```
