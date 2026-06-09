# CSharePagePerm::_OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x18006b930`
- end: `0x18006bb33`
- name: `?_OnCommand@CSharePagePerm@@AEAAXPEAUHWND__@@_K_J@Z`
- size: `515`
- prototype: `void __fastcall(CSharePagePerm *__hidden this, HWND hDlg, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006ce90`

## callees

- `0x18001c4a8`
- `0x1800254e0`
- `0x180053bb8`
- `0x18006b060`
- `0x18006b850`
- `0x18006b930`
- `0x18006c9c4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006baa8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006baa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ba07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ba07`
- `USER32!EnableWindow` at `0x18006b9fe`
- `USER32!EnableWindow` at `0x18006bb0b`
- `USER32!EnableWindow` at `0x18006b9fe`
- `USER32!EnableWindow` at `0x18006bb0b`
- `USER32!PostMessageW` at `0x18006bae2`
- `USER32!PostMessageW` at `0x18006bae2`
- `USER32!GetDlgItem` at `0x18006b9f3`
- `USER32!GetDlgItem` at `0x18006ba71`
- `USER32!GetDlgItem` at `0x18006bafd`
- `USER32!GetDlgItem` at `0x18006b9f3`
- `USER32!GetDlgItem` at `0x18006ba71`
- `USER32!GetDlgItem` at `0x18006bafd`
- `USER32!SendMessageW` at `0x18006ba2e`
- `USER32!SendMessageW` at `0x18006ba63`
- `USER32!SendMessageW` at `0x18006ba2e`
- `USER32!SendMessageW` at `0x18006ba63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSharePagePerm::_OnCommand(HWND *this, HWND hDlg, int a3, int a4)
{
  __int16 v4; // edi^2
  BOOL v7; // ebx
  void *v8; // rsi
  __int64 v9; // rdi
  HWND DlgItem; // rax
  int v11; // eax
  HWND v12; // rax
  BOOL v13; // edx
  LPVOID pv[2]; // [rsp+30h] [rbp-38h] BYREF

  v4 = HIWORD(a3);
  if ( (unsigned __int16)a3 != 4005 )
  {
    if ( (unsigned __int16)a3 == 4015 )
    {
      if ( (Microsoft_Windows_ntshruiEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          10,
          (unsigned int)Sharing_Add_User_To_Sharing_Permissions_Start,
          a3,
          a4,
          (__int64)pv);
      if ( !v4 )
        CSharePagePerm::_StartBackgroundNameResolution((CSharePagePerm *)this);
    }
    return;
  }
  if ( HIWORD(a3) == 5 )
  {
    v7 = 0;
    pv[0] = 0;
    if ( (int)CSharePagePerm::_GetUserNameComboText((CSharePagePerm *)this, (unsigned __int16 **)pv) >= 0 )
    {
      v8 = pv[0];
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)pv[0] + v9) );
      LOBYTE(v7) = v9 != 0;
      DlgItem = GetDlgItem(hDlg, 4015);
      EnableWindow(DlgItem, v7);
      CoTaskMemFree(v8);
    }
    return;
  }
  if ( HIWORD(a3) != 9 )
    return;
  v11 = SendMessageW(this[32], 0x147u, 0, 0);
  if ( v11 == -1 )
    return;
  if ( v11 == *((_DWORD *)this + 16) )
  {
    CSharePagePerm::_InvokeObjectPicker((CSharePagePerm *)this, this[1]);
    SendMessageW(this[32], 0x14Eu, 0xFFFFFFFFFFFFFFFFuLL, 0);
    v12 = GetDlgItem(hDlg, 4015);
    v13 = 0;
LABEL_22:
    EnableWindow(v12, v13);
    return;
  }
  if ( v11 != *((_DWORD *)this + 17) )
  {
    v12 = GetDlgItem(hDlg, 4015);
    v13 = 1;
    goto LABEL_22;
  }
  pv[0] = 0;
  if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 0x17u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, pv) >= 0
    && (*(int (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)pv[0] + 24LL))(
         pv[0],
         L"Microsoft.UserAccounts",
         0,
         0) >= 0 )
  {
    PostMessageW(hDlg, 0x471u, 5u, 0);
  }
  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(pv);
}

```

## disassembly

```asm
0x18006b930  mov     r11, rsp
0x18006b933  mov     [r11+18h], rbx
0x18006b937  mov     [r11+20h], rbp
0x18006b93b  push    rsi
0x18006b93c  push    rdi
0x18006b93d  push    r14
0x18006b93f  sub     rsp, 50h
0x18006b943  mov     rax, cs:__security_cookie
0x18006b94a  xor     rax, rsp
0x18006b94d  mov     [rsp+68h+var_28], rax
0x18006b952  mov     rdi, r8
0x18006b955  mov     rbp, rdx
0x18006b958  mov     rsi, rcx
0x18006b95b  movzx   ecx, r8w
0x18006b95f  sub     ecx, 0FA5h
0x18006b965  jz      short loc_18006B9A7
0x18006b967  cmp     ecx, 0Ah
0x18006b96a  jnz     loc_18006BB11
0x18006b970  test    byte ptr cs:Microsoft_Windows_ntshruiEnableBits, 1
0x18006b977  jz      short loc_18006B98D
0x18006b979  lea     rax, [r11-38h]
0x18006b97d  mov     [r11-48h], rax
0x18006b981  lea     rdx, Sharing_Add_User_To_Sharing_Permissions_Start
0x18006b988  call    McGenEventWrite_EtwEventWriteTransfer
0x18006b98d  shr     rdi, 10h
0x18006b991  test    di, di
0x18006b994  jnz     loc_18006BB11
0x18006b99a  mov     rcx, rsi; this
0x18006b99d  call    ?_StartBackgroundNameResolution@CSharePagePerm@@AEAAXXZ; CSharePagePerm::_StartBackgroundNameResolution(void)
0x18006b9a2  jmp     loc_18006BB11
0x18006b9a7  shr     rdi, 10h
0x18006b9ab  mov     r14d, 5
0x18006b9b1  cmp     di, r14w
0x18006b9b5  jnz     short loc_18006BA12
0x18006b9b7  xor     ebx, ebx
0x18006b9b9  mov     [rsp+68h+pv], rbx
0x18006b9be  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x18006b9c3  mov     rcx, rsi; this
0x18006b9c6  call    ?_GetUserNameComboText@CSharePagePerm@@AEAAJPEAPEAG@Z; CSharePagePerm::_GetUserNameComboText(ushort * *)
0x18006b9cb  test    eax, eax
0x18006b9cd  js      loc_18006BB11
0x18006b9d3  mov     rsi, [rsp+68h+pv]
0x18006b9d8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006b9dc  inc     rdi
0x18006b9df  cmp     [rsi+rdi*2], bx
0x18006b9e3  jnz     short loc_18006B9DC
0x18006b9e5  test    rdi, rdi
0x18006b9e8  setnz   bl
0x18006b9eb  mov     edx, 0FAFh; nIDDlgItem
0x18006b9f0  mov     rcx, rbp; hDlg
0x18006b9f3  call    cs:__imp_GetDlgItem
0x18006b9f9  mov     rcx, rax; hWnd
0x18006b9fc  mov     edx, ebx; bEnable
0x18006b9fe  call    cs:__imp_EnableWindow
0x18006ba04  mov     rcx, rsi; pv
0x18006ba07  call    cs:__imp_CoTaskMemFree
0x18006ba0d  jmp     loc_18006BB11
0x18006ba12  cmp     di, 9
0x18006ba16  jnz     loc_18006BB11
0x18006ba1c  xor     r9d, r9d; lParam
0x18006ba1f  xor     r8d, r8d; wParam
0x18006ba22  mov     edx, 147h; Msg
0x18006ba27  mov     rcx, [rsi+100h]; hWnd
0x18006ba2e  call    cs:__imp_SendMessageW
0x18006ba34  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006ba38  cmp     eax, edi
0x18006ba3a  jz      loc_18006BB11
0x18006ba40  cmp     eax, [rsi+40h]
0x18006ba43  jnz     short loc_18006BA7E
0x18006ba45  mov     rdx, [rsi+8]; HWND
0x18006ba49  mov     rcx, rsi; this
0x18006ba4c  call    ?_InvokeObjectPicker@CSharePagePerm@@AEAAJPEAUHWND__@@@Z; CSharePagePerm::_InvokeObjectPicker(HWND__ *)
0x18006ba51  xor     r9d, r9d; lParam
0x18006ba54  mov     r8, rdi; wParam
0x18006ba57  mov     edx, 14Eh; Msg
0x18006ba5c  mov     rcx, [rsi+100h]; hWnd
0x18006ba63  call    cs:__imp_SendMessageW
0x18006ba69  mov     edx, 0FAFh; nIDDlgItem
0x18006ba6e  mov     rcx, rbp; hDlg
0x18006ba71  call    cs:__imp_GetDlgItem
0x18006ba77  xor     edx, edx
0x18006ba79  jmp     loc_18006BB08
0x18006ba7e  cmp     eax, [rsi+44h]
0x18006ba81  jnz     short loc_18006BAF5
0x18006ba83  xor     ebx, ebx
0x18006ba85  mov     [rsp+68h+pv], rbx
0x18006ba8a  lea     rax, [rsp+68h+pv]
0x18006ba8f  mov     [rsp+68h+ppv], rax; ppv
0x18006ba94  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18006ba9b  xor     edx, edx; pUnkOuter
0x18006ba9d  lea     r8d, [rbx+17h]; dwClsContext
0x18006baa1  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18006baa8  call    cs:__imp_CoCreateInstance
0x18006baae  test    eax, eax
0x18006bab0  js      short loc_18006BAE9
0x18006bab2  mov     rcx, [rsp+68h+pv]
0x18006bab7  mov     rax, [rcx]
0x18006baba  xor     r9d, r9d
0x18006babd  xor     r8d, r8d
0x18006bac0  lea     rdx, aMicrosoftUsera; "Microsoft.UserAccounts"
0x18006bac7  mov     rax, [rax+18h]
0x18006bacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bad0  test    eax, eax
0x18006bad2  js      short loc_18006BAE9
0x18006bad4  xor     r9d, r9d; lParam
0x18006bad7  mov     r8, r14; wParam
0x18006bada  mov     edx, 471h; Msg
0x18006badf  mov     rcx, rbp; hWnd
0x18006bae2  call    cs:__imp_PostMessageW
0x18006bae8  nop
0x18006bae9  lea     rcx, [rsp+68h+pv]
0x18006baee  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18006baf3  jmp     short loc_18006BB11
0x18006baf5  mov     edx, 0FAFh; nIDDlgItem
0x18006bafa  mov     rcx, rbp; hDlg
0x18006bafd  call    cs:__imp_GetDlgItem
0x18006bb03  mov     edx, 1; bEnable
0x18006bb08  mov     rcx, rax; hWnd
0x18006bb0b  call    cs:__imp_EnableWindow
0x18006bb11  mov     rcx, [rsp+68h+var_28]
0x18006bb16  xor     rcx, rsp; StackCookie
0x18006bb19  call    __security_check_cookie
0x18006bb1e  lea     r11, [rsp+68h+var_18]
0x18006bb23  mov     rbx, [r11+30h]
0x18006bb27  mov     rbp, [r11+38h]
0x18006bb2b  mov     rsp, r11
0x18006bb2e  pop     r14
0x18006bb30  pop     rdi
0x18006bb31  pop     rsi
0x18006bb32  retn
```
