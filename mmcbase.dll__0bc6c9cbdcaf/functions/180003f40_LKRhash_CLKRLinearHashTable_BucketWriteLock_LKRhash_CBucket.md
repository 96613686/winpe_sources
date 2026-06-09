# LKRhash::CLKRLinearHashTable::_BucketWriteLock(LKRhash::CBucket *)

- ea: `0x180003f40`
- end: `0x180003f8f`
- name: `?_BucketWriteLock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z`
- size: `79`
- prototype: `void(LKRhash::CLKRLinearHashTable *__hidden this, struct LKRhash::CBucket *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000813c`
- `0x180019de8`
- `0x180019f9c`
- `0x18001a07c`

## callees

- `0x180003f40`
- `0x180019624`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_BucketWriteLock(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CBucket *a2)
{
  signed __int32 v3; // ecx
  signed __int32 i; // edx

  if ( *((_BYTE *)this + 153) )
  {
    if ( (unsigned __int16)*(_DWORD *)a2
      || (v3 = *(_DWORD *)a2,
          v3 != _InterlockedCompareExchange((volatile signed __int32 *)a2, (v3 + 0x10000) | 0xFFFF, v3)) )
    {
      for ( i = *(_DWORD *)a2;
            i != _InterlockedCompareExchange((volatile signed __int32 *)a2, i + 0x10000, i);
            i = *(_DWORD *)a2 )
      {
        ;
      }
      CReaderWriterLock2::_LockSpin(a2, 1);
    }
  }
}

```

## disassembly

```asm
0x180003f40  cmp     byte ptr [rcx+99h], 0
0x180003f47  mov     r9, rdx
0x180003f4a  jz      short locret_180003F8E
0x180003f4c  mov     ecx, [rdx]
0x180003f4e  test    cx, cx
0x180003f51  jnz     short loc_180003F6C
0x180003f53  lea     r8d, [rcx+10000h]
0x180003f5a  mov     eax, ecx
0x180003f5c  or      r8d, 0FFFFh
0x180003f63  lock cmpxchg [rdx], r8d
0x180003f68  cmp     ecx, eax
0x180003f6a  jz      short locret_180003F8E
0x180003f6c  mov     edx, [rdx]
0x180003f6e  lea     ecx, [rdx+10000h]
0x180003f74  mov     eax, edx
0x180003f76  lock cmpxchg [r9], ecx
0x180003f7b  cmp     edx, eax
0x180003f7d  jz      short loc_180003F84
0x180003f7f  mov     edx, [r9]
0x180003f82  jmp     short loc_180003F6E
0x180003f84  mov     dl, 1; bool
0x180003f86  mov     rcx, r9; this
0x180003f89  jmp     ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180003f8e  retn
```
