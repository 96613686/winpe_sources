# CTrigger::SetTrigger(_TASK_TRIGGER * const)

- ea: `0x18000e550`
- end: `0x18000e571`
- name: `?SetTrigger@CTrigger@@UEAAJQEAU_TASK_TRIGGER@@@Z`
- size: `33`
- prototype: `int(CTrigger *__hidden this, struct _TASK_TRIGGER *const)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000e2ac`
- `0x18000e550`

## pseudocode

```c
__int64 __fastcall CTrigger::SetTrigger(CTrigger *this, struct _TASK_TRIGGER *const a2)
{
  if ( a2 && a2->cbTriggerSize == 48 )
    return CJob::SetTrigger(*((CJob **)this + 1), *((_WORD *)this + 8), a2);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18000e550  test    rdx, rdx
0x18000e553  jz      short loc_18000E56B
0x18000e555  cmp     word ptr [rdx], 30h ; '0'
0x18000e559  jnz     short loc_18000E56B
0x18000e55b  mov     r8, rdx; struct _TASK_TRIGGER *
0x18000e55e  movzx   edx, word ptr [rcx+10h]; unsigned __int16
0x18000e562  mov     rcx, [rcx+8]; this
0x18000e566  jmp     ?SetTrigger@CJob@@QEAAJGPEAU_TASK_TRIGGER@@@Z; CJob::SetTrigger(ushort,_TASK_TRIGGER *)
0x18000e56b  mov     eax, 80070057h
0x18000e570  retn
```
