# SetTimer

- ea: `0x14000fa20`
- end: `0x14000fa8f`
- name: `SetTimer`
- size: `111`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f698`
- `0x14000f930`
- `0x1400181a8`

## callees

- `0x14000fa20`

## import_xrefs

- `NDIS!NdisSetTimer` at `0x14000fa7d`
- `NDIS!NdisSetTimer` at `0x14000fa7d`

## pseudocode

```c
void __fastcall SetTimer(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  UINT v6; // edx
  __int64 v7; // rcx

  v2 = a1 + 8;
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 != v2 && !*(_BYTE *)(a1 + 40) )
  {
    if ( !a2 )
      a2 = MEMORY[0xFFFFF78000000014];
    v5 = (unsigned __int128)((*(_QWORD *)(v4 + 16) - a2) * (__int128)0x346DC5D63886594BLL) >> 64;
    v6 = 0;
    v7 = ((unsigned __int64)v5 >> 63) + (v5 >> 11);
    if ( v7 > 0 )
      v6 = v7;
    NdisSetTimer((PNDIS_TIMER)(a1 + 64), v6);
  }
}

```

## disassembly

```asm
0x14000fa20  sub     rsp, 28h
0x14000fa24  lea     rax, [rcx+8]
0x14000fa28  mov     r8, rcx
0x14000fa2b  mov     rcx, [rax]
0x14000fa2e  cmp     rcx, rax
0x14000fa31  jz      short loc_14000FA89
0x14000fa33  cmp     byte ptr [r8+28h], 0
0x14000fa38  jnz     short loc_14000FA89
0x14000fa3a  test    rdx, rdx
0x14000fa3d  jnz     short loc_14000FA4C
0x14000fa3f  mov     rdx, 0FFFFF78000000014h
0x14000fa49  mov     rdx, [rdx]
0x14000fa4c  mov     rcx, [rcx+10h]
0x14000fa50  mov     rax, 346DC5D63886594Bh
0x14000fa5a  sub     rcx, rdx
0x14000fa5d  imul    rcx
0x14000fa60  mov     rcx, rdx
0x14000fa63  xor     edx, edx
0x14000fa65  sar     rcx, 0Bh
0x14000fa69  mov     rax, rcx
0x14000fa6c  shr     rax, 3Fh
0x14000fa70  add     rcx, rax
0x14000fa73  test    rcx, rcx
0x14000fa76  cmovg   edx, ecx; MillisecondsToDelay
0x14000fa79  lea     rcx, [r8+40h]; Timer
0x14000fa7d  call    cs:__imp_NdisSetTimer
0x14000fa84  nop     dword ptr [rax+rax+00h]
0x14000fa89  add     rsp, 28h
0x14000fa8d  retn
```
