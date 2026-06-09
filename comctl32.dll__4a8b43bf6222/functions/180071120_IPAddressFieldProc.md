# IPAddressFieldProc

- ea: `0x180071120`
- end: `0x180071509`
- name: `IPAddressFieldProc`
- size: `1001`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180070fac`
- `0x180070ff8`
- `0x180071120`
- `0x180071ffc`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800714f0`
- `GDI32!DeleteObject` at `0x1800714f0`
- `USER32!GetParent` at `0x18007113d`
- `USER32!GetParent` at `0x18007113d`
- `USER32!SendMessageW` at `0x1800711eb`
- `USER32!SendMessageW` at `0x18007126c`
- `USER32!SendMessageW` at `0x1800712b3`
- `USER32!SendMessageW` at `0x1800712d2`
- `USER32!SendMessageW` at `0x1800712f7`
- `USER32!SendMessageW` at `0x180071407`
- `USER32!SendMessageW` at `0x180071461`
- `USER32!SendMessageW` at `0x1800714e7`
- `USER32!SendMessageW` at `0x1800711eb`
- `USER32!SendMessageW` at `0x18007126c`
- `USER32!SendMessageW` at `0x1800712b3`
- `USER32!SendMessageW` at `0x1800712d2`
- `USER32!SendMessageW` at `0x1800712f7`
- `USER32!SendMessageW` at `0x180071407`
- `USER32!SendMessageW` at `0x180071461`
- `USER32!SendMessageW` at `0x1800714e7`
- `USER32!MessageBeep` at `0x180071334`
- `USER32!MessageBeep` at `0x180071334`
- `USER32!GetKeyState` at `0x18007139a`
- `USER32!GetKeyState` at `0x18007139a`
- `USER32!GetWindowLongPtrW` at `0x180071158`
- `USER32!GetWindowLongPtrW` at `0x18007116f`
- `USER32!GetWindowLongPtrW` at `0x180071158`
- `USER32!GetWindowLongPtrW` at `0x18007116f`
- `USER32!CallWindowProcW` at `0x1800711d7`
- `USER32!CallWindowProcW` at `0x1800714d2`
- `USER32!CallWindowProcW` at `0x1800711d7`
- `USER32!CallWindowProcW` at `0x1800714d2`

## pseudocode

```c
LRESULT __fastcall IPAddressFieldProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  HWND Parent; // rax
  LONG_PTR WindowLongPtrW; // rdi
  unsigned int v10; // eax
  __int64 v11; // r15
  unsigned int v12; // ebx
  LRESULT v13; // rsi
  __int64 v15; // rax
  __int64 v16; // rbx
  LRESULT v17; // rax
  unsigned int v18; // r8d
  int v19; // r9d
  unsigned int v20; // r8d
  int v21; // eax
  void *v22; // rax
  __int16 lParama; // [rsp+20h] [rbp-58h]

  Parent = GetParent(hWnd);
  if ( !Parent )
    return 0;
  WindowLongPtrW = GetWindowLongPtrW(Parent, -21);
  if ( !WindowLongPtrW )
    return 0;
  v10 = GetWindowLongPtrW(hWnd, -21);
  v11 = v10;
  v12 = v10;
  if ( *(HWND *)(WindowLongPtrW + 24LL * v10 + 40) != hWnd )
    return 0;
  switch ( Msg )
  {
    case 2u:
      v22 = (void *)SendMessageW(hWnd, 0x31u, 0, 0);
      DeleteObject(v22);
      return 0;
    case 8u:
      if ( (unsigned int)ExitField(WindowLongPtrW, v10) )
        return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
      return 0;
    case 0x100u:
      if ( wParam == 35 )
      {
        if ( v10 >= 3 )
          return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
        SwitchFields(WindowLongPtrW, v10, 3, 3, 3);
        return 0;
      }
      if ( wParam == 36 )
      {
        if ( !v10 )
          return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
        SwitchFields(WindowLongPtrW, v10, 0, 0, 0);
        return 0;
      }
      if ( wParam != 37 && wParam != 38 && wParam - 39 > 1 )
        return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
      if ( GetKeyState(17) >= 0 )
      {
        v21 = SendMessageW(hWnd, 0xB0u, 0, 0);
        if ( (_WORD)v21 != HIWORD(v21) )
          return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
        if ( wParam - 37 > 1 || (_WORD)v21 || !v12 )
        {
          if ( wParam - 39 > 1 || v12 >= 3 || (unsigned __int16)v21 < (unsigned int)SendMessageW(hWnd, 0xC1u, 0, 0) )
            return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
          v18 = v12 + 1;
          lParama = 0;
          goto LABEL_39;
        }
        v20 = v12 - 1;
        v19 = 3;
      }
      else
      {
        if ( wParam - 37 <= 1 && v12 )
        {
          v18 = v12 - 1;
          lParama = 3;
LABEL_39:
          SwitchFields(WindowLongPtrW, v12, v18, 0, lParama);
          return 0;
        }
        if ( wParam - 39 > 1 || v12 >= 3 )
          return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
        v19 = 0;
        v20 = v12 + 1;
      }
      SwitchFields(WindowLongPtrW, v12, v20, v19, 3);
      return 0;
  }
  if ( Msg != 258 )
    return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
  if ( wParam - 48 > 9 )
  {
    if ( wParam == 46 || wParam == 32 )
    {
      v17 = SendMessageW(hWnd, 0xB0u, 0, 0);
      if ( !v17 || WORD1(v17) != (_WORD)v17 || !(unsigned int)ExitField(WindowLongPtrW, v12) )
        return 0;
      if ( v12 < 3 )
      {
        EnterField(WindowLongPtrW + 8 * (v12 + 1 + 2LL * (v12 + 1) + 5), 0, 3);
        return 0;
      }
    }
    else
    {
      if ( wParam == 8 )
      {
        if ( v10 && !SendMessageW(hWnd, 0xB0u, 0, 0) )
        {
          if ( (unsigned int)SwitchFields(WindowLongPtrW, v12, v12 - 1, 3, 3) )
          {
            v15 = v12 - 1;
            v16 = 3 * v15;
            if ( SendMessageW(*(HWND *)(WindowLongPtrW + 24 * v15 + 40), 0xC1u, 0, 0) )
              SendMessageW(*(HWND *)(WindowLongPtrW + 8 * v16 + 40), 0x102u, 8u, lParam);
          }
          return 0;
        }
        return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
      }
      if ( wParam <= 0x20 )
        return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24 * v11 + 48), hWnd, Msg, wParam, lParam);
    }
    MessageBeep(0xFFFFFFFF);
    return 0;
  }
  CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24LL * v10 + 48), hWnd, 0x102u, wParam, lParam);
  v13 = SendMessageW(hWnd, 0xB0u, 0, 0);
  if ( v13 == 196611 && (unsigned int)ExitField(WindowLongPtrW, v12) && v12 < 3 )
    EnterField(WindowLongPtrW + 8 * (v12 + 1 + 2LL * (v12 + 1) + 5), 0, 3);
  return v13;
}

```

## disassembly

```asm
0x180071120  push    rbx
0x180071122  push    rbp
0x180071123  push    rsi
0x180071124  push    rdi
0x180071125  push    r12
0x180071127  push    r13
0x180071129  push    r14
0x18007112b  push    r15
0x18007112d  sub     rsp, 38h
0x180071131  mov     r12, r9
0x180071134  mov     rsi, r8
0x180071137  mov     r13d, edx
0x18007113a  mov     rbp, rcx
0x18007113d  call    cs:__imp_GetParent
0x180071143  xor     r14d, r14d
0x180071146  test    rax, rax
0x180071149  jz      loc_1800714F6
0x18007114f  lea     ebx, [r14-15h]
0x180071153  mov     rcx, rax; hWnd
0x180071156  mov     edx, ebx; nIndex
0x180071158  call    cs:__imp_GetWindowLongPtrW
0x18007115e  mov     rdi, rax
0x180071161  test    rax, rax
0x180071164  jz      loc_1800714F6
0x18007116a  mov     edx, ebx; nIndex
0x18007116c  mov     rcx, rbp; hWnd
0x18007116f  call    cs:__imp_GetWindowLongPtrW
0x180071175  mov     r15d, eax
0x180071178  mov     rbx, rax
0x18007117b  lea     rcx, [r15+r15*2]
0x18007117f  cmp     [rdi+rcx*8+28h], rbp
0x180071184  jnz     loc_1800714F6
0x18007118a  mov     eax, r13d
0x18007118d  sub     eax, 2
0x180071190  jz      loc_1800714DA
0x180071196  sub     eax, 6
0x180071199  jz      loc_1800714AD
0x18007119f  sub     eax, 0F8h
0x1800711a4  jz      loc_180071362
0x1800711aa  cmp     eax, 2
0x1800711ad  jnz     loc_1800714BB
0x1800711b3  lea     rax, [rsi-30h]
0x1800711b7  cmp     rax, 9
0x1800711bb  ja      short loc_180071238
0x1800711bd  lea     rcx, [r15+r15*2]
0x1800711c1  mov     qword ptr [rsp+78h+lParam], r12; lParam
0x1800711c6  mov     rcx, [rdi+rcx*8+30h]; lpPrevWndFunc
0x1800711cb  mov     r9, rsi; wParam
0x1800711ce  mov     r8d, 102h; Msg
0x1800711d4  mov     rdx, rbp; hWnd
0x1800711d7  call    cs:__imp_CallWindowProcW
0x1800711dd  xor     r9d, r9d; lParam
0x1800711e0  xor     r8d, r8d; wParam
0x1800711e3  mov     edx, 0B0h; Msg
0x1800711e8  mov     rcx, rbp; hWnd
0x1800711eb  call    cs:__imp_SendMessageW
0x1800711f1  mov     rsi, rax
0x1800711f4  cmp     rax, 30003h
0x1800711fa  jnz     short loc_180071230
0x1800711fc  mov     edx, ebx
0x1800711fe  mov     rcx, rdi
0x180071201  call    ExitField
0x180071206  test    eax, eax
0x180071208  jz      short loc_180071230
0x18007120a  lea     ecx, [r14+3]
0x18007120e  cmp     ebx, ecx
0x180071210  jnb     short loc_180071230
0x180071212  mov     r8d, ecx
0x180071215  lea     eax, [rbx+1]
0x180071218  mov     ecx, eax
0x18007121a  xor     edx, edx
0x18007121c  lea     rax, ds:5[rax*2]
0x180071224  add     rax, rcx
0x180071227  lea     rcx, [rdi+rax*8]
0x18007122b  call    EnterField
0x180071230  mov     rax, rsi
0x180071233  jmp     loc_1800714F8
0x180071238  cmp     rsi, 2Eh ; '.'
0x18007123c  jz      loc_1800712E9
0x180071242  cmp     rsi, 20h ; ' '
0x180071246  jz      loc_1800712E9
0x18007124c  cmp     rsi, 8
0x180071250  jnz     loc_1800712DD
0x180071256  test    ebx, ebx
0x180071258  jz      loc_1800714BB
0x18007125e  xor     r9d, r9d; lParam
0x180071261  xor     r8d, r8d; wParam
0x180071264  mov     edx, 0B0h; Msg
0x180071269  mov     rcx, rbp; hWnd
0x18007126c  call    cs:__imp_SendMessageW
0x180071272  test    rax, rax
0x180071275  jnz     loc_1800714BB
0x18007127b  lea     ecx, [rsi-5]
0x18007127e  mov     edx, ebx
0x180071280  mov     r9d, ecx
0x180071283  mov     [rsp+78h+lParam], cx
0x180071288  mov     rcx, rdi
0x18007128b  lea     r8d, [rbx-1]
0x18007128f  call    SwitchFields
0x180071294  test    eax, eax
0x180071296  jz      loc_1800714F6
0x18007129c  lea     eax, [rbx-1]
0x18007129f  xor     r9d, r9d; lParam
0x1800712a2  lea     rbx, [rax+rax*2]
0x1800712a6  xor     r8d, r8d; wParam
0x1800712a9  mov     rcx, [rdi+rbx*8+28h]; hWnd
0x1800712ae  mov     edx, 0C1h; Msg
0x1800712b3  call    cs:__imp_SendMessageW
0x1800712b9  test    rax, rax
0x1800712bc  jz      loc_1800714F6
0x1800712c2  mov     rcx, [rdi+rbx*8+28h]; hWnd
0x1800712c7  mov     r9, r12; lParam
0x1800712ca  mov     edx, 102h; Msg
0x1800712cf  mov     r8, rsi; wParam
0x1800712d2  call    cs:__imp_SendMessageW
0x1800712d8  jmp     loc_1800714F6
0x1800712dd  cmp     rsi, 20h ; ' '
0x1800712e1  jbe     loc_1800714BB
0x1800712e7  jmp     short loc_180071331
0x1800712e9  xor     r9d, r9d; lParam
0x1800712ec  xor     r8d, r8d; wParam
0x1800712ef  mov     edx, 0B0h; Msg
0x1800712f4  mov     rcx, rbp; hWnd
0x1800712f7  call    cs:__imp_SendMessageW
0x1800712fd  test    rax, rax
0x180071300  jz      loc_1800714F6
0x180071306  mov     rcx, rax
0x180071309  shr     rcx, 10h
0x18007130d  cmp     cx, ax
0x180071310  jnz     loc_1800714F6
0x180071316  mov     edx, ebx
0x180071318  mov     rcx, rdi
0x18007131b  call    ExitField
0x180071320  test    eax, eax
0x180071322  jz      loc_1800714F6
0x180071328  mov     ecx, 3
0x18007132d  cmp     ebx, ecx
0x18007132f  jb      short loc_18007133F
0x180071331  or      ecx, 0FFFFFFFFh; uType
0x180071334  call    cs:__imp_MessageBeep
0x18007133a  jmp     loc_1800714F6
0x18007133f  mov     r8d, ecx
0x180071342  lea     eax, [rbx+1]
0x180071345  mov     ecx, eax
0x180071347  xor     edx, edx
0x180071349  lea     rax, ds:5[rax*2]
0x180071351  add     rax, rcx
0x180071354  lea     rcx, [rdi+rax*8]
0x180071358  call    EnterField
0x18007135d  jmp     loc_1800714F6
0x180071362  mov     rax, rsi
0x180071365  sub     rax, 23h ; '#'
0x180071369  jz      loc_180071494
0x18007136f  sub     rax, 1
0x180071373  jz      loc_18007147F
0x180071379  sub     rax, 1
0x18007137d  jz      short loc_180071395
0x18007137f  sub     rax, 1
0x180071383  jz      short loc_180071395
0x180071385  sub     rax, 1
0x180071389  jz      short loc_180071395
0x18007138b  cmp     rax, 1
0x18007138f  jnz     loc_1800714BB
0x180071395  mov     ecx, 11h; nVirtKey
0x18007139a  call    cs:__imp_GetKeyState
0x1800713a0  test    ax, ax
0x1800713a3  jns     short loc_1800713F9
0x1800713a5  lea     rax, [rsi-25h]
0x1800713a9  cmp     rax, 1
0x1800713ad  ja      short loc_1800713D0
0x1800713af  test    ebx, ebx
0x1800713b1  jz      short loc_1800713D0
0x1800713b3  lea     r8d, [rbx-1]
0x1800713b7  mov     [rsp+78h+lParam], 3
0x1800713be  xor     r9d, r9d
0x1800713c1  mov     edx, ebx
0x1800713c3  mov     rcx, rdi
0x1800713c6  call    SwitchFields
0x1800713cb  jmp     loc_1800714F6
0x1800713d0  lea     rax, [rsi-27h]
0x1800713d4  cmp     rax, 1
0x1800713d8  ja      loc_1800714BB
0x1800713de  mov     ecx, 3
0x1800713e3  cmp     ebx, ecx
0x1800713e5  jnb     loc_1800714BB
0x1800713eb  xor     r9d, r9d
0x1800713ee  lea     r8d, [rbx+1]
0x1800713f2  mov     [rsp+78h+lParam], cx
0x1800713f7  jmp     short loc_1800713C1
0x1800713f9  xor     r9d, r9d; lParam
0x1800713fc  xor     r8d, r8d; wParam
0x1800713ff  mov     edx, 0B0h; Msg
0x180071404  mov     rcx, rbp; hWnd
0x180071407  call    cs:__imp_SendMessageW
0x18007140d  mov     ecx, eax
0x18007140f  mov     r14, rax
0x180071412  shr     ecx, 10h
0x180071415  cmp     ax, cx
0x180071418  jnz     loc_1800714BB
0x18007141e  lea     rcx, [rsi-25h]
0x180071422  cmp     rcx, 1
0x180071426  ja      short loc_180071440
0x180071428  test    r14w, r14w
0x18007142c  jnz     short loc_180071440
0x18007142e  test    ebx, ebx
0x180071430  jz      short loc_180071440
0x180071432  mov     ecx, 3
0x180071437  lea     r8d, [rbx-1]
0x18007143b  mov     r9d, ecx
0x18007143e  jmp     short loc_1800713F2
0x180071440  lea     rax, [rsi-27h]
0x180071444  cmp     rax, 1
0x180071448  ja      short loc_1800714BB
0x18007144a  mov     ecx, 3
0x18007144f  cmp     ebx, ecx
0x180071451  jnb     short loc_1800714BB
0x180071453  xor     r9d, r9d; lParam
0x180071456  xor     r8d, r8d; wParam
0x180071459  mov     edx, 0C1h; Msg
0x18007145e  mov     rcx, rbp; hWnd
0x180071461  call    cs:__imp_SendMessageW
0x180071467  movzx   ecx, r14w
0x18007146b  cmp     ecx, eax
0x18007146d  jb      short loc_1800714BB
0x18007146f  xor     eax, eax
0x180071471  lea     r8d, [rbx+1]
0x180071475  mov     [rsp+78h+lParam], ax
0x18007147a  jmp     loc_1800713BE
0x18007147f  test    ebx, ebx
0x180071481  jz      short loc_1800714BB
0x180071483  xor     r9d, r9d
0x180071486  mov     [rsp+78h+lParam], r14w
0x18007148c  xor     r8d, r8d
0x18007148f  jmp     loc_1800713C1
0x180071494  mov     ecx, 3
0x180071499  cmp     ebx, ecx
0x18007149b  jnb     short loc_1800714BB
0x18007149d  mov     r9d, ecx
0x1800714a0  mov     [rsp+78h+lParam], cx
0x1800714a5  mov     r8d, ecx
0x1800714a8  jmp     loc_1800713C1
0x1800714ad  mov     edx, ebx
0x1800714af  mov     rcx, rdi
0x1800714b2  call    ExitField
0x1800714b7  test    eax, eax
0x1800714b9  jz      short loc_1800714F6
0x1800714bb  lea     rcx, [r15+r15*2]
0x1800714bf  mov     qword ptr [rsp+78h+lParam], r12; lParam
0x1800714c4  mov     rcx, [rdi+rcx*8+30h]; lpPrevWndFunc
0x1800714c9  mov     r9, rsi; wParam
0x1800714cc  mov     r8d, r13d; Msg
0x1800714cf  mov     rdx, rbp; hWnd
0x1800714d2  call    cs:__imp_CallWindowProcW
0x1800714d8  jmp     short loc_1800714F8
0x1800714da  xor     r9d, r9d; lParam
0x1800714dd  xor     r8d, r8d; wParam
0x1800714e0  mov     rcx, rbp; hWnd
0x1800714e3  lea     edx, [r9+31h]; Msg
0x1800714e7  call    cs:__imp_SendMessageW
0x1800714ed  mov     rcx, rax; ho
0x1800714f0  call    cs:__imp_DeleteObject
0x1800714f6  xor     eax, eax
0x1800714f8  add     rsp, 38h
0x1800714fc  pop     r15
0x1800714fe  pop     r14
0x180071500  pop     r13
0x180071502  pop     r12
0x180071504  pop     rdi
0x180071505  pop     rsi
0x180071506  pop     rbp
0x180071507  pop     rbx
0x180071508  retn
```
