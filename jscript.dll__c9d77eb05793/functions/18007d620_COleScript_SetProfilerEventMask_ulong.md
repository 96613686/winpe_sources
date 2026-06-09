# COleScript::SetProfilerEventMask(ulong)

- ea: `0x18007d620`
- end: `0x18007d67f`
- name: `?SetProfilerEventMask@COleScript@@UEAAJK@Z`
- size: `95`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007d620`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007d644`
- `KERNEL32!GetCurrentThreadId` at `0x18007d644`

## pseudocode

```c
__int64 __fastcall COleScript::SetProfilerEventMask(COleScript *this, int a2)
{
  int v4; // ebx
  __int64 v5; // rax

  if ( !*((_QWORD *)this + 80) )
    return 2147500037LL;
  v4 = *((_DWORD *)this + 57);
  if ( GetCurrentThreadId() != v4 )
    return 2147500037LL;
  v5 = *((_QWORD *)this + 80);
  if ( !*(_QWORD *)(v5 + 8) )
    return 2147746305LL;
  *(_DWORD *)(v5 + 24) = a2;
  return 0;
}

```

## disassembly

```asm
0x18007d620  mov     [rsp+arg_0], rbx
0x18007d625  mov     [rsp+arg_8], rsi
0x18007d62a  push    rdi
0x18007d62b  sub     rsp, 20h
0x18007d62f  cmp     qword ptr [rcx+280h], 0
0x18007d637  mov     esi, edx
0x18007d639  mov     rdi, rcx
0x18007d63c  jz      short loc_18007D66A
0x18007d63e  mov     ebx, [rcx+0E4h]
0x18007d644  call    cs:__imp_GetCurrentThreadId
0x18007d64a  cmp     eax, ebx
0x18007d64c  jnz     short loc_18007D66A
0x18007d64e  mov     rax, [rdi+280h]
0x18007d655  cmp     qword ptr [rax+8], 0
0x18007d65a  jnz     short loc_18007D663
0x18007d65c  mov     eax, 80040201h
0x18007d661  jmp     short loc_18007D66F
0x18007d663  mov     [rax+18h], esi
0x18007d666  xor     eax, eax
0x18007d668  jmp     short loc_18007D66F
0x18007d66a  mov     eax, 80004005h
0x18007d66f  mov     rbx, [rsp+28h+arg_0]
0x18007d674  mov     rsi, [rsp+28h+arg_8]
0x18007d679  add     rsp, 20h
0x18007d67d  pop     rdi
0x18007d67e  retn
```
