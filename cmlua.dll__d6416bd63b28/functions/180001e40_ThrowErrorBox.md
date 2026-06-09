# _ThrowErrorBox

- ea: `0x180001e40`
- end: `0x180001eb8`
- name: `_ThrowErrorBox`
- size: `120`
- prototype: `__int64 __fastcall(HWND hWnd, LPCWSTR lpCaption)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c20`

## callees

- `0x180001e40`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180001e7f`
- `KERNEL32!FormatMessageW` at `0x180001e7f`
- `KERNEL32!LocalFree` at `0x180001ea5`
- `KERNEL32!LocalFree` at `0x180001ea5`
- `USER32!MessageBoxW` at `0x180001e9a`
- `USER32!MessageBoxW` at `0x180001e9a`

## pseudocode

```c
__int64 __fastcall ThrowErrorBox(HWND hWnd, LPCWSTR lpCaption, DWORD a3)
{
  LPCWSTR lpText; // [rsp+68h] [rbp+20h] BYREF

  lpText = 0;
  if ( FormatMessageW(0x1300u, 0, a3, 0x400u, (LPWSTR)&lpText, 0, 0) )
  {
    MessageBoxW(hWnd, lpText, lpCaption, 0x10u);
    LocalFree((HLOCAL)lpText);
  }
  return 0;
}

```

## disassembly

```asm
0x180001e40  mov     rax, rsp
0x180001e43  mov     [rax+8], rbx
0x180001e47  push    rdi
0x180001e48  sub     rsp, 40h
0x180001e4c  mov     qword ptr [rax-18h], 0
0x180001e54  mov     rbx, rdx
0x180001e57  mov     dword ptr [rax-20h], 0
0x180001e5e  mov     rdi, rcx
0x180001e61  mov     qword ptr [rax+20h], 0
0x180001e69  lea     rax, [rax+20h]
0x180001e6d  xor     edx, edx; lpSource
0x180001e6f  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180001e74  mov     r9d, 400h; dwLanguageId
0x180001e7a  mov     ecx, 1300h; dwFlags
0x180001e7f  call    cs:__imp_FormatMessageW
0x180001e85  test    eax, eax
0x180001e87  jz      short loc_180001EAB
0x180001e89  mov     rdx, [rsp+48h+lpText]; lpText
0x180001e8e  mov     r9d, 10h; uType
0x180001e94  mov     r8, rbx; lpCaption
0x180001e97  mov     rcx, rdi; hWnd
0x180001e9a  call    cs:__imp_MessageBoxW
0x180001ea0  mov     rcx, [rsp+48h+lpText]; hMem
0x180001ea5  call    cs:__imp_LocalFree
0x180001eab  mov     rbx, [rsp+48h+arg_0]
0x180001eb0  xor     eax, eax
0x180001eb2  add     rsp, 40h
0x180001eb6  pop     rdi
0x180001eb7  retn
```
