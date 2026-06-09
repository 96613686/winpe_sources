# SecPsGetProcessContextByIdForLoadImage

- ea: `0x14002f800`
- end: `0x14002f8e1`
- name: `SecPsGetProcessContextByIdForLoadImage`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002fa68`

## callees

- `0x140006754`
- `0x140011650`
- `0x14002c6b0`
- `0x14002f800`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14002f847`
- `ntoskrnl!ObfReferenceObject` at `0x14002f847`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002f86e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002f86e`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002f839`
- `ntoskrnl!PsGetProcessId` at `0x14002f858`
- `ntoskrnl!PsGetProcessId` at `0x14002f858`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f8b5`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f8b5`

## pseudocode

```c
__int64 __fastcall SecPsGetProcessContextByIdForLoadImage(struct _SLIST_ENTRY *a1, PSLIST_ENTRY *a2)
{
  struct _SLIST_ENTRY *ProcessId; // rdi
  int ProcessContextByObject; // ebx
  PEPROCESS Process; // [rsp+20h] [rbp-18h] BYREF

  Process = 0;
  *a2 = 0;
  ProcessId = a1;
  if ( a1 )
  {
    ProcessContextByObject = PsLookupProcessByProcessId(a1, &Process);
    if ( ProcessContextByObject < 0 )
      goto LABEL_6;
  }
  else
  {
    Process = PsInitialSystemProcess;
    ObfReferenceObject(PsInitialSystemProcess);
    ProcessId = (struct _SLIST_ENTRY *)PsGetProcessId(PsInitialSystemProcess);
  }
  ProcessContextByObject = SecGetProcessContextByObject(Process, a2);
  if ( ProcessContextByObject < 0 )
  {
    _mm_lfence();
    ProcessContextByObject = SecCreateProcessContext(ProcessId, Process, 0, a2);
  }
LABEL_6:
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)ProcessContextByObject;
}

```

## disassembly

```asm
0x14002f800  mov     r11, rsp
0x14002f803  mov     [r11+18h], rbx
0x14002f807  mov     [r11+20h], rsi
0x14002f80b  push    rdi
0x14002f80c  sub     rsp, 30h
0x14002f810  mov     rax, cs:__security_cookie
0x14002f817  xor     rax, rsp
0x14002f81a  mov     [rsp+38h+var_10], rax
0x14002f81f  mov     qword ptr [r11-18h], 0
0x14002f827  mov     rsi, rdx
0x14002f82a  mov     qword ptr [rdx], 0
0x14002f831  mov     rdi, rcx
0x14002f834  test    rcx, rcx
0x14002f837  jnz     short loc_14002F869
0x14002f839  mov     rax, cs:__imp_PsInitialSystemProcess
0x14002f840  mov     rcx, [rax]; Object
0x14002f843  mov     [r11-18h], rcx
0x14002f847  call    cs:__imp_ObfReferenceObject
0x14002f84e  nop     dword ptr [rax+rax+00h]
0x14002f853  mov     rcx, [rsp+38h+Process]; Process
0x14002f858  call    cs:__imp_PsGetProcessId
0x14002f85f  nop     dword ptr [rax+rax+00h]
0x14002f864  mov     rdi, rax
0x14002f867  jmp     short loc_14002F880
0x14002f869  lea     rdx, [rsp+38h+Process]; Process
0x14002f86e  call    cs:__imp_PsLookupProcessByProcessId
0x14002f875  nop     dword ptr [rax+rax+00h]
0x14002f87a  mov     ebx, eax
0x14002f87c  test    eax, eax
0x14002f87e  js      short loc_14002F8AB
0x14002f880  mov     rcx, [rsp+38h+Process]
0x14002f885  mov     rdx, rsi
0x14002f888  call    SecGetProcessContextByObject
0x14002f88d  mov     ebx, eax
0x14002f88f  test    eax, eax
0x14002f891  jns     short loc_14002F8AB
0x14002f893  lfence
0x14002f896  mov     rdx, [rsp+38h+Process]
0x14002f89b  mov     r9, rsi
0x14002f89e  xor     r8d, r8d
0x14002f8a1  mov     rcx, rdi
0x14002f8a4  call    SecCreateProcessContext
0x14002f8a9  mov     ebx, eax
0x14002f8ab  mov     rcx, [rsp+38h+Process]; Object
0x14002f8b0  test    rcx, rcx
0x14002f8b3  jz      short loc_14002F8C1
0x14002f8b5  call    cs:__imp_ObfDereferenceObject
0x14002f8bc  nop     dword ptr [rax+rax+00h]
0x14002f8c1  mov     eax, ebx
0x14002f8c3  mov     rcx, [rsp+38h+var_10]
0x14002f8c8  xor     rcx, rsp; StackCookie
0x14002f8cb  call    __security_check_cookie
0x14002f8d0  mov     rbx, [rsp+38h+arg_10]
0x14002f8d5  mov     rsi, [rsp+38h+arg_18]
0x14002f8da  add     rsp, 30h
0x14002f8de  pop     rdi
0x14002f8df  retn
```
