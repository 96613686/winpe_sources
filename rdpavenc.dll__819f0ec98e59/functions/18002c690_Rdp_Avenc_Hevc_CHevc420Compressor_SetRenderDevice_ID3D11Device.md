# Rdp::Avenc::Hevc::CHevc420Compressor::SetRenderDevice(ID3D11Device *)

- ea: `0x18002c690`
- end: `0x18002c93b`
- name: `?SetRenderDevice@CHevc420Compressor@Hevc@Avenc@Rdp@@QEAAXPEAUID3D11Device@@@Z`
- size: `683`
- prototype: `void(Rdp::Avenc::Hevc::CHevc420Compressor *__hidden this, struct ID3D11Device *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002c950`

## callees

- `0x180006580`
- `0x180007018`
- `0x18000e848`
- `0x18000ec04`
- `0x18002ace4`
- `0x18002c690`
- `0x180089010`

## import_xrefs

- `MFPlat!MFCreateDXGIDeviceManager` at `0x18002c749`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x18002c749`

## string_xrefs

- `0x18002c914`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002c756`: `Failed to create DXGI device manager`
- `0x18002c765`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\HevcProcessor/HevcCompressor.h`
- `0x18002c7a1`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\HevcProcessor/HevcCompressor.h`
- `0x18002c8ff`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\HevcProcessor/HevcCompressor.h`
- `0x18002c929`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\HevcProcessor/HevcCompressor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Rdp::Avenc::Hevc::CHevc420Compressor::SetRenderDevice(
        Rdp::Avenc::Hevc::CHevc420Compressor *this,
        struct ID3D11Device *a2)
{
  __int64 v4; // rsi
  bool v5; // al
  _QWORD *v6; // rsi
  unsigned int *v7; // r14
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  __int64 (__fastcall *v11)(__int64, __int64 *); // rsi
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  const char *v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  char v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  _BYTE v22[296]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v4 = *((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct ID3D11Device *))a2->lpVtbl->AddRef)(a2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  Rdp::Utils::Graphics::CRenderDevice::CRenderDevice((Rdp::Utils::Graphics::CRenderDevice *)v18, a2);
  v5 = v19 == 0;
  *((_BYTE *)this + 260) = v19 == 0;
  if ( v5 )
  {
    v6 = (_QWORD *)((char *)this + 232);
    if ( *((_QWORD *)this + 29) )
    {
      v7 = (unsigned int *)((char *)this + 256);
    }
    else
    {
      *v6 = 0;
      v7 = (unsigned int *)((char *)this + 256);
      v8 = MFCreateDXGIDeviceManager((UINT *)this + 64, (IMFDXGIDeviceManager **)this + 29);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcCompressor.h",
        (const char *)v8,
        (int)"Failed to create DXGI device manager",
        v15);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct ID3D11Device *, _QWORD))(*(_QWORD *)*v6 + 56LL))(*v6, a2, *v7);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcCompressor.h",
      (const char *)v9,
      (int)"Failed to reset D3D device",
      v15);
    v16 = 0;
    v17 = 0;
    v10 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_05008617_fbfd_4051_a790_144884b4f6a9,
            &v17);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v10,
        v14);
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 56LL);
    v16 = 0;
    v12 = v11(v17, &v16);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcCompressor.h",
        (const char *)(unsigned int)v12,
        v14);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    memset_0(v22, 0, 0x130u);
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v16 + 64LL))(v16, v22);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\HevcProcessor/HevcCompressor.h",
        (const char *)(unsigned int)v13,
        v14);
    *((_QWORD *)this + 27) = v23;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
}

```

## disassembly

```asm
0x18002c690  mov     [rsp-8+arg_10], rbx
0x18002c695  mov     [rsp-8+arg_18], rsi
0x18002c69a  push    rbp
0x18002c69b  push    rdi
0x18002c69c  push    r14
0x18002c69e  lea     rbp, [rsp-0A0h]
0x18002c6a6  sub     rsp, 1A0h
0x18002c6ad  mov     rax, cs:__security_cookie
0x18002c6b4  xor     rax, rsp
0x18002c6b7  mov     [rbp+0B0h+var_20], rax
0x18002c6be  mov     rdi, rdx
0x18002c6c1  mov     rbx, rcx
0x18002c6c4  mov     rsi, [rcx+0B8h]
0x18002c6cb  mov     [rcx+0B8h], rdx
0x18002c6d2  test    rdx, rdx
0x18002c6d5  jz      short loc_18002C6E6
0x18002c6d7  mov     rax, [rdx]
0x18002c6da  mov     rcx, rdx
0x18002c6dd  mov     rax, [rax+8]
0x18002c6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6e6  test    rsi, rsi
0x18002c6e9  jz      short loc_18002C6FB
0x18002c6eb  mov     rax, [rsi]
0x18002c6ee  mov     rcx, rsi
0x18002c6f1  mov     rax, [rax+10h]
0x18002c6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6fa  nop
0x18002c6fb  mov     rdx, rdi; struct ID3D11Device *
0x18002c6fe  lea     rcx, [rsp+1B0h+var_170]; this
0x18002c703  call    ??0CRenderDevice@Graphics@Utils@Rdp@@QEAA@PEAUID3D11Device@@@Z; Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(ID3D11Device *)
0x18002c708  nop
0x18002c709  cmp     [rsp+1B0h+var_168], 0
0x18002c70e  setz    al
0x18002c711  mov     [rbx+104h], al
0x18002c717  test    al, al
0x18002c719  jz      loc_18002C8A7
0x18002c71f  lea     rsi, [rbx+0E8h]
0x18002c726  cmp     qword ptr [rsi], 0
0x18002c72a  jz      short loc_18002C735
0x18002c72c  lea     r14, [rbx+100h]
0x18002c733  jmp     short loc_18002C776
0x18002c735  mov     qword ptr [rsi], 0
0x18002c73c  lea     r14, [rbx+100h]
0x18002c743  mov     rdx, rsi; ppDeviceManager
0x18002c746  mov     rcx, r14; resetToken
0x18002c749  call    cs:__imp_MFCreateDXGIDeviceManager
0x18002c74f  mov     rcx, [rbp+0B8h]; this
0x18002c756  lea     rdx, aFailedToCreate_1; "Failed to create DXGI device manager"
0x18002c75d  mov     qword ptr [rsp+1B0h+var_190], rdx; int
0x18002c762  mov     r9d, eax; char *
0x18002c765  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002c76c  mov     edx, 45h ; 'E'; void *
0x18002c771  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002c776  mov     rcx, [rsi]
0x18002c779  mov     rax, [rcx]
0x18002c77c  mov     r8d, [r14]
0x18002c77f  mov     rdx, rdi
0x18002c782  mov     rax, [rax+38h]
0x18002c786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c78b  mov     rcx, [rbp+0B8h]; this
0x18002c792  lea     rdx, aFailedToResetD; "Failed to reset D3D device"
0x18002c799  mov     qword ptr [rsp+1B0h+var_190], rdx; int
0x18002c79e  mov     r9d, eax; char *
0x18002c7a1  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002c7a8  mov     edx, 49h ; 'I'; void *
0x18002c7ad  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002c7b2  mov     [rsp+1B0h+var_180], 0
0x18002c7bb  mov     [rsp+1B0h+var_178], 0
0x18002c7c4  mov     rax, [rdi]
0x18002c7c7  lea     r8, [rsp+1B0h+var_178]
0x18002c7cc  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18002c7d3  mov     rcx, rdi
0x18002c7d6  mov     rax, [rax]
0x18002c7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7de  mov     rcx, [rbp+0B8h]; this
0x18002c7e5  test    eax, eax
0x18002c7e7  js      loc_18002C911
0x18002c7ed  mov     rdi, [rsp+1B0h+var_178]
0x18002c7f2  mov     rax, [rdi]
0x18002c7f5  mov     rsi, [rax+38h]
0x18002c7f9  mov     rcx, [rsp+1B0h+var_180]
0x18002c7fe  mov     [rsp+1B0h+var_180], 0
0x18002c807  test    rcx, rcx
0x18002c80a  jz      short loc_18002C819
0x18002c80c  mov     rdx, [rcx]
0x18002c80f  mov     rax, [rdx+10h]
0x18002c813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c818  nop
0x18002c819  lea     rdx, [rsp+1B0h+var_180]
0x18002c81e  mov     rcx, rdi
0x18002c821  mov     rax, rsi
0x18002c824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c829  mov     rcx, [rbp+0B8h]; this
0x18002c830  test    eax, eax
0x18002c832  js      loc_18002C926
0x18002c838  mov     rcx, [rsp+1B0h+var_178]
0x18002c83d  test    rcx, rcx
0x18002c840  jz      short loc_18002C84F
0x18002c842  mov     rax, [rcx]
0x18002c845  mov     rax, [rax+10h]
0x18002c849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c84e  nop
0x18002c84f  xor     edx, edx; Val
0x18002c851  mov     r8d, 130h; Size
0x18002c857  lea     rcx, [rsp+1B0h+var_150]; void *
0x18002c85c  call    memset_0
0x18002c861  mov     rcx, [rsp+1B0h+var_180]
0x18002c866  mov     rax, [rcx]
0x18002c869  lea     rdx, [rsp+1B0h+var_150]
0x18002c86e  mov     rax, [rax+40h]
0x18002c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c877  mov     rcx, [rbp+0B8h]; this
0x18002c87e  test    eax, eax
0x18002c880  js      short loc_18002C8FC
0x18002c882  mov     rax, [rbp+0B0h+var_28]
0x18002c889  mov     [rbx+0D8h], rax
0x18002c890  mov     rcx, [rsp+1B0h+var_180]
0x18002c895  test    rcx, rcx
0x18002c898  jz      short loc_18002C8A7
0x18002c89a  mov     rax, [rcx]
0x18002c89d  mov     rax, [rax+10h]
0x18002c8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8a6  nop
0x18002c8a7  mov     rcx, [rsp+1B0h+var_158]
0x18002c8ac  test    rcx, rcx
0x18002c8af  jz      short loc_18002C8BE
0x18002c8b1  mov     rax, [rcx]
0x18002c8b4  mov     rax, [rax+10h]
0x18002c8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8bd  nop
0x18002c8be  mov     rcx, [rsp+1B0h+var_160]
0x18002c8c3  test    rcx, rcx
0x18002c8c6  jz      short loc_18002C8D5
0x18002c8c8  mov     rax, [rcx]
0x18002c8cb  mov     rax, [rax+10h]
0x18002c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8d4  nop
0x18002c8d5  mov     rcx, [rbp+0B0h+var_20]
0x18002c8dc  xor     rcx, rsp; StackCookie
0x18002c8df  call    __security_check_cookie
0x18002c8e4  lea     r11, [rsp+1B0h+var_10]
0x18002c8ec  mov     rbx, [r11+30h]
0x18002c8f0  mov     rsi, [r11+38h]
0x18002c8f4  mov     rsp, r11
0x18002c8f7  pop     r14
0x18002c8f9  pop     rdi
0x18002c8fa  pop     rbp
0x18002c8fb  retn
0x18002c8fc  mov     r9d, eax; char *
0x18002c8ff  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002c906  mov     edx, 52h ; 'R'; void *
0x18002c90b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002c911  mov     r9d, eax; char *
0x18002c914  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c91b  mov     edx, 1CBEh; void *
0x18002c920  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002c926  mov     r9d, eax; char *
0x18002c929  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002c930  mov     edx, 4Fh ; 'O'; void *
0x18002c935  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
