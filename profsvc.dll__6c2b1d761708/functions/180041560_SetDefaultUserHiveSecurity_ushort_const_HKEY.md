# SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)

- ea: `0x180041560`
- end: `0x180041612`
- name: `?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030050`
- `0x18003b26c`

## callees

- `0x180039ce0`
- `0x180041560`
- `0x180041678`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041596`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415eb`

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
0x180041560  mov     r11, rsp
0x180041563  mov     [r11+8], rbx
0x180041567  mov     [r11+10h], rdx
0x18004156b  push    rdi
0x18004156c  sub     rsp, 30h
0x180041570  mov     rdi, rcx
0x180041573  mov     qword ptr [r11+10h], 0
0x18004157b  lea     rax, [r11+10h]
0x18004157f  mov     rdx, rcx; lpSubKey
0x180041582  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180041589  mov     [r11-18h], rax
0x18004158d  mov     r9d, 60019h; samDesired
0x180041593  xor     r8d, r8d; ulOptions
0x180041596  call    cs:__imp_RegOpenKeyExW
0x18004159d  nop     dword ptr [rax+rax+00h]
0x1800415a2  mov     ebx, eax
0x1800415a4  test    eax, eax
0x1800415a6  jle     short loc_1800415B1
0x1800415a8  movzx   ebx, ax
0x1800415ab  or      ebx, 80070000h
0x1800415b1  test    ebx, ebx
0x1800415b3  js      short loc_180041604
0x1800415b5  mov     rdx, [rsp+38h+hKey]; HKEY
0x1800415ba  lea     r8, ?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x1800415c1  mov     rcx, rdi; unsigned __int16 *
0x1800415c4  call    ?SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetUserHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x1800415c9  mov     rdx, [rsp+38h+hKey]; hKey
0x1800415ce  lea     r8, ?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x1800415d5  mov     rcx, rdi; unsigned __int16 *
0x1800415d8  mov     ebx, eax
0x1800415da  call    ?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x1800415df  mov     rcx, [rsp+38h+hKey]; hKey
0x1800415e4  mov     edi, eax
0x1800415e6  test    rcx, rcx
0x1800415e9  jz      short loc_1800415F7
0x1800415eb  call    cs:__imp_RegCloseKey
0x1800415f2  nop     dword ptr [rax+rax+00h]
0x1800415f7  test    ebx, ebx
0x1800415f9  js      short loc_180041604
0x1800415fb  xor     eax, eax
0x1800415fd  test    edi, edi
0x1800415ff  cmovs   eax, edi
0x180041602  jmp     short loc_180041606
0x180041604  mov     eax, ebx
0x180041606  mov     rbx, [rsp+38h+arg_0]
0x18004160b  add     rsp, 30h
0x18004160f  pop     rdi
0x180041610  retn
```
