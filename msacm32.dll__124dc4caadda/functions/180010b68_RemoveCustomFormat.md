# RemoveCustomFormat

- ea: `0x180010b68`
- end: `0x180010c09`
- name: `RemoveCustomFormat`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000dff8`

## callees

- `0x1800084c0`
- `0x18000e08c`
- `0x180010b68`
- `0x180011434`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010beb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010beb`

## pseudocode

```c
__int64 __fastcall RemoveCustomFormat(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rcx

  if ( *(_QWORD **)(a1 + 136) == a2 )
    *(_QWORD *)(a1 + 136) = *a2;
  if ( *(_QWORD **)(a1 + 144) == a2 )
    *(_QWORD *)(a1 + 144) = a2[1];
  v4 = (_QWORD *)a2[1];
  if ( v4 )
    *v4 = *a2;
  if ( *a2 )
    *(_QWORD *)(*a2 + 8LL) = a2[1];
  if ( (unsigned int)IsSystemName(a1, a2[2], 1) )
    SetSystemDefaultName(a1);
  RegDeleteValueW(*(HKEY *)(a1 + 168), (LPCWSTR)(a2[2] + 2LL));
  DeleteCustomFormat(a2);
  return 1;
}

```

## disassembly

```asm
0x180010b68  mov     [rsp+arg_0], rbx
0x180010b6d  push    rdi
0x180010b6e  sub     rsp, 20h
0x180010b72  mov     rbx, rdx
0x180010b75  mov     rdi, rcx
0x180010b78  cmp     [rcx+88h], rdx
0x180010b7f  jnz     short loc_180010B8B
0x180010b81  mov     rax, [rdx]
0x180010b84  mov     [rcx+88h], rax
0x180010b8b  cmp     [rcx+90h], rbx
0x180010b92  jnz     short loc_180010B9F
0x180010b94  mov     rax, [rdx+8]
0x180010b98  mov     [rcx+90h], rax
0x180010b9f  mov     rcx, [rdx+8]
0x180010ba3  test    rcx, rcx
0x180010ba6  jz      short loc_180010BAE
0x180010ba8  mov     rax, [rdx]
0x180010bab  mov     [rcx], rax
0x180010bae  mov     rcx, [rdx]
0x180010bb1  test    rcx, rcx
0x180010bb4  jz      short loc_180010BBE
0x180010bb6  mov     rax, [rdx+8]
0x180010bba  mov     [rcx+8], rax
0x180010bbe  mov     rdx, [rdx+10h]
0x180010bc2  mov     r8d, 1
0x180010bc8  mov     rcx, rdi
0x180010bcb  call    IsSystemName
0x180010bd0  test    eax, eax
0x180010bd2  jz      short loc_180010BDC
0x180010bd4  mov     rcx, rdi
0x180010bd7  call    SetSystemDefaultName
0x180010bdc  mov     rdx, [rbx+10h]
0x180010be0  mov     rcx, [rdi+0A8h]; hKey
0x180010be7  add     rdx, 2; lpValueName
0x180010beb  call    cs:__imp_RegDeleteValueW
0x180010bf1  mov     rcx, rbx; pMem
0x180010bf4  call    DeleteCustomFormat
0x180010bf9  mov     rbx, [rsp+28h+arg_0]
0x180010bfe  mov     eax, 1
0x180010c03  add     rsp, 20h
0x180010c07  pop     rdi
0x180010c08  retn
```
