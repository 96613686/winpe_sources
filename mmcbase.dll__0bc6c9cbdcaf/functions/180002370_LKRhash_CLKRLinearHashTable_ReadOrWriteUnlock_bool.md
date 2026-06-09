# LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(bool)

- ea: `0x180002370`
- end: `0x1800023cf`
- name: `?_ReadOrWriteUnlock@CLKRLinearHashTable@LKRhash@@AEBAX_N@Z`
- size: `95`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001940`
- `0x180001c00`

## callees

- `0x180002370`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(LKRhash::CLKRLinearHashTable *this, char a2)
{
  signed __int32 v3; // edx
  int v4; // eax
  __int32 v5; // ecx
  __int32 v6; // eax
  signed __int32 v7; // edx

  if ( *((_BYTE *)this + 153) )
  {
    if ( a2 )
    {
      do
        v3 = *((_DWORD *)this + 6);
      while ( v3 != _InterlockedCompareExchange((volatile signed __int32 *)this + 6, v3 - 1, v3) );
    }
    else
    {
      v4 = *((_DWORD *)this + 7);
      v5 = 0;
      v6 = v4 - 1;
      if ( (v6 & 3) != 0 )
        v5 = v6;
      _InterlockedExchange((volatile __int32 *)this + 7, v5);
      if ( !v5 )
      {
        _m_prefetchw((char *)this + 24);
        do
          v7 = *((_DWORD *)this + 6);
        while ( v7 != _InterlockedCompareExchange((volatile signed __int32 *)this + 6, (v7 - 0x10000) & 0xFFFF0000, v7) );
      }
    }
  }
}

```

## disassembly

```asm
0x180002370  cmp     byte ptr [rcx+99h], 0
0x180002377  mov     r9, rcx
0x18000237a  jz      short locret_180002393
0x18000237c  test    dl, dl
0x18000237e  jz      short loc_180002394
0x180002380  mov     edx, [rcx+18h]
0x180002383  mov     eax, edx
0x180002385  lea     r8d, [rdx-1]
0x180002389  lock cmpxchg [rcx+18h], r8d
0x18000238f  cmp     edx, eax
0x180002391  jnz     short loc_180002380
0x180002393  retn
0x180002394  mov     eax, [rcx+1Ch]
0x180002397  mov     ecx, 0
0x18000239c  dec     eax
0x18000239e  test    al, 3
0x1800023a0  cmovnz  ecx, eax
0x1800023a3  mov     eax, ecx
0x1800023a5  xchg    eax, [r9+1Ch]
0x1800023a9  test    ecx, ecx
0x1800023ab  jnz     short locret_180002393
0x1800023ad  prefetchw byte ptr [r9+18h]
0x1800023b2  mov     edx, [r9+18h]
0x1800023b6  mov     eax, edx
0x1800023b8  lea     ecx, [rdx-10000h]
0x1800023be  and     ecx, 0FFFF0000h
0x1800023c4  lock cmpxchg [r9+18h], ecx
0x1800023ca  cmp     edx, eax
0x1800023cc  jnz     short loc_1800023B2
0x1800023ce  retn
```
