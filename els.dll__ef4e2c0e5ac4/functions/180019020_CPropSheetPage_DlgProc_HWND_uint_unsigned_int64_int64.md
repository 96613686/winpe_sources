# CPropSheetPage::DlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019020`
- end: `0x1800191e5`
- name: `?DlgProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `453`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019020`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019181`
- `KERNEL32!GetCurrentThreadId` at `0x180019181`
- `USER32!EnumThreadWindows` at `0x180019193`
- `USER32!EnumThreadWindows` at `0x180019193`
- `USER32!SetWindowLongPtrW` at `0x1800190b1`
- `USER32!SetWindowLongPtrW` at `0x1800190e9`
- `USER32!SetWindowLongPtrW` at `0x1800191a3`
- `USER32!SetWindowLongPtrW` at `0x1800190b1`
- `USER32!SetWindowLongPtrW` at `0x1800190e9`
- `USER32!SetWindowLongPtrW` at `0x1800191a3`
- `USER32!GetWindowLongPtrW` at `0x18001903f`
- `USER32!GetWindowLongPtrW` at `0x18001903f`

## pseudocode

```c
__int64 __fastcall CPropSheetPage::DlgProc(HWND hWnd, unsigned int a2, __int64 a3, __int64 a4)
{
  _WORD *WindowLongPtrW; // rcx
  unsigned int v9; // eax
  __int64 *v10; // rbx
  __int64 v11; // rax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 (*v17)(void); // rax
  DWORD CurrentThreadId; // eax
  void (*v19)(void); // rax

  WindowLongPtrW = (_WORD *)GetWindowLongPtrW(hWnd, 16);
  if ( a2 == 2 )
  {
    if ( !WindowLongPtrW )
      return 0;
    v19 = *(void (**)(void))(*(_QWORD *)WindowLongPtrW + 72LL);
LABEL_34:
    v19();
    return 0;
  }
  if ( a2 == 21 )
  {
    v19 = *(void (**)(void))(*(_QWORD *)WindowLongPtrW + 88LL);
    goto LABEL_34;
  }
  if ( a2 != 26 )
  {
    if ( a2 != 78 )
    {
      switch ( a2 )
      {
        case 0x53u:
        case 0x7Bu:
          (*(void (__fastcall **)(_WORD *, _QWORD, __int64, __int64))(*(_QWORD *)WindowLongPtrW + 40LL))(
            WindowLongPtrW,
            a2,
            a3,
            a4);
          return 1;
        case 0x110u:
          v10 = *(__int64 **)(a4 + 48);
          SetWindowLongPtrW(hWnd, 16, (LONG_PTR)v10);
          v11 = *v10;
          v10[2] = (__int64)hWnd;
          (*(void (__fastcall **)(__int64 *, __int64))(v11 + 8))(v10, a4);
          break;
        case 0x111u:
          if ( WindowLongPtrW )
            (*(void (__fastcall **)(_WORD *, __int64, __int64))(*(_QWORD *)WindowLongPtrW + 24LL))(
              WindowLongPtrW,
              a3,
              a4);
          break;
        case 0x46Cu:
          v9 = (*(__int64 (__fastcall **)(_WORD *, __int64, __int64))(*(_QWORD *)WindowLongPtrW + 64LL))(
                 WindowLongPtrW,
                 a3,
                 a4);
          SetWindowLongPtrW(hWnd, 0, v9);
          break;
      }
      return 0;
    }
    v13 = *(_DWORD *)(a4 + 16);
    v14 = 0;
    if ( v13 == -203 )
    {
      WindowLongPtrW[4] |= 0x10u;
      CurrentThreadId = GetCurrentThreadId();
      EnumThreadWindows(CurrentThreadId, ChildDialogEnumCallback, 0);
      goto LABEL_28;
    }
    if ( v13 == -202 )
    {
      if ( (WindowLongPtrW[4] & 0x10) != 0 )
        goto LABEL_28;
      v17 = *(__int64 (**)(void))(*(_QWORD *)WindowLongPtrW + 32LL);
    }
    else
    {
      v15 = *(_QWORD *)WindowLongPtrW;
      if ( v13 == -201 )
      {
        v17 = *(__int64 (**)(void))(v15 + 56);
      }
      else
      {
        if ( v13 != -200 )
        {
          v16 = (*(__int64 (__fastcall **)(_WORD *, __int64))(v15 + 48))(WindowLongPtrW, a4);
LABEL_23:
          v14 = v16;
LABEL_28:
          SetWindowLongPtrW(hWnd, 0, v14);
          return v14;
        }
        v17 = *(__int64 (**)(void))(v15 + 16);
      }
    }
    v16 = v17();
    goto LABEL_23;
  }
  if ( WindowLongPtrW )
    (*(void (__fastcall **)(_WORD *, __int64, __int64))(*(_QWORD *)WindowLongPtrW + 80LL))(WindowLongPtrW, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180019020  push    rbx
0x180019022  push    rbp
0x180019023  push    rsi
0x180019024  push    rdi
0x180019025  push    r14
0x180019027  sub     rsp, 30h
0x18001902b  mov     ebx, edx
0x18001902d  mov     r14d, 10h
0x180019033  mov     edx, r14d; nIndex
0x180019036  mov     rdi, r9
0x180019039  mov     rsi, r8
0x18001903c  mov     rbp, rcx
0x18001903f  call    cs:__imp_GetWindowLongPtrW
0x180019045  mov     rcx, rax
0x180019048  mov     eax, ebx
0x18001904a  sub     eax, 2
0x18001904d  jz      loc_1800191C7
0x180019053  sub     eax, 13h
0x180019056  jz      loc_1800191BE
0x18001905c  sub     eax, 5
0x18001905f  jz      loc_1800191AD
0x180019065  sub     eax, 34h ; '4'
0x180019068  jz      loc_180019128
0x18001906e  sub     eax, 5
0x180019071  jz      loc_18001910A
0x180019077  sub     eax, 28h ; '('
0x18001907a  jz      loc_18001910A
0x180019080  sub     eax, 95h
0x180019085  jz      short loc_1800190DC
0x180019087  sub     eax, 1
0x18001908a  jz      short loc_1800190BC
0x18001908c  cmp     eax, 35Bh
0x180019091  jnz     loc_1800191D8
0x180019097  mov     rax, [rcx]
0x18001909a  mov     r8, rdi
0x18001909d  mov     rdx, rsi
0x1800190a0  mov     rax, [rax+40h]
0x1800190a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190a9  mov     r8d, eax; dwNewLong
0x1800190ac  xor     edx, edx; nIndex
0x1800190ae  mov     rcx, rbp; hWnd
0x1800190b1  call    cs:__imp_SetWindowLongPtrW
0x1800190b7  jmp     loc_1800191D8
0x1800190bc  test    rcx, rcx
0x1800190bf  jz      loc_1800191D8
0x1800190c5  mov     rax, [rcx]
0x1800190c8  mov     rax, [rax+18h]
0x1800190cc  mov     rdx, rsi
0x1800190cf  mov     r8, rdi
0x1800190d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d7  jmp     loc_1800191D8
0x1800190dc  mov     rbx, [rdi+30h]
0x1800190e0  mov     edx, r14d; nIndex
0x1800190e3  mov     r8, rbx; dwNewLong
0x1800190e6  mov     rcx, rbp; hWnd
0x1800190e9  call    cs:__imp_SetWindowLongPtrW
0x1800190ef  mov     rax, [rbx]
0x1800190f2  mov     rdx, rdi
0x1800190f5  mov     rcx, rbx
0x1800190f8  mov     [rbx+10h], rbp
0x1800190fc  mov     rax, [rax+8]
0x180019100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019105  jmp     loc_1800191D8
0x18001910a  mov     rax, [rcx]
0x18001910d  mov     r9, rdi
0x180019110  mov     r8, rsi
0x180019113  mov     edx, ebx
0x180019115  mov     rax, [rax+28h]
0x180019119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001911e  mov     eax, 1
0x180019123  jmp     loc_1800191DA
0x180019128  mov     eax, [rdi+10h]
0x18001912b  xor     ebx, ebx
0x18001912d  cmp     eax, 0FFFFFF35h
0x180019132  jz      short loc_18001917C
0x180019134  cmp     eax, 0FFFFFF36h
0x180019139  jz      short loc_18001916D
0x18001913b  mov     r8, [rcx]
0x18001913e  cmp     eax, 0FFFFFF37h
0x180019143  jz      short loc_180019167
0x180019145  cmp     eax, 0FFFFFF38h
0x18001914a  jz      short loc_18001915A
0x18001914c  mov     rax, [r8+30h]
0x180019150  mov     rdx, rdi
0x180019153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019158  jmp     short loc_180019163
0x18001915a  mov     rax, [r8+10h]
0x18001915e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019163  mov     ebx, eax
0x180019165  jmp     short loc_180019199
0x180019167  mov     rax, [r8+38h]
0x18001916b  jmp     short loc_18001915E
0x18001916d  test    [rcx+8], r14b
0x180019171  jnz     short loc_180019199
0x180019173  mov     rax, [rcx]
0x180019176  mov     rax, [rax+20h]
0x18001917a  jmp     short loc_18001915E
0x18001917c  or      [rcx+8], r14w
0x180019181  call    cs:__imp_GetCurrentThreadId
0x180019187  xor     r8d, r8d; lParam
0x18001918a  lea     rdx, ?ChildDialogEnumCallback@@YAHPEAUHWND__@@_J@Z; lpfn
0x180019191  mov     ecx, eax; dwThreadId
0x180019193  call    cs:__imp_EnumThreadWindows
0x180019199  mov     ebx, ebx
0x18001919b  xor     edx, edx; nIndex
0x18001919d  mov     r8d, ebx; dwNewLong
0x1800191a0  mov     rcx, rbp; hWnd
0x1800191a3  call    cs:__imp_SetWindowLongPtrW
0x1800191a9  mov     eax, ebx
0x1800191ab  jmp     short loc_1800191DA
0x1800191ad  test    rcx, rcx
0x1800191b0  jz      short loc_1800191D8
0x1800191b2  mov     rax, [rcx]
0x1800191b5  mov     rax, [rax+50h]
0x1800191b9  jmp     loc_1800190CC
0x1800191be  mov     rax, [rcx]
0x1800191c1  mov     rax, [rax+58h]
0x1800191c5  jmp     short loc_1800191D3
0x1800191c7  test    rcx, rcx
0x1800191ca  jz      short loc_1800191D8
0x1800191cc  mov     rax, [rcx]
0x1800191cf  mov     rax, [rax+48h]
0x1800191d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d8  xor     eax, eax
0x1800191da  add     rsp, 30h
0x1800191de  pop     r14
0x1800191e0  pop     rdi
0x1800191e1  pop     rsi
0x1800191e2  pop     rbp
0x1800191e3  pop     rbx
0x1800191e4  retn
```
