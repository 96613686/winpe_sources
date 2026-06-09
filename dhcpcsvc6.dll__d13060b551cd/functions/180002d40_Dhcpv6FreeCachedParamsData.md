# Dhcpv6FreeCachedParamsData

- ea: `0x180002d40`
- end: `0x180002dc5`
- name: `Dhcpv6FreeCachedParamsData`
- size: `133`
- prototype: `HLOCAL __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d8c`

## pseudocode

```c
HLOCAL __fastcall Dhcpv6FreeCachedParamsData(int *a1)
{
  __int64 v1; // rbx
  unsigned int v2; // r14d
  unsigned int v3; // esi
  __int64 v4; // rbp
  __int64 v5; // rdi
  HLOCAL result; // rax

  v1 = *((_QWORD *)a1 + 1);
  if ( v1 )
  {
    v2 = *a1;
    if ( *a1 )
    {
      v3 = 0;
      v4 = 0;
      do
      {
        v5 = 32 * v4;
        result = LocalFree(*(HLOCAL *)(32 * v4 + v1 + 16));
        ++v3;
        *(_QWORD *)(v5 + v1 + 16) = 0;
        ++v4;
        *(_DWORD *)(v5 + v1 + 24) = 0;
      }
      while ( v3 < v2 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d40  push    rbx
0x180002d42  sub     rsp, 30h
0x180002d46  mov     rbx, [rcx+8]
0x180002d4a  test    rbx, rbx
0x180002d4d  jz      short loc_180002DBF
0x180002d4f  mov     [rsp+38h+var_10], r14
0x180002d54  mov     r14d, [rcx]
0x180002d57  test    r14d, r14d
0x180002d5a  jz      short loc_180002DBA
0x180002d5c  mov     [rsp+38h+arg_0], rbp
0x180002d61  mov     [rsp+38h+arg_8], rsi
0x180002d66  mov     [rsp+38h+arg_10], rdi
0x180002d6b  mov     [rsp+38h+var_18], r15
0x180002d70  xor     r15d, r15d
0x180002d73  mov     esi, r15d
0x180002d76  mov     ebp, r15d
0x180002d79  nop     dword ptr [rax+00000000h]
0x180002d80  mov     rdi, rbp
0x180002d83  shl     rdi, 5
0x180002d87  mov     rcx, [rdi+rbx+10h]; hMem
0x180002d8c  call    cs:__imp_LocalFree
0x180002d92  inc     esi
0x180002d94  mov     [rdi+rbx+10h], r15
0x180002d99  inc     rbp
0x180002d9c  mov     [rdi+rbx+18h], r15d
0x180002da1  cmp     esi, r14d
0x180002da4  jb      short loc_180002D80
0x180002da6  mov     r15, [rsp+38h+var_18]
0x180002dab  mov     rdi, [rsp+38h+arg_10]
0x180002db0  mov     rsi, [rsp+38h+arg_8]
0x180002db5  mov     rbp, [rsp+38h+arg_0]
0x180002dba  mov     r14, [rsp+38h+var_10]
0x180002dbf  add     rsp, 30h
0x180002dc3  pop     rbx
0x180002dc4  retn
```
