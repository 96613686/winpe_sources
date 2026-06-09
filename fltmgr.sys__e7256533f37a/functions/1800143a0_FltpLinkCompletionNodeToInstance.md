# FltpLinkCompletionNodeToInstance

- ea: `0x1800143a0`
- end: `0x180014634`
- name: `FltpLinkCompletionNodeToInstance`
- size: `660`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800047e0`
- `0x1800128f0`

## callees

- `0x1800143a0`
- `0x180014f10`
- `0x1800188d0`
- `0x180018b20`
- `0x18001f0a0`
- `0x18002114c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001444d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001444d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800144f6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800144f6`

## string_xrefs

- `0x180014534`: `FltpLinkCompletionNodeToInstance`
- `0x180014572`: `FltpLinkCompletionNodeToInstance`
- `0x1800145aa`: `FltpLinkCompletionNodeToInstance`
- `0x1800145cf`: `FltpLinkCompletionNodeToInstance`
- `0x18001460b`: `FltpLinkCompletionNodeToInstance`

## pseudocode

```c
void __fastcall FltpLinkCompletionNodeToInstance(__int64 *a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v4; // rsi
  bool v5; // bp
  KSPIN_LOCK *v6; // r14
  int v7; // ecx
  KSPIN_LOCK **v8; // rdx
  __int64 v9; // r15
  KSPIN_LOCK **v10; // rcx
  KSPIN_LOCK *v11; // r14
  KSPIN_LOCK **v12; // rcx
  KSPIN_LOCK *v13; // r14
  __int64 v14; // rbx
  int v15; // edi
  PCHAR v16; // rax
  __int64 v17; // rbx
  int v18; // edi
  PCHAR IrpName; // rax
  int v20; // r8d
  __int64 v21; // rbx
  int v22; // edi
  PCHAR v23; // rax
  int v24; // r8d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-38h] BYREF

  v2 = *(_QWORD *)a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = (__int64)a1;
  v5 = 0;
  if ( (*(_DWORD *)(v2 + 232) & 2) == 0 )
  {
    a1 = FltpOperationFlags;
    if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(a2 + 52) + 22)) & 1) == 0 )
      v5 = 1;
  }
  if ( *(_QWORD *)(*(_QWORD *)(v4 + 72) + 240LL) || v5 )
  {
    v6 = (KSPIN_LOCK *)(*(_QWORD *)(*(_QWORD *)(v4 + 296) + 8LL)
                      + (unsigned int)(dword_18003ECE8 * (HIDWORD(KeGetPcr()[1].LockArray) % **(_DWORD **)(v4 + 296))));
    *(_QWORD *)(a2 + 32) = v6;
    KeAcquireInStackQueuedSpinLock(v6, &LockHandle);
    if ( (*(_DWORD *)(v4 + 80) & 2) == 0 )
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 2) != 0 )
        McTemplateU0sppd_EtwWriteTransfer(
          v7,
          (unsigned int)CompletionNodeSup_c440,
          (unsigned int)"FltpLinkCompletionNodeToInstance",
          *(_QWORD *)a2,
          a2,
          *(_BYTE *)(a2 + 52));
      v8 = (KSPIN_LOCK **)v6[2];
      if ( *v8 != v6 + 1 )
        goto LABEL_12;
      *(_QWORD *)(a2 + 16) = v6 + 1;
      *(_QWORD *)(a2 + 24) = v8;
      *v8 = (KSPIN_LOCK *)(a2 + 16);
      v6[2] = a2 + 16;
      *(_WORD *)(a2 + 120) |= 2u;
LABEL_21:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return;
    }
    v9 = *(_QWORD *)a2;
    if ( v5 )
    {
      if ( (*(_BYTE *)(a2 + 120) & 8) == 0 )
      {
        DrainCompletionNode(v4, a2, &LockHandle);
        return;
      }
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 2) != 0 )
        McTemplateU0sppd_EtwWriteTransfer(
          v7,
          (unsigned int)CompletionNodeSup_c480,
          (unsigned int)"FltpLinkCompletionNodeToInstance",
          v9,
          a2,
          *(_BYTE *)(a2 + 52));
      v12 = (KSPIN_LOCK **)v6[4];
      v13 = v6 + 3;
      if ( *v12 == v13 )
      {
        *(_QWORD *)(a2 + 16) = v13;
        *(_QWORD *)(a2 + 24) = v12;
        *v12 = (KSPIN_LOCK *)(a2 + 16);
        v13[1] = a2 + 16;
        *(_WORD *)(a2 + 120) |= 4u;
        if ( (*(_DWORD *)(v9 + 232) & 1) != 0 )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 48) + 68LL) = 1;
          if ( (byte_180040A41 & 0x20) != 0 )
          {
            v17 = *(_QWORD *)(v9 + 248);
            v18 = *(char *)(v17 + 4);
            IrpName = FltGetIrpName(*(_BYTE *)(v17 + 4));
            McTemplateU0sdds_EtwWriteTransfer(
              *(char *)(v17 + 5),
              (unsigned int)CompletionNodeSup_c506,
              v20,
              v18,
              *(_BYTE *)(v17 + 5),
              (__int64)IrpName);
          }
        }
        else if ( (byte_180040A41 & 0x20) != 0 )
        {
          v21 = *(_QWORD *)(v9 + 248);
          v22 = *(char *)(v21 + 4);
          v23 = FltGetIrpName(*(_BYTE *)(v21 + 4));
          McTemplateU0sdds_EtwWriteTransfer(
            *(char *)(v21 + 5),
            (unsigned int)CompletionNodeSup_c514,
            v24,
            v22,
            *(_BYTE *)(v21 + 5),
            (__int64)v23);
        }
        goto LABEL_21;
      }
    }
    else
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 2) != 0 )
        McTemplateU0sppd_EtwWriteTransfer(
          v7,
          (unsigned int)CompletionNodeSup_c548,
          (unsigned int)"FltpLinkCompletionNodeToInstance",
          v9,
          a2,
          *(_BYTE *)(a2 + 52));
      v10 = (KSPIN_LOCK **)v6[4];
      v11 = v6 + 3;
      if ( *v10 == v11 )
      {
        *(_QWORD *)(a2 + 16) = v11;
        *(_QWORD *)(a2 + 24) = v10;
        *v10 = (KSPIN_LOCK *)(a2 + 16);
        v11[1] = a2 + 16;
        *(_WORD *)(a2 + 120) |= 4u;
        if ( (byte_180040A41 & 0x20) != 0 )
        {
          v14 = *(_QWORD *)(v9 + 248);
          v15 = *(char *)(v14 + 4);
          v16 = FltGetIrpName(*(_BYTE *)(v14 + 4));
          McTemplateU0sddsp_EtwWriteTransfer(
            *(char *)(v14 + 5),
            (unsigned int)CompletionNodeSup_c559,
            (unsigned int)"FltpLinkCompletionNodeToInstance",
            v15,
            *(_BYTE *)(v14 + 5),
            (__int64)v16,
            v9);
        }
        goto LABEL_21;
      }
    }
LABEL_12:
    __fastfail(3u);
  }
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 2) != 0 )
    McTemplateU0sppd_EtwWriteTransfer(
      (_DWORD)a1,
      (unsigned int)")",
      (unsigned int)"FltpLinkCompletionNodeToInstance",
      v2,
      a2,
      *(_BYTE *)(a2 + 52));
  *(_QWORD *)(a2 + 32) = 0;
}

```

## disassembly

```asm
0x1800143a0  mov     [rsp+arg_10], rbx
0x1800143a5  push    rbp
0x1800143a6  push    rsi
0x1800143a7  push    rdi
0x1800143a8  sub     rsp, 60h
0x1800143ac  mov     r9, [rdx]
0x1800143af  xor     eax, eax
0x1800143b1  xorps   xmm0, xmm0
0x1800143b4  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1800143b9  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1800143be  mov     rdi, rdx
0x1800143c1  mov     rsi, rcx
0x1800143c4  mov     eax, [r9+0E8h]
0x1800143cb  test    al, 2
0x1800143cd  jz      loc_180014485
0x1800143d3  xor     bpl, bpl
0x1800143d6  mov     rax, [rsi+48h]
0x1800143da  cmp     qword ptr [rax+0F0h], 0
0x1800143e2  jnz     short loc_18001440F
0x1800143e4  test    bpl, bpl
0x1800143e7  jnz     short loc_18001440F
0x1800143e9  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 2
0x1800143f0  jnz     loc_18001456E
0x1800143f6  mov     qword ptr [rdi+20h], 0
0x1800143fe  mov     rbx, [rsp+78h+arg_10]
0x180014406  add     rsp, 60h
0x18001440a  pop     rdi
0x18001440b  pop     rsi
0x18001440c  pop     rbp
0x18001440d  retn
0x18001440f  mov     eax, gs:1A4h
0x180014417  xor     edx, edx
0x180014419  mov     r8, [rsi+128h]
0x180014420  mov     [rsp+78h+arg_0], r14
0x180014428  mov     [rsp+78h+arg_8], r15
0x180014430  div     dword ptr [r8]
0x180014433  imul    edx, cs:dword_18003ECE8
0x18001443a  mov     r14d, edx
0x18001443d  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x180014442  add     r14, [r8+8]
0x180014446  mov     rcx, r14; SpinLock
0x180014449  mov     [rdi+20h], r14
0x18001444d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x180014454  nop     dword ptr [rax+rax+00h]
0x180014459  mov     eax, [rsi+50h]
0x18001445c  test    al, 2
0x18001445e  jnz     short loc_1800144A7
0x180014460  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 2
0x180014467  jnz     loc_180014530
0x18001446d  mov     rdx, [r14+10h]
0x180014471  lea     rcx, [r14+8]
0x180014475  cmp     [rdx], rcx
0x180014478  jz      loc_180014517
0x18001447e  mov     ecx, 3
0x180014483  int     29h; Win8: RtlFailFast(ecx)
0x180014485  movzx   eax, byte ptr [rdx+34h]
0x180014489  lea     rcx, FltpOperationFlags
0x180014490  add     al, 16h
0x180014492  movzx   eax, al
0x180014495  test    byte ptr [rax+rcx], 1
0x180014499  jnz     loc_1800143D3
0x18001449f  mov     bpl, 1
0x1800144a2  jmp     loc_1800143D6
0x1800144a7  mov     r15, [rdi]
0x1800144aa  test    bpl, bpl
0x1800144ad  jnz     loc_180014593
0x1800144b3  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 2
0x1800144ba  jnz     loc_1800145CB
0x1800144c0  mov     rcx, [r14+20h]
0x1800144c4  add     r14, 18h
0x1800144c8  cmp     [rcx], r14
0x1800144cb  jnz     short loc_18001447E
0x1800144cd  lea     rax, [rdi+10h]
0x1800144d1  mov     [rax], r14
0x1800144d4  mov     [rax+8], rcx
0x1800144d8  mov     [rcx], rax
0x1800144db  mov     [r14+8], rax
0x1800144df  or      word ptr [rdi+78h], 4
0x1800144e4  test    cs:byte_180040A41, 20h
0x1800144eb  jnz     loc_1800145F3
0x1800144f1  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1800144f6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1800144fd  nop     dword ptr [rax+rax+00h]
0x180014502  mov     r14, [rsp+78h+arg_0]
0x18001450a  mov     r15, [rsp+78h+arg_8]
0x180014512  jmp     loc_1800143FE
0x180014517  lea     rax, [rdi+10h]
0x18001451b  mov     [rax], rcx
0x18001451e  mov     [rax+8], rdx
0x180014522  mov     [rdx], rax
0x180014525  mov     [rcx+8], rax
0x180014529  or      word ptr [rdi+78h], 2
0x18001452e  jmp     short loc_1800144F1
0x180014530  movsx   eax, byte ptr [rdi+34h]
0x180014534  lea     r8, aFltplinkcomple; "FltpLinkCompletionNodeToInstance"
0x18001453b  mov     r9, [rdi]
0x18001453e  lea     rdx, CompletionNodeSup_c440
0x180014545  mov     dword ptr [rsp+78h+var_50], eax
0x180014549  mov     [rsp+78h+var_58], rdi
0x18001454e  call    McTemplateU0sppd_EtwWriteTransfer
0x180014553  jmp     loc_18001446D
0x180014558  mov     rcx, [r14+20h]
0x18001455c  add     r14, 18h
0x180014560  cmp     [rcx], r14
0x180014563  jnz     loc_18001447E
0x180014569  jmp     loc_180025EF0
0x18001456e  movsx   eax, byte ptr [rdx+34h]
0x180014572  lea     r8, aFltplinkcomple; "FltpLinkCompletionNodeToInstance"
0x180014579  mov     dword ptr [rsp+78h+var_50], eax
0x18001457d  lea     rdx, CompletionNodeSup_c401; ")"
0x180014584  mov     [rsp+78h+var_58], rdi
0x180014589  call    McTemplateU0sppd_EtwWriteTransfer
0x18001458e  jmp     loc_1800143F6
0x180014593  test    byte ptr [rdi+78h], 8
0x180014597  jz      loc_180025FA0
0x18001459d  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 2
0x1800145a4  jz      short loc_180014558
0x1800145a6  movsx   eax, byte ptr [rdi+34h]
0x1800145aa  lea     r8, aFltplinkcomple; "FltpLinkCompletionNodeToInstance"
0x1800145b1  mov     dword ptr [rsp+78h+var_50], eax
0x1800145b5  lea     rdx, CompletionNodeSup_c480
0x1800145bc  mov     r9, r15
0x1800145bf  mov     [rsp+78h+var_58], rdi
0x1800145c4  call    McTemplateU0sppd_EtwWriteTransfer
0x1800145c9  jmp     short loc_180014558
0x1800145cb  movsx   eax, byte ptr [rdi+34h]
0x1800145cf  lea     r8, aFltplinkcomple; "FltpLinkCompletionNodeToInstance"
0x1800145d6  mov     dword ptr [rsp+78h+var_50], eax
0x1800145da  lea     rdx, CompletionNodeSup_c548
0x1800145e1  mov     r9, r15
0x1800145e4  mov     [rsp+78h+var_58], rdi
0x1800145e9  call    McTemplateU0sppd_EtwWriteTransfer
0x1800145ee  jmp     loc_1800144C0
0x1800145f3  mov     rbx, [r15+0F8h]
0x1800145fa  movsx   edi, byte ptr [rbx+4]
0x1800145fe  movzx   ecx, dil; IrpMajorCode
0x180014602  call    FltGetIrpName
0x180014607  movsx   ecx, byte ptr [rbx+5]
0x18001460b  lea     r8, aFltplinkcomple; "FltpLinkCompletionNodeToInstance"
0x180014612  mov     [rsp+78h+var_48], r15
0x180014617  lea     rdx, CompletionNodeSup_c559
0x18001461e  mov     [rsp+78h+var_50], rax
0x180014623  mov     r9d, edi
0x180014626  mov     dword ptr [rsp+78h+var_58], ecx
0x18001462a  call    McTemplateU0sddsp_EtwWriteTransfer
0x18001462f  jmp     loc_1800144F1
0x180025ef0  lea     rax, [rdi+10h]
0x180025ef4  mov     [rax], r14
0x180025ef7  mov     [rax+8], rcx
0x180025efb  mov     [rcx], rax
0x180025efe  mov     [r14+8], rax
0x180025f02  or      word ptr [rdi+78h], 4
0x180025f07  mov     eax, [r15+0E8h]
0x180025f0e  test    al, 1
0x180025f10  jz      short loc_180025F5D
0x180025f12  mov     rax, [r15+30h]
0x180025f16  mov     byte ptr [rax+44h], 1
0x180025f1a  test    cs:byte_180040A41, 20h
0x180025f21  jz      loc_1800144F1
0x180025f27  mov     rbx, [r15+0F8h]
0x180025f2e  movsx   edi, byte ptr [rbx+4]
0x180025f32  movzx   ecx, dil; IrpMajorCode
0x180025f36  call    FltGetIrpName
0x180025f3b  movsx   ecx, byte ptr [rbx+5]
0x180025f3f  lea     rdx, CompletionNodeSup_c506
0x180025f46  mov     [rsp+78h+var_50], rax
0x180025f4b  mov     r9d, edi
0x180025f4e  mov     dword ptr [rsp+78h+var_58], ecx
0x180025f52  call    McTemplateU0sdds_EtwWriteTransfer
0x180025f57  nop
0x180025f58  jmp     loc_1800144F1
0x180025f5d  test    cs:byte_180040A41, 20h
0x180025f64  jz      loc_1800144F1
0x180025f6a  mov     rbx, [r15+0F8h]
0x180025f71  movsx   edi, byte ptr [rbx+4]
0x180025f75  movzx   ecx, dil; IrpMajorCode
0x180025f79  call    FltGetIrpName
0x180025f7e  movsx   ecx, byte ptr [rbx+5]
0x180025f82  lea     rdx, CompletionNodeSup_c514
0x180025f89  mov     [rsp+78h+var_50], rax
0x180025f8e  mov     r9d, edi
0x180025f91  mov     dword ptr [rsp+78h+var_58], ecx
0x180025f95  call    McTemplateU0sdds_EtwWriteTransfer
0x180025f9a  nop
0x180025f9b  jmp     loc_1800144F1
0x180025fa0  lea     r8, [rsp+78h+LockHandle]
0x180025fa5  mov     rdx, rdi
0x180025fa8  mov     rcx, rsi
0x180025fab  call    DrainCompletionNode
0x180025fb0  nop
0x180025fb1  jmp     loc_180014502
```
