# COleScript::StopProfiling(long)

- ea: `0x18007f550`
- end: `0x18007f5ae`
- name: `?StopProfiling@COleScript@@UEAAJJ@Z`
- size: `94`
- prototype: `int(COleScript *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180062efc`
- `0x18007f550`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007f574`
- `KERNEL32!GetCurrentThreadId` at `0x18007f574`

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
0x18007f550  mov     [rsp+arg_0], rbx
0x18007f555  mov     [rsp+arg_8], rsi
0x18007f55a  push    rdi
0x18007f55b  sub     rsp, 20h
0x18007f55f  cmp     qword ptr [rcx+280h], 0
0x18007f567  mov     esi, edx
0x18007f569  mov     rdi, rcx
0x18007f56c  jz      short loc_18007F598
0x18007f56e  mov     ebx, [rcx+0E4h]
0x18007f574  call    cs:__imp_GetCurrentThreadId
0x18007f57b  nop     dword ptr [rax+rax+00h]
0x18007f580  cmp     eax, ebx
0x18007f582  jnz     short loc_18007F598
0x18007f584  mov     rcx, [rdi+280h]
0x18007f58b  mov     edx, esi; int
0x18007f58d  add     rcx, 8; this
0x18007f591  call    ?ShutdownAndReleaseProfiler@EEToProfInterfaceImpl@@QEAAJJ@Z; EEToProfInterfaceImpl::ShutdownAndReleaseProfiler(long)
0x18007f596  jmp     short loc_18007F59D
0x18007f598  mov     eax, 80004005h
0x18007f59d  mov     rbx, [rsp+28h+arg_0]
0x18007f5a2  mov     rsi, [rsp+28h+arg_8]
0x18007f5a7  add     rsp, 20h
0x18007f5ab  pop     rdi
0x18007f5ac  retn
```
