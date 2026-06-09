# Tls1CombineRandomSeeds

- ea: `0x180012cdc`
- end: `0x180012d66`
- name: `Tls1CombineRandomSeeds`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cb0`

## callees

- `0x18000b594`
- `0x180012cdc`

## string_xrefs

- `0x180012d3c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1CombineRandomSeeds(_OWORD *a1, int a2, _OWORD *a3, int a4, _OWORD *a5)
{
  unsigned int v5; // ebx

  if ( a2 == 32 && a4 == 32 )
  {
    v5 = 0;
    *a5 = *a1;
    a5[1] = a1[1];
    a5[2] = *a3;
    a5[3] = a3[1];
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        91);
  }
  return v5;
}

```

## disassembly

```asm
0x180012cdc  push    rbx
0x180012cde  sub     rsp, 40h
0x180012ce2  cmp     edx, 20h ; ' '
0x180012ce5  jnz     short loc_180012D1A
0x180012ce7  cmp     r9d, edx
0x180012cea  jnz     short loc_180012D1A
0x180012cec  movups  xmm0, xmmword ptr [rcx]
0x180012cef  mov     rax, [rsp+48h+arg_20]
0x180012cf4  xor     ebx, ebx
0x180012cf6  movaps  xmmword ptr [rax], xmm0
0x180012cf9  movups  xmm1, xmmword ptr [rcx+10h]
0x180012cfd  movaps  xmmword ptr [rax+10h], xmm1
0x180012d01  movups  xmm0, xmmword ptr [r8]
0x180012d05  movups  xmmword ptr [rax+20h], xmm0
0x180012d09  movups  xmm1, xmmword ptr [r8+10h]
0x180012d0e  movups  xmmword ptr [rax+30h], xmm1
0x180012d12  mov     eax, ebx
0x180012d14  add     rsp, 40h
0x180012d18  pop     rbx
0x180012d19  retn
0x180012d1a  mov     ebx, 0C000000Dh
0x180012d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d26  lea     rax, WPP_GLOBAL_Control
0x180012d2d  cmp     rcx, rax
0x180012d30  jz      short loc_180012D12
0x180012d32  test    byte ptr [rcx+1Ch], 1
0x180012d36  jz      short loc_180012D12
0x180012d38  mov     rcx, [rcx+10h]
0x180012d3c  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012d43  mov     [rsp+48h+var_18], 5Bh ; '['
0x180012d4b  lea     r9, aStatus; "Status"
0x180012d52  mov     [rsp+48h+var_20], rax
0x180012d57  mov     [rsp+48h+var_28], 0C000000Dh
0x180012d5f  call    WPP_SF_sDsd
0x180012d64  jmp     short loc_180012D12
```
