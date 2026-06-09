# CThreadInputMgr::IsInputServiceEnabledWindow(HWND__ *,bool *,bool *)

- ea: `0x180079a10`
- end: `0x180079bd9`
- name: `?IsInputServiceEnabledWindow@CThreadInputMgr@@SA_NPEAUHWND__@@PEA_N1@Z`
- size: `457`
- prototype: `bool __fastcall(HWND hWnd, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800297f0`

## callees

- `0x18002979c`
- `0x1800748d0`
- `0x180079a10`
- `0x18009c868`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180079ac1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180079ac1`
- `USER32!GetPropW` at `0x180079bc2`
- `USER32!GetPropW` at `0x180079bc2`
- `USER32!GetParent` at `0x180079afc`
- `USER32!GetParent` at `0x180079afc`
- `USER32!RealGetWindowClassW` at `0x180079a6f`
- `USER32!RealGetWindowClassW` at `0x180079b15`
- `USER32!RealGetWindowClassW` at `0x180079a6f`
- `USER32!RealGetWindowClassW` at `0x180079b15`

## string_xrefs

- `0x180079add`: `Windows.UI.Core.CoreComponentInputSource`

## pseudocode

```c
char __fastcall CThreadInputMgr::IsInputServiceEnabledWindow(HWND hWnd, bool *a2, bool *a3)
{
  char v3; // bl
  UINT WindowClassW; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 v11; // rcx
  HWND Parent; // rax
  _QWORD v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR ptszClassName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = 0;
  *a2 = 0;
  *a3 = 0;
  memset_0(ptszClassName, 0, 0x208u);
  WindowClassW = RealGetWindowClassW(hWnd, ptszClassName, 0x103u);
  v14[0] = ptszClassName;
  if ( WindowClassW - 1 <= 0x102 )
  {
    v11 = 2LL * WindowClassW;
    if ( v11 >= 0x208 )
      _report_rangecheckfailure(v11, v8, v9, v10);
    ptszClassName[WindowClassW] = 0;
    if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"Windows.UI.Core.CoreWindow", -1) != 2 )
    {
      if ( !IsInputServiceEnabledForCCI() )
        return v3;
      if ( (unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(
                              v14,
                              L"Windows.UI.Core.CoreComponentInputSource") )
      {
        *a2 = 1;
        Parent = GetParent(hWnd);
        if ( !Parent
          || RealGetWindowClassW(Parent, ptszClassName, 0x103u) - 1 > 0x102
          || !(unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(v14, L"Windows.UI.Core.CoreWindow")
          && !(unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(v14, L"TabWindowClass")
          && !(unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(v14, L"Windows.UI.Core.AppWindow")
          && !(unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(
                                 v14,
                                 L"Windows.UI.Input.InputSite.WindowClass") )
        {
          return v3;
        }
      }
      else if ( (unsigned __int8)lambda_219897664d39556ce9bc00a98142d62d_::operator()(
                                   v14,
                                   L"Windows.UI.Input.InputSite.WindowClass") )
      {
        *a2 = 1;
      }
      else
      {
        if ( !GetPropW(hWnd, L"TSFWin32EditControlWindow") )
          return v3;
        *a3 = 1;
      }
    }
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180079a10  mov     [rsp-8+arg_18], rbx
0x180079a15  push    rbp
0x180079a16  push    rsi
0x180079a17  push    rdi
0x180079a18  push    r14
0x180079a1a  push    r15
0x180079a1c  lea     rbp, [rsp-160h]
0x180079a24  sub     rsp, 260h
0x180079a2b  mov     rax, cs:__security_cookie
0x180079a32  xor     rax, rsp
0x180079a35  mov     [rbp+180h+var_30], rax
0x180079a3c  xor     bl, bl
0x180079a3e  mov     r14, r8
0x180079a41  mov     [rdx], bl
0x180079a43  mov     rdi, rdx
0x180079a46  mov     [r8], bl
0x180079a49  mov     rsi, rcx
0x180079a4c  mov     r15d, 208h
0x180079a52  lea     rcx, [rsp+280h+ptszClassName]; void *
0x180079a57  mov     r8d, r15d; Size
0x180079a5a  xor     edx, edx; Val
0x180079a5c  call    memset_0
0x180079a61  mov     r8d, 103h; cchClassNameMax
0x180079a67  lea     rdx, [rsp+280h+ptszClassName]; ptszClassName
0x180079a6c  mov     rcx, rsi; hwnd
0x180079a6f  call    cs:__imp_RealGetWindowClassW
0x180079a75  mov     ecx, eax
0x180079a77  lea     rax, [rsp+280h+ptszClassName]
0x180079a7c  mov     [rsp+280h+var_250], rax
0x180079a81  lea     eax, [rcx-1]
0x180079a84  cmp     eax, 102h
0x180079a89  ja      loc_180079B74
0x180079a8f  add     rcx, rcx
0x180079a92  cmp     rcx, r15
0x180079a95  jnb     loc_180079BD3
0x180079a9b  xor     eax, eax
0x180079a9d  lea     r15, aWindowsUiCoreC_0; "Windows.UI.Core.CoreWindow"
0x180079aa4  or      r9d, 0FFFFFFFFh; cchCount1
0x180079aa8  mov     [rsp+rcx+280h+ptszClassName], ax
0x180079aad  mov     [rsp+280h+cchCount2], r9d; cchCount2
0x180079ab2  lea     r8, [rsp+280h+ptszClassName]; lpString1
0x180079ab7  xor     edx, edx; dwCmpFlags
0x180079ab9  mov     [rsp+280h+lpString2], r15; lpString2
0x180079abe  lea     ecx, [rax+7Fh]; Locale
0x180079ac1  call    cs:__imp_CompareStringW
0x180079ac7  cmp     eax, 2
0x180079aca  jz      loc_180079BB4
0x180079ad0  call    ?IsInputServiceEnabledForCCI@@YA_NXZ; IsInputServiceEnabledForCCI(void)
0x180079ad5  test    al, al
0x180079ad7  jz      loc_180079B74
0x180079add  lea     rdx, aWindowsUiCoreC_1; "Windows.UI.Core.CoreComponentInputSourc"...
0x180079ae4  lea     rcx, [rsp+280h+var_250]
0x180079ae9  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079aee  test    al, al
0x180079af0  jz      loc_180079B9C
0x180079af6  mov     rcx, rsi; hWnd
0x180079af9  mov     byte ptr [rdi], 1
0x180079afc  call    cs:__imp_GetParent
0x180079b02  test    rax, rax
0x180079b05  jz      short loc_180079B74
0x180079b07  mov     r8d, 103h; cchClassNameMax
0x180079b0d  lea     rdx, [rsp+280h+ptszClassName]; ptszClassName
0x180079b12  mov     rcx, rax; hwnd
0x180079b15  call    cs:__imp_RealGetWindowClassW
0x180079b1b  dec     eax
0x180079b1d  cmp     eax, 102h
0x180079b22  ja      short loc_180079B74
0x180079b24  mov     rdx, r15
0x180079b27  lea     rcx, [rsp+280h+var_250]
0x180079b2c  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079b31  test    al, al
0x180079b33  jnz     short loc_180079BB4
0x180079b35  lea     rdx, aTabwindowclass; "TabWindowClass"
0x180079b3c  lea     rcx, [rsp+280h+var_250]
0x180079b41  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079b46  test    al, al
0x180079b48  jnz     short loc_180079BB4
0x180079b4a  lea     rdx, aWindowsUiCoreA; "Windows.UI.Core.AppWindow"
0x180079b51  lea     rcx, [rsp+280h+var_250]
0x180079b56  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079b5b  test    al, al
0x180079b5d  jnz     short loc_180079BB4
0x180079b5f  lea     rdx, aWindowsUiInput; "Windows.UI.Input.InputSite.WindowClass"
0x180079b66  lea     rcx, [rsp+280h+var_250]
0x180079b6b  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079b70  test    al, al
0x180079b72  jnz     short loc_180079BB4
0x180079b74  mov     al, bl
0x180079b76  mov     rcx, [rbp+180h+var_30]
0x180079b7d  xor     rcx, rsp; StackCookie
0x180079b80  call    __security_check_cookie
0x180079b85  mov     rbx, [rsp+280h+arg_18]
0x180079b8d  add     rsp, 260h
0x180079b94  pop     r15
0x180079b96  pop     r14
0x180079b98  pop     rdi
0x180079b99  pop     rsi
0x180079b9a  pop     rbp
0x180079b9b  retn
0x180079b9c  lea     rdx, aWindowsUiInput; "Windows.UI.Input.InputSite.WindowClass"
0x180079ba3  lea     rcx, [rsp+280h+var_250]
0x180079ba8  call    _lambda_219897664d39556ce9bc00a98142d62d___operator__
0x180079bad  test    al, al
0x180079baf  jz      short loc_180079BB8
0x180079bb1  mov     byte ptr [rdi], 1
0x180079bb4  mov     bl, 1
0x180079bb6  jmp     short loc_180079B74
0x180079bb8  lea     rdx, aTsfwin32editco; "TSFWin32EditControlWindow"
0x180079bbf  mov     rcx, rsi; hWnd
0x180079bc2  call    cs:__imp_GetPropW
0x180079bc8  test    rax, rax
0x180079bcb  jz      short loc_180079B74
0x180079bcd  mov     byte ptr [r14], 1
0x180079bd1  jmp     short loc_180079BB4
0x180079bd3  call    __report_rangecheckfailure
```
