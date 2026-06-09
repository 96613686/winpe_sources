# NgscbpDoesRegKeyExist

- ea: `0x180010ad8`
- end: `0x180010b5d`
- name: `NgscbpDoesRegKeyExist`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800114b4`
- `0x1800126b8`

## callees

- `0x180010ad8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180010b3d`
- `ADVAPI32!RegCloseKey` at `0x180010b3d`
- `ADVAPI32!RegOpenKeyExW` at `0x180010b12`
- `ADVAPI32!RegOpenKeyExW` at `0x180010b12`

## pseudocode

```c
__int64 __fastcall NgscbpDoesRegKeyExist(__int64 a1, __int64 a2, _DWORD *a3)
{
  LSTATUS v4; // eax
  int v5; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      *a3 = 0;
      v5 = 0;
    }
  }
  else
  {
    *a3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010ad8  mov     r11, rsp
0x180010adb  mov     [r11+8], rbx
0x180010adf  mov     [r11+10h], rdx
0x180010ae3  push    rdi
0x180010ae4  sub     rsp, 30h
0x180010ae8  mov     rdi, r8
0x180010aeb  mov     qword ptr [r11+10h], 0
0x180010af3  lea     rax, [r11+10h]
0x180010af7  xor     r8d, r8d; ulOptions
0x180010afa  mov     r9d, 20019h; samDesired
0x180010b00  mov     [r11-18h], rax
0x180010b04  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180010b0b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010b12  call    cs:__imp_RegOpenKeyExW
0x180010b18  mov     ebx, eax
0x180010b1a  test    eax, eax
0x180010b1c  jnz     short loc_180010B26
0x180010b1e  mov     dword ptr [rdi], 1
0x180010b24  jmp     short loc_180010B33
0x180010b26  cmp     eax, 2
0x180010b29  jnz     short loc_180010B33
0x180010b2b  mov     dword ptr [rdi], 0
0x180010b31  xor     ebx, ebx
0x180010b33  mov     rcx, [rsp+38h+hKey]; hKey
0x180010b38  test    rcx, rcx
0x180010b3b  jz      short loc_180010B43
0x180010b3d  call    cs:__imp_RegCloseKey
0x180010b43  test    ebx, ebx
0x180010b45  jle     short loc_180010B50
0x180010b47  movzx   ebx, bx
0x180010b4a  or      ebx, 80070000h
0x180010b50  mov     eax, ebx
0x180010b52  mov     rbx, [rsp+38h+arg_0]
0x180010b57  add     rsp, 30h
0x180010b5b  pop     rdi
0x180010b5c  retn
```
