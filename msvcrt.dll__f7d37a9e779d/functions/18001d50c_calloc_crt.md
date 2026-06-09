# _calloc_crt

- ea: `0x18001d50c`
- end: `0x18001d562`
- name: `_calloc_crt`
- size: `86`
- prototype: ``
- caller_count: `63`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a24`
- `0x180008140`
- `0x180008330`
- `0x180008f30`
- `0x180018cc0`
- `0x180019010`
- `0x180019810`
- `0x180019b70`
- `0x18001a300`
- `0x18001a660`
- `0x18001ad60`
- `0x18001b0e0`
- `0x18001b604`
- `0x18001b684`
- `0x18001bba4`
- `0x18001bf4c`
- `0x18001c4a0`
- `0x18001d804`
- `0x18001e9c0`
- `0x18001fd30`
- `0x18002b790`
- `0x18002c350`
- `0x18002c760`
- `0x18002d060`
- `0x18002dd60`
- `0x18002e660`
- `0x18002f6a8`
- `0x18002f9b0`
- `0x180030340`
- `0x180030e40`
- `0x180031450`
- `0x180031608`
- `0x180031940`
- `0x180031cc0`
- `0x180033660`
- `0x180033adc`
- `0x180034084`
- `0x1800343b0`
- `0x180034950`
- `0x180035020`
- `0x180036d94`
- `0x18003714c`
- `0x1800374d0`
- `0x18003777c`
- `0x18003e074`
- `0x18003e1dc`
- `0x18003e2a0`
- `0x18003e4b0`
- `0x18003f628`
- `0x18003f754`

## callees

- `0x18001d50c`
- `0x18001d688`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d53d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d53d`

## pseudocode

```c
__int64 __fastcall calloc_crt(__int64 a1, __int64 a2)
{
  DWORD v4; // ebx
  __int64 v5; // rdi

  v4 = 0;
  do
  {
    v5 = calloc_impl(a1, a2, 0);
    if ( v5 )
      break;
    if ( !maxwait )
      break;
    Sleep(v4);
    v4 += 1000;
    if ( v4 > maxwait )
      break;
  }
  while ( v4 != -1 );
  return v5;
}

```

## disassembly

```asm
0x18001d50c  push    rbx
0x18001d50e  push    rbp
0x18001d50f  push    rsi
0x18001d510  push    rdi
0x18001d511  sub     rsp, 28h
0x18001d515  mov     rsi, rdx
0x18001d518  mov     rbp, rcx
0x18001d51b  xor     ebx, ebx
0x18001d51d  xor     r8d, r8d
0x18001d520  mov     rdx, rsi
0x18001d523  mov     rcx, rbp
0x18001d526  call    _calloc_impl
0x18001d52b  mov     rdi, rax
0x18001d52e  test    rax, rax
0x18001d531  jnz     short loc_18001D556
0x18001d533  cmp     cs:_maxwait, eax
0x18001d539  jbe     short loc_18001D556
0x18001d53b  mov     ecx, ebx; dwMilliseconds
0x18001d53d  call    cs:__imp_Sleep
0x18001d543  add     ebx, 3E8h
0x18001d549  cmp     ebx, cs:_maxwait
0x18001d54f  ja      short loc_18001D556
0x18001d551  cmp     ebx, 0FFFFFFFFh
0x18001d554  jnz     short loc_18001D51D
0x18001d556  mov     rax, rdi
0x18001d559  add     rsp, 28h
0x18001d55d  pop     rdi
0x18001d55e  pop     rsi
0x18001d55f  pop     rbp
0x18001d560  pop     rbx
0x18001d561  retn
```
