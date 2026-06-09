# SECEdit

- ea: `0x180047fd4`
- end: `0x180048322`
- name: `SECEdit`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18004060c`

## callees

- `0x1800115f0`
- `0x180017a0c`
- `0x180047fd4`
- `0x18004983c`
- `0x180049a2c`
- `0x180076c20`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180048086`
- `KERNEL32!lstrlenW` at `0x180048086`
- `USER32!MapWindowPoints` at `0x180048159`
- `USER32!MapWindowPoints` at `0x180048159`
- `USER32!PeekMessageW` at `0x1800482a1`
- `USER32!PeekMessageW` at `0x1800482a1`
- `USER32!PtInRect` at `0x180048221`
- `USER32!PtInRect` at `0x180048221`
- `USER32!TranslateMessage` at `0x180048265`
- `USER32!TranslateMessage` at `0x180048265`
- `USER32!DispatchMessageW` at `0x180048270`
- `USER32!DispatchMessageW` at `0x180048270`
- `USER32!WaitMessage` at `0x180048278`
- `USER32!WaitMessage` at `0x180048278`
- `USER32!SendMessageW` at `0x18004818c`
- `USER32!SendMessageW` at `0x1800481a0`
- `USER32!SendMessageW` at `0x18004818c`
- `USER32!SendMessageW` at `0x1800481a0`
- `USER32!DestroyWindow` at `0x1800482d1`
- `USER32!DestroyWindow` at `0x1800482d1`
- `USER32!ShowWindow` at `0x1800481bd`
- `USER32!ShowWindow` at `0x1800481bd`
- `USER32!CreateWindowExW` at `0x18004812e`
- `USER32!CreateWindowExW` at `0x18004812e`
- `USER32!SetFocus` at `0x1800481a9`
- `USER32!SetFocus` at `0x1800481a9`
- `USER32!GetFocus` at `0x1800482a9`
- `USER32!GetFocus` at `0x1800482a9`
- `USER32!InvalidateRect` at `0x180048177`
- `USER32!InvalidateRect` at `0x1800482eb`
- `USER32!InvalidateRect` at `0x180048177`
- `USER32!InvalidateRect` at `0x1800482eb`
- `USER32!GetMessageW` at `0x18004823c`
- `USER32!GetMessageW` at `0x18004823c`
- `USER32!GetWindowTextW` at `0x1800482c8`
- `USER32!GetWindowTextW` at `0x1800482c8`

## pseudocode

```c
__int64 __fastcall SECEdit(__int64 a1, WCHAR *a2)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  wchar_t *v5; // r15
  int v6; // r12d
  _DWORD *v7; // r14
  __int64 v8; // rdi
  int v9; // eax
  HWND Window; // rdi
  HWND *v11; // rcx
  int v12; // edx
  BOOL v13; // esi
  int i; // [rsp+60h] [rbp-A0h]
  unsigned int v16; // [rsp+64h] [rbp-9Ch]
  struct tagMSG Msg; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpString; // [rsp+98h] [rbp-68h]
  struct tagPOINT Points[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszDest[128]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = a1 + 152;
  lpString = a2;
  v3 = 0;
  v16 = *(_DWORD *)(a1 + 196);
  SECSetCurSubed(a1, 4294967294LL);
  v5 = pszDest;
  v6 = 128;
  v7 = (_DWORD *)(v2 + 48);
  if ( (*(_BYTE *)(v2 + 152) & 1) != 0 )
    v8 = *(_QWORD *)(v2 + 80) + 80LL * (*v7 - 1);
  else
    v8 = *(_QWORD *)(v2 + 80);
  for ( i = 0; i < *v7; v8 += (-(__int64)((*(_DWORD *)(v2 + 152) & 1) != 0) & 0xFFFFFFFFFFFFFF60uLL) + 80 )
  {
    if ( *(_DWORD *)v8 == 11 )
      StringCchCopyW(v5, v6, *(STRSAFE_LPCWSTR *)(v8 + 64));
    else
      SEGetTimeDateFormat(v8, v2, v5, (unsigned int)v6);
    v9 = lstrlenW(v5);
    v6 -= v9;
    ++i;
    v5 += v9;
  }
  SECSetCurSubed(a1, v16);
  Window = CreateWindowExW(
             0,
             L"EDIT",
             pszDest,
             0x40000080u,
             *(_DWORD *)(v2 + 24) + 2,
             *(_DWORD *)(v2 + 28) + 2,
             *(_DWORD *)(v2 + 32) - *(_DWORD *)(v2 + 24),
             *(_DWORD *)(v2 + 36) - *(_DWORD *)(v2 + 28),
             **(HWND **)v2,
             0,
             g_hinst,
             0);
  if ( Window )
  {
    v11 = *(HWND **)v2;
    *(_OWORD *)&Points[0].x = *(_OWORD *)(v2 + 24);
    MapWindowPoints(*v11, 0, Points, 2u);
    *(_DWORD *)(a1 + 376) |= 0x400u;
    InvalidateRect(**(HWND **)v2, 0, 1);
    SendMessageW(Window, 0xC5u, 0x7Fu, 0);
    SendMessageW(Window, 0x30u, *(_QWORD *)(v2 + 16), 0);
    SetFocus(Window);
    RescrollEditWindow(Window);
    ShowWindow(Window, 1);
    while ( 1 )
    {
      while ( 1 )
      {
        memset(&Msg, 0, sizeof(Msg));
        v13 = PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( GetFocus() != Window )
        {
LABEL_26:
          v3 = 1;
          GetWindowTextW(Window, lpString, 128);
          goto LABEL_27;
        }
        if ( v13 )
          break;
        WaitMessage();
      }
      if ( Msg.message - 259 <= 0xF )
      {
        v12 = 32795;
        if ( _bittest(&v12, Msg.message - 259) )
          break;
      }
      if ( Msg.message == 18 )
        break;
      if ( (Msg.message == 513 || Msg.message == 161 || Msg.message - 515 <= 1 || Msg.message == 164)
        && !PtInRect((const RECT *)Points, Msg.pt) )
      {
        goto LABEL_26;
      }
      GetMessageW(&Msg, 0, 0, 0);
      if ( Msg.message == 256 )
      {
        if ( Msg.wParam == 27 )
          break;
        if ( Msg.wParam == 13 )
          goto LABEL_26;
      }
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    v3 = 0;
LABEL_27:
    DestroyWindow(Window);
    *(_DWORD *)(a1 + 376) &= ~0x400u;
    InvalidateRect(**(HWND **)v2, 0, 1);
  }
  return v3;
}

```

## disassembly

```asm
0x180047fd4  mov     [rsp-8+arg_10], rbx
0x180047fd9  push    rbp
0x180047fda  push    rsi
0x180047fdb  push    rdi
0x180047fdc  push    r12
0x180047fde  push    r13
0x180047fe0  push    r14
0x180047fe2  push    r15
0x180047fe4  lea     rbp, [rsp-0C0h]
0x180047fec  sub     rsp, 1C0h
0x180047ff3  mov     rax, cs:__security_cookie
0x180047ffa  xor     rax, rsp
0x180047ffd  mov     [rbp+0F0h+var_40], rax
0x180048004  lea     rbx, [rcx+98h]
0x18004800b  mov     [rbp+0F0h+lpString], rdx
0x18004800f  mov     eax, [rbx+2Ch]
0x180048012  xor     esi, esi
0x180048014  mov     r13, rcx
0x180048017  mov     [rsp+1F0h+var_18C], eax
0x18004801b  lea     edx, [rsi-2]
0x18004801e  call    SECSetCurSubed
0x180048023  test    byte ptr [rbx+98h], 1
0x18004802a  lea     r15, [rbp+0F0h+pszDest]
0x18004802e  mov     r12d, 80h
0x180048034  lea     r14, [rbx+30h]
0x180048038  jz      short loc_18004804F
0x18004803a  mov     eax, [r14]
0x18004803d  dec     eax
0x18004803f  cdqe
0x180048041  lea     rdi, [rax+rax*4]
0x180048045  shl     rdi, 4
0x180048049  add     rdi, [rbx+50h]
0x18004804d  jmp     short loc_180048053
0x18004804f  mov     rdi, [rbx+50h]
0x180048053  mov     [rsp+1F0h+var_190], esi
0x180048057  cmp     [r14], esi
0x18004805a  jle     short loc_1800480BF
0x18004805c  cmp     dword ptr [rdi], 0Bh
0x18004805f  jnz     short loc_180048072
0x180048061  mov     r8, [rdi+40h]; pszSrc
0x180048065  mov     rcx, r15; pszDest
0x180048068  movsxd  rdx, r12d; cchDest
0x18004806b  call    StringCchCopyW
0x180048070  jmp     short loc_180048083
0x180048072  mov     r9d, r12d
0x180048075  mov     r8, r15
0x180048078  mov     rdx, rbx
0x18004807b  mov     rcx, rdi
0x18004807e  call    SEGetTimeDateFormat
0x180048083  mov     rcx, r15; lpString
0x180048086  call    cs:__imp_lstrlenW
0x18004808c  mov     edx, [rsp+1F0h+var_190]
0x180048090  sub     r12d, eax
0x180048093  cdqe
0x180048095  inc     edx
0x180048097  mov     [rsp+1F0h+var_190], edx
0x18004809b  lea     r15, [r15+rax*2]
0x18004809f  mov     eax, [rbx+98h]
0x1800480a5  and     al, 1
0x1800480a7  neg     al
0x1800480a9  sbb     rcx, rcx
0x1800480ac  and     rcx, 0FFFFFFFFFFFFFF60h
0x1800480b3  add     rcx, 50h ; 'P'
0x1800480b7  add     rdi, rcx
0x1800480ba  cmp     edx, [r14]
0x1800480bd  jl      short loc_18004805C
0x1800480bf  mov     edx, [rsp+1F0h+var_18C]
0x1800480c3  mov     rcx, r13
0x1800480c6  call    SECSetCurSubed
0x1800480cb  mov     eax, [rbx+18h]
0x1800480ce  xor     r14d, r14d
0x1800480d1  mov     r8, [rbx]
0x1800480d4  mov     ecx, [rbx+1Ch]
0x1800480d7  mov     r9d, [rbx+20h]
0x1800480db  mov     r10d, [rbx+24h]
0x1800480df  lea     edx, [rax+2]
0x1800480e2  mov     [rsp+1F0h+lpParam], r14; lpParam
0x1800480e7  sub     r9d, eax
0x1800480ea  mov     rax, cs:g_hinst
0x1800480f1  sub     r10d, ecx
0x1800480f4  mov     [rsp+1F0h+hInstance], rax; hInstance
0x1800480f9  add     ecx, 2
0x1800480fc  mov     rax, [r8]
0x1800480ff  lea     r8, [rbp+0F0h+pszDest]; lpWindowName
0x180048103  mov     [rsp+1F0h+hMenu], r14; hMenu
0x180048108  mov     [rsp+1F0h+hWndParent], rax; hWndParent
0x18004810d  mov     [rsp+1F0h+nHeight], r10d; nHeight
0x180048112  mov     [rsp+1F0h+nWidth], r9d; nWidth
0x180048117  mov     r9d, 40000080h; dwStyle
0x18004811d  mov     [rsp+1F0h+Y], ecx; Y
0x180048121  xor     ecx, ecx; dwExStyle
0x180048123  mov     [rsp+1F0h+X], edx; X
0x180048127  lea     rdx, aEdit; "EDIT"
0x18004812e  call    cs:__imp_CreateWindowExW
0x180048134  mov     rdi, rax
0x180048137  test    rax, rax
0x18004813a  jz      loc_1800482F1
0x180048140  movups  xmm0, xmmword ptr [rbx+18h]
0x180048144  mov     rcx, [rbx]
0x180048147  lea     r9d, [r14+2]; cPoints
0x18004814b  lea     r8, [rbp+0F0h+Points]; lpPoints
0x18004814f  xor     edx, edx; hWndTo
0x180048151  movdqu  xmmword ptr [rbp+0F0h+Points.x], xmm0
0x180048156  mov     rcx, [rcx]; hWndFrom
0x180048159  call    cs:__imp_MapWindowPoints
0x18004815f  bts     dword ptr [r13+178h], 0Ah
0x180048168  lea     r15d, [r14+1]
0x18004816c  mov     rcx, [rbx]
0x18004816f  mov     r8d, r15d; bErase
0x180048172  xor     edx, edx; lpRect
0x180048174  mov     rcx, [rcx]; hWnd
0x180048177  call    cs:__imp_InvalidateRect
0x18004817d  xor     r9d, r9d; lParam
0x180048180  lea     r8d, [r14+7Fh]; wParam
0x180048184  mov     edx, 0C5h; Msg
0x180048189  mov     rcx, rdi; hWnd
0x18004818c  call    cs:__imp_SendMessageW
0x180048192  mov     r8, [rbx+10h]; wParam
0x180048196  lea     edx, [r14+30h]; Msg
0x18004819a  xor     r9d, r9d; lParam
0x18004819d  mov     rcx, rdi; hWnd
0x1800481a0  call    cs:__imp_SendMessageW
0x1800481a6  mov     rcx, rdi; hWnd
0x1800481a9  call    cs:__imp_SetFocus
0x1800481af  mov     rcx, rdi
0x1800481b2  call    RescrollEditWindow
0x1800481b7  mov     edx, r15d; nCmdShow
0x1800481ba  mov     rcx, rdi; hWnd
0x1800481bd  call    cs:__imp_ShowWindow
0x1800481c3  jmp     loc_18004827E
0x1800481c8  test    esi, esi
0x1800481ca  jz      loc_180048278
0x1800481d0  mov     ecx, [rsp+1F0h+Msg.message]
0x1800481d4  lea     eax, [rcx-103h]
0x1800481da  cmp     eax, 0Fh
0x1800481dd  ja      short loc_1800481ED
0x1800481df  mov     edx, 801Bh
0x1800481e4  bt      edx, eax
0x1800481e7  jb      loc_18004831D
0x1800481ed  cmp     ecx, 12h
0x1800481f0  jz      loc_18004831D
0x1800481f6  cmp     ecx, 201h
0x1800481fc  jz      short loc_180048219
0x1800481fe  cmp     ecx, 0A1h
0x180048204  jz      short loc_180048219
0x180048206  lea     eax, [rcx-203h]
0x18004820c  cmp     eax, r15d
0x18004820f  jbe     short loc_180048219
0x180048211  cmp     ecx, 0A4h
0x180048217  jnz     short loc_18004822F
0x180048219  mov     rdx, qword ptr [rbp+0F0h+Msg.pt.x]; pt
0x18004821d  lea     rcx, [rbp+0F0h+Points]; lprc
0x180048221  call    cs:__imp_PtInRect
0x180048227  test    eax, eax
0x180048229  jz      loc_1800482B8
0x18004822f  xor     r9d, r9d; wMsgFilterMax
0x180048232  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180048237  xor     r8d, r8d; wMsgFilterMin
0x18004823a  xor     edx, edx; hWnd
0x18004823c  call    cs:__imp_GetMessageW
0x180048242  cmp     [rsp+1F0h+Msg.message], 100h
0x18004824a  jnz     short loc_180048260
0x18004824c  cmp     [rsp+1F0h+Msg.wParam], 1Bh
0x180048252  jz      loc_18004831D
0x180048258  cmp     [rsp+1F0h+Msg.wParam], 0Dh
0x18004825e  jz      short loc_1800482B8
0x180048260  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180048265  call    cs:__imp_TranslateMessage
0x18004826b  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180048270  call    cs:__imp_DispatchMessageW
0x180048276  jmp     short loc_18004827E
0x180048278  call    cs:__imp_WaitMessage
0x18004827e  xorps   xmm0, xmm0
0x180048281  mov     [rsp+1F0h+X], r14d; wRemoveMsg
0x180048286  xor     r9d, r9d; wMsgFilterMax
0x180048289  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x18004828e  xor     r8d, r8d; wMsgFilterMin
0x180048291  xor     edx, edx; hWnd
0x180048293  movups  xmmword ptr [rsp+1F0h+Msg.hwnd], xmm0
0x180048298  movups  xmmword ptr [rsp+1F0h+Msg.wParam], xmm0
0x18004829d  movups  xmmword ptr [rbp-78h], xmm0
0x1800482a1  call    cs:__imp_PeekMessageW
0x1800482a7  mov     esi, eax
0x1800482a9  call    cs:__imp_GetFocus
0x1800482af  cmp     rax, rdi
0x1800482b2  jz      loc_1800481C8
0x1800482b8  mov     rdx, [rbp+0F0h+lpString]; lpString
0x1800482bc  mov     r8d, 80h; nMaxCount
0x1800482c2  mov     rcx, rdi; hWnd
0x1800482c5  mov     esi, r15d
0x1800482c8  call    cs:__imp_GetWindowTextW
0x1800482ce  mov     rcx, rdi; hWnd
0x1800482d1  call    cs:__imp_DestroyWindow
0x1800482d7  btr     dword ptr [r13+178h], 0Ah
0x1800482e0  mov     r8d, r15d; bErase
0x1800482e3  mov     rcx, [rbx]
0x1800482e6  xor     edx, edx; lpRect
0x1800482e8  mov     rcx, [rcx]; hWnd
0x1800482eb  call    cs:__imp_InvalidateRect
0x1800482f1  mov     eax, esi
0x1800482f3  mov     rcx, [rbp+0F0h+var_40]
0x1800482fa  xor     rcx, rsp; StackCookie
0x1800482fd  call    __security_check_cookie
0x180048302  mov     rbx, [rsp+1F0h+arg_10]
0x18004830a  add     rsp, 1C0h
0x180048311  pop     r15
0x180048313  pop     r14
0x180048315  pop     r13
0x180048317  pop     r12
0x180048319  pop     rdi
0x18004831a  pop     rsi
0x18004831b  pop     rbp
0x18004831c  retn
0x18004831d  mov     esi, r14d
0x180048320  jmp     short loc_1800482CE
```
