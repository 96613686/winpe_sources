# ShimLog::LogNewline(void)

- ea: `0x180030758`
- end: `0x180030791`
- name: `?LogNewline@ShimLog@@QEAAXXZ`
- size: `57`
- prototype: `void __fastcall(ShimLog *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009af4`
- `0x18000a59c`
- `0x18002adf4`
- `0x180030798`

## callees

- `0x180030758`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180030786`
- `KERNEL32!WriteFile` at `0x180030786`

## pseudocode

```c
void __fastcall ShimLog::LogNewline(ShimLog *this)
{
  void *v1; // rcx
  int Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp+10h] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    v1 = (void *)*((_QWORD *)this + 2);
    Buffer = 655373;
    NumberOfBytesWritten = 0;
    WriteFile(v1, &Buffer, 4u, &NumberOfBytesWritten, 0);
  }
}

```

## disassembly

```asm
0x180030758  sub     rsp, 38h
0x18003075c  xor     eax, eax
0x18003075e  cmp     [rcx+8], eax
0x180030761  jz      short loc_18003078C
0x180030763  mov     rcx, [rcx+10h]; hFile
0x180030767  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003076c  lea     r8d, [rax+4]; nNumberOfBytesToWrite
0x180030770  mov     [rsp+38h+Buffer], 0A000Dh
0x180030778  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18003077d  mov     [rsp+38h+NumberOfBytesWritten], eax
0x180030781  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180030786  call    cs:__imp_WriteFile
0x18003078c  add     rsp, 38h
0x180030790  retn
```
