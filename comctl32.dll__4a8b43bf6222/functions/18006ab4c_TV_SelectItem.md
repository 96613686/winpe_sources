# TV_SelectItem

- ea: `0x18006ab4c`
- end: `0x18006add4`
- name: `TV_SelectItem`
- size: `648`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180067db0`
- `0x1800680c8`
- `0x180068910`
- `0x180069940`
- `0x180069d54`
- `0x18006a0c4`
- `0x18006af90`
- `0x18006bbb0`
- `0x18007e72c`

## callees

- `0x1800197bc`
- `0x180068c0c`
- `0x180068e44`
- `0x1800697d0`
- `0x18006ab4c`
- `0x18006b0b8`
- `0x18006cca4`
- `0x18007d988`
- `0x18007daf0`
- `0x18007dc50`
- `0x180085d00`

## import_xrefs

- `USER32!GetDoubleClickTime` at `0x18006ac5c`
- `USER32!GetDoubleClickTime` at `0x18006ac5c`
- `USER32!UpdateWindow` at `0x18006acdb`
- `USER32!UpdateWindow` at `0x18006ad7c`
- `USER32!UpdateWindow` at `0x18006acdb`
- `USER32!UpdateWindow` at `0x18006ad7c`
- `USER32!SetTimer` at `0x18006ac6e`
- `USER32!SetTimer` at `0x18006ac6e`

## pseudocode

```c
__int64 __fastcall TV_SelectItem(HWND *a1, __int64 a2, HWND a3, char a4, int a5)
{
  struct _IMAGELIST *v6; // rcx
  unsigned int v10; // r14d
  __int64 v11; // rbx
  __int64 v12; // rbx
  HWND v13; // r8
  HWND v14; // rax
  HWND v15; // rbx
  HWND v16; // rbx
  UINT DoubleClickTime; // eax
  HWND v18; // rax
  HWND v19; // rdx
  HWND v21; // [rsp+80h] [rbp+8h]

  v6 = (struct _IMAGELIST *)a1[19];
  v10 = 1;
  if ( v6 && ImageList_GetBkColor(v6) == -1 )
    v10 = 5;
  if ( (unsigned int)ValidateTreeItem(a3, 1) )
  {
    v11 = a2 - 5;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( !v12 )
      {
        v18 = a1[10];
        if ( a3 != v18 )
        {
          if ( v18 )
          {
            *((_WORD *)v18 + 20) &= ~8u;
            TV_InvalidateItem(a1, a1[10], v10);
          }
          if ( a3 )
          {
            *((_WORD *)a3 + 20) |= 8u;
            TV_InvalidateItem(a1, a3, v10);
          }
          v19 = a1[9];
          a1[10] = a3;
          if ( v19 )
            TV_InvalidateItem(a1, v19, v10);
          if ( (a4 & 2) != 0 )
            UpdateWindow(*a1);
        }
        return 1;
      }
      if ( v12 == 1 )
      {
        v13 = a1[9];
        if ( v13 == a3 )
          return 1;
        if ( (a4 & 1) == 0 || !(unsigned int)TV_SendSelChange((_DWORD)a1, -450, (_DWORD)v13, (_DWORD)a3, a5) )
        {
          v14 = a1[9];
          if ( v14 )
          {
            *((_WORD *)v14 + 20) &= ~2u;
            TV_InvalidateItem(a1, a1[9], v10);
          }
          v15 = a1[9];
          v21 = v15;
          a1[9] = a3;
          if ( a3 )
          {
            *((_WORD *)a3 + 20) |= 2u;
            TV_ExpandParents(a1, a3, a4 & 1);
            TV_InvalidateItem(a1, a3, v10);
            if ( a5 == 1 )
            {
              v16 = *a1;
              DoubleClickTime = GetDoubleClickTime();
              SetTimer(v16, 0x2Bu, DoubleClickTime, 0);
              *((_DWORD *)a1 + 14) |= 0x20u;
              v15 = v21;
            }
            else if ( ((_BYTE)a1[7] & 0x10) != 0 )
            {
              TV_ScrollVertIntoView(a1, a3);
            }
          }
          if ( (a4 & 1) != 0 )
            TV_SendSelChange((_DWORD)a1, -451, (_DWORD)v15, (_DWORD)a3, a5);
          if ( ((_DWORD)a1[2] & 0x400) != 0 && (a4 & 4) == 0 && a5 != 2 )
            TV_ExpandOnSelChange(a1, a1[9], v15);
          if ( (a4 & 2) != 0 )
            UpdateWindow(*a1);
          MyNotifyWinEvent(32773, *a1, 4294967292LL);
          MyNotifyWinEvent(32774, *a1, 4294967292LL);
          return 1;
        }
      }
    }
    else if ( a3 )
    {
      TV_ExpandParents(a1, a3, 1);
      TV_ScrollIntoView(a1, a3);
      if ( ((_BYTE)a1[7] & 2) != 0 )
        TV_SmoothSetTopItem(a1, *((unsigned __int16 *)a3 + 24), 0);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006ab4c  push    rbx
0x18006ab4e  push    rbp
0x18006ab4f  push    rsi
0x18006ab50  push    rdi
0x18006ab51  push    r12
0x18006ab53  push    r13
0x18006ab55  push    r14
0x18006ab57  push    r15
0x18006ab59  sub     rsp, 38h
0x18006ab5d  mov     r15d, 1
0x18006ab63  mov     rdi, rcx
0x18006ab66  mov     rcx, [rcx+98h]; himl
0x18006ab6d  mov     r13d, r9d
0x18006ab70  mov     rsi, r8
0x18006ab73  mov     rbx, rdx
0x18006ab76  mov     r14d, r15d
0x18006ab79  lea     ebp, [r15+4]
0x18006ab7d  test    rcx, rcx
0x18006ab80  jz      short loc_18006AB8E
0x18006ab82  call    ImageList_GetBkColor
0x18006ab87  cmp     eax, 0FFFFFFFFh
0x18006ab8a  cmovz   r14d, ebp
0x18006ab8e  mov     edx, r15d
0x18006ab91  mov     rcx, rsi
0x18006ab94  call    ValidateTreeItem
0x18006ab99  test    eax, eax
0x18006ab9b  jz      loc_18006ADC1
0x18006aba1  sub     rbx, rbp
0x18006aba4  jz      loc_18006AD84
0x18006abaa  sub     rbx, 3
0x18006abae  jz      loc_18006AD15
0x18006abb4  cmp     rbx, r15
0x18006abb7  jnz     loc_18006ADC1
0x18006abbd  mov     r8, [rdi+48h]
0x18006abc1  cmp     r8, rsi
0x18006abc4  jz      loc_18006ADBC
0x18006abca  mov     r12d, [rsp+78h+arg_20]
0x18006abd2  mov     r15d, r13d
0x18006abd5  and     r15d, 1
0x18006abd9  jz      short loc_18006ABF8
0x18006abdb  mov     r9, rsi
0x18006abde  mov     [rsp+78h+var_58], r12d
0x18006abe3  mov     edx, 0FFFFFE3Eh
0x18006abe8  mov     rcx, rdi
0x18006abeb  call    TV_SendSelChange
0x18006abf0  test    eax, eax
0x18006abf2  jnz     loc_18006ADC1
0x18006abf8  mov     rax, [rdi+48h]
0x18006abfc  test    rax, rax
0x18006abff  jz      short loc_18006AC19
0x18006ac01  mov     ecx, 0FFFDh
0x18006ac06  mov     r8d, r14d
0x18006ac09  and     [rax+28h], cx
0x18006ac0d  mov     rcx, rdi
0x18006ac10  mov     rdx, [rdi+48h]
0x18006ac14  call    TV_InvalidateItem
0x18006ac19  mov     rbx, [rdi+48h]
0x18006ac1d  mov     ebp, 2
0x18006ac22  mov     [rsp+78h+arg_0], rbx
0x18006ac2a  mov     [rdi+48h], rsi
0x18006ac2e  test    rsi, rsi
0x18006ac31  jz      short loc_18006AC93
0x18006ac33  or      [rsi+28h], bp
0x18006ac37  mov     r8d, r15d
0x18006ac3a  mov     rdx, rsi
0x18006ac3d  mov     rcx, rdi
0x18006ac40  call    TV_ExpandParents
0x18006ac45  mov     r8d, r14d
0x18006ac48  mov     rdx, rsi
0x18006ac4b  mov     rcx, rdi
0x18006ac4e  call    TV_InvalidateItem
0x18006ac53  cmp     r12d, 1
0x18006ac57  jnz     short loc_18006AC82
0x18006ac59  mov     rbx, [rdi]
0x18006ac5c  call    cs:__imp_GetDoubleClickTime
0x18006ac62  xor     r9d, r9d; lpTimerFunc
0x18006ac65  lea     edx, [rbp+29h]; nIDEvent
0x18006ac68  mov     r8d, eax; uElapse
0x18006ac6b  mov     rcx, rbx; hWnd
0x18006ac6e  call    cs:__imp_SetTimer
0x18006ac74  or      dword ptr [rdi+38h], 20h
0x18006ac78  mov     rbx, [rsp+78h+arg_0]
0x18006ac80  jmp     short loc_18006AC93
0x18006ac82  test    byte ptr [rdi+38h], 10h
0x18006ac86  jz      short loc_18006AC93
0x18006ac88  mov     rdx, rsi
0x18006ac8b  mov     rcx, rdi
0x18006ac8e  call    TV_ScrollVertIntoView
0x18006ac93  test    r15d, r15d
0x18006ac96  jz      short loc_18006ACB0
0x18006ac98  mov     r9, rsi
0x18006ac9b  mov     [rsp+78h+var_58], r12d
0x18006aca0  mov     r8, rbx
0x18006aca3  mov     edx, 0FFFFFE3Dh
0x18006aca8  mov     rcx, rdi
0x18006acab  call    TV_SendSelChange
0x18006acb0  test    dword ptr [rdi+10h], 400h
0x18006acb7  jz      short loc_18006ACD3
0x18006acb9  test    r13b, 4
0x18006acbd  jnz     short loc_18006ACD3
0x18006acbf  cmp     r12d, ebp
0x18006acc2  jz      short loc_18006ACD3
0x18006acc4  mov     rdx, [rdi+48h]
0x18006acc8  mov     r8, rbx
0x18006accb  mov     rcx, rdi
0x18006acce  call    TV_ExpandOnSelChange
0x18006acd3  test    bpl, r13b
0x18006acd6  jz      short loc_18006ACE1
0x18006acd8  mov     rcx, [rdi]; hWnd
0x18006acdb  call    cs:__imp_UpdateWindow
0x18006ace1  mov     rdx, [rdi]
0x18006ace4  mov     ebx, 0FFFFFFFCh
0x18006ace9  mov     r8d, ebx
0x18006acec  mov     r9, rsi
0x18006acef  mov     ecx, 8005h
0x18006acf4  call    MyNotifyWinEvent
0x18006acf9  mov     rdx, [rdi]
0x18006acfc  mov     r9, rsi
0x18006acff  mov     r8d, ebx
0x18006ad02  mov     ecx, 8006h
0x18006ad07  call    MyNotifyWinEvent
0x18006ad0c  lea     r15d, [rbx+5]
0x18006ad10  jmp     loc_18006ADBC
0x18006ad15  mov     rax, [rdi+50h]
0x18006ad19  cmp     rsi, rax
0x18006ad1c  jz      loc_18006ADBC
0x18006ad22  test    rax, rax
0x18006ad25  jz      short loc_18006AD3F
0x18006ad27  mov     ecx, 0FFF7h
0x18006ad2c  mov     r8d, r14d
0x18006ad2f  and     [rax+28h], cx
0x18006ad33  mov     rcx, rdi
0x18006ad36  mov     rdx, [rdi+50h]
0x18006ad3a  call    TV_InvalidateItem
0x18006ad3f  test    rsi, rsi
0x18006ad42  jz      short loc_18006AD57
0x18006ad44  or      word ptr [rsi+28h], 8
0x18006ad49  mov     r8d, r14d
0x18006ad4c  mov     rdx, rsi
0x18006ad4f  mov     rcx, rdi
0x18006ad52  call    TV_InvalidateItem
0x18006ad57  mov     rdx, [rdi+48h]
0x18006ad5b  mov     [rdi+50h], rsi
0x18006ad5f  test    rdx, rdx
0x18006ad62  jz      short loc_18006AD6F
0x18006ad64  mov     r8d, r14d
0x18006ad67  mov     rcx, rdi
0x18006ad6a  call    TV_InvalidateItem
0x18006ad6f  mov     ebp, 2
0x18006ad74  test    bpl, r13b
0x18006ad77  jz      short loc_18006ADBC
0x18006ad79  mov     rcx, [rdi]; hWnd
0x18006ad7c  call    cs:__imp_UpdateWindow
0x18006ad82  jmp     short loc_18006ADBC
0x18006ad84  test    rsi, rsi
0x18006ad87  jz      short loc_18006ADC1
0x18006ad89  mov     r8d, r15d
0x18006ad8c  mov     rdx, rsi
0x18006ad8f  mov     rcx, rdi
0x18006ad92  call    TV_ExpandParents
0x18006ad97  mov     rdx, rsi
0x18006ad9a  mov     rcx, rdi
0x18006ad9d  call    TV_ScrollIntoView
0x18006ada2  mov     ebp, 2
0x18006ada7  test    [rdi+38h], bpl
0x18006adab  jz      short loc_18006ADBC
0x18006adad  movzx   edx, word ptr [rsi+30h]
0x18006adb1  xor     r8d, r8d
0x18006adb4  mov     rcx, rdi
0x18006adb7  call    TV_SmoothSetTopItem
0x18006adbc  mov     eax, r15d
0x18006adbf  jmp     short loc_18006ADC3
0x18006adc1  xor     eax, eax
0x18006adc3  add     rsp, 38h
0x18006adc7  pop     r15
0x18006adc9  pop     r14
0x18006adcb  pop     r13
0x18006adcd  pop     r12
0x18006adcf  pop     rdi
0x18006add0  pop     rsi
0x18006add1  pop     rbp
0x18006add2  pop     rbx
0x18006add3  retn
```
