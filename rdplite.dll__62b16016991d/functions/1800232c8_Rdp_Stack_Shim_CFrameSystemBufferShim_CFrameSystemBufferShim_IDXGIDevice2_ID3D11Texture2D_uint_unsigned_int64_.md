# Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(IDXGIDevice2 *,ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint)

- ea: `0x1800232c8`
- end: `0x180023507`
- name: `??0CFrameSystemBufferShim@Shim@Stack@Rdp@@QEAA@PEAUIDXGIDevice2@@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@I@Z`
- size: `575`
- prototype: `Rdp::Stack::Shim::CFrameSystemBufferShim *__fastcall(Rdp::Stack::Shim::CFrameSystemBufferShim *this, struct IDXGIDevice2 *, struct ID3D11Texture2D *, int, unsigned __int64, struct tagRECT *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021640`
- `0x180021b78`

## callees

- `0x1800036f0`
- `0x180005130`
- `0x180007b28`
- `0x18000cea4`
- `0x1800126d0`
- `0x180012a04`
- `0x180023050`
- `0x1800230a8`
- `0x1800232c8`
- `0x18002a010`

## string_xrefs

- `0x180023430`: `Warp RenderCompletionEvent timed out!`
- `0x180023463`: `Warp extension returned null buffer, device is removed`

## pseudocode

```c
Rdp::Stack::Shim::CFrameSystemBufferShim *__fastcall Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(
        Rdp::Stack::Shim::CFrameSystemBufferShim *this,
        struct IDXGIDevice2 *a2,
        struct ID3D11Texture2D *a3,
        int a4,
        unsigned __int64 a5,
        struct tagRECT *a6,
        unsigned int a7)
{
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  char v13; // al
  const char *v15; // [rsp+30h] [rbp-71h]
  const char *v16; // [rsp+30h] [rbp-71h]
  __int64 v17; // [rsp+60h] [rbp-41h] BYREF
  _QWORD v18[2]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v19; // [rsp+78h] [rbp-29h]
  int v20; // [rsp+80h] [rbp-21h]
  _QWORD v21[2]; // [rsp+88h] [rbp-19h] BYREF
  _OWORD v22[3]; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v21[1] = this;
  v21[0] = a2;
  Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>(
    (_DWORD)this,
    (_DWORD)a3,
    a4,
    a5,
    (__int64)a6,
    a7);
  *(_QWORD *)this = &Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
  *((_QWORD *)this + 10) = &Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Avenc::IFrameSystemBuffer'};
  *((_QWORD *)this + 11) = &Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Avenc::IFrameSystemBuffer1'};
  *((_QWORD *)this + 12) = &Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>::`vftable'{for `Rdp::Avenc::IGpuFence'};
  *((_QWORD *)this + 13) = &Rdp::Stack::Shim::CFrameDxBufferShim::`vftable'{for `Rdp::Avenc::IFrameBufferBlob'};
  *((_QWORD *)this + 40) = 0;
  v10 = (__int64 *)wil::com_query<IWarpPrivateAPI,IDXGIDevice2 * &>(&v17, v21);
  v11 = *v10;
  *v10 = 0;
  v12 = *((_QWORD *)this + 40);
  *((_QWORD *)this + 40) = v11;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v17);
  v17 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v17,
    0);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 80LL))(*((_QWORD *)this + 21), 2013265920);
  v18[0] = 13;
  v18[1] = 1;
  v19 = 0;
  v20 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 40) + 24LL))(*((_QWORD *)this + 40), v18);
  ((void (__fastcall *)(struct IDXGIDevice2 *, __int64))a2->lpVtbl->EnqueueSetEvent)(a2, v17);
  v13 = _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
          &v17,
          1500);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x77,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\framebuffershim.cpp",
    (const char *)0x800705B4LL,
    v13 ^ 1,
    (bool)"Warp RenderCompletionEvent timed out!",
    v15);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x7F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\framebuffershim.cpp",
    (const char *)0x887A0005LL,
    v19 == 0,
    (bool)"Warp extension returned null buffer, device is removed",
    v16);
  memset(v22, 0, 44);
  ((void (__fastcall *)(struct ID3D11Texture2D *, _OWORD *))a3->lpVtbl->GetDesc)(a3, v22);
  *(_QWORD *)((char *)this + 300) = *(_QWORD *)&v22[0];
  *((_DWORD *)this + 77) = v22[1];
  *((_QWORD *)this + 39) = v19;
  *((_DWORD *)this + 74) = v20;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return this;
}

```

## disassembly

```asm
0x1800232c8  mov     [rsp-8+arg_18], rbx
0x1800232cd  push    rbp
0x1800232ce  push    rsi
0x1800232cf  push    rdi
0x1800232d0  lea     rbp, [rsp-2Fh]
0x1800232d5  sub     rsp, 0D0h
0x1800232dc  mov     rax, cs:__security_cookie
0x1800232e3  xor     rax, rsp
0x1800232e6  mov     [rbp+3Fh+var_18], rax
0x1800232ea  mov     r10d, r9d
0x1800232ed  mov     rsi, r8
0x1800232f0  mov     rdi, rdx
0x1800232f3  mov     rbx, rcx
0x1800232f6  mov     [rbp+3Fh+var_50], rcx
0x1800232fa  mov     [rbp+3Fh+var_58], rdx
0x1800232fe  mov     rcx, [rbp+3Fh+arg_28]
0x180023302  mov     eax, [rbp+3Fh+arg_30]
0x180023305  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180023309  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18002330e  mov     r9, [rbp+3Fh+arg_20]
0x180023312  mov     r8d, r10d
0x180023315  mov     rdx, rsi
0x180023318  mov     rcx, rbx
0x18002331b  call    ??0?$CFrameBufferShim@UIFrameSystemBuffer@Avenc@Rdp@@UIFrameSystemBuffer1@23@@Shim@Stack@Rdp@@QEAA@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@IPEAXPEAUID3D11Fence@@1IPEBE@Z; Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>(ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint,void *,ID3D11Fence *,unsigned __int64,uint,uchar const *)
0x180023320  nop
0x180023321  lea     rax, ??_7CFrameSystemBufferShim@Shim@Stack@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x180023328  mov     [rbx], rax
0x18002332b  lea     rax, ??_7CFrameSystemBufferShim@Shim@Stack@Rdp@@6BIFrameSystemBuffer@Avenc@3@@; const Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Avenc::IFrameSystemBuffer'}
0x180023332  mov     [rbx+50h], rax
0x180023336  lea     rax, ??_7CFrameSystemBufferShim@Shim@Stack@Rdp@@6BIFrameSystemBuffer1@Avenc@3@@; const Rdp::Stack::Shim::CFrameSystemBufferShim::`vftable'{for `Rdp::Avenc::IFrameSystemBuffer1'}
0x18002333d  mov     [rbx+58h], rax
0x180023341  lea     rax, ??_7?$CFrameBufferShim@UIFrameSystemBuffer@Avenc@Rdp@@UIFrameSystemBuffer1@23@@Shim@Stack@Rdp@@6BIGpuFence@Avenc@3@@; const Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>::`vftable'{for `Rdp::Avenc::IGpuFence'}
0x180023348  mov     [rbx+60h], rax
0x18002334c  lea     rax, ??_7CFrameDxBufferShim@Shim@Stack@Rdp@@6BIFrameBufferBlob@Avenc@3@@; const Rdp::Stack::Shim::CFrameDxBufferShim::`vftable'{for `Rdp::Avenc::IFrameBufferBlob'}
0x180023353  mov     [rbx+68h], rax
0x180023357  mov     qword ptr [rbx+140h], 0
0x180023362  lea     rdx, [rbp+3Fh+var_58]
0x180023366  lea     rcx, [rbp+3Fh+var_80]
0x18002336a  call    ??$com_query@VIWarpPrivateAPI@@AEAPEAUIDXGIDevice2@@@wil@@YA?AV?$com_ptr_t@VIWarpPrivateAPI@@Uerr_exception_policy@wil@@@0@AEAPEAUIDXGIDevice2@@@Z; wil::com_query<IWarpPrivateAPI,IDXGIDevice2 * &>(IDXGIDevice2 * &)
0x18002336f  mov     rcx, [rax]
0x180023372  mov     qword ptr [rax], 0
0x180023379  mov     rdx, [rbx+140h]
0x180023380  mov     [rbx+140h], rcx
0x180023387  test    rdx, rdx
0x18002338a  jz      short loc_18002339C
0x18002338c  mov     rax, [rdx]
0x18002338f  mov     rcx, rdx
0x180023392  mov     rax, [rax+10h]
0x180023396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002339b  nop
0x18002339c  lea     rcx, [rbp+3Fh+var_80]
0x1800233a0  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800233a5  mov     [rbp+3Fh+var_80], 0
0x1800233ad  xor     edx, edx
0x1800233af  lea     rcx, [rbp+3Fh+var_80]
0x1800233b3  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800233b8  mov     rcx, [rbx+0A8h]
0x1800233bf  mov     rax, [rcx]
0x1800233c2  mov     edx, 78000000h
0x1800233c7  mov     rax, [rax+50h]
0x1800233cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233d0  mov     [rbp+3Fh+var_78], 0Dh
0x1800233d8  mov     [rbp+3Fh+var_70], 1
0x1800233e0  mov     [rbp+3Fh+var_68], 0
0x1800233e8  mov     [rbp+3Fh+var_60], 0
0x1800233ef  mov     rcx, [rbx+140h]
0x1800233f6  mov     rax, [rcx]
0x1800233f9  lea     rdx, [rbp+3Fh+var_78]
0x1800233fd  mov     rax, [rax+18h]
0x180023401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023406  mov     rax, [rdi]
0x180023409  mov     rdx, [rbp+3Fh+var_80]
0x18002340d  mov     rcx, rdi
0x180023410  mov     rax, [rax+80h]
0x180023417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002341c  mov     edx, 5DCh
0x180023421  lea     rcx, [rbp+3Fh+var_80]
0x180023425  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18002342a  xor     al, 1
0x18002342c  mov     rcx, [rbp+47h]; this
0x180023430  lea     rdx, aWarpRendercomp; "Warp RenderCompletionEvent timed out!"
0x180023437  mov     qword ptr [rsp+0E0h+var_B8], rdx; bool
0x18002343c  mov     [rsp+0E0h+var_C0], al; char
0x180023440  mov     r9d, 800705B4h; char *
0x180023446  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002344d  mov     edx, 77h ; 'w'; void *
0x180023452  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180023457  cmp     [rbp+3Fh+var_68], 0
0x18002345c  setz    al
0x18002345f  mov     rcx, [rbp+47h]; this
0x180023463  lea     rdx, aWarpExtensionR; "Warp extension returned null buffer, de"...
0x18002346a  mov     qword ptr [rsp+0E0h+var_B8], rdx; bool
0x18002346f  mov     [rsp+0E0h+var_C0], al; char
0x180023473  mov     r9d, 887A0005h; char *
0x180023479  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180023480  mov     edx, 7Fh; void *
0x180023485  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002348a  xorps   xmm0, xmm0
0x18002348d  movups  [rbp+3Fh+var_48], xmm0
0x180023491  movups  xmmword ptr [rbp+3Fh+var_38], xmm0
0x180023495  movups  xmmword ptr [rbp+3Fh+var_38+0Ch], xmm0
0x180023499  mov     rax, [rsi]
0x18002349c  lea     rdx, [rbp+3Fh+var_48]
0x1800234a0  mov     rcx, rsi
0x1800234a3  mov     rax, [rax+50h]
0x1800234a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ac  mov     ecx, dword ptr [rbp+3Fh+var_48]
0x1800234af  mov     [rbx+12Ch], ecx
0x1800234b5  mov     ecx, dword ptr [rbp+3Fh+var_48+4]
0x1800234b8  mov     [rbx+130h], ecx
0x1800234be  mov     ecx, dword ptr [rbp+3Fh+var_38]
0x1800234c1  mov     [rbx+134h], ecx
0x1800234c7  mov     rcx, [rbp+3Fh+var_68]
0x1800234cb  mov     [rbx+138h], rcx
0x1800234d2  mov     ecx, [rbp+3Fh+var_60]
0x1800234d5  mov     [rbx+128h], ecx
0x1800234db  lea     rcx, [rbp+3Fh+var_80]
0x1800234df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800234e4  nop
0x1800234e5  mov     rax, rbx
0x1800234e8  mov     rcx, [rbp+3Fh+var_18]
0x1800234ec  xor     rcx, rsp; StackCookie
0x1800234ef  call    __security_check_cookie
0x1800234f4  mov     rbx, [rsp+0E0h+arg_18]
0x1800234fc  add     rsp, 0D0h
0x180023503  pop     rdi
0x180023504  pop     rsi
0x180023505  pop     rbp
0x180023506  retn
```
