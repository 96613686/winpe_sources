# CDescriptor_SERVER_INFO::_Init(ulong)

- ea: `0x180008460`
- end: `0x1800084ab`
- name: `?_Init@CDescriptor_SERVER_INFO@@UEAAEK@Z`
- size: `75`
- prototype: `unsigned __int8 __fastcall(CDescriptor_SERVER_INFO *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008460`

## pseudocode

```c
unsigned __int8 __fastcall CDescriptor_SERVER_INFO::_Init(CDescriptor_SERVER_INFO *this, int a2)
{
  unsigned __int8 result; // al
  int v3; // edx

  result = 1;
  v3 = a2 - 100;
  if ( v3 )
  {
    if ( v3 != 1 )
      return 0;
    *((_DWORD *)this + 17) = 40;
    *((_DWORD *)this + 5) = 8;
    *((_DWORD *)this + 6) = 32;
    *((_QWORD *)this + 12) = 5;
    *((_DWORD *)this + 26) = 2;
  }
  else
  {
    *((_DWORD *)this + 17) = 16;
    *((_DWORD *)this + 5) = 8;
  }
  *((_DWORD *)this + 20) = 500;
  return result;
}

```

## disassembly

```asm
0x180008460  mov     al, 1
0x180008462  sub     edx, 64h ; 'd'
0x180008465  jz      short loc_180008495
0x180008467  cmp     edx, 1
0x18000846a  jz      short loc_18000846F
0x18000846c  xor     al, al
0x18000846e  retn
0x18000846f  mov     dword ptr [rcx+44h], 28h ; '('
0x180008476  mov     dword ptr [rcx+14h], 8
0x18000847d  mov     dword ptr [rcx+18h], 20h ; ' '
0x180008484  mov     qword ptr [rcx+60h], 5
0x18000848c  mov     dword ptr [rcx+68h], 2
0x180008493  jmp     short loc_1800084A3
0x180008495  mov     dword ptr [rcx+44h], 10h
0x18000849c  mov     dword ptr [rcx+14h], 8
0x1800084a3  mov     dword ptr [rcx+50h], 1F4h
0x1800084aa  retn
```
