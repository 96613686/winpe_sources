# CStdCollection::DestroyList(CCollectionList *)

- ea: `0x18000f7c0`
- end: `0x18000f889`
- name: `?DestroyList@CStdCollection@@QEAAXPEAVCCollectionList@@@Z`
- size: `201`
- prototype: `void(CStdCollection *__hidden this, struct CCollectionList *)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001c98`
- `0x18000a320`
- `0x18000bbc0`
- `0x18000d530`
- `0x180011d7c`
- `0x180012824`
- `0x180086470`
- `0x1800a0910`

## callees

- `0x18000f7c0`
- `0x18000f890`
- `0x18000f8c0`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f7d9`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f7d9`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f80e`
- `MSDART!MpHeapFree` at `0x18000f873`
- `MSDART!MpHeapFree` at `0x18000f873`

## pseudocode

```c
void __fastcall CStdCollection::DestroyList(CStdCollection *this, struct CCollectionList *a2)
{
  __int64 v4; // rbp
  __int64 v5; // r8
  __int64 v6; // rdx

  CReaderWriterLock3AR::WriteLock((CStdCollection *)((char *)this + 72));
  if ( a2 || (a2 = (struct CCollectionList *)*((_QWORD *)this + 8), *((_QWORD *)this + 8) = 0, a2) )
  {
    LODWORD(v4) = *((_DWORD *)a2 + 4);
    while ( (_DWORD)v4 )
    {
      v5 = (unsigned int)v4;
      v4 = (unsigned int)(v4 - 1);
      if ( (unsigned int)v4 < *((_DWORD *)a2 + 4) )
      {
        v6 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v4);
        if ( v6 )
        {
          if ( v6 != v5 )
            (*(void (__fastcall **)(CStdCollection *))(*(_QWORD *)this + 352LL))(this);
        }
      }
    }
    CCollectionMap::~CCollectionMap((struct CCollectionList *)((char *)a2 + 24));
    CDynamicArray::~CDynamicArray(a2);
    MpHeapFree(g_hHeapHandle, a2);
  }
  CReaderWriterLock3AR::WriteUnlock((CStdCollection *)((char *)this + 72));
}

```

## disassembly

```asm
0x18000f7c0  mov     [rsp+arg_8], rbx
0x18000f7c5  mov     [rsp+arg_10], rsi
0x18000f7ca  push    rdi
0x18000f7cb  sub     rsp, 20h
0x18000f7cf  mov     rdi, rcx
0x18000f7d2  mov     rbx, rdx
0x18000f7d5  add     rcx, 48h ; 'H'
0x18000f7d9  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000f7e0  nop     dword ptr [rax+rax+00h]
0x18000f7e5  test    rbx, rbx
0x18000f7e8  jnz     short loc_18000F81A
0x18000f7ea  mov     rbx, [rdi+40h]
0x18000f7ee  mov     qword ptr [rdi+40h], 0
0x18000f7f6  test    rbx, rbx
0x18000f7f9  jnz     short loc_18000F81A
0x18000f7fb  lea     rcx, [rdi+48h]
0x18000f7ff  mov     rbx, [rsp+28h+arg_8]
0x18000f804  mov     rsi, [rsp+28h+arg_10]
0x18000f809  add     rsp, 20h
0x18000f80d  pop     rdi
0x18000f80e  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000f81a  mov     [rsp+28h+arg_0], rbp
0x18000f81f  mov     ebp, [rbx+10h]
0x18000f822  test    ebp, ebp
0x18000f824  jz      short loc_18000F858
0x18000f826  mov     r8d, ebp
0x18000f829  dec     ebp
0x18000f82b  cmp     ebp, [rbx+10h]
0x18000f82e  jnb     short loc_18000F854
0x18000f830  mov     rax, [rbx+8]
0x18000f834  mov     rdx, [rax+rbp*8]
0x18000f838  test    rdx, rdx
0x18000f83b  jz      short loc_18000F854
0x18000f83d  cmp     rdx, r8
0x18000f840  jz      short loc_18000F854
0x18000f842  mov     rax, [rdi]
0x18000f845  mov     rcx, rdi
0x18000f848  mov     rax, [rax+160h]
0x18000f84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f854  test    ebp, ebp
0x18000f856  jnz     short loc_18000F826
0x18000f858  lea     rcx, [rbx+18h]; this
0x18000f85c  call    ??1CCollectionMap@@QEAA@XZ; CCollectionMap::~CCollectionMap(void)
0x18000f861  mov     rcx, rbx; this
0x18000f864  call    ??1CDynamicArray@@QEAA@XZ; CDynamicArray::~CDynamicArray(void)
0x18000f869  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000f870  mov     rdx, rbx
0x18000f873  call    cs:__imp_MpHeapFree
0x18000f87a  nop     dword ptr [rax+rax+00h]
0x18000f87f  mov     rbp, [rsp+28h+arg_0]
0x18000f884  jmp     loc_18000F7FB
```
