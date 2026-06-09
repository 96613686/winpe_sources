# CControlPanelPage::Notify(ushort const *)

- ea: `0x18001cd68`
- end: `0x18001cf31`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014f80`

## callees

- `0x180002270`
- `0x180012458`
- `0x18001cd68`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001ce3d`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001ce3d`
- `SHLWAPI!__imp_StrCmpCW` at `0x18001cdae`
- `SHLWAPI!__imp_StrCmpCW` at `0x18001cdae`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cded`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001ceaf`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cded`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001ceaf`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001cdc3`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001cdc3`
- `SHELL32!SHParseDisplayName` at `0x18001ce87`
- `SHELL32!SHParseDisplayName` at `0x18001ce87`
- `SHELL32!__imp_ILFree` at `0x18001ceef`
- `SHELL32!__imp_ILFree` at `0x18001ceef`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001ce13`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001ce13`

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
0x18001cd68  mov     [rsp-8+arg_10], rbx
0x18001cd6d  push    rbp
0x18001cd6e  push    rsi
0x18001cd6f  push    rdi
0x18001cd70  lea     rbp, [rsp-220h]
0x18001cd78  sub     rsp, 320h
0x18001cd7f  mov     rax, cs:__security_cookie
0x18001cd86  xor     rax, rsp
0x18001cd89  mov     [rbp+230h+var_20], rax
0x18001cd90  xor     esi, esi
0x18001cd92  mov     rax, rdx
0x18001cd95  mov     rdi, rcx
0x18001cd98  cmp     [rcx-8], rsi
0x18001cd9c  jz      loc_18001CF08
0x18001cda2  lea     rdx, pszStr2; "SearchText"
0x18001cda9  mov     rcx, rax; pszStr1
0x18001cdac  mov     ebx, esi
0x18001cdae  call    cs:__imp_StrCmpCW
0x18001cdb4  test    eax, eax
0x18001cdb6  jnz     loc_18001CF0D
0x18001cdbc  lea     rcx, POLID_NoControlPanel; "C"
0x18001cdc3  call    cs:__imp_SHWindowsPolicy
0x18001cdc9  test    eax, eax
0x18001cdcb  jnz     loc_18001CF0D
0x18001cdd1  mov     rcx, [rdi-8]; punk
0x18001cdd5  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x18001cdda  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001cde1  mov     [rsp+330h+ppvOut], rsi
0x18001cde6  lea     rdx, IID_IFrameManager; guidService
0x18001cded  call    cs:__imp_IUnknown_QueryService
0x18001cdf3  mov     ebx, eax
0x18001cdf5  test    eax, eax
0x18001cdf7  js      loc_18001CF0D
0x18001cdfd  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18001ce02  lea     r8, [rbp+230h+value]; value
0x18001ce06  mov     r9d, 104h; characterCount
0x18001ce0c  lea     rdx, pszStr2; "SearchText"
0x18001ce13  call    cs:__imp_PSPropertyBag_ReadStr
0x18001ce19  mov     ebx, eax
0x18001ce1b  test    eax, eax
0x18001ce1d  js      loc_18001CEF5
0x18001ce23  cmp     [rbp+230h+value], si
0x18001ce27  jz      loc_18001CEF5
0x18001ce2d  lea     r8d, [rsi+27h]
0x18001ce31  lea     rdx, [rsp+330h+var_2E0]
0x18001ce36  lea     rcx, CLSID_ControlPanelCategory
0x18001ce3d  call    cs:__imp_SHStringFromGUIDW
0x18001ce43  mov     ebx, eax
0x18001ce45  test    eax, eax
0x18001ce47  js      loc_18001CEF5
0x18001ce4d  lea     r9, [rsp+330h+var_2E0]
0x18001ce52  lea     r8, aS_0; "::%s"
0x18001ce59  lea     edx, [rsi+29h]; unsigned __int64
0x18001ce5c  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18001ce60  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ce65  mov     ebx, eax
0x18001ce67  test    eax, eax
0x18001ce69  js      loc_18001CEF5
0x18001ce6f  xor     r9d, r9d; sfgaoIn
0x18001ce72  mov     [rsp+330h+ppidl], rsi
0x18001ce77  lea     r8, [rsp+330h+ppidl]; ppidl
0x18001ce7c  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x18001ce81  xor     edx, edx; pbc
0x18001ce83  lea     rcx, [rbp+230h+pszName]; pszName
0x18001ce87  call    cs:__imp_SHParseDisplayName
0x18001ce8d  mov     ebx, eax
0x18001ce8f  test    eax, eax
0x18001ce91  js      short loc_18001CEF5
0x18001ce93  mov     rcx, [rdi-8]; punk
0x18001ce97  lea     r9, [rsp+330h+var_300]; ppvOut
0x18001ce9c  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001cea3  mov     [rsp+330h+var_300], rsi
0x18001cea8  lea     rdx, SID_STopLevelBrowser; guidService
0x18001ceaf  call    cs:__imp_IUnknown_QueryService
0x18001ceb5  mov     ebx, eax
0x18001ceb7  test    eax, eax
0x18001ceb9  js      short loc_18001CEEA
0x18001cebb  mov     rcx, [rsp+330h+var_300]
0x18001cec0  mov     r8d, 180001h
0x18001cec6  mov     rdx, [rsp+330h+ppidl]
0x18001cecb  mov     rax, [rcx]
0x18001cece  mov     rax, [rax+58h]
0x18001ced2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced7  mov     rcx, [rsp+330h+var_300]
0x18001cedc  mov     ebx, eax
0x18001cede  mov     rax, [rcx]
0x18001cee1  mov     rax, [rax+10h]
0x18001cee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceea  mov     rcx, [rsp+330h+ppidl]; pidl
0x18001ceef  call    cs:__imp_ILFree
0x18001cef5  mov     rcx, [rsp+330h+ppvOut]
0x18001cefa  mov     rax, [rcx]
0x18001cefd  mov     rax, [rax+10h]
0x18001cf01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf06  jmp     short loc_18001CF0D
0x18001cf08  mov     ebx, 80070057h
0x18001cf0d  mov     eax, ebx
0x18001cf0f  mov     rcx, [rbp+230h+var_20]
0x18001cf16  xor     rcx, rsp; StackCookie
0x18001cf19  call    __security_check_cookie
0x18001cf1e  mov     rbx, [rsp+330h+arg_10]
0x18001cf26  add     rsp, 320h
0x18001cf2d  pop     rdi
0x18001cf2e  pop     rsi
0x18001cf2f  pop     rbp
0x18001cf30  retn
```
