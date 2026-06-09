# MCIWndiCreate

- ea: `0x18001306c`
- end: `0x1800132b0`
- name: `MCIWndiCreate`
- size: `580`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cc0`

## callees

- `0x1800014b0`
- `0x18001306c`
- `0x180013c60`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001314c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001314c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013097`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013097`
- `SHELL32!DragAcceptFiles` at `0x1800130ff`
- `SHELL32!DragAcceptFiles` at `0x1800130ff`
- `USER32!SetWindowLongPtrW` at `0x1800130b3`
- `USER32!SetWindowLongPtrW` at `0x1800130b3`
- `USER32!SendMessageW` at `0x18001322a`
- `USER32!SendMessageW` at `0x180013288`
- `USER32!SendMessageW` at `0x18001322a`
- `USER32!SendMessageW` at `0x180013288`
- `USER32!GetWindowLongW` at `0x1800130e9`
- `USER32!GetWindowLongW` at `0x1800130e9`
- `USER32!GetParent` at `0x1800130bf`
- `USER32!GetParent` at `0x180013121`
- `USER32!GetParent` at `0x18001324c`
- `USER32!GetParent` at `0x1800130bf`
- `USER32!GetParent` at `0x180013121`
- `USER32!GetParent` at `0x18001324c`
- `USER32!IsWindowUnicode` at `0x18001325f`
- `USER32!IsWindowUnicode` at `0x18001325f`
- `USER32!GetClassNameW` at `0x18001313a`
- `USER32!GetClassNameW` at `0x18001313a`
- `USER32!LoadIconW` at `0x18001320f`
- `USER32!LoadIconW` at `0x18001320f`
- `USER32!GetWindow` at `0x1800130d4`
- `USER32!GetWindow` at `0x1800130d4`

## pseudocode

```c
LONG_PTR __fastcall MCIWndiCreate(HWND hWnd, LPARAM *a2)
{
  LONG_PTR result; // rax
  __int64 v5; // rbx
  HWND Parent; // rax
  LONG WindowLongW; // eax
  HWND v8; // rcx
  int v9; // eax
  LPARAM v10; // rdi
  HWND v11; // rax
  int v12; // eax
  HINSTANCE v13; // rcx
  HWND v14; // rax
  HWND v15; // rbx
  UINT v16; // edx
  WCHAR ClassName[20]; // [rsp+20h] [rbp-48h] BYREF

  result = (LONG_PTR)LocalAlloc(0x40u, 0x3B8u);
  v5 = result;
  if ( result )
  {
    SetWindowLongPtrW(hWnd, 0, result);
    *(_QWORD *)v5 = hWnd;
    Parent = GetParent(hWnd);
    *(_QWORD *)(v5 + 8) = Parent;
    if ( !Parent )
      *(_QWORD *)(v5 + 8) = GetWindow(hWnd, 4u);
    *(_DWORD *)(v5 + 16) = (_DWORD)hWnd;
    WindowLongW = GetWindowLongW(hWnd, -16);
    v8 = *(HWND *)v5;
    *(_DWORD *)(v5 + 32) = WindowLongW;
    DragAcceptFiles(v8, (WindowLongW & 0x8008) == 0);
    v9 = *(_DWORD *)(v5 + 32);
    if ( (v9 & 0xC00000) == 0 )
    {
      v9 &= 0xFFFFFF8F;
      *(_DWORD *)(v5 + 32) = v9;
    }
    v10 = *a2;
    if ( (v9 & 0x40000000) != 0 )
    {
      v11 = GetParent(hWnd);
      if ( v11 )
      {
        GetClassNameW(v11, ClassName, 20);
        v12 = lstrcmpiW(ClassName, szMDIClient);
        *(_DWORD *)(v5 + 104) = v12 == 0;
        if ( !v12 )
          v10 = *(_QWORD *)(v10 + 48);
      }
    }
    MCIWndiMakeMeAPlaybar(v5);
    *(_DWORD *)(v5 + 236) = 500;
    *(_WORD *)(v5 + 244) = 0;
    *(_QWORD *)(v5 + 808) = v5 + 244;
    v13 = hInst;
    *(_DWORD *)(v5 + 240) = 2000;
    *(_DWORD *)(v5 + 760) = 152;
    *(_QWORD *)(v5 + 768) = hWnd;
    *(_QWORD *)(v5 + 776) = 0;
    *(_QWORD *)(v5 + 792) = 0;
    *(_QWORD *)(v5 + 800) = 0;
    *(_DWORD *)(v5 + 816) = 128;
    *(_QWORD *)(v5 + 824) = 0;
    *(_DWORD *)(v5 + 832) = 0;
    *(_QWORD *)(v5 + 840) = 0;
    *(_QWORD *)(v5 + 848) = 0;
    *(_QWORD *)(v5 + 856) = 6148;
    *(_QWORD *)(v5 + 864) = 0;
    *(_QWORD *)(v5 + 872) = 0;
    *(_QWORD *)(v5 + 880) = 0;
    *(_QWORD *)(v5 + 888) = 0;
    *(_QWORD *)(v5 + 936) = LoadIconW(v13, (LPCWSTR)0x3AF);
    SendMessageW(hWnd, 0x804u, 0, 0);
    if ( !v10 )
      return 1;
    if ( fFileNameIsUnicode )
      goto LABEL_25;
    v14 = *(HWND *)(v5 + 8);
    if ( v14 )
    {
      do
      {
        v15 = v14;
        v14 = GetParent(v14);
      }
      while ( v14 );
    }
    else
    {
      v15 = 0;
    }
    if ( IsWindowUnicode(v15) )
    {
LABEL_25:
      if ( *(_WORD *)v10 )
      {
        v16 = 1276;
        goto LABEL_21;
      }
    }
    else if ( *(_BYTE *)v10 )
    {
      v16 = 1177;
LABEL_21:
      SendMessageW(hWnd, v16, 0, v10);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001306c  mov     [rsp+arg_10], rbx
0x180013071  push    rbp
0x180013072  push    rsi
0x180013073  push    rdi
0x180013074  sub     rsp, 50h
0x180013078  mov     rax, cs:__security_cookie
0x18001307f  xor     rax, rsp
0x180013082  mov     [rsp+68h+var_20], rax
0x180013087  mov     rdi, rdx
0x18001308a  mov     rsi, rcx
0x18001308d  mov     edx, 3B8h; uBytes
0x180013092  mov     ecx, 40h ; '@'; uFlags
0x180013097  call    cs:__imp_LocalAlloc
0x18001309d  xor     ebp, ebp
0x18001309f  mov     rbx, rax
0x1800130a2  test    rax, rax
0x1800130a5  jz      loc_180013293
0x1800130ab  mov     r8, rbx; dwNewLong
0x1800130ae  xor     edx, edx; nIndex
0x1800130b0  mov     rcx, rsi; hWnd
0x1800130b3  call    cs:__imp_SetWindowLongPtrW
0x1800130b9  mov     rcx, rsi; hWnd
0x1800130bc  mov     [rbx], rsi
0x1800130bf  call    cs:__imp_GetParent
0x1800130c5  mov     [rbx+8], rax
0x1800130c9  test    rax, rax
0x1800130cc  jnz     short loc_1800130DE
0x1800130ce  lea     edx, [rax+4]; uCmd
0x1800130d1  mov     rcx, rsi; hWnd
0x1800130d4  call    cs:__imp_GetWindow
0x1800130da  mov     [rbx+8], rax
0x1800130de  mov     edx, 0FFFFFFF0h; nIndex
0x1800130e3  mov     [rbx+10h], esi
0x1800130e6  mov     rcx, rsi; hWnd
0x1800130e9  call    cs:__imp_GetWindowLongW
0x1800130ef  mov     rcx, [rbx]; hWnd
0x1800130f2  mov     edx, ebp
0x1800130f4  test    eax, 8008h
0x1800130f9  mov     [rbx+20h], eax
0x1800130fc  setz    dl; fAccept
0x1800130ff  call    cs:__imp_DragAcceptFiles
0x180013105  mov     eax, [rbx+20h]
0x180013108  test    eax, 0C00000h
0x18001310d  jnz     short loc_180013115
0x18001310f  and     eax, 0FFFFFF8Fh
0x180013112  mov     [rbx+20h], eax
0x180013115  mov     rdi, [rdi]
0x180013118  bt      eax, 1Eh
0x18001311c  jnb     short loc_180013164
0x18001311e  mov     rcx, rsi; hWnd
0x180013121  call    cs:__imp_GetParent
0x180013127  test    rax, rax
0x18001312a  jz      short loc_180013164
0x18001312c  mov     r8d, 14h; nMaxCount
0x180013132  lea     rdx, [rsp+68h+ClassName]; lpClassName
0x180013137  mov     rcx, rax; hWnd
0x18001313a  call    cs:__imp_GetClassNameW
0x180013140  lea     rdx, szMDIClient; "MDIClient"
0x180013147  lea     rcx, [rsp+68h+ClassName]; lpString1
0x18001314c  call    cs:__imp_lstrcmpiW
0x180013152  test    eax, eax
0x180013154  mov     ecx, ebp
0x180013156  setz    cl
0x180013159  mov     [rbx+68h], ecx
0x18001315c  test    eax, eax
0x18001315e  jnz     short loc_180013164
0x180013160  mov     rdi, [rdi+30h]
0x180013164  mov     rcx, rbx
0x180013167  call    MCIWndiMakeMeAPlaybar
0x18001316c  lea     rcx, [rbx+0F4h]
0x180013173  mov     dword ptr [rbx+0ECh], 1F4h
0x18001317d  mov     [rcx], bp
0x180013180  mov     edx, 3AFh; lpIconName
0x180013185  mov     [rbx+328h], rcx
0x18001318c  mov     rcx, cs:hInst; hInstance
0x180013193  mov     dword ptr [rbx+0F0h], 7D0h
0x18001319d  mov     dword ptr [rbx+2F8h], 98h
0x1800131a7  mov     [rbx+300h], rsi
0x1800131ae  mov     [rbx+308h], rbp
0x1800131b5  mov     [rbx+318h], rbp
0x1800131bc  mov     [rbx+320h], rbp
0x1800131c3  mov     dword ptr [rbx+330h], 80h
0x1800131cd  mov     [rbx+338h], rbp
0x1800131d4  mov     [rbx+340h], ebp
0x1800131da  mov     [rbx+348h], rbp
0x1800131e1  mov     [rbx+350h], rbp
0x1800131e8  mov     qword ptr [rbx+358h], 1804h
0x1800131f3  mov     [rbx+360h], rbp
0x1800131fa  mov     [rbx+368h], rbp
0x180013201  mov     [rbx+370h], rbp
0x180013208  mov     [rbx+378h], rbp
0x18001320f  call    cs:__imp_LoadIconW
0x180013215  xor     r9d, r9d; lParam
0x180013218  xor     r8d, r8d; wParam
0x18001321b  mov     edx, 804h; Msg
0x180013220  mov     [rbx+3A8h], rax
0x180013227  mov     rcx, rsi; hWnd
0x18001322a  call    cs:__imp_SendMessageW
0x180013230  test    rdi, rdi
0x180013233  jz      short loc_18001328E
0x180013235  cmp     cs:fFileNameIsUnicode, ebp
0x18001323b  jnz     short loc_180013275
0x18001323d  mov     rax, [rbx+8]
0x180013241  test    rax, rax
0x180013244  jz      short loc_180013259
0x180013246  mov     rcx, rax; hWnd
0x180013249  mov     rbx, rax
0x18001324c  call    cs:__imp_GetParent
0x180013252  test    rax, rax
0x180013255  jnz     short loc_180013246
0x180013257  jmp     short loc_18001325C
0x180013259  mov     rbx, rax
0x18001325c  mov     rcx, rbx; hWnd
0x18001325f  call    cs:__imp_IsWindowUnicode
0x180013265  test    eax, eax
0x180013267  jnz     short loc_180013275
0x180013269  cmp     [rdi], bpl
0x18001326c  jz      short loc_18001328E
0x18001326e  mov     edx, 499h
0x180013273  jmp     short loc_18001327F
0x180013275  cmp     [rdi], bp
0x180013278  jz      short loc_18001328E
0x18001327a  mov     edx, 4FCh; Msg
0x18001327f  mov     r9, rdi; lParam
0x180013282  xor     r8d, r8d; wParam
0x180013285  mov     rcx, rsi; hWnd
0x180013288  call    cs:__imp_SendMessageW
0x18001328e  mov     eax, 1
0x180013293  mov     rcx, [rsp+68h+var_20]
0x180013298  xor     rcx, rsp; StackCookie
0x18001329b  call    __security_check_cookie
0x1800132a0  mov     rbx, [rsp+68h+arg_10]
0x1800132a8  add     rsp, 50h
0x1800132ac  pop     rdi
0x1800132ad  pop     rsi
0x1800132ae  pop     rbp
0x1800132af  retn
```
