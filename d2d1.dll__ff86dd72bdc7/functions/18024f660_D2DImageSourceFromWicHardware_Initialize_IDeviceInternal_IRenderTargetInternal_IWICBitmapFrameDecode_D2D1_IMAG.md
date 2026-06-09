# D2DImageSourceFromWicHardware::Initialize(IDeviceInternal *,IRenderTargetInternal *,IWICBitmapFrameDecode *,D2D1_IMAGE_SOURCE_LOADING_OPTIONS,D2D1_IMAGE_SOURCE_DECODING_PARAMETERS const *,void *,LockStatus::Enum)

- ea: `0x18024f660`
- end: `0x18024fc3a`
- name: `?Initialize@D2DImageSourceFromWicHardware@@QEAAJPEAVIDeviceInternal@@PEAVIRenderTargetInternal@@PEAUIWICBitmapFrameDecode@@W4D2D1_IMAGE_SOURCE_LOADING_OPTIONS@@PEBUD2D1_IMAGE_SOURCE_DECODING_PARAMETERS@@PEAXW4Enum@LockStatus@@@Z`
- size: `1498`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18024ec48`

## callees

- `0x1800152a0`
- `0x18001fd58`
- `0x1800389c0`
- `0x1800b0dd0`
- `0x1800b6b7c`
- `0x180162150`
- `0x18024f660`
- `0x18024fc40`
- `0x180250764`
- `0x1802507dc`
- `0x1802509bc`
- `0x18025b100`
- `0x18025b124`
- `0x1802adfe8`
- `0x1802aeae8`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024fa22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024fa22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024f975`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024f975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024fa4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024fa4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024f98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024fa2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024f98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024fa2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024f980`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024f980`

## pseudocode

```c
__int64 __fastcall D2DImageSourceFromWicHardware::Initialize(
        __int64 a1,
        struct IDeviceInternal *a2,
        struct IRenderTargetInternal *a3,
        _QWORD *a4,
        int a5,
        unsigned int *a6,
        __int64 a7,
        unsigned int a8)
{
  enum D2D1_ORIENTATION v11; // edx
  char v12; // r8
  __int64 v13; // r15
  __int64 v14; // rax
  enum D2D1_ORIENTATION v15; // edx
  signed int v16; // ebx
  int v17; // ecx
  unsigned int v18; // r12d
  unsigned int v19; // r13d
  unsigned int v20; // r11d
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  int v25; // eax
  __int64 v26; // rbx
  HANDLE EventW; // r13
  signed int LastError; // eax
  int v29; // ecx
  __int64 v30; // r15
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  signed int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // eax
  struct IDeviceInternal **v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rdx
  _QWORD *v43; // rax
  int v45; // [rsp+20h] [rbp-E0h]
  enum D2D1_ORIENTATION v46; // [rsp+38h] [rbp-C8h]
  struct IDeviceInternal *v47; // [rsp+40h] [rbp-C0h] BYREF
  struct IDXGISurface *v48; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v51; // [rsp+60h] [rbp-A0h]
  struct IRenderTargetInternal *v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  int v55; // [rsp+80h] [rbp-80h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57[10]; // [rsp+A8h] [rbp-58h] BYREF
  char v58; // [rsp+FCh] [rbp-4h]

  v52 = a3;
  v51 = a4;
  v50 = a7;
  v47 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct IDeviceInternal *))(*(_QWORD *)a2 + 8LL))(a2);
    v47 = a2;
  }
  win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
    &v47,
    a1 + 16);
  if ( v47 )
    (*(void (__fastcall **)(struct IDeviceInternal *))(*(_QWORD *)v47 + 16LL))(v47);
  v12 = a5;
  if ( (a5 & 0xFFFFFFFC) != 0 || a6 && !D2D1::ORIENTATION_IsValid((D2D1 *)*a6, v11) || (v12 & 2) != 0 )
  {
    v16 = -2147024809;
    DoStackCapture(-2147024809);
    return (unsigned int)v16;
  }
  if ( (v12 & 1) == 0 )
    ATL::CComPtr<ID3D12Resource>::operator=(a1 + 216, a4);
  v13 = *(_QWORD *)((*(__int64 (__fastcall **)(struct IDeviceInternal *))(*(_QWORD *)a2 + 64LL))(a2) + 104);
  v53 = v13;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v14 = (*(__int64 (__fastcall **)(struct IDeviceInternal *))(*(_QWORD *)a2 + 64LL))(a2);
  ATL::CComPtr<ID3D12Resource>::operator=(a1 + 192, *(_QWORD *)(v14 + 128));
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 192))(
         *(_QWORD *)(a1 + 192),
         &GUID_1345b344_2425_44ac_8299_091659b81f40,
         a1 + 200) >= 0 )
  {
    v57[0] = 0;
    v56 = 0;
    v58 = 0;
    if ( a6 && !D2D1::ORIENTATION_IsValid((D2D1 *)*a6, v15) )
    {
      v16 = -2147024809;
      v17 = -2147024809;
LABEL_30:
      DoStackCapture(v17);
LABEL_31:
      DoStackCapture(v16);
LABEL_79:
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(v57);
      goto LABEL_80;
    }
    v49 = -1;
    v18 = -1;
    v19 = -1;
    if ( a6 )
    {
      GetOrientedSizes<unsigned int>(a6[1], a6[2], *a6, (unsigned int)&v49, (__int64)&v49 + 4);
      v18 = v49;
      v19 = HIDWORD(v49);
      if ( !(_DWORD)v49 )
        v18 = v20;
      if ( !HIDWORD(v49) )
        v19 = v20;
    }
    v21 = *a4;
    v47 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD *, struct IDeviceInternal **, char *))(v21 + 24))(
            a4,
            &v47,
            (char *)&v47 + 4);
    v16 = v22;
    if ( v22 < 0 )
      goto LABEL_29;
    v23 = (unsigned int)v47;
    if ( v18 < (unsigned int)v47 )
      v23 = v18;
    LODWORD(v49) = v23;
    v24 = HIDWORD(v47);
    if ( v19 < HIDWORD(v47) )
      v24 = v19;
    HIDWORD(v49) = v24;
    LOBYTE(v45) = 1;
    v22 = HardwareJpegHelper::Initialize(&v56, a2, v51, 1, v45, v49, v47);
    v16 = v22;
    if ( v22 < 0 )
    {
LABEL_29:
      v17 = v22;
      goto LABEL_30;
    }
    if ( !v58 )
    {
      v16 = -2003238909;
      goto LABEL_31;
    }
    v48 = 0;
    v54 = 16;
    v55 = 5;
    v25 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v13 + 480LL))(v13, &v54, a1 + 208);
    v16 = v25;
    if ( v25 >= 0 )
    {
      v25 = HardwareJpegHelper::Decode(
              &v56,
              *(_QWORD *)(a1 + 192),
              *(_QWORD *)(a1 + 200),
              a8,
              *(_QWORD *)(a1 + 208),
              &v48);
      v16 = v25;
      if ( v25 >= 0 )
      {
        v26 = v50;
        if ( v50 )
        {
          if ( a8 == 1 )
          {
            v40 = *(_QWORD *)((a1 & -(__int64)(a1 != -16)) + 0x10);
            v41 = v40 + 8;
            if ( !v40 )
              v41 = 16;
            v42 = *(_QWORD *)v41;
          }
          else
          {
            v42 = 0;
          }
          CGuard<AbstractLock>::CGuard<AbstractLock>(&v50, v42);
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 192) + 1152LL))(
            *(_QWORD *)(a1 + 192),
            5,
            v26);
          v39 = (struct IDeviceInternal **)&v50;
        }
        else
        {
          EventW = CreateEventW(0, 0, 0, 0);
          SetLastError(0);
          if ( !EventW )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
            if ( v16 >= 0 )
              v16 = -2003238887;
            goto LABEL_42;
          }
          v16 = 0;
          if ( a8 == 1 )
          {
            v30 = a1 + 16;
            v31 = *(_QWORD *)((a1 & -(__int64)(a1 != -16)) + 0x10);
            v32 = v31 + 8;
            if ( !v31 )
              v32 = 16;
            v33 = *(_QWORD *)v32;
          }
          else
          {
            v33 = 0;
            v30 = a1 + 16;
          }
          CGuard<AbstractLock>::CGuard<AbstractLock>(&v50, v33);
          (*(void (__fastcall **)(_QWORD, __int64, HANDLE))(**(_QWORD **)(a1 + 192) + 1152LL))(
            *(_QWORD *)(a1 + 192),
            5,
            EventW);
          CGuard<AbstractLock>::~CGuard<AbstractLock>(&v50);
          if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
          {
            v34 = GetLastError();
            v16 = v34;
            if ( v34 > 0 )
              v16 = (unsigned __int16)v34 | 0x80070000;
            if ( v16 >= 0 )
              v16 = -2003238887;
          }
          CloseHandle(EventW);
          if ( v16 < 0 )
            goto LABEL_42;
          if ( a8 == 1 )
          {
            v35 = *(_QWORD *)((a1 & -(__int64)(v30 != 0)) + 0x10);
            v36 = v35 + 8;
            if ( !v35 )
              v36 = 16;
            v37 = *(_QWORD *)v36;
          }
          else
          {
            v37 = 0;
          }
          CGuard<AbstractLock>::CGuard<AbstractLock>(&v47, v37);
          v38 = D2DImageSourceFromWicHardware::CheckQuerySuccess((D2DImageSourceFromWicHardware *)a1);
          v16 = v38;
          if ( v38 < 0 )
          {
            DoStackCapture(v38);
            CGuard<AbstractLock>::~CGuard<AbstractLock>(&v47);
LABEL_78:
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v48);
            goto LABEL_79;
          }
          v39 = &v47;
        }
        CGuard<AbstractLock>::~CGuard<AbstractLock>(v39);
        v43 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v43 )
        {
          v43[1] = 0;
          v43[2] = 0;
          v43[3] = 0;
          v43[4] = 0;
          v43[5] = 0;
          *((_DWORD *)v43 + 16) = 0;
          *((_BYTE *)v43 + 68) = 0;
          *v43 = &RefCountedObject<ImageSourceFrame,LockingRequired,DeleteOnZeroReference>::`vftable';
          *((_DWORD *)v43 + 18) = 1;
        }
        else
        {
          v43 = 0;
        }
        *(_QWORD *)(a1 + 136) = v43;
        if ( !v43 )
        {
          v16 = -2147024882;
LABEL_42:
          v29 = v16;
LABEL_75:
          DoStackCapture(v29);
          goto LABEL_78;
        }
        v25 = ImageSourceFrame::Initialize(
                (ImageSourceFrame *)v43,
                a2,
                v52,
                &v48,
                1u,
                DXGI_COLOR_SPACE_YCBCR_FULL_G22_NONE_P709_X601,
                D2D1_IMAGE_SOURCE_FROM_DXGI_OPTIONS_NONE,
                v46);
        v16 = v25;
        if ( v25 >= 0 )
        {
          if ( a6 )
          {
            *(_DWORD *)(a1 + 168) = *a6;
            *(_DWORD *)(a1 + 172) = 1065353216;
            *(_DWORD *)(a1 + 176) = 1065353216;
            *(_DWORD *)(a1 + 180) = 1;
            *(_BYTE *)(a1 + 184) = 1;
          }
          goto LABEL_78;
        }
      }
    }
    v29 = v25;
    goto LABEL_75;
  }
  v16 = -2003238909;
  DoStackCapture(-2003238909);
LABEL_80:
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v53);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18024f660  push    rbp
0x18024f662  push    rbx
0x18024f663  push    rsi
0x18024f664  push    rdi
0x18024f665  push    r12
0x18024f667  push    r13
0x18024f669  push    r14
0x18024f66b  push    r15
0x18024f66d  lea     rbp, [rsp-28h]
0x18024f672  sub     rsp, 128h
0x18024f679  mov     rax, cs:__security_cookie
0x18024f680  xor     rax, rsp
0x18024f683  mov     [rbp+60h+var_50], rax
0x18024f687  mov     rax, [rbp+60h+arg_30]
0x18024f68e  xor     r13d, r13d
0x18024f691  mov     [rsp+160h+var_F8], r8
0x18024f696  mov     rbx, r9
0x18024f699  mov     [rsp+160h+var_100], rbx
0x18024f69e  mov     r14, rdx
0x18024f6a1  mov     [rsp+160h+var_108], rax
0x18024f6a6  mov     rdi, rcx
0x18024f6a9  mov     [rsp+160h+var_120], r13
0x18024f6ae  test    rdx, rdx
0x18024f6b1  jz      short loc_18024F6C7
0x18024f6b3  mov     rax, [rdx]
0x18024f6b6  mov     rcx, rdx
0x18024f6b9  mov     rax, [rax+8]
0x18024f6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f6c2  mov     [rsp+160h+var_120], r14
0x18024f6c7  lea     rdx, [rdi+10h]
0x18024f6cb  lea     rcx, [rsp+160h+var_120]
0x18024f6d0  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x18024f6d5  mov     rcx, [rsp+160h+var_120]
0x18024f6da  test    rcx, rcx
0x18024f6dd  jz      short loc_18024F6EB
0x18024f6df  mov     rax, [rcx]
0x18024f6e2  mov     rax, [rax+10h]
0x18024f6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f6eb  mov     r8d, [rbp+60h+arg_20]
0x18024f6f2  test    r8d, 0FFFFFFFCh
0x18024f6f9  jnz     loc_18024FC0C
0x18024f6ff  mov     rsi, [rbp+60h+arg_28]
0x18024f706  test    rsi, rsi
0x18024f709  jz      short loc_18024F71A
0x18024f70b  mov     ecx, [rsi]; this
0x18024f70d  call    ?ORIENTATION_IsValid@D2D1@@YA_NW4D2D1_ORIENTATION@@@Z; D2D1::ORIENTATION_IsValid(D2D1_ORIENTATION)
0x18024f712  test    al, al
0x18024f714  jz      loc_18024FC0C
0x18024f71a  test    r8b, 2
0x18024f71e  jnz     loc_18024FC0C
0x18024f724  test    r8b, 1
0x18024f728  jnz     short loc_18024F739
0x18024f72a  lea     rcx, [rdi+0D8h]
0x18024f731  mov     rdx, rbx
0x18024f734  call    ??4?$CComPtr@UID3D12Resource@@@ATL@@QEAAPEAUID3D12Resource@@PEAU2@@Z; ATL::CComPtr<ID3D12Resource>::operator=(ID3D12Resource *)
0x18024f739  mov     rax, [r14]
0x18024f73c  mov     rcx, r14
0x18024f73f  mov     rax, [rax+40h]
0x18024f743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f748  mov     r15, [rax+68h]
0x18024f74c  mov     [rsp+160h+var_F0], r15
0x18024f751  test    r15, r15
0x18024f754  jz      short loc_18024F765
0x18024f756  mov     rax, [r15]
0x18024f759  mov     rcx, r15
0x18024f75c  mov     rax, [rax+8]
0x18024f760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f765  mov     rax, [r14]
0x18024f768  mov     rcx, r14
0x18024f76b  mov     rax, [rax+40h]
0x18024f76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f774  lea     r12, [rdi+0C0h]
0x18024f77b  mov     rcx, r12
0x18024f77e  mov     rdx, [rax+80h]
0x18024f785  call    ??4?$CComPtr@UID3D12Resource@@@ATL@@QEAAPEAUID3D12Resource@@PEAU2@@Z; ATL::CComPtr<ID3D12Resource>::operator=(ID3D12Resource *)
0x18024f78a  mov     rcx, [r12]
0x18024f78e  lea     r8, [rdi+0C8h]
0x18024f795  lea     rdx, _GUID_1345b344_2425_44ac_8299_091659b81f40
0x18024f79c  mov     rax, [rcx]
0x18024f79f  mov     rax, [rax]
0x18024f7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f7a7  test    eax, eax
0x18024f7a9  jns     short loc_18024F7BC
0x18024f7ab  mov     ebx, 88990003h
0x18024f7b0  mov     ecx, ebx; int
0x18024f7b2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18024f7b7  jmp     loc_18024FC00
0x18024f7bc  mov     [rbp+60h+var_B8], r13
0x18024f7c0  xorps   xmm0, xmm0
0x18024f7c3  movdqa  [rbp+60h+var_D0], xmm0
0x18024f7c8  mov     [rbp+60h+var_64], r13b
0x18024f7cc  test    rsi, rsi
0x18024f7cf  jz      short loc_18024F7E8
0x18024f7d1  mov     ecx, [rsi]; this
0x18024f7d3  call    ?ORIENTATION_IsValid@D2D1@@YA_NW4D2D1_ORIENTATION@@@Z; D2D1::ORIENTATION_IsValid(D2D1_ORIENTATION)
0x18024f7d8  test    al, al
0x18024f7da  jnz     short loc_18024F7E8
0x18024f7dc  mov     ebx, 80070057h
0x18024f7e1  mov     ecx, ebx
0x18024f7e3  jmp     loc_18024F8B4
0x18024f7e8  or      r11d, 0FFFFFFFFh
0x18024f7ec  mov     dword ptr [rsp+160h+var_110], r11d
0x18024f7f1  mov     r12d, r11d
0x18024f7f4  mov     dword ptr [rsp+160h+var_110+4], r11d
0x18024f7f9  mov     r13d, r11d
0x18024f7fc  test    rsi, rsi
0x18024f7ff  jz      short loc_18024F836
0x18024f801  mov     r8d, [rsi]
0x18024f804  lea     rax, [rsp+160h+var_110+4]
0x18024f809  mov     edx, [rsi+8]
0x18024f80c  lea     r9, [rsp+160h+var_110]
0x18024f811  mov     ecx, [rsi+4]
0x18024f814  mov     qword ptr [rsp+160h+var_140], rax
0x18024f819  call    ??$GetOrientedSizes@I@@YAXIIW4D2D1_ORIENTATION@@PEAI1@Z; GetOrientedSizes<uint>(uint,uint,D2D1_ORIENTATION,uint *,uint *)
0x18024f81e  mov     r12d, dword ptr [rsp+160h+var_110]
0x18024f823  test    r12d, r12d
0x18024f826  mov     r13d, dword ptr [rsp+160h+var_110+4]
0x18024f82b  cmovz   r12d, r11d
0x18024f82f  test    r13d, r13d
0x18024f832  cmovz   r13d, r11d
0x18024f836  mov     rax, [rbx]
0x18024f839  lea     r8, [rsp+160h+var_120+4]
0x18024f83e  lea     rdx, [rsp+160h+var_120]
0x18024f843  mov     [rsp+160h+var_120], 0
0x18024f84c  mov     rcx, rbx
0x18024f84f  mov     rax, [rax+18h]
0x18024f853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f858  mov     ebx, eax
0x18024f85a  test    eax, eax
0x18024f85c  js      short loc_18024F8B2
0x18024f85e  mov     rax, [rsp+160h+var_120]
0x18024f863  mov     r9d, 1
0x18024f869  mov     r8, [rsp+160h+var_100]
0x18024f86e  cmp     r12d, eax
0x18024f871  mov     ecx, eax
0x18024f873  mov     qword ptr [rsp+160h+var_130], rax
0x18024f878  cmovb   ecx, r12d
0x18024f87c  mov     rdx, r14
0x18024f87f  mov     dword ptr [rsp+160h+var_110], ecx
0x18024f883  mov     ecx, dword ptr [rsp+160h+var_120+4]
0x18024f887  cmp     r13d, ecx
0x18024f88a  cmovb   ecx, r13d
0x18024f88e  mov     dword ptr [rsp+160h+var_110+4], ecx
0x18024f892  lea     rcx, [rbp+60h+var_D0]
0x18024f896  mov     rax, [rsp+160h+var_110]
0x18024f89b  mov     qword ptr [rsp+160h+var_138], rax
0x18024f8a0  mov     byte ptr [rsp+160h+var_140], 1
0x18024f8a5  call    ?Initialize@HardwareJpegHelper@@QEAAJPEAVIDeviceInternal@@PEAUIWICBitmapFrameDecode@@W4D2D1_IMAGE_SOURCE_DECODING_SUPPORT_OPTIONS@@_NUD2D_SIZE_U@@4@Z; HardwareJpegHelper::Initialize(IDeviceInternal *,IWICBitmapFrameDecode *,D2D1_IMAGE_SOURCE_DECODING_SUPPORT_OPTIONS,bool,D2D_SIZE_U,D2D_SIZE_U)
0x18024f8aa  xor     ecx, ecx
0x18024f8ac  mov     ebx, eax
0x18024f8ae  test    eax, eax
0x18024f8b0  jns     short loc_18024F8C5
0x18024f8b2  mov     ecx, eax; int
0x18024f8b4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18024f8b9  mov     ecx, ebx; int
0x18024f8bb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18024f8c0  jmp     loc_18024FBF7
0x18024f8c5  cmp     [rbp+60h+var_64], cl
0x18024f8c8  mov     eax, ecx
0x18024f8ca  setnz   al
0x18024f8cd  test    eax, eax
0x18024f8cf  jnz     short loc_18024F8D8
0x18024f8d1  mov     ebx, 88990003h
0x18024f8d6  jmp     short loc_18024F8B9
0x18024f8d8  mov     [rsp+160h+var_118], rcx
0x18024f8dd  lea     r12, [rdi+0D0h]
0x18024f8e4  mov     [rsp+160h+var_E8], 10h
0x18024f8ed  lea     rdx, [rsp+160h+var_E8]
0x18024f8f2  mov     [rbp+60h+var_E0], 5
0x18024f8f9  mov     r8, r12
0x18024f8fc  mov     rax, [r15]
0x18024f8ff  mov     rcx, r15
0x18024f902  mov     rax, [rax+1E0h]
0x18024f909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024f90e  xor     r15d, r15d
0x18024f911  mov     ebx, eax
0x18024f913  test    eax, eax
0x18024f915  js      loc_18024FBB5
0x18024f91b  mov     r8, [rdi+0C8h]
0x18024f922  lea     rax, [rsp+160h+var_118]
0x18024f927  mov     qword ptr [rsp+160h+var_138], rax
0x18024f92c  lea     r13, [rdi+0C0h]
0x18024f933  mov     rax, [r12]
0x18024f937  lea     rcx, [rbp+60h+var_D0]
0x18024f93b  mov     r12d, [rbp+60h+arg_38]
0x18024f942  mov     r9d, r12d
0x18024f945  mov     rdx, [r13+0]
0x18024f949  mov     qword ptr [rsp+160h+var_140], rax
0x18024f94e  call    ?Decode@HardwareJpegHelper@@QEAAJPEAUID3D11DeviceContext1@@PEAUID3D11ImageContext@@W4Enum@LockStatus@@PEAUID3D11Query1@@PEAPEAUIDXGISurface@@@Z; HardwareJpegHelper::Decode(ID3D11DeviceContext1 *,ID3D11ImageContext *,LockStatus::Enum,ID3D11Query1 *,IDXGISurface * *)
0x18024f953  mov     ebx, eax
0x18024f955  test    eax, eax
0x18024f957  js      loc_18024FBB5
0x18024f95d  mov     rbx, [rsp+160h+var_108]
0x18024f962  test    rbx, rbx
0x18024f965  jnz     loc_18024FAC2
0x18024f96b  xor     r9d, r9d; lpName
0x18024f96e  xor     r8d, r8d; bInitialState
0x18024f971  xor     edx, edx; bManualReset
0x18024f973  xor     ecx, ecx; lpEventAttributes
0x18024f975  call    cs:__imp_CreateEventW
0x18024f97b  xor     ecx, ecx; dwErrCode
0x18024f97d  mov     r13, rax
0x18024f980  call    cs:__imp_SetLastError
0x18024f986  test    r13, r13
0x18024f989  jnz     short loc_18024F9B1
0x18024f98b  call    cs:__imp_GetLastError
0x18024f991  mov     ebx, eax
0x18024f993  test    eax, eax
0x18024f995  jle     short loc_18024F9A0
0x18024f997  movzx   ebx, ax
0x18024f99a  or      ebx, 80070000h
0x18024f9a0  test    ebx, ebx
0x18024f9a2  mov     eax, 88990019h
0x18024f9a7  cmovns  ebx, eax
0x18024f9aa  mov     ecx, ebx
0x18024f9ac  jmp     loc_18024FBB7
0x18024f9b1  mov     ebx, r15d
0x18024f9b4  cmp     r12d, 1
0x18024f9b8  jnz     short loc_18024F9E3
0x18024f9ba  lea     r15, [rdi+10h]
0x18024f9be  mov     rax, r15
0x18024f9c1  neg     rax
0x18024f9c4  sbb     rcx, rcx
0x18024f9c7  and     rcx, rdi
0x18024f9ca  mov     rax, [rcx+10h]
0x18024f9ce  test    rax, rax
0x18024f9d1  lea     rcx, [rax+8]
0x18024f9d5  lea     eax, [r12+0Fh]
0x18024f9da  cmovz   rcx, rax
0x18024f9de  mov     rdx, [rcx]
0x18024f9e1  jmp     short loc_18024F9EA
0x18024f9e3  mov     rdx, r15
0x18024f9e6  lea     r15, [rdi+10h]
0x18024f9ea  lea     rcx, [rsp+160h+var_108]
0x18024f9ef  call    ??0?$CGuard@VAbstractLock@@@@QEAA@PEAVAbstractLock@@@Z; CGuard<AbstractLock>::CGuard<AbstractLock>(AbstractLock *)
0x18024f9f4  mov     rcx, [rdi+0C0h]
0x18024f9fb  mov     r8, r13
0x18024f9fe  mov     edx, 5
0x18024fa03  mov     rax, [rcx]
0x18024fa06  mov     rax, [rax+480h]
0x18024fa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024fa12  lea     rcx, [rsp+160h+var_108]
0x18024fa17  call    ??1?$CGuard@VAbstractLock@@@@QEAA@XZ; CGuard<AbstractLock>::~CGuard<AbstractLock>(void)
0x18024fa1c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18024fa1f  mov     rcx, r13; hHandle
0x18024fa22  call    cs:__imp_WaitForSingleObject
0x18024fa28  test    eax, eax
0x18024fa2a  jz      short loc_18024FA4B
0x18024fa2c  call    cs:__imp_GetLastError
0x18024fa32  mov     ebx, eax
0x18024fa34  test    eax, eax
0x18024fa36  jle     short loc_18024FA41
0x18024fa38  movzx   ebx, ax
0x18024fa3b  or      ebx, 80070000h
0x18024fa41  test    ebx, ebx
0x18024fa43  mov     eax, 88990019h
0x18024fa48  cmovns  ebx, eax
0x18024fa4b  mov     rcx, r13; hObject
0x18024fa4e  call    cs:__imp_CloseHandle
0x18024fa54  test    ebx, ebx
0x18024fa56  js      loc_18024F9AA
0x18024fa5c  cmp     r12d, 1
0x18024fa60  jnz     short loc_18024FA87
0x18024fa62  neg     r15
0x18024fa65  sbb     rax, rax
0x18024fa68  xor     r15d, r15d
0x18024fa6b  and     rax, rdi
0x18024fa6e  mov     rcx, [rax+10h]
0x18024fa72  test    rcx, rcx
0x18024fa75  lea     rax, [rcx+8]
0x18024fa79  lea     ecx, [r12+0Fh]
0x18024fa7e  cmovz   rax, rcx
0x18024fa82  mov     rdx, [rax]
0x18024fa85  jmp     short loc_18024FA8D
0x18024fa87  xor     r15d, r15d
0x18024fa8a  mov     edx, r15d
0x18024fa8d  lea     rcx, [rsp+160h+var_120]
0x18024fa92  call    ??0?$CGuard@VAbstractLock@@@@QEAA@PEAVAbstractLock@@@Z; CGuard<AbstractLock>::CGuard<AbstractLock>(AbstractLock *)
0x18024fa97  mov     rcx, rdi; this
0x18024fa9a  call    ?CheckQuerySuccess@D2DImageSourceFromWicHardware@@AEBAJXZ; D2DImageSourceFromWicHardware::CheckQuerySuccess(void)
0x18024fa9f  mov     ebx, eax
0x18024faa1  test    eax, eax
0x18024faa3  jns     short loc_18024FABB
0x18024faa5  mov     ecx, eax; int
0x18024faa7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18024faac  lea     rcx, [rsp+160h+var_120]
0x18024fab1  call    ??1?$CGuard@VAbstractLock@@@@QEAA@XZ; CGuard<AbstractLock>::~CGuard<AbstractLock>(void)
0x18024fab6  jmp     loc_18024FBED
0x18024fabb  lea     rcx, [rsp+160h+var_120]
0x18024fac0  jmp     short loc_18024FB1E
0x18024fac2  cmp     r12d, 1
0x18024fac6  jnz     short loc_18024FAF1
0x18024fac8  lea     r15, [rdi+10h]
0x18024facc  neg     r15
0x18024facf  sbb     rax, rax
0x18024fad2  xor     r15d, r15d
0x18024fad5  and     rax, rdi
0x18024fad8  mov     rcx, [rax+10h]
0x18024fadc  test    rcx, rcx
0x18024fadf  lea     rax, [rcx+8]
  ... truncated ...
```
