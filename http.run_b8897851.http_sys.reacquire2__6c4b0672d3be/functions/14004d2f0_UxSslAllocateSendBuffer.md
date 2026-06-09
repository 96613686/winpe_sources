# UxSslAllocateSendBuffer

- ea: `0x14004d2f0`
- end: `0x14004d750`
- name: `UxSslAllocateSendBuffer`
- size: `1120`
- prototype: `__int64 __fastcall(SIZE_T Length)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004d760`
- `0x14004e120`
- `0x140096e60`
- `0x14013cab8`

## callees

- `0x140049d28`
- `0x14004d2f0`
- `0x140051410`
- `0x1401677e0`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d3a5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d480`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d530`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d3a5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d480`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004d530`
- `ntoskrnl!MmSizeOfMdl` at `0x14004d322`
- `ntoskrnl!MmSizeOfMdl` at `0x14004d322`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d688`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6b9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6ea`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d71b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d688`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6b9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d6ea`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004d71b`
- `ntoskrnl!ExAllocatePool3` at `0x1401766ca`
- `ntoskrnl!ExAllocatePool3` at `0x1401766ca`

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
0x14004d2f0  push    rbx
0x14004d2f2  sub     rsp, 30h
0x14004d2f6  mov     [rsp+38h+arg_8], rsi
0x14004d2fb  mov     [rsp+38h+arg_10], rdi
0x14004d300  mov     [rsp+38h+arg_18], r14
0x14004d305  xor     r14d, r14d
0x14004d308  mov     ebx, r14d
0x14004d30b  mov     edi, ecx
0x14004d30d  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d314  jnz     loc_14004D663
0x14004d31a  mov     rdx, rdi; Length
0x14004d31d  mov     ecx, 0FFFh; Base
0x14004d322  call    cs:__imp_MmSizeOfMdl
0x14004d329  nop     dword ptr [rax+rax+00h]
0x14004d32e  mov     rsi, rax
0x14004d331  lea     eax, [rdi+50h]
0x14004d334  cmp     eax, 50h ; 'P'
0x14004d337  jb      loc_14004D3FE
0x14004d33d  add     esi, 7
0x14004d340  lea     eax, [rdi+50h]
0x14004d343  and     esi, 0FFFFFFF8h
0x14004d346  add     eax, esi
0x14004d348  cmp     eax, esi
0x14004d34a  jb      loc_14004D3FE
0x14004d350  mov     [rsp+38h+arg_0], rbp
0x14004d355  cmp     edi, 905h
0x14004d35b  ja      loc_14004D424
0x14004d361  mov     ebp, gs:1A4h
0x14004d369  cmp     cs:UxDebugDisableLookaside, bl
0x14004d36f  jnz     loc_14004D4C4
0x14004d375  cmp     cs:UxCompactMode, bl
0x14004d37b  jnz     loc_14004D681
0x14004d381  mov     rcx, cs:qword_1401A0610
0x14004d388  lea     ebx, [rbp+1]
0x14004d38b  shl     rbx, 7
0x14004d38f  add     rbx, rcx
0x14004d392  movzx   eax, byte ptr [rbx+0B0h]
0x14004d399  test    al, al
0x14004d39b  jz      loc_14004D6A4
0x14004d3a1  lea     rcx, [rbx+40h]; Lookaside
0x14004d3a5  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d3ac  nop     dword ptr [rax+rax+00h]
0x14004d3b1  mov     rbx, rax
0x14004d3b4  test    rax, rax
0x14004d3b7  jz      short loc_14004D3F9
0x14004d3b9  mov     [rax+4], r14
0x14004d3bd  mov     [rax+0Ch], r14d
0x14004d3c1  mov     [rax+18h], r14
0x14004d3c5  mov     [rax+20h], r14
0x14004d3c9  mov     [rax+28h], r14
0x14004d3cd  mov     [rax+30h], r14
0x14004d3d1  mov     [rax+38h], r14d
0x14004d3d5  mov     [rax+48h], r14
0x14004d3d9  mov     [rax], ebp
0x14004d3db  mov     eax, r14d
0x14004d3de  mov     r9d, esi
0x14004d3e1  add     r9, 50h ; 'P'
0x14004d3e5  mov     dword ptr [rbx+10h], 53537855h
0x14004d3ec  add     r9, rbx
0x14004d3ef  mov     [rbx+14h], eax
0x14004d3f2  mov     [rbx+40h], r9
0x14004d3f6  mov     [rbx+3Ch], edi
0x14004d3f9  mov     rbp, [rsp+38h+arg_0]
0x14004d3fe  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d405  mov     r14, [rsp+38h+arg_18]
0x14004d40a  mov     rdi, [rsp+38h+arg_10]
0x14004d40f  mov     rsi, [rsp+38h+arg_8]
0x14004d414  jnz     loc_14004D732
0x14004d41a  mov     rax, rbx
0x14004d41d  add     rsp, 30h
0x14004d421  pop     rbx
0x14004d422  retn
0x14004d424  cmp     edi, 2105h
0x14004d42a  jbe     loc_14004D4EC
0x14004d430  cmp     edi, 4105h
0x14004d436  ja      loc_14004D5C4
0x14004d43c  mov     ebp, gs:1A4h
0x14004d444  cmp     cs:UxDebugDisableLookaside, bl
0x14004d44a  jnz     loc_14004D574
0x14004d450  cmp     cs:UxCompactMode, bl
0x14004d456  jnz     loc_14004D6E3
0x14004d45c  mov     rcx, cs:qword_1401A0670
0x14004d463  lea     ebx, [rbp+1]
0x14004d466  shl     rbx, 7
0x14004d46a  add     rbx, rcx
0x14004d46d  movzx   eax, byte ptr [rbx+0B0h]
0x14004d474  test    al, al
0x14004d476  jz      loc_14004D706
0x14004d47c  lea     rcx, [rbx+40h]; Lookaside
0x14004d480  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d487  nop     dword ptr [rax+rax+00h]
0x14004d48c  mov     rbx, rax
0x14004d48f  test    rax, rax
0x14004d492  jz      loc_14004D3F9
0x14004d498  mov     [rax+4], r14
0x14004d49c  mov     [rax+0Ch], r14d
0x14004d4a0  mov     [rax+18h], r14
0x14004d4a4  mov     [rax+20h], r14
0x14004d4a8  mov     [rax+28h], r14
0x14004d4ac  mov     [rax+30h], r14
0x14004d4b0  mov     [rax+38h], r14d
0x14004d4b4  mov     [rax+48h], r14
0x14004d4b8  mov     [rax], ebp
0x14004d4ba  mov     eax, 2
0x14004d4bf  jmp     loc_14004D3DE
0x14004d4c4  mov     rax, cs:off_1401A0630
0x14004d4cb  xor     r9d, r9d
0x14004d4ce  mov     r8d, cs:dword_1401A0628
0x14004d4d5  mov     rdx, cs:qword_1401A0620
0x14004d4dc  mov     ecx, cs:dword_1401A0618
0x14004d4e2  call    _guard_dispatch_icall
0x14004d4e7  jmp     loc_14004D3B1
0x14004d4ec  mov     ebp, gs:1A4h
0x14004d4f4  cmp     cs:UxDebugDisableLookaside, bl
0x14004d4fa  jnz     loc_14004D59C
0x14004d500  cmp     cs:UxCompactMode, bl
0x14004d506  jnz     loc_14004D6B2
0x14004d50c  mov     rcx, cs:qword_1401A0640
0x14004d513  lea     ebx, [rbp+1]
0x14004d516  shl     rbx, 7
0x14004d51a  add     rbx, rcx
0x14004d51d  movzx   eax, byte ptr [rbx+0B0h]
0x14004d524  test    al, al
0x14004d526  jz      loc_14004D6D5
0x14004d52c  lea     rcx, [rbx+40h]; Lookaside
0x14004d530  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004d537  nop     dword ptr [rax+rax+00h]
0x14004d53c  mov     rbx, rax
0x14004d53f  test    rax, rax
0x14004d542  jz      loc_14004D3F9
0x14004d548  mov     [rax+4], r14
0x14004d54c  mov     [rax+0Ch], r14d
0x14004d550  mov     [rax+18h], r14
0x14004d554  mov     [rax+20h], r14
0x14004d558  mov     [rax+28h], r14
0x14004d55c  mov     [rax+30h], r14
0x14004d560  mov     [rax+38h], r14d
0x14004d564  mov     [rax+48h], r14
0x14004d568  mov     [rax], ebp
0x14004d56a  mov     eax, 1
0x14004d56f  jmp     loc_14004D3DE
0x14004d574  mov     rax, cs:off_1401A0690
0x14004d57b  xor     r9d, r9d
0x14004d57e  mov     r8d, cs:dword_1401A0688
0x14004d585  mov     rdx, cs:qword_1401A0680
0x14004d58c  mov     ecx, cs:dword_1401A0678
0x14004d592  call    _guard_dispatch_icall
0x14004d597  jmp     loc_14004D48C
0x14004d59c  mov     rax, cs:off_1401A0660
0x14004d5a3  xor     r9d, r9d
0x14004d5a6  mov     r8d, cs:dword_1401A0658
0x14004d5ad  mov     rdx, cs:qword_1401A0650
0x14004d5b4  mov     ecx, cs:dword_1401A0648
0x14004d5ba  call    _guard_dispatch_icall
0x14004d5bf  jmp     loc_14004D53C
0x14004d5c4  cmp     cs:UxSslLargeBufferEnabled, bl
0x14004d5ca  jz      loc_1401766AE
0x14004d5d0  cmp     edi, 820Ah
0x14004d5d6  ja      loc_1401766AE
0x14004d5dc  mov     ebp, gs:1A4h
0x14004d5e4  cmp     cs:UxDebugDisableLookaside, bl
0x14004d5ea  jnz     short loc_14004D63E
0x14004d5ec  cmp     cs:UxCompactMode, bl
0x14004d5f2  jnz     loc_14004D714
0x14004d5f8  mov     rcx, cs:qword_1401A06A0
0x14004d5ff  mov     edx, ebp
0x14004d601  call    PplAllocateFromLookasideListProcessor
0x14004d606  mov     rbx, rax
0x14004d609  test    rax, rax
0x14004d60c  jz      loc_14004D3F9
0x14004d612  mov     [rax+4], r14
0x14004d616  mov     [rax+0Ch], r14d
0x14004d61a  mov     [rax+18h], r14
0x14004d61e  mov     [rax+20h], r14
0x14004d622  mov     [rax+28h], r14
0x14004d626  mov     [rax+30h], r14
0x14004d62a  mov     [rax+38h], r14d
0x14004d62e  mov     [rax+48h], r14
0x14004d632  mov     [rax], ebp
0x14004d634  mov     eax, 3
0x14004d639  jmp     loc_14004D3DE
0x14004d63e  mov     rax, cs:off_1401A06C0
0x14004d645  xor     r9d, r9d
0x14004d648  mov     r8d, cs:dword_1401A06B8
0x14004d64f  mov     rdx, cs:qword_1401A06B0
0x14004d656  mov     ecx, cs:dword_1401A06A8
0x14004d65c  call    _guard_dispatch_icall
0x14004d661  jmp     short loc_14004D606
0x14004d663  mov     edx, 0Eh
0x14004d668  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004d66f  mov     ecx, 411h
0x14004d674  mov     r9d, edi
0x14004d677  call    WPP_SF_d
0x14004d67c  jmp     loc_14004D31A
0x14004d681  mov     rbx, cs:qword_1401A0610
0x14004d688  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d68f  nop     dword ptr [rax+rax+00h]
0x14004d694  movzx   edx, ax
0x14004d697  mov     rcx, rbx
0x14004d69a  call    PplAllocateFromLookasideListProcessor
0x14004d69f  jmp     loc_14004D3B1
0x14004d6a4  lea     rdx, [rbx+40h]
0x14004d6a8  call    PplpLazyInitializeLookasideList
0x14004d6ad  jmp     loc_14004D3A1
0x14004d6b2  mov     rbx, cs:qword_1401A0640
0x14004d6b9  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d6c0  nop     dword ptr [rax+rax+00h]
0x14004d6c5  movzx   edx, ax
0x14004d6c8  mov     rcx, rbx
0x14004d6cb  call    PplAllocateFromLookasideListProcessor
0x14004d6d0  jmp     loc_14004D53C
0x14004d6d5  lea     rdx, [rbx+40h]
0x14004d6d9  call    PplpLazyInitializeLookasideList
0x14004d6de  jmp     loc_14004D52C
0x14004d6e3  mov     rbx, cs:qword_1401A0670
0x14004d6ea  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d6f1  nop     dword ptr [rax+rax+00h]
0x14004d6f6  movzx   edx, ax
0x14004d6f9  mov     rcx, rbx
0x14004d6fc  call    PplAllocateFromLookasideListProcessor
0x14004d701  jmp     loc_14004D48C
0x14004d706  lea     rdx, [rbx+40h]
0x14004d70a  call    PplpLazyInitializeLookasideList
0x14004d70f  jmp     loc_14004D47C
0x14004d714  mov     rbx, cs:qword_1401A06A0
0x14004d71b  call    cs:__imp_KeGetCurrentNodeNumber
0x14004d722  nop     dword ptr [rax+rax+00h]
0x14004d727  movzx   edx, ax
0x14004d72a  mov     rcx, rbx
0x14004d72d  jmp     loc_14004D601
0x14004d732  mov     edx, 0Fh
0x14004d737  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004d73e  mov     ecx, 411h
0x14004d743  mov     r9, rbx
0x14004d746  call    WPP_SF_q
0x14004d74b  jmp     loc_14004D41A
0x1401766ae  mov     edx, eax
0x1401766b0  lea     r9, UxLowPriorityPool
0x1401766b7  mov     ecx, 42h ; 'B'
0x1401766bc  mov     [rsp+38h+var_18], 1
0x1401766c4  mov     r8d, 53537855h
0x1401766ca  call    cs:__imp_ExAllocatePool3
0x1401766d1  nop     dword ptr [rax+rax+00h]
0x1401766d6  mov     rbx, rax
0x1401766d9  test    rax, rax
0x1401766dc  jz      loc_14004D3F9
0x1401766e2  mov     [rax], r14
0x1401766e5  mov     [rax+8], r14
0x1401766e9  mov     [rax+18h], r14
0x1401766ed  mov     [rax+20h], r14
0x1401766f1  mov     [rax+28h], r14
0x1401766f5  mov     [rax+30h], r14
0x1401766f9  mov     [rax+38h], r14d
0x1401766fd  mov     [rax+48h], r14
0x140176701  mov     eax, 4
0x140176706  jmp     loc_14004D3DE
```
