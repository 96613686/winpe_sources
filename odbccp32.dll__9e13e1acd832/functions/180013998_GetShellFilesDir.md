# GetShellFilesDir

- ea: `0x180013998`
- end: `0x180013a5b`
- name: `GetShellFilesDir`
- size: `195`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer, UINT uSize)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c98`
- `0x1800134d4`

## callees

- `0x180013998`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180013a40`
- `KERNEL32!GetSystemDirectoryW` at `0x180013a40`
- `ADVAPI32!RegCloseKey` at `0x180013a31`
- `ADVAPI32!RegCloseKey` at `0x180013a31`
- `ADVAPI32!RegGetValueW` at `0x180013a24`
- `ADVAPI32!RegGetValueW` at `0x180013a24`
- `ADVAPI32!RegOpenKeyExW` at `0x1800139e9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800139e9`

## string_xrefs

- `0x180013a02`: `CommonFilesDir`

## pseudocode

```c
__int64 __fastcall GetShellFilesDir(LPWSTR lpBuffer, UINT uSize)
{
  DWORD v2; // eax
  LSTATUS ValueW; // ebx
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v2 = 2 * uSize;
  hkey = 0;
  if ( !uSize )
    v2 = 0;
  pcbData = v2;
  *lpBuffer = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hkey)
    || (ValueW = RegGetValueW(hkey, &SubKey, L"CommonFilesDir", 2u, 0, lpBuffer, &pcbData), RegCloseKey(hkey), ValueW) )
  {
    GetSystemDirectoryW(lpBuffer, uSize);
  }
  return 1;
}

```

## disassembly

```asm
0x180013998  mov     r11, rsp
0x18001399b  mov     [r11+8], rbx
0x18001399f  mov     [r11+20h], rsi
0x1800139a3  mov     [r11+18h], r8
0x1800139a7  push    rdi
0x1800139a8  sub     rsp, 40h
0x1800139ac  lea     eax, [rdx+rdx]
0x1800139af  mov     qword ptr [r11+18h], 0
0x1800139b7  test    edx, edx
0x1800139b9  mov     esi, edx
0x1800139bb  mov     rdi, rcx
0x1800139be  mov     r9d, 20019h; samDesired
0x1800139c4  cmovz   eax, edx
0x1800139c7  xor     r8d, r8d; ulOptions
0x1800139ca  mov     [rsp+48h+arg_8], eax
0x1800139ce  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800139d5  xor     eax, eax
0x1800139d7  mov     [rcx], ax
0x1800139da  lea     rax, [r11+18h]
0x1800139de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800139e5  mov     [r11-28h], rax
0x1800139e9  call    cs:__imp_RegOpenKeyExW
0x1800139ef  test    eax, eax
0x1800139f1  jnz     short loc_180013A3B
0x1800139f3  mov     rcx, [rsp+48h+hkey]; hkey
0x1800139f8  lea     rax, [rsp+48h+arg_8]
0x1800139fd  mov     [rsp+48h+pcbData], rax; pcbData
0x180013a02  lea     r8, aCommonfilesdir; "CommonFilesDir"
0x180013a09  mov     [rsp+48h+pvData], rdi; pvData
0x180013a0e  lea     rdx, SubKey; lpSubKey
0x180013a15  mov     r9d, 2; dwFlags
0x180013a1b  mov     [rsp+48h+pdwType], 0; pdwType
0x180013a24  call    cs:__imp_RegGetValueW
0x180013a2a  mov     rcx, [rsp+48h+hkey]; hKey
0x180013a2f  mov     ebx, eax
0x180013a31  call    cs:__imp_RegCloseKey
0x180013a37  test    ebx, ebx
0x180013a39  jz      short loc_180013A46
0x180013a3b  mov     edx, esi; uSize
0x180013a3d  mov     rcx, rdi; lpBuffer
0x180013a40  call    cs:__imp_GetSystemDirectoryW
0x180013a46  mov     rbx, [rsp+48h+arg_0]
0x180013a4b  mov     eax, 1
0x180013a50  mov     rsi, [rsp+48h+arg_18]
0x180013a55  add     rsp, 40h
0x180013a59  pop     rdi
0x180013a5a  retn
```
