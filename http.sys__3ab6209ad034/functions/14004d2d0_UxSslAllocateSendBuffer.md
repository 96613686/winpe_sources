# UxSslAllocateSendBuffer

- ea: `0x14004d2d0`
- end: `0x14004d730`
- name: `UxSslAllocateSendBuffer`
- size: `1120`
- prototype: `__int64 __fastcall(SIZE_T Length)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004d740`
- `0x14004e100`
- `0x140096e40`
- `0x14013cba8`

## callees

- `0x140049d08`
- `0x14004d2d0`
- `0x1400513f0`
- `0x1401678f0`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d385`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d460`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d510`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d385`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d460`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d510`
- `ntoskrnl!MmSizeOfMdl` at `0x14004d302`
- `ntoskrnl!MmSizeOfMdl` at `0x14004d302`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d668`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d699`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6ca`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6fb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d668`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d699`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6ca`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6fb`
- `ntoskrnl!ExAllocatePool3` at `0x1401767ca`
- `ntoskrnl!ExAllocatePool3` at `0x1401767ca`

## pseudocode

```c
char *__fastcall UxSslAllocateSendBuffer(SIZE_T Length)
{
  char *v1; // rbx
  SIZE_T v2; // rdi
  int v3; // esi
  unsigned int v4; // esi
  unsigned int v5; // eax
  int v6; // ebp
  unsigned __int64 v7; // rbx
  char *v8; // rax
  int v9; // eax
  int v11; // ebp
  unsigned __int64 v12; // rbx
  char *v13; // rax
  int LockArray_high; // ebp
  unsigned __int64 v15; // rbx
  char *v16; // rax
  unsigned int v17; // ebp
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rbx
  USHORT v22; // ax
  __int64 v23; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v25; // rbx
  USHORT v26; // ax
  __int64 v27; // rbx
  __int64 Pool3; // rax

  v1 = 0;
  v2 = (unsigned int)Length;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, (unsigned int)Length);
  v3 = MmSizeOfMdl((PVOID)0xFFF, v2);
  if ( (unsigned int)v2 < 0xFFFFFFB0 )
  {
    v4 = (v3 + 7) & 0xFFFFFFF8;
    v5 = v4 + v2 + 80;
    if ( v5 >= v4 )
    {
      if ( (unsigned int)v2 > 0x905 )
      {
        if ( (unsigned int)v2 <= 0x2105 )
        {
          LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
          if ( UxDebugDisableLookaside )
          {
            v16 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0660)(
                            (unsigned int)dword_1401A0648,
                            qword_1401A0650,
                            (unsigned int)dword_1401A0658,
                            0);
          }
          else if ( UxCompactMode )
          {
            v23 = qword_1401A0640;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            v16 = (char *)PplAllocateFromLookasideListProcessor(v23, CurrentNodeNumber);
          }
          else
          {
            v15 = qword_1401A0640 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
            if ( !*(_BYTE *)(v15 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0640, v15 + 64);
            v16 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v15 + 64));
          }
          v1 = v16;
          if ( v16 )
          {
            *(_QWORD *)(v16 + 4) = 0;
            *((_DWORD *)v16 + 3) = 0;
            *((_QWORD *)v16 + 3) = 0;
            *((_QWORD *)v16 + 4) = 0;
            *((_QWORD *)v16 + 5) = 0;
            *((_QWORD *)v16 + 6) = 0;
            *((_DWORD *)v16 + 14) = 0;
            *((_QWORD *)v16 + 9) = 0;
            *(_DWORD *)v16 = LockArray_high;
            v9 = 1;
            goto LABEL_13;
          }
        }
        else if ( (unsigned int)v2 > 0x4105 )
        {
          if ( UxSslLargeBufferEnabled && (unsigned int)v2 <= 0x820A )
          {
            v17 = HIDWORD(KeGetPcr()[1].LockArray);
            if ( UxDebugDisableLookaside )
            {
              v20 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A06C0)(
                      (unsigned int)dword_1401A06A8,
                      qword_1401A06B0,
                      (unsigned int)dword_1401A06B8,
                      0);
            }
            else
            {
              if ( UxCompactMode )
              {
                v27 = qword_1401A06A0;
                v19 = KeGetCurrentNodeNumber();
                v18 = v27;
              }
              else
              {
                v18 = qword_1401A06A0;
                v19 = v17;
              }
              v20 = PplAllocateFromLookasideListProcessor(v18, v19);
            }
            v1 = (char *)v20;
            if ( v20 )
            {
              *(_QWORD *)(v20 + 4) = 0;
              *(_DWORD *)(v20 + 12) = 0;
              *(_QWORD *)(v20 + 24) = 0;
              *(_QWORD *)(v20 + 32) = 0;
              *(_QWORD *)(v20 + 40) = 0;
              *(_QWORD *)(v20 + 48) = 0;
              *(_DWORD *)(v20 + 56) = 0;
              *(_QWORD *)(v20 + 72) = 0;
              *(_DWORD *)v20 = v17;
              v9 = 3;
              goto LABEL_13;
            }
          }
          else
          {
            Pool3 = ExAllocatePool3(66, v5, 1397979221, UxLowPriorityPool, 1);
            v1 = (char *)Pool3;
            if ( Pool3 )
            {
              *(_QWORD *)Pool3 = 0;
              *(_QWORD *)(Pool3 + 8) = 0;
              *(_QWORD *)(Pool3 + 24) = 0;
              *(_QWORD *)(Pool3 + 32) = 0;
              *(_QWORD *)(Pool3 + 40) = 0;
              *(_QWORD *)(Pool3 + 48) = 0;
              *(_DWORD *)(Pool3 + 56) = 0;
              *(_QWORD *)(Pool3 + 72) = 0;
              v9 = 4;
              goto LABEL_13;
            }
          }
        }
        else
        {
          v11 = HIDWORD(KeGetPcr()[1].LockArray);
          if ( UxDebugDisableLookaside )
          {
            v13 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0690)(
                            (unsigned int)dword_1401A0678,
                            qword_1401A0680,
                            (unsigned int)dword_1401A0688,
                            0);
          }
          else if ( UxCompactMode )
          {
            v25 = qword_1401A0670;
            v26 = KeGetCurrentNodeNumber();
            v13 = (char *)PplAllocateFromLookasideListProcessor(v25, v26);
          }
          else
          {
            v12 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(v11 + 1) << 7);
            if ( !*(_BYTE *)(v12 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0670, v12 + 64);
            v13 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v12 + 64));
          }
          v1 = v13;
          if ( v13 )
          {
            *(_QWORD *)(v13 + 4) = 0;
            *((_DWORD *)v13 + 3) = 0;
            *((_QWORD *)v13 + 3) = 0;
            *((_QWORD *)v13 + 4) = 0;
            *((_QWORD *)v13 + 5) = 0;
            *((_QWORD *)v13 + 6) = 0;
            *((_DWORD *)v13 + 14) = 0;
            *((_QWORD *)v13 + 9) = 0;
            *(_DWORD *)v13 = v11;
            v9 = 2;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v6 = HIDWORD(KeGetPcr()[1].LockArray);
        if ( UxDebugDisableLookaside )
        {
          v8 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0630)(
                         (unsigned int)dword_1401A0618,
                         qword_1401A0620,
                         (unsigned int)dword_1401A0628,
                         0);
        }
        else if ( UxCompactMode )
        {
          v21 = qword_1401A0610;
          v22 = KeGetCurrentNodeNumber();
          v8 = (char *)PplAllocateFromLookasideListProcessor(v21, v22);
        }
        else
        {
          v7 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(v6 + 1) << 7);
          if ( !*(_BYTE *)(v7 + 176) )
            PplpLazyInitializeLookasideList(qword_1401A0610, v7 + 64);
          v8 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v7 + 64));
        }
        v1 = v8;
        if ( v8 )
        {
          *(_QWORD *)(v8 + 4) = 0;
          *((_DWORD *)v8 + 3) = 0;
          *((_QWORD *)v8 + 3) = 0;
          *((_QWORD *)v8 + 4) = 0;
          *((_QWORD *)v8 + 5) = 0;
          *((_QWORD *)v8 + 6) = 0;
          *((_DWORD *)v8 + 14) = 0;
          *((_QWORD *)v8 + 9) = 0;
          *(_DWORD *)v8 = v6;
          v9 = 0;
LABEL_13:
          *((_DWORD *)v1 + 4) = 1397979221;
          *((_DWORD *)v1 + 5) = v9;
          *((_QWORD *)v1 + 8) = &v1[v4 + 80];
          *((_DWORD *)v1 + 15) = v2;
        }
      }
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 15, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x14004d2d0  push    rbx
0x14004d2d2  sub     rsp, 30h
0x14004d2d6  mov     [rsp+38h+arg_8], rsi
0x14004d2db  mov     [rsp+38h+arg_10], rdi
0x14004d2e0  mov     [rsp+38h+arg_18], r14
0x14004d2e5  xor     r14d, r14d
0x14004d2e8  mov     ebx, r14d
0x14004d2eb  mov     edi, ecx
0x14004d2ed  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d2f4  jnz     loc_14004D643
0x14004d2fa  mov     rdx, rdi; Length
0x14004d2fd  mov     ecx, 0FFFh; Base
0x14004d302  call    cs:__imp_MmSizeOfMdl
0x14004d309  nop     dword ptr [rax+rax+00h]
0x14004d30e  mov     rsi, rax
0x14004d311  lea     eax, [rdi+50h]
0x14004d314  cmp     eax, 50h ; 'P'
0x14004d317  jb      loc_14004D3DE
0x14004d31d  add     esi, 7
0x14004d320  lea     eax, [rdi+50h]
0x14004d323  and     esi, 0FFFFFFF8h
0x14004d326  add     eax, esi
0x14004d328  cmp     eax, esi
0x14004d32a  jb      loc_14004D3DE
0x14004d330  mov     [rsp+38h+arg_0], rbp
0x14004d335  cmp     edi, 905h
0x14004d33b  ja      loc_14004D404
0x14004d341  mov     ebp, gs:1A4h
0x14004d349  cmp     cs:UxDebugDisableLookaside, bl
0x14004d34f  jnz     loc_14004D4A4
0x14004d355  cmp     cs:UxCompactMode, bl
0x14004d35b  jnz     loc_14004D661
0x14004d361  mov     rcx, cs:qword_1401A0610
0x14004d368  lea     ebx, [rbp+1]
0x14004d36b  shl     rbx, 7
0x14004d36f  add     rbx, rcx
0x14004d372  movzx   eax, byte ptr [rbx+0B0h]
0x14004d379  test    al, al
0x14004d37b  jz      loc_14004D684
0x14004d381  lea     rcx, [rbx+40h]; Lookaside
0x14004d385  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d38c  nop     dword ptr [rax+rax+00h]
0x14004d391  mov     rbx, rax
0x14004d394  test    rax, rax
0x14004d397  jz      short loc_14004D3D9
0x14004d399  mov     [rax+4], r14
0x14004d39d  mov     [rax+0Ch], r14d
0x14004d3a1  mov     [rax+18h], r14
0x14004d3a5  mov     [rax+20h], r14
0x14004d3a9  mov     [rax+28h], r14
0x14004d3ad  mov     [rax+30h], r14
0x14004d3b1  mov     [rax+38h], r14d
0x14004d3b5  mov     [rax+48h], r14
0x14004d3b9  mov     [rax], ebp
0x14004d3bb  mov     eax, r14d
0x14004d3be  mov     r9d, esi
0x14004d3c1  add     r9, 50h ; 'P'
0x14004d3c5  mov     dword ptr [rbx+10h], 53537855h
0x14004d3cc  add     r9, rbx
0x14004d3cf  mov     [rbx+14h], eax
0x14004d3d2  mov     [rbx+40h], r9
0x14004d3d6  mov     [rbx+3Ch], edi
0x14004d3d9  mov     rbp, [rsp+38h+arg_0]
0x14004d3de  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d3e5  mov     r14, [rsp+38h+arg_18]
0x14004d3ea  mov     rdi, [rsp+38h+arg_10]
0x14004d3ef  mov     rsi, [rsp+38h+arg_8]
0x14004d3f4  jnz     loc_14004D712
0x14004d3fa  mov     rax, rbx
0x14004d3fd  add     rsp, 30h
0x14004d401  pop     rbx
0x14004d402  retn
0x14004d404  cmp     edi, 2105h
0x14004d40a  jbe     loc_14004D4CC
0x14004d410  cmp     edi, 4105h
0x14004d416  ja      loc_14004D5A4
0x14004d41c  mov     ebp, gs:1A4h
0x14004d424  cmp     cs:UxDebugDisableLookaside, bl
0x14004d42a  jnz     loc_14004D554
0x14004d430  cmp     cs:UxCompactMode, bl
0x14004d436  jnz     loc_14004D6C3
0x14004d43c  mov     rcx, cs:qword_1401A0670
0x14004d443  lea     ebx, [rbp+1]
0x14004d446  shl     rbx, 7
0x14004d44a  add     rbx, rcx
0x14004d44d  movzx   eax, byte ptr [rbx+0B0h]
0x14004d454  test    al, al
0x14004d456  jz      loc_14004D6E6
0x14004d45c  lea     rcx, [rbx+40h]; Lookaside
0x14004d460  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d467  nop     dword ptr [rax+rax+00h]
0x14004d46c  mov     rbx, rax
0x14004d46f  test    rax, rax
0x14004d472  jz      loc_14004D3D9
0x14004d478  mov     [rax+4], r14
0x14004d47c  mov     [rax+0Ch], r14d
0x14004d480  mov     [rax+18h], r14
0x14004d484  mov     [rax+20h], r14
0x14004d488  mov     [rax+28h], r14
0x14004d48c  mov     [rax+30h], r14
0x14004d490  mov     [rax+38h], r14d
0x14004d494  mov     [rax+48h], r14
0x14004d498  mov     [rax], ebp
0x14004d49a  mov     eax, 2
0x14004d49f  jmp     loc_14004D3BE
0x14004d4a4  mov     rax, cs:off_1401A0630
0x14004d4ab  xor     r9d, r9d
0x14004d4ae  mov     r8d, cs:dword_1401A0628
0x14004d4b5  mov     rdx, cs:qword_1401A0620
0x14004d4bc  mov     ecx, cs:dword_1401A0618
0x14004d4c2  call    _guard_dispatch_icall
0x14004d4c7  jmp     loc_14004D391
0x14004d4cc  mov     ebp, gs:1A4h
0x14004d4d4  cmp     cs:UxDebugDisableLookaside, bl
0x14004d4da  jnz     loc_14004D57C
0x14004d4e0  cmp     cs:UxCompactMode, bl
0x14004d4e6  jnz     loc_14004D692
0x14004d4ec  mov     rcx, cs:qword_1401A0640
0x14004d4f3  lea     ebx, [rbp+1]
0x14004d4f6  shl     rbx, 7
0x14004d4fa  add     rbx, rcx
0x14004d4fd  movzx   eax, byte ptr [rbx+0B0h]
0x14004d504  test    al, al
0x14004d506  jz      loc_14004D6B5
0x14004d50c  lea     rcx, [rbx+40h]; Lookaside
0x14004d510  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d517  nop     dword ptr [rax+rax+00h]
0x14004d51c  mov     rbx, rax
0x14004d51f  test    rax, rax
0x14004d522  jz      loc_14004D3D9
0x14004d528  mov     [rax+4], r14
0x14004d52c  mov     [rax+0Ch], r14d
0x14004d530  mov     [rax+18h], r14
0x14004d534  mov     [rax+20h], r14
0x14004d538  mov     [rax+28h], r14
0x14004d53c  mov     [rax+30h], r14
0x14004d540  mov     [rax+38h], r14d
0x14004d544  mov     [rax+48h], r14
0x14004d548  mov     [rax], ebp
0x14004d54a  mov     eax, 1
0x14004d54f  jmp     loc_14004D3BE
0x14004d554  mov     rax, cs:off_1401A0690
0x14004d55b  xor     r9d, r9d
0x14004d55e  mov     r8d, cs:dword_1401A0688
0x14004d565  mov     rdx, cs:qword_1401A0680
0x14004d56c  mov     ecx, cs:dword_1401A0678
0x14004d572  call    _guard_dispatch_icall
0x14004d577  jmp     loc_14004D46C
0x14004d57c  mov     rax, cs:off_1401A0660
0x14004d583  xor     r9d, r9d
0x14004d586  mov     r8d, cs:dword_1401A0658
0x14004d58d  mov     rdx, cs:qword_1401A0650
0x14004d594  mov     ecx, cs:dword_1401A0648
0x14004d59a  call    _guard_dispatch_icall
0x14004d59f  jmp     loc_14004D51C
0x14004d5a4  cmp     cs:UxSslLargeBufferEnabled, bl
0x14004d5aa  jz      loc_1401767AE
0x14004d5b0  cmp     edi, 820Ah
0x14004d5b6  ja      loc_1401767AE
0x14004d5bc  mov     ebp, gs:1A4h
0x14004d5c4  cmp     cs:UxDebugDisableLookaside, bl
0x14004d5ca  jnz     short loc_14004D61E
0x14004d5cc  cmp     cs:UxCompactMode, bl
0x14004d5d2  jnz     loc_14004D6F4
0x14004d5d8  mov     rcx, cs:qword_1401A06A0
0x14004d5df  mov     edx, ebp
0x14004d5e1  call    PplAllocateFromLookasideListProcessor
0x14004d5e6  mov     rbx, rax
0x14004d5e9  test    rax, rax
0x14004d5ec  jz      loc_14004D3D9
0x14004d5f2  mov     [rax+4], r14
0x14004d5f6  mov     [rax+0Ch], r14d
0x14004d5fa  mov     [rax+18h], r14
0x14004d5fe  mov     [rax+20h], r14
0x14004d602  mov     [rax+28h], r14
0x14004d606  mov     [rax+30h], r14
0x14004d60a  mov     [rax+38h], r14d
0x14004d60e  mov     [rax+48h], r14
0x14004d612  mov     [rax], ebp
0x14004d614  mov     eax, 3
0x14004d619  jmp     loc_14004D3BE
0x14004d61e  mov     rax, cs:off_1401A06C0
0x14004d625  xor     r9d, r9d
0x14004d628  mov     r8d, cs:dword_1401A06B8
0x14004d62f  mov     rdx, cs:qword_1401A06B0
0x14004d636  mov     ecx, cs:dword_1401A06A8
0x14004d63c  call    _guard_dispatch_icall
0x14004d641  jmp     short loc_14004D5E6
0x14004d643  mov     edx, 0Eh
0x14004d648  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004d64f  mov     ecx, 411h
0x14004d654  mov     r9d, edi
0x14004d657  call    WPP_SF_d
0x14004d65c  jmp     loc_14004D2FA
0x14004d661  mov     rbx, cs:qword_1401A0610
0x14004d668  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d66f  nop     dword ptr [rax+rax+00h]
0x14004d674  movzx   edx, ax
0x14004d677  mov     rcx, rbx
0x14004d67a  call    PplAllocateFromLookasideListProcessor
0x14004d67f  jmp     loc_14004D391
0x14004d684  lea     rdx, [rbx+40h]
0x14004d688  call    PplpLazyInitializeLookasideList
0x14004d68d  jmp     loc_14004D381
0x14004d692  mov     rbx, cs:qword_1401A0640
0x14004d699  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d6a0  nop     dword ptr [rax+rax+00h]
0x14004d6a5  movzx   edx, ax
0x14004d6a8  mov     rcx, rbx
0x14004d6ab  call    PplAllocateFromLookasideListProcessor
0x14004d6b0  jmp     loc_14004D51C
0x14004d6b5  lea     rdx, [rbx+40h]
0x14004d6b9  call    PplpLazyInitializeLookasideList
0x14004d6be  jmp     loc_14004D50C
0x14004d6c3  mov     rbx, cs:qword_1401A0670
0x14004d6ca  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d6d1  nop     dword ptr [rax+rax+00h]
0x14004d6d6  movzx   edx, ax
0x14004d6d9  mov     rcx, rbx
0x14004d6dc  call    PplAllocateFromLookasideListProcessor
0x14004d6e1  jmp     loc_14004D46C
0x14004d6e6  lea     rdx, [rbx+40h]
0x14004d6ea  call    PplpLazyInitializeLookasideList
0x14004d6ef  jmp     loc_14004D45C
0x14004d6f4  mov     rbx, cs:qword_1401A06A0
0x14004d6fb  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d702  nop     dword ptr [rax+rax+00h]
0x14004d707  movzx   edx, ax
0x14004d70a  mov     rcx, rbx
0x14004d70d  jmp     loc_14004D5E1
0x14004d712  mov     edx, 0Fh
0x14004d717  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004d71e  mov     ecx, 411h
0x14004d723  mov     r9, rbx
0x14004d726  call    WPP_SF_q
0x14004d72b  jmp     loc_14004D3FA
0x1401767ae  mov     edx, eax
0x1401767b0  lea     r9, UxLowPriorityPool
0x1401767b7  mov     ecx, 42h ; 'B'
0x1401767bc  mov     [rsp+38h+var_18], 1
0x1401767c4  mov     r8d, 53537855h
0x1401767ca  call    cs:__imp_ExAllocatePool3
0x1401767d1  nop     dword ptr [rax+rax+00h]
0x1401767d6  mov     rbx, rax
0x1401767d9  test    rax, rax
0x1401767dc  jz      loc_14004D3D9
0x1401767e2  mov     [rax], r14
0x1401767e5  mov     [rax+8], r14
0x1401767e9  mov     [rax+18h], r14
0x1401767ed  mov     [rax+20h], r14
0x1401767f1  mov     [rax+28h], r14
0x1401767f5  mov     [rax+30h], r14
0x1401767f9  mov     [rax+38h], r14d
0x1401767fd  mov     [rax+48h], r14
0x140176801  mov     eax, 4
0x140176806  jmp     loc_14004D3BE
```
