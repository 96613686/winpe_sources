# DfscRmIsTimeToRefresh

- ea: `0x14001cfd0`
- end: `0x14001d084`
- name: `DfscRmIsTimeToRefresh`
- size: `180`
- prototype: `char __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c8ac`
- `0x14001cb40`
- `0x14001cee0`
- `0x14001d110`
- `0x14001fb50`

## callees

- `0x14001cfd0`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x14001cfe7`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001cff5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001cfe7`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001cff5`

## pseudocode

```c
char __fastcall DfscRmIsTimeToRefresh(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  unsigned __int64 TimeIncrement; // rbp
  ULONG v6; // edx
  int v7; // r9d
  char result; // al

  v1 = *(_QWORD *)(a1 + 16);
  v3 = *(unsigned int *)(v1 + 40);
  v4 = *(_QWORD *)(v1 + 32);
  TimeIncrement = KeQueryTimeIncrement();
  v6 = KeQueryTimeIncrement();
  if ( (*(_DWORD *)(a1 + 8) & 4) != 0 )
    return 1;
  v7 = *(_DWORD *)(a1 + 8);
  if ( MEMORY[0xFFFFF78000000320] >= (__int64)(10000000
                                             * (unsigned __int64)(unsigned int)(HIDWORD(xmmword_14000C750) * v3)
                                             / v6
                                             + v4) )
  {
    *(_DWORD *)(a1 + 8) = v7 | 5;
    return 1;
  }
  if ( (v7 & 1) != 0 )
    return 1;
  if ( MEMORY[0xFFFFF78000000320] < (__int64)(v4 + 10000000 * v3 / TimeIncrement) )
    return 0;
  result = 1;
  *(_DWORD *)(a1 + 8) = v7 | 1;
  return result;
}

```

## disassembly

```asm
0x14001cfd0  push    rbx
0x14001cfd2  push    rbp
0x14001cfd3  push    rsi
0x14001cfd4  push    rdi
0x14001cfd5  sub     rsp, 28h
0x14001cfd9  mov     rax, [rcx+10h]
0x14001cfdd  mov     rbx, rcx
0x14001cfe0  mov     edi, [rax+28h]
0x14001cfe3  mov     rsi, [rax+20h]
0x14001cfe7  call    cs:__imp_KeQueryTimeIncrement
0x14001cfee  nop     dword ptr [rax+rax+00h]
0x14001cff3  mov     ebp, eax
0x14001cff5  call    cs:__imp_KeQueryTimeIncrement
0x14001cffc  nop     dword ptr [rax+rax+00h]
0x14001d001  mov     ecx, [rbx+8]
0x14001d004  mov     edx, eax
0x14001d006  test    cl, 4
0x14001d009  jnz     short loc_14001D062
0x14001d00b  mov     ecx, edx
0x14001d00d  mov     eax, edi
0x14001d00f  imul    eax, dword ptr cs:xmmword_14000C750+0Ch
0x14001d016  xor     edx, edx
0x14001d018  imul    rax, 989680h
0x14001d01f  div     rcx
0x14001d022  mov     rcx, 0FFFFF78000000320h
0x14001d02c  mov     rcx, [rcx]
0x14001d02f  lea     rdx, [rax+rsi]
0x14001d033  mov     r9d, [rbx+8]
0x14001d037  cmp     rcx, rdx
0x14001d03a  jge     short loc_14001D06E
0x14001d03c  test    r9b, 1
0x14001d040  jnz     short loc_14001D062
0x14001d042  imul    rax, rdi, 989680h
0x14001d049  xor     edx, edx
0x14001d04b  div     rbp
0x14001d04e  add     rax, rsi
0x14001d051  cmp     rcx, rax
0x14001d054  jge     short loc_14001D078
0x14001d056  xor     al, al
0x14001d058  add     rsp, 28h
0x14001d05c  pop     rdi
0x14001d05d  pop     rsi
0x14001d05e  pop     rbp
0x14001d05f  pop     rbx
0x14001d060  retn
0x14001d062  mov     al, 1
0x14001d064  add     rsp, 28h
0x14001d068  pop     rdi
0x14001d069  pop     rsi
0x14001d06a  pop     rbp
0x14001d06b  pop     rbx
0x14001d06c  retn
0x14001d06e  or      r9d, 5
0x14001d072  mov     [rbx+8], r9d
0x14001d076  jmp     short loc_14001D062
0x14001d078  or      r9d, 1
0x14001d07c  mov     al, 1
0x14001d07e  mov     [rbx+8], r9d
0x14001d082  jmp     short loc_14001D058
```
