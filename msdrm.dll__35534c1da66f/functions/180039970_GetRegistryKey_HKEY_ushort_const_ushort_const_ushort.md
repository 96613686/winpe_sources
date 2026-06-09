# GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x180039970`
- end: `0x180039a53`
- name: `?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800193e4`
- `0x1800262b4`
- `0x180026568`
- `0x180026b34`
- `0x180026bf0`
- `0x180039460`
- `0x180044088`

## callees

- `0x180001244`
- `0x180039970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800399b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800399b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039a2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039a2d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall GetRegistryKey(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  unsigned __int16 *v9; // rax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  int v14; // [rsp+74h] [rbp+2Ch]

  v14 = HIDWORD(a1);
  hKey = 0;
  Type = 0;
  cbData = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v6 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v9 = (unsigned __int16 *)operator new(cbData);
  *a4 = v9;
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_8;
  }
  v6 = RegQueryValueExW(hKey, a3, 0, &Type, (LPBYTE)v9, &cbData);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
  {
LABEL_2:
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180039970  mov     qword ptr [rsp-20h+cbData], rcx
0x180039975  push    rbp
0x180039976  push    rbx
0x180039977  push    rsi
0x180039978  push    rdi
0x180039979  mov     rbp, rsp
0x18003997c  sub     rsp, 48h
0x180039980  mov     rsi, r9
0x180039983  mov     [rbp+hKey], 0
0x18003998b  mov     rdi, r8
0x18003998e  mov     [rbp+Type], 0
0x180039995  lea     rax, [rbp+hKey]
0x180039999  mov     [rbp+cbData], 0
0x1800399a0  mov     r9d, 20019h; samDesired
0x1800399a6  mov     [rsp+48h+phkResult], rax; phkResult
0x1800399ab  xor     r8d, r8d; ulOptions
0x1800399ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800399b5  call    cs:__imp_RegOpenKeyExW
0x1800399bb  mov     ebx, eax
0x1800399bd  test    eax, eax
0x1800399bf  jz      short loc_1800399CE
0x1800399c1  jle     short loc_180039A39
0x1800399c3  movzx   ebx, ax
0x1800399c6  or      ebx, 80070000h
0x1800399cc  jmp     short loc_180039A39
0x1800399ce  mov     rcx, [rbp+hKey]; hKey
0x1800399d2  lea     rax, [rbp+cbData]
0x1800399d6  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800399db  lea     r9, [rbp+Type]; lpType
0x1800399df  xor     r8d, r8d; lpReserved
0x1800399e2  mov     [rsp+48h+phkResult], 0; lpData
0x1800399eb  mov     rdx, rdi; lpValueName
0x1800399ee  call    cs:__imp_RegQueryValueExW
0x1800399f4  mov     ebx, eax
0x1800399f6  test    eax, eax
0x1800399f8  jnz     short loc_1800399C1
0x1800399fa  mov     ecx, [rbp+cbData]; Size
0x1800399fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039a02  mov     [rsi], rax
0x180039a05  test    rax, rax
0x180039a08  jnz     short loc_180039A11
0x180039a0a  mov     ebx, 8007000Eh
0x180039a0f  jmp     short loc_180039A39
0x180039a11  lea     rcx, [rbp+cbData]
0x180039a15  xor     r8d, r8d; lpReserved
0x180039a18  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x180039a1d  lea     r9, [rbp+Type]; lpType
0x180039a21  mov     rcx, [rbp+hKey]; hKey
0x180039a25  mov     rdx, rdi; lpValueName
0x180039a28  mov     [rsp+48h+phkResult], rax; lpData
0x180039a2d  call    cs:__imp_RegQueryValueExW
0x180039a33  mov     ebx, eax
0x180039a35  test    eax, eax
0x180039a37  jnz     short loc_1800399C1
0x180039a39  mov     rcx, [rbp+hKey]; hKey
0x180039a3d  test    rcx, rcx
0x180039a40  jz      short loc_180039A48
0x180039a42  call    cs:__imp_RegCloseKey
0x180039a48  mov     eax, ebx
0x180039a4a  add     rsp, 48h
0x180039a4e  pop     rdi
0x180039a4f  pop     rsi
0x180039a50  pop     rbx
0x180039a51  pop     rbp
0x180039a52  retn
```
