# InitializeLock

- ea: `0x1800065e0`
- end: `0x18000667e`
- name: `InitializeLock`
- size: `158`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064a0`

## callees

- `0x1800065e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800065fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006616`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800065fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006616`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000663a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000663a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000664b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000664b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006655`

## pseudocode

```c
__int64 __fastcall InitializeLock(LPCRITICAL_SECTION lpCriticalSection)
{
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  HANDLE v3; // rax

  EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 1, 1, 0);
  lpCriticalSection[1].DebugInfo = EventW;
  if ( !EventW )
    return 0;
  v3 = CreateEventW(0, 1, 1, 0);
  lpCriticalSection[1].OwningThread = v3;
  if ( !v3 )
  {
    CloseHandle(lpCriticalSection[1].DebugInfo);
    return 0;
  }
  InitializeCriticalSection(lpCriticalSection);
  *(HANDLE *)((char *)&lpCriticalSection[1].LockSemaphore + 4) = 0;
  lpCriticalSection[1].LockCount = 1;
  LODWORD(lpCriticalSection[1].LockSemaphore) = 1;
  return 1;
}

```

## disassembly

```asm
0x1800065e0  mov     [rsp+arg_0], rcx
0x1800065e5  push    rbx
0x1800065e6  sub     rsp, 20h
0x1800065ea  mov     rbx, rcx
0x1800065ed  xor     r9d, r9d; lpName
0x1800065f0  mov     edx, 1; bManualReset
0x1800065f5  mov     r8d, edx; bInitialState
0x1800065f8  xor     ecx, ecx; lpEventAttributes
0x1800065fa  call    cs:__imp_CreateEventW
0x180006600  mov     [rbx+28h], rax
0x180006604  test    rax, rax
0x180006607  jz      short loc_18000662F
0x180006609  xor     r9d, r9d; lpName
0x18000660c  mov     edx, 1; bManualReset
0x180006611  mov     r8d, edx; bInitialState
0x180006614  xor     ecx, ecx; lpEventAttributes
0x180006616  call    cs:__imp_CreateEventW
0x18000661c  mov     [rbx+38h], rax
0x180006620  test    rax, rax
0x180006623  jnz     short loc_180006637
0x180006625  mov     rcx, [rbx+28h]; hObject
0x180006629  call    cs:__imp_CloseHandle
0x18000662f  xor     eax, eax
0x180006631  add     rsp, 20h
0x180006635  pop     rbx
0x180006636  retn
0x180006637  mov     rcx, rbx; lpCriticalSection
0x18000663a  call    cs:__imp_InitializeCriticalSection
0x180006640  jmp     short loc_18000665F
0x180006642  mov     rbx, [rsp+28h+arg_0]
0x180006647  mov     rcx, [rbx+38h]; hObject
0x18000664b  call    cs:__imp_CloseHandle
0x180006651  mov     rcx, [rbx+28h]; hObject
0x180006655  call    cs:__imp_CloseHandle
0x18000665b  xor     eax, eax
0x18000665d  jmp     short loc_180006631
0x18000665f  xor     ecx, ecx
0x180006661  mov     [rbx+44h], rcx
0x180006665  mov     dword ptr [rbx+30h], 1
0x18000666c  mov     dword ptr [rbx+40h], 1
0x180006673  mov     eax, 1
0x180006678  add     rsp, 20h
0x18000667c  pop     rbx
0x18000667d  retn
```
