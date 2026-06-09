# PermissionDialogThreadProc(void *)

- ea: `0x180049bb0`
- end: `0x180049dc6`
- name: `?PermissionDialogThreadProc@@YAKPEAX@Z`
- size: `534`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800194cc`
- `0x18001c4a8`
- `0x180024e44`
- `0x18003c10c`
- `0x180049bb0`
- `0x18004ef08`
- `0x18004f004`
- `0x1800511d0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049ce0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049ce0`
- `SHELL32!SHParseDisplayName` at `0x180049c6e`
- `SHELL32!SHParseDisplayName` at `0x180049c6e`
- `SHLWAPI!PathIsDirectoryW` at `0x180049d29`
- `SHLWAPI!PathIsDirectoryW` at `0x180049d29`
- `SHLWAPI!PathFindFileNameW` at `0x180049d05`
- `SHLWAPI!PathFindFileNameW` at `0x180049d05`
- `OLEAUT32!__imp_SysAllocString` at `0x180049cf4`
- `OLEAUT32!__imp_SysAllocString` at `0x180049d0e`
- `OLEAUT32!__imp_SysAllocString` at `0x180049cf4`
- `OLEAUT32!__imp_SysAllocString` at `0x180049d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d74`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d74`
- `USER32!DestroyWindow` at `0x180049d7e`
- `USER32!DestroyWindow` at `0x180049d7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_BOOL8 __fastcall PermissionDialogThreadProc(CMarshaledInterface *Parameter, unsigned int a2, __int64 a3, bool a4)
{
  HRESULT v5; // esi
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, __int64, PCWSTR *); // rbx
  struct IDataObject *v8; // rcx
  OLECHAR *v9; // rdi
  const OLECHAR *FileNameW; // rax
  BSTR v11; // rax
  OLECHAR *v12; // rbx
  BOOL IsDirectoryW; // eax
  PCWSTR pszName; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+58h] [rbp-18h]
  __int64 v17; // [rsp+60h] [rbp-10h]
  HWND hWnd; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+38h] BYREF
  LPITEMIDLIST ppidl; // [rsp+B0h] [rbp+40h] BYREF
  void *v21; // [rsp+B8h] [rbp+48h] BYREF

  v21 = 0;
  v5 = -2147467259;
  if ( *(_QWORD *)Parameter )
  {
    v5 = CMarshaledInterface::_Unmarshal(Parameter, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v21, a4);
    if ( v5 >= 0 )
    {
      pszName = 0;
      v16 = 0;
      v17 = 0;
      v6 = v21;
      v7 = *(__int64 (__fastcall **)(void *, __int64, PCWSTR *))(*(_QWORD *)v21 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszName);
      v16 = -1;
      v17 = -1;
      v5 = v7(v6, 2147844096LL, &pszName);
      if ( v5 >= 0 )
      {
        hWnd = 0;
        ppidl = 0;
        v5 = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
        if ( v5 >= 0 )
        {
          ppv = 0;
          Stub_GetPosition(v8, 0, (struct tagPOINT *)&ppv);
          Stub_EnsureUniqueStubWithParent(0, (const struct _ITEMIDLIST_ABSOLUTE *)ppidl, 1, (struct tagPOINT)ppv, &hWnd);
          if ( hWnd )
          {
            ppv = 0;
            v5 = CoCreateInstance(
                   &GUID_1f2e5c40_9550_11ce_99d2_00aa006e086c,
                   0,
                   1u,
                   &GUID_74807f67_0058_440d_8600_65541a7fbbea,
                   &ppv);
            if ( v5 >= 0 )
            {
              v9 = SysAllocString(pszName);
              FileNameW = PathFindFileNameW(pszName);
              v11 = SysAllocString(FileNameW);
              v12 = v11;
              if ( v9 && v11 )
              {
                IsDirectoryW = PathIsDirectoryW(pszName);
                v5 = (*(__int64 (__fastcall **)(LPVOID, HWND, OLECHAR *, OLECHAR *, unsigned int, int))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       hWnd,
                       v9,
                       v12,
                       (unsigned int)IsDirectoryW + 16,
                       0x10000);
              }
              else
              {
                v5 = -2147024882;
              }
              SysFreeString(v12);
              SysFreeString(v9);
            }
            DestroyWindow(hWnd);
            ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppv);
          }
        }
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppidl);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszName);
    }
  }
  CThreadProcData::`scalar deleting destructor'(Parameter, a2);
  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v21);
  return v5 >= 0;
}

```

## disassembly

```asm
0x180049bb0  push    rbp
0x180049bb2  push    rbx
0x180049bb3  push    rsi
0x180049bb4  push    rdi
0x180049bb5  push    r14
0x180049bb7  mov     rbp, rsp
0x180049bba  sub     rsp, 70h
0x180049bbe  mov     r14, rcx
0x180049bc1  mov     [rbp+arg_18], 0
0x180049bc9  mov     esi, 80004005h
0x180049bce  cmp     qword ptr [rcx], 0
0x180049bd2  jz      loc_180049DA2
0x180049bd8  lea     r8, [rbp+arg_18]; void **
0x180049bdc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x180049be3  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x180049be8  mov     esi, eax
0x180049bea  test    eax, eax
0x180049bec  js      loc_180049DA2
0x180049bf2  mov     [rbp+pszName], 0
0x180049bfa  mov     [rbp+var_18], 0
0x180049c02  mov     [rbp+var_10], 0
0x180049c0a  mov     rdi, [rbp+arg_18]
0x180049c0e  mov     rax, [rdi]
0x180049c11  mov     rbx, [rax+28h]
0x180049c15  lea     rcx, [rbp+pszName]
0x180049c19  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180049c1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049c22  mov     [rbp+var_18], rax
0x180049c26  mov     [rbp+var_10], rax
0x180049c2a  lea     r8, [rbp+pszName]
0x180049c2e  mov     edx, 80058000h
0x180049c33  mov     rcx, rdi
0x180049c36  mov     rax, rbx
0x180049c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c3e  mov     esi, eax
0x180049c40  test    eax, eax
0x180049c42  js      loc_180049D99
0x180049c48  mov     [rbp+hWnd], 0
0x180049c50  mov     [rbp+ppidl], 0
0x180049c58  mov     [rsp+70h+psfgaoOut], 0; psfgaoOut
0x180049c61  xor     r9d, r9d; sfgaoIn
0x180049c64  lea     r8, [rbp+ppidl]; ppidl
0x180049c68  xor     edx, edx; pbc
0x180049c6a  mov     rcx, [rbp+pszName]; pszName
0x180049c6e  call    cs:__imp_SHParseDisplayName
0x180049c74  mov     esi, eax
0x180049c76  test    eax, eax
0x180049c78  js      loc_180049D8F
0x180049c7e  mov     [rbp+ppv], 0
0x180049c86  lea     r8, [rbp+ppv]; struct tagPOINT *
0x180049c8a  xor     edx, edx; HWND
0x180049c8c  call    ?Stub_GetPosition@@YAXPEAUIDataObject@@PEAUHWND__@@PEAUtagPOINT@@@Z; Stub_GetPosition(IDataObject *,HWND__ *,tagPOINT *)
0x180049c91  lea     rax, [rbp+hWnd]
0x180049c95  mov     [rsp+70h+psfgaoOut], rax; HWND *
0x180049c9a  mov     r9, [rbp+ppv]; struct tagPOINT
0x180049c9e  mov     ebx, 1
0x180049ca3  mov     r8d, ebx; int
0x180049ca6  mov     rdx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180049caa  xor     ecx, ecx; HWND
0x180049cac  call    ?Stub_EnsureUniqueStubWithParent@@YAHPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@HUtagPOINT@@PEAPEAU1@@Z; Stub_EnsureUniqueStubWithParent(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,int,tagPOINT,HWND__ * *)
0x180049cb1  cmp     [rbp+hWnd], 0
0x180049cb6  jz      loc_180049D8F
0x180049cbc  mov     [rbp+ppv], 0
0x180049cc4  lea     rax, [rbp+ppv]
0x180049cc8  mov     [rsp+70h+psfgaoOut], rax; ppv
0x180049ccd  lea     r9, _GUID_74807f67_0058_440d_8600_65541a7fbbea; riid
0x180049cd4  mov     r8d, ebx; dwClsContext
0x180049cd7  xor     edx, edx; pUnkOuter
0x180049cd9  lea     rcx, _GUID_1f2e5c40_9550_11ce_99d2_00aa006e086c; rclsid
0x180049ce0  call    cs:__imp_CoCreateInstance
0x180049ce6  mov     esi, eax
0x180049ce8  test    eax, eax
0x180049cea  js      loc_180049D7A
0x180049cf0  mov     rcx, [rbp+pszName]; psz
0x180049cf4  call    cs:__imp_SysAllocString
0x180049cfa  mov     rdi, rax
0x180049cfd  mov     [rbp+var_30], rax
0x180049d01  mov     rcx, [rbp+pszName]; pszPath
0x180049d05  call    cs:__imp_PathFindFileNameW
0x180049d0b  mov     rcx, rax; psz
0x180049d0e  call    cs:__imp_SysAllocString
0x180049d14  mov     rbx, rax
0x180049d17  mov     [rbp+var_28], rax
0x180049d1b  test    rdi, rdi
0x180049d1e  jz      short loc_180049D62
0x180049d20  test    rax, rax
0x180049d23  jz      short loc_180049D62
0x180049d25  mov     rcx, [rbp+pszName]; pszPath
0x180049d29  call    cs:__imp_PathIsDirectoryW
0x180049d2f  neg     eax
0x180049d31  sbb     edx, edx
0x180049d33  neg     edx
0x180049d35  add     edx, 10h
0x180049d38  mov     rcx, [rbp+ppv]
0x180049d3c  mov     rax, [rcx]
0x180049d3f  mov     [rsp+70h+var_48], 10000h
0x180049d47  mov     dword ptr [rsp+70h+psfgaoOut], edx
0x180049d4b  mov     r9, rbx
0x180049d4e  mov     r8, rdi
0x180049d51  mov     rdx, [rbp+hWnd]
0x180049d55  mov     rax, [rax+18h]
0x180049d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d5e  mov     esi, eax
0x180049d60  jmp     short loc_180049D67
0x180049d62  mov     esi, 8007000Eh
0x180049d67  mov     rcx, rbx; bstrString
0x180049d6a  call    cs:__imp_SysFreeString
0x180049d70  nop
0x180049d71  mov     rcx, rdi; bstrString
0x180049d74  call    cs:__imp_SysFreeString
0x180049d7a  mov     rcx, [rbp+hWnd]; hWnd
0x180049d7e  call    cs:__imp_DestroyWindow
0x180049d84  nop
0x180049d85  lea     rcx, [rbp+ppv]
0x180049d89  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180049d8e  nop
0x180049d8f  lea     rcx, [rbp+ppidl]
0x180049d93  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180049d98  nop
0x180049d99  lea     rcx, [rbp+pszName]
0x180049d9d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180049da2  mov     rcx, r14; this
0x180049da5  call    ??_GCThreadProcData@@QEAAPEAXI@Z; CThreadProcData::`scalar deleting destructor'(uint)
0x180049daa  nop
0x180049dab  not     esi
0x180049dad  shr     esi, 1Fh
0x180049db0  lea     rcx, [rbp+arg_18]
0x180049db4  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180049db9  mov     eax, esi
0x180049dbb  add     rsp, 70h
0x180049dbf  pop     r14
0x180049dc1  pop     rdi
0x180049dc2  pop     rsi
0x180049dc3  pop     rbx
0x180049dc4  pop     rbp
0x180049dc5  retn
```
