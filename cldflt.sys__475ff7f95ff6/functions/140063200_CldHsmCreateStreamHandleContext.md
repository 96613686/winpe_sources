# CldHsmCreateStreamHandleContext

- ea: `0x140063200`
- end: `0x1400638a5`
- name: `CldHsmCreateStreamHandleContext`
- size: `1701`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x140063200`
- `0x1400638b0`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400634b2`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400634b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063879`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063879`
- `ntoskrnl!ExAllocatePool2` at `0x1400636b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400636b4`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400632a1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400632cc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400632a1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400632cc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063894`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063894`
- `ntoskrnl!PsInitialSystemProcess` at `0x140063295`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140063596`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400636f0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140063596`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400636f0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006325a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006325a`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140063746`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1400637fa`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140063746`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1400637fa`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063762`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063820`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063762`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140063820`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063778`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063847`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063778`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140063847`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006362e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006362e`
- `FLTMGR!FltReleasePushLockEx` at `0x140063390`
- `FLTMGR!FltReleasePushLockEx` at `0x1400634d1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400634e8`
- `FLTMGR!FltReleasePushLockEx` at `0x140063390`
- `FLTMGR!FltReleasePushLockEx` at `0x1400634d1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400634e8`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006349a`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006349a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140063860`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140063860`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006332e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140063472`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006332e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140063472`

## pseudocode

```c
__int64 __fastcall CldHsmCreateStreamHandleContext(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  NTSTATUS FileNameInformationUnsafe; // r14d
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
  __int64 v27; // [rsp+30h] [rbp-58h]
  struct _FILE_OBJECT *FileObject; // [rsp+38h] [rbp-50h]
  ULONG ProcessInformationLength; // [rsp+90h] [rbp+8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp+18h]
  __int64 Buffer; // [rsp+A8h] [rbp+20h] BYREF

  v31 = a3;
  FileNameInformationUnsafe = 0;
  v4 = a2[2];
  Pool2 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(*a2 + 16LL) + 32LL);
  v27 = v7;
  FileObject = *(struct _FILE_OBJECT **)(a1 + 48);
  ProcessInformationLength = 0;
  FileNameInformation = 0;
  v9 = ExAllocateFromPagedLookasideList(&stru_140028B80);
  v10 = v9;
  if ( !v9 )
  {
    FileNameInformationUnsafe = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
        0,
        v7,
        -1073741670);
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
      v7 = v27;
    }
    FltReleasePushLockEx(v4 + 24, 0);
  }
  v11 = *(_QWORD *)(v4 + 32);
  if ( v11 )
  {
    FileNameInformationUnsafe = CldStreamOpen(a2);
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
          v10,
          v7,
          FileNameInformationUnsafe);
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
    *v31 = v10;
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
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, 0, 0x102u, &FileNameInformation);
      HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
      if ( FileNameInformationUnsafe < 0 )
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
            FileObject,
            FileNameInformationUnsafe);
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
    FileNameInformationUnsafe = ZwQueryInformationProcess(
                                  (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                  ProcessImageFileName,
                                  0,
                                  0,
                                  &ProcessInformationLength);
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
    if ( ((FileNameInformationUnsafe + 0x80000000) & 0x80000000) == 0 && FileNameInformationUnsafe != -1073741820 )
      break;
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(256, ProcessInformationLength, 1852861507);
    if ( !Pool2 )
    {
      FileNameInformationUnsafe = -1073741670;
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
      WPP_SF_qd(
        v25->AttachedDevice,
        v26,
        WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
        a1,
        FileNameInformationUnsafe);
      goto LABEL_22;
    }
    FileNameInformationUnsafe = ZwQueryInformationProcess(
                                  (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                  ProcessImageFileName,
                                  Pool2,
                                  ProcessInformationLength,
                                  &ProcessInformationLength);
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
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
0x140063200  mov     r11, rsp
0x140063203  mov     [r11+18h], r8
0x140063207  push    rdi
0x140063208  push    r14
0x14006320a  sub     rsp, 78h
0x14006320e  mov     rax, [rdx]
0x140063211  xor     r14d, r14d
0x140063214  mov     [r11-18h], rbx
0x140063218  mov     [r11-20h], rbp
0x14006321c  mov     rbp, [rdx+10h]
0x140063220  mov     r9, [rax+10h]
0x140063224  mov     rax, [rcx+30h]
0x140063228  mov     [r11-28h], rsi
0x14006322c  mov     rsi, rdx
0x14006322f  mov     [r11-30h], r12
0x140063233  mov     r12d, r14d
0x140063236  mov     rbx, [r9+20h]
0x14006323a  mov     [r11-38h], r13
0x14006323e  mov     r13, rcx
0x140063241  lea     rcx, stru_140028B80; Lookaside
0x140063248  mov     [rsp+88h+var_58], rbx
0x14006324d  mov     [rsp+88h+FileObject], rax
0x140063252  mov     [r11+8], r14d
0x140063256  mov     [r11+10h], r14
0x14006325a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140063261  nop     dword ptr [rax+rax+00h]
0x140063266  mov     rdi, rax
0x140063269  test    rax, rax
0x14006326c  jz      loc_14006350C
0x140063272  mov     [rax], r13
0x140063275  mov     [rax+8], rsi
0x140063279  mov     [rsp+88h+var_40], r15
0x14006327e  cmp     [rbp+20h], r14
0x140063282  jz      loc_140063462
0x140063288  mov     r15, [rbp+20h]
0x14006328c  test    r15, r15
0x14006328f  jnz     loc_1400633F6
0x140063295  mov     rax, cs:__imp_PsInitialSystemProcess
0x14006329c  xor     ebx, ebx
0x14006329e  mov     rsi, [rax]
0x1400632a1  call    cs:__imp_IoGetCurrentProcess
0x1400632a8  nop     dword ptr [rax+rax+00h]
0x1400632ad  cmp     rax, rsi
0x1400632b0  jz      short loc_140063328
0x1400632b2  test    r15, r15
0x1400632b5  jz      loc_1400634F9
0x1400632bb  mov     rax, [r15+60h]
0x1400632bf  test    rax, rax
0x1400632c2  jz      loc_1400634F9
0x1400632c8  mov     rsi, [rax+68h]
0x1400632cc  call    cs:__imp_IoGetCurrentProcess
0x1400632d3  nop     dword ptr [rax+rax+00h]
0x1400632d8  cmp     rax, rsi
0x1400632db  jz      short loc_140063328
0x1400632dd  mov     rsi, cs:Expression
0x1400632e4  mov     r15d, 80000000h
0x1400632ea  mov     rax, [rsi+8]
0x1400632ee  test    rax, rax
0x1400632f1  jz      short loc_140063307
0x1400632f3  cmp     word ptr [rax], 2Ah ; '*'
0x1400632f7  jnz     loc_14006356E
0x1400632fd  cmp     word ptr [rsi], 2
0x140063301  jnz     loc_14006356E
0x140063307  mov     rax, [rsi+18h]
0x14006330b  test    rax, rax
0x14006330e  jz      short loc_140063325
0x140063310  cmp     word ptr [rax], 2Ah ; '*'
0x140063314  jnz     loc_140063616
0x14006331a  cmp     word ptr [rsi+10h], 2
0x14006331f  jnz     loc_140063616
0x140063325  mov     ebx, [rsi+20h]
0x140063328  xor     edx, edx
0x14006332a  lea     rcx, [rbp+18h]
0x14006332e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140063335  nop     dword ptr [rax+rax+00h]
0x14006333a  mov     edx, [rbp+28h]
0x14006333d  mov     eax, ebx
0x14006333f  mov     ecx, edx
0x140063341  and     eax, 0Fh
0x140063344  mov     r9d, edx
0x140063347  and     ecx, 0Fh
0x14006334a  cmp     cl, al
0x14006334c  lea     rcx, [rbp+18h]
0x140063350  cmovbe  r9d, ebx
0x140063354  shr     ebx, 4
0x140063357  xor     r9d, edx
0x14006335a  mov     eax, ebx
0x14006335c  and     r9d, 0Fh
0x140063360  and     eax, 0Fh
0x140063363  xor     r9d, edx
0x140063366  mov     r8d, r9d
0x140063369  shr     r8d, 4
0x14006336d  mov     edx, r8d
0x140063370  and     edx, 0Fh
0x140063373  cmp     dl, al
0x140063375  cmovbe  r8d, ebx
0x140063379  xor     edx, edx
0x14006337b  shl     r8d, 4
0x14006337f  xor     r8d, r9d
0x140063382  and     r8d, 0F0h
0x140063389  xor     r8d, r9d
0x14006338c  mov     [rbp+28h], r8d
0x140063390  call    cs:__imp_FltReleasePushLockEx
0x140063397  nop     dword ptr [rax+rax+00h]
0x14006339c  mov     rax, [rsp+88h+arg_10]
0x1400633a4  mov     [rax], rdi
0x1400633a7  xor     edi, edi
0x1400633a9  mov     r15, [rsp+88h+var_40]
0x1400633ae  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x1400633b6  mov     r13, [rsp+88h+var_38]
0x1400633bb  mov     rsi, [rsp+88h+var_28]
0x1400633c0  mov     rbp, [rsp+88h+var_20]
0x1400633c5  mov     rbx, [rsp+88h+var_18]
0x1400633ca  test    rcx, rcx
0x1400633cd  jnz     loc_140063860
0x1400633d3  test    r12, r12
0x1400633d6  jnz     loc_140063871
0x1400633dc  mov     r12, [rsp+88h+var_30]
0x1400633e1  test    rdi, rdi
0x1400633e4  jnz     loc_14006388A
0x1400633ea  mov     eax, r14d
0x1400633ed  add     rsp, 78h
0x1400633f1  pop     r14
0x1400633f3  pop     rdi
0x1400633f4  retn
0x1400633f6  mov     rcx, rsi
0x1400633f9  call    CldStreamOpen
0x1400633fe  mov     ecx, eax
0x140063400  mov     r14d, eax
0x140063403  call    HsmDbgBreakOnStatus
0x140063408  test    r14d, r14d
0x14006340b  jns     loc_140063295
0x140063411  mov     rcx, cs:WPP_GLOBAL_Control
0x140063418  lea     rax, WPP_GLOBAL_Control
0x14006341f  cmp     rcx, rax
0x140063422  jz      short loc_1400633A9
0x140063424  test    dword ptr [rcx+2Ch], 100h
0x14006342b  jz      loc_1400633A9
0x140063431  cmp     byte ptr [rcx+29h], 2
0x140063435  jb      loc_1400633A9
0x14006343b  mov     rcx, [rcx+18h]
0x14006343f  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063446  mov     edx, 0Eh
0x14006344b  mov     [rsp+88h+var_60], r14d
0x140063450  mov     r9, rdi
0x140063453  mov     [rsp+88h+ReturnLength], rbx
0x140063458  call    WPP_SF_qqd
0x14006345d  jmp     loc_1400633A9
0x140063462  cmp     [rbp+10h], r12
0x140063466  jz      loc_140063288
0x14006346c  xor     edx, edx
0x14006346e  lea     rcx, [rbp+18h]
0x140063472  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140063479  nop     dword ptr [rax+rax+00h]
0x14006347e  cmp     [rbp+20h], r12
0x140063482  jnz     short loc_1400634E2
0x140063484  mov     rbx, [rbp+8]
0x140063488  xor     edx, edx
0x14006348a  mov     rax, [rbp+10h]
0x14006348e  mov     [rsp+88h+Buffer], rax
0x140063496  lea     rcx, [rbx+8]
0x14006349a  call    cs:__imp_FltAcquirePushLockSharedEx
0x1400634a1  nop     dword ptr [rax+rax+00h]
0x1400634a6  lea     rcx, [rbx+10h]; Table
0x1400634aa  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1400634b2  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400634b9  nop     dword ptr [rax+rax+00h]
0x1400634be  test    rax, rax
0x1400634c1  jz      short loc_140063500
0x1400634c3  mov     rax, [rax+8]
0x1400634c7  mov     [rbp+20h], rax
0x1400634cb  xor     edx, edx
0x1400634cd  lea     rcx, [rbx+8]
0x1400634d1  call    cs:__imp_FltReleasePushLockEx
0x1400634d8  nop     dword ptr [rax+rax+00h]
0x1400634dd  mov     rbx, [rsp+88h+var_58]
0x1400634e2  xor     edx, edx
0x1400634e4  lea     rcx, [rbp+18h]
0x1400634e8  call    cs:__imp_FltReleasePushLockEx
0x1400634ef  nop     dword ptr [rax+rax+00h]
0x1400634f4  jmp     loc_140063288
0x1400634f9  xor     esi, esi
0x1400634fb  jmp     loc_1400632CC
0x140063500  mov     ecx, 0C000CF01h
0x140063505  call    HsmDbgBreakOnStatus
0x14006350a  jmp     short loc_1400634CB
0x14006350c  mov     ecx, 0C000009Ah
0x140063511  mov     r14d, ecx
0x140063514  call    HsmDbgBreakOnStatus
0x140063519  mov     rcx, cs:WPP_GLOBAL_Control
0x140063520  lea     rax, WPP_GLOBAL_Control
0x140063527  cmp     rcx, rax
0x14006352a  jz      loc_1400633AE
0x140063530  test    dword ptr [rcx+2Ch], 100h
0x140063537  jz      loc_1400633AE
0x14006353d  cmp     byte ptr [rcx+29h], 2
0x140063541  jb      loc_1400633AE
0x140063547  mov     rcx, [rcx+18h]
0x14006354b  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063552  mov     edx, 0Dh
0x140063557  mov     [rsp+88h+var_60], r14d
0x14006355c  xor     r9d, r9d
0x14006355f  mov     [rsp+88h+ReturnLength], rbx
0x140063564  call    WPP_SF_qqd
0x140063569  jmp     loc_1400633AE
0x14006356e  test    r12, r12
0x140063571  jnz     loc_140063743
0x140063577  lea     rax, [rsp+88h+ProcessInformationLength]
0x14006357f  xor     r9d, r9d; ProcessInformationLength
0x140063582  xor     r8d, r8d; ProcessInformation
0x140063585  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x14006358a  mov     edx, 1Bh; ProcessInformationClass
0x14006358f  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140063596  call    cs:__imp_ZwQueryInformationProcess
0x14006359d  nop     dword ptr [rax+rax+00h]
0x1400635a2  mov     ecx, eax
0x1400635a4  mov     r14d, eax
0x1400635a7  call    HsmDbgBreakOnStatus
0x1400635ac  lea     eax, [r14+r15]
0x1400635b0  test    r15d, eax
0x1400635b3  jnz     loc_1400636A2
0x1400635b9  cmp     r14d, 0C0000004h
0x1400635c0  jz      loc_1400636A2
0x1400635c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400635cd  lea     rax, WPP_GLOBAL_Control
0x1400635d4  cmp     rcx, rax
0x1400635d7  jz      loc_1400633A9
0x1400635dd  test    dword ptr [rcx+2Ch], 100h
0x1400635e4  jz      loc_1400633A9
0x1400635ea  cmp     byte ptr [rcx+29h], 2
0x1400635ee  jb      loc_1400633A9
0x1400635f4  mov     edx, 0Fh
0x1400635f9  mov     rcx, [rcx+18h]
0x1400635fd  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063604  mov     r9, r13
0x140063607  mov     dword ptr [rsp+88h+ReturnLength], r14d
0x14006360c  call    WPP_SF_qd
0x140063611  jmp     loc_1400633A9
0x140063616  mov     r15, [rsp+88h+FileObject]
0x14006361b  lea     r9, [rsp+88h+FileNameInformation]; FileNameInformation
0x140063623  mov     rcx, r15; FileObject
0x140063626  xor     edx, edx; Instance
0x140063628  mov     r8d, 102h; NameOptions
0x14006362e  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140063635  nop     dword ptr [rax+rax+00h]
0x14006363a  mov     ecx, eax
0x14006363c  mov     r14d, eax
0x14006363f  call    HsmDbgBreakOnStatus
0x140063644  test    r14d, r14d
0x140063647  jns     loc_1400637DA
0x14006364d  mov     rcx, cs:WPP_GLOBAL_Control
0x140063654  lea     rax, WPP_GLOBAL_Control
0x14006365b  cmp     rcx, rax
0x14006365e  jz      loc_1400633A9
0x140063664  test    dword ptr [rcx+2Ch], 100h
0x14006366b  jz      loc_1400633A9
0x140063671  cmp     byte ptr [rcx+29h], 2
0x140063675  jb      loc_1400633A9
0x14006367b  mov     rcx, [rcx+18h]
0x14006367f  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x140063686  mov     edx, 12h
0x14006368b  mov     [rsp+88h+var_60], r14d
0x140063690  mov     r9, r13
0x140063693  mov     [rsp+88h+ReturnLength], r15
0x140063698  call    WPP_SF_qqd
0x14006369d  jmp     loc_1400633A9
0x1400636a2  mov     edx, [rsp+88h+ProcessInformationLength]
0x1400636a9  mov     ecx, 100h
0x1400636ae  mov     r8d, 6E706C43h
0x1400636b4  call    cs:__imp_ExAllocatePool2
0x1400636bb  nop     dword ptr [rax+rax+00h]
0x1400636c0  mov     r12, rax
0x1400636c3  test    rax, rax
0x1400636c6  jz      loc_140063795
0x1400636cc  mov     r9d, [rsp+88h+ProcessInformationLength]; ProcessInformationLength
0x1400636d4  lea     rax, [rsp+88h+ProcessInformationLength]
0x1400636dc  mov     r8, r12; ProcessInformation
0x1400636df  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1400636e4  mov     edx, 1Bh; ProcessInformationClass
0x1400636e9  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400636f0  call    cs:__imp_ZwQueryInformationProcess
0x1400636f7  nop     dword ptr [rax+rax+00h]
0x1400636fc  mov     ecx, eax
0x1400636fe  mov     r14d, eax
0x140063701  call    HsmDbgBreakOnStatus
0x140063706  test    r14d, r14d
0x140063709  jns     short loc_140063743
0x14006370b  mov     rcx, cs:WPP_GLOBAL_Control
0x140063712  lea     rax, WPP_GLOBAL_Control
0x140063719  cmp     rcx, rax
0x14006371c  jz      loc_1400633A9
0x140063722  test    dword ptr [rcx+2Ch], 100h
0x140063729  jz      loc_1400633A9
0x14006372f  cmp     byte ptr [rcx+29h], 2
0x140063733  jb      loc_1400633A9
0x140063739  mov     edx, 11h
0x14006373e  jmp     loc_1400635F9
0x140063743  mov     rcx, rsi; Name
0x140063746  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14006374d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
