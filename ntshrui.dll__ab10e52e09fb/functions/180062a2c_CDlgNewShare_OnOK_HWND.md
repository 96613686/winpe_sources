# CDlgNewShare::_OnOK(HWND__ *)

- ea: `0x180062a2c`
- end: `0x180062d7d`
- name: `?_OnOK@CDlgNewShare@@AEAAHPEAUHWND__@@@Z`
- size: `849`
- prototype: `__int64 __fastcall(CDlgNewShare *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180062588`

## callees

- `0x1800115cc`
- `0x180011cb0`
- `0x180011df0`
- `0x18001d2d0`
- `0x1800254e0`
- `0x1800259bc`
- `0x180026394`
- `0x18005e42c`
- `0x18005e45c`
- `0x18005e4b4`
- `0x18005e51c`
- `0x18005e598`
- `0x180061250`
- `0x180061a50`
- `0x180062a2c`
- `0x180072674`
- `0x180073280`
- `0x18007337c`
- `0x180073488`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062ad9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062af4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062b21`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062b80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062bc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062ad9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062af4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062b21`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062b80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062bc0`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180062b6b`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180062b6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180062b07`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180062b07`
- `SHLWAPI!PathIsRootW` at `0x180062b5e`
- `SHLWAPI!PathIsRootW` at `0x180062b5e`
- `USER32!GetDlgItemTextW` at `0x180062a85`
- `USER32!GetDlgItemTextW` at `0x180062cf4`
- `USER32!GetDlgItemTextW` at `0x180062a85`
- `USER32!GetDlgItemTextW` at `0x180062cf4`
- `USER32!IsDlgButtonChecked` at `0x180062d0f`
- `USER32!IsDlgButtonChecked` at `0x180062d26`
- `USER32!IsDlgButtonChecked` at `0x180062d0f`
- `USER32!IsDlgButtonChecked` at `0x180062d26`
- `USER32!EndDialog` at `0x180062d4e`
- `USER32!EndDialog` at `0x180062d4e`

## pseudocode

```c
__int64 __fastcall CDlgNewShare::_OnOK(CShareInfo **this, HWND a2)
{
  unsigned int v4; // edx
  unsigned int v6; // ebx
  unsigned __int16 *Path; // rax
  unsigned int v8; // edx
  unsigned __int16 *v9; // rbx
  CShareCache *v10; // rcx
  CShareInfo *i; // rbx
  unsigned __int16 *Netname; // rax
  const unsigned __int16 *v13; // rax
  CShareInfo **v14; // rax
  CShareInfo **v15; // rdi
  int inited; // eax
  unsigned int v17; // edx
  CShareInfo *v18; // rcx
  int v19; // eax
  CShareInfo *v20; // rcx
  CShareInfo ***v21; // rax
  unsigned int v22; // edx
  WCHAR v23; // [rsp+28h] [rbp-D8h] BYREF
  int v24; // [rsp+2Ah] [rbp-D6h]
  WCHAR String[88]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v27[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(String, 0, 0xA2u);
  if ( !GetDlgItemTextW(a2, 1001, String, 81) )
  {
    MyErrorDialog(a2, -2147483380);
LABEL_3:
    SetErrorFocus(a2, v4);
    return 1;
  }
  TrimLeadingAndTrailingSpaces(String);
  if ( !(unsigned int)IsValidShareName(String) )
  {
    MyErrorDialog(a2, -2147483379);
    goto LABEL_3;
  }
  if ( (unsigned int)_o__wcsicmp(&g_szIpcShare, String) )
  {
    if ( !(unsigned int)_o__wcsicmp(&g_szAdminShare, String) )
    {
      if ( !GetWindowsDirectoryW(Buffer, 0x104u)
        || (Path = CShareInfo::GetPath(this[4]), (unsigned int)_o__wcsicmp(Path, Buffer)) )
      {
        v6 = 0;
        goto LABEL_12;
      }
    }
    v9 = CShareInfo::GetPath(this[4]);
    v23 = *v9;
    v24 = 36;
    if ( PathIsRootW(v9) && GetDriveTypeW(v9) == 3 && !(unsigned int)_o__wcsicmp(String, &v23) )
    {
LABEL_16:
      MyErrorDialog(a2, -2147483377, String);
      v6 = 1;
      goto LABEL_23;
    }
    for ( i = *(CShareInfo **)this[3]; i != this[3]; i = *(CShareInfo **)i )
    {
      Netname = CShareInfo::GetNetname(i);
      if ( !(unsigned int)_o__wcsicmp(Netname, String) )
        goto LABEL_16;
    }
    v6 = 1;
    if ( CShareCache::IsExistingShare(v10, String, v27, 257) )
    {
      v13 = CShareInfo::GetPath(this[4]);
      if ( ConfirmReplaceShare(a2, String, v27, v13) != 6 )
        goto LABEL_23;
      v14 = (CShareInfo **)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      v15 = v14;
      if ( !v14 )
        return 0;
      v14[2] = (CShareInfo *)1;
      v14[3] = 0;
      *((_DWORD *)v14 + 8) = -1;
      *v14 = (CShareInfo *)v14;
      v14[1] = (CShareInfo *)v14;
      inited = CShareInfo::InitInstance((CShareInfo *)v14);
      v18 = (CShareInfo *)v15;
      if ( inited < 0 || (v19 = CShareInfo::SetNetname((CShareInfo *)v15, String), v18 = (CShareInfo *)v15, v19 < 0) )
      {
LABEL_26:
        CShareInfo::`scalar deleting destructor'(v18, v17);
        return 0;
      }
      if ( CShareInfo::SetPath((CShareInfo *)v15, v27) < 0 )
      {
        v18 = (CShareInfo *)v15;
        goto LABEL_26;
      }
      *((_DWORD *)v15 + 5) = 2;
      v20 = this[5];
      v21 = (CShareInfo ***)*((_QWORD *)v20 + 1);
      *v15 = v20;
      v15[1] = (CShareInfo *)v21;
      *((_QWORD *)v20 + 1) = v15;
      *v21 = v15;
    }
    if ( *((_DWORD *)this + 12) )
      CShareInfo::SetNetname(this[4], String);
    if ( *((_DWORD *)this + 13) )
    {
      Buffer[0] = 0;
      GetDlgItemTextW(a2, 1002, Buffer, 257);
      CShareInfo::SetRemark(this[4], Buffer);
    }
    if ( IsDlgButtonChecked(a2, 1006) == 1 )
    {
      v22 = -1;
    }
    else
    {
      if ( IsDlgButtonChecked(a2, 1007) != 1 )
      {
LABEL_41:
        EndDialog(a2, 1);
        return v6;
      }
      CDlgNewShare::_CacheMaxUses((CDlgNewShare *)this, a2);
      v22 = *((_DWORD *)this + 14);
    }
    CShareInfo::SetMaxUses(this[4], v22);
    goto LABEL_41;
  }
  v6 = 1;
LABEL_12:
  MyErrorDialog(a2, -2147483375);
LABEL_23:
  SetErrorFocus(a2, v8);
  return v6;
}

```

## disassembly

```asm
0x180062a2c  mov     [rsp-8+arg_10], rbx
0x180062a31  mov     [rsp-8+arg_18], rsi
0x180062a36  push    rbp
0x180062a37  push    rdi
0x180062a38  push    r14
0x180062a3a  lea     rbp, [rsp-410h]
0x180062a42  sub     rsp, 510h
0x180062a49  mov     rax, cs:__security_cookie
0x180062a50  xor     rax, rsp
0x180062a53  mov     [rbp+420h+var_20], rax
0x180062a5a  mov     rsi, rdx
0x180062a5d  mov     r14, rcx
0x180062a60  xor     edx, edx; Val
0x180062a62  lea     rcx, [rsp+520h+String]; void *
0x180062a67  mov     r8d, 0A2h; Size
0x180062a6d  call    memset_0
0x180062a72  mov     r9d, 51h ; 'Q'; cchMax
0x180062a78  lea     r8, [rsp+520h+String]; lpString
0x180062a7d  mov     edx, 3E9h; nIDDlgItem
0x180062a82  mov     rcx, rsi; hDlg
0x180062a85  call    cs:__imp_GetDlgItemTextW
0x180062a8b  test    eax, eax
0x180062a8d  jnz     short loc_180062AAE
0x180062a8f  mov     edx, 8000010Ch; int
0x180062a94  mov     rcx, rsi; HWND
0x180062a97  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180062a9c  mov     rcx, rsi; HWND
0x180062a9f  call    ?SetErrorFocus@@YAXPEAUHWND__@@I@Z; SetErrorFocus(HWND__ *,uint)
0x180062aa4  mov     eax, 1
0x180062aa9  jmp     loc_180062D56
0x180062aae  lea     rcx, [rsp+520h+String]; unsigned __int16 *
0x180062ab3  call    ?TrimLeadingAndTrailingSpaces@@YAXPEAG@Z; TrimLeadingAndTrailingSpaces(ushort *)
0x180062ab8  lea     rcx, [rsp+520h+String]; unsigned __int16 *
0x180062abd  call    ?IsValidShareName@@YAHPEBG@Z; IsValidShareName(ushort const *)
0x180062ac2  test    eax, eax
0x180062ac4  jnz     short loc_180062ACD
0x180062ac6  mov     edx, 8000010Dh
0x180062acb  jmp     short loc_180062A94
0x180062acd  lea     rdx, [rsp+520h+String]
0x180062ad2  lea     rcx, ?g_szIpcShare@@3PAGA; "IPC$"
0x180062ad9  call    cs:__imp__o__wcsicmp
0x180062adf  test    eax, eax
0x180062ae1  jnz     short loc_180062AE8
0x180062ae3  lea     ebx, [rax+1]
0x180062ae6  jmp     short loc_180062B2D
0x180062ae8  lea     rdx, [rsp+520h+String]
0x180062aed  lea     rcx, ?g_szAdminShare@@3PAGA; "ADMIN$"
0x180062af4  call    cs:__imp__o__wcsicmp
0x180062afa  test    eax, eax
0x180062afc  jnz     short loc_180062B3F
0x180062afe  mov     edx, 104h; uSize
0x180062b03  lea     rcx, [rbp+420h+Buffer]; lpBuffer
0x180062b07  call    cs:__imp_GetWindowsDirectoryW
0x180062b0d  test    eax, eax
0x180062b0f  jz      short loc_180062B2B
0x180062b11  mov     rcx, [r14+20h]; this
0x180062b15  call    ?GetPath@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetPath(void)
0x180062b1a  mov     rcx, rax
0x180062b1d  lea     rdx, [rbp+420h+Buffer]
0x180062b21  call    cs:__imp__o__wcsicmp
0x180062b27  test    eax, eax
0x180062b29  jz      short loc_180062B3F
0x180062b2b  xor     ebx, ebx
0x180062b2d  mov     edx, 80000111h; int
0x180062b32  mov     rcx, rsi; HWND
0x180062b35  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180062b3a  jmp     loc_180062C18
0x180062b3f  mov     rcx, [r14+20h]; this
0x180062b43  call    ?GetPath@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetPath(void)
0x180062b48  mov     rbx, rax
0x180062b4b  movzx   ecx, word ptr [rax]
0x180062b4e  mov     [rsp+520h+var_4F8], cx
0x180062b53  mov     rcx, rax; pszPath
0x180062b56  mov     [rsp+520h+var_4F6], 24h ; '$'
0x180062b5e  call    cs:__imp_PathIsRootW
0x180062b64  test    eax, eax
0x180062b66  jz      short loc_180062BA3
0x180062b68  mov     rcx, rbx; lpRootPathName
0x180062b6b  call    cs:__imp_GetDriveTypeW
0x180062b71  cmp     eax, 3
0x180062b74  jnz     short loc_180062BA3
0x180062b76  lea     rdx, [rsp+520h+var_4F8]
0x180062b7b  lea     rcx, [rsp+520h+String]
0x180062b80  call    cs:__imp__o__wcsicmp
0x180062b86  test    eax, eax
0x180062b88  jnz     short loc_180062BA3
0x180062b8a  lea     r8, [rsp+520h+String]
0x180062b8f  mov     edx, 8000010Fh; int
0x180062b94  mov     rcx, rsi; HWND
0x180062b97  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180062b9c  mov     ebx, 1
0x180062ba1  jmp     short loc_180062C18
0x180062ba3  mov     rax, [r14+18h]
0x180062ba7  mov     rbx, [rax]
0x180062baa  cmp     rbx, [r14+18h]
0x180062bae  jz      short loc_180062BCF
0x180062bb0  mov     rcx, rbx; this
0x180062bb3  call    ?GetNetname@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetNetname(void)
0x180062bb8  mov     rcx, rax
0x180062bbb  lea     rdx, [rsp+520h+String]
0x180062bc0  call    cs:__imp__o__wcsicmp
0x180062bc6  test    eax, eax
0x180062bc8  jz      short loc_180062B8A
0x180062bca  mov     rbx, [rbx]
0x180062bcd  jmp     short loc_180062BAA
0x180062bcf  mov     r9d, 101h; int
0x180062bd5  lea     r8, [rbp+420h+var_230]; unsigned __int16 *
0x180062bdc  lea     rdx, [rsp+520h+String]; unsigned __int16 *
0x180062be1  call    ?IsExistingShare@CShareCache@@QEAAHPEBGPEAGH@Z; CShareCache::IsExistingShare(ushort const *,ushort *,int)
0x180062be6  mov     ebx, 1
0x180062beb  test    eax, eax
0x180062bed  jz      loc_180062CC0
0x180062bf3  mov     rcx, [r14+20h]; this
0x180062bf7  call    ?GetPath@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetPath(void)
0x180062bfc  mov     r9, rax; unsigned __int16 *
0x180062bff  lea     rdx, [rsp+520h+String]; unsigned __int16 *
0x180062c04  lea     r8, [rbp+420h+var_230]; unsigned __int16 *
0x180062c0b  mov     rcx, rsi; HWND
0x180062c0e  call    ?ConfirmReplaceShare@@YAKPEAUHWND__@@PEBG11@Z; ConfirmReplaceShare(HWND__ *,ushort const *,ushort const *,ushort const *)
0x180062c13  cmp     eax, 6
0x180062c16  jz      short loc_180062C25
0x180062c18  mov     rcx, rsi; HWND
0x180062c1b  call    ?SetErrorFocus@@YAXPEAUHWND__@@I@Z; SetErrorFocus(HWND__ *,uint)
0x180062c20  jmp     loc_180062D54
0x180062c25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180062c2c  mov     ecx, 28h ; '('; unsigned __int64
0x180062c31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180062c36  mov     [rsp+520h+var_500], rax
0x180062c3b  mov     rdi, rax
0x180062c3e  test    rax, rax
0x180062c41  jz      short loc_180062C76
0x180062c43  mov     [rax+10h], rbx
0x180062c47  mov     qword ptr [rax+18h], 0
0x180062c4f  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x180062c56  mov     [rax], rax
0x180062c59  mov     [rax+8], rax
0x180062c5d  test    rax, rax
0x180062c60  jz      short loc_180062C76
0x180062c62  mov     rcx, rax; this
0x180062c65  call    ?InitInstance@CShareInfo@@QEAAJXZ; CShareInfo::InitInstance(void)
0x180062c6a  mov     rcx, rdi; this
0x180062c6d  test    eax, eax
0x180062c6f  jns     short loc_180062C7D
0x180062c71  call    ??_GCShareInfo@@QEAAPEAXI@Z; CShareInfo::`scalar deleting destructor'(uint)
0x180062c76  xor     eax, eax
0x180062c78  jmp     loc_180062D56
0x180062c7d  lea     rdx, [rsp+520h+String]; unsigned __int16 *
0x180062c82  call    ?SetNetname@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetNetname(ushort const *)
0x180062c87  mov     rcx, rdi; this
0x180062c8a  test    eax, eax
0x180062c8c  js      short loc_180062C71
0x180062c8e  lea     rdx, [rbp+420h+var_230]; unsigned __int16 *
0x180062c95  call    ?SetPath@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetPath(ushort const *)
0x180062c9a  test    eax, eax
0x180062c9c  jns     short loc_180062CA3
0x180062c9e  mov     rcx, rdi
0x180062ca1  jmp     short loc_180062C71
0x180062ca3  mov     dword ptr [rdi+14h], 2
0x180062caa  mov     rcx, [r14+28h]
0x180062cae  mov     rax, [rcx+8]
0x180062cb2  mov     [rdi], rcx
0x180062cb5  mov     [rdi+8], rax
0x180062cb9  mov     [rcx+8], rdi
0x180062cbd  mov     [rax], rdi
0x180062cc0  cmp     dword ptr [r14+30h], 0
0x180062cc5  jz      short loc_180062CD5
0x180062cc7  mov     rcx, [r14+20h]; this
0x180062ccb  lea     rdx, [rsp+520h+String]; unsigned __int16 *
0x180062cd0  call    ?SetNetname@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetNetname(ushort const *)
0x180062cd5  cmp     dword ptr [r14+34h], 0
0x180062cda  jz      short loc_180062D07
0x180062cdc  xor     eax, eax
0x180062cde  lea     r8, [rbp+420h+Buffer]; lpString
0x180062ce2  mov     r9d, 101h; cchMax
0x180062ce8  mov     [rbp+420h+Buffer], ax
0x180062cec  mov     edx, 3EAh; nIDDlgItem
0x180062cf1  mov     rcx, rsi; hDlg
0x180062cf4  call    cs:__imp_GetDlgItemTextW
0x180062cfa  mov     rcx, [r14+20h]; this
0x180062cfe  lea     rdx, [rbp+420h+Buffer]; unsigned __int16 *
0x180062d02  call    ?SetRemark@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetRemark(ushort const *)
0x180062d07  mov     edx, 3EEh; nIDButton
0x180062d0c  mov     rcx, rsi; hDlg
0x180062d0f  call    cs:__imp_IsDlgButtonChecked
0x180062d15  cmp     eax, ebx
0x180062d17  jnz     short loc_180062D1E
0x180062d19  or      edx, 0FFFFFFFFh
0x180062d1c  jmp     short loc_180062D3F
0x180062d1e  mov     edx, 3EFh; nIDButton
0x180062d23  mov     rcx, rsi; hDlg
0x180062d26  call    cs:__imp_IsDlgButtonChecked
0x180062d2c  cmp     eax, ebx
0x180062d2e  jnz     short loc_180062D48
0x180062d30  mov     rdx, rsi; HWND
0x180062d33  mov     rcx, r14; this
0x180062d36  call    ?_CacheMaxUses@CDlgNewShare@@AEAAXPEAUHWND__@@@Z; CDlgNewShare::_CacheMaxUses(HWND__ *)
0x180062d3b  mov     edx, [r14+38h]; unsigned int
0x180062d3f  mov     rcx, [r14+20h]; this
0x180062d43  call    ?SetMaxUses@CShareInfo@@QEAAJK@Z; CShareInfo::SetMaxUses(ulong)
0x180062d48  mov     rdx, rbx; nResult
0x180062d4b  mov     rcx, rsi; hDlg
0x180062d4e  call    cs:__imp_EndDialog
0x180062d54  mov     eax, ebx
0x180062d56  mov     rcx, [rbp+420h+var_20]
0x180062d5d  xor     rcx, rsp; StackCookie
0x180062d60  call    __security_check_cookie
0x180062d65  lea     r11, [rsp+520h+var_10]
0x180062d6d  mov     rbx, [r11+30h]
0x180062d71  mov     rsi, [r11+38h]
0x180062d75  mov     rsp, r11
0x180062d78  pop     r14
0x180062d7a  pop     rdi
0x180062d7b  pop     rbp
0x180062d7c  retn
```
