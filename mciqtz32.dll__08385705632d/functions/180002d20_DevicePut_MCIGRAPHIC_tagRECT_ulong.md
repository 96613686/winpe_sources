# DevicePut(_MCIGRAPHIC *,tagRECT *,ulong)

- ea: `0x180002d20`
- end: `0x18000306b`
- name: `?DevicePut@@YAKPEAU_MCIGRAPHIC@@PEAUtagRECT@@K@Z`
- size: `843`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, struct tagRECT *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005268`

## callees

- `0x180001460`
- `0x180001e7c`
- `0x180002d20`
- `0x180007010`

## import_xrefs

- `USER32!IsIconic` at `0x180002db7`
- `USER32!IsIconic` at `0x180002db7`
- `USER32!GetClientRect` at `0x180002e5a`
- `USER32!GetClientRect` at `0x180002f2f`
- `USER32!GetClientRect` at `0x180002e5a`
- `USER32!GetClientRect` at `0x180002f2f`
- `USER32!SetRectEmpty` at `0x180002d57`
- `USER32!SetRectEmpty` at `0x180002d57`
- `USER32!GetWindowLongW` at `0x180002ea3`
- `USER32!GetWindowLongW` at `0x180002ea3`
- `USER32!GetWindowRect` at `0x180002e62`
- `USER32!GetWindowRect` at `0x180002e62`
- `USER32!SetWindowPos` at `0x180002ee8`
- `USER32!SetWindowPos` at `0x180002ee8`
- `USER32!ShowWindow` at `0x180002dcd`
- `USER32!ShowWindow` at `0x180002dcd`
- `USER32!AdjustWindowRect` at `0x180002eb1`
- `USER32!AdjustWindowRect` at `0x180002eb1`

## pseudocode

```c
unsigned int __fastcall DevicePut(struct _MCIGRAPHIC *a1, struct tagRECT *p_rc, int a3)
{
  __int64 v6; // rcx
  HWND v7; // rcx
  LONG WindowLongW; // eax
  int v9; // eax
  __int64 v10; // rcx
  tagRECT rc; // [rsp+40h] [rbp-20h] BYREF

  rc = 0;
  SetRectEmpty(&rc);
  if ( p_rc )
  {
    p_rc->right -= p_rc->left;
    p_rc->bottom -= p_rc->top;
  }
  if ( a3 == 0x20000 )
  {
    v10 = *((_QWORD *)a1 + 21);
    if ( v10 )
    {
      if ( !p_rc )
      {
        p_rc = &rc;
        (*(void (__fastcall **)(__int64, LONG *))(*(_QWORD *)v10 + 80LL))(v10, &rc.right);
        (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 88LL))(*((_QWORD *)a1 + 21), &rc.bottom);
      }
      if ( p_rc->right <= 0 )
        (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 120LL))(*((_QWORD *)a1 + 21), &p_rc->right);
      if ( p_rc->bottom <= 0 )
        (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 152LL))(*((_QWORD *)a1 + 21), &p_rc->bottom);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, LONG))(**((_QWORD **)a1 + 21) + 224LL))(
             *((_QWORD *)a1 + 21),
             (unsigned int)p_rc->left,
             (unsigned int)p_rc->top,
             (unsigned int)p_rc->right,
             p_rc->bottom);
      return CheckResult(v9);
    }
    return 346;
  }
  if ( a3 == 0x40000 )
  {
    if ( *((_QWORD *)a1 + 21) && *((_QWORD *)a1 + 22) )
    {
      if ( !p_rc )
      {
        p_rc = &rc;
        GetClientRect(*((HWND *)a1 + 37), &rc);
      }
      if ( p_rc->right <= 0 )
        (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 184LL))(*((_QWORD *)a1 + 21), &p_rc->right);
      if ( p_rc->bottom <= 0 )
        (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 216LL))(*((_QWORD *)a1 + 21), &p_rc->bottom);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, LONG))(**((_QWORD **)a1 + 22) + 312LL))(
             *((_QWORD *)a1 + 22),
             (unsigned int)p_rc->left,
             (unsigned int)p_rc->top,
             (unsigned int)p_rc->right,
             p_rc->bottom);
      return CheckResult(v9);
    }
    return 346;
  }
  if ( ((a3 - 0x200000) & 0xFF9FFFFF) != 0 || a3 == 0x800000 )
  {
    v9 = -2147467263;
    return CheckResult(v9);
  }
  if ( !*((_QWORD *)a1 + 22) )
    return 346;
  if ( IsIconic(*((HWND *)a1 + 37)) )
    ShowWindow(*((HWND *)a1 + 37), 9);
  if ( p_rc )
  {
    v7 = (HWND)*((_QWORD *)a1 + 37);
    if ( (a3 & 0x400000) != 0 )
      GetClientRect(v7, &rc);
    else
      GetWindowRect(v7, &rc);
    if ( p_rc->right <= 0 )
      p_rc->right = rc.right - rc.left;
    if ( p_rc->bottom <= 0 )
      p_rc->bottom = rc.bottom - rc.top;
    if ( (a3 & 0x400000) == 0 )
      goto LABEL_22;
    goto LABEL_21;
  }
  v6 = *((_QWORD *)a1 + 21);
  if ( !v6 )
    return 346;
  p_rc = &rc;
  (*(void (__fastcall **)(__int64, LONG *))(*(_QWORD *)v6 + 80LL))(v6, &rc.right);
  (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 21) + 88LL))(*((_QWORD *)a1 + 21), &rc.bottom);
  (*(void (__fastcall **)(_QWORD, tagRECT *))(**((_QWORD **)a1 + 22) + 176LL))(*((_QWORD *)a1 + 22), &rc);
  (*(void (__fastcall **)(_QWORD, LONG *))(**((_QWORD **)a1 + 22) + 208LL))(*((_QWORD *)a1 + 22), &rc.top);
LABEL_21:
  p_rc->bottom += p_rc->top;
  p_rc->right += p_rc->left;
  WindowLongW = GetWindowLongW(*((HWND *)a1 + 37), -16);
  AdjustWindowRect(p_rc, WindowLongW, 0);
  p_rc->bottom -= p_rc->top;
  p_rc->right -= p_rc->left;
LABEL_22:
  SetWindowPos(*((HWND *)a1 + 37), 0, p_rc->left, p_rc->top, p_rc->right, p_rc->bottom, 0x14u);
  v9 = 0;
  return CheckResult(v9);
}

```

## disassembly

```asm
0x180002d20  mov     [rsp-18h+arg_10], rbx
0x180002d25  mov     [rsp-18h+arg_18], rsi
0x180002d2a  push    rbp
0x180002d2b  push    rdi
0x180002d2c  push    r14
0x180002d2e  mov     rbp, rsp
0x180002d31  sub     rsp, 60h
0x180002d35  mov     rax, cs:__security_cookie
0x180002d3c  xor     rax, rsp
0x180002d3f  mov     [rbp+var_10], rax
0x180002d43  mov     rdi, rcx
0x180002d46  xorps   xmm0, xmm0
0x180002d49  lea     rcx, [rbp+rc]; lprc
0x180002d4d  mov     esi, r8d
0x180002d50  movups  xmmword ptr [rbp+rc.left], xmm0
0x180002d54  mov     rbx, rdx
0x180002d57  call    cs:__imp_SetRectEmpty
0x180002d5d  test    rbx, rbx
0x180002d60  jz      short loc_180002D6D
0x180002d62  mov     eax, [rbx]
0x180002d64  sub     [rbx+8], eax
0x180002d67  mov     eax, [rbx+4]
0x180002d6a  sub     [rbx+0Ch], eax
0x180002d6d  cmp     esi, 20000h
0x180002d73  jz      loc_180002F95
0x180002d79  cmp     esi, 40000h
0x180002d7f  jz      loc_180002EFF
0x180002d85  lea     eax, [rsi-200000h]
0x180002d8b  test    eax, 0FF9FFFFFh
0x180002d90  jnz     loc_180002EF5
0x180002d96  cmp     esi, 800000h
0x180002d9c  jz      loc_180002EF5
0x180002da2  cmp     qword ptr [rdi+0B0h], 0
0x180002daa  jz      loc_180002FA1
0x180002db0  mov     rcx, [rdi+128h]; hWnd
0x180002db7  call    cs:__imp_IsIconic
0x180002dbd  test    eax, eax
0x180002dbf  jz      short loc_180002DD3
0x180002dc1  mov     rcx, [rdi+128h]; hWnd
0x180002dc8  mov     edx, 9; nCmdShow
0x180002dcd  call    cs:__imp_ShowWindow
0x180002dd3  test    rbx, rbx
0x180002dd6  jnz     short loc_180002E49
0x180002dd8  mov     rcx, [rdi+0A8h]
0x180002ddf  test    rcx, rcx
0x180002de2  jz      loc_180002FA1
0x180002de8  mov     rax, [rcx]
0x180002deb  lea     rdx, [rbp+rc.right]
0x180002def  lea     rbx, [rbp+rc]
0x180002df3  mov     rax, [rax+50h]
0x180002df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfc  mov     rcx, [rdi+0A8h]
0x180002e03  lea     rdx, [rbp+rc.bottom]
0x180002e07  mov     rax, [rcx]
0x180002e0a  mov     rax, [rax+58h]
0x180002e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e13  mov     rcx, [rdi+0B0h]
0x180002e1a  lea     rdx, [rbp+rc]
0x180002e1e  mov     rax, [rcx]
0x180002e21  mov     rax, [rax+0B0h]
0x180002e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2d  mov     rcx, [rdi+0B0h]
0x180002e34  lea     rdx, [rbp+rc.top]
0x180002e38  mov     rax, [rcx]
0x180002e3b  mov     rax, [rax+0D0h]
0x180002e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e47  jmp     short loc_180002E8C
0x180002e49  bt      esi, 16h
0x180002e4d  mov     rcx, [rdi+128h]; hWnd
0x180002e54  lea     rdx, [rbp+rc]; lpRect
0x180002e58  jnb     short loc_180002E62
0x180002e5a  call    cs:__imp_GetClientRect
0x180002e60  jmp     short loc_180002E68
0x180002e62  call    cs:__imp_GetWindowRect
0x180002e68  cmp     dword ptr [rbx+8], 0
0x180002e6c  jg      short loc_180002E77
0x180002e6e  mov     eax, [rbp+rc.right]
0x180002e71  sub     eax, [rbp+rc.left]
0x180002e74  mov     [rbx+8], eax
0x180002e77  cmp     dword ptr [rbx+0Ch], 0
0x180002e7b  jg      short loc_180002E86
0x180002e7d  mov     eax, [rbp+rc.bottom]
0x180002e80  sub     eax, [rbp+rc.top]
0x180002e83  mov     [rbx+0Ch], eax
0x180002e86  bt      esi, 16h
0x180002e8a  jnb     short loc_180002EC2
0x180002e8c  mov     eax, [rbx+4]
0x180002e8f  mov     edx, 0FFFFFFF0h; nIndex
0x180002e94  add     [rbx+0Ch], eax
0x180002e97  mov     eax, [rbx]
0x180002e99  add     [rbx+8], eax
0x180002e9c  mov     rcx, [rdi+128h]; hWnd
0x180002ea3  call    cs:__imp_GetWindowLongW
0x180002ea9  xor     r8d, r8d; bMenu
0x180002eac  mov     rcx, rbx; lpRect
0x180002eaf  mov     edx, eax; dwStyle
0x180002eb1  call    cs:__imp_AdjustWindowRect
0x180002eb7  mov     eax, [rbx+4]
0x180002eba  sub     [rbx+0Ch], eax
0x180002ebd  mov     eax, [rbx]
0x180002ebf  sub     [rbx+8], eax
0x180002ec2  mov     eax, [rbx+0Ch]
0x180002ec5  xor     edx, edx; hWndInsertAfter
0x180002ec7  mov     r9d, [rbx+4]; Y
0x180002ecb  mov     r8d, [rbx]; X
0x180002ece  mov     rcx, [rdi+128h]; hWnd
0x180002ed5  mov     [rsp+60h+uFlags], 14h; uFlags
0x180002edd  mov     [rsp+60h+cy], eax; cy
0x180002ee1  mov     eax, [rbx+8]
0x180002ee4  mov     [rsp+60h+var_40], eax; cx
0x180002ee8  call    cs:__imp_SetWindowPos
0x180002eee  xor     eax, eax
0x180002ef0  jmp     loc_180003043
0x180002ef5  mov     eax, 80004001h
0x180002efa  jmp     loc_180003043
0x180002eff  cmp     qword ptr [rdi+0A8h], 0
0x180002f07  jz      loc_180002FA1
0x180002f0d  cmp     qword ptr [rdi+0B0h], 0
0x180002f15  jz      loc_180002FA1
0x180002f1b  test    rbx, rbx
0x180002f1e  jnz     short loc_180002F35
0x180002f20  mov     rcx, [rdi+128h]; hWnd
0x180002f27  lea     rdx, [rbp+rc]; lpRect
0x180002f2b  lea     rbx, [rbp+rc]
0x180002f2f  call    cs:__imp_GetClientRect
0x180002f35  lea     r14, [rbx+8]
0x180002f39  cmp     dword ptr [r14], 0
0x180002f3d  jg      short loc_180002F58
0x180002f3f  mov     rcx, [rdi+0A8h]
0x180002f46  mov     rdx, r14
0x180002f49  mov     rax, [rcx]
0x180002f4c  mov     rax, [rax+0B8h]
0x180002f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f58  lea     rsi, [rbx+0Ch]
0x180002f5c  cmp     dword ptr [rsi], 0
0x180002f5f  jg      short loc_180002F7A
0x180002f61  mov     rcx, [rdi+0A8h]
0x180002f68  mov     rdx, rsi
0x180002f6b  mov     rax, [rcx]
0x180002f6e  mov     rax, [rax+0D8h]
0x180002f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7a  mov     rcx, [rdi+0B0h]
0x180002f81  mov     edx, [rsi]
0x180002f83  mov     r9d, [r14]
0x180002f86  mov     rax, [rcx]
0x180002f89  mov     rax, [rax+138h]
0x180002f90  jmp     loc_180003034
0x180002f95  mov     rcx, [rdi+0A8h]
0x180002f9c  test    rcx, rcx
0x180002f9f  jnz     short loc_180002FAB
0x180002fa1  mov     eax, 15Ah
0x180002fa6  jmp     loc_18000304A
0x180002fab  test    rbx, rbx
0x180002fae  jnz     short loc_180002FDB
0x180002fb0  mov     rax, [rcx]
0x180002fb3  lea     rdx, [rbp+rc.right]
0x180002fb7  lea     rbx, [rbp+rc]
0x180002fbb  mov     rax, [rax+50h]
0x180002fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc4  mov     rcx, [rdi+0A8h]
0x180002fcb  lea     rdx, [rbp+rc.bottom]
0x180002fcf  mov     rax, [rcx]
0x180002fd2  mov     rax, [rax+58h]
0x180002fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fdb  lea     rsi, [rbx+8]
0x180002fdf  cmp     dword ptr [rsi], 0
0x180002fe2  jg      short loc_180002FFA
0x180002fe4  mov     rcx, [rdi+0A8h]
0x180002feb  mov     rdx, rsi
0x180002fee  mov     rax, [rcx]
0x180002ff1  mov     rax, [rax+78h]
0x180002ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffa  lea     r14, [rbx+0Ch]
0x180002ffe  cmp     dword ptr [r14], 0
0x180003002  jg      short loc_18000301D
0x180003004  mov     rcx, [rdi+0A8h]
0x18000300b  mov     rdx, r14
0x18000300e  mov     rax, [rcx]
0x180003011  mov     rax, [rax+98h]
0x180003018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301d  mov     rcx, [rdi+0A8h]
0x180003024  mov     edx, [r14]
0x180003027  mov     r9d, [rsi]
0x18000302a  mov     rax, [rcx]
0x18000302d  mov     rax, [rax+0E0h]
0x180003034  mov     r8d, [rbx+4]
0x180003038  mov     [rsp+60h+var_40], edx
0x18000303c  mov     edx, [rbx]
0x18000303e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003043  mov     ecx, eax; int
0x180003045  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x18000304a  mov     rcx, [rbp+var_10]
0x18000304e  xor     rcx, rsp; StackCookie
0x180003051  call    __security_check_cookie
0x180003056  lea     r11, [rsp+60h+var_s0]
0x18000305b  mov     rbx, [r11+30h]
0x18000305f  mov     rsi, [r11+38h]
0x180003063  mov     rsp, r11
0x180003066  pop     r14
0x180003068  pop     rdi
0x180003069  pop     rbp
0x18000306a  retn
```
