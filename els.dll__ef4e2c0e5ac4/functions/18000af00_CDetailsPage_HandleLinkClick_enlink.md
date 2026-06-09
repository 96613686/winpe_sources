# CDetailsPage::_HandleLinkClick(_enlink *)

- ea: `0x18000af00`
- end: `0x18000b0c8`
- name: `?_HandleLinkClick@CDetailsPage@@AEAAXPEAU_enlink@@@Z`
- size: `456`
- prototype: `void __fastcall(CDetailsPage *__hidden this, struct _enlink *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b530`

## callees

- `0x180002bb8`
- `0x18000af00`
- `0x18000bfe0`
- `0x18000f8f4`
- `0x180010710`
- `0x180010b0c`
- `0x18001abd8`
- `0x18001ae60`
- `0x18001aef4`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcschr` at `0x18000afa2`
- `msvcrt!wcschr` at `0x18000afb7`
- `msvcrt!wcschr` at `0x18000afa2`
- `msvcrt!wcschr` at `0x18000afb7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000afdf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b09b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000afdf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b09b`
- `USER32!SendMessageW` at `0x18000af96`
- `USER32!SendMessageW` at `0x18000af96`
- `USER32!GetDlgItem` at `0x18000af80`
- `USER32!GetDlgItem` at `0x18000af80`

## pseudocode

```c
void __fastcall CDetailsPage::_HandleLinkClick(CDetailsPage *this, struct _enlink *a2)
{
  unsigned int v3; // edi
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  HWND v7; // rcx
  HWND DlgItem; // rax
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  HWND v11; // rdx
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-D0h] BYREF
  LPARAM lParam[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[1024]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+460h] [rbp+360h]

  v3 = 1;
  v5 = (wchar_t *)operator new[](saturated_mul((unsigned int)(a2->chrg.cpMax - a2->chrg.cpMin + 1), 2u));
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    lParam[0] = (LPARAM)a2->chrg;
    v7 = (HWND)*((_QWORD *)this + 2);
    lParam[1] = (LPARAM)v5;
    DlgItem = GetDlgItem(v7, 127);
    SendMessageW(DlgItem, 0x44Bu, 0, (LPARAM)lParam);
    v9 = wcschr(v6, 0x3Au);
    if ( v9 )
    {
      v10 = wcschr(v9, 0x3Fu);
      if ( v10 )
        *v10 = 0;
      CEventUrl::CEventUrl(v16, v6, *((_QWORD *)this + 6), (char *)this + 112);
      operator delete[](v6);
      v6 = 0;
      v14[0] = &CConfirmUrlDlg::`vftable';
      v14[1] = 0;
      if ( !v17 )
        goto LABEL_11;
      v13 = 0;
      if ( CSafeReg::Open(
             (CSafeReg *)&v13,
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Event Viewer",
             0x20019u) >= 0 )
      {
        v12 = 0;
        if ( (int)CSafeReg::QueryDword((CSafeReg *)&v13, L"ConfirmUrl", &v12) >= 0 )
          v3 = v12;
      }
      CSafeReg::Close((CSafeReg *)&v13);
      if ( !v3
        || (v11 = (HWND)*((_QWORD *)this + 2), v14[2] = v16, (unsigned int)CDlg::_DoModalDlg((CDlg *)v14, v11, 108)) )
      {
LABEL_11:
        CEventUrl::Invoke((CEventUrl *)v16);
      }
      v14[0] = &CDlg::`vftable';
      CEventUrl::~CEventUrl((CEventUrl *)v16);
    }
  }
  operator delete[](v6);
}

```

## disassembly

```asm
0x18000af00  mov     [rsp-8+arg_10], rbx
0x18000af05  mov     [rsp-8+arg_18], rsi
0x18000af0a  push    rbp
0x18000af0b  push    rdi
0x18000af0c  push    r14
0x18000af0e  lea     rbp, [rsp-3A0h]
0x18000af16  sub     rsp, 4A0h
0x18000af1d  mov     rax, cs:__security_cookie
0x18000af24  xor     rax, rsp
0x18000af27  mov     [rbp+3B0h+var_20], rax
0x18000af2e  mov     rsi, rcx
0x18000af31  mov     edi, 1
0x18000af36  mov     ecx, [rdx+30h]
0x18000af39  mov     r14, rdx
0x18000af3c  sub     ecx, [rdx+2Ch]
0x18000af3f  add     ecx, edi
0x18000af41  lea     eax, [rdi+1]
0x18000af44  mul     rcx
0x18000af47  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000af4e  cmovb   rax, rcx
0x18000af52  mov     rcx, rax; unsigned __int64
0x18000af55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000af5a  mov     rbx, rax
0x18000af5d  test    rax, rax
0x18000af60  jz      loc_18000B098
0x18000af66  xor     ecx, ecx
0x18000af68  lea     edx, [rdi+7Eh]; nIDDlgItem
0x18000af6b  mov     [rax], cx
0x18000af6e  mov     rcx, [r14+2Ch]
0x18000af72  mov     [rsp+4B0h+lParam], rcx
0x18000af77  mov     rcx, [rsi+10h]; hDlg
0x18000af7b  mov     [rsp+4B0h+var_460], rax
0x18000af80  call    cs:__imp_GetDlgItem
0x18000af86  lea     r9, [rsp+4B0h+lParam]; lParam
0x18000af8b  xor     r8d, r8d; wParam
0x18000af8e  mov     rcx, rax; hWnd
0x18000af91  mov     edx, 44Bh; Msg
0x18000af96  call    cs:__imp_SendMessageW
0x18000af9c  lea     edx, [rdi+39h]; Ch
0x18000af9f  mov     rcx, rbx; Str
0x18000afa2  call    cs:__imp_wcschr
0x18000afa8  test    rax, rax
0x18000afab  jz      loc_18000B098
0x18000afb1  lea     edx, [rdi+3Eh]; Ch
0x18000afb4  mov     rcx, rax; Str
0x18000afb7  call    cs:__imp_wcschr
0x18000afbd  test    rax, rax
0x18000afc0  jz      short loc_18000AFC7
0x18000afc2  xor     ecx, ecx
0x18000afc4  mov     [rax], cx
0x18000afc7  mov     r8, [rsi+30h]
0x18000afcb  lea     r9, [rsi+70h]
0x18000afcf  mov     rdx, rbx
0x18000afd2  lea     rcx, [rsp+4B0h+var_450]
0x18000afd7  call    ??0CEventUrl@@QEAA@PEBGPEAUIResultPrshtActions@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CEventUrl::CEventUrl(ushort const *,IResultPrshtActions *,std::wstring const &)
0x18000afdc  mov     rcx, rbx
0x18000afdf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000afe5  xor     ebx, ebx
0x18000afe7  lea     rax, ??_7CConfirmUrlDlg@@6B@; const CConfirmUrlDlg::`vftable'
0x18000afee  mov     [rsp+4B0h+var_480], rax
0x18000aff3  mov     [rsp+4B0h+var_478], rbx
0x18000aff8  cmp     [rbp+3B0h+var_50], ebx
0x18000affe  jz      short loc_18000B078
0x18000b000  mov     r9d, 20019h; unsigned int
0x18000b006  mov     [rsp+4B0h+var_488], rbx
0x18000b00b  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000b012  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x18000b019  lea     rcx, [rsp+4B0h+var_488]; this
0x18000b01e  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18000b023  test    eax, eax
0x18000b025  js      short loc_18000B048
0x18000b027  lea     r8, [rsp+4B0h+var_490]; unsigned int *
0x18000b02c  mov     [rsp+4B0h+var_490], ebx
0x18000b030  lea     rdx, aConfirmurl; "ConfirmUrl"
0x18000b037  lea     rcx, [rsp+4B0h+var_488]; this
0x18000b03c  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x18000b041  test    eax, eax
0x18000b043  cmovns  edi, [rsp+4B0h+var_490]
0x18000b048  lea     rcx, [rsp+4B0h+var_488]; this
0x18000b04d  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18000b052  test    edi, edi
0x18000b054  jz      short loc_18000B078
0x18000b056  mov     rdx, [rsi+10h]; HWND
0x18000b05a  lea     rax, [rsp+4B0h+var_450]
0x18000b05f  mov     r8d, 6Ch ; 'l'; int
0x18000b065  mov     [rsp+4B0h+var_470], rax
0x18000b06a  lea     rcx, [rsp+4B0h+var_480]; this
0x18000b06f  call    ?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z; CDlg::_DoModalDlg(HWND__ *,int)
0x18000b074  test    eax, eax
0x18000b076  jz      short loc_18000B082
0x18000b078  lea     rcx, [rsp+4B0h+var_450]; this
0x18000b07d  call    ?Invoke@CEventUrl@@QEBAXXZ; CEventUrl::Invoke(void)
0x18000b082  lea     rax, ??_7CDlg@@6B@; const CDlg::`vftable'
0x18000b089  lea     rcx, [rsp+4B0h+var_450]; this
0x18000b08e  mov     [rsp+4B0h+var_480], rax
0x18000b093  call    ??1CEventUrl@@QEAA@XZ; CEventUrl::~CEventUrl(void)
0x18000b098  mov     rcx, rbx
0x18000b09b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b0a1  mov     rcx, [rbp+3B0h+var_20]
0x18000b0a8  xor     rcx, rsp; StackCookie
0x18000b0ab  call    __security_check_cookie
0x18000b0b0  lea     r11, [rsp+4B0h+var_10]
0x18000b0b8  mov     rbx, [r11+30h]
0x18000b0bc  mov     rsi, [r11+38h]
0x18000b0c0  mov     rsp, r11
0x18000b0c3  pop     r14
0x18000b0c5  pop     rdi
0x18000b0c6  pop     rbp
0x18000b0c7  retn
```
