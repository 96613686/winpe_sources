# GetRegBinary

- ea: `0x1800413ac`
- end: `0x180041463`
- name: `GetRegBinary`
- size: `183`
- prototype: `int __fastcall(HKEY hKey, __int64, BYTE **, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180040768`

## callees

- `0x1800413ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180041414`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180041414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041403`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041443`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041403`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041443`

## string_xrefs

- `0x1800413d0`: `ConfigData`
- `0x180041434`: `ConfigData`

## pseudocode

```c
int __fastcall GetRegBinary(HKEY hKey, __int64 a2, BYTE **a3, _DWORD *a4)
{
  BYTE *lpData; // rax
  BYTE *v8; // rbx
  DWORD dwBytes; // [rsp+58h] [rbp+10h] BYREF
  int dwBytes_4; // [rsp+5Ch] [rbp+14h]
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF

  dwBytes_4 = HIDWORD(a2);
  *a3 = 0;
  *a4 = 0;
  Type = 0;
  dwBytes = 0;
  LODWORD(lpData) = RegQueryValueExW(hKey, L"ConfigData", 0, &Type, 0, &dwBytes);
  if ( !(_DWORD)lpData )
  {
    lpData = (BYTE *)GlobalAlloc(0x40u, dwBytes);
    v8 = lpData;
    if ( lpData )
    {
      LODWORD(lpData) = RegQueryValueExW(hKey, L"ConfigData", 0, &Type, lpData, &dwBytes);
      if ( !(_DWORD)lpData )
      {
        LODWORD(lpData) = dwBytes;
        *a3 = v8;
        *a4 = (_DWORD)lpData;
      }
    }
  }
  return (int)lpData;
}

```

## disassembly

```asm
0x1800413ac  mov     r11, rsp
0x1800413af  mov     [r11+8], rbx
0x1800413b3  mov     [r11+10h], rdx
0x1800413b7  push    rbp
0x1800413b8  push    rsi
0x1800413b9  push    rdi
0x1800413ba  sub     rsp, 30h
0x1800413be  mov     qword ptr [r8], 0
0x1800413c5  lea     rax, [r11+10h]
0x1800413c9  mov     dword ptr [r9], 0
0x1800413d0  lea     rdx, aConfigdata; "ConfigData"
0x1800413d7  mov     rdi, r9
0x1800413da  mov     [r11-20h], rax
0x1800413de  mov     rsi, r8
0x1800413e1  mov     qword ptr [r11-28h], 0
0x1800413e9  lea     r9, [r11+18h]; lpType
0x1800413ed  mov     [rsp+48h+Type], 0
0x1800413f5  xor     r8d, r8d; lpReserved
0x1800413f8  mov     dword ptr [rsp+48h+dwBytes], 0
0x180041400  mov     rbp, rcx
0x180041403  call    cs:__imp_RegQueryValueExW
0x180041409  test    eax, eax
0x18004140b  jnz     short loc_180041456
0x18004140d  mov     edx, dword ptr [rsp+48h+dwBytes]; dwBytes
0x180041411  lea     ecx, [rax+40h]; uFlags
0x180041414  call    cs:__imp_GlobalAlloc
0x18004141a  mov     rbx, rax
0x18004141d  test    rax, rax
0x180041420  jz      short loc_180041456
0x180041422  lea     rax, [rsp+48h+dwBytes]
0x180041427  xor     r8d, r8d; lpReserved
0x18004142a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18004142f  lea     r9, [rsp+48h+Type]; lpType
0x180041434  lea     rdx, aConfigdata; "ConfigData"
0x18004143b  mov     [rsp+48h+lpData], rbx; lpData
0x180041440  mov     rcx, rbp; hKey
0x180041443  call    cs:__imp_RegQueryValueExW
0x180041449  test    eax, eax
0x18004144b  jnz     short loc_180041456
0x18004144d  mov     eax, dword ptr [rsp+48h+dwBytes]
0x180041451  mov     [rsi], rbx
0x180041454  mov     [rdi], eax
0x180041456  mov     rbx, [rsp+48h+arg_0]
0x18004145b  add     rsp, 30h
0x18004145f  pop     rdi
0x180041460  pop     rsi
0x180041461  pop     rbp
0x180041462  retn
```
