# PrjfPreCreate

- ea: `0x1400237d0`
- end: `0x140023d0e`
- name: `PrjfPreCreate`
- size: `1342`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x14000d128`
- `0x140021368`
- `0x1400237d0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023ccb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023ce6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023ccb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023ce6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400239f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140023b32`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400239f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140023b32`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140023ab2`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140023bd8`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140023ab2`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140023bd8`
- `FLTMGR!FltEnlistInTransaction` at `0x1400238cc`
- `FLTMGR!FltEnlistInTransaction` at `0x1400238cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023cb0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023cb0`
- `FLTMGR!FltGetFileNameInformation` at `0x14002396a`
- `FLTMGR!FltGetFileNameInformation` at `0x14002398a`
- `FLTMGR!FltGetFileNameInformation` at `0x14002396a`
- `FLTMGR!FltGetFileNameInformation` at `0x14002398a`
- `FLTMGR!FltReleaseContext` at `0x140023c97`
- `FLTMGR!FltReleaseContext` at `0x140023c97`

## string_xrefs

- `0x140023860`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023910`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400239c6`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023a40`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023aee`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023b79`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023c10`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rax
  _QWORD *v4; // rbx
  PFLT_CONTEXT v5; // r15
  void *v6; // rsi
  unsigned int v9; // r12d
  struct _KTRANSACTION *v11; // rdx
  int v12; // edx
  int v13; // edi
  int v14; // r8d
  NTSTATUS v15; // eax
  int v16; // edx
  int v17; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  UCHAR OperationFlags; // al
  int v20; // edx
  int v21; // r8d
  char *v22; // rax
  int v23; // r8d
  int v24; // edx
  char v25; // r10
  int v26; // edx
  int v27; // r8d
  char *v28; // rax
  __int16 v30; // [rsp+30h] [rbp-68h]
  char v31; // [rsp+48h] [rbp-50h]
  char v32; // [rsp+50h] [rbp-48h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A8h] [rbp+10h] BYREF
  PFLT_CONTEXT TransactionContext; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)(a2 + 32);
  v4 = 0;
  v5 = 0;
  FileNameInformation = 0;
  v6 = 0;
  TransactionContext = 0;
  v9 = 1;
  if ( (*(_DWORD *)(v3 + 80) & 0x400000) == 0 )
  {
    v11 = *(struct _KTRANSACTION **)(a2 + 40);
    v9 = 4;
    if ( v11 )
    {
      v13 = PrjfFindOrCreateTransactionContext(*(PFLT_INSTANCE *)(a2 + 24), v11);
      if ( v13 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            517,
            v12,
            v14,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            23,
            (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
            78,
            v13);
        }
        v5 = TransactionContext;
        goto LABEL_41;
      }
      v5 = TransactionContext;
      v15 = FltEnlistInTransaction(*(PFLT_INSTANCE *)(a2 + 24), *(PKTRANSACTION *)(a2 + 40), TransactionContext, 0xCu);
      v13 = 0;
      if ( v15 != -1071906789 )
        v13 = v15;
      if ( v13 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            517,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            24,
            (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
            94,
            v13);
        }
        goto LABEL_41;
      }
    }
    Iopb = CallbackData->Iopb;
    if ( (Iopb->Parameters.Create.Options & 0x2000) == 0 )
    {
      OperationFlags = Iopb->OperationFlags;
      if ( (OperationFlags & 4) != 0 )
      {
        Iopb->OperationFlags = OperationFlags & 0xFB;
        v13 = FltGetFileNameInformation(CallbackData, 0x302u, &FileNameInformation);
        CallbackData->Iopb->OperationFlags |= 4u;
      }
      else
      {
        v13 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
      }
      if ( v13 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v20) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            517,
            v20,
            v21,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            25,
            (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
            136,
            v13);
        }
        goto LABEL_41;
      }
    }
    v22 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A740);
    v4 = v22;
    if ( !v22 )
    {
      v24 = -1073741670;
      v13 = -1073741670;
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v25 = xmmword_14001A3D0 & 0x20;
      if ( (xmmword_14001A3D0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v32 = -102;
      v31 = -110;
      v30 = 26;
      goto LABEL_26;
    }
    *(_QWORD *)(v22 + 44) = 0;
    *(_QWORD *)(v22 + 52) = 0;
    *((_DWORD *)v22 + 15) = 0;
    *((_QWORD *)v22 + 1) = v22;
    *(_QWORD *)v22 = v22;
    *(_OWORD *)(v22 + 24) = 0;
    *((_DWORD *)v22 + 4) = -1879048164;
    *((_DWORD *)v22 + 5) = -2147483644;
    *((_WORD *)v22 + 20) = 48;
    *((_WORD *)v22 + 21) = 0;
    v13 = FltAddOpenReparseEntry(Globals, CallbackData, v22);
    if ( v13 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v26,
          v27,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          27,
          (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          160,
          v13);
      }
      goto LABEL_41;
    }
    if ( (CallbackData->Iopb->Parameters.Create.Options & 0x200000) != 0 )
    {
      v28 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A6C0);
      v6 = v28;
      if ( !v28 )
      {
        v24 = -1073741670;
        v13 = -1073741670;
        LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v25 = xmmword_14001A3D0 & 0x20;
        if ( (xmmword_14001A3D0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_41;
        v32 = -102;
        v31 = -80;
        v30 = 28;
LABEL_26:
        LOBYTE(v24) = v25;
LABEL_40:
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v24,
          v23,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          v30,
          (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          v31,
          v32);
LABEL_41:
        CallbackData->IoStatus.Status = v13;
        CallbackData->IoStatus.Information = 0;
        goto LABEL_43;
      }
      *((_QWORD *)v28 + 1) = v28;
      *(_QWORD *)v28 = v28;
      *(_OWORD *)(v28 + 24) = 0;
      *((_DWORD *)v28 + 4) = -1610612702;
      *((_DWORD *)v28 + 5) = -2147483522;
      *((_WORD *)v28 + 20) = 48;
      *((_WORD *)v28 + 21) = 0;
      v13 = FltAddOpenReparseEntry(Globals, CallbackData, v28);
      if ( v13 < 0 )
      {
        LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v24) = xmmword_14001A3D0 & 0x20;
        if ( (xmmword_14001A3D0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_41;
        v32 = v13;
        v31 = -64;
        v30 = 29;
        goto LABEL_40;
      }
    }
    v4[6] = FileNameInformation;
    FileNameInformation = 0;
    v4[7] = v6;
    v6 = 0;
    *a3 = v4;
    v4 = 0;
    v9 = 5;
  }
LABEL_43:
  if ( v5 )
    FltReleaseContext(v5);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v6 )
    ExFreeToPagedLookasideList(&stru_14001A6C0, v6);
  if ( v4 )
    ExFreeToPagedLookasideList(&stru_14001A740, v4);
  return v9;
}

```

## disassembly

```asm
0x1400237d0  mov     r11, rsp
0x1400237d3  mov     [r11+8], rbx
0x1400237d7  push    rbp
0x1400237d8  push    rsi
0x1400237d9  push    rdi
0x1400237da  push    r12
0x1400237dc  push    r13
0x1400237de  push    r14
0x1400237e0  push    r15
0x1400237e2  sub     rsp, 60h
0x1400237e6  mov     rax, [rdx+20h]
0x1400237ea  xor     ebx, ebx
0x1400237ec  xor     r15d, r15d
0x1400237ef  mov     [r11+10h], rbx
0x1400237f3  xor     esi, esi
0x1400237f5  mov     [r11+20h], r15
0x1400237f9  mov     r13, r8
0x1400237fc  mov     rbp, rdx
0x1400237ff  test    dword ptr [rax+50h], 400000h
0x140023806  lea     r12d, [rbx+1]
0x14002380a  mov     r14, rcx
0x14002380d  jnz     loc_140023C8F
0x140023813  mov     rdx, [rdx+28h]; Transaction
0x140023817  lea     r12d, [rbx+4]
0x14002381b  test    rdx, rdx
0x14002381e  jz      loc_14002393C
0x140023824  mov     rcx, [rbp+18h]; Instance
0x140023828  lea     r8, [r11+20h]
0x14002382c  call    PrjfFindOrCreateTransactionContext
0x140023831  mov     edi, eax
0x140023833  test    eax, eax
0x140023835  jns     short loc_1400238B3
0x140023837  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002383d  lea     rax, WPP_RECORDER_INITIALIZED
0x140023844  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002384b  setnz   r8b
0x14002384f  and     dl, 20h
0x140023852  jnz     short loc_140023859
0x140023854  test    r8b, r8b
0x140023857  jz      short loc_1400238A6
0x140023859  mov     r9, cs:WPP_GLOBAL_Control
0x140023860  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023867  mov     dword ptr [rsp+98h+var_48], edi
0x14002386b  mov     ecx, 205h
0x140023870  mov     dword ptr [rsp+98h+var_50], 44Eh
0x140023878  mov     [rsp+98h+var_58], rax
0x14002387d  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023884  mov     r9, [r9+40h]
0x140023888  mov     [rsp+98h+var_60], rax
0x14002388d  mov     [rsp+98h+var_68], 17h
0x140023894  mov     [rsp+98h+var_70], 5
0x14002389c  mov     [rsp+98h+var_78], 2
0x1400238a1  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400238a6  mov     r15, [rsp+98h+TransactionContext]
0x1400238ae  jmp     loc_140023C59
0x1400238b3  mov     r15, [rsp+98h+TransactionContext]
0x1400238bb  mov     r9d, 0Ch; NotificationMask
0x1400238c1  mov     rdx, [rbp+28h]; Transaction
0x1400238c5  mov     r8, r15; TransactionContext
0x1400238c8  mov     rcx, [rbp+18h]; Instance
0x1400238cc  call    cs:__imp_FltEnlistInTransaction
0x1400238d3  nop     dword ptr [rax+rax+00h]
0x1400238d8  xor     edi, edi
0x1400238da  cmp     eax, 0C01C001Bh
0x1400238df  cmovnz  edi, eax
0x1400238e2  test    edi, edi
0x1400238e4  jns     short loc_14002393C
0x1400238e6  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400238ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1400238f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400238fa  setnz   r8b
0x1400238fe  and     dl, 20h
0x140023901  jnz     short loc_14002390C
0x140023903  test    r8b, r8b
0x140023906  jz      loc_140023C59
0x14002390c  mov     dword ptr [rsp+98h+var_48], edi
0x140023910  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023917  mov     dword ptr [rsp+98h+var_50], 45Eh
0x14002391f  mov     [rsp+98h+var_58], rax
0x140023924  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002392b  mov     [rsp+98h+var_60], rax
0x140023930  mov     [rsp+98h+var_68], 18h
0x140023937  jmp     loc_140023C37
0x14002393c  mov     rcx, [r14+10h]
0x140023940  test    dword ptr [rcx+20h], 2000h
0x140023947  jnz     loc_1400239F2
0x14002394d  mov     al, [rcx+6]
0x140023950  lea     r8, [rsp+98h+FileNameInformation]; FileNameInformation
0x140023958  test    r12b, al
0x14002395b  jz      short loc_140023982
0x14002395d  and     al, 0FBh
0x14002395f  mov     edx, 302h; NameOptions
0x140023964  mov     [rcx+6], al
0x140023967  mov     rcx, r14; CallbackData
0x14002396a  call    cs:__imp_FltGetFileNameInformation
0x140023971  nop     dword ptr [rax+rax+00h]
0x140023976  mov     edi, eax
0x140023978  mov     rax, [r14+10h]
0x14002397c  or      [rax+6], r12b
0x140023980  jmp     short loc_140023998
0x140023982  mov     edx, 102h; NameOptions
0x140023987  mov     rcx, r14; CallbackData
0x14002398a  call    cs:__imp_FltGetFileNameInformation
0x140023991  nop     dword ptr [rax+rax+00h]
0x140023996  mov     edi, eax
0x140023998  test    edi, edi
0x14002399a  jns     short loc_1400239F2
0x14002399c  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400239a2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400239a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400239b0  setnz   r8b
0x1400239b4  and     dl, 20h
0x1400239b7  jnz     short loc_1400239C2
0x1400239b9  test    r8b, r8b
0x1400239bc  jz      loc_140023C59
0x1400239c2  mov     dword ptr [rsp+98h+var_48], edi
0x1400239c6  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400239cd  mov     dword ptr [rsp+98h+var_50], 488h
0x1400239d5  mov     [rsp+98h+var_58], rax
0x1400239da  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400239e1  mov     [rsp+98h+var_60], rax
0x1400239e6  mov     [rsp+98h+var_68], 19h
0x1400239ed  jmp     loc_140023C37
0x1400239f2  lea     rcx, stru_14001A740; Lookaside
0x1400239f9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140023a00  nop     dword ptr [rax+rax+00h]
0x140023a05  mov     rbx, rax
0x140023a08  test    rax, rax
0x140023a0b  jnz     short loc_140023A6F
0x140023a0d  mov     edx, 0C000009Ah
0x140023a12  mov     edi, edx
0x140023a14  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x140023a1b  lea     rax, WPP_RECORDER_INITIALIZED
0x140023a22  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023a29  setnz   r8b
0x140023a2d  and     r10b, 20h
0x140023a31  jnz     short loc_140023A3C
0x140023a33  test    r8b, r8b
0x140023a36  jz      loc_140023C59
0x140023a3c  mov     dword ptr [rsp+98h+var_48], edx
0x140023a40  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023a47  mov     dword ptr [rsp+98h+var_50], 492h
0x140023a4f  mov     [rsp+98h+var_58], rax
0x140023a54  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023a5b  mov     [rsp+98h+var_60], rax
0x140023a60  mov     [rsp+98h+var_68], 1Ah
0x140023a67  mov     dl, r10b
0x140023a6a  jmp     loc_140023C37
0x140023a6f  mov     [rax+2Ch], rsi
0x140023a73  xorps   xmm0, xmm0
0x140023a76  mov     [rax+34h], rsi
0x140023a7a  mov     ebp, 30h ; '0'
0x140023a7f  mov     [rax+3Ch], esi
0x140023a82  mov     r8, rbx
0x140023a85  mov     [rax+8], rbx
0x140023a89  mov     rdx, r14
0x140023a8c  mov     [rax], rbx
0x140023a8f  movups  xmmword ptr [rax+18h], xmm0
0x140023a93  mov     dword ptr [rax+10h], 9000001Ch
0x140023a9a  mov     dword ptr [rax+14h], 80000004h
0x140023aa1  mov     [rax+28h], bp
0x140023aa5  xor     eax, eax
0x140023aa7  mov     [rbx+2Ah], ax
0x140023aab  mov     rcx, cs:Globals
0x140023ab2  call    cs:__imp_FltAddOpenReparseEntry
0x140023ab9  nop     dword ptr [rax+rax+00h]
0x140023abe  mov     edi, eax
0x140023ac0  test    eax, eax
0x140023ac2  jns     short loc_140023B1A
0x140023ac4  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023aca  lea     rax, WPP_RECORDER_INITIALIZED
0x140023ad1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ad8  setnz   r8b
0x140023adc  and     dl, 20h
0x140023adf  jnz     short loc_140023AEA
0x140023ae1  test    r8b, r8b
0x140023ae4  jz      loc_140023C59
0x140023aea  mov     dword ptr [rsp+98h+var_48], edi
0x140023aee  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023af5  mov     dword ptr [rsp+98h+var_50], 4A0h
0x140023afd  mov     [rsp+98h+var_58], rax
0x140023b02  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023b09  mov     [rsp+98h+var_60], rax
0x140023b0e  mov     [rsp+98h+var_68], 1Bh
0x140023b15  jmp     loc_140023C37
0x140023b1a  mov     rax, [r14+10h]
0x140023b1e  test    dword ptr [rax+20h], 200000h
0x140023b25  jz      loc_140023C67
0x140023b2b  lea     rcx, stru_14001A6C0; Lookaside
0x140023b32  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140023b39  nop     dword ptr [rax+rax+00h]
0x140023b3e  mov     rsi, rax
0x140023b41  test    rax, rax
0x140023b44  jnz     short loc_140023BA5
0x140023b46  mov     edx, 0C000009Ah
0x140023b4b  mov     edi, edx
0x140023b4d  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x140023b54  lea     rax, WPP_RECORDER_INITIALIZED
0x140023b5b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023b62  setnz   r8b
0x140023b66  and     r10b, 20h
0x140023b6a  jnz     short loc_140023B75
0x140023b6c  test    r8b, r8b
0x140023b6f  jz      loc_140023C59
0x140023b75  mov     dword ptr [rsp+98h+var_48], edx
0x140023b79  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023b80  mov     dword ptr [rsp+98h+var_50], 4B0h
0x140023b88  mov     [rsp+98h+var_58], rax
0x140023b8d  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023b94  mov     [rsp+98h+var_60], rax
0x140023b99  mov     [rsp+98h+var_68], 1Ch
0x140023ba0  jmp     loc_140023A67
0x140023ba5  mov     [rax+8], rsi
0x140023ba9  xorps   xmm0, xmm0
0x140023bac  mov     [rax], rsi
0x140023baf  mov     r8, rsi
0x140023bb2  movups  xmmword ptr [rax+18h], xmm0
0x140023bb6  mov     dword ptr [rax+10h], 0A0000022h
0x140023bbd  mov     rdx, r14
0x140023bc0  mov     dword ptr [rax+14h], 8000007Eh
0x140023bc7  mov     [rax+28h], bp
0x140023bcb  xor     eax, eax
0x140023bcd  mov     [rsi+2Ah], ax
0x140023bd1  mov     rcx, cs:Globals
0x140023bd8  call    cs:__imp_FltAddOpenReparseEntry
0x140023bdf  nop     dword ptr [rax+rax+00h]
0x140023be4  mov     edi, eax
0x140023be6  test    eax, eax
0x140023be8  jns     short loc_140023C67
0x140023bea  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023bf0  lea     rax, WPP_RECORDER_INITIALIZED
0x140023bf7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023bfe  setnz   r8b
0x140023c02  and     dl, 20h
0x140023c05  jnz     short loc_140023C0C
0x140023c07  test    r8b, r8b
0x140023c0a  jz      short loc_140023C59
0x140023c0c  mov     dword ptr [rsp+98h+var_48], edi
0x140023c10  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023c17  mov     dword ptr [rsp+98h+var_50], 4C0h
0x140023c1f  mov     [rsp+98h+var_58], rax
0x140023c24  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023c2b  mov     [rsp+98h+var_60], rax
0x140023c30  mov     [rsp+98h+var_68], 1Dh
0x140023c37  mov     r9, cs:WPP_GLOBAL_Control
0x140023c3e  mov     ecx, 205h
0x140023c43  mov     [rsp+98h+var_70], 5
0x140023c4b  mov     [rsp+98h+var_78], 2
0x140023c50  mov     r9, [r9+40h]
0x140023c54  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140023c59  mov     [r14+18h], edi
0x140023c5d  mov     qword ptr [r14+20h], 0
0x140023c65  jmp     short loc_140023C8F
0x140023c67  mov     rax, [rsp+98h+FileNameInformation]
0x140023c6f  mov     [rbx+30h], rax
0x140023c73  mov     [rsp+98h+FileNameInformation], 0
0x140023c7f  mov     [rbx+38h], rsi
0x140023c83  xor     esi, esi
0x140023c85  mov     [r13+0], rbx
0x140023c89  xor     ebx, ebx
0x140023c8b  lea     r12d, [rsi+5]
0x140023c8f  test    r15, r15
0x140023c92  jz      short loc_140023CA3
0x140023c94  mov     rcx, r15; Context
0x140023c97  call    cs:__imp_FltReleaseContext
0x140023c9e  nop     dword ptr [rax+rax+00h]
0x140023ca3  mov     rcx, [rsp+98h+FileNameInformation]; FileNameInformation
0x140023cab  test    rcx, rcx
0x140023cae  jz      short loc_140023CBC
0x140023cb0  call    cs:__imp_FltReleaseFileNameInformation
0x140023cb7  nop     dword ptr [rax+rax+00h]
0x140023cbc  test    rsi, rsi
0x140023cbf  jz      short loc_140023CD7
0x140023cc1  mov     rdx, rsi; Entry
0x140023cc4  lea     rcx, stru_14001A6C0; Lookaside
0x140023ccb  call    cs:__imp_ExFreeToPagedLookasideList
0x140023cd2  nop     dword ptr [rax+rax+00h]
0x140023cd7  test    rbx, rbx
0x140023cda  jz      short loc_140023CF2
0x140023cdc  mov     rdx, rbx; Entry
0x140023cdf  lea     rcx, stru_14001A740; Lookaside
0x140023ce6  call    cs:__imp_ExFreeToPagedLookasideList
0x140023ced  nop     dword ptr [rax+rax+00h]
0x140023cf2  mov     rbx, [rsp+98h+arg_0]
0x140023cfa  mov     eax, r12d
0x140023cfd  add     rsp, 60h
0x140023d01  pop     r15
0x140023d03  pop     r14
0x140023d05  pop     r13
0x140023d07  pop     r12
0x140023d09  pop     rdi
0x140023d0a  pop     rsi
0x140023d0b  pop     rbp
0x140023d0c  retn
```
