# CControlPanelPage::Notify(ushort const *)

- ea: `0x18002fd30`
- end: `0x18002fef9`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800102d0`

## callees

- `0x1800081bc`
- `0x18002fd30`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18002fd76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18002fd76`
- `SHCORE!IUnknown_QueryService` at `0x18002fdb5`
- `SHCORE!IUnknown_QueryService` at `0x18002fe77`
- `SHCORE!IUnknown_QueryService` at `0x18002fdb5`
- `SHCORE!IUnknown_QueryService` at `0x18002fe77`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18002fd8b`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18002fd8b`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002fe05`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002fe05`
- `SHELL32!SHParseDisplayName` at `0x18002fe4f`
- `SHELL32!SHParseDisplayName` at `0x18002fe4f`
- `SHELL32!__imp_ILFree` at `0x18002feb7`
- `SHELL32!__imp_ILFree` at `0x18002feb7`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002fddb`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002fddb`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::Notify(CControlPanelPage *this, const unsigned __int16 *a2)
{
  HRESULT Str; // ebx
  IUnknown *v4; // rcx
  IUnknown *v5; // rcx
  void *v7; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[48]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR value[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_QWORD *)this - 1) )
  {
    Str = 0;
    if ( !StrCmpCW(a2, L"SearchText") && !(unsigned int)SHWindowsPolicy(POLID_NoControlPanel) )
    {
      v4 = (IUnknown *)*((_QWORD *)this - 1);
      ppvOut = 0;
      Str = IUnknown_QueryService(v4, &IID_IFrameManager, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppvOut);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr((IPropertyBag *)ppvOut, L"SearchText", value, 260);
        if ( Str >= 0 )
        {
          if ( value[0] )
          {
            Str = SHStringFromGUIDW(&CLSID_ControlPanelCategory, v10, 39);
            if ( Str >= 0 )
            {
              Str = StringCchPrintfW(pszName, 0x29u, L"::%s", v10);
              if ( Str >= 0 )
              {
                ppidl = 0;
                Str = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
                if ( Str >= 0 )
                {
                  v5 = (IUnknown *)*((_QWORD *)this - 1);
                  v7 = 0;
                  Str = IUnknown_QueryService(
                          v5,
                          (const GUID *const)&SID_STopLevelBrowser,
                          &GUID_000214e2_0000_0000_c000_000000000046,
                          &v7);
                  if ( Str >= 0 )
                  {
                    Str = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)v7 + 88LL))(
                            v7,
                            ppidl,
                            1572865);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
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
0x18002fd30  mov     [rsp-8+arg_10], rbx
0x18002fd35  push    rbp
0x18002fd36  push    rsi
0x18002fd37  push    rdi
0x18002fd38  lea     rbp, [rsp-220h]
0x18002fd40  sub     rsp, 320h
0x18002fd47  mov     rax, cs:__security_cookie
0x18002fd4e  xor     rax, rsp
0x18002fd51  mov     [rbp+230h+var_20], rax
0x18002fd58  xor     esi, esi
0x18002fd5a  mov     rax, rdx
0x18002fd5d  mov     rdi, rcx
0x18002fd60  cmp     [rcx-8], rsi
0x18002fd64  jz      loc_18002FED0
0x18002fd6a  lea     rdx, aSearchtext; "SearchText"
0x18002fd71  mov     rcx, rax; pszStr1
0x18002fd74  mov     ebx, esi
0x18002fd76  call    cs:__imp_StrCmpCW
0x18002fd7c  test    eax, eax
0x18002fd7e  jnz     loc_18002FED5
0x18002fd84  lea     rcx, POLID_NoControlPanel
0x18002fd8b  call    cs:__imp_SHWindowsPolicy
0x18002fd91  test    eax, eax
0x18002fd93  jnz     loc_18002FED5
0x18002fd99  mov     rcx, [rdi-8]; punk
0x18002fd9d  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x18002fda2  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18002fda9  mov     [rsp+330h+ppvOut], rsi
0x18002fdae  lea     rdx, IID_IFrameManager; guidService
0x18002fdb5  call    cs:__imp_IUnknown_QueryService
0x18002fdbb  mov     ebx, eax
0x18002fdbd  test    eax, eax
0x18002fdbf  js      loc_18002FED5
0x18002fdc5  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18002fdca  lea     r8, [rbp+230h+value]; value
0x18002fdce  mov     r9d, 104h; characterCount
0x18002fdd4  lea     rdx, aSearchtext; "SearchText"
0x18002fddb  call    cs:__imp_PSPropertyBag_ReadStr
0x18002fde1  mov     ebx, eax
0x18002fde3  test    eax, eax
0x18002fde5  js      loc_18002FEBD
0x18002fdeb  cmp     [rbp+230h+value], si
0x18002fdef  jz      loc_18002FEBD
0x18002fdf5  lea     r8d, [rsi+27h]
0x18002fdf9  lea     rdx, [rsp+330h+var_2E0]
0x18002fdfe  lea     rcx, CLSID_ControlPanelCategory
0x18002fe05  call    cs:__imp_SHStringFromGUIDW
0x18002fe0b  mov     ebx, eax
0x18002fe0d  test    eax, eax
0x18002fe0f  js      loc_18002FEBD
0x18002fe15  lea     r9, [rsp+330h+var_2E0]
0x18002fe1a  lea     r8, aS; "::%s"
0x18002fe21  lea     edx, [rsi+29h]; unsigned __int64
0x18002fe24  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18002fe28  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fe2d  mov     ebx, eax
0x18002fe2f  test    eax, eax
0x18002fe31  js      loc_18002FEBD
0x18002fe37  xor     r9d, r9d; sfgaoIn
0x18002fe3a  mov     [rsp+330h+ppidl], rsi
0x18002fe3f  lea     r8, [rsp+330h+ppidl]; ppidl
0x18002fe44  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x18002fe49  xor     edx, edx; pbc
0x18002fe4b  lea     rcx, [rbp+230h+pszName]; pszName
0x18002fe4f  call    cs:__imp_SHParseDisplayName
0x18002fe55  mov     ebx, eax
0x18002fe57  test    eax, eax
0x18002fe59  js      short loc_18002FEBD
0x18002fe5b  mov     rcx, [rdi-8]; punk
0x18002fe5f  lea     r9, [rsp+330h+var_300]; ppvOut
0x18002fe64  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18002fe6b  mov     [rsp+330h+var_300], rsi
0x18002fe70  lea     rdx, SID_STopLevelBrowser; guidService
0x18002fe77  call    cs:__imp_IUnknown_QueryService
0x18002fe7d  mov     ebx, eax
0x18002fe7f  test    eax, eax
0x18002fe81  js      short loc_18002FEB2
0x18002fe83  mov     rcx, [rsp+330h+var_300]
0x18002fe88  mov     r8d, 180001h
0x18002fe8e  mov     rdx, [rsp+330h+ppidl]
0x18002fe93  mov     rax, [rcx]
0x18002fe96  mov     rax, [rax+58h]
0x18002fe9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe9f  mov     rcx, [rsp+330h+var_300]
0x18002fea4  mov     ebx, eax
0x18002fea6  mov     rax, [rcx]
0x18002fea9  mov     rax, [rax+10h]
0x18002fead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feb2  mov     rcx, [rsp+330h+ppidl]; pidl
0x18002feb7  call    cs:__imp_ILFree
0x18002febd  mov     rcx, [rsp+330h+ppvOut]
0x18002fec2  mov     rax, [rcx]
0x18002fec5  mov     rax, [rax+10h]
0x18002fec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fece  jmp     short loc_18002FED5
0x18002fed0  mov     ebx, 80070057h
0x18002fed5  mov     eax, ebx
0x18002fed7  mov     rcx, [rbp+230h+var_20]
0x18002fede  xor     rcx, rsp; StackCookie
0x18002fee1  call    __security_check_cookie
0x18002fee6  mov     rbx, [rsp+330h+arg_10]
0x18002feee  add     rsp, 320h
0x18002fef5  pop     rdi
0x18002fef6  pop     rsi
0x18002fef7  pop     rbp
0x18002fef8  retn
```
