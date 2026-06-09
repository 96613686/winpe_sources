# _ioterm

- ea: `0x18001da98`
- end: `0x18001db14`
- name: `_ioterm`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a24`

## callees

- `0x18001d300`
- `0x18001da98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dacf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dacf`

## pseudocode

```c
void ioterm()
{
  __int64 i; // rdi
  unsigned __int64 v1; // rbx
  void *v2; // rcx

  for ( i = 0; i != 64; ++i )
  {
    v1 = _pioinfo[i];
    if ( v1 )
    {
      if ( v1 >= v1 + 1792 )
      {
        v2 = (void *)_pioinfo[i];
      }
      else
      {
        do
        {
          if ( (*(_BYTE *)(v1 + 12) & 4) != 0 )
            DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
          v2 = (void *)_pioinfo[i];
          v1 += 56LL;
        }
        while ( v1 < (unsigned __int64)v2 + 1792 );
      }
      free(v2);
      _pioinfo[i] = 0;
    }
  }
}

```

## disassembly

```asm
0x18001da98  mov     [rsp+arg_0], rbx
0x18001da9d  mov     [rsp+arg_8], rsi
0x18001daa2  push    rdi
0x18001daa3  sub     rsp, 20h
0x18001daa7  xor     edi, edi
0x18001daa9  lea     rsi, __pioinfo
0x18001dab0  mov     rbx, [rsi+rdi*8]
0x18001dab4  test    rbx, rbx
0x18001dab7  jz      short loc_18001DAFB
0x18001dab9  lea     rax, [rbx+700h]
0x18001dac0  cmp     rbx, rax
0x18001dac3  jnb     short loc_18001DAEB
0x18001dac5  test    byte ptr [rbx+0Ch], 4
0x18001dac9  jz      short loc_18001DAD5
0x18001dacb  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001dacf  call    cs:__imp_DeleteCriticalSection
0x18001dad5  mov     rcx, [rsi+rdi*8]
0x18001dad9  add     rbx, 38h ; '8'
0x18001dadd  lea     rax, [rcx+700h]
0x18001dae4  cmp     rbx, rax
0x18001dae7  jb      short loc_18001DAC5
0x18001dae9  jmp     short loc_18001DAEE
0x18001daeb  mov     rcx, rbx; Block
0x18001daee  call    free
0x18001daf3  mov     qword ptr [rsi+rdi*8], 0
0x18001dafb  inc     rdi
0x18001dafe  cmp     rdi, 40h ; '@'
0x18001db02  jnz     short loc_18001DAA9
0x18001db04  mov     rbx, [rsp+28h+arg_0]
0x18001db09  mov     rsi, [rsp+28h+arg_8]
0x18001db0e  add     rsp, 20h
0x18001db12  pop     rdi
0x18001db13  retn
```
