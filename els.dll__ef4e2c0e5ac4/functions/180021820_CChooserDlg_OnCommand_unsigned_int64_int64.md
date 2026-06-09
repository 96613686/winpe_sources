# CChooserDlg::_OnCommand(unsigned __int64,__int64)

- ea: `0x180021820`
- end: `0x180021b27`
- name: `?_OnCommand@CChooserDlg@@EEAAH_K_J@Z`
- size: `775`
- prototype: `__int64 __fastcall(CChooserDlg *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180006fc0`
- `0x180007990`
- `0x180008698`
- `0x180020580`
- `0x180020ee0`
- `0x180021584`
- `0x180021820`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180021a0d`
- `KERNEL32!lstrcmpiW` at `0x180021a0d`
- `USER32!GetDlgItem` at `0x180021886`
- `USER32!GetDlgItem` at `0x1800218a3`
- `USER32!GetDlgItem` at `0x1800218b9`
- `USER32!GetDlgItem` at `0x1800218d3`
- `USER32!GetDlgItem` at `0x18002198e`
- `USER32!GetDlgItem` at `0x180021886`
- `USER32!GetDlgItem` at `0x1800218a3`
- `USER32!GetDlgItem` at `0x1800218b9`
- `USER32!GetDlgItem` at `0x1800218d3`
- `USER32!GetDlgItem` at `0x18002198e`
- `USER32!GetWindowTextW` at `0x1800219a5`
- `USER32!GetWindowTextW` at `0x1800219a5`
- `USER32!EnableWindow` at `0x180021894`
- `USER32!EnableWindow` at `0x1800218c4`
- `USER32!EnableWindow` at `0x1800218de`
- `USER32!EnableWindow` at `0x180021894`
- `USER32!EnableWindow` at `0x1800218c4`
- `USER32!EnableWindow` at `0x1800218de`
- `USER32!IsDlgButtonChecked` at `0x18002196f`
- `USER32!IsDlgButtonChecked` at `0x18002196f`
- `USER32!GetWindowLongPtrW` at `0x1800219df`
- `USER32!GetWindowLongPtrW` at `0x1800219df`
- `USER32!EndDialog` at `0x180021aff`
- `USER32!EndDialog` at `0x180021aff`

## pseudocode

```c
__int64 __fastcall CChooserDlg::_OnCommand(CChooserDlg *this, __int16 a2)
{
  HWND v3; // rax
  HWND v4; // rax
  BOOL v5; // edx
  HWND v6; // rax
  INT_PTR v7; // rdx
  HWND DlgItem; // rbp
  WCHAR *i; // rdi
  _QWORD *WindowLongPtrW; // rax
  _QWORD *v11; // r14
  const WCHAR *v12; // rcx
  const wchar_t *v13; // rdx
  int v14; // ecx
  WCHAR String[264]; // [rsp+20h] [rbp-258h] BYREF

  switch ( a2 )
  {
    case 1:
      memset_0(String, 0, sizeof(String));
      if ( IsDlgButtonChecked(*((HWND *)this + 1), 972) )
      {
        i = String;
      }
      else
      {
        DlgItem = GetDlgItem(*((HWND *)this + 1), 974);
        GetWindowTextW(DlgItem, String, 264);
        StripLeadTrailSpace(String);
        if ( !String[0] )
        {
          MsgBox(*((HWND *)this + 1), 0x10Du, 0x10u);
          return 0;
        }
        for ( i = String; *i == 92; ++i )
          ;
        WindowLongPtrW = (_QWORD *)GetWindowLongPtrW(DlgItem, -21);
        v11 = WindowLongPtrW;
        if ( WindowLongPtrW && WindowLongPtrW[6] )
        {
          v12 = WindowLongPtrW[3] < 8u ? (const WCHAR *)WindowLongPtrW : (const WCHAR *)*WindowLongPtrW;
          if ( !lstrcmpiW(v12, i) )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1152LL) + 88LL))(
              *(_QWORD *)(*((_QWORD *)this + 2) + 1152LL),
              *((_QWORD *)this + 3));
            CComponentData::_RemoveLogSetFromScopePane(*((CComponentData **)this + 2), 0);
            v13 = (const wchar_t *)(v11 + 4);
            if ( v11[7] >= 8u )
              v13 = *(const wchar_t **)v13;
            CComponentData::SetServerFocus(*((CComponentData **)this + 2), v13);
            *(_WORD *)(*((_QWORD *)this + 2) + 56LL) |= 0x80u;
            v14 = CComponentData::_OnExpand(
                    *((CComponentData **)this + 2),
                    *((_QWORD *)this + 3),
                    *((struct IDataObject **)this + 4),
                    *((HWND *)this + 1));
            if ( v14 >= 0 )
              goto LABEL_30;
          }
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1152LL) + 88LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 1152LL),
        *((_QWORD *)this + 3));
      CComponentData::_RemoveLogSetFromScopePane(*((CComponentData **)this + 2), 0);
      CComponentData::SetServerFocus(*((CComponentData **)this + 2), i);
      *(_WORD *)(*((_QWORD *)this + 2) + 56LL) |= 0x80u;
      v14 = CComponentData::_OnExpand(
              *((CComponentData **)this + 2),
              *((_QWORD *)this + 3),
              *((struct IDataObject **)this + 4),
              *((HWND *)this + 1));
LABEL_30:
      *((_DWORD *)this + 142) = (unsigned int)v14 >> 31;
      if ( v14 < 0 )
        return 0;
      v7 = 1;
LABEL_32:
      EndDialog(*((HWND *)this + 1), v7);
      return 0;
    case 2:
      if ( *((_DWORD *)this + 142) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1152LL) + 88LL))(
          *(_QWORD *)(*((_QWORD *)this + 2) + 1152LL),
          *((_QWORD *)this + 3));
        CComponentData::_RemoveLogSetFromScopePane(*((CComponentData **)this + 2), 0);
        CComponentData::SetServerFocus(*((CComponentData **)this + 2), (STRSAFE_PCNZWCH)this + 20);
        *(_WORD *)(*((_QWORD *)this + 2) + 56LL) |= 0x80u;
        CComponentData::_OnExpand(
          *((CComponentData **)this + 2),
          *((_QWORD *)this + 3),
          *((struct IDataObject **)this + 4),
          *((HWND *)this + 1));
      }
      v7 = 2;
      goto LABEL_32;
    case 972:
      v6 = GetDlgItem(*((HWND *)this + 1), 974);
      EnableWindow(v6, 0);
      v4 = GetDlgItem(*((HWND *)this + 1), 975);
      v5 = 0;
      goto LABEL_9;
    case 973:
      v3 = GetDlgItem(*((HWND *)this + 1), 974);
      EnableWindow(v3, 1);
      v4 = GetDlgItem(*((HWND *)this + 1), 975);
      v5 = 1;
LABEL_9:
      EnableWindow(v4, v5);
      return 0;
    case 975:
      CChooserDlg::_OnBrowseForMachine(this);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180021820  push    rbx
0x180021822  push    rbp
0x180021823  push    rsi
0x180021824  push    rdi
0x180021825  push    r14
0x180021827  push    r15
0x180021829  sub     rsp, 248h
0x180021830  mov     rax, cs:__security_cookie
0x180021837  xor     rax, rsp
0x18002183a  mov     [rsp+278h+var_48], rax
0x180021842  mov     rbx, rcx
0x180021845  movzx   ecx, dx
0x180021848  sub     ecx, 1
0x18002184b  jz      loc_180021954
0x180021851  sub     ecx, 1
0x180021854  jz      loc_1800218E9
0x18002185a  sub     ecx, 3CAh
0x180021860  jz      short loc_1800218B0
0x180021862  sub     ecx, 1
0x180021865  jz      short loc_18002187D
0x180021867  cmp     ecx, 2
0x18002186a  jnz     loc_180021B05
0x180021870  mov     rcx, rbx; this
0x180021873  call    ?_OnBrowseForMachine@CChooserDlg@@AEAAXXZ; CChooserDlg::_OnBrowseForMachine(void)
0x180021878  jmp     loc_180021B05
0x18002187d  mov     rcx, [rbx+8]; hDlg
0x180021881  mov     edx, 3CEh; nIDDlgItem
0x180021886  call    cs:__imp_GetDlgItem
0x18002188c  mov     rcx, rax; hWnd
0x18002188f  mov     edx, 1; bEnable
0x180021894  call    cs:__imp_EnableWindow
0x18002189a  mov     rcx, [rbx+8]; hDlg
0x18002189e  mov     edx, 3CFh; nIDDlgItem
0x1800218a3  call    cs:__imp_GetDlgItem
0x1800218a9  mov     edx, 1
0x1800218ae  jmp     short loc_1800218DB
0x1800218b0  mov     rcx, [rbx+8]; hDlg
0x1800218b4  mov     edx, 3CEh; nIDDlgItem
0x1800218b9  call    cs:__imp_GetDlgItem
0x1800218bf  mov     rcx, rax; hWnd
0x1800218c2  xor     edx, edx; bEnable
0x1800218c4  call    cs:__imp_EnableWindow
0x1800218ca  mov     rcx, [rbx+8]; hDlg
0x1800218ce  mov     edx, 3CFh; nIDDlgItem
0x1800218d3  call    cs:__imp_GetDlgItem
0x1800218d9  xor     edx, edx; bEnable
0x1800218db  mov     rcx, rax; hWnd
0x1800218de  call    cs:__imp_EnableWindow
0x1800218e4  jmp     loc_180021B05
0x1800218e9  xor     esi, esi
0x1800218eb  cmp     [rbx+238h], esi
0x1800218f1  jz      short loc_18002194A
0x1800218f3  mov     rax, [rbx+10h]
0x1800218f7  mov     rdx, [rbx+18h]
0x1800218fb  mov     rcx, [rax+480h]
0x180021902  mov     rax, [rcx]
0x180021905  mov     rax, [rax+58h]
0x180021909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002190e  mov     rcx, [rbx+10h]; this
0x180021912  xor     edx, edx; __int64
0x180021914  call    ?_RemoveLogSetFromScopePane@CComponentData@@AEAAX_J@Z; CComponentData::_RemoveLogSetFromScopePane(__int64)
0x180021919  mov     rcx, [rbx+10h]; this
0x18002191d  lea     rdx, [rbx+28h]; pszSrc
0x180021921  call    ?SetServerFocus@CComponentData@@QEAAXPEBG@Z; CComponentData::SetServerFocus(ushort const *)
0x180021926  mov     rax, [rbx+10h]
0x18002192a  mov     r15d, 80h
0x180021930  or      [rax+38h], r15w
0x180021935  mov     r9, [rbx+8]; hWnd
0x180021939  mov     r8, [rbx+20h]; struct IDataObject *
0x18002193d  mov     rdx, [rbx+18h]; __int64
0x180021941  mov     rcx, [rbx+10h]; this
0x180021945  call    ?_OnExpand@CComponentData@@AEAAJ_JPEAUIDataObject@@PEAUHWND__@@@Z; CComponentData::_OnExpand(__int64,IDataObject *,HWND__ *)
0x18002194a  mov     edx, 2
0x18002194f  jmp     loc_180021AFB
0x180021954  xor     edx, edx; Val
0x180021956  lea     rcx, [rsp+278h+String]; void *
0x18002195b  mov     r8d, 210h; Size
0x180021961  call    memset_0
0x180021966  mov     rcx, [rbx+8]; hDlg
0x18002196a  mov     edx, 3CCh; nIDButton
0x18002196f  call    cs:__imp_IsDlgButtonChecked
0x180021975  xor     esi, esi
0x180021977  mov     r15d, 80h
0x18002197d  test    eax, eax
0x18002197f  jnz     loc_180021A90
0x180021985  mov     rcx, [rbx+8]; hDlg
0x180021989  mov     edx, 3CEh; nIDDlgItem
0x18002198e  call    cs:__imp_GetDlgItem
0x180021994  mov     r8d, 108h; nMaxCount
0x18002199a  lea     rdx, [rsp+278h+String]; lpString
0x18002199f  mov     rcx, rax; hWnd
0x1800219a2  mov     rbp, rax
0x1800219a5  call    cs:__imp_GetWindowTextW
0x1800219ab  lea     rcx, [rsp+278h+String]; unsigned __int16 *
0x1800219b0  call    ?StripLeadTrailSpace@@YAXPEAG@Z; StripLeadTrailSpace(ushort *)
0x1800219b5  cmp     [rsp+278h+String], si
0x1800219ba  jz      loc_180021A7A
0x1800219c0  cmp     [rsp+278h+String], 5Ch ; '\'
0x1800219c6  lea     rdi, [rsp+278h+String]
0x1800219cb  jnz     short loc_1800219D7
0x1800219cd  add     rdi, 2
0x1800219d1  cmp     word ptr [rdi], 5Ch ; '\'
0x1800219d5  jz      short loc_1800219CD
0x1800219d7  mov     edx, 0FFFFFFEBh; nIndex
0x1800219dc  mov     rcx, rbp; hWnd
0x1800219df  call    cs:__imp_GetWindowLongPtrW
0x1800219e5  mov     r14, rax
0x1800219e8  test    rax, rax
0x1800219eb  jz      loc_180021A95
0x1800219f1  cmp     [rax+30h], rsi
0x1800219f5  jz      loc_180021A95
0x1800219fb  cmp     qword ptr [rax+18h], 8
0x180021a00  jb      short loc_180021A07
0x180021a02  mov     rcx, [rax]
0x180021a05  jmp     short loc_180021A0A
0x180021a07  mov     rcx, r14; lpString1
0x180021a0a  mov     rdx, rdi; lpString2
0x180021a0d  call    cs:__imp_lstrcmpiW
0x180021a13  test    eax, eax
0x180021a15  jnz     short loc_180021A95
0x180021a17  mov     rax, [rbx+10h]
0x180021a1b  mov     rdx, [rbx+18h]
0x180021a1f  mov     rcx, [rax+480h]
0x180021a26  mov     rax, [rcx]
0x180021a29  mov     rax, [rax+58h]
0x180021a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a32  mov     rcx, [rbx+10h]; this
0x180021a36  xor     edx, edx; __int64
0x180021a38  call    ?_RemoveLogSetFromScopePane@CComponentData@@AEAAX_J@Z; CComponentData::_RemoveLogSetFromScopePane(__int64)
0x180021a3d  lea     rdx, [r14+20h]
0x180021a41  cmp     qword ptr [rdx+18h], 8
0x180021a46  jb      short loc_180021A4B
0x180021a48  mov     rdx, [rdx]; pszSrc
0x180021a4b  mov     rcx, [rbx+10h]; this
0x180021a4f  call    ?SetServerFocus@CComponentData@@QEAAXPEBG@Z; CComponentData::SetServerFocus(ushort const *)
0x180021a54  mov     rax, [rbx+10h]
0x180021a58  or      [rax+38h], r15w
0x180021a5d  mov     r9, [rbx+8]; hWnd
0x180021a61  mov     r8, [rbx+20h]; struct IDataObject *
0x180021a65  mov     rdx, [rbx+18h]; __int64
0x180021a69  mov     rcx, [rbx+10h]; this
0x180021a6d  call    ?_OnExpand@CComponentData@@AEAAJ_JPEAUIDataObject@@PEAUHWND__@@@Z; CComponentData::_OnExpand(__int64,IDataObject *,HWND__ *)
0x180021a72  mov     ecx, eax
0x180021a74  test    eax, eax
0x180021a76  jns     short loc_180021AE7
0x180021a78  jmp     short loc_180021A95
0x180021a7a  mov     rcx, [rbx+8]; hWnd
0x180021a7e  mov     edx, 10Dh; uID
0x180021a83  mov     r8d, 10h; unsigned int
0x180021a89  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x180021a8e  jmp     short loc_180021B05
0x180021a90  lea     rdi, [rsp+278h+String]
0x180021a95  mov     rax, [rbx+10h]
0x180021a99  mov     rdx, [rbx+18h]
0x180021a9d  mov     rcx, [rax+480h]
0x180021aa4  mov     rax, [rcx]
0x180021aa7  mov     rax, [rax+58h]
0x180021aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ab0  mov     rcx, [rbx+10h]; this
0x180021ab4  xor     edx, edx; __int64
0x180021ab6  call    ?_RemoveLogSetFromScopePane@CComponentData@@AEAAX_J@Z; CComponentData::_RemoveLogSetFromScopePane(__int64)
0x180021abb  mov     rcx, [rbx+10h]; this
0x180021abf  mov     rdx, rdi; pszSrc
0x180021ac2  call    ?SetServerFocus@CComponentData@@QEAAXPEBG@Z; CComponentData::SetServerFocus(ushort const *)
0x180021ac7  mov     rax, [rbx+10h]
0x180021acb  or      [rax+38h], r15w
0x180021ad0  mov     r9, [rbx+8]; hWnd
0x180021ad4  mov     r8, [rbx+20h]; struct IDataObject *
0x180021ad8  mov     rdx, [rbx+18h]; __int64
0x180021adc  mov     rcx, [rbx+10h]; this
0x180021ae0  call    ?_OnExpand@CComponentData@@AEAAJ_JPEAUIDataObject@@PEAUHWND__@@@Z; CComponentData::_OnExpand(__int64,IDataObject *,HWND__ *)
0x180021ae5  mov     ecx, eax
0x180021ae7  mov     eax, ecx
0x180021ae9  shr     eax, 1Fh
0x180021aec  mov     [rbx+238h], eax
0x180021af2  test    ecx, ecx
0x180021af4  js      short loc_180021B05
0x180021af6  mov     edx, 1; nResult
0x180021afb  mov     rcx, [rbx+8]; hDlg
0x180021aff  call    cs:__imp_EndDialog
0x180021b05  xor     eax, eax
0x180021b07  mov     rcx, [rsp+278h+var_48]
0x180021b0f  xor     rcx, rsp; StackCookie
0x180021b12  call    __security_check_cookie
0x180021b17  add     rsp, 248h
0x180021b1e  pop     r15
0x180021b20  pop     r14
0x180021b22  pop     rdi
0x180021b23  pop     rsi
0x180021b24  pop     rbp
0x180021b25  pop     rbx
0x180021b26  retn
```
