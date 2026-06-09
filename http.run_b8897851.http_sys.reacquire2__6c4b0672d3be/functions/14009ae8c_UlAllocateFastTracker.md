# UlAllocateFastTracker

- ea: `0x14009ae8c`
- end: `0x14009b0f7`
- name: `UlAllocateFastTracker`
- size: `619`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400aa118`
- `0x1400e4ddc`
- `0x1400e5650`

## callees

- `0x140049d28`
- `0x140051410`
- `0x140099568`
- `0x14009ae8c`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3f78`
- `0x1401cb564`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009af78`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009af78`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c3c3`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c3e6`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c3c3`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c3e6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14009b081`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14009b081`
- `ntoskrnl!ExAllocatePool3` at `0x14017c44e`
- `ntoskrnl!ExAllocatePool3` at `0x14017c44e`

## pseudocode

```c
_DWORD *__fastcall UlAllocateFastTracker(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        int a6,
        int a7,
        unsigned int a8)
{
  unsigned int v8; // esi
  unsigned int v9; // r14d
  _DWORD *v10; // rbx
  int v11; // ecx
  unsigned int v12; // ebp
  int LockArray_high; // esi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // rax
  __int64 v17; // rbx
  USHORT CurrentNodeNumber; // ax
  unsigned int v19; // eax
  __int64 v20; // r14
  __int64 v21; // rsi
  unsigned __int64 v22; // rdx
  _DWORD *Pool3; // rax
  __int64 v24; // [rsp+60h] [rbp-58h]
  __int64 v25; // [rsp+68h] [rbp-50h]

  v8 = a3;
  v9 = a2;
  v10 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLLLlLLL(a1, a2, a3, a1, a2, a3, a4, a5, a6, a7, a8);
  v11 = UlVariableHeaderSize + v9;
  if ( (unsigned int)UlVariableHeaderSize + v9 >= (unsigned int)UlVariableHeaderSize && v11 + v8 >= v8 )
  {
    v12 = 24 * a6;
    if ( !a5 || v8 > 0x800 || v9 > 0x200 || v12 > UlH3DefaultPairSize || a8 )
    {
      v19 = v9 != 0 ? v11 : 0;
      v20 = v19;
      v21 = a8 + v19 + v8;
      v24 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v21) + 7) & 0xFFFFFFF8;
      v25 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, a4) + 7) & 0xFFFFFFF8;
      v22 = a8 + v21 + v20 + v25 + 3 * (v24 + 160) + 2 * ((unsigned int)(24 * a7) + (unsigned __int64)v12);
      if ( v22 <= 0xFFFFFFFF )
      {
        Pool3 = (_DWORD *)ExAllocatePool3(66, (unsigned int)v22, 1430678613, UxLowPriorityPool, 1);
        v10 = Pool3;
        if ( Pool3 )
        {
          memset(Pool3, 0, 0x1E0u);
          v10[22] = v21;
          UlInitializeFastTrackerPool((_DWORD)v10, v24, v25, v20, a8, a6, 24 * a6, a7, 24 * a7);
          goto LABEL_17;
        }
      }
    }
    else
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v15 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0240[0])(
                          (unsigned int)dword_1401A0228,
                          qword_1401A0230,
                          (unsigned int)dword_1401A0238,
                          0);
      }
      else if ( UxCompactMode )
      {
        v17 = qword_1401A0220;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        v15 = (_DWORD *)PplAllocateFromLookasideListProcessor(v17, CurrentNodeNumber);
      }
      else
      {
        v14 = qword_1401A0220 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0220, v14 + 64);
        v15 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64));
      }
      v10 = v15;
      if ( v15 )
      {
        *v15 = LockArray_high;
LABEL_17:
        v10[4] = 1430678613;
        *((_QWORD *)v10 + 18) = 0;
        *((_QWORD *)v10 + 19) = 0;
        *((_QWORD *)v10 + 22) = 0;
        *((_QWORD *)v10 + 21) = 0;
        *((_QWORD *)v10 + 20) = 0;
        *((_QWORD *)v10 + 10) = 0;
        *((_BYTE *)v10 + 21) = 0;
        v10[66] = 0;
        *((_OWORD *)v10 + 17) = 0;
        memset(v10 + 46, 0, 0x50u);
        *((_QWORD *)v10 + 15) = *(_QWORD *)((char *)v10 + (a6 != 0 ? 8 : 0) + 104);
        v10[80] = 0;
        *((_QWORD *)v10 + 43) = 0;
        v10[100] = 0;
        *((_QWORD *)v10 + 53) = 0;
        v10[90] = 0;
        *((_QWORD *)v10 + 48) = 0;
        v10[110] = 0;
        *((_QWORD *)v10 + 58) = 0;
      }
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 72, WPP_4fd7477c6c0434f68f66d00f5eadbc3e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x14009ae8c  mov     dword ptr [rsp+Length], r9d
0x14009ae91  push    rbx
0x14009ae92  push    rbp
0x14009ae93  push    rsi
0x14009ae94  push    rdi
0x14009ae95  push    r12
0x14009ae97  push    r13
0x14009ae99  push    r14
0x14009ae9b  push    r15
0x14009ae9d  sub     rsp, 78h
0x14009aea1  mov     esi, r8d
0x14009aea4  mov     r14d, edx
0x14009aea7  xor     ebx, ebx
0x14009aea9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14009aeb0  mov     r15d, [rsp+0B8h+arg_38]
0x14009aeb8  mov     r13d, [rsp+0B8h+arg_30]
0x14009aec0  mov     edi, [rsp+0B8h+arg_28]
0x14009aec7  movzx   r12d, [rsp+0B8h+arg_20]
0x14009aed0  jnz     loc_14009B0AB
0x14009aed6  mov     eax, cs:UlVariableHeaderSize
0x14009aedc  lea     ecx, [rax+r14]
0x14009aee0  cmp     ecx, eax
0x14009aee2  jb      loc_14009B030
0x14009aee8  lea     eax, [rcx+rsi]
0x14009aeeb  cmp     eax, esi
0x14009aeed  jb      loc_14009B030
0x14009aef3  lea     ebp, [rdi+rdi*2]
0x14009aef6  shl     ebp, 3
0x14009aef9  test    r12b, r12b
0x14009aefc  jz      loc_14017C39E
0x14009af02  cmp     esi, 800h
0x14009af08  ja      loc_14017C39E
0x14009af0e  cmp     r14d, 200h
0x14009af15  ja      loc_14017C39E
0x14009af1b  cmp     ebp, cs:UlH3DefaultPairSize
0x14009af21  ja      loc_14017C39E
0x14009af27  xor     r12d, r12d
0x14009af2a  test    r15d, r15d
0x14009af2d  jnz     loc_14017C39E
0x14009af33  mov     esi, gs:1A4h
0x14009af3b  cmp     cs:UxDebugDisableLookaside, r12b
0x14009af42  jnz     loc_14009B052
0x14009af48  cmp     cs:UxCompactMode, r12b
0x14009af4f  jnz     loc_14009B07A
0x14009af55  mov     rcx, cs:qword_1401A0220
0x14009af5c  lea     ebx, [rsi+1]
0x14009af5f  shl     rbx, 7
0x14009af63  add     rbx, rcx
0x14009af66  mov     al, [rbx+0B0h]
0x14009af6c  test    al, al
0x14009af6e  jz      loc_14009B09D
0x14009af74  lea     rcx, [rbx+40h]; Lookaside
0x14009af78  call    cs:__imp_ExAllocateFromLookasideListEx
0x14009af7f  nop     dword ptr [rax+rax+00h]
0x14009af84  mov     rbx, rax
0x14009af87  test    rax, rax
0x14009af8a  jz      loc_14009B030
0x14009af90  mov     [rax], esi
0x14009af92  xor     edx, edx; Val
0x14009af94  mov     dword ptr [rbx+10h], 55466C55h
0x14009af9b  xorps   xmm0, xmm0
0x14009af9e  mov     [rbx+90h], r12
0x14009afa5  mov     [rbx+98h], r12
0x14009afac  lea     rcx, [rbx+0B8h]; void *
0x14009afb3  mov     [rbx+0B0h], r12
0x14009afba  mov     [rbx+0A8h], r12
0x14009afc1  lea     r8d, [rdx+50h]; Size
0x14009afc5  mov     [rbx+0A0h], r12
0x14009afcc  mov     [rbx+50h], r12
0x14009afd0  mov     [rbx+15h], r12b
0x14009afd4  mov     [rbx+108h], r12d
0x14009afdb  movups  xmmword ptr [rbx+110h], xmm0
0x14009afe2  call    memset
0x14009afe7  neg     edi
0x14009afe9  sbb     rax, rax
0x14009afec  and     eax, 8
0x14009afef  mov     rax, [rax+rbx+68h]
0x14009aff4  mov     [rbx+78h], rax
0x14009aff8  mov     [rbx+140h], r12d
0x14009afff  mov     [rbx+158h], r12
0x14009b006  mov     [rbx+190h], r12d
0x14009b00d  mov     [rbx+1A8h], r12
0x14009b014  mov     [rbx+168h], r12d
0x14009b01b  mov     [rbx+180h], r12
0x14009b022  mov     [rbx+1B8h], r12d
0x14009b029  mov     [rbx+1D0h], r12
0x14009b030  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14009b037  jnz     loc_14009B0D9
0x14009b03d  mov     rax, rbx
0x14009b040  add     rsp, 78h
0x14009b044  pop     r15
0x14009b046  pop     r14
0x14009b048  pop     r13
0x14009b04a  pop     r12
0x14009b04c  pop     rdi
0x14009b04d  pop     rsi
0x14009b04e  pop     rbp
0x14009b04f  pop     rbx
0x14009b050  retn
0x14009b052  mov     rax, cs:off_1401A0240
0x14009b059  xor     r9d, r9d
0x14009b05c  mov     r8d, cs:dword_1401A0238
0x14009b063  mov     rdx, cs:qword_1401A0230
0x14009b06a  mov     ecx, cs:dword_1401A0228
0x14009b070  call    _guard_dispatch_icall
0x14009b075  jmp     loc_14009AF84
0x14009b07a  mov     rbx, cs:qword_1401A0220
0x14009b081  call    cs:__imp_KeGetCurrentNodeNumber
0x14009b088  nop     dword ptr [rax+rax+00h]
0x14009b08d  movzx   edx, ax
0x14009b090  mov     rcx, rbx
0x14009b093  call    PplAllocateFromLookasideListProcessor
0x14009b098  jmp     loc_14009AF84
0x14009b09d  lea     rdx, [rbx+40h]
0x14009b0a1  call    PplpLazyInitializeLookasideList
0x14009b0a6  jmp     loc_14009AF74
0x14009b0ab  mov     [rsp+0B8h+var_68], r15d
0x14009b0b0  mov     [rsp+0B8h+var_70], r13d
0x14009b0b5  mov     [rsp+0B8h+var_78], edi
0x14009b0b9  mov     [rsp+0B8h+var_80], r12d
0x14009b0be  mov     [rsp+0B8h+var_88], r9d
0x14009b0c3  mov     r9, rcx
0x14009b0c6  mov     [rsp+0B8h+var_90], esi
0x14009b0ca  mov     [rsp+0B8h+var_98], r14d
0x14009b0cf  call    WPP_SF_qLLLlLLL
0x14009b0d4  jmp     loc_14009AED6
0x14009b0d9  mov     edx, 48h ; 'H'
0x14009b0de  lea     r8, WPP_4fd7477c6c0434f68f66d00f5eadbc3e_Traceguids
0x14009b0e5  mov     ecx, 409h
0x14009b0ea  mov     r9, rbx
0x14009b0ed  call    WPP_SF_q
0x14009b0f2  jmp     loc_14009B03D
0x14017c39e  lea     r12d, ds:0[r13*2]
0x14017c3a6  add     r12d, r13d
0x14017c3a9  shl     r12d, 3
0x14017c3ad  neg     r14d
0x14017c3b0  sbb     eax, eax
0x14017c3b2  and     eax, ecx
0x14017c3b4  mov     ecx, 0FFFh; Base
0x14017c3b9  add     esi, eax
0x14017c3bb  mov     r14d, eax
0x14017c3be  add     esi, r15d
0x14017c3c1  mov     edx, esi; Length
0x14017c3c3  call    cs:__imp_MmSizeOfMdl
0x14017c3ca  nop     dword ptr [rax+rax+00h]
0x14017c3cf  mov     edx, dword ptr [rsp+0B8h+Length]; Length
0x14017c3d6  mov     ecx, 0FFFh; Base
0x14017c3db  add     eax, 7
0x14017c3de  and     eax, 0FFFFFFF8h
0x14017c3e1  mov     [rsp+0B8h+var_58], rax
0x14017c3e6  call    cs:__imp_MmSizeOfMdl
0x14017c3ed  nop     dword ptr [rax+rax+00h]
0x14017c3f2  mov     ecx, ebp
0x14017c3f4  add     rcx, r12
0x14017c3f7  lea     r8d, [rax+7]
0x14017c3fb  mov     rax, [rsp+0B8h+var_58]
0x14017c400  add     rax, 0A0h
0x14017c406  and     r8d, 0FFFFFFF8h
0x14017c40a  mov     [rsp+0B8h+var_50], r8
0x14017c40f  lea     rax, [rax+rax*2]
0x14017c413  lea     rdx, [rax+rcx*2]
0x14017c417  mov     eax, 0FFFFFFFFh
0x14017c41c  add     rdx, r8
0x14017c41f  lea     rcx, [rsi+r14]
0x14017c423  add     rdx, rcx
0x14017c426  add     rdx, r15
0x14017c429  cmp     rdx, rax
0x14017c42c  ja      loc_14009B030
0x14017c432  mov     edx, edx
0x14017c434  lea     r9, UxLowPriorityPool
0x14017c43b  mov     ecx, 42h ; 'B'
0x14017c440  mov     [rsp+0B8h+var_98], 1
0x14017c448  mov     r8d, 55466C55h
0x14017c44e  call    cs:__imp_ExAllocatePool3
0x14017c455  nop     dword ptr [rax+rax+00h]
0x14017c45a  mov     rbx, rax
0x14017c45d  test    rax, rax
0x14017c460  jz      loc_14009B030
0x14017c466  xor     edx, edx; Val
0x14017c468  mov     r8d, 1E0h; Size
0x14017c46e  mov     rcx, rax; void *
0x14017c471  call    memset
0x14017c476  mov     r8d, dword ptr [rsp+0B8h+var_50]
0x14017c47b  mov     r9d, r14d
0x14017c47e  mov     edx, dword ptr [rsp+0B8h+var_58]
0x14017c482  mov     rcx, rbx
0x14017c485  mov     [rsp+0B8h+var_78], r12d
0x14017c48a  mov     [rsp+0B8h+var_80], r13d
0x14017c48f  mov     [rsp+0B8h+var_88], ebp
0x14017c493  mov     [rsp+0B8h+var_90], edi
0x14017c497  mov     [rsp+0B8h+var_98], r15d
0x14017c49c  mov     [rbx+58h], esi
0x14017c49f  call    UlInitializeFastTrackerPool
0x14017c4a4  xor     r12d, r12d
0x14017c4a7  jmp     loc_14009AF92
```
