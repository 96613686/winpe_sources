# CThreadErrorMode::SetThreadErrorMode(ulong)

- ea: `0x180010160`
- end: `0x180010184`
- name: `?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z`
- size: `36`
- prototype: `__int64 __fastcall(PULONG OldMode, ULONG NewMode)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090a4`
- `0x18000d9bc`
- `0x18000ea80`
- `0x180017eac`
- `0x180018130`
- `0x18001860c`
- `0x18001ce8c`

## callees

- `0x180010160`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180010170`
- `ntdll!RtlSetThreadErrorMode` at `0x180010170`

## pseudocode

```c
NTSTATUS __fastcall CThreadErrorMode::SetThreadErrorMode(PULONG OldMode, ULONG NewMode)
{
  NTSTATUS result; // eax

  result = RtlSetThreadErrorMode(NewMode, OldMode);
  if ( result >= 0 )
    *((_BYTE *)OldMode + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x180010160  push    rbx
0x180010162  sub     rsp, 20h
0x180010166  mov     eax, edx
0x180010168  mov     rbx, rcx
0x18001016b  mov     rdx, rcx; OldMode
0x18001016e  mov     ecx, eax; NewMode
0x180010170  call    cs:__imp_RtlSetThreadErrorMode
0x180010176  test    eax, eax
0x180010178  js      short loc_18001017E
0x18001017a  mov     byte ptr [rbx+4], 1
0x18001017e  add     rsp, 20h
0x180010182  pop     rbx
0x180010183  retn
```
