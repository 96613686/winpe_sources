# CMMFAllocator::ReadPingPage(ulong)

- ea: `0x1400106f4`
- end: `0x140010777`
- name: `?ReadPingPage@CMMFAllocator@@AEBAJK@Z`
- size: `131`
- prototype: `__int64 __fastcall(CMMFAllocator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140010984`

## callees

- `0x1400106f4`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x140010750`
- `ntoskrnl!ZwReadFile` at `0x140010750`

## pseudocode

```c
NTSTATUS __fastcall CMMFAllocator::ReadPingPage(CMMFAllocator *this, unsigned int a2)
{
  _DWORD *v2; // rax
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK v4; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v5; // [rsp+70h] [rbp+8h] BYREF

  v5.QuadPart = a2;
  v2 = (_DWORD *)*((_QWORD *)this + 16);
  v4 = 0;
  *v2 = 0;
  result = ZwReadFile(*((HANDLE *)this + 17), 0, 0, 0, &v4, *((PVOID *)this + 16), 0x1000u, &v5, 0);
  if ( result >= 0 && v4.Information != 4096 )
    return -1073741596;
  return result;
}

```

## disassembly

```asm
0x1400106f4  mov     r11, rsp
0x1400106f7  sub     rsp, 68h
0x1400106fb  mov     qword ptr [r11-28h], 0
0x140010703  xorps   xmm0, xmm0
0x140010706  mov     eax, edx
0x140010708  xor     r9d, r9d; ApcContext
0x14001070b  mov     [r11+8], rax
0x14001070f  xor     r8d, r8d; ApcRoutine
0x140010712  mov     rax, [rcx+80h]
0x140010719  xor     edx, edx; Event
0x14001071b  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140010720  mov     dword ptr [rax], 0
0x140010726  lea     rax, [r11+8]
0x14001072a  mov     [r11-30h], rax
0x14001072e  mov     rax, [rcx+80h]
0x140010735  mov     rcx, [rcx+88h]; FileHandle
0x14001073c  mov     [rsp+68h+Length], 1000h; Length
0x140010744  mov     [r11-40h], rax
0x140010748  lea     rax, [r11-18h]
0x14001074c  mov     [r11-48h], rax
0x140010750  call    cs:__imp_ZwReadFile
0x140010757  nop     dword ptr [rax+rax+00h]
0x14001075c  test    eax, eax
0x14001075e  js      short loc_140010771
0x140010760  cmp     [rsp+68h+var_18.Information], 1000h
0x140010769  mov     ecx, 0C00000E4h
0x14001076e  cmovnz  eax, ecx
0x140010771  add     rsp, 68h
0x140010775  retn
```
