# HsmOsBlockPlaceholderAccessByProcessId

- ea: `0x140012b80`
- end: `0x140012be2`
- name: `HsmOsBlockPlaceholderAccessByProcessId`
- size: `98`
- prototype: `__int64 __fastcall(HANDLE ProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003a03c`

## callees

- `0x14001266c`
- `0x140012b80`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x140012b9d`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140012b9d`
- `ntoskrnl!ObfDereferenceObject` at `0x140012bc8`
- `ntoskrnl!ObfDereferenceObject` at `0x140012bc8`

## pseudocode

```c
__int64 __fastcall HsmOsBlockPlaceholderAccessByProcessId(HANDLE ProcessId, char a2)
{
  int v3; // ebx
  PEPROCESS Process; // [rsp+40h] [rbp+18h] BYREF

  Process = 0;
  v3 = PsLookupProcessByProcessId((HANDLE)(unsigned int)ProcessId, &Process);
  if ( v3 >= 0 )
    v3 = HsmOsBlockPlaceholderAccess(Process, a2);
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012b80  mov     [rsp+arg_0], rbx
0x140012b85  push    rdi
0x140012b86  sub     rsp, 20h
0x140012b8a  mov     dil, dl
0x140012b8d  mov     ecx, ecx; ProcessId
0x140012b8f  lea     rdx, [rsp+28h+Process]; Process
0x140012b94  mov     [rsp+28h+Process], 0
0x140012b9d  call    cs:__imp_PsLookupProcessByProcessId
0x140012ba4  nop     dword ptr [rax+rax+00h]
0x140012ba9  mov     ebx, eax
0x140012bab  test    eax, eax
0x140012bad  js      short loc_140012BBE
0x140012baf  mov     rcx, [rsp+28h+Process]; PROCESS
0x140012bb4  mov     dl, dil
0x140012bb7  call    HsmOsBlockPlaceholderAccess
0x140012bbc  mov     ebx, eax
0x140012bbe  mov     rcx, [rsp+28h+Process]; Object
0x140012bc3  test    rcx, rcx
0x140012bc6  jz      short loc_140012BD4
0x140012bc8  call    cs:__imp_ObfDereferenceObject
0x140012bcf  nop     dword ptr [rax+rax+00h]
0x140012bd4  mov     eax, ebx
0x140012bd6  mov     rbx, [rsp+28h+arg_0]
0x140012bdb  add     rsp, 20h
0x140012bdf  pop     rdi
0x140012be0  retn
```
