# CStdCollection::Delete(CStdComObjectRoot *)

- ea: `0x180011700`
- end: `0x1800117fa`
- name: `?Delete@CStdCollection@@QEAAJPEAVCStdComObjectRoot@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(CStdCollection *__hidden this, struct CStdComObjectRoot *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800649c0`
- `0x1800680f0`
- `0x18009cfa0`
- `0x18009d5f0`
- `0x1800a1714`

## callees

- `0x180011700`
- `0x1800119e0`
- `0x1800cdade`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011713`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011713`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011797`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011797`

## pseudocode

```c
__int64 __fastcall CStdCollection::Delete(CStdCollection *this, struct CStdComObjectRoot *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // r8d
  __int64 i; // rdx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx

  CReaderWriterLock3AR::WriteLock((CStdCollection *)((char *)this + 72));
  (*(void (__fastcall **)(struct CStdComObjectRoot *, _QWORD))(*(_QWORD *)a2 + 152LL))(a2, 0);
  v4 = *((_QWORD *)this + 8);
  v5 = *(_DWORD *)(v4 + 16);
  if ( v5 )
  {
    v12 = *(_QWORD *)(v4 + 8);
    v13 = 0;
    while ( *(struct CStdComObjectRoot **)(v12 + 8 * v13) != a2 )
    {
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= v5 )
        goto LABEL_2;
    }
    if ( (_DWORD)v13 != v5 - 1 )
      memmove_0((void *)(v12 + 8 * v13), (const void *)(v12 + 8 * v13 + 8), 8LL * (~(_DWORD)v13 + v5));
    --*(_DWORD *)(v4 + 16);
  }
LABEL_2:
  for ( i = 0; (unsigned int)i < *(_DWORD *)(v4 + 24); i = (unsigned int)(i + 1) )
  {
    v7 = *(_QWORD *)(v4 + 32) + 8 * i;
    v8 = *(_QWORD *)v7;
    if ( *(_QWORD *)v7 )
    {
      while ( v8 )
      {
        if ( *(struct CStdComObjectRoot **)(v8 + 24) == a2 )
        {
          v9 = *(_QWORD *)(*(_QWORD *)v7 + 40LL);
          *(_QWORD *)v7 = v9;
          CCollectionMapEntry::`scalar deleting destructor'((CCollectionMapEntry *)v8, v9);
          --*(_DWORD *)(v4 + 40);
          goto LABEL_9;
        }
        v7 = v8 + 40;
        v8 = *(_QWORD *)(v8 + 40);
      }
    }
  }
LABEL_9:
  v10 = (*(__int64 (__fastcall **)(CStdCollection *, struct CStdComObjectRoot *))(*(_QWORD *)this + 352LL))(this, a2);
  CReaderWriterLock3AR::WriteUnlock((CStdCollection *)((char *)this + 72));
  return v10;
}

```

## disassembly

```asm
0x180011700  push    rbx
0x180011702  push    rbp
0x180011703  push    rsi
0x180011704  push    rdi
0x180011705  sub     rsp, 28h
0x180011709  mov     rsi, rcx
0x18001170c  mov     rdi, rdx
0x18001170f  add     rcx, 48h ; 'H'
0x180011713  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18001171a  nop     dword ptr [rax+rax+00h]
0x18001171f  mov     rax, [rdi]
0x180011722  xor     edx, edx
0x180011724  mov     rcx, rdi
0x180011727  mov     rax, [rax+98h]
0x18001172e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011733  mov     rbx, [rsi+40h]
0x180011737  mov     r8d, [rbx+10h]
0x18001173b  test    r8d, r8d
0x18001173e  jnz     short loc_1800117AF
0x180011740  xor     edx, edx
0x180011742  cmp     edx, [rbx+18h]
0x180011745  jnb     short loc_18001177C
0x180011747  mov     rax, [rbx+20h]
0x18001174b  lea     r8, [rax+rdx*8]
0x18001174f  mov     rcx, [r8]; this
0x180011752  test    rcx, rcx
0x180011755  jnz     short loc_18001175B
0x180011757  inc     edx
0x180011759  jmp     short loc_180011742
0x18001175b  test    rcx, rcx
0x18001175e  jz      short loc_180011757
0x180011760  cmp     [rcx+18h], rdi
0x180011764  jnz     loc_1800117EE
0x18001176a  mov     rax, [r8]
0x18001176d  mov     rdx, [rax+28h]; unsigned int
0x180011771  mov     [r8], rdx
0x180011774  call    ??_GCCollectionMapEntry@@QEAAPEAXI@Z; CCollectionMapEntry::`scalar deleting destructor'(uint)
0x180011779  dec     dword ptr [rbx+28h]
0x18001177c  mov     rax, [rsi]
0x18001177f  mov     rdx, rdi
0x180011782  mov     rcx, rsi
0x180011785  mov     rax, [rax+160h]
0x18001178c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011791  mov     ebx, eax
0x180011793  lea     rcx, [rsi+48h]
0x180011797  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18001179e  nop     dword ptr [rax+rax+00h]
0x1800117a3  mov     eax, ebx
0x1800117a5  add     rsp, 28h
0x1800117a9  pop     rdi
0x1800117aa  pop     rsi
0x1800117ab  pop     rbp
0x1800117ac  pop     rbx
0x1800117ad  retn
0x1800117af  mov     rcx, [rbx+8]
0x1800117b3  xor     edx, edx
0x1800117b5  cmp     [rcx+rdx*8], rdi
0x1800117b9  jz      short loc_1800117C8
0x1800117bb  inc     edx
0x1800117bd  cmp     edx, r8d
0x1800117c0  jnb     loc_180011740
0x1800117c6  jmp     short loc_1800117B5
0x1800117c8  lea     eax, [r8-1]
0x1800117cc  cmp     edx, eax
0x1800117ce  jz      short loc_1800117E6
0x1800117d0  lea     rcx, [rcx+rdx*8]; void *
0x1800117d4  not     edx
0x1800117d6  add     r8d, edx
0x1800117d9  lea     rdx, [rcx+8]; Src
0x1800117dd  shl     r8, 3; Size
0x1800117e1  call    memmove_0
0x1800117e6  dec     dword ptr [rbx+10h]
0x1800117e9  jmp     loc_180011740
0x1800117ee  lea     r8, [rcx+28h]
0x1800117f2  mov     rcx, [r8]
0x1800117f5  jmp     loc_18001175B
```
