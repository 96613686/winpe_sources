# COleScript::OnEnterScript(void)

- ea: `0x180019dac`
- end: `0x180019e20`
- name: `?OnEnterScript@COleScript@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013044`
- `0x180019d24`

## callees

- `0x180019dac`
- `0x180019e28`
- `0x18001a29c`
- `0x18001a2dc`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019dbf`
- `KERNEL32!GetCurrentThreadId` at `0x180019dbf`

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
0x180019dac  mov     [rsp+arg_0], rbx
0x180019db1  push    rdi
0x180019db2  sub     rsp, 20h
0x180019db6  mov     ebx, [rcx+104h]
0x180019dbc  mov     rdi, rcx
0x180019dbf  call    cs:__imp_GetCurrentThreadId
0x180019dc5  cmp     eax, ebx
0x180019dc7  jnz     short loc_180019E15
0x180019dc9  mov     rcx, rdi; this
0x180019dcc  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180019dd1  test    eax, eax
0x180019dd3  jz      short loc_180019E15
0x180019dd5  inc     dword ptr [rdi+12Ch]
0x180019ddb  cmp     dword ptr [rdi+12Ch], 1
0x180019de2  mov     dword ptr [rdi+128h], 1
0x180019dec  jnz     short loc_180019DFA
0x180019dee  lea     rcx, [rdi+260h]; struct tagEXCEPINFO *
0x180019df5  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180019dfa  mov     rcx, rdi; this
0x180019dfd  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180019e02  mov     rcx, [rdi+0B0h]
0x180019e09  mov     rax, [rcx]
0x180019e0c  mov     rax, [rax+48h]
0x180019e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e15  mov     rbx, [rsp+28h+arg_0]
0x180019e1a  add     rsp, 20h
0x180019e1e  pop     rdi
0x180019e1f  retn
```
