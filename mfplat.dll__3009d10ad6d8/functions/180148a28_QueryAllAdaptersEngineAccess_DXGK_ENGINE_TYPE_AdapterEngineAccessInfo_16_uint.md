# QueryAllAdaptersEngineAccess(DXGK_ENGINE_TYPE,AdapterEngineAccessInfo (&)[16],uint *)

- ea: `0x180148a28`
- end: `0x180148cf1`
- name: `?QueryAllAdaptersEngineAccess@@YAJW4DXGK_ENGINE_TYPE@@AEAY0BA@UAdapterEngineAccessInfo@@PEAI@Z`
- size: `713`
- prototype: `int __high(enum DXGK_ENGINE_TYPE, struct AdapterEngineAccessInfo (*)[16], unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092ba0`

## callees

- `0x180004870`
- `0x1801200d0`
- `0x180120ecc`
- `0x180148a04`
- `0x180148a28`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-2!D3DKMTEnumAdapters2` at `0x180148aaf`
- `api-ms-win-dx-d3dkmt-l1-1-2!D3DKMTEnumAdapters2` at `0x180148aaf`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x180148c19`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x180148c19`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-5!__imp_D3DKMTQueryFeatureInterface` at `0x180148c44`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-5!__imp_D3DKMTQueryFeatureInterface` at `0x180148c44`
- `dxgi!CreateDXGIFactory` at `0x180148aeb`
- `dxgi!CreateDXGIFactory` at `0x180148aeb`

## pseudocode

```c
int __fastcall QueryAllAdaptersEngineAccess(int a1, void *a2, int *a3)
{
  int v4; // edi
  int v5; // r15d
  int v6; // eax
  unsigned int v8; // r14d
  unsigned int v9; // r12d
  int (__fastcall ***v10)(void *, GUID *, __int64 *); // rbx
  __int64 v11; // rsi
  int (__fastcall *v12)(void *, GUID *, __int64 *); // rdi
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v15; // ebx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  void *ppFactory; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  _QWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v22[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h]
  int *v24; // [rsp+80h] [rbp-80h]
  _DWORD v25[2]; // [rsp+88h] [rbp-78h] BYREF
  int v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  int v28; // [rsp+A0h] [rbp-60h]
  _BYTE v29[256]; // [rsp+B0h] [rbp-50h] BYREF
  int v30; // [rsp+1B0h] [rbp+B0h]
  _BYTE v31[320]; // [rsp+1F0h] [rbp+F0h] BYREF

  v19 = a1;
  v4 = a1;
  v24 = a3;
  *a3 = 0;
  memset_0(a2, 0, 0x100u);
  memset_0(v31, 0, sizeof(v31));
  v21[0] = 16;
  v21[1] = v31;
  v5 = 16;
  v6 = D3DKMTEnumAdapters2(v21);
  if ( v6 < 0 )
    return v6 | 0x10000000;
  v8 = v21[0];
  if ( LODWORD(v21[0]) )
  {
    ppFactory = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppFactory);
    CreateDXGIFactory(&GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369, &ppFactory);
    v9 = 0;
    do
    {
      if ( v9 >= 0x10 )
        break;
      v10 = (int (__fastcall ***)(void *, GUID *, __int64 *))ppFactory;
      v11 = 2LL * v9;
      v20 = 5LL * v9;
      *((_QWORD *)a2 + v11) = *(_QWORD *)&v31[20 * v9 + 4];
      *((_DWORD *)a2 + 2 * v11 + 2) = 0;
      *((_BYTE *)a2 + 8 * v11 + 12) = 0;
      if ( v10 )
      {
        v17 = 0;
        v16 = 0;
        v12 = **v10;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
        if ( v12(v10, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &v16) >= 0 )
        {
          v13 = v16;
          v14 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v16 + 208LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          if ( v14(v13, *(_QWORD *)&v31[4 * v20 + 4], &GUID_29038f61_3839_4626_91fd_086879011a05, &v17) >= 0 )
          {
            memset_0(v29, 0, 0x138u);
            if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 80LL))(v17, v29) >= 0 )
              *((_DWORD *)a2 + 4 * v9 + 2) = v30;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        v4 = v19;
      }
      v28 = 0;
      v27 = *(_QWORD *)&v31[4 * v20 + 4];
      if ( (int)D3DKMTOpenAdapterFromLuid(&v27) >= 0 )
      {
        v15 = v28;
        LODWORD(v16) = v28;
        v23 = 0;
        v22[0] = v28;
        v22[1] = 268435465;
        if ( (int)D3DKMTQueryFeatureInterface(v22) >= 0 && (BYTE2(v23) & 1) != 0 )
        {
          if ( *((_QWORD *)&v23 + 1) )
          {
            if ( DWORD1(v23) >= 2 )
            {
              if ( *(_QWORD *)(*((_QWORD *)&v23 + 1) + 8LL) )
              {
                v26 = 0;
                v25[0] = v15;
                v25[1] = v4;
                if ( (*(int (__fastcall **)(_DWORD *))(*((_QWORD *)&v23 + 1) + 8LL))(v25) >= 0 )
                  *((_BYTE *)a2 + 16 * v9 + 12) = v26 == 2;
              }
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned int,void (*)(unsigned int),&void CloseD3DKMTAdapter(unsigned int),wistd::integral_constant<unsigned __int64,0>,unsigned int,unsigned int,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned int,void (*)(unsigned int),&void CloseD3DKMTAdapter(unsigned int),wistd::integral_constant<unsigned __int64,0>,unsigned int,unsigned int,0,std::nullptr_t>>(&v16);
      }
      ++v9;
    }
    while ( v9 < v8 );
    if ( v8 < 0x10 )
      v5 = v8;
    *v24 = v5;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppFactory);
  }
  return 0;
}

```

## disassembly

```asm
0x180148a28  mov     [rsp-8+arg_18], rbx
0x180148a2d  push    rbp
0x180148a2e  push    rsi
0x180148a2f  push    rdi
0x180148a30  push    r12
0x180148a32  push    r13
0x180148a34  push    r14
0x180148a36  push    r15
0x180148a38  lea     rbp, [rsp-240h]
0x180148a40  sub     rsp, 340h
0x180148a47  mov     rax, cs:__security_cookie
0x180148a4e  xor     rax, rsp
0x180148a51  mov     [rbp+270h+var_40], rax
0x180148a58  mov     r13, rdx
0x180148a5b  mov     [rsp+370h+var_328], ecx
0x180148a5f  mov     rbx, r8
0x180148a62  mov     edi, ecx
0x180148a64  xor     esi, esi
0x180148a66  mov     [rbp+270h+var_2F0], rbx
0x180148a6a  mov     [r8], esi
0x180148a6d  xor     edx, edx; Val
0x180148a6f  mov     r8d, 100h; Size
0x180148a75  mov     rcx, r13; void *
0x180148a78  call    memset_0
0x180148a7d  xor     edx, edx; Val
0x180148a7f  lea     rcx, [rbp+270h+var_180]; void *
0x180148a86  mov     r8d, 140h; Size
0x180148a8c  call    memset_0
0x180148a91  lea     rax, [rbp+270h+var_180]
0x180148a98  mov     [rsp+370h+var_318], 10h
0x180148aa1  lea     rcx, [rsp+370h+var_318]
0x180148aa6  mov     [rsp+370h+var_310], rax
0x180148aab  lea     r15d, [rsi+10h]
0x180148aaf  call    cs:__imp_D3DKMTEnumAdapters2
0x180148ab5  test    eax, eax
0x180148ab7  jns     short loc_180148AC2
0x180148ab9  bts     eax, 1Ch
0x180148abd  jmp     loc_180148CC7
0x180148ac2  mov     r14d, dword ptr [rsp+370h+var_318]
0x180148ac7  test    r14d, r14d
0x180148aca  jz      loc_180148CC5
0x180148ad0  lea     rcx, [rsp+370h+ppFactory]
0x180148ad5  mov     [rsp+370h+ppFactory], rsi
0x180148ada  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148adf  lea     rdx, [rsp+370h+ppFactory]; ppFactory
0x180148ae4  lea     rcx, _GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369; riid
0x180148aeb  call    cs:__imp_CreateDXGIFactory
0x180148af1  mov     r12d, esi
0x180148af4  test    r14d, r14d
0x180148af7  jz      loc_180148CB1
0x180148afd  cmp     r12d, r15d
0x180148b00  jnb     loc_180148CAD
0x180148b06  mov     rbx, [rsp+370h+ppFactory]
0x180148b0b  mov     esi, r12d
0x180148b0e  lea     rax, [rsi+rsi*4]
0x180148b12  add     rsi, rsi
0x180148b15  mov     [rsp+370h+var_320], rax
0x180148b1a  mov     rax, [rbp+rax*4+270h+var_17C]
0x180148b22  mov     [r13+rsi*8+0], rax
0x180148b27  xor     eax, eax
0x180148b29  mov     [r13+rsi*8+8], eax
0x180148b2e  mov     [r13+rsi*8+0Ch], al
0x180148b33  test    rbx, rbx
0x180148b36  jz      loc_180148C01
0x180148b3c  mov     [rsp+370h+var_338], rax
0x180148b41  lea     rcx, [rsp+370h+var_340]
0x180148b46  mov     [rsp+370h+var_340], rax
0x180148b4b  mov     rax, [rbx]
0x180148b4e  mov     rdi, [rax]
0x180148b51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148b56  lea     r8, [rsp+370h+var_340]
0x180148b5b  mov     rcx, rbx
0x180148b5e  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a
0x180148b65  mov     rax, rdi
0x180148b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148b6d  test    eax, eax
0x180148b6f  js      short loc_180148BE7
0x180148b71  mov     rdi, [rsp+370h+var_340]
0x180148b76  lea     rcx, [rsp+370h+var_338]
0x180148b7b  mov     rax, [rdi]
0x180148b7e  mov     rbx, [rax+0D0h]
0x180148b85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148b8a  mov     rdx, [rsp+370h+var_320]
0x180148b8f  lea     r9, [rsp+370h+var_338]
0x180148b94  lea     r8, _GUID_29038f61_3839_4626_91fd_086879011a05
0x180148b9b  mov     rcx, rdi
0x180148b9e  mov     rax, rbx
0x180148ba1  mov     rdx, [rbp+rdx*4+270h+var_17C]
0x180148ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148bae  test    eax, eax
0x180148bb0  js      short loc_180148BE7
0x180148bb2  xor     edx, edx; Val
0x180148bb4  lea     rcx, [rbp+270h+var_2C0]; void *
0x180148bb8  mov     r8d, 138h; Size
0x180148bbe  call    memset_0
0x180148bc3  mov     rcx, [rsp+370h+var_338]
0x180148bc8  lea     rdx, [rbp+270h+var_2C0]
0x180148bcc  mov     rax, [rcx]
0x180148bcf  mov     rax, [rax+50h]
0x180148bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148bd8  test    eax, eax
0x180148bda  js      short loc_180148BE7
0x180148bdc  mov     eax, [rbp+270h+var_1C0]
0x180148be2  mov     [r13+rsi*8+8], eax
0x180148be7  lea     rcx, [rsp+370h+var_340]
0x180148bec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148bf1  lea     rcx, [rsp+370h+var_338]
0x180148bf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148bfb  mov     edi, [rsp+370h+var_328]
0x180148bff  xor     eax, eax
0x180148c01  mov     [rbp+270h+var_2D0], eax
0x180148c04  lea     rcx, [rbp+270h+var_2D8]
0x180148c08  mov     rax, [rsp+370h+var_320]
0x180148c0d  mov     rax, [rbp+rax*4+270h+var_17C]
0x180148c15  mov     [rbp+270h+var_2D8], rax
0x180148c19  call    cs:__imp_D3DKMTOpenAdapterFromLuid
0x180148c1f  test    eax, eax
0x180148c21  js      short loc_180148CA1
0x180148c23  mov     ebx, [rbp+270h+var_2D0]
0x180148c26  lea     rcx, [rsp+370h+var_308]
0x180148c2b  xorps   xmm0, xmm0
0x180148c2e  mov     dword ptr [rsp+370h+var_340], ebx
0x180148c32  movdqu  [rsp+370h+var_300], xmm0
0x180148c38  mov     [rsp+370h+var_308], ebx
0x180148c3c  mov     [rsp+370h+var_304], 10000009h
0x180148c44  call    cs:__imp_D3DKMTQueryFeatureInterface
0x180148c4a  test    eax, eax
0x180148c4c  js      short loc_180148C97
0x180148c4e  test    byte ptr [rsp+370h+var_300+2], 1
0x180148c53  jz      short loc_180148C97
0x180148c55  mov     rax, qword ptr [rsp+370h+var_300+8]
0x180148c5a  test    rax, rax
0x180148c5d  jz      short loc_180148C97
0x180148c5f  cmp     dword ptr [rsp+370h+var_300+4], 2
0x180148c64  jb      short loc_180148C97
0x180148c66  cmp     qword ptr [rax+8], 0
0x180148c6b  jz      short loc_180148C97
0x180148c6d  mov     [rbp+270h+var_2E0], 0
0x180148c74  lea     rcx, [rbp+270h+var_2E8]
0x180148c78  mov     [rbp+270h+var_2E8], ebx
0x180148c7b  mov     [rbp+270h+var_2E4], edi
0x180148c7e  mov     rax, [rax+8]
0x180148c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148c87  test    eax, eax
0x180148c89  js      short loc_180148C97
0x180148c8b  cmp     [rbp+270h+var_2E0], 2
0x180148c8f  setz    al
0x180148c92  mov     [r13+rsi*8+0Ch], al
0x180148c97  lea     rcx, [rsp+370h+var_340]
0x180148c9c  call    ??1?$unique_storage@U?$resource_policy@IP6AXI@Z$1?CloseD3DKMTAdapter@@YAXI@ZU?$integral_constant@_K$0A@@wistd@@II$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uint,void (*)(uint),&CloseD3DKMTAdapter(uint),wistd::integral_constant<unsigned __int64,0>,uint,uint,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uint,void (*)(uint),&CloseD3DKMTAdapter(uint),wistd::integral_constant<unsigned __int64,0>,uint,uint,0,std::nullptr_t>>(void)
0x180148ca1  inc     r12d
0x180148ca4  cmp     r12d, r14d
0x180148ca7  jb      loc_180148AFD
0x180148cad  mov     rbx, [rbp+270h+var_2F0]
0x180148cb1  cmp     r14d, r15d
0x180148cb4  lea     rcx, [rsp+370h+ppFactory]
0x180148cb9  cmovb   r15d, r14d
0x180148cbd  mov     [rbx], r15d
0x180148cc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180148cc5  xor     eax, eax
0x180148cc7  mov     rcx, [rbp+270h+var_40]
0x180148cce  xor     rcx, rsp; StackCookie
0x180148cd1  call    __security_check_cookie
0x180148cd6  mov     rbx, [rsp+370h+arg_18]
0x180148cde  add     rsp, 340h
0x180148ce5  pop     r15
0x180148ce7  pop     r14
0x180148ce9  pop     r13
0x180148ceb  pop     r12
0x180148ced  pop     rdi
0x180148cee  pop     rsi
0x180148cef  pop     rbp
0x180148cf0  retn
```
