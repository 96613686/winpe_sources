# DbTable::SeekNext(void)

- ea: `0x1800153f4`
- end: `0x180015460`
- name: `?SeekNext@DbTable@@AEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(DbTable *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180014770`
- `0x180014884`
- `0x1800151c4`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x1800153f4`

## import_xrefs

- `ESENT!JetMove` at `0x180015410`
- `ESENT!JetMove` at `0x180015410`

## pseudocode

```c
__int64 __fastcall DbTable::SeekNext(DbTable *this)
{
  unsigned int v1; // ebx
  JET_ERR v2; // eax
  __int64 v3; // rcx
  int v4; // edi
  int *v5; // rax
  int v7; // [rsp+20h] [rbp-18h]

  v1 = 1;
  v2 = JetMove(*((_QWORD *)this + 5), *((_QWORD *)this + 9), 1, 0);
  v4 = v2;
  if ( v2 != -1603 )
  {
    v1 = 0;
    if ( v2 < 0 )
    {
      v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v3);
      v7 = v4;
      DSLogger::LogError((DSLogger *)v5, L"DbTable::SeekNext", 869, L"JET_ERR : %d", v7);
      return (unsigned int)JetToHResult(v4);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800153f4  mov     [rsp+arg_0], rbx
0x1800153f9  push    rdi
0x1800153fa  sub     rsp, 30h
0x1800153fe  mov     rdx, [rcx+48h]; tableid
0x180015402  xor     r9d, r9d; grbit
0x180015405  mov     rcx, [rcx+28h]; sesid
0x180015409  lea     ebx, [r9+1]
0x18001540d  mov     r8d, ebx; cRow
0x180015410  call    cs:__imp_JetMove
0x180015416  mov     edi, eax
0x180015418  cmp     eax, 0FFFFF9BDh
0x18001541d  jz      short loc_180015453
0x18001541f  xor     ebx, ebx
0x180015421  test    eax, eax
0x180015423  jns     short loc_180015453
0x180015425  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001542a  lea     r9, aJetErrD; "JET_ERR : %d"
0x180015431  mov     [rsp+38h+var_18], edi
0x180015435  mov     r8d, 365h; unsigned int
0x18001543b  lea     rdx, aDbtableSeeknex; "DbTable::SeekNext"
0x180015442  mov     rcx, rax; this
0x180015445  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001544a  mov     ecx, edi; int
0x18001544c  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015451  mov     ebx, eax
0x180015453  mov     eax, ebx
0x180015455  mov     rbx, [rsp+38h+arg_0]
0x18001545a  add     rsp, 30h
0x18001545e  pop     rdi
0x18001545f  retn
```
