# _mtdeletelocks

- ea: `0x180018a34`
- end: `0x180018ab1`
- name: `_mtdeletelocks`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fa94`

## callees

- `0x18000f264`
- `0x180018a34`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018a60`
- `KERNEL32!DeleteCriticalSection` at `0x180018a99`
- `KERNEL32!DeleteCriticalSection` at `0x180018a60`
- `KERNEL32!DeleteCriticalSection` at `0x180018a99`

## pseudocode

```c
void mtdeletelocks()
{
  __int64 i; // rbx
  void *v1; // rsi
  __int64 j; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  for ( i = 0; i != 36; ++i )
  {
    v1 = (void *)qword_18005EFC0[2 * i];
    if ( v1 && LODWORD(qword_18005EFC0[2 * i + 1]) != 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)qword_18005EFC0[2 * i]);
      free(v1);
      qword_18005EFC0[2 * i] = 0;
    }
  }
  for ( j = 0; j != 36; ++j )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)qword_18005EFC0[2 * j];
    if ( v3 )
    {
      if ( LODWORD(qword_18005EFC0[2 * j + 1]) == 1 )
        DeleteCriticalSection(v3);
    }
  }
}

```

## disassembly

```asm
0x180018a34  push    rbx
0x180018a36  push    rbp
0x180018a37  push    rsi
0x180018a38  push    rdi
0x180018a39  sub     rsp, 28h
0x180018a3d  xor     ebx, ebx
0x180018a3f  lea     rbp, qword_18005EFC0
0x180018a46  mov     rdi, rbx
0x180018a49  add     rdi, rdi
0x180018a4c  mov     rsi, [rbp+rdi*8+0]
0x180018a51  test    rsi, rsi
0x180018a54  jz      short loc_180018A77
0x180018a56  cmp     dword ptr [rbp+rdi*8+8], 1
0x180018a5b  jz      short loc_180018A77
0x180018a5d  mov     rcx, rsi; lpCriticalSection
0x180018a60  call    cs:__imp_DeleteCriticalSection
0x180018a66  mov     rcx, rsi; Block
0x180018a69  call    free
0x180018a6e  mov     qword ptr [rbp+rdi*8+0], 0
0x180018a77  inc     rbx
0x180018a7a  cmp     rbx, 24h ; '$'
0x180018a7e  jnz     short loc_180018A46
0x180018a80  xor     ebx, ebx
0x180018a82  mov     rax, rbx
0x180018a85  add     rax, rax
0x180018a88  mov     rcx, [rbp+rax*8+0]; lpCriticalSection
0x180018a8d  test    rcx, rcx
0x180018a90  jz      short loc_180018A9F
0x180018a92  cmp     dword ptr [rbp+rax*8+8], 1
0x180018a97  jnz     short loc_180018A9F
0x180018a99  call    cs:__imp_DeleteCriticalSection
0x180018a9f  inc     rbx
0x180018aa2  cmp     rbx, 24h ; '$'
0x180018aa6  jnz     short loc_180018A82
0x180018aa8  add     rsp, 28h
0x180018aac  pop     rdi
0x180018aad  pop     rsi
0x180018aae  pop     rbp
0x180018aaf  pop     rbx
0x180018ab0  retn
```
