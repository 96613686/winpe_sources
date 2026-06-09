# CONFIG_HASH<CONFIG_VDIR>::Insert(CONFIG_HASH_KEY *,CONFIG_VDIR *,int)

- ea: `0x180056f14`
- end: `0x180057005`
- name: `?Insert@?$CONFIG_HASH@VCONFIG_VDIR@@@@QEAAJPEAVCONFIG_HASH_KEY@@PEAVCONFIG_VDIR@@H@Z`
- size: `241`
- prototype: `__int64 __fastcall(CONFIG_HASH_BUCKETS *this, struct CONFIG_HASH_KEY *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180056948`

## callees

- `0x18000ab70`
- `0x18000ac5c`
- `0x18000ad58`
- `0x180056f14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056fd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056fe2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056fe2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180056f4b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180056f4b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180056fec`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180056fec`

## pseudocode

```c
__int64 __fastcall CONFIG_HASH<CONFIG_VDIR>::Insert(
        CONFIG_HASH_BUCKETS *this,
        struct CONFIG_HASH_KEY *a2,
        volatile signed __int32 *a3)
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
        v13 = CONFIG_HASH_NODE::Allocate(a2, (void *)a3, (struct CONFIG_HASH_NODE **)&lpMem);
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
            _InterlockedIncrement(a3 + 11);
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
0x180056f14  push    rbx
0x180056f16  push    rbp
0x180056f17  push    rsi
0x180056f18  push    rdi
0x180056f19  push    r12
0x180056f1b  push    r13
0x180056f1d  push    r14
0x180056f1f  push    r15
0x180056f21  sub     rsp, 28h
0x180056f25  cmp     dword ptr [rcx+24h], 0
0x180056f29  mov     rbp, r8
0x180056f2c  mov     rsi, rdx
0x180056f2f  mov     [rsp+68h+lpMem], 0
0x180056f38  mov     rbx, rcx
0x180056f3b  jz      short loc_180056F47
0x180056f3d  mov     edi, 80070021h
0x180056f42  jmp     loc_180056FF2
0x180056f47  add     rcx, 18h
0x180056f4b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180056f51  mov     eax, [rbx+20h]
0x180056f54  cmp     eax, 1000000h
0x180056f59  jb      short loc_180056F65
0x180056f5b  mov     edi, 80070032h
0x180056f60  jmp     loc_180056FE8
0x180056f65  mov     edx, [rbx+10h]
0x180056f68  shr     eax, 1
0x180056f6a  cmp     edx, eax
0x180056f6c  jnb     short loc_180056F7F
0x180056f6e  shl     edx, 2; unsigned int
0x180056f71  mov     rcx, rbx; this
0x180056f74  call    ?Resize@CONFIG_HASH_BUCKETS@@QEAAJK@Z; CONFIG_HASH_BUCKETS::Resize(ulong)
0x180056f79  mov     edi, eax
0x180056f7b  test    eax, eax
0x180056f7d  js      short loc_180056FE8
0x180056f7f  mov     r15d, [rsi+10h]
0x180056f83  lea     r8, [rsp+68h+lpMem]; struct CONFIG_HASH_NODE **
0x180056f88  mov     r12d, [rbx+10h]
0x180056f8c  mov     rdx, rbp; void *
0x180056f8f  mov     r13, [rbx]
0x180056f92  mov     rcx, rsi; struct CONFIG_HASH_KEY *
0x180056f95  call    ?Allocate@CONFIG_HASH_NODE@@SAJPEAVCONFIG_HASH_KEY@@PEAXPEAPEAV1@@Z; CONFIG_HASH_NODE::Allocate(CONFIG_HASH_KEY *,void *,CONFIG_HASH_NODE * *)
0x180056f9a  mov     rsi, [rsp+68h+lpMem]
0x180056f9f  mov     edi, eax
0x180056fa1  test    eax, eax
0x180056fa3  js      short loc_180056FCF
0x180056fa5  xor     edx, edx
0x180056fa7  mov     eax, r15d
0x180056faa  div     r12d
0x180056fad  mov     rcx, rsi; this
0x180056fb0  lea     rdx, ds:0[rdx*8]
0x180056fb8  add     rdx, r13; struct CONFIG_HASH_NODE **
0x180056fbb  call    ?Insert@CONFIG_HASH_NODE@@QEAAJPEAPEAV1@@Z; CONFIG_HASH_NODE::Insert(CONFIG_HASH_NODE * *)
0x180056fc0  mov     edi, eax
0x180056fc2  test    eax, eax
0x180056fc4  js      short loc_180056FCF
0x180056fc6  xor     esi, esi
0x180056fc8  lock inc dword ptr [rbp+2Ch]
0x180056fcc  inc     dword ptr [rbx+20h]
0x180056fcf  test    rsi, rsi
0x180056fd2  jz      short loc_180056FE8
0x180056fd4  call    cs:__imp_GetProcessHeap
0x180056fda  mov     r8, rsi; lpMem
0x180056fdd  xor     edx, edx; dwFlags
0x180056fdf  mov     rcx, rax; hHeap
0x180056fe2  call    cs:__imp_HeapFree
0x180056fe8  lea     rcx, [rbx+18h]
0x180056fec  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180056ff2  mov     eax, edi
0x180056ff4  add     rsp, 28h
0x180056ff8  pop     r15
0x180056ffa  pop     r14
0x180056ffc  pop     r13
0x180056ffe  pop     r12
0x180057000  pop     rdi
0x180057001  pop     rsi
0x180057002  pop     rbp
0x180057003  pop     rbx
0x180057004  retn
```
