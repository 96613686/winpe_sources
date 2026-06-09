# COleScript::SetProfilerEventMask(ulong)

- ea: `0x18007ef40`
- end: `0x18007efa6`
- name: `?SetProfilerEventMask@COleScript@@UEAAJK@Z`
- size: `102`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007ef40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007ef64`
- `KERNEL32!GetCurrentThreadId` at `0x18007ef64`

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
0x18007ef40  mov     [rsp+arg_0], rbx
0x18007ef45  mov     [rsp+arg_8], rsi
0x18007ef4a  push    rdi
0x18007ef4b  sub     rsp, 20h
0x18007ef4f  cmp     qword ptr [rcx+280h], 0
0x18007ef57  mov     esi, edx
0x18007ef59  mov     rdi, rcx
0x18007ef5c  jz      short loc_18007EF90
0x18007ef5e  mov     ebx, [rcx+0E4h]
0x18007ef64  call    cs:__imp_GetCurrentThreadId
0x18007ef6b  nop     dword ptr [rax+rax+00h]
0x18007ef70  cmp     eax, ebx
0x18007ef72  jnz     short loc_18007EF90
0x18007ef74  mov     rax, [rdi+280h]
0x18007ef7b  cmp     qword ptr [rax+8], 0
0x18007ef80  jnz     short loc_18007EF89
0x18007ef82  mov     eax, 80040201h
0x18007ef87  jmp     short loc_18007EF95
0x18007ef89  mov     [rax+18h], esi
0x18007ef8c  xor     eax, eax
0x18007ef8e  jmp     short loc_18007EF95
0x18007ef90  mov     eax, 80004005h
0x18007ef95  mov     rbx, [rsp+28h+arg_0]
0x18007ef9a  mov     rsi, [rsp+28h+arg_8]
0x18007ef9f  add     rsp, 20h
0x18007efa3  pop     rdi
0x18007efa4  retn
```
