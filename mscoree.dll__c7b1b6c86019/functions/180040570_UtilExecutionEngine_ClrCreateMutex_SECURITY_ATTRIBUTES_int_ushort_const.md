# UtilExecutionEngine::ClrCreateMutex(_SECURITY_ATTRIBUTES *,int,ushort const *)

- ea: `0x180040570`
- end: `0x180040582`
- name: `?ClrCreateMutex@UtilExecutionEngine@@EEAAPEAXPEAU_SECURITY_ATTRIBUTES@@HPEBG@Z`
- size: `18`
- prototype: `void *__fastcall(UtilExecutionEngine *__hidden this, struct _SECURITY_ATTRIBUTES *, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18004057b`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::ClrCreateMutex(
        UtilExecutionEngine *this,
        struct _SECURITY_ATTRIBUTES *a2,
        BOOL a3,
        const unsigned __int16 *a4)
{
  return CreateMutexW(a2, a3, a4);
}

```

## disassembly

```asm
0x180040570  mov     eax, r8d
0x180040573  mov     rcx, rdx
0x180040576  mov     edx, eax
0x180040578  mov     r8, r9
0x18004057b  jmp     cs:__imp_CreateMutexW
```
