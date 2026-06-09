# SharedMemory::open(ushort const *,ulong)

- ea: `0x18002d598`
- end: `0x18002d618`
- name: `?open@SharedMemory@@QEAA_NPEBGK@Z`
- size: `128`
- prototype: `bool __fastcall(SharedMemory *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024c00`

## callees

- `0x18002b4a8`
- `0x18002d4ec`
- `0x18002d598`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18002d5eb`
- `KERNEL32!MapViewOfFile` at `0x18002d5eb`
- `KERNEL32!CloseHandle` at `0x18002d5fd`
- `KERNEL32!CloseHandle` at `0x18002d5fd`

## pseudocode

```c
bool __fastcall SharedMemory::open(SharedMemory *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rcx
  unsigned int v5; // eax
  HANDLE SharedFileMapping; // rax
  LPVOID v7; // rax

  SharedMemory::close(this);
  v3 = (const unsigned __int16 *)*((unsigned int *)this + 4);
  if ( (unsigned int)v3 >= 0xFFFC0000 )
    return 0;
  v5 = ((int)v3 + 0x3FFFF) / (unsigned int)v3;
  *((_DWORD *)this + 5) = v5;
  SharedFileMapping = CreateSharedFileMapping(v3, (unsigned int)v3 * v5);
  *(_QWORD *)this = SharedFileMapping;
  if ( SharedFileMapping )
  {
    v7 = MapViewOfFile(SharedFileMapping, 2u, 0, 0, 0);
    *((_QWORD *)this + 1) = v7;
    if ( !v7 )
    {
      CloseHandle(*(HANDLE *)this);
      *(_QWORD *)this = 0;
    }
  }
  return *((_QWORD *)this + 1) != 0;
}

```

## disassembly

```asm
0x18002d598  push    rbx
0x18002d59a  sub     rsp, 30h
0x18002d59e  mov     rbx, rcx
0x18002d5a1  call    ?close@SharedMemory@@QEAAXXZ; SharedMemory::close(void)
0x18002d5a6  mov     ecx, [rbx+10h]; unsigned __int16 *
0x18002d5a9  lea     eax, [rcx+40000h]
0x18002d5af  cmp     eax, 40000h
0x18002d5b4  jnb     short loc_18002D5BA
0x18002d5b6  xor     al, al
0x18002d5b8  jmp     short loc_18002D612
0x18002d5ba  dec     eax
0x18002d5bc  xor     edx, edx
0x18002d5be  div     ecx
0x18002d5c0  mov     [rbx+14h], eax
0x18002d5c3  imul    eax, ecx
0x18002d5c6  mov     edx, eax; unsigned int
0x18002d5c8  call    ?CreateSharedFileMapping@@YAPEAXPEBGK@Z; CreateSharedFileMapping(ushort const *,ulong)
0x18002d5cd  mov     [rbx], rax
0x18002d5d0  test    rax, rax
0x18002d5d3  jz      short loc_18002D60A
0x18002d5d5  xor     r9d, r9d; dwFileOffsetLow
0x18002d5d8  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18002d5e1  xor     r8d, r8d; dwFileOffsetHigh
0x18002d5e4  mov     rcx, rax; hFileMappingObject
0x18002d5e7  lea     edx, [r9+2]; dwDesiredAccess
0x18002d5eb  call    cs:__imp_MapViewOfFile
0x18002d5f1  mov     [rbx+8], rax
0x18002d5f5  test    rax, rax
0x18002d5f8  jnz     short loc_18002D60A
0x18002d5fa  mov     rcx, [rbx]; hObject
0x18002d5fd  call    cs:__imp_CloseHandle
0x18002d603  mov     qword ptr [rbx], 0
0x18002d60a  cmp     qword ptr [rbx+8], 0
0x18002d60f  setnz   al
0x18002d612  add     rsp, 30h
0x18002d616  pop     rbx
0x18002d617  retn
```
