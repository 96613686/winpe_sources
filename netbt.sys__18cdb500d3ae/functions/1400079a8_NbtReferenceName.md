# NbtReferenceName

- ea: `0x1400079a8`
- end: `0x140007a00`
- name: `NbtReferenceName`
- size: `88`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140004038`
- `0x14000508c`
- `0x140007354`
- `0x140008a74`
- `0x140015818`
- `0x140017d80`
- `0x1400232bc`
- `0x140029d28`
- `0x14002ab80`
- `0x1400445a8`

## callees

- `0x1400079a8`
- `0x1400089c8`
- `0x140028144`

## pseudocode

```c
__int64 __fastcall NbtReferenceName(__int64 a1)
{
  __int64 result; // rax
  int v2; // r10d
  __int64 v3; // r9

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
  result = NbtCheckNameAddrTimer(a1);
  if ( *(_DWORD *)(v3 + 16) == -87097344 )
  {
    if ( v2 == 1 )
    {
      result = (unsigned int)(dword_140039760 + 1);
      dword_140039760 = result;
      if ( (unsigned int)result > 0x100 )
        return NbtScheduleRemoteTimeout();
    }
    else
    {
      result = (unsigned int)(v2 - 2);
      if ( (result & 0xFFFFFFFB) == 0 )
        --dword_140039760;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400079a8  sub     rsp, 28h
0x1400079ac  mov     r10d, edx
0x1400079af  mov     r9, rcx
0x1400079b2  lock inc dword ptr [rcx+14h]
0x1400079b6  call    NbtCheckNameAddrTimer
0x1400079bb  cmp     dword ptr [r9+10h], 0FACF0000h
0x1400079c3  jz      short loc_1400079CB
0x1400079c5  add     rsp, 28h
0x1400079c9  retn
0x1400079cb  cmp     r10d, 1
0x1400079cf  jnz     short loc_1400079ED
0x1400079d1  mov     eax, cs:dword_140039760
0x1400079d7  inc     eax
0x1400079d9  mov     cs:dword_140039760, eax
0x1400079df  cmp     eax, 100h
0x1400079e4  jbe     short loc_1400079C5
0x1400079e6  call    NbtScheduleRemoteTimeout
0x1400079eb  jmp     short loc_1400079C5
0x1400079ed  lea     eax, [r10-2]
0x1400079f1  test    eax, 0FFFFFFFBh
0x1400079f6  jnz     short loc_1400079C5
0x1400079f8  dec     cs:dword_140039760
0x1400079fe  jmp     short loc_1400079C5
```
