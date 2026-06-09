# QuickKey::Copy(uchar *,uint,Err &)

- ea: `0x10039890`
- end: `0x10039911`
- name: `?Copy@QuickKey@@QBEIPAEIAAVErr@@@Z`
- size: `129`
- prototype: `unsigned int __thiscall(QuickKey *__hidden this, unsigned __int8 *, unsigned int, struct Err *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001aaa0`
- `0x1002d6b0`
- `0x10032460`
- `0x10038650`
- `0x10058210`

## callees

- `0x10039890`
- `0x1005e7e8`
- `0x1005f07c`

## pseudocode

```c
const void *__thiscall QuickKey::Copy(const void **this, unsigned __int8 *a2, unsigned int a3, void **a4)
{
  if ( a3 >= (unsigned int)*this )
  {
    memcpy(a2, this[1], (size_t)*this);
    return *this;
  }
  else
  {
    if ( (int)*a4 < 8 )
    {
      if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
      {
        if ( a4[3] )
          operator delete[](a4[3]);
        if ( a4[4] )
          operator delete[](a4[4]);
      }
      *a4 = (void *)8;
      a4[1] = (void *)-1038;
      a4[2] = 0;
      a4[3] = 0;
      a4[4] = 0;
    }
    return *this;
  }
}

```

## disassembly

```asm
0x10039890  mov     edi, edi
0x10039892  push    ebp
0x10039893  mov     ebp, esp
0x10039895  push    edi
0x10039896  mov     edi, ecx
0x10039898  mov     eax, [edi]
0x1003989a  cmp     [ebp+arg_4], eax
0x1003989d  jnb     short loc_100398FB
0x1003989f  push    esi
0x100398a0  mov     esi, [ebp+arg_8]
0x100398a3  mov     eax, [esi]
0x100398a5  cmp     eax, 8
0x100398a8  jge     short loc_100398F3
0x100398aa  test    eax, 0FFFFFFFEh
0x100398af  jz      short loc_100398D1
0x100398b1  mov     eax, [esi+0Ch]
0x100398b4  test    eax, eax
0x100398b6  jz      short loc_100398C1
0x100398b8  push    eax; Block
0x100398b9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100398be  add     esp, 4
0x100398c1  mov     eax, [esi+10h]
0x100398c4  test    eax, eax
0x100398c6  jz      short loc_100398D1
0x100398c8  push    eax; Block
0x100398c9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100398ce  add     esp, 4
0x100398d1  mov     dword ptr [esi], 8
0x100398d7  mov     dword ptr [esi+4], 0FFFFFBF2h
0x100398de  mov     dword ptr [esi+8], 0
0x100398e5  mov     dword ptr [esi+0Ch], 0
0x100398ec  mov     dword ptr [esi+10h], 0
0x100398f3  mov     eax, [edi]
0x100398f5  pop     esi
0x100398f6  pop     edi
0x100398f7  pop     ebp
0x100398f8  retn    0Ch
0x100398fb  push    eax; Size
0x100398fc  push    dword ptr [edi+4]; Src
0x100398ff  push    [ebp+arg_0]; void *
0x10039902  call    _memcpy
0x10039907  mov     eax, [edi]
0x10039909  add     esp, 0Ch
0x1003990c  pop     edi
0x1003990d  pop     ebp
0x1003990e  retn    0Ch
```
