# CSchedulePage::_LoadTriggerStrings(void)

- ea: `0x180014328`
- end: `0x1800144a4`
- name: `?_LoadTriggerStrings@CSchedulePage@@AEAAHXZ`
- size: `380`
- prototype: `__int64 __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180013fd8`
- `0x180014620`
- `0x180014aa0`

## callees

- `0x180013504`
- `0x180014328`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001439f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001439f`
- `USER32!SendMessageW` at `0x1800143d7`
- `USER32!SendMessageW` at `0x1800143f3`
- `USER32!SendMessageW` at `0x180014459`
- `USER32!SendMessageW` at `0x180014471`
- `USER32!SendMessageW` at `0x1800143d7`
- `USER32!SendMessageW` at `0x1800143f3`
- `USER32!SendMessageW` at `0x180014459`
- `USER32!SendMessageW` at `0x180014471`
- `USER32!GetDlgItem` at `0x18001436a`
- `USER32!GetDlgItem` at `0x1800143ae`
- `USER32!GetDlgItem` at `0x180014429`
- `USER32!GetDlgItem` at `0x18001436a`
- `USER32!GetDlgItem` at `0x1800143ae`
- `USER32!GetDlgItem` at `0x180014429`
- `USER32!SetWindowTextW` at `0x1800143c1`
- `USER32!SetWindowTextW` at `0x18001443c`
- `USER32!SetWindowTextW` at `0x1800143c1`
- `USER32!SetWindowTextW` at `0x18001443c`

## pseudocode

```c
__int64 __fastcall CSchedulePage::_LoadTriggerStrings(HWND *this)
{
  HWND DlgItem; // rsi
  _QWORD *v3; // rbx
  HWND v4; // rax
  int v5; // eax
  HWND v7; // rax
  int v8; // eax
  WCHAR Buffer[512]; // [rsp+20h] [rbp-418h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  DlgItem = GetDlgItem(this[14], 1692);
  if ( !DlgItem )
    return 0;
  v3 = this[86];
  if ( v3 )
  {
    while ( 1 )
    {
      CJobTrigger::TriggerString((CJobTrigger *)v3, 1, Buffer);
      if ( v3 == (_QWORD *)this[86] )
      {
        v7 = GetDlgItem(this[14], 1693);
        if ( v7 )
          SetWindowTextW(v7, Buffer);
        this[91] = (HWND)v3;
      }
      v8 = SendMessageW(DlgItem, 0x143u, 0, (LPARAM)Buffer);
      if ( v8 < 0 )
        break;
      SendMessageW(DlgItem, 0x151u, v8, (LPARAM)v3);
      v3 = (_QWORD *)v3[1];
      if ( !v3 )
        return 1;
    }
    return 0;
  }
  LoadStringW(g_hInstance, 0x1013u, Buffer, 512);
  v4 = GetDlgItem(this[14], 1693);
  if ( v4 )
    SetWindowTextW(v4, Buffer);
  v5 = SendMessageW(DlgItem, 0x143u, 0, (LPARAM)Buffer);
  if ( v5 < 0 )
    return 0;
  SendMessageW(DlgItem, 0x151u, v5, 0);
  return 1;
}

```

## disassembly

```asm
0x180014328  mov     [rsp+arg_8], rbx
0x18001432d  mov     [rsp+arg_10], rsi
0x180014332  push    rdi
0x180014333  sub     rsp, 430h
0x18001433a  mov     rax, cs:__security_cookie
0x180014341  xor     rax, rsp
0x180014344  mov     [rsp+438h+var_18], rax
0x18001434c  mov     rdi, rcx
0x18001434f  xor     edx, edx; Val
0x180014351  lea     rcx, [rsp+438h+Buffer]; void *
0x180014356  mov     r8d, 400h; Size
0x18001435c  call    memset_0
0x180014361  mov     rcx, [rdi+70h]; hDlg
0x180014365  mov     edx, 69Ch; nIDDlgItem
0x18001436a  call    cs:__imp_GetDlgItem
0x180014370  mov     rsi, rax
0x180014373  test    rax, rax
0x180014376  jz      loc_18001447D
0x18001437c  mov     rbx, [rdi+2B0h]
0x180014383  test    rbx, rbx
0x180014386  jnz     short loc_180014405
0x180014388  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001438f  lea     r8, [rsp+438h+Buffer]; lpBuffer
0x180014394  mov     r9d, 200h; cchBufferMax
0x18001439a  mov     edx, 1013h; uID
0x18001439f  call    cs:__imp_LoadStringW
0x1800143a5  mov     rcx, [rdi+70h]; hDlg
0x1800143a9  mov     edx, 69Dh; nIDDlgItem
0x1800143ae  call    cs:__imp_GetDlgItem
0x1800143b4  test    rax, rax
0x1800143b7  jz      short loc_1800143C7
0x1800143b9  lea     rdx, [rsp+438h+Buffer]; lpString
0x1800143be  mov     rcx, rax; hWnd
0x1800143c1  call    cs:__imp_SetWindowTextW
0x1800143c7  lea     r9, [rsp+438h+Buffer]; lParam
0x1800143cc  xor     r8d, r8d; wParam
0x1800143cf  mov     edx, 143h; Msg
0x1800143d4  mov     rcx, rsi; hWnd
0x1800143d7  call    cs:__imp_SendMessageW
0x1800143dd  test    eax, eax
0x1800143df  js      loc_18001447D
0x1800143e5  movsxd  r8, eax; wParam
0x1800143e8  xor     r9d, r9d; lParam
0x1800143eb  mov     edx, 151h; Msg
0x1800143f0  mov     rcx, rsi; hWnd
0x1800143f3  call    cs:__imp_SendMessageW
0x1800143f9  mov     eax, 1
0x1800143fe  jmp     short loc_18001447F
0x180014400  test    rbx, rbx
0x180014403  jz      short loc_1800143F9
0x180014405  lea     r8, [rsp+438h+Buffer]; unsigned __int16 *
0x18001440a  mov     edx, 1; int
0x18001440f  mov     rcx, rbx; this
0x180014412  call    ?TriggerString@CJobTrigger@@QEAAPEAGHQEAG_K@Z; CJobTrigger::TriggerString(int,ushort * const,unsigned __int64)
0x180014417  cmp     rbx, [rdi+2B0h]
0x18001441e  jnz     short loc_180014449
0x180014420  mov     rcx, [rdi+70h]; hDlg
0x180014424  mov     edx, 69Dh; nIDDlgItem
0x180014429  call    cs:__imp_GetDlgItem
0x18001442f  test    rax, rax
0x180014432  jz      short loc_180014442
0x180014434  lea     rdx, [rsp+438h+Buffer]; lpString
0x180014439  mov     rcx, rax; hWnd
0x18001443c  call    cs:__imp_SetWindowTextW
0x180014442  mov     [rdi+2D8h], rbx
0x180014449  lea     r9, [rsp+438h+Buffer]; lParam
0x18001444e  xor     r8d, r8d; wParam
0x180014451  mov     edx, 143h; Msg
0x180014456  mov     rcx, rsi; hWnd
0x180014459  call    cs:__imp_SendMessageW
0x18001445f  test    eax, eax
0x180014461  js      short loc_18001447D
0x180014463  movsxd  r8, eax; wParam
0x180014466  mov     r9, rbx; lParam
0x180014469  mov     edx, 151h; Msg
0x18001446e  mov     rcx, rsi; hWnd
0x180014471  call    cs:__imp_SendMessageW
0x180014477  mov     rbx, [rbx+8]
0x18001447b  jmp     short loc_180014400
0x18001447d  xor     eax, eax
0x18001447f  mov     rcx, [rsp+438h+var_18]
0x180014487  xor     rcx, rsp; StackCookie
0x18001448a  call    __security_check_cookie
0x18001448f  lea     r11, [rsp+438h+var_8]
0x180014497  mov     rbx, [r11+18h]
0x18001449b  mov     rsi, [r11+20h]
0x18001449f  mov     rsp, r11
0x1800144a2  pop     rdi
0x1800144a3  retn
```
