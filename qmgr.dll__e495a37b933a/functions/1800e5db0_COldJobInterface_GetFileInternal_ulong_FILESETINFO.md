# COldJobInterface::GetFileInternal(ulong,_FILESETINFO *)

- ea: `0x1800e5db0`
- end: `0x1800e612d`
- name: `?GetFileInternal@COldJobInterface@@UEAAJKPEAU_FILESETINFO@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(COldJobInterface *__hidden this, unsigned int, struct _FILESETINFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a380`
- `0x18000b0f8`
- `0x18000c770`
- `0x18001d530`
- `0x18006c2a4`
- `0x180099fb8`
- `0x1800a3420`
- `0x1800b1bd0`
- `0x1800b1db8`
- `0x1800e5db0`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e5fe2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e5ff4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e5fe2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e5ff4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COldJobInterface::GetFileInternal(
        COldJobInterface *this,
        unsigned int a2,
        struct _FILESETINFO *a3,
        void (*a4)(void))
{
  struct _FILESETINFO *v4; // rbx
  unsigned int v5; // esi
  COldJobInterface *v6; // r14
  unsigned int v7; // r15d
  int v8; // ecx
  CFile *v9; // rax
  CFile *v10; // rdi
  int LocalName; // ecx
  int RemoteName; // ecx
  OLECHAR *v13; // r12
  OLECHAR *v14; // r13
  BSTR v15; // rax
  DWORD BytesTotal; // ecx
  struct _FILESETINFO *v18; // rbx
  unsigned int v19; // [rsp+40h] [rbp-318h]
  OLECHAR *psz; // [rsp+50h] [rbp-308h] BYREF
  OLECHAR *v22; // [rsp+58h] [rbp-300h] BYREF
  struct _FILESETINFO *v23; // [rsp+60h] [rbp-2F8h]
  COldJobInterface *v24; // [rsp+68h] [rbp-2F0h]
  _BG_FILE_PROGRESS v25; // [rsp+70h] [rbp-2E8h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-2C8h] BYREF
  __int128 v27; // [rsp+98h] [rbp-2C0h]
  int v28; // [rsp+A8h] [rbp-2B0h]
  int v29; // [rsp+ACh] [rbp-2ACh]
  int v30; // [rsp+B0h] [rbp-2A8h]
  void **v31; // [rsp+F0h] [rbp-268h] BYREF
  __int128 v32; // [rsp+F8h] [rbp-260h]
  int v33; // [rsp+108h] [rbp-250h]
  int v34; // [rsp+10Ch] [rbp-24Ch]
  int v35; // [rsp+110h] [rbp-248h]
  void **v36; // [rsp+150h] [rbp-208h] BYREF
  __int128 v37; // [rsp+158h] [rbp-200h]
  int v38; // [rsp+168h] [rbp-1F0h]
  int v39; // [rsp+16Ch] [rbp-1ECh]
  int v40; // [rsp+170h] [rbp-1E8h]
  void **v41; // [rsp+1B0h] [rbp-1A8h] BYREF
  __int128 v42; // [rsp+1B8h] [rbp-1A0h]
  int v43; // [rsp+1C8h] [rbp-190h]
  int v44; // [rsp+1CCh] [rbp-18Ch]
  int v45; // [rsp+1D0h] [rbp-188h]
  void **v46; // [rsp+210h] [rbp-148h] BYREF
  __int128 v47; // [rsp+218h] [rbp-140h]
  int v48; // [rsp+228h] [rbp-130h]
  int v49; // [rsp+22Ch] [rbp-12Ch]
  int v50; // [rsp+230h] [rbp-128h]
  _QWORD v51[8]; // [rsp+270h] [rbp-E8h] BYREF
  void **v52; // [rsp+2B0h] [rbp-A8h] BYREF
  _DWORD v53[22]; // [rsp+2B8h] [rbp-A0h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v24 = this;
  v23 = a3;
  v7 = 0;
  CLockedJobReadPointer::CLockedJobReadPointer(v51, (_QWORD *)this + 2, (__int64)a3, a4);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_1bb31f0f9f79319249327086e23aeca0_Traceguids, v6, v5, v4);
  try
  {
    psz = 0;
    v22 = 0;
    *(_OWORD *)&v4->bstrRemoteFile = 0;
    *(_QWORD *)&v4->dwSizeHint = 0;
    v8 = CLockedJobReadPointer::ValidateAccess((CLockedJobReadPointer *)v51);
    if ( v8 < 0 )
    {
      v27 = 0;
      pExceptionObject = &ComError::`vftable';
      v28 = v8;
      v29 = 916;
      v30 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v9 = (CFile *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v51[0] + 384LL))(v51[0], v5);
    v10 = v9;
    if ( !v9 )
    {
      v32 = 0;
      v31 = &ComError::`vftable';
      v33 = -2130702332;
      v34 = 0;
      v35 = 1;
      throw (ComError *)&v31;
    }
    LocalName = CFile::GetLocalName(v9, &psz);
    if ( LocalName < 0 )
    {
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = LocalName;
      v39 = 923;
      v40 = 1;
      throw (ComError *)&v36;
    }
    RemoteName = CFile::GetRemoteName(v10, &v22);
    if ( RemoteName < 0 )
    {
      v42 = 0;
      v41 = &ComError::`vftable';
      v43 = RemoteName;
      v44 = 924;
      v45 = 1;
      throw (ComError *)&v41;
    }
    v13 = psz;
    v4->bstrLocalFile = SysAllocString(psz);
    v14 = v22;
    v15 = SysAllocString(v22);
    v4->bstrRemoteFile = v15;
    if ( !v4->bstrLocalFile || !v15 )
    {
      v47 = 0;
      v46 = &ComError::`vftable';
      v48 = -2147024882;
      v49 = 0;
      v50 = 1;
      throw (ComError *)&v46;
    }
    memset(&v25, 0, sizeof(v25));
    CFile::GetProgress(v10, &v25);
    BytesTotal = v25.BytesTotal;
    if ( v25.BytesTotal == -1 )
      BytesTotal = 0;
    v4->dwSizeHint = BytesTotal;
  }
  catch ( ComError v52 )
  {
    v19 = v53[4];
    v18 = v23;
    if ( v23 )
    {
      SysFreeString(v23->bstrLocalFile);
      SysFreeString(v18->bstrRemoteFile);
      *(_OWORD *)&v18->bstrRemoteFile = 0;
      *(_QWORD *)&v18->dwSizeHint = 0;
    }
    v52 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(v53);
    v7 = v19;
    v13 = psz;
    v14 = v22;
    v6 = v24;
    v5 = a2;
    v4 = v23;
  }
  CoTaskMemFree(v13);
  CoTaskMemFree(v14);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_qDDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      WPP_1bb31f0f9f79319249327086e23aeca0_Traceguids,
      v6,
      v7,
      v5,
      v4);
  CLockedReadPointer<CJob,2147483648>::~CLockedReadPointer<CJob,2147483648>((__int64)v51);
  return v7;
}

```

## disassembly

```asm
0x1800e5db0  push    rbx
0x1800e5db2  push    rsi
0x1800e5db3  push    rdi
0x1800e5db4  push    r12
0x1800e5db6  push    r13
0x1800e5db8  push    r14
0x1800e5dba  push    r15
0x1800e5dbc  sub     rsp, 320h
0x1800e5dc3  mov     rax, cs:__security_cookie
0x1800e5dca  xor     rax, rsp
0x1800e5dcd  mov     [rsp+358h+var_48], rax
0x1800e5dd5  mov     rbx, r8
0x1800e5dd8  mov     esi, edx
0x1800e5dda  mov     r14, rcx
0x1800e5ddd  mov     [rsp+358h+var_2F0], rcx
0x1800e5de2  mov     [rsp+358h+var_310], edx
0x1800e5de6  mov     [rsp+358h+var_2F8], rbx
0x1800e5deb  xor     r12d, r12d
0x1800e5dee  mov     r15d, r12d
0x1800e5df1  lea     rdx, [rcx+10h]
0x1800e5df5  lea     rcx, [rsp+358h+var_E8]
0x1800e5dfd  call    ??0CLockedJobReadPointer@@QEAA@AEBV?$ComPtr@VCJob@@@WRL@Microsoft@@@Z; CLockedJobReadPointer::CLockedJobReadPointer(Microsoft::WRL::ComPtr<CJob> const &)
0x1800e5e02  nop
0x1800e5e03  lea     rax, WPP_GLOBAL_Control
0x1800e5e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5e11  cmp     rcx, rax
0x1800e5e14  jz      short loc_1800E5E3D
0x1800e5e16  test    byte ptr [rcx+1Ch], 8
0x1800e5e1a  jz      short loc_1800E5E3D
0x1800e5e1c  lea     edx, [r12+32h]
0x1800e5e21  mov     [rsp+358h+var_330], rbx
0x1800e5e26  mov     [rsp+358h+var_338], esi
0x1800e5e2a  mov     r9, r14
0x1800e5e2d  lea     r8, WPP_1bb31f0f9f79319249327086e23aeca0_Traceguids
0x1800e5e34  mov     rcx, [rcx+10h]
0x1800e5e38  call    WPP_SF_qDq
0x1800e5e3d  mov     [rsp+358h+psz], r12
0x1800e5e42  mov     [rsp+358h+var_300], r12
0x1800e5e47  xorps   xmm0, xmm0
0x1800e5e4a  xor     eax, eax
0x1800e5e4c  movups  xmmword ptr [rbx], xmm0
0x1800e5e4f  mov     [rbx+10h], rax
0x1800e5e53  lea     rcx, [rsp+358h+var_E8]; this
0x1800e5e5b  call    ?ValidateAccess@CLockedJobReadPointer@@QEAAJXZ; CLockedJobReadPointer::ValidateAccess(void)
0x1800e5e60  mov     ecx, eax
0x1800e5e62  test    eax, eax
0x1800e5e64  jns     short loc_1800E5EB1
0x1800e5e66  xorps   xmm0, xmm0
0x1800e5e69  movups  [rsp+358h+var_2C0], xmm0
0x1800e5e71  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e5e78  mov     [rsp+358h+pExceptionObject], rax
0x1800e5e80  mov     [rsp+358h+var_2B0], ecx
0x1800e5e87  mov     [rsp+358h+var_2AC], 394h
0x1800e5e92  mov     [rsp+358h+var_2A8], 1
0x1800e5e9d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e5ea4  lea     rcx, [rsp+358h+pExceptionObject]; pExceptionObject
0x1800e5eac  call    _CxxThrowException_0
0x1800e5eb1  mov     rcx, [rsp+358h+var_E8]
0x1800e5eb9  mov     rax, [rcx]
0x1800e5ebc  mov     edx, esi
0x1800e5ebe  mov     rax, [rax+180h]
0x1800e5ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5eca  mov     rdi, rax
0x1800e5ecd  test    rax, rax
0x1800e5ed0  jnz     short loc_1800E5F1E
0x1800e5ed2  xorps   xmm0, xmm0
0x1800e5ed5  movups  [rsp+358h+var_260], xmm0
0x1800e5edd  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e5ee4  mov     [rsp+358h+var_268], rax
0x1800e5eec  mov     [rsp+358h+var_250], 81001004h
0x1800e5ef7  mov     [rsp+358h+var_24C], r12d
0x1800e5eff  mov     [rsp+358h+var_248], 1
0x1800e5f0a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e5f11  lea     rcx, [rsp+358h+var_268]; pExceptionObject
0x1800e5f19  call    _CxxThrowException_0
0x1800e5f1e  lea     rdx, [rsp+358h+psz]; unsigned __int16 **
0x1800e5f23  mov     rcx, rdi; this
0x1800e5f26  call    ?GetLocalName@CFile@@QEBAJPEAPEAG@Z; CFile::GetLocalName(ushort * *)
0x1800e5f2b  mov     ecx, eax
0x1800e5f2d  test    eax, eax
0x1800e5f2f  jns     short loc_1800E5F7C
0x1800e5f31  xorps   xmm0, xmm0
0x1800e5f34  movups  [rsp+358h+var_200], xmm0
0x1800e5f3c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e5f43  mov     [rsp+358h+var_208], rax
0x1800e5f4b  mov     [rsp+358h+var_1F0], ecx
0x1800e5f52  mov     [rsp+358h+var_1EC], 39Bh
0x1800e5f5d  mov     [rsp+358h+var_1E8], 1
0x1800e5f68  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e5f6f  lea     rcx, [rsp+358h+var_208]; pExceptionObject
0x1800e5f77  call    _CxxThrowException_0
0x1800e5f7c  lea     rdx, [rsp+358h+var_300]; unsigned __int16 **
0x1800e5f81  mov     rcx, rdi; this
0x1800e5f84  call    ?GetRemoteName@CFile@@QEBAJPEAPEAG@Z; CFile::GetRemoteName(ushort * *)
0x1800e5f89  mov     ecx, eax
0x1800e5f8b  test    eax, eax
0x1800e5f8d  jns     short loc_1800E5FDA
0x1800e5f8f  xorps   xmm0, xmm0
0x1800e5f92  movups  [rsp+358h+var_1A0], xmm0
0x1800e5f9a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e5fa1  mov     [rsp+358h+var_1A8], rax
0x1800e5fa9  mov     [rsp+358h+var_190], ecx
0x1800e5fb0  mov     [rsp+358h+var_18C], 39Ch
0x1800e5fbb  mov     [rsp+358h+var_188], 1
0x1800e5fc6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e5fcd  lea     rcx, [rsp+358h+var_1A8]; pExceptionObject
0x1800e5fd5  call    _CxxThrowException_0
0x1800e5fda  mov     r12, [rsp+358h+psz]
0x1800e5fdf  mov     rcx, r12; psz
0x1800e5fe2  call    cs:__imp_SysAllocString
0x1800e5fe8  mov     [rbx+8], rax
0x1800e5fec  mov     r13, [rsp+358h+var_300]
0x1800e5ff1  mov     rcx, r13; psz
0x1800e5ff4  call    cs:__imp_SysAllocString
0x1800e5ffa  mov     [rbx], rax
0x1800e5ffd  cmp     qword ptr [rbx+8], 0
0x1800e6002  jz      short loc_1800E603B
0x1800e6004  test    rax, rax
0x1800e6007  jz      short loc_1800E603B
0x1800e6009  xorps   xmm0, xmm0
0x1800e600c  xor     eax, eax
0x1800e600e  movups  xmmword ptr [rsp+358h+var_2E8.BytesTotal], xmm0
0x1800e6013  mov     qword ptr [rsp+358h+var_2E8.Completed], rax
0x1800e601b  lea     rdx, [rsp+358h+var_2E8]; struct _BG_FILE_PROGRESS *
0x1800e6020  mov     rcx, rdi; this
0x1800e6023  call    ?GetProgress@CFile@@QEBAXPEAU_BG_FILE_PROGRESS@@@Z; CFile::GetProgress(_BG_FILE_PROGRESS *)
0x1800e6028  mov     rcx, [rsp+358h+var_2E8.BytesTotal]
0x1800e602d  xor     eax, eax
0x1800e602f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e6033  cmovz   ecx, eax
0x1800e6036  mov     [rbx+10h], ecx
0x1800e6039  jmp     short loc_1800E60A8
0x1800e603b  xorps   xmm0, xmm0
0x1800e603e  movups  [rsp+358h+var_140], xmm0
0x1800e6046  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e604d  mov     [rsp+358h+var_148], rax
0x1800e6055  mov     [rsp+358h+var_130], 8007000Eh
0x1800e6060  mov     [rsp+358h+var_12C], 0
0x1800e606b  mov     [rsp+358h+var_128], 1
0x1800e6076  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e607d  lea     rcx, [rsp+358h+var_148]; pExceptionObject
0x1800e6085  call    _CxxThrowException_0
0x1800e608b  mov     r15d, [rsp+358h+var_318]
0x1800e6090  mov     r12, [rsp+358h+psz]
0x1800e6095  mov     r13, [rsp+358h+var_300]
0x1800e609a  mov     r14, [rsp+358h+var_2F0]
0x1800e609f  mov     esi, [rsp+358h+var_310]
0x1800e60a3  mov     rbx, [rsp+358h+var_2F8]
0x1800e60a8  lea     rdi, WPP_GLOBAL_Control
0x1800e60af  mov     rcx, r12; pv
0x1800e60b2  call    cs:__imp_CoTaskMemFree
0x1800e60b8  mov     rcx, r13; pv
0x1800e60bb  call    cs:__imp_CoTaskMemFree
0x1800e60c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60c8  cmp     rcx, rdi
0x1800e60cb  jz      short loc_1800E60FA
0x1800e60cd  test    byte ptr [rcx+1Ch], 8
0x1800e60d1  jz      short loc_1800E60FA
0x1800e60d3  mov     edx, 33h ; '3'
0x1800e60d8  mov     [rsp+358h+var_328], rbx
0x1800e60dd  mov     dword ptr [rsp+358h+var_330], esi
0x1800e60e1  mov     [rsp+358h+var_338], r15d
0x1800e60e6  mov     r9, r14
0x1800e60e9  lea     r8, WPP_1bb31f0f9f79319249327086e23aeca0_Traceguids
0x1800e60f0  mov     rcx, [rcx+10h]
0x1800e60f4  call    WPP_SF_qDDq
0x1800e60f9  nop
0x1800e60fa  lea     rcx, [rsp+358h+var_E8]
0x1800e6102  call    ??1?$CLockedReadPointer@VCJob@@$0IAAAAAAA@@@QEAA@XZ; CLockedReadPointer<CJob,2147483648>::~CLockedReadPointer<CJob,2147483648>(void)
0x1800e6107  mov     eax, r15d
0x1800e610a  mov     rcx, [rsp+358h+var_48]
0x1800e6112  xor     rcx, rsp; StackCookie
0x1800e6115  call    __security_check_cookie
0x1800e611a  add     rsp, 320h
0x1800e6121  pop     r15
0x1800e6123  pop     r14
0x1800e6125  pop     r13
0x1800e6127  pop     r12
0x1800e6129  pop     rdi
0x1800e612a  pop     rsi
0x1800e612b  pop     rbx
0x1800e612c  retn
```
