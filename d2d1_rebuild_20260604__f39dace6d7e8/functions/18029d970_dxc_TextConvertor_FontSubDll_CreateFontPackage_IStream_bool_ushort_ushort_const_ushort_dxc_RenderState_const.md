# dxc::TextConvertor::FontSubDll::CreateFontPackage(IStream *,bool,ushort,ushort const *,ushort,dxc::RenderState const *)

- ea: `0x18029d970`
- end: `0x18029db9b`
- name: `?CreateFontPackage@FontSubDll@TextConvertor@dxc@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIStream@@_NGPEBGGPEBURenderState@3@@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18029e2e0`

## callees

- `0x1800172a0`
- `0x180050430`
- `0x1801f7fbc`
- `0x180214888`
- `0x18029d970`
- `0x18029f0dc`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18029da18`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18029da18`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18029dae0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18029dae0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18029daa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18029daa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18029dac6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18029dac6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18029db14`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18029db14`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18029d9ea`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18029d9ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPSTREAM *__fastcall dxc::TextConvertor::FontSubDll::CreateFontPackage(
        __int64 a1,
        LPSTREAM *a2,
        IStream *a3,
        unsigned __int8 a4,
        __int16 a5,
        __int64 a6,
        __int16 a7,
        dxc *a8)
{
  __int16 v8; // r14
  int v12; // eax
  const char *v13; // rdx
  dxc *v14; // rcx
  const char *v15; // r8
  int v16; // r9d
  HRESULT HGlobalFromStream; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  __int64 (__fastcall *v21)(LPVOID, _QWORD, LPCVOID *, __int64 *, unsigned int *, _WORD, __int16, _WORD, _WORD, _WORD, __int16, __int64, __int16, void *(__fastcall *)(dxc *__hidden, unsigned __int64), void *(*)(dxc *__hidden, void *, unsigned __int64), void (__fastcall *)(dxc *__hidden, void *), _QWORD); // r15
  LPVOID v22; // rax
  unsigned int v23; // ebx
  HGLOBAL v24; // rax
  const char *v25; // rdx
  dxc *v26; // rcx
  int v27; // r8d
  void *v28; // rdi
  __int64 v29; // rbx
  const char *v30; // rdx
  dxc *v31; // rcx
  int v32; // r8d
  HRESULT StreamOnHGlobal; // eax
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  int v37; // eax
  int v38; // edx
  const char *v39; // r8
  int v40; // r9d
  const char *v41; // rdx
  dxc *v42; // rcx
  int v43; // r8d
  unsigned int v45; // [rsp+98h] [rbp-19h] BYREF
  int v46; // [rsp+9Ch] [rbp-15h]
  __int64 v47; // [rsp+A0h] [rbp-11h] BYREF
  HGLOBAL phglobal; // [rsp+A8h] [rbp-9h] BYREF
  LPCVOID pMem[7]; // [rsp+B0h] [rbp-1h] BYREF
  __int64 v50; // [rsp+108h] [rbp+57h] BYREF
  unsigned __int8 v51; // [rsp+110h] [rbp+5Fh]

  v51 = a4;
  v8 = a4;
  v46 = 0;
  v50 = 0;
  v47 = 0;
  v12 = (*(__int64 (__fastcall **)(IStream *, _QWORD, __int64, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, 0, 2, &v47);
  if ( v12 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v12, (int)v13, v15, v16);
  if ( HIDWORD(v47) )
    dxc::ThrowLogicException(v14, v13, (int)v15);
  phglobal = 0;
  HGlobalFromStream = GetHGlobalFromStream(a3, &phglobal);
  if ( HGlobalFromStream < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)HGlobalFromStream, v18, v19, v20);
  pMem[0] = 0;
  LODWORD(v50) = 0;
  v45 = 0;
  v21 = *(__int64 (__fastcall **)(LPVOID, _QWORD, LPCVOID *, __int64 *, unsigned int *, _WORD, __int16, _WORD, _WORD, _WORD, __int16, __int64, __int16, void *(__fastcall *)(dxc *__hidden, unsigned __int64), void *(*)(dxc *__hidden, void *, unsigned __int64), void (__fastcall *)(dxc *__hidden, void *), _QWORD))(a1 + 8);
  v22 = GlobalLock(phglobal);
  v23 = v21(
          v22,
          (unsigned int)v47,
          pMem,
          &v50,
          &v45,
          4 * v8 + 9,
          a5,
          0,
          0,
          0,
          -1,
          a6,
          a7,
          dxc::AllocFixedGMem,
          dxc::ReallocFixedGMem,
          dxc::FreeFixedGMem,
          0);
  GlobalUnlock(phglobal);
  *a2 = 0;
  v46 = 1;
  if ( v23 )
  {
    if ( v51 )
    {
      dxc::OutputDebugMessage(a8, (const struct dxc::RenderState *)0x4A9, v23);
      dxc::ThrowLogicException(v42, v41, v43);
    }
    dxc::OutputDebugMessage(a8, (const struct dxc::RenderState *)0x4A8, v23);
    win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(a2, a3);
  }
  else
  {
    v24 = GlobalHandle(pMem[0]);
    v28 = v24;
    if ( !v24 )
      dxc::ThrowLogicException(v26, v25, v27);
    v29 = (unsigned int)v50;
    if ( GlobalSize(v24) != v29 )
      dxc::ThrowLogicException(v31, v30, v32);
    if ( v45 > (unsigned int)v50 )
      dxc::ThrowLogicException(v31, v30, v32);
    win_scope::close<IStream *,win_scope::const_policies<win_scope::com_policies>>(a2);
    *a2 = 0;
    StreamOnHGlobal = CreateStreamOnHGlobal(v28, 1, a2);
    if ( StreamOnHGlobal < 0 )
      dxc::ThrowHRExceptionPage((dxc *)(unsigned int)StreamOnHGlobal, v34, v35, v36);
    if ( v45 < (unsigned int)v50 )
    {
      v37 = (*(__int64 (__fastcall **)(LPSTREAM))(*(_QWORD *)*a2 + 48LL))(*a2);
      if ( v37 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v37, v38, v39, v40);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18029d970  mov     rax, rsp
0x18029d973  mov     [rax+8], rbx
0x18029d977  mov     [rax+20h], r9b
0x18029d97b  mov     [rax+10h], rdx
0x18029d97f  push    rbp
0x18029d980  push    rsi
0x18029d981  push    rdi
0x18029d982  push    r12
0x18029d984  push    r13
0x18029d986  push    r14
0x18029d988  push    r15
0x18029d98a  lea     rbp, [rax-3Fh]
0x18029d98e  sub     rsp, 0B0h
0x18029d995  movzx   r14d, r9b
0x18029d999  mov     r13, r8
0x18029d99c  mov     r12, rdx
0x18029d99f  mov     r15, rcx
0x18029d9a2  xor     esi, esi
0x18029d9a4  mov     [rbp+37h+var_4C], esi
0x18029d9a7  mov     [rbp+37h+arg_10], rsi
0x18029d9ab  mov     [rbp+37h+var_48], rsi
0x18029d9af  mov     rax, [r8]
0x18029d9b2  lea     r9, [rbp+37h+var_48]
0x18029d9b6  lea     r8d, [rsi+2]
0x18029d9ba  mov     edx, esi
0x18029d9bc  mov     rcx, r13
0x18029d9bf  mov     rax, [rax+28h]
0x18029d9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029d9c8  test    eax, eax
0x18029d9ca  jns     short loc_18029D9D4
0x18029d9cc  mov     ecx, eax; this
0x18029d9ce  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x18029d9d4  cmp     dword ptr [rbp+37h+var_48+4], esi
0x18029d9d7  jz      short loc_18029D9DF
0x18029d9d9  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029d9df  mov     [rbp+37h+phglobal], rsi
0x18029d9e3  lea     rdx, [rbp+37h+phglobal]; phglobal
0x18029d9e7  mov     rcx, r13; pstm
0x18029d9ea  call    cs:__imp_GetHGlobalFromStream
0x18029d9f0  test    eax, eax
0x18029d9f2  jns     short loc_18029D9FC
0x18029d9f4  mov     ecx, eax; this
0x18029d9f6  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x18029d9fc  mov     [rbp+37h+pMem], rsi
0x18029da00  mov     dword ptr [rbp+37h+arg_10], esi
0x18029da03  mov     [rbp+37h+var_50], esi
0x18029da06  mov     r15, [r15+8]
0x18029da0a  shl     r14w, 2
0x18029da0f  add     r14w, 9
0x18029da14  mov     rcx, [rbp+37h+phglobal]; hMem
0x18029da18  call    cs:__imp_GlobalLock
0x18029da1e  mov     rcx, rax
0x18029da21  mov     [rsp+80h], rsi
0x18029da29  lea     rax, ?FreeFixedGMem@dxc@@YAXPEAX@Z; dxc::FreeFixedGMem(void *)
0x18029da30  mov     [rsp+0E0h+var_68], rax
0x18029da35  lea     rax, ?ReallocFixedGMem@dxc@@YAPEAXPEAX_K@Z; dxc::ReallocFixedGMem(void *,unsigned __int64)
0x18029da3c  mov     [rsp+0E0h+var_70], rax
0x18029da41  lea     rax, ?AllocFixedGMem@dxc@@YAPEAX_K@Z; dxc::AllocFixedGMem(unsigned __int64)
0x18029da48  mov     [rsp+0E0h+var_78], rax
0x18029da4d  movzx   eax, [rbp+37h+arg_30]
0x18029da51  mov     word ptr [rsp+0E0h+var_80], ax
0x18029da56  mov     rdx, [rbp+37h+arg_28]
0x18029da5a  mov     qword ptr [rsp+0E0h+var_88], rdx
0x18029da5f  mov     word ptr [rsp+0E0h+var_90], 0FFFFh
0x18029da66  mov     [rsp+0E0h+var_98], si
0x18029da6b  mov     [rsp+0E0h+var_A0], si
0x18029da70  mov     [rsp+0E0h+var_A8], si
0x18029da75  movzx   edx, [rbp+37h+arg_20]
0x18029da79  mov     [rsp+0E0h+var_B0], dx
0x18029da7e  mov     [rsp+0E0h+var_B8], r14w
0x18029da84  lea     rax, [rbp+37h+var_50]
0x18029da88  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18029da8d  lea     r9, [rbp+37h+arg_10]
0x18029da91  lea     r8, [rbp+37h+pMem]
0x18029da95  mov     edx, dword ptr [rbp+37h+var_48]
0x18029da98  mov     rax, r15
0x18029da9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029daa0  mov     ebx, eax
0x18029daa2  mov     rcx, [rbp+37h+phglobal]; hMem
0x18029daa6  call    cs:__imp_GlobalUnlock
0x18029daac  mov     [r12], rsi
0x18029dab0  mov     r14d, 1
0x18029dab6  mov     [rbp+37h+var_4C], r14d
0x18029daba  test    ebx, ebx
0x18029dabc  jnz     loc_18029DB4A
0x18029dac2  mov     rcx, [rbp+37h+pMem]; pMem
0x18029dac6  call    cs:__imp_GlobalHandle
0x18029dacc  mov     rdi, rax
0x18029dacf  test    rax, rax
0x18029dad2  jnz     short loc_18029DADA
0x18029dad4  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029dada  mov     ebx, dword ptr [rbp+37h+arg_10]
0x18029dadd  mov     rcx, rdi; hMem
0x18029dae0  call    cs:__imp_GlobalSize
0x18029dae6  cmp     rax, rbx
0x18029dae9  jz      short loc_18029DAF1
0x18029daeb  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029daf1  mov     eax, dword ptr [rbp+37h+arg_10]
0x18029daf4  cmp     [rbp+37h+var_50], eax
0x18029daf7  jbe     short loc_18029DAFF
0x18029daf9  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029daff  mov     rcx, r12
0x18029db02  call    ??$close@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@YAXAEAV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@0@@Z; win_scope::close<IStream *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>> &)
0x18029db07  mov     [r12], rsi
0x18029db0b  mov     r8, r12; ppstm
0x18029db0e  mov     edx, r14d; fDeleteOnRelease
0x18029db11  mov     rcx, rdi; hGlobal
0x18029db14  call    cs:__imp_CreateStreamOnHGlobal
0x18029db1a  test    eax, eax
0x18029db1c  jns     short loc_18029DB26
0x18029db1e  mov     ecx, eax; this
0x18029db20  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x18029db26  mov     edx, [rbp+37h+var_50]
0x18029db29  cmp     edx, dword ptr [rbp+37h+arg_10]
0x18029db2c  jnb     short loc_18029DB7C
0x18029db2e  mov     rcx, [r12]
0x18029db32  mov     rax, [rcx]
0x18029db35  mov     rax, [rax+30h]
0x18029db39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029db3e  test    eax, eax
0x18029db40  jns     short loc_18029DB7C
0x18029db42  mov     ecx, eax; this
0x18029db44  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x18029db4a  mov     r8d, ebx; unsigned int
0x18029db4d  mov     rcx, [rbp+37h+arg_38]; this
0x18029db51  cmp     [rbp+37h+arg_18], sil
0x18029db55  jz      short loc_18029DB67
0x18029db57  mov     edx, 4A9h; struct dxc::RenderState *
0x18029db5c  call    ?OutputDebugMessage@dxc@@YAXPEBURenderState@1@IZZ; dxc::OutputDebugMessage(dxc::RenderState const *,uint,...)
0x18029db61  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029db67  mov     edx, 4A8h; struct dxc::RenderState *
0x18029db6c  call    ?OutputDebugMessage@dxc@@YAXPEBURenderState@1@IZZ; dxc::OutputDebugMessage(dxc::RenderState const *,uint,...)
0x18029db71  mov     rdx, r13
0x18029db74  mov     rcx, r12
0x18029db77  call    ?reset@?$scope_helper@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAVIDeviceInternal@@@Z; win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>> &,IDeviceInternal *)
0x18029db7c  mov     rax, r12
0x18029db7f  mov     rbx, [rsp+0E0h+arg_0]
0x18029db87  add     rsp, 0B0h
0x18029db8e  pop     r15
0x18029db90  pop     r14
0x18029db92  pop     r13
0x18029db94  pop     r12
0x18029db96  pop     rdi
0x18029db97  pop     rsi
0x18029db98  pop     rbp
0x18029db99  retn
```
