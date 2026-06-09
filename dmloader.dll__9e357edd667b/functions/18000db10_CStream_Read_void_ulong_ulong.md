# CStream::Read(void *,ulong,ulong *)

- ea: `0x18000db10`
- end: `0x18000db35`
- name: `?Read@CStream@@UEAAJPEAXKPEAK@Z`
- size: `37`
- prototype: `__int64 __fastcall(CStream *this, void *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000db10`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CStream::Read(CStream *this, void *a2, __int64 a3, unsigned int *a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, void *, __int64, unsigned int *))(*(_QWORD *)v4 + 24LL))(v4, a2, a3, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000db10  sub     rsp, 38h
0x18000db14  mov     rcx, [rcx+18h]
0x18000db18  test    rcx, rcx
0x18000db1b  jz      short loc_18000DB2B
0x18000db1d  mov     rax, [rcx]
0x18000db20  mov     rax, [rax+18h]
0x18000db24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db29  jmp     short loc_18000DB30
0x18000db2b  mov     eax, 80004005h
0x18000db30  add     rsp, 38h
0x18000db34  retn
```
