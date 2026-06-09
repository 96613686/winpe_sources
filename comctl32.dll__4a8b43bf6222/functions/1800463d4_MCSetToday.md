# MCSetToday

- ea: `0x1800463d4`
- end: `0x1800464f4`
- name: `MCSetToday`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800440e8`
- `0x180046d90`

## callees

- `0x1800115f0`
- `0x1800432d0`
- `0x1800434c4`
- `0x1800463d4`
- `0x180046cd8`
- `0x180072058`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x18004640e`
- `KERNEL32!GetLocalTime` at `0x18004640e`
- `USER32!InvalidateRect` at `0x18004646d`
- `USER32!InvalidateRect` at `0x1800464a7`
- `USER32!InvalidateRect` at `0x1800464c9`
- `USER32!InvalidateRect` at `0x18004646d`
- `USER32!InvalidateRect` at `0x1800464a7`
- `USER32!InvalidateRect` at `0x1800464c9`
- `USER32!UpdateWindow` at `0x1800464d2`
- `USER32!UpdateWindow` at `0x1800464d2`

## pseudocode

```c
int __fastcall MCSetToday(__int64 a1, struct _SYSTEMTIME *a2)
{
  struct _SYSTEMTIME v3; // xmm0
  int result; // eax
  RECT Rect; // [rsp+20h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-20h] BYREF

  SystemTime = 0;
  Rect = 0;
  if ( a2 )
  {
    v3 = *a2;
    *(_DWORD *)(a1 + 2392) |= 0x400u;
    SystemTime = v3;
  }
  else
  {
    GetLocalTime(&SystemTime);
    *(_DWORD *)(a1 + 2392) &= ~0x400u;
  }
  result = CmpDate(&SystemTime, a1 + 1804);
  if ( result )
  {
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, RECT *))MCGetRcForDay)(
      a1,
      *(unsigned int *)(a1 + 2088),
      *(unsigned __int16 *)(a1 + 1810),
      &Rect);
    InvalidateRect(*(HWND *)a1, &Rect, 0);
    *(struct _SYSTEMTIME *)(a1 + 1804) = SystemTime;
    MCUpdateToday(a1);
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, RECT *))MCGetRcForDay)(
      a1,
      *(unsigned int *)(a1 + 2088),
      *(unsigned __int16 *)(a1 + 1810),
      &Rect);
    InvalidateRect(*(HWND *)a1, &Rect, 0);
    if ( (*(_BYTE *)(a1 + 16) & 0x10) == 0 )
    {
      MCGetTodayBtnRect(a1, &Rect);
      InvalidateRect(*(HWND *)a1, &Rect, 0);
    }
    return UpdateWindow(*(HWND *)a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800463d4  mov     [rsp-8+arg_8], rbx
0x1800463d9  mov     [rsp-8+arg_10], rdi
0x1800463de  push    rbp
0x1800463df  mov     rbp, rsp
0x1800463e2  sub     rsp, 50h
0x1800463e6  mov     rax, cs:__security_cookie
0x1800463ed  xor     rax, rsp
0x1800463f0  mov     [rbp+var_10], rax
0x1800463f4  xorps   xmm0, xmm0
0x1800463f7  xorps   xmm1, xmm1
0x1800463fa  mov     rbx, rcx
0x1800463fd  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180046401  movups  xmmword ptr [rbp+Rect.left], xmm1
0x180046405  test    rdx, rdx
0x180046408  jnz     short loc_18004641E
0x18004640a  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18004640e  call    cs:__imp_GetLocalTime
0x180046414  btr     dword ptr [rbx+958h], 0Ah
0x18004641c  jmp     short loc_18004642E
0x18004641e  movups  xmm0, xmmword ptr [rdx]
0x180046421  bts     dword ptr [rcx+958h], 0Ah
0x180046429  movdqu  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18004642e  lea     rdi, [rbx+70Ch]
0x180046435  mov     rdx, rdi
0x180046438  lea     rcx, [rbp+SystemTime]
0x18004643c  call    CmpDate
0x180046441  test    eax, eax
0x180046443  jz      loc_1800464D8
0x180046449  movzx   r8d, word ptr [rbx+712h]
0x180046451  lea     r9, [rbp+Rect]
0x180046455  mov     edx, [rbx+828h]
0x18004645b  mov     rcx, rbx
0x18004645e  call    MCGetRcForDay
0x180046463  mov     rcx, [rbx]; hWnd
0x180046466  lea     rdx, [rbp+Rect]; lpRect
0x18004646a  xor     r8d, r8d; bErase
0x18004646d  call    cs:__imp_InvalidateRect
0x180046473  movups  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x180046477  mov     rcx, rbx
0x18004647a  movdqu  xmmword ptr [rdi], xmm0
0x18004647e  call    MCUpdateToday
0x180046483  movzx   r8d, word ptr [rbx+712h]
0x18004648b  lea     r9, [rbp+Rect]
0x18004648f  mov     edx, [rbx+828h]
0x180046495  mov     rcx, rbx
0x180046498  call    MCGetRcForDay
0x18004649d  mov     rcx, [rbx]; hWnd
0x1800464a0  lea     rdx, [rbp+Rect]; lpRect
0x1800464a4  xor     r8d, r8d; bErase
0x1800464a7  call    cs:__imp_InvalidateRect
0x1800464ad  test    byte ptr [rbx+10h], 10h
0x1800464b1  jnz     short loc_1800464CF
0x1800464b3  lea     rdx, [rbp+Rect]
0x1800464b7  mov     rcx, rbx
0x1800464ba  call    MCGetTodayBtnRect
0x1800464bf  mov     rcx, [rbx]; hWnd
0x1800464c2  lea     rdx, [rbp+Rect]; lpRect
0x1800464c6  xor     r8d, r8d; bErase
0x1800464c9  call    cs:__imp_InvalidateRect
0x1800464cf  mov     rcx, [rbx]; hWnd
0x1800464d2  call    cs:__imp_UpdateWindow
0x1800464d8  mov     rcx, [rbp+var_10]
0x1800464dc  xor     rcx, rsp; StackCookie
0x1800464df  call    __security_check_cookie
0x1800464e4  mov     rbx, [rsp+50h+arg_8]
0x1800464e9  mov     rdi, [rsp+50h+arg_10]
0x1800464ee  add     rsp, 50h
0x1800464f2  pop     rbp
0x1800464f3  retn
```
