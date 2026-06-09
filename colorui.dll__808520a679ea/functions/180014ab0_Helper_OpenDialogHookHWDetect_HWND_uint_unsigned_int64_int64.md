# Helper::OpenDialogHookHWDetect(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180014ab0`
- end: `0x180014b30`
- name: `?OpenDialogHookHWDetect@Helper@@YA_KPEAUHWND__@@I_K_J@Z`
- size: `128`
- prototype: `unsigned __int64 __fastcall(Helper *this, HWND)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b40`

## callees

- `0x180014ab0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014b04`
- `KERNEL32!GetLastError` at `0x180014b04`
- `KERNEL32!SetLastError` at `0x180014ae8`
- `KERNEL32!SetLastError` at `0x180014ae8`
- `USER32!GetParent` at `0x180014ac2`
- `USER32!GetParent` at `0x180014ac2`
- `USER32!SetWindowLongPtrW` at `0x180014af9`
- `USER32!SetWindowLongPtrW` at `0x180014b1d`
- `USER32!SetWindowLongPtrW` at `0x180014af9`
- `USER32!SetWindowLongPtrW` at `0x180014b1d`
- `USER32!GetWindowLongPtrW` at `0x180014ad8`
- `USER32!GetWindowLongPtrW` at `0x180014ad8`

## pseudocode

```c
unsigned __int64 __fastcall Helper::OpenDialogHookHWDetect(Helper *this, HWND a2)
{
  HWND Parent; // rax
  HWND v3; // rbx
  LONG_PTR WindowLongPtrW; // rdi

  if ( (_DWORD)a2 == 272 )
  {
    Parent = GetParent((HWND)this);
    v3 = Parent;
    if ( Parent )
    {
      WindowLongPtrW = GetWindowLongPtrW(Parent, -4);
      if ( WindowLongPtrW )
      {
        SetLastError(0);
        if ( SetWindowLongPtrW(v3, -21, WindowLongPtrW) || !GetLastError() )
          SetWindowLongPtrW(v3, -4, (LONG_PTR)Helper::WndProcHWChangeDetect);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp+arg_0], rbx
0x180014ab5  push    rdi
0x180014ab6  sub     rsp, 20h
0x180014aba  cmp     edx, 110h
0x180014ac0  jnz     short loc_180014B23
0x180014ac2  call    cs:__imp_GetParent
0x180014ac8  mov     rbx, rax
0x180014acb  test    rax, rax
0x180014ace  jz      short loc_180014B23
0x180014ad0  mov     edx, 0FFFFFFFCh; nIndex
0x180014ad5  mov     rcx, rax; hWnd
0x180014ad8  call    cs:__imp_GetWindowLongPtrW
0x180014ade  mov     rdi, rax
0x180014ae1  test    rax, rax
0x180014ae4  jz      short loc_180014B23
0x180014ae6  xor     ecx, ecx; dwErrCode
0x180014ae8  call    cs:__imp_SetLastError
0x180014aee  mov     r8, rdi; dwNewLong
0x180014af1  mov     edx, 0FFFFFFEBh; nIndex
0x180014af6  mov     rcx, rbx; hWnd
0x180014af9  call    cs:__imp_SetWindowLongPtrW
0x180014aff  test    rax, rax
0x180014b02  jnz     short loc_180014B0E
0x180014b04  call    cs:__imp_GetLastError
0x180014b0a  test    eax, eax
0x180014b0c  jnz     short loc_180014B23
0x180014b0e  lea     r8, ?WndProcHWChangeDetect@Helper@@YA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180014b15  mov     edx, 0FFFFFFFCh; nIndex
0x180014b1a  mov     rcx, rbx; hWnd
0x180014b1d  call    cs:__imp_SetWindowLongPtrW
0x180014b23  mov     rbx, [rsp+28h+arg_0]
0x180014b28  xor     eax, eax
0x180014b2a  add     rsp, 20h
0x180014b2e  pop     rdi
0x180014b2f  retn
```
