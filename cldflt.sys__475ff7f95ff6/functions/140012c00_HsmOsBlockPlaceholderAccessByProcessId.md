# HsmOsBlockPlaceholderAccessByProcessId

- ea: `0x140012c00`
- end: `0x140012c62`
- name: `HsmOsBlockPlaceholderAccessByProcessId`
- size: `98`
- prototype: `__int64 __fastcall(HANDLE ProcessId, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003a05c`

## callees

- `0x1400126ec`
- `0x140012c00`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x140012c1d`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140012c1d`
- `ntoskrnl!ObfDereferenceObject` at `0x140012c48`
- `ntoskrnl!ObfDereferenceObject` at `0x140012c48`

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
0x140012c00  mov     [rsp+arg_0], rbx
0x140012c05  push    rdi
0x140012c06  sub     rsp, 20h
0x140012c0a  mov     dil, dl
0x140012c0d  mov     ecx, ecx; ProcessId
0x140012c0f  lea     rdx, [rsp+28h+Process]; Process
0x140012c14  mov     [rsp+28h+Process], 0
0x140012c1d  call    cs:__imp_PsLookupProcessByProcessId
0x140012c24  nop     dword ptr [rax+rax+00h]
0x140012c29  mov     ebx, eax
0x140012c2b  test    eax, eax
0x140012c2d  js      short loc_140012C3E
0x140012c2f  mov     rcx, [rsp+28h+Process]; PROCESS
0x140012c34  mov     dl, dil
0x140012c37  call    HsmOsBlockPlaceholderAccess
0x140012c3c  mov     ebx, eax
0x140012c3e  mov     rcx, [rsp+28h+Process]; Object
0x140012c43  test    rcx, rcx
0x140012c46  jz      short loc_140012C54
0x140012c48  call    cs:__imp_ObfDereferenceObject
0x140012c4f  nop     dword ptr [rax+rax+00h]
0x140012c54  mov     eax, ebx
0x140012c56  mov     rbx, [rsp+28h+arg_0]
0x140012c5b  add     rsp, 20h
0x140012c5f  pop     rdi
0x140012c60  retn
```
