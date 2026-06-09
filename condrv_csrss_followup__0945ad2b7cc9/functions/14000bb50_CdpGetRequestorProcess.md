# CdpGetRequestorProcess

- ea: `0x14000bb50`
- end: `0x14000bb78`
- name: `CdpGetRequestorProcess`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b4d0`
- `0x14000b820`
- `0x14000be70`
- `0x14000c690`
- `0x14000d5c0`

## callees

- `0x14000bb50`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x14000bb5a`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000bb5a`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000bb6c`

## pseudocode

```c
PEPROCESS __fastcall CdpGetRequestorProcess(IRP *a1)
{
  if ( a1->RequestorMode == 1 )
    return IoGetRequestorProcess(a1);
  else
    return PsInitialSystemProcess;
}

```

## disassembly

```asm
0x14000bb50  sub     rsp, 28h
0x14000bb54  cmp     byte ptr [rcx+40h], 1
0x14000bb58  jnz     short loc_14000BB6C
0x14000bb5a  call    cs:__imp_IoGetRequestorProcess
0x14000bb61  nop     dword ptr [rax+rax+00h]
0x14000bb66  add     rsp, 28h
0x14000bb6a  retn
0x14000bb6c  mov     rax, cs:__imp_PsInitialSystemProcess
0x14000bb73  mov     rax, [rax]
0x14000bb76  jmp     short loc_14000BB66
```
