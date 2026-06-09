# CDXGIOutput::GetDisplaySurfaceDataCore(DXGI_GETDISPLAYSURFACEDATA_VERSION,uint,IDXGIResource *)

- ea: `0x180072434`
- end: `0x180072d38`
- name: `?GetDisplaySurfaceDataCore@CDXGIOutput@@AEAAJW4DXGI_GETDISPLAYSURFACEDATA_VERSION@@IPEAUIDXGIResource@@@Z`
- size: `2308`
- prototype: `int __high(enum DXGI_GETDISPLAYSURFACEDATA_VERSION, unsigned int, struct IDXGIResource *)`
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180086ec0`
- `0x180086ee0`

## callees

- `0x18000c6b0`
- `0x18000cb1c`
- `0x18000cb70`
- `0x180010d40`
- `0x180014750`
- `0x18001b22c`
- `0x180037850`
- `0x180037e50`
- `0x18003a030`
- `0x1800480b8`
- `0x1800480f0`
- `0x180072434`
- `0x180075fa0`
- `0x180076f20`
- `0x180079e18`
- `0x180084d4c`
- `0x1800853f8`
- `0x180085590`
- `0x18008747c`
- `0x1800875a8`
- `0x180087e20`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x1800728e6`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x1800728e6`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1800729dd`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180072c03`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1800729dd`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180072c03`

## string_xrefs

- `0x180072b53`: `OsThunkDDICreateDCFromMemory`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDXGIOutput::GetDisplaySurfaceDataCore(
        __int64 a1,
        int a2,
        unsigned int a3,
        struct IDXGIDeviceSubObject *a4)
{
  struct IDXGIDeviceSubObject *v4; // r13
  int OwnerDevice; // eax
  int v8; // edi
  struct CSourceBits *v9; // r14
  int v10; // eax
  unsigned int v11; // r8d
  __int64 i; // rdx
  __int64 v13; // rdx
  bool v14; // di
  int v15; // eax
  enum DXGI_MODE_ROTATION v16; // eax
  HDC hdcSrc; // r13
  HDC v18; // r15
  CSourceBitsDIBSection *v19; // rax
  __int64 j; // rax
  unsigned int v21; // eax
  int v22; // eax
  CModule *v23; // rcx
  int v24; // r15d
  BOOL v25; // eax
  bool v28; // [rsp+64h] [rbp-204h]
  unsigned int v29; // [rsp+68h] [rbp-200h] BYREF
  struct IUnknown *v30; // [rsp+70h] [rbp-1F8h] BYREF
  struct IDXGIDeviceSubObject *v31; // [rsp+78h] [rbp-1F0h] BYREF
  struct CSourceBits *v32; // [rsp+80h] [rbp-1E8h]
  HDC hdcDest[2]; // [rsp+88h] [rbp-1E0h] BYREF
  struct ILockOwner *v34; // [rsp+98h] [rbp-1D0h] BYREF
  _QWORD v35[2]; // [rsp+A0h] [rbp-1C8h] BYREF
  struct IUnknown *v36; // [rsp+B0h] [rbp-1B8h] BYREF
  int v37; // [rsp+B8h] [rbp-1B0h]
  int v38; // [rsp+BCh] [rbp-1ACh]
  _BYTE v39[8]; // [rsp+C0h] [rbp-1A8h] BYREF
  __int64 v40; // [rsp+C8h] [rbp-1A0h] BYREF
  char v41; // [rsp+D0h] [rbp-198h]
  _com_error *v42; // [rsp+D8h] [rbp-190h] BYREF
  _BYTE v43[84]; // [rsp+E0h] [rbp-188h] BYREF
  enum DXGI_MODE_ROTATION v44; // [rsp+134h] [rbp-134h]
  struct DXGI_SURFACE_DESC wDest; // [rsp+140h] [rbp-128h] BYREF
  DXGI_SURFACE_DESC v46; // [rsp+158h] [rbp-110h] BYREF
  unsigned int v47; // [rsp+170h] [rbp-F8h] BYREF
  __int128 v48; // [rsp+174h] [rbp-F4h]
  __int128 v49; // [rsp+188h] [rbp-E0h] BYREF
  __int128 v50; // [rsp+198h] [rbp-D0h]
  __int128 v51; // [rsp+1A8h] [rbp-C0h]
  __int64 v52; // [rsp+1B8h] [rbp-B0h]
  WCHAR pwszDriver[32]; // [rsp+1C0h] [rbp-A8h] BYREF
  int xSrc; // [rsp+200h] [rbp-68h]
  int ySrc; // [rsp+204h] [rbp-64h]
  int v56; // [rsp+208h] [rbp-60h]
  int v57; // [rsp+20Ch] [rbp-5Ch]

  v4 = a4;
  v31 = a4;
  v30 = 0;
  v34 = 0;
  OwnerDevice = CDXGIOutput::GetOwnerDevice((CDXGIOutput *)a1, (struct IDXGIDeviceInternal3 **)&v30, &v34);
  v8 = -2005270527;
  if ( OwnerDevice != -2005270527 )
  {
    if ( OwnerDevice < 0 )
    {
      v8 = OwnerDevice;
      goto LABEL_77;
    }
    LockOwnerLock::LockOwnerLock((LockOwnerLock *)v39, v34);
    if ( !v4 )
    {
      DXGI_SDK_MSG(
        *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
        DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_pDestinationIsNULL);
LABEL_76:
      LockOwnerLock::~LockOwnerLock((LockOwnerLock *)v39);
      goto LABEL_77;
    }
    v41 = 0;
    v40 = (a1 + 152) & -(__int64)(a1 != 0);
    CThreadLock<0>::TakeLock(&v40);
    v36 = v30;
    v37 = 1;
    v38 = 1;
    v9 = 0;
    v32 = 0;
    try
    {
      v10 = ((__int64 (*)(void))v30->lpVtbl[8].QueryInterface)();
      DXGIThrowFailure(v10);
      v28 = IsCompatibleWithDevice(v30, v4);
      memset(&wDest, 0, sizeof(wDest));
      v29 = 0;
      LODWORD(hdcDest[0]) = ((__int64 (__fastcall *)(struct IUnknown *, struct IDXGIDeviceSubObject *, struct DXGI_SURFACE_DESC *, unsigned int *))v30->lpVtbl[6].QueryInterface)(
                              v30,
                              v4,
                              &wDest,
                              &v29);
      DXGIThrowFailure((int)hdcDest[0]);
      if ( a2 <= 0 )
        v29 = 1;
      if ( wDest.Format > DXGI_FORMAT_B5G5R5A1_UNORM )
      {
        if ( wDest.Format == DXGI_FORMAT_B8G8R8A8_UNORM
          || wDest.Format == DXGI_FORMAT_B8G8R8X8_UNORM
          || wDest.Format == DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM
          || wDest.Format == DXGI_FORMAT_B8G8R8A8_UNORM_SRGB )
        {
          goto LABEL_23;
        }
      }
      else if ( wDest.Format == DXGI_FORMAT_B5G5R5A1_UNORM
             || wDest.Format == DXGI_FORMAT_R16G16B16A16_FLOAT
             || wDest.Format == DXGI_FORMAT_R10G10B10A2_UNORM
             || wDest.Format == DXGI_FORMAT_R8G8B8A8_UNORM
             || wDest.Format == DXGI_FORMAT_R8G8B8A8_UNORM_SRGB
             || wDest.Format == DXGI_FORMAT_B5G6R5_UNORM )
      {
        goto LABEL_23;
      }
      DXGI_SDK_MSG(
        *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
        DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_InvalidTargetSurfaceFormat);
      DXGIThrowFailure(-2005270527);
LABEL_23:
      v48 = 0;
      v11 = v29;
      v47 = v29;
      for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
      {
        *((_DWORD *)&v48 + 2 * i) = i;
        *((_DWORD *)&v48 + 2 * i + 1) = a3 + i;
      }
      v13 = *(_QWORD *)(a1 + 12888);
      if ( v13 )
      {
        memset(&v46, 0, sizeof(v46));
        LODWORD(v35[0]) = 0;
        ((void (__fastcall *)(struct IUnknown *, __int64, DXGI_SURFACE_DESC *, _QWORD *))v30->lpVtbl[6].QueryInterface)(
          v30,
          v13,
          &v46,
          v35);
        if ( LODWORD(v35[0]) != v29 )
        {
          DXGI_SDK_MSG(
            *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
            DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_ArraySizeMismatch);
          DXGIThrowFailure(-2005270527);
        }
        memset_0(v43, 0, 0x60u);
        v14 = 1;
        DWORD2(v51) = 0;
        LODWORD(v31) = 44;
        if ( (*(int (__fastcall **)(_QWORD, __int64 *, struct IDXGIDeviceSubObject **, __int128 *))(**(_QWORD **)(a1 + 12888)
                                                                                                  + 40LL))(
               *(_QWORD *)(a1 + 12888),
               qword_1800D5848,
               &v31,
               &v49) >= 0 )
          v14 = (v49 & 2) != 0;
        v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 56LL))(a1, v43);
        DXGIThrowFailure(v15);
        if ( v46.Format == wDest.Format && v46.Width == wDest.Width && v46.Height == wDest.Height )
        {
          v16 = v44;
          if ( v44 != DXGI_MODE_ROTATION_IDENTITY && v14 )
          {
LABEL_41:
            v9 = CopySrcToStagingSurface(
                   (struct IDXGIDeviceInternal3 *)v30,
                   *(struct IDXGIResource **)(a1 + 12888),
                   &v46,
                   v29,
                   (const struct SUBRESOURCE_BLT_MAP *)&v47,
                   v16);
            v32 = v9;
            goto LABEL_42;
          }
          if ( v28 )
          {
            ResolvingNonConvertingCopy(
              (struct IDXGIDeviceInternal3 *)v30,
              *(struct IDXGIResource **)(a1 + 12888),
              (struct IDXGIResource *)v4,
              (const struct SUBRESOURCE_BLT_MAP *)&v47);
            v37 = 2;
LABEL_42:
            v8 = (int)hdcDest[0];
LABEL_55:
            if ( v9 )
            {
              ConvertingRotatingStretchBlt(
                v9,
                (struct IDXGIResource *)v4,
                (const struct SUBRESOURCE_BLT_MAP *)&v47,
                *(struct IDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL));
              v8 = 0;
              v37 = 2;
            }
            goto LABEL_80;
          }
        }
        else
        {
          v16 = v44;
        }
        if ( !v14 )
          v16 = DXGI_MODE_ROTATION_IDENTITY;
        v44 = v16;
        goto LABEL_41;
      }
      if ( (unsigned __int8)IsCreateDCWPresent() )
      {
        if ( v29 != -1 )
        {
          DXGI_SDK_MSG(
            *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
            DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_ArraySizeMismatch);
          DXGIThrowFailure(-2005270527);
        }
        memset_0(pwszDriver, 0, 0x60u);
        v8 = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)a1 + 56LL))(a1, pwszDriver);
        hdcSrc = CreateDCW(pwszDriver, pwszDriver, 0, 0);
        DXGIThrowFailure(hdcSrc == 0 ? 0x80004005 : 0);
        if ( wDest.Format == DXGI_FORMAT_B5G6R5_UNORM
          || wDest.Format == DXGI_FORMAT_B5G5R5A1_UNORM
          || (unsigned int)(wDest.Format - 87) < 2 )
        {
          *(_OWORD *)hdcDest = 0;
          v8 = ((__int64 (__fastcall *)(struct IUnknown *, struct IDXGIDeviceSubObject *, _QWORD, HDC *, int))v30->lpVtbl[6].AddRef)(
                 v30,
                 v31,
                 a3,
                 hdcDest,
                 2);
          if ( v8 < 0 )
          {
            DXGI_SDK_MSG(
              *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
              DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_MapOfDestinationFailed);
            DXGIThrowFailure(v8);
          }
          v50 = 0;
          v51 = 0;
          v52 = 0;
          v49 = (unsigned __int64)hdcDest[1];
          for ( j = 0; (unsigned int)j < 0x5F; j = (unsigned int)(j + 1) )
          {
            if ( *((_DWORD *)&DXGI_D3D_Equivalencies + 2 * j) == wDest.Format )
            {
              v21 = *((_DWORD *)&DXGI_D3D_Equivalencies + 2 * j + 1);
              goto LABEL_65;
            }
          }
          v21 = 0;
LABEL_65:
          *((_QWORD *)&v49 + 1) = __PAIR64__(wDest.Width, v21);
          *(_QWORD *)&v50 = __PAIR64__((unsigned int)hdcDest[0], wDest.Height);
          *((_QWORD *)&v50 + 1) = hdcSrc;
          *(_QWORD *)&v51 = 0;
          v22 = (*(__int64 (__fastcall **)(__int128 *, _QWORD, const struct SDXGI_D3D near *const *))(*(_QWORD *)(a1 + 168) + 288LL))(
                  &v49,
                  (unsigned int)wDest.Format,
                  &DXGI_D3D_Equivalencies);
          v24 = v22;
          if ( v22 < 0 )
          {
            CModule::RecordJournalImpl(v23, v22, "OsThunkDDICreateDCFromMemory");
            ((void (__fastcall *)(struct IUnknown *, struct IDXGIDeviceSubObject *, _QWORD))v30->lpVtbl[6].Release)(
              v30,
              v31,
              a3);
            v8 = NTStatusToHResult(v24);
            if ( v8 == -2005530512 )
              v8 = -2005270523;
            DXGIThrowFailure(v8);
          }
          v25 = StretchBlt(
                  *((HDC *)&v51 + 1),
                  0,
                  0,
                  wDest.Width,
                  wDest.Height,
                  hdcSrc,
                  xSrc,
                  ySrc,
                  v56 - xSrc,
                  v57 - ySrc,
                  0xCC0020u);
          v4 = v31;
          if ( !v25 )
          {
            ((void (__fastcall *)(struct IUnknown *, struct IDXGIDeviceSubObject *, _QWORD))v30->lpVtbl[6].Release)(
              v30,
              v31,
              a3);
            DXGIThrowFailure(-2147467259);
          }
          v35[0] = *((_QWORD *)&v51 + 1);
          v35[1] = v52;
          (*(void (__fastcall **)(_QWORD *))(*(_QWORD *)(a1 + 168) + 296LL))(v35);
          ((void (__fastcall *)(struct IUnknown *, struct IDXGIDeviceSubObject *, _QWORD))v30->lpVtbl[6].Release)(
            v30,
            v4,
            a3);
          v37 = 2;
        }
        else
        {
          v18 = 0;
          hdcDest[0] = 0;
          v19 = (CSourceBitsDIBSection *)operator new(0x38u);
          v35[0] = v19;
          if ( v19 )
          {
            v9 = CSourceBitsDIBSection::CSourceBitsDIBSection(v19, &wDest, hdcDest);
            v18 = hdcDest[0];
          }
          else
          {
            v9 = 0;
          }
          v32 = v9;
          if ( !StretchBlt(v18, 0, 0, wDest.Width, wDest.Height, hdcSrc, xSrc, ySrc, v56 - xSrc, v57 - ySrc, 0xCC0020u) )
            DXGIThrowFailure(-2147467259);
          v4 = v31;
        }
        goto LABEL_55;
      }
      v8 = -2147467263;
    }
    catch ( _com_error *v42 )
    {
      v9 = v32;
      v8 = *((_DWORD *)v42 + 2);
    }
    catch ( std::bad_alloc )
    {
      v9 = v32;
      v8 = -2147024882;
    }
LABEL_80:
    if ( v9 )
      (**(void (__fastcall ***)(struct CSourceBits *, __int64))v9)(v9, 1);
    DXGILogMarkerHelper::~DXGILogMarkerHelper((DXGILogMarkerHelper *)&v36);
    CThreadLock<0>::ReleaseLock(&v40);
    goto LABEL_76;
  }
  DXGI_SDK_MSG(
    *(struct CDXGIFactory **)(*(_QWORD *)(a1 + 168) + 168LL),
    DXGI_MSG_IDXGIOutput_GetDisplaySurfaceData_NoOwnerDevice);
LABEL_77:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180072434  push    rsi
0x180072436  push    rdi
0x180072437  push    r12
0x180072439  push    r13
0x18007243b  push    r14
0x18007243d  push    r15
0x18007243f  sub     rsp, 238h
0x180072446  mov     rax, cs:__security_cookie
0x18007244d  xor     rax, rsp
0x180072450  mov     [rsp+268h+var_48], rax
0x180072458  mov     r13, r9
0x18007245b  mov     [rsp+268h+var_1F0], r9
0x180072460  mov     [rsp+268h+var_208], r8d
0x180072465  mov     r15d, edx
0x180072468  mov     rsi, rcx
0x18007246b  mov     [rsp+268h+var_1F8], 0
0x180072474  mov     [rsp+268h+var_1D0], 0
0x180072480  lea     r8, [rsp+268h+var_1D0]; struct ILockOwner **
0x180072488  lea     rdx, [rsp+268h+var_1F8]; struct IDXGIDeviceInternal3 **
0x18007248d  call    ?GetOwnerDevice@CDXGIOutput@@AEAAJPEAPEAUIDXGIDeviceInternal3@@PEAPEAUILockOwner@@@Z; CDXGIOutput::GetOwnerDevice(IDXGIDeviceInternal3 * *,ILockOwner * *)
0x180072492  mov     edi, 887A0001h
0x180072497  cmp     eax, edi
0x180072499  jnz     short loc_1800724B8
0x18007249b  mov     rcx, [rsi+0A8h]
0x1800724a2  mov     edx, 31h ; '1'; enum DXGI_Message_Id
0x1800724a7  mov     rcx, [rcx+0A8h]; struct CDXGIFactory *
0x1800724ae  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x1800724b3  jmp     loc_180072CFC
0x1800724b8  test    eax, eax
0x1800724ba  jns     short loc_1800724C3
0x1800724bc  mov     edi, eax
0x1800724be  jmp     loc_180072CFC
0x1800724c3  mov     rdx, [rsp+268h+var_1D0]; struct ILockOwner *
0x1800724cb  lea     rcx, [rsp+268h+var_1A8]; this
0x1800724d3  call    ??0LockOwnerLock@@QEAA@PEAUILockOwner@@@Z; LockOwnerLock::LockOwnerLock(ILockOwner *)
0x1800724d8  nop
0x1800724d9  test    r13, r13
0x1800724dc  jnz     short loc_1800724FA
0x1800724de  mov     rcx, [rsi+0A8h]
0x1800724e5  lea     edx, [r13+32h]; enum DXGI_Message_Id
0x1800724e9  mov     rcx, [rcx+0A8h]; struct CDXGIFactory *
0x1800724f0  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x1800724f5  jmp     loc_180072CEE
0x1800724fa  mov     [rsp+268h+var_198], 0
0x180072502  mov     rax, rsi
0x180072505  lea     rdx, [rsi+98h]
0x18007250c  neg     rax
0x18007250f  sbb     rcx, rcx
0x180072512  and     rcx, rdx
0x180072515  mov     [rsp+268h+var_1A0], rcx
0x18007251d  lea     rcx, [rsp+268h+var_1A0]
0x180072525  call    ?TakeLock@?$CThreadLock@$0A@@@QEAAXXZ; CThreadLock<0>::TakeLock(void)
0x18007252a  nop
0x18007252b  mov     rax, [rsp+268h+var_1F8]
0x180072530  mov     [rsp+268h+var_1B8], rax
0x180072538  mov     r12d, 1
0x18007253e  mov     [rsp+268h+var_1B0], r12d
0x180072546  mov     [rsp+268h+var_1AC], r12d
0x18007254e  xor     r14d, r14d
0x180072551  mov     [rsp+268h+var_1E8], r14
0x180072559  mov     rax, [rsi+0A8h]
0x180072560  mov     rcx, [rax+0A8h]
0x180072567  mov     eax, [rcx+19Ch]
0x18007256d  and     eax, r12d
0x180072570  neg     al
0x180072572  sbb     r8, r8
0x180072575  and     r8, rcx
0x180072578  mov     rcx, [rsp+268h+var_1F8]
0x18007257d  mov     rdx, [rcx]
0x180072580  lea     rax, [r8+0E0h]
0x180072587  neg     r8
0x18007258a  sbb     r10, r10
0x18007258d  and     r10, rax
0x180072590  mov     rax, [rdx+0C0h]
0x180072597  mov     r9, r13
0x18007259a  mov     r8d, r15d
0x18007259d  mov     rdx, r10
0x1800725a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725a5  mov     ecx, eax; int
0x1800725a7  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800725ac  mov     rdx, r13; struct IDXGIDeviceSubObject *
0x1800725af  mov     rcx, [rsp+268h+var_1F8]; struct IUnknown *
0x1800725b4  call    ?IsCompatibleWithDevice@@YA_NPEAUIUnknown@@PEAUIDXGIDeviceSubObject@@@Z; IsCompatibleWithDevice(IUnknown *,IDXGIDeviceSubObject *)
0x1800725b9  mov     [rsp+268h+var_204], al
0x1800725bd  xorps   xmm0, xmm0
0x1800725c0  xor     eax, eax
0x1800725c2  movups  xmmword ptr [rsp+268h+wDest], xmm0
0x1800725ca  mov     [rsp+268h+var_118], eax
0x1800725d1  mov     [rsp+268h+var_200], eax
0x1800725d5  mov     rcx, [rsp+268h+var_1F8]
0x1800725da  mov     rdx, [rcx]
0x1800725dd  mov     rax, [rdx+90h]
0x1800725e4  lea     r9, [rsp+268h+var_200]
0x1800725e9  lea     r8, [rsp+268h+wDest]
0x1800725f1  mov     rdx, r13
0x1800725f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725f9  mov     dword ptr [rsp+268h+hdcDest], eax
0x180072600  mov     ecx, eax; int
0x180072602  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180072607  test    r15d, r15d
0x18007260a  jg      short loc_180072611
0x18007260c  mov     [rsp+268h+var_200], r12d
0x180072611  mov     ecx, [rsp+268h+wDest+8]
0x180072618  cmp     ecx, 56h ; 'V'
0x18007261b  jg      short loc_18007263A
0x18007261d  jz      short loc_18007266D
0x18007261f  sub     ecx, 0Ah
0x180072622  jz      short loc_18007266D
0x180072624  sub     ecx, 0Eh
0x180072627  jz      short loc_18007266D
0x180072629  sub     ecx, 4
0x18007262c  jz      short loc_18007266D
0x18007262e  sub     ecx, 1
0x180072631  jz      short loc_18007266D
0x180072633  cmp     ecx, 38h ; '8'
0x180072636  jnz     short loc_18007264E
0x180072638  jmp     short loc_18007266D
0x18007263a  sub     ecx, 57h ; 'W'
0x18007263d  jz      short loc_18007266D
0x18007263f  sub     ecx, 1
0x180072642  jz      short loc_18007266D
0x180072644  sub     ecx, 1
0x180072647  jz      short loc_18007266D
0x180072649  cmp     ecx, 2
0x18007264c  jz      short loc_18007266D
0x18007264e  mov     rcx, [rsi+0A8h]
0x180072655  mov     edx, 43h ; 'C'; enum DXGI_Message_Id
0x18007265a  mov     rcx, [rcx+0A8h]; struct CDXGIFactory *
0x180072661  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x180072666  mov     ecx, edi; int
0x180072668  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18007266d  xorps   xmm0, xmm0
0x180072670  movdqu  [rsp+268h+var_F4], xmm0
0x180072679  mov     r8d, [rsp+268h+var_200]
0x18007267e  mov     [rsp+268h+var_F8], r8d
0x180072686  xor     edx, edx
0x180072688  mov     r15d, [rsp+268h+var_208]
0x18007268d  test    r8d, r8d
0x180072690  jz      short loc_1800726AC
0x180072692  mov     dword ptr [rsp+rdx*8+268h+var_F4], edx
0x180072699  lea     eax, [r15+rdx]
0x18007269d  mov     dword ptr [rsp+rdx*8+268h+var_F4+4], eax
0x1800726a4  add     edx, r12d
0x1800726a7  cmp     edx, r8d
0x1800726aa  jb      short loc_180072692
0x1800726ac  mov     rdx, [rsi+3258h]
0x1800726b3  test    rdx, rdx
0x1800726b6  jz      loc_180072871
0x1800726bc  xorps   xmm0, xmm0
0x1800726bf  xor     eax, eax
0x1800726c1  movups  xmmword ptr [rsp+268h+var_110.Width], xmm0
0x1800726c9  mov     [rsp+268h+var_110.SampleDesc.Quality], eax
0x1800726d0  mov     dword ptr [rsp+268h+var_1C8], eax
0x1800726d7  mov     rcx, [rsp+268h+var_1F8]
0x1800726dc  mov     rax, [rcx]
0x1800726df  lea     r9, [rsp+268h+var_1C8]
0x1800726e7  lea     r8, [rsp+268h+var_110]
0x1800726ef  mov     rax, [rax+90h]
0x1800726f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726fb  mov     eax, [rsp+268h+var_200]
0x1800726ff  cmp     dword ptr [rsp+268h+var_1C8], eax
0x180072706  jz      short loc_180072727
0x180072708  mov     rcx, [rsi+0A8h]
0x18007270f  mov     edx, 0B4h; enum DXGI_Message_Id
0x180072714  mov     rcx, [rcx+0A8h]; struct CDXGIFactory *
0x18007271b  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x180072720  mov     ecx, edi; int
0x180072722  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180072727  xor     edx, edx; Val
0x180072729  lea     r8d, [rdx+60h]; Size
0x18007272d  lea     rcx, [rsp+268h+var_188]; void *
0x180072735  call    memset_0
0x18007273a  mov     dil, r12b
0x18007273d  mov     dword ptr [rsp+268h+var_B8], 0
0x180072748  mov     dword ptr [rsp+268h+var_1F0], 2Ch ; ','
0x180072750  mov     rcx, [rsi+3258h]
0x180072757  mov     rax, [rcx]
0x18007275a  lea     r9, [rsp+268h+var_E0]
0x180072762  lea     r8, [rsp+268h+var_1F0]
0x180072767  lea     rdx, qword_1800D5848
0x18007276e  mov     rax, [rax+28h]
0x180072772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072777  test    eax, eax
0x180072779  js      short loc_180072787
0x18007277b  mov     edi, dword ptr [rsp+268h+var_E0]
0x180072782  shr     edi, 1
0x180072784  and     dil, r12b
0x180072787  mov     rax, [rsi]
0x18007278a  lea     rdx, [rsp+268h+var_188]
0x180072792  mov     rcx, rsi
0x180072795  mov     rax, [rax+38h]
0x180072799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007279e  mov     ecx, eax; int
0x1800727a0  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800727a5  mov     eax, [rsp+268h+wDest+8]
0x1800727ac  cmp     [rsp+268h+var_110.Format], eax
0x1800727b3  jnz     short loc_180072816
0x1800727b5  mov     eax, [rsp+268h+wDest]
0x1800727bc  cmp     [rsp+268h+var_110.Width], eax
0x1800727c3  jnz     short loc_180072816
0x1800727c5  mov     eax, [rsp+268h+wDest+4]
0x1800727cc  cmp     [rsp+268h+var_110.Height], eax
0x1800727d3  jnz     short loc_180072816
0x1800727d5  mov     eax, [rsp+268h+var_134]
0x1800727dc  cmp     eax, r12d
0x1800727df  jz      short loc_1800727E6
0x1800727e1  test    dil, dil
0x1800727e4  jnz     short loc_18007282B
0x1800727e6  cmp     [rsp+268h+var_204], 0
0x1800727eb  jz      short loc_18007281D
0x1800727ed  lea     r9, [rsp+268h+var_F8]; struct SUBRESOURCE_BLT_MAP *
0x1800727f5  mov     r8, r13; struct IDXGIResource *
0x1800727f8  mov     rdx, [rsi+3258h]; struct IDXGIResource *
0x1800727ff  mov     rcx, [rsp+268h+var_1F8]; struct IDXGIDeviceInternal3 *
0x180072804  call    ?ResolvingNonConvertingCopy@@YAXPEAUIDXGIDeviceInternal3@@PEAUIDXGIResource@@1PEBUSUBRESOURCE_BLT_MAP@@@Z; ResolvingNonConvertingCopy(IDXGIDeviceInternal3 *,IDXGIResource *,IDXGIResource *,SUBRESOURCE_BLT_MAP const *)
0x180072809  mov     [rsp+268h+var_1B0], 2
0x180072814  jmp     short loc_180072865
0x180072816  mov     eax, [rsp+268h+var_134]
0x18007281d  test    dil, dil
0x180072820  cmovz   eax, r12d
0x180072824  mov     [rsp+268h+var_134], eax
0x18007282b  mov     dword ptr [rsp+268h+hdcSrc], eax; enum DXGI_MODE_ROTATION
0x18007282f  lea     rax, [rsp+268h+var_F8]
0x180072837  mov     qword ptr [rsp+268h+hDest], rax; struct SUBRESOURCE_BLT_MAP *
0x18007283c  mov     r9d, [rsp+268h+var_200]; unsigned int
0x180072841  lea     r8, [rsp+268h+var_110]; struct DXGI_SURFACE_DESC *
0x180072849  mov     rdx, [rsi+3258h]; struct IDXGIResource *
0x180072850  mov     rcx, [rsp+268h+var_1F8]; struct IDXGIDeviceInternal3 *
0x180072855  call    ?CopySrcToStagingSurface@@YAPEAVCSourceBits@@PEAUIDXGIDeviceInternal3@@PEAUIDXGIResource@@PEAUDXGI_SURFACE_DESC@@IPEBUSUBRESOURCE_BLT_MAP@@W4DXGI_MODE_ROTATION@@@Z; CopySrcToStagingSurface(IDXGIDeviceInternal3 *,IDXGIResource *,DXGI_SURFACE_DESC *,uint,SUBRESOURCE_BLT_MAP const *,DXGI_MODE_ROTATION)
0x18007285a  mov     r14, rax
0x18007285d  mov     [rsp+268h+var_1E8], rax
0x180072865  mov     edi, dword ptr [rsp+268h+hdcDest]
0x18007286c  jmp     loc_1800729F6
0x180072871  call    IsCreateDCWPresent
0x180072876  test    al, al
0x180072878  jz      loc_180072CA0
0x18007287e  cmp     [rsp+268h+var_200], 0FFFFFFFFh
0x180072883  jz      short loc_1800728A4
0x180072885  mov     rcx, [rsi+0A8h]
0x18007288c  mov     edx, 0B4h; enum DXGI_Message_Id
0x180072891  mov     rcx, [rcx+0A8h]; struct CDXGIFactory *
0x180072898  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x18007289d  mov     ecx, edi; int
0x18007289f  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800728a4  xor     edx, edx; Val
0x1800728a6  lea     r8d, [rdx+60h]; Size
0x1800728aa  lea     rcx, [rsp+268h+pwszDriver]; void *
0x1800728b2  call    memset_0
0x1800728b7  mov     rax, [rsi]
0x1800728ba  lea     rdx, [rsp+268h+pwszDriver]
0x1800728c2  mov     rcx, rsi
0x1800728c5  mov     rax, [rax+38h]
0x1800728c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800728ce  mov     edi, eax
0x1800728d0  xor     r9d, r9d; pdm
0x1800728d3  xor     r8d, r8d; pszPort
0x1800728d6  lea     rdx, [rsp+268h+pwszDriver]; pwszDevice
0x1800728de  lea     rcx, [rsp+268h+pwszDriver]; pwszDriver
0x1800728e6  call    cs:__imp_CreateDCW
0x1800728ec  mov     r13, rax
0x1800728ef  mov     rcx, rax
0x1800728f2  neg     rcx
0x1800728f5  sbb     ecx, ecx
0x1800728f7  not     ecx
0x1800728f9  and     ecx, 80004005h; int
0x1800728ff  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180072904  mov     edx, [rsp+268h+wDest+8]
0x18007290b  sub     edx, 55h ; 'U'
0x18007290e  jz      loc_180072A32
0x180072914  sub     edx, 1
0x180072917  jz      loc_180072A32
0x18007291d  sub     edx, 1
0x180072920  jz      loc_180072A32
0x180072926  cmp     edx, 1
0x180072929  jz      loc_180072A32
0x18007292f  xor     r15d, r15d
0x180072932  mov     [rsp+268h+hdcDest], r15
0x18007293a  lea     ecx, [r15+38h]; dwBytes
0x18007293e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072943  mov     [rsp+268h+var_1C8], rax
0x18007294b  test    rax, rax
0x18007294e  jz      short loc_180072975
0x180072950  lea     r8, [rsp+268h+hdcDest]; HDC *
0x180072958  lea     rdx, [rsp+268h+wDest]; struct DXGI_SURFACE_DESC *
0x180072960  mov     rcx, rax; this
0x180072963  call    ??0CSourceBitsDIBSection@@QEAA@AEBUDXGI_SURFACE_DESC@@PEAPEAUHDC__@@@Z; CSourceBitsDIBSection::CSourceBitsDIBSection(DXGI_SURFACE_DESC const &,HDC__ * *)
0x180072968  mov     r14, rax
0x18007296b  mov     r15, [rsp+268h+hdcDest]
0x180072973  jmp     short loc_180072978
0x180072975  xor     r14d, r14d
0x180072978  mov     [rsp+268h+var_1E8], r14
0x180072980  mov     r8d, [rsp+268h+var_5C]
0x180072988  mov     r9d, [rsp+268h+var_64]
0x180072990  sub     r8d, r9d
0x180072993  mov     eax, [rsp+268h+var_60]
0x18007299a  mov     edx, [rsp+268h+var_68]
0x1800729a1  sub     eax, edx
0x1800729a3  mov     [rsp+268h+rop], 0CC0020h; rop
0x1800729ab  mov     [rsp+268h+hSrc], r8d; hSrc
0x1800729b0  mov     [rsp+268h+wSrc], eax; wSrc
  ... truncated ...
```
