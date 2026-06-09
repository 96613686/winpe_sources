# operator new(unsigned __int64)

- ea: `0x140003978`
- end: `0x1400039b6`
- name: `??2@YAPEAX_K@Z`
- size: `62`
- prototype: `void *__fastcall(SIZE_T dwBytes)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022d0`
- `0x140002790`
- `0x140002fe0`
- `0x140003a10`
- `0x140003cd0`
- `0x140004108`
- `0x140005e98`
- `0x14000747c`
- `0x140007bcc`
- `0x140007e20`
- `0x140007ed0`

## callees

- `0x140003978`
- `0x14000cf74`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140003981`
- `KERNEL32!GetProcessHeap` at `0x140003981`
- `KERNEL32!HeapAlloc` at `0x140003998`
- `KERNEL32!HeapAlloc` at `0x140003998`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rax
  LPVOID result; // rax

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, dwBytes);
  if ( !result )
    std::_Xbad_alloc();
  return result;
}

```

## disassembly

```asm
0x140003978  push    rbx
0x14000397a  sub     rsp, 20h
0x14000397e  mov     rbx, rcx
0x140003981  call    cs:__imp_GetProcessHeap
0x140003988  nop     dword ptr [rax+rax+00h]
0x14000398d  mov     r8, rbx; dwBytes
0x140003990  mov     edx, 8; dwFlags
0x140003995  mov     rcx, rax; hHeap
0x140003998  call    cs:__imp_HeapAlloc
0x14000399f  nop     dword ptr [rax+rax+00h]
0x1400039a4  test    rax, rax
0x1400039a7  jz      short loc_1400039B0
0x1400039a9  add     rsp, 20h
0x1400039ad  pop     rbx
0x1400039ae  retn
0x1400039b0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
