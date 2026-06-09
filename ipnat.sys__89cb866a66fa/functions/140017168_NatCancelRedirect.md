# NatCancelRedirect

- ea: `0x140017168`
- end: `0x14001770f`
- name: `NatCancelRedirect`
- size: `1447`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000e378`
- `0x14000f134`
- `0x140017168`
- `0x140019cec`
- `0x14001c2e0`

## import_xrefs

- `ntoskrnl!IoSetIoCompletion` at `0x140017640`
- `ntoskrnl!IoSetIoCompletion` at `0x140017640`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017247`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001742d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017247`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001742d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400172bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017394`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017615`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400176d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400172bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017394`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017615`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400176d3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400172a6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001737e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400174d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001754f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400175cf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400175f2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400176bd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400172a6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001737e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400174d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001754f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400175cf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400175f2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400176bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017231`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017231`

## pseudocode

```c
__int64 __fastcall NatCancelRedirect(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rdx
  KIRQL v6; // r14
  __int64 v7; // rax
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  _QWORD **v11; // r8
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  __int64 v14; // rdx
  __int64 v16; // rbp
  char *v17; // rsi
  int v18; // eax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdi
  int v25; // [rsp+28h] [rbp-80h]
  unsigned __int64 v26; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v27; // [rsp+58h] [rbp-50h]
  unsigned __int64 v28; // [rsp+60h] [rbp-48h]
  unsigned __int64 v29; // [rsp+68h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  v4 = *(unsigned int *)(a1 + 36);
  v5 = (unsigned __int64)*(unsigned __int8 *)(a1 + 16) << 16;
  v26 = *(unsigned int *)(a1 + 28) | ((v5 | *(unsigned __int16 *)(a1 + 32)) << 32);
  if ( (_DWORD)v4 )
  {
    v28 = *(unsigned int *)(a1 + 20) | ((v5 | *(unsigned __int16 *)(a1 + 24)) << 32);
    v27 = v4 | ((v5 | *(unsigned __int16 *)(a1 + 40)) << 32);
  }
  else
  {
    v28 = 0;
    v27 = 0;
  }
  v29 = *(unsigned int *)(a1 + 44) | ((v5 | *(unsigned __int16 *)(a1 + 48)) << 32);
  v6 = KeAcquireSpinLockRaiseToDpc(&MappingLock);
  KeAcquireSpinLockAtDpcLevel(&RedirectLock);
  v7 = searchRhizome(RedirectRhizome, &v26);
  v8 = -1073741823;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, 3221225473LL);
    }
    KeReleaseSpinLockFromDpcLevel(&RedirectLock);
    KeReleaseSpinLock(&MappingLock, v6);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v8;
    }
    v10 = 12;
    goto LABEL_32;
  }
  v11 = (_QWORD **)(*(_QWORD *)(v7 + 8) + 16LL);
  v12 = *v11;
  if ( *v11 != v11 )
  {
    while ( 1 )
    {
      v13 = v12 - 4;
      if ( (*(_DWORD *)a1 & 1) == 0 || (v14 = v13[16]) == 0 || *(_QWORD *)(v14 + 96) == *(_QWORD *)(a1 + 8) )
      {
        if ( a2 != v13[17] )
        {
          v8 = -1073741790;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids,
              3221225506LL);
          }
          KeReleaseSpinLockFromDpcLevel(&RedirectLock);
          KeReleaseSpinLock(&MappingLock, v6);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
          {
            v10 = 14;
            goto LABEL_32;
          }
          return v8;
        }
        if ( *(_DWORD *)(a1 + 28) == *((_DWORD *)v13 + 56)
          && *(_WORD *)(a1 + 32) == *((_WORD *)v13 + 114)
          && *(_DWORD *)(a1 + 44) == *((_DWORD *)v13 + 58)
          && *(_WORD *)(a1 + 48) == *((_WORD *)v13 + 118) )
        {
          v16 = 0;
          v17 = (char *)v13[19];
          if ( (v13[14] & 0x20) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
            }
            KeAcquireSpinLockAtDpcLevel(&RedirectCompletionLock);
            v18 = *((_DWORD *)v13 + 28);
            if ( (v18 & 0x20000000) != 0 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v20 = 16;
                goto LABEL_67;
              }
              goto LABEL_68;
            }
            if ( (v18 & 0x40000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
              }
              *((_DWORD *)v13 + 28) &= ~0x40000000u;
              v21 = v13 + 2;
              v22 = v13[2];
              if ( *(_QWORD **)(v22 + 8) != v13 + 2 || (v23 = (_QWORD *)v13[3], (_QWORD *)*v23 != v21) )
                __fastfail(3u);
              *v23 = v22;
              *(_QWORD *)(v22 + 8) = v23;
              v13[3] = v13 + 2;
              *v21 = v21;
              KeReleaseSpinLockFromDpcLevel(&RedirectCompletionLock);
              v24 = *(_QWORD **)(v13[17] + 176LL);
              if ( v24 )
              {
                v16 = *(_QWORD *)(v13[16] + 96LL);
                goto LABEL_60;
              }
              goto LABEL_70;
            }
            if ( (v18 & 0x4000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
              }
              KeReleaseSpinLockFromDpcLevel(&RedirectCompletionLock);
              v24 = 0;
LABEL_60:
              if ( v17 )
                NatQueryInformationMapping((_DWORD)v17, 0, 0, 0, 0, 0, 0, 0, (__int64)(v13 + 20));
LABEL_70:
              NatpCleanupRedirect(v13);
              KeReleaseSpinLockFromDpcLevel(&RedirectLock);
              if ( v17 )
                NatDeleteMapping(v17);
              KeReleaseSpinLock(&MappingLock, v6);
              if ( v24 )
              {
                LOBYTE(v25) = 0;
                IoSetIoCompletion(*v24, v24[1], v16, 259, 0, v25);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, 0);
              }
              return 0;
            }
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v20 = 19;
LABEL_67:
              WPP_SF_(v19->AttachedDevice, v20, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
            }
LABEL_68:
            KeReleaseSpinLockFromDpcLevel(&RedirectCompletionLock);
          }
          v24 = 0;
          goto LABEL_70;
        }
      }
      v12 = (_QWORD *)*v12;
      if ( v12 == v11 )
      {
        v8 = -1073741823;
        break;
      }
    }
  }
  KeReleaseSpinLockFromDpcLevel(&RedirectLock);
  KeReleaseSpinLock(&MappingLock, v6);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v10 = 21;
LABEL_32:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140017168  push    rbx
0x14001716a  push    rbp
0x14001716b  push    rsi
0x14001716c  push    rdi
0x14001716d  push    r13
0x14001716f  push    r14
0x140017171  push    r15
0x140017173  sub     rsp, 70h
0x140017177  mov     rsi, rdx
0x14001717a  mov     rdi, rcx
0x14001717d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017184  lea     r13, WPP_GLOBAL_Control
0x14001718b  lea     rbp, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x140017192  cmp     rcx, r13
0x140017195  jz      short loc_1400171B5
0x140017197  mov     eax, [rcx+2Ch]
0x14001719a  test    al, 1
0x14001719c  jz      short loc_1400171B5
0x14001719e  cmp     byte ptr [rcx+29h], 6
0x1400171a2  jb      short loc_1400171B5
0x1400171a4  mov     rcx, [rcx+18h]
0x1400171a8  mov     edx, 0Ah
0x1400171ad  mov     r8, rbp
0x1400171b0  call    WPP_SF_
0x1400171b5  movzx   edx, byte ptr [rdi+10h]
0x1400171b9  xor     r15d, r15d
0x1400171bc  movzx   ecx, word ptr [rdi+20h]
0x1400171c0  mov     eax, [rdi+1Ch]
0x1400171c3  mov     r8d, [rdi+24h]
0x1400171c7  shl     rdx, 10h
0x1400171cb  or      rcx, rdx
0x1400171ce  shl     rcx, 20h
0x1400171d2  or      rcx, rax
0x1400171d5  mov     [rsp+0A8h+var_58], rcx
0x1400171da  test    r8d, r8d
0x1400171dd  jnz     short loc_1400171EB
0x1400171df  mov     [rsp+0A8h+var_48], r15
0x1400171e4  mov     [rsp+0A8h+var_50], r15
0x1400171e9  jmp     short loc_140017214
0x1400171eb  movzx   ecx, word ptr [rdi+18h]
0x1400171ef  mov     eax, [rdi+14h]
0x1400171f2  or      rcx, rdx
0x1400171f5  shl     rcx, 20h
0x1400171f9  or      rcx, rax
0x1400171fc  mov     [rsp+0A8h+var_48], rcx
0x140017201  movzx   ecx, word ptr [rdi+28h]
0x140017205  or      rcx, rdx
0x140017208  shl     rcx, 20h
0x14001720c  or      rcx, r8
0x14001720f  mov     [rsp+0A8h+var_50], rcx
0x140017214  movzx   ecx, word ptr [rdi+30h]
0x140017218  mov     eax, [rdi+2Ch]
0x14001721b  or      rcx, rdx
0x14001721e  shl     rcx, 20h
0x140017222  or      rcx, rax
0x140017225  mov     [rsp+0A8h+var_40], rcx
0x14001722a  lea     rcx, MappingLock; SpinLock
0x140017231  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017238  nop     dword ptr [rax+rax+00h]
0x14001723d  lea     rcx, RedirectLock; SpinLock
0x140017244  mov     r14b, al
0x140017247  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001724e  nop     dword ptr [rax+rax+00h]
0x140017253  lea     rdx, [rsp+0A8h+var_58]
0x140017258  lea     rcx, RedirectRhizome
0x14001725f  call    searchRhizome
0x140017264  mov     ebx, 0C0000001h
0x140017269  test    rax, rax
0x14001726c  jnz     loc_1400172F7
0x140017272  mov     rcx, cs:WPP_GLOBAL_Control
0x140017279  cmp     rcx, r13
0x14001727c  jz      short loc_14001729F
0x14001727e  mov     eax, [rcx+2Ch]
0x140017281  test    al, 1
0x140017283  jz      short loc_14001729F
0x140017285  cmp     byte ptr [rcx+29h], 2
0x140017289  jb      short loc_14001729F
0x14001728b  mov     rcx, [rcx+18h]
0x14001728f  mov     edx, 0Bh
0x140017294  mov     r9d, ebx
0x140017297  mov     r8, rbp
0x14001729a  call    WPP_SF_d
0x14001729f  lea     rcx, RedirectLock; SpinLock
0x1400172a6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400172ad  nop     dword ptr [rax+rax+00h]
0x1400172b2  mov     dl, r14b; NewIrql
0x1400172b5  lea     rcx, MappingLock; SpinLock
0x1400172bc  call    cs:__imp_KeReleaseSpinLock
0x1400172c3  nop     dword ptr [rax+rax+00h]
0x1400172c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172cf  cmp     rcx, r13
0x1400172d2  jz      loc_1400173CE
0x1400172d8  mov     eax, [rcx+2Ch]
0x1400172db  test    al, 1
0x1400172dd  jz      loc_1400173CE
0x1400172e3  cmp     byte ptr [rcx+29h], 6
0x1400172e7  jb      loc_1400173CE
0x1400172ed  mov     edx, 0Ch
0x1400172f2  jmp     loc_1400173BF
0x1400172f7  mov     r8, [rax+8]
0x1400172fb  add     r8, 10h
0x1400172ff  mov     rcx, [r8]
0x140017302  cmp     rcx, r8
0x140017305  jz      short loc_140017377
0x140017307  mov     r9d, [rdi]
0x14001730a  and     r9d, 1
0x14001730e  lea     rbx, [rcx-20h]
0x140017312  test    r9d, r9d
0x140017315  jz      short loc_14001732D
0x140017317  mov     rdx, [rbx+80h]
0x14001731e  test    rdx, rdx
0x140017321  jz      short loc_14001732D
0x140017323  mov     rax, [rdi+8]
0x140017327  cmp     [rdx+60h], rax
0x14001732b  jnz     short loc_14001736A
0x14001732d  cmp     rsi, [rbx+88h]
0x140017334  jnz     loc_140017684
0x14001733a  mov     eax, [rbx+0E0h]
0x140017340  cmp     [rdi+1Ch], eax
0x140017343  jnz     short loc_14001736A
0x140017345  movzx   eax, word ptr [rbx+0E4h]
0x14001734c  cmp     [rdi+20h], ax
0x140017350  jnz     short loc_14001736A
0x140017352  mov     eax, [rbx+0E8h]
0x140017358  cmp     [rdi+2Ch], eax
0x14001735b  jnz     short loc_14001736A
0x14001735d  movzx   eax, word ptr [rbx+0ECh]
0x140017364  cmp     [rdi+30h], ax
0x140017368  jz      short loc_1400173E0
0x14001736a  mov     rcx, [rcx]
0x14001736d  cmp     rcx, r8
0x140017370  jnz     short loc_14001730E
0x140017372  mov     ebx, 0C0000001h
0x140017377  lea     rcx, RedirectLock; SpinLock
0x14001737e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140017385  nop     dword ptr [rax+rax+00h]
0x14001738a  mov     dl, r14b; NewIrql
0x14001738d  lea     rcx, MappingLock; SpinLock
0x140017394  call    cs:__imp_KeReleaseSpinLock
0x14001739b  nop     dword ptr [rax+rax+00h]
0x1400173a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173a7  cmp     rcx, r13
0x1400173aa  jz      short loc_1400173CE
0x1400173ac  mov     edx, [rcx+2Ch]
0x1400173af  test    dl, 1
0x1400173b2  jz      short loc_1400173CE
0x1400173b4  cmp     byte ptr [rcx+29h], 6
0x1400173b8  jb      short loc_1400173CE
0x1400173ba  mov     edx, 15h
0x1400173bf  mov     rcx, [rcx+18h]
0x1400173c3  mov     r9d, ebx
0x1400173c6  mov     r8, rbp
0x1400173c9  call    WPP_SF_d
0x1400173ce  mov     eax, ebx
0x1400173d0  add     rsp, 70h
0x1400173d4  pop     r15
0x1400173d6  pop     r14
0x1400173d8  pop     r13
0x1400173da  pop     rdi
0x1400173db  pop     rsi
0x1400173dc  pop     rbp
0x1400173dd  pop     rbx
0x1400173de  retn
0x1400173e0  mov     eax, [rbx+70h]
0x1400173e3  mov     rbp, r15
0x1400173e6  mov     rsi, [rbx+98h]
0x1400173ed  test    al, 20h
0x1400173ef  jz      loc_1400175DB
0x1400173f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173fc  mov     dil, 5
0x1400173ff  cmp     rcx, r13
0x140017402  jz      short loc_140017426
0x140017404  mov     eax, [rcx+2Ch]
0x140017407  test    al, 1
0x140017409  jz      short loc_140017426
0x14001740b  cmp     [rcx+29h], dil
0x14001740f  jb      short loc_140017426
0x140017411  mov     rcx, [rcx+18h]
0x140017415  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001741c  mov     edx, 0Fh
0x140017421  call    WPP_SF_
0x140017426  lea     rcx, RedirectCompletionLock; SpinLock
0x14001742d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140017434  nop     dword ptr [rax+rax+00h]
0x140017439  mov     eax, [rbx+70h]
0x14001743c  bt      eax, 1Dh
0x140017440  jnb     short loc_140017471
0x140017442  mov     rcx, cs:WPP_GLOBAL_Control
0x140017449  cmp     rcx, r13
0x14001744c  jz      loc_1400175C8
0x140017452  mov     eax, [rcx+2Ch]
0x140017455  test    al, 1
0x140017457  jz      loc_1400175C8
0x14001745d  cmp     [rcx+29h], dil
0x140017461  jb      loc_1400175C8
0x140017467  mov     edx, 10h
0x14001746c  jmp     loc_1400175B8
0x140017471  bt      eax, 1Eh
0x140017475  jnb     loc_140017510
0x14001747b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017482  cmp     rcx, r13
0x140017485  jz      short loc_1400174A9
0x140017487  mov     eax, [rcx+2Ch]
0x14001748a  test    al, 1
0x14001748c  jz      short loc_1400174A9
0x14001748e  cmp     [rcx+29h], dil
0x140017492  jb      short loc_1400174A9
0x140017494  mov     rcx, [rcx+18h]
0x140017498  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001749f  mov     edx, 11h
0x1400174a4  call    WPP_SF_
0x1400174a9  btr     dword ptr [rbx+70h], 1Eh
0x1400174ae  lea     rax, [rbx+10h]
0x1400174b2  mov     rdx, [rax]
0x1400174b5  cmp     [rdx+8], rax
0x1400174b9  jnz     short loc_140017509
0x1400174bb  mov     rcx, [rax+8]
0x1400174bf  cmp     [rcx], rax
0x1400174c2  jnz     short loc_140017509
0x1400174c4  mov     [rcx], rdx
0x1400174c7  mov     [rdx+8], rcx
0x1400174cb  lea     rcx, RedirectCompletionLock; SpinLock
0x1400174d2  mov     [rax+8], rax
0x1400174d6  mov     [rax], rax
0x1400174d9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400174e0  nop     dword ptr [rax+rax+00h]
0x1400174e5  mov     rax, [rbx+88h]
0x1400174ec  mov     rdi, [rax+0B0h]
0x1400174f3  test    rdi, rdi
0x1400174f6  jz      loc_1400175DE
0x1400174fc  mov     rax, [rbx+80h]
0x140017503  mov     rbp, [rax+60h]
0x140017507  jmp     short loc_14001755E
0x140017509  mov     ecx, 3
0x14001750e  int     29h; Win8: RtlFailFast(ecx)
0x140017510  bt      eax, 1Ah
0x140017514  jnb     loc_14001759A
0x14001751a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017521  cmp     rcx, r13
0x140017524  jz      short loc_140017548
0x140017526  mov     eax, [rcx+2Ch]
0x140017529  test    al, 1
0x14001752b  jz      short loc_140017548
0x14001752d  cmp     [rcx+29h], dil
0x140017531  jb      short loc_140017548
0x140017533  mov     rcx, [rcx+18h]
0x140017537  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001753e  mov     edx, 12h
0x140017543  call    WPP_SF_
0x140017548  lea     rcx, RedirectCompletionLock; SpinLock
0x14001754f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140017556  nop     dword ptr [rax+rax+00h]
0x14001755b  mov     rdi, r15
0x14001755e  test    rsi, rsi
0x140017561  jz      short loc_140017593
0x140017563  lea     rax, [rbx+0A0h]
0x14001756a  xor     r9d, r9d
0x14001756d  mov     [rsp+0A8h+var_68], rax
0x140017572  xor     r8d, r8d
0x140017575  mov     [rsp+0A8h+var_70], r15
0x14001757a  xor     edx, edx
0x14001757c  mov     [rsp+0A8h+var_78], r15
0x140017581  mov     rcx, rsi
0x140017584  mov     [rsp+0A8h+var_80], r15
0x140017589  mov     [rsp+0A8h+var_88], r15
0x14001758e  call    NatQueryInformationMapping
0x140017593  mov     edx, 80h
0x140017598  jmp     short loc_1400175E3
0x14001759a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175a1  cmp     rcx, r13
0x1400175a4  jz      short loc_1400175C8
0x1400175a6  mov     eax, [rcx+2Ch]
0x1400175a9  test    al, 1
0x1400175ab  jz      short loc_1400175C8
0x1400175ad  cmp     [rcx+29h], dil
0x1400175b1  jb      short loc_1400175C8
0x1400175b3  mov     edx, 13h
0x1400175b8  mov     rcx, [rcx+18h]
0x1400175bc  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x1400175c3  call    WPP_SF_
0x1400175c8  lea     rcx, RedirectCompletionLock; SpinLock
0x1400175cf  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400175d6  nop     dword ptr [rax+rax+00h]
0x1400175db  mov     rdi, r15
0x1400175de  mov     edx, 0C0000120h
0x1400175e3  mov     rcx, rbx; P
0x1400175e6  call    NatpCleanupRedirect
0x1400175eb  lea     rcx, RedirectLock; SpinLock
0x1400175f2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400175f9  nop     dword ptr [rax+rax+00h]
0x1400175fe  test    rsi, rsi
0x140017601  jz      short loc_14001760B
0x140017603  mov     rcx, rsi; Entry
0x140017606  call    NatDeleteMapping
0x14001760b  mov     dl, r14b; NewIrql
0x14001760e  lea     rcx, MappingLock; SpinLock
0x140017615  call    cs:__imp_KeReleaseSpinLock
0x14001761c  nop     dword ptr [rax+rax+00h]
0x140017621  test    rdi, rdi
0x140017624  jz      short loc_14001764C
  ... truncated ...
```
