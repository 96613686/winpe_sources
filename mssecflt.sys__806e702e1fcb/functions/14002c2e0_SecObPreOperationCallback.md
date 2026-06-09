# SecObPreOperationCallback

- ea: `0x14002c2e0`
- end: `0x14002c377`
- name: `SecObPreOperationCallback`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1400088e4`
- `0x1400088ec`
- `0x1400088f4`
- `0x1400088fc`
- `0x14002ba50`
- `0x14002bc14`
- `0x14002be2c`
- `0x14002c080`
- `0x14002c2e0`
- `0x14003b5cc`
- `0x14003b5d4`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x14002c30a`
- `ntoskrnl!PsThreadType` at `0x14002c337`
- `ntoskrnl!ExDesktopObjectType` at `0x14002c2f0`

## pseudocode

```c
__int64 __fastcall SecObPreOperationCallback(__int64 a1, __int64 a2)
{
  POBJECT_TYPE *v3; // rcx
  char IsCriticalProcessStrictProtectionEnabled; // al

  if ( *(_QWORD *)(a2 + 8) )
  {
    v3 = *(POBJECT_TYPE **)(a2 + 16);
    if ( v3 == ExDesktopObjectType )
    {
      SecObHandleOpenDesktopCallback((int *)a2);
      return 0;
    }
    if ( v3 == PsProcessType )
    {
      SecObHandleOpenProcessCallback(a2);
      if ( (unsigned __int8)SecIsCriticalProcessSuspendProtectionEnabled()
        || (unsigned __int8)SecIsCriticalProcessTerminationProtectionEnabled() )
      {
        goto LABEL_13;
      }
      IsCriticalProcessStrictProtectionEnabled = SecIsCriticalProcessStrictProtectionEnabled();
    }
    else
    {
      if ( v3 != PsThreadType )
        return 0;
      SecObHandleOpenThreadCallback(a2);
      if ( (unsigned __int8)SecIsCriticalThreadSuspendProtectionEnabled()
        || (unsigned __int8)SecIsCriticalThreadTerminationProtectionEnabled() )
      {
LABEL_13:
        SecObForbidAccessToHardenedResources((unsigned int *)a2);
        return 0;
      }
      IsCriticalProcessStrictProtectionEnabled = SecIsCriticalThreadStrictProtectionEnabled();
    }
    if ( !IsCriticalProcessStrictProtectionEnabled )
      return 0;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x14002c2e0  push    rbx
0x14002c2e2  sub     rsp, 20h
0x14002c2e6  cmp     qword ptr [rdx+8], 0
0x14002c2eb  mov     rbx, rdx
0x14002c2ee  jz      short loc_14002C36E
0x14002c2f0  mov     rax, cs:ExDesktopObjectType
0x14002c2f7  mov     rcx, [rdx+10h]
0x14002c2fb  cmp     rcx, [rax]
0x14002c2fe  jnz     short loc_14002C30A
0x14002c300  mov     rcx, rdx
0x14002c303  call    SecObHandleOpenDesktopCallback
0x14002c308  jmp     short loc_14002C36E
0x14002c30a  mov     rax, cs:__imp_PsProcessType
0x14002c311  cmp     rcx, [rax]
0x14002c314  jnz     short loc_14002C337
0x14002c316  mov     rcx, rbx
0x14002c319  call    SecObHandleOpenProcessCallback
0x14002c31e  call    SecIsCriticalProcessSuspendProtectionEnabled
0x14002c323  test    al, al
0x14002c325  jnz     short loc_14002C366
0x14002c327  call    SecIsCriticalProcessTerminationProtectionEnabled
0x14002c32c  test    al, al
0x14002c32e  jnz     short loc_14002C366
0x14002c330  call    SecIsCriticalProcessStrictProtectionEnabled
0x14002c335  jmp     short loc_14002C362
0x14002c337  mov     rax, cs:__imp_PsThreadType
0x14002c33e  cmp     rcx, [rax]
0x14002c341  jnz     short loc_14002C36E
0x14002c343  mov     rcx, rbx
0x14002c346  call    SecObHandleOpenThreadCallback
0x14002c34b  call    SecIsCriticalThreadSuspendProtectionEnabled
0x14002c350  test    al, al
0x14002c352  jnz     short loc_14002C366
0x14002c354  call    SecIsCriticalThreadTerminationProtectionEnabled
0x14002c359  test    al, al
0x14002c35b  jnz     short loc_14002C366
0x14002c35d  call    SecIsCriticalThreadStrictProtectionEnabled
0x14002c362  test    al, al
0x14002c364  jz      short loc_14002C36E
0x14002c366  mov     rcx, rbx
0x14002c369  call    SecObForbidAccessToHardenedResources
0x14002c36e  xor     eax, eax
0x14002c370  add     rsp, 20h
0x14002c374  pop     rbx
0x14002c375  retn
```
