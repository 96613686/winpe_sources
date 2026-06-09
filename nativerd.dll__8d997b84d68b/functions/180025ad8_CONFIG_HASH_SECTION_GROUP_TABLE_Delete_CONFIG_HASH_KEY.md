# CONFIG_HASH<SECTION_GROUP_TABLE>::Delete(CONFIG_HASH_KEY *)

- ea: `0x180025ad8`
- end: `0x180025ba0`
- name: `?Delete@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEAVCONFIG_HASH_KEY@@@Z`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180025cb0`
- `0x180025da0`
- `0x18004334c`

## callees

- `0x18000adc8`
- `0x1800168d0`
- `0x180025ad8`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b78`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025b0d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180025b0d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025b85`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025b85`

## pseudocode

```c
__int64 __fastcall CONFIG_HASH<SECTION_GROUP_TABLE>::Delete(__int64 a1, struct CONFIG_HASH_KEY *a2)
{
  bool v2; // zf
  int v5; // ebx
  struct CONFIG_HASH_NODE **v6; // r14
  _QWORD **v7; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 36) == 0;
  lpMem = 0;
  if ( v2 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 24));
    v6 = (struct CONFIG_HASH_NODE **)(*(_QWORD *)a1 + 8LL * (unsigned int)(*((_DWORD *)a2 + 4) % *(_DWORD *)(a1 + 16)));
    v5 = CONFIG_HASH_NODE::Find(a2, v6, (struct CONFIG_HASH_NODE **)&lpMem);
    if ( !v5 )
    {
      v7 = (_QWORD **)lpMem;
      if ( lpMem )
      {
        v5 = CONFIG_HASH_NODE::Remove((CONFIG_HASH_NODE *)lpMem, v6);
        if ( v5 >= 0 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v7[4] + 16LL))(v7[4]);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          --*(_DWORD *)(a1 + 32);
        }
      }
      else
      {
        v5 = -2147024893;
      }
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 24));
  }
  else
  {
    return (unsigned int)-2147024863;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180025ad8  mov     [rsp+arg_8], rbx
0x180025add  mov     [rsp+arg_10], rbp
0x180025ae2  push    rsi
0x180025ae3  push    rdi
0x180025ae4  push    r14
0x180025ae6  sub     rsp, 20h
0x180025aea  cmp     dword ptr [rcx+24h], 0
0x180025aee  mov     rbx, rdx
0x180025af1  mov     rsi, rcx
0x180025af4  mov     [rsp+38h+lpMem], 0
0x180025afd  jz      short loc_180025B09
0x180025aff  mov     ebx, 80070021h
0x180025b04  jmp     loc_180025B8B
0x180025b09  add     rcx, 18h
0x180025b0d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180025b13  mov     eax, [rbx+10h]
0x180025b16  lea     r8, [rsp+38h+lpMem]; struct CONFIG_HASH_NODE **
0x180025b1b  xor     edx, edx
0x180025b1d  mov     rcx, rbx; struct CONFIG_HASH_KEY *
0x180025b20  div     dword ptr [rsi+10h]
0x180025b23  mov     rax, [rsi]
0x180025b26  lea     r14, [rax+rdx*8]
0x180025b2a  mov     rdx, r14; struct CONFIG_HASH_NODE **
0x180025b2d  call    ?Find@CONFIG_HASH_NODE@@SAJPEAVCONFIG_HASH_KEY@@PEAPEAV1@1@Z; CONFIG_HASH_NODE::Find(CONFIG_HASH_KEY *,CONFIG_HASH_NODE * *,CONFIG_HASH_NODE * *)
0x180025b32  mov     ebx, eax
0x180025b34  test    eax, eax
0x180025b36  jnz     short loc_180025B81
0x180025b38  mov     rdi, [rsp+38h+lpMem]
0x180025b3d  test    rdi, rdi
0x180025b40  jnz     short loc_180025B49
0x180025b42  mov     ebx, 80070003h
0x180025b47  jmp     short loc_180025B81
0x180025b49  mov     rdx, r14; struct CONFIG_HASH_NODE **
0x180025b4c  mov     rcx, rdi; this
0x180025b4f  call    ?Remove@CONFIG_HASH_NODE@@QEAAJPEAPEAV1@@Z; CONFIG_HASH_NODE::Remove(CONFIG_HASH_NODE * *)
0x180025b54  mov     ebx, eax
0x180025b56  test    eax, eax
0x180025b58  js      short loc_180025B81
0x180025b5a  mov     rcx, [rdi+20h]
0x180025b5e  mov     rax, [rcx]
0x180025b61  mov     rax, [rax+10h]
0x180025b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b6a  call    cs:__imp_GetProcessHeap
0x180025b70  mov     r8, rdi; lpMem
0x180025b73  xor     edx, edx; dwFlags
0x180025b75  mov     rcx, rax; hHeap
0x180025b78  call    cs:__imp_HeapFree
0x180025b7e  dec     dword ptr [rsi+20h]
0x180025b81  lea     rcx, [rsi+18h]
0x180025b85  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180025b8b  mov     rbp, [rsp+38h+arg_10]
0x180025b90  mov     eax, ebx
0x180025b92  mov     rbx, [rsp+38h+arg_8]
0x180025b97  add     rsp, 20h
0x180025b9b  pop     r14
0x180025b9d  pop     rdi
0x180025b9e  pop     rsi
0x180025b9f  retn
```
