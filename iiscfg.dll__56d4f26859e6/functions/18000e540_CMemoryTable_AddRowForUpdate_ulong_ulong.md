# CMemoryTable::AddRowForUpdate(ulong,ulong *)

- ea: `0x18000e540`
- end: `0x18000e5be`
- name: `?AddRowForUpdate@CMemoryTable@@UEAAJKPEAK@Z`
- size: `126`
- prototype: `int(CMemoryTable *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000e540`
- `0x18000e730`
- `0x18000ecb8`
- `0x18000f6bc`

## pseudocode

```c
__int64 __fastcall CMemoryTable::AddRowForUpdate(CMemoryTable *this, unsigned int a2, unsigned int *a3)
{
  CMemoryTable *v3; // rbx
  __int64 result; // rax
  unsigned int v7; // r10d
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  v3 = (CMemoryTable *)((char *)this - 8);
  if ( (*((_BYTE *)this + 24) & 2) == 0 && (*((_BYTE *)this + 84) & 2) == 0 )
    return 2147500033LL;
  result = 0;
  if ( (*((_BYTE *)this + 84) & 2) == 0 )
  {
    result = CMemoryTable::GetRowFromIndex((CMemoryTable *)((char *)this - 8), 0, a2, &v8);
    if ( (int)result >= 0 )
    {
      result = CMemoryTable::AddWriteRow(v3, v7, a3);
      if ( (int)result >= 0 )
        return CMemoryTable::CopyWriteRowFromReadRow(v3, a2, *a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e540  mov     [rsp+arg_8], rbx
0x18000e545  mov     [rsp+arg_10], rsi
0x18000e54a  push    rdi
0x18000e54b  sub     rsp, 20h
0x18000e54f  lea     rbx, [rcx-8]
0x18000e553  mov     r10d, 2
0x18000e559  mov     rdi, r8
0x18000e55c  mov     esi, edx
0x18000e55e  test    [rbx+20h], r10b
0x18000e562  jnz     short loc_18000E571
0x18000e564  test    [rcx+54h], r10b
0x18000e568  jnz     short loc_18000E571
0x18000e56a  mov     eax, 80004001h
0x18000e56f  jmp     short loc_18000E5AE
0x18000e571  xor     eax, eax
0x18000e573  test    [rcx+54h], r10b
0x18000e577  jnz     short loc_18000E5AE
0x18000e579  lea     r9, [rsp+28h+arg_0]; void **
0x18000e57e  mov     r8d, esi; unsigned int
0x18000e581  xor     edx, edx; unsigned int
0x18000e583  mov     rcx, rbx; this
0x18000e586  call    ?GetRowFromIndex@CMemoryTable@@AEAAJKKPEAPEAX@Z; CMemoryTable::GetRowFromIndex(ulong,ulong,void * *)
0x18000e58b  test    eax, eax
0x18000e58d  js      short loc_18000E5AE
0x18000e58f  mov     r8, rdi; unsigned int *
0x18000e592  mov     edx, r10d; unsigned int
0x18000e595  mov     rcx, rbx; this
0x18000e598  call    ?AddWriteRow@CMemoryTable@@AEAAJKPEAK@Z; CMemoryTable::AddWriteRow(ulong,ulong *)
0x18000e59d  test    eax, eax
0x18000e59f  js      short loc_18000E5AE
0x18000e5a1  mov     r8d, [rdi]; unsigned int
0x18000e5a4  mov     edx, esi; unsigned int
0x18000e5a6  mov     rcx, rbx; this
0x18000e5a9  call    ?CopyWriteRowFromReadRow@CMemoryTable@@AEAAJKK@Z; CMemoryTable::CopyWriteRowFromReadRow(ulong,ulong)
0x18000e5ae  mov     rbx, [rsp+28h+arg_8]
0x18000e5b3  mov     rsi, [rsp+28h+arg_10]
0x18000e5b8  add     rsp, 20h
0x18000e5bc  pop     rdi
0x18000e5bd  retn
```
