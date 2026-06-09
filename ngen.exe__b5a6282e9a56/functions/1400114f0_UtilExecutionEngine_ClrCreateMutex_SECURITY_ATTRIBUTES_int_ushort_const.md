# UtilExecutionEngine::ClrCreateMutex(_SECURITY_ATTRIBUTES *,int,ushort const *)

- ea: `0x1400114f0`
- end: `0x140011502`
- name: `?ClrCreateMutex@UtilExecutionEngine@@EEAAPEAXPEAU_SECURITY_ATTRIBUTES@@HPEBG@Z`
- size: `18`
- prototype: `HANDLE __fastcall(UtilExecutionEngine *this, struct _SECURITY_ATTRIBUTES *, BOOL, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x1400114fb`

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
0x1400114f0  mov     eax, r8d
0x1400114f3  mov     rcx, rdx
0x1400114f6  mov     edx, eax
0x1400114f8  mov     r8, r9
0x1400114fb  jmp     cs:__imp_CreateMutexW
```
