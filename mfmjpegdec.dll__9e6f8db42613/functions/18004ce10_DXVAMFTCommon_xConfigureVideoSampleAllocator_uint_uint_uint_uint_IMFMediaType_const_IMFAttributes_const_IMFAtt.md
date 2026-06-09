# DXVAMFTCommon::xConfigureVideoSampleAllocator(uint,uint,uint,uint,IMFMediaType * const,IMFAttributes * const,IMFAttributes * const)

- ea: `0x18004ce10`
- end: `0x18004d082`
- name: `?xConfigureVideoSampleAllocator@DXVAMFTCommon@@IEAAJIIIIQEAUIMFMediaType@@QEAUIMFAttributes@@1@Z`
- size: `626`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, struct IMFMediaType *const, struct IMFAttributes *const, struct IMFAttributes *const)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x180020598`
- `0x1800239d4`
- `0x180023b84`
- `0x180024220`
- `0x18004b04c`
- `0x18004b1e0`
- `0x18004b4a4`
- `0x18004ce10`
- `0x18005652c`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18004cece`
- `MFPlat!MFCreateAttributes` at `0x18004cece`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x18004ce6f`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x18004ce6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall DXVAMFTCommon::xConfigureVideoSampleAllocator(
        DXVAMFTCommon *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct IMFMediaType *const a6,
        struct IMFAttributes *const a7,
        struct IMFAttributes *const a8)
{
  void **v9; // rdi
  HRESULT result; // eax
  HRESULT v11; // esi
  int v12; // edx
  enum DXGI_FORMAT *v13; // r8
  bool v14; // cl
  __int64 v15; // rsi
  __int64 v16; // rdx
  struct IMFDXGIDeviceManager *v17; // rdx
  bool v18; // bl
  int v19; // ebx
  int v20; // r8d
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-50h] BYREF
  struct ID3D12Device *v22; // [rsp+38h] [rbp-48h] BYREF
  struct _GUID v23; // [rsp+40h] [rbp-40h] BYREF
  __int128 v24; // [rsp+50h] [rbp-30h] BYREF
  int v25[4]; // [rsp+60h] [rbp-20h] BYREF

  *(_OWORD *)v25 = 0;
  v9 = (void **)((char *)this + 408);
  if ( *((_QWORD *)this + 51)
    || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 408),
        (result = MFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, v9)) == 0) )
  {
    ppMFAttributes = 0;
    *(_DWORD *)v23.Data4 = 1;
    v11 = ((__int64 (__fastcall *)(struct IMFMediaType *const, const GUID *, int *))a6->lpVtbl->GetGUID)(
            a6,
            &MF_MT_SUBTYPE,
            v25);
    if ( v11
      || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes),
          (v11 = MFCreateAttributes(&ppMFAttributes, 1u)) != 0)
      || (v11 = ResolveFlagsForMFSampleAllocator(
                  (int)v25,
                  v12,
                  (int)a7,
                  (int)a8,
                  *((struct IMFDXGIDeviceManager **)this + 50),
                  (__int64)ppMFAttributes)) != 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
      return v11;
    }
    else
    {
      v14 = 0;
      v15 = *((_QWORD *)this + 50);
      if ( v15 )
      {
        *(_DWORD *)&v23.Data2 = 0;
        LODWORD(v22) = 0;
        v23.Data1 = 0;
        v24 = *(_OWORD *)v25;
        v14 = (int)MFMEDIATYPEUtils::SubtypeToDXGIFormat((MFMEDIATYPEUtils *)&v24, &v23, v13) >= 0
           && ((int)GetTextureFormatSupport(v23.Data1, v15, &v23.Data2, &v22) < 0
            || (*(_DWORD *)&v23.Data2 & 0x8004200) != 0);
      }
      if ( v14 )
        v16 = *((_QWORD *)this + 50);
      else
        v16 = 0;
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, v16);
      ((void (__fastcall *)(struct IMFAttributes *const, __int64 *, unsigned __int8 *))a8->lpVtbl->GetUINT32)(
        a8,
        MF_SA_MINIMUM_OUTPUT_SAMPLE_COUNT,
        v23.Data4);
      v17 = (struct IMFDXGIDeviceManager *)*((_QWORD *)this + 50);
      if ( !v17 )
        goto LABEL_19;
      DXGIDeviceManagerRAII::DXGIDeviceManagerRAII((DXGIDeviceManagerRAII *)&v24, v17);
      v22 = 0;
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)v24 + 48LL))(v24, (char *)&v24 + 8);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      DXGIDeviceManagerRAII::GetService((DXGIDeviceManagerRAII *)&v24, &v22);
      v18 = v22 != 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      DXGIDeviceManagerRAII::~DXGIDeviceManagerRAII((DXGIDeviceManagerRAII *)&v24);
      if ( !v18
        || (v19 = ((__int64 (__fastcall *)(struct IMFMediaType *const, __int64 *, __int64))a6->lpVtbl->SetUINT32)(
                    a6,
                    MF_MT_D3D_RESOURCE_VERSION,
                    1)) == 0 )
      {
LABEL_19:
        v20 = *(_DWORD *)v23.Data4;
        if ( !*(_DWORD *)v23.Data4 )
          v20 = 1;
        v19 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, IMFAttributes *, struct IMFMediaType *const))(*(_QWORD *)*v9 + 56LL))(
                *v9,
                1,
                (unsigned int)(v20 + 2),
                ppMFAttributes,
                a6);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
      return v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004ce10  mov     [rsp-28h+arg_8], rbx
0x18004ce15  mov     [rsp-28h+arg_10], rsi
0x18004ce1a  push    rbp
0x18004ce1b  push    rdi
0x18004ce1c  push    r12
0x18004ce1e  push    r14
0x18004ce20  push    r15
0x18004ce22  mov     rbp, rsp
0x18004ce25  sub     rsp, 80h
0x18004ce2c  mov     rax, cs:__security_cookie
0x18004ce33  xor     rax, rsp
0x18004ce36  mov     [rbp+var_10], rax
0x18004ce3a  mov     rbx, rcx
0x18004ce3d  mov     r14, [rbp+arg_28]
0x18004ce41  mov     r15, [rbp+arg_30]
0x18004ce45  mov     r12, [rbp+arg_38]
0x18004ce49  xorps   xmm0, xmm0
0x18004ce4c  movups  xmmword ptr [rbp+var_20], xmm0
0x18004ce50  lea     rdi, [rcx+198h]
0x18004ce57  cmp     qword ptr [rdi], 0
0x18004ce5b  jnz     short loc_18004CE7D
0x18004ce5d  mov     rcx, rdi
0x18004ce60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ce65  mov     rdx, rdi; ppSampleAllocator
0x18004ce68  lea     rcx, _GUID_545b3a48_3283_4f62_866f_a62d8f598f9f; riid
0x18004ce6f  call    cs:__imp_MFCreateVideoSampleAllocatorEx
0x18004ce75  test    eax, eax
0x18004ce77  jnz     loc_18004D05A
0x18004ce7d  mov     [rbp+ppMFAttributes], 0
0x18004ce85  mov     dword ptr [rbp+var_40.Data4], 1
0x18004ce8c  mov     rax, [r14]
0x18004ce8f  lea     r8, [rbp+var_20]
0x18004ce93  lea     rdx, MF_MT_SUBTYPE
0x18004ce9a  mov     rcx, r14
0x18004ce9d  mov     rax, [rax+50h]
0x18004cea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cea6  mov     esi, eax
0x18004cea8  test    eax, eax
0x18004ceaa  jz      short loc_18004CEBC
0x18004ceac  lea     rcx, [rbp+ppMFAttributes]
0x18004ceb0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ceb5  mov     eax, esi
0x18004ceb7  jmp     loc_18004D05A
0x18004cebc  lea     rcx, [rbp+ppMFAttributes]
0x18004cec0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cec5  mov     edx, 1; cInitialSize
0x18004ceca  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004cece  call    cs:__imp_MFCreateAttributes
0x18004ced4  mov     esi, eax
0x18004ced6  test    eax, eax
0x18004ced8  jnz     short loc_18004CEAC
0x18004ceda  mov     rax, [rbp+ppMFAttributes]
0x18004cede  mov     [rsp+80h+var_58], rax; __int64
0x18004cee3  mov     rax, [rbx+190h]
0x18004ceea  mov     [rsp+80h+var_60], rax; struct IMFDXGIDeviceManager *
0x18004ceef  mov     r9, r12; int
0x18004cef2  mov     r8, r15; int
0x18004cef5  lea     rcx, [rbp+var_20]; int
0x18004cef9  call    ResolveFlagsForMFSampleAllocator
0x18004cefe  mov     esi, eax
0x18004cf00  test    eax, eax
0x18004cf02  jnz     short loc_18004CEAC
0x18004cf04  xor     cl, cl
0x18004cf06  mov     rsi, [rbx+190h]
0x18004cf0d  test    rsi, rsi
0x18004cf10  jz      short loc_18004CF5B
0x18004cf12  mov     dword ptr [rbp+var_40.Data2], eax
0x18004cf15  mov     dword ptr [rbp+var_48], eax
0x18004cf18  mov     [rbp+var_40.Data1], eax
0x18004cf1b  movaps  xmm0, xmmword ptr [rbp+var_20]
0x18004cf1f  movdqa  [rbp+var_30], xmm0
0x18004cf24  lea     rdx, [rbp+var_40]; struct _GUID
0x18004cf28  lea     rcx, [rbp+var_30]; this
0x18004cf2c  call    ?SubtypeToDXGIFormat@MFMEDIATYPEUtils@@YAJU_GUID@@PEAW4DXGI_FORMAT@@@Z; MFMEDIATYPEUtils::SubtypeToDXGIFormat(_GUID,DXGI_FORMAT *)
0x18004cf31  test    eax, eax
0x18004cf33  js      short loc_18004CF59
0x18004cf35  lea     r9, [rbp+var_48]
0x18004cf39  lea     r8, [rbp+var_40.Data2]
0x18004cf3d  mov     rdx, rsi
0x18004cf40  mov     ecx, [rbp+var_40.Data1]
0x18004cf43  call    GetTextureFormatSupport
0x18004cf48  test    eax, eax
0x18004cf4a  js      short loc_18004CF55
0x18004cf4c  test    dword ptr [rbp+var_40.Data2], 8004200h
0x18004cf53  jz      short loc_18004CF59
0x18004cf55  mov     cl, 1
0x18004cf57  jmp     short loc_18004CF5B
0x18004cf59  xor     cl, cl
0x18004cf5b  mov     r8, [rdi]
0x18004cf5e  mov     rax, [r8]
0x18004cf61  test    cl, cl
0x18004cf63  jz      short loc_18004CF6E
0x18004cf65  mov     rdx, [rbx+190h]
0x18004cf6c  jmp     short loc_18004CF70
0x18004cf6e  xor     edx, edx
0x18004cf70  mov     rcx, r8
0x18004cf73  mov     rax, [rax+18h]
0x18004cf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf7c  mov     rax, [r12]
0x18004cf80  lea     r8, [rbp+var_40.Data4]
0x18004cf84  lea     rdx, MF_SA_MINIMUM_OUTPUT_SAMPLE_COUNT
0x18004cf8b  mov     rcx, r12
0x18004cf8e  mov     rax, [rax+38h]
0x18004cf92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf97  mov     rdx, [rbx+190h]; struct IMFDXGIDeviceManager *
0x18004cf9e  test    rdx, rdx
0x18004cfa1  jz      short loc_18004D021
0x18004cfa3  lea     rcx, [rbp+var_30]; this
0x18004cfa7  call    ??0DXGIDeviceManagerRAII@@QEAA@PEAUIMFDXGIDeviceManager@@@Z; DXGIDeviceManagerRAII::DXGIDeviceManagerRAII(IMFDXGIDeviceManager *)
0x18004cfac  mov     [rbp+var_48], 0
0x18004cfb4  mov     rcx, qword ptr [rbp+var_30]
0x18004cfb8  mov     rax, [rcx]
0x18004cfbb  lea     rdx, [rbp+var_30+8]
0x18004cfbf  mov     rax, [rax+30h]
0x18004cfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfc8  lea     rcx, [rbp+var_48]
0x18004cfcc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cfd1  lea     rdx, [rbp+var_48]; struct ID3D12Device **
0x18004cfd5  lea     rcx, [rbp+var_30]; this
0x18004cfd9  call    ?GetService@DXGIDeviceManagerRAII@@QEAAJPEAPEAUID3D12Device@@@Z; DXGIDeviceManagerRAII::GetService(ID3D12Device * *)
0x18004cfde  cmp     [rbp+var_48], 0
0x18004cfe3  setnz   bl
0x18004cfe6  lea     rcx, [rbp+var_48]
0x18004cfea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cfef  lea     rcx, [rbp+var_30]; this
0x18004cff3  call    ??1DXGIDeviceManagerRAII@@QEAA@XZ; DXGIDeviceManagerRAII::~DXGIDeviceManagerRAII(void)
0x18004cff8  test    bl, bl
0x18004cffa  jz      short loc_18004D021
0x18004cffc  mov     rax, [r14]
0x18004cfff  mov     r8d, 1
0x18004d005  lea     rdx, MF_MT_D3D_RESOURCE_VERSION
0x18004d00c  mov     rcx, r14
0x18004d00f  mov     rax, [rax+0A8h]
0x18004d016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d01b  mov     ebx, eax
0x18004d01d  test    eax, eax
0x18004d01f  jnz     short loc_18004D04F
0x18004d021  mov     rcx, [rdi]
0x18004d024  mov     rax, [rcx]
0x18004d027  mov     r8d, dword ptr [rbp+var_40.Data4]
0x18004d02b  mov     edx, 1
0x18004d030  cmp     r8d, edx
0x18004d033  cmovb   r8d, edx
0x18004d037  add     r8d, 2
0x18004d03b  mov     [rsp+80h+var_60], r14
0x18004d040  mov     r9, [rbp+ppMFAttributes]
0x18004d044  mov     rax, [rax+38h]
0x18004d048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d04d  mov     ebx, eax
0x18004d04f  lea     rcx, [rbp+ppMFAttributes]
0x18004d053  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d058  mov     eax, ebx
0x18004d05a  mov     rcx, [rbp+var_10]
0x18004d05e  xor     rcx, rsp; StackCookie
0x18004d061  call    __security_check_cookie
0x18004d066  lea     r11, [rsp+80h+var_s0]
0x18004d06e  mov     rbx, [r11+38h]
0x18004d072  mov     rsi, [r11+40h]
0x18004d076  mov     rsp, r11
0x18004d079  pop     r15
0x18004d07b  pop     r14
0x18004d07d  pop     r12
0x18004d07f  pop     rdi
0x18004d080  pop     rbp
0x18004d081  retn
```
