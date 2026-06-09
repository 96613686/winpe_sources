# NpTransceive

- ea: `0x140010890`
- end: `0x140010d10`
- name: `NpTransceive`
- size: `1152`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000efb0`

## callees

- `0x140001ad4`
- `0x140001e40`
- `0x14000d314`
- `0x14000deb8`
- `0x140010890`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010b0d`
- `ntoskrnl!ExAllocatePool2` at `0x140010b0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010987`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010987`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b2b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b95`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010ce0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b2b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b95`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010ce0`
- `ntoskrnl!ProbeForWrite` at `0x140010912`
- `ntoskrnl!ProbeForWrite` at `0x140010912`
- `ntoskrnl!IoFreeIrp` at `0x140010b3a`
- `ntoskrnl!IoFreeIrp` at `0x140010bc2`
- `ntoskrnl!IoFreeIrp` at `0x140010b3a`
- `ntoskrnl!IoFreeIrp` at `0x140010bc2`
- `ntoskrnl!IoAllocateIrp` at `0x140010a8a`
- `ntoskrnl!IoAllocateIrp` at `0x140010a8a`
- `ntoskrnl!ProbeForRead` at `0x1400108fa`
- `ntoskrnl!ProbeForRead` at `0x1400108fa`

## pseudocode

```c
__int64 __fastcall NpTransceive(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  unsigned int v6; // r15d
  char *v7; // rcx
  unsigned int v8; // r14d
  volatile void *v9; // rdi
  __int64 v10; // rbx
  unsigned __int64 v11; // r14
  __int64 v12; // r12
  int v13; // ebx
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // ecx
  int v18; // edi
  PIRP v19; // rax
  IRP *v20; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v22; // rax
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r15
  size_t v24; // rbx
  struct _IRP *Pool2; // rcx
  char *v27; // rdx
  struct _IO_STACK_LOCATION *v28; // rcx
  int v29; // eax
  struct _LIST_ENTRY *v30; // rdx
  size_t v31; // [rsp+28h] [rbp-C0h]
  unsigned int Size; // [rsp+64h] [rbp-84h] BYREF
  unsigned int Size_4; // [rsp+68h] [rbp-80h]
  size_t v34; // [rsp+70h] [rbp-78h]
  unsigned __int64 v35; // [rsp+78h] [rbp-70h]
  char *v36; // [rsp+80h] [rbp-68h]
  struct _KTHREAD *v37; // [rsp+88h] [rbp-60h]
  unsigned __int64 v38; // [rsp+90h] [rbp-58h]
  int v39[2]; // [rsp+98h] [rbp-50h]
  struct _IO_STACK_LOCATION *v40; // [rsp+A0h] [rbp-48h]
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *v41; // [rsp+A8h] [rbp-40h]
  PIRP Irp; // [rsp+B0h] [rbp-38h]
  int v43[12]; // [rsp+B8h] [rbp-30h]
  __int64 v45; // [rsp+F8h] [rbp+10h]
  char v46; // [rsp+108h] [rbp+20h]

  v45 = a2;
  Size = 0;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(_DWORD *)(v5 + 16);
  Size_4 = v6;
  v7 = *(char **)(v5 + 32);
  v36 = v7;
  v8 = *(_DWORD *)(v5 + 8);
  LODWORD(v34) = v8;
  v9 = *(volatile void **)(a2 + 112);
  v46 = *(_BYTE *)(a2 + 64);
  if ( v46 )
  {
    ProbeForRead(v7, v6, 1u);
    ProbeForWrite(v9, v8, 1u);
    a2 = v45;
  }
  v10 = *(_QWORD *)(v5 + 48);
  if ( (*(_QWORD *)(v10 + 32) & 1) != 0 && **(_WORD **)(v10 + 24) == 514 )
  {
    v11 = *(_QWORD *)(v10 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
    v12 = (*(_QWORD *)(v10 + 32) >> 1) & 1LL;
    *(_QWORD *)v39 = v12;
    v37 = *(struct _KTHREAD **)(a2 + 152);
    v35 = v11 + 64;
    ExAcquirePushLockExclusiveEx(v11 + 64, 0, a3, a4);
    if ( (*(_QWORD *)(v10 + 32) & 1) != 0 )
    {
      if ( *(_BYTE *)(v11 + 8) != 3
        || (v14 = (_DWORD)v12 != 0 ? 168LL : 72LL,
            v15 = (-(__int64)((_DWORD)v12 != 0) & 0xFFFFFFFFFFFFFFA0uLL) + 168,
            v16 = *(_QWORD *)(v11 + 40),
            (unsigned __int16)*(_DWORD *)(v16 + 256) != 2)
        || (v17 = *(_BYTE *)(v12 + v11 + 9) & 1, (*(_BYTE *)(v12 + v11 + 9) & 1) == 0) )
      {
        v13 = -1073741651;
        goto LABEL_33;
      }
      v18 = v15 + v11;
      v38 = v15 + v11;
      if ( *(_DWORD *)(v15 + v11 + 16) == 2 )
      {
        *(_QWORD *)v43 = v14 + v11;
        v13 = NpWriteDataQueue(
                (int)v14 + (int)v11,
                v17,
                (_DWORD)v36,
                v6,
                v46,
                *(_DWORD *)(v16 + 260),
                (__int64)&Size,
                v11,
                v12,
                (__int64)v37,
                a3);
        if ( v13 == -1073741802 )
        {
          v19 = IoAllocateIrp(*(_BYTE *)(a1 + 76), 1u);
          v20 = v19;
          Irp = v19;
          if ( !v19 )
          {
            v13 = -1073741670;
            goto LABEL_33;
          }
          CurrentStackLocation = v19->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&NpCompleteTransceiveIrp;
          CurrentStackLocation[-1].Context = 0;
          CurrentStackLocation[-1].Control = -32;
          v22 = v20->Tail.Overlay.CurrentStackLocation;
          v40 = v22;
          p_AssociatedIrp = &v20->AssociatedIrp;
          v41 = &v20->AssociatedIrp;
          v24 = Size;
          if ( Size )
          {
            Pool2 = (struct _IRP *)ExAllocatePool2(257, Size, 2001104974);
            p_AssociatedIrp->MasterIrp = Pool2;
            if ( !Pool2 )
            {
              ExReleasePushLockExclusiveEx(v35, 0);
              IoFreeIrp(v20);
              return 3221225626LL;
            }
            v27 = &v36[Size_4 - (unsigned int)v24];
            if ( v46 )
              RtlCopyFromUser(Pool2, v27, v24);
            else
              RtlCopyVolatileMemory(Pool2, v27, v24);
            LODWORD(v12) = v39[0];
            v22 = v40;
          }
          else
          {
            p_AssociatedIrp->MasterIrp = 0;
          }
          v28 = v22 - 1;
          --v20->CurrentLocation;
          v20->Tail.Overlay.CurrentStackLocation = v22 - 1;
          v20->Tail.Overlay.Thread = v37;
          v20->IoStatus.Information = v24;
          v28->Parameters.Read.Length = v24;
          v28->MajorFunction = 4;
          if ( (_DWORD)v24 )
            v20->Flags = 48;
          v20->UserIosb = (PIO_STATUS_BLOCK)qword_1400060A0;
          LODWORD(v31) = v24;
          v29 = NpAddDataQueueEntry(v12, v11, v43[0], 1, 1, v31, (__int64)v20, 0, 0);
          v13 = v29;
          if ( v29 != 259 )
          {
            v20->IoStatus.Status = v29;
            v30 = *(struct _LIST_ENTRY **)(a3 + 8);
            if ( v30->Flink != (struct _LIST_ENTRY *)a3 )
              __fastfail(3u);
            v20->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)a3;
            v20->Tail.Overlay.ListEntry.Blink = v30;
            v30->Flink = &v20->Tail.Overlay.ListEntry;
            *(_QWORD *)(a3 + 8) = &v20->Tail.Overlay.ListEntry;
          }
          v18 = v38;
        }
        if ( v13 >= 0 )
        {
          LODWORD(v31) = v34;
          v13 = NpAddDataQueueEntry(v12, v11, v18, 0, 0, v31, v45, 0, 0);
        }
        goto LABEL_33;
      }
      v13 = -1073741650;
    }
    else
    {
      v13 = -1073741648;
    }
LABEL_33:
    ExReleasePushLockExclusiveEx(v35, 0);
    return (unsigned int)v13;
  }
  return 3221225648LL;
}

```

## disassembly

```asm
0x140010890  mov     [rsp+arg_10], rbx
0x140010895  mov     [rsp+arg_8], rdx
0x14001089a  mov     [rsp+arg_0], rcx
0x14001089f  push    rdi
0x1400108a0  push    r12
0x1400108a2  push    r13
0x1400108a4  push    r14
0x1400108a6  push    r15
0x1400108a8  sub     rsp, 0C0h
0x1400108af  mov     r13, r8
0x1400108b2  mov     dword ptr [rsp+0E8h+Size], 0
0x1400108ba  mov     rbx, [rdx+0B8h]
0x1400108c1  mov     r15d, [rbx+10h]
0x1400108c5  mov     dword ptr [rsp+0E8h+Size+4], r15d
0x1400108ca  mov     rcx, [rbx+20h]; Address
0x1400108ce  mov     [rsp+0E8h+var_68], rcx
0x1400108d6  mov     r14d, [rbx+8]
0x1400108da  mov     dword ptr [rsp+0E8h+var_78], r14d
0x1400108df  mov     rdi, [rdx+70h]
0x1400108e3  mov     al, [rdx+40h]
0x1400108e6  mov     [rsp+0E8h+arg_18], al
0x1400108ed  test    al, al
0x1400108ef  jz      short loc_14001092D
0x1400108f1  mov     edx, r15d; Length
0x1400108f4  mov     r8d, 1; Alignment
0x1400108fa  call    cs:__imp_ProbeForRead
0x140010901  nop     dword ptr [rax+rax+00h]
0x140010906  mov     edx, r14d; Length
0x140010909  mov     r8d, 1; Alignment
0x14001090f  mov     rcx, rdi; Address
0x140010912  call    cs:__imp_ProbeForWrite
0x140010919  nop     dword ptr [rax+rax+00h]
0x14001091e  mov     rdx, [rsp+0E8h+arg_8]
0x140010926  jmp     short loc_14001092D
0x140010928  jmp     loc_140010CF6
0x14001092d  mov     rbx, [rbx+30h]
0x140010931  mov     rax, [rbx+20h]
0x140010935  test    al, 1
0x140010937  jz      loc_140010CF1
0x14001093d  mov     rax, [rbx+18h]
0x140010941  mov     ecx, 202h
0x140010946  cmp     [rax], cx
0x140010949  jnz     loc_140010CF1
0x14001094f  mov     r14, [rbx+20h]
0x140010953  and     r14, 0FFFFFFFFFFFFFFFCh
0x140010957  mov     r12, [rbx+20h]
0x14001095b  shr     r12, 1
0x14001095e  and     r12d, 1
0x140010962  mov     qword ptr [rsp+0E8h+var_50], r12
0x14001096a  mov     rax, [rdx+98h]
0x140010971  mov     [rsp+0E8h+var_60], rax
0x140010979  lea     rax, [r14+40h]
0x14001097d  mov     [rsp+0E8h+var_70], rax
0x140010982  xor     edx, edx
0x140010984  mov     rcx, rax
0x140010987  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001098e  nop     dword ptr [rax+rax+00h]
0x140010993  mov     rax, [rbx+20h]
0x140010997  test    al, 1
0x140010999  jnz     short loc_1400109A5
0x14001099b  mov     ebx, 0C00000B0h
0x1400109a0  jmp     loc_140010CD9
0x1400109a5  cmp     byte ptr [r14+8], 3
0x1400109aa  jnz     loc_140010CD4
0x1400109b0  mov     eax, r12d
0x1400109b3  neg     eax
0x1400109b5  sbb     r8, r8
0x1400109b8  and     r8d, 60h
0x1400109bc  add     r8, 48h ; 'H'
0x1400109c0  mov     eax, r12d
0x1400109c3  neg     eax
0x1400109c5  sbb     rdx, rdx
0x1400109c8  and     rdx, 0FFFFFFFFFFFFFFA0h
0x1400109cc  add     rdx, 0A8h
0x1400109d3  mov     r9, [r14+28h]
0x1400109d7  mov     eax, [r9+100h]
0x1400109de  cmp     ax, 2
0x1400109e2  jnz     loc_140010CD4
0x1400109e8  movzx   ecx, byte ptr [r12+r14+9]
0x1400109ee  and     ecx, 1
0x1400109f1  jz      loc_140010CD4
0x1400109f7  lea     rdi, [rdx+r14]
0x1400109fb  mov     [rsp+0E8h+var_58], rdi
0x140010a03  cmp     dword ptr [rdi+10h], 2
0x140010a07  jz      short loc_140010A13
0x140010a09  mov     ebx, 0C00000AEh
0x140010a0e  jmp     loc_140010CD9
0x140010a13  lea     r10, [r8+r14]
0x140010a17  mov     qword ptr [rsp+0E8h+var_30], r10
0x140010a1f  mov     [rsp+0E8h+var_98], r13
0x140010a24  mov     rax, [rsp+0E8h+var_60]
0x140010a2c  mov     [rsp+0E8h+var_A0], rax
0x140010a31  mov     [rsp+0E8h+var_A8], r12d
0x140010a36  mov     [rsp+0E8h+Src], r14
0x140010a3b  lea     rax, [rsp+0E8h+Size]
0x140010a40  mov     [rsp+0E8h+var_B8], rax
0x140010a45  mov     eax, [r9+104h]
0x140010a4c  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140010a50  mov     al, [rsp+0E8h+arg_18]
0x140010a57  mov     byte ptr [rsp+0E8h+var_C8], al
0x140010a5b  mov     r9d, r15d
0x140010a5e  mov     r8, [rsp+0E8h+var_68]
0x140010a66  mov     edx, ecx
0x140010a68  mov     rcx, r10
0x140010a6b  call    NpWriteDataQueue
0x140010a70  mov     ebx, eax
0x140010a72  cmp     eax, 0C0000016h
0x140010a77  jnz     loc_140010C8D
0x140010a7d  mov     dl, 1; ChargeQuota
0x140010a7f  mov     rcx, [rsp+0E8h+arg_0]
0x140010a87  mov     cl, [rcx+4Ch]; StackSize
0x140010a8a  call    cs:__imp_IoAllocateIrp
0x140010a91  nop     dword ptr [rax+rax+00h]
0x140010a96  mov     rdi, rax
0x140010a99  mov     [rsp+0E8h+Irp], rax
0x140010aa1  test    rax, rax
0x140010aa4  jnz     short loc_140010AB0
0x140010aa6  mov     ebx, 0C000009Ah
0x140010aab  jmp     loc_140010CD9
0x140010ab0  mov     rax, [rax+0B8h]
0x140010ab7  lea     rcx, NpCompleteTransceiveIrp
0x140010abe  mov     [rax-10h], rcx
0x140010ac2  mov     qword ptr [rax-8], 0
0x140010aca  mov     byte ptr [rax-45h], 0E0h
0x140010ace  mov     rax, [rdi+0B8h]
0x140010ad5  mov     [rsp+0E8h+var_48], rax
0x140010add  lea     r15, [rdi+18h]
0x140010ae1  mov     [rsp+0E8h+var_40], r15
0x140010ae9  mov     ebx, dword ptr [rsp+0E8h+Size]
0x140010aed  test    ebx, ebx
0x140010aef  jz      loc_140010BD5
0x140010af5  mov     al, [rsp+0E8h+arg_18]
0x140010afc  mov     [rsp+0E8h+var_88], al
0x140010b00  mov     r8d, 7746704Eh
0x140010b06  mov     edx, ebx
0x140010b08  mov     ecx, 101h
0x140010b0d  call    cs:__imp_ExAllocatePool2
0x140010b14  nop     dword ptr [rax+rax+00h]
0x140010b19  mov     rcx, rax; void *
0x140010b1c  mov     [r15], rax
0x140010b1f  test    rax, rax
0x140010b22  jnz     short loc_140010B50
0x140010b24  xor     edx, edx
0x140010b26  mov     rcx, [rsp+0E8h+var_70]
0x140010b2b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010b32  nop     dword ptr [rax+rax+00h]
0x140010b37  mov     rcx, rdi; Irp
0x140010b3a  call    cs:__imp_IoFreeIrp
0x140010b41  nop     dword ptr [rax+rax+00h]
0x140010b46  mov     eax, 0C000009Ah
0x140010b4b  jmp     loc_140010CF6
0x140010b50  mov     eax, dword ptr [rsp+0E8h+Size+4]
0x140010b54  sub     eax, ebx
0x140010b56  mov     rdx, [rsp+0E8h+var_68]
0x140010b5e  add     rdx, rax; Src
0x140010b61  mov     r8, rbx; Size
0x140010b64  cmp     [rsp+0E8h+arg_18], 0
0x140010b6c  jz      short loc_140010B75
0x140010b6e  call    RtlCopyFromUser
0x140010b73  jmp     short loc_140010B7A
0x140010b75  call    RtlCopyVolatileMemory
0x140010b7a  mov     r12, qword ptr [rsp+0E8h+var_50]
0x140010b82  mov     rax, [rsp+0E8h+var_48]
0x140010b8a  jmp     short loc_140010BDC
0x140010b8c  mov     ebx, eax
0x140010b8e  xor     edx, edx
0x140010b90  mov     rcx, [rsp+0E8h+var_70]
0x140010b95  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010b9c  nop     dword ptr [rax+rax+00h]
0x140010ba1  xor     edx, edx; Tag
0x140010ba3  mov     rcx, [rsp+0E8h+var_40]
0x140010bab  mov     rcx, [rcx]; P
0x140010bae  call    cs:__imp_ExFreePoolWithTag
0x140010bb5  nop     dword ptr [rax+rax+00h]
0x140010bba  mov     rcx, [rsp+0E8h+Irp]; Irp
0x140010bc2  call    cs:__imp_IoFreeIrp
0x140010bc9  nop     dword ptr [rax+rax+00h]
0x140010bce  mov     eax, ebx
0x140010bd0  jmp     loc_140010CF6
0x140010bd5  mov     qword ptr [r15], 0
0x140010bdc  lea     rcx, [rax-48h]
0x140010be0  dec     byte ptr [rdi+43h]
0x140010be3  mov     [rdi+0B8h], rcx
0x140010bea  mov     rax, [rsp+0E8h+var_60]
0x140010bf2  mov     [rdi+98h], rax
0x140010bf9  mov     [rdi+38h], rbx
0x140010bfd  mov     [rcx+8], ebx
0x140010c00  mov     byte ptr [rcx], 4
0x140010c03  test    ebx, ebx
0x140010c05  jz      short loc_140010C0E
0x140010c07  mov     dword ptr [rdi+10h], 30h ; '0'
0x140010c0e  lea     rax, qword_1400060A0
0x140010c15  mov     [rdi+48h], rax
0x140010c19  mov     [rsp+0E8h+var_A8], 0; int
0x140010c21  mov     [rsp+0E8h+Src], 0; Src
0x140010c2a  mov     [rsp+0E8h+var_B8], rdi; __int64
0x140010c2f  mov     dword ptr [rsp+0E8h+var_C0], ebx; Size
0x140010c33  mov     [rsp+0E8h+var_C8], 1; int
0x140010c3b  mov     r9d, 1; int
0x140010c41  mov     r8, qword ptr [rsp+0E8h+var_30]; int
0x140010c49  mov     rdx, r14; int
0x140010c4c  mov     ecx, r12d; int
0x140010c4f  call    NpAddDataQueueEntry
0x140010c54  mov     ebx, eax
0x140010c56  cmp     eax, 103h
0x140010c5b  jz      short loc_140010C85
0x140010c5d  mov     [rdi+30h], eax
0x140010c60  mov     rdx, [r13+8]
0x140010c64  cmp     [rdx], r13
0x140010c67  jz      short loc_140010C70
0x140010c69  mov     ecx, 3
0x140010c6e  int     29h; Win8: RtlFailFast(ecx)
0x140010c70  lea     rax, [rdi+0A8h]
0x140010c77  mov     [rax], r13
0x140010c7a  mov     [rax+8], rdx
0x140010c7e  mov     [rdx], rax
0x140010c81  mov     [r13+8], rax
0x140010c85  mov     rdi, [rsp+0E8h+var_58]
0x140010c8d  test    ebx, ebx
0x140010c8f  js      short loc_140010CD9
0x140010c91  mov     [rsp+0E8h+var_A8], 0; int
0x140010c99  mov     [rsp+0E8h+Src], 0; Src
0x140010ca2  mov     rax, [rsp+0E8h+arg_8]
0x140010caa  mov     [rsp+0E8h+var_B8], rax; __int64
0x140010caf  mov     eax, dword ptr [rsp+0E8h+var_78]
0x140010cb3  mov     dword ptr [rsp+0E8h+var_C0], eax; Size
0x140010cb7  mov     [rsp+0E8h+var_C8], 0; int
0x140010cbf  xor     r9d, r9d; int
0x140010cc2  mov     r8, rdi; int
0x140010cc5  mov     rdx, r14; int
0x140010cc8  mov     ecx, r12d; int
0x140010ccb  call    NpAddDataQueueEntry
0x140010cd0  mov     ebx, eax
0x140010cd2  jmp     short loc_140010CD9
0x140010cd4  mov     ebx, 0C00000ADh
0x140010cd9  xor     edx, edx
0x140010cdb  mov     rcx, [rsp+0E8h+var_70]
0x140010ce0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010ce7  nop     dword ptr [rax+rax+00h]
0x140010cec  jmp     loc_140010BCE
0x140010cf1  mov     eax, 0C00000B0h
0x140010cf6  mov     rbx, [rsp+0E8h+arg_10]
0x140010cfe  add     rsp, 0C0h
0x140010d05  pop     r15
0x140010d07  pop     r14
0x140010d09  pop     r13
0x140010d0b  pop     r12
0x140010d0d  pop     rdi
0x140010d0e  retn
0x14001667a  push    rbp
0x14001667c  sub     rsp, 60h
0x140016680  mov     rbp, rdx
0x140016683  xor     eax, eax
0x140016685  cmp     [rbp+60h], al
0x140016688  setnz   al
0x14001668b  mov     [rbp+6Ch], eax
0x14001668e  mov     eax, [rbp+6Ch]
0x140016691  add     rsp, 60h
0x140016695  pop     rbp
0x140016696  retn
```
