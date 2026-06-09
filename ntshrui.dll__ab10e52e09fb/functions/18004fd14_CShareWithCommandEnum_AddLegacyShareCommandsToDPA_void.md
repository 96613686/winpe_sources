# CShareWithCommandEnum::_AddLegacyShareCommandsToDPA(void)

- ea: `0x18004fd14`
- end: `0x18004ff22`
- name: `?_AddLegacyShareCommandsToDPA@CShareWithCommandEnum@@IEAAJXZ`
- size: `526`
- prototype: `__int64 __fastcall(CShareWithCommandEnum *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050090`

## callees

- `0x1800120e0`
- `0x18001c4a8`
- `0x18004fd14`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004fe67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004fe67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fd4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fd4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff03`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18004fd7a`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18004fd7a`

## string_xrefs

- `0x18004fd3e`: `ShareCommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CShareWithCommandEnum::_AddLegacyShareCommandsToDPA(CShareWithCommandEnum *this)
{
  HRESULT appended; // ebx
  char v3; // si
  __int64 v4; // rdx
  _DWORD *v5; // rax
  void *ppv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v8; // [rsp+38h] [rbp-18h] BYREF
  __int64 v9; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  int v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 v12; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  appended = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"ShareCommands", 0, 0x20019u, &hKey) )
  {
    ppv = 0;
    appended = SHCoCreateInstance(
                 0,
                 &CLSID_ExplorerCommandEnumerator,
                 0,
                 &GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8,
                 &ppv);
    if ( appended >= 0 )
    {
      v9 = 0;
      appended = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                   ppv,
                   &GUID_d960050c_f4e1_4294_ac4b_598913605923,
                   &v9);
      if ( appended >= 0 )
      {
        appended = (*(__int64 (__fastcall **)(__int64, HKEY))(*(_QWORD *)v9 + 24LL))(v9, hKey);
        if ( appended >= 0 )
        {
          v12 = 0;
          v11 = 0;
          v3 = 1;
          while ( (*(int (__fastcall **)(void *, __int64, __int64 *, int *))(*(_QWORD *)ppv + 24LL))(ppv, 1, &v12, &v11) >= 0 )
          {
            v4 = v12;
            if ( !v12 )
              break;
            if ( v3 )
            {
              v5 = (_DWORD *)*((_QWORD *)this + 2);
              if ( v5 )
              {
                if ( *v5 )
                {
                  v3 = 0;
                  v13 = 0;
                  v8 = 0;
                  appended = CoCreateInstance(
                               &CLSID_CommandStore,
                               0,
                               1u,
                               &GUID_3ef82a5e_f7d2_4688_9e64_90614e7820c8,
                               &v8);
                  if ( appended >= 0 )
                    appended = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v8 + 24LL))(
                                 v8,
                                 L"Windows.Separator",
                                 &GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9,
                                 &v13);
                  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v8);
                  if ( appended >= 0 )
                  {
                    appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr((char *)this + 16, v13);
                    if ( appended >= 0 )
                      v13 = 0;
                  }
                  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v13);
                  v4 = v12;
                }
              }
            }
            if ( appended < 0 )
              break;
            appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr((char *)this + 16, v4);
            if ( appended < 0 )
              break;
            v12 = 0;
          }
          ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v12);
        }
      }
      ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v9);
    }
    RegCloseKey(hKey);
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppv);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004fd14  mov     [rsp-18h+arg_0], rbx
0x18004fd19  push    rbp
0x18004fd1a  push    rsi
0x18004fd1b  push    rdi
0x18004fd1c  mov     rbp, rsp
0x18004fd1f  sub     rsp, 50h
0x18004fd23  mov     rdi, rcx
0x18004fd26  xor     ebx, ebx
0x18004fd28  mov     [rbp+hKey], rbx
0x18004fd2c  lea     rax, [rbp+hKey]
0x18004fd30  mov     [rsp+50h+phkResult], rax; phkResult
0x18004fd35  mov     r9d, 20019h; samDesired
0x18004fd3b  xor     r8d, r8d; ulOptions
0x18004fd3e  lea     rdx, aSharecommands; "ShareCommands"
0x18004fd45  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004fd4c  call    cs:__imp_RegOpenKeyExW
0x18004fd52  test    eax, eax
0x18004fd54  jnz     loc_18004FF13
0x18004fd5a  mov     [rbp+ppv], rbx
0x18004fd5e  lea     rax, [rbp+ppv]
0x18004fd62  mov     [rsp+50h+phkResult], rax; ppv
0x18004fd67  lea     r9, _GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8; riid
0x18004fd6e  xor     r8d, r8d; pUnkOuter
0x18004fd71  lea     rdx, CLSID_ExplorerCommandEnumerator; pclsid
0x18004fd78  xor     ecx, ecx; pszCLSID
0x18004fd7a  call    cs:__imp_SHCoCreateInstance
0x18004fd80  mov     ebx, eax
0x18004fd82  test    eax, eax
0x18004fd84  js      loc_18004FEFF
0x18004fd8a  mov     [rbp+var_10], 0
0x18004fd92  mov     rcx, [rbp+ppv]
0x18004fd96  mov     rax, [rcx]
0x18004fd99  lea     r8, [rbp+var_10]
0x18004fd9d  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x18004fda4  mov     rax, [rax]
0x18004fda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fdac  mov     ebx, eax
0x18004fdae  test    eax, eax
0x18004fdb0  js      loc_18004FEF6
0x18004fdb6  mov     rcx, [rbp+var_10]
0x18004fdba  mov     rax, [rcx]
0x18004fdbd  mov     rdx, [rbp+hKey]
0x18004fdc1  mov     rax, [rax+18h]
0x18004fdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fdca  mov     ebx, eax
0x18004fdcc  test    eax, eax
0x18004fdce  js      loc_18004FEF6
0x18004fdd4  mov     [rbp+arg_10], 0
0x18004fddc  mov     [rbp+arg_8], 0
0x18004fde3  mov     sil, 1
0x18004fde6  mov     rcx, [rbp+ppv]
0x18004fdea  mov     rax, [rcx]
0x18004fded  lea     r9, [rbp+arg_8]
0x18004fdf1  lea     r8, [rbp+arg_10]
0x18004fdf5  mov     edx, 1
0x18004fdfa  mov     rax, [rax+18h]
0x18004fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe03  test    eax, eax
0x18004fe05  js      loc_18004FEEC
0x18004fe0b  mov     rdx, [rbp+arg_10]
0x18004fe0f  test    rdx, rdx
0x18004fe12  jz      loc_18004FEEC
0x18004fe18  test    sil, sil
0x18004fe1b  jz      loc_18004FECC
0x18004fe21  mov     rax, [rdi+10h]
0x18004fe25  test    rax, rax
0x18004fe28  jz      loc_18004FECC
0x18004fe2e  cmp     dword ptr [rax], 0
0x18004fe31  jz      loc_18004FECC
0x18004fe37  xor     sil, sil
0x18004fe3a  mov     [rbp+arg_18], 0
0x18004fe42  mov     [rbp+var_18], 0
0x18004fe4a  lea     rax, [rbp+var_18]
0x18004fe4e  mov     [rsp+50h+phkResult], rax; ppv
0x18004fe53  lea     r9, _GUID_3ef82a5e_f7d2_4688_9e64_90614e7820c8; riid
0x18004fe5a  xor     edx, edx; pUnkOuter
0x18004fe5c  lea     r8d, [rdx+1]; dwClsContext
0x18004fe60  lea     rcx, CLSID_CommandStore; rclsid
0x18004fe67  call    cs:__imp_CoCreateInstance
0x18004fe6d  mov     ebx, eax
0x18004fe6f  test    eax, eax
0x18004fe71  js      short loc_18004FE97
0x18004fe73  mov     rcx, [rbp+var_18]
0x18004fe77  mov     rax, [rcx]
0x18004fe7a  lea     r9, [rbp+arg_18]
0x18004fe7e  lea     r8, _GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9
0x18004fe85  lea     rdx, aWindowsSeparat; "Windows.Separator"
0x18004fe8c  mov     rax, [rax+18h]
0x18004fe90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe95  mov     ebx, eax
0x18004fe97  lea     rcx, [rbp+var_18]
0x18004fe9b  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18004fea0  test    ebx, ebx
0x18004fea2  js      short loc_18004FEBF
0x18004fea4  mov     rdx, [rbp+arg_18]
0x18004fea8  lea     rcx, [rdi+10h]
0x18004feac  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18004feb1  mov     ebx, eax
0x18004feb3  test    eax, eax
0x18004feb5  js      short loc_18004FEBF
0x18004feb7  mov     [rbp+arg_18], 0
0x18004febf  lea     rcx, [rbp+arg_18]
0x18004fec3  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18004fec8  mov     rdx, [rbp+arg_10]
0x18004fecc  test    ebx, ebx
0x18004fece  js      short loc_18004FEEC
0x18004fed0  lea     rcx, [rdi+10h]
0x18004fed4  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18004fed9  mov     ebx, eax
0x18004fedb  test    eax, eax
0x18004fedd  js      short loc_18004FEEC
0x18004fedf  mov     [rbp+arg_10], 0
0x18004fee7  jmp     loc_18004FDE6
0x18004feec  lea     rcx, [rbp+arg_10]
0x18004fef0  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18004fef5  nop
0x18004fef6  lea     rcx, [rbp+var_10]
0x18004fefa  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18004feff  mov     rcx, [rbp+hKey]; hKey
0x18004ff03  call    cs:__imp_RegCloseKey
0x18004ff09  nop
0x18004ff0a  lea     rcx, [rbp+ppv]
0x18004ff0e  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18004ff13  mov     eax, ebx
0x18004ff15  mov     rbx, [rsp+50h+arg_0]
0x18004ff1a  add     rsp, 50h
0x18004ff1e  pop     rdi
0x18004ff1f  pop     rsi
0x18004ff20  pop     rbp
0x18004ff21  retn
```
