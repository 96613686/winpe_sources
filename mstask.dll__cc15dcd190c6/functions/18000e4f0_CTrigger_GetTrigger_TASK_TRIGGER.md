# CTrigger::GetTrigger(_TASK_TRIGGER *)

- ea: `0x18000e4f0`
- end: `0x18000e50b`
- name: `?GetTrigger@CTrigger@@UEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `27`
- prototype: `int(CTrigger *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180007cd0`
- `0x18000e4f0`

## pseudocode

```c
__int64 __fastcall CTrigger::GetTrigger(CTrigger *this, struct _TASK_TRIGGER *a2)
{
  if ( a2 )
    return CJob::GetTrigger(*((CJob **)this + 1), *((_WORD *)this + 8), a2);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18000e4f0  test    rdx, rdx
0x18000e4f3  jnz     short loc_18000E4FB
0x18000e4f5  mov     eax, 80070057h
0x18000e4fa  retn
0x18000e4fb  mov     r8, rdx; struct _TASK_TRIGGER *
0x18000e4fe  movzx   edx, word ptr [rcx+10h]; unsigned __int16
0x18000e502  mov     rcx, [rcx+8]; this
0x18000e506  jmp     ?GetTrigger@CJob@@QEAAJGPEAU_TASK_TRIGGER@@@Z; CJob::GetTrigger(ushort,_TASK_TRIGGER *)
```
