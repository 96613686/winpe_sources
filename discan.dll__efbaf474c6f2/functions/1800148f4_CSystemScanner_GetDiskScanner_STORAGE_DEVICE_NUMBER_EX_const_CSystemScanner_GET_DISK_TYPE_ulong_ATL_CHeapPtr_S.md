# CSystemScanner::GetDiskScanner(_STORAGE_DEVICE_NUMBER_EX const *,CSystemScanner::GET_DISK_TYPE,ulong,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &,CDiskScanner * &)

- ea: `0x1800148f4`
- end: `0x180014eb6`
- name: `?GetDiskScanner@CSystemScanner@@AEAAJPEBU_STORAGE_DEVICE_NUMBER_EX@@W4GET_DISK_TYPE@1@KAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAKAEAPEAVCDiskScanner@@@Z`
- size: `1474`
- prototype: `__int64 __fastcall(struct IDiskScanNotify *, struct _STORAGE_DEVICE_NUMBER_EX *, int, char, __int64, struct __POSITION *, __int64 *)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x180015ed8`

## callees

- `0x180001b78`
- `0x1800032f8`
- `0x180003640`
- `0x180006470`
- `0x180006498`
- `0x1800064d8`
- `0x180006688`
- `0x1800090a4`
- `0x18000d2ec`
- `0x18000d730`
- `0x180012514`
- `0x180012f60`
- `0x180013668`
- `0x180013720`
- `0x1800137d4`
- `0x180013fa8`
- `0x1800140f4`
- `0x1800146c4`
- `0x1800148f4`
- `0x180014ee8`
- `0x180015440`
- `0x180016540`
- `0x18001bb24`
- `0x180037620`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180014a09`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014a09`

## pseudocode

```c
__int64 __fastcall CSystemScanner::GetDiskScanner(
        struct IDiskScanNotify *a1,
        struct _STORAGE_DEVICE_NUMBER_EX *a2,
        int a3,
        char a4,
        __int64 a5,
        struct __POSITION *a6,
        __int64 *a7)
{
  __int64 v11; // r9
  USHORT v12; // dx
  USHORT Length; // cx
  USHORT v14; // ax
  DWORD *p_DeviceNumber; // rsi
  __int64 v16; // rax
  int SpacePoolContext; // ebx
  int SpaceId; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // r14d
  HANDLE v22; // rbx
  int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  struct __POSITION *v26; // r15
  struct CSpacePoolContext *v27; // rax
  __int64 v28; // rcx
  struct CSpacePoolContext *v29; // rbx
  __int64 result; // rax
  int TargetHandle; // [rsp+20h] [rbp-D8h]
  HANDLE hSourceHandle; // [rsp+40h] [rbp-B8h] BYREF
  char *v33; // [rsp+48h] [rbp-B0h]
  struct __POSITION *v34; // [rsp+50h] [rbp-A8h] BYREF
  const char *v35; // [rsp+58h] [rbp-A0h] BYREF
  int v36; // [rsp+60h] [rbp-98h]
  struct CSpacePoolContext *v37; // [rsp+68h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+70h] [rbp-88h] BYREF
  RTL_SRWLOCK *v39; // [rsp+78h] [rbp-80h] BYREF
  struct CSpacePoolContext *v40; // [rsp+80h] [rbp-78h] BYREF
  struct CSpacePoolContext **v41; // [rsp+88h] [rbp-70h]
  _BYTE v42[16]; // [rsp+90h] [rbp-68h] BYREF
  struct _GUID v43[2]; // [rsp+A0h] [rbp-58h] BYREF

  v34 = a6;
  v41 = (struct CSpacePoolContext **)a7;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v11 + 16) = "CSystemScanner::GetDiskScanner";
  v35 = "CSystemScanner::GetDiskScanner";
  v12 = ++*(_WORD *)(v11 + 8);
  Length = GlobalIndentString.Length;
  v14 = GlobalIndentString.Length;
  if ( v12 < GlobalIndentString.Length )
    v14 = *(_WORD *)(v11 + 8);
  LOWORD(hSourceHandle) = v14;
  if ( v12 < GlobalIndentString.Length )
    Length = v12;
  WORD1(hSourceHandle) = Length;
  HIDWORD(hSourceHandle) = 0;
  v33 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CSystemScanner::GetDiskScanner");
  }
  *a7 = 0;
  v39 = (RTL_SRWLOCK *)((char *)a1 + 152);
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 19);
  p_DeviceNumber = &a2->DeviceNumber;
  v16 = ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::Lookup(
          (char *)a1 + 208,
          &a2->DeviceNumber);
  if ( v16 )
  {
    *a7 = v16;
    v36 = 0;
    SpacePoolContext = 0;
    goto LABEL_61;
  }
  if ( a3 == 1 )
  {
    SpacePoolContext = -2147023728;
    v36 = -2147023728;
    goto LABEL_61;
  }
  hSourceHandle = (HANDLE)-1LL;
  LODWORD(v33) = 0;
  BYTE4(v33) = 0;
  SpaceId = DiskCreateHandle(a2, &hSourceHandle, 0x100080u);
  SpacePoolContext = SpaceId;
  v36 = SpaceId;
  if ( SpaceId < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v20 = 38;
    goto LABEL_18;
  }
  memset(v43, 0, sizeof(v43));
  if ( (a4 & 2) != 0 )
  {
    SpaceId = GetSpaceId(a2, hSourceHandle, v43, &v43[1], a5, v34);
    SpacePoolContext = SpaceId;
    v36 = SpaceId;
    if ( SpaceId < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v20 = 39;
LABEL_18:
      TargetHandle = SpaceId;
LABEL_19:
      WPP_SF_Dd(v19[2], v20, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, *p_DeviceNumber, TargetHandle);
LABEL_20:
      CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&hSourceHandle);
      goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D_guid__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        *p_DeviceNumber,
        (__int64)v43,
        (__int64)&v43[1]);
    }
  }
  v37 = 0;
  SpacePoolContext = CSystemScanner::GetSpacePoolContext(a1, a2, v43, &v37);
  v36 = SpacePoolContext;
  if ( SpacePoolContext < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v20 = 41;
    TargetHandle = SpacePoolContext;
    goto LABEL_19;
  }
  v21 = (2 * !(a4 & 1)) | 1;
  v22 = hSourceHandle;
  v23 = IsParitySpace(a2, hSourceHandle, a5, v34);
  v36 = v23;
  if ( v23 >= 0 )
  {
    if ( v23 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_74;
      }
      v25 = 44;
    }
    else
    {
      v21 |= 1u;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_74;
      }
      v25 = 43;
    }
    WPP_SF_d(v24[2], v25, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, *p_DeviceNumber);
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
      *p_DeviceNumber,
      v23);
  }
LABEL_74:
  try
  {
    v26 = (struct __POSITION *)ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::AddTail((char *)a1 + 160);
    v34 = v26;
    lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_::_lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_(v42, a1, &v34);
    v34 = (struct __POSITION *)v42;
    v27 = (struct CSpacePoolContext *)operator new(0x108u);
    v40 = v27;
    if ( v27 )
      v29 = CDiskScanner::CDiskScanner(
              v27,
              v22,
              (struct CSpacePoolContext *)((char *)v37 + 112),
              a1,
              a2,
              (const struct SPACEPORT_DISK_INFO *)v43,
              v26,
              v21);
    else
      v29 = 0;
    v40 = v29;
    v37 = v29;
    ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::SetAt(v28, v26, &v37);
    ATL::CAutoPtr<CDiskScanner>::Free(&v37);
    if ( !(unsigned int)ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::Add(
                          (char *)a1 + 208,
                          &a2->DeviceNumber,
                          &v40) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
      }
      ATL::AtlThrowImpl(-2147024882);
    }
    v34 = 0;
    CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___::_CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___(&v34);
    *v41 = v29;
    v36 = 0;
    CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&hSourceHandle);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v39);
    CHResultImp::~CHResultImp((CHResultImp *)&v35);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
    }
    v36 = -2147024882;
    CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&hSourceHandle);
    SpacePoolContext = -2147024882;
LABEL_61:
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v39);
    CHResultImp::~CHResultImp((CHResultImp *)&v35);
    return (unsigned int)SpacePoolContext;
  }
  catch ( ATL::CAtlException v38 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
    }
    v36 = v38;
    CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&hSourceHandle);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v39);
    CHResultImp::~CHResultImp((CHResultImp *)&v35);
    return v38;
  }
  v26 = (struct __POSITION *)ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::AddTail((char *)a1 + 160);
}

```

## disassembly

```asm
0x1800148f4  mov     [rsp+arg_10], rbx
0x1800148f9  mov     [rsp+arg_18], rsi
0x1800148fe  push    rdi
0x1800148ff  push    r12
0x180014901  push    r13
0x180014903  push    r14
0x180014905  push    r15
0x180014907  sub     rsp, 0D0h
0x18001490e  mov     rax, cs:__security_cookie
0x180014915  xor     rax, rsp
0x180014918  mov     [rsp+0F8h+var_38], rax
0x180014920  mov     r14d, r9d
0x180014923  mov     ebx, r8d
0x180014926  mov     r12, rdx
0x180014929  mov     r13, rcx
0x18001492c  mov     r15, [rsp+0F8h+arg_20]
0x180014934  mov     rax, [rsp+0F8h+arg_28]
0x18001493c  mov     [rsp+0F8h+var_A8], rax
0x180014941  mov     rdi, [rsp+0F8h+arg_30]
0x180014949  mov     [rsp+0F8h+var_70], rdi
0x180014951  mov     ecx, cs:_tls_index
0x180014957  mov     rax, gs:58h
0x180014960  mov     r9, [rax+rcx*8]
0x180014964  mov     eax, 10h
0x180014969  lea     r10, aCsystemscanner_5; "CSystemScanner::GetDiskScanner"
0x180014970  mov     [rax+r9], r10
0x180014974  mov     [rsp+0F8h+var_A0], r10
0x180014979  mov     edx, 8
0x18001497e  mov     r8d, 1
0x180014984  add     [rdx+r9], r8w
0x180014989  movzx   edx, word ptr [rdx+r9]
0x18001498e  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180014995  movzx   eax, cx
0x180014998  cmp     dx, cx
0x18001499b  cmovb   ax, dx
0x18001499f  mov     word ptr [rsp+0F8h+hSourceHandle], ax
0x1800149a4  cmovb   cx, dx
0x1800149a8  mov     word ptr [rsp+0F8h+hSourceHandle+2], cx
0x1800149ad  xor     eax, eax
0x1800149af  mov     dword ptr [rsp+0F8h+hSourceHandle+4], eax
0x1800149b3  mov     rax, cs:off_180047060; "                                       "...
0x1800149ba  mov     [rsp+0F8h+var_B0], rax
0x1800149bf  lea     rax, WPP_GLOBAL_Control
0x1800149c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149cd  cmp     rcx, rax
0x1800149d0  jz      short loc_1800149F6
0x1800149d2  test    [rcx+1Ch], r8b
0x1800149d6  jz      short loc_1800149F6
0x1800149d8  cmp     byte ptr [rcx+19h], 5
0x1800149dc  jb      short loc_1800149F6
0x1800149de  lea     edx, [r8+0Ch]
0x1800149e2  mov     [rsp+0F8h+TargetHandle], r10; __int64
0x1800149e7  lea     r9, [rsp+0F8h+hSourceHandle]
0x1800149ec  mov     rcx, [rcx+10h]; LoggerHandle
0x1800149f0  call    WPP_SF_aZs
0x1800149f5  nop
0x1800149f6  mov     qword ptr [rdi], 0
0x1800149fd  lea     rcx, [r13+98h]; SRWLock
0x180014a04  mov     [rsp+0F8h+var_80], rcx
0x180014a09  call    cs:__imp_AcquireSRWLockExclusive
0x180014a0f  nop
0x180014a10  lea     rcx, [r13+0D0h]
0x180014a17  lea     rsi, [r12+10h]
0x180014a1c  mov     rdx, rsi
0x180014a1f  call    ?Lookup@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEBAPEAVCDiskScanner@@AEBK@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::Lookup(ulong const &)
0x180014a24  xor     ecx, ecx
0x180014a26  test    rax, rax
0x180014a29  jz      short loc_180014A39
0x180014a2b  mov     [rdi], rax
0x180014a2e  mov     [rsp+0F8h+var_98], ecx
0x180014a32  mov     ebx, ecx
0x180014a34  jmp     loc_180014E4C
0x180014a39  cmp     ebx, 1
0x180014a3c  jnz     short loc_180014A4C
0x180014a3e  mov     ebx, 80070490h
0x180014a43  mov     [rsp+0F8h+var_98], ebx
0x180014a47  jmp     loc_180014E4C
0x180014a4c  mov     [rsp+0F8h+hSourceHandle], 0FFFFFFFFFFFFFFFFh
0x180014a55  mov     dword ptr [rsp+0F8h+var_B0], ecx
0x180014a59  mov     byte ptr [rsp+0F8h+var_B0+4], cl
0x180014a5d  mov     r8d, 100080h; unsigned int
0x180014a63  lea     rdx, [rsp+0F8h+hSourceHandle]; void **
0x180014a68  mov     rcx, r12; struct _STORAGE_DEVICE_NUMBER_EX *
0x180014a6b  call    ?DiskCreateHandle@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAPEAXK@Z; DiskCreateHandle(_STORAGE_DEVICE_NUMBER_EX const *,void * *,ulong)
0x180014a70  mov     ebx, eax
0x180014a72  mov     [rsp+0F8h+var_98], eax
0x180014a76  test    eax, eax
0x180014a78  jns     short loc_180014AC8
0x180014a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a81  lea     rdx, WPP_GLOBAL_Control
0x180014a88  cmp     rcx, rdx
0x180014a8b  jz      short loc_180014AB9
0x180014a8d  test    byte ptr [rcx+1Ch], 1
0x180014a91  jz      short loc_180014AB9
0x180014a93  mov     dil, 2
0x180014a96  cmp     [rcx+19h], dil
0x180014a9a  jb      short loc_180014AB9
0x180014a9c  mov     edx, 26h ; '&'
0x180014aa1  mov     dword ptr [rsp+0F8h+TargetHandle], eax
0x180014aa5  mov     r9d, [rsi]
0x180014aa8  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180014aaf  mov     rcx, [rcx+10h]
0x180014ab3  call    WPP_SF_Dd
0x180014ab8  nop
0x180014ab9  lea     rcx, [rsp+0F8h+hSourceHandle]
0x180014abe  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x180014ac3  jmp     loc_180014E4C
0x180014ac8  mov     dword ptr [rsp+0F8h+var_58], 0
0x180014ad3  xorps   xmm0, xmm0
0x180014ad6  movups  xmmword ptr [rsp+0F8h+var_58+4], xmm0
0x180014ade  movups  xmmword ptr [rsp+0F8h+var_58+10h], xmm0
0x180014ae6  mov     dil, 2
0x180014ae9  test    dil, r14b
0x180014aec  jz      loc_180014BAE
0x180014af2  mov     rax, [rsp+0F8h+var_A8]
0x180014af7  mov     [rsp+0F8h+var_D0], rax
0x180014afc  mov     [rsp+0F8h+TargetHandle], r15
0x180014b01  lea     r9, [rsp+0F8h+var_58+10h]
0x180014b09  lea     r8, [rsp+0F8h+var_58]
0x180014b11  mov     rdx, [rsp+0F8h+hSourceHandle]
0x180014b16  mov     rcx, r12
0x180014b19  call    ?GetSpaceId@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXPEAU_GUID@@2AEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z; GetSpaceId(_STORAGE_DEVICE_NUMBER_EX const *,void *,_GUID *,_GUID *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &)
0x180014b1e  mov     ebx, eax
0x180014b20  mov     [rsp+0F8h+var_98], eax
0x180014b24  test    eax, eax
0x180014b26  jns     short loc_180014B5D
0x180014b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b2f  lea     rdx, WPP_GLOBAL_Control
0x180014b36  cmp     rcx, rdx
0x180014b39  jz      loc_180014AB9
0x180014b3f  test    byte ptr [rcx+1Ch], 1
0x180014b43  jz      loc_180014AB9
0x180014b49  cmp     [rcx+19h], dil
0x180014b4d  jb      loc_180014AB9
0x180014b53  mov     edx, 27h ; '''
0x180014b58  jmp     loc_180014AA1
0x180014b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b64  lea     rax, WPP_GLOBAL_Control
0x180014b6b  cmp     rcx, rax
0x180014b6e  jz      short loc_180014BAE
0x180014b70  test    byte ptr [rcx+1Ch], 1
0x180014b74  jz      short loc_180014BAE
0x180014b76  cmp     byte ptr [rcx+19h], 4
0x180014b7a  jb      short loc_180014BAE
0x180014b7c  mov     edx, 28h ; '('
0x180014b81  lea     rax, [rsp+0F8h+var_58+10h]
0x180014b89  mov     [rsp+0F8h+var_D0], rax
0x180014b8e  lea     rax, [rsp+0F8h+var_58]
0x180014b96  mov     [rsp+0F8h+TargetHandle], rax
0x180014b9b  mov     r9d, [rsi]
0x180014b9e  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180014ba5  mov     rcx, [rcx+10h]
0x180014ba9  call    WPP_SF_D_guid__guid_
0x180014bae  mov     [rsp+0F8h+var_90], 0
0x180014bb7  lea     r9, [rsp+0F8h+var_90]; struct CSpacePoolContext **
0x180014bbc  lea     r8, [rsp+0F8h+var_58]; struct _GUID *
0x180014bc4  mov     rdx, r12; struct _STORAGE_DEVICE_NUMBER_EX *
0x180014bc7  mov     rcx, r13; this
0x180014bca  call    ?GetSpacePoolContext@CSystemScanner@@AEAAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEBU_GUID@@AEAPEAVCSpacePoolContext@@@Z; CSystemScanner::GetSpacePoolContext(_STORAGE_DEVICE_NUMBER_EX const *,_GUID const *,CSpacePoolContext * &)
0x180014bcf  mov     ebx, eax
0x180014bd1  mov     [rsp+0F8h+var_98], eax
0x180014bd5  test    eax, eax
0x180014bd7  jns     short loc_180014C12
0x180014bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014be0  lea     rax, WPP_GLOBAL_Control
0x180014be7  cmp     rcx, rax
0x180014bea  jz      loc_180014AB9
0x180014bf0  test    byte ptr [rcx+1Ch], 1
0x180014bf4  jz      loc_180014AB9
0x180014bfa  cmp     [rcx+19h], dil
0x180014bfe  jb      loc_180014AB9
0x180014c04  mov     edx, 29h ; ')'
0x180014c09  mov     dword ptr [rsp+0F8h+TargetHandle], ebx
0x180014c0d  jmp     loc_180014AA5
0x180014c12  and     r14d, 1
0x180014c16  xor     r14d, 1
0x180014c1a  add     r14d, r14d
0x180014c1d  or      r14d, 1
0x180014c21  mov     r9, [rsp+0F8h+var_A8]
0x180014c26  mov     r8, r15
0x180014c29  mov     rbx, [rsp+0F8h+hSourceHandle]
0x180014c2e  mov     rdx, rbx
0x180014c31  mov     rcx, r12
0x180014c34  call    ?IsParitySpace@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z; IsParitySpace(_STORAGE_DEVICE_NUMBER_EX const *,void *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &)
0x180014c39  mov     [rsp+0F8h+var_98], eax
0x180014c3d  test    eax, eax
0x180014c3f  jns     short loc_180014C8A
0x180014c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c48  lea     rdx, WPP_GLOBAL_Control
0x180014c4f  cmp     rcx, rdx
0x180014c52  jz      loc_180014CED
0x180014c58  test    byte ptr [rcx+1Ch], 1
0x180014c5c  jz      loc_180014CED
0x180014c62  cmp     [rcx+19h], dil
0x180014c66  jb      loc_180014CED
0x180014c6c  mov     edx, 2Ah ; '*'
0x180014c71  mov     dword ptr [rsp+0F8h+TargetHandle], eax
0x180014c75  mov     r9d, [rsi]
0x180014c78  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180014c7f  mov     rcx, [rcx+10h]
0x180014c83  call    WPP_SF_Dd
0x180014c88  jmp     short loc_180014CED
0x180014c8a  jnz     short loc_180014CB6
0x180014c8c  or      r14d, 1
0x180014c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c97  lea     rax, WPP_GLOBAL_Control
0x180014c9e  cmp     rcx, rax
0x180014ca1  jz      short loc_180014CED
0x180014ca3  test    byte ptr [rcx+1Ch], 1
0x180014ca7  jz      short loc_180014CED
0x180014ca9  cmp     byte ptr [rcx+19h], 4
0x180014cad  jb      short loc_180014CED
0x180014caf  mov     edx, 2Bh ; '+'
0x180014cb4  jmp     short loc_180014CDA
0x180014cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cbd  lea     rax, WPP_GLOBAL_Control
0x180014cc4  cmp     rcx, rax
0x180014cc7  jz      short loc_180014CED
0x180014cc9  test    byte ptr [rcx+1Ch], 1
0x180014ccd  jz      short loc_180014CED
0x180014ccf  cmp     byte ptr [rcx+19h], 4
0x180014cd3  jb      short loc_180014CED
0x180014cd5  mov     edx, 2Ch ; ','
0x180014cda  mov     r9d, [rsi]
0x180014cdd  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180014ce4  mov     rcx, [rcx+10h]
0x180014ce8  call    WPP_SF_d
0x180014ced  lea     rcx, [r13+0A0h]
0x180014cf4  call    ?AddTail@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAPEAU__POSITION@@XZ; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::AddTail(void)
0x180014cf9  mov     r15, rax
0x180014cfc  mov     [rsp+0F8h+var_A8], rax
0x180014d01  lea     r8, [rsp+0F8h+var_A8]
0x180014d06  mov     rdx, r13
0x180014d09  lea     rcx, [rsp+0F8h+var_68]
0x180014d11  call    _lambda_a1b1af645970ce3b4f2d5a29ed6a25f9____lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_
0x180014d16  lea     rcx, [rsp+0F8h+var_68]
0x180014d1e  mov     [rsp+0F8h+var_A8], rcx
0x180014d23  mov     ecx, 108h; Size
0x180014d28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d2d  mov     [rsp+0F8h+var_78], rax
0x180014d35  test    rax, rax
0x180014d38  jz      short loc_180014D72
0x180014d3a  mov     r8, [rsp+0F8h+var_90]
0x180014d3f  add     r8, 70h ; 'p'; struct _SCRUB_ENVIRONMENT *
0x180014d43  mov     [rsp+0F8h+var_C0], r14d; unsigned int
0x180014d48  mov     [rsp+0F8h+var_C8], r15; struct __POSITION *
0x180014d4d  lea     rcx, [rsp+0F8h+var_58]
0x180014d55  mov     [rsp+0F8h+var_D0], rcx; struct SPACEPORT_DISK_INFO *
0x180014d5a  mov     [rsp+0F8h+TargetHandle], r12; TargetHandle
0x180014d5f  mov     r9, r13; struct IDiskScanNotify *
0x180014d62  mov     rdx, rbx; hSourceHandle
0x180014d65  mov     rcx, rax; pv
0x180014d68  call    ??0CDiskScanner@@QEAA@PEAXPEAU_SCRUB_ENVIRONMENT@@PEAUIDiskScanNotify@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@PEAU__POSITION@@K@Z; CDiskScanner::CDiskScanner(void *,_SCRUB_ENVIRONMENT *,IDiskScanNotify *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,__POSITION *,ulong)
0x180014d6d  mov     rbx, rax
0x180014d70  jmp     short loc_180014D74
0x180014d72  xor     ebx, ebx
0x180014d74  mov     [rsp+0F8h+var_78], rbx
0x180014d7c  mov     [rsp+0F8h+var_90], rbx
0x180014d81  lea     r8, [rsp+0F8h+var_90]
0x180014d86  mov     rdx, r15
0x180014d89  call    ?SetAt@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAXPEAU__POSITION@@AEAV?$CAutoPtr@VCDiskScanner@@@2@@Z; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::SetAt(__POSITION *,ATL::CAutoPtr<CDiskScanner> &)
0x180014d8e  nop
0x180014d8f  lea     rcx, [rsp+0F8h+var_90]
0x180014d94  call    ?Free@?$CAutoPtr@VCDiskScanner@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CDiskScanner>::Free(void)
0x180014d99  lea     r8, [rsp+0F8h+var_78]
0x180014da1  mov     rdx, rsi
0x180014da4  lea     rcx, [r13+0D0h]
0x180014dab  call    ?Add@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAHAEBKAEBQEAVCDiskScanner@@@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::Add(ulong const &,CDiskScanner * const &)
0x180014db0  test    eax, eax
0x180014db2  jnz     short loc_180014DF2
0x180014db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dbb  lea     rax, WPP_GLOBAL_Control
0x180014dc2  cmp     rcx, rax
0x180014dc5  jz      short loc_180014DE8
0x180014dc7  test    byte ptr [rcx+1Ch], 1
0x180014dcb  jz      short loc_180014DE8
0x180014dcd  cmp     [rcx+19h], dil
0x180014dd1  jb      short loc_180014DE8
0x180014dd3  mov     edx, 2Dh ; '-'
0x180014dd8  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180014ddf  mov     rcx, [rcx+10h]
0x180014de3  call    WPP_SF_
0x180014de8  mov     ecx, 8007000Eh; int
0x180014ded  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014df2  mov     [rsp+0F8h+var_A8], 0
0x180014dfb  lea     rcx, [rsp+0F8h+var_A8]
0x180014e00  call    CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4______CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___
0x180014e05  nop
0x180014e06  mov     rax, [rsp+0F8h+var_70]
0x180014e0e  mov     [rax], rbx
0x180014e11  mov     [rsp+0F8h+var_98], 0
0x180014e19  lea     rcx, [rsp+0F8h+hSourceHandle]
0x180014e1e  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x180014e23  nop
0x180014e24  lea     rcx, [rsp+0F8h+var_80]; this
0x180014e29  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180014e2e  nop
0x180014e2f  lea     rcx, [rsp+0F8h+var_A0]; this
0x180014e34  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180014e39  xor     eax, eax
  ... truncated ...
```
