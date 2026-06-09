# CConfigTrackingPage::OnApply(HWND__ *,int &)

- ea: `0x180012a40`
- end: `0x180012bc1`
- name: `?OnApply@CConfigTrackingPage@@UEAAKPEAUHWND__@@AEAH@Z`
- size: `385`
- prototype: `unsigned int(CConfigTrackingPage *__hidden this, HWND, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180012a40`
- `0x1800157a4`
- `0x180017010`

## import_xrefs

- `USER32!IsDlgButtonChecked` at `0x180012a93`
- `USER32!IsDlgButtonChecked` at `0x180012aac`
- `USER32!IsDlgButtonChecked` at `0x180012ac5`
- `USER32!IsDlgButtonChecked` at `0x180012ade`
- `USER32!IsDlgButtonChecked` at `0x180012af7`
- `USER32!IsDlgButtonChecked` at `0x180012a93`
- `USER32!IsDlgButtonChecked` at `0x180012aac`
- `USER32!IsDlgButtonChecked` at `0x180012ac5`
- `USER32!IsDlgButtonChecked` at `0x180012ade`
- `USER32!IsDlgButtonChecked` at `0x180012af7`

## pseudocode

```c
__int64 __fastcall CConfigTrackingPage::OnApply(CConfigTrackingPage *this, HWND a2, int *a3)
{
  _BOOL8 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  *((_DWORD *)this + 9) = IsDlgButtonChecked(a2, 4564) == 1;
  *((_DWORD *)this + 10) = IsDlgButtonChecked(a2, 4565) == 1;
  *((_DWORD *)this + 11) = IsDlgButtonChecked(a2, 4566) == 1;
  *((_DWORD *)this + 12) = IsDlgButtonChecked(a2, 4569) == 1;
  v6 = IsDlgButtonChecked(a2, 4570) == 1;
  *((_DWORD *)this + 13) = v6;
  v7 = SaveTrackingOptions((int *)this + 8, v6);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids, v7);
    }
    *a3 = 1;
    (*(__int64 (__fastcall **)(CConfigTrackingPage *, _QWORD))(*(_QWORD *)this + 48LL))(this, v8);
    FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
  }
  else
  {
    *a3 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180012a40  push    rbx
0x180012a42  push    rbp
0x180012a43  push    rsi
0x180012a44  push    rdi
0x180012a45  push    r12
0x180012a47  sub     rsp, 30h
0x180012a4b  mov     rsi, r8
0x180012a4e  mov     rbp, rdx
0x180012a51  mov     rdi, rcx
0x180012a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a5b  lea     r12, WPP_GLOBAL_Control
0x180012a62  cmp     rcx, r12
0x180012a65  jz      short loc_180012A8B
0x180012a67  test    dword ptr [rcx+1Ch], 100h
0x180012a6e  jz      short loc_180012A8B
0x180012a70  cmp     byte ptr [rcx+19h], 5
0x180012a74  jb      short loc_180012A8B
0x180012a76  mov     rcx, [rcx+10h]
0x180012a7a  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012a81  mov     edx, 0Eh
0x180012a86  call    WPP_SF_
0x180012a8b  mov     edx, 11D4h; nIDButton
0x180012a90  mov     rcx, rbp; hDlg
0x180012a93  call    cs:__imp_IsDlgButtonChecked
0x180012a99  xor     ecx, ecx
0x180012a9b  mov     edx, 11D5h; nIDButton
0x180012aa0  cmp     eax, 1
0x180012aa3  setz    cl
0x180012aa6  mov     [rdi+24h], ecx
0x180012aa9  mov     rcx, rbp; hDlg
0x180012aac  call    cs:__imp_IsDlgButtonChecked
0x180012ab2  xor     ecx, ecx
0x180012ab4  mov     edx, 11D6h; nIDButton
0x180012ab9  cmp     eax, 1
0x180012abc  setz    cl
0x180012abf  mov     [rdi+28h], ecx
0x180012ac2  mov     rcx, rbp; hDlg
0x180012ac5  call    cs:__imp_IsDlgButtonChecked
0x180012acb  xor     ecx, ecx
0x180012acd  mov     edx, 11D9h; nIDButton
0x180012ad2  cmp     eax, 1
0x180012ad5  setz    cl
0x180012ad8  mov     [rdi+2Ch], ecx
0x180012adb  mov     rcx, rbp; hDlg
0x180012ade  call    cs:__imp_IsDlgButtonChecked
0x180012ae4  xor     edx, edx
0x180012ae6  mov     rcx, rbp; hDlg
0x180012ae9  cmp     eax, 1
0x180012aec  setz    dl
0x180012aef  mov     [rdi+30h], edx
0x180012af2  mov     edx, 11DAh; nIDButton
0x180012af7  call    cs:__imp_IsDlgButtonChecked
0x180012afd  xor     edx, edx
0x180012aff  lea     rcx, [rdi+20h]
0x180012b03  cmp     eax, 1
0x180012b06  setz    dl
0x180012b09  mov     [rdi+34h], edx
0x180012b0c  call    SaveTrackingOptions
0x180012b11  mov     ebx, eax
0x180012b13  test    eax, eax
0x180012b15  jz      loc_180012BAE
0x180012b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b22  cmp     rcx, r12
0x180012b25  jz      short loc_180012B4E
0x180012b27  test    dword ptr [rcx+1Ch], 100h
0x180012b2e  jz      short loc_180012B4E
0x180012b30  cmp     byte ptr [rcx+19h], 2
0x180012b34  jb      short loc_180012B4E
0x180012b36  mov     rcx, [rcx+10h]
0x180012b3a  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012b41  mov     edx, 10h
0x180012b46  mov     r9d, eax
0x180012b49  call    WPP_SF_d
0x180012b4e  mov     dword ptr [rsi], 1
0x180012b54  mov     edx, ebx
0x180012b56  mov     rax, [rdi]
0x180012b59  mov     rcx, rdi
0x180012b5c  mov     rax, [rax+30h]
0x180012b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b65  test    eax, eax
0x180012b67  jnz     short loc_180012B8F
0x180012b69  cmp     ebx, 5
0x180012b6c  jz      short loc_180012B8A
0x180012b6e  cmp     ebx, 8
0x180012b71  jz      short loc_180012B83
0x180012b73  mov     eax, 1234h
0x180012b78  cmp     ebx, 7Ah ; 'z'
0x180012b7b  lea     ecx, [rax+2]
0x180012b7e  cmovnz  eax, ecx
0x180012b81  jmp     short loc_180012B8F
0x180012b83  mov     eax, 1237h
0x180012b88  jmp     short loc_180012B8F
0x180012b8a  mov     eax, 1235h
0x180012b8f  mov     rdx, [rdi+8]
0x180012b93  mov     r9d, eax
0x180012b96  mov     r8d, 1230h
0x180012b9c  mov     [rsp+58h+var_38], 10h
0x180012ba4  mov     rcx, rbp
0x180012ba7  call    FaxMsgBox
0x180012bac  jmp     short loc_180012BB4
0x180012bae  mov     dword ptr [rsi], 0
0x180012bb4  mov     eax, ebx
0x180012bb6  add     rsp, 30h
0x180012bba  pop     r12
0x180012bbc  pop     rdi
0x180012bbd  pop     rsi
0x180012bbe  pop     rbp
0x180012bbf  pop     rbx
0x180012bc0  retn
```
