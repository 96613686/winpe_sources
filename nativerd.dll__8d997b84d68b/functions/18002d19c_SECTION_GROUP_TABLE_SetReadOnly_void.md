# SECTION_GROUP_TABLE::SetReadOnly(void)

- ea: `0x18002d19c`
- end: `0x18002d26b`
- name: `?SetReadOnly@SECTION_GROUP_TABLE@@QEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(SECTION_GROUP_TABLE *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180028cec`
- `0x18002d19c`

## callees

- `0x180026a30`
- `0x180027d84`
- `0x180027dd4`
- `0x18002bd64`
- `0x18002d104`
- `0x18002d19c`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d1ca`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d232`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d1ca`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d232`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d1de`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d243`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d1de`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002d243`

## pseudocode

```c
__int64 __fastcall SECTION_GROUP_TABLE::SetReadOnly(SECTION_GROUP_TABLE *this)
{
  int Iterator; // ebx
  int i; // eax
  SECTION_GROUP_TABLE *Data; // rax
  __int64 v5; // rbx
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]
  int v9; // [rsp+38h] [rbp-10h]

  v8 = 0;
  v9 = 0;
  v7 = 0;
  CReaderWriterLock3::WriteLock((SECTION_GROUP_TABLE *)((char *)this + 120));
  *((_DWORD *)this + 33) = 1;
  CReaderWriterLock3::WriteUnlock((SECTION_GROUP_TABLE *)((char *)this + 120));
  Iterator = CONFIG_HASH<SECTION_GROUP_TABLE>::GetIterator((char *)this + 96, &v7);
  if ( Iterator >= 0 )
  {
    for ( i = CONFIG_HASH_ITERATOR<CONFIG_ELEMENT>::MoveFirst(&v7);
          !i;
          i = CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::MoveNext(&v7) )
    {
      Data = (SECTION_GROUP_TABLE *)CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::GetData(&v7);
      Iterator = SECTION_GROUP_TABLE::SetReadOnly(Data);
      if ( Iterator < 0 )
        goto LABEL_7;
    }
    v5 = *((_QWORD *)this + 4);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v5 + 64));
    *(_DWORD *)(v5 + 76) = 1;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v5 + 64));
    Iterator = 0;
  }
LABEL_7:
  CONFIG_HASH<SECTION_GROUP_TABLE>::ReleaseIterator((char *)this + 96, &v7);
  return (unsigned int)Iterator;
}

```

## disassembly

```asm
0x18002d19c  mov     rax, rsp
0x18002d19f  mov     [rax+8], rbx
0x18002d1a3  mov     [rax+10h], rsi
0x18002d1a7  push    rdi
0x18002d1a8  sub     rsp, 40h
0x18002d1ac  mov     rdi, rcx
0x18002d1af  mov     qword ptr [rax-18h], 0
0x18002d1b7  xorps   xmm0, xmm0
0x18002d1ba  mov     dword ptr [rax-10h], 0
0x18002d1c1  add     rcx, 78h ; 'x'
0x18002d1c5  movdqu  xmmword ptr [rax-28h], xmm0
0x18002d1ca  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002d1d0  lea     rcx, [rdi+78h]
0x18002d1d4  mov     dword ptr [rdi+84h], 1
0x18002d1de  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002d1e4  lea     rdx, [rsp+48h+var_28]
0x18002d1e9  lea     rcx, [rdi+60h]
0x18002d1ed  call    ?GetIterator@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEAV?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@@Z; CONFIG_HASH<SECTION_GROUP_TABLE>::GetIterator(CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE> *)
0x18002d1f2  mov     ebx, eax
0x18002d1f4  test    eax, eax
0x18002d1f6  js      short loc_18002D24B
0x18002d1f8  lea     rcx, [rsp+48h+var_28]
0x18002d1fd  call    ?MoveFirst@?$CONFIG_HASH_ITERATOR@VCONFIG_ELEMENT@@@@QEAAJXZ; CONFIG_HASH_ITERATOR<CONFIG_ELEMENT>::MoveFirst(void)
0x18002d202  test    eax, eax
0x18002d204  jnz     short loc_18002D22A
0x18002d206  lea     rcx, [rsp+48h+var_28]
0x18002d20b  call    ?GetData@?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@QEAAPEAVSECTION_GROUP_TABLE@@XZ; CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::GetData(void)
0x18002d210  mov     rcx, rax; this
0x18002d213  call    ?SetReadOnly@SECTION_GROUP_TABLE@@QEAAJXZ; SECTION_GROUP_TABLE::SetReadOnly(void)
0x18002d218  mov     ebx, eax
0x18002d21a  test    eax, eax
0x18002d21c  js      short loc_18002D24B
0x18002d21e  lea     rcx, [rsp+48h+var_28]
0x18002d223  call    ?MoveNext@?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@QEAAJXZ; CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::MoveNext(void)
0x18002d228  jmp     short loc_18002D202
0x18002d22a  mov     rbx, [rdi+20h]
0x18002d22e  lea     rcx, [rbx+40h]
0x18002d232  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002d238  lea     rcx, [rbx+40h]
0x18002d23c  mov     dword ptr [rbx+4Ch], 1
0x18002d243  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002d249  xor     ebx, ebx
0x18002d24b  lea     rdx, [rsp+48h+var_28]
0x18002d250  lea     rcx, [rdi+60h]
0x18002d254  call    ?ReleaseIterator@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEAV?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@@Z; CONFIG_HASH<SECTION_GROUP_TABLE>::ReleaseIterator(CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE> *)
0x18002d259  mov     rsi, [rsp+48h+arg_8]
0x18002d25e  mov     eax, ebx
0x18002d260  mov     rbx, [rsp+48h+arg_0]
0x18002d265  add     rsp, 40h
0x18002d269  pop     rdi
0x18002d26a  retn
```
