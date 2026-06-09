# ImapiComReturnObject::ImapiComReturnObject(void)

- ea: `0x180028850`
- end: `0x18002888e`
- name: `??0ImapiComReturnObject@@QEAA@XZ`
- size: `62`
- prototype: `ImapiComReturnObject *__fastcall(ImapiComReturnObject *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800287b0`
- `0x18003ae64`
- `0x18003c1a0`
- `0x18003d844`
- `0x18003d954`
- `0x18003da70`
- `0x180054944`
- `0x180054a64`
- `0x180054b74`

## callees

- `0x180028804`
- `0x180028850`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002887f`
- `KERNEL32!DeleteCriticalSection` at `0x18002887f`

## pseudocode

```c
ImapiComReturnObject *__fastcall ImapiComReturnObject::ImapiComReturnObject(ImapiComReturnObject *this)
{
  char v2; // al

  ImapiComObject::ImapiComObject(this);
  *(_QWORD *)this = &ImapiComReturnObject::`vftable';
  *((_QWORD *)this + 8) = 0;
  v2 = *((_BYTE *)this + 16);
  *((_BYTE *)this + 16) = 0;
  if ( v2 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return this;
}

```

## disassembly

```asm
0x180028850  push    rbx
0x180028852  sub     rsp, 20h
0x180028856  mov     rbx, rcx
0x180028859  call    ??0ImapiComObject@@QEAA@XZ; ImapiComObject::ImapiComObject(void)
0x18002885e  lea     rax, ??_7ImapiComReturnObject@@6B@; const ImapiComReturnObject::`vftable'
0x180028865  mov     [rbx], rax
0x180028868  mov     qword ptr [rbx+40h], 0
0x180028870  mov     al, [rbx+10h]
0x180028873  mov     byte ptr [rbx+10h], 0
0x180028877  test    al, al
0x180028879  jz      short loc_180028885
0x18002887b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18002887f  call    cs:__imp_DeleteCriticalSection
0x180028885  mov     rax, rbx
0x180028888  add     rsp, 20h
0x18002888c  pop     rbx
0x18002888d  retn
```
