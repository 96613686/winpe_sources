# CONFIG_HASH<SECTION_GROUP_TABLE>::Insert(CONFIG_HASH_KEY *,SECTION_GROUP_TABLE *,int)

- ea: `0x18000aa6c`
- end: `0x18000ab6a`
- name: `?Insert@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEAVCONFIG_HASH_KEY@@PEAVSECTION_GROUP_TABLE@@H@Z`
- size: `254`
- prototype: `__int64 __fastcall(CONFIG_HASH_BUCKETS *this, struct CONFIG_HASH_KEY *, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a83c`
- `0x18002b5d0`
- `0x1800431d0`

## callees

- `0x18000aa6c`
- `0x18000ab70`
- `0x18000ac5c`
- `0x18000ad58`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab39`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa9d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa9d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ab43`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ab43`

## pseudocode

```c
__int64 __fastcall CONFIG_HASH<SECTION_GROUP_TABLE>::Insert(
        CONFIG_HASH_BUCKETS *this,
        struct CONFIG_HASH_KEY *a2,
        void *a3)
{
  bool v3; // zf
  unsigned int v7; // eax
  unsigned int v8; // edx
  int v9; // edi
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  __int64 v12; // r13
  int v13; // eax
  void *v14; // rsi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 9) == 0;
  lpMem = 0;
  if ( v3 )
  {
    CReaderWriterLock3::WriteLock((CONFIG_HASH_BUCKETS *)((char *)this + 24));
    v7 = *((_DWORD *)this + 8);
    if ( v7 >= 0x1000000 )
    {
      v9 = -2147024846;
    }
    else
    {
      v8 = *((_DWORD *)this + 4);
      if ( v8 >= v7 >> 1 || (v9 = CONFIG_HASH_BUCKETS::Resize(this, 4 * v8), v9 >= 0) )
      {
        v10 = *((_DWORD *)a2 + 4);
        v11 = *((_DWORD *)this + 4);
        v12 = *(_QWORD *)this;
        v13 = CONFIG_HASH_NODE::Allocate(a2, a3, (struct CONFIG_HASH_NODE **)&lpMem);
        v14 = lpMem;
        v9 = v13;
        if ( v13 >= 0 )
        {
          v9 = CONFIG_HASH_NODE::Insert(
                 (CONFIG_HASH_NODE *)lpMem,
                 (struct CONFIG_HASH_NODE **)(v12 + 8LL * (v10 % v11)));
          if ( v9 >= 0 )
          {
            v14 = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)a3 + 8LL))(a3);
            ++*((_DWORD *)this + 8);
          }
        }
        if ( v14 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v14);
        }
      }
    }
    CReaderWriterLock3::WriteUnlock((CONFIG_HASH_BUCKETS *)((char *)this + 24));
  }
  else
  {
    return (unsigned int)-2147024863;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000aa6c  push    rbx
0x18000aa6e  push    rbp
0x18000aa6f  push    rsi
0x18000aa70  push    rdi
0x18000aa71  push    r12
0x18000aa73  push    r13
0x18000aa75  push    r14
0x18000aa77  push    r15
0x18000aa79  sub     rsp, 28h
0x18000aa7d  cmp     dword ptr [rcx+24h], 0
0x18000aa81  mov     r14, r8
0x18000aa84  mov     rsi, rdx
0x18000aa87  mov     [rsp+68h+lpMem], 0
0x18000aa90  mov     rbx, rcx
0x18000aa93  jnz     loc_18000AB5C
0x18000aa99  add     rcx, 18h
0x18000aa9d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000aaa3  mov     eax, [rbx+20h]
0x18000aaa6  cmp     eax, 1000000h
0x18000aaab  jnb     loc_18000AB63
0x18000aab1  mov     edx, [rbx+10h]
0x18000aab4  shr     eax, 1
0x18000aab6  cmp     edx, eax
0x18000aab8  jnb     short loc_18000AACB
0x18000aaba  shl     edx, 2; unsigned int
0x18000aabd  mov     rcx, rbx; this
0x18000aac0  call    ?Resize@CONFIG_HASH_BUCKETS@@QEAAJK@Z; CONFIG_HASH_BUCKETS::Resize(ulong)
0x18000aac5  mov     edi, eax
0x18000aac7  test    eax, eax
0x18000aac9  js      short loc_18000AB3F
0x18000aacb  mov     r15d, [rsi+10h]
0x18000aacf  lea     r8, [rsp+68h+lpMem]; struct CONFIG_HASH_NODE **
0x18000aad4  mov     r12d, [rbx+10h]
0x18000aad8  mov     rdx, r14; void *
0x18000aadb  mov     r13, [rbx]
0x18000aade  mov     rcx, rsi; struct CONFIG_HASH_KEY *
0x18000aae1  call    ?Allocate@CONFIG_HASH_NODE@@SAJPEAVCONFIG_HASH_KEY@@PEAXPEAPEAV1@@Z; CONFIG_HASH_NODE::Allocate(CONFIG_HASH_KEY *,void *,CONFIG_HASH_NODE * *)
0x18000aae6  mov     rsi, [rsp+68h+lpMem]
0x18000aaeb  mov     edi, eax
0x18000aaed  test    eax, eax
0x18000aaef  js      short loc_18000AB26
0x18000aaf1  xor     edx, edx
0x18000aaf3  mov     eax, r15d
0x18000aaf6  div     r12d
0x18000aaf9  mov     rcx, rsi; this
0x18000aafc  lea     rdx, ds:0[rdx*8]
0x18000ab04  add     rdx, r13; struct CONFIG_HASH_NODE **
0x18000ab07  call    ?Insert@CONFIG_HASH_NODE@@QEAAJPEAPEAV1@@Z; CONFIG_HASH_NODE::Insert(CONFIG_HASH_NODE * *)
0x18000ab0c  mov     edi, eax
0x18000ab0e  test    eax, eax
0x18000ab10  js      short loc_18000AB26
0x18000ab12  mov     rax, [r14]
0x18000ab15  mov     rcx, r14
0x18000ab18  xor     esi, esi
0x18000ab1a  mov     rax, [rax+8]
0x18000ab1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab23  inc     dword ptr [rbx+20h]
0x18000ab26  test    rsi, rsi
0x18000ab29  jz      short loc_18000AB3F
0x18000ab2b  call    cs:__imp_GetProcessHeap
0x18000ab31  mov     r8, rsi; lpMem
0x18000ab34  xor     edx, edx; dwFlags
0x18000ab36  mov     rcx, rax; hHeap
0x18000ab39  call    cs:__imp_HeapFree
0x18000ab3f  lea     rcx, [rbx+18h]
0x18000ab43  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ab49  mov     eax, edi
0x18000ab4b  add     rsp, 28h
0x18000ab4f  pop     r15
0x18000ab51  pop     r14
0x18000ab53  pop     r13
0x18000ab55  pop     r12
0x18000ab57  pop     rdi
0x18000ab58  pop     rsi
0x18000ab59  pop     rbp
0x18000ab5a  pop     rbx
0x18000ab5b  retn
0x18000ab5c  mov     edi, 80070021h
0x18000ab61  jmp     short loc_18000AB49
0x18000ab63  mov     edi, 80070032h
0x18000ab68  jmp     short loc_18000AB3F
```
