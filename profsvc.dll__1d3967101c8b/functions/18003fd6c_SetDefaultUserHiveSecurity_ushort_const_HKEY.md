# SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)

- ea: `0x18003fd6c`
- end: `0x18003fe11`
- name: `?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ed00`
- `0x180039d6c`

## callees

- `0x180037f78`
- `0x18003fd6c`
- `0x18003fe74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fda2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fda2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdf1`

## pseudocode

```c
__int64 __fastcall SetDefaultUserHiveSecurity(const unsigned __int16 *a1, HKEY a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  int v5; // edi
  __int64 result; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_USERS, a1, 0, 0x60019u, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    return (unsigned int)v4;
  v4 = SetUserHiveSecurity_(a1, hKey, (int (*)(HKEY, void *, void *, int, int))_ApplySecurityToRegistryTree);
  v5 = SetDefaultHiveAppContainerSecurity_(
         a1,
         hKey,
         (int (*)(HKEY, void *, void *, int, int))_ApplySecurityToRegistryTree);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 < 0 )
    return (unsigned int)v4;
  result = 0;
  if ( v5 < 0 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18003fd6c  mov     r11, rsp
0x18003fd6f  mov     [r11+8], rbx
0x18003fd73  mov     [r11+10h], rdx
0x18003fd77  push    rdi
0x18003fd78  sub     rsp, 30h
0x18003fd7c  mov     rdi, rcx
0x18003fd7f  mov     qword ptr [r11+10h], 0
0x18003fd87  lea     rax, [r11+10h]
0x18003fd8b  mov     rdx, rcx; lpSubKey
0x18003fd8e  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003fd95  mov     [r11-18h], rax
0x18003fd99  mov     r9d, 60019h; samDesired
0x18003fd9f  xor     r8d, r8d; ulOptions
0x18003fda2  call    cs:__imp_RegOpenKeyExW
0x18003fda8  mov     ebx, eax
0x18003fdaa  test    eax, eax
0x18003fdac  jle     short loc_18003FDB7
0x18003fdae  movzx   ebx, ax
0x18003fdb1  or      ebx, 80070000h
0x18003fdb7  test    ebx, ebx
0x18003fdb9  js      short loc_18003FE04
0x18003fdbb  mov     rdx, [rsp+38h+hKey]; HKEY
0x18003fdc0  lea     r8, ?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x18003fdc7  mov     rcx, rdi; unsigned __int16 *
0x18003fdca  call    ?SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetUserHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x18003fdcf  mov     rdx, [rsp+38h+hKey]; hKey
0x18003fdd4  lea     r8, ?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x18003fddb  mov     rcx, rdi; unsigned __int16 *
0x18003fdde  mov     ebx, eax
0x18003fde0  call    ?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x18003fde5  mov     rcx, [rsp+38h+hKey]; hKey
0x18003fdea  mov     edi, eax
0x18003fdec  test    rcx, rcx
0x18003fdef  jz      short loc_18003FDF7
0x18003fdf1  call    cs:__imp_RegCloseKey
0x18003fdf7  test    ebx, ebx
0x18003fdf9  js      short loc_18003FE04
0x18003fdfb  xor     eax, eax
0x18003fdfd  test    edi, edi
0x18003fdff  cmovs   eax, edi
0x18003fe02  jmp     short loc_18003FE06
0x18003fe04  mov     eax, ebx
0x18003fe06  mov     rbx, [rsp+38h+arg_0]
0x18003fe0b  add     rsp, 30h
0x18003fe0f  pop     rdi
0x18003fe10  retn
```
