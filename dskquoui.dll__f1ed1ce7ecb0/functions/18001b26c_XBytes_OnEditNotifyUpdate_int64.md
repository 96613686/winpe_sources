# XBytes::OnEditNotifyUpdate(__int64)

- ea: `0x18001b26c`
- end: `0x18001b3a9`
- name: `?OnEditNotifyUpdate@XBytes@@QEAAH_J@Z`
- size: `317`
- prototype: `__int64 __fastcall(XBytes *__hidden this, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006848`
- `0x180017b7c`
- `0x1800191e8`

## callees

- `0x180001510`
- `0x18001b26c`
- `0x18001b3b0`
- `0x18001b52c`
- `0x18001b7a4`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18001b2db`
- `KERNEL32!lstrcmpiW` at `0x18001b2db`
- `KERNEL32!lstrlenW` at `0x18001b2ab`
- `KERNEL32!lstrlenW` at `0x18001b2ab`
- `USER32!GetDlgItemTextW` at `0x18001b2a0`
- `USER32!GetDlgItemTextW` at `0x18001b2a0`
- `USER32!MessageBeep` at `0x18001b380`
- `USER32!MessageBeep` at `0x18001b380`
- `USER32!SendMessageW` at `0x18001b304`
- `USER32!SendMessageW` at `0x18001b353`
- `USER32!SendMessageW` at `0x18001b304`
- `USER32!SendMessageW` at `0x18001b353`
- `USER32!SetDlgItemTextW` at `0x18001b2c9`
- `USER32!SetDlgItemTextW` at `0x18001b2c9`
- `USER32!GetDlgItem` at `0x18001b2f0`
- `USER32!GetDlgItem` at `0x18001b33f`
- `USER32!GetDlgItem` at `0x18001b2f0`
- `USER32!GetDlgItem` at `0x18001b33f`

## pseudocode

```c
__int64 __fastcall XBytes::OnEditNotifyUpdate(XBytes *this)
{
  int v2; // edx
  HWND v3; // rcx
  HWND DlgItem; // rax
  int v5; // eax
  char v6; // di
  HWND v7; // rax
  WCHAR String[264]; // [rsp+20h] [rbp-228h] BYREF

  GetDlgItemTextW(*((HWND *)this + 1), *((_DWORD *)this + 4), String, 260);
  if ( lstrlenW(String) > 16 )
  {
    v2 = *((_DWORD *)this + 4);
    v3 = (HWND)*((_QWORD *)this + 1);
    String[16] = 0;
    SetDlgItemTextW(v3, v2, String);
  }
  if ( lstrcmpiW(&XBytes::m_szNoLimit, String) )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    v5 = SendMessageW(DlgItem, 0x147u, 0, 0);
    if ( !(unsigned int)XBytes::Store(this, String, v5 + 1) )
    {
      if ( !XBytes::UndoLastEdit(this) )
        XBytes::SetBytes(this, 0x6000000000000000LL);
      goto LABEL_11;
    }
    v6 = 0;
    if ( *(__int64 *)this < 0 )
    {
      XBytes::SetBytes(this, 1024);
      v6 = 1;
    }
    v7 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 4));
    SendMessageW(v7, 0xCDu, 0, 0);
    if ( v6 )
LABEL_11:
      MessageBeep(0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b26c  mov     [rsp+arg_8], rbx
0x18001b271  push    rdi
0x18001b272  sub     rsp, 240h
0x18001b279  mov     rax, cs:__security_cookie
0x18001b280  xor     rax, rsp
0x18001b283  mov     [rsp+248h+var_18], rax
0x18001b28b  mov     edx, [rcx+10h]; nIDDlgItem
0x18001b28e  lea     r8, [rsp+248h+String]; lpString
0x18001b293  mov     rbx, rcx
0x18001b296  mov     r9d, 104h; cchMax
0x18001b29c  mov     rcx, [rcx+8]; hDlg
0x18001b2a0  call    cs:__imp_GetDlgItemTextW
0x18001b2a6  lea     rcx, [rsp+248h+String]; lpString
0x18001b2ab  call    cs:__imp_lstrlenW
0x18001b2b1  cmp     eax, 10h
0x18001b2b4  jle     short loc_18001B2CF
0x18001b2b6  mov     edx, [rbx+10h]; nIDDlgItem
0x18001b2b9  lea     r8, [rsp+248h+String]; lpString
0x18001b2be  mov     rcx, [rbx+8]; hDlg
0x18001b2c2  xor     eax, eax
0x18001b2c4  mov     [rsp+248h+var_208], ax
0x18001b2c9  call    cs:__imp_SetDlgItemTextW
0x18001b2cf  lea     rdx, [rsp+248h+String]; lpString2
0x18001b2d4  lea     rcx, ?m_szNoLimit@XBytes@@0PAGA; lpString1
0x18001b2db  call    cs:__imp_lstrcmpiW
0x18001b2e1  test    eax, eax
0x18001b2e3  jz      loc_18001B386
0x18001b2e9  mov     edx, [rbx+14h]; nIDDlgItem
0x18001b2ec  mov     rcx, [rbx+8]; hDlg
0x18001b2f0  call    cs:__imp_GetDlgItem
0x18001b2f6  xor     r9d, r9d; lParam
0x18001b2f9  xor     r8d, r8d; wParam
0x18001b2fc  mov     rcx, rax; hWnd
0x18001b2ff  mov     edx, 147h; Msg
0x18001b304  call    cs:__imp_SendMessageW
0x18001b30a  lea     rdx, [rsp+248h+String]; unsigned __int16 *
0x18001b30f  mov     rcx, rbx; this
0x18001b312  lea     r8, [rax+1]; int
0x18001b316  call    ?Store@XBytes@@AEAAHPEBGH@Z; XBytes::Store(ushort const *,int)
0x18001b31b  test    eax, eax
0x18001b31d  jz      short loc_18001B360
0x18001b31f  xor     dil, dil
0x18001b322  cmp     qword ptr [rbx], 0
0x18001b326  jge     short loc_18001B338
0x18001b328  mov     edx, 400h; __int64
0x18001b32d  mov     rcx, rbx; this
0x18001b330  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x18001b335  mov     dil, 1
0x18001b338  mov     edx, [rbx+10h]; nIDDlgItem
0x18001b33b  mov     rcx, [rbx+8]; hDlg
0x18001b33f  call    cs:__imp_GetDlgItem
0x18001b345  xor     r9d, r9d; lParam
0x18001b348  xor     r8d, r8d; wParam
0x18001b34b  mov     rcx, rax; hWnd
0x18001b34e  mov     edx, 0CDh; Msg
0x18001b353  call    cs:__imp_SendMessageW
0x18001b359  test    dil, dil
0x18001b35c  jz      short loc_18001B386
0x18001b35e  jmp     short loc_18001B37E
0x18001b360  mov     rcx, rbx; this
0x18001b363  call    ?UndoLastEdit@XBytes@@AEAA_NXZ; XBytes::UndoLastEdit(void)
0x18001b368  test    al, al
0x18001b36a  jnz     short loc_18001B37E
0x18001b36c  mov     rdx, 6000000000000000h; __int64
0x18001b376  mov     rcx, rbx; this
0x18001b379  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x18001b37e  xor     ecx, ecx; uType
0x18001b380  call    cs:__imp_MessageBeep
0x18001b386  xor     eax, eax
0x18001b388  mov     rcx, [rsp+248h+var_18]
0x18001b390  xor     rcx, rsp; StackCookie
0x18001b393  call    __security_check_cookie
0x18001b398  mov     rbx, [rsp+248h+arg_8]
0x18001b3a0  add     rsp, 240h
0x18001b3a7  pop     rdi
0x18001b3a8  retn
```
