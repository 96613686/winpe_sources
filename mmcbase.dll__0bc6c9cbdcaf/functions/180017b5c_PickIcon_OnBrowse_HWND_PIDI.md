# PickIcon_OnBrowse(HWND__ *,PIDI *)

- ea: `0x180017b5c`
- end: `0x180017c30`
- name: `?PickIcon_OnBrowse@@YAXPEAUHWND__@@PEAUPIDI@@@Z`
- size: `212`
- prototype: `void __fastcall(HWND hDlg, struct PIDI *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017550`

## callees

- `0x1800173a4`
- `0x180017684`
- `0x180017b5c`
- `0x18001b522`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180017bad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180017bad`
- `USER32!SetDlgItemTextW` at `0x180017be5`
- `USER32!SetDlgItemTextW` at `0x180017be5`
- `USER32!SendMessageW` at `0x180017bfa`
- `USER32!SendMessageW` at `0x180017bfa`
- `COMDLG32!GetOpenFileNameW` at `0x180017bcb`
- `COMDLG32!GetOpenFileNameW` at `0x180017bcb`

## pseudocode

```c
void __fastcall PickIcon_OnBrowse(HWND hDlg, struct PIDI *a2)
{
  unsigned int v4; // r8d
  DWORD FileAttributesW; // eax
  tagOFNW v6; // [rsp+20h] [rbp-448h] BYREF
  WCHAR String[460]; // [rsp+B8h] [rbp-3B0h] BYREF

  memset_0(&v6, 0, 0x430u);
  InitOpenFileName(hDlg, (struct COFN *)&v6, v4, (const unsigned __int16 *)a2 + 12);
  FileAttributesW = GetFileAttributesW((LPCWSTR)a2 + 12);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
    String[0] = 0;
  if ( GetOpenFileNameW(&v6) )
  {
    SetDlgItemTextW(hDlg, 1005, String);
    SendMessageW(hDlg, 0x401u, 1u, 0);
    PickIcon_FillIconList(hDlg, (WCHAR *)a2);
  }
}

```

## disassembly

```asm
0x180017b5c  mov     [rsp+arg_10], rbx
0x180017b61  mov     [rsp+arg_18], rsi
0x180017b66  push    rdi
0x180017b67  sub     rsp, 460h
0x180017b6e  mov     rax, cs:__security_cookie
0x180017b75  xor     rax, rsp
0x180017b78  mov     [rsp+468h+var_18], rax
0x180017b80  mov     rsi, rdx
0x180017b83  mov     rdi, rcx
0x180017b86  xor     edx, edx; Val
0x180017b88  lea     rcx, [rsp+468h+var_448]; void *
0x180017b8d  mov     r8d, 430h; Size
0x180017b93  call    memset_0
0x180017b98  lea     r9, [rsi+18h]; unsigned __int16 *
0x180017b9c  mov     rcx, rdi; HWND
0x180017b9f  lea     rdx, [rsp+468h+var_448]; struct COFN *
0x180017ba4  call    ?InitOpenFileName@@YAXPEAUHWND__@@PEAUCOFN@@IPEBG@Z; InitOpenFileName(HWND__ *,COFN *,uint,ushort const *)
0x180017ba9  lea     rcx, [rsi+18h]; lpFileName
0x180017bad  call    cs:__imp_GetFileAttributesW
0x180017bb3  cmp     eax, 0FFFFFFFFh
0x180017bb6  jz      short loc_180017BBC
0x180017bb8  test    al, 10h
0x180017bba  jz      short loc_180017BC6
0x180017bbc  xor     eax, eax
0x180017bbe  mov     [rsp+468h+String], ax
0x180017bc6  lea     rcx, [rsp+468h+var_448]; LPOPENFILENAMEW
0x180017bcb  call    cs:__imp_GetOpenFileNameW
0x180017bd1  test    eax, eax
0x180017bd3  jz      short loc_180017C0B
0x180017bd5  lea     r8, [rsp+468h+String]; lpString
0x180017bdd  mov     edx, 3EDh; nIDDlgItem
0x180017be2  mov     rcx, rdi; hDlg
0x180017be5  call    cs:__imp_SetDlgItemTextW
0x180017beb  xor     r9d, r9d; lParam
0x180017bee  mov     edx, 401h; Msg
0x180017bf3  mov     rcx, rdi; hWnd
0x180017bf6  lea     r8d, [r9+1]; wParam
0x180017bfa  call    cs:__imp_SendMessageW
0x180017c00  mov     rdx, rsi; struct PIDI *
0x180017c03  mov     rcx, rdi; hDlg
0x180017c06  call    ?PickIcon_FillIconList@@YAXPEAUHWND__@@PEAUPIDI@@@Z; PickIcon_FillIconList(HWND__ *,PIDI *)
0x180017c0b  mov     rcx, [rsp+468h+var_18]
0x180017c13  xor     rcx, rsp; StackCookie
0x180017c16  call    __security_check_cookie
0x180017c1b  lea     r11, [rsp+468h+var_8]
0x180017c23  mov     rbx, [r11+20h]
0x180017c27  mov     rsi, [r11+28h]
0x180017c2b  mov     rsp, r11
0x180017c2e  pop     rdi
0x180017c2f  retn
```
