# Localize_Combobox_Styles(HWND__ *,int,ulong)

- ea: `0x180027020`
- end: `0x180027149`
- name: `?Localize_Combobox_Styles@@YAXPEAUHWND__@@HK@Z`
- size: `297`
- prototype: `void __fastcall(HWND hDlg, int nIDDlgItem, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800112a0`
- `0x180021afc`

## callees

- `0x180027020`
- `0x180027150`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `USER32!GetDlgItem` at `0x18002705f`
- `USER32!GetDlgItem` at `0x18002705f`
- `USER32!SendMessageW` at `0x180027076`
- `USER32!SendMessageW` at `0x1800270a7`
- `USER32!SendMessageW` at `0x1800270c4`
- `USER32!SendMessageW` at `0x180027102`
- `USER32!SendMessageW` at `0x18002711b`
- `USER32!SendMessageW` at `0x180027076`
- `USER32!SendMessageW` at `0x1800270a7`
- `USER32!SendMessageW` at `0x1800270c4`
- `USER32!SendMessageW` at `0x180027102`
- `USER32!SendMessageW` at `0x18002711b`

## pseudocode

```c
void __fastcall Localize_Combobox_Styles(HWND hDlg, int nIDDlgItem, unsigned int a3)
{
  HWND DlgItem; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebp
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // [rsp+20h] [rbp-248h]
  unsigned __int16 lParam[128]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v13[128]; // [rsp+130h] [rbp-138h] BYREF

  memset_0(lParam, 0, sizeof(lParam));
  DlgItem = GetDlgItem(hDlg, nIDDlgItem);
  v7 = SendMessageW(DlgItem, 0x146u, 0, 0);
  v8 = v7;
  if ( g_fStylesLocalized )
  {
    v9 = 0;
    if ( v7 )
    {
      do
      {
        if ( (unsigned int)SendMessageW(DlgItem, 0x149u, (int)v9, 0) >= 0x80 )
        {
          v10 = -1;
        }
        else
        {
          v10 = SendMessageW(DlgItem, 0x148u, (int)v9, (LPARAM)lParam);
          if ( v10 == -1 )
            return;
        }
        if ( v10 != -1 )
        {
          Localize_Format_String(a3, lParam, 0x80u, v13, v11);
          SendMessageW(DlgItem, 0x144u, (int)v9, 0);
          SendMessageW(DlgItem, 0x14Au, (int)v9, (LPARAM)v13);
        }
        ++v9;
      }
      while ( v9 < v8 );
    }
  }
}

```

## disassembly

```asm
0x180027020  push    rbx
0x180027022  push    rbp
0x180027023  push    rsi
0x180027024  push    rdi
0x180027025  push    r14
0x180027027  sub     rsp, 240h
0x18002702e  mov     rax, cs:__security_cookie
0x180027035  xor     rax, rsp
0x180027038  mov     [rsp+268h+var_38], rax
0x180027040  mov     r14d, r8d
0x180027043  mov     edi, edx
0x180027045  mov     rbx, rcx
0x180027048  xor     edx, edx; Val
0x18002704a  mov     r8d, 100h; Size
0x180027050  lea     rcx, [rsp+268h+lParam]; void *
0x180027055  call    memset_0
0x18002705a  mov     edx, edi; nIDDlgItem
0x18002705c  mov     rcx, rbx; hDlg
0x18002705f  call    cs:__imp_GetDlgItem
0x180027065  xor     r9d, r9d; lParam
0x180027068  xor     r8d, r8d; wParam
0x18002706b  mov     rcx, rax; hWnd
0x18002706e  mov     edx, 146h; Msg
0x180027073  mov     rsi, rax
0x180027076  call    cs:__imp_SendMessageW
0x18002707c  cmp     cs:?g_fStylesLocalized@@3HA, 0; int g_fStylesLocalized
0x180027083  mov     rbp, rax
0x180027086  jz      loc_18002712B
0x18002708c  xor     ebx, ebx
0x18002708e  test    ebp, ebp
0x180027090  jz      loc_18002712B
0x180027096  movsxd  rdi, ebx
0x180027099  xor     r9d, r9d; lParam
0x18002709c  mov     r8, rdi; wParam
0x18002709f  mov     edx, 149h; Msg
0x1800270a4  mov     rcx, rsi; hWnd
0x1800270a7  call    cs:__imp_SendMessageW
0x1800270ad  cmp     eax, 80h
0x1800270b2  jnb     short loc_1800270D1
0x1800270b4  lea     r9, [rsp+268h+lParam]; lParam
0x1800270b9  mov     r8, rdi; wParam
0x1800270bc  mov     edx, 148h; Msg
0x1800270c1  mov     rcx, rsi; hWnd
0x1800270c4  call    cs:__imp_SendMessageW
0x1800270ca  cmp     eax, 0FFFFFFFFh
0x1800270cd  jz      short loc_18002712B
0x1800270cf  jmp     short loc_1800270D4
0x1800270d1  or      eax, 0FFFFFFFFh
0x1800270d4  cmp     eax, 0FFFFFFFFh
0x1800270d7  jz      short loc_180027121
0x1800270d9  lea     r9, [rsp+268h+var_138]; unsigned __int16 *
0x1800270e1  mov     r8d, 80h; unsigned int
0x1800270e7  lea     rdx, [rsp+268h+lParam]; unsigned __int16 *
0x1800270ec  mov     ecx, r14d; unsigned int
0x1800270ef  call    ?Localize_Format_String@@YAXKPEBGKPEAGK@Z; Localize_Format_String(ulong,ushort const *,ulong,ushort *,ulong)
0x1800270f4  xor     r9d, r9d; lParam
0x1800270f7  mov     r8, rdi; wParam
0x1800270fa  mov     edx, 144h; Msg
0x1800270ff  mov     rcx, rsi; hWnd
0x180027102  call    cs:__imp_SendMessageW
0x180027108  lea     r9, [rsp+268h+var_138]; lParam
0x180027110  mov     r8, rdi; wParam
0x180027113  mov     edx, 14Ah; Msg
0x180027118  mov     rcx, rsi; hWnd
0x18002711b  call    cs:__imp_SendMessageW
0x180027121  inc     ebx
0x180027123  cmp     ebx, ebp
0x180027125  jb      loc_180027096
0x18002712b  mov     rcx, [rsp+268h+var_38]
0x180027133  xor     rcx, rsp; StackCookie
0x180027136  call    __security_check_cookie
0x18002713b  add     rsp, 240h
0x180027142  pop     r14
0x180027144  pop     rdi
0x180027145  pop     rsi
0x180027146  pop     rbp
0x180027147  pop     rbx
0x180027148  retn
```
