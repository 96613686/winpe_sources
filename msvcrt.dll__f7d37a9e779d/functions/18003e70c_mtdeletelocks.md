# _mtdeletelocks

- ea: `0x18003e70c`
- end: `0x18003e789`
- name: `_mtdeletelocks`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003e264`

## callees

- `0x18001d300`
- `0x18003e70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e738`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e771`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e738`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e771`

## pseudocode

```c
void mtdeletelocks()
{
  __int64 i; // rbx
  __int64 **v1; // rsi
  __int64 j; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  for ( i = 0; i != 36; ++i )
  {
    v1 = (&off_18009C7C0)[2 * i];
    if ( v1 && LODWORD((&off_18009C7C0)[2 * i + 1]) != 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(&off_18009C7C0)[2 * i]);
      free(v1);
      (&off_18009C7C0)[2 * i] = 0;
    }
  }
  for ( j = 0; j != 36; ++j )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)(&off_18009C7C0)[2 * j];
    if ( v3 )
    {
      if ( LODWORD((&off_18009C7C0)[2 * j + 1]) == 1 )
        DeleteCriticalSection(v3);
    }
  }
}

```

## disassembly

```asm
0x18003e70c  push    rbx
0x18003e70e  push    rbp
0x18003e70f  push    rsi
0x18003e710  push    rdi
0x18003e711  sub     rsp, 28h
0x18003e715  xor     ebx, ebx
0x18003e717  lea     rbp, off_18009C7C0
0x18003e71e  mov     rdi, rbx
0x18003e721  add     rdi, rdi
0x18003e724  mov     rsi, [rbp+rdi*8+0]
0x18003e729  test    rsi, rsi
0x18003e72c  jz      short loc_18003E74F
0x18003e72e  cmp     dword ptr [rbp+rdi*8+8], 1
0x18003e733  jz      short loc_18003E74F
0x18003e735  mov     rcx, rsi; lpCriticalSection
0x18003e738  call    cs:__imp_DeleteCriticalSection
0x18003e73e  mov     rcx, rsi; Block
0x18003e741  call    free
0x18003e746  mov     qword ptr [rbp+rdi*8+0], 0
0x18003e74f  inc     rbx
0x18003e752  cmp     rbx, 24h ; '$'
0x18003e756  jnz     short loc_18003E71E
0x18003e758  xor     ebx, ebx
0x18003e75a  mov     rax, rbx
0x18003e75d  add     rax, rax
0x18003e760  mov     rcx, [rbp+rax*8+0]; lpCriticalSection
0x18003e765  test    rcx, rcx
0x18003e768  jz      short loc_18003E777
0x18003e76a  cmp     dword ptr [rbp+rax*8+8], 1
0x18003e76f  jnz     short loc_18003E777
0x18003e771  call    cs:__imp_DeleteCriticalSection
0x18003e777  inc     rbx
0x18003e77a  cmp     rbx, 24h ; '$'
0x18003e77e  jnz     short loc_18003E75A
0x18003e780  add     rsp, 28h
0x18003e784  pop     rdi
0x18003e785  pop     rsi
0x18003e786  pop     rbp
0x18003e787  pop     rbx
0x18003e788  retn
```
