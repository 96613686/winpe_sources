# CComponentData::_OpenDlgHookProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180007f70`
- end: `0x180008396`
- name: `?_OpenDlgHookProc@CComponentData@@CA_KPEAUHWND__@@I_K_J@Z`
- size: `1062`
- prototype: `unsigned __int64 __fastcall(HWND, unsigned int, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180001910`
- `0x180001dd0`
- `0x18000513c`
- `0x18000536c`
- `0x180007724`
- `0x180007f70`
- `0x18000839c`
- `0x180008728`
- `0x18001f278`
- `0x18001f858`
- `0x1800203e0`
- `0x180020430`
- `0x180020580`
- `0x180020ee0`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000810a`
- `USER32!SendMessageW` at `0x18000812c`
- `USER32!SendMessageW` at `0x18000827f`
- `USER32!SendMessageW` at `0x180008305`
- `USER32!SendMessageW` at `0x18000810a`
- `USER32!SendMessageW` at `0x18000812c`
- `USER32!SendMessageW` at `0x18000827f`
- `USER32!SendMessageW` at `0x180008305`
- `USER32!GetDlgItem` at `0x18000800c`
- `USER32!GetDlgItem` at `0x1800080a2`
- `USER32!GetDlgItem` at `0x1800080f5`
- `USER32!GetDlgItem` at `0x180008118`
- `USER32!GetDlgItem` at `0x180008197`
- `USER32!GetDlgItem` at `0x1800081d3`
- `USER32!GetDlgItem` at `0x18000821a`
- `USER32!GetDlgItem` at `0x180008268`
- `USER32!GetDlgItem` at `0x1800082c7`
- `USER32!GetDlgItem` at `0x180008365`
- `USER32!GetDlgItem` at `0x18000800c`
- `USER32!GetDlgItem` at `0x1800080a2`
- `USER32!GetDlgItem` at `0x1800080f5`
- `USER32!GetDlgItem` at `0x180008118`
- `USER32!GetDlgItem` at `0x180008197`
- `USER32!GetDlgItem` at `0x1800081d3`
- `USER32!GetDlgItem` at `0x18000821a`
- `USER32!GetDlgItem` at `0x180008268`
- `USER32!GetDlgItem` at `0x1800082c7`
- `USER32!GetDlgItem` at `0x180008365`
- `USER32!SetWindowPos` at `0x1800081be`
- `USER32!SetWindowPos` at `0x180008239`
- `USER32!SetWindowPos` at `0x180008258`
- `USER32!SetWindowPos` at `0x1800081be`
- `USER32!SetWindowPos` at `0x180008239`
- `USER32!SetWindowPos` at `0x180008258`
- `USER32!GetParent` at `0x180008185`
- `USER32!GetParent` at `0x1800081c7`
- `USER32!GetParent` at `0x1800081df`
- `USER32!GetParent` at `0x18000820e`
- `USER32!GetParent` at `0x180008185`
- `USER32!GetParent` at `0x1800081c7`
- `USER32!GetParent` at `0x1800081df`
- `USER32!GetParent` at `0x18000820e`
- `USER32!FindWindowExW` at `0x1800081f9`
- `USER32!FindWindowExW` at `0x1800081f9`
- `USER32!SetWindowLongPtrW` at `0x1800082aa`
- `USER32!SetWindowLongPtrW` at `0x1800082aa`
- `USER32!GetWindowTextW` at `0x180008022`
- `USER32!GetWindowTextW` at `0x1800082d9`
- `USER32!GetWindowTextW` at `0x180008022`
- `USER32!GetWindowTextW` at `0x1800082d9`
- `USER32!SetWindowTextW` at `0x1800080ae`
- `USER32!SetWindowTextW` at `0x1800080ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall CComponentData::_OpenDlgHookProc(HWND a1, __int64 a2, size_t *a3, __int64 a4)
{
  HWND v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdx
  const WCHAR *v10; // rbx
  HWND v11; // rax
  __int64 v12; // rdx
  HWND v13; // rax
  HWND v14; // rax
  int v15; // eax
  HWND Parent; // rax
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rbx
  HWND v20; // rax
  HWND Window; // rbx
  HWND v22; // rax
  HWND v23; // rax
  HWND v24; // r15
  int v25; // r12d
  HWND v26; // rcx
  UINT v27; // edx
  __int64 v29; // r14
  HWND v30; // rax
  LRESULT v31; // rax
  _DWORD *v32; // rsi
  _QWORD *v33; // rbx
  _QWORD *v34; // rcx
  unsigned __int16 v35; // r8
  HWND DlgItem; // rax
  LPCWSTR lpString[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t lParam[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String[264]; // [rsp+290h] [rbp+190h] BYREF

  switch ( (_DWORD)a2 )
  {
    case 2:
      DlgItem = GetDlgItem(a1, 101);
      _ResetOpenSavedLogTypeCombo(DlgItem);
      return 0;
    case 0x4E:
      v15 = *(_DWORD *)(a4 + 16);
      if ( v15 == -606 )
      {
        v24 = GetDlgItem(a1, 101);
        v25 = SendMessageW(v24, 0x147u, 0, 0);
        v26 = a1;
        if ( v25 )
        {
          v29 = *(_QWORD *)(*(_QWORD *)(a4 + 24) + 112LL);
          v30 = GetDlgItem(a1, 102);
          GetWindowTextW(v30, (LPWSTR)v29, 260);
          StripLeadTrailSpace((unsigned __int16 *)v29);
          if ( *(_WORD *)v29 )
          {
            v31 = SendMessageW(v24, 0x150u, v25, 0);
            v32 = (_DWORD *)v31;
            v33 = (_QWORD *)(v31 + 8);
            if ( *(_QWORD *)(v31 + 32) < 8u )
              v34 = (_QWORD *)(v31 + 8);
            else
              v34 = (_QWORD *)*v33;
            *(_DWORD *)(v29 + 1076) = DetermineLogType(v34);
            if ( v33[3] >= 8u )
              v33 = (_QWORD *)*v33;
            std::wstring::assign(v29 + 520, v33);
            *(_DWORD *)(v29 + 1072) = *v32;
            _GetOpenSavedServer(a1, (unsigned __int16 *)(v29 + 552), v35);
            return 0;
          }
          v27 = 330;
          v26 = a1;
        }
        else
        {
          v27 = 264;
        }
        MsgBox(v26, v27, 0x10u);
        SetWindowLongPtrW(a1, 0, 1);
        return 1;
      }
      if ( v15 != -603 && v15 != -602 )
      {
        if ( v15 == -601 )
        {
          Parent = GetParent(a1);
          v17 = GetDlgItem(Parent, 1136);
          SetWindowPos(a1, v17, 0, 0, 0, 0, 0x13u);
          v18 = GetParent(a1);
          v19 = GetDlgItem(v18, 1136);
          v20 = GetParent(a1);
          Window = FindWindowExW(v20, v19, L"ToolbarWindow32", &::String);
          if ( Window )
          {
            v22 = GetParent(a1);
            v23 = GetDlgItem(v22, 1136);
            SetWindowPos(Window, v23, 0, 0, 0, 0, 0x13u);
            SetWindowPos(a1, Window, 0, 0, 0, 0, 0x13u);
          }
        }
        return 0;
      }
LABEL_15:
      _PopulateOpenSavedLogTypeCombo(a1, a2, a3);
      return 0;
    case 0x53:
    case 0x7B:
      InvokeWinHelp(a2, (unsigned __int64)a3, a4, (const unsigned __int16 *)a3, (ULONG_PTR)&dwData);
      return 0;
    case 0x110:
      LoadStr(0x102u, lParam, 0x104u, (wchar_t *)L"(Unspecified)");
      v13 = GetDlgItem(a1, 101);
      SendMessageW(v13, 0x143u, 0, (LPARAM)lParam);
      v14 = GetDlgItem(a1, 101);
      SendMessageW(v14, 0x14Eu, 0, 0);
      return 0;
    case 0x111:
      if ( WORD1(a3) != 3 )
      {
        if ( WORD1(a3) == 9 )
        {
          _GetOpenSavedServer(a1, lParam, (unsigned __int16)a3);
          v6 = GetDlgItem(a1, 101);
          GetWindowTextW(v6, String, 260);
          StripLeadTrailSpace(String);
          std::wstring::wstring(lpString);
          if ( lParam[0] )
            v8 = FormatString(v38, 271, String, lParam);
          else
            v8 = FormatString(v38, 272, String, v7);
          std::wstring::operator=(lpString, v8);
          LOBYTE(v9) = 1;
          std::wstring::_Tidy(v38, v9, 0);
          v10 = (const WCHAR *)lpString;
          if ( lpString[3] >= (LPCWSTR)8 )
            v10 = lpString[0];
          v11 = GetDlgItem(a1, 102);
          SetWindowTextW(v11, v10);
          LOBYTE(v12) = 1;
          std::wstring::_Tidy(lpString, v12, 0);
        }
        return 0;
      }
      goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x180007f70  push    rbp
0x180007f72  push    rbx
0x180007f73  push    rsi
0x180007f74  push    rdi
0x180007f75  push    r12
0x180007f77  push    r14
0x180007f79  push    r15
0x180007f7b  lea     rbp, [rsp-3B0h]
0x180007f83  sub     rsp, 4B0h
0x180007f8a  mov     rax, cs:__security_cookie
0x180007f91  xor     rax, rsp
0x180007f94  mov     [rbp+3E0h+var_40], rax
0x180007f9b  mov     rbx, r9
0x180007f9e  mov     r9, r8; unsigned __int16 *
0x180007fa1  mov     r10d, edx
0x180007fa4  mov     rdi, rcx
0x180007fa7  mov     eax, edx
0x180007fa9  sub     eax, 2
0x180007fac  jz      loc_180008360
0x180007fb2  sub     eax, 4Ch ; 'L'
0x180007fb5  jz      loc_180008156
0x180007fbb  sub     eax, 5
0x180007fbe  jz      loc_180008137
0x180007fc4  sub     eax, 28h ; '('
0x180007fc7  jz      loc_180008137
0x180007fcd  sub     eax, 95h
0x180007fd2  jz      loc_1800080D3
0x180007fd8  cmp     eax, 1
0x180007fdb  jnz     loc_180008373
0x180007fe1  shr     r9, 10h
0x180007fe5  cmp     r9w, 3
0x180007fea  jz      loc_1800080C9
0x180007ff0  cmp     r9w, 9
0x180007ff5  jnz     loc_180008373
0x180007ffb  lea     rdx, [rbp+3E0h+lParam]; unsigned __int16 *
0x180007fff  call    ?_GetOpenSavedServer@@YAXPEAUHWND__@@PEAGG@Z; _GetOpenSavedServer(HWND__ *,ushort *,ushort)
0x180008004  mov     edx, 65h ; 'e'; nIDDlgItem
0x180008009  mov     rcx, rdi; hDlg
0x18000800c  call    cs:__imp_GetDlgItem
0x180008012  mov     rcx, rax; hWnd
0x180008015  mov     r8d, 104h; nMaxCount
0x18000801b  lea     rdx, [rbp+3E0h+String]; lpString
0x180008022  call    cs:__imp_GetWindowTextW
0x180008028  lea     rcx, [rbp+3E0h+String]; unsigned __int16 *
0x18000802f  call    ?StripLeadTrailSpace@@YAXPEAG@Z; StripLeadTrailSpace(ushort *)
0x180008034  lea     rcx, [rsp+4E0h+lpString]
0x180008039  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000803e  nop
0x18000803f  xor     esi, esi
0x180008041  lea     r8, [rbp+3E0h+String]
0x180008048  lea     rcx, [rsp+4E0h+var_480]
0x18000804d  cmp     [rbp+3E0h+lParam], si
0x180008051  jz      short loc_180008063
0x180008053  lea     r9, [rbp+3E0h+lParam]
0x180008057  mov     edx, 10Fh
0x18000805c  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x180008061  jmp     short loc_18000806D
0x180008063  mov     edx, 110h
0x180008068  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18000806d  mov     rdx, rax
0x180008070  lea     rcx, [rsp+4E0h+lpString]
0x180008075  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000807a  xor     r8d, r8d
0x18000807d  mov     dl, 1
0x18000807f  lea     rcx, [rsp+4E0h+var_480]
0x180008084  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008089  lea     rbx, [rsp+4E0h+lpString]
0x18000808e  cmp     [rsp+4E0h+var_488], 8
0x180008094  cmovnb  rbx, [rsp+4E0h+lpString]
0x18000809a  mov     edx, 66h ; 'f'; nIDDlgItem
0x18000809f  mov     rcx, rdi; hDlg
0x1800080a2  call    cs:__imp_GetDlgItem
0x1800080a8  mov     rdx, rbx; lpString
0x1800080ab  mov     rcx, rax; hWnd
0x1800080ae  call    cs:__imp_SetWindowTextW
0x1800080b4  nop
0x1800080b5  xor     r8d, r8d
0x1800080b8  mov     dl, 1
0x1800080ba  lea     rcx, [rsp+4E0h+lpString]
0x1800080bf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800080c4  jmp     loc_180008373
0x1800080c9  call    ?_PopulateOpenSavedLogTypeCombo@@YAXPEAUHWND__@@@Z; _PopulateOpenSavedLogTypeCombo(HWND__ *)
0x1800080ce  jmp     loc_180008373
0x1800080d3  lea     r9, aUnspecified; "(Unspecified)"
0x1800080da  mov     r8d, 104h; SizeInWords
0x1800080e0  lea     rdx, [rbp+3E0h+lParam]; Destination
0x1800080e4  lea     ecx, [r8-2]; uID
0x1800080e8  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x1800080ed  mov     edx, 65h ; 'e'; nIDDlgItem
0x1800080f2  mov     rcx, rdi; hDlg
0x1800080f5  call    cs:__imp_GetDlgItem
0x1800080fb  mov     rcx, rax; hWnd
0x1800080fe  lea     r9, [rbp+3E0h+lParam]; lParam
0x180008102  xor     r8d, r8d; wParam
0x180008105  mov     edx, 143h; Msg
0x18000810a  call    cs:__imp_SendMessageW
0x180008110  mov     edx, 65h ; 'e'; nIDDlgItem
0x180008115  mov     rcx, rdi; hDlg
0x180008118  call    cs:__imp_GetDlgItem
0x18000811e  mov     rcx, rax; hWnd
0x180008121  xor     r9d, r9d; lParam
0x180008124  xor     r8d, r8d; wParam
0x180008127  mov     edx, 14Eh; Msg
0x18000812c  call    cs:__imp_SendMessageW
0x180008132  jmp     loc_180008373
0x180008137  lea     rax, dwData
0x18000813e  mov     [rsp+4E0h+dwData], rax; dwData
0x180008143  mov     r8, rbx; __int64
0x180008146  mov     rdx, r9; unsigned __int64
0x180008149  mov     ecx, r10d; unsigned int
0x18000814c  call    ?InvokeWinHelp@@YAXI_K_JPEBGQEAK@Z; InvokeWinHelp(uint,unsigned __int64,__int64,ushort const *,ulong * const)
0x180008151  jmp     loc_180008373
0x180008156  mov     eax, [rbx+10h]
0x180008159  cmp     eax, 0FFFFFDA2h
0x18000815e  jz      loc_180008263
0x180008164  cmp     eax, 0FFFFFDA5h
0x180008169  jz      loc_1800080C9
0x18000816f  cmp     eax, 0FFFFFDA6h
0x180008174  jz      loc_1800080C9
0x18000817a  cmp     eax, 0FFFFFDA7h
0x18000817f  jnz     loc_180008373
0x180008185  call    cs:__imp_GetParent
0x18000818b  mov     rcx, rax; hDlg
0x18000818e  mov     r15d, 470h
0x180008194  mov     edx, r15d; nIDDlgItem
0x180008197  call    cs:__imp_GetDlgItem
0x18000819d  mov     rdx, rax; hWndInsertAfter
0x1800081a0  mov     r14d, 13h
0x1800081a6  mov     [rsp+4E0h+uFlags], r14d; uFlags
0x1800081ab  xor     esi, esi
0x1800081ad  mov     [rsp+4E0h+cy], esi; cy
0x1800081b1  mov     dword ptr [rsp+4E0h+dwData], esi; cx
0x1800081b5  xor     r9d, r9d; Y
0x1800081b8  xor     r8d, r8d; X
0x1800081bb  mov     rcx, rdi; hWnd
0x1800081be  call    cs:__imp_SetWindowPos
0x1800081c4  mov     rcx, rdi; hWnd
0x1800081c7  call    cs:__imp_GetParent
0x1800081cd  mov     rcx, rax; hDlg
0x1800081d0  mov     edx, r15d; nIDDlgItem
0x1800081d3  call    cs:__imp_GetDlgItem
0x1800081d9  mov     rbx, rax
0x1800081dc  mov     rcx, rdi; hWnd
0x1800081df  call    cs:__imp_GetParent
0x1800081e5  lea     r9, String; lpszWindow
0x1800081ec  lea     r8, szClass; "ToolbarWindow32"
0x1800081f3  mov     rdx, rbx; hWndChildAfter
0x1800081f6  mov     rcx, rax; hWndParent
0x1800081f9  call    cs:__imp_FindWindowExW
0x1800081ff  mov     rbx, rax
0x180008202  test    rax, rax
0x180008205  jz      loc_180008373
0x18000820b  mov     rcx, rdi; hWnd
0x18000820e  call    cs:__imp_GetParent
0x180008214  mov     rcx, rax; hDlg
0x180008217  mov     edx, r15d; nIDDlgItem
0x18000821a  call    cs:__imp_GetDlgItem
0x180008220  mov     rdx, rax; hWndInsertAfter
0x180008223  mov     [rsp+4E0h+uFlags], r14d; uFlags
0x180008228  mov     [rsp+4E0h+cy], esi; cy
0x18000822c  mov     dword ptr [rsp+4E0h+dwData], esi; cx
0x180008230  xor     r9d, r9d; Y
0x180008233  xor     r8d, r8d; X
0x180008236  mov     rcx, rbx; hWnd
0x180008239  call    cs:__imp_SetWindowPos
0x18000823f  mov     [rsp+4E0h+uFlags], r14d; uFlags
0x180008244  mov     [rsp+4E0h+cy], esi; cy
0x180008248  mov     dword ptr [rsp+4E0h+dwData], esi; cx
0x18000824c  xor     r9d, r9d; Y
0x18000824f  xor     r8d, r8d; X
0x180008252  mov     rdx, rbx; hWndInsertAfter
0x180008255  mov     rcx, rdi; hWnd
0x180008258  call    cs:__imp_SetWindowPos
0x18000825e  jmp     loc_180008373
0x180008263  mov     edx, 65h ; 'e'; nIDDlgItem
0x180008268  call    cs:__imp_GetDlgItem
0x18000826e  mov     r15, rax
0x180008271  xor     r9d, r9d; lParam
0x180008274  xor     r8d, r8d; wParam
0x180008277  mov     edx, 147h; Msg
0x18000827c  mov     rcx, rax; hWnd
0x18000827f  call    cs:__imp_SendMessageW
0x180008285  mov     r12, rax
0x180008288  xor     esi, esi
0x18000828a  mov     rcx, rdi; hWnd
0x18000828d  test    eax, eax
0x18000828f  jnz     short loc_1800082BA
0x180008291  mov     edx, 108h; uID
0x180008296  mov     r8d, 10h; unsigned int
0x18000829c  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x1800082a1  xor     edx, edx; nIndex
0x1800082a3  lea     r8d, [rdx+1]; dwNewLong
0x1800082a7  mov     rcx, rdi; hWnd
0x1800082aa  call    cs:__imp_SetWindowLongPtrW
0x1800082b0  mov     eax, 1
0x1800082b5  jmp     loc_180008375
0x1800082ba  mov     rax, [rbx+18h]
0x1800082be  mov     r14, [rax+70h]
0x1800082c2  mov     edx, 66h ; 'f'; nIDDlgItem
0x1800082c7  call    cs:__imp_GetDlgItem
0x1800082cd  mov     rcx, rax; hWnd
0x1800082d0  mov     r8d, 104h; nMaxCount
0x1800082d6  mov     rdx, r14; lpString
0x1800082d9  call    cs:__imp_GetWindowTextW
0x1800082df  mov     rcx, r14; unsigned __int16 *
0x1800082e2  call    ?StripLeadTrailSpace@@YAXPEAG@Z; StripLeadTrailSpace(ushort *)
0x1800082e7  cmp     [r14], si
0x1800082eb  jnz     short loc_1800082F7
0x1800082ed  mov     edx, 14Ah
0x1800082f2  mov     rcx, rdi
0x1800082f5  jmp     short loc_180008296
0x1800082f7  movsxd  r8, r12d; wParam
0x1800082fa  xor     r9d, r9d; lParam
0x1800082fd  mov     edx, 150h; Msg
0x180008302  mov     rcx, r15; hWnd
0x180008305  call    cs:__imp_SendMessageW
0x18000830b  mov     rsi, rax
0x18000830e  lea     rbx, [rax+8]
0x180008312  cmp     qword ptr [rbx+18h], 8
0x180008317  jb      short loc_18000831E
0x180008319  mov     rcx, [rbx]
0x18000831c  jmp     short loc_180008321
0x18000831e  mov     rcx, rbx
0x180008321  call    ?DetermineLogType@@YA?AW4EVENTLOGTYPE@@PEBG@Z; DetermineLogType(ushort const *)
0x180008326  mov     [r14+434h], eax
0x18000832d  cmp     qword ptr [rbx+18h], 8
0x180008332  jb      short loc_180008337
0x180008334  mov     rbx, [rbx]
0x180008337  lea     rcx, [r14+208h]
0x18000833e  mov     rdx, rbx
0x180008341  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008346  mov     eax, [rsi]
0x180008348  mov     [r14+430h], eax
0x18000834f  lea     rdx, [r14+228h]; unsigned __int16 *
0x180008356  mov     rcx, rdi; HWND
0x180008359  call    ?_GetOpenSavedServer@@YAXPEAUHWND__@@PEAGG@Z; _GetOpenSavedServer(HWND__ *,ushort *,ushort)
0x18000835e  jmp     short loc_180008373
0x180008360  mov     edx, 65h ; 'e'; nIDDlgItem
0x180008365  call    cs:__imp_GetDlgItem
0x18000836b  mov     rcx, rax; hWnd
0x18000836e  call    ?_ResetOpenSavedLogTypeCombo@@YAXPEAUHWND__@@@Z; _ResetOpenSavedLogTypeCombo(HWND__ *)
0x180008373  xor     eax, eax
0x180008375  mov     rcx, [rbp+3E0h+var_40]
0x18000837c  xor     rcx, rsp; StackCookie
0x18000837f  call    __security_check_cookie
0x180008384  add     rsp, 4B0h
0x18000838b  pop     r15
0x18000838d  pop     r14
0x18000838f  pop     r12
0x180008391  pop     rdi
0x180008392  pop     rsi
0x180008393  pop     rbx
0x180008394  pop     rbp
0x180008395  retn
```
