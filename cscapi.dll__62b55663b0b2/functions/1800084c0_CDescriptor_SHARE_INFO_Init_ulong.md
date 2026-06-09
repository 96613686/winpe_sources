# CDescriptor_SHARE_INFO::_Init(ulong)

- ea: `0x1800084c0`
- end: `0x1800084f5`
- name: `?_Init@CDescriptor_SHARE_INFO@@UEAAEK@Z`
- size: `53`
- prototype: `unsigned __int8 __fastcall(CDescriptor_SHARE_INFO *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800084c0`

## pseudocode

```c
unsigned __int8 __fastcall CDescriptor_SHARE_INFO::_Init(CDescriptor_SHARE_INFO *this, int a2)
{
  unsigned __int8 result; // al

  result = 1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      *((_DWORD *)this + 17) = 24;
      *((_DWORD *)this + 5) = 0;
      *((_DWORD *)this + 6) = 16;
      *((_DWORD *)this + 22) = 0;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    *((_DWORD *)this + 17) = 8;
    *((_DWORD *)this + 5) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800084c0  xor     r8d, r8d
0x1800084c3  mov     al, 1
0x1800084c5  test    edx, edx
0x1800084c7  jz      short loc_1800084E9
0x1800084c9  cmp     edx, 1
0x1800084cc  jz      short loc_1800084D2
0x1800084ce  mov     al, r8b
0x1800084d1  retn
0x1800084d2  mov     dword ptr [rcx+44h], 18h
0x1800084d9  mov     [rcx+14h], r8d
0x1800084dd  mov     dword ptr [rcx+18h], 10h
0x1800084e4  mov     [rcx+58h], r8d
0x1800084e8  retn
0x1800084e9  mov     dword ptr [rcx+44h], 8
0x1800084f0  mov     [rcx+14h], r8d
0x1800084f4  retn
```
