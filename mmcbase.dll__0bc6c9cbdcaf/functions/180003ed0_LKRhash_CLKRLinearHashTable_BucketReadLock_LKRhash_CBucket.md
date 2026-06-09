# LKRhash::CLKRLinearHashTable::_BucketReadLock(LKRhash::CBucket *)

- ea: `0x180003ed0`
- end: `0x180003f00`
- name: `?_BucketReadLock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z`
- size: `48`
- prototype: `void(LKRhash::CLKRLinearHashTable *__hidden this, struct LKRhash::CBucket *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003cf0`
- `0x18000813c`

## callees

- `0x180003ed0`
- `0x180019624`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_BucketReadLock(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CBucket *a2)
{
  signed __int32 v2; // ecx

  if ( *((_BYTE *)this + 153) )
  {
    if ( (*(_DWORD *)a2 & 0xFFFF8000) != 0
      || (v2 = *(_DWORD *)a2, v2 != _InterlockedCompareExchange((volatile signed __int32 *)a2, v2 + 1, v2)) )
    {
      CReaderWriterLock2::_LockSpin(a2, 0);
    }
  }
}

```

## disassembly

```asm
0x180003ed0  cmp     byte ptr [rcx+99h], 0
0x180003ed7  mov     r9, rdx
0x180003eda  jz      short locret_180003EFF
0x180003edc  mov     ecx, [rdx]
0x180003ede  test    ecx, 0FFFF8000h
0x180003ee4  jnz     short loc_180003EF5
0x180003ee6  lea     r8d, [rcx+1]
0x180003eea  mov     eax, ecx
0x180003eec  lock cmpxchg [rdx], r8d
0x180003ef1  cmp     ecx, eax
0x180003ef3  jz      short locret_180003EFF
0x180003ef5  xor     edx, edx; bool
0x180003ef7  mov     rcx, r9; this
0x180003efa  jmp     ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180003eff  retn
```
