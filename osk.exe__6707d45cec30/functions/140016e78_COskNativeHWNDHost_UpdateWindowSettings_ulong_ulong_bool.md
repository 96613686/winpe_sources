# COskNativeHWNDHost::UpdateWindowSettings(ulong,ulong,bool)

- ea: `0x140016e78`
- end: `0x140016feb`
- name: `?UpdateWindowSettings@COskNativeHWNDHost@@AEAAXKK_N@Z`
- size: `371`
- prototype: `void(COskNativeHWNDHost *__hidden this, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140014cb8`
- `0x140015c60`

## callees

- `0x140016e78`

## import_xrefs

- `KERNEL32!MulDiv` at `0x140016eab`
- `KERNEL32!MulDiv` at `0x140016eab`
- `USER32!SetWindowPos` at `0x140016f07`
- `USER32!SetWindowPos` at `0x140016f4a`
- `USER32!SetWindowPos` at `0x140016f95`
- `USER32!SetWindowPos` at `0x140016fd9`
- `USER32!SetWindowPos` at `0x140016f07`
- `USER32!SetWindowPos` at `0x140016f4a`
- `USER32!SetWindowPos` at `0x140016f95`
- `USER32!SetWindowPos` at `0x140016fd9`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016ee6`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016f29`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016f6c`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016fb0`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016ee6`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016f29`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016f6c`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140016fb0`

## pseudocode

```c
void __fastcall COskNativeHWNDHost::UpdateWindowSettings(COskNativeHWNDHost *this, int a2, int a3, char a4)
{
  int cy; // esi
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  HWND HWND; // rax
  int v13; // ebx
  HWND v14; // rax
  int v15; // ebx
  HWND v16; // rax
  int v17; // ebx
  HWND v18; // rax

  cy = a3;
  if ( (unsigned int)(a2 - 2) <= 1 )
  {
    v8 = 84;
    if ( a2 != 2 )
      v8 = 88;
    cy = MulDiv(a3, *(_DWORD *)((char *)this + v8), 96);
  }
  if ( a2 )
  {
    v9 = a2 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 == 1 && *((_DWORD *)this + 29) != cy )
        {
          if ( a4 )
          {
            v11 = *((_DWORD *)this + 28);
            HWND = DirectUI::NativeHWNDHost::GetHWND(this);
            SetWindowPos(HWND, 0, 0, 0, v11, cy, 0x16u);
          }
          *((_DWORD *)this + 29) = cy;
        }
      }
      else if ( *((_DWORD *)this + 28) != cy )
      {
        if ( a4 )
        {
          v13 = *((_DWORD *)this + 29);
          v14 = DirectUI::NativeHWNDHost::GetHWND(this);
          SetWindowPos(v14, 0, 0, 0, cy, v13, 0x16u);
        }
        *((_DWORD *)this + 28) = cy;
      }
    }
    else if ( *((_DWORD *)this + 27) != cy )
    {
      if ( a4 )
      {
        v15 = *((_DWORD *)this + 26);
        v16 = DirectUI::NativeHWNDHost::GetHWND(this);
        SetWindowPos(v16, 0, v15, cy, 0, 0, 0x15u);
      }
      *((_DWORD *)this + 27) = cy;
    }
  }
  else if ( *((_DWORD *)this + 26) != cy )
  {
    if ( a4 )
    {
      v17 = *((_DWORD *)this + 27);
      v18 = DirectUI::NativeHWNDHost::GetHWND(this);
      SetWindowPos(v18, 0, cy, v17, 0, 0, 0x15u);
    }
    *((_DWORD *)this + 26) = cy;
  }
}

```

## disassembly

```asm
0x140016e78  push    rbx
0x140016e7a  push    rbp
0x140016e7b  push    rsi
0x140016e7c  push    rdi
0x140016e7d  sub     rsp, 48h
0x140016e81  lea     eax, [rdx-2]
0x140016e84  mov     bpl, r9b
0x140016e87  mov     esi, r8d
0x140016e8a  mov     ebx, edx
0x140016e8c  mov     rdi, rcx
0x140016e8f  cmp     eax, 1
0x140016e92  ja      short loc_140016EB3
0x140016e94  mov     edx, 54h ; 'T'
0x140016e99  cmp     ebx, 2
0x140016e9c  lea     eax, [rdx+4]
0x140016e9f  cmovnz  edx, eax
0x140016ea2  lea     r8d, [rax+8]; nDenominator
0x140016ea6  mov     edx, [rdx+rcx]; nNumerator
0x140016ea9  mov     ecx, esi; nNumber
0x140016eab  call    cs:__imp_MulDiv
0x140016eb1  mov     esi, eax
0x140016eb3  test    ebx, ebx
0x140016eb5  jz      loc_140016FA0
0x140016ebb  sub     ebx, 1
0x140016ebe  jz      loc_140016F58
0x140016ec4  sub     ebx, 1
0x140016ec7  jz      short loc_140016F15
0x140016ec9  cmp     ebx, 1
0x140016ecc  jnz     loc_140016FE2
0x140016ed2  cmp     [rdi+74h], esi
0x140016ed5  jz      loc_140016FE2
0x140016edb  test    bpl, bpl
0x140016ede  jz      short loc_140016F0D
0x140016ee0  mov     ebx, [rdi+70h]
0x140016ee3  mov     rcx, rdi
0x140016ee6  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140016eec  mov     [rsp+68h+uFlags], 16h; uFlags
0x140016ef4  xor     r9d, r9d; Y
0x140016ef7  mov     rcx, rax; hWnd
0x140016efa  mov     [rsp+68h+cy], esi; cy
0x140016efe  xor     r8d, r8d; X
0x140016f01  mov     [rsp+68h+var_48], ebx; cx
0x140016f05  xor     edx, edx; hWndInsertAfter
0x140016f07  call    cs:__imp_SetWindowPos
0x140016f0d  mov     [rdi+74h], esi
0x140016f10  jmp     loc_140016FE2
0x140016f15  cmp     [rdi+70h], esi
0x140016f18  jz      loc_140016FE2
0x140016f1e  test    bpl, bpl
0x140016f21  jz      short loc_140016F50
0x140016f23  mov     ebx, [rdi+74h]
0x140016f26  mov     rcx, rdi
0x140016f29  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140016f2f  mov     [rsp+68h+uFlags], 16h; uFlags
0x140016f37  xor     r9d, r9d; Y
0x140016f3a  mov     rcx, rax; hWnd
0x140016f3d  mov     [rsp+68h+cy], ebx; cy
0x140016f41  xor     r8d, r8d; X
0x140016f44  mov     [rsp+68h+var_48], esi; cx
0x140016f48  xor     edx, edx; hWndInsertAfter
0x140016f4a  call    cs:__imp_SetWindowPos
0x140016f50  mov     [rdi+70h], esi
0x140016f53  jmp     loc_140016FE2
0x140016f58  cmp     [rdi+6Ch], esi
0x140016f5b  jz      loc_140016FE2
0x140016f61  test    bpl, bpl
0x140016f64  jz      short loc_140016F9B
0x140016f66  mov     ebx, [rdi+68h]
0x140016f69  mov     rcx, rdi
0x140016f6c  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140016f72  mov     [rsp+68h+uFlags], 15h; uFlags
0x140016f7a  mov     r9d, esi; Y
0x140016f7d  mov     rcx, rax; hWnd
0x140016f80  mov     [rsp+68h+cy], 0; cy
0x140016f88  mov     r8d, ebx; X
0x140016f8b  mov     [rsp+68h+var_48], 0; cx
0x140016f93  xor     edx, edx; hWndInsertAfter
0x140016f95  call    cs:__imp_SetWindowPos
0x140016f9b  mov     [rdi+6Ch], esi
0x140016f9e  jmp     short loc_140016FE2
0x140016fa0  cmp     [rdi+68h], esi
0x140016fa3  jz      short loc_140016FE2
0x140016fa5  test    bpl, bpl
0x140016fa8  jz      short loc_140016FDF
0x140016faa  mov     ebx, [rdi+6Ch]
0x140016fad  mov     rcx, rdi
0x140016fb0  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140016fb6  mov     [rsp+68h+uFlags], 15h; uFlags
0x140016fbe  mov     r9d, ebx; Y
0x140016fc1  mov     rcx, rax; hWnd
0x140016fc4  mov     [rsp+68h+cy], 0; cy
0x140016fcc  mov     r8d, esi; X
0x140016fcf  mov     [rsp+68h+var_48], 0; cx
0x140016fd7  xor     edx, edx; hWndInsertAfter
0x140016fd9  call    cs:__imp_SetWindowPos
0x140016fdf  mov     [rdi+68h], esi
0x140016fe2  add     rsp, 48h
0x140016fe6  pop     rdi
0x140016fe7  pop     rsi
0x140016fe8  pop     rbp
0x140016fe9  pop     rbx
0x140016fea  retn
```
