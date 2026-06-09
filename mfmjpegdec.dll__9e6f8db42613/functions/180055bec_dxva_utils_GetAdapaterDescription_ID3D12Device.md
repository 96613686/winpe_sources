# dxva_utils::GetAdapaterDescription(ID3D12Device &)

- ea: `0x180055bec`
- end: `0x180055e05`
- name: `?GetAdapaterDescription@dxva_utils@@YA?AV?$expected@UDXGI_ADAPTER_DESC@@J@std@@AEAUID3D12Device@@@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004c424`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x18004a11c`
- `0x180055bec`
- `0x180055e0c`
- `0x180070010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180055c39`
- `dxgi!CreateDXGIFactory1` at `0x180055c39`

## string_xrefs

- `0x180055c57`: `CreateDXGIFactory1(IID_PPV_ARGS(&pDxgiFactory))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall dxva_utils::GetAdapaterDescription(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  int v5; // r8d
  HRESULT v6; // ebx
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, __int64, GUID *, __int64 *); // rbx
  int v9; // ebx
  int v10; // r8d
  int v11; // edx
  const char *v12; // r9
  _OWORD *v13; // rax
  _OWORD *v14; // rcx
  __int64 v15; // rdx
  void *ppFactory; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[304]; // [rsp+50h] [rbp-B0h] BYREF

  ppFactory = 0;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&ppFactory);
  v4 = CreateDXGIFactory1(&GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &ppFactory);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 344LL))(a2, &v19);
    v7 = ppFactory;
    v8 = *(__int64 (__fastcall **)(void *, __int64, GUID *, __int64 *))(*(_QWORD *)ppFactory + 208LL);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v18);
    v9 = v8(v7, v19, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, &v18);
    if ( v9 >= 0 )
    {
      memset_0(v20, 0, sizeof(v20));
      v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 64LL))(v18, v20);
      if ( v9 >= 0 )
      {
        v13 = (_OWORD *)a1;
        v14 = v20;
        v15 = 2;
        do
        {
          *v13 = *v14;
          v13[1] = v14[1];
          v13[2] = v14[2];
          v13[3] = v14[3];
          v13[4] = v14[4];
          v13[5] = v14[5];
          v13[6] = v14[6];
          v13[7] = v14[7];
          v13 += 8;
          v14 += 8;
          --v15;
        }
        while ( v15 );
        *v13 = *v14;
        v13[1] = v14[1];
        v13[2] = v14[2];
        *(_BYTE *)(a1 + 304) = 1;
        goto LABEL_16;
      }
      if ( g_wppLevels )
      {
        v11 = 12;
        v12 = "pDXGIAdapter->GetDesc(&desc)";
        goto LABEL_8;
      }
    }
    else if ( g_wppLevels )
    {
      v11 = 11;
      v12 = "pDxgiFactory->EnumAdapterByLuid(adapterLuid, IID_PPV_ARGS(&pDXGIAdapter))";
LABEL_8:
      WPP_SF_sDq(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, (_DWORD)v12, v9);
    }
    *(_DWORD *)a1 = v9;
    *(_BYTE *)(a1 + 304) = 0;
LABEL_16:
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v18);
    goto LABEL_17;
  }
  if ( g_wppLevels )
    WPP_SF_sDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      v5,
      (unsigned int)"CreateDXGIFactory1(IID_PPV_ARGS(&pDxgiFactory))",
      v4);
  *(_DWORD *)a1 = v6;
  *(_BYTE *)(a1 + 304) = 0;
LABEL_17:
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&ppFactory);
  return a1;
}

```

## disassembly

```asm
0x180055bec  mov     [rsp-8+arg_10], rbx
0x180055bf1  push    rbp
0x180055bf2  push    rsi
0x180055bf3  push    rdi
0x180055bf4  lea     rbp, [rsp-90h]
0x180055bfc  sub     rsp, 190h
0x180055c03  mov     rax, cs:__security_cookie
0x180055c0a  xor     rax, rsp
0x180055c0d  mov     [rbp+0A0h+var_20], rax
0x180055c14  mov     rdi, rdx
0x180055c17  mov     rsi, rcx
0x180055c1a  mov     [rsp+1A0h+ppFactory], 0
0x180055c23  lea     rcx, [rsp+1A0h+ppFactory]
0x180055c28  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180055c2d  lea     rdx, [rsp+1A0h+ppFactory]; ppFactory
0x180055c32  lea     rcx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x180055c39  call    cs:__imp_CreateDXGIFactory1
0x180055c3f  mov     ebx, eax
0x180055c41  test    eax, eax
0x180055c43  jns     short loc_180055C7C
0x180055c45  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055c4c  jb      short loc_180055C6E
0x180055c4e  mov     edx, 0Ah
0x180055c53  mov     [rsp+1A0h+var_180], eax
0x180055c57  lea     r9, aCreatedxgifact; "CreateDXGIFactory1(IID_PPV_ARGS(&pDxgiF"...
0x180055c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c65  mov     rcx, [rcx+10h]
0x180055c69  call    WPP_SF_sDq
0x180055c6e  mov     [rsi], ebx
0x180055c70  mov     byte ptr [rsi+130h], 0
0x180055c77  jmp     loc_180055DD6
0x180055c7c  mov     [rsp+1A0h+var_168], 0
0x180055c85  mov     rax, [rdi]
0x180055c88  lea     rdx, [rsp+1A0h+var_160]
0x180055c8d  mov     rcx, rdi
0x180055c90  mov     rax, [rax+158h]
0x180055c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c9c  mov     rdi, [rsp+1A0h+ppFactory]
0x180055ca1  mov     rax, [rdi]
0x180055ca4  mov     rbx, [rax+0D0h]
0x180055cab  lea     rcx, [rsp+1A0h+var_168]
0x180055cb0  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180055cb5  lea     r9, [rsp+1A0h+var_168]
0x180055cba  lea     r8, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180055cc1  mov     rdx, [rsp+1A0h+var_160]
0x180055cc6  mov     rcx, rdi
0x180055cc9  mov     rax, rbx
0x180055ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cd1  mov     ebx, eax
0x180055cd3  test    eax, eax
0x180055cd5  jns     short loc_180055D0E
0x180055cd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055cde  jb      short loc_180055D00
0x180055ce0  mov     edx, 0Bh
0x180055ce5  lea     r9, aPdxgifactoryEn; "pDxgiFactory->EnumAdapterByLuid(adapter"...
0x180055cec  mov     [rsp+1A0h+var_180], ebx
0x180055cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180055cf7  mov     rcx, [rcx+10h]
0x180055cfb  call    WPP_SF_sDq
0x180055d00  mov     [rsi], ebx
0x180055d02  mov     byte ptr [rsi+130h], 0
0x180055d09  jmp     loc_180055DCB
0x180055d0e  xor     edx, edx; Val
0x180055d10  mov     r8d, 130h; Size
0x180055d16  lea     rcx, [rsp+1A0h+var_150]; void *
0x180055d1b  call    memset_0
0x180055d20  mov     rcx, [rsp+1A0h+var_168]
0x180055d25  mov     rax, [rcx]
0x180055d28  lea     rdx, [rsp+1A0h+var_150]
0x180055d2d  mov     rax, [rax+40h]
0x180055d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d36  mov     ebx, eax
0x180055d38  test    eax, eax
0x180055d3a  jns     short loc_180055D53
0x180055d3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055d43  jb      short loc_180055D00
0x180055d45  mov     edx, 0Ch
0x180055d4a  lea     r9, aPdxgiadapterGe; "pDXGIAdapter->GetDesc(&desc)"
0x180055d51  jmp     short loc_180055CEC
0x180055d53  mov     rax, rsi
0x180055d56  lea     rcx, [rsp+1A0h+var_150]
0x180055d5b  mov     edx, 2
0x180055d60  lea     r8d, [rdx+7Eh]
0x180055d64  movups  xmm0, xmmword ptr [rcx]
0x180055d67  movups  xmmword ptr [rax], xmm0
0x180055d6a  movups  xmm1, xmmword ptr [rcx+10h]
0x180055d6e  movups  xmmword ptr [rax+10h], xmm1
0x180055d72  movups  xmm0, xmmword ptr [rcx+20h]
0x180055d76  movups  xmmword ptr [rax+20h], xmm0
0x180055d7a  movups  xmm1, xmmword ptr [rcx+30h]
0x180055d7e  movups  xmmword ptr [rax+30h], xmm1
0x180055d82  movups  xmm0, xmmword ptr [rcx+40h]
0x180055d86  movups  xmmword ptr [rax+40h], xmm0
0x180055d8a  movups  xmm1, xmmword ptr [rcx+50h]
0x180055d8e  movups  xmmword ptr [rax+50h], xmm1
0x180055d92  movups  xmm0, xmmword ptr [rcx+60h]
0x180055d96  movups  xmmword ptr [rax+60h], xmm0
0x180055d9a  movups  xmm1, xmmword ptr [rcx+70h]
0x180055d9e  movups  xmmword ptr [rax+70h], xmm1
0x180055da2  add     rax, r8
0x180055da5  add     rcx, r8
0x180055da8  sub     rdx, 1
0x180055dac  jnz     short loc_180055D64
0x180055dae  movups  xmm0, xmmword ptr [rcx]
0x180055db1  movups  xmmword ptr [rax], xmm0
0x180055db4  movups  xmm1, xmmword ptr [rcx+10h]
0x180055db8  movups  xmmword ptr [rax+10h], xmm1
0x180055dbc  movups  xmm0, xmmword ptr [rcx+20h]
0x180055dc0  movups  xmmword ptr [rax+20h], xmm0
0x180055dc4  mov     byte ptr [rsi+130h], 1
0x180055dcb  lea     rcx, [rsp+1A0h+var_168]
0x180055dd0  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180055dd5  nop
0x180055dd6  lea     rcx, [rsp+1A0h+ppFactory]
0x180055ddb  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180055de0  mov     rax, rsi
0x180055de3  mov     rcx, [rbp+0A0h+var_20]
0x180055dea  xor     rcx, rsp; StackCookie
0x180055ded  call    __security_check_cookie
0x180055df2  mov     rbx, [rsp+1A0h+arg_10]
0x180055dfa  add     rsp, 190h
0x180055e01  pop     rdi
0x180055e02  pop     rsi
0x180055e03  pop     rbp
0x180055e04  retn
```
