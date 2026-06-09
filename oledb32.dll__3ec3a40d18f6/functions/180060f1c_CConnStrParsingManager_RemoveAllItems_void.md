# CConnStrParsingManager::RemoveAllItems(void)

- ea: `0x180060f1c`
- end: `0x180060f82`
- name: `?RemoveAllItems@CConnStrParsingManager@@QEAAJXZ`
- size: `102`
- prototype: `__int64 __fastcall(CConnStrParsingManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005f664`
- `0x180060c18`

## callees

- `0x180060ef0`
- `0x180060f1c`

## import_xrefs

- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060f68`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060f68`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060f39`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060f39`

## pseudocode

```c
__int64 __fastcall CConnStrParsingManager::RemoveAllItems(CConnStrParsingManager *this)
{
  __int64 i; // rdi
  char *v3; // rbp
  CConnStrParsingCacheItem *v4; // rcx
  CConnStrParsingCacheItem *v5; // rbx

  for ( i = 0; i != 64; ++i )
  {
    v3 = (char *)this + 12 * i;
    CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(v3 + 512));
    v4 = (CConnStrParsingCacheItem *)*((_QWORD *)this + i);
    *((_QWORD *)this + i) = 0;
    if ( v4 )
    {
      do
      {
        v5 = (CConnStrParsingCacheItem *)*((_QWORD *)v4 + 5);
        CConnStrParsingCacheItem::ReleaseReference(v4);
        v4 = v5;
      }
      while ( v5 );
    }
    CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)(v3 + 512));
  }
  return 0;
}

```

## disassembly

```asm
0x180060f1c  push    rbx
0x180060f1e  push    rbp
0x180060f1f  push    rsi
0x180060f20  push    rdi
0x180060f21  sub     rsp, 28h
0x180060f25  mov     rsi, rcx
0x180060f28  xor     edi, edi
0x180060f2a  lea     rax, [rdi+rdi*2]
0x180060f2e  lea     rbp, [rsi+rax*4]
0x180060f32  lea     rcx, [rbp+200h]
0x180060f39  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x180060f3f  mov     rcx, [rsi+rdi*8]; this
0x180060f43  mov     qword ptr [rsi+rdi*8], 0
0x180060f4b  test    rcx, rcx
0x180060f4e  jz      short loc_180060F61
0x180060f50  mov     rbx, [rcx+28h]
0x180060f54  call    ?ReleaseReference@CConnStrParsingCacheItem@@QEAAJXZ; CConnStrParsingCacheItem::ReleaseReference(void)
0x180060f59  mov     rcx, rbx
0x180060f5c  test    rbx, rbx
0x180060f5f  jnz     short loc_180060F50
0x180060f61  lea     rcx, [rbp+200h]
0x180060f68  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180060f6e  inc     rdi
0x180060f71  cmp     rdi, 40h ; '@'
0x180060f75  jnz     short loc_180060F2A
0x180060f77  xor     eax, eax
0x180060f79  add     rsp, 28h
0x180060f7d  pop     rdi
0x180060f7e  pop     rsi
0x180060f7f  pop     rbp
0x180060f80  pop     rbx
0x180060f81  retn
```
