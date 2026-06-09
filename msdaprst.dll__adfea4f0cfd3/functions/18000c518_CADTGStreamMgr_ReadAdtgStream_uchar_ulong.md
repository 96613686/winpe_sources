# CADTGStreamMgr::ReadAdtgStream(uchar *,ulong)

- ea: `0x18000c518`
- end: `0x18000c5f7`
- name: `?ReadAdtgStream@CADTGStreamMgr@@QEAAXPEAEK@Z`
- size: `223`
- prototype: `void __fastcall(CADTGStreamMgr *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c600`
- `0x18000c63c`
- `0x18000cbc8`
- `0x18000d084`
- `0x18000d1fc`
- `0x18000eeb0`
- `0x18000f2e0`
- `0x18000f9f8`
- `0x180010564`
- `0x180010658`
- `0x180010ee0`

## callees

- `0x18000c518`
- `0x180016584`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## pseudocode

```c
void __fastcall CADTGStreamMgr::ReadAdtgStream(CADTGStreamMgr *this, unsigned __int8 *a2, __int64 a3)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // ebx
  int v9; // [rsp+50h] [rbp+18h] BYREF

  if ( (_DWORD)a3 )
  {
    v3 = *(_QWORD *)this;
    v9 = 0;
    v4 = a3;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, int *))(*(_QWORD *)v3 + 24LL))(v3, a2, a3, &v9);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800495D8[0] )
          bidTraceW(off_1800491C8[0], 2667520, off_1800495D8[0], (unsigned int)v5, 2605);
      }
      ThrowHR(v6);
    }
    if ( v9 != v4 )
    {
      v7 = Exit(-2147467259, 0x85u);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800495D0[0] )
          bidTraceW(off_1800491C8[0], 2673664, off_1800495D0[0], (unsigned int)v7, 2611);
        ThrowHR(v8);
      }
    }
  }
}

```

## disassembly

```asm
0x18000c518  test    r8d, r8d
0x18000c51b  jz      locret_18000C5F5
0x18000c521  mov     [rsp+arg_0], rbx
0x18000c526  push    rdi
0x18000c527  sub     rsp, 30h
0x18000c52b  mov     rcx, [rcx]
0x18000c52e  lea     r9, [rsp+38h+arg_10]
0x18000c533  mov     [rsp+38h+arg_10], 0
0x18000c53b  mov     ebx, r8d
0x18000c53e  mov     rax, [rcx]
0x18000c541  mov     rax, [rax+18h]
0x18000c545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c54a  mov     edi, eax
0x18000c54c  test    eax, eax
0x18000c54e  jns     short loc_18000C590
0x18000c550  test    byte ptr cs:_bidGblFlags, 2
0x18000c557  jz      short loc_18000C588
0x18000c559  mov     rcx, cs:off_1800495D8; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c560  test    rcx, rcx
0x18000c563  jz      short loc_18000C588
0x18000c565  mov     r8, cs:off_1800495D8; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c56c  mov     r9d, eax
0x18000c56f  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000c576  mov     edx, 28B400h
0x18000c57b  mov     [rsp+38h+var_18], 0A2Dh
0x18000c583  call    _bidTraceW
0x18000c588  mov     ecx, edi; int
0x18000c58a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000c590  cmp     [rsp+38h+arg_10], ebx
0x18000c594  jz      short loc_18000C5EB
0x18000c596  mov     edx, 85h; unsigned int
0x18000c59b  mov     ecx, 80004005h; int
0x18000c5a0  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000c5a5  mov     ebx, eax
0x18000c5a7  test    eax, eax
0x18000c5a9  jns     short loc_18000C5EB
0x18000c5ab  test    byte ptr cs:_bidGblFlags, 2
0x18000c5b2  jz      short loc_18000C5E3
0x18000c5b4  mov     rcx, cs:off_1800495D0; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c5bb  test    rcx, rcx
0x18000c5be  jz      short loc_18000C5E3
0x18000c5c0  mov     r8, cs:off_1800495D0; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c5c7  mov     r9d, eax
0x18000c5ca  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000c5d1  mov     edx, 28CC00h
0x18000c5d6  mov     [rsp+38h+var_18], 0A33h
0x18000c5de  call    _bidTraceW
0x18000c5e3  mov     ecx, ebx; int
0x18000c5e5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000c5eb  mov     rbx, [rsp+38h+arg_0]
0x18000c5f0  add     rsp, 30h
0x18000c5f4  pop     rdi
0x18000c5f5  retn
```
