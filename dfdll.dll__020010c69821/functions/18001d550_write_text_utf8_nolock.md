# write_text_utf8_nolock

- ea: `0x18001d550`
- end: `0x18001d6c2`
- name: `write_text_utf8_nolock`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001d7b0`

## callees

- `0x180012bd0`
- `0x18001d550`
- `0x18001ee90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d68b`
- `KERNEL32!GetLastError` at `0x18001d68b`
- `KERNEL32!WideCharToMultiByte` at `0x18001d636`
- `KERNEL32!WideCharToMultiByte` at `0x18001d636`
- `KERNEL32!WriteFile` at `0x18001d669`
- `KERNEL32!WriteFile` at `0x18001d669`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, WCHAR *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  WCHAR *v7; // rdi
  void *v8; // r12
  bool v9; // cf
  WCHAR *v10; // rax
  WCHAR v11; // cx
  unsigned int v12; // ebp
  unsigned int v13; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  WCHAR WideCharStr[852]; // [rsp+50h] [rbp-1448h] BYREF
  char v17; // [rsp+6F8h] [rbp-DA0h] BYREF
  CHAR MultiByteStr[3424]; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + ((unsigned __int64)(a2 & 0x3F) << 6) + 40);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 4) = 0;
  v9 = (unsigned __int64)a3 < v5;
LABEL_2:
  if ( v9 )
  {
    v10 = WideCharStr;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v11 = *v7++;
      if ( v11 == 10 )
        *v10++ = 13;
      *v10++ = v11;
    }
    while ( v10 < (WCHAR *)&v17 );
    v12 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v10 - WideCharStr, MultiByteStr, 3413, 0, 0);
    if ( v12 )
    {
      v13 = 0;
      while ( WriteFile(v8, &MultiByteStr[v13], v12 - v13, &NumberOfBytesWritten, 0) )
      {
        v13 += NumberOfBytesWritten;
        if ( v13 >= v12 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          v9 = (unsigned __int64)v7 < v5;
          goto LABEL_2;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18001d550  mov     [rsp+arg_0], rbx
0x18001d555  mov     [rsp+arg_10], rbp
0x18001d55a  push    rsi
0x18001d55b  push    rdi
0x18001d55c  push    r12
0x18001d55e  push    r14
0x18001d560  push    r15
0x18001d562  mov     eax, 1470h
0x18001d567  call    _alloca_probe
0x18001d56c  sub     rsp, rax
0x18001d56f  mov     rax, cs:__security_cookie
0x18001d576  xor     rax, rsp
0x18001d579  mov     [rsp+1498h+var_38], rax
0x18001d581  movsxd  r10, edx
0x18001d584  mov     rbx, rcx
0x18001d587  mov     rax, r10
0x18001d58a  mov     r14d, r9d
0x18001d58d  sar     rax, 6
0x18001d591  lea     rcx, __pioinfo
0x18001d598  and     r10d, 3Fh
0x18001d59c  add     r14, r8
0x18001d59f  shl     r10, 6
0x18001d5a3  mov     r15, r8
0x18001d5a6  mov     rdi, r8
0x18001d5a9  mov     rax, [rcx+rax*8]
0x18001d5ad  mov     r12, [rax+r10+28h]
0x18001d5b2  xor     eax, eax
0x18001d5b4  and     dword ptr [rbx], 0
0x18001d5b7  mov     [rbx+4], rax
0x18001d5bb  cmp     r8, r14
0x18001d5be  jnb     loc_18001D693
0x18001d5c4  lea     rax, [rsp+1498h+WideCharStr]
0x18001d5c9  cmp     rdi, r14
0x18001d5cc  jnb     short loc_18001D5FB
0x18001d5ce  movzx   ecx, word ptr [rdi]
0x18001d5d1  add     rdi, 2
0x18001d5d5  cmp     cx, 0Ah
0x18001d5d9  jnz     short loc_18001D5E7
0x18001d5db  mov     edx, 0Dh
0x18001d5e0  mov     [rax], dx
0x18001d5e3  add     rax, 2
0x18001d5e7  mov     [rax], cx
0x18001d5ea  add     rax, 2
0x18001d5ee  lea     rcx, [rsp+1498h+var_DA0]
0x18001d5f6  cmp     rax, rcx
0x18001d5f9  jb      short loc_18001D5C9
0x18001d5fb  and     [rsp+1498h+var_1460], 0
0x18001d601  lea     rcx, [rsp+1498h+WideCharStr]
0x18001d606  and     [rsp+1498h+var_1468], 0
0x18001d60c  lea     r8, [rsp+1498h+WideCharStr]; lpWideCharStr
0x18001d611  sub     rax, rcx
0x18001d614  mov     [rsp+1498h+cbMultiByte], 0D55h; cbMultiByte
0x18001d61c  lea     rcx, [rsp+1498h+MultiByteStr]
0x18001d624  sar     rax, 1
0x18001d627  mov     [rsp+1498h+lpMultiByteStr], rcx; lpOverlapped
0x18001d62c  mov     r9d, eax; cchWideChar
0x18001d62f  mov     ecx, 0FDE9h; CodePage
0x18001d634  xor     edx, edx; dwFlags
0x18001d636  call    cs:__imp_WideCharToMultiByte
0x18001d63c  mov     ebp, eax
0x18001d63e  test    eax, eax
0x18001d640  jz      short loc_18001D68B
0x18001d642  xor     esi, esi
0x18001d644  test    eax, eax
0x18001d646  jz      short loc_18001D67B
0x18001d648  and     [rsp+1498h+lpMultiByteStr], 0
0x18001d64e  lea     rdx, [rsp+1498h+MultiByteStr]
0x18001d656  mov     ecx, esi
0x18001d658  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d65d  mov     r8d, ebp
0x18001d660  add     rdx, rcx; lpBuffer
0x18001d663  mov     rcx, r12; hFile
0x18001d666  sub     r8d, esi; nNumberOfBytesToWrite
0x18001d669  call    cs:__imp_WriteFile
0x18001d66f  test    eax, eax
0x18001d671  jz      short loc_18001D68B
0x18001d673  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x18001d677  cmp     esi, ebp
0x18001d679  jb      short loc_18001D648
0x18001d67b  mov     eax, edi
0x18001d67d  sub     eax, r15d
0x18001d680  mov     [rbx+4], eax
0x18001d683  cmp     rdi, r14
0x18001d686  jmp     loc_18001D5BE
0x18001d68b  call    cs:__imp_GetLastError
0x18001d691  mov     [rbx], eax
0x18001d693  mov     rax, rbx
0x18001d696  mov     rcx, [rsp+1498h+var_38]
0x18001d69e  xor     rcx, rsp; StackCookie
0x18001d6a1  call    __security_check_cookie
0x18001d6a6  lea     r11, [rsp+1498h+var_28]
0x18001d6ae  mov     rbx, [r11+30h]
0x18001d6b2  mov     rbp, [r11+40h]
0x18001d6b6  mov     rsp, r11
0x18001d6b9  pop     r15
0x18001d6bb  pop     r14
0x18001d6bd  pop     r12
0x18001d6bf  pop     rdi
0x18001d6c0  pop     rsi
0x18001d6c1  retn
```
