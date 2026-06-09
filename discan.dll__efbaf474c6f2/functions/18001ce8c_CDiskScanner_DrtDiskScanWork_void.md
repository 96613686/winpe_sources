# CDiskScanner::DrtDiskScanWork(void)

- ea: `0x18001ce8c`
- end: `0x18001d804`
- name: `?DrtDiskScanWork@CDiskScanner@@IEAAJXZ`
- size: `2424`
- prototype: `__int64 __fastcall(CDiskScanner *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cba8`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x1800064d8`
- `0x180006688`
- `0x180008654`
- `0x1800088a4`
- `0x18000891c`
- `0x1800090a4`
- `0x18000946c`
- `0x1800097e0`
- `0x180009960`
- `0x180009bc4`
- `0x18000aaec`
- `0x180010160`
- `0x180012048`
- `0x180012158`
- `0x18001b87c`
- `0x18001bb10`
- `0x18001ce8c`
- `0x18001d80c`
- `0x18001dca4`
- `0x18001ec84`
- `0x18001f8dc`
- `0x180020200`
- `0x180020260`
- `0x18002031c`
- `0x18002038c`
- `0x180037620`

## import_xrefs

- `msvcrt!free` at `0x18001d447`
- `msvcrt!free` at `0x18001d5d9`
- `msvcrt!free` at `0x18001d447`
- `msvcrt!free` at `0x18001d5d9`
- `ntdll!RtlGetThreadErrorMode` at `0x18001cf6c`
- `ntdll!RtlGetThreadErrorMode` at `0x18001cf6c`
- `ntdll!NtWaitForSingleObject` at `0x18001d232`
- `ntdll!NtWaitForSingleObject` at `0x18001d282`
- `ntdll!NtWaitForSingleObject` at `0x18001d45a`
- `ntdll!NtWaitForSingleObject` at `0x18001d232`
- `ntdll!NtWaitForSingleObject` at `0x18001d282`
- `ntdll!NtWaitForSingleObject` at `0x18001d45a`
- `KERNEL32!Sleep` at `0x18001d137`
- `KERNEL32!Sleep` at `0x18001d137`

## pseudocode

```c
__int64 __fastcall CDiskScanner::DrtDiskScanWork(CDiskScanner *this)
{
  __int64 v2; // rdx
  USHORT v3; // r8
  USHORT Length; // cx
  USHORT v5; // ax
  ULONG ThreadErrorMode; // eax
  int DiskLength; // eax
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  void *v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int i; // r14d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int IsDiskLayoutStable; // eax
  const struct SPACEPORT_DISK_INFO *v19; // r8
  unsigned __int64 v20; // r15
  char *v21; // rax
  char *v22; // r14
  int v23; // eax
  __int64 v24; // r15
  int Dirty; // r10d
  int v26; // eax
  struct _SCRUB_ENVIRONMENT *v27; // rcx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  unsigned int *v33; // [rsp+20h] [rbp-E0h]
  char v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v35[7]; // [rsp+41h] [rbp-BFh] BYREF
  const char *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  void *v38; // [rsp+58h] [rbp-A8h] BYREF
  char *v39; // [rsp+60h] [rbp-A0h]
  ULONG OldMode; // [rsp+68h] [rbp-98h] BYREF
  char v41; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v43[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v44[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]
  void *Block; // [rsp+E8h] [rbp-18h]

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v2 + 16) = "CDiskScanner::DrtDiskScanWork";
  v36 = "CDiskScanner::DrtDiskScanWork";
  v3 = ++*(_WORD *)(v2 + 8);
  Length = GlobalIndentString.Length;
  v5 = GlobalIndentString.Length;
  if ( v3 < GlobalIndentString.Length )
    v5 = *(_WORD *)(v2 + 8);
  LOWORD(v38) = v5;
  if ( v3 < GlobalIndentString.Length )
    Length = v3;
  WORD1(v38) = Length;
  HIDWORD(v38) = 0;
  v39 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskScanner::DrtDiskScanWork");
  }
  v34 = 0;
  v41 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      *((unsigned int *)this + 4));
  }
  v38 = 0;
  LODWORD(v39) = 0;
  BYTE4(v39) = 0;
  DiskLength = DiskCreateHandle((const struct _STORAGE_DEVICE_NUMBER_EX *)this, &v38, 0xC0100000);
  v8 = DiskLength;
  v37 = DiskLength;
  if ( DiskLength < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    v10 = 27;
    goto LABEL_23;
  }
  v42 = 0;
  v11 = v38;
  DiskLength = DiskGetDiskLength((const struct _STORAGE_DEVICE_NUMBER_EX *)this, v38, &v42);
  v8 = DiskLength;
  v37 = DiskLength;
  if ( DiskLength < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    v10 = 28;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v33 = (unsigned int *)v42;
    WPP_SF_Di(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, *((unsigned int *)this + 4));
  }
  DiskLength = DiskWaitForVolumesReady((const struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
  v8 = DiskLength;
  v37 = DiskLength;
  if ( DiskLength < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    v10 = 30;
    goto LABEL_23;
  }
  DiskLength = CDiskScanner::UpdateReferenceDriveLayout((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
  v8 = DiskLength;
  v37 = DiskLength;
  if ( DiskLength < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    v10 = 31;
LABEL_23:
    WPP_SF_Dd(v9[2], v10, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, *((unsigned int *)this + 4), DiskLength);
    goto LABEL_134;
  }
  for ( i = 0; ; ++i )
  {
    v34 = 0;
    if ( i )
    {
      Sleep(0x2710u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(v33) = i;
        WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, *((unsigned int *)this + 4));
      }
    }
    v17 = lambda_d2dfc46f77b2634b1ca0c267f611ece0_::_lambda_d2dfc46f77b2634b1ca0c267f611ece0_(v43, this, &v34);
    v8 = EnumerateSystemVolumes__lambda_488da5a65988c65ea4b6f74dbc66c10d_(v17);
    v37 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *((unsigned int *)this + 4),
          v8);
      }
      goto LABEL_134;
    }
    if ( v34 || i >= 7 )
      break;
  }
  IsDiskLayoutStable = CDiskScanner::IsDiskLayoutStable((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
  if ( IsDiskLayoutStable )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *((unsigned int *)this + 4),
        IsDiskLayoutStable);
    }
    v19 = (CDiskScanner *)((char *)this + 40);
    goto LABEL_125;
  }
  v20 = 0;
  v21 = (char *)this + 160;
  v22 = (char *)*((_QWORD *)this + 20);
  v8 = -805306102;
  while ( 1 )
  {
    if ( v22 == v21 )
    {
      v23 = CDiskScanner::IsDiskLayoutStable((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
      if ( !v23 )
      {
        if ( v20 >= v42 )
          v20 = v42;
        CDiskScanner::DrtScrubNonVolumeArea((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11, v20, v42 - v20);
        v37 = 0;
        CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&v38);
        CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
        CHResultImp::~CHResultImp((CHResultImp *)&v36);
        return 0;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_124;
      }
      v29 = 54;
LABEL_123:
      WPP_SF_Dd(v28[2], v29, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, *((unsigned int *)this + 4), v23);
      goto LABEL_124;
    }
    if ( !NtWaitForSingleObject(*((HANDLE *)this + 12), 0, &LiZero) )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_126;
      }
      v31 = 43;
LABEL_117:
      WPP_SF_d(v30[2], v31, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, *((unsigned int *)this + 4));
      goto LABEL_126;
    }
    v23 = CDiskScanner::IsDiskLayoutStable((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
    if ( v23 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_124;
      }
      v29 = 44;
      goto LABEL_123;
    }
    CDiskScanner::DrtScrubNonVolumeArea((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11, v20, *((_QWORD *)v22 + 8) - v20);
    v24 = *((_QWORD *)v22 + 9);
    v43[0] = *((_QWORD *)v22 + 8);
    if ( !NtWaitForSingleObject(*((HANDLE *)this + 12), 0, &LiZero) )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_126;
      }
      v31 = 45;
      goto LABEL_117;
    }
    v23 = CDiskScanner::IsDiskLayoutStable((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
    if ( v23 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_124;
      }
      v29 = 46;
      goto LABEL_123;
    }
    Dirty = DrtQueryDirty(
              (const struct _STORAGE_DEVICE_NUMBER_EX *)this,
              v11,
              *((_QWORD *)v22 + 8),
              *((_QWORD *)v22 + 9));
    v37 = Dirty;
    if ( Dirty == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && ((unsigned __int8)Dirty & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v33 = (unsigned int *)*((_QWORD *)v22 + 8);
        WPP_SF_Diii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(Dirty + 46),
          *((_QWORD *)v22 + 9),
          *((unsigned int *)this + 4));
      }
    }
    else if ( Dirty >= 0 )
    {
      v35[0] = 0;
      CScrubVolumeIdentifier::CScrubVolumeIdentifier(
        (CScrubVolumeIdentifier *)v44,
        (struct CVolumeListEntry *)v22,
        (CDiskScanner *)((char *)this + 40));
      v26 = CDiskScanner::ScrubVolume(this, (const struct _SCRUB_VOLUME_IDENTIFIER *)v44, 16, v35, 0);
      v37 = v26;
      if ( v26 == -805306102 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
            *(_DWORD *)(v44[0] + 16LL),
            *(_DWORD *)(v44[0] + 36LL),
            v45,
            10);
        }
        free(Block);
        Block = 0;
        goto LABEL_134;
      }
      if ( v26 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZZd(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(v44[0] + 36LL), v45, (__int64)(v22 + 80), v26);
      }
      if ( v35[0] )
        CDiskScanner::DrtScrubNonVolumeArea(
          (struct _STORAGE_DEVICE_NUMBER_EX *)this,
          v11,
          *((_QWORD *)v22 + 8),
          *((_QWORD *)v22 + 9));
      free(Block);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = (unsigned int *)*((_QWORD *)v22 + 8);
      WPP_SF_Diiid(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, *((_QWORD *)v22 + 9), *((unsigned int *)this + 4));
    }
    if ( !NtWaitForSingleObject(*((HANDLE *)this + 12), 0, &LiZero) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *((unsigned int *)this + 4));
      }
      v37 = 0;
      v8 = 0;
      goto LABEL_134;
    }
    v23 = CDiskScanner::IsDiskLayoutStable((struct _STORAGE_DEVICE_NUMBER_EX *)this, v11);
    if ( v23 )
      break;
    v20 = v43[0] + v24;
    if ( DrtClear(
           v27,
           (const struct _STORAGE_DEVICE_NUMBER_EX *)this,
           (CDiskScanner *)((char *)this + 40),
           v11,
           (__int64)v33,
           *((_QWORD *)v22 + 8) + *((_QWORD *)v22 + 9),
           0) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = (unsigned int *)*((_QWORD *)v22 + 8);
      WPP_SF_Diiid(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, *((_QWORD *)v22 + 9), *((unsigned int *)this + 4));
    }
    v22 = *(char **)v22;
    v21 = (char *)this + 160;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v29 = 52;
    goto LABEL_123;
  }
LABEL_124:
  v19 = (CDiskScanner *)((char *)this + 40);
LABEL_125:
  EventWriteDiskScanComplete(
    *((struct _SCRUB_ENVIRONMENT **)this + 10),
    (const struct _STORAGE_DEVICE_NUMBER_EX *)this,
    v19,
    1);
  v8 = -2147467260;
LABEL_126:
  v37 = v8;
LABEL_134:
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&v38);
  CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
  CHResultImp::~CHResultImp((CHResultImp *)&v36);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ce8c  push    rbp
0x18001ce8e  push    rbx
0x18001ce8f  push    rsi
0x18001ce90  push    rdi
0x18001ce91  push    r12
0x18001ce93  push    r13
0x18001ce95  push    r14
0x18001ce97  push    r15
0x18001ce99  lea     rbp, [rsp-28h]
0x18001ce9e  sub     rsp, 128h
0x18001cea5  mov     rax, cs:__security_cookie
0x18001ceac  xor     rax, rsp
0x18001ceaf  mov     [rbp+60h+var_50], rax
0x18001ceb3  mov     rdi, rcx
0x18001ceb6  mov     ecx, cs:_tls_index
0x18001cebc  mov     rax, gs:58h
0x18001cec5  mov     rdx, [rax+rcx*8]
0x18001cec9  mov     eax, 10h
0x18001cece  lea     r9, aCdiskscannerDr; "CDiskScanner::DrtDiskScanWork"
0x18001ced5  mov     [rax+rdx], r9
0x18001ced9  mov     [rsp+160h+var_118], r9
0x18001cede  mov     r8d, 8
0x18001cee4  mov     r15d, 1
0x18001ceea  add     [r8+rdx], r15w
0x18001ceef  movzx   r8d, word ptr [r8+rdx]
0x18001cef4  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001cefb  movzx   eax, cx
0x18001cefe  cmp     r8w, cx
0x18001cf02  cmovb   ax, r8w
0x18001cf07  mov     word ptr [rsp+160h+var_108], ax
0x18001cf0c  cmovb   cx, r8w
0x18001cf11  mov     word ptr [rsp+160h+var_108+2], cx
0x18001cf16  xor     eax, eax
0x18001cf18  mov     dword ptr [rsp+160h+var_108+4], eax
0x18001cf1c  mov     rax, cs:off_180047060; "                                       "...
0x18001cf23  mov     [rsp+160h+var_100], rax
0x18001cf28  lea     rsi, WPP_GLOBAL_Control
0x18001cf2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf36  cmp     rcx, rsi
0x18001cf39  jz      short loc_18001CF5F
0x18001cf3b  test    [rcx+1Ch], r15b
0x18001cf3f  jz      short loc_18001CF5F
0x18001cf41  cmp     byte ptr [rcx+19h], 5
0x18001cf45  jb      short loc_18001CF5F
0x18001cf47  lea     edx, [r15+0Ch]
0x18001cf4b  mov     [rsp+160h+var_140], r9; __int64
0x18001cf50  lea     r9, [rsp+160h+var_108]
0x18001cf55  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cf59  call    WPP_SF_aZs
0x18001cf5e  nop
0x18001cf5f  xor     r13d, r13d
0x18001cf62  mov     [rsp+160h+var_120], r13b
0x18001cf67  mov     [rsp+160h+var_F4], r13b
0x18001cf6c  call    cs:__imp_RtlGetThreadErrorMode
0x18001cf72  or      eax, 10h
0x18001cf75  mov     edx, eax; NewMode
0x18001cf77  lea     rcx, [rsp+160h+OldMode]; OldMode
0x18001cf7c  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x18001cf81  lea     r14, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001cf88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf8f  cmp     rcx, rsi
0x18001cf92  jz      short loc_18001CFB4
0x18001cf94  test    [rcx+1Ch], r15b
0x18001cf98  jz      short loc_18001CFB4
0x18001cf9a  cmp     byte ptr [rcx+19h], 4
0x18001cf9e  jb      short loc_18001CFB4
0x18001cfa0  lea     edx, [r13+1Ah]
0x18001cfa4  mov     r9d, [rdi+10h]
0x18001cfa8  mov     r8, r14
0x18001cfab  mov     rcx, [rcx+10h]
0x18001cfaf  call    WPP_SF_d
0x18001cfb4  mov     [rsp+160h+var_108], r13
0x18001cfb9  mov     dword ptr [rsp+160h+var_100], r13d
0x18001cfbe  mov     byte ptr [rsp+160h+var_100+4], r13b
0x18001cfc3  mov     r8d, 0C0100000h; unsigned int
0x18001cfc9  lea     rdx, [rsp+160h+var_108]; void **
0x18001cfce  mov     rcx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001cfd1  call    ?DiskCreateHandle@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAPEAXK@Z; DiskCreateHandle(_STORAGE_DEVICE_NUMBER_EX const *,void * *,ulong)
0x18001cfd6  mov     ebx, eax
0x18001cfd8  mov     [rsp+160h+var_110], eax
0x18001cfdc  test    eax, eax
0x18001cfde  jns     short loc_18001D00E
0x18001cfe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfe7  cmp     rcx, rsi
0x18001cfea  jz      loc_18001D7C2
0x18001cff0  test    [rcx+1Ch], r15b
0x18001cff4  jz      loc_18001D7C2
0x18001cffa  mov     sil, 2
0x18001cffd  cmp     [rcx+19h], sil
0x18001d001  jb      loc_18001D7C2
0x18001d007  mov     edx, 1Bh
0x18001d00c  jmp     short loc_18001D05E
0x18001d00e  mov     [rsp+160h+var_F0], r13
0x18001d013  lea     r8, [rsp+160h+var_F0]; unsigned __int64 *
0x18001d018  mov     r12, [rsp+160h+var_108]
0x18001d01d  mov     rdx, r12; void *
0x18001d020  mov     rcx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001d023  call    ?DiskGetDiskLength@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXPEA_K@Z; DiskGetDiskLength(_STORAGE_DEVICE_NUMBER_EX const *,void *,unsigned __int64 *)
0x18001d028  mov     ebx, eax
0x18001d02a  mov     [rsp+160h+var_110], eax
0x18001d02e  test    eax, eax
0x18001d030  jns     short loc_18001D06A
0x18001d032  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d039  cmp     rcx, rsi
0x18001d03c  jz      loc_18001D7C2
0x18001d042  test    [rcx+1Ch], r15b
0x18001d046  jz      loc_18001D7C2
0x18001d04c  mov     sil, 2
0x18001d04f  cmp     [rcx+19h], sil
0x18001d053  jb      loc_18001D7C2
0x18001d059  mov     edx, 1Ch
0x18001d05e  mov     dword ptr [rsp+160h+var_140], eax
0x18001d062  mov     r8, r14
0x18001d065  jmp     loc_18001D7B4
0x18001d06a  mov     rax, [rsp+160h+var_F0]
0x18001d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d076  cmp     rcx, rsi
0x18001d079  jz      short loc_18001D099
0x18001d07b  test    [rcx+1Ch], r15b
0x18001d07f  jz      short loc_18001D099
0x18001d081  cmp     byte ptr [rcx+19h], 4
0x18001d085  jb      short loc_18001D099
0x18001d087  mov     [rsp+160h+var_140], rax
0x18001d08c  mov     r9d, [rdi+10h]
0x18001d090  mov     rcx, [rcx+10h]
0x18001d094  call    WPP_SF_Di
0x18001d099  mov     rdx, r12; void *
0x18001d09c  mov     rcx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001d09f  call    ?DiskWaitForVolumesReady@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAX@Z; DiskWaitForVolumesReady(_STORAGE_DEVICE_NUMBER_EX const *,void *)
0x18001d0a4  mov     ebx, eax
0x18001d0a6  mov     [rsp+160h+var_110], eax
0x18001d0aa  test    eax, eax
0x18001d0ac  jns     short loc_18001D0DC
0x18001d0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0b5  cmp     rcx, rsi
0x18001d0b8  jz      loc_18001D7C2
0x18001d0be  test    [rcx+1Ch], r15b
0x18001d0c2  jz      loc_18001D7C2
0x18001d0c8  mov     sil, 2
0x18001d0cb  cmp     [rcx+19h], sil
0x18001d0cf  jb      loc_18001D7C2
0x18001d0d5  mov     edx, 1Eh
0x18001d0da  jmp     short loc_18001D05E
0x18001d0dc  mov     rdx, r12; void *
0x18001d0df  mov     rcx, rdi; this
0x18001d0e2  call    ?UpdateReferenceDriveLayout@CDiskScanner@@QEAAJPEAX@Z; CDiskScanner::UpdateReferenceDriveLayout(void *)
0x18001d0e7  mov     ebx, eax
0x18001d0e9  mov     [rsp+160h+var_110], eax
0x18001d0ed  test    eax, eax
0x18001d0ef  jns     short loc_18001D122
0x18001d0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0f8  cmp     rcx, rsi
0x18001d0fb  jz      loc_18001D7C2
0x18001d101  test    [rcx+1Ch], r15b
0x18001d105  jz      loc_18001D7C2
0x18001d10b  mov     sil, 2
0x18001d10e  cmp     [rcx+19h], sil
0x18001d112  jb      loc_18001D7C2
0x18001d118  mov     edx, 1Fh
0x18001d11d  jmp     loc_18001D05E
0x18001d122  mov     r14d, r13d
0x18001d125  mov     sil, 2
0x18001d128  mov     [rsp+160h+var_120], r13b
0x18001d12d  test    r14d, r14d
0x18001d130  jz      short loc_18001D172
0x18001d132  mov     ecx, 2710h; dwMilliseconds
0x18001d137  call    cs:__imp_Sleep
0x18001d13d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d144  lea     rax, WPP_GLOBAL_Control
0x18001d14b  cmp     rcx, rax
0x18001d14e  jz      short loc_18001D172
0x18001d150  test    [rcx+1Ch], r15b
0x18001d154  jz      short loc_18001D172
0x18001d156  cmp     [rcx+19h], sil
0x18001d15a  jb      short loc_18001D172
0x18001d15c  mov     dword ptr [rsp+160h+var_138], ebx
0x18001d160  mov     dword ptr [rsp+160h+var_140], r14d
0x18001d165  mov     r9d, [rdi+10h]
0x18001d169  mov     rcx, [rcx+10h]
0x18001d16d  call    WPP_SF_Ddd
0x18001d172  lea     r8, [rsp+160h+var_120]
0x18001d177  mov     rdx, rdi
0x18001d17a  lea     rcx, [rsp+160h+var_E8]
0x18001d17f  call    _lambda_d2dfc46f77b2634b1ca0c267f611ece0____lambda_d2dfc46f77b2634b1ca0c267f611ece0_
0x18001d184  mov     rcx, rax
0x18001d187  call    EnumerateSystemVolumes__lambda_488da5a65988c65ea4b6f74dbc66c10d___; EnumerateSystemVolumes__lambda_488da5a65988c65ea4b6f74dbc66c10d_
0x18001d18c  mov     ebx, eax
0x18001d18e  mov     [rsp+160h+var_110], eax
0x18001d192  test    eax, eax
0x18001d194  js      loc_18001D785
0x18001d19a  cmp     [rsp+160h+var_120], r13b
0x18001d19f  jnz     short loc_18001D1AF
0x18001d1a1  cmp     r14d, 7
0x18001d1a5  jnb     short loc_18001D1AF
0x18001d1a7  add     r14d, r15d
0x18001d1aa  jmp     loc_18001D128
0x18001d1af  mov     rdx, r12; void *
0x18001d1b2  mov     rcx, rdi; this
0x18001d1b5  call    ?IsDiskLayoutStable@CDiskScanner@@IEAAJPEAX@Z; CDiskScanner::IsDiskLayoutStable(void *)
0x18001d1ba  test    eax, eax
0x18001d1bc  jz      short loc_18001D206
0x18001d1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1c5  lea     rdx, WPP_GLOBAL_Control
0x18001d1cc  cmp     rcx, rdx
0x18001d1cf  jz      short loc_18001D1FA
0x18001d1d1  test    [rcx+1Ch], r15b
0x18001d1d5  jz      short loc_18001D1FA
0x18001d1d7  cmp     [rcx+19h], sil
0x18001d1db  jb      short loc_18001D1FA
0x18001d1dd  mov     edx, 2Ah ; '*'
0x18001d1e2  mov     dword ptr [rsp+160h+var_140], eax
0x18001d1e6  mov     r9d, [rdi+10h]
0x18001d1ea  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001d1f1  mov     rcx, [rcx+10h]
0x18001d1f5  call    WPP_SF_Dd
0x18001d1fa  lea     r8, [rdi+28h]
0x18001d1fe  mov     r9d, r15d
0x18001d201  jmp     loc_18001D71F
0x18001d206  mov     r15, r13
0x18001d209  lea     rax, [rdi+0A0h]
0x18001d210  mov     r14, [rax]
0x18001d213  lea     r13, [rdi+28h]
0x18001d217  mov     ebx, 0D000010Ah
0x18001d21c  cmp     r14, rax
0x18001d21f  jz      loc_18001D6CB
0x18001d225  lea     r8, ?LiZero@@3T_LARGE_INTEGER@@A; Timeout
0x18001d22c  xor     edx, edx; Alertable
0x18001d22e  mov     rcx, [rdi+60h]; Handle
0x18001d232  call    cs:__imp_NtWaitForSingleObject
0x18001d238  test    eax, eax
0x18001d23a  jz      loc_18001D685
0x18001d240  mov     rdx, r12; void *
0x18001d243  mov     rcx, rdi; this
0x18001d246  call    ?IsDiskLayoutStable@CDiskScanner@@IEAAJPEAX@Z; CDiskScanner::IsDiskLayoutStable(void *)
0x18001d24b  test    eax, eax
0x18001d24d  jnz     loc_18001D653
0x18001d253  mov     r9, [r14+40h]
0x18001d257  sub     r9, r15; unsigned __int64
0x18001d25a  mov     r8, r15; __int64
0x18001d25d  mov     rdx, r12; void *
0x18001d260  mov     rcx, rdi; this
0x18001d263  call    ?DrtScrubNonVolumeArea@CDiskScanner@@IEAAJPEAX_J_K@Z; CDiskScanner::DrtScrubNonVolumeArea(void *,__int64,unsigned __int64)
0x18001d268  mov     r15, [r14+48h]
0x18001d26c  mov     rax, [r14+40h]
0x18001d270  mov     [rsp+160h+var_E8], rax
0x18001d275  lea     r8, ?LiZero@@3T_LARGE_INTEGER@@A; Timeout
0x18001d27c  xor     edx, edx; Alertable
0x18001d27e  mov     rcx, [rdi+60h]; Handle
0x18001d282  call    cs:__imp_NtWaitForSingleObject
0x18001d288  test    eax, eax
0x18001d28a  jz      loc_18001D621
0x18001d290  mov     rdx, r12; void *
0x18001d293  mov     rcx, rdi; this
0x18001d296  call    ?IsDiskLayoutStable@CDiskScanner@@IEAAJPEAX@Z; CDiskScanner::IsDiskLayoutStable(void *)
0x18001d29b  test    eax, eax
0x18001d29d  jnz     loc_18001D5EC
0x18001d2a3  mov     r9, [r14+48h]; unsigned __int64
0x18001d2a7  mov     r8, [r14+40h]; __int64
0x18001d2ab  mov     rdx, r12; void *
0x18001d2ae  mov     rcx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001d2b1  call    ?DrtQueryDirty@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAX_J_K@Z; DrtQueryDirty(_STORAGE_DEVICE_NUMBER_EX const *,void *,__int64,unsigned __int64)
0x18001d2b6  mov     r10d, eax
0x18001d2b9  mov     [rsp+160h+var_110], eax
0x18001d2bd  cmp     eax, 1
0x18001d2c0  jnz     short loc_18001D31E
0x18001d2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2c9  lea     rax, WPP_GLOBAL_Control
0x18001d2d0  cmp     rcx, rax
0x18001d2d3  jz      loc_18001D44D
0x18001d2d9  test    [rcx+1Ch], r10b
0x18001d2dd  jz      loc_18001D44D
0x18001d2e3  cmp     byte ptr [rcx+19h], 4
0x18001d2e7  jb      loc_18001D44D
0x18001d2ed  mov     r8, [r14+48h]
0x18001d2f1  mov     r9, [r14+40h]
0x18001d2f5  lea     rax, [r9+r8]
0x18001d2f9  lea     edx, [r10+2Eh]
0x18001d2fd  mov     qword ptr [rsp+160h+var_130], r8
0x18001d302  mov     [rsp+160h+var_138], rax
0x18001d307  mov     [rsp+160h+var_140], r9
0x18001d30c  mov     r9d, [rdi+10h]
0x18001d310  mov     rcx, [rcx+10h]
0x18001d314  call    WPP_SF_Diii
0x18001d319  jmp     loc_18001D44D
0x18001d31e  test    r10d, r10d
0x18001d321  jns     short loc_18001D385
0x18001d323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d32a  lea     rax, WPP_GLOBAL_Control
0x18001d331  cmp     rcx, rax
0x18001d334  jz      loc_18001D44D
0x18001d33a  test    byte ptr [rcx+1Ch], 1
0x18001d33e  jz      loc_18001D44D
0x18001d344  cmp     [rcx+19h], sil
0x18001d348  jb      loc_18001D44D
0x18001d34e  mov     r8, [r14+48h]
0x18001d352  mov     r9, [r14+40h]
0x18001d356  lea     rax, [r9+r8]
0x18001d35a  mov     edx, 30h ; '0'
0x18001d35f  mov     dword ptr [rsp+160h+var_128], r10d
0x18001d364  mov     qword ptr [rsp+160h+var_130], r8
  ... truncated ...
```
