# LKRhash::CLKRLinearHashTable::WriteUnlock(void)

- ea: `0x1800037e0`
- end: `0x18000382f`
- name: `?WriteUnlock@CLKRLinearHashTable@LKRhash@@QEBAXXZ`
- size: `79`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800026c0`
- `0x1800029d0`
- `0x180002d60`
- `0x180019de8`
- `0x18001a07c`

## callees

- `0x1800037e0`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::WriteUnlock(LKRhash::CLKRLinearHashTable *this)
{
  __int32 v1; // edx
  signed __int32 v2; // r8d

  if ( *((_BYTE *)this + 153) )
  {
    v1 = 0;
    if ( ((*((_BYTE *)this + 28) - 1) & 3) != 0 )
      v1 = *((_DWORD *)this + 7) - 1;
    _InterlockedExchange((volatile __int32 *)this + 7, v1);
    if ( !v1 )
    {
      _m_prefetchw((char *)this + 24);
      do
        v2 = *((_DWORD *)this + 6);
      while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 6, (v2 - 0x10000) & 0xFFFF0000, v2) );
    }
  }
}

```

## disassembly

```asm
0x1800037e0  cmp     byte ptr [rcx+99h], 0
0x1800037e7  jz      short locret_180003801
0x1800037e9  mov     eax, [rcx+1Ch]
0x1800037ec  mov     edx, 0
0x1800037f1  dec     eax
0x1800037f3  test    al, 3
0x1800037f5  cmovnz  edx, eax
0x1800037f8  mov     eax, edx
0x1800037fa  xchg    eax, [rcx+1Ch]
0x1800037fd  test    edx, edx
0x1800037ff  jz      short loc_180003802
0x180003801  retn
0x180003802  prefetchw byte ptr [rcx+18h]
0x180003806  nop     word ptr [rax+rax+00000000h]
0x180003810  mov     r8d, [rcx+18h]
0x180003814  mov     eax, r8d
0x180003817  lea     edx, [r8-10000h]
0x18000381e  and     edx, 0FFFF0000h
0x180003824  lock cmpxchg [rcx+18h], edx
0x180003829  cmp     r8d, eax
0x18000382c  jnz     short loc_180003810
0x18000382e  retn
```
