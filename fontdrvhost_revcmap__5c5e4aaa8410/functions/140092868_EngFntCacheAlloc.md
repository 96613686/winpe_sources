# EngFntCacheAlloc

- ea: `0x140092868`
- end: `0x1400928b8`
- name: `EngFntCacheAlloc`
- size: `80`
- prototype: `PVOID __stdcall(ULONG FastCheckSum, ULONG ulSize)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14007eac4`
- `0x140092168`

## callees

- `0x140092868`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140092882`
- `KERNEL32!GetProcessHeap` at `0x140092882`
- `KERNEL32!HeapAlloc` at `0x140092890`
- `KERNEL32!HeapAlloc` at `0x140092890`

## pseudocode

```c
PVOID __stdcall EngFntCacheAlloc(ULONG FastCheckSum, ULONG ulSize)
{
  ULONG v2; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rax

  v2 = ulSize + 16;
  if ( ulSize + 16 < ulSize )
    return 0;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 0, v2);
  if ( !v6 )
    return 0;
  *v6 = FastCheckSum;
  v6[1] = ulSize;
  return v6 + 4;
}

```

## disassembly

```asm
0x140092868  mov     [rsp+arg_0], rbx
0x14009286d  mov     [rsp+arg_8], rsi
0x140092872  push    rdi
0x140092873  sub     rsp, 20h
0x140092877  lea     edi, [rdx+10h]
0x14009287a  mov     ebx, edx
0x14009287c  mov     esi, ecx
0x14009287e  cmp     edi, edx
0x140092880  jb      short loc_1400928A6
0x140092882  call    cs:__imp_GetProcessHeap
0x140092888  mov     r8d, edi; dwBytes
0x14009288b  xor     edx, edx; dwFlags
0x14009288d  mov     rcx, rax; hHeap
0x140092890  call    cs:__imp_HeapAlloc
0x140092896  test    rax, rax
0x140092899  jz      short loc_1400928A6
0x14009289b  mov     [rax], esi
0x14009289d  mov     [rax+4], ebx
0x1400928a0  add     rax, 10h
0x1400928a4  jmp     short loc_1400928A8
0x1400928a6  xor     eax, eax
0x1400928a8  mov     rbx, [rsp+28h+arg_0]
0x1400928ad  mov     rsi, [rsp+28h+arg_8]
0x1400928b2  add     rsp, 20h
0x1400928b6  pop     rdi
0x1400928b7  retn
```
