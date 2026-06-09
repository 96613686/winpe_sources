# COleScript::StopProfiling(long)

- ea: `0x18007dc10`
- end: `0x18007dc67`
- name: `?StopProfiling@COleScript@@UEAAJJ@Z`
- size: `87`
- prototype: `int(COleScript *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180061cb0`
- `0x18007dc10`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007dc34`
- `KERNEL32!GetCurrentThreadId` at `0x18007dc34`

## pseudocode

```c
__int64 __fastcall COleScript::StopProfiling(COleScript *this, int a2)
{
  int v4; // ebx

  if ( *((_QWORD *)this + 80) && (v4 = *((_DWORD *)this + 57), GetCurrentThreadId() == v4) )
    return EEToProfInterfaceImpl::ShutdownAndReleaseProfiler(
             (EEToProfInterfaceImpl *)(*((_QWORD *)this + 80) + 8LL),
             a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18007dc10  mov     [rsp+arg_0], rbx
0x18007dc15  mov     [rsp+arg_8], rsi
0x18007dc1a  push    rdi
0x18007dc1b  sub     rsp, 20h
0x18007dc1f  cmp     qword ptr [rcx+280h], 0
0x18007dc27  mov     esi, edx
0x18007dc29  mov     rdi, rcx
0x18007dc2c  jz      short loc_18007DC52
0x18007dc2e  mov     ebx, [rcx+0E4h]
0x18007dc34  call    cs:__imp_GetCurrentThreadId
0x18007dc3a  cmp     eax, ebx
0x18007dc3c  jnz     short loc_18007DC52
0x18007dc3e  mov     rcx, [rdi+280h]
0x18007dc45  mov     edx, esi; int
0x18007dc47  add     rcx, 8; this
0x18007dc4b  call    ?ShutdownAndReleaseProfiler@EEToProfInterfaceImpl@@QEAAJJ@Z; EEToProfInterfaceImpl::ShutdownAndReleaseProfiler(long)
0x18007dc50  jmp     short loc_18007DC57
0x18007dc52  mov     eax, 80004005h
0x18007dc57  mov     rbx, [rsp+28h+arg_0]
0x18007dc5c  mov     rsi, [rsp+28h+arg_8]
0x18007dc61  add     rsp, 20h
0x18007dc65  pop     rdi
0x18007dc66  retn
```
