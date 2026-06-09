# FltGetRequestorProcessId

- ea: `0x180015c90`
- end: `0x180015cd7`
- name: `FltGetRequestorProcessId`
- size: `71`
- prototype: `ULONG __stdcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180015c90`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x180015cc7`
- `ntoskrnl!IoGetCurrentProcess` at `0x180015cc7`
- `ntoskrnl!IoGetRequestorProcess` at `0x180015ca1`
- `ntoskrnl!IoGetRequestorProcess` at `0x180015ca1`
- `ntoskrnl!PsGetProcessId` at `0x180015cb5`
- `ntoskrnl!PsGetProcessId` at `0x180015cb5`

## pseudocode

```c
ULONG __stdcall FltGetRequestorProcessId(PFLT_CALLBACK_DATA CallbackData)
{
  struct _KPROCESS *RequestorProcess; // rax

  if ( (CallbackData->Flags & 1) != 0 )
    RequestorProcess = IoGetRequestorProcess(*(PIRP *)&CallbackData[-3].RequestorMode);
  else
    RequestorProcess = IoGetCurrentProcess();
  if ( RequestorProcess )
    LODWORD(RequestorProcess) = (unsigned int)PsGetProcessId(RequestorProcess);
  return (unsigned int)RequestorProcess;
}

```

## disassembly

```asm
0x180015c90  sub     rsp, 28h
0x180015c94  mov     eax, [rcx]
0x180015c96  test    al, 1
0x180015c98  jz      short loc_180015CC7
0x180015c9a  mov     rcx, [rcx-0B8h]; Irp
0x180015ca1  call    cs:__imp_IoGetRequestorProcess
0x180015ca8  nop     dword ptr [rax+rax+00h]
0x180015cad  test    rax, rax
0x180015cb0  jz      short loc_180015CD5
0x180015cb2  mov     rcx, rax; Process
0x180015cb5  call    cs:__imp_PsGetProcessId
0x180015cbc  nop     dword ptr [rax+rax+00h]
0x180015cc1  add     rsp, 28h
0x180015cc5  retn
0x180015cc7  call    cs:__imp_IoGetCurrentProcess
0x180015cce  nop     dword ptr [rax+rax+00h]
0x180015cd3  jmp     short loc_180015CAD
0x180015cd5  jmp     short loc_180015CC1
```
