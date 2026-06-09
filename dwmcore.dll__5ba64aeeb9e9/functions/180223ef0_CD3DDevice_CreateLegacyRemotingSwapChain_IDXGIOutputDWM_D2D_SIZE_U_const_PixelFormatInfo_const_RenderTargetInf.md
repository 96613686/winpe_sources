# CD3DDevice::CreateLegacyRemotingSwapChain(IDXGIOutputDWM *,D2D_SIZE_U const &,PixelFormatInfo const &,RenderTargetInfo const &,ILegacyRemotingSwapChain * *)

- ea: `0x180223ef0`
- end: `0x180224304`
- name: `?CreateLegacyRemotingSwapChain@CD3DDevice@@QEAAJPEAUIDXGIOutputDWM@@AEBUD2D_SIZE_U@@AEBUPixelFormatInfo@@AEBVRenderTargetInfo@@PEAPEAVILegacyRemotingSwapChain@@@Z`
- size: `1044`
- prototype: `__int64 __usercall@<rax>(CD3DDevice *__hidden this@<rcx>, struct IDXGIOutputDWM *@<rdx>, const struct D2D_SIZE_U *@<r8>, const struct PixelFormatInfo *@<r9>, const struct RenderTargetInfo *, struct ILegacyRemotingSwapChain **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18024f530`

## callees

- `0x18001dfb0`
- `0x180026eac`
- `0x180050270`
- `0x1800c20b4`
- `0x1800c344c`
- `0x180144c48`
- `0x18015a97c`
- `0x18015adb4`
- `0x180223ef0`
- `0x1802284b0`
- `0x18022945c`
- `0x18028ac2c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802240c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802240c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802240e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802240e6`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1802240db`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1802240db`

## pseudocode

```c
__int64 __fastcall CD3DDevice::CreateLegacyRemotingSwapChain(
        CD3DDevice *this,
        struct IDXGIOutputDWM *a2,
        const struct D2D_SIZE_U *a3,
        const struct PixelFormatInfo *a4,
        const struct RenderTargetInfo *a5,
        struct ILegacyRemotingSwapChain **a6)
{
  void *v10; // r14
  int v11; // eax
  signed int v12; // ebx
  __int64 *v13; // rcx
  int v14; // eax
  int v15; // r9d
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  struct D3D11_SUBRESOURCE_DATA *v19; // r8
  int v20; // eax
  HANDLE v21; // rax
  signed int LastError; // eax
  int v23; // r9d
  struct IRenderTargetBitmap *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  struct IRenderTargetBitmap *v30; // [rsp+40h] [rbp-C0h] BYREF
  struct ID3D11Texture2D *v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h]
  void *v33; // [rsp+58h] [rbp-A8h] BYREF
  _UNSIGNED_RATIO v34; // [rsp+60h] [rbp-A0h] BYREF
  struct ILegacyRemotingSwapChain **v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+74h] [rbp-8Ch]
  _DWORD v37[5]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+94h] [rbp-6Ch]
  int v39; // [rsp+9Ch] [rbp-64h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  int v41; // [rsp+A8h] [rbp-58h]
  const char *v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+BCh] [rbp-44h]
  _BYTE v45[40]; // [rsp+C0h] [rbp-40h] BYREF
  _UNSIGNED_RATIO v46; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v47[48]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Name[64]; // [rsp+190h] [rbp+90h] BYREF

  v35 = a6;
  v30 = 0;
  *a6 = 0;
  v10 = 0;
  v33 = 0;
  if ( *((_DWORD *)this + 281) )
  {
    v12 = -2003304307;
    v15 = -2003304307;
    v28 = 784;
    goto LABEL_28;
  }
  memset_0(v45, 0, 0xC8u);
  v11 = (*(__int64 (__fastcall **)(struct IDXGIOutputDWM *, _BYTE *))(*(_QWORD *)a2 + 32LL))(a2, v45);
  v12 = v11;
  if ( v11 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1803554C8, 2u, v11, 0x313u, 0);
    goto LABEL_29;
  }
  v13 = (__int64 *)*((_QWORD *)this + 72);
  v34 = v46;
  if ( !v13 )
  {
    wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(&v30);
    v32 = 28;
    v31 = (struct ID3D11Texture2D *)"DWM LegacyRemoting SwapChain";
    v14 = CD3DDevice::CreateRenderTargetBitmap(this, &v31, a3, a4, a5, 0, &v30);
    v12 = v14;
    if ( v14 < 0 )
    {
      v28 = 841;
LABEL_6:
      v15 = v14;
LABEL_28:
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1803554C8, 2u, v15, v28, 0);
      goto LABEL_29;
    }
    goto LABEL_19;
  }
  v16 = *v13;
  v31 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v16 + 24))(v13, 0);
  v12 = v17;
  if ( v17 < 0 )
  {
    v29 = 800;
    goto LABEL_22;
  }
  v43 = 28;
  v37[2] = 1;
  v42 = "DWM LegacyRemoting SwapChain";
  v44 = v36;
  v37[0] = a3->width;
  v37[1] = a3->height;
  v18 = *(_DWORD *)a4;
  v37[3] = 1;
  v38 = 1;
  v37[4] = v18;
  v39 = 0;
  v40 = 40;
  v41 = 2;
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(&v31);
  v20 = CD3DDevice::CreateTexture(this, (const struct DWM_TEXTURE2D_DESC *)v37, v19, &v31);
  v12 = v20;
  if ( v20 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1803554C8, 2u, v20, 0x330u, 0);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v31);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 72) + 32LL))(*((_QWORD *)this + 72), 0, 0);
    goto LABEL_29;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64))(**((_QWORD **)this + 72) + 32LL))(
          *((_QWORD *)this + 72),
          Name,
          64);
  v12 = v17;
  if ( v17 < 0 )
  {
    v29 = 819;
    goto LABEL_22;
  }
  SetLastError(0);
  v21 = OpenFileMappingW(0xF001Fu, 0, Name);
  if ( !v21 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v29 = 824;
    if ( v12 >= 0 )
      v12 = -2003304445;
    v23 = v12;
    goto LABEL_16;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v33,
    v21);
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(&v30);
  v17 = CD3DDevice::CreateRenderTargetBitmap(
          this,
          v31,
          *((unsigned int *)a4 + 1),
          *((unsigned int *)a4 + 2),
          *((_DWORD *)a5 + 2),
          *((_DWORD *)a5 + 4),
          &v30);
  v12 = v17;
  if ( v17 < 0 )
  {
    v29 = 832;
LABEL_22:
    v23 = v17;
LABEL_16:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1803554C8, 2u, v23, v29, 0);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v31);
    goto LABEL_29;
  }
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v31);
  v10 = v33;
LABEL_19:
  v24 = v30;
  v25 = (*(__int64 (__fastcall **)(struct IRenderTargetBitmap *))(*(_QWORD *)v30 + 144LL))(v30);
  LOBYTE(v26) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 224LL))(v25, v26);
  v33 = 0;
  v14 = CLegacyRemotingSwapChain::Create(this, v47, &v34, v24, v10, v35);
  v12 = v14;
  if ( v14 < 0 )
  {
    v28 = 854;
    goto LABEL_6;
  }
LABEL_29:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v30);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180223ef0  push    rbp
0x180223ef2  push    rbx
0x180223ef3  push    rsi
0x180223ef4  push    rdi
0x180223ef5  push    r12
0x180223ef7  push    r13
0x180223ef9  push    r14
0x180223efb  push    r15
0x180223efd  lea     rbp, [rsp-128h]
0x180223f05  sub     rsp, 228h
0x180223f0c  mov     rax, cs:__security_cookie
0x180223f13  xor     rax, rsp
0x180223f16  mov     [rbp+160h+var_50], rax
0x180223f1d  mov     rax, [rbp+160h+arg_28]
0x180223f24  xor     edi, edi
0x180223f26  mov     r13, [rbp+160h+arg_20]
0x180223f2d  mov     r15, r9
0x180223f30  mov     r12, r8
0x180223f33  mov     [rsp+260h+var_1F8], rax
0x180223f38  mov     rbx, rdx
0x180223f3b  mov     [rsp+260h+var_220], rdi
0x180223f40  mov     [rax], rdi
0x180223f43  mov     rsi, rcx
0x180223f46  mov     r14d, edi
0x180223f49  mov     [rsp+260h+var_208], rdi
0x180223f4e  cmp     [rcx+464h], edi
0x180223f54  jnz     loc_18022429F
0x180223f5a  xor     edx, edx; Val
0x180223f5c  lea     rcx, [rbp+160h+var_1A0]; void *
0x180223f60  mov     r8d, 0C8h; Size
0x180223f66  call    memset_0
0x180223f6b  mov     rax, [rbx]
0x180223f6e  lea     rdx, [rbp+160h+var_1A0]
0x180223f72  mov     rcx, rbx
0x180223f75  mov     rax, [rax+20h]
0x180223f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180223f7e  mov     ebx, eax
0x180223f80  test    eax, eax
0x180223f82  js      loc_18022428D
0x180223f88  mov     eax, [rbp+160h+var_178]
0x180223f8b  lea     edi, [r14+2]
0x180223f8f  mov     rcx, [rsi+240h]
0x180223f96  mov     [rsp+260h+var_200.uiNumerator], eax
0x180223f9a  mov     eax, [rbp+160h+var_174]
0x180223f9d  mov     [rsp+260h+var_200.uiDenominator], eax
0x180223fa1  test    rcx, rcx
0x180223fa4  jnz     short loc_18022400D
0x180223fa6  lea     rcx, [rsp+260h+var_220]
0x180223fab  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x180223fb0  lea     rax, aDwmLegacyremot; "DWM LegacyRemoting SwapChain"
0x180223fb7  mov     [rsp+260h+var_210], 1Ch
0x180223fbf  mov     [rsp+260h+var_218], rax
0x180223fc4  lea     rdx, [rsp+260h+var_218]
0x180223fc9  lea     rax, [rsp+260h+var_220]
0x180223fce  mov     r9, r15
0x180223fd1  mov     [rsp+260h+var_230], rax
0x180223fd6  mov     r8, r12
0x180223fd9  mov     dword ptr [rsp+260h+var_238], r14d
0x180223fde  mov     rcx, rsi
0x180223fe1  mov     [rsp+260h+var_240], r13
0x180223fe6  call    ?CreateRenderTargetBitmap@CD3DDevice@@QEAAJAEBVCResourceTag@@AEBUD2D_SIZE_U@@AEBUPixelFormatInfo@@AEBVRenderTargetInfo@@W4Enum@CacheMode@@PEAPEAVIRenderTargetBitmap@@@Z; CD3DDevice::CreateRenderTargetBitmap(CResourceTag const &,D2D_SIZE_U const &,PixelFormatInfo const &,RenderTargetInfo const &,CacheMode::Enum,IRenderTargetBitmap * *)
0x180223feb  mov     ebx, eax
0x180223fed  test    eax, eax
0x180223fef  jns     loc_18022419B
0x180223ff5  mov     [rsp+260h+var_238], r14
0x180223ffa  mov     dword ptr [rsp+260h+var_240], 349h
0x180224002  mov     r9d, eax
0x180224005  mov     r8d, edi
0x180224008  jmp     loc_1802242BA
0x18022400d  mov     rax, [rcx]
0x180224010  xor     edx, edx
0x180224012  mov     [rsp+260h+var_218], r14
0x180224017  mov     rax, [rax+18h]
0x18022401b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224020  mov     ebx, eax
0x180224022  test    eax, eax
0x180224024  js      loc_18022427E
0x18022402a  mov     ecx, 1
0x18022402f  mov     [rbp+160h+var_1A8], 1Ch
0x180224036  lea     rax, aDwmLegacyremot; "DWM LegacyRemoting SwapChain"
0x18022403d  mov     [rbp+160h+var_1D8], ecx
0x180224040  mov     [rbp+160h+var_1B0], rax
0x180224044  mov     eax, [rsp+260h+var_1EC]
0x180224048  mov     [rbp+160h+var_1A4], eax
0x18022404b  mov     eax, [r12]
0x18022404f  mov     [rbp+160h+var_1E0], eax
0x180224052  mov     eax, [r12+4]
0x180224057  mov     [rbp+160h+var_1DC], eax
0x18022405a  mov     eax, [r15]
0x18022405d  mov     [rbp+160h+var_1D4], ecx
0x180224060  mov     [rbp+160h+var_1CC], rcx
0x180224064  lea     rcx, [rsp+260h+var_218]
0x180224069  mov     [rbp+160h+var_1D0], eax
0x18022406c  mov     [rbp+160h+var_1C4], r14d
0x180224070  mov     [rbp+160h+var_1C0], 28h ; '('
0x180224078  mov     [rbp+160h+var_1B8], edi
0x18022407b  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x180224080  lea     r9, [rsp+260h+var_218]; struct ID3D11Texture2D **
0x180224085  mov     rcx, rsi; this
0x180224088  lea     rdx, [rbp+160h+var_1E0]; struct DWM_TEXTURE2D_DESC *
0x18022408c  call    ?CreateTexture@CD3DDevice@@QEAAJAEBVDWM_TEXTURE2D_DESC@@PEAUD3D11_SUBRESOURCE_DATA@@PEAPEAUID3D11Texture2D@@@Z; CD3DDevice::CreateTexture(DWM_TEXTURE2D_DESC const &,D3D11_SUBRESOURCE_DATA *,ID3D11Texture2D * *)
0x180224091  mov     ebx, eax
0x180224093  test    eax, eax
0x180224095  js      loc_180224236
0x18022409b  mov     rcx, [rsi+240h]
0x1802240a2  lea     rdx, [rbp+160h+Name]
0x1802240a9  mov     r8d, 40h ; '@'
0x1802240af  mov     rax, [rcx]
0x1802240b2  mov     rax, [rax+20h]
0x1802240b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802240bb  mov     ebx, eax
0x1802240bd  test    eax, eax
0x1802240bf  js      loc_180224227
0x1802240c5  xor     ecx, ecx; dwErrCode
0x1802240c7  call    cs:__imp_SetLastError
0x1802240cd  lea     r8, [rbp+160h+Name]; lpName
0x1802240d4  xor     edx, edx; bInheritHandle
0x1802240d6  mov     ecx, 0F001Fh; dwDesiredAccess
0x1802240db  call    cs:__imp_OpenFileMappingW
0x1802240e1  test    rax, rax
0x1802240e4  jnz     short loc_180224138
0x1802240e6  call    cs:__imp_GetLastError
0x1802240ec  mov     ebx, eax
0x1802240ee  test    eax, eax
0x1802240f0  jle     short loc_1802240FB
0x1802240f2  movzx   ebx, ax
0x1802240f5  or      ebx, 80070000h
0x1802240fb  test    ebx, ebx
0x1802240fd  mov     [rsp+260h+var_238], r14; void *
0x180224102  mov     eax, 88980003h
0x180224107  mov     dword ptr [rsp+260h+var_240], 338h; unsigned int
0x18022410f  cmovns  ebx, eax
0x180224112  mov     r9d, ebx; int
0x180224115  mov     r8d, edi; unsigned int
0x180224118  lea     rdx, qword_1803554C8; int *
0x18022411f  mov     ecx, 14h; unsigned int
0x180224124  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180224129  lea     rcx, [rsp+260h+var_218]
0x18022412e  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180224133  jmp     loc_1802242CB
0x180224138  mov     rdx, rax
0x18022413b  lea     rcx, [rsp+260h+var_208]
0x180224140  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180224145  lea     rcx, [rsp+260h+var_220]
0x18022414a  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x18022414f  movss   xmm0, dword ptr [r13+10h]
0x180224155  lea     rcx, [rsp+260h+var_220]
0x18022415a  mov     eax, [r13+8]
0x18022415e  mov     r9d, [r15+8]
0x180224162  mov     r8d, [r15+4]
0x180224166  mov     rdx, [rsp+260h+var_218]
0x18022416b  mov     [rsp+260h+var_230], rcx
0x180224170  mov     rcx, rsi
0x180224173  movss   dword ptr [rsp+260h+var_238], xmm0
0x180224179  mov     dword ptr [rsp+260h+var_240], eax
0x18022417d  call    ?CreateRenderTargetBitmap@CD3DDevice@@QEAAJPEAUID3D11Texture2D@@W4DXGI_ALPHA_MODE@@W4DXGI_COLOR_SPACE_TYPE@@VDisplayId@@MPEAPEAVIRenderTargetBitmap@@@Z; CD3DDevice::CreateRenderTargetBitmap(ID3D11Texture2D *,DXGI_ALPHA_MODE,DXGI_COLOR_SPACE_TYPE,DisplayId,float,IRenderTargetBitmap * *)
0x180224182  mov     ebx, eax
0x180224184  test    eax, eax
0x180224186  js      loc_180224212
0x18022418c  lea     rcx, [rsp+260h+var_218]
0x180224191  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180224196  mov     r14, [rsp+260h+var_208]
0x18022419b  mov     rbx, [rsp+260h+var_220]
0x1802241a0  mov     rcx, rbx
0x1802241a3  mov     rax, [rbx]
0x1802241a6  mov     rax, [rax+90h]
0x1802241ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802241b2  mov     rcx, rax
0x1802241b5  mov     dl, 1
0x1802241b7  mov     r8, [rax]
0x1802241ba  mov     rax, [r8+0E0h]
0x1802241c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802241c6  mov     rax, [rsp+260h+var_1F8]
0x1802241cb  lea     r8, [rsp+260h+var_200]; struct _UNSIGNED_RATIO *
0x1802241d0  mov     [rsp+260h+var_238], rax; struct ILegacyRemotingSwapChain **
0x1802241d5  lea     rdx, [rbp+160h+var_130]; unsigned __int16 *
0x1802241d9  mov     r9, rbx; struct IRenderTargetBitmap *
0x1802241dc  mov     [rsp+260h+var_240], r14; void *
0x1802241e1  mov     rcx, rsi; struct CD3DDevice *
0x1802241e4  mov     [rsp+260h+var_208], 0
0x1802241ed  call    ?Create@CLegacyRemotingSwapChain@@KAJPEAVCD3DDevice@@PEBGAEBU_UNSIGNED_RATIO@@PEAVIRenderTargetBitmap@@PEAXPEAPEAVILegacyRemotingSwapChain@@@Z; CLegacyRemotingSwapChain::Create(CD3DDevice *,ushort const *,_UNSIGNED_RATIO const &,IRenderTargetBitmap *,void *,ILegacyRemotingSwapChain * *)
0x1802241f2  mov     ebx, eax
0x1802241f4  test    eax, eax
0x1802241f6  jns     loc_1802242CB
0x1802241fc  mov     [rsp+260h+var_238], 0
0x180224205  mov     dword ptr [rsp+260h+var_240], 356h
0x18022420d  jmp     loc_180224002
0x180224212  mov     [rsp+260h+var_238], r14
0x180224217  mov     dword ptr [rsp+260h+var_240], 340h
0x18022421f  mov     r9d, eax
0x180224222  jmp     loc_180224115
0x180224227  mov     [rsp+260h+var_238], r14
0x18022422c  mov     dword ptr [rsp+260h+var_240], 333h
0x180224234  jmp     short loc_18022421F
0x180224236  mov     [rsp+260h+var_238], r14; void *
0x18022423b  lea     rdx, qword_1803554C8; int *
0x180224242  mov     r9d, eax; int
0x180224245  mov     dword ptr [rsp+260h+var_240], 330h; unsigned int
0x18022424d  mov     r8d, edi; unsigned int
0x180224250  mov     ecx, 14h; unsigned int
0x180224255  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18022425a  lea     rcx, [rsp+260h+var_218]
0x18022425f  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180224264  mov     rcx, [rsi+240h]
0x18022426b  xor     r8d, r8d
0x18022426e  xor     edx, edx
0x180224270  mov     rax, [rcx]
0x180224273  mov     rax, [rax+20h]
0x180224277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022427c  jmp     short loc_1802242CB
0x18022427e  mov     [rsp+260h+var_238], r14
0x180224283  mov     dword ptr [rsp+260h+var_240], 320h
0x18022428b  jmp     short loc_18022421F
0x18022428d  mov     [rsp+260h+var_238], rdi
0x180224292  mov     r9d, eax
0x180224295  mov     dword ptr [rsp+260h+var_240], 313h
0x18022429d  jmp     short loc_1802242B4
0x18022429f  mov     ebx, 8898008Dh
0x1802242a4  mov     [rsp+260h+var_238], rdi; void *
0x1802242a9  mov     r9d, ebx; int
0x1802242ac  mov     dword ptr [rsp+260h+var_240], 310h; unsigned int
0x1802242b4  mov     r8d, 2; unsigned int
0x1802242ba  lea     rdx, qword_1803554C8; int *
0x1802242c1  mov     ecx, 14h; unsigned int
0x1802242c6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1802242cb  lea     rcx, [rsp+260h+var_208]
0x1802242d0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802242d5  lea     rcx, [rsp+260h+var_220]
0x1802242da  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802242df  mov     eax, ebx
0x1802242e1  mov     rcx, [rbp+160h+var_50]
0x1802242e8  xor     rcx, rsp; StackCookie
0x1802242eb  call    __security_check_cookie
0x1802242f0  add     rsp, 228h
0x1802242f7  pop     r15
0x1802242f9  pop     r14
0x1802242fb  pop     r13
0x1802242fd  pop     r12
0x1802242ff  pop     rdi
0x180224300  pop     rsi
0x180224301  pop     rbx
0x180224302  pop     rbp
0x180224303  retn
```
