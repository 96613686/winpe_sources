# CReaderWriterLock3::WriteUnlock(void)

- ea: `0x180003840`
- end: `0x18000387d`
- name: `?WriteUnlock@CReaderWriterLock3@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180001940`
- `0x180001c00`
- `0x180003890`

## callees

- `0x180003840`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteUnlock(CReaderWriterLock3 *this)
{
  __int32 v1; // edx
  signed __int32 v2; // r8d

  v1 = 0;
  if ( ((*((_BYTE *)this + 4) - 1) & 3) != 0 )
    v1 = *((_DWORD *)this + 1) - 1;
  _InterlockedExchange((volatile __int32 *)this + 1, v1);
  if ( !v1 )
  {
    _m_prefetchw(this);
    do
      v2 = *(_DWORD *)this;
    while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 - 0x10000) & 0xFFFF0000, v2) );
  }
}

```

## disassembly

```asm
0x180003840  mov     eax, [rcx+4]
0x180003843  mov     edx, 0
0x180003848  dec     eax
0x18000384a  test    al, 3
0x18000384c  cmovnz  edx, eax
0x18000384f  mov     eax, edx
0x180003851  xchg    eax, [rcx+4]
0x180003854  test    edx, edx
0x180003856  jz      short loc_180003859
0x180003858  retn
0x180003859  prefetchw byte ptr [rcx]
0x18000385c  nop     dword ptr [rax+00h]
0x180003860  mov     r8d, [rcx]
0x180003863  mov     eax, r8d
0x180003866  lea     edx, [r8-10000h]
0x18000386d  and     edx, 0FFFF0000h
0x180003873  lock cmpxchg [rcx], edx
0x180003877  cmp     r8d, eax
0x18000387a  jnz     short loc_180003860
0x18000387c  retn
```
