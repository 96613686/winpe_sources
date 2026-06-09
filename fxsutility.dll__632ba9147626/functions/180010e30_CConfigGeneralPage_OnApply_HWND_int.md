# CConfigGeneralPage::OnApply(HWND__ *,int &)

- ea: `0x180010e30`
- end: `0x180010fed`
- name: `?OnApply@CConfigGeneralPage@@UEAAKPEAUHWND__@@AEAH@Z`
- size: `445`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180010e30`
- `0x180017010`

## import_xrefs

- `FXSAPI!FaxSetPortExW` at `0x180010f17`
- `FXSAPI!FaxSetPortExW` at `0x180010f17`
- `KERNEL32!GetLastError` at `0x180010f25`
- `KERNEL32!GetLastError` at `0x180010f25`
- `USER32!GetDlgItemInt` at `0x180010ede`
- `USER32!GetDlgItemInt` at `0x180010ede`
- `USER32!IsDlgButtonChecked` at `0x180010ea8`
- `USER32!IsDlgButtonChecked` at `0x180010ebb`
- `USER32!IsDlgButtonChecked` at `0x180010eef`
- `USER32!IsDlgButtonChecked` at `0x180010ea8`
- `USER32!IsDlgButtonChecked` at `0x180010ebb`
- `USER32!IsDlgButtonChecked` at `0x180010eef`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::OnApply(CConfigGeneralPage *this, HWND a2, int *a3)
{
  int v6; // ebx
  UINT DlgItemInt; // r14d
  UINT v8; // eax
  DWORD LastError; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  *a3 = 0;
  if ( !*((_DWORD *)this + 32) || !*((_DWORD *)this + 13) )
    return 0;
  v6 = 0;
  DlgItemInt = 0;
  if ( IsDlgButtonChecked(a2, 4507) == 1 )
  {
    if ( IsDlgButtonChecked(a2, 4508) == 1 )
    {
      v6 = 2;
    }
    else
    {
      v6 = 1;
      DlgItemInt = GetDlgItemInt(a2, 4510, 0, 0);
    }
  }
  v8 = IsDlgButtonChecked(a2, 4506);
  *((_DWORD *)this + 23) = v6;
  *((_DWORD *)this + 22) = v8 == 1;
  if ( v6 == 1 )
    *((_DWORD *)this + 25) = DlgItemInt;
  if ( (unsigned int)FaxSetPortExW(*((_QWORD *)this + 15), *((unsigned int *)this + 13), (char *)this + 48) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
      }
      *a3 = 1;
      if ( LastError != 1003 )
      {
        (*(__int64 (__fastcall **)(CConfigGeneralPage *, _QWORD))(*(_QWORD *)this + 48LL))(this, LastError);
        FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180010e30  push    rbx
0x180010e32  push    rbp
0x180010e33  push    rsi
0x180010e34  push    rdi
0x180010e35  push    r14
0x180010e37  push    r15
0x180010e39  sub     rsp, 38h
0x180010e3d  mov     r15, r8
0x180010e40  mov     rbp, rdx
0x180010e43  mov     rdi, rcx
0x180010e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e4d  lea     rax, WPP_GLOBAL_Control
0x180010e54  cmp     rcx, rax
0x180010e57  jz      short loc_180010E7D
0x180010e59  test    dword ptr [rcx+1Ch], 100h
0x180010e60  jz      short loc_180010E7D
0x180010e62  cmp     byte ptr [rcx+19h], 5
0x180010e66  jb      short loc_180010E7D
0x180010e68  mov     rcx, [rcx+10h]
0x180010e6c  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010e73  mov     edx, 23h ; '#'
0x180010e78  call    WPP_SF_
0x180010e7d  mov     dword ptr [r15], 0
0x180010e84  cmp     dword ptr [rdi+80h], 0
0x180010e8b  jz      loc_180010FDE
0x180010e91  cmp     dword ptr [rdi+34h], 0
0x180010e95  jz      loc_180010FDE
0x180010e9b  mov     edx, 119Bh; nIDButton
0x180010ea0  mov     rcx, rbp; hDlg
0x180010ea3  xor     ebx, ebx
0x180010ea5  xor     r14d, r14d
0x180010ea8  call    cs:__imp_IsDlgButtonChecked
0x180010eae  cmp     eax, 1
0x180010eb1  jnz     short loc_180010EE7
0x180010eb3  mov     edx, 119Ch; nIDButton
0x180010eb8  mov     rcx, rbp; hDlg
0x180010ebb  call    cs:__imp_IsDlgButtonChecked
0x180010ec1  cmp     eax, 1
0x180010ec4  jnz     short loc_180010ECB
0x180010ec6  lea     ebx, [rax+1]
0x180010ec9  jmp     short loc_180010EE7
0x180010ecb  xor     r9d, r9d; bSigned
0x180010ece  xor     r8d, r8d; lpTranslated
0x180010ed1  mov     edx, 119Eh; nIDDlgItem
0x180010ed6  mov     rcx, rbp; hDlg
0x180010ed9  mov     ebx, 1
0x180010ede  call    cs:__imp_GetDlgItemInt
0x180010ee4  mov     r14d, eax
0x180010ee7  mov     edx, 119Ah; nIDButton
0x180010eec  mov     rcx, rbp; hDlg
0x180010eef  call    cs:__imp_IsDlgButtonChecked
0x180010ef5  xor     ecx, ecx
0x180010ef7  mov     [rdi+5Ch], ebx
0x180010efa  cmp     eax, 1
0x180010efd  setz    cl
0x180010f00  mov     [rdi+58h], ecx
0x180010f03  cmp     ebx, 1
0x180010f06  jnz     short loc_180010F0C
0x180010f08  mov     [rdi+64h], r14d
0x180010f0c  mov     edx, [rdi+34h]
0x180010f0f  lea     r8, [rdi+30h]
0x180010f13  mov     rcx, [rdi+78h]
0x180010f17  call    cs:__imp_FaxSetPortExW
0x180010f1d  test    eax, eax
0x180010f1f  jnz     loc_180010FD8
0x180010f25  call    cs:__imp_GetLastError
0x180010f2b  mov     ebx, eax
0x180010f2d  test    eax, eax
0x180010f2f  jz      loc_180010FDA
0x180010f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f3c  lea     rax, WPP_GLOBAL_Control
0x180010f43  cmp     rcx, rax
0x180010f46  jz      short loc_180010F6F
0x180010f48  test    dword ptr [rcx+1Ch], 100h
0x180010f4f  jz      short loc_180010F6F
0x180010f51  cmp     byte ptr [rcx+19h], 2
0x180010f55  jb      short loc_180010F6F
0x180010f57  mov     rcx, [rcx+10h]
0x180010f5b  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010f62  mov     edx, 25h ; '%'
0x180010f67  mov     r9d, ebx
0x180010f6a  call    WPP_SF_d
0x180010f6f  mov     dword ptr [r15], 1
0x180010f76  cmp     ebx, 3EBh
0x180010f7c  jz      short loc_180010FDA
0x180010f7e  mov     rax, [rdi]
0x180010f81  mov     edx, ebx
0x180010f83  mov     rcx, rdi
0x180010f86  mov     rax, [rax+30h]
0x180010f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8f  test    eax, eax
0x180010f91  jnz     short loc_180010FB9
0x180010f93  cmp     ebx, 5
0x180010f96  jz      short loc_180010FB4
0x180010f98  cmp     ebx, 8
0x180010f9b  jz      short loc_180010FAD
0x180010f9d  mov     eax, 1234h
0x180010fa2  cmp     ebx, 7Ah ; 'z'
0x180010fa5  lea     ecx, [rax+2]
0x180010fa8  cmovnz  eax, ecx
0x180010fab  jmp     short loc_180010FB9
0x180010fad  mov     eax, 1237h
0x180010fb2  jmp     short loc_180010FB9
0x180010fb4  mov     eax, 1235h
0x180010fb9  mov     rdx, [rdi+8]
0x180010fbd  mov     r9d, eax
0x180010fc0  mov     r8d, 1230h
0x180010fc6  mov     [rsp+68h+var_48], 10h
0x180010fce  mov     rcx, rbp
0x180010fd1  call    FaxMsgBox
0x180010fd6  jmp     short loc_180010FDA
0x180010fd8  xor     ebx, ebx
0x180010fda  mov     eax, ebx
0x180010fdc  jmp     short loc_180010FE0
0x180010fde  xor     eax, eax
0x180010fe0  add     rsp, 38h
0x180010fe4  pop     r15
0x180010fe6  pop     r14
0x180010fe8  pop     rdi
0x180010fe9  pop     rsi
0x180010fea  pop     rbp
0x180010feb  pop     rbx
0x180010fec  retn
```
