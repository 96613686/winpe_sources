# DrFindAndSubclassClbNumbersControls

- ea: `0x18000baf4`
- end: `0x18000bc28`
- name: `DrFindAndSubclassClbNumbersControls`
- size: `308`
- prototype: `__int64 __fastcall(HANDLE hData)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bd74`

## callees

- `0x18000baf4`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb37`
- `USER32!SetPropW` at `0x18000bb92`
- `USER32!SetPropW` at `0x18000bba9`
- `USER32!SetPropW` at `0x18000bb92`
- `USER32!SetPropW` at `0x18000bba9`
- `USER32!GetComboBoxInfo` at `0x18000bb2d`
- `USER32!GetComboBoxInfo` at `0x18000bb2d`
- `USER32!SetWindowLongPtrW` at `0x18000bbc2`
- `USER32!SetWindowLongPtrW` at `0x18000bbe2`
- `USER32!SetWindowLongPtrW` at `0x18000bbc2`
- `USER32!SetWindowLongPtrW` at `0x18000bbe2`
- `rtutils!TracePrintfExA` at `0x18000bb5b`
- `rtutils!TracePrintfExA` at `0x18000bc0a`
- `rtutils!TracePrintfExA` at `0x18000bb5b`
- `rtutils!TracePrintfExA` at `0x18000bc0a`

## string_xrefs

- `0x18000bb4f`: `DrFindAndSubclassClbNumbersControls failed to get GetComboBoxInfo information. Error:%d`

## pseudocode

```c
__int64 __fastcall DrFindAndSubclassClbNumbersControls(HANDLE hData)
{
  HWND v2; // rcx
  DWORD LastError; // eax
  HWND hwndItem; // rcx
  HWND hwndList; // rax
  LONG_PTR v6; // rax
  HWND v7; // rcx
  tagCOMBOBOXINFO pcbi; // [rsp+20h] [rbp-58h] BYREF

  memset_0(&pcbi, 0, sizeof(pcbi));
  v2 = (HWND)*((_QWORD *)hData + 8);
  pcbi.cbSize = 64;
  if ( GetComboBoxInfo(v2, &pcbi) )
  {
    hwndItem = pcbi.hwndItem;
    hwndList = pcbi.hwndList;
    *((_QWORD *)hData + 23) = pcbi.hwndItem;
    *((_QWORD *)hData + 24) = hwndList;
    if ( hwndItem && hwndList )
    {
      SetPropW(hwndItem, g_contextId, hData);
      SetPropW(*((HWND *)hData + 24), g_contextId, hData);
      v6 = SetWindowLongPtrW(*((HWND *)hData + 23), -4, (LONG_PTR)DrClbNumbersEbWndProc);
      v7 = (HWND)*((_QWORD *)hData + 24);
      *((_QWORD *)hData + 25) = v6;
      *((_QWORD *)hData + 26) = SetWindowLongPtrW(v7, -4, (LONG_PTR)DrClbNumbersLbWndProc);
      return 0;
    }
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "DrFindAndSubclassClbNumbersControls failed to get handles for Editbox and Listbox");
  }
  else
  {
    LastError = GetLastError();
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "DrFindAndSubclassClbNumbersControls failed to get GetComboBoxInfo information. Error:%d",
        LastError);
  }
  return 1168;
}

```

## disassembly

```asm
0x18000baf4  push    rbx
0x18000baf6  sub     rsp, 70h
0x18000bafa  mov     rax, cs:__security_cookie
0x18000bb01  xor     rax, rsp
0x18000bb04  mov     [rsp+78h+var_18], rax
0x18000bb09  xor     edx, edx; Val
0x18000bb0b  mov     rbx, rcx
0x18000bb0e  lea     rcx, [rsp+78h+pcbi]; void *
0x18000bb13  lea     r8d, [rdx+40h]; Size
0x18000bb17  call    memset_0
0x18000bb1c  mov     rcx, [rbx+40h]; hwndCombo
0x18000bb20  lea     rdx, [rsp+78h+pcbi]; pcbi
0x18000bb25  mov     [rsp+78h+pcbi.cbSize], 40h ; '@'
0x18000bb2d  call    cs:__imp_GetComboBoxInfo
0x18000bb33  test    eax, eax
0x18000bb35  jnz     short loc_18000BB66
0x18000bb37  call    cs:__imp_GetLastError
0x18000bb3d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bb43  cmp     ecx, 0FFFFFFFFh
0x18000bb46  jz      loc_18000BC10
0x18000bb4c  mov     r9d, eax
0x18000bb4f  lea     r8, aDrfindandsubcl_0; "DrFindAndSubclassClbNumbersControls fai"...
0x18000bb56  mov     edx, 0Ch; dwFlags
0x18000bb5b  call    cs:__imp_TracePrintfExA
0x18000bb61  jmp     loc_18000BC10
0x18000bb66  mov     rcx, [rsp+78h+pcbi.hwndItem]; hWnd
0x18000bb6b  mov     rax, [rsp+78h+pcbi.hwndList]
0x18000bb70  mov     [rbx+0B8h], rcx
0x18000bb77  mov     [rbx+0C0h], rax
0x18000bb7e  test    rcx, rcx
0x18000bb81  jz      short loc_18000BBF3
0x18000bb83  test    rax, rax
0x18000bb86  jz      short loc_18000BBF3
0x18000bb88  mov     rdx, cs:g_contextId; lpString
0x18000bb8f  mov     r8, rbx; hData
0x18000bb92  call    cs:__imp_SetPropW
0x18000bb98  mov     rdx, cs:g_contextId; lpString
0x18000bb9f  mov     r8, rbx; hData
0x18000bba2  mov     rcx, [rbx+0C0h]; hWnd
0x18000bba9  call    cs:__imp_SetPropW
0x18000bbaf  mov     rcx, [rbx+0B8h]; hWnd
0x18000bbb6  lea     r8, DrClbNumbersEbWndProc; dwNewLong
0x18000bbbd  mov     edx, 0FFFFFFFCh; nIndex
0x18000bbc2  call    cs:__imp_SetWindowLongPtrW
0x18000bbc8  mov     rcx, [rbx+0C0h]; hWnd
0x18000bbcf  lea     r8, DrClbNumbersLbWndProc; dwNewLong
0x18000bbd6  mov     edx, 0FFFFFFFCh; nIndex
0x18000bbdb  mov     [rbx+0C8h], rax
0x18000bbe2  call    cs:__imp_SetWindowLongPtrW
0x18000bbe8  mov     [rbx+0D0h], rax
0x18000bbef  xor     eax, eax
0x18000bbf1  jmp     short loc_18000BC15
0x18000bbf3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bbf9  cmp     ecx, 0FFFFFFFFh
0x18000bbfc  jz      short loc_18000BC10
0x18000bbfe  lea     r8, aDrfindandsubcl; "DrFindAndSubclassClbNumbersControls fai"...
0x18000bc05  mov     edx, 0Ch; dwFlags
0x18000bc0a  call    cs:__imp_TracePrintfExA
0x18000bc10  mov     eax, 490h
0x18000bc15  mov     rcx, [rsp+78h+var_18]
0x18000bc1a  xor     rcx, rsp; StackCookie
0x18000bc1d  call    __security_check_cookie
0x18000bc22  add     rsp, 70h
0x18000bc26  pop     rbx
0x18000bc27  retn
```
