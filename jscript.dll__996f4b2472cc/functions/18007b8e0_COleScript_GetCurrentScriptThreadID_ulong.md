# COleScript::GetCurrentScriptThreadID(ulong *)

- ea: `0x18007b8e0`
- end: `0x18007b90c`
- name: `?GetCurrentScriptThreadID@COleScript@@UEAAJPEAK@Z`
- size: `44`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007b8e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007b8f5`
- `KERNEL32!GetCurrentThreadId` at `0x18007b8f5`

## pseudocode

```c
__int64 __fastcall COleScript::GetCurrentScriptThreadID(COleScript *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = GetCurrentThreadId();
  return 0;
}

```

## disassembly

```asm
0x18007b8e0  push    rbx
0x18007b8e2  sub     rsp, 20h
0x18007b8e6  mov     rbx, rdx
0x18007b8e9  test    rdx, rdx
0x18007b8ec  jnz     short loc_18007B8F5
0x18007b8ee  mov     eax, 80004003h
0x18007b8f3  jmp     short loc_18007B905
0x18007b8f5  call    cs:__imp_GetCurrentThreadId
0x18007b8fc  nop     dword ptr [rax+rax+00h]
0x18007b901  mov     [rbx], eax
0x18007b903  xor     eax, eax
0x18007b905  add     rsp, 20h
0x18007b909  pop     rbx
0x18007b90a  retn
```
