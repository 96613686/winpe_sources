# CMapiPreviewer::CopyTextToClipboard(HWND__ *,wchar_t const *)

- ea: `0x180022a64`
- end: `0x180022b5c`
- name: `?CopyTextToClipboard@CMapiPreviewer@@CAJPEAUHWND__@@PEB_W@Z`
- size: `248`
- prototype: `__int64 __fastcall(HWND, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800247e0`

## callees

- `0x180004080`
- `0x18000557c`
- `0x180022a64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180022abd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180022abd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022b38`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022b38`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x180022a74`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x180022a74`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x180022b3e`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x180022b3e`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x180022a85`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x180022a85`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x180022b1f`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x180022b1f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180022b0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180022b0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180022ad5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180022ad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::CopyTextToClipboard(HWND a1, const wchar_t *a2)
{
  int Error; // ebx
  __int64 v4; // rsi
  __int64 v5; // rdx
  HGLOBAL v6; // rax
  void *v7; // rdi
  wchar_t *v8; // r14

  if ( OpenClipboard(a1) )
  {
    if ( EmptyClipboard() || (Error = ResultFromLastError(), Error >= 0) )
    {
      v4 = -1;
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v6 = GlobalAlloc(2u, 2 * v5 + 2);
      v7 = v6;
      if ( v6 )
      {
        v8 = (wchar_t *)GlobalLock(v6);
        if ( !v8 )
        {
          Error = ResultFromLastError();
          if ( Error < 0 )
            goto LABEL_14;
        }
        do
          ++v4;
        while ( a2[v4] );
        Error = StringCchCopyW(v8, v4 + 1, a2);
        GlobalUnlock(v7);
        if ( Error < 0 || !SetClipboardData(0xDu, v7) && (Error = ResultFromLastError(), Error < 0) )
LABEL_14:
          GlobalFree(v7);
      }
      else
      {
        Error = -2147024882;
      }
    }
    CloseClipboard();
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180022a64  push    rbx
0x180022a66  push    rbp
0x180022a67  push    rsi
0x180022a68  push    rdi
0x180022a69  push    r14
0x180022a6b  push    r15
0x180022a6d  sub     rsp, 28h
0x180022a71  mov     rbp, rdx
0x180022a74  call    cs:__imp_OpenClipboard
0x180022a7a  xor     r15d, r15d
0x180022a7d  test    eax, eax
0x180022a7f  jz      loc_180022B46
0x180022a85  call    cs:__imp_EmptyClipboard
0x180022a8b  test    eax, eax
0x180022a8d  jnz     short loc_180022A9E
0x180022a8f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022a94  mov     ebx, eax
0x180022a96  test    eax, eax
0x180022a98  js      loc_180022B3E
0x180022a9e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022aa2  mov     rdx, rsi
0x180022aa5  inc     rdx
0x180022aa8  cmp     [rbp+rdx*2+0], r15w
0x180022aae  jnz     short loc_180022AA5
0x180022ab0  lea     rdx, ds:2[rdx*2]; dwBytes
0x180022ab8  mov     ecx, 2; uFlags
0x180022abd  call    cs:__imp_GlobalAlloc
0x180022ac3  mov     rdi, rax
0x180022ac6  test    rax, rax
0x180022ac9  jnz     short loc_180022AD2
0x180022acb  mov     ebx, 8007000Eh
0x180022ad0  jmp     short loc_180022B3E
0x180022ad2  mov     rcx, rdi; hMem
0x180022ad5  call    cs:__imp_GlobalLock
0x180022adb  mov     r14, rax
0x180022ade  test    rax, rax
0x180022ae1  jnz     short loc_180022AEE
0x180022ae3  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022ae8  mov     ebx, eax
0x180022aea  test    eax, eax
0x180022aec  js      short loc_180022B35
0x180022aee  inc     rsi
0x180022af1  cmp     [rbp+rsi*2+0], r15w
0x180022af7  jnz     short loc_180022AEE
0x180022af9  lea     rdx, [rsi+1]; unsigned __int64
0x180022afd  mov     r8, rbp; wchar_t *
0x180022b00  mov     rcx, r14; wchar_t *
0x180022b03  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180022b08  mov     rcx, rdi; hMem
0x180022b0b  mov     ebx, eax
0x180022b0d  call    cs:__imp_GlobalUnlock
0x180022b13  test    ebx, ebx
0x180022b15  js      short loc_180022B35
0x180022b17  mov     rdx, rdi; hMem
0x180022b1a  mov     ecx, 0Dh; uFormat
0x180022b1f  call    cs:__imp_SetClipboardData
0x180022b25  test    rax, rax
0x180022b28  jnz     short loc_180022B3E
0x180022b2a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022b2f  mov     ebx, eax
0x180022b31  test    eax, eax
0x180022b33  jns     short loc_180022B3E
0x180022b35  mov     rcx, rdi; hMem
0x180022b38  call    cs:__imp_GlobalFree
0x180022b3e  call    cs:__imp_CloseClipboard
0x180022b44  jmp     short loc_180022B4D
0x180022b46  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022b4b  mov     ebx, eax
0x180022b4d  mov     eax, ebx
0x180022b4f  add     rsp, 28h
0x180022b53  pop     r15
0x180022b55  pop     r14
0x180022b57  pop     rdi
0x180022b58  pop     rsi
0x180022b59  pop     rbp
0x180022b5a  pop     rbx
0x180022b5b  retn
```
