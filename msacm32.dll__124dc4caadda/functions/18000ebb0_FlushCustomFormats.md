# FlushCustomFormats

- ea: `0x18000ebb0`
- end: `0x18000ec11`
- name: `FlushCustomFormats`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000dff8`
- `0x180011018`

## callees

- `0x18000ebb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ebf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ebf8`

## pseudocode

```c
LSTATUS __fastcall FlushCustomFormats(__int64 a1)
{
  __int64 *i; // rbx
  LSTATUS result; // eax

  if ( *(_QWORD *)(a1 + 168) )
  {
    for ( i = *(__int64 **)(a1 + 136); i; i = (__int64 *)*i )
      result = RegSetValueExW(*(HKEY *)(a1 + 168), (LPCWSTR)(i[2] + 2), 0, 3u, (const BYTE *)i[3], *((_DWORD *)i + 8));
  }
  return result;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp+arg_0], rbx
0x18000ebb5  push    rdi
0x18000ebb6  sub     rsp, 30h
0x18000ebba  cmp     qword ptr [rcx+0A8h], 0
0x18000ebc2  mov     rdi, rcx
0x18000ebc5  jz      short loc_18000EC06
0x18000ebc7  mov     rbx, [rcx+88h]
0x18000ebce  jmp     short loc_18000EC01
0x18000ebd0  mov     eax, [rbx+20h]
0x18000ebd3  mov     r9d, 3; dwType
0x18000ebd9  mov     rdx, [rbx+10h]
0x18000ebdd  xor     r8d, r8d; Reserved
0x18000ebe0  mov     rcx, [rdi+0A8h]; hKey
0x18000ebe7  add     rdx, 2; lpValueName
0x18000ebeb  mov     [rsp+38h+cbData], eax; cbData
0x18000ebef  mov     rax, [rbx+18h]
0x18000ebf3  mov     [rsp+38h+lpData], rax; lpData
0x18000ebf8  call    cs:__imp_RegSetValueExW
0x18000ebfe  mov     rbx, [rbx]
0x18000ec01  test    rbx, rbx
0x18000ec04  jnz     short loc_18000EBD0
0x18000ec06  mov     rbx, [rsp+38h+arg_0]
0x18000ec0b  add     rsp, 30h
0x18000ec0f  pop     rdi
0x18000ec10  retn
```
