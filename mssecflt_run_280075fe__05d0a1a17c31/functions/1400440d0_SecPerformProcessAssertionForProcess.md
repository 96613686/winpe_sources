# SecPerformProcessAssertionForProcess

- ea: `0x1400440d0`
- end: `0x14004413f`
- name: `SecPerformProcessAssertionForProcess`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000ac04`
- `0x140011650`
- `0x1400440d0`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400440fa`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400440fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14004411f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004411f`

## pseudocode

```c
NTSTATUS __fastcall SecPerformProcessAssertionForProcess(__int64 a1)
{
  NTSTATUS result; // eax
  PEPROCESS Process; // [rsp+20h] [rbp-18h] BYREF

  Process = 0;
  result = PsLookupProcessByProcessId(*(HANDLE *)(a1 + 32), &Process);
  if ( result >= 0 )
  {
    SecDetPerformProcessAssertionsWithContext(Process, a1, 0);
    return ObfDereferenceObject(Process);
  }
  return result;
}

```

## disassembly

```asm
0x1400440d0  push    rbx
0x1400440d2  sub     rsp, 30h
0x1400440d6  mov     rax, cs:__security_cookie
0x1400440dd  xor     rax, rsp
0x1400440e0  mov     [rsp+38h+var_10], rax
0x1400440e5  mov     rbx, rcx
0x1400440e8  mov     [rsp+38h+Process], 0
0x1400440f1  mov     rcx, [rcx+20h]; ProcessId
0x1400440f5  lea     rdx, [rsp+38h+Process]; Process
0x1400440fa  call    cs:__imp_PsLookupProcessByProcessId
0x140044101  nop     dword ptr [rax+rax+00h]
0x140044106  test    eax, eax
0x140044108  js      short loc_14004412B
0x14004410a  mov     rcx, [rsp+38h+Process]
0x14004410f  xor     r8d, r8d
0x140044112  mov     rdx, rbx
0x140044115  call    SecDetPerformProcessAssertionsWithContext
0x14004411a  mov     rcx, [rsp+38h+Process]; Object
0x14004411f  call    cs:__imp_ObfDereferenceObject
0x140044126  nop     dword ptr [rax+rax+00h]
0x14004412b  mov     rcx, [rsp+38h+var_10]
0x140044130  xor     rcx, rsp; StackCookie
0x140044133  call    __security_check_cookie
0x140044138  add     rsp, 30h
0x14004413c  pop     rbx
0x14004413d  retn
```
