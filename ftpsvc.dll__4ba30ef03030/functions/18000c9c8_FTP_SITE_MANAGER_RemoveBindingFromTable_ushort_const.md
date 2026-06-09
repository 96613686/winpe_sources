# FTP_SITE_MANAGER::RemoveBindingFromTable(ushort const *)

- ea: `0x18000c9c8`
- end: `0x18000ca8a`
- name: `?RemoveBindingFromTable@FTP_SITE_MANAGER@@QEAAXPEBG@Z`
- size: `194`
- prototype: `void __fastcall(FTP_SITE_MANAGER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000aab0`

## callees

- `0x180001250`
- `0x18000c9c8`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca2f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca2f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca3f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca3f`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000ca6c`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000ca6c`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000ca22`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000ca22`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ca0c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ca0c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ca63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ca63`

## pseudocode

```c
void __fastcall FTP_SITE_MANAGER::RemoveBindingFromTable(FTP_SITE_MANAGER *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  char *v3; // rdi
  volatile signed __int32 *v4; // rbx
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  if ( (unsigned int)v2 > 1 && a2[(unsigned int)v2 - 1] != 58 )
    --*((_DWORD *)this + 41);
  v3 = (char *)this + 88;
  Block = 0;
  CLKRHashTable::FindKey((char *)this + 88, a2, &Block);
  v4 = (volatile signed __int32 *)Block;
  if ( Block )
  {
    CLKRHashTable::DeleteRecord(v3, Block);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v4 + 2));
    *((_QWORD *)v4 + 25) = 0;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v4 + 2));
    if ( _InterlockedExchangeAdd(v4 + 1, 0xFFFFFFFF) == 1 )
    {
      *v4 = 1684173926;
      *((_QWORD *)v4 + 25) = 0;
      STRU::~STRU((void *)(v4 + 4));
      CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)(v4 + 2));
      operator delete((void *)v4);
    }
  }
}

```

## disassembly

```asm
0x18000c9c8  mov     [rsp+arg_8], rbx
0x18000c9cd  mov     [rsp+arg_10], rsi
0x18000c9d2  push    rdi
0x18000c9d3  sub     rsp, 20h
0x18000c9d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c9db  xor     esi, esi
0x18000c9dd  inc     rax
0x18000c9e0  cmp     [rdx+rax*2], si
0x18000c9e4  jnz     short loc_18000C9DD
0x18000c9e6  cmp     eax, 1
0x18000c9e9  jbe     short loc_18000C9FB
0x18000c9eb  mov     eax, eax
0x18000c9ed  cmp     word ptr [rdx+rax*2-2], 3Ah ; ':'
0x18000c9f3  jz      short loc_18000C9FB
0x18000c9f5  dec     dword ptr [rcx+0A4h]
0x18000c9fb  lea     rdi, [rcx+58h]
0x18000c9ff  mov     [rsp+28h+Block], rsi
0x18000ca04  mov     rcx, rdi
0x18000ca07  lea     r8, [rsp+28h+Block]
0x18000ca0c  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000ca12  mov     rbx, [rsp+28h+Block]
0x18000ca17  test    rbx, rbx
0x18000ca1a  jz      short loc_18000CA7A
0x18000ca1c  mov     rdx, rbx
0x18000ca1f  mov     rcx, rdi
0x18000ca22  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18000ca28  lea     rdi, [rbx+8]
0x18000ca2c  mov     rcx, rdi
0x18000ca2f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ca35  mov     rcx, rdi
0x18000ca38  mov     [rbx+0C8h], rsi
0x18000ca3f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ca45  or      eax, 0FFFFFFFFh
0x18000ca48  lock xadd [rbx+4], eax
0x18000ca4d  cmp     eax, 1
0x18000ca50  jnz     short loc_18000CA7A
0x18000ca52  lea     rcx, [rbx+10h]
0x18000ca56  mov     dword ptr [rbx], 64627466h
0x18000ca5c  mov     [rbx+0C8h], rsi
0x18000ca63  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ca69  mov     rcx, rdi
0x18000ca6c  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000ca72  mov     rcx, rbx; Block
0x18000ca75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ca7a  mov     rbx, [rsp+28h+arg_8]
0x18000ca7f  mov     rsi, [rsp+28h+arg_10]
0x18000ca84  add     rsp, 20h
0x18000ca88  pop     rdi
0x18000ca89  retn
```
