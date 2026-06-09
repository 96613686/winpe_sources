# TeredoCompartmentQueryGlobals

- ea: `0x1800542b0`
- end: `0x1800544f4`
- name: `TeredoCompartmentQueryGlobals`
- size: `580`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18004b630`
- `0x1800542b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800542fd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005431f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054341`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054363`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054385`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005440e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054432`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054456`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005447a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005449c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544c7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800542fd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005431f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054341`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054363`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054385`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800543cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005440e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054432`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054456`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005447a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005449c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800544c7`

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
0x1800542b0  mov     [rsp-28h+arg_10], rbx
0x1800542b5  push    rbp
0x1800542b6  push    rsi
0x1800542b7  push    rdi
0x1800542b8  push    r12
0x1800542ba  push    r15
0x1800542bc  mov     rbp, rsp
0x1800542bf  sub     rsp, 50h
0x1800542c3  mov     rax, cs:__security_cookie
0x1800542ca  xor     rax, rsp
0x1800542cd  mov     [rbp+var_8], rax
0x1800542d1  xor     r12d, r12d
0x1800542d4  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800542d8  mov     rsi, rdx
0x1800542db  mov     [rbp+NumberOfBytesWritten], r12d
0x1800542df  mov     rdi, rcx
0x1800542e2  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800542e7  xorps   xmm0, xmm0
0x1800542ea  lea     rdx, [rcx+10h]; lpBuffer
0x1800542ee  lea     r15d, [r12+4]
0x1800542f3  mov     rcx, rsi; hFile
0x1800542f6  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800542f9  movups  [rbp+Buffer], xmm0
0x1800542fd  call    cs:__imp_WriteFile
0x180054304  nop     dword ptr [rax+rax+00h]
0x180054309  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005430d  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054312  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054315  lea     rdx, dword_1800CA09C; lpBuffer
0x18005431c  mov     rcx, rsi; hFile
0x18005431f  call    cs:__imp_WriteFile
0x180054326  nop     dword ptr [rax+rax+00h]
0x18005432b  lea     rdx, [rdi+0B34h]; lpBuffer
0x180054332  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054337  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005433b  mov     r8d, r15d; nNumberOfBytesToWrite
0x18005433e  mov     rcx, rsi; hFile
0x180054341  call    cs:__imp_WriteFile
0x180054348  nop     dword ptr [rax+rax+00h]
0x18005434d  lea     rdx, [rdi+0B3Ch]; lpBuffer
0x180054354  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054359  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005435d  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054360  mov     rcx, rsi; hFile
0x180054363  call    cs:__imp_WriteFile
0x18005436a  nop     dword ptr [rax+rax+00h]
0x18005436f  lea     rdx, [rdi+0B30h]; lpBuffer
0x180054376  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005437b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005437f  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054382  mov     rcx, rsi; hFile
0x180054385  call    cs:__imp_WriteFile
0x18005438c  nop     dword ptr [rax+rax+00h]
0x180054391  lea     rdx, [rdi+34E8h]; lpBuffer
0x180054398  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005439d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800543a1  mov     rcx, rsi; hFile
0x1800543a4  lea     r8d, [r12+58h]; nNumberOfBytesToWrite
0x1800543a9  call    cs:__imp_WriteFile
0x1800543b0  nop     dword ptr [rax+rax+00h]
0x1800543b5  lea     rdx, [rdi+0AD4h]; lpBuffer
0x1800543bc  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800543c1  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800543c5  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800543c8  mov     rcx, rsi; hFile
0x1800543cb  call    cs:__imp_WriteFile
0x1800543d2  nop     dword ptr [rax+rax+00h]
0x1800543d7  lea     eax, [r12+2]
0x1800543dc  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800543e1  mov     word ptr [rbp+Buffer], ax
0x1800543e5  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800543e9  mov     eax, [rdi+3584h]
0x1800543ef  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x1800543f4  not     eax
0x1800543f6  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800543fa  mov     dword ptr [rbp+Buffer+4], eax
0x1800543fd  mov     rcx, rsi; hFile
0x180054400  movzx   eax, word ptr [rdi+3582h]
0x180054407  not     ax
0x18005440a  mov     word ptr [rbp+Buffer+2], ax
0x18005440e  call    cs:__imp_WriteFile
0x180054415  nop     dword ptr [rax+rax+00h]
0x18005441a  lea     rdx, [rdi+31DCh]; lpBuffer
0x180054421  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054426  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005442a  mov     rcx, rsi; hFile
0x18005442d  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x180054432  call    cs:__imp_WriteFile
0x180054439  nop     dword ptr [rax+rax+00h]
0x18005443e  lea     rdx, [rdi+4B60h]; lpBuffer
0x180054445  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005444a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005444e  mov     rcx, rsi; hFile
0x180054451  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x180054456  call    cs:__imp_WriteFile
0x18005445d  nop     dword ptr [rax+rax+00h]
0x180054462  lea     rdx, [rdi+4B70h]; lpBuffer
0x180054469  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x18005446e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054472  mov     rcx, rsi; hFile
0x180054475  lea     r8d, [r12+10h]; nNumberOfBytesToWrite
0x18005447a  call    cs:__imp_WriteFile
0x180054481  nop     dword ptr [rax+rax+00h]
0x180054486  lea     rdx, [rdi+4B80h]; lpBuffer
0x18005448d  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x180054492  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054496  mov     r8d, r15d; nNumberOfBytesToWrite
0x180054499  mov     rcx, rsi; hFile
0x18005449c  call    cs:__imp_WriteFile
0x1800544a3  nop     dword ptr [rax+rax+00h]
0x1800544a8  cmp     dword ptr [rdi+10h], 1
0x1800544ac  jnz     short loc_1800544D3
0x1800544ae  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800544b2  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1800544b7  mov     r8d, 110h; nNumberOfBytesToWrite
0x1800544bd  lea     rdx, dword_1800CB7E8; lpBuffer
0x1800544c4  mov     rcx, rsi; hFile
0x1800544c7  call    cs:__imp_WriteFile
0x1800544ce  nop     dword ptr [rax+rax+00h]
0x1800544d3  mov     rcx, [rbp+var_8]
0x1800544d7  xor     rcx, rsp; StackCookie
0x1800544da  call    __security_check_cookie
0x1800544df  mov     rbx, [rsp+50h+arg_10]
0x1800544e7  add     rsp, 50h
0x1800544eb  pop     r15
0x1800544ed  pop     r12
0x1800544ef  pop     rdi
0x1800544f0  pop     rsi
0x1800544f1  pop     rbp
0x1800544f2  retn
```
