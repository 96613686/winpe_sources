# StdEncoderOutputBlock

- ea: `0x1800026e0`
- end: `0x1800028d0`
- name: `StdEncoderOutputBlock`
- size: `496`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001c40`
- `0x18000689c`

## callees

- `0x1800026e0`
- `0x180003a60`
- `0x180004760`
- `0x180004c30`
- `0x180005a94`
- `0x180006ad5`

## pseudocode

```c
__int64 __fastcall StdEncoderOutputBlock(__int64 a1)
{
  __int64 v2; // rsi
  bool v3; // zf
  __int64 v4; // r15
  __int64 v5; // r12
  _WORD *v6; // r14
  __int64 v7; // rbp
  __int64 result; // rax
  __int64 v9; // rax

  v2 = *(_QWORD *)(a1 + 80);
  if ( *(_DWORD *)a1 )
  {
    v7 = v2 + 195264;
    v6 = (_WORD *)(v2 + 193248);
    v5 = v2 + 181792;
    v4 = v2 + 192384;
  }
  else
  {
    v3 = *(_DWORD *)(a1 + 28) == 0;
    *(_DWORD *)(a1 + 24) = 0;
    if ( v3 )
      return 1;
    v4 = v2 + 192384;
    makeTable(288, 12, v2 + 192384, v2 + 181888, v2 + 190080, v2 + 191232);
    v5 = v2 + 181792;
    makeTable(32, 8, v2 + 181792, v2 + 181024, v2 + 181536, v2 + 181664);
    v6 = (_WORD *)(v2 + 193248);
    makeTree(288, 15, (_WORD *)(v2 + 193248), (_WORD *)(v2 + 194400), v2 + 194976);
    v7 = v2 + 195264;
    makeTree(32, 15, (_WORD *)(v2 + 195264), (_WORD *)(v2 + 195392), v2 + 195456);
  }
  result = StdEncoderOutputDynamicBlock(a1);
  if ( !(_DWORD)result )
    return result;
  if ( !*(_DWORD *)a1 )
  {
    v9 = *(_QWORD *)(a1 + 80) + 148234LL;
    *(_QWORD *)(v2 + 181004) = 0;
    *(_QWORD *)(v2 + 181016) = v9;
    *(_DWORD *)(a1 + 28) = 0;
    NormaliseFrequencies(v6, v7);
    makeTree(32, 9, (_WORD *)v7, (_WORD *)(v2 + 181824), v5);
    makeTree(288, 13, v6, (_WORD *)(v2 + 192672), v4);
    memset_0(v6, 0, 0x480u);
    *(_OWORD *)v7 = 0;
    *(_OWORD *)(v7 + 16) = 0;
    *(_OWORD *)(v7 + 32) = 0;
    *(_OWORD *)(v7 + 48) = 0;
    *(_OWORD *)(v7 + 64) = 0;
    *(_OWORD *)(v7 + 80) = 0;
    *(_OWORD *)(v7 + 96) = 0;
    *(_OWORD *)(v7 + 112) = 0;
    *(_WORD *)(v2 + 193760) = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x1800026e0  push    rbx
0x1800026e2  push    rbp
0x1800026e3  push    rsi
0x1800026e4  push    rdi
0x1800026e5  push    r12
0x1800026e7  push    r13
0x1800026e9  push    r14
0x1800026eb  push    r15
0x1800026ed  sub     rsp, 38h
0x1800026f1  cmp     dword ptr [rcx], 0
0x1800026f4  mov     rbx, rcx
0x1800026f7  mov     rsi, [rcx+50h]
0x1800026fb  mov     r13d, 1
0x180002701  jnz     loc_1800027E2
0x180002707  cmp     dword ptr [rcx+1Ch], 0
0x18000270b  mov     dword ptr [rcx+18h], 0
0x180002712  jz      loc_1800028BC
0x180002718  lea     rcx, [rsi+2E680h]
0x18000271f  mov     edx, 0Ch
0x180002724  lea     rax, [rsi+2EB00h]
0x18000272b  mov     [rsp+78h+var_50], rax
0x180002730  lea     r15, [rsi+2EF80h]
0x180002737  mov     [rsp+78h+var_58], rcx
0x18000273c  lea     r9, [rsi+2C680h]
0x180002743  mov     ecx, 120h
0x180002748  mov     r8, r15
0x18000274b  call    makeTable
0x180002750  lea     rcx, [rsi+2C520h]
0x180002757  mov     edx, 8
0x18000275c  lea     rax, [rsi+2C5A0h]
0x180002763  mov     [rsp+78h+var_50], rax
0x180002768  lea     r12, [rsi+2C620h]
0x18000276f  mov     [rsp+78h+var_58], rcx
0x180002774  lea     r9, [rsi+2C320h]
0x18000277b  mov     ecx, 20h ; ' '
0x180002780  mov     r8, r12
0x180002783  call    makeTable
0x180002788  lea     rax, [rsi+2F9A0h]
0x18000278f  mov     edx, 0Fh
0x180002794  lea     r14, [rsi+2F2E0h]
0x18000279b  mov     [rsp+78h+var_58], rax
0x1800027a0  mov     r8, r14
0x1800027a3  lea     r9, [rsi+2F760h]
0x1800027aa  mov     ecx, 120h
0x1800027af  call    makeTree
0x1800027b4  lea     rax, [rsi+2FB80h]
0x1800027bb  mov     edx, 0Fh
0x1800027c0  lea     rbp, [rsi+2FAC0h]
0x1800027c7  mov     [rsp+78h+var_58], rax
0x1800027cc  mov     r8, rbp
0x1800027cf  lea     r9, [rsi+2FB40h]
0x1800027d6  mov     ecx, 20h ; ' '
0x1800027db  call    makeTree
0x1800027e0  jmp     short loc_1800027FE
0x1800027e2  lea     rbp, [rsi+2FAC0h]
0x1800027e9  lea     r14, [rsi+2F2E0h]
0x1800027f0  lea     r12, [rsi+2C620h]
0x1800027f7  lea     r15, [rsi+2EF80h]
0x1800027fe  mov     rcx, rbx
0x180002801  call    StdEncoderOutputDynamicBlock
0x180002806  test    eax, eax
0x180002808  jz      loc_1800028BF
0x18000280e  cmp     dword ptr [rbx], 0
0x180002811  jnz     loc_1800028BC
0x180002817  mov     rax, [rbx+50h]
0x18000281b  mov     rdx, rbp
0x18000281e  add     rax, 2430Ah
0x180002824  mov     qword ptr [rsi+2C30Ch], 0
0x18000282f  mov     [rsi+2C318h], rax
0x180002836  mov     rcx, r14
0x180002839  mov     dword ptr [rbx+1Ch], 0
0x180002840  call    NormaliseFrequencies
0x180002845  lea     r9, [rsi+2C640h]
0x18000284c  mov     [rsp+78h+var_58], r12
0x180002851  mov     r8, rbp
0x180002854  mov     edx, 9
0x180002859  mov     ecx, 20h ; ' '
0x18000285e  call    makeTree
0x180002863  lea     r9, [rsi+2F0A0h]
0x18000286a  mov     [rsp+78h+var_58], r15
0x18000286f  mov     r8, r14
0x180002872  mov     edx, 0Dh
0x180002877  mov     ecx, 120h
0x18000287c  call    makeTree
0x180002881  xor     edx, edx; Val
0x180002883  mov     r8d, 480h; Size
0x180002889  mov     rcx, r14; void *
0x18000288c  call    memset_0
0x180002891  xorps   xmm0, xmm0
0x180002894  movups  xmmword ptr [rbp+0], xmm0
0x180002898  movups  xmmword ptr [rbp+10h], xmm0
0x18000289c  movups  xmmword ptr [rbp+20h], xmm0
0x1800028a0  movups  xmmword ptr [rbp+30h], xmm0
0x1800028a4  movups  xmmword ptr [rbp+40h], xmm0
0x1800028a8  movups  xmmword ptr [rbp+50h], xmm0
0x1800028ac  movups  xmmword ptr [rbp+60h], xmm0
0x1800028b0  movups  xmmword ptr [rbp+70h], xmm0
0x1800028b4  mov     [rsi+2F4E0h], r13w
0x1800028bc  mov     eax, r13d
0x1800028bf  add     rsp, 38h
0x1800028c3  pop     r15
0x1800028c5  pop     r14
0x1800028c7  pop     r13
0x1800028c9  pop     r12
0x1800028cb  pop     rdi
0x1800028cc  pop     rsi
0x1800028cd  pop     rbp
0x1800028ce  pop     rbx
0x1800028cf  retn
```
