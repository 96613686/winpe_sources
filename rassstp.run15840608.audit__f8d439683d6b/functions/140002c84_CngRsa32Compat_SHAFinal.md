# CngRsa32Compat_SHAFinal

- ea: `0x140002c84`
- end: `0x140002cd0`
- name: `CngRsa32Compat_SHAFinal`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400100ac`

## callees

- `0x140002c84`

## import_xrefs

- `ksecdd!BCryptDestroyHash` at `0x140002cb6`
- `ksecdd!BCryptDestroyHash` at `0x140002cb6`
- `ksecdd!BCryptFinishHash` at `0x140002c9c`
- `ksecdd!BCryptFinishHash` at `0x140002c9c`

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
0x140002c84  push    rbx
0x140002c86  sub     rsp, 20h
0x140002c8a  mov     rbx, rcx
0x140002c8d  test    rdx, rdx
0x140002c90  jz      short loc_140002CB3
0x140002c92  mov     rcx, [rcx]; hHash
0x140002c95  xor     r9d, r9d; dwFlags
0x140002c98  lea     r8d, [r9+14h]; cbOutput
0x140002c9c  call    cs:__imp_BCryptFinishHash
0x140002ca3  nop     dword ptr [rax+rax+00h]
0x140002ca8  test    eax, eax
0x140002caa  jns     short loc_140002CB3
0x140002cac  mov     ecx, 7
0x140002cb1  int     29h; Win8: RtlFailFast(ecx)
0x140002cb3  mov     rcx, [rbx]; hHash
0x140002cb6  call    cs:__imp_BCryptDestroyHash
0x140002cbd  nop     dword ptr [rax+rax+00h]
0x140002cc2  mov     qword ptr [rbx], 0
0x140002cc9  add     rsp, 20h
0x140002ccd  pop     rbx
0x140002cce  retn
```
