# ATMmsize

- ea: `0x1400395c8`
- end: `0x1400395e9`
- name: `ATMmsize`
- size: `33`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140031ed8`
- `0x140038e74`
- `0x1400392dc`
- `0x140039564`
- `0x14003f708`
- `0x14004005c`
- `0x14005be0c`
- `0x140066080`
- `0x14007f17c`
- `0x140081a78`

## callees

- `0x1400395c8`

## pseudocode

```c
__int64 __fastcall ATMmsize(__int64 a1)
{
  __int64 result; // rax

  LODWORD(result) = 0;
  if ( a1 )
  {
    LODWORD(result) = *(_DWORD *)(a1 - 8);
    if ( (int)result < 0 )
      LODWORD(result) = -(int)result;
  }
  return (int)result;
}

```

## disassembly

```asm
0x1400395c8  sub     rsp, 18h
0x1400395cc  xor     eax, eax
0x1400395ce  test    rcx, rcx
0x1400395d1  jz      short loc_1400395E2
0x1400395d3  mov     eax, [rcx-8]
0x1400395d6  mov     [rsp+18h+var_18], eax
0x1400395d9  test    eax, eax
0x1400395db  jns     short loc_1400395E2
0x1400395dd  neg     eax
0x1400395df  mov     [rsp+18h+var_18], eax
0x1400395e2  cdqe
0x1400395e4  add     rsp, 18h
0x1400395e8  retn
0x140096b71  push    rbp
0x140096b73  mov     rbp, rdx
0x140096b76  pop     rbp
0x140096b77  retn
```
