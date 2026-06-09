# write_text_utf8_nolock

- ea: `0x1800fe990`
- end: `0x1800feb02`
- name: `write_text_utf8_nolock`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800febf0`

## callees

- `0x1800f0d20`
- `0x1800fe990`
- `0x180105e80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800feacb`
- `KERNEL32!GetLastError` at `0x1800feacb`
- `KERNEL32!WideCharToMultiByte` at `0x1800fea76`
- `KERNEL32!WideCharToMultiByte` at `0x1800fea76`
- `KERNEL32!WriteFile` at `0x1800feaa9`
- `KERNEL32!WriteFile` at `0x1800feaa9`

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
0x1800fe990  mov     [rsp+arg_0], rbx
0x1800fe995  mov     [rsp+arg_10], rbp
0x1800fe99a  push    rsi
0x1800fe99b  push    rdi
0x1800fe99c  push    r12
0x1800fe99e  push    r14
0x1800fe9a0  push    r15
0x1800fe9a2  mov     eax, 1470h
0x1800fe9a7  call    _alloca_probe
0x1800fe9ac  sub     rsp, rax
0x1800fe9af  mov     rax, cs:__security_cookie
0x1800fe9b6  xor     rax, rsp
0x1800fe9b9  mov     [rsp+1498h+var_38], rax
0x1800fe9c1  movsxd  r10, edx
0x1800fe9c4  mov     rbx, rcx
0x1800fe9c7  mov     rax, r10
0x1800fe9ca  mov     r14d, r9d
0x1800fe9cd  sar     rax, 6
0x1800fe9d1  lea     rcx, __pioinfo
0x1800fe9d8  and     r10d, 3Fh
0x1800fe9dc  add     r14, r8
0x1800fe9df  shl     r10, 6
0x1800fe9e3  mov     r15, r8
0x1800fe9e6  mov     rdi, r8
0x1800fe9e9  mov     rax, [rcx+rax*8]
0x1800fe9ed  mov     r12, [rax+r10+28h]
0x1800fe9f2  xor     eax, eax
0x1800fe9f4  and     dword ptr [rbx], 0
0x1800fe9f7  mov     [rbx+4], rax
0x1800fe9fb  cmp     r8, r14
0x1800fe9fe  jnb     loc_1800FEAD3
0x1800fea04  lea     rax, [rsp+1498h+WideCharStr]
0x1800fea09  cmp     rdi, r14
0x1800fea0c  jnb     short loc_1800FEA3B
0x1800fea0e  movzx   ecx, word ptr [rdi]
0x1800fea11  add     rdi, 2
0x1800fea15  cmp     cx, 0Ah
0x1800fea19  jnz     short loc_1800FEA27
0x1800fea1b  mov     edx, 0Dh
0x1800fea20  mov     [rax], dx
0x1800fea23  add     rax, 2
0x1800fea27  mov     [rax], cx
0x1800fea2a  add     rax, 2
0x1800fea2e  lea     rcx, [rsp+1498h+var_DA0]
0x1800fea36  cmp     rax, rcx
0x1800fea39  jb      short loc_1800FEA09
0x1800fea3b  and     [rsp+1498h+var_1460], 0
0x1800fea41  lea     rcx, [rsp+1498h+WideCharStr]
0x1800fea46  and     [rsp+1498h+var_1468], 0
0x1800fea4c  lea     r8, [rsp+1498h+WideCharStr]; lpWideCharStr
0x1800fea51  sub     rax, rcx
0x1800fea54  mov     [rsp+1498h+cbMultiByte], 0D55h; cbMultiByte
0x1800fea5c  lea     rcx, [rsp+1498h+MultiByteStr]
0x1800fea64  sar     rax, 1
0x1800fea67  mov     [rsp+1498h+lpMultiByteStr], rcx; lpOverlapped
0x1800fea6c  mov     r9d, eax; cchWideChar
0x1800fea6f  mov     ecx, 0FDE9h; CodePage
0x1800fea74  xor     edx, edx; dwFlags
0x1800fea76  call    cs:__imp_WideCharToMultiByte
0x1800fea7c  mov     ebp, eax
0x1800fea7e  test    eax, eax
0x1800fea80  jz      short loc_1800FEACB
0x1800fea82  xor     esi, esi
0x1800fea84  test    eax, eax
0x1800fea86  jz      short loc_1800FEABB
0x1800fea88  and     [rsp+1498h+lpMultiByteStr], 0
0x1800fea8e  lea     rdx, [rsp+1498h+MultiByteStr]
0x1800fea96  mov     ecx, esi
0x1800fea98  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fea9d  mov     r8d, ebp
0x1800feaa0  add     rdx, rcx; lpBuffer
0x1800feaa3  mov     rcx, r12; hFile
0x1800feaa6  sub     r8d, esi; nNumberOfBytesToWrite
0x1800feaa9  call    cs:__imp_WriteFile
0x1800feaaf  test    eax, eax
0x1800feab1  jz      short loc_1800FEACB
0x1800feab3  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x1800feab7  cmp     esi, ebp
0x1800feab9  jb      short loc_1800FEA88
0x1800feabb  mov     eax, edi
0x1800feabd  sub     eax, r15d
0x1800feac0  mov     [rbx+4], eax
0x1800feac3  cmp     rdi, r14
0x1800feac6  jmp     loc_1800FE9FE
0x1800feacb  call    cs:__imp_GetLastError
0x1800fead1  mov     [rbx], eax
0x1800fead3  mov     rax, rbx
0x1800fead6  mov     rcx, [rsp+1498h+var_38]
0x1800feade  xor     rcx, rsp; StackCookie
0x1800feae1  call    __security_check_cookie
0x1800feae6  lea     r11, [rsp+1498h+var_28]
0x1800feaee  mov     rbx, [r11+30h]
0x1800feaf2  mov     rbp, [r11+40h]
0x1800feaf6  mov     rsp, r11
0x1800feaf9  pop     r15
0x1800feafb  pop     r14
0x1800feafd  pop     r12
0x1800feaff  pop     rdi
0x1800feb00  pop     rsi
0x1800feb01  retn
```
