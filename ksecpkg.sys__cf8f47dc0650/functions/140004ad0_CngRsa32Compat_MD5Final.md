# CngRsa32Compat_MD5Final

- ea: `0x140004ad0`
- end: `0x140004b1f`
- name: `CngRsa32Compat_MD5Final`
- size: `79`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a4ec`
- `0x14000eb40`
- `0x14000eef8`
- `0x14000f340`
- `0x14002df20`

## callees

- `0x140004ad0`

## import_xrefs

- `cng!BCryptDestroyHash` at `0x140004afc`
- `cng!BCryptDestroyHash` at `0x140004afc`
- `cng!BCryptFinishHash` at `0x140004ae9`
- `cng!BCryptFinishHash` at `0x140004ae9`

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
0x140004ad0  push    rbx
0x140004ad2  sub     rsp, 20h
0x140004ad6  mov     rbx, rcx
0x140004ad9  lea     rdx, [rcx+8]; pbOutput
0x140004add  mov     rcx, [rcx]; hHash
0x140004ae0  xor     r9d, r9d; dwFlags
0x140004ae3  mov     r8d, 10h; cbOutput
0x140004ae9  call    cs:__imp_BCryptFinishHash
0x140004af0  nop     dword ptr [rax+rax+00h]
0x140004af5  test    eax, eax
0x140004af7  js      short loc_140004B16
0x140004af9  mov     rcx, [rbx]; hHash
0x140004afc  call    cs:__imp_BCryptDestroyHash
0x140004b03  nop     dword ptr [rax+rax+00h]
0x140004b08  mov     qword ptr [rbx], 0
0x140004b0f  add     rsp, 20h
0x140004b13  pop     rbx
0x140004b14  retn
0x140004b16  mov     ecx, 7
0x140004b1b  int     29h; Win8: RtlFailFast(ecx)
0x140004b1d  jmp     short loc_140004AF9
```
