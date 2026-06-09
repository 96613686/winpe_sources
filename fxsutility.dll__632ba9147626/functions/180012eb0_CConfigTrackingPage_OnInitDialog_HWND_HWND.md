# CConfigTrackingPage::OnInitDialog(HWND__ *,HWND__ * &)

- ea: `0x180012eb0`
- end: `0x180012f81`
- name: `?OnInitDialog@CConfigTrackingPage@@UEAAKPEAUHWND__@@AEAPEAU2@@Z`
- size: `209`
- prototype: `unsigned int(CConfigTrackingPage *__hidden this, HWND, HWND *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180012eb0`

## import_xrefs

- `USER32!CheckDlgButton` at `0x180012f0a`
- `USER32!CheckDlgButton` at `0x180012f23`
- `USER32!CheckDlgButton` at `0x180012f3c`
- `USER32!CheckDlgButton` at `0x180012f55`
- `USER32!CheckDlgButton` at `0x180012f6e`
- `USER32!CheckDlgButton` at `0x180012f0a`
- `USER32!CheckDlgButton` at `0x180012f23`
- `USER32!CheckDlgButton` at `0x180012f3c`
- `USER32!CheckDlgButton` at `0x180012f55`
- `USER32!CheckDlgButton` at `0x180012f6e`

## pseudocode

```c
__int64 __fastcall CConfigTrackingPage::OnInitDialog(CConfigTrackingPage *this, HWND a2, HWND *a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  CheckDlgButton(a2, 4564, *((_DWORD *)this + 9) != 0);
  CheckDlgButton(a2, 4565, *((_DWORD *)this + 10) != 0);
  CheckDlgButton(a2, 4566, *((_DWORD *)this + 11) != 0);
  CheckDlgButton(a2, 4569, *((_DWORD *)this + 12) != 0);
  CheckDlgButton(a2, 4570, *((_DWORD *)this + 13) != 0);
  return 0;
}

```

## disassembly

```asm
0x180012eb0  mov     [rsp+arg_0], rbx
0x180012eb5  push    rdi
0x180012eb6  sub     rsp, 20h
0x180012eba  mov     rbx, rdx
0x180012ebd  mov     rdi, rcx
0x180012ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ec7  lea     rax, WPP_GLOBAL_Control
0x180012ece  cmp     rcx, rax
0x180012ed1  jz      short loc_180012EF7
0x180012ed3  test    dword ptr [rcx+1Ch], 100h
0x180012eda  jz      short loc_180012EF7
0x180012edc  cmp     byte ptr [rcx+19h], 5
0x180012ee0  jb      short loc_180012EF7
0x180012ee2  mov     rcx, [rcx+10h]
0x180012ee6  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012eed  mov     edx, 0Ch
0x180012ef2  call    WPP_SF_
0x180012ef7  xor     r8d, r8d
0x180012efa  mov     edx, 11D4h; nIDButton
0x180012eff  cmp     [rdi+24h], r8d
0x180012f03  mov     rcx, rbx; hDlg
0x180012f06  setnz   r8b; uCheck
0x180012f0a  call    cs:__imp_CheckDlgButton
0x180012f10  xor     r8d, r8d
0x180012f13  mov     edx, 11D5h; nIDButton
0x180012f18  cmp     [rdi+28h], r8d
0x180012f1c  mov     rcx, rbx; hDlg
0x180012f1f  setnz   r8b; uCheck
0x180012f23  call    cs:__imp_CheckDlgButton
0x180012f29  xor     r8d, r8d
0x180012f2c  mov     edx, 11D6h; nIDButton
0x180012f31  cmp     [rdi+2Ch], r8d
0x180012f35  mov     rcx, rbx; hDlg
0x180012f38  setnz   r8b; uCheck
0x180012f3c  call    cs:__imp_CheckDlgButton
0x180012f42  xor     r8d, r8d
0x180012f45  mov     edx, 11D9h; nIDButton
0x180012f4a  cmp     [rdi+30h], r8d
0x180012f4e  mov     rcx, rbx; hDlg
0x180012f51  setnz   r8b; uCheck
0x180012f55  call    cs:__imp_CheckDlgButton
0x180012f5b  xor     r8d, r8d
0x180012f5e  mov     edx, 11DAh; nIDButton
0x180012f63  cmp     [rdi+34h], r8d
0x180012f67  mov     rcx, rbx; hDlg
0x180012f6a  setnz   r8b; uCheck
0x180012f6e  call    cs:__imp_CheckDlgButton
0x180012f74  mov     rbx, [rsp+28h+arg_0]
0x180012f79  xor     eax, eax
0x180012f7b  add     rsp, 20h
0x180012f7f  pop     rdi
0x180012f80  retn
```
