# COleScript::OnLeaveScript(void)

- ea: `0x180019b34`
- end: `0x180019b9b`
- name: `?OnLeaveScript@COleScript@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f91c`
- `0x1800107c0`
- `0x180011ecc`
- `0x180012ae4`

## callees

- `0x180019b34`
- `0x180019e28`
- `0x18001a29c`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019b47`
- `KERNEL32!GetCurrentThreadId` at `0x180019b47`

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
0x180019b34  mov     [rsp+arg_8], rbx
0x180019b39  push    rdi
0x180019b3a  sub     rsp, 20h
0x180019b3e  mov     ebx, [rcx+104h]
0x180019b44  mov     rdi, rcx
0x180019b47  call    cs:__imp_GetCurrentThreadId
0x180019b4d  cmp     eax, ebx
0x180019b4f  jnz     short loc_180019B90
0x180019b51  mov     rcx, [rdi+0B0h]
0x180019b58  test    rcx, rcx
0x180019b5b  jz      short loc_180019B69
0x180019b5d  mov     rax, [rcx]
0x180019b60  mov     rax, [rax+50h]
0x180019b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b69  mov     rcx, rdi; this
0x180019b6c  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180019b71  test    eax, eax
0x180019b73  jz      short loc_180019B90
0x180019b75  add     dword ptr [rdi+12Ch], 0FFFFFFFFh
0x180019b7c  jnz     short loc_180019B88
0x180019b7e  mov     dword ptr [rdi+128h], 0
0x180019b88  mov     rcx, rdi; this
0x180019b8b  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180019b90  mov     rbx, [rsp+28h+arg_8]
0x180019b95  add     rsp, 20h
0x180019b99  pop     rdi
0x180019b9a  retn
```
