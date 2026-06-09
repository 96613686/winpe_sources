# Memory::HeapAllocator::NoThrowAllocZero(unsigned __int64)

- ea: `0x180023bd0`
- end: `0x180023c3b`
- name: `?NoThrowAllocZero@HeapAllocator@Memory@@QEAAPEAD_K@Z`
- size: `107`
- prototype: `char *__fastcall(Memory::HeapAllocator *__hidden this, unsigned __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800252a0`
- `0x18002570c`
- `0x1800266c8`
- `0x1800780d4`
- `0x1800793e0`
- `0x180256680`
- `0x180266ff4`
- `0x18031eae4`
- `0x18032a924`
- `0x18036cc8c`
- `0x1803cbdb8`
- `0x180489460`

## callees

- `0x180023bd0`
- `0x1805a9c5a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023bf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023bf6`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180023c2a`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180023c2a`

## pseudocode

```c
char *__fastcall Memory::HeapAllocator::NoThrowAllocZero(HANDLE *this, SIZE_T a2)
{
  HANDLE v3; // rax
  void *v4; // rax
  void *v5; // rbx

  v3 = *this;
  if ( !*this )
  {
    v3 = HeapCreate(0, 0, 0);
    *this = v3;
  }
  v4 = HeapAlloc(v3, 0, a2);
  v5 = v4;
  if ( v4 )
    memset_0(v4, 0, a2);
  return (char *)v5;
}

```

## disassembly

```asm
0x180023bd0  mov     [rsp+dwBytes], rdx
0x180023bd5  mov     [rsp+arg_0], rcx
0x180023bda  push    rbx
0x180023bdb  sub     rsp, 20h
0x180023bdf  mov     rbx, [rsp+28h+arg_0]
0x180023be4  mov     rax, [rbx]
0x180023be7  test    rax, rax
0x180023bea  jz      short loc_180023C23
0x180023bec  mov     r8, [rsp+28h+dwBytes]; dwBytes
0x180023bf1  xor     edx, edx; dwFlags
0x180023bf3  mov     rcx, rax; hHeap
0x180023bf6  call    cs:__imp_HeapAlloc
0x180023bfd  nop     dword ptr [rax+rax+00h]
0x180023c02  mov     rbx, rax
0x180023c05  test    rax, rax
0x180023c08  jz      short loc_180023C19
0x180023c0a  mov     r8, [rsp+28h+dwBytes]; Size
0x180023c0f  xor     edx, edx; Val
0x180023c11  mov     rcx, rax; void *
0x180023c14  call    memset_0
0x180023c19  mov     rax, rbx
0x180023c1c  add     rsp, 20h
0x180023c20  pop     rbx
0x180023c21  retn
0x180023c23  xor     r8d, r8d; dwMaximumSize
0x180023c26  xor     edx, edx; dwInitialSize
0x180023c28  xor     ecx, ecx; flOptions
0x180023c2a  call    cs:__imp_HeapCreate
0x180023c31  nop     dword ptr [rax+rax+00h]
0x180023c36  mov     [rbx], rax
0x180023c39  jmp     short loc_180023BEC
```
