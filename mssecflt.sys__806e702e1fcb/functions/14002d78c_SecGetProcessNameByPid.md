# SecGetProcessNameByPid

- ea: `0x14002d78c`
- end: `0x14002d808`
- name: `SecGetProcessNameByPid`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002dc0c`

## callees

- `0x1400100a4`
- `0x140011650`
- `0x14002d78c`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d7b6`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d7b6`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d7e1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d7e1`

## pseudocode

```c
__int64 __fastcall SecGetProcessNameByPid(void *a1, PUNICODE_STRING *a2)
{
  NTSTATUS ProcessImageName_0; // ebx
  PEPROCESS Process; // [rsp+20h] [rbp-18h] BYREF

  Process = 0;
  ProcessImageName_0 = PsLookupProcessByProcessId(a1, &Process);
  if ( ProcessImageName_0 >= 0 )
    ProcessImageName_0 = SeLocateProcessImageName_0(Process, a2);
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)ProcessImageName_0;
}

```

## disassembly

```asm
0x14002d78c  mov     [rsp+arg_10], rbx
0x14002d791  push    rdi
0x14002d792  sub     rsp, 30h
0x14002d796  mov     rax, cs:__security_cookie
0x14002d79d  xor     rax, rsp
0x14002d7a0  mov     [rsp+38h+var_10], rax
0x14002d7a5  mov     rdi, rdx
0x14002d7a8  mov     [rsp+38h+Process], 0
0x14002d7b1  lea     rdx, [rsp+38h+Process]; Process
0x14002d7b6  call    cs:__imp_PsLookupProcessByProcessId
0x14002d7bd  nop     dword ptr [rax+rax+00h]
0x14002d7c2  mov     ebx, eax
0x14002d7c4  test    eax, eax
0x14002d7c6  js      short loc_14002D7D7
0x14002d7c8  mov     rcx, [rsp+38h+Process]; Process
0x14002d7cd  mov     rdx, rdi; pImageFileName
0x14002d7d0  call    SeLocateProcessImageName_0
0x14002d7d5  mov     ebx, eax
0x14002d7d7  mov     rcx, [rsp+38h+Process]; Object
0x14002d7dc  test    rcx, rcx
0x14002d7df  jz      short loc_14002D7ED
0x14002d7e1  call    cs:__imp_ObfDereferenceObject
0x14002d7e8  nop     dword ptr [rax+rax+00h]
0x14002d7ed  mov     eax, ebx
0x14002d7ef  mov     rcx, [rsp+38h+var_10]
0x14002d7f4  xor     rcx, rsp; StackCookie
0x14002d7f7  call    __security_check_cookie
0x14002d7fc  mov     rbx, [rsp+38h+arg_10]
0x14002d801  add     rsp, 30h
0x14002d805  pop     rdi
0x14002d806  retn
```
