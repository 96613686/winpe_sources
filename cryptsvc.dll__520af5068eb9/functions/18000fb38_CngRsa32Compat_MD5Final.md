# CngRsa32Compat_MD5Final

- ea: `0x18000fb38`
- end: `0x18000fb76`
- name: `CngRsa32Compat_MD5Final`
- size: `62`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800028f0`
- `0x180003f00`
- `0x180005bd0`
- `0x180007af0`

## callees

- `0x18000fb38`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18000fb63`
- `bcrypt!BCryptDestroyHash` at `0x18000fb63`
- `bcrypt!BCryptFinishHash` at `0x18000fb4f`
- `bcrypt!BCryptFinishHash` at `0x18000fb4f`

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
0x18000fb38  push    rbx
0x18000fb3a  sub     rsp, 20h
0x18000fb3e  xor     r9d, r9d; dwFlags
0x18000fb41  lea     rdx, [rcx+8]; pbOutput
0x18000fb45  mov     rbx, rcx
0x18000fb48  mov     rcx, [rcx]; hHash
0x18000fb4b  lea     r8d, [r9+10h]; cbOutput
0x18000fb4f  call    cs:__imp_BCryptFinishHash
0x18000fb55  test    eax, eax
0x18000fb57  jns     short loc_18000FB60
0x18000fb59  mov     ecx, 7
0x18000fb5e  int     29h; Win8: RtlFailFast(ecx)
0x18000fb60  mov     rcx, [rbx]; hHash
0x18000fb63  call    cs:__imp_BCryptDestroyHash
0x18000fb69  mov     qword ptr [rbx], 0
0x18000fb70  add     rsp, 20h
0x18000fb74  pop     rbx
0x18000fb75  retn
```
