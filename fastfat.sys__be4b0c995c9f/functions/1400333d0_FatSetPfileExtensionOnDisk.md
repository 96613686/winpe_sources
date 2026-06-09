# FatSetPfileExtensionOnDisk

- ea: `0x1400333d0`
- end: `0x140033e7b`
- name: `FatSetPfileExtensionOnDisk`
- size: `2731`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x140034054`

## callees

- `0x1400065a4`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x140024228`
- `0x14002486c`
- `0x14002ca48`
- `0x1400302d8`
- `0x14003062c`
- `0x140031468`
- `0x1400319bc`
- `0x140031e8c`
- `0x1400333d0`
- `0x14004498c`
- `0x140044dc4`
- `0x1400471f8`
- `0x140048680`
- `0x1400486ec`
- `0x1400492a4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x14003375f`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x14003375f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140033802`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140033802`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x1400335a7`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x1400335c6`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x1400335a7`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x1400335c6`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140033794`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140033794`
- `ntoskrnl!CcUnpinData` at `0x140033da6`
- `ntoskrnl!CcUnpinData` at `0x140033dc7`
- `ntoskrnl!CcUnpinData` at `0x140033de8`
- `ntoskrnl!CcUnpinData` at `0x140033e01`
- `ntoskrnl!CcUnpinData` at `0x14005d392`
- `ntoskrnl!CcUnpinData` at `0x14005d3b5`
- `ntoskrnl!CcUnpinData` at `0x14005d3d8`
- `ntoskrnl!CcUnpinData` at `0x14005d3f1`
- `ntoskrnl!CcUnpinData` at `0x140033da6`
- `ntoskrnl!CcUnpinData` at `0x140033dc7`
- `ntoskrnl!CcUnpinData` at `0x140033de8`
- `ntoskrnl!CcUnpinData` at `0x140033e01`
- `ntoskrnl!CcUnpinData` at `0x14005d392`
- `ntoskrnl!CcUnpinData` at `0x14005d3b5`
- `ntoskrnl!CcUnpinData` at `0x14005d3d8`
- `ntoskrnl!CcUnpinData` at `0x14005d3f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033e21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d419`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033e21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d419`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140033b3e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140033b3e`
- `ntoskrnl!ExRaiseStatus` at `0x140033702`
- `ntoskrnl!ExRaiseStatus` at `0x14003381b`
- `ntoskrnl!ExRaiseStatus` at `0x140033966`
- `ntoskrnl!ExRaiseStatus` at `0x140033989`
- `ntoskrnl!ExRaiseStatus` at `0x1400339a4`
- `ntoskrnl!ExRaiseStatus` at `0x140033702`
- `ntoskrnl!ExRaiseStatus` at `0x14003381b`
- `ntoskrnl!ExRaiseStatus` at `0x140033966`
- `ntoskrnl!ExRaiseStatus` at `0x140033989`
- `ntoskrnl!ExRaiseStatus` at `0x1400339a4`

## pseudocode

```c
__int64 __fastcall FatSetPfileExtensionOnDisk(__int64 a1, __int64 a2, char a3)
{
  __int64 v6; // r14
  USHORT Length; // r11
  int v8; // r8d
  bool v9; // r10
  bool v10; // r8
  char v11; // r9
  unsigned int v12; // ecx
  WCHAR v13; // dx
  PWSTR Buffer; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int128 v17; // xmm6
  char v18; // r13
  ULONG v19; // r14d
  __int64 v20; // r12
  unsigned int NewDirent; // eax
  __int64 v22; // rbx
  int v23; // r9d
  __int64 v24; // r12
  char *PoolWithTag; // rax
  char *v26; // r15
  __int64 v27; // r12
  __int64 v28; // rbx
  char v29; // dl
  __int64 v30; // rcx
  char v31; // cl
  __int64 v32; // rbx
  size_t v33; // r12
  size_t v34; // r8
  void *v35; // r12
  void *v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 result; // rax
  __int64 v49; // [rsp+30h] [rbp-318h]
  __int64 v50; // [rsp+30h] [rbp-318h]
  char v51; // [rsp+60h] [rbp-2E8h]
  char v52; // [rsp+61h] [rbp-2E7h]
  char v53; // [rsp+62h] [rbp-2E6h] BYREF
  bool v54; // [rsp+63h] [rbp-2E5h] BYREF
  char v55; // [rsp+64h] [rbp-2E4h]
  char v56; // [rsp+65h] [rbp-2E3h] BYREF
  char v57; // [rsp+66h] [rbp-2E2h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-2E0h] BYREF
  int v59; // [rsp+78h] [rbp-2D0h] BYREF
  NTSTATUS v60; // [rsp+7Ch] [rbp-2CCh] BYREF
  struct _STRING v61; // [rsp+80h] [rbp-2C8h] BYREF
  unsigned int v62; // [rsp+90h] [rbp-2B8h]
  size_t Size; // [rsp+94h] [rbp-2B4h]
  PVOID Bcb; // [rsp+A0h] [rbp-2A8h] BYREF
  PVOID v65; // [rsp+A8h] [rbp-2A0h] BYREF
  char *v66; // [rsp+B0h] [rbp-298h] BYREF
  struct _UNICODE_STRING v67; // [rsp+B8h] [rbp-290h] BYREF
  UNICODE_STRING SourceString; // [rsp+C8h] [rbp-280h] BYREF
  int v69[2]; // [rsp+D8h] [rbp-270h]
  PVOID v70; // [rsp+E0h] [rbp-268h] BYREF
  unsigned int v71; // [rsp+E8h] [rbp-260h] BYREF
  int v72; // [rsp+ECh] [rbp-25Ch]
  int v73; // [rsp+F0h] [rbp-258h]
  PVOID v74; // [rsp+F8h] [rbp-250h] BYREF
  UNICODE_STRING v75; // [rsp+100h] [rbp-248h] BYREF
  __int64 v76; // [rsp+110h] [rbp-238h] BYREF
  __int64 v77; // [rsp+118h] [rbp-230h] BYREF
  void *v78; // [rsp+120h] [rbp-228h]
  void *v79; // [rsp+128h] [rbp-220h] BYREF
  struct _UNICODE_STRING v80; // [rsp+130h] [rbp-218h] BYREF
  ANSI_STRING DbcsName; // [rsp+140h] [rbp-208h] BYREF
  __int64 v82; // [rsp+150h] [rbp-1F8h]
  __int64 v83[2]; // [rsp+158h] [rbp-1F0h] BYREF
  struct _UNICODE_STRING v84[5]; // [rsp+170h] [rbp-1D8h] BYREF
  _QWORD v85[4]; // [rsp+1C0h] [rbp-188h]
  char v86; // [rsp+1E0h] [rbp-168h] BYREF
  char v87; // [rsp+200h] [rbp-148h] BYREF
  char v88; // [rsp+240h] [rbp-108h] BYREF
  char v89; // [rsp+280h] [rbp-C8h] BYREF
  char v90; // [rsp+2C0h] [rbp-88h] BYREF

  v82 = a1;
  v6 = *(_QWORD *)(a2 + 176);
  *(_QWORD *)v69 = v6;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  SourceString = 0;
  *(_DWORD *)(&v80.MaximumLength + 1) = 0;
  v75 = 0;
  *(_OWORD *)v83 = 0;
  v67 = 0;
  *(_DWORD *)(&v61.MaximumLength + 1) = 0;
  memset(v84, 0, sizeof(v84));
  v77 = 0;
  Bcb = 0;
  v71 = 0;
  v59 = 0;
  v76 = 0;
  v65 = 0;
  v66 = 0;
  v74 = 0;
  v78 = 0;
  v79 = 0;
  v70 = 0;
  v52 = 0;
  v54 = 0;
  v53 = 0;
  v56 = 0;
  Size = 0;
  DestinationString.Buffer = (PWSTR)&v87;
  *(_DWORD *)&DestinationString.Length = 0x400000;
  v80.Buffer = (PWSTR)&v86;
  *(_DWORD *)&v80.Length = 1572864;
  v61.Buffer = &v88;
  *(_DWORD *)&v61.Length = 0x400000;
  if ( *(_WORD *)(a2 + 552) )
  {
    FatEnsureStringBufferEnough(&DestinationString);
    v51 = 1;
    memmove(DestinationString.Buffer, *(const void **)(a2 + 560), *(unsigned __int16 *)(a2 + 552));
    Length = *(_WORD *)(a2 + 552);
    DestinationString.Length = Length;
  }
  else
  {
    v62 = 0;
    v55 = 0;
    RtlOemStringToCountedUnicodeString(&DestinationString, (PCOEM_STRING)(a2 + 480), 0);
    v51 = 0;
    RtlOemStringToCountedUnicodeString(&v80, (PCOEM_STRING)(a2 + 480), 0);
    v8 = *(_DWORD *)(a2 + 192);
    v9 = (v8 & 0x1000) != 0;
    v54 = v9;
    v10 = (v8 & 0x2000) != 0;
    v53 = v10;
    v11 = 0;
    v55 = 0;
    v12 = 0;
    Length = DestinationString.Length;
    while ( 1 )
    {
      v62 = v12;
      if ( v12 >= Length >> 1 )
        break;
      v13 = DestinationString.Buffer[v12];
      if ( v13 == 46 )
      {
        v11 = 1;
        v55 = 1;
      }
      else if ( (v9 && !v11 || v10 && v11 == 1) && (unsigned __int16)(v13 - 65) <= 0x19u )
      {
        DestinationString.Buffer[v12] = v13 + 32;
        Length = DestinationString.Length;
      }
      ++v12;
    }
    v6 = *(_QWORD *)v69;
  }
  if ( !a3 )
  {
    FatRemovePfileExtension(&DestinationString);
    SourceString.Buffer = DestinationString.Buffer;
    SourceString.Length = DestinationString.Length;
    SourceString.MaximumLength = DestinationString.MaximumLength;
    FatEnsureStringBufferEnough(&v61);
    v60 = RtlUpcaseUnicodeStringToCountedOemString(&v61, &SourceString, 0);
    if ( v60 < 0 )
    {
      v60 = 0;
    }
    else
    {
      DbcsName = v61;
      if ( FsRtlIsFatDbcsLegal(&DbcsName, 0, 0, 0) && !(unsigned __int8)FatSpaceInName(v15, &SourceString) )
        goto LABEL_24;
    }
    v61.Length = 0;
    goto LABEL_24;
  }
  Buffer = DestinationString.Buffer;
  *(_QWORD *)((char *)DestinationString.Buffer + Length) = *(_QWORD *)L".PFILE";
  *(_DWORD *)((char *)Buffer + Length + 8) = *(_DWORD *)L"LE";
  DestinationString.Length += 12;
  *(_DWORD *)(&v84[0].MaximumLength + 1) = *(_DWORD *)(&v84[0].MaximumLength + 1) & 0xFF000000 | 2;
  SourceString.Buffer = DestinationString.Buffer;
  SourceString.Length = DestinationString.Length - 12;
  SourceString.MaximumLength = DestinationString.MaximumLength;
  if ( DestinationString.Length > 0x1FEu )
  {
    *(_DWORD *)(a1 + 72) = -1073741773;
    ExRaiseStatus(-1073741773);
  }
LABEL_24:
  v67.Buffer = (PWSTR)&v89;
  *(_DWORD *)&v67.Length = 0x400000;
  FatEnsureStringBufferEnough(&v67);
  v16 = RtlUpcaseUnicodeString(&v67, &DestinationString, 0);
  v60 = v16;
  if ( v16 < 0 )
  {
    *(_DWORD *)(a1 + 72) = v16;
    ExRaiseStatus(v16);
  }
  v84[3] = v67;
  LOBYTE(v84[0].Buffer) = 0;
  FatGetDirentFromFcbOrDcb(a1, a2, 0, (unsigned int)&v76, (__int64)&v65);
  v85[0] = *(_QWORD *)v76;
  v72 = *(_DWORD *)(v76 + 7);
  *(_DWORD *)((char *)v85 + 7) = v72;
  v57 = *(_BYTE *)(v76 + 11);
  v17 = *(_OWORD *)(v76 + 12);
  v73 = *(_DWORD *)(v76 + 28);
  v59 = 268435471;
  v75.Buffer = (PWSTR)&v90;
  *(_DWORD *)&v75.Length = 0x400000;
  FatLocateDirent(a1, v6, (__int64)v84, 0, &v59, (PVOID *)&v77, &Bcb, &v71, 0, &v75, v83);
  if ( v77 )
  {
    *(_DWORD *)(a1 + 72) = -1073741790;
    ExRaiseStatus(-1073741790);
  }
  if ( a3 )
  {
    if ( (v59 & 0xC00) != 0 )
    {
      *(_DWORD *)(a1 + 72) = -1073741790;
      ExRaiseStatus(-1073741790);
    }
  }
  else if ( (v59 & 0x10) != 0 )
  {
    *(_DWORD *)(a1 + 72) = -1073741790;
    ExRaiseStatus(-1073741790);
  }
  FatSelectNames(a1, v6, &v61, &DestinationString, &v61, 0, &v54, &v53, &v56);
  v18 = v56;
  if ( v56 )
    v19 = (((unsigned __int64)DestinationString.Length >> 1) + 12) / 0xD + 1;
  else
    v19 = 1;
  FatDeleteDirent(a1, a2, 0, 0);
  v20 = *(_QWORD *)v69;
  NewDirent = FatCreateNewDirent(a1, v69[0], v19);
  v22 = NewDirent;
  v69[0] = NewDirent;
  FatPrepareWriteDirectoryFile(a1, v20, NewDirent, 0x20u, &v74, (PVOID *)&v66, v49, 0, &v60);
  *(_QWORD *)&DbcsName.Length = v22 + 32LL * (v19 - 1);
  if ( ((v22 ^ *(_QWORD *)&DbcsName.Length) & 0xFFFFFFFFFFFFF000uLL) != 0 )
  {
    LODWORD(Size) = (v22 & 0xFFFFF000) + 4096 - v22;
    HIDWORD(Size) = (unsigned int)Size >> 5;
    FatPrepareWriteDirectoryFile(a1, v20, (v22 & 0xFFFFF000) + 4096, 0x20u, &v70, &v79, v50, 0, &v60);
    v78 = v66;
    v24 = v19;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, 32LL * v19, 0x44746146u);
    v26 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, 32LL * v19);
    v66 = v26;
    v52 = 1;
  }
  else
  {
    v24 = v19;
    v26 = v66;
  }
  v27 = 32 * v24;
  v28 = (__int64)&v26[v27 - 32];
  *(_QWORD *)v28 = v85[0];
  *(_DWORD *)(v28 + 7) = v72;
  v29 = v57;
  *(_BYTE *)(v28 + 11) = v57;
  *(_OWORD *)(v28 + 12) = v17;
  *(_DWORD *)(v28 + 28) = v73;
  LOBYTE(v23) = v54;
  FatConstructDirent(
    (unsigned __int64)&DestinationString & -(__int64)(v18 != 0),
    v27 + (_DWORD)v26 - 32,
    (unsigned int)&v61,
    v23,
    v53,
    (unsigned __int64)&DestinationString & -(__int64)(v18 != 0),
    v29,
    0,
    0);
  v30 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 200LL);
  if ( (v30 & 0x400000) != 0 )
  {
    if ( (*(_DWORD *)(a2 + 192) & 0x8000) != 0 )
    {
      v30 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 372LL);
      if ( *(_DWORD *)(a2 + 132) != (_DWORD)v30 )
        *(_BYTE *)(v28 + 12) |= 2u;
      *(_BYTE *)(v28 + 12) = *(_BYTE *)(v28 + 12) & 0x1B
                           | (4 * (-*(_BYTE *)(a2 + 32) & 1 | (4 * (-*(_BYTE *)(a2 + 32) & 0xFE))));
    }
    v31 = *(_BYTE *)(v28 + 12);
    if ( (*(_DWORD *)(a2 + 192) & 0x20000) != 0 )
      LOBYTE(v30) = v31 | 1;
    else
      LOBYTE(v30) = v31 & 0xFE;
    *(_BYTE *)(v28 + 12) = v30;
  }
  if ( v52 )
  {
    v32 = (unsigned int)Size;
    memmove(v78, v26, (unsigned int)Size);
    v33 = v27 - v32;
    LODWORD(v32) = HIDWORD(Size);
    v34 = v33;
    v35 = v79;
    memmove(v79, &v26[32 * HIDWORD(Size)], v34);
    v28 = (__int64)v35 + 32 * (v19 - (unsigned int)v32) - 32;
  }
  FatRemoveNames(v30, a2);
  v36 = *(void **)(a2 + 536);
  if ( v36 )
  {
    ExFreePoolWithTag(v36, 0);
    *(_QWORD *)(a2 + 536) = 0;
  }
  v37 = *(void **)(a2 + 560);
  if ( v37 )
  {
    ExFreePoolWithTag(v37, 0);
    *(_QWORD *)(a2 + 560) = 0;
  }
  ExFreePoolWithTag(*(PVOID *)(a2 + 488), 0);
  *(_QWORD *)(a2 + 488) = 0;
  FatConstructNamesInFcb(v38, a2, v28, (unsigned __int64)&SourceString & -(__int64)(v18 != 0));
  FatSetFullNameInFcb(a1, a2, &SourceString);
  if ( v51 )
    FatFreeStringBuffer(&DestinationString, v39, v40, v41);
  FatFreeStringBuffer(&v67, v39, v40, v41);
  FatFreeStringBuffer(&v75, v42, v43, v44);
  FatFreeStringBuffer(&v61, v45, v46, v47);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v65 )
  {
    CcUnpinData(v65);
    v65 = 0;
  }
  if ( v74 )
    CcUnpinData(v74);
  if ( v70 )
    CcUnpinData(v70);
  FatUnpinRepinnedBcbs(a1);
  if ( v52 )
    ExFreePoolWithTag(v26, 0);
  *(_DWORD *)(a2 + 248) = v69[0];
  result = *(_QWORD *)&DbcsName.Length;
  *(_DWORD *)(a2 + 244) = *(_DWORD *)&DbcsName.Length;
  return result;
}

```

## disassembly

```asm
0x1400333d0  mov     rax, rsp
0x1400333d3  mov     [rax+18h], rbx
0x1400333d7  mov     [rax+20h], rsi
0x1400333db  push    rdi
0x1400333dc  push    r12
0x1400333de  push    r13
0x1400333e0  push    r14
0x1400333e2  push    r15
0x1400333e4  sub     rsp, 320h
0x1400333eb  movaps  xmmword ptr [rax-38h], xmm6
0x1400333ef  mov     rax, cs:__security_cookie
0x1400333f6  xor     rax, rsp
0x1400333f9  mov     [rsp+348h+var_48], rax
0x140033401  mov     r12b, r8b
0x140033404  mov     rdi, rdx
0x140033407  mov     rsi, rcx
0x14003340a  mov     [rsp+348h+var_1F8], rcx
0x140033412  mov     r14, [rdx+0B0h]
0x140033419  mov     qword ptr [rsp+348h+var_270], r14
0x140033421  xorps   xmm0, xmm0
0x140033424  movups  xmmword ptr [rsp+348h+DestinationString.Length], xmm0
0x140033429  xorps   xmm1, xmm1
0x14003342c  movups  xmmword ptr [rsp+348h+SourceString.Length], xmm1
0x140033434  movups  xmmword ptr [rsp+348h+var_218.Length], xmm0
0x14003343c  xor     r13d, r13d
0x14003343f  mov     [rsp+348h+var_2E8], r13b
0x140033444  movups  xmmword ptr [rsp+348h+var_248.Length], xmm0
0x14003344c  movups  xmmword ptr [rsp+348h+var_1F0], xmm1
0x140033454  movups  xmmword ptr [rsp+348h+var_290.Length], xmm0
0x14003345c  movups  xmmword ptr [rsp+348h+var_2C8.Length], xmm1
0x140033464  xor     edx, edx; Val
0x140033466  lea     r8d, [r13+50h]; Size
0x14003346a  lea     rcx, [rsp+348h+var_1D8]; void *
0x140033472  call    memset
0x140033477  mov     [rsp+348h+var_230], r13
0x14003347f  mov     [rsp+348h+Bcb], r13
0x140033487  mov     dword ptr [rsp+348h+var_260], r13d
0x14003348f  mov     dword ptr [rsp+348h+var_2D0], r13d
0x140033494  mov     [rsp+348h+var_238], r13
0x14003349c  mov     [rsp+348h+var_2A0], r13
0x1400334a4  mov     [rsp+348h+var_298], r13
0x1400334ac  mov     [rsp+348h+var_250], r13
0x1400334b4  mov     [rsp+348h+var_228], r13
0x1400334bc  mov     [rsp+348h+var_220], r13
0x1400334c4  mov     [rsp+348h+var_268], r13
0x1400334cc  mov     [rsp+348h+var_2E7], r13b
0x1400334d1  mov     [rsp+348h+var_2E5], r13b
0x1400334d6  mov     [rsp+348h+var_2E6], r13b
0x1400334db  mov     [rsp+348h+var_2E3], r13b
0x1400334e0  mov     dword ptr [rsp+348h+Size+4], r13d
0x1400334e8  mov     dword ptr [rsp+348h+Size], r13d
0x1400334f0  lea     rax, [rsp+348h+var_148]
0x1400334f8  mov     [rsp+348h+DestinationString.Buffer], rax
0x1400334fd  mov     dword ptr [rsp+348h+DestinationString.Length], 400000h
0x140033505  lea     rax, [rsp+348h+var_168]
0x14003350d  mov     [rsp+348h+var_218.Buffer], rax
0x140033515  mov     dword ptr [rsp+348h+var_218.Length], 180000h
0x140033520  lea     rax, [rsp+348h+var_108]
0x140033528  mov     [rsp+348h+var_2C8.Buffer], rax
0x140033530  mov     dword ptr [rsp+348h+var_2C8.Length], 400000h
0x14003353b  movzx   edx, word ptr [rdi+228h]
0x140033542  lea     rcx, [rsp+348h+DestinationString]; DestinationString
0x140033547  test    dx, dx
0x14003354a  jz      short loc_14003358D
0x14003354c  lea     ebx, [r13+0Ch]
0x140033550  add     dx, bx
0x140033553  call    FatEnsureStringBufferEnough
0x140033558  mov     [rsp+348h+var_2E8], 1
0x14003355d  movzx   r8d, word ptr [rdi+228h]; Size
0x140033565  mov     rdx, [rdi+230h]; Src
0x14003356c  mov     rcx, [rsp+348h+DestinationString.Buffer]; void *
0x140033571  call    memmove
0x140033576  movzx   r11d, word ptr [rdi+228h]
0x14003357e  mov     [rsp+348h+DestinationString.Length], r11w
0x140033584  lea     r15d, [r13+20h]
0x140033588  jmp     loc_140033678
0x14003358d  mov     [rsp+348h+var_2B8], r13d
0x140033595  mov     [rsp+348h+var_2E4], r13b
0x14003359a  lea     rbx, [rdi+1E0h]
0x1400335a1  xor     r8d, r8d; AllocateDestinationString
0x1400335a4  mov     rdx, rbx; SourceString
0x1400335a7  call    cs:__imp_RtlOemStringToCountedUnicodeString
0x1400335ae  nop     dword ptr [rax+rax+00h]
0x1400335b3  mov     [rsp+348h+var_2E8], r13b
0x1400335b8  xor     r8d, r8d; AllocateDestinationString
0x1400335bb  mov     rdx, rbx; SourceString
0x1400335be  lea     rcx, [rsp+348h+var_218]; DestinationString
0x1400335c6  call    cs:__imp_RtlOemStringToCountedUnicodeString
0x1400335cd  nop     dword ptr [rax+rax+00h]
0x1400335d2  mov     r8d, [rdi+0C0h]
0x1400335d9  mov     r10d, r8d
0x1400335dc  shr     r10d, 0Ch
0x1400335e0  and     r10b, 1
0x1400335e4  mov     [rsp+348h+var_2E5], r10b
0x1400335e9  shr     r8d, 0Dh
0x1400335ed  and     r8b, 1
0x1400335f1  mov     [rsp+348h+var_2E6], r8b
0x1400335f6  mov     r9b, r13b
0x1400335f9  mov     [rsp+348h+var_2E4], r13b
0x1400335fe  mov     ecx, r13d
0x140033601  mov     r15d, 20h ; ' '
0x140033607  movzx   r11d, [rsp+348h+DestinationString.Length]
0x14003360d  mov     [rsp+348h+var_2B8], ecx
0x140033614  movzx   eax, r11w
0x140033618  shr     eax, 1
0x14003361a  cmp     ecx, eax
0x14003361c  jnb     short loc_14003366B
0x14003361e  mov     ebx, ecx
0x140033620  mov     r14, [rsp+348h+DestinationString.Buffer]
0x140033625  movzx   edx, word ptr [r14+rbx*2]
0x14003362a  cmp     dx, 2Eh ; '.'
0x14003362e  jnz     short loc_14003363A
0x140033630  mov     r9b, 1
0x140033633  mov     [rsp+348h+var_2E4], r9b
0x140033638  jmp     short loc_140033667
0x14003363a  test    r10b, r10b
0x14003363d  jz      short loc_140033644
0x14003363f  test    r9b, r9b
0x140033642  jz      short loc_14003364F
0x140033644  test    r8b, r8b
0x140033647  jz      short loc_140033667
0x140033649  cmp     r9b, 1
0x14003364d  jnz     short loc_140033667
0x14003364f  lea     eax, [rdx-41h]
0x140033652  cmp     ax, 19h
0x140033656  ja      short loc_140033667
0x140033658  add     dx, r15w
0x14003365c  mov     [r14+rbx*2], dx
0x140033661  movzx   r11d, [rsp+348h+DestinationString.Length]
0x140033667  inc     ecx
0x140033669  jmp     short loc_14003360D
0x14003366b  mov     ebx, 0Ch
0x140033670  mov     r14, qword ptr [rsp+348h+var_270]
0x140033678  test    r12b, r12b
0x14003367b  jz      loc_14003370E
0x140033681  movzx   edx, r11w
0x140033685  mov     rcx, [rsp+348h+DestinationString.Buffer]
0x14003368a  movsd   xmm0, qword ptr cs:aPfile_0; ".PFILE"
0x140033692  movsd   qword ptr [rdx+rcx], xmm0
0x140033697  mov     eax, dword ptr cs:aPfile_0+8; "LE"
0x14003369d  mov     [rdx+rcx+8], eax
0x1400336a1  movzx   ecx, [rsp+348h+DestinationString.Length]
0x1400336a6  add     cx, bx
0x1400336a9  mov     [rsp+348h+DestinationString.Length], cx
0x1400336ae  mov     eax, [rsp+348h+var_1D4]
0x1400336b5  and     eax, 0FF000002h
0x1400336ba  or      eax, 2
0x1400336bd  mov     [rsp+348h+var_1D4], eax
0x1400336c4  mov     rax, [rsp+348h+DestinationString.Buffer]
0x1400336c9  mov     [rsp+348h+SourceString.Buffer], rax
0x1400336d1  movzx   eax, cx
0x1400336d4  sub     ax, bx
0x1400336d7  mov     [rsp+348h+SourceString.Length], ax
0x1400336df  movzx   eax, [rsp+348h+DestinationString.MaximumLength]
0x1400336e4  mov     [rsp+348h+SourceString.MaximumLength], ax
0x1400336ec  mov     eax, 1FEh
0x1400336f1  cmp     cx, ax
0x1400336f4  jbe     loc_1400337C5
0x1400336fa  mov     ecx, 0C0000033h; Status
0x1400336ff  mov     [rsi+48h], ecx
0x140033702  call    cs:__imp_ExRaiseStatus
0x14003370e  lea     rcx, [rsp+348h+DestinationString]
0x140033713  call    FatRemovePfileExtension
0x140033718  mov     rax, [rsp+348h+DestinationString.Buffer]
0x14003371d  mov     [rsp+348h+SourceString.Buffer], rax
0x140033725  movzx   edx, [rsp+348h+DestinationString.Length]
0x14003372a  mov     [rsp+348h+SourceString.Length], dx
0x140033732  movzx   eax, [rsp+348h+DestinationString.MaximumLength]
0x140033737  mov     [rsp+348h+SourceString.MaximumLength], ax
0x14003373f  lea     rcx, [rsp+348h+var_2C8]
0x140033747  call    FatEnsureStringBufferEnough
0x14003374c  xor     r8d, r8d; AllocateDestinationString
0x14003374f  lea     rdx, [rsp+348h+SourceString]; SourceString
0x140033757  lea     rcx, [rsp+348h+var_2C8]; DestinationString
0x14003375f  call    cs:__imp_RtlUpcaseUnicodeStringToCountedOemString
0x140033766  nop     dword ptr [rax+rax+00h]
0x14003376b  mov     dword ptr [rsp+348h+var_2D0+4], eax
0x14003376f  test    eax, eax
0x140033771  js      short loc_1400337B7
0x140033773  movaps  xmm0, xmmword ptr [rsp+348h+var_2C8.Length]
0x14003377b  movdqa  xmmword ptr [rsp+348h+DbcsName.Length], xmm0
0x140033784  xor     r9d, r9d; LeadingBackslashPermissible
0x140033787  xor     r8d, r8d; PathNamePermissible
0x14003378a  xor     edx, edx; WildCardsPermissible
0x14003378c  lea     rcx, [rsp+348h+DbcsName]; DbcsName
0x140033794  call    cs:__imp_FsRtlIsFatDbcsLegal
0x14003379b  nop     dword ptr [rax+rax+00h]
0x1400337a0  test    al, al
0x1400337a2  jz      short loc_1400337BC
0x1400337a4  lea     rdx, [rsp+348h+SourceString]
0x1400337ac  call    FatSpaceInName
0x1400337b1  test    al, al
0x1400337b3  jz      short loc_1400337C5
0x1400337b5  jmp     short loc_1400337BC
0x1400337b7  mov     dword ptr [rsp+348h+var_2D0+4], r13d
0x1400337bc  mov     [rsp+348h+var_2C8.Length], r13w
0x1400337c5  lea     rax, [rsp+348h+var_C8]
0x1400337cd  mov     [rsp+348h+var_290.Buffer], rax
0x1400337d5  mov     dword ptr [rsp+348h+var_290.Length], 400000h
0x1400337e0  movzx   edx, [rsp+348h+DestinationString.Length]
0x1400337e5  lea     rcx, [rsp+348h+var_290]
0x1400337ed  call    FatEnsureStringBufferEnough
0x1400337f2  xor     r8d, r8d; AllocateDestinationString
0x1400337f5  lea     rdx, [rsp+348h+DestinationString]; SourceString
0x1400337fa  lea     rcx, [rsp+348h+var_290]; DestinationString
0x140033802  call    cs:__imp_RtlUpcaseUnicodeString
0x140033809  nop     dword ptr [rax+rax+00h]
0x14003380e  mov     dword ptr [rsp+348h+var_2D0+4], eax
0x140033812  test    eax, eax
0x140033814  jns     short loc_140033827
0x140033816  mov     [rsi+48h], eax
0x140033819  mov     ecx, eax; Status
0x14003381b  call    cs:__imp_ExRaiseStatus
0x140033827  movzx   eax, [rsp+348h+var_290.Length]
0x14003382f  mov     [rsp+348h+var_1A8], ax
0x140033837  movzx   eax, [rsp+348h+var_290.MaximumLength]
0x14003383f  mov     [rsp+348h+var_1A6], ax
0x140033847  mov     eax, dword ptr [rsp+348h+var_290+4]
0x14003384e  mov     [rsp+348h+var_1A4], eax
0x140033855  mov     rax, [rsp+348h+var_290.Buffer]
0x14003385d  mov     [rsp+348h+var_1A0], rax
0x140033865  mov     [rsp+348h+var_1D0], r13b
0x14003386d  lea     rax, [rsp+348h+var_2A0]
0x140033875  mov     [rsp+348h+var_328], rax
0x14003387a  lea     r9, [rsp+348h+var_238]
0x140033882  xor     r8d, r8d
0x140033885  mov     rdx, rdi
0x140033888  mov     rcx, rsi
0x14003388b  call    FatGetDirentFromFcbOrDcb
0x140033890  mov     rax, [rsp+348h+var_238]
0x140033898  movsd   xmm0, qword ptr [rax]
0x14003389c  movsd   [rsp+348h+var_188], xmm0
0x1400338a5  mov     ecx, [rax+7]
0x1400338a8  mov     dword ptr [rsp+348h+var_260+4], ecx
0x1400338af  mov     dword ptr [rsp+348h+var_188+7], ecx
0x1400338b6  mov     cl, [rax+0Bh]
0x1400338b9  mov     [rsp+348h+var_2E2], cl
0x1400338bd  movups  xmm6, xmmword ptr [rax+0Ch]
0x1400338c1  mov     eax, [rax+1Ch]
0x1400338c4  mov     [rsp+348h+var_258], eax
0x1400338cb  mov     dword ptr [rsp+348h+var_2D0], 1000000Fh
0x1400338d3  lea     rax, [rsp+348h+var_88]
0x1400338db  mov     [rsp+348h+var_248.Buffer], rax
0x1400338e3  mov     dword ptr [rsp+348h+var_248.Length], 400000h
0x1400338ee  lea     rax, [rsp+348h+var_1F0]
0x1400338f6  mov     [rsp+348h+var_2F8], rax; __int64
0x1400338fb  lea     rax, [rsp+348h+var_248]
0x140033903  mov     [rsp+348h+var_300], rax; SourceString
0x140033908  mov     [rsp+348h+var_308], r13; __int64
0x14003390d  lea     rax, [rsp+348h+var_260]
0x140033915  mov     [rsp+348h+var_310], rax; __int64
0x14003391a  lea     rax, [rsp+348h+Bcb]
0x140033922  mov     [rsp+348h+var_318], rax; __int64
0x140033927  lea     rax, [rsp+348h+var_230]
0x14003392f  mov     [rsp+348h+var_320], rax; __int64
0x140033934  lea     rax, [rsp+348h+var_2D0]
0x140033939  mov     [rsp+348h+var_328], rax; __int64
0x14003393e  xor     r9d, r9d; int
0x140033941  lea     r8, [rsp+348h+var_1D8]; int
0x140033949  mov     rdx, r14; int
0x14003394c  mov     rcx, rsi; int
0x14003394f  call    FatLocateDirent
0x140033954  cmp     [rsp+348h+var_230], r13
0x14003395c  jz      short loc_140033972
0x14003395e  mov     ecx, 0C0000022h; Status
0x140033963  mov     [rsi+48h], ecx
0x140033966  call    cs:__imp_ExRaiseStatus
0x140033972  test    r12b, r12b
0x140033975  jz      short loc_140033995
0x140033977  test    dword ptr [rsp+348h+var_2D0], 0C00h
0x14003397f  jz      short loc_1400339B0
0x140033981  mov     ecx, 0C0000022h; Status
0x140033986  mov     [rsi+48h], ecx
0x140033989  call    cs:__imp_ExRaiseStatus
0x140033995  test    byte ptr [rsp+348h+var_2D0], 10h
0x14003399a  jz      short loc_1400339B0
0x14003399c  mov     ecx, 0C0000022h; Status
0x1400339a1  mov     [rsi+48h], ecx
0x1400339a4  call    cs:__imp_ExRaiseStatus
0x1400339b0  lea     rax, [rsp+348h+var_2E3]
0x1400339b5  mov     [rsp+348h+var_308], rax
0x1400339ba  lea     rax, [rsp+348h+var_2E6]
0x1400339bf  mov     [rsp+348h+var_310], rax
0x1400339c4  lea     rax, [rsp+348h+var_2E5]
0x1400339c9  mov     [rsp+348h+var_318], rax
0x1400339ce  mov     [rsp+348h+var_320], r13
0x1400339d3  lea     rax, [rsp+348h+var_2C8]
0x1400339db  mov     [rsp+348h+var_328], rax
0x1400339e0  lea     r9, [rsp+348h+DestinationString]
0x1400339e5  lea     r8, [rsp+348h+var_2C8]
0x1400339ed  mov     rdx, r14
0x1400339f0  mov     rcx, rsi
0x1400339f3  call    FatSelectNames
0x1400339f8  mov     r13b, [rsp+348h+var_2E3]
0x1400339fd  test    r13b, r13b
0x140033a00  jz      short loc_140033A26
0x140033a02  movzx   ecx, [rsp+348h+DestinationString.Length]
0x140033a07  shr     rcx, 1
0x140033a0a  add     rcx, rbx
0x140033a0d  mov     rax, 4EC4EC4EC4EC4EC5h
  ... truncated ...
```
