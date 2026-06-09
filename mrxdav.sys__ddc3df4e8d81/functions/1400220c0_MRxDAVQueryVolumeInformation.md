# MRxDAVQueryVolumeInformation

- ea: `0x1400220c0`
- end: `0x14002284e`
- name: `MRxDAVQueryVolumeInformation`
- size: `1934`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x1400019bc`
- `0x1400067a0`
- `0x140006c00`
- `0x1400220c0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002216b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400221c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002223b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400222b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022377`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400223e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002244d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400224b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022599`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400225dd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022663`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400226a1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022718`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400227c9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002216b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400221c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002223b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400222b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022377`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400223e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002244d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400224b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022599`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400225dd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022663`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400226a1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022718`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400227c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400221fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400221fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002281f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002281f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400222e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400222e8`
- `ntoskrnl!ZwClose` at `0x140022809`
- `ntoskrnl!ZwClose` at `0x140022809`
- `ntoskrnl!ZwOpenFile` at `0x140022338`
- `ntoskrnl!ZwOpenFile` at `0x140022338`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400223ac`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400223ac`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryVolumeInformation(__int64 a1, __int64 a2, int a3)
{
  int v3; // edx
  int v4; // edi
  int v5; // r13d
  unsigned int v6; // r15d
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  unsigned int v12; // eax
  wchar_t *Pool2; // rax
  wchar_t *v14; // r12
  NTSTATUS Status; // esi
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r14
  __int64 v29; // rbx
  HANDLE v30; // rax
  __int64 v31; // r15
  int v32; // ebx
  __int64 v33; // rdi
  HANDLE v34; // rax
  void *FileHandle; // [rsp+38h] [rbp-81h] BYREF
  __int64 v38; // [rsp+40h] [rbp-79h]
  __int64 v39; // [rsp+48h] [rbp-71h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-29h] BYREF
  __int128 FsInformation; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-9h]

  v3 = a1;
  v4 = 0;
  v5 = *(_DWORD *)(a1 + 448);
  v6 = *(_DWORD *)(a1 + 472);
  v7 = *(_QWORD *)(a1 + 456);
  v38 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
  FileHandle = 0;
  v8 = *(_QWORD *)(a1 + 72);
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  FsInformation = 0;
  v44 = 0;
  v39 = *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 10, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId, v5);
  }
  if ( ((v5 - 3) & 0xFFFFFFFB) != 0 )
  {
    Status = 0;
    v14 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(
        v11,
        11,
        (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids,
        v12,
        (__int64)&DavWinInetCachePath);
    }
    Pool2 = (wchar_t *)ExAllocatePool2(258, 542, 1850103364);
    v14 = Pool2;
    if ( !Pool2 )
    {
      Status = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v17 = PsGetCurrentThreadId();
        WPP_SF_qD(v16, 12, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v17, -1073741670);
      }
      goto LABEL_76;
    }
    memset(Pool2, 0, 0x21Eu);
    StringCbCopyW(v14, 0x21Eu, L"\\GLOBAL??\\");
    StringCbCopyW(v14 + 10, 0x20Au, &DavWinInetCachePath);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v18, 13, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v19, (__int64)v14);
    }
    RtlInitUnicodeString(&DestinationString, v14);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x800021u);
    if ( Status < 0 )
    {
      FileHandle = 0;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_76;
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v21 = PsGetCurrentThreadId();
      v22 = 14;
      goto LABEL_20;
    }
    Status = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
    if ( Status < 0 )
    {
      Status = IoStatusBlock.Status;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_76;
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v21 = PsGetCurrentThreadId();
      v22 = 15;
LABEL_20:
      WPP_SF_qD(v20, v22, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v21, Status);
      goto LABEL_76;
    }
  }
  switch ( v5 )
  {
    case 1:
      if ( v6 < 0x18 )
      {
        Status = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_76;
        }
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v26 = PsGetCurrentThreadId();
        v27 = 16;
        goto LABEL_39;
      }
      *(_QWORD *)v7 = 0;
      *(_QWORD *)(v7 + 8) = 0;
      *(_WORD *)(v7 + 18) = 0;
      *(_BYTE *)(v7 + 16) = 0;
LABEL_75:
      v4 = 24;
      goto LABEL_76;
    case 3:
      if ( v6 < 0x18 )
      {
        Status = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_76;
        }
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v26 = PsGetCurrentThreadId();
        v27 = 17;
        goto LABEL_39;
      }
      if ( *(_DWORD *)(v39 + 104) )
      {
        v28 = a1;
        Status = UMRxAsyncEngOuterWrapper(
                   a1,
                   v3,
                   a3,
                   14,
                   (__int64)MRxDAVQueryVolumeInformationContinuation,
                   (__int64)"MRxDAVQueryVolumeInformation");
        if ( !Status )
          v4 = 24;
        goto LABEL_77;
      }
      *(_OWORD *)(v7 + 8) = v44;
      *(_QWORD *)v7 = FsInformation;
      goto LABEL_75;
    case 4:
      if ( v6 >= 8 )
      {
        v31 = v38;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v32 = *(_DWORD *)(v38 + 80);
          v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v34 = PsGetCurrentThreadId();
          WPP_SF_qD(v33, 20, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v34, v32);
        }
        v4 = 8;
        *(_DWORD *)v7 = *(_DWORD *)(v31 + 80);
        *(_DWORD *)(v7 + 4) = 8208;
        goto LABEL_76;
      }
      Status = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v26 = PsGetCurrentThreadId();
        v27 = 19;
        goto LABEL_39;
      }
LABEL_76:
      v28 = a1;
      goto LABEL_77;
    case 5:
      if ( v6 >= 0x16 )
      {
        *(_DWORD *)v7 = 2;
        if ( !DisableEFS )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v29 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v30 = PsGetCurrentThreadId();
            WPP_SF_q(v29, 22, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v30);
          }
          *(_DWORD *)v7 |= 0x20000u;
        }
        *(_DWORD *)(v7 + 4) = 255;
        *(_DWORD *)(v7 + 8) = 8;
        StringCbCopyW((STRSAFE_LPWSTR)(v7 + 12), 8u, L"FAT");
        v4 = 22;
        goto LABEL_76;
      }
      Status = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v26 = PsGetCurrentThreadId();
        v27 = 21;
LABEL_39:
        WPP_SF_q(v25, v27, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v26);
        goto LABEL_76;
      }
      goto LABEL_76;
  }
  if ( v5 != 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v24 = PsGetCurrentThreadId();
      WPP_SF_qD(v23, 23, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v24, v5);
    }
    Status = -1073741822;
    goto LABEL_76;
  }
  if ( v6 < 0x20 )
  {
    Status = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_76;
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v26 = PsGetCurrentThreadId();
    v27 = 18;
    goto LABEL_39;
  }
  if ( !*(_DWORD *)(v39 + 104) )
  {
    v4 = 32;
    *(_QWORD *)(v7 + 16) = v44;
    *(_DWORD *)(v7 + 28) = HIDWORD(v44);
    *(_QWORD *)(v7 + 8) = *((_QWORD *)&FsInformation + 1);
    *(_DWORD *)(v7 + 24) = DWORD2(v44);
    *(_QWORD *)v7 = FsInformation;
    goto LABEL_76;
  }
  v28 = a1;
  Status = UMRxAsyncEngOuterWrapper(
             a1,
             v3,
             a3,
             14,
             (__int64)MRxDAVQueryVolumeInformationContinuation,
             (__int64)"MRxDAVQueryVolumeInformation");
  if ( !Status )
    v4 = 32;
LABEL_77:
  *(_DWORD *)(v28 + 472) -= v4;
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400220c0  push    rbp
0x1400220c2  push    rbx
0x1400220c3  push    rsi
0x1400220c4  push    rdi
0x1400220c5  push    r12
0x1400220c7  push    r13
0x1400220c9  push    r14
0x1400220cb  push    r15
0x1400220cd  lea     rbp, [rsp-1Fh]
0x1400220d2  sub     rsp, 0D8h
0x1400220d9  mov     rax, cs:__security_cookie
0x1400220e0  xor     rax, rsp
0x1400220e3  mov     [rbp+57h+var_50], rax
0x1400220e7  mov     rax, [rcx+38h]
0x1400220eb  xorps   xmm0, xmm0
0x1400220ee  mov     rdx, rcx
0x1400220f1  mov     [rsp+110h+var_E0], rcx
0x1400220f6  xor     edi, edi
0x1400220f8  xorps   xmm1, xmm1
0x1400220fb  mov     rax, [rax+78h]
0x1400220ff  mov     r13d, [rdx+1C0h]
0x140022106  mov     r15d, [rdx+1D8h]
0x14002210d  mov     r14, [rdx+1C8h]
0x140022114  mov     [rbp+57h+var_D0], rax
0x140022118  xor     eax, eax
0x14002211a  mov     [rsp+110h+FileHandle], rax
0x14002211f  mov     rax, [rcx+48h]
0x140022123  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140022127  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002212b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002212f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140022133  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140022137  movups  [rbp+57h+FsInformation], xmm0
0x14002213b  movups  [rbp+57h+var_60], xmm0
0x14002213f  mov     rcx, [rax+28h]
0x140022143  mov     rax, [rcx+28h]
0x140022147  mov     [rbp+57h+var_C8], rax
0x14002214b  mov     rbx, cs:WPP_GLOBAL_Control
0x140022152  lea     rsi, WPP_GLOBAL_Control
0x140022159  cmp     rbx, rsi
0x14002215c  jz      short loc_140022191
0x14002215e  test    dword ptr [rbx+2Ch], 4000h
0x140022165  jz      short loc_140022191
0x140022167  mov     rbx, [rbx+18h]
0x14002216b  call    cs:__imp_PsGetCurrentThreadId
0x140022172  nop     dword ptr [rax+rax+00h]
0x140022177  lea     edx, [rdi+0Ah]
0x14002217a  mov     [rsp+110h+ShareAccess], r13d
0x14002217f  mov     r9, rax
0x140022182  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022189  mov     rcx, rbx
0x14002218c  call    WPP_SF_qD
0x140022191  lea     eax, [r13-3]
0x140022195  test    eax, 0FFFFFFFBh
0x14002219a  jnz     loc_1400223FC
0x1400221a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400221a7  lea     r12, DavWinInetCachePath
0x1400221ae  cmp     rbx, rsi
0x1400221b1  jz      short loc_1400221E8
0x1400221b3  test    dword ptr [rbx+2Ch], 4000h
0x1400221ba  jz      short loc_1400221E8
0x1400221bc  mov     rbx, [rbx+18h]
0x1400221c0  call    cs:__imp_PsGetCurrentThreadId
0x1400221c7  nop     dword ptr [rax+rax+00h]
0x1400221cc  mov     edx, 0Bh
0x1400221d1  mov     qword ptr [rsp+110h+ShareAccess], r12
0x1400221d6  mov     r9, rax
0x1400221d9  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400221e0  mov     rcx, rbx
0x1400221e3  call    WPP_SF_qS
0x1400221e8  mov     ebx, 21Eh
0x1400221ed  mov     r8d, 6E465644h
0x1400221f3  mov     edx, ebx
0x1400221f5  mov     ecx, 102h
0x1400221fa  call    cs:__imp_ExAllocatePool2
0x140022201  nop     dword ptr [rax+rax+00h]
0x140022206  mov     r12, rax
0x140022209  test    rax, rax
0x14002220c  jnz     short loc_14002226B
0x14002220e  mov     esi, 0C000009Ah
0x140022213  mov     rbx, cs:WPP_GLOBAL_Control
0x14002221a  lea     rax, WPP_GLOBAL_Control
0x140022221  cmp     rbx, rax
0x140022224  jz      loc_1400227F3
0x14002222a  test    dword ptr [rbx+2Ch], 2000h
0x140022231  jz      loc_1400227F3
0x140022237  mov     rbx, [rbx+18h]
0x14002223b  call    cs:__imp_PsGetCurrentThreadId
0x140022242  nop     dword ptr [rax+rax+00h]
0x140022247  lea     edx, [r12+0Ch]
0x14002224c  mov     [rsp+110h+ShareAccess], 0C000009Ah
0x140022254  mov     r9, rax
0x140022257  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002225e  mov     rcx, rbx
0x140022261  call    WPP_SF_qD
0x140022266  jmp     loc_1400227F3
0x14002226b  mov     r8, rbx; Size
0x14002226e  xor     edx, edx; Val
0x140022270  mov     rcx, r12; void *
0x140022273  call    memset
0x140022278  lea     r8, aGlobal; "\\GLOBAL??\\"
0x14002227f  mov     rdx, rbx; cbDest
0x140022282  mov     rcx, r12; pszDest
0x140022285  call    StringCbCopyW
0x14002228a  lea     rcx, [r12+14h]; pszDest
0x14002228f  mov     edx, 20Ah; cbDest
0x140022294  lea     r8, DavWinInetCachePath; pszSrc
0x14002229b  call    StringCbCopyW
0x1400222a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400222a7  cmp     rbx, rsi
0x1400222aa  jz      short loc_1400222E1
0x1400222ac  test    dword ptr [rbx+2Ch], 4000h
0x1400222b3  jz      short loc_1400222E1
0x1400222b5  mov     rbx, [rbx+18h]
0x1400222b9  call    cs:__imp_PsGetCurrentThreadId
0x1400222c0  nop     dword ptr [rax+rax+00h]
0x1400222c5  mov     edx, 0Dh
0x1400222ca  mov     qword ptr [rsp+110h+ShareAccess], r12
0x1400222cf  mov     r9, rax
0x1400222d2  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400222d9  mov     rcx, rbx
0x1400222dc  call    WPP_SF_qS
0x1400222e1  mov     rdx, r12; SourceString
0x1400222e4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400222e8  call    cs:__imp_RtlInitUnicodeString
0x1400222ef  nop     dword ptr [rax+rax+00h]
0x1400222f4  lea     rax, [rbp+57h+DestinationString]
0x1400222f8  mov     [rsp+110h+OpenOptions], 800021h; OpenOptions
0x140022300  xorps   xmm0, xmm0
0x140022303  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140022307  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14002230b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140022312  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140022316  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14002231a  mov     edx, 100001h; DesiredAccess
0x14002231f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022326  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x14002232b  mov     [rsp+110h+ShareAccess], 3; ShareAccess
0x140022333  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140022338  call    cs:__imp_ZwOpenFile
0x14002233f  nop     dword ptr [rax+rax+00h]
0x140022344  mov     esi, eax
0x140022346  test    eax, eax
0x140022348  jns     short loc_140022391
0x14002234a  mov     [rsp+110h+FileHandle], rdi
0x14002234f  mov     rbx, cs:WPP_GLOBAL_Control
0x140022356  lea     rax, WPP_GLOBAL_Control
0x14002235d  cmp     rbx, rax
0x140022360  jz      loc_1400227F3
0x140022366  test    dword ptr [rbx+2Ch], 2000h
0x14002236d  jz      loc_1400227F3
0x140022373  mov     rbx, [rbx+18h]
0x140022377  call    cs:__imp_PsGetCurrentThreadId
0x14002237e  nop     dword ptr [rax+rax+00h]
0x140022383  mov     edx, 0Eh
0x140022388  mov     [rsp+110h+ShareAccess], esi
0x14002238c  jmp     loc_140022254
0x140022391  mov     rcx, [rsp+110h+FileHandle]; FileHandle
0x140022396  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14002239a  mov     r9d, 20h ; ' '; Length
0x1400223a0  mov     [rsp+110h+ShareAccess], 7; FsInformationClass
0x1400223a8  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400223ac  call    cs:__imp_ZwQueryVolumeInformationFile
0x1400223b3  nop     dword ptr [rax+rax+00h]
0x1400223b8  mov     esi, eax
0x1400223ba  test    eax, eax
0x1400223bc  jns     short loc_140022401
0x1400223be  mov     esi, dword ptr [rbp+57h+IoStatusBlock]
0x1400223c1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400223c8  lea     rax, WPP_GLOBAL_Control
0x1400223cf  cmp     rbx, rax
0x1400223d2  jz      loc_1400227F3
0x1400223d8  test    dword ptr [rbx+2Ch], 2000h
0x1400223df  jz      loc_1400227F3
0x1400223e5  mov     rbx, [rbx+18h]
0x1400223e9  call    cs:__imp_PsGetCurrentThreadId
0x1400223f0  nop     dword ptr [rax+rax+00h]
0x1400223f5  mov     edx, 0Fh
0x1400223fa  jmp     short loc_140022388
0x1400223fc  xor     esi, esi
0x1400223fe  xor     r12d, r12d
0x140022401  mov     ecx, r13d
0x140022404  sub     ecx, 1
0x140022407  jz      loc_14002279A
0x14002240d  sub     ecx, 2
0x140022410  jz      loc_1400226E1
0x140022416  sub     ecx, 1
0x140022419  jz      loc_140022630
0x14002241f  sub     ecx, 1
0x140022422  jz      loc_140022561
0x140022428  cmp     ecx, 2
0x14002242b  jz      short loc_14002247F
0x14002242d  mov     rbx, cs:WPP_GLOBAL_Control
0x140022434  lea     rax, WPP_GLOBAL_Control
0x14002243b  cmp     rbx, rax
0x14002243e  jz      short loc_140022475
0x140022440  test    dword ptr [rbx+2Ch], 2000h
0x140022447  jz      short loc_140022475
0x140022449  mov     rbx, [rbx+18h]
0x14002244d  call    cs:__imp_PsGetCurrentThreadId
0x140022454  nop     dword ptr [rax+rax+00h]
0x140022459  mov     edx, 17h
0x14002245e  mov     [rsp+110h+ShareAccess], r13d
0x140022463  mov     r9, rax
0x140022466  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002246d  mov     rcx, rbx
0x140022470  call    WPP_SF_qD
0x140022475  mov     esi, 0C0000002h
0x14002247a  jmp     loc_1400227F3
0x14002247f  cmp     r15d, 20h ; ' '
0x140022483  jnb     short loc_1400224DA
0x140022485  mov     esi, 0C000009Ah
0x14002248a  mov     rbx, cs:WPP_GLOBAL_Control
0x140022491  lea     rax, WPP_GLOBAL_Control
0x140022498  cmp     rbx, rax
0x14002249b  jz      loc_1400227F3
0x1400224a1  test    dword ptr [rbx+2Ch], 2000h
0x1400224a8  jz      loc_1400227F3
0x1400224ae  mov     rbx, [rbx+18h]
0x1400224b2  call    cs:__imp_PsGetCurrentThreadId
0x1400224b9  nop     dword ptr [rax+rax+00h]
0x1400224be  mov     edx, 12h
0x1400224c3  mov     r9, rax
0x1400224c6  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400224cd  mov     rcx, rbx
0x1400224d0  call    WPP_SF_q
0x1400224d5  jmp     loc_1400227F3
0x1400224da  mov     rax, [rbp+57h+var_C8]
0x1400224de  cmp     [rax+68h], edi
0x1400224e1  jnz     short loc_140022524
0x1400224e3  mov     eax, dword ptr [rbp+57h+var_60]
0x1400224e6  mov     edi, 20h ; ' '
0x1400224eb  mov     [r14+10h], eax
0x1400224ef  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1400224f2  mov     [r14+14h], eax
0x1400224f6  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x1400224f9  mov     [r14+1Ch], eax
0x1400224fd  mov     eax, dword ptr [rbp+57h+FsInformation+8]
0x140022500  mov     [r14+8], eax
0x140022504  mov     eax, dword ptr [rbp+57h+FsInformation+0Ch]
0x140022507  mov     [r14+0Ch], eax
0x14002250b  mov     eax, dword ptr [rbp+57h+var_60+8]
0x14002250e  mov     [r14+18h], eax
0x140022512  mov     eax, dword ptr [rbp+57h+FsInformation]
0x140022515  mov     [r14], eax
0x140022518  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x14002251b  mov     [r14+4], eax
0x14002251f  jmp     loc_1400227F3
0x140022524  mov     r14, [rsp+110h+var_E0]
0x140022529  lea     rax, aMrxdavqueryvol; "MRxDAVQueryVolumeInformation"
0x140022530  mov     qword ptr [rsp+110h+OpenOptions], rax
0x140022535  mov     r9d, 0Eh
0x14002253b  lea     rax, MRxDAVQueryVolumeInformationContinuation
0x140022542  mov     rcx, r14
0x140022545  mov     qword ptr [rsp+110h+ShareAccess], rax
0x14002254a  call    UMRxAsyncEngOuterWrapper
0x14002254f  mov     esi, eax
0x140022551  test    eax, eax
0x140022553  jnz     loc_1400227F8
0x140022559  lea     edi, [rax+20h]
0x14002255c  jmp     loc_1400227F8
0x140022561  mov     r13d, 16h
0x140022567  cmp     r15d, r13d
0x14002256a  jnb     short loc_1400225AE
0x14002256c  mov     esi, 0C000009Ah
0x140022571  mov     rbx, cs:WPP_GLOBAL_Control
0x140022578  lea     rax, WPP_GLOBAL_Control
0x14002257f  cmp     rbx, rax
0x140022582  jz      loc_1400227F3
0x140022588  test    dword ptr [rbx+2Ch], 2000h
0x14002258f  jz      loc_1400227F3
0x140022595  mov     rbx, [rbx+18h]
0x140022599  call    cs:__imp_PsGetCurrentThreadId
0x1400225a0  nop     dword ptr [rax+rax+00h]
0x1400225a5  lea     edx, [r13-1]
0x1400225a9  jmp     loc_1400224C3
0x1400225ae  mov     dword ptr [r14], 2
0x1400225b5  cmp     cs:DisableEFS, edi
0x1400225bb  jnz     short loc_140022603
0x1400225bd  mov     rbx, cs:WPP_GLOBAL_Control
0x1400225c4  lea     rax, WPP_GLOBAL_Control
0x1400225cb  cmp     rbx, rax
0x1400225ce  jz      short loc_1400225FE
0x1400225d0  test    dword ptr [rbx+2Ch], 4000h
0x1400225d7  jz      short loc_1400225FE
0x1400225d9  mov     rbx, [rbx+18h]
0x1400225dd  call    cs:__imp_PsGetCurrentThreadId
0x1400225e4  nop     dword ptr [rax+rax+00h]
0x1400225e9  mov     edx, r13d
0x1400225ec  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400225f3  mov     r9, rax
0x1400225f6  mov     rcx, rbx
0x1400225f9  call    WPP_SF_q
0x1400225fe  bts     dword ptr [r14], 11h
0x140022603  lea     rcx, [r14+0Ch]; pszDest
0x140022607  mov     dword ptr [r14+4], 0FFh
0x14002260f  lea     r8, aFat; "FAT"
0x140022616  mov     dword ptr [r14+8], 8
0x14002261e  mov     edx, 8; cbDest
0x140022623  call    StringCbCopyW
  ... truncated ...
```
