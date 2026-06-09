# RegQueryDWORDWithDefault(HKEY__ *,ushort const *,ulong)

- ea: `0x180011c68`
- end: `0x180011d0a`
- name: `?RegQueryDWORDWithDefault@@YAKPEAUHKEY__@@PEBGK@Z`
- size: `162`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001215c`

## callees

- `0x180011c68`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180011cf1`
- `ADVAPI32!RegSetValueExW` at `0x180011cf1`
- `ADVAPI32!RegQueryValueExW` at `0x180011cb1`
- `ADVAPI32!RegQueryValueExW` at `0x180011cb1`

## pseudocode

```c
__int64 __fastcall RegQueryDWORDWithDefault(HKEY hKey, LPCWSTR lpValueName, unsigned int a3)
{
  LSTATUS v5; // eax
  DWORD v7; // [rsp+30h] [rbp-10h] BYREF
  BYTE lpData[12]; // [rsp+34h] [rbp-Ch] BYREF
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  Data = a3;
  Type = 0;
  *(_DWORD *)lpData = 0;
  v7 = 4;
  v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &v7);
  if ( !v5 )
  {
    if ( Type == 4 && v7 == 4 )
      return *(unsigned int *)lpData;
    goto LABEL_6;
  }
  if ( v5 == 2 )
LABEL_6:
    RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  return Data;
}

```

## disassembly

```asm
0x180011c68  mov     r11, rsp
0x180011c6b  mov     [r11+8], rbx
0x180011c6f  mov     [r11+10h], rdi
0x180011c73  mov     [r11+18h], r8d
0x180011c77  push    rbp
0x180011c78  mov     rbp, rsp
0x180011c7b  sub     rsp, 40h
0x180011c7f  lea     rax, [rbp+var_10]
0x180011c83  mov     [rbp+Type], 0
0x180011c8a  mov     [r11-20h], rax
0x180011c8e  lea     r9, [rbp+Type]; lpType
0x180011c92  lea     rax, [rbp+var_C]
0x180011c96  mov     dword ptr [rbp+var_C], 0
0x180011c9d  xor     r8d, r8d; lpReserved
0x180011ca0  mov     [r11-28h], rax
0x180011ca4  mov     rbx, rdx
0x180011ca7  mov     [rbp+var_10], 4
0x180011cae  mov     rdi, rcx
0x180011cb1  call    cs:__imp_RegQueryValueExW
0x180011cb7  test    eax, eax
0x180011cb9  jnz     short loc_180011CCC
0x180011cbb  cmp     [rbp+Type], 4
0x180011cbf  jnz     short loc_180011CD1
0x180011cc1  cmp     [rbp+var_10], 4
0x180011cc5  jnz     short loc_180011CD1
0x180011cc7  mov     eax, dword ptr [rbp+var_C]
0x180011cca  jmp     short loc_180011CFA
0x180011ccc  cmp     eax, 2
0x180011ccf  jnz     short loc_180011CF7
0x180011cd1  lea     rax, [rbp+Data]
0x180011cd5  mov     [rsp+40h+cbData], 4; cbData
0x180011cdd  mov     r9d, 4; dwType
0x180011ce3  mov     [rsp+40h+lpData], rax; lpData
0x180011ce8  xor     r8d, r8d; Reserved
0x180011ceb  mov     rdx, rbx; lpValueName
0x180011cee  mov     rcx, rdi; hKey
0x180011cf1  call    cs:__imp_RegSetValueExW
0x180011cf7  mov     eax, [rbp+Data]
0x180011cfa  mov     rbx, [rsp+40h+arg_0]
0x180011cff  mov     rdi, [rsp+40h+arg_8]
0x180011d04  add     rsp, 40h
0x180011d08  pop     rbp
0x180011d09  retn
```
