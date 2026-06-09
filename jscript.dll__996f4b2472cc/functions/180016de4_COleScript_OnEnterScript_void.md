# COleScript::OnEnterScript(void)

- ea: `0x180016de4`
- end: `0x180016e5f`
- name: `?OnEnterScript@COleScript@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001028c`
- `0x180016d48`

## callees

- `0x180016de4`
- `0x180016e68`
- `0x1800172e8`
- `0x180017330`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180016df7`
- `KERNEL32!GetCurrentThreadId` at `0x180016df7`

## pseudocode

```c
void __fastcall COleScript::OnEnterScript(COleScript *this)
{
  int v1; // ebx
  bool v3; // zf

  v1 = *((_DWORD *)this + 65);
  if ( GetCurrentThreadId() == v1 && (unsigned int)COleScript::DisableInterrupts(this) )
  {
    v3 = ++*((_DWORD *)this + 75) == 1;
    *((_DWORD *)this + 74) = 1;
    if ( v3 )
      FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 608));
    COleScript::EnableInterrupts(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 72LL))(*((_QWORD *)this + 22));
  }
}

```

## disassembly

```asm
0x180016de4  mov     [rsp+arg_0], rbx
0x180016de9  push    rdi
0x180016dea  sub     rsp, 20h
0x180016dee  mov     ebx, [rcx+104h]
0x180016df4  mov     rdi, rcx
0x180016df7  call    cs:__imp_GetCurrentThreadId
0x180016dfe  nop     dword ptr [rax+rax+00h]
0x180016e03  cmp     eax, ebx
0x180016e05  jnz     short loc_180016E53
0x180016e07  mov     rcx, rdi; this
0x180016e0a  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180016e0f  test    eax, eax
0x180016e11  jz      short loc_180016E53
0x180016e13  inc     dword ptr [rdi+12Ch]
0x180016e19  cmp     dword ptr [rdi+12Ch], 1
0x180016e20  mov     dword ptr [rdi+128h], 1
0x180016e2a  jnz     short loc_180016E38
0x180016e2c  lea     rcx, [rdi+260h]; struct tagEXCEPINFO *
0x180016e33  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180016e38  mov     rcx, rdi; this
0x180016e3b  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180016e40  mov     rcx, [rdi+0B0h]
0x180016e47  mov     rax, [rcx]
0x180016e4a  mov     rax, [rax+48h]
0x180016e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e53  mov     rbx, [rsp+28h+arg_0]
0x180016e58  add     rsp, 20h
0x180016e5c  pop     rdi
0x180016e5d  retn
```
