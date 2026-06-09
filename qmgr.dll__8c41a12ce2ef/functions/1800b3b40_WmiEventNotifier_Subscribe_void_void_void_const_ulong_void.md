# WmiEventNotifier::Subscribe(void (*)(void *,void const *,ulong),void *)

- ea: `0x1800b3b40`
- end: `0x1800b3fff`
- name: `?Subscribe@WmiEventNotifier@@UEAAXP6AXPEAXPEBXK@Z0@Z`
- size: `1215`
- prototype: `void __fastcall(char *Parameter, void (*)(void *, const void *, unsigned int), void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002c6ac`
- `0x180069014`
- `0x180099b10`
- `0x18009d024`
- `0x1800b3b40`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b3bdf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b3bdf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b3f2d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800b3f2d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3fde`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3fde`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WmiEventNotifier::Subscribe(char *Parameter, void (*a2)(void *, const void *, unsigned int), void *a3)
{
  HRESULT Instance; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, char *); // rbx
  struct IUnknown **v9; // r15
  int v10; // eax
  int v11; // eax
  struct IUnknown *v12; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v14; // eax
  struct IUnknown *v15; // rdi
  ULONG (__stdcall *v16)(IUnknown *); // rbx
  int v17; // eax
  int v18; // eax
  unsigned int LastError; // eax
  BSTR v20; // [rsp+50h] [rbp-2D8h] BYREF
  const ComError *v21; // [rsp+58h] [rbp-2D0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-2C8h] BYREF
  __int128 v23; // [rsp+68h] [rbp-2C0h]
  HRESULT v24; // [rsp+78h] [rbp-2B0h]
  int v25; // [rsp+7Ch] [rbp-2ACh]
  int v26; // [rsp+80h] [rbp-2A8h]
  void **v27; // [rsp+C0h] [rbp-268h] BYREF
  __int128 v28; // [rsp+C8h] [rbp-260h]
  int v29; // [rsp+D8h] [rbp-250h]
  int v30; // [rsp+DCh] [rbp-24Ch]
  int v31; // [rsp+E0h] [rbp-248h]
  void **v32; // [rsp+120h] [rbp-208h] BYREF
  __int128 v33; // [rsp+128h] [rbp-200h]
  int v34; // [rsp+138h] [rbp-1F0h]
  int v35; // [rsp+13Ch] [rbp-1ECh]
  int v36; // [rsp+140h] [rbp-1E8h]
  void **v37; // [rsp+180h] [rbp-1A8h] BYREF
  __int128 v38; // [rsp+188h] [rbp-1A0h]
  int v39; // [rsp+198h] [rbp-190h]
  int v40; // [rsp+19Ch] [rbp-18Ch]
  int v41; // [rsp+1A0h] [rbp-188h]
  void **v42; // [rsp+1E0h] [rbp-148h] BYREF
  __int128 v43; // [rsp+1E8h] [rbp-140h]
  int v44; // [rsp+1F8h] [rbp-130h]
  int v45; // [rsp+1FCh] [rbp-12Ch]
  int v46; // [rsp+200h] [rbp-128h]
  void **v47; // [rsp+240h] [rbp-E8h] BYREF
  __int128 v48; // [rsp+248h] [rbp-E0h]
  int v49; // [rsp+258h] [rbp-D0h]
  int v50; // [rsp+25Ch] [rbp-CCh]
  int v51; // [rsp+260h] [rbp-C8h]
  void **v52; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v53; // [rsp+2A8h] [rbp-80h]
  unsigned int v54; // [rsp+2B8h] [rbp-70h]
  int v55; // [rsp+2BCh] [rbp-6Ch]
  int v56; // [rsp+2C0h] [rbp-68h]
  BSTR bstrString; // [rsp+348h] [rbp+20h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
  }
  else
  {
    *((_QWORD *)Parameter + 7) = a2;
    *((_QWORD *)Parameter + 8) = a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(Parameter + 8);
    Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)Parameter + 1);
    try
    {
      if ( Instance < 0 )
      {
        v23 = 0;
        pExceptionObject = &ComError::`vftable';
        v24 = Instance;
        v25 = 1172;
        v26 = 1;
        throw (ComError *)&pExceptionObject;
      }
      SmartBSTR::SmartBSTR((SmartBSTR *)&v20, L"ROOT\\CIMV2");
      v7 = *((_QWORD *)Parameter + 1);
      v8 = *(__int64 (__fastcall **)(__int64, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, char *))(*(_QWORD *)v7 + 24LL);
      v9 = (struct IUnknown **)(Parameter + 16);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(Parameter + 16);
      v10 = v8(v7, v20, 0, 0, 0, 0, 0, 0, Parameter + 16);
      if ( v10 < 0 )
      {
        v28 = 0;
        v27 = &ComError::`vftable';
        v29 = v10;
        v30 = 1184;
        v31 = 1;
        throw (ComError *)&v27;
      }
      v11 = ConfigureProxyBlanket(*v9, 3, 0);
      if ( v11 < 0 )
      {
        v33 = 0;
        v32 = &ComError::`vftable';
        v34 = v11;
        v35 = 1190;
        v36 = 1;
        throw (ComError *)&v32;
      }
      SmartBSTR::SmartBSTR((SmartBSTR *)&bstrString, L"WQL");
      v12 = *v9;
      AddRef = (*v9)->lpVtbl[7].AddRef;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(Parameter + 24);
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, __int64, _QWORD, char *))AddRef)(
              v12,
              bstrString,
              *((_QWORD *)Parameter + 4),
              48,
              0,
              Parameter + 24);
      if ( v14 < 0 )
      {
        if ( !*((_QWORD *)Parameter + 5) )
        {
          v43 = 0;
          v42 = &ComError::`vftable';
          v44 = v14;
          v45 = 1215;
          v46 = 1;
          throw (ComError *)&v42;
        }
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
        v15 = *v9;
        v16 = (*v9)->lpVtbl[7].AddRef;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(Parameter + 24);
        v17 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, __int64, _QWORD, char *))v16)(
                v15,
                bstrString,
                *((_QWORD *)Parameter + 5),
                48,
                0,
                Parameter + 24);
        if ( v17 < 0 )
        {
          v38 = 0;
          v37 = &ComError::`vftable';
          v39 = v17;
          v40 = 1211;
          v41 = 1;
          throw (ComError *)&v37;
        }
      }
      v18 = ConfigureProxyBlanket(*((struct IUnknown **)Parameter + 3), 3, 0);
      if ( v18 < 0 )
      {
        v48 = 0;
        v47 = &ComError::`vftable';
        v49 = v18;
        v50 = 1222;
        v51 = 1;
        throw (ComError *)&v47;
      }
      if ( !CreateTimerQueueTimer(
              (PHANDLE)Parameter + 9,
              0,
              (WAITORTIMERCALLBACK)WmiEventNotifier::WmiQueryWorker,
              Parameter,
              *((_DWORD *)Parameter + 12),
              *((_DWORD *)Parameter + 12),
              0) )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v53 = 0;
        v52 = &ComError::`vftable';
        v54 = LastError;
        v55 = 1235;
        v56 = 1;
        throw (ComError *)&v52;
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
      SysFreeString(bstrString);
      SysFreeString(v20);
    }
    catch ( const ComError *v21 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids,
          *((unsigned int *)v21 + 6),
          *((_DWORD *)v21 + 7));
      (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 24LL))(Parameter);
    }
  }
}

```

## disassembly

```asm
0x1800b3b40  mov     [rsp+arg_8], rbx
0x1800b3b45  mov     [rsp+arg_0], rcx
0x1800b3b4a  push    rsi
0x1800b3b4b  push    rdi
0x1800b3b4c  push    r12
0x1800b3b4e  push    r14
0x1800b3b50  push    r15
0x1800b3b52  sub     rsp, 300h
0x1800b3b59  mov     rbx, r8
0x1800b3b5c  mov     rdi, rdx
0x1800b3b5f  mov     rsi, rcx
0x1800b3b62  mov     rax, [rcx]
0x1800b3b65  mov     rax, [rax+10h]
0x1800b3b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b6e  test    al, al
0x1800b3b70  jz      short loc_1800B3BAD
0x1800b3b72  lea     r14, WPP_GLOBAL_Control
0x1800b3b79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3b80  cmp     rcx, r14
0x1800b3b83  jz      loc_1800B3FE7
0x1800b3b89  test    byte ptr [rcx+1Ch], 2
0x1800b3b8d  jz      loc_1800B3FE7
0x1800b3b93  mov     edx, 2Eh ; '.'
0x1800b3b98  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x1800b3b9f  mov     rcx, [rcx+10h]
0x1800b3ba3  call    WPP_SF_
0x1800b3ba8  jmp     loc_1800B3FE7
0x1800b3bad  mov     [rsi+38h], rdi
0x1800b3bb1  mov     [rsi+40h], rbx
0x1800b3bb5  lea     rdi, [rsi+8]
0x1800b3bb9  mov     rcx, rdi
0x1800b3bbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3bc1  mov     [rsp+328h+ppv], rdi; ppv
0x1800b3bc6  lea     r9, IID_IWbemLocator; riid
0x1800b3bcd  mov     r14d, 1
0x1800b3bd3  mov     r8d, r14d; dwClsContext
0x1800b3bd6  xor     edx, edx; pUnkOuter
0x1800b3bd8  lea     rcx, CLSID_WbemLocator; rclsid
0x1800b3bdf  call    cs:__imp_CoCreateInstance
0x1800b3be5  test    eax, eax
0x1800b3be7  jns     short loc_1800B3C22
0x1800b3be9  xorps   xmm0, xmm0
0x1800b3bec  movups  [rsp+328h+var_2C0], xmm0
0x1800b3bf1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3bf8  mov     [rsp+328h+pExceptionObject], rcx
0x1800b3bfd  mov     [rsp+328h+var_2B0], eax
0x1800b3c01  mov     [rsp+328h+var_2AC], 494h
0x1800b3c09  mov     [rsp+328h+var_2A8], r14d
0x1800b3c11  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3c18  lea     rcx, [rsp+328h+pExceptionObject]; pExceptionObject
0x1800b3c1d  call    _CxxThrowException_0
0x1800b3c22  lea     rdx, aRootCimv2; "ROOT\\CIMV2"
0x1800b3c29  lea     rcx, [rsp+328h+var_2D8]; this
0x1800b3c2e  call    ??0SmartBSTR@@QEAA@PEBG@Z; SmartBSTR::SmartBSTR(ushort const *)
0x1800b3c33  nop
0x1800b3c34  mov     rdi, [rdi]
0x1800b3c37  mov     rax, [rdi]
0x1800b3c3a  mov     rbx, [rax+18h]
0x1800b3c3e  lea     r15, [rsi+10h]
0x1800b3c42  mov     rcx, r15
0x1800b3c45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3c4a  mov     [rsp+328h+var_2E8], r15
0x1800b3c4f  mov     [rsp+328h+var_2F0], 0
0x1800b3c58  mov     qword ptr [rsp+328h+Flags], 0
0x1800b3c61  mov     [rsp+328h+Period], 0
0x1800b3c69  mov     [rsp+328h+ppv], 0
0x1800b3c72  xor     r9d, r9d
0x1800b3c75  xor     r8d, r8d
0x1800b3c78  mov     rdx, [rsp+328h+var_2D8]
0x1800b3c7d  mov     rcx, rdi
0x1800b3c80  mov     rax, rbx
0x1800b3c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c88  test    eax, eax
0x1800b3c8a  jns     short loc_1800B3CD4
0x1800b3c8c  xorps   xmm0, xmm0
0x1800b3c8f  movups  [rsp+328h+var_260], xmm0
0x1800b3c97  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3c9e  mov     [rsp+328h+var_268], rcx
0x1800b3ca6  mov     [rsp+328h+var_250], eax
0x1800b3cad  mov     [rsp+328h+var_24C], 4A0h
0x1800b3cb8  mov     [rsp+328h+var_248], r14d
0x1800b3cc0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3cc7  lea     rcx, [rsp+328h+var_268]; pExceptionObject
0x1800b3ccf  call    _CxxThrowException_0
0x1800b3cd4  xor     r8d, r8d; unsigned int
0x1800b3cd7  lea     edx, [r8+3]; unsigned int
0x1800b3cdb  mov     rcx, [r15]; struct IUnknown *
0x1800b3cde  call    ?ConfigureProxyBlanket@@YAJPEAUIUnknown@@KK@Z; ConfigureProxyBlanket(IUnknown *,ulong,ulong)
0x1800b3ce3  test    eax, eax
0x1800b3ce5  jns     short loc_1800B3D2F
0x1800b3ce7  xorps   xmm0, xmm0
0x1800b3cea  movups  [rsp+328h+var_200], xmm0
0x1800b3cf2  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3cf9  mov     [rsp+328h+var_208], rcx
0x1800b3d01  mov     [rsp+328h+var_1F0], eax
0x1800b3d08  mov     [rsp+328h+var_1EC], 4A6h
0x1800b3d13  mov     [rsp+328h+var_1E8], r14d
0x1800b3d1b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3d22  lea     rcx, [rsp+328h+var_208]; pExceptionObject
0x1800b3d2a  call    _CxxThrowException_0
0x1800b3d2f  lea     rdx, aWql; "WQL"
0x1800b3d36  lea     rcx, [rsp+328h+bstrString]; this
0x1800b3d3e  call    ??0SmartBSTR@@QEAA@PEBG@Z; SmartBSTR::SmartBSTR(ushort const *)
0x1800b3d43  nop
0x1800b3d44  mov     rdi, [r15]
0x1800b3d47  mov     rax, [rdi]
0x1800b3d4a  mov     rbx, [rax+0B0h]
0x1800b3d51  lea     r12, [rsi+18h]
0x1800b3d55  mov     rcx, r12
0x1800b3d58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3d5d  mov     qword ptr [rsp+328h+Period], r12
0x1800b3d62  mov     [rsp+328h+ppv], 0
0x1800b3d6b  mov     r9d, 30h ; '0'
0x1800b3d71  mov     r8, [rsi+20h]
0x1800b3d75  mov     rdx, [rsp+328h+bstrString]
0x1800b3d7d  mov     rcx, rdi
0x1800b3d80  mov     rax, rbx
0x1800b3d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d88  test    eax, eax
0x1800b3d8a  jns     loc_1800B3EA4
0x1800b3d90  cmp     qword ptr [rsi+28h], 0
0x1800b3d95  jz      loc_1800B3E5C
0x1800b3d9b  lea     r14, WPP_GLOBAL_Control
0x1800b3da2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3da9  cmp     rcx, r14
0x1800b3dac  jz      short loc_1800B3DC9
0x1800b3dae  test    byte ptr [rcx+1Ch], 2
0x1800b3db2  jz      short loc_1800B3DC9
0x1800b3db4  mov     edx, 2Fh ; '/'
0x1800b3db9  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x1800b3dc0  mov     rcx, [rcx+10h]
0x1800b3dc4  call    WPP_SF_
0x1800b3dc9  mov     rdi, [r15]
0x1800b3dcc  mov     rax, [rdi]
0x1800b3dcf  mov     rbx, [rax+0B0h]
0x1800b3dd6  mov     rcx, r12
0x1800b3dd9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3dde  mov     qword ptr [rsp+328h+Period], r12
0x1800b3de3  mov     [rsp+328h+ppv], 0
0x1800b3dec  mov     r9d, 30h ; '0'
0x1800b3df2  mov     r8, [rsi+28h]
0x1800b3df6  mov     rdx, [rsp+328h+bstrString]
0x1800b3dfe  mov     rcx, rdi
0x1800b3e01  mov     rax, rbx
0x1800b3e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e09  test    eax, eax
0x1800b3e0b  jns     loc_1800B3EAB
0x1800b3e11  xorps   xmm0, xmm0
0x1800b3e14  movups  [rsp+328h+var_1A0], xmm0
0x1800b3e1c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3e23  mov     [rsp+328h+var_1A8], rcx
0x1800b3e2b  mov     [rsp+328h+var_190], eax
0x1800b3e32  mov     [rsp+328h+var_18C], 4BBh
0x1800b3e3d  mov     [rsp+328h+var_188], 1
0x1800b3e48  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3e4f  lea     rcx, [rsp+328h+var_1A8]; pExceptionObject
0x1800b3e57  call    _CxxThrowException_0
0x1800b3e5c  xorps   xmm0, xmm0
0x1800b3e5f  movups  [rsp+328h+var_140], xmm0
0x1800b3e67  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3e6e  mov     [rsp+328h+var_148], rcx
0x1800b3e76  mov     [rsp+328h+var_130], eax
0x1800b3e7d  mov     [rsp+328h+var_12C], 4BFh
0x1800b3e88  mov     [rsp+328h+var_128], r14d
0x1800b3e90  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3e97  lea     rcx, [rsp+328h+var_148]; pExceptionObject
0x1800b3e9f  call    _CxxThrowException_0
0x1800b3ea4  lea     r14, WPP_GLOBAL_Control
0x1800b3eab  xor     r8d, r8d; unsigned int
0x1800b3eae  lea     edx, [r8+3]; unsigned int
0x1800b3eb2  mov     rcx, [r12]; struct IUnknown *
0x1800b3eb6  call    ?ConfigureProxyBlanket@@YAJPEAUIUnknown@@KK@Z; ConfigureProxyBlanket(IUnknown *,ulong,ulong)
0x1800b3ebb  test    eax, eax
0x1800b3ebd  jns     short loc_1800B3F0A
0x1800b3ebf  xorps   xmm0, xmm0
0x1800b3ec2  movups  [rsp+328h+var_E0], xmm0
0x1800b3eca  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3ed1  mov     [rsp+328h+var_E8], rcx
0x1800b3ed9  mov     [rsp+328h+var_D0], eax
0x1800b3ee0  mov     [rsp+328h+var_CC], 4C6h
0x1800b3eeb  mov     [rsp+328h+var_C8], 1
0x1800b3ef6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3efd  lea     rcx, [rsp+328h+var_E8]; pExceptionObject
0x1800b3f05  call    _CxxThrowException_0
0x1800b3f0a  mov     eax, [rsi+30h]
0x1800b3f0d  lea     rcx, [rsi+48h]; phNewTimer
0x1800b3f11  mov     [rsp+328h+Flags], 0; Flags
0x1800b3f19  mov     [rsp+328h+Period], eax; Period
0x1800b3f1d  mov     dword ptr [rsp+328h+ppv], eax; DueTime
0x1800b3f21  mov     r9, rsi; Parameter
0x1800b3f24  lea     r8, ?WmiQueryWorker@WmiEventNotifier@@CAXPEAXE@Z; Callback
0x1800b3f2b  xor     edx, edx; TimerQueue
0x1800b3f2d  call    cs:__imp_CreateTimerQueueTimer
0x1800b3f33  test    eax, eax
0x1800b3f35  jnz     short loc_1800B3FA2
0x1800b3f37  call    cs:__imp_GetLastError
0x1800b3f3d  test    eax, eax
0x1800b3f3f  jg      short loc_1800B3F49
0x1800b3f41  call    cs:__imp_GetLastError
0x1800b3f47  jmp     short loc_1800B3F57
0x1800b3f49  call    cs:__imp_GetLastError
0x1800b3f4f  movzx   eax, ax
0x1800b3f52  or      eax, 80070000h
0x1800b3f57  xorps   xmm0, xmm0
0x1800b3f5a  movups  [rsp+328h+var_80], xmm0
0x1800b3f62  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800b3f69  mov     [rsp+328h+var_88], rcx
0x1800b3f71  mov     [rsp+328h+var_70], eax
0x1800b3f78  mov     [rsp+328h+var_6C], 4D3h
0x1800b3f83  mov     [rsp+328h+var_68], 1
0x1800b3f8e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800b3f95  lea     rcx, [rsp+328h+var_88]; pExceptionObject
0x1800b3f9d  call    _CxxThrowException_0
0x1800b3fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3fa9  cmp     rcx, r14
0x1800b3fac  jz      short loc_1800B3FCA
0x1800b3fae  test    byte ptr [rcx+1Ch], 1
0x1800b3fb2  jz      short loc_1800B3FCA
0x1800b3fb4  mov     edx, 30h ; '0'
0x1800b3fb9  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x1800b3fc0  mov     rcx, [rcx+10h]
0x1800b3fc4  call    WPP_SF_
0x1800b3fc9  nop
0x1800b3fca  mov     rcx, [rsp+328h+bstrString]; bstrString
0x1800b3fd2  call    cs:__imp_SysFreeString
0x1800b3fd8  nop
0x1800b3fd9  mov     rcx, [rsp+328h+var_2D8]; bstrString
0x1800b3fde  call    cs:__imp_SysFreeString
0x1800b3fe4  nop
0x1800b3fe5  jmp     short $+2
0x1800b3fe7  mov     rbx, [rsp+328h+arg_8]
0x1800b3fef  add     rsp, 300h
0x1800b3ff6  pop     r15
0x1800b3ff8  pop     r14
0x1800b3ffa  pop     r12
0x1800b3ffc  pop     rdi
0x1800b3ffd  pop     rsi
0x1800b3ffe  retn
```
