# MCIWndCommands

- ea: `0x180010194`
- end: `0x180010571`
- name: `MCIWndCommands`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010cc0`

## callees

- `0x180010194`
- `0x180010578`
- `0x1800129a0`
- `0x1800135a4`
- `0x1800144a8`
- `0x180014cc8`
- `0x180014fbc`

## import_xrefs

- `USER32!SendMessageW` at `0x1800101d7`
- `USER32!SendMessageW` at `0x18001022e`
- `USER32!SendMessageW` at `0x1800102b8`
- `USER32!SendMessageW` at `0x18001040d`
- `USER32!SendMessageW` at `0x180010439`
- `USER32!SendMessageW` at `0x1800101d7`
- `USER32!SendMessageW` at `0x18001022e`
- `USER32!SendMessageW` at `0x1800102b8`
- `USER32!SendMessageW` at `0x18001040d`
- `USER32!SendMessageW` at `0x180010439`
- `USER32!DialogBoxParamW` at `0x1800103ac`
- `USER32!DialogBoxParamW` at `0x1800103ac`
- `USER32!InvalidateRect` at `0x18001034c`
- `USER32!InvalidateRect` at `0x18001034c`
- `USER32!CheckMenuItem` at `0x18001024e`
- `USER32!CheckMenuItem` at `0x180010264`
- `USER32!CheckMenuItem` at `0x1800102d8`
- `USER32!CheckMenuItem` at `0x1800102ed`
- `USER32!CheckMenuItem` at `0x18001024e`
- `USER32!CheckMenuItem` at `0x180010264`
- `USER32!CheckMenuItem` at `0x1800102d8`
- `USER32!CheckMenuItem` at `0x1800102ed`
- `USER32!GetKeyState` at `0x1800103f0`
- `USER32!GetKeyState` at `0x18001044d`
- `USER32!GetKeyState` at `0x180010464`
- `USER32!GetKeyState` at `0x180010471`
- `USER32!GetKeyState` at `0x1800104dc`
- `USER32!GetKeyState` at `0x1800103f0`
- `USER32!GetKeyState` at `0x18001044d`
- `USER32!GetKeyState` at `0x180010464`
- `USER32!GetKeyState` at `0x180010471`
- `USER32!GetKeyState` at `0x1800104dc`

## string_xrefs

- `0x18001032d`: `configure`

## pseudocode

```c
__int64 __fastcall MCIWndCommands(__int64 a1, HWND a2, unsigned __int16 a3, __int64 a4)
{
  unsigned __int16 v7; // si
  unsigned __int16 v8; // bp
  UINT v9; // edx
  LPARAM v10; // r9
  unsigned __int16 KeyState; // ax
  SHORT v13; // ax
  int v14; // ecx
  WCHAR *v15; // r9
  SHORT v16; // ax
  int v17; // ecx
  WCHAR *v18; // r9

  v7 = a3;
  if ( (unsigned __int16)(a3 - 11000) <= 0x3E7u )
    SendMessageW(a2, 0x46Cu, 0, (unsigned int)a3 - 11000);
  if ( v7 == 12201 )
    v7 = *(_WORD *)(a1 + 120) + 12000;
  if ( v7 == 12202 )
  {
    v7 = 12000;
  }
  else if ( v7 < 0x2EE0u )
  {
    goto LABEL_12;
  }
  if ( v7 <= (unsigned int)(*(_DWORD *)(a1 + 120) + 12000)
    && !(unsigned int)SendMessageW(a2, 0x46Eu, 0, 10 * (unsigned int)v7 - 120000)
    && a4 != 42 )
  {
    CheckMenuItem(*(HMENU *)(a1 + 168), *(_DWORD *)(a1 + 912), 0);
    CheckMenuItem(*(HMENU *)(a1 + 168), v7, 8u);
  }
LABEL_12:
  if ( v7 == 13201 )
  {
    v8 = 13200;
  }
  else if ( v7 == 13202 )
  {
    v8 = 13000;
  }
  else
  {
    v8 = v7;
    if ( (unsigned __int16)(v7 - 13000) > 0xC8u )
      goto LABEL_20;
  }
  if ( !(unsigned int)SendMessageW(a2, 0x470u, 0, 10 * (unsigned int)v8 - 130000) && a4 != 42 )
  {
    CheckMenuItem(*(HMENU *)(a1 + 176), *(_DWORD *)(a1 + 912), 0);
    CheckMenuItem(*(HMENU *)(a1 + 176), v8, 8u);
  }
LABEL_20:
  if ( v8 > 0x6Fu )
  {
    switch ( v8 )
    {
      case 0x70u:
        MCIWndCopy(a1);
        break;
      case 0x806u:
        KeyState = GetKeyState(16);
        MCIWndiPlaySeek(a1, KeyState >> 15);
        if ( GetKeyState(17) >= 0 )
        {
          v16 = GetKeyState(16);
          v17 = *(_DWORD *)(a1 + 56);
          v18 = szRepeat;
          if ( v16 >= 0 )
          {
            if ( !v17 )
              v18 = &szNULL;
            if ( (unsigned int)MCIWndString(a1, 0, szPlay, v18) )
              MCIWndString(a1, 1, szPlay, &szNULL);
          }
          else
          {
            if ( !v17 )
              v18 = &szNULL;
            if ( (unsigned int)MCIWndString(a1, 0, szPlayReverse, v18) )
              MCIWndString(a1, 1, szPlayReverse, &szNULL);
          }
        }
        else
        {
          v13 = GetKeyState(16);
          v14 = *(_DWORD *)(a1 + 56);
          v15 = szRepeat;
          if ( v13 >= 0 )
          {
            if ( !v14 )
              v15 = &szNULL;
            if ( (unsigned int)MCIWndString(a1, 0, szPlayFullscreen, v15) )
              MCIWndString(a1, 1, szPlayFullscreen, &szNULL);
          }
          else
          {
            if ( !v14 )
              v15 = &szNULL;
            if ( (unsigned int)MCIWndString(a1, 0, szPlayFullscreenReverse, v15) )
              MCIWndString(a1, 1, szPlayFullscreenReverse, &szNULL);
          }
        }
        MCIWndiTimerStuff(a1);
        return 0;
      case 0x808u:
        v9 = 2056;
        goto LABEL_46;
      case 0x809u:
        v9 = 2057;
        goto LABEL_46;
      case 0x80Fu:
        if ( GetKeyState(16) >= 0 )
        {
          SendMessageW(a2, 0x80Fu, 0, 0);
          *(_DWORD *)(a1 + 88) = 0;
          MCIWndiMakeMeAMenu(a1);
        }
        return 0;
      case 0x813u:
        v10 = -1;
        v9 = 2067;
        return (int)SendMessageW(a2, v9, 0, v10);
    }
  }
  else
  {
    if ( v8 != 111 )
    {
      if ( v8 == 103 )
      {
        v9 = 1258;
      }
      else
      {
        if ( v8 == 104 )
        {
          v10 = -1;
          v9 = 1276;
          return (int)SendMessageW(a2, v9, 0, v10);
        }
        if ( v8 != 105 )
        {
          if ( v8 != 106 )
          {
            if ( v8 != 108 )
            {
              if ( v8 == 110 )
              {
                MCIWndString(a1, 1, szConfigure);
                MCIWndiSize(a1, 0);
                InvalidateRect(a2, 0, 1);
              }
              return 0;
            }
            v9 = 1131;
            goto LABEL_46;
          }
          v10 = -1;
          v9 = 2055;
          return (int)SendMessageW(a2, v9, 0, v10);
        }
        v9 = 2052;
      }
LABEL_46:
      v10 = 0;
      return (int)SendMessageW(a2, v9, 0, v10);
    }
    DialogBoxParamW(hInst, (LPCWSTR)0x3AE, a2, mciDlgProc, (LPARAM)a2);
  }
  return 0;
}

```

## disassembly

```asm
0x180010194  push    rbx
0x180010196  push    rbp
0x180010197  push    rsi
0x180010198  push    rdi
0x180010199  push    r12
0x18001019b  push    r14
0x18001019d  push    r15
0x18001019f  sub     rsp, 30h
0x1800101a3  mov     rdi, rdx
0x1800101a6  movzx   eax, r8w
0x1800101aa  mov     edx, 2AF8h
0x1800101af  mov     rbx, rcx
0x1800101b2  sub     ax, dx
0x1800101b5  mov     ecx, 3E7h
0x1800101ba  mov     r15, r9
0x1800101bd  mov     rsi, r8
0x1800101c0  cmp     ax, cx
0x1800101c3  ja      short loc_1800101DD
0x1800101c5  movzx   r9d, si
0x1800101c9  xor     r8d, r8d; wParam
0x1800101cc  sub     r9d, edx; lParam
0x1800101cf  mov     rcx, rdi; hWnd
0x1800101d2  mov     edx, 46Ch; Msg
0x1800101d7  call    cs:__imp_SendMessageW
0x1800101dd  mov     eax, 2FA9h
0x1800101e2  mov     ecx, 2EE0h
0x1800101e7  cmp     si, ax
0x1800101ea  jnz     short loc_1800101F2
0x1800101ec  mov     esi, ecx
0x1800101ee  add     si, [rbx+78h]
0x1800101f2  mov     eax, 2FAAh
0x1800101f7  xor     r12d, r12d
0x1800101fa  cmp     si, ax
0x1800101fd  jnz     short loc_180010204
0x1800101ff  movzx   esi, cx
0x180010202  jmp     short loc_180010209
0x180010204  cmp     si, cx
0x180010207  jb      short loc_18001026A
0x180010209  mov     eax, [rbx+78h]
0x18001020c  add     eax, ecx
0x18001020e  movzx   r14d, si
0x180010212  cmp     r14d, eax
0x180010215  ja      short loc_18001026A
0x180010217  lea     eax, [r14+r14*4]
0x18001021b  xor     r8d, r8d; wParam
0x18001021e  lea     r9d, ds:0FFFFFFFFFFFE2B40h[rax*2]; lParam
0x180010226  mov     edx, 46Eh; Msg
0x18001022b  mov     rcx, rdi; hWnd
0x18001022e  call    cs:__imp_SendMessageW
0x180010234  test    eax, eax
0x180010236  jnz     short loc_18001026A
0x180010238  cmp     r15, 2Ah ; '*'
0x18001023c  jz      short loc_18001026A
0x18001023e  mov     edx, [rbx+390h]; uIDCheckItem
0x180010244  xor     r8d, r8d; uCheck
0x180010247  mov     rcx, [rbx+0A8h]; hMenu
0x18001024e  call    cs:__imp_CheckMenuItem
0x180010254  mov     rcx, [rbx+0A8h]; hMenu
0x18001025b  mov     r8d, 8; uCheck
0x180010261  mov     edx, r14d; uIDCheckItem
0x180010264  call    cs:__imp_CheckMenuItem
0x18001026a  mov     eax, 3391h
0x18001026f  cmp     si, ax
0x180010272  jnz     short loc_180010279
0x180010274  lea     ebp, [rax-1]
0x180010277  jmp     short loc_18001029F
0x180010279  mov     eax, 3392h
0x18001027e  cmp     si, ax
0x180010281  jnz     short loc_18001028A
0x180010283  mov     ebp, 32C8h
0x180010288  jmp     short loc_18001029F
0x18001028a  mov     eax, 32C8h
0x18001028f  movzx   ebp, si
0x180010292  sub     si, ax
0x180010295  mov     eax, 0C8h
0x18001029a  cmp     si, ax
0x18001029d  ja      short loc_1800102F3
0x18001029f  movzx   esi, bp
0x1800102a2  xor     r8d, r8d; wParam
0x1800102a5  mov     edx, 470h; Msg
0x1800102aa  mov     rcx, rdi; hWnd
0x1800102ad  lea     eax, [rsi+rsi*4]
0x1800102b0  lea     r9d, ds:0FFFFFFFFFFFE0430h[rax*2]; lParam
0x1800102b8  call    cs:__imp_SendMessageW
0x1800102be  test    eax, eax
0x1800102c0  jnz     short loc_1800102F3
0x1800102c2  cmp     r15, 2Ah ; '*'
0x1800102c6  jz      short loc_1800102F3
0x1800102c8  mov     edx, [rbx+390h]; uIDCheckItem
0x1800102ce  xor     r8d, r8d; uCheck
0x1800102d1  mov     rcx, [rbx+0B0h]; hMenu
0x1800102d8  call    cs:__imp_CheckMenuItem
0x1800102de  mov     rcx, [rbx+0B0h]; hMenu
0x1800102e5  mov     r8d, 8; uCheck
0x1800102eb  mov     edx, esi; uIDCheckItem
0x1800102ed  call    cs:__imp_CheckMenuItem
0x1800102f3  movzx   ecx, bp
0x1800102f6  cmp     ecx, 6Fh ; 'o'
0x1800102f9  ja      loc_1800103B7
0x1800102ff  jz      loc_180010391
0x180010305  sub     ecx, 67h ; 'g'
0x180010308  jz      short loc_180010387
0x18001030a  sub     ecx, 1
0x18001030d  jz      short loc_180010379
0x18001030f  sub     ecx, 1
0x180010312  jz      short loc_18001036F
0x180010314  sub     ecx, 1
0x180010317  jz      short loc_180010361
0x180010319  sub     ecx, 2
0x18001031c  jz      short loc_180010357
0x18001031e  cmp     ecx, 2
0x180010321  jnz     loc_180010560
0x180010327  lea     edx, [rcx-1]
0x18001032a  mov     rcx, rbx
0x18001032d  lea     r8, szConfigure; "configure"
0x180010334  call    MCIWndString
0x180010339  xor     edx, edx
0x18001033b  mov     rcx, rbx
0x18001033e  call    MCIWndiSize
0x180010343  xor     edx, edx; lpRect
0x180010345  mov     rcx, rdi; hWnd
0x180010348  lea     r8d, [rdx+1]; bErase
0x18001034c  call    cs:__imp_InvalidateRect
0x180010352  jmp     loc_180010560
0x180010357  mov     edx, 46Bh
0x18001035c  jmp     loc_180010430
0x180010361  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010365  mov     edx, 807h
0x18001036a  jmp     loc_180010433
0x18001036f  mov     edx, 804h
0x180010374  jmp     loc_180010430
0x180010379  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001037d  mov     edx, 4FCh
0x180010382  jmp     loc_180010433
0x180010387  mov     edx, 4EAh
0x18001038c  jmp     loc_180010430
0x180010391  mov     rcx, cs:hInst; hInstance
0x180010398  lea     r9, mciDlgProc; lpDialogFunc
0x18001039f  mov     r8, rdi; hWndParent
0x1800103a2  mov     [rsp+68h+dwInitParam], rdi; dwInitParam
0x1800103a7  mov     edx, 3AEh; lpTemplateName
0x1800103ac  call    cs:__imp_DialogBoxParamW
0x1800103b2  jmp     loc_180010560
0x1800103b7  sub     ecx, 70h ; 'p'
0x1800103ba  jz      loc_180010558
0x1800103c0  sub     ecx, 796h
0x1800103c6  jz      short loc_180010446
0x1800103c8  sub     ecx, 2
0x1800103cb  jz      short loc_18001042B
0x1800103cd  sub     ecx, 1
0x1800103d0  jz      short loc_180010424
0x1800103d2  sub     ecx, 6
0x1800103d5  jz      short loc_1800103EB
0x1800103d7  cmp     ecx, 4
0x1800103da  jnz     loc_180010560
0x1800103e0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800103e4  mov     edx, 813h
0x1800103e9  jmp     short loc_180010433
0x1800103eb  mov     ecx, 10h; nVirtKey
0x1800103f0  call    cs:__imp_GetKeyState
0x1800103f6  test    ax, ax
0x1800103f9  js      loc_180010560
0x1800103ff  xor     r9d, r9d; lParam
0x180010402  xor     r8d, r8d; wParam
0x180010405  mov     edx, 80Fh; Msg
0x18001040a  mov     rcx, rdi; hWnd
0x18001040d  call    cs:__imp_SendMessageW
0x180010413  mov     rcx, rbx
0x180010416  mov     [rbx+58h], r12d
0x18001041a  call    MCIWndiMakeMeAMenu
0x18001041f  jmp     loc_180010560
0x180010424  mov     edx, 809h
0x180010429  jmp     short loc_180010430
0x18001042b  mov     edx, 808h; Msg
0x180010430  xor     r9d, r9d; lParam
0x180010433  xor     r8d, r8d; wParam
0x180010436  mov     rcx, rdi; hWnd
0x180010439  call    cs:__imp_SendMessageW
0x18001043f  cdqe
0x180010441  jmp     loc_180010562
0x180010446  mov     esi, 10h
0x18001044b  mov     ecx, esi; nVirtKey
0x18001044d  call    cs:__imp_GetKeyState
0x180010453  movzx   edx, ax
0x180010456  mov     rcx, rbx
0x180010459  shr     edx, 0Fh
0x18001045c  call    MCIWndiPlaySeek
0x180010461  lea     ecx, [rsi+1]; nVirtKey
0x180010464  call    cs:__imp_GetKeyState
0x18001046a  mov     ecx, esi; nVirtKey
0x18001046c  test    ax, ax
0x18001046f  jns     short loc_1800104DC
0x180010471  call    cs:__imp_GetKeyState
0x180010477  mov     ecx, [rbx+38h]
0x18001047a  lea     rdi, szNULL
0x180010481  lea     r9, szRepeat; "repeat"
0x180010488  test    ax, ax
0x18001048b  jns     short loc_1800104B8
0x18001048d  test    ecx, ecx
0x18001048f  lea     r8, szPlayFullscreenReverse; "play fullscreen reverse %s"
0x180010496  mov     rcx, rbx
0x180010499  cmovz   r9, rdi
0x18001049d  xor     edx, edx
0x18001049f  call    MCIWndString
0x1800104a4  test    eax, eax
0x1800104a6  jz      loc_18001054E
0x1800104ac  lea     r8, szPlayFullscreenReverse; "play fullscreen reverse %s"
0x1800104b3  jmp     loc_18001053E
0x1800104b8  test    ecx, ecx
0x1800104ba  lea     r8, szPlayFullscreen; "play fullscreen %s"
0x1800104c1  mov     rcx, rbx
0x1800104c4  cmovz   r9, rdi
0x1800104c8  xor     edx, edx
0x1800104ca  call    MCIWndString
0x1800104cf  test    eax, eax
0x1800104d1  jz      short loc_18001054E
0x1800104d3  lea     r8, szPlayFullscreen; "play fullscreen %s"
0x1800104da  jmp     short loc_18001053E
0x1800104dc  call    cs:__imp_GetKeyState
0x1800104e2  mov     ecx, [rbx+38h]
0x1800104e5  lea     rdi, szNULL
0x1800104ec  lea     r9, szRepeat; "repeat"
0x1800104f3  test    ax, ax
0x1800104f6  jns     short loc_18001051C
0x1800104f8  test    ecx, ecx
0x1800104fa  lea     r8, szPlayReverse; "play reverse %s"
0x180010501  mov     rcx, rbx
0x180010504  cmovz   r9, rdi
0x180010508  xor     edx, edx
0x18001050a  call    MCIWndString
0x18001050f  test    eax, eax
0x180010511  jz      short loc_18001054E
0x180010513  lea     r8, szPlayReverse; "play reverse %s"
0x18001051a  jmp     short loc_18001053E
0x18001051c  test    ecx, ecx
0x18001051e  lea     r8, szPlay; "play %s"
0x180010525  mov     rcx, rbx
0x180010528  cmovz   r9, rdi
0x18001052c  xor     edx, edx
0x18001052e  call    MCIWndString
0x180010533  test    eax, eax
0x180010535  jz      short loc_18001054E
0x180010537  lea     r8, szPlay; "play %s"
0x18001053e  mov     r9, rdi
0x180010541  mov     edx, 1
0x180010546  mov     rcx, rbx
0x180010549  call    MCIWndString
0x18001054e  mov     rcx, rbx
0x180010551  call    MCIWndiTimerStuff
0x180010556  jmp     short loc_180010560
0x180010558  mov     rcx, rbx
0x18001055b  call    MCIWndCopy
0x180010560  xor     eax, eax
0x180010562  add     rsp, 30h
0x180010566  pop     r15
0x180010568  pop     r14
0x18001056a  pop     r12
0x18001056c  pop     rdi
0x18001056d  pop     rsi
0x18001056e  pop     rbp
0x18001056f  pop     rbx
0x180010570  retn
```
