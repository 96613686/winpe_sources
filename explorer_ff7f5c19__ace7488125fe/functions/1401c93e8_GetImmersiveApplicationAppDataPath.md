# GetImmersiveApplicationAppDataPath

- ea: `0x1401c93e8`
- end: `0x1401c95d6`
- name: `GetImmersiveApplicationAppDataPath`
- size: `494`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14008f52c`

## callees

- `0x140005d28`
- `0x1400073a0`
- `0x1401c93e8`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401c941c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401c9480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401c941c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401c9480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c95ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c95ab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401c9451`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401c9451`

## pseudocode

```c
__int64 __fastcall GetImmersiveApplicationAppDataPath(PCNZWCH sourceString, __int64 a2, _QWORD *a3)
{
  HRESULT ActivationFactory; // ebx
  HSTRING v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  HSTRING v20; // [rsp+30h] [rbp-20h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  __int64 v23; // [rsp+80h] [rbp+30h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Management.Core.ApplicationDataManager", 0x2Eu, &string);
  if ( ActivationFactory >= 0 )
  {
    v6 = string;
    v19 = 0;
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v19);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_1e1862e3_698e_49a1_9752_dee94925b9b3, &v19);
    if ( ActivationFactory >= 0 )
    {
      v21 = 0;
      v7 = -1;
      do
        ++v7;
      while ( sourceString[v7] );
      ActivationFactory = WindowsCreateString(sourceString, v7, &v21);
      if ( ActivationFactory >= 0 )
      {
        v8 = v19;
        v18 = 0;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v19 + 48LL);
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v18);
        ActivationFactory = v9(v8, v21, &v18);
        if ( ActivationFactory >= 0 )
        {
          v10 = v18;
          v24 = 0;
          v11 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v18 + 96LL);
          Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v24);
          ActivationFactory = v11(v10, &v24);
          if ( ActivationFactory >= 0 )
          {
            v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
            v23 = 0;
            v13 = **v24;
            Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v23);
            ActivationFactory = v13(v12, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v23);
            if ( ActivationFactory >= 0 )
            {
              v20 = 0;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 96LL))(v23, &v20);
              if ( ActivationFactory >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(v20, 0);
                ActivationFactory = _AllocString<CTCoAllocPolicy>(v16, v15, StringRawBuffer, a3);
                WindowsDeleteString(v20);
              }
            }
            Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v23);
          }
          Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v24);
        }
        WindowsDeleteString(v21);
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v18);
      }
    }
    WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v19);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1401c93e8  mov     [rsp-18h+arg_0], rbx
0x1401c93ed  mov     [rsp-18h+arg_8], rsi
0x1401c93f2  push    rbp
0x1401c93f3  push    rdi
0x1401c93f4  push    r14
0x1401c93f6  mov     rbp, rsp
0x1401c93f9  sub     rsp, 50h
0x1401c93fd  xor     r14d, r14d
0x1401c9400  mov     rsi, r8
0x1401c9403  mov     rdi, rcx
0x1401c9406  mov     [r8], r14
0x1401c9409  lea     r8, [rbp+string]; string
0x1401c940d  mov     [rbp+string], r14
0x1401c9411  lea     rcx, ?RuntimeClass_Windows_Management_Core_ApplicationDataManager@@3QBGB; "Windows.Management.Core.ApplicationData"...
0x1401c9418  lea     edx, [r14+2Eh]; length
0x1401c941c  call    cs:__imp_WindowsCreateString
0x1401c9423  nop     dword ptr [rax+rax+00h]
0x1401c9428  mov     ebx, eax
0x1401c942a  test    eax, eax
0x1401c942c  js      loc_1401C95C0
0x1401c9432  mov     rbx, [rbp+string]
0x1401c9436  lea     rcx, [rbp+var_28]
0x1401c943a  mov     [rbp+var_28], r14
0x1401c943e  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9443  lea     r8, [rbp+var_28]
0x1401c9447  mov     rcx, rbx
0x1401c944a  lea     rdx, _GUID_1e1862e3_698e_49a1_9752_dee94925b9b3
0x1401c9451  call    cs:__imp_RoGetActivationFactory
0x1401c9458  nop     dword ptr [rax+rax+00h]
0x1401c945d  mov     ebx, eax
0x1401c945f  test    eax, eax
0x1401c9461  js      loc_1401C95A7
0x1401c9467  mov     [rbp+var_18], r14
0x1401c946b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1401c946f  inc     rdx; length
0x1401c9472  cmp     [rdi+rdx*2], r14w
0x1401c9477  jnz     short loc_1401C946F
0x1401c9479  lea     r8, [rbp+var_18]; string
0x1401c947d  mov     rcx, rdi; sourceString
0x1401c9480  call    cs:__imp_WindowsCreateString
0x1401c9487  nop     dword ptr [rax+rax+00h]
0x1401c948c  mov     ebx, eax
0x1401c948e  test    eax, eax
0x1401c9490  js      loc_1401C95A7
0x1401c9496  mov     rdi, [rbp+var_28]
0x1401c949a  lea     rcx, [rbp+var_30]
0x1401c949e  mov     [rbp+var_30], r14
0x1401c94a2  mov     rax, [rdi]
0x1401c94a5  mov     rbx, [rax+30h]
0x1401c94a9  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c94ae  mov     rdx, [rbp+var_18]
0x1401c94b2  lea     r8, [rbp+var_30]
0x1401c94b6  mov     rcx, rdi
0x1401c94b9  mov     rax, rbx
0x1401c94bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c94c1  mov     ebx, eax
0x1401c94c3  test    eax, eax
0x1401c94c5  js      loc_1401C958E
0x1401c94cb  mov     rdi, [rbp+var_30]
0x1401c94cf  lea     rcx, [rbp+arg_18]
0x1401c94d3  mov     [rbp+arg_18], r14
0x1401c94d7  mov     rax, [rdi]
0x1401c94da  mov     rbx, [rax+60h]
0x1401c94de  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c94e3  lea     rdx, [rbp+arg_18]
0x1401c94e7  mov     rcx, rdi
0x1401c94ea  mov     rax, rbx
0x1401c94ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c94f2  mov     ebx, eax
0x1401c94f4  test    eax, eax
0x1401c94f6  js      loc_1401C9585
0x1401c94fc  mov     rbx, [rbp+arg_18]
0x1401c9500  lea     rcx, [rbp+arg_10]
0x1401c9504  mov     [rbp+arg_10], r14
0x1401c9508  mov     rax, [rbx]
0x1401c950b  mov     rdi, [rax]
0x1401c950e  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9513  lea     r8, [rbp+arg_10]
0x1401c9517  mov     rcx, rbx
0x1401c951a  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1401c9521  mov     rax, rdi
0x1401c9524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c9529  mov     ebx, eax
0x1401c952b  test    eax, eax
0x1401c952d  js      short loc_1401C957C
0x1401c952f  mov     rcx, [rbp+arg_10]
0x1401c9533  lea     rdx, [rbp+var_20]
0x1401c9537  mov     [rbp+var_20], r14
0x1401c953b  mov     rax, [rcx]
0x1401c953e  mov     rax, [rax+60h]
0x1401c9542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c9547  mov     ebx, eax
0x1401c9549  test    eax, eax
0x1401c954b  js      short loc_1401C957C
0x1401c954d  mov     rcx, [rbp+var_20]; string
0x1401c9551  xor     edx, edx; length
0x1401c9553  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c955a  nop     dword ptr [rax+rax+00h]
0x1401c955f  mov     r8, rax
0x1401c9562  mov     r9, rsi
0x1401c9565  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1401c956a  mov     rcx, [rbp+var_20]; string
0x1401c956e  mov     ebx, eax
0x1401c9570  call    cs:__imp_WindowsDeleteString
0x1401c9577  nop     dword ptr [rax+rax+00h]
0x1401c957c  lea     rcx, [rbp+arg_10]
0x1401c9580  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9585  lea     rcx, [rbp+arg_18]
0x1401c9589  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c958e  mov     rcx, [rbp+var_18]; string
0x1401c9592  call    cs:__imp_WindowsDeleteString
0x1401c9599  nop     dword ptr [rax+rax+00h]
0x1401c959e  lea     rcx, [rbp+var_30]
0x1401c95a2  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c95a7  mov     rcx, [rbp+string]; string
0x1401c95ab  call    cs:__imp_WindowsDeleteString
0x1401c95b2  nop     dword ptr [rax+rax+00h]
0x1401c95b7  lea     rcx, [rbp+var_28]
0x1401c95bb  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c95c0  mov     rsi, [rsp+50h+arg_8]
0x1401c95c5  mov     eax, ebx
0x1401c95c7  mov     rbx, [rsp+50h+arg_0]
0x1401c95cc  add     rsp, 50h
0x1401c95d0  pop     r14
0x1401c95d2  pop     rdi
0x1401c95d3  pop     rbp
0x1401c95d4  retn
```
