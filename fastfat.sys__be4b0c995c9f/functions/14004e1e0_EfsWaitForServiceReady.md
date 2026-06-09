# EfsWaitForServiceReady

- ea: `0x14004e1e0`
- end: `0x14004e22a`
- name: `EfsWaitForServiceReady`
- size: `74`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140052604`
- `0x140053420`
- `0x140053460`
- `0x1400576c0`
- `0x1400577d4`

## callees

- `0x14004e1e0`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x14004e20b`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14004e20b`

## pseudocode

```c
NTSTATUS EfsWaitForServiceReady()
{
  NTSTATUS result; // eax

  if ( !Handle )
    return -1073741811;
  Timeout.QuadPart = -200000000;
  result = ZwWaitForSingleObject(Handle, 0, &Timeout);
  if ( result == 258 )
    return -1073741790;
  return result;
}

```

## disassembly

```asm
0x14004e1e0  sub     rsp, 28h
0x14004e1e4  mov     rcx, cs:Handle; Handle
0x14004e1eb  test    rcx, rcx
0x14004e1ee  jnz     short loc_14004E1F7
0x14004e1f0  mov     eax, 0C000000Dh
0x14004e1f5  jmp     short loc_14004E224
0x14004e1f7  lea     r8, Timeout; Timeout
0x14004e1fe  mov     qword ptr cs:Timeout, 0FFFFFFFFF4143E00h
0x14004e209  xor     edx, edx; Alertable
0x14004e20b  call    cs:__imp_ZwWaitForSingleObject
0x14004e212  nop     dword ptr [rax+rax+00h]
0x14004e217  cmp     eax, 102h
0x14004e21c  mov     ecx, 0C0000022h
0x14004e221  cmovz   eax, ecx
0x14004e224  add     rsp, 28h
0x14004e228  retn
```
