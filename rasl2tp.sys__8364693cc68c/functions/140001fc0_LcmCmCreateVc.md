# LcmCmCreateVc

- ea: `0x140001fc0`
- end: `0x1400021b5`
- name: `LcmCmCreateVc`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140011518`

## callees

- `0x140001b70`
- `0x140001fc0`
- `0x140003050`
- `0x1400031ec`
- `0x140004c00`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400020b0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400020c0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400020d3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400020b0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400020c0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400020d3`

## pseudocode

```c
__int64 __fastcall LcmCmCreateVc(__int64 a1, __int64 a2, _QWORD *a3)
{
  char *v7; // rax
  char *v8; // rbx
  int v9; // eax

  if ( *(_DWORD *)a1 != 827601484 )
    return 3221291029LL;
  v7 = (char *)ALLOC_NONPAGED(488, 861155916);
  v8 = v7;
  if ( v7 )
  {
    memset(v7, 0, 0x1E8u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, v8);
    }
    *((_QWORD *)v8 + 1) = v8;
    *(_QWORD *)v8 = v8;
    *((_QWORD *)v8 + 13) = v8 + 96;
    *((_QWORD *)v8 + 12) = v8 + 96;
    *((_QWORD *)v8 + 15) = v8 + 112;
    *((_QWORD *)v8 + 14) = v8 + 112;
    *((_DWORD *)v8 + 4) = 861155916;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    *((_QWORD *)v8 + 3) = a1;
    KeInitializeSpinLock((PKSPIN_LOCK)v8 + 5);
    KeInitializeSpinLock((PKSPIN_LOCK)v8 + 9);
    KeInitializeSpinLock((PKSPIN_LOCK)v8 + 58);
    *((_QWORD *)v8 + 30) = v8 + 232;
    *((_QWORD *)v8 + 29) = v8 + 232;
    *((_QWORD *)v8 + 37) = v8 + 288;
    *((_QWORD *)v8 + 36) = v8 + 288;
    *((_QWORD *)v8 + 56) = v8 + 440;
    *((_QWORD *)v8 + 55) = v8 + 440;
    *((_DWORD *)v8 + 65) = 500;
    *((_DWORD *)v8 + 67) = 500;
    v8[456] = 0;
    *((_QWORD *)v8 + 38) = a2;
    *(_OWORD *)(v8 + 312) = 0;
    *(_OWORD *)(v8 + 328) = 0;
    *((_DWORD *)v8 + 78) = *(_DWORD *)(a1 + 360);
    *((_DWORD *)v8 + 79) = *(_DWORD *)(a1 + 360);
    *((_DWORD *)v8 + 80) = *(_DWORD *)(a1 + 368);
    *((_DWORD *)v8 + 81) = *(_DWORD *)(a1 + 368);
    *((_DWORD *)v8 + 84) = *(_DWORD *)(a1 + 372);
    *((_DWORD *)v8 + 85) = *(_DWORD *)(a1 + 372);
    v9 = *(_DWORD *)(a1 + 364) >> 1;
    *((_DWORD *)v8 + 62) = v9;
    if ( !v9 )
      *((_DWORD *)v8 + 62) = 1;
    *a3 = v8;
    _InterlockedIncrement((volatile signed __int32 *)v8 + 5);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 376));
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140001fc0  push    rbx
0x140001fc2  push    rbp
0x140001fc3  push    rsi
0x140001fc4  push    rdi
0x140001fc5  sub     rsp, 28h
0x140001fc9  cmp     dword ptr [rcx], 3154324Ch
0x140001fcf  mov     rsi, r8
0x140001fd2  mov     rbp, rdx
0x140001fd5  mov     rdi, rcx
0x140001fd8  jz      short loc_140001FE4
0x140001fda  mov     eax, 0C0010015h
0x140001fdf  jmp     loc_1400021AB
0x140001fe4  mov     edx, 3354324Ch
0x140001fe9  mov     ecx, 1E8h
0x140001fee  call    ALLOC_NONPAGED
0x140001ff3  mov     rbx, rax
0x140001ff6  test    rax, rax
0x140001ff9  jnz     short loc_140002038
0x140001ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140002002  lea     rax, WPP_GLOBAL_Control
0x140002009  cmp     rcx, rax
0x14000200c  jz      short loc_14000202E
0x14000200e  mov     eax, [rcx+2Ch]
0x140002011  test    al, 1
0x140002013  jz      short loc_14000202E
0x140002015  cmp     byte ptr [rcx+29h], 1
0x140002019  jb      short loc_14000202E
0x14000201b  mov     rcx, [rcx+18h]
0x14000201f  lea     edx, [rbx+11h]
0x140002022  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002029  call    WPP_SF_
0x14000202e  mov     eax, 0C000009Ah
0x140002033  jmp     loc_1400021AB
0x140002038  xor     edx, edx; Val
0x14000203a  mov     r8d, 1E8h; Size
0x140002040  mov     rcx, rbx; void *
0x140002043  call    memset
0x140002048  mov     rcx, cs:WPP_GLOBAL_Control
0x14000204f  lea     rax, WPP_GLOBAL_Control
0x140002056  cmp     rcx, rax
0x140002059  jz      short loc_140002080
0x14000205b  mov     eax, [rcx+2Ch]
0x14000205e  test    al, 4
0x140002060  jz      short loc_140002080
0x140002062  cmp     byte ptr [rcx+29h], 2
0x140002066  jb      short loc_140002080
0x140002068  mov     rcx, [rcx+18h]
0x14000206c  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002073  mov     edx, 12h
0x140002078  mov     r9, rbx
0x14000207b  call    WPP_SF_q
0x140002080  mov     [rbx+8], rbx
0x140002084  lea     rax, [rbx+60h]
0x140002088  mov     [rbx], rbx
0x14000208b  mov     [rax+8], rax
0x14000208f  mov     [rax], rax
0x140002092  lea     rax, [rbx+70h]
0x140002096  mov     [rax+8], rax
0x14000209a  mov     [rax], rax
0x14000209d  mov     dword ptr [rbx+10h], 3354324Ch
0x1400020a4  lock inc dword ptr [rdi+4]
0x1400020a8  lea     rcx, [rbx+28h]; SpinLock
0x1400020ac  mov     [rbx+18h], rdi
0x1400020b0  call    cs:__imp_KeInitializeSpinLock
0x1400020b7  nop     dword ptr [rax+rax+00h]
0x1400020bc  lea     rcx, [rbx+48h]; SpinLock
0x1400020c0  call    cs:__imp_KeInitializeSpinLock
0x1400020c7  nop     dword ptr [rax+rax+00h]
0x1400020cc  lea     rcx, [rbx+1D0h]; SpinLock
0x1400020d3  call    cs:__imp_KeInitializeSpinLock
0x1400020da  nop     dword ptr [rax+rax+00h]
0x1400020df  lea     rax, [rbx+0E8h]
0x1400020e6  xorps   xmm0, xmm0
0x1400020e9  mov     [rax+8], rax
0x1400020ed  mov     [rax], rax
0x1400020f0  lea     rax, [rbx+120h]
0x1400020f7  mov     [rax+8], rax
0x1400020fb  mov     [rax], rax
0x1400020fe  lea     rax, [rbx+1B8h]
0x140002105  mov     [rax+8], rax
0x140002109  mov     [rax], rax
0x14000210c  mov     eax, 1F4h
0x140002111  mov     [rbx+104h], eax
0x140002117  mov     [rbx+10Ch], eax
0x14000211d  mov     byte ptr [rbx+1C8h], 0
0x140002124  mov     [rbx+130h], rbp
0x14000212b  movups  xmmword ptr [rbx+138h], xmm0
0x140002132  movups  xmmword ptr [rbx+148h], xmm0
0x140002139  mov     eax, [rdi+168h]
0x14000213f  mov     [rbx+138h], eax
0x140002145  mov     eax, [rdi+168h]
0x14000214b  mov     [rbx+13Ch], eax
0x140002151  mov     eax, [rdi+170h]
0x140002157  mov     [rbx+140h], eax
0x14000215d  mov     eax, [rdi+170h]
0x140002163  mov     [rbx+144h], eax
0x140002169  mov     eax, [rdi+174h]
0x14000216f  mov     [rbx+150h], eax
0x140002175  mov     eax, [rdi+174h]
0x14000217b  mov     [rbx+154h], eax
0x140002181  mov     eax, [rdi+16Ch]
0x140002187  shr     eax, 1
0x140002189  mov     [rbx+0F8h], eax
0x14000218f  jnz     short loc_14000219B
0x140002191  mov     dword ptr [rbx+0F8h], 1
0x14000219b  mov     [rsi], rbx
0x14000219e  lock inc dword ptr [rbx+14h]
0x1400021a2  lock inc dword ptr [rdi+178h]
0x1400021a9  xor     eax, eax
0x1400021ab  add     rsp, 28h
0x1400021af  pop     rdi
0x1400021b0  pop     rsi
0x1400021b1  pop     rbp
0x1400021b2  pop     rbx
0x1400021b3  retn
```
