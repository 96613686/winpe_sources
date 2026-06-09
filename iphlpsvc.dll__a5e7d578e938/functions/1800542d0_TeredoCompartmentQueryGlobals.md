# TeredoCompartmentQueryGlobals

- ea: `0x1800542d0`
- end: `0x180054514`
- name: `TeredoCompartmentQueryGlobals`
- size: `580`
- prototype: `BOOL __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18004b5f0`
- `0x1800542d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005431d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005433f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054361`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054383`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543a5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543c9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005442e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054452`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054476`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005449a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544bc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544e7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005431d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005433f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054361`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054383`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543a5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543c9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005442e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054452`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054476`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005449a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544bc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544e7`

## pseudocode

```c
BOOL __fastcall TeredoCompartmentQueryGlobals(__int64 a1, void *a2)
{
  BOOL result; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-18h] BYREF

  NumberOfBytesWritten = 0;
  Buffer = 0;
  WriteFile(a2, (LPCVOID)(a1 + 16), 4u, &NumberOfBytesWritten, 0);
  WriteFile(a2, &dword_1800CA09C, 4u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 2868), 4u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 2876), 4u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 2864), 4u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 13544), 0x58u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 2772), 4u, &NumberOfBytesWritten, 0);
  LOWORD(Buffer) = 2;
  DWORD1(Buffer) = ~*(_DWORD *)(a1 + 13700);
  WORD1(Buffer) = ~*(_WORD *)(a1 + 13698);
  WriteFile(a2, &Buffer, 0x10u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 12764), 0x10u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 19296), 0x10u, &NumberOfBytesWritten, 0);
  WriteFile(a2, (LPCVOID)(a1 + 19312), 0x10u, &NumberOfBytesWritten, 0);
  result = WriteFile(a2, (LPCVOID)(a1 + 19328), 4u, &NumberOfBytesWritten, 0);
  if ( *(_DWORD *)(a1 + 16) == 1 )
    return WriteFile(a2, &dword_1800CB7E8, 0x110u, &NumberOfBytesWritten, 0);
  return result;
}

```

## disassembly

```asm
0x1800542d0  mov     [rsp-28h+arg_10], rbx
0x1800542d5  push    rbp
0x1800542d6  push    rsi
0x1800542d7  push    rdi
0x1800542d8  push    r12
0x1800542da  push    r15
0x1800542dc  mov     rbp, rsp
0x1800542df  sub     rsp, 50h
0x1800542e3  mov     rax, cs:__security_cookie
0x1800542ea  xor     rax, rsp
0x1800542ed  mov     [rbp+var_8], rax
0x1800542f1  xor     r12d, r12d
0x1800542f4  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800542f8  mov     rsi, rdx
0x1800542fb  mov     [rbp+NumberOfBytesWritten], r12d
0x1800542ff  mov     rdi, rcx
0x180054302  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054307  xorps   xmm0, xmm0
0x18005430a  lea     rdx, [rcx+10h]; lpBuffer
0x18005430e  lea     r15d, [r12+4]
0x180054313  mov     rcx, rsi; hFile
0x180054316  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054319  movups  [rbp+Buffer], xmm0
0x18005431d  call    cs:__imp_WriteFile
0x180054324  nop     dword ptr [rax+rax+00h]
0x180054329  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005432d  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054332  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054335  lea     rdx, dword_1800CA09C; lpBuffer
0x18005433c  mov     rcx, rsi; hFile
0x18005433f  call    cs:__imp_WriteFile
0x180054346  nop     dword ptr [rax+rax+00h]
0x18005434b  lea     rdx, [rdi+0B34h]; lpBuffer
0x180054352  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054357  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005435b  mov     r8d, r15d; nNumberOfBytesToWrite
0x18005435e  mov     rcx, rsi; hFile
0x180054361  call    cs:__imp_WriteFile
0x180054368  nop     dword ptr [rax+rax+00h]
0x18005436d  lea     rdx, [rdi+0B3Ch]; lpBuffer
0x180054374  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054379  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005437d  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054380  mov     rcx, rsi; hFile
0x180054383  call    cs:__imp_WriteFile
0x18005438a  nop     dword ptr [rax+rax+00h]
0x18005438f  lea     rdx, [rdi+0B30h]; lpBuffer
0x180054396  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005439b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005439f  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800543a2  mov     rcx, rsi; hFile
0x1800543a5  call    cs:__imp_WriteFile
0x1800543ac  nop     dword ptr [rax+rax+00h]
0x1800543b1  lea     rdx, [rdi+34E8h]; lpBuffer
0x1800543b8  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800543bd  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800543c1  mov     rcx, rsi; hFile
0x1800543c4  lea     r8d, [r12+58h]; nNumberOfBytesToWrite
0x1800543c9  call    cs:__imp_WriteFile
0x1800543d0  nop     dword ptr [rax+rax+00h]
0x1800543d5  lea     rdx, [rdi+0AD4h]; lpBuffer
0x1800543dc  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800543e1  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800543e5  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800543e8  mov     rcx, rsi; hFile
0x1800543eb  call    cs:__imp_WriteFile
0x1800543f2  nop     dword ptr [rax+rax+00h]
0x1800543f7  lea     eax, [r12+2]
0x1800543fc  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054401  mov     word ptr [rbp+Buffer], ax
0x180054405  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054409  mov     eax, [rdi+3584h]
0x18005440f  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x180054414  not     eax
0x180054416  lea     rdx, [rbp+Buffer]; lpBuffer
0x18005441a  mov     dword ptr [rbp+Buffer+4], eax
0x18005441d  mov     rcx, rsi; hFile
0x180054420  movzx   eax, word ptr [rdi+3582h]
0x180054427  not     ax
0x18005442a  mov     word ptr [rbp+Buffer+2], ax
0x18005442e  call    cs:__imp_WriteFile
0x180054435  nop     dword ptr [rax+rax+00h]
0x18005443a  lea     rdx, [rdi+31DCh]; lpBuffer
0x180054441  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054446  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005444a  mov     rcx, rsi; hFile
0x18005444d  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x180054452  call    cs:__imp_WriteFile
0x180054459  nop     dword ptr [rax+rax+00h]
0x18005445e  lea     rdx, [rdi+4B60h]; lpBuffer
0x180054465  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005446a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005446e  mov     rcx, rsi; hFile
0x180054471  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x180054476  call    cs:__imp_WriteFile
0x18005447d  nop     dword ptr [rax+rax+00h]
0x180054482  lea     rdx, [rdi+4B70h]; lpBuffer
0x180054489  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005448e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054492  mov     rcx, rsi; hFile
0x180054495  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x18005449a  call    cs:__imp_WriteFile
0x1800544a1  nop     dword ptr [rax+rax+00h]
0x1800544a6  lea     rdx, [rdi+4B80h]; lpBuffer
0x1800544ad  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800544b2  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800544b6  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800544b9  mov     rcx, rsi; hFile
0x1800544bc  call    cs:__imp_WriteFile
0x1800544c3  nop     dword ptr [rax+rax+00h]
0x1800544c8  cmp     dword ptr [rdi+10h], 1
0x1800544cc  jnz     short loc_1800544F3
0x1800544ce  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800544d2  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800544d7  mov     r8d, 110h; nNumberOfBytesToWrite
0x1800544dd  lea     rdx, dword_1800CB7E8; lpBuffer
0x1800544e4  mov     rcx, rsi; hFile
0x1800544e7  call    cs:__imp_WriteFile
0x1800544ee  nop     dword ptr [rax+rax+00h]
0x1800544f3  mov     rcx, [rbp+var_8]
0x1800544f7  xor     rcx, rsp; StackCookie
0x1800544fa  call    __security_check_cookie
0x1800544ff  mov     rbx, [rsp+50h+arg_10]
0x180054507  add     rsp, 50h
0x18005450b  pop     r15
0x18005450d  pop     r12
0x18005450f  pop     rdi
0x180054510  pop     rsi
0x180054511  pop     rbp
0x180054512  retn
```
