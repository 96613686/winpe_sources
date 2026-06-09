# CWMWriterProperties::OnReceiveMessage(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180012c00`
- end: `0x180012f46`
- name: `?OnReceiveMessage@CWMWriterProperties@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `838`
- prototype: `__int64 __usercall@<rax>(CWMWriterProperties *__hidden this@<rcx>, HWND hDlg@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001460`
- `0x1800121e0`
- `0x1800126e0`
- `0x180012c00`
- `0x18001d10c`
- `0x18001f010`

## import_xrefs

- `USER32!SendMessageW` at `0x180012e09`
- `USER32!SendMessageW` at `0x180012f23`
- `USER32!SendMessageW` at `0x180012e09`
- `USER32!SendMessageW` at `0x180012f23`
- `USER32!GetDlgItemInt` at `0x180012ca2`
- `USER32!GetDlgItemInt` at `0x180012d26`
- `USER32!GetDlgItemInt` at `0x180012ca2`
- `USER32!GetDlgItemInt` at `0x180012d26`
- `USER32!SetDlgItemInt` at `0x180012ed6`
- `USER32!SetDlgItemInt` at `0x180012eeb`
- `USER32!SetDlgItemInt` at `0x180012ed6`
- `USER32!SetDlgItemInt` at `0x180012eeb`
- `USER32!GetDlgItem` at `0x180012da7`
- `USER32!GetDlgItem` at `0x180012db9`
- `USER32!GetDlgItem` at `0x180012dcb`
- `USER32!GetDlgItem` at `0x180012da7`
- `USER32!GetDlgItem` at `0x180012db9`
- `USER32!GetDlgItem` at `0x180012dcb`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::OnReceiveMessage(
        CWMWriterProperties *this,
        HWND hDlg,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-34h] BYREF
  UINT DlgItemInt; // [rsp+48h] [rbp-30h] BYREF
  BOOL Translated; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+54h] [rbp-24h] BYREF
  UINT uValue; // [rsp+58h] [rbp-20h] BYREF
  int v19; // [rsp+5Ch] [rbp-1Ch] BYREF

  if ( a3 == 272 )
  {
    *((_QWORD *)this + 9) = GetDlgItem(hDlg, 102);
    *((_QWORD *)this + 10) = GetDlgItem(hDlg, 103);
    *((_QWORD *)this + 11) = GetDlgItem(hDlg, 106);
    CWMWriterProperties::FillProfileList((HWND *)this);
    v9 = *((_QWORD *)this + 12);
    v17 = 1;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 80LL))(v9, &v17);
    SendMessageW(*((HWND *)this + 10), 0xF1u, v17, 0);
    v13 = 0;
    uValue = -1;
    if ( (int)CWMWriterProperties::GetVideoInputNumber(this, &v13) >= 0 )
    {
      v10 = *((_QWORD *)this + 14);
      DlgItemInt = 0;
      LOWORD(v14) = 4;
      (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *, UINT *, UINT *, unsigned int *))(*(_QWORD *)v10 + 112LL))(
        v10,
        v13,
        L"DeinterlaceMode",
        &DlgItemInt,
        &uValue,
        &v14);
    }
    v13 = 0;
    DlgItemInt = -1;
    if ( (int)CWMWriterProperties::GetVideoInputNumber(this, &v13) >= 0 )
    {
      v11 = *((_QWORD *)this + 14);
      v19 = 0;
      LOWORD(v14) = 4;
      (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *, int *, UINT *, unsigned int *))(*(_QWORD *)v11 + 112LL))(
        v11,
        v13,
        L"InitialPatternForInverseTelecine",
        &v19,
        &DlgItemInt,
        &v14);
    }
    SetDlgItemInt(hDlg, 104, uValue, 1);
    SetDlgItemInt(hDlg, 105, DlgItemInt, 1);
    v12 = *((_QWORD *)this + 12);
    Translated = 0;
    (*(void (__fastcall **)(__int64, __int64, BOOL *))(*(_QWORD *)v12 + 104LL))(v12, 2, &Translated);
    SendMessageW(*((HWND *)this + 11), 0xF1u, Translated, 0);
  }
  else
  {
    if ( a3 != 273 )
      return CBasePropertyPage::OnReceiveMessage(this, hDlg, a3, a4, a5);
    if ( WORD1(a4) == 1 || (_WORD)a4 == 103 || (_WORD)a4 == 106 )
    {
      *((_DWORD *)this + 14) = 1;
      v8 = *((_QWORD *)this + 4);
      if ( v8 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
    }
    else if ( (_WORD)a4 == 104 )
    {
      if ( WORD1(a4) == 512 )
      {
        Translated = 0;
        v14 = 0;
        DlgItemInt = GetDlgItemInt(hDlg, 104, &Translated, 0);
        if ( (int)CWMWriterProperties::GetVideoInputNumber(this, &v14) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, UINT *, __int16))(**((_QWORD **)this + 14)
                                                                                           + 120LL))(
            *((_QWORD *)this + 14),
            v14,
            L"DeinterlaceMode",
            0,
            &DlgItemInt,
            4);
      }
    }
    else if ( (_DWORD)a4 == 33554537 )
    {
      Translated = 0;
      v14 = 0;
      DlgItemInt = GetDlgItemInt(hDlg, 105, &Translated, 0);
      if ( (int)CWMWriterProperties::GetVideoInputNumber(this, &v14) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, UINT *, __int16))(**((_QWORD **)this + 14)
                                                                                         + 120LL))(
          *((_QWORD *)this + 14),
          v14,
          L"InitialPatternForInverseTelecine",
          0,
          &DlgItemInt,
          4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180012c00  push    rbp
0x180012c02  push    rsi
0x180012c03  push    rdi
0x180012c04  push    r12
0x180012c06  push    r14
0x180012c08  push    r15
0x180012c0a  mov     rbp, rsp
0x180012c0d  sub     rsp, 78h
0x180012c11  mov     rax, cs:__security_cookie
0x180012c18  xor     rax, rsp
0x180012c1b  mov     [rbp+var_18], rax
0x180012c1f  mov     eax, r8d
0x180012c22  mov     r15, rdx
0x180012c25  mov     rdi, rcx
0x180012c28  sub     eax, 110h
0x180012c2d  jz      loc_180012D9F
0x180012c33  cmp     eax, 1
0x180012c36  jz      short loc_180012C4B
0x180012c38  mov     rax, [rbp+arg_20]
0x180012c3c  mov     [rsp+78h+var_58], rax; __int64
0x180012c41  call    ?OnReceiveMessage@CBasePropertyPage@@UEAA_JPEAUHWND__@@I_K_J@Z; CBasePropertyPage::OnReceiveMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180012c46  jmp     loc_180012F2C
0x180012c4b  mov     rax, r9
0x180012c4e  mov     esi, 1
0x180012c53  shr     rax, 10h
0x180012c57  cmp     ax, si
0x180012c5a  jz      loc_180012D7C
0x180012c60  lea     edx, [rsi+66h]
0x180012c63  cmp     r9w, dx
0x180012c67  jz      loc_180012D7C
0x180012c6d  lea     edx, [rsi+69h]
0x180012c70  cmp     r9w, dx
0x180012c74  jz      loc_180012D7C
0x180012c7a  lea     edx, [rsi+67h]; nIDDlgItem
0x180012c7d  cmp     r9w, dx
0x180012c81  jnz     short loc_180012CF8
0x180012c83  mov     ecx, 200h
0x180012c88  cmp     cx, ax
0x180012c8b  jnz     loc_180012F29
0x180012c91  xor     r9d, r9d; bSigned
0x180012c94  mov     [rbp+Translated], 0
0x180012c9b  lea     r8, [rbp+Translated]; lpTranslated
0x180012c9f  mov     rcx, r15; hDlg
0x180012ca2  call    cs:__imp_GetDlgItemInt
0x180012ca8  lea     rdx, [rbp+var_34]; unsigned int *
0x180012cac  mov     [rbp+var_34], 0
0x180012cb3  mov     rcx, rdi; this
0x180012cb6  mov     [rbp+var_30], eax
0x180012cb9  call    ?GetVideoInputNumber@CWMWriterProperties@@AEAAJPEAK@Z; CWMWriterProperties::GetVideoInputNumber(ulong *)
0x180012cbe  test    eax, eax
0x180012cc0  js      loc_180012F29
0x180012cc6  mov     rcx, [rdi+70h]
0x180012cca  lea     rdx, [rbp+var_30]
0x180012cce  mov     word ptr [rsp+78h+var_50], 4
0x180012cd5  lea     r8, aDeinterlacemod; "DeinterlaceMode"
0x180012cdc  mov     [rsp+78h+var_58], rdx
0x180012ce1  xor     r9d, r9d
0x180012ce4  mov     edx, [rbp+var_34]
0x180012ce7  mov     rax, [rcx]
0x180012cea  mov     rax, [rax+78h]
0x180012cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf3  jmp     loc_180012F29
0x180012cf8  mov     edx, 69h ; 'i'; nIDDlgItem
0x180012cfd  cmp     r9w, dx
0x180012d01  jnz     loc_180012F29
0x180012d07  mov     ecx, 200h
0x180012d0c  cmp     cx, ax
0x180012d0f  jnz     loc_180012F29
0x180012d15  xor     r9d, r9d; bSigned
0x180012d18  mov     [rbp+Translated], 0
0x180012d1f  lea     r8, [rbp+Translated]; lpTranslated
0x180012d23  mov     rcx, r15; hDlg
0x180012d26  call    cs:__imp_GetDlgItemInt
0x180012d2c  lea     rdx, [rbp+var_34]; unsigned int *
0x180012d30  mov     [rbp+var_34], 0
0x180012d37  mov     rcx, rdi; this
0x180012d3a  mov     [rbp+var_30], eax
0x180012d3d  call    ?GetVideoInputNumber@CWMWriterProperties@@AEAAJPEAK@Z; CWMWriterProperties::GetVideoInputNumber(ulong *)
0x180012d42  test    eax, eax
0x180012d44  js      loc_180012F29
0x180012d4a  mov     rcx, [rdi+70h]
0x180012d4e  lea     rdx, [rbp+var_30]
0x180012d52  mov     word ptr [rsp+78h+var_50], 4
0x180012d59  lea     r8, aInitialpattern; "InitialPatternForInverseTelecine"
0x180012d60  mov     [rsp+78h+var_58], rdx
0x180012d65  xor     r9d, r9d
0x180012d68  mov     edx, [rbp+var_34]
0x180012d6b  mov     rax, [rcx]
0x180012d6e  mov     rax, [rax+78h]
0x180012d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d77  jmp     loc_180012F29
0x180012d7c  mov     [rcx+38h], esi
0x180012d7f  mov     rcx, [rcx+20h]
0x180012d83  test    rcx, rcx
0x180012d86  jz      loc_180012F29
0x180012d8c  mov     rdx, [rcx]
0x180012d8f  mov     rax, [rdx+18h]
0x180012d93  mov     edx, esi
0x180012d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d9a  jmp     loc_180012F29
0x180012d9f  mov     edx, 66h ; 'f'; nIDDlgItem
0x180012da4  mov     rcx, r15; hDlg
0x180012da7  call    cs:__imp_GetDlgItem
0x180012dad  mov     edx, 67h ; 'g'; nIDDlgItem
0x180012db2  mov     rcx, r15; hDlg
0x180012db5  mov     [rdi+48h], rax
0x180012db9  call    cs:__imp_GetDlgItem
0x180012dbf  mov     edx, 6Ah ; 'j'; nIDDlgItem
0x180012dc4  mov     rcx, r15; hDlg
0x180012dc7  mov     [rdi+50h], rax
0x180012dcb  call    cs:__imp_GetDlgItem
0x180012dd1  mov     rcx, rdi; this
0x180012dd4  mov     [rdi+58h], rax
0x180012dd8  call    ?FillProfileList@CWMWriterProperties@@AEAAXXZ; CWMWriterProperties::FillProfileList(void)
0x180012ddd  mov     rcx, [rdi+60h]
0x180012de1  lea     rdx, [rbp+var_24]
0x180012de5  mov     esi, 1
0x180012dea  mov     [rbp+var_24], esi
0x180012ded  mov     rax, [rcx]
0x180012df0  mov     rax, [rax+50h]
0x180012df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012df9  movsxd  r8, [rbp+var_24]; wParam
0x180012dfd  xor     r9d, r9d; lParam
0x180012e00  mov     rcx, [rdi+50h]; hWnd
0x180012e04  mov     edx, 0F1h; Msg
0x180012e09  call    cs:__imp_SendMessageW
0x180012e0f  lea     rdx, [rbp+var_38]; unsigned int *
0x180012e13  mov     [rbp+var_38], 0
0x180012e1a  mov     rcx, rdi; this
0x180012e1d  mov     [rbp+uValue], 0FFFFFFFFh
0x180012e24  call    ?GetVideoInputNumber@CWMWriterProperties@@AEAAJPEAK@Z; CWMWriterProperties::GetVideoInputNumber(ulong *)
0x180012e29  lea     r14d, [rsi+3]
0x180012e2d  test    eax, eax
0x180012e2f  js      short loc_180012E6D
0x180012e31  mov     rcx, [rdi+70h]
0x180012e35  lea     rdx, [rbp+var_34]
0x180012e39  mov     [rsp+78h+var_50], rdx
0x180012e3e  lea     r9, [rbp+var_30]
0x180012e42  lea     rdx, [rbp+uValue]
0x180012e46  mov     [rbp+var_30], 0
0x180012e4d  mov     word ptr [rbp+var_34], r14w
0x180012e52  lea     r8, aDeinterlacemod; "DeinterlaceMode"
0x180012e59  mov     rax, [rcx]
0x180012e5c  mov     [rsp+78h+var_58], rdx
0x180012e61  mov     edx, [rbp+var_38]
0x180012e64  mov     rax, [rax+70h]
0x180012e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e6d  lea     rdx, [rbp+var_38]; unsigned int *
0x180012e71  mov     [rbp+var_38], 0
0x180012e78  mov     rcx, rdi; this
0x180012e7b  mov     [rbp+var_30], 0FFFFFFFFh
0x180012e82  call    ?GetVideoInputNumber@CWMWriterProperties@@AEAAJPEAK@Z; CWMWriterProperties::GetVideoInputNumber(ulong *)
0x180012e87  test    eax, eax
0x180012e89  js      short loc_180012EC7
0x180012e8b  mov     rcx, [rdi+70h]
0x180012e8f  lea     rdx, [rbp+var_34]
0x180012e93  mov     [rsp+78h+var_50], rdx
0x180012e98  lea     r9, [rbp+var_1C]
0x180012e9c  lea     rdx, [rbp+var_30]
0x180012ea0  mov     [rbp+var_1C], 0
0x180012ea7  mov     word ptr [rbp+var_34], r14w
0x180012eac  lea     r8, aInitialpattern; "InitialPatternForInverseTelecine"
0x180012eb3  mov     rax, [rcx]
0x180012eb6  mov     [rsp+78h+var_58], rdx
0x180012ebb  mov     edx, [rbp+var_38]
0x180012ebe  mov     rax, [rax+70h]
0x180012ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec7  mov     r8d, [rbp+uValue]; uValue
0x180012ecb  mov     r9d, esi; bSigned
0x180012ece  mov     edx, 68h ; 'h'; nIDDlgItem
0x180012ed3  mov     rcx, r15; hDlg
0x180012ed6  call    cs:__imp_SetDlgItemInt
0x180012edc  mov     r8d, [rbp+var_30]; uValue
0x180012ee0  mov     r9d, esi; bSigned
0x180012ee3  mov     edx, 69h ; 'i'; nIDDlgItem
0x180012ee8  mov     rcx, r15; hDlg
0x180012eeb  call    cs:__imp_SetDlgItemInt
0x180012ef1  mov     rcx, [rdi+60h]
0x180012ef5  lea     r8, [rbp+Translated]
0x180012ef9  mov     [rbp+Translated], 0
0x180012f00  xor     r9d, r9d
0x180012f03  mov     rax, [rcx]
0x180012f06  lea     edx, [r9+2]
0x180012f0a  mov     rax, [rax+68h]
0x180012f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f13  movsxd  r8, [rbp+Translated]; wParam
0x180012f17  xor     r9d, r9d; lParam
0x180012f1a  mov     rcx, [rdi+58h]; hWnd
0x180012f1e  mov     edx, 0F1h; Msg
0x180012f23  call    cs:__imp_SendMessageW
0x180012f29  mov     rax, rsi
0x180012f2c  mov     rcx, [rbp+var_18]
0x180012f30  xor     rcx, rsp; StackCookie
0x180012f33  call    __security_check_cookie
0x180012f38  add     rsp, 78h
0x180012f3c  pop     r15
0x180012f3e  pop     r14
0x180012f40  pop     r12
0x180012f42  pop     rdi
0x180012f43  pop     rsi
0x180012f44  pop     rbp
0x180012f45  retn
```
