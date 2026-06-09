# CngRsa32Compat_MD5Final

- ea: `0x18001fa58`
- end: `0x18001fa96`
- name: `CngRsa32Compat_MD5Final`
- size: `62`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001c80`
- `0x180002810`
- `0x18000335c`
- `0x180006d40`
- `0x180007a40`

## callees

- `0x18001fa58`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18001fa83`
- `bcrypt!BCryptDestroyHash` at `0x18001fa83`
- `bcrypt!BCryptFinishHash` at `0x18001fa6f`
- `bcrypt!BCryptFinishHash` at `0x18001fa6f`

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
0x18001fa58  push    rbx
0x18001fa5a  sub     rsp, 20h
0x18001fa5e  xor     r9d, r9d; dwFlags
0x18001fa61  lea     rdx, [rcx+8]; pbOutput
0x18001fa65  mov     rbx, rcx
0x18001fa68  mov     rcx, [rcx]; hHash
0x18001fa6b  lea     r8d, [r9+10h]; cbOutput
0x18001fa6f  call    cs:__imp_BCryptFinishHash
0x18001fa75  test    eax, eax
0x18001fa77  jns     short loc_18001FA80
0x18001fa79  mov     ecx, 7
0x18001fa7e  int     29h; Win8: RtlFailFast(ecx)
0x18001fa80  mov     rcx, [rbx]; hHash
0x18001fa83  call    cs:__imp_BCryptDestroyHash
0x18001fa89  mov     qword ptr [rbx], 0
0x18001fa90  add     rsp, 20h
0x18001fa94  pop     rbx
0x18001fa95  retn
```
