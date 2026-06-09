# COleScript::GetCurrentScriptThreadID(ulong *)

- ea: `0x18007a130`
- end: `0x18007a155`
- name: `?GetCurrentScriptThreadID@COleScript@@UEAAJPEAK@Z`
- size: `37`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007a130`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007a145`
- `KERNEL32!GetCurrentThreadId` at `0x18007a145`

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
0x18007a130  push    rbx
0x18007a132  sub     rsp, 20h
0x18007a136  mov     rbx, rdx
0x18007a139  test    rdx, rdx
0x18007a13c  jnz     short loc_18007A145
0x18007a13e  mov     eax, 80004003h
0x18007a143  jmp     short loc_18007A14F
0x18007a145  call    cs:__imp_GetCurrentThreadId
0x18007a14b  mov     [rbx], eax
0x18007a14d  xor     eax, eax
0x18007a14f  add     rsp, 20h
0x18007a153  pop     rbx
0x18007a154  retn
```
