# COleScript::OnLeaveScript(void)

- ea: `0x180016b54`
- end: `0x180016bc2`
- name: `?OnLeaveScript@COleScript@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f108`

## callees

- `0x180016b54`
- `0x180016e68`
- `0x1800172e8`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180016b67`
- `KERNEL32!GetCurrentThreadId` at `0x180016b67`

## pseudocode

```c
void __fastcall COleScript::OnLeaveScript(COleScript *this)
{
  int v1; // ebx
  __int64 v3; // rcx

  v1 = *((_DWORD *)this + 65);
  if ( GetCurrentThreadId() == v1 )
  {
    v3 = *((_QWORD *)this + 22);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
    if ( (unsigned int)COleScript::DisableInterrupts(this) )
    {
      if ( (*((_DWORD *)this + 75))-- == 1 )
        *((_DWORD *)this + 74) = 0;
      COleScript::EnableInterrupts(this);
    }
  }
}

```

## disassembly

```asm
0x180016b54  mov     [rsp+arg_8], rbx
0x180016b59  push    rdi
0x180016b5a  sub     rsp, 20h
0x180016b5e  mov     ebx, [rcx+104h]
0x180016b64  mov     rdi, rcx
0x180016b67  call    cs:__imp_GetCurrentThreadId
0x180016b6e  nop     dword ptr [rax+rax+00h]
0x180016b73  cmp     eax, ebx
0x180016b75  jnz     short loc_180016BB6
0x180016b77  mov     rcx, [rdi+0B0h]
0x180016b7e  test    rcx, rcx
0x180016b81  jz      short loc_180016B8F
0x180016b83  mov     rax, [rcx]
0x180016b86  mov     rax, [rax+50h]
0x180016b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b8f  mov     rcx, rdi; this
0x180016b92  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180016b97  test    eax, eax
0x180016b99  jz      short loc_180016BB6
0x180016b9b  add     dword ptr [rdi+12Ch], 0FFFFFFFFh
0x180016ba2  jnz     short loc_180016BAE
0x180016ba4  mov     dword ptr [rdi+128h], 0
0x180016bae  mov     rcx, rdi; this
0x180016bb1  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180016bb6  mov     rbx, [rsp+28h+arg_8]
0x180016bbb  add     rsp, 20h
0x180016bbf  pop     rdi
0x180016bc0  retn
```
