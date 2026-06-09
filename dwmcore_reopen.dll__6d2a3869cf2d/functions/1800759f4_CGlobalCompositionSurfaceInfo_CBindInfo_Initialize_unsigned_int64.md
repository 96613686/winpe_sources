# CGlobalCompositionSurfaceInfo::CBindInfo::Initialize(unsigned __int64)

- ea: `0x1800759f4`
- end: `0x180075d90`
- name: `?Initialize@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAJ_K@Z`
- size: `924`
- prototype: `__int64 __fastcall(CGlobalCompositionSurfaceInfo::CBindInfo *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074b30`
- `0x180074d70`

## callees

- `0x180026eac`
- `0x180049e34`
- `0x180050270`
- `0x180075840`
- `0x1800759f4`
- `0x180075df0`
- `0x180076ab0`
- `0x180076fa8`
- `0x180077254`
- `0x180077280`
- `0x1800775e8`
- `0x18015a97c`
- `0x1801ce658`
- `0x1802284b0`
- `0x18022945c`
- `0x18025b348`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075d1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075d1e`
- `win32u!NtQueryCompositionSurfaceBinding` at `0x180075a65`
- `win32u!NtQueryCompositionSurfaceBinding` at `0x180075a65`

## pseudocode

```c
__int64 __fastcall CGlobalCompositionSurfaceInfo::CBindInfo::Initialize(
        CGlobalCompositionSurfaceInfo::CBindInfo *this,
        __int64 a2)
{
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  _DWORD *v7; // r14
  int v8; // edi
  int v9; // r8d
  int v10; // r8d
  char *v11; // rbx
  const struct CCompositionSurfaceInfo *v12; // rcx
  int v13; // eax
  struct CFlipExSwapchainStatistics *v14; // rdx
  int v15; // eax
  unsigned int v17; // r8d
  int v18; // eax
  const struct CGlobalCompositionSurfaceInfo *v19; // rcx
  int v20; // eax
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  struct CFlipExSwapchainStatistics *v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[144]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+F4h] [rbp-Ch]
  HANDLE hObject; // [rsp+4D8h] [rbp+3D8h]
  unsigned __int64 v30; // [rsp+4E0h] [rbp+3E0h]
  unsigned __int16 v31[64]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v23 = a2;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
    McTemplateU0xx_EventWriteTransfer(this, &CompSurfInfo_Binding_Start, *(_QWORD *)(*(_QWORD *)this + 40LL), a2);
  memset_0(v25, 0, 0x520u);
  if ( *((_QWORD *)this + 3) )
    CGlobalCompositionSurfaceInfo::CBindInfo::Reset(this, 0);
  v3 = NtQueryCompositionSurfaceBinding(*(_QWORD *)(*(_QWORD *)this + 32LL), &v23, v25);
  if ( v3 < 0 )
  {
    v8 = v3 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, v3 | 0x10000000, 0x3C2u, 0);
    v7 = (_DWORD *)((char *)this + 32);
    goto LABEL_17;
  }
  v6 = v25[0];
  v7 = (_DWORD *)((char *)this + 32);
  v8 = 0;
  *((_QWORD *)this + 3) = v23;
  *((_DWORD *)this + 8) = v6;
  if ( v6 )
  {
    v9 = v6 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
          v8 = -2147024809;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, -2147024809, 0x406u, 0);
          goto LABEL_26;
        }
        v11 = (char *)hObject;
        v12 = *(const struct CCompositionSurfaceInfo **)this;
        v24[0] = hObject;
        v22 = 0;
        v13 = CCompositionSwapchainStatistics::Create(v12, hObject, v30, &v22);
        v8 = v13;
        if ( v13 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, v13, 0x3F4u, 0);
          if ( v22 )
            (*(void (__fastcall **)(struct CFlipExSwapchainStatistics *))(*(_QWORD *)v22 + 16LL))(v22);
          if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v11);
          goto LABEL_26;
        }
        v14 = v22;
        v22 = 0;
        wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(
          (char *)this + 16,
          v14);
        v15 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
                this,
                (const struct CSM_BUFFER_ATTRIBUTES *)v26,
                v28);
        v8 = v15;
        if ( v15 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, v15, 0x3F8u, 0);
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v22);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v24);
          goto LABEL_26;
        }
        CGlobalCompositionSurfaceInfo::CBindInfo::CheckBufferHomogeneity(this);
        CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(this, v31);
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v11);
        goto LABEL_14;
      }
      v17 = v28;
      if ( v28 > 1 )
      {
        v19 = *(const struct CGlobalCompositionSurfaceInfo **)this;
        v22 = 0;
        v20 = CFlipExSwapchainStatistics::Create(v19, &v22);
        v8 = v20;
        if ( v20 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, v20, 0x3DEu, 0);
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v22);
          goto LABEL_26;
        }
        wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(
          (char *)this + 16,
          v22);
        v17 = v28;
      }
      v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
              this,
              (const struct CSM_BUFFER_ATTRIBUTES *)v26,
              v17);
      v8 = v18;
      if ( v18 >= 0 )
      {
        CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(this, v31);
LABEL_14:
        v6 = v25[0];
        goto LABEL_15;
      }
      v21 = 996;
    }
    else
    {
      v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSingleBuffer(
              this,
              (const struct CSM_BUFFER_ATTRIBUTES *)v26,
              (const struct CSM_SINGLE_BUFFER_INFO *)v27);
      v8 = v18;
      if ( v18 >= 0 )
        goto LABEL_14;
      v21 = 975;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4720, 4u, v18, v21, 0);
    goto LABEL_26;
  }
LABEL_15:
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
    McTemplateU0qqt_EventWriteTransfer(
      v5,
      v4,
      v6,
      (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 3,
      *((_BYTE *)this + 190));
LABEL_17:
  if ( v8 < 0 )
  {
LABEL_26:
    *((_QWORD *)this + 3) = 0;
    *v7 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800759f4  mov     [rsp-8+arg_10], rbx
0x1800759f9  push    rbp
0x1800759fa  push    rsi
0x1800759fb  push    rdi
0x1800759fc  push    r14
0x1800759fe  push    r15
0x180075a00  lea     rbp, [rsp-480h]
0x180075a08  sub     rsp, 580h
0x180075a0f  mov     rax, cs:__security_cookie
0x180075a16  xor     rax, rsp
0x180075a19  mov     [rbp+4A0h+var_30], rax
0x180075a20  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x180075a27  mov     rsi, rcx
0x180075a2a  mov     [rsp+5A0h+var_568], rdx
0x180075a2f  jnz     loc_180075BCE
0x180075a35  xor     edx, edx; Val
0x180075a37  lea     rcx, [rsp+5A0h+var_550]; void *
0x180075a3c  mov     r8d, 520h; Size
0x180075a42  call    memset_0
0x180075a47  xor     r15d, r15d
0x180075a4a  cmp     [rsi+18h], r15
0x180075a4e  jnz     loc_180075C72
0x180075a54  mov     rcx, [rsi]
0x180075a57  lea     r8, [rsp+5A0h+var_550]
0x180075a5c  lea     rdx, [rsp+5A0h+var_568]
0x180075a61  mov     rcx, [rcx+20h]
0x180075a65  call    cs:__imp_NtQueryCompositionSurfaceBinding
0x180075a6b  mov     edi, eax
0x180075a6d  test    eax, eax
0x180075a6f  js      loc_180075C81
0x180075a75  mov     r8d, [rsp+5A0h+var_550]
0x180075a7a  lea     r14, [rsi+20h]
0x180075a7e  mov     rax, [rsp+5A0h+var_568]
0x180075a83  mov     edi, r15d
0x180075a86  mov     [rsi+18h], rax
0x180075a8a  mov     [r14], r8d
0x180075a8d  test    r8d, r8d
0x180075a90  jz      loc_180075B3E
0x180075a96  sub     r8d, 1
0x180075a9a  jz      loc_180075D70
0x180075aa0  sub     r8d, 1
0x180075aa4  jz      loc_180075B77
0x180075aaa  cmp     r8d, 1
0x180075aae  jnz     loc_180075CB4
0x180075ab4  mov     rbx, [rbp+4A0h+hObject]
0x180075abb  lea     r9, [rsp+5A0h+var_570]; struct CCompositionSwapchainStatistics **
0x180075ac0  mov     r8, [rbp+4A0h+var_C0]; unsigned __int64
0x180075ac7  mov     rdx, rbx; void *
0x180075aca  mov     rcx, [rsi]; struct CCompositionSurfaceInfo *
0x180075acd  mov     [rsp+5A0h+var_560], rbx
0x180075ad2  mov     [rsp+5A0h+var_570], r15
0x180075ad7  call    ?Create@CCompositionSwapchainStatistics@@SAJPEBVCCompositionSurfaceInfo@@PEAX_KPEAPEAV1@@Z; CCompositionSwapchainStatistics::Create(CCompositionSurfaceInfo const *,void *,unsigned __int64,CCompositionSwapchainStatistics * *)
0x180075adc  mov     edi, eax
0x180075ade  test    eax, eax
0x180075ae0  js      loc_180075BE9
0x180075ae6  mov     rdx, [rsp+5A0h+var_570]
0x180075aeb  lea     rcx, [rsi+10h]
0x180075aef  mov     [rsp+5A0h+var_570], r15
0x180075af4  call    ?attach@?$com_ptr_t@UIDisplayTarget@Core@Display@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXPEAUIDisplayTarget@Core@Display@Devices@Windows@@@Z; wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(Windows::Devices::Display::Core::IDisplayTarget *)
0x180075af9  mov     r8d, [rbp+4A0h+var_4AC]; unsigned int
0x180075afd  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x180075b02  mov     rcx, rsi; this
0x180075b05  call    ?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)
0x180075b0a  mov     edi, eax
0x180075b0c  test    eax, eax
0x180075b0e  js      loc_180075CDC
0x180075b14  mov     rcx, rsi; this
0x180075b17  call    ?CheckBufferHomogeneity@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXXZ; CGlobalCompositionSurfaceInfo::CBindInfo::CheckBufferHomogeneity(void)
0x180075b1c  lea     rdx, [rbp+4A0h+var_B0]; unsigned __int16 *
0x180075b23  mov     rcx, rsi; this
0x180075b26  call    ?EnsureSwapChainTelemetryInitialized@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEBG@Z; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(ushort const *)
0x180075b2b  lea     rax, [rbx-1]
0x180075b2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180075b33  jbe     loc_180075CCE
0x180075b39  mov     r8d, [rsp+5A0h+var_550]
0x180075b3e  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x180075b45  jnz     short loc_180075BAD
0x180075b47  test    edi, edi
0x180075b49  js      loc_180075C33
0x180075b4f  mov     eax, edi
0x180075b51  mov     rcx, [rbp+4A0h+var_30]
0x180075b58  xor     rcx, rsp; StackCookie
0x180075b5b  call    __security_check_cookie
0x180075b60  mov     rbx, [rsp+5A0h+arg_10]
0x180075b68  add     rsp, 580h
0x180075b6f  pop     r15
0x180075b71  pop     r14
0x180075b73  pop     rdi
0x180075b74  pop     rsi
0x180075b75  pop     rbp
0x180075b76  retn
0x180075b77  mov     r8d, [rbp+4A0h+var_4AC]; unsigned int
0x180075b7b  cmp     r8d, 1
0x180075b7f  ja      loc_180075C3F
0x180075b85  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x180075b8a  mov     rcx, rsi; this
0x180075b8d  call    ?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)
0x180075b92  mov     edi, eax
0x180075b94  test    eax, eax
0x180075b96  js      loc_180075D5E
0x180075b9c  lea     rdx, [rbp+4A0h+var_B0]; unsigned __int16 *
0x180075ba3  mov     rcx, rsi; this
0x180075ba6  call    ?EnsureSwapChainTelemetryInitialized@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEBG@Z; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureSwapChainTelemetryInitialized(ushort const *)
0x180075bab  jmp     short loc_180075B39
0x180075bad  mov     r9, [rsi+50h]
0x180075bb1  sub     r9, [rsi+48h]
0x180075bb5  movzx   eax, byte ptr [rsi+0BEh]
0x180075bbc  sar     r9, 3
0x180075bc0  mov     [rsp+5A0h+var_580], eax
0x180075bc4  call    McTemplateU0qqt_EventWriteTransfer
0x180075bc9  jmp     loc_180075B47
0x180075bce  mov     r8, [rcx]
0x180075bd1  mov     r9, rdx
0x180075bd4  lea     rdx, CompSurfInfo_Binding_Start
0x180075bdb  mov     r8, [r8+28h]
0x180075bdf  call    McTemplateU0xx_EventWriteTransfer
0x180075be4  jmp     loc_180075A35
0x180075be9  mov     r8d, 4; unsigned int
0x180075bef  mov     [rsp+5A0h+var_578], r15; void *
0x180075bf4  mov     r9d, eax; int
0x180075bf7  mov     [rsp+5A0h+var_580], 3F4h; unsigned int
0x180075bff  lea     rdx, dword_1802D4720; int *
0x180075c06  lea     ecx, [r8+10h]; unsigned int
0x180075c0a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180075c0f  mov     rcx, [rsp+5A0h+var_570]
0x180075c14  test    rcx, rcx
0x180075c17  jz      short loc_180075C25
0x180075c19  mov     rax, [rcx]
0x180075c1c  mov     rax, [rax+10h]
0x180075c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c25  lea     rax, [rbx-1]
0x180075c29  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180075c2d  jbe     loc_180075D1B
0x180075c33  mov     [rsi+18h], r15
0x180075c37  mov     [r14], r15d
0x180075c3a  jmp     loc_180075B4F
0x180075c3f  mov     rcx, [rsi]; struct CGlobalCompositionSurfaceInfo *
0x180075c42  lea     rdx, [rsp+5A0h+var_570]; struct CFlipExSwapchainStatistics **
0x180075c47  mov     [rsp+5A0h+var_570], r15
0x180075c4c  call    ?Create@CFlipExSwapchainStatistics@@SAJPEBVCGlobalCompositionSurfaceInfo@@PEAPEAV1@@Z; CFlipExSwapchainStatistics::Create(CGlobalCompositionSurfaceInfo const *,CFlipExSwapchainStatistics * *)
0x180075c51  mov     edi, eax
0x180075c53  test    eax, eax
0x180075c55  js      loc_180075D29
0x180075c5b  mov     rdx, [rsp+5A0h+var_570]
0x180075c60  lea     rcx, [rsi+10h]
0x180075c64  call    ?attach@?$com_ptr_t@UIDisplayTarget@Core@Display@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXPEAUIDisplayTarget@Core@Display@Devices@Windows@@@Z; wil::com_ptr_t<Windows::Devices::Display::Core::IDisplayTarget,wil::err_returncode_policy>::attach(Windows::Devices::Display::Core::IDisplayTarget *)
0x180075c69  mov     r8d, [rbp+4A0h+var_4AC]
0x180075c6d  jmp     loc_180075B85
0x180075c72  xor     edx, edx; bool
0x180075c74  mov     rcx, rsi; this
0x180075c77  call    ?Reset@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAX_N@Z; CGlobalCompositionSurfaceInfo::CBindInfo::Reset(bool)
0x180075c7c  jmp     loc_180075A54
0x180075c81  mov     r8d, 4; unsigned int
0x180075c87  mov     [rsp+5A0h+var_578], r15; void *
0x180075c8c  bts     edi, 1Ch
0x180075c90  mov     [rsp+5A0h+var_580], 3C2h; unsigned int
0x180075c98  mov     r9d, edi; int
0x180075c9b  lea     rdx, dword_1802D4720; int *
0x180075ca2  lea     ecx, [r8+10h]; unsigned int
0x180075ca6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180075cab  lea     r14, [rsi+20h]
0x180075caf  jmp     loc_180075B47
0x180075cb4  mov     edi, 80070057h
0x180075cb9  mov     [rsp+5A0h+var_578], r15
0x180075cbe  mov     r9d, edi
0x180075cc1  mov     [rsp+5A0h+var_580], 406h
0x180075cc9  jmp     loc_18029EBF8
0x180075cce  mov     rcx, rbx; hObject
0x180075cd1  call    cs:__imp_CloseHandle
0x180075cd7  jmp     loc_180075B39
0x180075cdc  mov     r8d, 4; unsigned int
0x180075ce2  mov     [rsp+5A0h+var_578], r15; void *
0x180075ce7  mov     r9d, eax; int
0x180075cea  mov     [rsp+5A0h+var_580], 3F8h; unsigned int
0x180075cf2  lea     rdx, dword_1802D4720; int *
0x180075cf9  lea     ecx, [r8+10h]; unsigned int
0x180075cfd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180075d02  lea     rcx, [rsp+5A0h+var_570]
0x180075d07  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180075d0c  lea     rcx, [rsp+5A0h+var_560]
0x180075d11  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180075d16  jmp     loc_180075C33
0x180075d1b  mov     rcx, rbx; hObject
0x180075d1e  call    cs:__imp_CloseHandle
0x180075d24  jmp     loc_180075C33
0x180075d29  mov     r8d, 4; unsigned int
0x180075d2f  mov     [rsp+5A0h+var_578], r15; void *
0x180075d34  mov     r9d, eax; int
0x180075d37  mov     [rsp+5A0h+var_580], 3DEh; unsigned int
0x180075d3f  lea     rdx, dword_1802D4720; int *
0x180075d46  lea     ecx, [r8+10h]; unsigned int
0x180075d4a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180075d4f  lea     rcx, [rsp+5A0h+var_570]
0x180075d54  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180075d59  jmp     loc_180075C33
0x180075d5e  mov     [rsp+5A0h+var_578], r15
0x180075d63  mov     [rsp+5A0h+var_580], 3E4h
0x180075d6b  jmp     loc_18029EBF5
0x180075d70  lea     r8, [rbp+4A0h+var_4B0]; struct CSM_SINGLE_BUFFER_INFO *
0x180075d74  mov     rcx, rsi; this
0x180075d77  lea     rdx, [rsp+5A0h+var_540]; struct CSM_BUFFER_ATTRIBUTES *
0x180075d7c  call    ?CreateAndAddSingleBuffer@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@AEBUCSM_SINGLE_BUFFER_INFO@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSingleBuffer(CSM_BUFFER_ATTRIBUTES const &,CSM_SINGLE_BUFFER_INFO const &)
0x180075d81  mov     edi, eax
0x180075d83  test    eax, eax
0x180075d85  jns     loc_180075B39
0x180075d8b  jmp     loc_18029EBE8
0x18029ebe8  mov     [rsp+5A0h+var_578], r15; void *
0x18029ebed  mov     [rsp+5A0h+var_580], 3CFh; unsigned int
0x18029ebf5  mov     r9d, eax; int
0x18029ebf8  mov     r8d, 4; unsigned int
0x18029ebfe  lea     rdx, dword_1802D4720; int *
0x18029ec05  lea     ecx, [r8+10h]; unsigned int
0x18029ec09  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18029ec0e  nop
0x18029ec0f  jmp     loc_180075C33
```
