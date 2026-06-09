# CSharePageWarn::_BuildParentFolderList(CDPA<CResultItem,CTContainer_PolicyUnOwned<CResultItem>> &)

- ea: `0x180070d14`
- end: `0x180071030`
- name: `?_BuildParentFolderList@CSharePageWarn@@AEAAJAEAV?$CDPA@VCResultItem@@V?$CTContainer_PolicyUnOwned@VCResultItem@@@@@@@Z`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071038`

## callees

- `0x18001a1a4`
- `0x18001b05c`
- `0x1800254e0`
- `0x1800575e8`
- `0x180070a2c`
- `0x180070d14`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180070e18`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180070e18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070fdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070fdc`
- `ole32!CreateBindCtx` at `0x180070e6f`
- `ole32!CreateBindCtx` at `0x180070e6f`

## pseudocode

```c
__int64 __fastcall CSharePageWarn::_BuildParentFolderList(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  HRESULT IdentityItemName; // ebx
  unsigned int v5; // edx
  const struct _GUID *v6; // r8
  __int64 v7; // rcx
  unsigned int i; // edi
  __int64 v9; // rcx
  PWSTR pszPath; // [rsp+30h] [rbp-29h] BYREF
  struct IShellItem *v12; // [rsp+38h] [rbp-21h] BYREF
  int v13; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-15h] BYREF
  __int64 v15; // [rsp+48h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-9h] BYREF
  int v17; // [rsp+58h] [rbp-1h] BYREF
  __int64 v18; // [rsp+60h] [rbp+7h] BYREF
  __int64 v19; // [rsp+68h] [rbp+Fh] BYREF
  void *v20; // [rsp+70h] [rbp+17h] BYREF
  __int64 v21; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v22[2]; // [rsp+80h] [rbp+27h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v21 = 0;
  IdentityItemName = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v2 + 16) + 72LL))(
                       *(_QWORD *)(v2 + 16),
                       &v21);
  if ( IdentityItemName >= 0 )
  {
    v17 = 0;
    v12 = 0;
    do
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IShellItem **, int *))(*(_QWORD *)v21 + 24LL))(
             v21,
             1,
             &v12,
             &v17) )
      {
        break;
      }
      v13 = 0;
      IdentityItemName = ((__int64 (__fastcall *)(struct IShellItem *, __int64, int *))v12->lpVtbl->GetAttributes)(
                           v12,
                           1614807040,
                           &v13);
      if ( IdentityItemName >= 0 && v13 != 1610612736 )
      {
        pv = 0;
        IdentityItemName = GetIdentityItemName(v12, SIGDN_NORMALDISPLAY, (unsigned __int16 **)&pv);
        if ( IdentityItemName >= 0 )
        {
          v20 = 0;
          pszPath = 0;
          IdentityItemName = GetIdentityItemName(v12, SIGDN_FILESYSPATH, &pszPath);
          if ( IdentityItemName >= 0 )
          {
            IdentityItemName = -2147221019;
            if ( !PathCchRemoveFileSpec(pszPath, 0x8000u) )
              IdentityItemName = SHSimpleItemFromAttributes(pszPath, v5, v6, &v20);
            CoTaskMemFree(pszPath);
            if ( IdentityItemName >= 0 )
            {
              IdentityItemName = CSharePageWarn::_AddItem(v7, a2, v20, 0, pv);
              if ( IdentityItemName >= 0 )
              {
                pszPath = 0;
                IdentityItemName = CreateBindCtx(0, (LPBC *)&pszPath);
                if ( IdentityItemName >= 0 )
                {
                  v22[0] = 16;
                  v22[1] = 0;
                  IdentityItemName = (*(__int64 (__fastcall **)(PWSTR, _QWORD *))(*(_QWORD *)pszPath + 48LL))(
                                       pszPath,
                                       v22);
                  if ( IdentityItemName >= 0 )
                  {
                    v19 = 0;
                    IdentityItemName = ((__int64 (__fastcall *)(struct IShellItem *, PWSTR, const GUID *, GUID *, __int64 *))v12->lpVtbl->BindToHandler)(
                                         v12,
                                         pszPath,
                                         &BHID_SFObject,
                                         &GUID_d774a009_5a9a_4b52_80b9_daa2deaf9bb3,
                                         &v19);
                    if ( IdentityItemName < 0 )
                    {
                      if ( IdentityItemName == -2147467263 )
                        IdentityItemName = 0;
                    }
                    else
                    {
                      v15 = 0;
                      IdentityItemName = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v19 + 24LL))(
                                           v19,
                                           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                           &v15);
                      if ( IdentityItemName >= 0 )
                      {
                        v14 = 0;
                        IdentityItemName = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 56LL))(
                                             v15,
                                             &v14);
                        for ( i = 0; IdentityItemName >= 0; ++i )
                        {
                          if ( i >= v14 )
                            break;
                          v18 = 0;
                          IdentityItemName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 64LL))(
                                               v15,
                                               i,
                                               &v18);
                          if ( IdentityItemName >= 0 )
                          {
                            IdentityItemName = CSharePageWarn::_AddItem(v9, a2, v18, v12, pv);
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                          }
                        }
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                    }
                    (*(void (__fastcall **)(PWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
                  }
                  else
                  {
                    SafeRelease<IShellItemArray>(&pszPath);
                  }
                }
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
          CoTaskMemFree(pv);
        }
      }
      ((void (__fastcall *)(struct IShellItem *))v12->lpVtbl->Release)(v12);
    }
    while ( IdentityItemName >= 0 );
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)IdentityItemName;
}

```

## disassembly

```asm
0x180070d14  mov     [rsp-8+arg_10], rbx
0x180070d19  mov     [rsp-8+arg_18], rsi
0x180070d1e  push    rbp
0x180070d1f  push    rdi
0x180070d20  push    r14
0x180070d22  lea     rbp, [rsp-47h]
0x180070d27  sub     rsp, 0A0h
0x180070d2e  mov     rax, cs:__security_cookie
0x180070d35  xor     rax, rsp
0x180070d38  mov     [rbp+57h+var_20], rax
0x180070d3c  mov     rax, [rcx+10h]
0x180070d40  mov     rsi, rdx
0x180070d43  xor     r14d, r14d
0x180070d46  lea     rdx, [rbp+57h+var_38]
0x180070d4a  mov     [rbp+57h+var_38], r14
0x180070d4e  mov     rcx, [rax+10h]
0x180070d52  mov     rax, [rcx]
0x180070d55  mov     rax, [rax+48h]
0x180070d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d5e  mov     ebx, eax
0x180070d60  test    eax, eax
0x180070d62  js      loc_18007100A
0x180070d68  mov     [rbp+57h+var_58], r14d
0x180070d6c  mov     [rbp+57h+var_78], r14
0x180070d70  mov     rcx, [rbp+57h+var_38]
0x180070d74  lea     r9, [rbp+57h+var_58]
0x180070d78  lea     r8, [rbp+57h+var_78]
0x180070d7c  mov     rdx, [rcx]
0x180070d7f  mov     rax, [rdx+18h]
0x180070d83  mov     edx, 1
0x180070d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d8d  test    eax, eax
0x180070d8f  jnz     loc_180070FFA
0x180070d95  mov     rcx, [rbp+57h+var_78]
0x180070d99  lea     r8, [rbp+57h+var_70]
0x180070d9d  mov     [rbp+57h+var_70], r14d
0x180070da1  mov     edx, 60400000h
0x180070da6  mov     rax, [rcx]
0x180070da9  mov     rax, [rax+30h]
0x180070dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070db2  mov     ebx, eax
0x180070db4  test    eax, eax
0x180070db6  js      loc_180070FE2
0x180070dbc  cmp     [rbp+57h+var_70], 60000000h
0x180070dc3  jz      loc_180070FE2
0x180070dc9  mov     rcx, [rbp+57h+var_78]; struct IShellItem *
0x180070dcd  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x180070dd1  xor     edx, edx; enum _SIGDN
0x180070dd3  mov     [rbp+57h+pv], r14
0x180070dd7  call    ?GetIdentityItemName@@YAJPEAUIShellItem@@W4_SIGDN@@PEAPEAG@Z; GetIdentityItemName(IShellItem *,_SIGDN,ushort * *)
0x180070ddc  mov     ebx, eax
0x180070dde  test    eax, eax
0x180070de0  js      loc_180070FE2
0x180070de6  mov     rcx, [rbp+57h+var_78]; struct IShellItem *
0x180070dea  lea     r8, [rbp+57h+pszPath]; unsigned __int16 **
0x180070dee  mov     edx, 80058000h; enum _SIGDN
0x180070df3  mov     [rbp+57h+var_40], r14
0x180070df7  mov     [rbp+57h+pszPath], r14
0x180070dfb  call    ?GetIdentityItemName@@YAJPEAUIShellItem@@W4_SIGDN@@PEAPEAG@Z; GetIdentityItemName(IShellItem *,_SIGDN,ushort * *)
0x180070e00  mov     ebx, eax
0x180070e02  test    eax, eax
0x180070e04  js      loc_180070FD8
0x180070e0a  mov     rcx, [rbp+57h+pszPath]; pszPath
0x180070e0e  mov     edx, 8000h; cchPath
0x180070e13  mov     ebx, 800401E5h
0x180070e18  call    cs:__imp_PathCchRemoveFileSpec
0x180070e1e  test    eax, eax
0x180070e20  jnz     short loc_180070E31
0x180070e22  mov     rcx, [rbp+57h+pszPath]; pszPath
0x180070e26  lea     r9, [rbp+57h+var_40]; void **
0x180070e2a  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x180070e2f  mov     ebx, eax
0x180070e31  mov     rcx, [rbp+57h+pszPath]; pv
0x180070e35  call    cs:__imp_CoTaskMemFree
0x180070e3b  test    ebx, ebx
0x180070e3d  js      loc_180070FD8
0x180070e43  mov     rax, [rbp+57h+pv]
0x180070e47  xor     r9d, r9d
0x180070e4a  mov     r8, [rbp+57h+var_40]
0x180070e4e  mov     rdx, rsi
0x180070e51  mov     [rsp+0B0h+var_90], rax
0x180070e56  call    ?_AddItem@CSharePageWarn@@AEAAJAEAV?$CDPA@VCResultItem@@V?$CTContainer_PolicyUnOwned@VCResultItem@@@@@@PEAUIShellItem@@1PEAG@Z; CSharePageWarn::_AddItem(CDPA<CResultItem,CTContainer_PolicyUnOwned<CResultItem>> &,IShellItem *,IShellItem *,ushort *)
0x180070e5b  mov     ebx, eax
0x180070e5d  test    eax, eax
0x180070e5f  js      loc_180070FC8
0x180070e65  lea     rdx, [rbp+57h+pszPath]; ppbc
0x180070e69  mov     [rbp+57h+pszPath], r14
0x180070e6d  xor     ecx, ecx; reserved
0x180070e6f  call    cs:__imp_CreateBindCtx
0x180070e75  mov     ebx, eax
0x180070e77  test    eax, eax
0x180070e79  js      loc_180070FC8
0x180070e7f  mov     rcx, [rbp+57h+pszPath]
0x180070e83  lea     rdx, [rbp+57h+var_30]
0x180070e87  mov     [rbp+57h+var_30], 10h
0x180070e8f  mov     [rbp+57h+var_28], r14
0x180070e93  mov     rax, [rcx]
0x180070e96  mov     rax, [rax+30h]
0x180070e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e9f  mov     ebx, eax
0x180070ea1  test    eax, eax
0x180070ea3  jns     short loc_180070EB3
0x180070ea5  lea     rcx, [rbp+57h+pszPath]
0x180070ea9  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180070eae  jmp     loc_180070FC8
0x180070eb3  mov     rcx, [rbp+57h+var_78]
0x180070eb7  lea     rdx, [rbp+57h+var_48]
0x180070ebb  mov     [rbp+57h+var_48], r14
0x180070ebf  lea     r9, _GUID_d774a009_5a9a_4b52_80b9_daa2deaf9bb3
0x180070ec6  mov     [rsp+0B0h+var_90], rdx
0x180070ecb  lea     r8, BHID_SFObject
0x180070ed2  mov     rdx, [rbp+57h+pszPath]
0x180070ed6  mov     rax, [rcx]
0x180070ed9  mov     rax, [rax+18h]
0x180070edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ee2  mov     ebx, eax
0x180070ee4  test    eax, eax
0x180070ee6  js      loc_180070FAE
0x180070eec  mov     rcx, [rbp+57h+var_48]
0x180070ef0  lea     r8, [rbp+57h+var_68]
0x180070ef4  mov     [rbp+57h+var_68], r14
0x180070ef8  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180070eff  mov     rax, [rcx]
0x180070f02  mov     rax, [rax+18h]
0x180070f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f0b  mov     ebx, eax
0x180070f0d  test    eax, eax
0x180070f0f  js      loc_180070F9C
0x180070f15  mov     rcx, [rbp+57h+var_68]
0x180070f19  lea     rdx, [rbp+57h+var_6C]
0x180070f1d  mov     [rbp+57h+var_6C], r14d
0x180070f21  mov     rax, [rcx]
0x180070f24  mov     rax, [rax+38h]
0x180070f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f2d  mov     ebx, eax
0x180070f2f  mov     edi, r14d
0x180070f32  test    eax, eax
0x180070f34  js      short loc_180070F8C
0x180070f36  cmp     edi, [rbp+57h+var_6C]
0x180070f39  jnb     short loc_180070F8C
0x180070f3b  mov     rcx, [rbp+57h+var_68]
0x180070f3f  lea     r8, [rbp+57h+var_50]
0x180070f43  mov     [rbp+57h+var_50], r14
0x180070f47  mov     edx, edi
0x180070f49  mov     rax, [rcx]
0x180070f4c  mov     rax, [rax+40h]
0x180070f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f55  mov     ebx, eax
0x180070f57  test    eax, eax
0x180070f59  js      short loc_180070F86
0x180070f5b  mov     rax, [rbp+57h+pv]
0x180070f5f  mov     rdx, rsi
0x180070f62  mov     r9, [rbp+57h+var_78]
0x180070f66  mov     r8, [rbp+57h+var_50]
0x180070f6a  mov     [rsp+0B0h+var_90], rax
0x180070f6f  call    ?_AddItem@CSharePageWarn@@AEAAJAEAV?$CDPA@VCResultItem@@V?$CTContainer_PolicyUnOwned@VCResultItem@@@@@@PEAUIShellItem@@1PEAG@Z; CSharePageWarn::_AddItem(CDPA<CResultItem,CTContainer_PolicyUnOwned<CResultItem>> &,IShellItem *,IShellItem *,ushort *)
0x180070f74  mov     rcx, [rbp+57h+var_50]
0x180070f78  mov     ebx, eax
0x180070f7a  mov     rax, [rcx]
0x180070f7d  mov     rax, [rax+10h]
0x180070f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f86  inc     edi
0x180070f88  test    ebx, ebx
0x180070f8a  jns     short loc_180070F36
0x180070f8c  mov     rcx, [rbp+57h+var_68]
0x180070f90  mov     rax, [rcx]
0x180070f93  mov     rax, [rax+10h]
0x180070f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f9c  mov     rcx, [rbp+57h+var_48]
0x180070fa0  mov     rax, [rcx]
0x180070fa3  mov     rax, [rax+10h]
0x180070fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fac  jmp     short loc_180070FB8
0x180070fae  cmp     ebx, 80004001h
0x180070fb4  cmovz   ebx, r14d
0x180070fb8  mov     rcx, [rbp+57h+pszPath]
0x180070fbc  mov     rax, [rcx]
0x180070fbf  mov     rax, [rax+10h]
0x180070fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fc8  mov     rcx, [rbp+57h+var_40]
0x180070fcc  mov     rax, [rcx]
0x180070fcf  mov     rax, [rax+10h]
0x180070fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fd8  mov     rcx, [rbp+57h+pv]; pv
0x180070fdc  call    cs:__imp_CoTaskMemFree
0x180070fe2  mov     rcx, [rbp+57h+var_78]
0x180070fe6  mov     rax, [rcx]
0x180070fe9  mov     rax, [rax+10h]
0x180070fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ff2  test    ebx, ebx
0x180070ff4  jns     loc_180070D70
0x180070ffa  mov     rcx, [rbp+57h+var_38]
0x180070ffe  mov     rax, [rcx]
0x180071001  mov     rax, [rax+10h]
0x180071005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007100a  mov     eax, ebx
0x18007100c  mov     rcx, [rbp+57h+var_20]
0x180071010  xor     rcx, rsp; StackCookie
0x180071013  call    __security_check_cookie
0x180071018  lea     r11, [rsp+0B0h+var_10]
0x180071020  mov     rbx, [r11+30h]
0x180071024  mov     rsi, [r11+38h]
0x180071028  mov     rsp, r11
0x18007102b  pop     r14
0x18007102d  pop     rdi
0x18007102e  pop     rbp
0x18007102f  retn
```
