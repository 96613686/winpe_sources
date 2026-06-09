# CFilteringPlatformHelperClass::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x1800088f0`
- end: `0x180008901`
- name: `?Repair@CFilteringPlatformHelperClass@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `17`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *__hidden this, struct tagRepairInfo *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::Repair(
        CFilteringPlatformHelperClass *this,
        struct tagRepairInfo *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  *a4 = RS_USER_ACTION;
  result = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800088f0  mov     dword ptr [r9], 4
0x1800088f7  xor     eax, eax
0x1800088f9  mov     dword ptr [r8], 0
0x180008900  retn
```
