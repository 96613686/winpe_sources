# _CopyCollection_CRecordset_

- ea: `0x180001b10`
- end: `0x180001c92`
- name: `_CopyCollection_CRecordset_`
- size: `386`
- prototype: `__int64 __fastcall(CStdCollection *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001c98`

## callees

- `0x180001b10`
- `0x180002840`
- `0x180047a50`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001b40`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001b40`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001c6e`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001c6e`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180001bc4`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180001bc4`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180001c00`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180001c00`
- `MSDART!MpHeapAlloc` at `0x180001b84`
- `MSDART!MpHeapAlloc` at `0x180001b84`

## pseudocode

```c
__int64 __fastcall CopyCollection_CRecordset_(CCollectionList **this, _QWORD *a2, _DWORD *a3)
{
  unsigned int v3; // ebx
  CReaderWriterLock3AR *v4; // r12
  unsigned int Count; // eax
  unsigned __int64 v7; // rsi
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  __int64 i; // r14
  char *v12; // rbp
  bool v13; // al
  CCollectionList *v14; // rcx
  bool v15; // r9
  unsigned int v16; // eax
  char *v17; // rax
  void *v19; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+10h]
  _DWORD *v21; // [rsp+70h] [rbp+18h]

  v21 = a3;
  v20 = a2;
  v3 = 0;
  v4 = (CReaderWriterLock3AR *)(this + 9);
  *a2 = 0;
  *a3 = 0;
  CReaderWriterLock3AR::ReadLock((CReaderWriterLock3AR *)(this + 9));
  Count = CStdCollection::GetCount((CStdCollection *)this);
  v7 = Count;
  if ( Count )
  {
    v19 = 0;
    v8 = 8LL * Count;
    if ( is_mul_ok(v7, 8u) )
    {
      v9 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, v8);
      v10 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, 8 * v7);
        for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
        {
          v12 = 0;
          v19 = 0;
          v13 = CReaderWriterLock3AR::ReadOrWriteLock(v4);
          v14 = this[8];
          v15 = v13;
          if ( v14 )
          {
            v16 = CCollectionList::LookUpByIndex(v14, (unsigned int)i, &v19);
            v12 = (char *)v19;
            v3 = v16;
          }
          else
          {
            v3 = 1;
          }
          CReaderWriterLock3AR::ReadOrWriteUnlock(v4, v15);
          if ( v12 )
            v17 = v12 - 32;
          else
            v17 = 0;
          v10[i] = v17;
          if ( v17
            && (*((_DWORD *)v17 + 20)
             || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v10[i] + 32LL) + 80LL))(v10[i] + 32LL)) )
          {
            v10[i] = 0;
          }
        }
        *v20 = v10;
        *v21 = v7;
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      v3 = -2147024362;
    }
  }
  CReaderWriterLock3AR::ReadUnlock(v4);
  return v3;
}

```

## disassembly

```asm
0x180001b10  mov     [rsp+arg_18], rbx
0x180001b15  mov     [rsp+arg_10], r8
0x180001b1a  mov     [rsp+arg_8], rdx
0x180001b1f  push    rbp
0x180001b20  push    rsi
0x180001b21  push    rdi
0x180001b22  push    r12
0x180001b24  push    r13
0x180001b26  push    r14
0x180001b28  push    r15
0x180001b2a  sub     rsp, 20h
0x180001b2e  xor     ebx, ebx
0x180001b30  lea     r12, [rcx+48h]
0x180001b34  mov     r13, rcx
0x180001b37  mov     [rdx], rbx
0x180001b3a  mov     rcx, r12
0x180001b3d  mov     [r8], ebx
0x180001b40  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x180001b47  nop     dword ptr [rax+rax+00h]
0x180001b4c  mov     rcx, r13; this
0x180001b4f  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x180001b54  mov     esi, eax
0x180001b56  test    eax, eax
0x180001b58  jz      loc_180001C6B
0x180001b5e  lea     eax, [rbx+8]
0x180001b61  mov     [rsp+58h+arg_0], rbx
0x180001b66  mul     rsi
0x180001b69  mov     rbp, rax
0x180001b6c  test    rdx, rdx
0x180001b6f  jnz     loc_180001C66
0x180001b75  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180001b7c  mov     r8, rax
0x180001b7f  mov     edx, 0A00000h
0x180001b84  call    cs:__imp_MpHeapAlloc
0x180001b8b  nop     dword ptr [rax+rax+00h]
0x180001b90  mov     rdi, rax
0x180001b93  test    rax, rax
0x180001b96  jnz     short loc_180001BA2
0x180001b98  mov     ebx, 8007000Eh
0x180001b9d  jmp     loc_180001C6B
0x180001ba2  mov     r8, rbp; Size
0x180001ba5  xor     edx, edx; Val
0x180001ba7  mov     rcx, rdi; void *
0x180001baa  call    memset_0
0x180001baf  xor     r14d, r14d
0x180001bb2  test    esi, esi
0x180001bb4  jz      loc_180001C55
0x180001bba  xor     ebp, ebp
0x180001bbc  mov     rcx, r12
0x180001bbf  mov     [rsp+58h+arg_0], rbp
0x180001bc4  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x180001bcb  nop     dword ptr [rax+rax+00h]
0x180001bd0  mov     rcx, [r13+40h]; this
0x180001bd4  mov     r9b, al
0x180001bd7  mov     r15d, r14d
0x180001bda  test    rcx, rcx
0x180001bdd  jz      short loc_180001BF5
0x180001bdf  lea     r8, [rsp+58h+arg_0]; void **
0x180001be4  mov     edx, r15d; unsigned __int64
0x180001be7  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x180001bec  mov     rbp, [rsp+58h+arg_0]
0x180001bf1  mov     ebx, eax
0x180001bf3  jmp     short loc_180001BFA
0x180001bf5  mov     ebx, 1
0x180001bfa  mov     dl, r9b
0x180001bfd  mov     rcx, r12
0x180001c00  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x180001c07  nop     dword ptr [rax+rax+00h]
0x180001c0c  test    rbp, rbp
0x180001c0f  jz      short loc_180001C17
0x180001c11  lea     rax, [rbp-20h]
0x180001c15  jmp     short loc_180001C19
0x180001c17  xor     eax, eax
0x180001c19  mov     [rdi+r14*8], rax
0x180001c1d  test    rax, rax
0x180001c20  jz      short loc_180001C49
0x180001c22  mov     eax, [rax+50h]
0x180001c25  test    eax, eax
0x180001c27  jnz     short loc_180001C41
0x180001c29  mov     rcx, [rdi+r14*8]
0x180001c2d  add     rcx, 20h ; ' '
0x180001c31  mov     rax, [rcx]
0x180001c34  mov     rax, [rax+50h]
0x180001c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c3d  test    eax, eax
0x180001c3f  jnz     short loc_180001C49
0x180001c41  mov     qword ptr [rdi+r14*8], 0
0x180001c49  inc     r14d
0x180001c4c  cmp     r14d, esi
0x180001c4f  jb      loc_180001BBA
0x180001c55  mov     rax, [rsp+58h+arg_8]
0x180001c5a  mov     [rax], rdi
0x180001c5d  mov     rax, [rsp+58h+arg_10]
0x180001c62  mov     [rax], esi
0x180001c64  jmp     short loc_180001C6B
0x180001c66  mov     ebx, 80070216h
0x180001c6b  mov     rcx, r12
0x180001c6e  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x180001c75  nop     dword ptr [rax+rax+00h]
0x180001c7a  mov     eax, ebx
0x180001c7c  mov     rbx, [rsp+58h+arg_18]
0x180001c81  add     rsp, 20h
0x180001c85  pop     r15
0x180001c87  pop     r14
0x180001c89  pop     r13
0x180001c8b  pop     r12
0x180001c8d  pop     rdi
0x180001c8e  pop     rsi
0x180001c8f  pop     rbp
0x180001c90  retn
```
