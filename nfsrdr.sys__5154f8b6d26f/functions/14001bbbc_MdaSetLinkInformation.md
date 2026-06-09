# MdaSetLinkInformation

- ea: `0x14001bbbc`
- end: `0x14001c68b`
- name: `MdaSetLinkInformation`
- size: `2767`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14001b5a0`

## callees

- `0x1400022c0`
- `0x140003510`
- `0x140005c90`
- `0x140008140`
- `0x140009380`
- `0x140009440`
- `0x14000f274`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x14001bbbc`
- `0x14001f9cc`
- `0x140020af4`
- `0x140025040`
- `0x14002fe10`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bd50`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bef8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bf18`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c0b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c1a9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c1d1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bd50`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bef8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bf18`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c0b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c1a9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c1d1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001bd7a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001bda1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001bd7a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001bda1`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14001c330`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14001c330`
- `ntoskrnl!KeReleaseMutex` at `0x14001bd62`
- `ntoskrnl!KeReleaseMutex` at `0x14001bf2a`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1e3`
- `ntoskrnl!KeReleaseMutex` at `0x14001c20f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c265`
- `ntoskrnl!KeReleaseMutex` at `0x14001c2ff`
- `ntoskrnl!KeReleaseMutex` at `0x14001c311`
- `ntoskrnl!KeReleaseMutex` at `0x14001c36f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c381`
- `ntoskrnl!KeReleaseMutex` at `0x14001c5b6`
- `ntoskrnl!KeReleaseMutex` at `0x14001bd62`
- `ntoskrnl!KeReleaseMutex` at `0x14001bf2a`
- `ntoskrnl!KeReleaseMutex` at `0x14001c1e3`
- `ntoskrnl!KeReleaseMutex` at `0x14001c20f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c265`
- `ntoskrnl!KeReleaseMutex` at `0x14001c2ff`
- `ntoskrnl!KeReleaseMutex` at `0x14001c311`
- `ntoskrnl!KeReleaseMutex` at `0x14001c36f`
- `ntoskrnl!KeReleaseMutex` at `0x14001c381`
- `ntoskrnl!KeReleaseMutex` at `0x14001c5b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c511`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c5ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c637`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c511`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c5ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c637`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc9a`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc9a`

## pseudocode

```c
__int64 __fastcall MdaSetLinkInformation(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  _QWORD *v8; // r13
  __int64 v9; // rbx
  char v10; // r12
  WCHAR *Pool2; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  NTSTATUS appended; // ebx
  __int64 v15; // r14
  __int64 v16; // r15
  __int64 v17; // r14
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // r9d
  int v21; // r13d
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rbx
  PCUNICODE_STRING v27; // r11
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // r8
  struct _KMUTANT *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rsi
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // eax
  struct _KMUTANT *v38; // rcx
  int v39; // r15d
  __int64 v40; // r14
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r14
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-D0h] BYREF
  PVOID v47; // [rsp+70h] [rbp-C8h]
  UNICODE_STRING ConstantNameB; // [rsp+78h] [rbp-C0h] BYREF
  int v49[2]; // [rsp+88h] [rbp-B0h]
  __int64 v50; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+98h] [rbp-A0h]
  UNICODE_STRING ConstantNameA; // [rsp+A0h] [rbp-98h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-78h]
  UNICODE_STRING Source; // [rsp+C8h] [rbp-70h] BYREF
  __int128 v56; // [rsp+D8h] [rbp-60h] BYREF
  UNICODE_STRING SourceString; // [rsp+E8h] [rbp-50h] BYREF
  __int64 v59; // [rsp+148h] [rbp+10h] BYREF
  __int64 v60; // [rsp+150h] [rbp+18h]

  Source = 0;
  ConstantNameA = 0;
  ConstantNameB = 0;
  DestinationString = 0;
  v56 = 0;
  SourceString = 0;
  Destination = 0;
  v47 = 0;
  v46 = 0;
  v59 = 0;
  v8 = *(_QWORD **)(a2 + 136);
  *(_QWORD *)v49 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 40LL);
  v54 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v49 + 32LL) + 40LL);
  v60 = a1[10];
  v9 = a1[6];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  v10 = (unsigned __int8)~*(_BYTE *)(v9 + 2) >> 7;
  Pool2 = (WCHAR *)ExAllocatePool2(258, 1560, 827483726);
  v47 = Pool2;
  if ( !Pool2 )
  {
    appended = -1073741670;
LABEL_91:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    return (unsigned int)appended;
  }
  *(_DWORD *)&ConstantNameA.Length = 34078720;
  ConstantNameA.Buffer = Pool2;
  *(_DWORD *)&ConstantNameB.Length = 34078720;
  ConstantNameB.Buffer = Pool2 + 260;
  *(_DWORD *)&DestinationString.Length = 34078720;
  DestinationString.Buffer = Pool2 + 520;
  v15 = *(_QWORD *)(v9 + 24);
  if ( v15 )
  {
    v50 = 0;
    v51 = 0;
    v26 = *(_QWORD *)(v15 + 24);
    LOWORD(v50) = *(_WORD *)(a4 + 16);
    WORD1(v50) = v50;
    v51 = a4 + 20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, a1[7] + 360LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v26 + 360);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, &v50);
    if ( !(unsigned __int8)MdaAreFcbsOnSameRemoteFilesystem(a2, v26, v13) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 149, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
      appended = -1073741612;
      goto LABEL_90;
    }
    Source = *(UNICODE_STRING *)(v15 + 88);
    MdaDissectNameTail(v26 + 360, &v56, &SourceString);
    RtlCopyUnicodeString(&DestinationString, v27);
    LOBYTE(v28) = v10;
    appended = MdaParsePathFast(v49[0], (int)a1, (int)&v56, v28, (__int64)&v46, &Destination, a6, 0);
    if ( appended == 260 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, &Destination);
      appended = -1073741612;
      ExFreePoolWithTag(Destination.Buffer, 0);
    }
    if ( appended >= 0 )
    {
      RtlCopyUnicodeString(&ConstantNameB, &SourceString);
      v16 = *v8;
      v17 = v8[1];
      HacAcquireLock(v17, v29, v30);
      RtlCopyUnicodeString(&ConstantNameA, (PCUNICODE_STRING)(v17 + 80));
      KeReleaseMutex(*(PRKMUTEX *)(v17 + 40), 0);
      v21 = (int)a1;
      goto LABEL_52;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_90;
    v19 = 151;
LABEL_23:
    WPP_SF_d(v18->AttachedDevice, v19, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    goto LABEL_90;
  }
  Source.Length = *(_WORD *)(a4 + 16);
  Source.Buffer = (PWSTR)(a4 + 20);
  if ( Source.Length >= 0x1FEu )
  {
    appended = -1073741773;
LABEL_90:
    ExFreePoolWithTag(v47, 0);
    goto LABEL_91;
  }
  v16 = *v8;
  v17 = v8[1];
  HacAcquireLock(*v8, v12, v13);
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v16 + 64));
  KeReleaseMutex(*(PRKMUTEX *)(v16 + 40), 0);
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Slash);
  if ( appended < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_90;
    v19 = 143;
    goto LABEL_23;
  }
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
  if ( appended < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_90;
    v19 = 142;
    goto LABEL_23;
  }
  MdaDissectNameTail(&DestinationString, &v56, &SourceString);
  LOBYTE(v20) = v10;
  v21 = (int)a1;
  appended = MdaParsePathFast(v49[0], (int)a1, (int)&v56, v20, (__int64)&v46, &Destination, a6, 0);
  if ( appended == 260 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, &Destination);
    appended = -1073741612;
    ExFreePoolWithTag(Destination.Buffer, 0);
  }
  if ( appended < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_90;
    v19 = 145;
    goto LABEL_23;
  }
  RtlCopyUnicodeString(&ConstantNameB, &SourceString);
  HacAcquireLock(v17, v22, v23);
  RtlCopyUnicodeString(&ConstantNameA, (PCUNICODE_STRING)(v17 + 80));
  KeReleaseMutex(*(PRKMUTEX *)(v17 + 40), 0);
LABEL_52:
  HacAcquireLock(v17, v24, v25);
  v31 = *(struct _KMUTANT **)(v17 + 40);
  if ( *(_DWORD *)(v17 + 128) == 2 )
  {
    KeReleaseMutex(v31, 0);
    if ( (unsigned __int8)HacFindOpenHandles(v17) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
      appended = -1073741790;
      v34 = v46;
      goto LABEL_87;
    }
  }
  else
  {
    KeReleaseMutex(v31, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, &ConstantNameB);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, &ConstantNameA);
  HacAcquireLock(v16, v32, v33);
  v34 = v46;
  HacAcquireLock(v46, v35, v36);
  v37 = AreHandlesEqual(v16 + 216, v34 + 216);
  v38 = *(struct _KMUTANT **)(v16 + 40);
  if ( v37 )
  {
    KeReleaseMutex(v38, 0);
    KeReleaseMutex(*(PRKMUTEX *)(v34 + 40), 0);
    if ( FsRtlAreNamesEqual(&ConstantNameA, &ConstantNameB, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
      appended = 0;
      goto LABEL_87;
    }
  }
  else
  {
    KeReleaseMutex(v38, 0);
    KeReleaseMutex(*(PRKMUTEX *)(v34 + 40), 0);
  }
  v39 = v49[0];
  if ( (int)CaseInsensitiveLookup(v49[0], v21, (unsigned int)&DestinationString, v34, v10, (__int64)&v59) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    appended = -1073741771;
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  appended = NfsLink(v39, v21, v17, v34, (__int64)&ConstantNameB, *(_DWORD *)(v17 + 128) == 2);
  if ( appended < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
LABEL_85:
    if ( v59 )
    {
      v43 = v60;
      HacDereference(v60, v59);
      goto LABEL_88;
    }
LABEL_87:
    v43 = v60;
LABEL_88:
    if ( v34 )
      HacDereference(v43, v34);
    goto LABEL_90;
  }
  v40 = v60;
  RemoveNegativeCacheEntry(v60, v54, &DestinationString);
  appended = CaseInsensitiveLookup(v39, v21, (unsigned int)&DestinationString, v34, v10, (__int64)&v59);
  if ( appended < 0 )
    goto LABEL_85;
  HacAcquireLock(v59, v41, v42);
  MdaNotifyFullReportChange(*(PFAST_MUTEX *)(v54 + 104), 0, 0, 64, 1, 0);
  KeReleaseMutex(*(PRKMUTEX *)(v59 + 40), 0);
  ExFreePoolWithTag(v47, 0);
  HacDereference(v40, v34);
  if ( v59 )
    HacDereference(v40, v59);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14001bbbc  mov     rax, rsp
0x14001bbbf  mov     [rax+8], rcx
0x14001bbc3  push    rbx
0x14001bbc4  push    rsi
0x14001bbc5  push    rdi
0x14001bbc6  push    r12
0x14001bbc8  push    r13
0x14001bbca  push    r14
0x14001bbcc  push    r15
0x14001bbce  sub     rsp, 100h
0x14001bbd5  mov     rsi, r9
0x14001bbd8  mov     r15, rdx
0x14001bbdb  xorps   xmm0, xmm0
0x14001bbde  movups  xmmword ptr [rax-70h], xmm0
0x14001bbe2  xorps   xmm1, xmm1
0x14001bbe5  movups  xmmword ptr [rax-98h], xmm1
0x14001bbec  movups  xmmword ptr [rsp+138h+ConstantNameB.Length], xmm0
0x14001bbf1  movups  xmmword ptr [rsp+138h+DestinationString.Length], xmm1
0x14001bbf6  movups  xmmword ptr [rax-60h], xmm0
0x14001bbfa  movups  xmmword ptr [rax-50h], xmm1
0x14001bbfe  movups  xmmword ptr [rax-88h], xmm0
0x14001bc05  xor     r14d, r14d
0x14001bc08  mov     [rsp+138h+var_C8], r14
0x14001bc0d  mov     [rsp+138h+var_D0], r14
0x14001bc12  mov     [rax+10h], r14
0x14001bc16  mov     r13, [rdx+88h]
0x14001bc1d  mov     rax, [r8+20h]
0x14001bc21  mov     rax, [rax+28h]
0x14001bc25  mov     qword ptr [rsp+138h+var_B0], rax
0x14001bc2d  mov     rax, [rax+20h]
0x14001bc31  mov     rax, [rax+28h]
0x14001bc35  mov     [rsp+138h+var_78], rax
0x14001bc3d  mov     rax, [rcx+50h]
0x14001bc41  mov     [rsp+138h+arg_10], rax
0x14001bc49  mov     rbx, [rcx+30h]
0x14001bc4d  lea     rax, WPP_GLOBAL_Control
0x14001bc54  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc5b  lea     rdi, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001bc62  cmp     rcx, rax
0x14001bc65  jz      short loc_14001BC7F
0x14001bc67  mov     eax, [rcx+2Ch]
0x14001bc6a  test    al, 8
0x14001bc6c  jz      short loc_14001BC7F
0x14001bc6e  mov     edx, 8Dh
0x14001bc73  mov     r8, rdi
0x14001bc76  mov     rcx, [rcx+18h]
0x14001bc7a  call    WPP_SF_
0x14001bc7f  mov     r12b, [rbx+2]
0x14001bc83  not     r12b
0x14001bc86  shr     r12b, 7
0x14001bc8a  mov     edx, 618h
0x14001bc8f  mov     ecx, 102h
0x14001bc94  mov     r8d, 3152664Eh
0x14001bc9a  call    cs:__imp_ExAllocatePool2
0x14001bca1  nop     dword ptr [rax+rax+00h]
0x14001bca6  mov     rcx, rax
0x14001bca9  mov     [rsp+138h+var_C8], rax
0x14001bcae  test    rax, rax
0x14001bcb1  jnz     short loc_14001BCC1
0x14001bcb3  mov     ebx, 0C000009Ah
0x14001bcb8  mov     [rsp+138h+var_E8], ebx
0x14001bcbc  jmp     loc_14001C51D
0x14001bcc1  mov     dword ptr [rsp+138h+ConstantNameA.Length], 2080000h
0x14001bccc  mov     [rsp+138h+ConstantNameA.Buffer], rcx
0x14001bcd4  mov     dword ptr [rsp+138h+ConstantNameB.Length], 2080000h
0x14001bcdc  add     rax, 208h
0x14001bce2  mov     [rsp+138h+ConstantNameB.Buffer], rax
0x14001bcea  mov     dword ptr [rsp+138h+DestinationString.Length], 2080000h
0x14001bcf2  lea     rax, [rcx+410h]
0x14001bcf9  mov     [rsp+138h+DestinationString.Buffer], rax
0x14001bcfe  mov     r14, [rbx+18h]
0x14001bd02  lea     rcx, [rsi+14h]
0x14001bd06  test    r14, r14
0x14001bd09  jnz     loc_14001BF67
0x14001bd0f  movzx   eax, word ptr [rsi+10h]
0x14001bd13  mov     [rsp+138h+Source.Length], ax
0x14001bd1b  mov     [rsp+138h+Source.Buffer], rcx
0x14001bd23  mov     ecx, 1FEh
0x14001bd28  cmp     ax, cx
0x14001bd2b  jb      short loc_14001BD37
0x14001bd2d  mov     ebx, 0C0000033h
0x14001bd32  jmp     loc_14001C07B
0x14001bd37  mov     r15, [r13+0]
0x14001bd3b  mov     r14, [r13+8]
0x14001bd3f  mov     rcx, r15
0x14001bd42  call    HacAcquireLock
0x14001bd47  lea     rdx, [r15+40h]; SourceString
0x14001bd4b  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x14001bd50  call    cs:__imp_RtlCopyUnicodeString
0x14001bd57  nop     dword ptr [rax+rax+00h]
0x14001bd5c  xor     edx, edx; Wait
0x14001bd5e  mov     rcx, [r15+28h]; Mutex
0x14001bd62  call    cs:__imp_KeReleaseMutex
0x14001bd69  nop     dword ptr [rax+rax+00h]
0x14001bd6e  lea     rdx, Slash; Source
0x14001bd75  lea     rcx, [rsp+138h+DestinationString]; Destination
0x14001bd7a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001bd81  nop     dword ptr [rax+rax+00h]
0x14001bd86  mov     ebx, eax
0x14001bd88  mov     [rsp+138h+var_E8], eax
0x14001bd8c  test    eax, eax
0x14001bd8e  js      loc_14001BF3B
0x14001bd94  lea     rdx, [rsp+138h+Source]; Source
0x14001bd9c  lea     rcx, [rsp+138h+DestinationString]; Destination
0x14001bda1  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001bda8  nop     dword ptr [rax+rax+00h]
0x14001bdad  mov     ebx, eax
0x14001bdaf  mov     [rsp+138h+var_E8], eax
0x14001bdb3  test    eax, eax
0x14001bdb5  jns     short loc_14001BDE3
0x14001bdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdbe  lea     rsi, WPP_GLOBAL_Control
0x14001bdc5  cmp     rcx, rsi
0x14001bdc8  jz      loc_14001C50A
0x14001bdce  mov     eax, [rcx+2Ch]
0x14001bdd1  test    al, 1
0x14001bdd3  jz      loc_14001C50A
0x14001bdd9  mov     edx, 8Eh
0x14001bdde  jmp     loc_14001BED7
0x14001bde3  lea     r8, [rsp+138h+SourceString]
0x14001bdeb  lea     rdx, [rsp+138h+var_60]
0x14001bdf3  lea     rcx, [rsp+138h+DestinationString]
0x14001bdf8  call    MdaDissectNameTail
0x14001bdfd  mov     [rsp+138h+var_100], 0; __int64
0x14001be06  mov     rax, [rsp+138h+arg_28]
0x14001be0e  mov     [rsp+138h+var_108], rax; __int64
0x14001be13  lea     rax, [rsp+138h+var_88]
0x14001be1b  mov     [rsp+138h+Destination], rax; Destination
0x14001be20  lea     rax, [rsp+138h+var_D0]
0x14001be25  mov     qword ptr [rsp+138h+var_118], rax; __int64
0x14001be2a  mov     r9b, r12b; int
0x14001be2d  lea     r8, [rsp+138h+var_60]; int
0x14001be35  mov     r13, qword ptr [rsp+138h+arg_0]
0x14001be3d  mov     rdx, r13; int
0x14001be40  mov     rcx, qword ptr [rsp+138h+var_B0]; int
0x14001be48  call    MdaParsePathFast
0x14001be4d  mov     ebx, eax
0x14001be4f  mov     [rsp+138h+var_E8], eax
0x14001be53  cmp     eax, 104h
0x14001be58  jnz     short loc_14001BEAC
0x14001be5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be61  lea     rsi, WPP_GLOBAL_Control
0x14001be68  cmp     rcx, rsi
0x14001be6b  jz      short loc_14001BE8B
0x14001be6d  mov     eax, [rcx+2Ch]
0x14001be70  test    al, 1
0x14001be72  jz      short loc_14001BE8B
0x14001be74  lea     edx, [rbx-74h]
0x14001be77  lea     r9, [rsp+138h+var_88]
0x14001be7f  mov     r8, rdi
0x14001be82  mov     rcx, [rcx+18h]
0x14001be86  call    WPP_SF_Z
0x14001be8b  mov     ebx, 0C00000D4h
0x14001be90  mov     [rsp+138h+var_E8], ebx
0x14001be94  xor     edx, edx; Tag
0x14001be96  mov     rcx, [rsp+138h+var_88.Buffer]; P
0x14001be9e  call    cs:__imp_ExFreePoolWithTag
0x14001bea5  nop     dword ptr [rax+rax+00h]
0x14001beaa  jmp     short loc_14001BEB3
0x14001beac  lea     rsi, WPP_GLOBAL_Control
0x14001beb3  test    ebx, ebx
0x14001beb5  jns     short loc_14001BEEB
0x14001beb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bebe  cmp     rcx, rsi
0x14001bec1  jz      loc_14001C50A
0x14001bec7  mov     eax, [rcx+2Ch]
0x14001beca  test    al, 1
0x14001becc  jz      loc_14001C50A
0x14001bed2  mov     edx, 91h
0x14001bed7  mov     r9d, ebx
0x14001beda  mov     r8, rdi
0x14001bedd  mov     rcx, [rcx+18h]
0x14001bee1  call    WPP_SF_d
0x14001bee6  jmp     loc_14001C50A
0x14001beeb  lea     rdx, [rsp+138h+SourceString]; SourceString
0x14001bef3  lea     rcx, [rsp+138h+ConstantNameB]; DestinationString
0x14001bef8  call    cs:__imp_RtlCopyUnicodeString
0x14001beff  nop     dword ptr [rax+rax+00h]
0x14001bf04  mov     rcx, r14
0x14001bf07  call    HacAcquireLock
0x14001bf0c  lea     rdx, [r14+50h]; SourceString
0x14001bf10  lea     rcx, [rsp+138h+ConstantNameA]; DestinationString
0x14001bf18  call    cs:__imp_RtlCopyUnicodeString
0x14001bf1f  nop     dword ptr [rax+rax+00h]
0x14001bf24  xor     edx, edx; Wait
0x14001bf26  mov     rcx, [r14+28h]; Mutex
0x14001bf2a  call    cs:__imp_KeReleaseMutex
0x14001bf31  nop     dword ptr [rax+rax+00h]
0x14001bf36  jmp     loc_14001C1F7
0x14001bf3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf42  lea     rax, WPP_GLOBAL_Control
0x14001bf49  cmp     rcx, rax
0x14001bf4c  jz      loc_14001C50A
0x14001bf52  mov     eax, [rcx+2Ch]
0x14001bf55  test    al, 1
0x14001bf57  jz      loc_14001C50A
0x14001bf5d  mov     edx, 8Fh
0x14001bf62  jmp     loc_14001BED7
0x14001bf67  xor     eax, eax
0x14001bf69  mov     [rsp+138h+var_A8], rax
0x14001bf71  mov     [rsp+138h+var_A0], rax
0x14001bf79  mov     rbx, [r14+18h]
0x14001bf7d  movzx   eax, word ptr [rsi+10h]
0x14001bf81  mov     word ptr [rsp+138h+var_A8], ax
0x14001bf89  mov     word ptr [rsp+138h+var_A8+2], ax
0x14001bf91  mov     [rsp+138h+var_A0], rcx
0x14001bf99  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfa0  lea     rdx, WPP_GLOBAL_Control
0x14001bfa7  mov     rsi, qword ptr [rsp+138h+arg_0]
0x14001bfaf  cmp     rcx, rdx
0x14001bfb2  jz      short loc_14001BFDE
0x14001bfb4  mov     eax, [rcx+2Ch]
0x14001bfb7  test    al, 4
0x14001bfb9  jz      short loc_14001BFDE
0x14001bfbb  mov     r9, [rsi+38h]
0x14001bfbf  add     r9, 168h
0x14001bfc6  mov     edx, 92h
0x14001bfcb  mov     r8, rdi
0x14001bfce  mov     rcx, [rcx+18h]
0x14001bfd2  call    WPP_SF_Z
0x14001bfd7  lea     rdx, WPP_GLOBAL_Control
0x14001bfde  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfe5  cmp     rcx, rdx
0x14001bfe8  jz      short loc_14001C010
0x14001bfea  mov     eax, [rcx+2Ch]
0x14001bfed  test    al, 4
0x14001bfef  jz      short loc_14001C010
0x14001bff1  lea     r9, [rbx+168h]
0x14001bff8  mov     edx, 93h
0x14001bffd  mov     r8, rdi
0x14001c000  mov     rcx, [rcx+18h]
0x14001c004  call    WPP_SF_Z
0x14001c009  lea     rdx, WPP_GLOBAL_Control
0x14001c010  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c017  cmp     rcx, rdx
0x14001c01a  jz      short loc_14001C03C
0x14001c01c  mov     eax, [rcx+2Ch]
0x14001c01f  test    al, 4
0x14001c021  jz      short loc_14001C03C
0x14001c023  mov     edx, 94h
0x14001c028  lea     r9, [rsp+138h+var_A8]
0x14001c030  mov     r8, rdi
0x14001c033  mov     rcx, [rcx+18h]
0x14001c037  call    WPP_SF_Z
0x14001c03c  mov     rdx, rbx
0x14001c03f  mov     rcx, r15
0x14001c042  call    MdaAreFcbsOnSameRemoteFilesystem
0x14001c047  test    al, al
0x14001c049  jnz     short loc_14001C084
0x14001c04b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c052  lea     rax, WPP_GLOBAL_Control
0x14001c059  cmp     rcx, rax
0x14001c05c  jz      short loc_14001C076
0x14001c05e  mov     eax, [rcx+2Ch]
0x14001c061  test    al, 1
0x14001c063  jz      short loc_14001C076
0x14001c065  mov     edx, 95h
0x14001c06a  mov     r8, rdi
0x14001c06d  mov     rcx, [rcx+18h]
0x14001c071  call    WPP_SF_
0x14001c076  mov     ebx, 0C00000D4h
0x14001c07b  mov     [rsp+138h+var_E8], ebx
0x14001c07f  jmp     loc_14001C50A
0x14001c084  movups  xmm0, xmmword ptr [r14+58h]
0x14001c089  movdqu  xmmword ptr [rsp+138h+Source.Length], xmm0
0x14001c092  lea     r11, [rbx+168h]
0x14001c099  lea     r8, [rsp+138h+SourceString]
0x14001c0a1  lea     rdx, [rsp+138h+var_60]
0x14001c0a9  mov     rcx, r11
0x14001c0ac  call    MdaDissectNameTail
0x14001c0b1  mov     rdx, r11; SourceString
0x14001c0b4  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x14001c0b9  call    cs:__imp_RtlCopyUnicodeString
0x14001c0c0  nop     dword ptr [rax+rax+00h]
0x14001c0c5  mov     [rsp+138h+var_100], 0; __int64
0x14001c0ce  mov     rax, [rsp+138h+arg_28]
0x14001c0d6  mov     [rsp+138h+var_108], rax; __int64
0x14001c0db  lea     rax, [rsp+138h+var_88]
0x14001c0e3  mov     [rsp+138h+Destination], rax; Destination
0x14001c0e8  lea     rax, [rsp+138h+var_D0]
0x14001c0ed  mov     qword ptr [rsp+138h+var_118], rax; __int64
0x14001c0f2  mov     r9b, r12b; int
0x14001c0f5  lea     r8, [rsp+138h+var_60]; int
0x14001c0fd  mov     rdx, rsi; int
0x14001c100  mov     rcx, qword ptr [rsp+138h+var_B0]; int
0x14001c108  call    MdaParsePathFast
0x14001c10d  mov     ebx, eax
0x14001c10f  mov     [rsp+138h+var_E8], eax
0x14001c113  cmp     eax, 104h
0x14001c118  jnz     short loc_14001C16C
0x14001c11a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c121  lea     rsi, WPP_GLOBAL_Control
0x14001c128  cmp     rcx, rsi
0x14001c12b  jz      short loc_14001C14B
0x14001c12d  mov     eax, [rcx+2Ch]
0x14001c130  test    al, 1
0x14001c132  jz      short loc_14001C14B
0x14001c134  lea     edx, [rbx-6Eh]
0x14001c137  lea     r9, [rsp+138h+var_88]
0x14001c13f  mov     r8, rdi
  ... truncated ...
```
