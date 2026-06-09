# MCIWndOpenDlg

- ea: `0x180010c08`
- end: `0x180010cba`
- name: `MCIWndOpenDlg`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013edc`
- `0x1800149d4`

## callees

- `0x1800014b0`
- `0x18000eb40`
- `0x180012ac4`

## pseudocode

```c
__int64 __fastcall MCIWndOpenDlg(__int64 a1, int a2, _WORD *a3)
{
  __int64 result; // rax
  wchar_t pszDest[512]; // [rsp+20h] [rbp-418h] BYREF

  *a3 = 0;
  *(_QWORD *)(a1 + 808) = a3;
  *(_DWORD *)(a1 + 816) = 128;
  *(_DWORD *)(a1 + 856) = a2 != 0 ? 2052 : 6148;
  MCIWndiBuildMeAFilter(pszDest);
  *(_QWORD *)(a1 + 784) = pszDest;
  result = GetFileNamePreview(a1 + 760, a2 != 0, (size_t *)1);
  *(_QWORD *)(a1 + 784) = 0;
  return result;
}

```

## disassembly

```asm
0x180010c08  mov     [rsp+arg_8], rbx
0x180010c0d  push    rdi
0x180010c0e  sub     rsp, 430h
0x180010c15  mov     rax, cs:__security_cookie
0x180010c1c  xor     rax, rsp
0x180010c1f  mov     [rsp+438h+var_18], rax
0x180010c27  xor     eax, eax
0x180010c29  mov     rdi, rcx
0x180010c2c  mov     [r8], ax
0x180010c30  mov     ebx, edx
0x180010c32  mov     [rcx+328h], r8
0x180010c39  mov     eax, edx
0x180010c3b  mov     dword ptr [rcx+330h], 80h
0x180010c45  neg     eax
0x180010c47  sbb     r8d, r8d
0x180010c4a  and     r8d, 0FFFFF000h
0x180010c51  add     r8d, 1804h
0x180010c58  mov     [rcx+358h], r8d
0x180010c5f  lea     rcx, [rsp+438h+pszDest]; pszDest
0x180010c64  call    MCIWndiBuildMeAFilter
0x180010c69  xor     edx, edx
0x180010c6b  lea     rax, [rsp+438h+pszDest]
0x180010c70  test    ebx, ebx
0x180010c72  mov     [rdi+310h], rax
0x180010c79  lea     rcx, [rdi+2F8h]
0x180010c80  mov     r8d, 1
0x180010c86  setnz   dl
0x180010c89  call    GetFileNamePreview
0x180010c8e  mov     qword ptr [rdi+310h], 0
0x180010c99  mov     rcx, [rsp+438h+var_18]
0x180010ca1  xor     rcx, rsp; StackCookie
0x180010ca4  call    __security_check_cookie
0x180010ca9  mov     rbx, [rsp+438h+arg_8]
0x180010cb1  add     rsp, 430h
0x180010cb8  pop     rdi
0x180010cb9  retn
```
