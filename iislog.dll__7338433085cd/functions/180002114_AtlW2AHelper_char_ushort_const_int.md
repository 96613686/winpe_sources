# AtlW2AHelper(char *,ushort const *,int)

- ea: `0x180002114`
- end: `0x180002166`
- name: `?AtlW2AHelper@@YAPEADPEADPEBGH@Z`
- size: `82`
- prototype: `char *(char *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d48`
- `0x180006870`
- `0x180008720`

## callees

- `0x180002114`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000214f`
- `KERNEL32!WideCharToMultiByte` at `0x18000214f`

## pseudocode

```c
char *__fastcall AtlW2AHelper(char *a1, const unsigned __int16 *a2, int a3)
{
  if ( a1 && a2 && (*a1 = 0, WideCharToMultiByte(0, 0, a2, -1, a1, a3, 0, 0)) )
    return a1;
  else
    return 0;
}

```

## disassembly

```asm
0x180002114  mov     rax, rsp
0x180002117  push    rbx
0x180002118  sub     rsp, 40h
0x18000211c  mov     rbx, rcx
0x18000211f  test    rcx, rcx
0x180002122  jz      short loc_18000215E
0x180002124  test    rdx, rdx
0x180002127  jz      short loc_18000215E
0x180002129  mov     qword ptr [rax-10h], 0
0x180002131  or      r9d, 0FFFFFFFFh; cchWideChar
0x180002135  mov     qword ptr [rax-18h], 0
0x18000213d  mov     [rax-20h], r8d
0x180002141  mov     r8, rdx; lpWideCharStr
0x180002144  mov     [rax-28h], rcx
0x180002148  xor     edx, edx; dwFlags
0x18000214a  mov     byte ptr [rcx], 0
0x18000214d  xor     ecx, ecx; CodePage
0x18000214f  call    cs:__imp_WideCharToMultiByte
0x180002155  test    eax, eax
0x180002157  jz      short loc_18000215E
0x180002159  mov     rax, rbx
0x18000215c  jmp     short loc_180002160
0x18000215e  xor     eax, eax
0x180002160  add     rsp, 40h
0x180002164  pop     rbx
0x180002165  retn
```
