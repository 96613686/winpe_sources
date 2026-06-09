# GetRegSz

- ea: `0x18000add4`
- end: `0x18000ae87`
- name: `GetRegSz`
- size: `179`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009588`
- `0x180009a30`

## callees

- `0x18000add4`

## import_xrefs

- `KERNEL32!RegQueryValueExW` at `0x18000ae14`
- `KERNEL32!RegQueryValueExW` at `0x18000ae6f`
- `KERNEL32!RegQueryValueExW` at `0x18000ae14`
- `KERNEL32!RegQueryValueExW` at `0x18000ae6f`
- `KERNEL32!GlobalAlloc` at `0x18000ae37`
- `KERNEL32!GlobalAlloc` at `0x18000ae37`

## pseudocode

```c
__int64 __fastcall GetRegSz(HKEY hKey, LPCWSTR lpValueName, BYTE **a3)
{
  unsigned int v6; // eax
  BYTE *lpData; // rax
  DWORD Type[6]; // [rsp+30h] [rbp-18h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(dwBytes) = 0;
  if ( RegQueryValueExW(hKey, lpValueName, 0, Type, 0, (LPDWORD)&dwBytes) || (v6 = dwBytes, (unsigned int)dwBytes < 2) )
  {
    v6 = 2;
    LODWORD(dwBytes) = 2;
  }
  lpData = (BYTE *)GlobalAlloc(0x40u, v6);
  if ( !lpData )
    return 8;
  *(_WORD *)lpData = 0;
  *a3 = lpData;
  RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, (LPDWORD)&dwBytes);
  return 0;
}

```

## disassembly

```asm
0x18000add4  mov     r11, rsp
0x18000add7  mov     [r11+8], rbx
0x18000addb  mov     [r11+10h], rsi
0x18000addf  push    rdi
0x18000ade0  sub     rsp, 40h
0x18000ade4  lea     rax, [r11+20h]
0x18000ade8  mov     [rsp+48h+Type], 0
0x18000adf0  mov     rsi, r8
0x18000adf3  mov     [r11-20h], rax
0x18000adf7  lea     r9, [r11-18h]; lpType
0x18000adfb  mov     qword ptr [r11-28h], 0
0x18000ae03  xor     r8d, r8d; lpReserved
0x18000ae06  mov     dword ptr [rsp+48h+dwBytes], 0
0x18000ae0e  mov     rbx, rdx
0x18000ae11  mov     rdi, rcx
0x18000ae14  call    cs:__imp_RegQueryValueExW
0x18000ae1a  test    eax, eax
0x18000ae1c  jnz     short loc_18000AE27
0x18000ae1e  mov     eax, dword ptr [rsp+48h+dwBytes]
0x18000ae22  cmp     eax, 2
0x18000ae25  jnb     short loc_18000AE30
0x18000ae27  mov     eax, 2
0x18000ae2c  mov     dword ptr [rsp+48h+dwBytes], eax
0x18000ae30  mov     edx, eax; dwBytes
0x18000ae32  mov     ecx, 40h ; '@'; uFlags
0x18000ae37  call    cs:__imp_GlobalAlloc
0x18000ae3d  mov     rcx, rax
0x18000ae40  test    rax, rax
0x18000ae43  jnz     short loc_18000AE4A
0x18000ae45  lea     eax, [rcx+8]
0x18000ae48  jmp     short loc_18000AE77
0x18000ae4a  xor     eax, eax
0x18000ae4c  lea     r9, [rsp+48h+Type]; lpType
0x18000ae51  mov     [rcx], ax
0x18000ae54  xor     r8d, r8d; lpReserved
0x18000ae57  lea     rax, [rsp+48h+dwBytes]
0x18000ae5c  mov     [rsi], rcx
0x18000ae5f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000ae64  mov     rdx, rbx; lpValueName
0x18000ae67  mov     [rsp+48h+lpData], rcx; lpData
0x18000ae6c  mov     rcx, rdi; hKey
0x18000ae6f  call    cs:__imp_RegQueryValueExW
0x18000ae75  xor     eax, eax
0x18000ae77  mov     rbx, [rsp+48h+arg_0]
0x18000ae7c  mov     rsi, [rsp+48h+arg_8]
0x18000ae81  add     rsp, 40h
0x18000ae85  pop     rdi
0x18000ae86  retn
```
