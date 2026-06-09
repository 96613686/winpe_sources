# CStream::Write(void const *,ulong,ulong *)

- ea: `0x18000df00`
- end: `0x18000df25`
- name: `?Write@CStream@@UEAAJPEBXKPEAK@Z`
- size: `37`
- prototype: `__int64 __fastcall(CStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000df00`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CStream::Write(CStream *this, const void *a2, __int64 a3, unsigned int *a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, const void *, __int64, unsigned int *))(*(_QWORD *)v4 + 32LL))(
             v4,
             a2,
             a3,
             a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000df00  sub     rsp, 38h
0x18000df04  mov     rcx, [rcx+18h]
0x18000df08  test    rcx, rcx
0x18000df0b  jz      short loc_18000DF1B
0x18000df0d  mov     rax, [rcx]
0x18000df10  mov     rax, [rax+20h]
0x18000df14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df19  jmp     short loc_18000DF20
0x18000df1b  mov     eax, 80004005h
0x18000df20  add     rsp, 38h
0x18000df24  retn
```
