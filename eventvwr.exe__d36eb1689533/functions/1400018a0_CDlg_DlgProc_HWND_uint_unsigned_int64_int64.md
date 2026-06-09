# CDlg::_DlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1400018a0`
- end: `0x1400019e6`
- name: `?_DlgProc@CDlg@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `326`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400018a0`
- `0x140003010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x1400018c1`
- `USER32!GetWindowLongPtrW` at `0x1400018c1`
- `USER32!SetWindowLongPtrW` at `0x14000193e`
- `USER32!SetWindowLongPtrW` at `0x14000193e`
- `USER32!DestroyWindow` at `0x14000196d`
- `USER32!DestroyWindow` at `0x14000196d`

## pseudocode

```c
INT_PTR __fastcall CDlg::_DlgProc(HWND a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  unsigned int v5; // edi
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v10; // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned __int8 v15; // [rsp+78h] [rbp+10h] BYREF

  v5 = 1;
  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v10 = WindowLongPtrW;
  switch ( a2 )
  {
    case 2u:
      if ( WindowLongPtrW )
      {
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 80LL))(WindowLongPtrW);
        *(_QWORD *)(v10 + 8) = 0;
      }
      break;
    case 5u:
      return (unsigned __int8)(*(__int64 (__fastcall **)(LONG_PTR, __int64, __int64 *))(*(_QWORD *)WindowLongPtrW + 56LL))(
                                WindowLongPtrW,
                                a3,
                                a4);
    case 0x24u:
      return (unsigned __int8)(*(__int64 (__fastcall **)(LONG_PTR, __int64 *))(*(_QWORD *)WindowLongPtrW + 32LL))(
                                WindowLongPtrW,
                                a4);
    case 0x4Eu:
      return (unsigned __int8)(*(__int64 (__fastcall **)(LONG_PTR, __int64, __int64 *))(*(_QWORD *)WindowLongPtrW + 48LL))(
                                WindowLongPtrW,
                                a3,
                                a4);
    case 0x53u:
    case 0x7Bu:
      (*(void (__fastcall **)(LONG_PTR, _QWORD, __int64, __int64 *))(*(_QWORD *)WindowLongPtrW + 8LL))(
        WindowLongPtrW,
        a2,
        a3,
        a4);
      return v5;
    case 0x110u:
      SetWindowLongPtrW(a1, 16, (LONG_PTR)a4);
      v12 = *a4;
      a4[1] = (__int64)a1;
      v15 = 1;
      v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *))(v12 + 16))(a4, &v15);
      v5 = v15;
      if ( v13 < 0 )
        DestroyWindow(a1);
      break;
    case 0x111u:
      return (unsigned __int8)(*(__int64 (__fastcall **)(LONG_PTR, __int64, __int64 *))(*(_QWORD *)WindowLongPtrW + 24LL))(
                                WindowLongPtrW,
                                a3,
                                a4);
    default:
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1400018a0  push    rbx
0x1400018a2  push    rbp
0x1400018a3  push    rsi
0x1400018a4  push    rdi
0x1400018a5  push    r14
0x1400018a7  push    r15
0x1400018a9  sub     rsp, 38h
0x1400018ad  mov     r15d, edx
0x1400018b0  mov     edi, 1
0x1400018b5  mov     rsi, r9
0x1400018b8  mov     rbp, r8
0x1400018bb  mov     r14, rcx
0x1400018be  lea     edx, [rdi+0Fh]; nIndex
0x1400018c1  call    cs:__imp_GetWindowLongPtrW
0x1400018c7  mov     r10d, r15d
0x1400018ca  mov     rbx, rax
0x1400018cd  sub     r10d, 2
0x1400018d1  jz      loc_1400019BB
0x1400018d7  sub     r10d, 3
0x1400018db  jz      loc_1400019AF
0x1400018e1  sub     r10d, 1Fh
0x1400018e5  jz      loc_140001998
0x1400018eb  sub     r10d, 2Ah ; '*'
0x1400018ef  jz      loc_14000198F
0x1400018f5  sub     r10d, 5
0x1400018f9  jz      short loc_140001975
0x1400018fb  sub     r10d, 28h ; '('
0x1400018ff  jz      short loc_140001975
0x140001901  sub     r10d, 95h
0x140001908  jz      short loc_140001933
0x14000190a  cmp     r10d, edi
0x14000190d  jz      short loc_140001916
0x14000190f  xor     edi, edi
0x140001911  jmp     loc_1400019D7
0x140001916  mov     rax, [rax]
0x140001919  mov     rax, [rax+18h]
0x14000191d  mov     r8, rsi
0x140001920  mov     rdx, rbp
0x140001923  mov     rcx, rbx
0x140001926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000192b  movzx   edi, al
0x14000192e  jmp     loc_1400019D7
0x140001933  mov     r8, rsi; dwNewLong
0x140001936  mov     edx, 10h; nIndex
0x14000193b  mov     rcx, r14; hWnd
0x14000193e  call    cs:__imp_SetWindowLongPtrW
0x140001944  mov     rax, [rsi]
0x140001947  lea     rdx, [rsp+68h+arg_8]
0x14000194c  mov     rcx, rsi
0x14000194f  mov     [rsi+8], r14
0x140001953  mov     [rsp+68h+arg_8], dil
0x140001958  mov     rax, [rax+10h]
0x14000195c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001961  movzx   edi, [rsp+68h+arg_8]
0x140001966  test    eax, eax
0x140001968  jns     short loc_1400019D7
0x14000196a  mov     rcx, r14; hWnd
0x14000196d  call    cs:__imp_DestroyWindow
0x140001973  jmp     short loc_1400019D7
0x140001975  mov     rax, [rax]
0x140001978  mov     r9, rsi
0x14000197b  mov     r8, rbp
0x14000197e  mov     edx, r15d
0x140001981  mov     rcx, rbx
0x140001984  mov     rax, [rax+8]
0x140001988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000198d  jmp     short loc_1400019D7
0x14000198f  mov     rax, [rax]
0x140001992  mov     rax, [rax+30h]
0x140001996  jmp     short loc_14000191D
0x140001998  mov     rax, [rax]
0x14000199b  mov     rdx, rsi
0x14000199e  mov     rcx, rbx
0x1400019a1  mov     rax, [rax+20h]
0x1400019a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019aa  jmp     loc_14000192B
0x1400019af  mov     rax, [rax]
0x1400019b2  mov     rax, [rax+38h]
0x1400019b6  jmp     loc_14000191D
0x1400019bb  test    rbx, rbx
0x1400019be  jz      short loc_1400019D7
0x1400019c0  mov     rax, [rax]
0x1400019c3  mov     rcx, rbx
0x1400019c6  mov     rax, [rax+50h]
0x1400019ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019cf  mov     qword ptr [rbx+8], 0
0x1400019d7  mov     eax, edi
0x1400019d9  add     rsp, 38h
0x1400019dd  pop     r15
0x1400019df  pop     r14
0x1400019e1  pop     rdi
0x1400019e2  pop     rsi
0x1400019e3  pop     rbp
0x1400019e4  pop     rbx
0x1400019e5  retn
```
