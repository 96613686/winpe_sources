# CSaveAttachDlg::DlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800cbc1c`
- end: `0x1800cbdbc`
- name: `?DlgProc@CSaveAttachDlg@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `416`
- prototype: `__int64 __usercall@<rax>(CSaveAttachDlg *__hidden this@<rcx>, HWND hDlg@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800cbdd0`

## callees

- `0x1800cbc1c`
- `0x1800cbee0`
- `0x1800cbf8c`
- `0x1800cc2e8`
- `0x1800cc590`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!BrowseForFolderW` at `0x1800cbce3`
- `MSOERT2!BrowseForFolderW` at `0x1800cbce3`
- `SHLWAPI!SHAutoComplete` at `0x1800cbd7a`
- `SHLWAPI!SHAutoComplete` at `0x1800cbd7a`
- `USER32!SendMessageA` at `0x1800cbd32`
- `USER32!SendMessageA` at `0x1800cbd32`
- `USER32!GetDlgItem` at `0x1800cbc9b`
- `USER32!GetDlgItem` at `0x1800cbc9b`
- `USER32!SetWindowTextW` at `0x1800cbcf8`
- `USER32!SetWindowTextW` at `0x1800cbcf8`
- `USER32!GetWindowTextW` at `0x1800cbcb5`
- `USER32!GetWindowTextW` at `0x1800cbcb5`
- `USER32!EndDialog` at `0x1800cbd63`
- `USER32!EndDialog` at `0x1800cbd63`
- `USER32!SetFocus` at `0x1800cbd3c`
- `USER32!SetFocus` at `0x1800cbd3c`

## pseudocode

```c
__int64 __fastcall CSaveAttachDlg::DlgProc(HWND *this, HWND hDlg, int a3, unsigned __int64 a4, __int64 a5)
{
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  HWND DlgItem; // rbx
  HWND v11; // rcx
  INT_PTR v13; // rdx
  LPARAM lParam; // [rsp+30h] [rbp-288h] BYREF
  int v15; // [rsp+3Ch] [rbp-27Ch]
  int v16; // [rsp+40h] [rbp-278h]
  WCHAR String[264]; // [rsp+90h] [rbp-228h] BYREF

  v7 = a3 - 2;
  if ( !v7 )
  {
    CSaveAttachDlg::OnDestroy((CSaveAttachDlg *)this);
    return 0;
  }
  v8 = v7 - 76;
  if ( !v8 )
  {
    CSaveAttachDlg::OnWMNotfiy((CSaveAttachDlg *)this, a4, a5);
    return 0;
  }
  v9 = v8 - 194;
  if ( !v9 )
  {
    if ( (int)CSaveAttachDlg::OnInitDialog((CSaveAttachDlg *)this, hDlg) >= 0 )
      SHAutoComplete(this[4], 0);
    return 0;
  }
  if ( v9 == 1 )
  {
    switch ( (unsigned __int16)a4 )
    {
      case 1u:
        if ( (int)CSaveAttachDlg::OnSave((CSaveAttachDlg *)this) < 0 )
          return 1;
        v13 = 0;
        break;
      case 2u:
        v13 = -2146691325;
        break;
      case 0x2BCu:
        memset_0(&lParam, 0, 0x58u);
        v11 = this[3];
        v16 = 2;
        v15 = 2;
        SendMessageA(v11, 0x102Bu, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&lParam);
        SetFocus(this[3]);
        return 1;
      case 0x2BFu:
        DlgItem = GetDlgItem(hDlg, 702);
        GetWindowTextW(DlgItem, String, 260);
        if ( (unsigned int)BrowseForFolderW(g_hLocRes, hDlg, String, 260, 1282, 0) )
          SetWindowTextW(DlgItem, String);
        return 1;
      default:
        return 0;
    }
    EndDialog(hDlg, v13);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800cbc1c  mov     [rsp+arg_10], rbx
0x1800cbc21  push    rdi
0x1800cbc22  sub     rsp, 2B0h
0x1800cbc29  mov     rax, cs:__security_cookie
0x1800cbc30  xor     rax, rsp
0x1800cbc33  mov     [rsp+2B8h+var_18], rax
0x1800cbc3b  mov     rdi, rdx
0x1800cbc3e  mov     rbx, rcx
0x1800cbc41  sub     r8d, 2
0x1800cbc45  jz      loc_1800CBD94
0x1800cbc4b  sub     r8d, 4Ch ; 'L'
0x1800cbc4f  jz      loc_1800CBD82
0x1800cbc55  sub     r8d, 0C2h
0x1800cbc5c  jz      loc_1800CBD6B
0x1800cbc62  cmp     r8d, 1
0x1800cbc66  jnz     loc_1800CBD99
0x1800cbc6c  movzx   ecx, r9w
0x1800cbc70  sub     ecx, r8d
0x1800cbc73  jz      loc_1800CBD52
0x1800cbc79  sub     ecx, r8d
0x1800cbc7c  jz      loc_1800CBD49
0x1800cbc82  sub     ecx, 2BAh
0x1800cbc88  jz      short loc_1800CBD00
0x1800cbc8a  cmp     ecx, 3
0x1800cbc8d  jnz     loc_1800CBD99
0x1800cbc93  mov     edx, 2BEh; nIDDlgItem
0x1800cbc98  mov     rcx, rdi; hDlg
0x1800cbc9b  call    cs:__imp_GetDlgItem
0x1800cbca1  mov     r8d, 104h; nMaxCount
0x1800cbca7  lea     rdx, [rsp+2B8h+String]; lpString
0x1800cbcaf  mov     rcx, rax; hWnd
0x1800cbcb2  mov     rbx, rax
0x1800cbcb5  call    cs:__imp_GetWindowTextW
0x1800cbcbb  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x1800cbcc2  lea     r8, [rsp+2B8h+String]
0x1800cbcca  mov     r9d, 104h
0x1800cbcd0  mov     [rsp+2B8h+var_290], 0
0x1800cbcd8  mov     rdx, rdi
0x1800cbcdb  mov     [rsp+2B8h+var_298], 502h
0x1800cbce3  call    cs:__imp_BrowseForFolderW
0x1800cbce9  test    eax, eax
0x1800cbceb  jz      short loc_1800CBD42
0x1800cbced  lea     rdx, [rsp+2B8h+String]; lpString
0x1800cbcf5  mov     rcx, rbx; hWnd
0x1800cbcf8  call    cs:__imp_SetWindowTextW
0x1800cbcfe  jmp     short loc_1800CBD42
0x1800cbd00  xor     edx, edx; Val
0x1800cbd02  lea     rcx, [rsp+2B8h+lParam]; void *
0x1800cbd07  lea     r8d, [rdx+58h]; Size
0x1800cbd0b  call    memset_0
0x1800cbd10  mov     rcx, [rbx+18h]; hWnd
0x1800cbd14  lea     r9, [rsp+2B8h+lParam]; lParam
0x1800cbd19  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800cbd1d  mov     [rsp+2B8h+var_278], 2
0x1800cbd25  mov     edx, 102Bh; Msg
0x1800cbd2a  mov     [rsp+2B8h+var_27C], 2
0x1800cbd32  call    cs:__imp_SendMessageA
0x1800cbd38  mov     rcx, [rbx+18h]; hWnd
0x1800cbd3c  call    cs:__imp_SetFocus
0x1800cbd42  mov     eax, 1
0x1800cbd47  jmp     short loc_1800CBD9B
0x1800cbd49  mov     rdx, 0FFFFFFFF800C1703h
0x1800cbd50  jmp     short loc_1800CBD60
0x1800cbd52  mov     rcx, rbx; this
0x1800cbd55  call    ?OnSave@CSaveAttachDlg@@AEAAJXZ; CSaveAttachDlg::OnSave(void)
0x1800cbd5a  test    eax, eax
0x1800cbd5c  js      short loc_1800CBD42
0x1800cbd5e  xor     edx, edx; nResult
0x1800cbd60  mov     rcx, rdi; hDlg
0x1800cbd63  call    cs:__imp_EndDialog
0x1800cbd69  jmp     short loc_1800CBD42
0x1800cbd6b  call    ?OnInitDialog@CSaveAttachDlg@@AEAAJPEAUHWND__@@@Z; CSaveAttachDlg::OnInitDialog(HWND__ *)
0x1800cbd70  test    eax, eax
0x1800cbd72  js      short loc_1800CBD99
0x1800cbd74  mov     rcx, [rbx+20h]; hwndEdit
0x1800cbd78  xor     edx, edx; dwFlags
0x1800cbd7a  call    cs:__imp_SHAutoComplete
0x1800cbd80  jmp     short loc_1800CBD99
0x1800cbd82  mov     r8, [rsp+2B8h+arg_20]; __int64
0x1800cbd8a  mov     rdx, r9; unsigned __int64
0x1800cbd8d  call    ?OnWMNotfiy@CSaveAttachDlg@@AEAAJ_K_J@Z; CSaveAttachDlg::OnWMNotfiy(unsigned __int64,__int64)
0x1800cbd92  jmp     short loc_1800CBD99
0x1800cbd94  call    ?OnDestroy@CSaveAttachDlg@@AEAAJXZ; CSaveAttachDlg::OnDestroy(void)
0x1800cbd99  xor     eax, eax
0x1800cbd9b  mov     rcx, [rsp+2B8h+var_18]
0x1800cbda3  xor     rcx, rsp; StackCookie
0x1800cbda6  call    __security_check_cookie
0x1800cbdab  mov     rbx, [rsp+2B8h+arg_10]
0x1800cbdb3  add     rsp, 2B0h
0x1800cbdba  pop     rdi
0x1800cbdbb  retn
```
