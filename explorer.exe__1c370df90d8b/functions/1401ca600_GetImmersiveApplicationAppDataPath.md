# GetImmersiveApplicationAppDataPath

- ea: `0x1401ca600`
- end: `0x1401ca7bf`
- name: `GetImmersiveApplicationAppDataPath`
- size: `447`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140089c7c`

## callees

- `0x14000c870`
- `0x140019770`
- `0x1401ca600`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401ca634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401ca68c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401ca634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1401ca68c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401ca755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401ca755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca76c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca79b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca76c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca79b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401ca663`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401ca663`

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
0x1401ca600  mov     [rsp-18h+arg_0], rbx
0x1401ca605  mov     [rsp-18h+arg_8], rsi
0x1401ca60a  push    rbp
0x1401ca60b  push    rdi
0x1401ca60c  push    r14
0x1401ca60e  mov     rbp, rsp
0x1401ca611  sub     rsp, 50h
0x1401ca615  xor     r14d, r14d
0x1401ca618  mov     rsi, r8
0x1401ca61b  mov     rdi, rcx
0x1401ca61e  mov     [r8], r14
0x1401ca621  lea     r8, [rbp+string]; string
0x1401ca625  mov     [rbp+string], r14
0x1401ca629  lea     rcx, ?RuntimeClass_Windows_Management_Core_ApplicationDataManager@@3QBGB; "Windows.Management.Core.ApplicationData"...
0x1401ca630  lea     edx, [r14+2Eh]; length
0x1401ca634  call    cs:__imp_WindowsCreateString
0x1401ca63a  mov     ebx, eax
0x1401ca63c  test    eax, eax
0x1401ca63e  js      loc_1401CA7AA
0x1401ca644  mov     rbx, [rbp+string]
0x1401ca648  lea     rcx, [rbp+var_28]
0x1401ca64c  mov     [rbp+var_28], r14
0x1401ca650  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca655  lea     r8, [rbp+var_28]
0x1401ca659  mov     rcx, rbx
0x1401ca65c  lea     rdx, _GUID_1e1862e3_698e_49a1_9752_dee94925b9b3
0x1401ca663  call    cs:__imp_RoGetActivationFactory
0x1401ca669  mov     ebx, eax
0x1401ca66b  test    eax, eax
0x1401ca66d  js      loc_1401CA797
0x1401ca673  mov     [rbp+var_18], r14
0x1401ca677  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1401ca67b  inc     rdx; length
0x1401ca67e  cmp     [rdi+rdx*2], r14w
0x1401ca683  jnz     short loc_1401CA67B
0x1401ca685  lea     r8, [rbp+var_18]; string
0x1401ca689  mov     rcx, rdi; sourceString
0x1401ca68c  call    cs:__imp_WindowsCreateString
0x1401ca692  mov     ebx, eax
0x1401ca694  test    eax, eax
0x1401ca696  js      loc_1401CA797
0x1401ca69c  mov     rdi, [rbp+var_28]
0x1401ca6a0  lea     rcx, [rbp+var_30]
0x1401ca6a4  mov     [rbp+var_30], r14
0x1401ca6a8  mov     rax, [rdi]
0x1401ca6ab  mov     rbx, [rax+30h]
0x1401ca6af  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca6b4  mov     rdx, [rbp+var_18]
0x1401ca6b8  lea     r8, [rbp+var_30]
0x1401ca6bc  mov     rcx, rdi
0x1401ca6bf  mov     rax, rbx
0x1401ca6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca6c7  mov     ebx, eax
0x1401ca6c9  test    eax, eax
0x1401ca6cb  js      loc_1401CA784
0x1401ca6d1  mov     rdi, [rbp+var_30]
0x1401ca6d5  lea     rcx, [rbp+arg_18]
0x1401ca6d9  mov     [rbp+arg_18], r14
0x1401ca6dd  mov     rax, [rdi]
0x1401ca6e0  mov     rbx, [rax+60h]
0x1401ca6e4  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca6e9  lea     rdx, [rbp+arg_18]
0x1401ca6ed  mov     rcx, rdi
0x1401ca6f0  mov     rax, rbx
0x1401ca6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca6f8  mov     ebx, eax
0x1401ca6fa  test    eax, eax
0x1401ca6fc  js      short loc_1401CA77B
0x1401ca6fe  mov     rbx, [rbp+arg_18]
0x1401ca702  lea     rcx, [rbp+arg_10]
0x1401ca706  mov     [rbp+arg_10], r14
0x1401ca70a  mov     rax, [rbx]
0x1401ca70d  mov     rdi, [rax]
0x1401ca710  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca715  lea     r8, [rbp+arg_10]
0x1401ca719  mov     rcx, rbx
0x1401ca71c  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1401ca723  mov     rax, rdi
0x1401ca726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca72b  mov     ebx, eax
0x1401ca72d  test    eax, eax
0x1401ca72f  js      short loc_1401CA772
0x1401ca731  mov     rcx, [rbp+arg_10]
0x1401ca735  lea     rdx, [rbp+var_20]
0x1401ca739  mov     [rbp+var_20], r14
0x1401ca73d  mov     rax, [rcx]
0x1401ca740  mov     rax, [rax+60h]
0x1401ca744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca749  mov     ebx, eax
0x1401ca74b  test    eax, eax
0x1401ca74d  js      short loc_1401CA772
0x1401ca74f  mov     rcx, [rbp+var_20]; string
0x1401ca753  xor     edx, edx; length
0x1401ca755  call    cs:__imp_WindowsGetStringRawBuffer
0x1401ca75b  mov     r8, rax
0x1401ca75e  mov     r9, rsi
0x1401ca761  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1401ca766  mov     rcx, [rbp+var_20]; string
0x1401ca76a  mov     ebx, eax
0x1401ca76c  call    cs:__imp_WindowsDeleteString
0x1401ca772  lea     rcx, [rbp+arg_10]
0x1401ca776  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca77b  lea     rcx, [rbp+arg_18]
0x1401ca77f  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca784  mov     rcx, [rbp+var_18]; string
0x1401ca788  call    cs:__imp_WindowsDeleteString
0x1401ca78e  lea     rcx, [rbp+var_30]
0x1401ca792  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca797  mov     rcx, [rbp+string]; string
0x1401ca79b  call    cs:__imp_WindowsDeleteString
0x1401ca7a1  lea     rcx, [rbp+var_28]
0x1401ca7a5  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca7aa  mov     rsi, [rsp+50h+arg_8]
0x1401ca7af  mov     eax, ebx
0x1401ca7b1  mov     rbx, [rsp+50h+arg_0]
0x1401ca7b6  add     rsp, 50h
0x1401ca7ba  pop     r14
0x1401ca7bc  pop     rdi
0x1401ca7bd  pop     rbp
0x1401ca7be  retn
```
