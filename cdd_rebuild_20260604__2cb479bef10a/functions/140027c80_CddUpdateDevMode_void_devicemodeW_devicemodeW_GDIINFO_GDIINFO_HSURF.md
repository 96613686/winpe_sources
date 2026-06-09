# CddUpdateDevMode(void *,_devicemodeW *,_devicemodeW *,_GDIINFO *,_GDIINFO *,HSURF__ * *)

- ea: `0x140027c80`
- end: `0x140028496`
- name: `?CddUpdateDevMode@@YAHPEAXPEAU_devicemodeW@@1PEAU_GDIINFO@@2PEAPEAUHSURF__@@@Z`
- size: `2070`
- prototype: `__int64 __usercall@<rax>(struct CDDPDEV *@<rcx>, struct _devicemodeW *@<rdx>, struct _devicemodeW *@<r8>, struct _GDIINFO *@<r9>, struct _GDIINFO *, HSURF *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140002470`
- `0x14000fbb4`
- `0x140012b60`
- `0x140018e30`
- `0x14001cc58`
- `0x140020c58`
- `0x140027c80`
- `0x14002849c`
- `0x1400289fc`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140028299`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400282b5`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140028299`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400282b5`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14002841c`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14002841c`
- `watchdog!WdLogSingleEntry1` at `0x140027d26`
- `watchdog!WdLogSingleEntry1` at `0x140027e40`
- `watchdog!WdLogSingleEntry1` at `0x140027f3d`
- `watchdog!WdLogSingleEntry1` at `0x14002804a`
- `watchdog!WdLogSingleEntry1` at `0x1400280b4`
- `watchdog!WdLogSingleEntry1` at `0x140028118`
- `watchdog!WdLogSingleEntry1` at `0x14002818f`
- `watchdog!WdLogSingleEntry1` at `0x140028206`
- `watchdog!WdLogSingleEntry1` at `0x140028243`
- `watchdog!WdLogSingleEntry1` at `0x140028405`
- `watchdog!WdLogSingleEntry1` at `0x140027d26`
- `watchdog!WdLogSingleEntry1` at `0x140027e40`
- `watchdog!WdLogSingleEntry1` at `0x140027f3d`
- `watchdog!WdLogSingleEntry1` at `0x14002804a`
- `watchdog!WdLogSingleEntry1` at `0x1400280b4`
- `watchdog!WdLogSingleEntry1` at `0x140028118`
- `watchdog!WdLogSingleEntry1` at `0x14002818f`
- `watchdog!WdLogSingleEntry1` at `0x140028206`
- `watchdog!WdLogSingleEntry1` at `0x140028243`
- `watchdog!WdLogSingleEntry1` at `0x140028405`
- `watchdog!WdLogNewEntry5_WdError` at `0x140027d3d`
- `watchdog!WdLogNewEntry5_WdError` at `0x140027e57`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028061`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002812f`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400281a6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002825a`
- `watchdog!WdLogNewEntry5_WdError` at `0x140027d3d`
- `watchdog!WdLogNewEntry5_WdError` at `0x140027e57`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028061`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002812f`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400281a6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002825a`
- `watchdog!WdLogSingleEntry0` at `0x140028394`
- `watchdog!WdLogSingleEntry0` at `0x140028394`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400283ab`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400283ab`
- `WIN32K!W32GetSessionState` at `0x140028378`
- `WIN32K!W32GetSessionState` at `0x140028378`
- `WIN32K!EngAssociateSurface` at `0x1400281ee`
- `WIN32K!EngAssociateSurface` at `0x1400281ee`
- `WIN32K!EngLockSurface` at `0x140028170`
- `WIN32K!EngLockSurface` at `0x140028170`
- `WIN32K!EngCreateBitmap` at `0x1400280f9`
- `WIN32K!EngCreateBitmap` at `0x1400280f9`
- `WIN32K!EngCreateDeviceSurface` at `0x14002802c`
- `WIN32K!EngCreateDeviceSurface` at `0x14002802c`
- `WIN32K!EngDeleteSurface` at `0x1400282ec`
- `WIN32K!EngDeleteSurface` at `0x1400282ec`
- `WIN32K!EngUnlockSurface` at `0x1400282d5`
- `WIN32K!EngUnlockSurface` at `0x1400282d5`

## pseudocode

```c
__int64 __fastcall CddUpdateDevMode(
        struct CDDPDEV *a1,
        struct _devicemodeW *a2,
        struct _devicemodeW *a3,
        struct _GDIINFO *a4,
        struct _GDIINFO *a5,
        HSURF *a6)
{
  _QWORD *v10; // rax
  int v11; // ebx
  _QWORD *v12; // rax
  ULONG ulLogPixelsX; // edx
  ULONG v14; // ecx
  ULONG v15; // edx
  ULONG ulHorzSize; // ecx
  ULONG ulVertSize; // edx
  LONG dmPelsWidth; // ebx
  HSURF DeviceSurface; // rax
  HSURF v20; // r15
  int v21; // ebx
  _QWORD *v22; // rax
  LONG v23; // r14d
  HBITMAP Bitmap; // rax
  HSURF v25; // rbx
  _QWORD *v26; // rax
  SIZEL v27; // r13
  int v28; // ebx
  _QWORD *v29; // rax
  int v30; // r8d
  _QWORD *v31; // rax
  bool v32; // zf
  __int64 v33; // rdx
  SURFOBJ *v34; // rcx
  HSURF *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  struct _CDD_DEVMODE *pvBits; // [rsp+20h] [rbp-E0h]
  unsigned int v41; // [rsp+28h] [rbp-D8h]
  unsigned int v42; // [rsp+28h] [rbp-D8h]
  SIZEL sizl; // [rsp+30h] [rbp-D0h] BYREF
  HSURF v44; // [rsp+38h] [rbp-C8h] BYREF
  HBITMAP v45; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  HSURF *v50; // [rsp+68h] [rbp-98h]
  _OWORD v51[15]; // [rsp+80h] [rbp-80h] BYREF
  int v52; // [rsp+170h] [rbp+70h]
  _BYTE v53[320]; // [rsp+180h] [rbp+80h] BYREF

  v50 = a6;
  memset(v53, 0, 0x138u);
  v49 = 0;
  v46 = 0;
  *a6 = 0;
  if ( (*((int (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))a1 + 75))(
         *((_QWORD *)a1 + 1),
         *(_QWORD *)a1,
         &v46,
         &v49) < 0 )
  {
    WdLogSingleEntry1(2, 0);
    WdLogGlobalForLineNumber = 6129;
    v10 = (_QWORD *)WdLogNewEntry5_WdError();
    v10[3] = gCddImageInfo;
    v10[4] = (unsigned int)dword_14003E570;
    v10[5] = 215857758;
    WdLogGlobalForLineNumber = 6129;
    return 0;
  }
  v51[0] = *(_OWORD *)((char *)a1 + 804);
  v51[1] = *(_OWORD *)((char *)a1 + 820);
  v51[2] = *(_OWORD *)((char *)a1 + 836);
  v51[3] = *(_OWORD *)((char *)a1 + 852);
  v51[4] = *(_OWORD *)((char *)a1 + 868);
  v51[5] = *(_OWORD *)((char *)a1 + 884);
  v51[6] = *(_OWORD *)((char *)a1 + 900);
  v51[7] = *(_OWORD *)((char *)a1 + 916);
  v51[8] = *(_OWORD *)((char *)a1 + 932);
  v51[9] = *(_OWORD *)((char *)a1 + 948);
  v51[10] = *(_OWORD *)((char *)a1 + 964);
  v51[11] = *(_OWORD *)((char *)a1 + 980);
  v51[12] = *(_OWORD *)((char *)a1 + 996);
  v51[13] = *(_OWORD *)((char *)a1 + 1012);
  v51[14] = *(_OWORD *)((char *)a1 + 1028);
  v52 = *((_DWORD *)a1 + 261);
  if ( (int)InitPDEV(
              a1,
              (struct _CDD_DEVMODE *)a3,
              a5,
              (struct tagDEVINFO *)v53,
              (struct CDDPDEV *)((char *)a1 + 728),
              v41) < 0 )
  {
    WdLogSingleEntry1(2, 1);
    v11 = 6147;
    WdLogGlobalForLineNumber = 6147;
    v12 = (_QWORD *)WdLogNewEntry5_WdError();
    v12[3] = gCddImageInfo;
    v12[4] = (unsigned int)dword_14003E570;
LABEL_68:
    v12[5] = 215857758;
    WdLogGlobalForLineNumber = v11;
    goto LABEL_69;
  }
  ulLogPixelsX = a5->ulLogPixelsX;
  if ( (((a2->dmDisplayOrientation - 1) & 0xFFFFFFFD) == 0) == (((a3->dmDisplayOrientation - 1) & 0xFFFFFFFD) == 0) )
  {
    if ( !ulLogPixelsX )
      a5->ulLogPixelsX = a4->ulLogPixelsX;
    if ( !a5->ulLogPixelsY )
      a5->ulLogPixelsY = a4->ulLogPixelsY;
    ulHorzSize = a5->ulHorzSize;
    if ( !ulHorzSize )
    {
      ulHorzSize = a4->ulHorzSize;
      a5->ulHorzSize = ulHorzSize;
    }
    ulVertSize = a5->ulVertSize;
    if ( !ulVertSize )
    {
      ulVertSize = a4->ulVertSize;
      a5->ulVertSize = ulVertSize;
    }
    if ( a5->ulHorzRes != a4->ulHorzRes
      || a5->ulVertRes != a4->ulVertRes
      || ulHorzSize != a4->ulHorzSize
      || ulVertSize != a4->ulVertSize
      || a5->ulAspectX != a4->ulAspectX
      || a5->ulAspectY != a4->ulAspectY
      || a5->ulPanningHorzRes != a4->ulPanningHorzRes
      || a5->ulPanningVertRes != a4->ulPanningVertRes
      || a5->ulLogPixelsX != a4->ulLogPixelsX
      || a5->ulLogPixelsY != a4->ulLogPixelsY )
    {
      WdLogSingleEntry1(3, 2);
      v11 = 6221;
      goto LABEL_67;
    }
  }
  else
  {
    if ( !ulLogPixelsX )
      a5->ulLogPixelsX = a4->ulLogPixelsY;
    if ( !a5->ulLogPixelsY )
      a5->ulLogPixelsY = a4->ulLogPixelsX;
    v14 = a5->ulHorzSize;
    if ( !v14 )
    {
      v14 = a4->ulVertSize;
      a5->ulHorzSize = v14;
    }
    v15 = a5->ulVertSize;
    if ( !v15 )
    {
      v15 = a4->ulHorzSize;
      a5->ulVertSize = v15;
    }
    if ( a5->ulHorzRes != a4->ulVertRes
      || a5->ulVertRes != a4->ulHorzRes
      || v14 != a4->ulVertSize
      || v15 != a4->ulHorzSize
      || a5->ulAspectX != a4->ulAspectY
      || a5->ulAspectY != a4->ulAspectX
      || a5->ulPanningHorzRes != a4->ulPanningVertRes
      || a5->ulPanningVertRes != a4->ulPanningHorzRes
      || a5->ulLogPixelsX != a4->ulLogPixelsY
      || a5->ulLogPixelsY != a4->ulLogPixelsX )
    {
      WdLogSingleEntry1(3, 1);
      v11 = 6188;
LABEL_67:
      WdLogGlobalForLineNumber = v11;
      v12 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v12[3] = gCddImageInfo;
      v12[4] = (unsigned int)dword_14003E570;
      goto LABEL_68;
    }
  }
  InitDisplayMode(a1);
  dmPelsWidth = a3->dmPelsWidth;
  sizl.cy = a3->dmPelsHeight;
  sizl.cx = dmPelsWidth;
  DeviceSurface = EngCreateDeviceSurface(0, sizl, 6u);
  v44 = DeviceSurface;
  v20 = DeviceSurface;
  if ( !DeviceSurface )
  {
    WdLogSingleEntry1(2, 2);
    v21 = 6240;
LABEL_45:
    WdLogGlobalForLineNumber = v21;
    v22 = (_QWORD *)WdLogNewEntry5_WdError();
    v22[3] = gCddImageInfo;
    v22[4] = (unsigned int)dword_14003E570;
    v22[5] = 215857758;
    WdLogGlobalForLineNumber = v21;
LABEL_46:
    wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(&v44);
LABEL_69:
    InitPDEV(a1, (struct _CDD_DEVMODE *)v51, a5, (struct tagDEVINFO *)v53, pvBits, v42);
    InitDisplayMode(a1);
    return 0;
  }
  if ( !CddModifySurface(a1, DeviceSurface) )
  {
    WdLogSingleEntry1(2, 3);
    v21 = 6245;
    goto LABEL_45;
  }
  v23 = (dmPelsWidth * (*((_DWORD *)a1 + 279) >> 3) + 3) & 0xFFFFFFFC;
  Bitmap = EngCreateBitmap(sizl, v23, 6u, 1u, (PVOID)0xDEADBEEFLL);
  v45 = Bitmap;
  v25 = (HSURF)Bitmap;
  if ( !Bitmap )
  {
    WdLogSingleEntry1(2, 4);
    WdLogGlobalForLineNumber = 6258;
    v26 = (_QWORD *)WdLogNewEntry5_WdError();
    v26[3] = gCddImageInfo;
    v26[4] = (unsigned int)dword_14003E570;
    v26[5] = 215857758;
    WdLogGlobalForLineNumber = 6258;
LABEL_51:
    wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(&v45);
    goto LABEL_46;
  }
  sizl = (SIZEL)EngLockSurface((HSURF)Bitmap);
  v27 = sizl;
  if ( !*(_QWORD *)&sizl )
  {
    WdLogSingleEntry1(2, 5);
    v28 = 6266;
LABEL_54:
    WdLogGlobalForLineNumber = v28;
    v29 = (_QWORD *)WdLogNewEntry5_WdError();
    v29[3] = gCddImageInfo;
    v29[4] = (unsigned int)dword_14003E570;
    v29[5] = 215857758;
    WdLogGlobalForLineNumber = v28;
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<_SURFOBJ *,void (_SURFOBJ *),&void EngUnlockSurface(_SURFOBJ *),wistd::integral_constant<unsigned __int64,0>,_SURFOBJ *,_SURFOBJ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SURFOBJ *,void (_SURFOBJ *),&void EngUnlockSurface(_SURFOBJ *),wistd::integral_constant<unsigned __int64,0>,_SURFOBJ *,_SURFOBJ *,0,std::nullptr_t>>(&sizl);
    goto LABEL_51;
  }
  if ( !EngAssociateSurface(v25, *((HDEV *)a1 + 1), 0) )
  {
    WdLogSingleEntry1(2, 6);
    v28 = 6274;
    goto LABEL_54;
  }
  CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v47, *((struct CDDMUTEX **)a1 + 686), v30);
  if ( (int)CddIssueCommand(a1, 19) < 0 )
  {
    WdLogSingleEntry1(2, 7);
    WdLogGlobalForLineNumber = 6286;
    v31 = (_QWORD *)WdLogNewEntry5_WdError();
    v32 = v48 == 0;
    v31[3] = gCddImageInfo;
    v31[4] = (unsigned int)dword_14003E570;
    v31[5] = 215857758;
    WdLogGlobalForLineNumber = 6286;
    if ( !v32 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v47);
    goto LABEL_55;
  }
  if ( v48 )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v47);
  CddFreeShadowSysMem(a1);
  v34 = (SURFOBJ *)*((_QWORD *)a1 + 349);
  if ( v34 )
  {
    EngUnlockSurface(v34);
    EngDeleteSurface(*(HSURF *)(*((_QWORD *)a1 + 349) + 8LL));
  }
  v35 = v50;
  *((_QWORD *)a1 + 2) = v20;
  v44 = 0;
  sizl = 0;
  *v35 = v20;
  *((SIZEL *)a1 + 349) = v27;
  *(_QWORD *)(*(_QWORD *)&v27 + 48LL) = *((_QWORD *)a1 + 319);
  v36 = *((_QWORD *)a1 + 349);
  v45 = 0;
  *(_QWORD *)(v36 + 56) = *(_QWORD *)(v36 + 48);
  LODWORD(v36) = *((_DWORD *)a1 + 200);
  *((_QWORD *)a1 + 320) = (unsigned int)(v23 * v36);
  *((_DWORD *)a1 + 274) = v23;
  LODWORD(v35) = *((_DWORD *)a1 + 199);
  *((_DWORD *)a1 + 1822) = (_DWORD)v35;
  *((_DWORD *)a1 + 1824) = (_DWORD)v35;
  *((_DWORD *)a1 + 1825) = v36;
  v37 = (unsigned int)v36 >> 3;
  *((_DWORD *)a1 + 894) = (unsigned int)v35 >> 3;
  *((_DWORD *)a1 + 895) = v37;
  *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v37, v33) + 72) + 3384LL) = 1;
  WdLogSingleEntry0(4);
  WdLogGlobalForLineNumber = 6337;
  v38 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v38[3] = gCddImageInfo;
  v38[4] = (unsigned int)dword_14003E570;
  v38[5] = 215857758;
  WdLogGlobalForLineNumber = 6337;
  wil::details::unique_storage<wil::details::resource_policy<_SURFOBJ *,void (_SURFOBJ *),&void EngUnlockSurface(_SURFOBJ *),wistd::integral_constant<unsigned __int64,0>,_SURFOBJ *,_SURFOBJ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SURFOBJ *,void (_SURFOBJ *),&void EngUnlockSurface(_SURFOBJ *),wistd::integral_constant<unsigned __int64,0>,_SURFOBJ *,_SURFOBJ *,0,std::nullptr_t>>(&sizl);
  wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(&v45);
  wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(&v44);
  return 1;
}

```

## disassembly

```asm
0x140027c80  mov     [rsp-8+arg_8], rbx
0x140027c85  push    rbp
0x140027c86  push    rsi
0x140027c87  push    rdi
0x140027c88  push    r12
0x140027c8a  push    r13
0x140027c8c  push    r14
0x140027c8e  push    r15
0x140027c90  lea     rbp, [rsp-1D0h]
0x140027c98  sub     rsp, 2D0h
0x140027c9f  mov     rax, cs:__security_cookie
0x140027ca6  xor     rax, rsp
0x140027ca9  mov     [rbp+200h+var_40], rax
0x140027cb0  mov     r12, [rbp+200h+arg_28]
0x140027cb7  mov     r15, r8
0x140027cba  mov     rdi, [rbp+200h+arg_20]
0x140027cc1  mov     r14, rdx
0x140027cc4  mov     rsi, rcx
0x140027cc7  mov     [rsp+300h+var_298], r12
0x140027ccc  xor     edx, edx; Val
0x140027cce  lea     rcx, [rbp+200h+var_180]; void *
0x140027cd5  mov     r8d, 138h; Size
0x140027cdb  mov     rbx, r9
0x140027cde  call    memset
0x140027ce3  xor     r13d, r13d
0x140027ce6  lea     rcx, [rsi+2D8h]
0x140027ced  mov     [rsp+300h+var_2A0], r13
0x140027cf2  lea     r9, [rsp+300h+var_2A0]
0x140027cf7  mov     [rsp+300h+var_2B8], r13d
0x140027cfc  lea     r8, [rsp+300h+var_2B8]
0x140027d01  mov     [r12], r13
0x140027d05  mov     rax, [rsi+258h]
0x140027d0c  mov     rdx, [rsi]
0x140027d0f  mov     [rsp+300h+pvBits], rcx; struct _CDD_DEVMODE *
0x140027d14  mov     rcx, [rsi+8]
0x140027d18  call    _guard_dispatch_icall
0x140027d1d  test    eax, eax
0x140027d1f  jns     short loc_140027D71
0x140027d21  xor     edx, edx
0x140027d23  lea     ecx, [rdx+2]
0x140027d26  call    cs:__imp_WdLogSingleEntry1
0x140027d2d  nop     dword ptr [rax+rax+00h]
0x140027d32  mov     ebx, 17F1h
0x140027d37  mov     cs:WdLogGlobalForLineNumber, ebx
0x140027d3d  call    cs:__imp_WdLogNewEntry5_WdError
0x140027d44  nop     dword ptr [rax+rax+00h]
0x140027d49  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140027d50  mov     [rax+18h], rcx
0x140027d54  mov     ecx, cs:dword_14003E570
0x140027d5a  mov     [rax+20h], rcx
0x140027d5e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140027d66  mov     cs:WdLogGlobalForLineNumber, ebx
0x140027d6c  jmp     loc_140028469
0x140027d71  movups  xmm0, xmmword ptr [rsi+324h]
0x140027d78  lea     r9, [rbp+200h+var_180]; struct tagDEVINFO *
0x140027d7f  mov     r8, rdi; struct _GDIINFO *
0x140027d82  mov     rdx, r15; struct _CDD_DEVMODE *
0x140027d85  mov     rcx, rsi; struct CDDPDEV *
0x140027d88  movups  [rbp+200h+var_280], xmm0
0x140027d8c  movups  xmm1, xmmword ptr [rsi+334h]
0x140027d93  movups  [rbp+200h+var_270], xmm1
0x140027d97  movups  xmm0, xmmword ptr [rsi+344h]
0x140027d9e  movups  [rbp+200h+var_260], xmm0
0x140027da2  movups  xmm1, xmmword ptr [rsi+354h]
0x140027da9  movups  [rbp+200h+var_250], xmm1
0x140027dad  movups  xmm0, xmmword ptr [rsi+364h]
0x140027db4  movups  [rbp+200h+var_240], xmm0
0x140027db8  movups  xmm1, xmmword ptr [rsi+374h]
0x140027dbf  movups  [rbp+200h+var_230], xmm1
0x140027dc3  movups  xmm0, xmmword ptr [rsi+384h]
0x140027dca  movups  [rbp+200h+var_220], xmm0
0x140027dce  movups  xmm1, xmmword ptr [rsi+394h]
0x140027dd5  movups  [rbp+200h+var_210], xmm1
0x140027dd9  movups  xmm0, xmmword ptr [rsi+3A4h]
0x140027de0  movups  [rbp+200h+var_200], xmm0
0x140027de4  movups  xmm1, xmmword ptr [rsi+3B4h]
0x140027deb  movups  [rbp+200h+var_1F0], xmm1
0x140027def  movups  xmm0, xmmword ptr [rsi+3C4h]
0x140027df6  movups  [rbp+200h+var_1E0], xmm0
0x140027dfa  movups  xmm1, xmmword ptr [rsi+3D4h]
0x140027e01  movups  [rbp+200h+var_1D0], xmm1
0x140027e05  movups  xmm0, xmmword ptr [rsi+3E4h]
0x140027e0c  movups  [rbp+200h+var_1C0], xmm0
0x140027e10  movups  xmm1, xmmword ptr [rsi+3F4h]
0x140027e17  movups  [rbp+200h+var_1B0], xmm1
0x140027e1b  movups  xmm0, xmmword ptr [rsi+404h]
0x140027e22  movups  [rbp+200h+var_1A0], xmm0
0x140027e26  mov     eax, [rsi+414h]
0x140027e2c  mov     [rbp+200h+var_190], eax
0x140027e2f  call    ?InitPDEV@@YAJPEAUCDDPDEV@@PEAU_CDD_DEVMODE@@PEAU_GDIINFO@@PEAUtagDEVINFO@@1I@Z; InitPDEV(CDDPDEV *,_CDD_DEVMODE *,_GDIINFO *,tagDEVINFO *,_CDD_DEVMODE *,uint)
0x140027e34  test    eax, eax
0x140027e36  jns     short loc_140027E7D
0x140027e38  mov     edx, 1
0x140027e3d  lea     ecx, [rdx+1]
0x140027e40  call    cs:__imp_WdLogSingleEntry1
0x140027e47  nop     dword ptr [rax+rax+00h]
0x140027e4c  mov     ebx, 1803h
0x140027e51  mov     cs:WdLogGlobalForLineNumber, ebx
0x140027e57  call    cs:__imp_WdLogNewEntry5_WdError
0x140027e5e  nop     dword ptr [rax+rax+00h]
0x140027e63  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140027e6a  mov     [rax+18h], rdx
0x140027e6e  mov     edx, cs:dword_14003E570
0x140027e74  mov     [rax+20h], rdx
0x140027e78  jmp     loc_14002843D
0x140027e7d  mov     eax, [r14+54h]
0x140027e81  mov     edx, 0FFFFFFFDh
0x140027e86  mov     r12d, 1
0x140027e8c  sub     eax, r12d
0x140027e8f  test    edx, eax
0x140027e91  mov     eax, [r15+54h]
0x140027e95  setz    cl
0x140027e98  sub     eax, r12d
0x140027e9b  test    edx, eax
0x140027e9d  mov     edx, [rdi+28h]
0x140027ea0  setz    al
0x140027ea3  cmp     cl, al
0x140027ea5  jz      loc_140027F53
0x140027eab  test    edx, edx
0x140027ead  jnz     short loc_140027EB5
0x140027eaf  mov     eax, [rbx+2Ch]
0x140027eb2  mov     [rdi+28h], eax
0x140027eb5  cmp     [rdi+2Ch], r13d
0x140027eb9  jnz     short loc_140027EC1
0x140027ebb  mov     eax, [rbx+28h]
0x140027ebe  mov     [rdi+2Ch], eax
0x140027ec1  mov     ecx, [rdi+8]
0x140027ec4  test    ecx, ecx
0x140027ec6  jnz     short loc_140027ECE
0x140027ec8  mov     ecx, [rbx+0Ch]
0x140027ecb  mov     [rdi+8], ecx
0x140027ece  mov     edx, [rdi+0Ch]
0x140027ed1  test    edx, edx
0x140027ed3  jnz     short loc_140027EDB
0x140027ed5  mov     edx, [rbx+8]
0x140027ed8  mov     [rdi+0Ch], edx
0x140027edb  mov     eax, [rbx+14h]
0x140027ede  cmp     [rdi+10h], eax
0x140027ee1  jnz     short loc_140027F35
0x140027ee3  mov     eax, [rbx+10h]
0x140027ee6  cmp     [rdi+14h], eax
0x140027ee9  jnz     short loc_140027F35
0x140027eeb  cmp     ecx, [rbx+0Ch]
0x140027eee  jnz     short loc_140027F35
0x140027ef0  cmp     edx, [rbx+8]
0x140027ef3  jnz     short loc_140027F35
0x140027ef5  mov     eax, [rbx+44h]
0x140027ef8  cmp     [rdi+40h], eax
0x140027efb  jnz     short loc_140027F35
0x140027efd  mov     eax, [rbx+40h]
0x140027f00  cmp     [rdi+44h], eax
0x140027f03  jnz     short loc_140027F35
0x140027f05  mov     eax, [rbx+104h]
0x140027f0b  cmp     [rdi+100h], eax
0x140027f11  jnz     short loc_140027F35
0x140027f13  mov     eax, [rbx+100h]
0x140027f19  cmp     [rdi+104h], eax
0x140027f1f  jnz     short loc_140027F35
0x140027f21  mov     eax, [rbx+2Ch]
0x140027f24  cmp     [rdi+28h], eax
0x140027f27  jnz     short loc_140027F35
0x140027f29  mov     eax, [rbx+28h]
0x140027f2c  cmp     [rdi+2Ch], eax
0x140027f2f  jz      loc_140028001
0x140027f35  mov     rdx, r12
0x140027f38  mov     ecx, 3
0x140027f3d  call    cs:__imp_WdLogSingleEntry1
0x140027f44  nop     dword ptr [rax+rax+00h]
0x140027f49  mov     ebx, 182Ch
0x140027f4e  jmp     loc_140028416
0x140027f53  test    edx, edx
0x140027f55  jnz     short loc_140027F5D
0x140027f57  mov     eax, [rbx+28h]
0x140027f5a  mov     [rdi+28h], eax
0x140027f5d  cmp     [rdi+2Ch], r13d
0x140027f61  jnz     short loc_140027F69
0x140027f63  mov     eax, [rbx+2Ch]
0x140027f66  mov     [rdi+2Ch], eax
0x140027f69  mov     ecx, [rdi+8]
0x140027f6c  test    ecx, ecx
0x140027f6e  jnz     short loc_140027F76
0x140027f70  mov     ecx, [rbx+8]
0x140027f73  mov     [rdi+8], ecx
0x140027f76  mov     edx, [rdi+0Ch]
0x140027f79  test    edx, edx
0x140027f7b  jnz     short loc_140027F83
0x140027f7d  mov     edx, [rbx+0Ch]
0x140027f80  mov     [rdi+0Ch], edx
0x140027f83  mov     eax, [rbx+10h]
0x140027f86  cmp     [rdi+10h], eax
0x140027f89  jnz     loc_1400283FD
0x140027f8f  mov     eax, [rbx+14h]
0x140027f92  cmp     [rdi+14h], eax
0x140027f95  jnz     loc_1400283FD
0x140027f9b  cmp     ecx, [rbx+8]
0x140027f9e  jnz     loc_1400283FD
0x140027fa4  cmp     edx, [rbx+0Ch]
0x140027fa7  jnz     loc_1400283FD
0x140027fad  mov     eax, [rbx+40h]
0x140027fb0  cmp     [rdi+40h], eax
0x140027fb3  jnz     loc_1400283FD
0x140027fb9  mov     eax, [rbx+44h]
0x140027fbc  cmp     [rdi+44h], eax
0x140027fbf  jnz     loc_1400283FD
0x140027fc5  mov     eax, [rbx+100h]
0x140027fcb  cmp     [rdi+100h], eax
0x140027fd1  jnz     loc_1400283FD
0x140027fd7  mov     eax, [rbx+104h]
0x140027fdd  cmp     [rdi+104h], eax
0x140027fe3  jnz     loc_1400283FD
0x140027fe9  mov     eax, [rbx+28h]
0x140027fec  cmp     [rdi+28h], eax
0x140027fef  jnz     loc_1400283FD
0x140027ff5  mov     eax, [rbx+2Ch]
0x140027ff8  cmp     [rdi+2Ch], eax
0x140027ffb  jnz     loc_1400283FD
0x140028001  mov     rcx, rsi; struct CDDPDEV *
0x140028004  call    ?InitDisplayMode@@YAXPEAUCDDPDEV@@@Z; InitDisplayMode(CDDPDEV *)
0x140028009  mov     eax, [r15+0B0h]
0x140028010  mov     r8d, 6; iFormatCompat
0x140028016  mov     ebx, [r15+0ACh]
0x14002801d  xor     ecx, ecx; dhsurf
0x14002801f  mov     [rsp+300h+sizl.cy], eax
0x140028023  mov     [rsp+300h+sizl.cx], ebx
0x140028027  mov     rdx, qword ptr [rsp+300h+sizl.cx]; sizl
0x14002802c  call    cs:__imp_EngCreateDeviceSurface
0x140028033  nop     dword ptr [rax+rax+00h]
0x140028038  mov     [rsp+300h+var_2C8], rax
0x14002803d  mov     r15, rax
0x140028040  test    rax, rax
0x140028043  jnz     short loc_14002809F
0x140028045  lea     edx, [rax+2]
0x140028048  mov     ecx, edx
0x14002804a  call    cs:__imp_WdLogSingleEntry1
0x140028051  nop     dword ptr [rax+rax+00h]
0x140028056  mov     ebx, 1860h
0x14002805b  mov     cs:WdLogGlobalForLineNumber, ebx
0x140028061  call    cs:__imp_WdLogNewEntry5_WdError
0x140028068  nop     dword ptr [rax+rax+00h]
0x14002806d  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028074  mov     [rax+18h], rcx
0x140028078  mov     ecx, cs:dword_14003E570
0x14002807e  mov     [rax+20h], rcx
0x140028082  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002808a  mov     cs:WdLogGlobalForLineNumber, ebx
0x140028090  lea     rcx, [rsp+300h+var_2C8]
0x140028095  call    ??1?$unique_storage@U?$resource_policy@PEAUHSURF__@@$$A6AHPEAU1@@Z$1?EngDeleteSurface@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(void)
0x14002809a  jmp     loc_14002844B
0x14002809f  mov     rdx, r15; HSURF
0x1400280a2  mov     rcx, rsi; struct CDDPDEV *
0x1400280a5  call    ?CddModifySurface@@YAHPEAUCDDPDEV@@PEAUHSURF__@@@Z; CddModifySurface(CDDPDEV *,HSURF__ *)
0x1400280aa  test    eax, eax
0x1400280ac  jnz     short loc_1400280C7
0x1400280ae  lea     edx, [rax+3]
0x1400280b1  lea     ecx, [rax+2]
0x1400280b4  call    cs:__imp_WdLogSingleEntry1
0x1400280bb  nop     dword ptr [rax+rax+00h]
0x1400280c0  mov     ebx, 1865h
0x1400280c5  jmp     short loc_14002805B
0x1400280c7  mov     r14d, [rsi+45Ch]
0x1400280ce  mov     eax, 0DEADBEEFh
0x1400280d3  mov     rcx, qword ptr [rsp+300h+sizl.cx]; sizl
0x1400280d8  mov     r9d, r12d; fl
0x1400280db  shr     r14d, 3
0x1400280df  mov     r8d, 6; iFormat
0x1400280e5  imul    r14d, ebx
0x1400280e9  mov     [rsp+300h+pvBits], rax; pvBits
0x1400280ee  add     r14d, 3
0x1400280f2  and     r14d, 0FFFFFFFCh
0x1400280f6  mov     edx, r14d; lWidth
0x1400280f9  call    cs:__imp_EngCreateBitmap
0x140028100  nop     dword ptr [rax+rax+00h]
0x140028105  mov     [rsp+300h+var_2C0], rax
0x14002810a  mov     rbx, rax
0x14002810d  test    rax, rax
0x140028110  jnz     short loc_14002816D
0x140028112  lea     edx, [rax+4]
0x140028115  lea     ecx, [rax+2]
0x140028118  call    cs:__imp_WdLogSingleEntry1
0x14002811f  nop     dword ptr [rax+rax+00h]
0x140028124  mov     ebx, 1872h
0x140028129  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002812f  call    cs:__imp_WdLogNewEntry5_WdError
0x140028136  nop     dword ptr [rax+rax+00h]
0x14002813b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028142  mov     [rax+18h], rcx
0x140028146  mov     ecx, cs:dword_14003E570
0x14002814c  mov     [rax+20h], rcx
0x140028150  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140028158  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002815e  lea     rcx, [rsp+300h+var_2C0]
0x140028163  call    ??1?$unique_storage@U?$resource_policy@PEAUHSURF__@@$$A6AHPEAU1@@Z$1?EngDeleteSurface@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(void)
0x140028168  jmp     loc_140028090
0x14002816d  mov     rcx, rbx; hsurf
0x140028170  call    cs:__imp_EngLockSurface
0x140028177  nop     dword ptr [rax+rax+00h]
0x14002817c  mov     qword ptr [rsp+300h+sizl.cx], rax
0x140028181  mov     r13, rax
0x140028184  test    rax, rax
0x140028187  jnz     short loc_1400281E4
  ... truncated ...
```
