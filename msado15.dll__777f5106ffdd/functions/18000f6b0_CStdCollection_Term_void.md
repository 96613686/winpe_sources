# CStdCollection::Term(void)

- ea: `0x18000f6b0`
- end: `0x18000f759`
- name: `?Term@CStdCollection@@UEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(CStdCollection *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f6b0`
- `0x18000f890`
- `0x18000f8c0`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f6c0`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f6c0`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f6e1`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f6e1`
- `MSDART!MpHeapFree` at `0x18000f71b`
- `MSDART!MpHeapFree` at `0x18000f71b`

## pseudocode

```c
__int64 __fastcall CStdCollection::Term(CStdCollection *this)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rdx

  CReaderWriterLock3AR::WriteLock((CStdCollection *)((char *)this + 72));
  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
  {
    LODWORD(v4) = *(_DWORD *)(v2 + 16);
    while ( (_DWORD)v4 )
    {
      v5 = (unsigned int)v4;
      v4 = (unsigned int)(v4 - 1);
      if ( (unsigned int)v4 < *(_DWORD *)(v2 + 16) )
      {
        v6 = *(_QWORD *)(*(_QWORD *)(v2 + 8) + 8 * v4);
        if ( v6 )
        {
          if ( v6 != v5 )
            (*(void (__fastcall **)(CStdCollection *))(*(_QWORD *)this + 352LL))(this);
        }
      }
    }
    CCollectionMap::~CCollectionMap((CCollectionMap *)(v2 + 24));
    CDynamicArray::~CDynamicArray((CDynamicArray *)v2);
    MpHeapFree(g_hHeapHandle, v2);
  }
  CReaderWriterLock3AR::WriteUnlock((CStdCollection *)((char *)this + 72));
  return 0;
}

```

## disassembly

```asm
0x18000f6b0  push    rbx
0x18000f6b2  push    rbp
0x18000f6b3  push    rsi
0x18000f6b4  push    rdi
0x18000f6b5  sub     rsp, 28h
0x18000f6b9  mov     rsi, rcx
0x18000f6bc  add     rcx, 48h ; 'H'
0x18000f6c0  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000f6c7  nop     dword ptr [rax+rax+00h]
0x18000f6cc  mov     rdi, [rsi+40h]
0x18000f6d0  mov     qword ptr [rsi+40h], 0
0x18000f6d8  test    rdi, rdi
0x18000f6db  jnz     short loc_18000F6F9
0x18000f6dd  lea     rcx, [rsi+48h]
0x18000f6e1  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000f6e8  nop     dword ptr [rax+rax+00h]
0x18000f6ed  xor     eax, eax
0x18000f6ef  add     rsp, 28h
0x18000f6f3  pop     rdi
0x18000f6f4  pop     rsi
0x18000f6f5  pop     rbp
0x18000f6f6  pop     rbx
0x18000f6f7  retn
0x18000f6f9  mov     ebx, [rdi+10h]
0x18000f6fc  test    ebx, ebx
0x18000f6fe  jnz     short loc_18000F729
0x18000f700  lea     rcx, [rdi+18h]; this
0x18000f704  call    ??1CCollectionMap@@QEAA@XZ; CCollectionMap::~CCollectionMap(void)
0x18000f709  mov     rcx, rdi; this
0x18000f70c  call    ??1CDynamicArray@@QEAA@XZ; CDynamicArray::~CDynamicArray(void)
0x18000f711  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000f718  mov     rdx, rdi
0x18000f71b  call    cs:__imp_MpHeapFree
0x18000f722  nop     dword ptr [rax+rax+00h]
0x18000f727  jmp     short loc_18000F6DD
0x18000f729  mov     r8d, ebx
0x18000f72c  dec     ebx
0x18000f72e  cmp     ebx, [rdi+10h]
0x18000f731  jnb     short loc_18000F6FC
0x18000f733  mov     rax, [rdi+8]
0x18000f737  mov     rdx, [rax+rbx*8]
0x18000f73b  test    rdx, rdx
0x18000f73e  jz      short loc_18000F6FC
0x18000f740  cmp     rdx, r8
0x18000f743  jz      short loc_18000F6FC
0x18000f745  mov     rax, [rsi]
0x18000f748  mov     rcx, rsi
0x18000f74b  mov     rax, [rax+160h]
0x18000f752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f757  jmp     short loc_18000F6FC
```
