# DbTable::Delete(_jetSeekCriteria *,ulong,ulong)

- ea: `0x180014770`
- end: `0x180014806`
- name: `?Delete@DbTable@@QEAAJPEAU_jetSeekCriteria@@KK@Z`
- size: `150`
- prototype: `__int64 __fastcall(JET_SESID *this, struct _jetSeekCriteria *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800165c0`
- `0x18001669c`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x180014770`
- `0x18001526c`
- `0x1800153f4`

## import_xrefs

- `ESENT!JetDelete` at `0x1800147aa`
- `ESENT!JetDelete` at `0x1800147aa`

## string_xrefs

- `0x1800147cc`: `DbTable::Delete`

## pseudocode

```c
__int64 __fastcall DbTable::Delete(JET_SESID *this, struct _jetSeekCriteria *a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  JET_ERR v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  DSLogger *v10; // rax
  __int64 v11; // [rsp+20h] [rbp-18h]

  if ( !a2 )
    return 2147942487LL;
  result = DbTable::Seek((DbTable *)this, a2, a3, 0, 1u);
  if ( (int)result >= 0 && (_DWORD)result != 1 )
  {
    do
    {
      v7 = JetDelete(this[5], this[9]);
      if ( v7 < 0 )
      {
        v10 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                            v6,
                            v5,
                            v8,
                            v9);
        LODWORD(v11) = v7;
        DSLogger::LogError(v10, L"DbTable::Delete", 0x28Fu, L"JET_ERR : %d", v11);
        result = JetToHResult(v7);
        if ( (int)result < 0 )
          break;
      }
      result = DbTable::SeekNext((DbTable *)this);
      if ( (_DWORD)result == 1 )
        return 0;
    }
    while ( (int)result >= 0 );
  }
  return result;
}

```

## disassembly

```asm
0x180014770  mov     [rsp+arg_0], rbx
0x180014775  push    rdi
0x180014776  sub     rsp, 30h
0x18001477a  mov     rbx, rcx
0x18001477d  test    rdx, rdx
0x180014780  jnz     short loc_180014789
0x180014782  mov     eax, 80070057h
0x180014787  jmp     short loc_1800147FB
0x180014789  xor     r9d, r9d; int
0x18001478c  mov     dword ptr [rsp+38h+var_18], 1; unsigned int
0x180014794  call    ?Seek@DbTable@@AEAAJPEAU_jetSeekCriteria@@KHK@Z; DbTable::Seek(_jetSeekCriteria *,ulong,int,ulong)
0x180014799  test    eax, eax
0x18001479b  js      short loc_1800147FB
0x18001479d  cmp     eax, 1
0x1800147a0  jz      short loc_1800147FB
0x1800147a2  mov     rdx, [rbx+48h]; tableid
0x1800147a6  mov     rcx, [rbx+28h]; sesid
0x1800147aa  call    cs:__imp_JetDelete
0x1800147b0  mov     edi, eax
0x1800147b2  test    eax, eax
0x1800147b4  jns     short loc_1800147E6
0x1800147b6  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800147bb  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800147c2  mov     dword ptr [rsp+38h+var_18], edi
0x1800147c6  mov     r8d, 28Fh; unsigned int
0x1800147cc  lea     rdx, aDbtableDelete; "DbTable::Delete"
0x1800147d3  mov     rcx, rax; this
0x1800147d6  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800147db  mov     ecx, edi; int
0x1800147dd  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800147e2  test    eax, eax
0x1800147e4  js      short loc_1800147FB
0x1800147e6  mov     rcx, rbx; this
0x1800147e9  call    ?SeekNext@DbTable@@AEAAJXZ; DbTable::SeekNext(void)
0x1800147ee  cmp     eax, 1
0x1800147f1  jz      short loc_1800147F9
0x1800147f3  test    eax, eax
0x1800147f5  jns     short loc_1800147A2
0x1800147f7  jmp     short loc_1800147FB
0x1800147f9  xor     eax, eax
0x1800147fb  mov     rbx, [rsp+38h+arg_0]
0x180014800  add     rsp, 30h
0x180014804  pop     rdi
0x180014805  retn
```
