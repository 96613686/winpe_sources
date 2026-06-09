# BrowseFolderCallbackProc(HWND__ *,uint,__int64,__int64)

- ea: `0x180008fa0`
- end: `0x18000903e`
- name: `?BrowseFolderCallbackProc@@YAHPEAUHWND__@@I_J1@Z`
- size: `158`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180008fa0`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180008fe5`
- `KERNEL32!GetFileAttributesW` at `0x180008fe5`
- `SHELL32!SHGetPathFromIDListW` at `0x180008fd6`
- `SHELL32!SHGetPathFromIDListW` at `0x180008fd6`
- `USER32!SendMessageW` at `0x180009015`
- `USER32!SendMessageW` at `0x180009015`

## pseudocode

```c
__int64 __fastcall BrowseFolderCallbackProc(HWND hWnd, int a2, const ITEMIDLIST *a3, LPARAM a4)
{
  HWND v4; // rdi
  int v5; // edx
  _BOOL8 v6; // rbx
  DWORD FileAttributesW; // eax
  WPARAM v8; // r8
  UINT v9; // edx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = hWnd;
  v5 = a2 - 1;
  if ( !v5 )
  {
    v9 = 1127;
    v8 = 1;
LABEL_8:
    SendMessageW(hWnd, v9, v8, a4);
    return 0;
  }
  if ( v5 == 1 )
  {
    v6 = 0;
    if ( SHGetPathFromIDListW(a3, pszPath) )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW != -1 )
        v6 = (FileAttributesW & 0x10) != 0;
    }
    a4 = v6;
    v8 = 0;
    v9 = 1125;
    hWnd = v4;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180008fa0  mov     [rsp+arg_8], rbx
0x180008fa5  push    rdi
0x180008fa6  sub     rsp, 240h
0x180008fad  mov     rax, cs:__security_cookie
0x180008fb4  xor     rax, rsp
0x180008fb7  mov     [rsp+248h+var_18], rax
0x180008fbf  mov     rdi, rcx
0x180008fc2  sub     edx, 1
0x180008fc5  jz      short loc_18000900A
0x180008fc7  cmp     edx, 1
0x180008fca  jnz     short loc_18000901B
0x180008fcc  lea     rdx, [rsp+248h+pszPath]; pszPath
0x180008fd1  mov     rcx, r8; pidl
0x180008fd4  xor     ebx, ebx
0x180008fd6  call    cs:__imp_SHGetPathFromIDListW
0x180008fdc  test    eax, eax
0x180008fde  jz      short loc_180008FFA
0x180008fe0  lea     rcx, [rsp+248h+pszPath]; lpFileName
0x180008fe5  call    cs:__imp_GetFileAttributesW
0x180008feb  cmp     eax, 0FFFFFFFFh
0x180008fee  jz      short loc_180008FFA
0x180008ff0  test    al, 10h
0x180008ff2  lea     r8d, [rbx+1]
0x180008ff6  cmovnz  ebx, r8d
0x180008ffa  mov     r9, rbx; lParam
0x180008ffd  xor     r8d, r8d
0x180009000  mov     edx, 465h
0x180009005  mov     rcx, rdi; hWnd
0x180009008  jmp     short loc_180009015
0x18000900a  mov     edx, 467h; Msg
0x18000900f  mov     r8d, 1; wParam
0x180009015  call    cs:__imp_SendMessageW
0x18000901b  xor     eax, eax
0x18000901d  mov     rcx, [rsp+248h+var_18]
0x180009025  xor     rcx, rsp; StackCookie
0x180009028  call    __security_check_cookie
0x18000902d  mov     rbx, [rsp+248h+arg_8]
0x180009035  add     rsp, 240h
0x18000903c  pop     rdi
0x18000903d  retn
```
