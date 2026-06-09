# NCryptStreamOpenToUnprotect

- ea: `0x180002400`
- end: `0x180002547`
- name: `NCryptStreamOpenToUnprotect`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002400`
- `0x180002550`
- `0x18000d02c`
- `0x18000e120`
- `0x180016128`

## string_xrefs

- `0x180002445`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x18000249c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180002506`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall NCryptStreamOpenToUnprotect(_OWORD *a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // rdi
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rax
  __int64 v12; // [rsp+88h] [rbp+20h] BYREF

  v5 = 0;
  v12 = 0;
  if ( a4 && a1 && *(_QWORD *)a1 )
  {
    if ( (a2 & 0xDFFEFF3F) != 0 )
    {
      v7 = -2146893815;
      DebugTraceError(
        2148073481LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        429);
      return v7;
    }
    v7 = I_StreamOpenToUnprotect(a2, a3, &v12);
    if ( !v7 )
    {
      v10 = v12;
      v7 = 0;
      *(_OWORD *)(v12 + 16) = *a1;
      *(_DWORD *)(v10 + 32) = 0;
      *a4 = v10;
      return v7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v9,
        (unsigned int)"Status",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        180);
    v5 = v12;
  }
  else
  {
    v7 = -2146893785;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
      166);
  }
  if ( v5 )
    I_StreamFree(v5);
  return v7;
}

```

## disassembly

```asm
0x180002400  mov     r11, rsp
0x180002403  push    rbx
0x180002404  push    rsi
0x180002405  push    rdi
0x180002406  push    r14
0x180002408  sub     rsp, 48h
0x18000240c  mov     r14, r9
0x18000240f  xor     edi, edi
0x180002411  mov     [r11+20h], rdi
0x180002415  mov     r9, r8
0x180002418  mov     eax, edx
0x18000241a  mov     rsi, rcx
0x18000241d  test    r14, r14
0x180002420  jz      loc_1800024E4
0x180002426  test    rcx, rcx
0x180002429  jz      loc_1800024E4
0x18000242f  cmp     [rcx], rdi
0x180002432  jz      loc_1800024E4
0x180002438  test    eax, 0DFFEFF3Fh
0x18000243d  jz      short loc_180002467
0x18000243f  mov     r9d, 1ADh
0x180002445  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000244c  lea     rdx, aStatus; "Status"
0x180002453  mov     ecx, 80090009h
0x180002458  mov     ebx, 80090009h
0x18000245d  call    DebugTraceError
0x180002462  jmp     loc_18000253B
0x180002467  lea     r8, [rsp+68h+arg_18]
0x18000246f  mov     rdx, r9
0x180002472  mov     ecx, eax
0x180002474  call    I_StreamOpenToUnprotect
0x180002479  mov     ebx, eax
0x18000247b  test    eax, eax
0x18000247d  jz      short loc_1800024CA
0x18000247f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002486  lea     rax, WPP_GLOBAL_Control
0x18000248d  cmp     rcx, rax
0x180002490  jz      short loc_1800024C0
0x180002492  test    byte ptr [rcx+1Ch], 1
0x180002496  jz      short loc_1800024C0
0x180002498  mov     rcx, [rcx+10h]
0x18000249c  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024a3  mov     [rsp+68h+var_38], 1B4h
0x1800024ab  lea     r9, aStatus; "Status"
0x1800024b2  mov     [rsp+68h+var_40], rax
0x1800024b7  mov     [rsp+68h+var_48], ebx
0x1800024bb  call    WPP_SF_sDsd
0x1800024c0  mov     rdi, [rsp+68h+arg_18]
0x1800024c8  jmp     short loc_18000252E
0x1800024ca  mov     rax, [rsp+68h+arg_18]
0x1800024d2  xor     ebx, ebx
0x1800024d4  movups  xmm0, xmmword ptr [rsi]
0x1800024d7  movdqu  xmmword ptr [rax+10h], xmm0
0x1800024dc  mov     [rax+20h], edi
0x1800024df  mov     [r14], rax
0x1800024e2  jmp     short loc_18000253B
0x1800024e4  mov     ebx, 80090027h
0x1800024e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024f0  lea     rax, WPP_GLOBAL_Control
0x1800024f7  cmp     rcx, rax
0x1800024fa  jz      short loc_18000253B
0x1800024fc  test    byte ptr [rcx+1Ch], 1
0x180002500  jz      short loc_18000253B
0x180002502  mov     rcx, [rcx+10h]
0x180002506  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000250d  mov     [rsp+68h+var_38], 1A6h
0x180002515  lea     r9, aStatus; "Status"
0x18000251c  mov     [rsp+68h+var_40], rax
0x180002521  mov     [rsp+68h+var_48], 80090027h
0x180002529  call    WPP_SF_sDsd
0x18000252e  test    rdi, rdi
0x180002531  jz      short loc_18000253B
0x180002533  mov     rcx, rdi
0x180002536  call    I_StreamFree
0x18000253b  mov     eax, ebx
0x18000253d  add     rsp, 48h
0x180002541  pop     r14
0x180002543  pop     rdi
0x180002544  pop     rsi
0x180002545  pop     rbx
0x180002546  retn
```
