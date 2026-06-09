# DfscRevert

- ea: `0x140017294`
- end: `0x1400172e4`
- name: `DfscRevert`
- size: `80`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140014520`
- `0x140014810`

## callees

- `0x140017294`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400172d2`
- `ntoskrnl!ZwClose` at `0x1400172d2`
- `ntoskrnl!ZwSetInformationThread` at `0x1400172bc`
- `ntoskrnl!ZwSetInformationThread` at `0x1400172bc`

## pseudocode

```c
NTSTATUS DfscRevert()
{
  NTSTATUS result; // eax
  HANDLE ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  ThreadInformation = 0;
  result = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( ThreadInformation )
    return ZwClose(ThreadInformation);
  return result;
}

```

## disassembly

```asm
0x140017294  mov     [rsp+ThreadInformation], rcx
0x140017299  sub     rsp, 28h
0x14001729d  mov     r9d, 8; ThreadInformationLength
0x1400172a3  mov     [rsp+28h+ThreadInformation], 0
0x1400172ac  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1400172b1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400172b8  lea     edx, [r9-3]; ThreadInformationClass
0x1400172bc  call    cs:__imp_ZwSetInformationThread
0x1400172c3  nop     dword ptr [rax+rax+00h]
0x1400172c8  mov     rcx, [rsp+28h+ThreadInformation]; Handle
0x1400172cd  test    rcx, rcx
0x1400172d0  jz      short loc_1400172DE
0x1400172d2  call    cs:__imp_ZwClose
0x1400172d9  nop     dword ptr [rax+rax+00h]
0x1400172de  add     rsp, 28h
0x1400172e2  retn
```
