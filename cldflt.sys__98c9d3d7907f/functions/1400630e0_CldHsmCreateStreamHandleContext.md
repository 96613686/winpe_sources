# CldHsmCreateStreamHandleContext

- ea: `0x1400630e0`
- end: `0x140063785`
- name: `CldHsmCreateStreamHandleContext`
- size: `1701`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x1400630e0`
- `0x140063790`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140063392`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140063392`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063759`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063759`
- `ntoskrnl!ExAllocatePool2` at `0x140063594`
- `ntoskrnl!ExAllocatePool2` at `0x140063594`
- `ntoskrnl!IoGetCurrentProcess` at `0x140063181`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400631ac`
- `ntoskrnl!IoGetCurrentProcess` at `0x140063181`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400631ac`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063774`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063774`
- `ntoskrnl!PsInitialSystemProcess` at `0x140063175`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140063476`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400635d0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140063476`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400635d0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006313a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006313a`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140063626`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1400636da`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140063626`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1400636da`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063642`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063700`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063642`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063700`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063658`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063727`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063658`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063727`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006350e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006350e`
- `FLTMGR!FltReleasePushLockEx` at `0x140063270`
- `FLTMGR!FltReleasePushLockEx` at `0x1400633b1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400633c8`
- `FLTMGR!FltReleasePushLockEx` at `0x140063270`
- `FLTMGR!FltReleasePushLockEx` at `0x1400633b1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400633c8`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006337a`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006337a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140063740`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140063740`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006320e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140063352`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006320e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140063352`

## pseudocode

```c
__int64 __fastcall CldHsmCreateStreamHandleContext(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 FileNameInformationUnsafe; // r14
  __int64 v4; // rbp
  UNICODE_STRING *Pool2; // r12
  __int64 v7; // rbx
  _QWORD *v9; // rax
  void *v10; // rdi
  __int64 v11; // r15
  unsigned int v12; // ebx
  __int64 v13; // rax
  struct _KPROCESS *v14; // rsi
  PUNICODE_STRING i; // rsi
  PWSTR v16; // rax
  PWSTR v17; // rax
  int v18; // r9d
  unsigned int v19; // ebx
  unsigned int v20; // r9d
  unsigned int v21; // r8d
  __int64 v23; // rbx
  _QWORD *v24; // rax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PULONG ReturnLength; // [rsp+20h] [rbp-68h]
  __int64 v28; // [rsp+30h] [rbp-58h]
  struct _FILE_OBJECT *FileObject; // [rsp+38h] [rbp-50h]
  ULONG ProcessInformationLength; // [rsp+90h] [rbp+8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v32; // [rsp+A0h] [rbp+18h]
  __int64 Buffer; // [rsp+A8h] [rbp+20h] BYREF

  v32 = a3;
  LODWORD(FileNameInformationUnsafe) = 0;
  v4 = a2[2];
  Pool2 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(*a2 + 16LL) + 32LL);
  v28 = v7;
  FileObject = *(struct _FILE_OBJECT **)(a1 + 48);
  ProcessInformationLength = 0;
  FileNameInformation = 0;
  v9 = ExAllocateFromPagedLookasideList(&stru_140028B80);
  v10 = v9;
  if ( !v9 )
  {
    LODWORD(FileNameInformationUnsafe) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids, 0, v7);
    }
    goto LABEL_22;
  }
  *v9 = a1;
  v9[1] = a2;
  if ( !*(_QWORD *)(v4 + 32) && *(_QWORD *)(v4 + 16) )
  {
    FltAcquirePushLockExclusiveEx(v4 + 24, 0);
    if ( !*(_QWORD *)(v4 + 32) )
    {
      v23 = *(_QWORD *)(v4 + 8);
      Buffer = *(_QWORD *)(v4 + 16);
      FltAcquirePushLockSharedEx(v23 + 8, 0);
      v24 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v23 + 16), &Buffer);
      if ( v24 )
        *(_QWORD *)(v4 + 32) = v24[1];
      else
        HsmDbgBreakOnStatus(3221278465LL);
      FltReleasePushLockEx(v23 + 8, 0);
      v7 = v28;
    }
    FltReleasePushLockEx(v4 + 24, 0);
  }
  v11 = *(_QWORD *)(v4 + 32);
  if ( v11 )
  {
    FileNameInformationUnsafe = (unsigned int)CldStreamOpen(a2);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( (int)FileNameInformationUnsafe < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids, v10, v7);
      }
      goto LABEL_22;
    }
  }
  v12 = 0;
  if ( IoGetCurrentProcess() == PsInitialSystemProcess
    || (!v11 || (v13 = *(_QWORD *)(v11 + 96)) == 0 ? (v14 = 0) : (v14 = *(struct _KPROCESS **)(v13 + 104)),
        IoGetCurrentProcess() == v14) )
  {
LABEL_17:
    FltAcquirePushLockExclusiveEx(v4 + 24, 0);
    v18 = *(_DWORD *)(v4 + 40);
    if ( (unsigned __int8)(v18 & 0xF) <= (unsigned __int8)(v12 & 0xF) )
      LOBYTE(v18) = v12;
    v19 = v12 >> 4;
    v20 = *(_DWORD *)(v4 + 40) ^ ((unsigned __int8)*(_DWORD *)(v4 + 40) ^ (unsigned __int8)v18) & 0xF;
    v21 = v20 >> 4;
    if ( (unsigned __int8)((unsigned __int8)v20 >> 4) <= (unsigned __int8)(v19 & 0xF) )
      LOBYTE(v21) = v19;
    *(_DWORD *)(v4 + 40) = v20 ^ ((unsigned __int8)v20 ^ (unsigned __int8)(16 * v21)) & 0xF0;
    FltReleasePushLockEx(v4 + 24, 0);
    *v32 = v10;
    v10 = 0;
    goto LABEL_22;
  }
  for ( i = Expression; ; i = (PUNICODE_STRING)((char *)i + 40) )
  {
    v16 = i->Buffer;
    if ( !v16 || *v16 == 42 && i->Length == 2 )
    {
LABEL_13:
      v17 = i[1].Buffer;
      if ( !v17 || *v17 == 42 && i[1].Length == 2 )
        goto LABEL_16;
      FileNameInformationUnsafe = (unsigned int)FltGetFileNameInformationUnsafe(
                                                  FileObject,
                                                  0,
                                                  0x102u,
                                                  &FileNameInformation);
      HsmDbgBreakOnStatus(FileNameInformationUnsafe);
      if ( (int)FileNameInformationUnsafe < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
            a1,
            FileObject);
        }
        goto LABEL_22;
      }
      if ( !FileNameInformation->Stream.Buffer
        && FileNameInformation->Extension.Buffer
        && (FsRtlDoesNameContainWildCards(i + 1)
         && FsRtlIsNameInExpression(i + 1, &FileNameInformation->Extension, 1u, 0)
         || !RtlCompareUnicodeString(i + 1, &FileNameInformation->Extension, 1u)) )
      {
LABEL_16:
        v12 = *(_DWORD *)&i[2].Length;
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    if ( Pool2 )
      goto LABEL_65;
    LODWORD(FileNameInformationUnsafe) = ZwQueryInformationProcess(
                                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                           ProcessImageFileName,
                                           0,
                                           0,
                                           &ProcessInformationLength);
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
    if ( (((_DWORD)FileNameInformationUnsafe + 0x80000000) & 0x80000000) == 0
      && (_DWORD)FileNameInformationUnsafe != -1073741820 )
    {
      break;
    }
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(256, ProcessInformationLength, 1852861507);
    if ( !Pool2 )
    {
      LODWORD(FileNameInformationUnsafe) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_22;
      }
      v26 = 16;
LABEL_53:
      LODWORD(ReturnLength) = FileNameInformationUnsafe;
      WPP_SF_qd(v25->AttachedDevice, v26, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids, a1, ReturnLength);
      goto LABEL_22;
    }
    FileNameInformationUnsafe = (unsigned int)ZwQueryInformationProcess(
                                                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                                ProcessImageFileName,
                                                Pool2,
                                                ProcessInformationLength,
                                                &ProcessInformationLength);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( (int)FileNameInformationUnsafe < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_22;
      }
      v26 = 17;
      goto LABEL_53;
    }
LABEL_65:
    if ( FsRtlDoesNameContainWildCards(i) )
    {
      if ( FsRtlIsNameInExpression(i, Pool2, 1u, 0) )
        goto LABEL_13;
    }
    else if ( !RtlCompareUnicodeString(i, Pool2, 1u) )
    {
      goto LABEL_13;
    }
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v26 = 15;
    goto LABEL_53;
  }
LABEL_22:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x6E706C43u);
  if ( v10 )
    ExFreeToPagedLookasideList(&stru_140028B80, v10);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x1400630e0  mov     r11, rsp
0x1400630e3  mov     [r11+18h], r8
0x1400630e7  push    rdi
0x1400630e8  push    r14
0x1400630ea  sub     rsp, 78h
0x1400630ee  mov     rax, [rdx]
0x1400630f1  xor     r14d, r14d
0x1400630f4  mov     [r11-18h], rbx
0x1400630f8  mov     [r11-20h], rbp
0x1400630fc  mov     rbp, [rdx+10h]
0x140063100  mov     r9, [rax+10h]
0x140063104  mov     rax, [rcx+30h]
0x140063108  mov     [r11-28h], rsi
0x14006310c  mov     rsi, rdx
0x14006310f  mov     [r11-30h], r12
0x140063113  mov     r12d, r14d
0x140063116  mov     rbx, [r9+20h]
0x14006311a  mov     [r11-38h], r13
0x14006311e  mov     r13, rcx
0x140063121  lea     rcx, stru_140028B80; Lookaside
0x140063128  mov     [rsp+88h+var_58], rbx
0x14006312d  mov     [rsp+88h+FileObject], rax
0x140063132  mov     [r11+8], r14d
0x140063136  mov     [r11+10h], r14
0x14006313a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140063141  nop     dword ptr [rax+rax+00h]
0x140063146  mov     rdi, rax
0x140063149  test    rax, rax
0x14006314c  jz      loc_1400633EC
0x140063152  mov     [rax], r13
0x140063155  mov     [rax+8], rsi
0x140063159  mov     [rsp+88h+var_40], r15
0x14006315e  cmp     [rbp+20h], r14
0x140063162  jz      loc_140063342
0x140063168  mov     r15, [rbp+20h]
0x14006316c  test    r15, r15
0x14006316f  jnz     loc_1400632D6
0x140063175  mov     rax, cs:__imp_PsInitialSystemProcess
0x14006317c  xor     ebx, ebx
0x14006317e  mov     rsi, [rax]
0x140063181  call    cs:__imp_IoGetCurrentProcess
0x140063188  nop     dword ptr [rax+rax+00h]
0x14006318d  cmp     rax, rsi
0x140063190  jz      short loc_140063208
0x140063192  test    r15, r15
0x140063195  jz      loc_1400633D9
0x14006319b  mov     rax, [r15+60h]
0x14006319f  test    rax, rax
0x1400631a2  jz      loc_1400633D9
0x1400631a8  mov     rsi, [rax+68h]
0x1400631ac  call    cs:__imp_IoGetCurrentProcess
0x1400631b3  nop     dword ptr [rax+rax+00h]
0x1400631b8  cmp     rax, rsi
0x1400631bb  jz      short loc_140063208
0x1400631bd  mov     rsi, cs:Expression
0x1400631c4  mov     r15d, 80000000h
0x1400631ca  mov     rax, [rsi+8]
0x1400631ce  test    rax, rax
0x1400631d1  jz      short loc_1400631E7
0x1400631d3  cmp     word ptr [rax], 2Ah ; '*'
0x1400631d7  jnz     loc_14006344E
0x1400631dd  cmp     word ptr [rsi], 2
0x1400631e1  jnz     loc_14006344E
0x1400631e7  mov     rax, [rsi+18h]
0x1400631eb  test    rax, rax
0x1400631ee  jz      short loc_140063205
0x1400631f0  cmp     word ptr [rax], 2Ah ; '*'
0x1400631f4  jnz     loc_1400634F6
0x1400631fa  cmp     word ptr [rsi+10h], 2
0x1400631ff  jnz     loc_1400634F6
0x140063205  mov     ebx, [rsi+20h]
0x140063208  xor     edx, edx
0x14006320a  lea     rcx, [rbp+18h]
0x14006320e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140063215  nop     dword ptr [rax+rax+00h]
0x14006321a  mov     edx, [rbp+28h]
0x14006321d  mov     eax, ebx
0x14006321f  mov     ecx, edx
0x140063221  and     eax, 0Fh
0x140063224  mov     r9d, edx
0x140063227  and     ecx, 0Fh
0x14006322a  cmp     cl, al
0x14006322c  lea     rcx, [rbp+18h]
0x140063230  cmovbe  r9d, ebx
0x140063234  shr     ebx, 4
0x140063237  xor     r9d, edx
0x14006323a  mov     eax, ebx
0x14006323c  and     r9d, 0Fh
0x140063240  and     eax, 0Fh
0x140063243  xor     r9d, edx
0x140063246  mov     r8d, r9d
0x140063249  shr     r8d, 4
0x14006324d  mov     edx, r8d
0x140063250  and     edx, 0Fh
0x140063253  cmp     dl, al
0x140063255  cmovbe  r8d, ebx
0x140063259  xor     edx, edx
0x14006325b  shl     r8d, 4
0x14006325f  xor     r8d, r9d
0x140063262  and     r8d, 0F0h
0x140063269  xor     r8d, r9d
0x14006326c  mov     [rbp+28h], r8d
0x140063270  call    cs:__imp_FltReleasePushLockEx
0x140063277  nop     dword ptr [rax+rax+00h]
0x14006327c  mov     rax, [rsp+88h+arg_10]
0x140063284  mov     [rax], rdi
0x140063287  xor     edi, edi
0x140063289  mov     r15, [rsp+88h+var_40]
0x14006328e  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x140063296  mov     r13, [rsp+88h+var_38]
0x14006329b  mov     rsi, [rsp+88h+var_28]
0x1400632a0  mov     rbp, [rsp+88h+var_20]
0x1400632a5  mov     rbx, [rsp+88h+var_18]
0x1400632aa  test    rcx, rcx
0x1400632ad  jnz     loc_140063740
0x1400632b3  test    r12, r12
0x1400632b6  jnz     loc_140063751
0x1400632bc  mov     r12, [rsp+88h+var_30]
0x1400632c1  test    rdi, rdi
0x1400632c4  jnz     loc_14006376A
0x1400632ca  mov     eax, r14d
0x1400632cd  add     rsp, 78h
0x1400632d1  pop     r14
0x1400632d3  pop     rdi
0x1400632d4  retn
0x1400632d6  mov     rcx, rsi
0x1400632d9  call    CldStreamOpen
0x1400632de  mov     ecx, eax
0x1400632e0  mov     r14d, eax
0x1400632e3  call    HsmDbgBreakOnStatus
0x1400632e8  test    r14d, r14d
0x1400632eb  jns     loc_140063175
0x1400632f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632f8  lea     rax, WPP_GLOBAL_Control
0x1400632ff  cmp     rcx, rax
0x140063302  jz      short loc_140063289
0x140063304  test    dword ptr [rcx+2Ch], 100h
0x14006330b  jz      loc_140063289
0x140063311  cmp     byte ptr [rcx+29h], 2
0x140063315  jb      loc_140063289
0x14006331b  mov     rcx, [rcx+18h]
0x14006331f  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063326  mov     edx, 0Eh
0x14006332b  mov     [rsp+88h+var_60], r14d
0x140063330  mov     r9, rdi
0x140063333  mov     [rsp+88h+ReturnLength], rbx
0x140063338  call    WPP_SF_qqd
0x14006333d  jmp     loc_140063289
0x140063342  cmp     [rbp+10h], r12
0x140063346  jz      loc_140063168
0x14006334c  xor     edx, edx
0x14006334e  lea     rcx, [rbp+18h]
0x140063352  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140063359  nop     dword ptr [rax+rax+00h]
0x14006335e  cmp     [rbp+20h], r12
0x140063362  jnz     short loc_1400633C2
0x140063364  mov     rbx, [rbp+8]
0x140063368  xor     edx, edx
0x14006336a  mov     rax, [rbp+10h]
0x14006336e  mov     [rsp+88h+Buffer], rax
0x140063376  lea     rcx, [rbx+8]
0x14006337a  call    cs:__imp_FltAcquirePushLockSharedEx
0x140063381  nop     dword ptr [rax+rax+00h]
0x140063386  lea     rcx, [rbx+10h]; Table
0x14006338a  lea     rdx, [rsp+88h+Buffer]; Buffer
0x140063392  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140063399  nop     dword ptr [rax+rax+00h]
0x14006339e  test    rax, rax
0x1400633a1  jz      short loc_1400633E0
0x1400633a3  mov     rax, [rax+8]
0x1400633a7  mov     [rbp+20h], rax
0x1400633ab  xor     edx, edx
0x1400633ad  lea     rcx, [rbx+8]
0x1400633b1  call    cs:__imp_FltReleasePushLockEx
0x1400633b8  nop     dword ptr [rax+rax+00h]
0x1400633bd  mov     rbx, [rsp+88h+var_58]
0x1400633c2  xor     edx, edx
0x1400633c4  lea     rcx, [rbp+18h]
0x1400633c8  call    cs:__imp_FltReleasePushLockEx
0x1400633cf  nop     dword ptr [rax+rax+00h]
0x1400633d4  jmp     loc_140063168
0x1400633d9  xor     esi, esi
0x1400633db  jmp     loc_1400631AC
0x1400633e0  mov     ecx, 0C000CF01h
0x1400633e5  call    HsmDbgBreakOnStatus
0x1400633ea  jmp     short loc_1400633AB
0x1400633ec  mov     ecx, 0C000009Ah
0x1400633f1  mov     r14d, ecx
0x1400633f4  call    HsmDbgBreakOnStatus
0x1400633f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140063400  lea     rax, WPP_GLOBAL_Control
0x140063407  cmp     rcx, rax
0x14006340a  jz      loc_14006328E
0x140063410  test    dword ptr [rcx+2Ch], 100h
0x140063417  jz      loc_14006328E
0x14006341d  cmp     byte ptr [rcx+29h], 2
0x140063421  jb      loc_14006328E
0x140063427  mov     rcx, [rcx+18h]
0x14006342b  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063432  mov     edx, 0Dh
0x140063437  mov     [rsp+88h+var_60], r14d
0x14006343c  xor     r9d, r9d
0x14006343f  mov     [rsp+88h+ReturnLength], rbx
0x140063444  call    WPP_SF_qqd
0x140063449  jmp     loc_14006328E
0x14006344e  test    r12, r12
0x140063451  jnz     loc_140063623
0x140063457  lea     rax, [rsp+88h+ProcessInformationLength]
0x14006345f  xor     r9d, r9d; ProcessInformationLength
0x140063462  xor     r8d, r8d; ProcessInformation
0x140063465  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x14006346a  mov     edx, 1Bh; ProcessInformationClass
0x14006346f  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140063476  call    cs:__imp_ZwQueryInformationProcess
0x14006347d  nop     dword ptr [rax+rax+00h]
0x140063482  mov     ecx, eax
0x140063484  mov     r14d, eax
0x140063487  call    HsmDbgBreakOnStatus
0x14006348c  lea     eax, [r14+r15]
0x140063490  test    r15d, eax
0x140063493  jnz     loc_140063582
0x140063499  cmp     r14d, 0C0000004h
0x1400634a0  jz      loc_140063582
0x1400634a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400634ad  lea     rax, WPP_GLOBAL_Control
0x1400634b4  cmp     rcx, rax
0x1400634b7  jz      loc_140063289
0x1400634bd  test    dword ptr [rcx+2Ch], 100h
0x1400634c4  jz      loc_140063289
0x1400634ca  cmp     byte ptr [rcx+29h], 2
0x1400634ce  jb      loc_140063289
0x1400634d4  mov     edx, 0Fh
0x1400634d9  mov     rcx, [rcx+18h]
0x1400634dd  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x1400634e4  mov     r9, r13
0x1400634e7  mov     dword ptr [rsp+88h+ReturnLength], r14d
0x1400634ec  call    WPP_SF_qd
0x1400634f1  jmp     loc_140063289
0x1400634f6  mov     r15, [rsp+88h+FileObject]
0x1400634fb  lea     r9, [rsp+88h+FileNameInformation]; FileNameInformation
0x140063503  mov     rcx, r15; FileObject
0x140063506  xor     edx, edx; Instance
0x140063508  mov     r8d, 102h; NameOptions
0x14006350e  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140063515  nop     dword ptr [rax+rax+00h]
0x14006351a  mov     ecx, eax
0x14006351c  mov     r14d, eax
0x14006351f  call    HsmDbgBreakOnStatus
0x140063524  test    r14d, r14d
0x140063527  jns     loc_1400636BA
0x14006352d  mov     rcx, cs:WPP_GLOBAL_Control
0x140063534  lea     rax, WPP_GLOBAL_Control
0x14006353b  cmp     rcx, rax
0x14006353e  jz      loc_140063289
0x140063544  test    dword ptr [rcx+2Ch], 100h
0x14006354b  jz      loc_140063289
0x140063551  cmp     byte ptr [rcx+29h], 2
0x140063555  jb      loc_140063289
0x14006355b  mov     rcx, [rcx+18h]
0x14006355f  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063566  mov     edx, 12h
0x14006356b  mov     [rsp+88h+var_60], r14d
0x140063570  mov     r9, r13
0x140063573  mov     [rsp+88h+ReturnLength], r15
0x140063578  call    WPP_SF_qqd
0x14006357d  jmp     loc_140063289
0x140063582  mov     edx, [rsp+88h+ProcessInformationLength]
0x140063589  mov     ecx, 100h
0x14006358e  mov     r8d, 6E706C43h
0x140063594  call    cs:__imp_ExAllocatePool2
0x14006359b  nop     dword ptr [rax+rax+00h]
0x1400635a0  mov     r12, rax
0x1400635a3  test    rax, rax
0x1400635a6  jz      loc_140063675
0x1400635ac  mov     r9d, [rsp+88h+ProcessInformationLength]; ProcessInformationLength
0x1400635b4  lea     rax, [rsp+88h+ProcessInformationLength]
0x1400635bc  mov     r8, r12; ProcessInformation
0x1400635bf  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1400635c4  mov     edx, 1Bh; ProcessInformationClass
0x1400635c9  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400635d0  call    cs:__imp_ZwQueryInformationProcess
0x1400635d7  nop     dword ptr [rax+rax+00h]
0x1400635dc  mov     ecx, eax
0x1400635de  mov     r14d, eax
0x1400635e1  call    HsmDbgBreakOnStatus
0x1400635e6  test    r14d, r14d
0x1400635e9  jns     short loc_140063623
0x1400635eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400635f2  lea     rax, WPP_GLOBAL_Control
0x1400635f9  cmp     rcx, rax
0x1400635fc  jz      loc_140063289
0x140063602  test    dword ptr [rcx+2Ch], 100h
0x140063609  jz      loc_140063289
0x14006360f  cmp     byte ptr [rcx+29h], 2
0x140063613  jb      loc_140063289
0x140063619  mov     edx, 11h
0x14006361e  jmp     loc_1400634D9
0x140063623  mov     rcx, rsi; Name
0x140063626  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14006362d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
