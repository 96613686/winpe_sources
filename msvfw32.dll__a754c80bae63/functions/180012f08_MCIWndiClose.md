# MCIWndiClose

- ea: `0x180012f08`
- end: `0x180013063`
- name: `MCIWndiClose`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010cc0`
- `0x180013edc`

## callees

- `0x1800129a0`
- `0x180012f08`
- `0x180013358`
- `0x1800135a4`
- `0x180014cc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012feb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012feb`
- `USER32!SendMessageW` at `0x180012fa9`
- `USER32!SendMessageW` at `0x18001303c`
- `USER32!SendMessageW` at `0x180012fa9`
- `USER32!SendMessageW` at `0x18001303c`
- `USER32!GetWindowLongPtrW` at `0x180012f2d`
- `USER32!GetWindowLongPtrW` at `0x180012f2d`
- `USER32!InvalidateRect` at `0x18001304b`
- `USER32!InvalidateRect` at `0x18001304b`
- `USER32!SetWindowTextW` at `0x180012ffb`
- `USER32!SetWindowTextW` at `0x180012ffb`
- `USER32!PostMessageW` at `0x180012f70`
- `USER32!PostMessageW` at `0x180012f70`
- `WINMM!mciSendCommandW` at `0x180012f8f`
- `WINMM!mciSendCommandW` at `0x180012f8f`

## pseudocode

```c
__int64 __fastcall MCIWndiClose(__int64 a1, int a2)
{
  _DWORD *v4; // rdi
  MCIDEVICEID v5; // ecx
  __int64 result; // rax
  HWND v7; // rcx
  DWORD_PTR dwParam2; // [rsp+30h] [rbp+8h] BYREF

  dwParam2 = 0;
  if ( (__int64 (__fastcall *)(HWND, UINT, unsigned __int64, unsigned int *))GetWindowLongPtrW(*(HWND *)a1, -4) != MCIWndProc
    && (v4 = (_DWORD *)(a1 + 20), *(_DWORD *)(a1 + 20))
    && *(_DWORD *)(a1 + 60) )
  {
    MCIWndString(a1, 0, szWindowHandle, 0);
    PostMessageW(*(HWND *)a1, 0x804u, 0, (unsigned int)*v4);
  }
  else
  {
    v4 = (_DWORD *)(a1 + 20);
    v5 = *(_DWORD *)(a1 + 20);
    if ( v5 )
      mciSendCommandW(v5, 0x804u, 0, (DWORD_PTR)&dwParam2);
  }
  if ( *(_DWORD *)(a1 + 64) )
    SendMessageW(*(HWND *)a1, 0x496u, 0, 0);
  result = 0;
  *v4 = 0;
  *(_WORD *)(a1 + 244) = 0;
  *(_DWORD *)(a1 + 212) = 0;
  if ( a2 )
  {
    if ( (*(_BYTE *)(a1 + 32) & 0x70) != 0 )
    {
      LoadStringW(hInst, 0x150u, &NewItem, 128);
      SetWindowTextW(*(HWND *)a1, &NewItem);
    }
    MCIWndiFixMyPlaybar(a1);
    MCIWndiMakeMeAMenu(a1);
    MCIWndiSize(a1, 0);
    if ( (*(_DWORD *)(a1 + 32) & 0x800) != 0 )
    {
      v7 = *(HWND *)(a1 + 8);
      if ( v7 )
        SendMessageW(v7, 0x4CBu, *(_QWORD *)a1, (LPARAM)&szNULL);
    }
    InvalidateRect(*(HWND *)a1, 0, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012f08  mov     [rsp+arg_8], rbx
0x180012f0d  mov     [rsp+arg_10], rsi
0x180012f12  push    rdi
0x180012f13  sub     rsp, 20h
0x180012f17  mov     esi, edx
0x180012f19  mov     [rsp+28h+dwParam2], 0
0x180012f22  mov     rbx, rcx
0x180012f25  mov     edx, 0FFFFFFFCh; nIndex
0x180012f2a  mov     rcx, [rcx]; hWnd
0x180012f2d  call    cs:__imp_GetWindowLongPtrW
0x180012f33  lea     rcx, MCIWndProc
0x180012f3a  cmp     rax, rcx
0x180012f3d  jz      short loc_180012F78
0x180012f3f  lea     rdi, [rbx+14h]
0x180012f43  cmp     dword ptr [rdi], 0
0x180012f46  jz      short loc_180012F78
0x180012f48  cmp     dword ptr [rbx+3Ch], 0
0x180012f4c  jz      short loc_180012F78
0x180012f4e  xor     r9d, r9d
0x180012f51  lea     r8, szWindowHandle; "window handle %u"
0x180012f58  xor     edx, edx
0x180012f5a  mov     rcx, rbx
0x180012f5d  call    MCIWndString
0x180012f62  mov     r9d, [rdi]; lParam
0x180012f65  xor     r8d, r8d; wParam
0x180012f68  mov     rcx, [rbx]; hWnd
0x180012f6b  mov     edx, 804h; Msg
0x180012f70  call    cs:__imp_PostMessageW
0x180012f76  jmp     short loc_180012F95
0x180012f78  lea     rdi, [rbx+14h]
0x180012f7c  mov     ecx, [rdi]; mciId
0x180012f7e  test    ecx, ecx
0x180012f80  jz      short loc_180012F95
0x180012f82  lea     r9, [rsp+28h+dwParam2]; dwParam2
0x180012f87  xor     r8d, r8d; dwParam1
0x180012f8a  mov     edx, 804h; uMsg
0x180012f8f  call    cs:__imp_mciSendCommandW
0x180012f95  cmp     dword ptr [rbx+40h], 0
0x180012f99  jz      short loc_180012FAF
0x180012f9b  mov     rcx, [rbx]; hWnd
0x180012f9e  xor     r9d, r9d; lParam
0x180012fa1  xor     r8d, r8d; wParam
0x180012fa4  mov     edx, 496h; Msg
0x180012fa9  call    cs:__imp_SendMessageW
0x180012faf  xor     eax, eax
0x180012fb1  mov     dword ptr [rdi], 0
0x180012fb7  mov     [rbx+0F4h], ax
0x180012fbe  mov     [rbx+0D4h], eax
0x180012fc4  test    esi, esi
0x180012fc6  jz      loc_180013053
0x180012fcc  test    byte ptr [rbx+20h], 70h
0x180012fd0  jz      short loc_180013001
0x180012fd2  mov     rcx, cs:hInst; hInstance
0x180012fd9  lea     r8, NewItem; lpBuffer
0x180012fe0  mov     r9d, 80h; cchBufferMax
0x180012fe6  mov     edx, 150h; uID
0x180012feb  call    cs:__imp_LoadStringW
0x180012ff1  mov     rcx, [rbx]; hWnd
0x180012ff4  lea     rdx, NewItem; lpString
0x180012ffb  call    cs:__imp_SetWindowTextW
0x180013001  mov     rcx, rbx
0x180013004  call    MCIWndiFixMyPlaybar
0x180013009  mov     rcx, rbx
0x18001300c  call    MCIWndiMakeMeAMenu
0x180013011  xor     edx, edx
0x180013013  mov     rcx, rbx
0x180013016  call    MCIWndiSize
0x18001301b  test    dword ptr [rbx+20h], 800h
0x180013022  jz      short loc_180013042
0x180013024  mov     rcx, [rbx+8]; hWnd
0x180013028  test    rcx, rcx
0x18001302b  jz      short loc_180013042
0x18001302d  mov     r8, [rbx]; wParam
0x180013030  lea     r9, szNULL; lParam
0x180013037  mov     edx, 4CBh; Msg
0x18001303c  call    cs:__imp_SendMessageW
0x180013042  mov     rcx, [rbx]; hWnd
0x180013045  xor     edx, edx; lpRect
0x180013047  lea     r8d, [rdx+1]; bErase
0x18001304b  call    cs:__imp_InvalidateRect
0x180013051  xor     eax, eax
0x180013053  mov     rbx, [rsp+28h+arg_8]
0x180013058  mov     rsi, [rsp+28h+arg_10]
0x18001305d  add     rsp, 20h
0x180013061  pop     rdi
0x180013062  retn
```
