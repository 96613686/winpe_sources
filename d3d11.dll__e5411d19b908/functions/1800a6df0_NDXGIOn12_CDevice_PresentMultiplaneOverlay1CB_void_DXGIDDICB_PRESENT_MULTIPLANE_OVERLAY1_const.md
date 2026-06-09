# NDXGIOn12::CDevice::PresentMultiplaneOverlay1CB(void *,DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 const *)

- ea: `0x1800a6df0`
- end: `0x1800a731f`
- name: `?PresentMultiplaneOverlay1CB@CDevice@NDXGIOn12@@SAJPEAXPEBUDXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1@@@Z`
- size: `1327`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, const struct DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800147d0`
- `0x180021b90`
- `0x180022400`
- `0x180022630`
- `0x180034550`
- `0x180035e3c`
- `0x18005ec80`
- `0x18005edd4`
- `0x180070520`
- `0x1800a6df0`
- `0x1800a7328`
- `0x1800a9d20`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a726d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a726d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6f50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6f50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a6ee4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a6ee4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a7267`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a7267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a72b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a72b0`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTPresentMultiPlaneOverlay3` at `0x1800a71c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NDXGIOn12::CDevice::PresentMultiplaneOverlay1CB(
        NDXGI::CDevice *this,
        const struct DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 *a2)
{
  __int64 v4; // r8
  __int64 (__fastcall **v5)(__int64, GUID *, __int64); // r9
  __int64 v6; // r10
  int v7; // eax
  __int64 v8; // rdx
  signed int v9; // ebx
  _com_error *v10; // r13
  _com_error *v11; // rdx
  __int64 v12; // r8
  __int64 *v13; // r9
  __int64 v14; // r10
  char *v15; // r14
  _com_error *v16; // rsi
  __int64 v17; // rcx
  char v18; // r9
  unsigned int i; // eax
  struct ID3D11Device *v20; // rcx
  int lpVtbl; // eax
  struct ID3D11Device *v22; // r13
  unsigned int v23; // r12d
  _QWORD *v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  _QWORD **v27; // rax
  _BYTE *v29; // rdx
  _BYTE *v30; // rdx
  _BYTE v31[32]; // [rsp+0h] [rbp-1F8h] BYREF
  char v32; // [rsp+30h] [rbp-1C8h]
  bool v33; // [rsp+31h] [rbp-1C7h] BYREF
  bool v34; // [rsp+32h] [rbp-1C6h] BYREF
  char v35; // [rsp+33h] [rbp-1C5h]
  char v36; // [rsp+34h] [rbp-1C4h]
  signed int v37; // [rsp+38h] [rbp-1C0h]
  __int64 v38; // [rsp+40h] [rbp-1B8h]
  struct ID3D11Device *v39; // [rsp+48h] [rbp-1B0h]
  __int64 v40; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v41; // [rsp+58h] [rbp-1A0h] BYREF
  _QWORD *v42; // [rsp+60h] [rbp-198h]
  _com_error *v43; // [rsp+68h] [rbp-190h] BYREF
  _com_error *v44; // [rsp+70h] [rbp-188h]
  __int64 v45; // [rsp+78h] [rbp-180h]
  char *v46; // [rsp+80h] [rbp-178h] BYREF
  _com_error *v47[3]; // [rsp+88h] [rbp-170h] BYREF
  void **pExceptionObject; // [rsp+A0h] [rbp-158h] BYREF
  int v49; // [rsp+A8h] [rbp-150h]
  __int128 v50; // [rsp+B0h] [rbp-148h]
  _DWORD v51[64]; // [rsp+C0h] [rbp-138h] BYREF

  v41 = 0;
  v4 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v41);
  v7 = (*v5)(v6, &GUID_36871736_2446_4858_8473_99bd44555307, v4);
  ThrowFailure(v7);
  if ( !(*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 2) + 328LL))((char *)this + 16) )
  {
    v9 = -2147467263;
    goto LABEL_75;
  }
  v45 = *((_QWORD *)a2 + 2);
  v37 = *((_DWORD *)a2 + 2);
  v10 = *(_com_error **)a2;
  v44 = v10;
  v38 = 0;
  v47[1] = this;
  v47[2] = v10;
  v42 = (_QWORD *)((char *)this + 72);
  LOBYTE(v8) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*((_QWORD *)this + 9), v8, 4) )
  {
    v15 = (char *)this + 1920;
    v39 = (struct ID3D11Device *)((char *)this + 1920);
    v46 = (char *)this + 1920;
    EnterCriticalSection((LPCRITICAL_SECTION)this + 48);
    v43 = v10;
    std::_Tree<std::_Tmap_traits<unsigned __int64,BatchablePresentMPO,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,BatchablePresentMPO>>,0>>::find(
      (char *)this + 1960,
      &v40,
      &v43);
    try
    {
      if ( v40 == *((_QWORD *)this + 245) )
      {
        pExceptionObject = &_com_error::`vftable';
        v49 = -2147024809;
        v50 = 0;
        throw (_com_error *)&pExceptionObject;
      }
      v16 = *(_com_error **)(v40 + 40);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 48);
      v13 = (__int64 *)((char *)this + 72);
      v14 = v45;
    }
    catch ( _com_error *v47 )
    {
      v29 = v31;
      v37 = *((_DWORD *)v47[0] + 2);
      LOBYTE(v29) = 9;
      if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*v42, v29, 4) )
        NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v39, v44);
      v9 = v37;
      goto LABEL_75;
    }
    catch ( std::bad_alloc )
    {
      v30 = v31;
      LOBYTE(v30) = 9;
      if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*v42, v30, 4) )
        NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v39, v44);
      v9 = -2147024882;
      goto LABEL_75;
    }
  }
  else
  {
    v16 = v10;
    v15 = (char *)this + 1920;
  }
  if ( v37 != *((_DWORD *)v16 + 7) )
  {
    v17 = *v13;
LABEL_39:
    LOBYTE(v11) = 9;
    if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v17, v11, 4) )
      NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v15, v10);
    v9 = -2147024809;
    goto LABEL_75;
  }
  *((_QWORD *)v16 + 1) = v51;
  *((_DWORD *)v16 + 1) = 0;
  v18 = 1;
  v35 = 1;
  v36 = 0;
  LOBYTE(v12) = 0;
  v32 = 0;
  for ( i = 0; ; i = v37 + 1 )
  {
    v37 = i;
    if ( i >= *((_DWORD *)v16 + 7) )
      break;
    v11 = *(_com_error **)(*((_QWORD *)v16 + 4) + 8LL * i);
    v43 = v11;
    v20 = *(struct ID3D11Device **)(v14 + 8LL * i);
    v39 = v20;
    if ( (*((_BYTE *)v11 + 4) & 1) != 0 )
    {
      if ( LODWORD(v20->lpVtbl) > 0x40 )
      {
        v17 = *v42;
        goto LABEL_39;
      }
      *((struct ID3D11Device *)v11 + 3) = v20[2];
      *((_DWORD *)v11 + 4) = v20->lpVtbl;
      if ( v18 )
      {
        v35 = 0;
        LODWORD(v40) = 0;
        lpVtbl = (int)v20->lpVtbl;
        if ( LODWORD(v20->lpVtbl) )
        {
          v22 = v20;
          v23 = 0;
          do
          {
            v51[v23] = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v41 + 176LL))(
                         v41,
                         *((_QWORD *)&v22[1].lpVtbl->QueryInterface + v23),
                         v12);
            ++v23;
            lpVtbl = (int)v22->lpVtbl;
          }
          while ( v23 < LODWORD(v22->lpVtbl) );
          v10 = v44;
          v20 = v39;
          v11 = v43;
          LOBYTE(v12) = v32;
        }
        *((_DWORD *)v16 + 1) = lpVtbl;
      }
      if ( (*((_BYTE *)v16 + 24) & 0x40) == 0 )
      {
        v33 = 0;
        v34 = 0;
        v9 = NDXGI::CDevice::HandleMPOSyncIntervalOverride(
               v20,
               &v33,
               &v34,
               v11,
               (struct DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *)v20);
        LODWORD(v38) = v9;
        if ( v9 < 0 )
        {
          v25 = *v42;
          goto LABEL_73;
        }
        if ( v33 )
        {
          if ( v34 )
          {
            v36 = 1;
            goto LABEL_32;
          }
          LOBYTE(v12) = 1;
          v32 = 1;
        }
        else
        {
LABEL_32:
          LOBYTE(v12) = v32;
        }
      }
      v20 = v39;
      v11 = v43;
      v18 = v35;
      v14 = v45;
      goto LABEL_36;
    }
    *((_QWORD *)v11 + 3) = 0;
    *((_DWORD *)v11 + 4) = 0;
LABEL_36:
    *((_DWORD *)v11 + 8) = v20[3].lpVtbl;
    *((struct ID3D11Device *)v11 + 5) = v20[4];
  }
  if ( v36 )
  {
    *((_DWORD *)v16 + 6) |= 0x200u;
  }
  else if ( (_BYTE)v12 )
  {
    *((_DWORD *)v16 + 6) &= ~0x200u;
  }
  if ( !*((_DWORD *)v16 + 1) )
  {
    *((_DWORD *)v16 + 1) = 1;
    v51[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v41 + 176LL))(
               v41,
               **(_QWORD **)(*(_QWORD *)v14 + 8LL),
               v12);
  }
  v26 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
          D3DKMTPresentMultiPlaneOverlay3,
          "PresentMultiplaneOverlay2",
          v16);
  HIDWORD(v38) = v26;
  if ( v26 > -1071775737 )
  {
    if ( v26 != -1071775733 )
    {
      if ( v26 == -1071775731 )
      {
        HIDWORD(v38) = 0;
        goto LABEL_55;
      }
      if ( v26 == -1071775720 || v26 == -1071774910 )
      {
LABEL_55:
        v9 = *((int *)this + 312) < 0 ? 0x88760870 : 0;
LABEL_64:
        LODWORD(v38) = v9;
        goto LABEL_65;
      }
      if ( v26 != 259 )
        goto LABEL_61;
    }
    v9 = 0;
    goto LABEL_64;
  }
  if ( v26 == -1071775737
    || v26 != -1073741811 && v26 != -1073741795 && (v26 == -1071775744 || v26 == -1071775739 || v26 == -1071775738) )
  {
    goto LABEL_55;
  }
LABEL_61:
  v9 = NDXGI::CDevice::NTStatusToHResult(this, v26);
  LODWORD(v38) = v9;
LABEL_65:
  AcquireSRWLockShared((PSRWLOCK)this + 167);
  LODWORD(v40) = GetCurrentThreadId();
  v27 = (_QWORD **)std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
                     (char *)this + 1344,
                     &v46,
                     &v40);
  v24 = *v27;
  if ( *v27 != *((_QWORD **)this + 169) )
  {
    v24 = (_QWORD *)v24[3];
    *v24 = v38;
  }
  if ( this != (NDXGI::CDevice *)-1336LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 167);
  if ( v9 == -2005532132 || v9 == -2005530512 )
    v9 = 0;
  v25 = *((_QWORD *)this + 9);
LABEL_73:
  LOBYTE(v24) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v25, v24, 4) )
    NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v15, v10);
LABEL_75:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a6df0  mov     [rsp+arg_10], rbx
0x1800a6df5  mov     [rsp+arg_18], rsi
0x1800a6dfa  push    rdi
0x1800a6dfb  push    r12
0x1800a6dfd  push    r13
0x1800a6dff  push    r14
0x1800a6e01  push    r15
0x1800a6e03  sub     rsp, 1D0h
0x1800a6e0a  mov     rax, cs:__security_cookie
0x1800a6e11  xor     rax, rsp
0x1800a6e14  mov     [rsp+1F8h+var_38], rax
0x1800a6e1c  mov     r13, rdx
0x1800a6e1f  mov     r15, rcx
0x1800a6e22  xor     edi, edi
0x1800a6e24  mov     [rsp+1F8h+var_1A0], rdi
0x1800a6e29  mov     r10, [rcx+828h]
0x1800a6e30  mov     r9, [r10]
0x1800a6e33  lea     rcx, [rsp+1F8h+var_1A0]
0x1800a6e38  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a6e3d  mov     r8, rax
0x1800a6e40  lea     rdx, _GUID_36871736_2446_4858_8473_99bd44555307
0x1800a6e47  mov     rcx, r10
0x1800a6e4a  mov     rax, [r9]
0x1800a6e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e52  mov     ecx, eax; int
0x1800a6e54  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a6e59  lea     rcx, [r15+10h]
0x1800a6e5d  mov     rax, [rcx]
0x1800a6e60  mov     rax, [rax+148h]
0x1800a6e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e6c  test    eax, eax
0x1800a6e6e  jnz     short loc_1800A6E7A
0x1800a6e70  mov     ebx, 80004001h
0x1800a6e75  jmp     loc_1800A72E6
0x1800a6e7a  mov     r10, [r13+10h]
0x1800a6e7e  mov     [rsp+1F8h+var_180], r10
0x1800a6e83  mov     eax, [r13+8]
0x1800a6e87  mov     [rsp+1F8h+var_1C0], eax
0x1800a6e8b  mov     r13, [r13+0]
0x1800a6e8f  mov     [rsp+1F8h+var_188], r13
0x1800a6e94  mov     [rsp+1F8h+var_1B8], rdi
0x1800a6e99  mov     [rsp+1F8h+var_168], r15
0x1800a6ea1  mov     [rsp+1F8h+var_160], r13
0x1800a6ea9  lea     r9, [r15+48h]
0x1800a6ead  mov     [rsp+1F8h+var_198], r9
0x1800a6eb2  mov     r12d, 4
0x1800a6eb8  mov     r8d, r12d
0x1800a6ebb  mov     dl, 9
0x1800a6ebd  mov     rcx, [r9]
0x1800a6ec0  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800a6ec5  test    al, al
0x1800a6ec7  jz      loc_1800A6FC5
0x1800a6ecd  lea     r14, [r15+780h]
0x1800a6ed4  mov     [rsp+1F8h+var_1B0], r14
0x1800a6ed9  mov     [rsp+1F8h+var_178], r14
0x1800a6ee1  mov     rcx, r14; lpCriticalSection
0x1800a6ee4  call    cs:__imp_EnterCriticalSection
0x1800a6eea  nop
0x1800a6eeb  mov     [rsp+1F8h+var_190], r13
0x1800a6ef0  lea     r8, [rsp+1F8h+var_190]
0x1800a6ef5  lea     rdx, [rsp+1F8h+var_1A8]
0x1800a6efa  lea     rcx, [r14+28h]
0x1800a6efe  call    ?find@?$_Tree@V?$_Tmap_traits@_KUBatchablePresentMPO@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUBatchablePresentMPO@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUBatchablePresentMPO@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,BatchablePresentMPO,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,BatchablePresentMPO>>,0>>::find(unsigned __int64 const &)
0x1800a6f03  mov     rdx, [rsp+1F8h+var_1A8]
0x1800a6f08  cmp     rdx, [r14+28h]
0x1800a6f0c  jnz     short loc_1800A6F49
0x1800a6f0e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800a6f15  mov     [rsp+1F8h+pExceptionObject], rax
0x1800a6f1d  mov     ebx, 80070057h
0x1800a6f22  mov     [rsp+1F8h+var_150], ebx
0x1800a6f29  xorps   xmm0, xmm0
0x1800a6f2c  movdqu  [rsp+1F8h+var_148], xmm0
0x1800a6f35  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800a6f3c  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x1800a6f44  call    _CxxThrowException_0
0x1800a6f49  mov     rsi, [rdx+28h]
0x1800a6f4d  mov     rcx, r14; lpCriticalSection
0x1800a6f50  call    cs:__imp_LeaveCriticalSection
0x1800a6f56  nop
0x1800a6f57  lea     r9, [r15+48h]
0x1800a6f5b  mov     r10, [rsp+1F8h+var_180]
0x1800a6f60  jmp     short loc_1800A6FCF
0x1800a6f62  mov     r8d, 4
0x1800a6f68  mov     dl, 9
0x1800a6f6a  mov     rcx, [rsp+1F8h+var_198]
0x1800a6f6f  mov     rcx, [rcx]
0x1800a6f72  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800a6f77  test    al, al
0x1800a6f79  jz      short loc_1800A6F8A
0x1800a6f7b  mov     rdx, [rsp+1F8h+var_188]
0x1800a6f80  mov     rcx, [rsp+1F8h+var_1B0]
0x1800a6f85  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800a6f8a  mov     ebx, 8007000Eh
0x1800a6f8f  jmp     loc_1800A72E6
0x1800a6f94  mov     r8d, 4
0x1800a6f9a  mov     dl, 9
0x1800a6f9c  mov     rcx, [rsp+1F8h+var_198]
0x1800a6fa1  mov     rcx, [rcx]
0x1800a6fa4  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800a6fa9  test    al, al
0x1800a6fab  jz      short loc_1800A6FBC
0x1800a6fad  mov     rdx, [rsp+1F8h+var_188]
0x1800a6fb2  mov     rcx, [rsp+1F8h+var_1B0]
0x1800a6fb7  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800a6fbc  mov     ebx, [rsp+1F8h+var_1C0]
0x1800a6fc0  jmp     loc_1800A72E6
0x1800a6fc5  mov     rsi, r13
0x1800a6fc8  lea     r14, [r15+780h]
0x1800a6fcf  mov     eax, [rsp+1F8h+var_1C0]
0x1800a6fd3  cmp     eax, [rsi+1Ch]
0x1800a6fd6  jz      short loc_1800A6FE0
0x1800a6fd8  mov     rcx, [r9]
0x1800a6fdb  jmp     loc_1800A7152
0x1800a6fe0  lea     rax, [rsp+1F8h+var_138]
0x1800a6fe8  mov     [rsi+8], rax
0x1800a6fec  mov     [rsi+4], edi
0x1800a6fef  mov     r9b, 1
0x1800a6ff2  mov     [rsp+1F8h+var_1C5], r9b
0x1800a6ff7  mov     [rsp+1F8h+var_1C4], dil
0x1800a6ffc  mov     r8b, dil
0x1800a6fff  mov     [rsp+1F8h+var_1C8], dil
0x1800a7004  mov     eax, edi
0x1800a7006  mov     [rsp+1F8h+var_1C0], eax
0x1800a700a  cmp     eax, [rsi+1Ch]
0x1800a700d  jnb     loc_1800A7175
0x1800a7013  mov     ecx, eax
0x1800a7015  mov     rax, [rsi+20h]
0x1800a7019  mov     rdx, [rax+rcx*8]
0x1800a701d  mov     [rsp+1F8h+var_190], rdx
0x1800a7022  mov     rcx, [r10+rcx*8]
0x1800a7026  mov     [rsp+1F8h+var_1B0], rcx
0x1800a702b  test    byte ptr [rdx+4], 1
0x1800a702f  jz      loc_1800A711D
0x1800a7035  cmp     dword ptr [rcx], 40h ; '@'
0x1800a7038  ja      loc_1800A714A
0x1800a703e  mov     rax, [rcx+10h]
0x1800a7042  mov     [rdx+18h], rax
0x1800a7046  mov     eax, [rcx]
0x1800a7048  mov     [rdx+10h], eax
0x1800a704b  test    r9b, r9b
0x1800a704e  jz      short loc_1800A70B4
0x1800a7050  mov     [rsp+1F8h+var_1C5], dil
0x1800a7055  mov     dword ptr [rsp+1F8h+var_1A8], edi
0x1800a7059  mov     eax, [rcx]
0x1800a705b  test    eax, eax
0x1800a705d  jz      short loc_1800A70B1
0x1800a705f  mov     r13, rcx
0x1800a7062  mov     r12d, edi
0x1800a7065  mov     rcx, [rsp+1F8h+var_1A0]
0x1800a706a  mov     ebx, r12d
0x1800a706d  mov     rax, [rcx]
0x1800a7070  mov     rdx, [r13+8]
0x1800a7074  mov     rdx, [rdx+rbx*8]
0x1800a7078  mov     rax, [rax+0B0h]
0x1800a707f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7084  mov     [rsp+rbx*4+1F8h+var_138], eax
0x1800a708b  inc     r12d
0x1800a708e  mov     eax, [r13+0]
0x1800a7092  cmp     r12d, eax
0x1800a7095  jb      short loc_1800A7065
0x1800a7097  mov     r12d, 4
0x1800a709d  mov     r13, [rsp+1F8h+var_188]
0x1800a70a2  mov     rcx, [rsp+1F8h+var_1B0]; struct ID3D11Device *
0x1800a70a7  mov     rdx, [rsp+1F8h+var_190]
0x1800a70ac  mov     r8b, [rsp+1F8h+var_1C8]
0x1800a70b1  mov     [rsi+4], eax
0x1800a70b4  test    byte ptr [rsi+18h], 40h
0x1800a70b8  jnz     short loc_1800A70FD
0x1800a70ba  mov     [rsp+1F8h+var_1C7], dil
0x1800a70bf  mov     [rsp+1F8h+var_1C6], dil
0x1800a70c4  mov     [rsp+1F8h+var_1D8], rcx; struct DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *
0x1800a70c9  mov     r9, rdx; struct _D3DKMT_MULTIPLANE_OVERLAY3 *
0x1800a70cc  lea     r8, [rsp+1F8h+var_1C6]; bool *
0x1800a70d1  lea     rdx, [rsp+1F8h+var_1C7]; bool *
0x1800a70d6  call    ?HandleMPOSyncIntervalOverride@CDevice@NDXGI@@KAJPEAUID3D11Device@@PEA_N1PEAU_D3DKMT_MULTIPLANE_OVERLAY3@@PEAUDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO@@@Z; NDXGI::CDevice::HandleMPOSyncIntervalOverride(ID3D11Device *,bool *,bool *,_D3DKMT_MULTIPLANE_OVERLAY3 *,DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *)
0x1800a70db  mov     ebx, eax
0x1800a70dd  mov     dword ptr [rsp+1F8h+var_1B8], eax
0x1800a70e1  test    eax, eax
0x1800a70e3  js      short loc_1800A713D
0x1800a70e5  cmp     [rsp+1F8h+var_1C7], dil
0x1800a70ea  jz      short loc_1800A70F8
0x1800a70ec  cmp     [rsp+1F8h+var_1C6], dil
0x1800a70f1  jz      short loc_1800A7113
0x1800a70f3  mov     [rsp+1F8h+var_1C4], 1
0x1800a70f8  mov     r8b, [rsp+1F8h+var_1C8]
0x1800a70fd  mov     rcx, [rsp+1F8h+var_1B0]
0x1800a7102  mov     rdx, [rsp+1F8h+var_190]
0x1800a7107  mov     r9b, [rsp+1F8h+var_1C5]
0x1800a710c  mov     r10, [rsp+1F8h+var_180]
0x1800a7111  jmp     short loc_1800A7124
0x1800a7113  mov     r8b, 1
0x1800a7116  mov     [rsp+1F8h+var_1C8], r8b
0x1800a711b  jmp     short loc_1800A70FD
0x1800a711d  mov     [rdx+18h], rdi
0x1800a7121  mov     [rdx+10h], edi
0x1800a7124  mov     eax, [rcx+18h]
0x1800a7127  mov     [rdx+20h], eax
0x1800a712a  mov     rax, [rcx+20h]
0x1800a712e  mov     [rdx+28h], rax
0x1800a7132  mov     eax, [rsp+1F8h+var_1C0]
0x1800a7136  inc     eax
0x1800a7138  jmp     loc_1800A7006
0x1800a713d  mov     rcx, [rsp+1F8h+var_198]
0x1800a7142  mov     rcx, [rcx]
0x1800a7145  jmp     loc_1800A72CC
0x1800a714a  mov     rcx, [rsp+1F8h+var_198]
0x1800a714f  mov     rcx, [rcx]
0x1800a7152  mov     r8d, r12d
0x1800a7155  mov     dl, 9
0x1800a7157  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800a715c  test    al, al
0x1800a715e  jz      short loc_1800A716B
0x1800a7160  mov     rdx, r13
0x1800a7163  mov     rcx, r14
0x1800a7166  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800a716b  mov     ebx, 80070057h
0x1800a7170  jmp     loc_1800A72E6
0x1800a7175  cmp     [rsp+1F8h+var_1C4], dil
0x1800a717a  jz      short loc_1800A7183
0x1800a717c  bts     dword ptr [rsi+18h], 9
0x1800a7181  jmp     short loc_1800A718D
0x1800a7183  test    r8b, r8b
0x1800a7186  jz      short loc_1800A718D
0x1800a7188  btr     dword ptr [rsi+18h], 9
0x1800a718d  cmp     [rsi+4], edi
0x1800a7190  jnz     short loc_1800A71BE
0x1800a7192  mov     dword ptr [rsi+4], 1
0x1800a7199  mov     rcx, [rsp+1F8h+var_1A0]
0x1800a719e  mov     r9, [rcx]
0x1800a71a1  mov     rax, [r10]
0x1800a71a4  mov     rdx, [rax+8]
0x1800a71a8  mov     rdx, [rdx]
0x1800a71ab  mov     rax, [r9+0B0h]
0x1800a71b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71b7  mov     [rsp+1F8h+var_138], eax
0x1800a71be  mov     r8, rsi
0x1800a71c1  lea     rdx, aPresentmultipl; "PresentMultiplaneOverlay2"
0x1800a71c8  mov     rcx, cs:__imp_D3DKMTPresentMultiPlaneOverlay3
0x1800a71cf  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEBDPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),char const *,_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *)
0x1800a71d4  mov     dword ptr [rsp+1F8h+var_1B8+4], eax
0x1800a71d8  mov     ecx, 0C01E0007h
0x1800a71dd  cmp     eax, ecx
0x1800a71df  jg      short loc_1800A721C
0x1800a71e1  jz      short loc_1800A7206
0x1800a71e3  cmp     eax, 0C000000Dh
0x1800a71e8  jz      short loc_1800A723F
0x1800a71ea  cmp     eax, 0C000001Dh
0x1800a71ef  jz      short loc_1800A723F
0x1800a71f1  cmp     eax, 0C01E0000h
0x1800a71f6  jz      short loc_1800A7206
0x1800a71f8  cmp     eax, 0C01E0005h
0x1800a71fd  jz      short loc_1800A7206
0x1800a71ff  cmp     eax, 0C01E0006h
0x1800a7204  jnz     short loc_1800A723F
0x1800a7206  mov     eax, [r15+4E0h]
0x1800a720d  shr     eax, 1Fh
0x1800a7210  neg     al
0x1800a7212  sbb     ebx, ebx
0x1800a7214  and     ebx, 88760870h
0x1800a721a  jmp     short loc_1800A7259
0x1800a721c  cmp     eax, 0C01E000Bh
0x1800a7221  jz      short loc_1800A7257
0x1800a7223  cmp     eax, 0C01E000Dh
0x1800a7228  jz      short loc_1800A7251
0x1800a722a  cmp     eax, 0C01E0018h
0x1800a722f  jz      short loc_1800A7206
0x1800a7231  cmp     eax, 0C01E0342h
0x1800a7236  jz      short loc_1800A7206
0x1800a7238  cmp     eax, 103h
0x1800a723d  jz      short loc_1800A7257
0x1800a723f  mov     edx, eax; int
0x1800a7241  mov     rcx, r15; this
0x1800a7244  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x1800a7249  mov     ebx, eax
0x1800a724b  mov     dword ptr [rsp+1F8h+var_1B8], eax
0x1800a724f  jmp     short loc_1800A725D
0x1800a7251  mov     dword ptr [rsp+1F8h+var_1B8+4], edi
0x1800a7255  jmp     short loc_1800A7206
0x1800a7257  mov     ebx, edi
0x1800a7259  mov     dword ptr [rsp+1F8h+var_1B8], ebx
0x1800a725d  lea     rsi, [r15+538h]
0x1800a7264  mov     rcx, rsi; SRWLock
0x1800a7267  call    cs:__imp_AcquireSRWLockShared
0x1800a726d  call    cs:__imp_GetCurrentThreadId
0x1800a7273  mov     dword ptr [rsp+1F8h+var_1A8], eax
0x1800a7277  lea     rcx, [r15+540h]
0x1800a727e  lea     r8, [rsp+1F8h+var_1A8]
0x1800a7283  lea     rdx, [rsp+1F8h+var_178]
0x1800a728b  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x1800a7290  mov     rdx, [rax]
0x1800a7293  cmp     rdx, [r15+548h]
0x1800a729a  jz      short loc_1800A72A8
0x1800a729c  mov     rdx, [rdx+18h]
0x1800a72a0  mov     rax, [rsp+1F8h+var_1B8]
0x1800a72a5  mov     [rdx], rax
0x1800a72a8  test    rsi, rsi
0x1800a72ab  jz      short loc_1800A72B6
0x1800a72ad  mov     rcx, rsi; SRWLock
0x1800a72b0  call    cs:__imp_ReleaseSRWLockShared
0x1800a72b6  cmp     ebx, 8876021Ch
  ... truncated ...
```
