# XBytes::OnComboNotifySelChange(__int64)

- ea: `0x18001b120`
- end: `0x18001b1d7`
- name: `?OnComboNotifySelChange@XBytes@@QEAAH_J@Z`
- size: `183`
- prototype: `__int64 __fastcall(XBytes *__hidden this, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006848`
- `0x180017b7c`
- `0x1800191e8`

## callees

- `0x180001510`
- `0x18001b120`
- `0x18001b3b0`
- `0x18001b52c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18001b15c`
- `KERNEL32!lstrcmpiW` at `0x18001b15c`
- `USER32!GetDlgItemTextW` at `0x18001b14a`
- `USER32!GetDlgItemTextW` at `0x18001b14a`
- `USER32!MessageBeep` at `0x18001b1bc`
- `USER32!MessageBeep` at `0x18001b1bc`
- `USER32!SendMessageW` at `0x18001b181`
- `USER32!SendMessageW` at `0x18001b181`
- `USER32!GetDlgItem` at `0x18001b16d`
- `USER32!GetDlgItem` at `0x18001b16d`

## pseudocode

```c
__int64 __fastcall XBytes::OnComboNotifySelChange(XBytes *this)
{
  HWND DlgItem; // rax
  int v3; // eax
  __int64 v4; // rdx
  WCHAR String[16]; // [rsp+20h] [rbp-38h] BYREF

  GetDlgItemTextW(*((HWND *)this + 1), *((_DWORD *)this + 4), String, 16);
  if ( lstrcmpiW(&XBytes::m_szNoLimit, String) )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    v3 = SendMessageW(DlgItem, 0x147u, 0, 0);
    if ( !(unsigned int)XBytes::Store(this, String, v3 + 1) )
    {
      v4 = 0x6000000000000000LL;
LABEL_6:
      XBytes::SetBytes(this, v4);
      MessageBeep(0);
      return 0;
    }
    v4 = 1024;
    if ( *(__int64 *)this < 1024 )
      goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x18001b120  push    rbx
0x18001b122  sub     rsp, 50h
0x18001b126  mov     rax, cs:__security_cookie
0x18001b12d  xor     rax, rsp
0x18001b130  mov     [rsp+58h+var_18], rax
0x18001b135  mov     edx, [rcx+10h]; nIDDlgItem
0x18001b138  lea     r8, [rsp+58h+String]; lpString
0x18001b13d  mov     rbx, rcx
0x18001b140  mov     r9d, 10h; cchMax
0x18001b146  mov     rcx, [rcx+8]; hDlg
0x18001b14a  call    cs:__imp_GetDlgItemTextW
0x18001b150  lea     rdx, [rsp+58h+String]; lpString2
0x18001b155  lea     rcx, ?m_szNoLimit@XBytes@@0PAGA; lpString1
0x18001b15c  call    cs:__imp_lstrcmpiW
0x18001b162  test    eax, eax
0x18001b164  jz      short loc_18001B1C2
0x18001b166  mov     edx, [rbx+14h]; nIDDlgItem
0x18001b169  mov     rcx, [rbx+8]; hDlg
0x18001b16d  call    cs:__imp_GetDlgItem
0x18001b173  xor     r9d, r9d; lParam
0x18001b176  xor     r8d, r8d; wParam
0x18001b179  mov     rcx, rax; hWnd
0x18001b17c  mov     edx, 147h; Msg
0x18001b181  call    cs:__imp_SendMessageW
0x18001b187  lea     rdx, [rsp+58h+String]; unsigned __int16 *
0x18001b18c  mov     rcx, rbx; this
0x18001b18f  lea     r8, [rax+1]; int
0x18001b193  call    ?Store@XBytes@@AEAAHPEBGH@Z; XBytes::Store(ushort const *,int)
0x18001b198  test    eax, eax
0x18001b19a  jz      short loc_18001B1A8
0x18001b19c  mov     edx, 400h
0x18001b1a1  cmp     [rbx], rdx
0x18001b1a4  jge     short loc_18001B1C2
0x18001b1a6  jmp     short loc_18001B1B2
0x18001b1a8  mov     rdx, 6000000000000000h; __int64
0x18001b1b2  mov     rcx, rbx; this
0x18001b1b5  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x18001b1ba  xor     ecx, ecx; uType
0x18001b1bc  call    cs:__imp_MessageBeep
0x18001b1c2  xor     eax, eax
0x18001b1c4  mov     rcx, [rsp+58h+var_18]
0x18001b1c9  xor     rcx, rsp; StackCookie
0x18001b1cc  call    __security_check_cookie
0x18001b1d1  add     rsp, 50h
0x18001b1d5  pop     rbx
0x18001b1d6  retn
```
