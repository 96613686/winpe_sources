# MRxSmbConstructDeferredOpenContext

- ea: `0x14004a2f0`
- end: `0x14004a49b`
- name: `MRxSmbConstructDeferredOpenContext`
- size: `427`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14003b3a4`
- `0x140049870`
- `0x1400499e0`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x1400166c0`
- `0x14004a2f0`
- `0x140051880`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004a36d`
- `ntoskrnl!ExAllocatePool2` at `0x14004a36d`

## pseudocode

```c
__int64 __fastcall MRxSmbConstructDeferredOpenContext(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // r15
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdx
  __int64 Pool2; // rax
  __int64 v7; // rsi
  unsigned int v8; // r14d

  v1 = *(_QWORD *)(a1 + 72);
  v3 = 0;
  if ( v1 )
    v3 = *(_QWORD *)(v1 + 48);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  v4 = *(unsigned __int16 **)(a1 + 568);
  v5 = 104;
  if ( v4 )
    v5 = v4[1] + 196LL;
  Pool2 = ExAllocatePool2(66, v5, 1329884499);
  v7 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(v3 + 16) = Pool2;
    v8 = 0;
    *(_OWORD *)Pool2 = *(_OWORD *)(a1 + 512);
    *(_OWORD *)(Pool2 + 16) = *(_OWORD *)(a1 + 528);
    *(_OWORD *)(Pool2 + 32) = *(_OWORD *)(a1 + 544);
    *(_OWORD *)(Pool2 + 48) = *(_OWORD *)(a1 + 560);
    *(_OWORD *)(Pool2 + 64) = *(_OWORD *)(a1 + 576);
    *(_QWORD *)(Pool2 + 80) = *(_QWORD *)(a1 + 592);
    *(_WORD *)(Pool2 + 100) = *(_WORD *)(a1 + 746);
    *(_DWORD *)(Pool2 + 88) = *(_DWORD *)(a1 + 120);
    *(_QWORD *)(Pool2 + 32) = 0;
    MRxSmbAdjustCreateParameters(a1, Pool2 + 92);
    *(_DWORD *)(v1 + 72) |= 0x100000u;
    if ( v4 )
    {
      *(_QWORD *)(v7 + 56) = v7 + 104;
      *(_OWORD *)(v7 + 104) = *(_OWORD *)v4;
      *(_OWORD *)(v7 + 120) = *((_OWORD *)v4 + 1);
      *(_OWORD *)(v7 + 136) = *((_OWORD *)v4 + 2);
      *(_OWORD *)(v7 + 152) = *((_OWORD *)v4 + 3);
      *(_OWORD *)(v7 + 168) = *((_OWORD *)v4 + 4);
      *(_QWORD *)(v7 + 184) = *((_QWORD *)v4 + 10);
      if ( *v4 )
      {
        *(_QWORD *)(v7 + 112) = v7 + 192;
        memmove((void *)(v7 + 192), *((const void **)v4 + 1), *v4);
      }
    }
  }
  else
  {
    v8 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x14004a2f0  push    rbx
0x14004a2f2  push    rbp
0x14004a2f3  push    rsi
0x14004a2f4  push    rdi
0x14004a2f5  push    r12
0x14004a2f7  push    r14
0x14004a2f9  push    r15
0x14004a2fb  sub     rsp, 20h
0x14004a2ff  mov     rbp, [rcx+48h]
0x14004a303  xor     r12d, r12d
0x14004a306  mov     rdi, rcx
0x14004a309  mov     r15d, r12d
0x14004a30c  test    rbp, rbp
0x14004a30f  jz      short loc_14004A315
0x14004a311  mov     r15, [rbp+30h]
0x14004a315  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a31c  lea     rax, WPP_GLOBAL_Control
0x14004a323  cmp     rcx, rax
0x14004a326  jz      short loc_14004A346
0x14004a328  test    dword ptr [rcx+2Ch], 400h
0x14004a32f  jz      short loc_14004A346
0x14004a331  mov     rcx, [rcx+18h]
0x14004a335  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14004a33c  mov     edx, 1Dh
0x14004a341  call    WPP_SF_
0x14004a346  mov     rbx, [rdi+238h]
0x14004a34d  mov     edx, 68h ; 'h'
0x14004a352  test    rbx, rbx
0x14004a355  jz      short loc_14004A362
0x14004a357  movzx   edx, word ptr [rbx+2]
0x14004a35b  add     rdx, 0C4h
0x14004a362  mov     ecx, 42h ; 'B'
0x14004a367  mov     r8d, 4F446D53h
0x14004a36d  call    cs:__imp_ExAllocatePool2
0x14004a374  nop     dword ptr [rax+rax+00h]
0x14004a379  mov     rsi, rax
0x14004a37c  test    rax, rax
0x14004a37f  jnz     short loc_14004A38C
0x14004a381  mov     r14d, 0C000009Ah
0x14004a387  jmp     loc_14004A454
0x14004a38c  mov     [r15+10h], rsi
0x14004a390  lea     rdx, [rsi+5Ch]
0x14004a394  movups  xmm0, xmmword ptr [rdi+200h]
0x14004a39b  mov     rcx, rdi
0x14004a39e  mov     r14d, r12d
0x14004a3a1  movups  xmmword ptr [rax], xmm0
0x14004a3a4  movups  xmm1, xmmword ptr [rdi+210h]
0x14004a3ab  movups  xmmword ptr [rax+10h], xmm1
0x14004a3af  movups  xmm0, xmmword ptr [rdi+220h]
0x14004a3b6  movups  xmmword ptr [rax+20h], xmm0
0x14004a3ba  movups  xmm1, xmmword ptr [rdi+230h]
0x14004a3c1  movups  xmmword ptr [rax+30h], xmm1
0x14004a3c5  movups  xmm0, xmmword ptr [rdi+240h]
0x14004a3cc  movups  xmmword ptr [rax+40h], xmm0
0x14004a3d0  movsd   xmm1, qword ptr [rdi+250h]
0x14004a3d8  movsd   qword ptr [rax+50h], xmm1
0x14004a3dd  movzx   eax, word ptr [rdi+2EAh]
0x14004a3e4  mov     [rsi+64h], ax
0x14004a3e8  mov     eax, [rdi+78h]
0x14004a3eb  mov     [rsi+58h], eax
0x14004a3ee  mov     [rsi+20h], r12
0x14004a3f2  call    MRxSmbAdjustCreateParameters
0x14004a3f7  bts     dword ptr [rbp+48h], 14h
0x14004a3fc  test    rbx, rbx
0x14004a3ff  jz      short loc_14004A454
0x14004a401  lea     rax, [rsi+68h]
0x14004a405  mov     [rsi+38h], rax
0x14004a409  movups  xmm0, xmmword ptr [rbx]
0x14004a40c  movups  xmmword ptr [rax], xmm0
0x14004a40f  movups  xmm1, xmmword ptr [rbx+10h]
0x14004a413  movups  xmmword ptr [rax+10h], xmm1
0x14004a417  movups  xmm0, xmmword ptr [rbx+20h]
0x14004a41b  movups  xmmword ptr [rax+20h], xmm0
0x14004a41f  movups  xmm1, xmmword ptr [rbx+30h]
0x14004a423  movups  xmmword ptr [rax+30h], xmm1
0x14004a427  movups  xmm0, xmmword ptr [rbx+40h]
0x14004a42b  movups  xmmword ptr [rax+40h], xmm0
0x14004a42f  movsd   xmm1, qword ptr [rbx+50h]
0x14004a434  movsd   qword ptr [rax+50h], xmm1
0x14004a439  cmp     [rbx], r12w
0x14004a43d  jz      short loc_14004A454
0x14004a43f  lea     rcx, [rax+58h]; void *
0x14004a443  mov     [rax+8], rcx
0x14004a447  movzx   r8d, word ptr [rbx]; Size
0x14004a44b  mov     rdx, [rbx+8]; Src
0x14004a44f  call    memmove
0x14004a454  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a45b  lea     rax, WPP_GLOBAL_Control
0x14004a462  cmp     rcx, rax
0x14004a465  jz      short loc_14004A488
0x14004a467  test    dword ptr [rcx+2Ch], 400h
0x14004a46e  jz      short loc_14004A488
0x14004a470  mov     rcx, [rcx+18h]
0x14004a474  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14004a47b  mov     edx, 1Eh
0x14004a480  mov     r9d, r14d
0x14004a483  call    WPP_SF_d
0x14004a488  mov     eax, r14d
0x14004a48b  add     rsp, 20h
0x14004a48f  pop     r15
0x14004a491  pop     r14
0x14004a493  pop     r12
0x14004a495  pop     rdi
0x14004a496  pop     rsi
0x14004a497  pop     rbp
0x14004a498  pop     rbx
0x14004a499  retn
```
