# CControlPanelPage::Notify(ushort const *)

- ea: `0x18002ecb0`
- end: `0x18002ee79`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180020690`

## callees

- `0x180006668`
- `0x18002ecb0`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002ed5b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002ed5b`
- `SHELL32!SHParseDisplayName` at `0x18002edcf`
- `SHELL32!SHParseDisplayName` at `0x18002edcf`
- `SHELL32!__imp_ILFree` at `0x18002ee37`
- `SHELL32!__imp_ILFree` at `0x18002ee37`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002ed85`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002ed85`
- `SHLWAPI!__imp_StrCmpCW` at `0x18002ecf6`
- `SHLWAPI!__imp_StrCmpCW` at `0x18002ecf6`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ed35`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002edf7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ed35`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002edf7`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18002ed0b`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18002ed0b`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::Notify(CControlPanelPage *this, const unsigned __int16 *a2)
{
  HRESULT Str; // ebx
  const CHAR *v4; // rdx
  IUnknown *v5; // rcx
  IUnknown *v6; // rcx
  void *v8; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[48]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR value[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_QWORD *)this - 1) )
  {
    Str = 0;
    if ( !StrCmpCW(a2, L"SearchText") && !SHWindowsPolicy(POLID_NoControlPanel, v4) )
    {
      v5 = (IUnknown *)*((_QWORD *)this - 1);
      ppvOut = 0;
      Str = IUnknown_QueryService(v5, &IID_IFrameManager, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppvOut);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr((IPropertyBag *)ppvOut, L"SearchText", value, 260);
        if ( Str >= 0 )
        {
          if ( value[0] )
          {
            Str = SHStringFromGUIDW(&CLSID_ControlPanelCategory, v11, 39);
            if ( Str >= 0 )
            {
              Str = StringCchPrintfW(pszName, 0x29u, L"::%s", v11);
              if ( Str >= 0 )
              {
                ppidl = 0;
                Str = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
                if ( Str >= 0 )
                {
                  v6 = (IUnknown *)*((_QWORD *)this - 1);
                  v8 = 0;
                  Str = IUnknown_QueryService(
                          v6,
                          (const GUID *const)&SID_STopLevelBrowser,
                          &GUID_000214e2_0000_0000_c000_000000000046,
                          &v8);
                  if ( Str >= 0 )
                  {
                    Str = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)v8 + 88LL))(
                            v8,
                            ppidl,
                            1572865);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
                  }
                  ILFree(ppidl);
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x18002ecb0  mov     [rsp-8+arg_10], rbx
0x18002ecb5  push    rbp
0x18002ecb6  push    rsi
0x18002ecb7  push    rdi
0x18002ecb8  lea     rbp, [rsp-220h]
0x18002ecc0  sub     rsp, 320h
0x18002ecc7  mov     rax, cs:__security_cookie
0x18002ecce  xor     rax, rsp
0x18002ecd1  mov     [rbp+230h+var_20], rax
0x18002ecd8  xor     esi, esi
0x18002ecda  mov     rax, rdx
0x18002ecdd  mov     rdi, rcx
0x18002ece0  cmp     [rcx-8], rsi
0x18002ece4  jz      loc_18002EE50
0x18002ecea  lea     rdx, aSearchtext; "SearchText"
0x18002ecf1  mov     rcx, rax; pszStr1
0x18002ecf4  mov     ebx, esi
0x18002ecf6  call    cs:__imp_StrCmpCW
0x18002ecfc  test    eax, eax
0x18002ecfe  jnz     loc_18002EE55
0x18002ed04  lea     rcx, POLID_NoControlPanel; "C"
0x18002ed0b  call    cs:__imp_SHWindowsPolicy
0x18002ed11  test    eax, eax
0x18002ed13  jnz     loc_18002EE55
0x18002ed19  mov     rcx, [rdi-8]; punk
0x18002ed1d  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x18002ed22  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18002ed29  mov     [rsp+330h+ppvOut], rsi
0x18002ed2e  lea     rdx, IID_IFrameManager; guidService
0x18002ed35  call    cs:__imp_IUnknown_QueryService
0x18002ed3b  mov     ebx, eax
0x18002ed3d  test    eax, eax
0x18002ed3f  js      loc_18002EE55
0x18002ed45  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18002ed4a  lea     r8, [rbp+230h+value]; value
0x18002ed4e  mov     r9d, 104h; characterCount
0x18002ed54  lea     rdx, aSearchtext; "SearchText"
0x18002ed5b  call    cs:__imp_PSPropertyBag_ReadStr
0x18002ed61  mov     ebx, eax
0x18002ed63  test    eax, eax
0x18002ed65  js      loc_18002EE3D
0x18002ed6b  cmp     [rbp+230h+value], si
0x18002ed6f  jz      loc_18002EE3D
0x18002ed75  lea     r8d, [rsi+27h]
0x18002ed79  lea     rdx, [rsp+330h+var_2E0]
0x18002ed7e  lea     rcx, CLSID_ControlPanelCategory
0x18002ed85  call    cs:__imp_SHStringFromGUIDW
0x18002ed8b  mov     ebx, eax
0x18002ed8d  test    eax, eax
0x18002ed8f  js      loc_18002EE3D
0x18002ed95  lea     r9, [rsp+330h+var_2E0]
0x18002ed9a  lea     r8, aS; "::%s"
0x18002eda1  lea     edx, [rsi+29h]; unsigned __int64
0x18002eda4  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18002eda8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002edad  mov     ebx, eax
0x18002edaf  test    eax, eax
0x18002edb1  js      loc_18002EE3D
0x18002edb7  xor     r9d, r9d; sfgaoIn
0x18002edba  mov     [rsp+330h+ppidl], rsi
0x18002edbf  lea     r8, [rsp+330h+ppidl]; ppidl
0x18002edc4  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x18002edc9  xor     edx, edx; pbc
0x18002edcb  lea     rcx, [rbp+230h+pszName]; pszName
0x18002edcf  call    cs:__imp_SHParseDisplayName
0x18002edd5  mov     ebx, eax
0x18002edd7  test    eax, eax
0x18002edd9  js      short loc_18002EE3D
0x18002eddb  mov     rcx, [rdi-8]; punk
0x18002eddf  lea     r9, [rsp+330h+var_300]; ppvOut
0x18002ede4  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18002edeb  mov     [rsp+330h+var_300], rsi
0x18002edf0  lea     rdx, SID_STopLevelBrowser; guidService
0x18002edf7  call    cs:__imp_IUnknown_QueryService
0x18002edfd  mov     ebx, eax
0x18002edff  test    eax, eax
0x18002ee01  js      short loc_18002EE32
0x18002ee03  mov     rcx, [rsp+330h+var_300]
0x18002ee08  mov     r8d, 180001h
0x18002ee0e  mov     rdx, [rsp+330h+ppidl]
0x18002ee13  mov     rax, [rcx]
0x18002ee16  mov     rax, [rax+58h]
0x18002ee1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee1f  mov     rcx, [rsp+330h+var_300]
0x18002ee24  mov     ebx, eax
0x18002ee26  mov     rax, [rcx]
0x18002ee29  mov     rax, [rax+10h]
0x18002ee2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee32  mov     rcx, [rsp+330h+ppidl]; pidl
0x18002ee37  call    cs:__imp_ILFree
0x18002ee3d  mov     rcx, [rsp+330h+ppvOut]
0x18002ee42  mov     rax, [rcx]
0x18002ee45  mov     rax, [rax+10h]
0x18002ee49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee4e  jmp     short loc_18002EE55
0x18002ee50  mov     ebx, 80070057h
0x18002ee55  mov     eax, ebx
0x18002ee57  mov     rcx, [rbp+230h+var_20]
0x18002ee5e  xor     rcx, rsp; StackCookie
0x18002ee61  call    __security_check_cookie
0x18002ee66  mov     rbx, [rsp+330h+arg_10]
0x18002ee6e  add     rsp, 320h
0x18002ee75  pop     rdi
0x18002ee76  pop     rsi
0x18002ee77  pop     rbp
0x18002ee78  retn
```
