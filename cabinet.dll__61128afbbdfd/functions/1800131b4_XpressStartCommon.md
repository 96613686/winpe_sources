# XpressStartCommon

- ea: `0x1800131b4`
- end: `0x180013237`
- name: `XpressStartCommon`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013150`
- `0x180013170`
- `0x180013190`
- `0x180017910`

## callees

- `0x1800131b4`
- `0x180013240`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall XpressStartCommon(
        __int64 (__fastcall *a1)(__int64, __int64),
        void (__fastcall *a2)(__int64, __int64),
        __int64 a3,
        int a4,
        __int16 a5)
{
  __int64 v9; // rax
  __int64 v10; // rbx

  v9 = a1(a3, 40);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)(v9 + 4) = 0;
    *(_WORD *)v9 = a5;
    *(_WORD *)(v9 + 2) = 0;
    *(_QWORD *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 8) = a1;
    *(_QWORD *)(v9 + 16) = a2;
    *(_QWORD *)(v9 + 24) = a3;
    if ( (unsigned int)XpressReallocateWorkspace(v9, a4) )
    {
      a2(a3, v10);
      return 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800131b4  push    rbx
0x1800131b6  push    rbp
0x1800131b7  push    rsi
0x1800131b8  push    rdi
0x1800131b9  push    r14
0x1800131bb  sub     rsp, 20h
0x1800131bf  mov     rbp, rcx
0x1800131c2  mov     rsi, rdx
0x1800131c5  mov     rax, rbp
0x1800131c8  mov     edx, 28h ; '('
0x1800131cd  mov     rcx, r8
0x1800131d0  mov     r14d, r9d
0x1800131d3  mov     rdi, r8
0x1800131d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131db  mov     rbx, rax
0x1800131de  test    rax, rax
0x1800131e1  jz      short loc_180013217
0x1800131e3  mov     dword ptr [rax+4], 0
0x1800131ea  mov     edx, r14d
0x1800131ed  movzx   eax, [rsp+48h+arg_20]
0x1800131f2  mov     rcx, rbx
0x1800131f5  mov     [rbx], ax
0x1800131f8  xor     eax, eax
0x1800131fa  mov     [rbx+2], ax
0x1800131fe  mov     [rbx+20h], rax
0x180013202  mov     [rbx+8], rbp
0x180013206  mov     [rbx+10h], rsi
0x18001320a  mov     [rbx+18h], rdi
0x18001320e  call    XpressReallocateWorkspace
0x180013213  test    eax, eax
0x180013215  jnz     short loc_180013225
0x180013217  mov     rax, rbx
0x18001321a  add     rsp, 20h
0x18001321e  pop     r14
0x180013220  pop     rdi
0x180013221  pop     rsi
0x180013222  pop     rbp
0x180013223  pop     rbx
0x180013224  retn
0x180013225  mov     rdx, rbx
0x180013228  mov     rcx, rdi
0x18001322b  mov     rax, rsi
0x18001322e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013233  xor     ebx, ebx
0x180013235  jmp     short loc_180013217
```
