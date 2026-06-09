# CngRsa32Compat_SHAFinal

- ea: `0x18000e090`
- end: `0x18000e0d1`
- name: `CngRsa32Compat_SHAFinal`
- size: `65`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ab6c`
- `0x18001b3ec`
- `0x18001c570`

## callees

- `0x18000e090`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18000e0be`
- `bcrypt!BCryptDestroyHash` at `0x18000e0be`
- `bcrypt!BCryptFinishHash` at `0x18000e0aa`
- `bcrypt!BCryptFinishHash` at `0x18000e0aa`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAFinal(BCRYPT_HASH_HANDLE *a1, UCHAR *a2)
{
  NTSTATUS result; // eax

  if ( a2 && BCryptFinishHash(*a1, a2, 0x14u, 0) < 0 )
    __fastfail(7u);
  result = BCryptDestroyHash(*a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e090  push    rbx
0x18000e092  sub     rsp, 20h
0x18000e096  mov     rbx, rcx
0x18000e099  test    rdx, rdx
0x18000e09c  jz      short loc_18000E0BB
0x18000e09e  mov     rcx, [rcx]; hHash
0x18000e0a1  xor     r9d, r9d; dwFlags
0x18000e0a4  mov     r8d, 14h; cbOutput
0x18000e0aa  call    cs:__imp_BCryptFinishHash
0x18000e0b0  test    eax, eax
0x18000e0b2  jns     short loc_18000E0BB
0x18000e0b4  mov     ecx, 7
0x18000e0b9  int     29h; Win8: RtlFailFast(ecx)
0x18000e0bb  mov     rcx, [rbx]; hHash
0x18000e0be  call    cs:__imp_BCryptDestroyHash
0x18000e0c4  mov     qword ptr [rbx], 0
0x18000e0cb  add     rsp, 20h
0x18000e0cf  pop     rbx
0x18000e0d0  retn
```
