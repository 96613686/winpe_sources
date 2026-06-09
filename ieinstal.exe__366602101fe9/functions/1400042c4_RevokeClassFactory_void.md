# RevokeClassFactory(void)

- ea: `0x1400042c4`
- end: `0x14000430b`
- name: `?RevokeClassFactory@@YAJXZ`
- size: `71`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cd0`
- `0x140007bcc`
- `0x14000ca10`

## callees

- `0x1400042c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400042f2`
- `KERNEL32!DeleteCriticalSection` at `0x1400042f2`
- `ole32!CoRevokeClassObject` at `0x1400042dd`
- `ole32!CoRevokeClassObject` at `0x1400042dd`

## pseudocode

```c
__int64 RevokeClassFactory(void)
{
  unsigned int v0; // ebx

  if ( _InterlockedExchange(&g_fClassRegistered, 0) == 1 )
  {
    v0 = CoRevokeClassObject(g_dwRegister);
    DeleteCriticalSection(&g_DetourCriticalSection);
  }
  else
  {
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x1400042c4  push    rbx
0x1400042c6  sub     rsp, 20h
0x1400042ca  xor     eax, eax
0x1400042cc  xchg    eax, cs:?g_fClassRegistered@@3JA; long g_fClassRegistered
0x1400042d2  cmp     eax, 1
0x1400042d5  jnz     short loc_140004300
0x1400042d7  mov     ecx, cs:?g_dwRegister@@3KA; dwRegister
0x1400042dd  call    cs:__imp_CoRevokeClassObject
0x1400042e4  nop     dword ptr [rax+rax+00h]
0x1400042e9  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400042f0  mov     ebx, eax
0x1400042f2  call    cs:__imp_DeleteCriticalSection
0x1400042f9  nop     dword ptr [rax+rax+00h]
0x1400042fe  jmp     short loc_140004302
0x140004300  xor     ebx, ebx
0x140004302  mov     eax, ebx
0x140004304  add     rsp, 20h
0x140004308  pop     rbx
0x140004309  retn
```
