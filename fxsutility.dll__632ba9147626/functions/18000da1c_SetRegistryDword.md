# SetRegistryDword

- ea: `0x18000da1c`
- end: `0x18000da7e`
- name: `SetRegistryDword`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800157a4`
- `0x1800159c0`

## callees

- `0x18000613c`
- `0x18000da1c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000da64`
- `KERNEL32!SetLastError` at `0x18000da64`
- `ADVAPI32!RegSetValueExW` at `0x18000da44`
- `ADVAPI32!RegSetValueExW` at `0x18000da44`

## string_xrefs

- `0x18000da53`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryDword(HKEY a1, const WCHAR *a2, int a3)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v4 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v7, 4u);
  v5 = v4;
  if ( !v4 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", a2, v4);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x18000da1c  mov     r11, rsp
0x18000da1f  mov     [r11+8], rbx
0x18000da23  mov     [r11+18h], r8d
0x18000da27  push    rdi
0x18000da28  sub     rsp, 30h
0x18000da2c  mov     r9d, 4; dwType
0x18000da32  lea     rax, [r11+18h]
0x18000da36  mov     [r11-10h], r9d
0x18000da3a  xor     r8d, r8d; Reserved
0x18000da3d  mov     [r11-18h], rax
0x18000da41  mov     rdi, rdx
0x18000da44  call    cs:__imp_RegSetValueExW
0x18000da4a  mov     ebx, eax
0x18000da4c  test    eax, eax
0x18000da4e  jz      short loc_18000DA6E
0x18000da50  mov     r8d, eax
0x18000da53  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000da5a  mov     rdx, rdi
0x18000da5d  call    fax_dprintf
0x18000da62  mov     ecx, ebx; dwErrCode
0x18000da64  call    cs:__imp_SetLastError
0x18000da6a  xor     eax, eax
0x18000da6c  jmp     short loc_18000DA73
0x18000da6e  mov     eax, 1
0x18000da73  mov     rbx, [rsp+38h+arg_0]
0x18000da78  add     rsp, 30h
0x18000da7c  pop     rdi
0x18000da7d  retn
```
