# Smb2ValidateSrvOpenRestrictions

- ea: `0x14000a570`
- end: `0x14000a98b`
- name: `Smb2ValidateSrvOpenRestrictions`
- size: `1051`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140008ec0`
- `0x140008f20`

## callees

- `0x14000a570`
- `0x140029764`
- `0x140029840`
- `0x140029df0`
- `0x14002a0b0`
- `0x14002a6a8`
- `0x14002a850`
- `0x14002a8e0`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14000a708`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14000a708`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000a84a`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000a84a`
- `ntoskrnl!PsGetProcessId` at `0x14000a888`
- `ntoskrnl!PsGetProcessId` at `0x14000a888`
- `ntoskrnl!SeLocateProcessImageName` at `0x14000a8a2`
- `ntoskrnl!SeLocateProcessImageName` at `0x14000a8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a927`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a927`
- `mrxsmb!SmbCeIsServerTrustedZoneRunOnce` at `0x14000a6f4`

## pseudocode

```c
__int64 __fastcall Smb2ValidateSrvOpenRestrictions(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // edi
  int v9; // eax
  unsigned int v10; // esi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  NTSTATUS v13; // eax
  bool v14; // di
  char v15; // al
  IRP *v16; // rcx
  struct _KPROCESS *RequestorProcess; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int16 v20; // di
  __int64 v21; // r15
  __int64 v22; // r14
  char ProcessId; // r12
  NTSTATUS v24; // eax
  BOOL v25; // edx
  PWSTR Buffer; // r8
  int Length; // r9d
  __int64 Timer_high; // rdx
  PUNICODE_STRING pImageFileName; // [rsp+A8h] [rbp+10h] BYREF

  v4 = *(unsigned __int8 *)(a3 + 469);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqqdddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int8 *)(a3 + 465),
      (*(unsigned __int8 *)(a2 + 328) >> 1) & 1,
      a1,
      a2,
      a3,
      a4,
      *(unsigned __int8 *)(a3 + 465),
      *(unsigned __int8 *)(a3 + 466),
      *(_BYTE *)(a2 + 328) & 1,
      (*(unsigned __int8 *)(a2 + 328) >> 1) & 1,
      (*(unsigned __int8 *)(a2 + 328) >> 2) & 1,
      v4);
  }
  v9 = *(_DWORD *)(a2 + 8);
  if ( (v9 & 0x800) != 0 && !*(_BYTE *)(a3 + 466) )
  {
    v10 = -1073741311;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 11;
LABEL_11:
      WPP_SF_qD(v11->AttachedDevice, v12, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, a1, -1073741311);
      return v10;
    }
    return v10;
  }
  if ( (v9 & 0x600) == 0 || (*(_BYTE *)(a3 + 4) & 3) == 0 )
  {
    v10 = 0;
    if ( !*(_BYTE *)(a3 + 465) || *(_BYTE *)(a3 + 466) || (_BYTE)v4 )
      return v10;
    if ( (*(_BYTE *)(a2 + 328) & 3) == 2 )
    {
      v13 = RtlRunOnceExecuteOnce((PRTL_RUN_ONCE)(a3 + 472), SmbCeIsServerTrustedZoneRunOnce, (PVOID)a3, 0);
      v14 = *(_BYTE *)(a3 + 480) == 0;
      if ( v13 >= 0 )
      {
LABEL_27:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            a2,
            a4,
            v14);
        }
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            (unsigned int)v13);
        goto LABEL_27;
      }
    }
    else
    {
      v14 = 1;
    }
LABEL_32:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Zqqqqddd(
        WPP_GLOBAL_Control->AttachedDevice,
        (*(unsigned __int8 *)(a2 + 328) >> 2) & 1,
        *(_BYTE *)(a2 + 328) & 1,
        *(_QWORD *)(a3 + 384) + 128,
        a1,
        a2,
        a3,
        a4,
        *(_BYTE *)(a2 + 328) & 1,
        (*(_BYTE *)(a2 + 328) & 2) != 0,
        (*(_BYTE *)(a2 + 328) & 4) != 0);
    }
    v15 = *(_BYTE *)(a2 + 328);
    if ( (v15 & 1) != 0 || (v15 & 2) != 0 && v14 )
    {
      if ( (v15 & 4) != 0 )
      {
        v16 = *(IRP **)(a1 + 40);
        if ( v16 && (v16->RequestorMode || (v16->Tail.Overlay.CurrentStackLocation->Flags & 1) != 0) )
        {
          RequestorProcess = IoGetRequestorProcess(v16);
          if ( RequestorProcess )
          {
            v18 = *(_QWORD *)(a4 + 88);
            pImageFileName = 0;
            v19 = *(_QWORD *)(v18 + 424);
            v20 = *(_WORD *)(v19 + 96);
            v21 = *(_QWORD *)(v19 + 104);
            v22 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 80LL);
            ProcessId = (unsigned __int8)PsGetProcessId(RequestorProcess);
            v24 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
            if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 0x10) != 0 )
            {
              if ( v24 < 0 )
              {
                Length = 0;
                Buffer = 0;
              }
              else
              {
                Length = pImageFileName->Length;
                Buffer = pImageFileName->Buffer;
                LOWORD(Length) = (unsigned __int16)Length >> 1;
              }
              v25 = (*(_BYTE *)(a2 + 328) & 1) == 0;
              McTemplateK0hzr0qqhzr4hzr6_EtwWriteTransfer(
                *(_WORD *)v22 >> 1,
                v25,
                (_DWORD)Buffer,
                Length,
                (__int64)Buffer,
                ProcessId,
                v25,
                v20 >> 1,
                v21,
                *(_WORD *)v22 >> 1,
                *(_QWORD *)(v22 + 8));
            }
            if ( pImageFileName )
              ExFreePoolWithTag(pImageFileName, 0);
          }
        }
      }
      else
      {
        v10 = -1067646964;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 1) != 0 )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) )
              WPP_SF_qqqqD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, a3, a1, a2, a3, a4);
          }
        }
      }
    }
    return v10;
  }
  v10 = -1073741311;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v12 = 12;
    goto LABEL_11;
  }
  return v10;
}

```

## disassembly

```asm
0x14000a570  mov     [rsp+arg_0], rbx
0x14000a575  mov     [rsp+arg_10], rbp
0x14000a57a  push    rsi
0x14000a57b  push    rdi
0x14000a57c  push    r12
0x14000a57e  push    r14
0x14000a580  push    r15
0x14000a582  sub     rsp, 70h
0x14000a586  movzx   edi, byte ptr [r8+1D5h]
0x14000a58e  mov     r15, r9
0x14000a591  mov     rbx, r8
0x14000a594  mov     rbp, rdx
0x14000a597  mov     r14, rcx
0x14000a59a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a5a1  lea     r12, WPP_GLOBAL_Control
0x14000a5a8  cmp     rcx, r12
0x14000a5ab  jz      short loc_14000A61F
0x14000a5ad  mov     eax, [rcx+2Ch]
0x14000a5b0  test    al, 10h
0x14000a5b2  jz      short loc_14000A61F
0x14000a5b4  cmp     byte ptr [rcx+29h], 4
0x14000a5b8  jb      short loc_14000A61F
0x14000a5ba  movzx   r11d, byte ptr [rdx+148h]
0x14000a5c2  movzx   eax, byte ptr [rbx+1D2h]
0x14000a5c9  mov     r10d, r11d
0x14000a5cc  movzx   edx, byte ptr [rbx+1D1h]
0x14000a5d3  mov     r8d, r11d
0x14000a5d6  mov     rcx, [rcx+18h]
0x14000a5da  and     r11d, 1
0x14000a5de  mov     [rsp+98h+var_38], edi
0x14000a5e2  shr     r10d, 2
0x14000a5e6  shr     r8d, 1
0x14000a5e9  and     r10d, 1
0x14000a5ed  mov     [rsp+98h+var_40], r10d
0x14000a5f2  and     r8d, 1
0x14000a5f6  mov     dword ptr [rsp+98h+var_48], r8d
0x14000a5fb  mov     [rsp+98h+var_50], r11d
0x14000a600  mov     dword ptr [rsp+98h+var_58], eax
0x14000a604  mov     dword ptr [rsp+98h+var_60], edx
0x14000a608  mov     [rsp+98h+var_68], r9
0x14000a60d  mov     r9, r14
0x14000a610  mov     [rsp+98h+var_70], rbx
0x14000a615  mov     [rsp+98h+var_78], rbp
0x14000a61a  call    WPP_SF_qqqqdddddd
0x14000a61f  mov     eax, [rbp+8]
0x14000a622  bt      eax, 0Bh
0x14000a626  jnb     short loc_14000A680
0x14000a628  cmp     byte ptr [rbx+1D2h], 0
0x14000a62f  jnz     short loc_14000A680
0x14000a631  mov     esi, 0C0000201h
0x14000a636  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a63d  cmp     rcx, r12
0x14000a640  jz      loc_14000A96F
0x14000a646  mov     eax, [rcx+2Ch]
0x14000a649  test    al, 1
0x14000a64b  jz      loc_14000A96F
0x14000a651  cmp     byte ptr [rcx+29h], 1
0x14000a655  jb      loc_14000A96F
0x14000a65b  mov     edx, 0Bh
0x14000a660  mov     rcx, [rcx+18h]
0x14000a664  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x14000a66b  mov     r9, r14
0x14000a66e  mov     dword ptr [rsp+98h+var_78], 0C0000201h
0x14000a676  call    WPP_SF_qD
0x14000a67b  jmp     loc_14000A96F
0x14000a680  test    eax, 600h
0x14000a685  jz      short loc_14000A6BE
0x14000a687  test    byte ptr [rbx+4], 3
0x14000a68b  jz      short loc_14000A6BE
0x14000a68d  mov     esi, 0C0000201h
0x14000a692  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a699  cmp     rcx, r12
0x14000a69c  jz      loc_14000A96F
0x14000a6a2  mov     eax, [rcx+2Ch]
0x14000a6a5  test    al, 1
0x14000a6a7  jz      loc_14000A96F
0x14000a6ad  cmp     byte ptr [rcx+29h], 1
0x14000a6b1  jb      loc_14000A96F
0x14000a6b7  mov     edx, 0Ch
0x14000a6bc  jmp     short loc_14000A660
0x14000a6be  xor     esi, esi
0x14000a6c0  cmp     [rbx+1D1h], sil
0x14000a6c7  jz      loc_14000A96F
0x14000a6cd  cmp     [rbx+1D2h], sil
0x14000a6d4  jnz     loc_14000A96F
0x14000a6da  test    dil, dil
0x14000a6dd  jnz     loc_14000A96F
0x14000a6e3  movzx   eax, byte ptr [rbp+148h]
0x14000a6ea  and     al, 3
0x14000a6ec  cmp     al, 2
0x14000a6ee  jnz     loc_14000A794
0x14000a6f4  mov     rdx, cs:__imp_SmbCeIsServerTrustedZoneRunOnce; InitFn
0x14000a6fb  lea     rcx, [rbx+1D8h]; RunOnce
0x14000a702  xor     r9d, r9d; Context
0x14000a705  mov     r8, rbx; Parameter
0x14000a708  call    cs:__imp_RtlRunOnceExecuteOnce
0x14000a70f  nop     dword ptr [rax+rax+00h]
0x14000a714  cmp     [rbx+1E0h], sil
0x14000a71b  mov     r9d, eax
0x14000a71e  setz    dil
0x14000a722  test    eax, eax
0x14000a724  jns     short loc_14000A754
0x14000a726  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a72d  cmp     rcx, r12
0x14000a730  jz      short loc_14000A797
0x14000a732  mov     eax, [rcx+2Ch]
0x14000a735  test    al, 1
0x14000a737  jz      short loc_14000A754
0x14000a739  cmp     byte ptr [rcx+29h], 1
0x14000a73d  jb      short loc_14000A754
0x14000a73f  mov     rcx, [rcx+18h]
0x14000a743  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x14000a74a  mov     edx, 0Dh
0x14000a74f  call    WPP_SF_d
0x14000a754  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a75b  cmp     rcx, r12
0x14000a75e  jz      short loc_14000A797
0x14000a760  mov     eax, [rcx+2Ch]
0x14000a763  test    al, 10h
0x14000a765  jz      short loc_14000A797
0x14000a767  cmp     byte ptr [rcx+29h], 2
0x14000a76b  jb      short loc_14000A797
0x14000a76d  mov     rcx, [rcx+18h]
0x14000a771  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x14000a778  movzx   eax, dil
0x14000a77c  mov     edx, 0Eh
0x14000a781  mov     dword ptr [rsp+98h+var_70], eax
0x14000a785  mov     r9, rbp
0x14000a788  mov     [rsp+98h+var_78], r15
0x14000a78d  call    WPP_SF_qqD
0x14000a792  jmp     short loc_14000A797
0x14000a794  mov     dil, 1
0x14000a797  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a79e  cmp     rcx, r12
0x14000a7a1  jz      short loc_14000A802
0x14000a7a3  mov     eax, [rcx+2Ch]
0x14000a7a6  test    al, 10h
0x14000a7a8  jz      short loc_14000A802
0x14000a7aa  cmp     byte ptr [rcx+29h], 2
0x14000a7ae  jb      short loc_14000A802
0x14000a7b0  movzx   r8d, byte ptr [rbp+148h]
0x14000a7b8  mov     r9, [rbx+180h]
0x14000a7bf  mov     edx, r8d
0x14000a7c2  mov     rcx, [rcx+18h]
0x14000a7c6  mov     eax, r8d
0x14000a7c9  shr     edx, 2
0x14000a7cc  and     r8d, 1
0x14000a7d0  shr     eax, 1
0x14000a7d2  and     edx, 1
0x14000a7d5  mov     dword ptr [rsp+98h+var_48], edx
0x14000a7d9  and     eax, 1
0x14000a7dc  mov     [rsp+98h+var_50], eax
0x14000a7e0  sub     r9, 0FFFFFFFFFFFFFF80h
0x14000a7e4  mov     dword ptr [rsp+98h+var_58], r8d
0x14000a7e9  mov     [rsp+98h+var_60], r15
0x14000a7ee  mov     [rsp+98h+var_68], rbx
0x14000a7f3  mov     [rsp+98h+var_70], rbp
0x14000a7f8  mov     [rsp+98h+var_78], r14
0x14000a7fd  call    WPP_SF_Zqqqqddd
0x14000a802  movzx   eax, byte ptr [rbp+148h]
0x14000a809  test    al, 1
0x14000a80b  jnz     short loc_14000A81E
0x14000a80d  test    al, 2
0x14000a80f  jz      loc_14000A96F
0x14000a815  test    dil, dil
0x14000a818  jz      loc_14000A96F
0x14000a81e  test    al, 4
0x14000a820  jz      loc_14000A935
0x14000a826  mov     rcx, [r14+28h]; Irp
0x14000a82a  test    rcx, rcx
0x14000a82d  jz      loc_14000A96F
0x14000a833  cmp     [rcx+40h], sil
0x14000a837  jnz     short loc_14000A84A
0x14000a839  mov     rax, [rcx+0B8h]
0x14000a840  test    byte ptr [rax+2], 1
0x14000a844  jz      loc_14000A96F
0x14000a84a  call    cs:__imp_IoGetRequestorProcess
0x14000a851  nop     dword ptr [rax+rax+00h]
0x14000a856  mov     rbx, rax
0x14000a859  test    rax, rax
0x14000a85c  jz      loc_14000A96F
0x14000a862  mov     rax, [r15+58h]
0x14000a866  mov     [rsp+98h+pImageFileName], rsi
0x14000a86e  mov     rcx, [rax+1A8h]
0x14000a875  mov     rax, [r14+48h]
0x14000a879  movzx   edi, word ptr [rcx+60h]
0x14000a87d  mov     r15, [rcx+68h]
0x14000a881  mov     rcx, rbx; Process
0x14000a884  mov     r14, [rax+50h]
0x14000a888  call    cs:__imp_PsGetProcessId
0x14000a88f  nop     dword ptr [rax+rax+00h]
0x14000a894  lea     rdx, [rsp+98h+pImageFileName]; pImageFileName
0x14000a89c  mov     rcx, rbx; Process
0x14000a89f  mov     r12, rax
0x14000a8a2  call    cs:__imp_SeLocateProcessImageName
0x14000a8a9  nop     dword ptr [rax+rax+00h]
0x14000a8ae  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 10h
0x14000a8b5  jz      short loc_14000A918
0x14000a8b7  movzx   edx, byte ptr [rbp+148h]
0x14000a8be  not     dl
0x14000a8c0  and     edx, 1
0x14000a8c3  test    eax, eax
0x14000a8c5  js      short loc_14000A8DD
0x14000a8c7  mov     rax, [rsp+98h+pImageFileName]
0x14000a8cf  movzx   r9d, word ptr [rax]
0x14000a8d3  mov     r8, [rax+8]
0x14000a8d7  shr     r9w, 1
0x14000a8db  jmp     short loc_14000A8E3
0x14000a8dd  xor     r9d, r9d
0x14000a8e0  xor     r8d, r8d
0x14000a8e3  movzx   ecx, word ptr [r14]
0x14000a8e7  mov     rax, [r14+8]
0x14000a8eb  mov     [rsp+98h+var_48], rax
0x14000a8f0  shr     cx, 1
0x14000a8f3  mov     word ptr [rsp+98h+var_50], cx
0x14000a8f8  mov     [rsp+98h+var_58], r15
0x14000a8fd  shr     di, 1
0x14000a900  mov     word ptr [rsp+98h+var_60], di
0x14000a905  mov     dword ptr [rsp+98h+var_68], edx
0x14000a909  mov     dword ptr [rsp+98h+var_70], r12d
0x14000a90e  mov     [rsp+98h+var_78], r8
0x14000a913  call    McTemplateK0hzr0qqhzr4hzr6_EtwWriteTransfer
0x14000a918  mov     rcx, [rsp+98h+pImageFileName]; P
0x14000a920  test    rcx, rcx
0x14000a923  jz      short loc_14000A96F
0x14000a925  xor     edx, edx; Tag
0x14000a927  call    cs:__imp_ExFreePoolWithTag
0x14000a92e  nop     dword ptr [rax+rax+00h]
0x14000a933  jmp     short loc_14000A96F
0x14000a935  mov     esi, 0C05D000Ch
0x14000a93a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a941  cmp     rcx, r12
0x14000a944  jz      short loc_14000A96F
0x14000a946  mov     edx, [rcx+2Ch]
0x14000a949  test    dl, 1
0x14000a94c  jz      short loc_14000A96F
0x14000a94e  cmp     byte ptr [rcx+29h], 1
0x14000a952  jb      short loc_14000A96F
0x14000a954  mov     rcx, [rcx+18h]
0x14000a958  mov     r9, r14
0x14000a95b  mov     [rsp+98h+var_68], r15
0x14000a960  mov     [rsp+98h+var_70], rbx
0x14000a965  mov     [rsp+98h+var_78], rbp
0x14000a96a  call    WPP_SF_qqqqD
0x14000a96f  lea     r11, [rsp+98h+var_28]
0x14000a974  mov     eax, esi
0x14000a976  mov     rbx, [r11+30h]
0x14000a97a  mov     rbp, [r11+40h]
0x14000a97e  mov     rsp, r11
0x14000a981  pop     r15
0x14000a983  pop     r14
0x14000a985  pop     r12
0x14000a987  pop     rdi
0x14000a988  pop     rsi
0x14000a989  retn
```
