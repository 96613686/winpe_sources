# MmAllocate(unsigned __int64)

- ea: `0x14000ed18`
- end: `0x14000ed69`
- name: `?MmAllocate@@YAPEAX_K@Z`
- size: `81`
- prototype: `void *__fastcall(size_t)`
- caller_count: `46`
- callee_count: `3`
- tags: ``

## callers

- `0x140002e10`
- `0x140002e34`
- `0x1400030ac`
- `0x140003720`
- `0x140003958`
- `0x140003f54`
- `0x1400046e0`
- `0x14000474c`
- `0x140004868`
- `0x140006624`
- `0x1400069a0`
- `0x140006a08`
- `0x140006a40`
- `0x140006a9c`
- `0x140007a18`
- `0x140007a64`
- `0x140009854`
- `0x140009994`
- `0x14000b2f0`
- `0x14000b43c`
- `0x14000b6f0`
- `0x14000baa8`
- `0x14000bdc0`
- `0x14000ca74`
- `0x14000d00c`
- `0x14000d75c`
- `0x14000d9d0`
- `0x14000e6d4`
- `0x14000e768`
- `0x14000eff0`
- `0x14000f6e0`
- `0x14000fabc`
- `0x14000fe40`
- `0x140010428`
- `0x1400107fc`
- `0x1400115c8`
- `0x1400124a8`
- `0x140012508`
- `0x140012d70`
- `0x140012e34`
- `0x140012edc`
- `0x1400130ac`
- `0x140014dbc`
- `0x140015220`
- `0x14001b47c`
- `0x14001d30d`

## callees

- `0x14000a5bc`
- `0x14000ed18`
- `0x14000ed70`

## import_xrefs

- `msvcrt!malloc` at `0x14000ed21`
- `msvcrt!malloc` at `0x14000ed21`

## pseudocode

```c
void *__fastcall MmAllocate(size_t a1)
{
  void *result; // rax

  result = malloc(a1);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_842345050487338cb5c1d37caa43611b_Traceguids, a1);
    MmThrowBadAlloc();
  }
  return result;
}

```

## disassembly

```asm
0x14000ed18  push    rbx
0x14000ed1a  sub     rsp, 20h
0x14000ed1e  mov     rbx, rcx
0x14000ed21  call    cs:__imp_malloc
0x14000ed27  test    rax, rax
0x14000ed2a  jnz     short loc_14000ED63
0x14000ed2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed33  lea     rax, WPP_GLOBAL_Control
0x14000ed3a  cmp     rcx, rax
0x14000ed3d  jz      short loc_14000ED5D
0x14000ed3f  test    byte ptr [rcx+1Ch], 1
0x14000ed43  jz      short loc_14000ED5D
0x14000ed45  mov     rcx, [rcx+10h]
0x14000ed49  lea     r8, WPP_842345050487338cb5c1d37caa43611b_Traceguids
0x14000ed50  mov     edx, 0Bh
0x14000ed55  mov     r9, rbx
0x14000ed58  call    WPP_SF_q
0x14000ed5d  call    ?MmThrowBadAlloc@@YAXXZ; MmThrowBadAlloc(void)
0x14000ed63  add     rsp, 20h
0x14000ed67  pop     rbx
0x14000ed68  retn
```
