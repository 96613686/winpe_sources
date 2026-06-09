# CngRsa32Compat_MD5Final

- ea: `0x14000fd40`
- end: `0x14000fdaa`
- name: `CngRsa32Compat_MD5Final`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004a60`
- `0x1400099a0`
- `0x14000b140`
- `0x140011e70`
- `0x1400126a4`
- `0x14001276c`
- `0x14003ec3c`

## callees

- `0x14000fd40`

## import_xrefs

- `ksecdd!BCryptFinishHash` at `0x14000fd57`
- `ksecdd!BCryptFinishHash` at `0x14000fd57`
- `ksecdd!BCryptDestroyHash` at `0x14000fd71`
- `ksecdd!BCryptDestroyHash` at `0x14000fd71`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000fd8f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000fd8f`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Final(__int64 a1)
{
  NTSTATUS result; // eax
  void *v3; // rcx

  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)a1, (PUCHAR)(a1 + 16), 0x10u, 0) < 0 )
    __fastfail(7u);
  result = BCryptDestroyHash(*(BCRYPT_HASH_HANDLE *)a1);
  v3 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  if ( v3 )
  {
    result = BCryptCloseAlgorithmProvider(v3, 0);
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000fd40  push    rbx
0x14000fd42  sub     rsp, 20h
0x14000fd46  xor     r9d, r9d; dwFlags
0x14000fd49  lea     rdx, [rcx+10h]; pbOutput
0x14000fd4d  mov     rbx, rcx
0x14000fd50  mov     rcx, [rcx]; hHash
0x14000fd53  lea     r8d, [r9+10h]; cbOutput
0x14000fd57  call    cs:__imp_BCryptFinishHash
0x14000fd5e  nop     dword ptr [rax+rax+00h]
0x14000fd63  test    eax, eax
0x14000fd65  jns     short loc_14000FD6E
0x14000fd67  mov     ecx, 7
0x14000fd6c  int     29h; Win8: RtlFailFast(ecx)
0x14000fd6e  mov     rcx, [rbx]; hHash
0x14000fd71  call    cs:__imp_BCryptDestroyHash
0x14000fd78  nop     dword ptr [rax+rax+00h]
0x14000fd7d  mov     rcx, [rbx+8]; hAlgorithm
0x14000fd81  mov     qword ptr [rbx], 0
0x14000fd88  test    rcx, rcx
0x14000fd8b  jz      short loc_14000FDA3
0x14000fd8d  xor     edx, edx; dwFlags
0x14000fd8f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000fd96  nop     dword ptr [rax+rax+00h]
0x14000fd9b  mov     qword ptr [rbx+8], 0
0x14000fda3  add     rsp, 20h
0x14000fda7  pop     rbx
0x14000fda8  retn
```
