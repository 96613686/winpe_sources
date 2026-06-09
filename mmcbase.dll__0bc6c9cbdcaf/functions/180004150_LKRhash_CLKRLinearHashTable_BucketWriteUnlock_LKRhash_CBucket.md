# LKRhash::CLKRLinearHashTable::_BucketWriteUnlock(LKRhash::CBucket *)

- ea: `0x180004150`
- end: `0x180004175`
- name: `?_BucketWriteUnlock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z`
- size: `37`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this, struct LKRhash::CBucket *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000813c`
- `0x180019de8`
- `0x180019f9c`
- `0x18001a07c`

## callees

- `0x180004150`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_BucketWriteUnlock(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CBucket *a2)
{
  bool i; // zf
  signed __int32 v3; // ecx

  for ( i = *((_BYTE *)this + 153) == 0;
        !i;
        i = v3 == _InterlockedCompareExchange((volatile signed __int32 *)a2, (v3 - 0x10000) & 0xFFFF0000, v3) )
  {
    v3 = *(_DWORD *)a2;
  }
}

```

## disassembly

```asm
0x180004150  cmp     byte ptr [rcx+99h], 0
0x180004157  jz      short locret_180004174
0x180004159  mov     ecx, [rdx]
0x18000415b  mov     eax, ecx
0x18000415d  lea     r8d, [rcx-10000h]
0x180004164  and     r8d, 0FFFF0000h
0x18000416b  lock cmpxchg [rdx], r8d
0x180004170  cmp     ecx, eax
0x180004172  jmp     short loc_180004157
0x180004174  retn
```
