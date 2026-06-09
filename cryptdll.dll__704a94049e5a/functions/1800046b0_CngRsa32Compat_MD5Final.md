# CngRsa32Compat_MD5Final

- ea: `0x1800046b0`
- end: `0x1800046f0`
- name: `CngRsa32Compat_MD5Final`
- size: `64`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800047d0`
- `0x1800067b0`
- `0x180006b18`
- `0x18000750c`

## callees

- `0x1800046b0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800046c9`
- `bcrypt!BCryptFinishHash` at `0x1800046c9`
- `bcrypt!BCryptDestroyHash` at `0x1800046dd`
- `bcrypt!BCryptDestroyHash` at `0x1800046dd`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Final(__int64 a1)
{
  NTSTATUS result; // eax

  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)a1, (PUCHAR)(a1 + 8), 0x10u, 0) < 0 )
    __fastfail(7u);
  result = BCryptDestroyHash(*(BCRYPT_HASH_HANDLE *)a1);
  *(_QWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800046b0  push    rbx
0x1800046b2  sub     rsp, 20h
0x1800046b6  mov     rbx, rcx
0x1800046b9  lea     rdx, [rcx+8]; pbOutput
0x1800046bd  mov     rcx, [rcx]; hHash
0x1800046c0  xor     r9d, r9d; dwFlags
0x1800046c3  mov     r8d, 10h; cbOutput
0x1800046c9  call    cs:__imp_BCryptFinishHash
0x1800046cf  test    eax, eax
0x1800046d1  jns     short loc_1800046DA
0x1800046d3  mov     ecx, 7
0x1800046d8  int     29h; Win8: RtlFailFast(ecx)
0x1800046da  mov     rcx, [rbx]; hHash
0x1800046dd  call    cs:__imp_BCryptDestroyHash
0x1800046e3  mov     qword ptr [rbx], 0
0x1800046ea  add     rsp, 20h
0x1800046ee  pop     rbx
0x1800046ef  retn
```
