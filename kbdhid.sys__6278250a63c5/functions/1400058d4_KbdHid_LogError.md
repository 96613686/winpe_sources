# KbdHid_LogError

- ea: `0x1400058d4`
- end: `0x14000591f`
- name: `KbdHid_LogError`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001300`

## callees

- `0x1400058d4`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400058da`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400058da`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000590d`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000590d`

## pseudocode

```c
void __fastcall KbdHid_LogError(void *a1)
{
  _OWORD *ErrorLogEntry; // rax

  ErrorLogEntry = IoAllocateErrorLogEntry(a1, 0x30u);
  if ( ErrorLogEntry )
  {
    *ErrorLogEntry = 0;
    ErrorLogEntry[1] = 0;
    ErrorLogEntry[2] = 0;
    *((_DWORD *)ErrorLogEntry + 3) = -2147155967;
    *((_DWORD *)ErrorLogEntry + 5) = -2147155967;
    *((_WORD *)ErrorLogEntry + 2) = 0;
    IoWriteErrorLogEntry(ErrorLogEntry);
  }
}

```

## disassembly

```asm
0x1400058d4  sub     rsp, 28h
0x1400058d8  mov     dl, 30h ; '0'; EntrySize
0x1400058da  call    cs:__imp_IoAllocateErrorLogEntry
0x1400058e1  nop     dword ptr [rax+rax+00h]
0x1400058e6  test    rax, rax
0x1400058e9  jz      short loc_140005919
0x1400058eb  xorps   xmm0, xmm0
0x1400058ee  mov     ecx, 80050001h
0x1400058f3  movups  xmmword ptr [rax], xmm0
0x1400058f6  movups  xmmword ptr [rax+10h], xmm0
0x1400058fa  movups  xmmword ptr [rax+20h], xmm0
0x1400058fe  mov     [rax+0Ch], ecx
0x140005901  mov     [rax+14h], ecx
0x140005904  xor     ecx, ecx
0x140005906  mov     [rax+4], cx
0x14000590a  mov     rcx, rax; ElEntry
0x14000590d  call    cs:__imp_IoWriteErrorLogEntry
0x140005914  nop     dword ptr [rax+rax+00h]
0x140005919  add     rsp, 28h
0x14000591d  retn
```
