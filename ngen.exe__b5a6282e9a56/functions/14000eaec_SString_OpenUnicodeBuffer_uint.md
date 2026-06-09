# SString::OpenUnicodeBuffer(uint)

- ea: `0x14000eaec`
- end: `0x14000eb5a`
- name: `?OpenUnicodeBuffer@SString@@QEAAPEAGI@Z`
- size: `110`
- prototype: `unsigned __int16 *__fastcall(SString *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011b6c`

## callees

- `0x14000c56c`
- `0x14000eaec`
- `0x1400102cc`

## pseudocode

```c
unsigned __int16 *__fastcall SString::OpenUnicodeBuffer(SString *this)
{
  int v2; // edx
  unsigned int v3; // edi

  SString::Resize(this, 260, 4, 0);
  v2 = *((_DWORD *)this + 2);
  v3 = 261 << ((v2 & 1) == 0);
  if ( v3 > *((_DWORD *)this + 1) )
  {
    SBuffer::ReallocateBuffer(this, v3, 1);
    v2 = *((_DWORD *)this + 2);
  }
  *(_DWORD *)this = v3;
  if ( (v2 & 0x10) != 0 )
    SBuffer::ReallocateBuffer(this, *((unsigned int *)this + 1), 1);
  return (unsigned __int16 *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x14000eaec  mov     [rsp+arg_0], rbx
0x14000eaf1  push    rdi
0x14000eaf2  sub     rsp, 20h
0x14000eaf6  xor     r9d, r9d
0x14000eaf9  mov     edx, 104h
0x14000eafe  mov     rbx, rcx
0x14000eb01  lea     r8d, [r9+4]
0x14000eb05  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000eb0a  mov     edx, [rbx+8]
0x14000eb0d  mov     edi, 105h
0x14000eb12  mov     ecx, edx
0x14000eb14  not     ecx
0x14000eb16  and     ecx, 1
0x14000eb19  shl     edi, cl
0x14000eb1b  cmp     edi, [rbx+4]
0x14000eb1e  jbe     short loc_14000EB33
0x14000eb20  mov     r8d, 1
0x14000eb26  mov     edx, edi
0x14000eb28  mov     rcx, rbx
0x14000eb2b  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x14000eb30  mov     edx, [rbx+8]
0x14000eb33  mov     [rbx], edi
0x14000eb35  test    dl, 10h
0x14000eb38  jz      short loc_14000EB4B
0x14000eb3a  mov     edx, [rbx+4]
0x14000eb3d  mov     r8d, 1
0x14000eb43  mov     rcx, rbx
0x14000eb46  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x14000eb4b  mov     rax, [rbx+10h]
0x14000eb4f  mov     rbx, [rsp+28h+arg_0]
0x14000eb54  add     rsp, 20h
0x14000eb58  pop     rdi
0x14000eb59  retn
```
