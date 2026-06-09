# CControlPanelPage::Notify(ushort const *)

- ea: `0x1800162d0`
- end: `0x180016499`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006408`
- `0x1800162d0`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001637b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001637b`
- `SHELL32!SHParseDisplayName` at `0x1800163ef`
- `SHELL32!SHParseDisplayName` at `0x1800163ef`
- `SHELL32!__imp_ILFree` at `0x180016457`
- `SHELL32!__imp_ILFree` at `0x180016457`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800163a5`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800163a5`
- `SHLWAPI!__imp_StrCmpCW` at `0x180016316`
- `SHLWAPI!__imp_StrCmpCW` at `0x180016316`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016355`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016417`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016355`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016417`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001632b`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001632b`

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
0x1800162d0  mov     [rsp-8+arg_10], rbx
0x1800162d5  push    rbp
0x1800162d6  push    rsi
0x1800162d7  push    rdi
0x1800162d8  lea     rbp, [rsp-220h]
0x1800162e0  sub     rsp, 320h
0x1800162e7  mov     rax, cs:__security_cookie
0x1800162ee  xor     rax, rsp
0x1800162f1  mov     [rbp+230h+var_20], rax
0x1800162f8  xor     esi, esi
0x1800162fa  mov     rax, rdx
0x1800162fd  mov     rdi, rcx
0x180016300  cmp     [rcx-8], rsi
0x180016304  jz      loc_180016470
0x18001630a  lea     rdx, aSearchtext; "SearchText"
0x180016311  mov     rcx, rax; pszStr1
0x180016314  mov     ebx, esi
0x180016316  call    cs:__imp_StrCmpCW
0x18001631c  test    eax, eax
0x18001631e  jnz     loc_180016475
0x180016324  lea     rcx, POLID_NoControlPanel; "C"
0x18001632b  call    cs:__imp_SHWindowsPolicy
0x180016331  test    eax, eax
0x180016333  jnz     loc_180016475
0x180016339  mov     rcx, [rdi-8]; punk
0x18001633d  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x180016342  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180016349  mov     [rsp+330h+ppvOut], rsi
0x18001634e  lea     rdx, IID_IFrameManager; guidService
0x180016355  call    cs:__imp_IUnknown_QueryService
0x18001635b  mov     ebx, eax
0x18001635d  test    eax, eax
0x18001635f  js      loc_180016475
0x180016365  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18001636a  lea     r8, [rbp+230h+value]; value
0x18001636e  mov     r9d, 104h; characterCount
0x180016374  lea     rdx, aSearchtext; "SearchText"
0x18001637b  call    cs:__imp_PSPropertyBag_ReadStr
0x180016381  mov     ebx, eax
0x180016383  test    eax, eax
0x180016385  js      loc_18001645D
0x18001638b  cmp     [rbp+230h+value], si
0x18001638f  jz      loc_18001645D
0x180016395  lea     r8d, [rsi+27h]
0x180016399  lea     rdx, [rsp+330h+var_2E0]
0x18001639e  lea     rcx, CLSID_ControlPanelCategory
0x1800163a5  call    cs:__imp_SHStringFromGUIDW
0x1800163ab  mov     ebx, eax
0x1800163ad  test    eax, eax
0x1800163af  js      loc_18001645D
0x1800163b5  lea     r9, [rsp+330h+var_2E0]
0x1800163ba  lea     r8, aS_0; "::%s"
0x1800163c1  lea     edx, [rsi+29h]; unsigned __int64
0x1800163c4  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x1800163c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800163cd  mov     ebx, eax
0x1800163cf  test    eax, eax
0x1800163d1  js      loc_18001645D
0x1800163d7  xor     r9d, r9d; sfgaoIn
0x1800163da  mov     [rsp+330h+ppidl], rsi
0x1800163df  lea     r8, [rsp+330h+ppidl]; ppidl
0x1800163e4  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x1800163e9  xor     edx, edx; pbc
0x1800163eb  lea     rcx, [rbp+230h+pszName]; pszName
0x1800163ef  call    cs:__imp_SHParseDisplayName
0x1800163f5  mov     ebx, eax
0x1800163f7  test    eax, eax
0x1800163f9  js      short loc_18001645D
0x1800163fb  mov     rcx, [rdi-8]; punk
0x1800163ff  lea     r9, [rsp+330h+var_300]; ppvOut
0x180016404  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001640b  mov     [rsp+330h+var_300], rsi
0x180016410  lea     rdx, SID_STopLevelBrowser; guidService
0x180016417  call    cs:__imp_IUnknown_QueryService
0x18001641d  mov     ebx, eax
0x18001641f  test    eax, eax
0x180016421  js      short loc_180016452
0x180016423  mov     rcx, [rsp+330h+var_300]
0x180016428  mov     r8d, 180001h
0x18001642e  mov     rdx, [rsp+330h+ppidl]
0x180016433  mov     rax, [rcx]
0x180016436  mov     rax, [rax+58h]
0x18001643a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001643f  mov     rcx, [rsp+330h+var_300]
0x180016444  mov     ebx, eax
0x180016446  mov     rax, [rcx]
0x180016449  mov     rax, [rax+10h]
0x18001644d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016452  mov     rcx, [rsp+330h+ppidl]; pidl
0x180016457  call    cs:__imp_ILFree
0x18001645d  mov     rcx, [rsp+330h+ppvOut]
0x180016462  mov     rax, [rcx]
0x180016465  mov     rax, [rax+10h]
0x180016469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646e  jmp     short loc_180016475
0x180016470  mov     ebx, 80070057h
0x180016475  mov     eax, ebx
0x180016477  mov     rcx, [rbp+230h+var_20]
0x18001647e  xor     rcx, rsp; StackCookie
0x180016481  call    __security_check_cookie
0x180016486  mov     rbx, [rsp+330h+arg_10]
0x18001648e  add     rsp, 320h
0x180016495  pop     rdi
0x180016496  pop     rsi
0x180016497  pop     rbp
0x180016498  retn
```
