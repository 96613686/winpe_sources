# FatSetEndOfFileInfo

- ea: `0x14003b9d0`
- end: `0x14003be9e`
- name: `FatSetEndOfFileInfo`
- size: `1230`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x140039e94`

## callees

- `0x140001858`
- `0x1400019b8`
- `0x140001d4c`
- `0x140020458`
- `0x1400226b8`
- `0x14002486c`
- `0x1400319bc`
- `0x140033270`
- `0x1400333b4`
- `0x14003805c`
- `0x14003b9d0`
- `0x140044bac`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x14003be69`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005e653`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14003be69`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005e653`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003bcc4`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003be2b`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003bcc4`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003be2b`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003bd41`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003bd41`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003bd61`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003bd61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003be7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e66a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003be7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e66a`
- `ntoskrnl!CcUnpinData` at `0x14003bce2`
- `ntoskrnl!CcUnpinData` at `0x14005e5ba`
- `ntoskrnl!CcUnpinData` at `0x14003bce2`
- `ntoskrnl!CcUnpinData` at `0x14005e5ba`
- `ntoskrnl!CcSetFileSizes` at `0x14003bdab`
- `ntoskrnl!CcSetFileSizes` at `0x14003bdab`
- `ntoskrnl!ExRaiseStatus` at `0x14003baf0`
- `ntoskrnl!ExRaiseStatus` at `0x14003baf0`

## pseudocode

```c
__int64 __fastcall FatSetEndOfFileInfo(__int64 a1, _QWORD *a2, struct _FILE_OBJECT *a3, __int64 a4, char *a5)
{
  char *v7; // rbx
  char v8; // r15
  BOOLEAN v9; // r14
  union _LARGE_INTEGER *v10; // r11
  unsigned int v11; // edi
  _DWORD *v12; // r10
  unsigned int *v13; // r11
  unsigned int v14; // edi
  _DWORD *v15; // r15
  _QWORD *p_DataSectionObject; // rax
  LONG v17; // edi
  char v18; // r14
  unsigned int v19; // eax
  __int64 v20; // rdi
  unsigned int v21; // ecx
  unsigned int v22; // r8d
  char v24; // [rsp+50h] [rbp-68h]
  BOOLEAN v25; // [rsp+51h] [rbp-67h]
  int v26; // [rsp+58h] [rbp-60h]
  PLARGE_INTEGER NewFileSize; // [rsp+60h] [rbp-58h] BYREF
  int v28; // [rsp+68h] [rbp-50h]
  unsigned int v29; // [rsp+6Ch] [rbp-4Ch]
  unsigned int v30; // [rsp+70h] [rbp-48h]
  PVOID Bcb; // [rsp+C8h] [rbp+10h] BYREF
  struct _FILE_OBJECT *v32; // [rsp+D0h] [rbp+18h]
  __int64 v33; // [rsp+D8h] [rbp+20h]

  v33 = a4;
  v32 = a3;
  Bcb = a2;
  v7 = a5;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v8 = 0;
  v24 = 0;
  v9 = 0;
  v25 = 0;
  v26 = 0;
  v10 = (union _LARGE_INTEGER *)a2[3];
  NewFileSize = v10;
  if ( *(_WORD *)a5 != 1282 )
  {
    v11 = -1073741808;
    goto LABEL_55;
  }
  if ( !(unsigned __int8)FatIsIoRangeValid(a1, v10->QuadPart, 0, *((unsigned int *)a5 + 33)) )
  {
    v11 = -1073741697;
    goto LABEL_55;
  }
  v14 = *v13;
  v15 = v7 + 192;
  if ( (*(_DWORD *)(*((_QWORD *)v7 + 23) + 200LL) & 0x400000) != 0 && (*v15 & 0x8000) != 0 )
    v26 = *((_DWORD *)v7 + 33);
  if ( *((_QWORD *)v7 + 3) == -1 && *((_DWORD *)v7 + 49) == 1 )
  {
    FatLookupFileAllocationSize(a1, v7);
    v12 = Bcb;
  }
  p_DataSectionObject = &a3->SectionObjectPointer->DataSectionObject;
  if ( *p_DataSectionObject && !p_DataSectionObject[1] && (v12[4] & 2) == 0 )
  {
    if ( (a3->Flags & 0x4000) != 0 )
    {
      *(_DWORD *)(a1 + 72) = -1073741528;
      ExRaiseStatus(-1073741528);
    }
    FatInitializeCacheMap((int)a3, (_DWORD)v7 + 24, 0, (int)&qword_140017D90, v7);
    v24 = 1;
  }
  if ( *(_BYTE *)(*((_QWORD *)Bcb + 23) + 33LL) )
  {
    if ( ((*v15 & 1) == 0 || *((_DWORD *)v7 + 57)) && *((_DWORD *)v7 + 49) == 1 )
    {
      NewFileSize = 0;
      Bcb = 0;
      if ( v14 >= *((_DWORD *)v7 + 8) )
        v14 = *((_DWORD *)v7 + 8);
      v17 = v26 + v14;
      FatGetDirentFromFcbOrDcb(a1, (_DWORD)v7, 0, (unsigned int)&NewFileSize, (__int64)&Bcb);
      v18 = 0;
      if ( (*(_DWORD *)(v33 + 200) & 0x400000) != 0 && (*v15 & 0x8000) != 0 )
      {
        v19 = (v17 + 15) & 0xFFFFFFF0;
        v18 = ((v17 + 15) & 0xF0) - v17;
        v17 = v19;
      }
      else
      {
        v19 = v17;
      }
      if ( v19 > NewFileSize[3].HighPart )
      {
        NewFileSize[3].HighPart = v17;
        v20 = v33;
        if ( (*(_DWORD *)(v33 + 200) & 0x400000) != 0 && (*v15 & 0x8000) != 0 )
        {
          FatUpdateFileHeader(a1, v7, *((unsigned int *)v7 + 33), (unsigned int)NewFileSize[3].HighPart);
          BYTE4(NewFileSize[1].QuadPart) = BYTE4(NewFileSize[1].QuadPart) & 0x1B | (4 * (v18 & 1 | (4 * (v18 & 0xFE))));
        }
        LOBYTE(a4) = 1;
        FatSetDirtyBcb(a1, Bcb, *((_QWORD *)v7 + 23), a4);
        if ( !*((_QWORD *)v7 + 67) )
          FatSetFullFileNameInFcb(a1);
        FsRtlNotifyFullReportChange(
          *(PNOTIFY_SYNC *)(v20 + 816),
          (PLIST_ENTRY)(v20 + 800),
          (PSTRING)v7 + 33,
          *((_WORD *)v7 + 264) - *((_WORD *)v7 + 272),
          0,
          0,
          8u,
          3u,
          0);
      }
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
    }
    goto LABEL_53;
  }
  a4 = v14 + v26;
  if ( (unsigned int)a4 > *((_DWORD *)v7 + 6) )
    FatAddFileAllocation(a1);
  if ( *((_DWORD *)v7 + 8) == v14 )
  {
LABEL_52:
    a3->Flags |= 0x1000u;
LABEL_53:
    v11 = 0;
    goto LABEL_54;
  }
  if ( *((_DWORD *)v7 + 8) <= v14 )
  {
LABEL_45:
    v28 = *((_DWORD *)v7 + 8);
    v29 = *((_DWORD *)v7 + 10);
    v21 = v29;
    v22 = *((_DWORD *)v7 + 70);
    v30 = v22;
    *((_DWORD *)v7 + 8) = v14;
    if ( v21 > v14 )
      *((_DWORD *)v7 + 10) = v14;
    if ( v22 > v14 )
      *((_DWORD *)v7 + 70) = v14;
    CcSetFileSizes(a3, (PCC_FILE_SIZES)v7 + 1);
    FatSetFileSizeInDirent(a1, v7);
    if ( !*((_QWORD *)v7 + 67) )
      FatSetFullFileNameInFcb(a1);
    FsRtlNotifyFullReportChange(
      *(PNOTIFY_SYNC *)(v33 + 816),
      (PLIST_ENTRY)(v33 + 800),
      (PSTRING)v7 + 33,
      *((_WORD *)v7 + 264) - *((_WORD *)v7 + 272),
      0,
      0,
      8u,
      3u,
      0);
    *v15 |= 2u;
    goto LABEL_52;
  }
  if ( !*((_DWORD *)v7 + 60) )
  {
    if ( !MmCanFileBeTruncated(a3->SectionObjectPointer, NewFileSize) )
    {
      v11 = -1073741245;
      goto LABEL_54;
    }
    v25 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)v7 + 2), 1u);
    goto LABEL_45;
  }
  v11 = -1073740747;
LABEL_54:
  v8 = v24;
  v9 = v25;
LABEL_55:
  FatUnpinRepinnedBcbs(a1, a2, a3, a4);
  if ( v8 )
    CcUninitializeCacheMap(a3, 0, 0);
  if ( v9 )
    ExReleaseResourceLite(*((PERESOURCE *)v7 + 2));
  return v11;
}

```

## disassembly

```asm
0x14003b9d0  mov     rax, rsp
0x14003b9d3  mov     [rax+20h], r9
0x14003b9d7  mov     [rax+18h], r8
0x14003b9db  mov     [rax+10h], rdx
0x14003b9df  mov     [rax+8], rcx
0x14003b9e3  push    rbx
0x14003b9e4  push    rsi
0x14003b9e5  push    rdi
0x14003b9e6  push    r13
0x14003b9e8  push    r14
0x14003b9ea  push    r15
0x14003b9ec  sub     rsp, 88h
0x14003b9f3  mov     r13, r8
0x14003b9f6  mov     r10, rdx
0x14003b9f9  mov     rsi, rcx
0x14003b9fc  mov     rbx, [rsp+0B8h+arg_20]
0x14003ba04  mov     dword ptr [rax-50h], 0
0x14003ba0b  mov     dword ptr [rax-4Ch], 0
0x14003ba12  mov     dword ptr [rax-48h], 0
0x14003ba19  xor     r15b, r15b
0x14003ba1c  mov     [rax-68h], r15b
0x14003ba20  mov     [rax-66h], r15b
0x14003ba24  xor     r14b, r14b
0x14003ba27  mov     [rax-67h], r14b
0x14003ba2b  mov     dword ptr [rax-60h], 0
0x14003ba32  mov     r11, [rdx+18h]
0x14003ba36  mov     [rsp+0B8h+NewFileSize], r11
0x14003ba3b  mov     eax, 502h
0x14003ba40  cmp     [rbx], ax
0x14003ba43  jz      short loc_14003BA4F
0x14003ba45  mov     edi, 0C0000010h
0x14003ba4a  jmp     loc_14003BE53
0x14003ba4f  mov     r9d, [rbx+84h]
0x14003ba56  xor     r8d, r8d
0x14003ba59  mov     rdx, [r11]
0x14003ba5c  call    FatIsIoRangeValid
0x14003ba61  test    al, al
0x14003ba63  jnz     short loc_14003BA6F
0x14003ba65  mov     edi, 0C000007Fh
0x14003ba6a  jmp     loc_14003BE53
0x14003ba6f  mov     edi, [r11]
0x14003ba72  mov     rax, [rbx+0B8h]
0x14003ba79  mov     ecx, [rax+0C8h]
0x14003ba7f  lea     r15, [rbx+0C0h]
0x14003ba86  bt      ecx, 16h
0x14003ba8a  jnb     short loc_14003BA9F
0x14003ba8c  test    dword ptr [r15], 8000h
0x14003ba93  jz      short loc_14003BA9F
0x14003ba95  mov     eax, [rbx+84h]
0x14003ba9b  mov     [rsp+0B8h+var_60], eax
0x14003ba9f  lea     r14, [rbx+18h]
0x14003baa3  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14003baa7  jnz     short loc_14003BAC5
0x14003baa9  cmp     dword ptr [rbx+0C4h], 1
0x14003bab0  jnz     short loc_14003BAC5
0x14003bab2  mov     rdx, rbx
0x14003bab5  mov     rcx, rsi
0x14003bab8  call    FatLookupFileAllocationSize
0x14003babd  mov     r10, [rsp+0B8h+Bcb]
0x14003bac5  mov     rax, [r13+28h]
0x14003bac9  xor     ecx, ecx
0x14003bacb  cmp     [rax], rcx
0x14003bace  jz      short loc_14003BB1D
0x14003bad0  cmp     [rax+8], rcx
0x14003bad4  jnz     short loc_14003BB1D
0x14003bad6  mov     eax, [r10+10h]
0x14003bada  test    al, 2
0x14003badc  jnz     short loc_14003BB1D
0x14003bade  mov     eax, [r13+50h]
0x14003bae2  bt      eax, 0Eh
0x14003bae6  jnb     short loc_14003BAFC
0x14003bae8  mov     ecx, 0C0000128h; Status
0x14003baed  mov     [rsi+48h], ecx
0x14003baf0  call    cs:__imp_ExRaiseStatus
0x14003bafc  mov     [rsp+0B8h+StreamName], rbx; PVOID
0x14003bb01  lea     r9, qword_140017D90; int
0x14003bb08  xor     r8d, r8d; int
0x14003bb0b  mov     rdx, r14; int
0x14003bb0e  mov     rcx, r13; int
0x14003bb11  call    FatInitializeCacheMap
0x14003bb16  mov     [rsp+0B8h+var_68], 1
0x14003bb1b  xor     ecx, ecx
0x14003bb1d  mov     rax, [rsp+0B8h+Bcb]
0x14003bb25  mov     rax, [rax+0B8h]
0x14003bb2c  cmp     [rax+21h], cl
0x14003bb2f  jz      loc_14003BCFF
0x14003bb35  mov     eax, [r15]
0x14003bb38  test    al, 1
0x14003bb3a  jz      short loc_14003BB48
0x14003bb3c  cmp     [rbx+0E4h], ecx
0x14003bb42  jz      loc_14003BE47
0x14003bb48  cmp     dword ptr [rbx+0C4h], 1
0x14003bb4f  jnz     loc_14003BE47
0x14003bb55  mov     [rsp+0B8h+NewFileSize], rcx
0x14003bb5a  mov     [rsp+0B8h+Bcb], rcx
0x14003bb62  mov     [rsp+0B8h+var_64], ecx
0x14003bb66  mov     eax, [rbx+20h]
0x14003bb69  cmp     edi, eax
0x14003bb6b  cmovnb  edi, eax
0x14003bb6e  mov     [rsp+0B8h+var_64], edi
0x14003bb72  add     edi, [rsp+0B8h+var_60]
0x14003bb76  mov     [rsp+0B8h+var_64], edi
0x14003bb7a  lea     rax, [rsp+0B8h+Bcb]
0x14003bb82  mov     [rsp+0B8h+StreamName], rax
0x14003bb87  lea     r9, [rsp+0B8h+NewFileSize]
0x14003bb8c  xor     r8d, r8d
0x14003bb8f  mov     rdx, rbx
0x14003bb92  mov     rcx, rsi
0x14003bb95  call    FatGetDirentFromFcbOrDcb
0x14003bb9a  nop
0x14003bb9b  xor     r14b, r14b
0x14003bb9e  mov     [rsp+0B8h+var_65], r14b
0x14003bba3  mov     rax, [rsp+0B8h+arg_18]
0x14003bbab  mov     eax, [rax+0C8h]
0x14003bbb1  bt      eax, 16h
0x14003bbb5  jnb     short loc_14003BBD9
0x14003bbb7  test    dword ptr [r15], 8000h
0x14003bbbe  jz      short loc_14003BBD9
0x14003bbc0  lea     eax, [rdi+0Fh]
0x14003bbc3  and     eax, 0FFFFFFF0h
0x14003bbc6  mov     r14b, al
0x14003bbc9  sub     r14b, dil
0x14003bbcc  mov     [rsp+0B8h+var_65], r14b
0x14003bbd1  mov     edi, eax
0x14003bbd3  mov     [rsp+0B8h+var_64], eax
0x14003bbd7  jmp     short loc_14003BBDB
0x14003bbd9  mov     eax, edi
0x14003bbdb  mov     rcx, [rsp+0B8h+NewFileSize]
0x14003bbe0  cmp     eax, [rcx+1Ch]
0x14003bbe3  jbe     loc_14003BCD1
0x14003bbe9  mov     [rcx+1Ch], edi
0x14003bbec  mov     rdi, [rsp+0B8h+arg_18]
0x14003bbf4  mov     eax, [rdi+0C8h]
0x14003bbfa  bt      eax, 16h
0x14003bbfe  jnb     short loc_14003BC46
0x14003bc00  mov     eax, [r15]
0x14003bc03  bt      eax, 0Fh
0x14003bc07  jnb     short loc_14003BC46
0x14003bc09  mov     rax, [rsp+0B8h+NewFileSize]
0x14003bc0e  mov     r9d, [rax+1Ch]
0x14003bc12  mov     r8d, [rbx+84h]
0x14003bc19  mov     rdx, rbx
0x14003bc1c  mov     rcx, rsi
0x14003bc1f  call    FatUpdateFileHeader
0x14003bc24  mov     rdx, [rsp+0B8h+NewFileSize]
0x14003bc29  mov     cl, r14b
0x14003bc2c  and     cl, 0FEh
0x14003bc2f  shl     cl, 2
0x14003bc32  and     r14b, 1
0x14003bc36  or      cl, r14b
0x14003bc39  shl     cl, 2
0x14003bc3c  mov     al, [rdx+0Ch]
0x14003bc3f  and     al, 1Bh
0x14003bc41  or      cl, al
0x14003bc43  mov     [rdx+0Ch], cl
0x14003bc46  mov     r9b, 1
0x14003bc49  mov     r8, [rbx+0B8h]
0x14003bc50  mov     rdx, [rsp+0B8h+Bcb]
0x14003bc58  mov     rcx, rsi
0x14003bc5b  call    FatSetDirtyBcb
0x14003bc60  cmp     qword ptr [rbx+218h], 0
0x14003bc68  jnz     short loc_14003BC75
0x14003bc6a  mov     rdx, rbx
0x14003bc6d  mov     rcx, rsi; int
0x14003bc70  call    FatSetFullFileNameInFcb
0x14003bc75  lea     r8, [rbx+210h]; FullTargetName
0x14003bc7c  movzx   eax, word ptr [rbx+220h]
0x14003bc83  movzx   r9d, word ptr [r8]
0x14003bc87  sub     r9w, ax; TargetNameOffset
0x14003bc8b  lea     rdx, [rdi+320h]; NotifyList
0x14003bc92  mov     [rsp+0B8h+TargetContext], 0; TargetContext
0x14003bc9b  mov     [rsp+0B8h+Action], 3; Action
0x14003bca3  mov     [rsp+0B8h+FilterMatch], 8; FilterMatch
0x14003bcab  mov     [rsp+0B8h+NormalizedParentName], 0; NormalizedParentName
0x14003bcb4  mov     [rsp+0B8h+StreamName], 0; StreamName
0x14003bcbd  mov     rcx, [rdi+330h]; NotifySync
0x14003bcc4  call    cs:__imp_FsRtlNotifyFullReportChange
0x14003bccb  nop     dword ptr [rax+rax+00h]
0x14003bcd0  nop
0x14003bcd1  mov     rcx, [rsp+0B8h+Bcb]; Bcb
0x14003bcd9  test    rcx, rcx
0x14003bcdc  jz      loc_14003BE47
0x14003bce2  call    cs:__imp_CcUnpinData
0x14003bce9  nop     dword ptr [rax+rax+00h]
0x14003bcee  mov     [rsp+0B8h+Bcb], 0
0x14003bcfa  jmp     loc_14003BE47
0x14003bcff  mov     r9d, [rsp+0B8h+var_60]
0x14003bd04  add     r9d, edi
0x14003bd07  cmp     r9d, [r14]
0x14003bd0a  jbe     short loc_14003BD1A
0x14003bd0c  mov     r8, r13
0x14003bd0f  mov     rdx, rbx
0x14003bd12  mov     rcx, rsi
0x14003bd15  call    FatAddFileAllocation
0x14003bd1a  cmp     [rbx+20h], edi
0x14003bd1d  jz      loc_14003BE3B
0x14003bd23  jbe     short loc_14003BD71
0x14003bd25  cmp     dword ptr [rbx+0F0h], 0
0x14003bd2c  jz      short loc_14003BD38
0x14003bd2e  mov     edi, 0C0000435h
0x14003bd33  jmp     loc_14003BE49
0x14003bd38  mov     rdx, [rsp+0B8h+NewFileSize]; NewFileSize
0x14003bd3d  mov     rcx, [r13+28h]; SectionPointer
0x14003bd41  call    cs:__imp_MmCanFileBeTruncated
0x14003bd48  nop     dword ptr [rax+rax+00h]
0x14003bd4d  test    al, al
0x14003bd4f  jnz     short loc_14003BD5B
0x14003bd51  mov     edi, 0C0000243h
0x14003bd56  jmp     loc_14003BE49
0x14003bd5b  mov     dl, 1; Wait
0x14003bd5d  mov     rcx, [rbx+10h]; Resource
0x14003bd61  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003bd68  nop     dword ptr [rax+rax+00h]
0x14003bd6d  mov     [rsp+0B8h+var_67], al
0x14003bd71  mov     ecx, [rbx+20h]
0x14003bd74  mov     [rsp+0B8h+var_50], ecx
0x14003bd78  mov     ecx, [rbx+28h]
0x14003bd7b  mov     [rsp+0B8h+var_4C], ecx
0x14003bd7f  mov     r8d, [rbx+118h]
0x14003bd86  mov     [rsp+0B8h+var_48], r8d
0x14003bd8b  mov     [rsp+0B8h+var_66], 1
0x14003bd90  mov     [rbx+20h], edi
0x14003bd93  cmp     ecx, edi
0x14003bd95  jbe     short loc_14003BD9A
0x14003bd97  mov     [rbx+28h], edi
0x14003bd9a  cmp     r8d, edi
0x14003bd9d  jbe     short loc_14003BDA5
0x14003bd9f  mov     [rbx+118h], edi
0x14003bda5  mov     rdx, r14; FileSizes
0x14003bda8  mov     rcx, r13; FileObject
0x14003bdab  call    cs:__imp_CcSetFileSizes
0x14003bdb2  nop     dword ptr [rax+rax+00h]
0x14003bdb7  mov     rdx, rbx
0x14003bdba  mov     rcx, rsi
0x14003bdbd  call    FatSetFileSizeInDirent
0x14003bdc2  cmp     qword ptr [rbx+218h], 0
0x14003bdca  jnz     short loc_14003BDD7
0x14003bdcc  mov     rdx, rbx
0x14003bdcf  mov     rcx, rsi; int
0x14003bdd2  call    FatSetFullFileNameInFcb
0x14003bdd7  lea     r8, [rbx+210h]; FullTargetName
0x14003bdde  movzx   r9d, word ptr [r8]
0x14003bde2  sub     r9w, [rbx+220h]; TargetNameOffset
0x14003bdea  mov     rax, [rsp+0B8h+arg_18]
0x14003bdf2  lea     rdx, [rax+320h]; NotifyList
0x14003bdf9  mov     [rsp+0B8h+TargetContext], 0; TargetContext
0x14003be02  mov     [rsp+0B8h+Action], 3; Action
0x14003be0a  mov     [rsp+0B8h+FilterMatch], 8; FilterMatch
0x14003be12  mov     [rsp+0B8h+NormalizedParentName], 0; NormalizedParentName
0x14003be1b  mov     [rsp+0B8h+StreamName], 0; StreamName
0x14003be24  mov     rcx, [rax+330h]; NotifySync
0x14003be2b  call    cs:__imp_FsRtlNotifyFullReportChange
0x14003be32  nop     dword ptr [rax+rax+00h]
0x14003be37  or      dword ptr [r15], 2
0x14003be3b  mov     eax, [r13+50h]
0x14003be3f  bts     eax, 0Ch
0x14003be43  mov     [r13+50h], eax
0x14003be47  xor     edi, edi
0x14003be49  mov     r15b, [rsp+0B8h+var_68]
0x14003be4e  mov     r14b, [rsp+0B8h+var_67]
0x14003be53  mov     rcx, rsi
0x14003be56  call    FatUnpinRepinnedBcbs
0x14003be5b  nop
0x14003be5c  test    r15b, r15b
0x14003be5f  jz      short loc_14003BE75
0x14003be61  xor     r8d, r8d; UninitializeEvent
0x14003be64  xor     edx, edx; TruncateSize
0x14003be66  mov     rcx, r13; FileObject
0x14003be69  call    cs:__imp_CcUninitializeCacheMap
0x14003be70  nop     dword ptr [rax+rax+00h]
0x14003be75  test    r14b, r14b
0x14003be78  jz      short loc_14003BE8A
0x14003be7a  mov     rcx, [rbx+10h]; Resource
0x14003be7e  call    cs:__imp_ExReleaseResourceLite
0x14003be85  nop     dword ptr [rax+rax+00h]
0x14003be8a  mov     eax, edi
0x14003be8c  add     rsp, 88h
0x14003be93  pop     r15
0x14003be95  pop     r14
0x14003be97  pop     r13
0x14003be99  pop     rdi
0x14003be9a  pop     rsi
0x14003be9b  pop     rbx
0x14003be9c  retn
0x14005e5a5  push    rbp
0x14005e5a7  sub     rsp, 50h
0x14005e5ab  mov     rbp, rdx
0x14005e5ae  mov     rcx, [rbp+0C8h]; Bcb
0x14005e5b5  test    rcx, rcx
0x14005e5b8  jz      short loc_14005E5D1
0x14005e5ba  call    cs:__imp_CcUnpinData
0x14005e5c1  nop     dword ptr [rax+rax+00h]
0x14005e5c6  mov     qword ptr [rbp+0C8h], 0
0x14005e5d1  add     rsp, 50h
0x14005e5d5  pop     rbp
0x14005e5d6  retn
0x14005e5d8  push    rbx
0x14005e5da  push    rbp
0x14005e5db  sub     rsp, 58h
0x14005e5df  mov     rbp, rdx
  ... truncated ...
```
