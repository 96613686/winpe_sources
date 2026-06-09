# COskOptionsDlg::SetIntervalUI(int)

- ea: `0x140019030`
- end: `0x140019100`
- name: `?SetIntervalUI@COskOptionsDlg@@AEAAXH@Z`
- size: `208`
- prototype: `void __fastcall(COskOptionsDlg *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018a60`

## callees

- `0x140019030`
- `0x140027010`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x1400190d0`
- `USER32!SetDlgItemTextW` at `0x1400190d0`
- `USER32!GetDlgItem` at `0x14001904a`
- `USER32!GetDlgItem` at `0x14001904a`
- `OLEACC!AccessibleObjectFromWindow` at `0x14001906b`
- `OLEACC!AccessibleObjectFromWindow` at `0x14001906b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400190da`
- `OLEAUT32!__imp_SysFreeString` at `0x1400190da`

## pseudocode

```c
void __fastcall COskOptionsDlg::SetIntervalUI(HWND *this, int a2)
{
  HWND DlgItem; // rax
  int v5; // edx
  __int128 v6; // [rsp+20h] [rbp-20h] BYREF
  __int64 v7; // [rsp+30h] [rbp-10h]
  LPCWSTR lpString; // [rsp+50h] [rbp+10h] BYREF
  void *ppvObject; // [rsp+60h] [rbp+20h] BYREF

  DlgItem = GetDlgItem(*this, a2);
  ppvObject = 0;
  if ( AccessibleObjectFromWindow(DlgItem, 0xFFFFFFFC, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &ppvObject) >= 0 )
  {
    lpString = 0;
    v7 = 0;
    v6 = 0;
    DWORD2(v6) = 0;
    LOWORD(v6) = 3;
    if ( (*(int (__fastcall **)(void *, __int128 *, LPCWSTR *))(*(_QWORD *)ppvObject + 88LL))(ppvObject, &v6, &lpString) >= 0 )
    {
      v5 = 5016;
      if ( a2 != 5017 )
        v5 = 5019;
      SetDlgItemTextW(*this, v5, lpString);
      SysFreeString((BSTR)lpString);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  }
}

```

## disassembly

```asm
0x140019030  mov     [rsp-8+arg_8], rbx
0x140019035  mov     [rsp-8+arg_18], rdi
0x14001903a  push    rbp
0x14001903b  mov     rbp, rsp
0x14001903e  sub     rsp, 40h
0x140019042  mov     rdi, rcx
0x140019045  mov     ebx, edx
0x140019047  mov     rcx, [rcx]; hDlg
0x14001904a  call    cs:__imp_GetDlgItem
0x140019050  lea     r9, [rbp+ppvObject]; ppvObject
0x140019054  mov     [rbp+ppvObject], 0
0x14001905c  mov     rcx, rax; hwnd
0x14001905f  lea     r8, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71; riid
0x140019066  mov     edx, 0FFFFFFFCh; dwId
0x14001906b  call    cs:__imp_AccessibleObjectFromWindow
0x140019071  test    eax, eax
0x140019073  js      short loc_1400190F0
0x140019075  xor     ecx, ecx
0x140019077  mov     [rbp+lpString], 0
0x14001907f  xorps   xmm0, xmm0
0x140019082  mov     [rbp+var_10], rcx
0x140019086  movups  [rbp+var_20], xmm0
0x14001908a  mov     dword ptr [rbp+var_20+8], ecx
0x14001908d  lea     r8, [rbp+lpString]
0x140019091  lea     eax, [rcx+3]
0x140019094  mov     rcx, [rbp+ppvObject]
0x140019098  mov     word ptr [rbp+var_20], ax
0x14001909c  lea     rdx, [rbp+var_20]
0x1400190a0  movups  xmm0, [rbp+var_20]
0x1400190a4  mov     rax, [rcx]
0x1400190a7  movaps  [rbp+var_20], xmm0
0x1400190ab  mov     rax, [rax+58h]
0x1400190af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400190b4  test    eax, eax
0x1400190b6  js      short loc_1400190E0
0x1400190b8  mov     r8, [rbp+lpString]; lpString
0x1400190bc  mov     edx, 1398h
0x1400190c1  mov     rcx, [rdi]; hDlg
0x1400190c4  cmp     ebx, 1399h
0x1400190ca  lea     eax, [rdx+3]
0x1400190cd  cmovnz  edx, eax; nIDDlgItem
0x1400190d0  call    cs:__imp_SetDlgItemTextW
0x1400190d6  mov     rcx, [rbp+lpString]; bstrString
0x1400190da  call    cs:__imp_SysFreeString
0x1400190e0  mov     rcx, [rbp+ppvObject]
0x1400190e4  mov     rax, [rcx]
0x1400190e7  mov     rax, [rax+10h]
0x1400190eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400190f0  mov     rbx, [rsp+40h+arg_8]
0x1400190f5  mov     rdi, [rsp+40h+arg_18]
0x1400190fa  add     rsp, 40h
0x1400190fe  pop     rbp
0x1400190ff  retn
```
