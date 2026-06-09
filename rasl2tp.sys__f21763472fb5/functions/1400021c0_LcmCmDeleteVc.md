# LcmCmDeleteVc

- ea: `0x1400021c0`
- end: `0x1400022d7`
- name: `LcmCmDeleteVc`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000f2ec`
- `0x140011518`

## callees

- `0x1400013f0`
- `0x140001850`
- `0x140001920`
- `0x1400021c0`
- `0x1400031ec`
- `0x14000328c`

## pseudocode

```c
__int64 __fastcall LcmCmDeleteVc(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 16) == 861155916 )
  {
    if ( (*(_DWORD *)(a1 + 60) & 0x10000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, a1);
      }
      return 3221225473LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdd(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
          a1,
          *(unsigned __int16 *)(a1 + 56),
          *(unsigned __int16 *)(a1 + 58));
      }
      SetFlags(a1 + 60, 0x10000);
      DereferenceAf(*(_QWORD *)(a1 + 24));
      DereferenceVc(a1);
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, a1);
    }
    return 3221291029LL;
  }
}

```

## disassembly

```asm
0x1400021c0  mov     [rsp+arg_0], rbx
0x1400021c5  push    rdi
0x1400021c6  sub     rsp, 30h
0x1400021ca  cmp     dword ptr [rcx+10h], 3354324Ch
0x1400021d1  mov     rbx, rcx
0x1400021d4  jz      short loc_140002218
0x1400021d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021dd  lea     rax, WPP_GLOBAL_Control
0x1400021e4  cmp     rcx, rax
0x1400021e7  jz      short loc_14000220E
0x1400021e9  mov     eax, [rcx+2Ch]
0x1400021ec  test    al, 4
0x1400021ee  jz      short loc_14000220E
0x1400021f0  cmp     byte ptr [rcx+29h], 1
0x1400021f4  jb      short loc_14000220E
0x1400021f6  mov     rcx, [rcx+18h]
0x1400021fa  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002201  mov     edx, 13h
0x140002206  mov     r9, rbx
0x140002209  call    WPP_SF_q
0x14000220e  mov     eax, 0C0010015h
0x140002213  jmp     loc_1400022CB
0x140002218  test    dword ptr [rcx+3Ch], 10000h
0x14000221f  jz      short loc_140002260
0x140002221  mov     rcx, cs:WPP_GLOBAL_Control
0x140002228  lea     rax, WPP_GLOBAL_Control
0x14000222f  cmp     rcx, rax
0x140002232  jz      short loc_140002259
0x140002234  mov     eax, [rcx+2Ch]
0x140002237  test    al, 4
0x140002239  jz      short loc_140002259
0x14000223b  cmp     byte ptr [rcx+29h], 1
0x14000223f  jb      short loc_140002259
0x140002241  mov     rcx, [rcx+18h]
0x140002245  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14000224c  mov     edx, 14h
0x140002251  mov     r9, rbx
0x140002254  call    WPP_SF_q
0x140002259  mov     eax, 0C0000001h
0x14000225e  jmp     short loc_1400022CB
0x140002260  mov     rcx, cs:WPP_GLOBAL_Control
0x140002267  lea     rax, WPP_GLOBAL_Control
0x14000226e  cmp     rcx, rax
0x140002271  jz      short loc_1400022AA
0x140002273  mov     eax, [rcx+2Ch]
0x140002276  test    al, 4
0x140002278  jz      short loc_1400022AA
0x14000227a  cmp     byte ptr [rcx+29h], 2
0x14000227e  jb      short loc_1400022AA
0x140002280  movzx   r8d, word ptr [rbx+38h]
0x140002285  mov     edx, 15h
0x14000228a  movzx   eax, word ptr [rbx+3Ah]
0x14000228e  mov     r9, rbx
0x140002291  mov     rcx, [rcx+18h]
0x140002295  mov     [rsp+38h+var_10], eax
0x140002299  mov     [rsp+38h+var_18], r8d
0x14000229e  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x1400022a5  call    WPP_SF_qdd
0x1400022aa  mov     edx, 10000h
0x1400022af  lea     rcx, [rbx+3Ch]
0x1400022b3  call    SetFlags
0x1400022b8  mov     rcx, [rbx+18h]
0x1400022bc  call    DereferenceAf
0x1400022c1  mov     rcx, rbx
0x1400022c4  call    DereferenceVc
0x1400022c9  xor     eax, eax
0x1400022cb  mov     rbx, [rsp+38h+arg_0]
0x1400022d0  add     rsp, 30h
0x1400022d4  pop     rdi
0x1400022d5  retn
```
