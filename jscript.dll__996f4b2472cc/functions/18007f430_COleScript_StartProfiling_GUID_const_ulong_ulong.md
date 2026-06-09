# COleScript::StartProfiling(_GUID const &,ulong,ulong)

- ea: `0x18007f430`
- end: `0x18007f498`
- name: `?StartProfiling@COleScript@@UEAAJAEBU_GUID@@KK@Z`
- size: `104`
- prototype: `int(COleScript *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180062938`
- `0x18007f430`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007f457`
- `KERNEL32!GetCurrentThreadId` at `0x18007f457`

## pseudocode

```c
__int64 __fastcall COleScript::StartProfiling(COleScript *this, const struct _GUID *a2, char a3, unsigned int a4)
{
  int v8; // ebx

  if ( *((_QWORD *)this + 80) && (v8 = *((_DWORD *)this + 57), GetCurrentThreadId() == v8) )
    return EEToProfInterfaceImpl::CreateAndInitializeProfiler(
             (LPVOID *)(*((_QWORD *)this + 80) + 8LL),
             *(struct COleScript **)(*((_QWORD *)this + 80) + 40LL),
             a2,
             a3,
             a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18007f430  push    rbx
0x18007f432  push    rbp
0x18007f433  push    rsi
0x18007f434  push    rdi
0x18007f435  push    r14
0x18007f437  sub     rsp, 30h
0x18007f43b  cmp     qword ptr [rcx+280h], 0
0x18007f443  mov     esi, r9d
0x18007f446  mov     ebp, r8d
0x18007f449  mov     r14, rdx
0x18007f44c  mov     rdi, rcx
0x18007f44f  jz      short loc_18007F487
0x18007f451  mov     ebx, [rcx+0E4h]
0x18007f457  call    cs:__imp_GetCurrentThreadId
0x18007f45e  nop     dword ptr [rax+rax+00h]
0x18007f463  cmp     eax, ebx
0x18007f465  jnz     short loc_18007F487
0x18007f467  mov     rdx, [rdi+280h]
0x18007f46e  mov     r9d, ebp; unsigned int
0x18007f471  mov     r8, r14; struct _GUID *
0x18007f474  mov     [rsp+58h+var_38], esi; unsigned int
0x18007f478  lea     rcx, [rdx+8]; ppv
0x18007f47c  mov     rdx, [rdx+28h]; struct COleScript *
0x18007f480  call    ?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z; EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)
0x18007f485  jmp     short loc_18007F48C
0x18007f487  mov     eax, 80004005h
0x18007f48c  add     rsp, 30h
0x18007f490  pop     r14
0x18007f492  pop     rdi
0x18007f493  pop     rsi
0x18007f494  pop     rbp
0x18007f495  pop     rbx
0x18007f496  retn
```
