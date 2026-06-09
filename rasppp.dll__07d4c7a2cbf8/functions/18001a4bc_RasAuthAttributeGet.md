# RasAuthAttributeGet

- ea: `0x18001a4bc`
- end: `0x18001a4df`
- name: `RasAuthAttributeGet`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003770`
- `0x1800126b8`
- `0x180012794`
- `0x180013bb4`
- `0x180017990`
- `0x1800198d8`
- `0x18001a9e4`
- `0x18001b910`
- `0x180026a5c`

## callees

- `0x18001a4bc`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGet(int a1, __int64 a2)
{
  unsigned int i; // r8d
  _DWORD *result; // rax

  if ( a2 )
  {
    for ( i = 0; ; ++i )
    {
      result = (_DWORD *)(a2 + 16LL * i);
      if ( !*result )
        break;
      if ( *result == a1 )
        return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001a4bc  test    rdx, rdx
0x18001a4bf  jz      short loc_18001A4DC
0x18001a4c1  xor     r8d, r8d
0x18001a4c4  mov     eax, r8d
0x18001a4c7  shl     rax, 4
0x18001a4cb  add     rax, rdx
0x18001a4ce  cmp     dword ptr [rax], 0
0x18001a4d1  jz      short loc_18001A4DC
0x18001a4d3  cmp     [rax], ecx
0x18001a4d5  jz      short locret_18001A4DE
0x18001a4d7  inc     r8d
0x18001a4da  jmp     short loc_18001A4C4
0x18001a4dc  xor     eax, eax
0x18001a4de  retn
```
