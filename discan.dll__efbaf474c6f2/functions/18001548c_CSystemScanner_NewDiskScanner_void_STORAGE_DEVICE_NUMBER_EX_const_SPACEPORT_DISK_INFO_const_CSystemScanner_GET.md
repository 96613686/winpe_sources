# CSystemScanner::NewDiskScanner(void *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,CSystemScanner::GET_DISK_TYPE,CSpacePoolContext *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &,CDiskScanner * &)

- ea: `0x18001548c`
- end: `0x1800157e1`
- name: `?NewDiskScanner@CSystemScanner@@AEAAJPEAXPEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@W4GET_DISK_TYPE@1@PEAVCSpacePoolContext@@AEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAKAEAPEAVCDiskScanner@@@Z`
- size: `853`
- prototype: `__int64(RTL_SRWLOCK *, HANDLE hSourceHandle, char *TargetHandle, struct SPACEPORT_DISK_INFO *, int, __int64, _QWORD *, __int64, ...)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800165a0`

## callees

- `0x180001b78`
- `0x1800032f8`
- `0x180003640`
- `0x180006470`
- `0x1800064d8`
- `0x180006688`
- `0x18000d730`
- `0x180012f60`
- `0x180013668`
- `0x1800137d4`
- `0x180013fa8`
- `0x1800140f4`
- `0x1800146c4`
- `0x180015440`
- `0x18001548c`
- `0x180016540`
- `0x18001bb24`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001556e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001556e`

## pseudocode

```c
__int64 CSystemScanner::NewDiskScanner(
        RTL_SRWLOCK *a1,
        HANDLE hSourceHandle,
        char *TargetHandle,
        struct SPACEPORT_DISK_INFO *a4,
        int a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        ...)
{
  __int64 v11; // r11
  USHORT v12; // dx
  USHORT Length; // cx
  USHORT v14; // ax
  CDiskScanner **v15; // r15
  RTL_SRWLOCK *v16; // r12
  unsigned int *v17; // rsi
  unsigned int v18; // ebx
  int v19; // eax
  struct __POSITION *v20; // rdi
  struct __POSITION *v21; // rax
  __int64 v22; // rcx
  CDiskScanner *v23; // rbx
  __int64 result; // rax
  unsigned int v25; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-70h] BYREF
  const char *v27; // [rsp+58h] [rbp-60h] BYREF
  int v28; // [rsp+60h] [rbp-58h]
  _BYTE v29[80]; // [rsp+68h] [rbp-50h] BYREF
  struct __POSITION *v30; // [rsp+C0h] [rbp+8h] BYREF
  _BYTE *v31; // [rsp+D0h] [rbp+18h] BYREF
  struct SPACEPORT_DISK_INFO *v32; // [rsp+D8h] [rbp+20h]
  RTL_SRWLOCK *v33; // [rsp+100h] [rbp+48h] BYREF
  va_list va; // [rsp+100h] [rbp+48h]
  va_list va1; // [rsp+108h] [rbp+50h] BYREF

  va_start(va1, a8);
  va_start(va, a8);
  v33 = va_arg(va1, RTL_SRWLOCK *);
  v32 = a4;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v11 + 16) = "CSystemScanner::NewDiskScanner";
  v27 = "CSystemScanner::NewDiskScanner";
  v12 = ++*(_WORD *)(v11 + 8);
  Length = GlobalIndentString.Length;
  v14 = GlobalIndentString.Length;
  if ( v12 < GlobalIndentString.Length )
    v14 = *(_WORD *)(v11 + 8);
  LOWORD(v26[0]) = v14;
  if ( v12 < GlobalIndentString.Length )
    Length = v12;
  WORD1(v26[0]) = Length;
  HIDWORD(v26[0]) = 0;
  v26[1] = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CSystemScanner::NewDiskScanner");
  }
  v15 = (CDiskScanner **)v33;
  v33->Ptr = 0;
  v33 = a1 + 19;
  AcquireSRWLockExclusive(a1 + 19);
  v16 = a1 + 26;
  v17 = (unsigned int *)(TargetHandle + 16);
  if ( ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::Lookup(
         &a1[26],
         TargetHandle + 16) )
  {
    v18 = -2147022882;
    v28 = -2147022882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        *v17,
        -2147022882);
    }
LABEL_29:
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)va);
    CHResultImp::~CHResultImp((CHResultImp *)&v27);
    return v18;
  }
  v19 = IsParitySpace((__int64)TargetHandle, hSourceHandle, a7, a8);
  v28 = v19;
  if ( v19 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, *v17, v19);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v20 = (struct __POSITION *)ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::AddTail(&a1[20]);
    v30 = v20;
    lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_::_lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_(v29, a1, &v30);
    v31 = v29;
    v21 = (struct __POSITION *)operator new(0x108u);
    v30 = v21;
    if ( v21 )
      v23 = CDiskScanner::CDiskScanner(
              v21,
              hSourceHandle,
              (struct _SCRUB_ENVIRONMENT *)(a6 + 112),
              (struct IDiskScanNotify *)a1,
              TargetHandle,
              v32,
              v20,
              1u);
    else
      v23 = 0;
    v26[0] = v23;
    v30 = v23;
    ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::SetAt(v22, v20, &v30);
    ATL::CAutoPtr<CDiskScanner>::Free(&v30);
    if ( !(unsigned int)ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::Add(
                          v16,
                          TargetHandle + 16,
                          v26) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
      }
      ATL::AtlThrowImpl(-2147024882);
    }
    v31 = 0;
    CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___::_CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___(&v31);
    *v15 = v23;
    v28 = 0;
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)va);
    CHResultImp::~CHResultImp((CHResultImp *)&v27);
    result = 0;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
      }
      v28 = -2147024882;
      v18 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180015791);
      goto LABEL_29;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v25) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids);
      }
      v28 = v25;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800157B2);
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)va);
      CHResultImp::~CHResultImp((CHResultImp *)&v27);
      return v25;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001548c  mov     [rsp+arg_18], r9
0x180015491  push    rbx
0x180015492  push    rsi
0x180015493  push    rdi
0x180015494  push    r12
0x180015496  push    r13
0x180015498  push    r14
0x18001549a  push    r15
0x18001549c  sub     rsp, 80h
0x1800154a3  mov     r14, r8
0x1800154a6  mov     r13, rdx
0x1800154a9  mov     rbx, rcx
0x1800154ac  mov     r10d, cs:_tls_index
0x1800154b3  mov     rax, gs:58h
0x1800154bc  mov     r11, [rax+r10*8]
0x1800154c0  mov     eax, 10h
0x1800154c5  lea     r8, aCsystemscanner_9; "CSystemScanner::NewDiskScanner"
0x1800154cc  mov     [rax+r11], r8
0x1800154d0  mov     [rsp+0B8h+var_60], r8
0x1800154d5  mov     edx, 8
0x1800154da  mov     edi, 1
0x1800154df  add     [rdx+r11], di
0x1800154e4  movzx   edx, word ptr [rdx+r11]
0x1800154e9  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800154f0  movzx   eax, cx
0x1800154f3  cmp     dx, cx
0x1800154f6  cmovb   ax, dx
0x1800154fa  mov     word ptr [rsp+0B8h+var_70], ax
0x1800154ff  cmovb   cx, dx
0x180015503  mov     word ptr [rsp+0B8h+var_70+2], cx
0x180015508  xor     eax, eax
0x18001550a  mov     dword ptr [rsp+0B8h+var_70+4], eax
0x18001550e  mov     rax, cs:off_180047060; "                                       "...
0x180015515  mov     [rsp+0B8h+var_68], rax
0x18001551a  lea     rax, WPP_GLOBAL_Control
0x180015521  mov     rcx, cs:WPP_GLOBAL_Control
0x180015528  cmp     rcx, rax
0x18001552b  jz      short loc_180015550
0x18001552d  test    [rcx+1Ch], dil
0x180015531  jz      short loc_180015550
0x180015533  cmp     byte ptr [rcx+19h], 5
0x180015537  jb      short loc_180015550
0x180015539  lea     edx, [rdi+0Ch]
0x18001553c  mov     [rsp+0B8h+TargetHandle], r8; __int64
0x180015541  lea     r9, [rsp+0B8h+var_70]
0x180015546  mov     rcx, [rcx+10h]; LoggerHandle
0x18001554a  call    WPP_SF_aZs
0x18001554f  nop
0x180015550  mov     r15, [rsp+0B8h+arg_40]
0x180015558  mov     qword ptr [r15], 0
0x18001555f  lea     rcx, [rbx+98h]; SRWLock
0x180015566  mov     [rsp+0B8h+arg_40], rcx
0x18001556e  call    cs:__imp_AcquireSRWLockExclusive
0x180015574  nop
0x180015575  lea     r12, [rbx+0D0h]
0x18001557c  lea     rsi, [r14+10h]
0x180015580  mov     rdx, rsi
0x180015583  mov     rcx, r12
0x180015586  call    ?Lookup@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEBAPEAVCDiskScanner@@AEBK@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::Lookup(ulong const &)
0x18001558b  test    rax, rax
0x18001558e  jz      short loc_1800155E5
0x180015590  mov     ebx, 800707DEh
0x180015595  mov     [rsp+0B8h+var_58], ebx
0x180015599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155a0  lea     rdx, WPP_GLOBAL_Control
0x1800155a7  cmp     rcx, rdx
0x1800155aa  jz      loc_180015796
0x1800155b0  test    [rcx+1Ch], dil
0x1800155b4  jz      loc_180015796
0x1800155ba  cmp     byte ptr [rcx+19h], 2
0x1800155be  jb      loc_180015796
0x1800155c4  mov     edx, 32h ; '2'
0x1800155c9  mov     dword ptr [rsp+0B8h+TargetHandle], ebx
0x1800155cd  mov     r9d, [rsi]
0x1800155d0  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800155d7  mov     rcx, [rcx+10h]
0x1800155db  call    WPP_SF_Dd
0x1800155e0  jmp     loc_180015796
0x1800155e5  mov     r9, [rsp+0B8h+arg_38]
0x1800155ed  mov     r8, [rsp+0B8h+arg_30]
0x1800155f5  mov     rdx, r13
0x1800155f8  mov     rcx, r14
0x1800155fb  call    ?IsParitySpace@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z; IsParitySpace(_STORAGE_DEVICE_NUMBER_EX const *,void *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &)
0x180015600  mov     [rsp+0B8h+var_58], eax
0x180015604  test    eax, eax
0x180015606  jns     short loc_180015643
0x180015608  mov     rcx, cs:WPP_GLOBAL_Control
0x18001560f  lea     rdx, WPP_GLOBAL_Control
0x180015616  cmp     rcx, rdx
0x180015619  jz      short loc_180015643
0x18001561b  test    [rcx+1Ch], dil
0x18001561f  jz      short loc_180015643
0x180015621  cmp     byte ptr [rcx+19h], 2
0x180015625  jb      short loc_180015643
0x180015627  mov     edx, 33h ; '3'
0x18001562c  mov     dword ptr [rsp+0B8h+TargetHandle], eax
0x180015630  mov     r9d, [rsi]
0x180015633  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x18001563a  mov     rcx, [rcx+10h]
0x18001563e  call    WPP_SF_Dd
0x180015643  lea     rcx, [rbx+0A0h]
0x18001564a  call    ?AddTail@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAPEAU__POSITION@@XZ; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::AddTail(void)
0x18001564f  mov     rdi, rax
0x180015652  mov     [rsp+0B8h+arg_0], rax
0x18001565a  lea     r8, [rsp+0B8h+arg_0]
0x180015662  mov     rdx, rbx
0x180015665  lea     rcx, [rsp+0B8h+var_50]
0x18001566a  call    _lambda_a1b1af645970ce3b4f2d5a29ed6a25f9____lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_
0x18001566f  lea     rcx, [rsp+0B8h+var_50]
0x180015674  mov     [rsp+0B8h+arg_10], rcx
0x18001567c  mov     ecx, 108h; Size
0x180015681  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015686  mov     [rsp+0B8h+arg_0], rax
0x18001568e  test    rax, rax
0x180015691  jz      short loc_1800156D1
0x180015693  mov     r8, [rsp+0B8h+arg_28]
0x18001569b  add     r8, 70h ; 'p'; struct _SCRUB_ENVIRONMENT *
0x18001569f  mov     [rsp+0B8h+var_80], 1; unsigned int
0x1800156a7  mov     [rsp+0B8h+var_88], rdi; struct __POSITION *
0x1800156ac  mov     rcx, [rsp+0B8h+arg_18]
0x1800156b4  mov     [rsp+0B8h+var_90], rcx; struct SPACEPORT_DISK_INFO *
0x1800156b9  mov     [rsp+0B8h+TargetHandle], r14; TargetHandle
0x1800156be  mov     r9, rbx; struct IDiskScanNotify *
0x1800156c1  mov     rdx, r13; hSourceHandle
0x1800156c4  mov     rcx, rax; pv
0x1800156c7  call    ??0CDiskScanner@@QEAA@PEAXPEAU_SCRUB_ENVIRONMENT@@PEAUIDiskScanNotify@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@PEAU__POSITION@@K@Z; CDiskScanner::CDiskScanner(void *,_SCRUB_ENVIRONMENT *,IDiskScanNotify *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,__POSITION *,ulong)
0x1800156cc  mov     rbx, rax
0x1800156cf  jmp     short loc_1800156D3
0x1800156d1  xor     ebx, ebx
0x1800156d3  mov     [rsp+0B8h+var_70], rbx
0x1800156d8  mov     [rsp+0B8h+arg_0], rbx
0x1800156e0  lea     r8, [rsp+0B8h+arg_0]
0x1800156e8  mov     rdx, rdi
0x1800156eb  call    ?SetAt@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAXPEAU__POSITION@@AEAV?$CAutoPtr@VCDiskScanner@@@2@@Z; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::SetAt(__POSITION *,ATL::CAutoPtr<CDiskScanner> &)
0x1800156f0  nop
0x1800156f1  lea     rcx, [rsp+0B8h+arg_0]
0x1800156f9  call    ?Free@?$CAutoPtr@VCDiskScanner@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CDiskScanner>::Free(void)
0x1800156fe  lea     r8, [rsp+0B8h+var_70]
0x180015703  mov     rdx, rsi
0x180015706  mov     rcx, r12
0x180015709  call    ?Add@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAHAEBKAEBQEAVCDiskScanner@@@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::Add(ulong const &,CDiskScanner * const &)
0x18001570e  test    eax, eax
0x180015710  jnz     short loc_180015750
0x180015712  mov     rcx, cs:WPP_GLOBAL_Control
0x180015719  lea     rax, WPP_GLOBAL_Control
0x180015720  cmp     rcx, rax
0x180015723  jz      short loc_180015746
0x180015725  test    byte ptr [rcx+1Ch], 1
0x180015729  jz      short loc_180015746
0x18001572b  cmp     byte ptr [rcx+19h], 2
0x18001572f  jb      short loc_180015746
0x180015731  mov     edx, 34h ; '4'
0x180015736  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x18001573d  mov     rcx, [rcx+10h]
0x180015741  call    WPP_SF_
0x180015746  mov     ecx, 8007000Eh; int
0x18001574b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015750  mov     [rsp+0B8h+arg_10], 0
0x18001575c  lea     rcx, [rsp+0B8h+arg_10]
0x180015764  call    CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4______CAutoTearDown__lambda_2c7b2c2616f7334e21186754b7651ef4___
0x180015769  nop
0x18001576a  mov     [r15], rbx
0x18001576d  mov     [rsp+0B8h+var_58], 0
0x180015775  lea     rcx, [rsp+0B8h+arg_40]; this
0x18001577d  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180015782  nop
0x180015783  lea     rcx, [rsp+0B8h+var_60]; this
0x180015788  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001578d  xor     eax, eax
0x18001578f  jmp     short loc_1800157CE
0x180015791  mov     ebx, 8007000Eh
0x180015796  lea     rcx, [rsp+0B8h+arg_40]; this
0x18001579e  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x1800157a3  nop
0x1800157a4  lea     rcx, [rsp+0B8h+var_60]; this
0x1800157a9  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800157ae  mov     eax, ebx
0x1800157b0  jmp     short loc_1800157CE
0x1800157b2  lea     rcx, [rsp+0B8h+arg_40]; this
0x1800157ba  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x1800157bf  nop
0x1800157c0  lea     rcx, [rsp+0B8h+var_60]; this
0x1800157c5  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800157ca  mov     eax, [rsp+0B8h+var_78]
0x1800157ce  add     rsp, 80h
0x1800157d5  pop     r15
0x1800157d7  pop     r14
0x1800157d9  pop     r13
0x1800157db  pop     r12
0x1800157dd  pop     rdi
0x1800157de  pop     rsi
0x1800157df  pop     rbx
0x1800157e0  retn
```
