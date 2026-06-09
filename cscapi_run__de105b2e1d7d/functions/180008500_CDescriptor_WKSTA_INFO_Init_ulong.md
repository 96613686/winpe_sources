# CDescriptor_WKSTA_INFO::_Init(ulong)

- ea: `0x180008500`
- end: `0x180008543`
- name: `?_Init@CDescriptor_WKSTA_INFO@@UEAAEK@Z`
- size: `67`
- prototype: `unsigned __int8 __fastcall(CDescriptor_WKSTA_INFO *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008500`

## pseudocode

```c
unsigned __int8 __fastcall CDescriptor_WKSTA_INFO::_Init(CDescriptor_WKSTA_INFO *this, int a2)
{
  unsigned __int8 result; // al
  int v3; // edx
  int v4; // edx

  result = 1;
  v3 = a2 - 100;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
        return 0;
      *((_DWORD *)this + 21) = 48;
    }
    else
    {
      *((_DWORD *)this + 21) = 40;
    }
    *((_DWORD *)this + 7) = 32;
  }
  else
  {
    *((_DWORD *)this + 21) = 32;
  }
  *((_DWORD *)this + 5) = 8;
  *((_DWORD *)this + 6) = 16;
  return result;
}

```

## disassembly

```asm
0x180008500  mov     al, 1
0x180008502  sub     edx, 64h ; 'd'
0x180008505  jz      short loc_18000852D
0x180008507  sub     edx, 1
0x18000850a  jz      short loc_180008524
0x18000850c  cmp     edx, 1
0x18000850f  jz      short loc_180008514
0x180008511  xor     al, al
0x180008513  retn
0x180008514  mov     dword ptr [rcx+54h], 30h ; '0'
0x18000851b  mov     dword ptr [rcx+1Ch], 20h ; ' '
0x180008522  jmp     short loc_180008534
0x180008524  mov     dword ptr [rcx+54h], 28h ; '('
0x18000852b  jmp     short loc_18000851B
0x18000852d  mov     dword ptr [rcx+54h], 20h ; ' '
0x180008534  mov     dword ptr [rcx+14h], 8
0x18000853b  mov     dword ptr [rcx+18h], 10h
0x180008542  retn
```
