# CONFIG_HASH<CONFIG_SECTION>::Insert(CONFIG_HASH_KEY *,CONFIG_SECTION *,int)

- ea: `0x18000a968`
- end: `0x18000aa64`
- name: `?Insert@?$CONFIG_HASH@VCONFIG_SECTION@@@@QEAAJPEAVCONFIG_HASH_KEY@@PEAVCONFIG_SECTION@@H@Z`
- size: `252`
- prototype: `__int64 __fastcall(CONFIG_HASH_BUCKETS *this, struct CONFIG_HASH_KEY *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a740`

## callees

- `0x18000a968`
- `0x18000ab70`
- `0x18000ac5c`
- `0x18000ad58`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa41`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a99f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a99f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa4b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa4b`

## pseudocode

```c
__int64 __fastcall CONFIG_HASH<CONFIG_SECTION>::Insert(CONFIG_HASH_BUCKETS *this, struct CONFIG_HASH_KEY *a2, void *a3)
{
  bool v3; // zf
  int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // edx
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
    v8 = *((_DWORD *)this + 8);
    if ( v8 < 0x1000000 )
    {
      v9 = *((_DWORD *)this + 4);
      if ( v9 >= v8 >> 1 || (v7 = CONFIG_HASH_BUCKETS::Resize(this, 4 * v9), v7 >= 0) )
      {
        v10 = *((_DWORD *)a2 + 4);
        v11 = *((_DWORD *)this + 4);
        v12 = *(_QWORD *)this;
        v13 = CONFIG_HASH_NODE::Allocate(a2, a3, (struct CONFIG_HASH_NODE **)&lpMem);
        v14 = lpMem;
        v7 = v13;
        if ( v13 >= 0 )
        {
          v7 = CONFIG_HASH_NODE::Insert(
                 (CONFIG_HASH_NODE *)lpMem,
                 (struct CONFIG_HASH_NODE **)(v12 + 8LL * (v10 % v11)));
          if ( v7 >= 0 )
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
    else
    {
      v7 = -2147024846;
    }
    CReaderWriterLock3::WriteUnlock((CONFIG_HASH_BUCKETS *)((char *)this + 24));
  }
  else
  {
    return (unsigned int)-2147024863;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a968  push    rbx
0x18000a96a  push    rbp
0x18000a96b  push    rsi
0x18000a96c  push    rdi
0x18000a96d  push    r12
0x18000a96f  push    r13
0x18000a971  push    r14
0x18000a973  push    r15
0x18000a975  sub     rsp, 28h
0x18000a979  cmp     dword ptr [rcx+24h], 0
0x18000a97d  mov     r14, r8
0x18000a980  mov     rsi, rdx
0x18000a983  mov     [rsp+68h+lpMem], 0
0x18000a98c  mov     rbx, rcx
0x18000a98f  jz      short loc_18000A99B
0x18000a991  mov     edi, 80070021h
0x18000a996  jmp     loc_18000AA51
0x18000a99b  add     rcx, 18h
0x18000a99f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a9a5  mov     eax, [rbx+20h]
0x18000a9a8  cmp     eax, 1000000h
0x18000a9ad  jb      short loc_18000A9B9
0x18000a9af  mov     edi, 80070032h
0x18000a9b4  jmp     loc_18000AA47
0x18000a9b9  mov     edx, [rbx+10h]
0x18000a9bc  shr     eax, 1
0x18000a9be  cmp     edx, eax
0x18000a9c0  jnb     short loc_18000A9D3
0x18000a9c2  shl     edx, 2; unsigned int
0x18000a9c5  mov     rcx, rbx; this
0x18000a9c8  call    ?Resize@CONFIG_HASH_BUCKETS@@QEAAJK@Z; CONFIG_HASH_BUCKETS::Resize(ulong)
0x18000a9cd  mov     edi, eax
0x18000a9cf  test    eax, eax
0x18000a9d1  js      short loc_18000AA47
0x18000a9d3  mov     r15d, [rsi+10h]
0x18000a9d7  lea     r8, [rsp+68h+lpMem]; struct CONFIG_HASH_NODE **
0x18000a9dc  mov     r12d, [rbx+10h]
0x18000a9e0  mov     rdx, r14; void *
0x18000a9e3  mov     r13, [rbx]
0x18000a9e6  mov     rcx, rsi; struct CONFIG_HASH_KEY *
0x18000a9e9  call    ?Allocate@CONFIG_HASH_NODE@@SAJPEAVCONFIG_HASH_KEY@@PEAXPEAPEAV1@@Z; CONFIG_HASH_NODE::Allocate(CONFIG_HASH_KEY *,void *,CONFIG_HASH_NODE * *)
0x18000a9ee  mov     rsi, [rsp+68h+lpMem]
0x18000a9f3  mov     edi, eax
0x18000a9f5  test    eax, eax
0x18000a9f7  js      short loc_18000AA2E
0x18000a9f9  xor     edx, edx
0x18000a9fb  mov     eax, r15d
0x18000a9fe  div     r12d
0x18000aa01  mov     rcx, rsi; this
0x18000aa04  lea     rdx, ds:0[rdx*8]
0x18000aa0c  add     rdx, r13; struct CONFIG_HASH_NODE **
0x18000aa0f  call    ?Insert@CONFIG_HASH_NODE@@QEAAJPEAPEAV1@@Z; CONFIG_HASH_NODE::Insert(CONFIG_HASH_NODE * *)
0x18000aa14  mov     edi, eax
0x18000aa16  test    eax, eax
0x18000aa18  js      short loc_18000AA2E
0x18000aa1a  mov     rax, [r14]
0x18000aa1d  mov     rcx, r14
0x18000aa20  xor     esi, esi
0x18000aa22  mov     rax, [rax+8]
0x18000aa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa2b  inc     dword ptr [rbx+20h]
0x18000aa2e  test    rsi, rsi
0x18000aa31  jz      short loc_18000AA47
0x18000aa33  call    cs:__imp_GetProcessHeap
0x18000aa39  mov     r8, rsi; lpMem
0x18000aa3c  xor     edx, edx; dwFlags
0x18000aa3e  mov     rcx, rax; hHeap
0x18000aa41  call    cs:__imp_HeapFree
0x18000aa47  lea     rcx, [rbx+18h]
0x18000aa4b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000aa51  mov     eax, edi
0x18000aa53  add     rsp, 28h
0x18000aa57  pop     r15
0x18000aa59  pop     r14
0x18000aa5b  pop     r13
0x18000aa5d  pop     r12
0x18000aa5f  pop     rdi
0x18000aa60  pop     rsi
0x18000aa61  pop     rbp
0x18000aa62  pop     rbx
0x18000aa63  retn
```
