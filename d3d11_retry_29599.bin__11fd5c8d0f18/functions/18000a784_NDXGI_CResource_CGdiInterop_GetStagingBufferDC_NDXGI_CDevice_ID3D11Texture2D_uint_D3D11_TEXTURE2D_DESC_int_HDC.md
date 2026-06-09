# NDXGI::CResource::CGdiInterop::GetStagingBufferDC(NDXGI::CDevice *,ID3D11Texture2D *,uint,D3D11_TEXTURE2D_DESC *,int,HDC__ * *)

- ea: `0x18000a784`
- end: `0x18000abbf`
- name: `?GetStagingBufferDC@CGdiInterop@CResource@NDXGI@@AEAAJPEAVCDevice@3@PEAUID3D11Texture2D@@IPEAUD3D11_TEXTURE2D_DESC@@HPEAPEAUHDC__@@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(NDXGI::CResource::CGdiInterop *__hidden this, struct CDevice *, struct ID3D11Texture2D *, unsigned int, struct D3D11_TEXTURE2D_DESC *, int, HDC *)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800093f4`
- `0x180009950`

## callees

- `0x18000a784`
- `0x180022400`
- `0x18002c7f0`
- `0x18002d0f0`
- `0x18002e160`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800da6c0`
- `0x1801cb010`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-gdi-l1-1-0!D3DKMTCreateDCFromMemory` at `0x18000aa66`
- `ext-ms-win-dx-d3dkmt-gdi-l1-1-0!D3DKMTCreateDCFromMemory` at `0x18000aa66`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000aa71`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000aa71`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x18000a9f0`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x18000a9f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NDXGI::CResource::CGdiInterop::GetStagingBufferDC(
        NDXGI::CResource::CGdiInterop *this,
        struct CDevice *a2,
        struct ID3D11Texture2D *a3,
        int a4,
        struct D3D11_TEXTURE2D_DESC *a5,
        int a6,
        HDC *a7)
{
  UINT v11; // r15d
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // r14
  void (__fastcall ***v15)(_QWORD, GUID *, size_t *); // rcx
  int v16; // edi
  HDC DCW; // r15
  signed int v18; // ebx
  char *v20; // rdi
  size_t Size; // [rsp+50h] [rbp-158h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-150h] BYREF
  __int64 v23; // [rsp+60h] [rbp-148h] BYREF
  __int64 v24; // [rsp+68h] [rbp-140h] BYREF
  void (__fastcall ***v25)(_QWORD, GUID *, size_t *); // [rsp+70h] [rbp-138h] BYREF
  __int64 v26; // [rsp+78h] [rbp-130h] BYREF
  HDC *v27; // [rsp+80h] [rbp-128h]
  void *v28[2]; // [rsp+88h] [rbp-120h] BYREF
  __int128 v29; // [rsp+98h] [rbp-110h] BYREF
  _BYTE v30[16]; // [rsp+A8h] [rbp-100h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-F0h]
  __int64 v32; // [rsp+C0h] [rbp-E8h]
  D3DKMT_CREATEDCFROMMEMORY v33; // [rsp+D0h] [rbp-D8h] BYREF
  _DWORD v34[5]; // [rsp+110h] [rbp-98h] BYREF
  DXGI_SAMPLE_DESC SampleDesc; // [rsp+124h] [rbp-84h]
  __int64 v36; // [rsp+12Ch] [rbp-7Ch]
  __int64 v37; // [rsp+134h] [rbp-74h]
  char v38[32]; // [rsp+140h] [rbp-68h] BYREF

  v27 = a7;
  v34[0] = a5->Width;
  v34[1] = a5->Height;
  v34[2] = 1;
  v34[3] = 1;
  v34[4] = a5->Format;
  SampleDesc = a5->SampleDesc;
  v36 = 3;
  v11 = 0;
  v37 = 196608;
  v24 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, __int64 *))(**((_QWORD **)a2 + 8) + 40LL))(
          *((_QWORD *)a2 + 8),
          v34,
          0,
          &v24);
  ThrowFailure(v12);
  strcpy(v38, "Staging Texture for GDI Interop");
  (*(void (__fastcall **)(__int64, const GUID *, __int64, char *))(*(_QWORD *)v24 + 40LL))(
    v24,
    &WKPDID_D3DDebugObjectName,
    31,
    v38);
  v26 = 0;
  ((void (__fastcall *)(struct ID3D11Texture2D *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
    a3,
    &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7,
    &v26);
  v23 = 0;
  (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v24)(v24, &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7, &v23);
  CDevCtxInterface::CDevCtxInterface(
    (CDevCtxInterface *)v30,
    *(struct CContext **)(*((_QWORD *)a2 + 9) + 1080LL),
    1,
    0,
    0);
  v13 = v31;
  v14 = v32;
  if ( !a6 )
  {
    if ( (a5->MiscFlags & 0x1000) != 0 )
    {
      *(_OWORD *)v28 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, void **))(v31 + 112))(
             v32,
             v23,
             0,
             3,
             0,
             v28) >= 0 )
      {
        v20 = (char *)v28[0];
        LODWORD(Size) = 0;
        CD3D11FormatHelper::CalculateMinimumRowMajorRowPitch(a5->Format, a5->Width, (unsigned int *)&Size);
        if ( a5->Height )
        {
          do
          {
            memset_0(v20, 0, (unsigned int)Size);
            v20 += LODWORD(v28[1]);
            ++v11;
          }
          while ( v11 < a5->Height );
        }
      }
    }
    v22 = 0;
    v25 = 0;
    (*(void (__fastcall **)(__int64, _QWORD, unsigned int *))(v13 + 688))(v14, &v25, &v22);
    if ( v25 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v13 + 240))(v14, 0, v22);
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _DWORD, __int64, int, _QWORD))(v13 + 368))(
      v14,
      v23,
      0,
      0,
      0,
      0,
      v26,
      a4,
      0);
    v15 = v25;
    if ( v25 )
    {
      Size = 0;
      (**v25)(v25, &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7, &Size);
      (*(void (__fastcall **)(__int64, size_t, _QWORD))(v13 + 240))(v14, Size, v22);
      ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>(&Size);
      v15 = v25;
    }
    if ( v15 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, size_t *)))(*v15)[2])(v15);
  }
  v29 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, __int128 *))(v13 + 112))(
          v14,
          v23,
          0,
          3,
          0,
          &v29);
  if ( v16 < 0 )
    goto LABEL_19;
  DCW = CreateDCW(L"display", 0, 0, 0);
  if ( !DCW )
  {
    v16 = -2147024882;
LABEL_22:
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(v13 + 120))(v14, v23, 0);
LABEL_19:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    ThrowFailure(v16);
    goto LABEL_14;
  }
  memset(&v33.pColorTable, 0, 24);
  v33.pMemory = (void *)v29;
  v33.Format = D3DDDIFMT_A8R8G8B8;
  v33.Width = a5->Width;
  v33.Height = a5->Height;
  v33.Pitch = DWORD2(v29);
  v33.hDeviceDc = DCW;
  v18 = D3DKMTCreateDCFromMemory(&v33);
  DeleteDC(DCW);
  if ( v18 < 0 )
  {
    v16 = -2147024882;
  }
  else
  {
    *v27 = v33.hDc;
    *((_QWORD *)this + 1) = v33.hBitmap;
    *((_QWORD *)this + 2) = v24;
  }
  if ( v16 < 0 )
    goto LABEL_22;
LABEL_14:
  CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v30);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x18000a784  mov     r11, rsp
0x18000a787  push    rbx
0x18000a788  push    rsi
0x18000a789  push    rdi
0x18000a78a  push    r12
0x18000a78c  push    r13
0x18000a78e  push    r14
0x18000a790  push    r15
0x18000a792  sub     rsp, 170h
0x18000a799  mov     rax, cs:__security_cookie
0x18000a7a0  xor     rax, rsp
0x18000a7a3  mov     [rsp+1A8h+var_48], rax
0x18000a7ab  mov     r12d, r9d
0x18000a7ae  mov     rdi, r8
0x18000a7b1  mov     rsi, rdx
0x18000a7b4  mov     r13, rcx
0x18000a7b7  mov     rbx, [rsp+1A8h+arg_20]
0x18000a7bf  mov     rax, [rsp+1A8h+arg_30]
0x18000a7c7  mov     [rsp+1A8h+var_128], rax
0x18000a7cf  mov     eax, [rbx]
0x18000a7d1  mov     [rsp+1A8h+var_98], eax
0x18000a7d8  mov     eax, [rbx+4]
0x18000a7db  mov     [rsp+1A8h+var_94], eax
0x18000a7e2  mov     r14d, 1
0x18000a7e8  mov     [r11-90h], r14d
0x18000a7ef  mov     [r11-8Ch], r14d
0x18000a7f6  mov     eax, [rbx+10h]
0x18000a7f9  mov     [rsp+1A8h+var_88], eax
0x18000a800  mov     rax, [rbx+14h]
0x18000a804  mov     [r11-84h], rax
0x18000a80b  mov     qword ptr [r11-7Ch], 3
0x18000a813  xor     r15d, r15d
0x18000a816  mov     qword ptr [r11-74h], 30000h
0x18000a81e  mov     [rsp+1A8h+var_140], r15
0x18000a823  mov     rcx, [rdx+40h]
0x18000a827  mov     rax, [rcx]
0x18000a82a  lea     r9, [rsp+1A8h+var_140]
0x18000a82f  xor     r8d, r8d
0x18000a832  lea     rdx, [r11-98h]
0x18000a839  mov     rax, [rax+28h]
0x18000a83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a842  mov     ecx, eax; int
0x18000a844  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18000a849  movups  xmm0, xmmword ptr cs:aStagingTexture; "Staging Texture for GDI Interop"
0x18000a850  movups  xmmword ptr [rsp+1A8h+var_68], xmm0
0x18000a858  movups  xmm1, xmmword ptr cs:aStagingTexture+10h; "for GDI Interop"
0x18000a85f  movups  xmmword ptr [rsp+1A8h+var_68+10h], xmm1
0x18000a867  mov     rcx, [rsp+1A8h+var_140]
0x18000a86c  mov     rax, [rcx]
0x18000a86f  lea     r9, [rsp+1A8h+var_68]
0x18000a877  lea     r8d, [r14+1Eh]
0x18000a87b  lea     rdx, WKPDID_D3DDebugObjectName
0x18000a882  mov     rax, [rax+28h]
0x18000a886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a88b  mov     [rsp+1A8h+var_130], r15
0x18000a890  mov     rax, [rdi]
0x18000a893  lea     r8, [rsp+1A8h+var_130]
0x18000a898  lea     rdx, _GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7
0x18000a89f  mov     rcx, rdi
0x18000a8a2  mov     rax, [rax]
0x18000a8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8aa  mov     [rsp+1A8h+var_148], r15
0x18000a8af  mov     rcx, [rsp+1A8h+var_140]
0x18000a8b4  mov     rax, [rcx]
0x18000a8b7  lea     r8, [rsp+1A8h+var_148]
0x18000a8bc  lea     rdx, _GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7
0x18000a8c3  mov     rax, [rax]
0x18000a8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8cb  mov     rdx, [rsi+48h]
0x18000a8cf  mov     [rsp+1A8h+var_188], r15b; bool
0x18000a8d4  xor     r9d, r9d; bool
0x18000a8d7  mov     r8b, r14b; bool
0x18000a8da  mov     rdx, [rdx+438h]; struct CContext *
0x18000a8e1  lea     rcx, [rsp+1A8h+var_100]; this
0x18000a8e9  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x18000a8ee  nop
0x18000a8ef  mov     rsi, [rsp+1A8h+var_F0]
0x18000a8f7  mov     r14, [rsp+1A8h+var_E8]
0x18000a8ff  cmp     [rsp+1A8h+arg_28], r15d
0x18000a907  jnz     loc_18000A9A0
0x18000a90d  test    dword ptr [rbx+28h], 1000h
0x18000a914  jnz     loc_1800E83F8
0x18000a91a  mov     [rsp+1A8h+var_150], r15d
0x18000a91f  mov     [rsp+1A8h+var_138], r15
0x18000a924  lea     r8, [rsp+1A8h+var_150]
0x18000a929  lea     rdx, [rsp+1A8h+var_138]
0x18000a92e  mov     rcx, r14
0x18000a931  mov     rax, [rsi+2B0h]
0x18000a938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a93d  cmp     [rsp+1A8h+var_138], r15
0x18000a942  jnz     loc_18000AB33
0x18000a948  mov     [rsp+1A8h+var_168], r15
0x18000a94d  mov     [rsp+1A8h+var_170], r12d
0x18000a952  mov     rcx, [rsp+1A8h+var_130]
0x18000a957  mov     [rsp+1A8h+var_178], rcx
0x18000a95c  mov     dword ptr [rsp+1A8h+var_180], r15d
0x18000a961  mov     dword ptr [rsp+1A8h+var_188], r15d
0x18000a966  xor     r9d, r9d
0x18000a969  xor     r8d, r8d
0x18000a96c  mov     rdx, [rsp+1A8h+var_148]
0x18000a971  mov     rcx, r14
0x18000a974  mov     rax, [rsi+170h]
0x18000a97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a980  mov     rcx, [rsp+1A8h+var_138]
0x18000a985  test    rcx, rcx
0x18000a988  jnz     loc_18000AB4E
0x18000a98e  test    rcx, rcx
0x18000a991  jz      short loc_18000A9A0
0x18000a993  mov     rax, [rcx]
0x18000a996  mov     rax, [rax+10h]
0x18000a99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a99f  nop
0x18000a9a0  xorps   xmm0, xmm0
0x18000a9a3  movups  [rsp+1A8h+var_110], xmm0
0x18000a9ab  lea     rax, [rsp+1A8h+var_110]
0x18000a9b3  mov     [rsp+1A8h+var_180], rax
0x18000a9b8  mov     dword ptr [rsp+1A8h+var_188], r15d
0x18000a9bd  mov     r9d, 3
0x18000a9c3  xor     r8d, r8d
0x18000a9c6  mov     rdx, [rsp+1A8h+var_148]
0x18000a9cb  mov     rcx, r14
0x18000a9ce  mov     rax, [rsi+70h]
0x18000a9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d7  mov     edi, eax
0x18000a9d9  test    eax, eax
0x18000a9db  js      loc_18000AB0F
0x18000a9e1  xor     r9d, r9d; pdm
0x18000a9e4  xor     r8d, r8d; pszPort
0x18000a9e7  xor     edx, edx; pwszDevice
0x18000a9e9  lea     rcx, pwszDriver; "display"
0x18000a9f0  call    cs:__imp_CreateDCW
0x18000a9f6  mov     r15, rax
0x18000a9f9  test    rax, rax
0x18000a9fc  jz      loc_18000AB98
0x18000aa02  xorps   xmm0, xmm0
0x18000aa05  movdqu  xmmword ptr [rsp+1A8h+var_D8.pColorTable], xmm0
0x18000aa0e  mov     [rsp+1A8h+var_D8.hBitmap], 0
0x18000aa1a  mov     rcx, qword ptr [rsp+1A8h+var_110]
0x18000aa22  mov     [rsp+1A8h+var_D8.pMemory], rcx
0x18000aa2a  mov     [rsp+1A8h+var_D8.Format], 15h
0x18000aa35  mov     ecx, [rbx]
0x18000aa37  mov     [rsp+1A8h+var_D8.Width], ecx
0x18000aa3e  mov     ecx, [rbx+4]
0x18000aa41  mov     [rsp+1A8h+var_D8.Height], ecx
0x18000aa48  mov     eax, dword ptr [rsp+1A8h+var_110+8]
0x18000aa4f  mov     [rsp+1A8h+var_D8.Pitch], eax
0x18000aa56  mov     [rsp+1A8h+var_D8.hDeviceDc], r15
0x18000aa5e  lea     rcx, [rsp+1A8h+var_D8]; D3DKMT_CREATEDCFROMMEMORY *
0x18000aa66  call    cs:__imp_D3DKMTCreateDCFromMemory
0x18000aa6c  mov     ebx, eax
0x18000aa6e  mov     rcx, r15; hdc
0x18000aa71  call    cs:__imp_DeleteDC
0x18000aa77  test    ebx, ebx
0x18000aa79  js      loc_18000AB29
0x18000aa7f  mov     rax, [rsp+1A8h+var_D8.hDc]
0x18000aa87  mov     rcx, [rsp+1A8h+var_128]
0x18000aa8f  mov     [rcx], rax
0x18000aa92  mov     rax, [rsp+1A8h+var_D8.hBitmap]
0x18000aa9a  mov     [r13+8], rax
0x18000aa9e  mov     rax, [rsp+1A8h+var_140]
0x18000aaa3  mov     [r13+10h], rax
0x18000aaa7  test    edi, edi
0x18000aaa9  js      loc_18000AB9D
0x18000aaaf  lea     rcx, [rsp+1A8h+var_100]; this
0x18000aab7  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x18000aabc  nop
0x18000aabd  mov     rcx, [rsp+1A8h+var_148]
0x18000aac2  test    rcx, rcx
0x18000aac5  jz      short loc_18000AAD4
0x18000aac7  mov     rax, [rcx]
0x18000aaca  mov     rax, [rax+10h]
0x18000aace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aad3  nop
0x18000aad4  mov     rcx, [rsp+1A8h+var_130]
0x18000aad9  test    rcx, rcx
0x18000aadc  jz      short loc_18000AAEA
0x18000aade  mov     rax, [rcx]
0x18000aae1  mov     rax, [rax+10h]
0x18000aae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaea  xor     eax, eax
0x18000aaec  mov     rcx, [rsp+1A8h+var_48]
0x18000aaf4  xor     rcx, rsp; StackCookie
0x18000aaf7  call    __security_check_cookie
0x18000aafc  add     rsp, 170h
0x18000ab03  pop     r15
0x18000ab05  pop     r14
0x18000ab07  pop     r13
0x18000ab09  pop     r12
0x18000ab0b  pop     rdi
0x18000ab0c  pop     rsi
0x18000ab0d  pop     rbx
0x18000ab0e  retn
0x18000ab0f  mov     rcx, [rsp+1A8h+var_140]
0x18000ab14  mov     rax, [rcx]
0x18000ab17  mov     rax, [rax+10h]
0x18000ab1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab20  mov     ecx, edi; int
0x18000ab22  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18000ab27  jmp     short loc_18000AAAF
0x18000ab29  mov     edi, 8007000Eh
0x18000ab2e  jmp     loc_18000AAA7
0x18000ab33  mov     r8d, [rsp+1A8h+var_150]
0x18000ab38  xor     edx, edx
0x18000ab3a  mov     rcx, r14
0x18000ab3d  mov     rax, [rsi+0F0h]
0x18000ab44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab49  jmp     loc_18000A948
0x18000ab4e  mov     [rsp+1A8h+Size], r15
0x18000ab53  mov     rax, [rcx]
0x18000ab56  lea     r8, [rsp+1A8h+Size]
0x18000ab5b  lea     rdx, _GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7
0x18000ab62  mov     rax, [rax]
0x18000ab65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab6a  mov     r8d, [rsp+1A8h+var_150]
0x18000ab6f  mov     rdx, [rsp+1A8h+Size]
0x18000ab74  mov     rcx, r14
0x18000ab77  mov     rax, [rsi+0F0h]
0x18000ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab83  nop
0x18000ab84  lea     rcx, [rsp+1A8h+Size]
0x18000ab89  call    ??1?$CComPtrBase@VCBuffer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>(void)
0x18000ab8e  mov     rcx, [rsp+1A8h+var_138]
0x18000ab93  jmp     loc_18000A98E
0x18000ab98  mov     edi, 8007000Eh
0x18000ab9d  xor     r8d, r8d
0x18000aba0  mov     rdx, [rsp+1A8h+var_148]
0x18000aba5  mov     rcx, r14
0x18000aba8  mov     rax, [rsi+78h]
0x18000abac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb1  jmp     loc_18000AB0F
0x18000abb6  mov     eax, dword ptr [rsp+1A8h+Size]
0x18000abba  jmp     loc_18000AAEC
0x1800e83f8  xorps   xmm0, xmm0
0x1800e83fb  movups  xmmword ptr [rsp+1A8h+var_120], xmm0
0x1800e8403  lea     rax, [rsp+1A8h+var_120]
0x1800e840b  mov     [rsp+1A8h+var_180], rax
0x1800e8410  mov     dword ptr [rsp+1A8h+var_188], r15d
0x1800e8415  mov     r9d, 3
0x1800e841b  xor     r8d, r8d
0x1800e841e  mov     rdx, [rsp+1A8h+var_148]
0x1800e8423  mov     rcx, r14
0x1800e8426  mov     rax, [rsi+70h]
0x1800e842a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e842f  test    eax, eax
0x1800e8431  js      loc_18000A91A
0x1800e8437  mov     rdi, [rsp+1A8h+var_120]
0x1800e843f  mov     dword ptr [rsp+1A8h+Size], r15d
0x1800e8444  lea     r8, [rsp+1A8h+Size]; unsigned int *
0x1800e8449  mov     edx, [rbx]; unsigned int
0x1800e844b  mov     ecx, [rbx+10h]; enum DXGI_FORMAT
0x1800e844e  call    ?CalculateMinimumRowMajorRowPitch@CD3D11FormatHelper@@SAJW4DXGI_FORMAT@@IAEAI@Z; CD3D11FormatHelper::CalculateMinimumRowMajorRowPitch(DXGI_FORMAT,uint,uint &)
0x1800e8453  cmp     dword ptr [rbx+4], 0
0x1800e8457  jbe     short loc_1800E847B
0x1800e8459  mov     r8d, dword ptr [rsp+1A8h+Size]; Size
0x1800e845e  xor     edx, edx; Val
0x1800e8460  mov     rcx, rdi; void *
0x1800e8463  call    memset_0
0x1800e8468  mov     eax, dword ptr [rsp+1A8h+var_120+8]
0x1800e846f  add     rdi, rax
0x1800e8472  inc     r15d
0x1800e8475  cmp     r15d, [rbx+4]
0x1800e8479  jb      short loc_1800E8459
0x1800e847b  xor     r15d, r15d
0x1800e847e  jmp     loc_18000A91A
```
