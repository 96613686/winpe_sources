# CWindowPropStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x18009f820`
- end: `0x18009fa9c`
- name: `?SetValue@CWindowPropStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CWindowPropStore *__hidden this, PROPERTYKEY *pkey, PROPVARIANT *propvar)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004010`
- `0x180008814`
- `0x180024418`
- `0x18002d640`
- `0x180042330`
- `0x180054940`
- `0x18006ed20`
- `0x18009f820`
- `0x1800a111c`
- `0x1800a1a0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f869`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f856`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f856`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009f8d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009f92a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009f8d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009f92a`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18009f8fe`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18009f8fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18009f9a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18009fa47`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18009f9a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18009fa47`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18009f918`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18009f9e6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18009f918`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18009f9e6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18009f8b9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18009f8b9`

## string_xrefs

- `0x18009f9db`: `CopilotKeyProviderFastPathMessage`

## pseudocode

```c
__int64 __fastcall CWindowPropStore::SetValue(CWindowPropStore *this, PROPERTYKEY *pkey, PROPVARIANT *propvar)
{
  HRESULT v6; // esi
  int v7; // ebx
  HANDLE v8; // rax
  int v9; // ecx
  int v10; // r8d
  __int64 v11; // rbx
  ATOM v12; // ax
  WPARAM v13; // rbx
  HWND TaskBandWindow; // rax
  UINT v15; // edx
  __int64 *v16; // rdx
  WPARAM v17; // rbx
  HWND v18; // rax
  _BYTE v20[16]; // [rsp+30h] [rbp-2D8h] BYREF
  WCHAR psz[56]; // [rsp+40h] [rbp-2C8h] BYREF
  WCHAR String[264]; // [rsp+B0h] [rbp-258h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CDSA_Base<_tagpropertykey>::Destroy((char *)this + 56);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v6 = PSStringFromPropertyKey(pkey, psz, 0x32u);
  if ( v6 >= 0 )
  {
    v6 = PropVariantToString(propvar, String, 0x104u);
    if ( v6 >= 0 )
    {
      v7 = 0;
      v8 = RemovePropW(*((HWND *)this + 4), psz);
      if ( v8 != (HANDLE)4026531840LL && (_WORD)v8 )
      {
        v7 = 1;
        GlobalDeleteAtom((ATOM)v8);
      }
      v6 = 0;
      if ( *(_WORD *)propvar )
      {
        if ( *(_WORD *)propvar == 1 )
        {
          v11 = 4026531840LL;
        }
        else
        {
          v12 = GlobalAddAtomW(String);
          v11 = v12;
          if ( !v12 )
            return (unsigned int)ResultFromKnownLastError();
        }
        if ( !SetPropW(*((HWND *)this + 4), psz, (HANDLE)v11) )
        {
          if ( v11 != 4026531840LL )
            GlobalDeleteAtom(v11);
          return (unsigned int)ResultFromKnownLastError();
        }
        if ( *((_BYTE *)this + 104) && (unsigned int)operator==(pkey, &PKEY_AppUserModel_ID) && *(_WORD *)propvar != 1 )
        {
          v13 = *((_QWORD *)this + 4);
          TaskBandWindow = CWindowPropStore::_GetTaskBandWindow(this);
          v15 = 1099;
        }
        else
        {
          if ( !(unsigned int)operator==(pkey, &PKEY_EdgeGesture_DisableTouchWhenFullscreen) || *(_WORD *)propvar == 1 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55121036>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55121036>::GetImpl'::`2'::impl)
              && (unsigned int)operator==(pkey, PKEY_Shell_CopilotKeyProviderFastPathMessage)
              && *(_WORD *)propvar == 23 )
            {
              SetPropW(
                *((HWND *)this + 4),
                L"CopilotKeyProviderFastPathMessage",
                (HANDLE)*((unsigned int *)propvar + 2));
            }
            goto LABEL_26;
          }
          v13 = *((_QWORD *)this + 4);
          TaskBandWindow = CWindowPropStore::_GetTaskBandWindow(this);
          v15 = 1121;
        }
        PostMessageW(TaskBandWindow, v15, v13, 0);
LABEL_26:
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) == 0 )
          return (unsigned int)v6;
        v16 = Shell32_WindowPropStore_SetValue_Info;
LABEL_36:
        McGenEventWrite_EtwEventWriteTransfer(v9, (_DWORD)v16, v10, 1, (__int64)v20);
        return (unsigned int)v6;
      }
      if ( *((_BYTE *)this + 104)
        && pkey->pid == PKEY_AppUserModel_ID.pid
        && *(_QWORD *)&pkey->fmtid.Data1 == *(_QWORD *)&PKEY_AppUserModel_ID.fmtid.Data1
        && *(_QWORD *)pkey->fmtid.Data4 == *(_QWORD *)PKEY_AppUserModel_ID.fmtid.Data4
        && v7 )
      {
        v17 = *((_QWORD *)this + 4);
        v18 = CWindowPropStore::_GetTaskBandWindow(this);
        PostMessageW(v18, 0x44Bu, v17, 0);
      }
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      {
        v16 = Shell32_WindowPropStore_ValueRemoved_Info;
        goto LABEL_36;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009f820  mov     [rsp+arg_18], rbx
0x18009f825  push    rbp
0x18009f826  push    rsi
0x18009f827  push    rdi
0x18009f828  push    r12
0x18009f82a  push    r13
0x18009f82c  push    r14
0x18009f82e  push    r15
0x18009f830  sub     rsp, 2D0h
0x18009f837  mov     rax, cs:__security_cookie
0x18009f83e  xor     rax, rsp
0x18009f841  mov     [rsp+308h+var_48], rax
0x18009f849  mov     rdi, rcx
0x18009f84c  mov     r14, r8
0x18009f84f  add     rcx, 40h ; '@'; lpCriticalSection
0x18009f853  mov     r15, rdx
0x18009f856  call    cs:__imp_EnterCriticalSection
0x18009f85c  lea     rcx, [rdi+38h]
0x18009f860  call    ?Destroy@?$CDSA_Base@U_tagpropertykey@@@@QEAAHXZ; CDSA_Base<_tagpropertykey>::Destroy(void)
0x18009f865  lea     rcx, [rdi+40h]; lpCriticalSection
0x18009f869  call    cs:__imp_LeaveCriticalSection
0x18009f86f  mov     r8d, 32h ; '2'; cch
0x18009f875  lea     rdx, [rsp+308h+psz]; psz
0x18009f87a  mov     rcx, r15; pkey
0x18009f87d  call    PSStringFromPropertyKey
0x18009f882  xor     ebp, ebp
0x18009f884  mov     esi, eax
0x18009f886  test    eax, eax
0x18009f888  js      loc_18009FA6F
0x18009f88e  mov     r8d, 104h; cch
0x18009f894  lea     rdx, [rsp+308h+String]; psz
0x18009f89c  mov     rcx, r14; propvar
0x18009f89f  call    PropVariantToString
0x18009f8a4  mov     esi, eax
0x18009f8a6  test    eax, eax
0x18009f8a8  js      loc_18009FA6F
0x18009f8ae  mov     rcx, [rdi+20h]; hWnd
0x18009f8b2  lea     rdx, [rsp+308h+psz]; lpString
0x18009f8b7  mov     ebx, ebp
0x18009f8b9  call    cs:__imp_RemovePropW
0x18009f8bf  mov     r13d, 0F0000000h
0x18009f8c5  lea     r12d, [rbp+1]
0x18009f8c9  cmp     rax, r13
0x18009f8cc  jz      short loc_18009F8DF
0x18009f8ce  test    ax, ax
0x18009f8d1  jz      short loc_18009F8DF
0x18009f8d3  movzx   ecx, ax; nAtom
0x18009f8d6  mov     ebx, r12d
0x18009f8d9  call    cs:__imp_GlobalDeleteAtom
0x18009f8df  mov     esi, ebp
0x18009f8e1  cmp     [r14], bp
0x18009f8e5  jz      loc_18009F9FE
0x18009f8eb  cmp     [r14], r12w
0x18009f8ef  jnz     short loc_18009F8F6
0x18009f8f1  mov     rbx, r13
0x18009f8f4  jmp     short loc_18009F90C
0x18009f8f6  lea     rcx, [rsp+308h+String]; lpString
0x18009f8fe  call    cs:__imp_GlobalAddAtomW
0x18009f904  movzx   ebx, ax
0x18009f907  test    rbx, rbx
0x18009f90a  jz      short loc_18009F930
0x18009f90c  mov     rcx, [rdi+20h]; hWnd
0x18009f910  lea     rdx, [rsp+308h+psz]; lpString
0x18009f915  mov     r8, rbx; hData
0x18009f918  call    cs:__imp_SetPropW
0x18009f91e  test    eax, eax
0x18009f920  jnz     short loc_18009F93C
0x18009f922  cmp     rbx, r13
0x18009f925  jz      short loc_18009F930
0x18009f927  movzx   ecx, bx; nAtom
0x18009f92a  call    cs:__imp_GlobalDeleteAtom
0x18009f930  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009f935  mov     esi, eax
0x18009f937  jmp     loc_18009FA6F
0x18009f93c  cmp     [rdi+68h], bpl
0x18009f940  jz      short loc_18009F96E
0x18009f942  lea     rdx, PKEY_AppUserModel_ID
0x18009f949  mov     rcx, r15
0x18009f94c  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18009f951  test    eax, eax
0x18009f953  jz      short loc_18009F96E
0x18009f955  cmp     r12w, [r14]
0x18009f959  jz      short loc_18009F96E
0x18009f95b  mov     rbx, [rdi+20h]
0x18009f95f  mov     rcx, rdi; this
0x18009f962  call    ?_GetTaskBandWindow@CWindowPropStore@@AEAAPEAUHWND__@@XZ; CWindowPropStore::_GetTaskBandWindow(void)
0x18009f967  mov     edx, 44Bh
0x18009f96c  jmp     short loc_18009F998
0x18009f96e  lea     rdx, PKEY_EdgeGesture_DisableTouchWhenFullscreen
0x18009f975  mov     rcx, r15
0x18009f978  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18009f97d  test    eax, eax
0x18009f97f  jz      short loc_18009F9A9
0x18009f981  cmp     r12w, [r14]
0x18009f985  jz      short loc_18009F9A9
0x18009f987  mov     rbx, [rdi+20h]
0x18009f98b  mov     rcx, rdi; this
0x18009f98e  call    ?_GetTaskBandWindow@CWindowPropStore@@AEAAPEAUHWND__@@XZ; CWindowPropStore::_GetTaskBandWindow(void)
0x18009f993  mov     edx, 461h; Msg
0x18009f998  mov     r8, rbx; wParam
0x18009f99b  xor     r9d, r9d; lParam
0x18009f99e  mov     rcx, rax; hWnd
0x18009f9a1  call    cs:__imp_PostMessageW
0x18009f9a7  jmp     short loc_18009F9EC
0x18009f9a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55121036@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55121036@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55121036> `wil::Feature<__WilFeatureTraits_Feature_55121036>::GetImpl(void)'::`2'::impl
0x18009f9b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55121036@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55121036>::__private_IsEnabled(void)
0x18009f9b5  test    al, al
0x18009f9b7  jz      short loc_18009F9EC
0x18009f9b9  lea     rdx, PKEY_Shell_CopilotKeyProviderFastPathMessage
0x18009f9c0  mov     rcx, r15
0x18009f9c3  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18009f9c8  test    eax, eax
0x18009f9ca  jz      short loc_18009F9EC
0x18009f9cc  mov     eax, 17h
0x18009f9d1  cmp     ax, [r14]
0x18009f9d5  jnz     short loc_18009F9EC
0x18009f9d7  mov     r8d, [r14+8]; hData
0x18009f9db  lea     rdx, aCopilotkeyprov; "CopilotKeyProviderFastPathMessage"
0x18009f9e2  mov     rcx, [rdi+20h]; hWnd
0x18009f9e6  call    cs:__imp_SetPropW
0x18009f9ec  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x18009f9f3  jz      short loc_18009FA6F
0x18009f9f5  lea     rdx, Shell32_WindowPropStore_SetValue_Info
0x18009f9fc  jmp     short loc_18009FA5D
0x18009f9fe  cmp     [rdi+68h], bpl
0x18009fa02  jz      short loc_18009FA4D
0x18009fa04  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x18009fa0a  cmp     [r15+10h], eax
0x18009fa0e  jnz     short loc_18009FA4D
0x18009fa10  mov     rax, [r15]
0x18009fa13  cmp     rax, qword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x18009fa1a  jnz     short loc_18009FA4D
0x18009fa1c  mov     rax, [r15+8]
0x18009fa20  cmp     rax, qword ptr cs:PKEY_AppUserModel_ID.fmtid.Data4
0x18009fa27  jnz     short loc_18009FA4D
0x18009fa29  test    ebx, ebx
0x18009fa2b  jz      short loc_18009FA4D
0x18009fa2d  mov     rbx, [rdi+20h]
0x18009fa31  mov     rcx, rdi; this
0x18009fa34  call    ?_GetTaskBandWindow@CWindowPropStore@@AEAAPEAUHWND__@@XZ; CWindowPropStore::_GetTaskBandWindow(void)
0x18009fa39  xor     r9d, r9d; lParam
0x18009fa3c  mov     r8, rbx; wParam
0x18009fa3f  mov     edx, 44Bh; Msg
0x18009fa44  mov     rcx, rax; hWnd
0x18009fa47  call    cs:__imp_PostMessageW
0x18009fa4d  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x18009fa54  jz      short loc_18009FA6F
0x18009fa56  lea     rdx, Shell32_WindowPropStore_ValueRemoved_Info
0x18009fa5d  lea     rax, [rsp+308h+var_2D8]
0x18009fa62  mov     r9d, r12d
0x18009fa65  mov     [rsp+308h+var_2E8], rax
0x18009fa6a  call    McGenEventWrite_EtwEventWriteTransfer
0x18009fa6f  mov     eax, esi
0x18009fa71  mov     rcx, [rsp+308h+var_48]
0x18009fa79  xor     rcx, rsp; StackCookie
0x18009fa7c  call    __security_check_cookie
0x18009fa81  mov     rbx, [rsp+308h+arg_18]
0x18009fa89  add     rsp, 2D0h
0x18009fa90  pop     r15
0x18009fa92  pop     r14
0x18009fa94  pop     r13
0x18009fa96  pop     r12
0x18009fa98  pop     rdi
0x18009fa99  pop     rsi
0x18009fa9a  pop     rbp
0x18009fa9b  retn
```
