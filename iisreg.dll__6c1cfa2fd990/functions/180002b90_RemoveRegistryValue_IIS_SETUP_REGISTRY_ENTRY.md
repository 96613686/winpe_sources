# RemoveRegistryValue(IIS_SETUP_REGISTRY_ENTRY *)

- ea: `0x180002b90`
- end: `0x180002d0b`
- name: `?RemoveRegistryValue@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180001a20`

## callees

- `0x180001ab0`
- `0x180001afc`
- `0x18000200c`
- `0x180002b90`
- `0x180002ff8`
- `0x180003650`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180002cf0`
- `ADVAPI32!RegDeleteValueW` at `0x180002cf0`
- `ADVAPI32!RegSetValueExW` at `0x180002ce0`
- `ADVAPI32!RegSetValueExW` at `0x180002ce0`
- `ADVAPI32!RegOpenKeyExW` at `0x180002c28`
- `ADVAPI32!RegOpenKeyExW` at `0x180002c28`
- `ADVAPI32!RegCloseKey` at `0x180002c48`
- `ADVAPI32!RegCloseKey` at `0x180002c48`

## pseudocode

```c
__int64 __fastcall RemoveRegistryValue(struct IIS_SETUP_REGISTRY_ENTRY *a1)
{
  BYTE *v1; // rdx
  __int64 v3; // rcx
  signed int v4; // ebx
  HKEY v5; // rax
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v9[4]; // [rsp+38h] [rbp-48h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-28h]
  int v11; // [rsp+60h] [rbp-20h]
  __int16 v12; // [rsp+64h] [rbp-1Ch]
  __int64 v13; // [rsp+68h] [rbp-18h]

  v1 = (BYTE *)v9;
  hKey = 0;
  lpData = (BYTE *)v9;
  v9[0] = 0;
  v3 = 0;
  v11 = 32;
  v12 = 256;
  while ( 1 )
  {
    *(_WORD *)&v1[2 * v3++] = 0;
    if ( v3 == 2 )
      break;
    v1 = lpData;
  }
  v13 = 2;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_9;
  }
  v5 = ConvertStringToHKey(*((wchar_t **)a1 + 1));
  v6 = RegOpenKeyExW(v5, *((LPCWSTR *)a1 + 2), 0, 0xF003Fu, &hKey);
  v4 = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
      goto LABEL_9;
    goto LABEL_8;
  }
  v4 = 0;
  if ( ConvertStringToType(*((wchar_t **)a1 + 4)) != 7 || (unsigned int)(*((_DWORD *)a1 + 13) - 1) > 1 )
    goto LABEL_19;
  v4 = GetMultiSzRegistryValueToWriteForRemoval(a1, (struct MULTISZ *)v9);
  if ( v4 < 0 )
    goto LABEL_9;
  if ( HIDWORD(v13) )
    v6 = RegSetValueExW(hKey, *((LPCWSTR *)a1 + 3), 0, 7u, lpData, 2 * v13);
  else
LABEL_19:
    v6 = RegDeleteValueW(hKey, *((LPCWSTR *)a1 + 3));
  if ( v6 )
  {
    if ( v6 > 0 )
    {
LABEL_8:
      v4 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_9;
    }
    v4 = v6;
  }
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (_BYTE)v12 )
    BUFFER::FreeMemoryInternal((BUFFER *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002b90  mov     [rsp-8+arg_8], rbx
0x180002b95  mov     [rsp-8+arg_10], rdi
0x180002b9a  push    rbp
0x180002b9b  mov     rbp, rsp
0x180002b9e  sub     rsp, 80h
0x180002ba5  mov     rax, cs:__security_cookie
0x180002bac  xor     rax, rsp
0x180002baf  mov     [rbp+var_10], rax
0x180002bb3  lea     rdx, [rbp+var_48]
0x180002bb7  mov     [rbp+hKey], 0
0x180002bbf  mov     rdi, rcx
0x180002bc2  mov     [rbp+lpData], rdx
0x180002bc6  mov     [rbp+var_48], 0
0x180002bce  xor     ecx, ecx
0x180002bd0  mov     [rbp+var_20], 20h ; ' '
0x180002bd7  mov     [rbp+var_1C], 100h
0x180002bdd  xor     eax, eax
0x180002bdf  mov     [rdx+rcx*2], ax
0x180002be3  inc     rcx
0x180002be6  cmp     rcx, 2
0x180002bea  jz      short loc_180002BF2
0x180002bec  mov     rdx, [rbp+lpData]
0x180002bf0  jmp     short loc_180002BDD
0x180002bf2  mov     [rbp+var_18], 2
0x180002bfa  test    rdi, rdi
0x180002bfd  jnz     short loc_180002C06
0x180002bff  mov     ebx, 80070057h
0x180002c04  jmp     short loc_180002C3F
0x180002c06  mov     rcx, [rdi+8]; String1
0x180002c0a  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x180002c0f  mov     rdx, [rdi+10h]; lpSubKey
0x180002c13  lea     rcx, [rbp+hKey]
0x180002c17  mov     [rsp+80h+phkResult], rcx; phkResult
0x180002c1c  mov     r9d, 0F003Fh; samDesired
0x180002c22  mov     rcx, rax; hKey
0x180002c25  xor     r8d, r8d; ulOptions
0x180002c28  call    cs:__imp_RegOpenKeyExW
0x180002c2e  mov     ebx, eax
0x180002c30  test    eax, eax
0x180002c32  jz      short loc_180002C88
0x180002c34  jle     short loc_180002C3F
0x180002c36  movzx   ebx, ax
0x180002c39  or      ebx, 80070000h
0x180002c3f  mov     rcx, [rbp+hKey]; hKey
0x180002c43  test    rcx, rcx
0x180002c46  jz      short loc_180002C56
0x180002c48  call    cs:__imp_RegCloseKey
0x180002c4e  mov     [rbp+hKey], 0
0x180002c56  cmp     byte ptr [rbp+var_1C], 0
0x180002c5a  jz      short loc_180002C65
0x180002c5c  lea     rcx, [rbp+var_48]; this
0x180002c60  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002c65  mov     eax, ebx
0x180002c67  mov     rcx, [rbp+var_10]
0x180002c6b  xor     rcx, rsp; StackCookie
0x180002c6e  call    __security_check_cookie
0x180002c73  lea     r11, [rsp+80h+var_s0]
0x180002c7b  mov     rbx, [r11+18h]
0x180002c7f  mov     rdi, [r11+20h]
0x180002c83  mov     rsp, r11
0x180002c86  pop     rbp
0x180002c87  retn
0x180002c88  mov     rcx, [rdi+20h]; String1
0x180002c8c  xor     ebx, ebx
0x180002c8e  call    ?ConvertStringToType@@YAKPEAG@Z; ConvertStringToType(ushort *)
0x180002c93  cmp     eax, 7
0x180002c96  jnz     short loc_180002CE8
0x180002c98  mov     eax, [rdi+34h]
0x180002c9b  dec     eax
0x180002c9d  cmp     eax, 1
0x180002ca0  ja      short loc_180002CE8
0x180002ca2  lea     rdx, [rbp+var_48]; this
0x180002ca6  mov     rcx, rdi; struct IIS_SETUP_REGISTRY_ENTRY *
0x180002ca9  call    ?GetMultiSzRegistryValueToWriteForRemoval@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVMULTISZ@@@Z; GetMultiSzRegistryValueToWriteForRemoval(IIS_SETUP_REGISTRY_ENTRY *,MULTISZ *)
0x180002cae  mov     ebx, eax
0x180002cb0  test    eax, eax
0x180002cb2  js      short loc_180002C3F
0x180002cb4  cmp     dword ptr [rbp+var_18+4], 0
0x180002cb8  jbe     short loc_180002CE8
0x180002cba  mov     r8d, dword ptr [rbp+var_18]
0x180002cbe  mov     r9d, 7; dwType
0x180002cc4  mov     rdx, [rdi+18h]; lpValueName
0x180002cc8  add     r8d, r8d
0x180002ccb  mov     rcx, [rbp+hKey]; hKey
0x180002ccf  mov     [rsp+80h+cbData], r8d; cbData
0x180002cd4  mov     r8, [rbp+lpData]
0x180002cd8  mov     [rsp+80h+phkResult], r8; lpData
0x180002cdd  xor     r8d, r8d; Reserved
0x180002ce0  call    cs:__imp_RegSetValueExW
0x180002ce6  jmp     short loc_180002CF6
0x180002ce8  mov     rdx, [rdi+18h]; lpValueName
0x180002cec  mov     rcx, [rbp+hKey]; hKey
0x180002cf0  call    cs:__imp_RegDeleteValueW
0x180002cf6  test    eax, eax
0x180002cf8  jz      loc_180002C3F
0x180002cfe  jg      loc_180002C36
0x180002d04  mov     ebx, eax
0x180002d06  jmp     loc_180002C3F
```
