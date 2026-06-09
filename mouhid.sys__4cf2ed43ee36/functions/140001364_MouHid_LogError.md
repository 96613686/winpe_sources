# MouHid_LogError

- ea: `0x140001364`
- end: `0x1400013af`
- name: `MouHid_LogError`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000baf0`

## callees

- `0x140001364`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000136e`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000136e`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000139c`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000139c`

## pseudocode

```c
void __fastcall MouHid_LogError(void *a1, int a2)
{
  _OWORD *ErrorLogEntry; // rax

  ErrorLogEntry = IoAllocateErrorLogEntry(a1, 0x30u);
  if ( ErrorLogEntry )
  {
    *ErrorLogEntry = 0;
    ErrorLogEntry[1] = 0;
    ErrorLogEntry[2] = 0;
    *((_WORD *)ErrorLogEntry + 2) = 0;
    *((_DWORD *)ErrorLogEntry + 3) = a2;
    *((_DWORD *)ErrorLogEntry + 5) = a2;
    IoWriteErrorLogEntry(ErrorLogEntry);
  }
}

```

## disassembly

```asm
0x140001364  push    rbx
0x140001366  sub     rsp, 20h
0x14000136a  mov     ebx, edx
0x14000136c  mov     dl, 30h ; '0'; EntrySize
0x14000136e  call    cs:__imp_IoAllocateErrorLogEntry
0x140001375  nop     dword ptr [rax+rax+00h]
0x14000137a  test    rax, rax
0x14000137d  jz      short loc_1400013A8
0x14000137f  xorps   xmm0, xmm0
0x140001382  xor     ecx, ecx
0x140001384  movups  xmmword ptr [rax], xmm0
0x140001387  movups  xmmword ptr [rax+10h], xmm0
0x14000138b  movups  xmmword ptr [rax+20h], xmm0
0x14000138f  mov     [rax+4], cx
0x140001393  mov     rcx, rax; ElEntry
0x140001396  mov     [rax+0Ch], ebx
0x140001399  mov     [rax+14h], ebx
0x14000139c  call    cs:__imp_IoWriteErrorLogEntry
0x1400013a3  nop     dword ptr [rax+rax+00h]
0x1400013a8  add     rsp, 20h
0x1400013ac  pop     rbx
0x1400013ad  retn
```
