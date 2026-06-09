# MCIWndiHandleError

- ea: `0x1800134d4`
- end: `0x18001359e`
- name: `MCIWndiHandleError`
- size: `202`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180010aa4`
- `0x180010cc0`
- `0x1800129a0`

## callees

- `0x1800014b0`
- `0x1800134d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013540`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013540`
- `USER32!SendMessageW` at `0x18001357f`
- `USER32!SendMessageW` at `0x18001357f`
- `USER32!MessageBoxW` at `0x18001355b`
- `USER32!MessageBoxW` at `0x18001355b`
- `WINMM!mciGetErrorStringW` at `0x180013521`
- `WINMM!mciGetErrorStringW` at `0x180013521`

## pseudocode

```c
int __fastcall MCIWndiHandleError(__int64 a1, MCIERROR a2)
{
  int result; // eax
  HWND v4; // rcx
  WCHAR pszText[128]; // [rsp+20h] [rbp-118h] BYREF

  *(_DWORD *)(a1 + 28) = a2;
  result = a2;
  if ( a2 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x4000) == 0 && !*(_DWORD *)(a1 + 108) && !*(_DWORD *)(a1 + 112) )
    {
      mciGetErrorStringW(a2, pszText, 0x80u);
      LoadStringW(hInst, 0x14Fu, &NewItem, 128);
      result = MessageBoxW(*(HWND *)a1, pszText, &NewItem, 0x30u);
    }
    if ( (*(_DWORD *)(a1 + 32) & 0x1000) != 0 )
    {
      v4 = *(HWND *)(a1 + 8);
      if ( v4 )
        return SendMessageW(v4, 0x4CDu, *(_QWORD *)a1, *(unsigned int *)(a1 + 28));
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800134d4  push    rbx
0x1800134d6  sub     rsp, 130h
0x1800134dd  mov     rax, cs:__security_cookie
0x1800134e4  xor     rax, rsp
0x1800134e7  mov     [rsp+138h+var_18], rax
0x1800134ef  mov     [rcx+1Ch], edx
0x1800134f2  mov     eax, edx
0x1800134f4  mov     rbx, rcx
0x1800134f7  test    edx, edx
0x1800134f9  jz      loc_180013585
0x1800134ff  test    dword ptr [rcx+20h], 4000h
0x180013506  jnz     short loc_180013561
0x180013508  cmp     dword ptr [rcx+6Ch], 0
0x18001350c  jnz     short loc_180013561
0x18001350e  cmp     dword ptr [rcx+70h], 0
0x180013512  jnz     short loc_180013561
0x180013514  mov     r8d, 80h; cchText
0x18001351a  lea     rdx, [rsp+138h+pszText]; pszText
0x18001351f  mov     ecx, eax; mcierr
0x180013521  call    cs:__imp_mciGetErrorStringW
0x180013527  mov     rcx, cs:hInst; hInstance
0x18001352e  lea     r8, NewItem; lpBuffer
0x180013535  mov     r9d, 80h; cchBufferMax
0x18001353b  mov     edx, 14Fh; uID
0x180013540  call    cs:__imp_LoadStringW
0x180013546  mov     rcx, [rbx]; hWnd
0x180013549  lea     r8, NewItem; lpCaption
0x180013550  mov     r9d, 30h ; '0'; uType
0x180013556  lea     rdx, [rsp+138h+pszText]; lpText
0x18001355b  call    cs:__imp_MessageBoxW
0x180013561  test    dword ptr [rbx+20h], 1000h
0x180013568  jz      short loc_180013585
0x18001356a  mov     rcx, [rbx+8]; hWnd
0x18001356e  test    rcx, rcx
0x180013571  jz      short loc_180013585
0x180013573  mov     r9d, [rbx+1Ch]; lParam
0x180013577  mov     edx, 4CDh; Msg
0x18001357c  mov     r8, [rbx]; wParam
0x18001357f  call    cs:__imp_SendMessageW
0x180013585  mov     rcx, [rsp+138h+var_18]
0x18001358d  xor     rcx, rsp; StackCookie
0x180013590  call    __security_check_cookie
0x180013595  add     rsp, 130h
0x18001359c  pop     rbx
0x18001359d  retn
```
