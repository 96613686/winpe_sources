# ATL::AtlCrtErrorCheck(int)

- ea: `0x180002210`
- end: `0x180002254`
- name: `?AtlCrtErrorCheck@ATL@@YAHH@Z`
- size: `68`
- prototype: `__int64 __fastcall(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c4c`
- `0x180005c7c`
- `0x180008efc`
- `0x180009758`
- `0x18000a728`
- `0x18000ae30`

## callees

- `0x180002210`
- `0x180002338`

## pseudocode

```c
__int64 __fastcall ATL::AtlCrtErrorCheck(unsigned int a1)
{
  if ( a1 )
  {
    if ( a1 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( a1 == 22 || a1 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( a1 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  return a1;
}

```

## disassembly

```asm
0x180002210  sub     rsp, 28h
0x180002214  test    ecx, ecx
0x180002216  jz      short loc_18000224D
0x180002218  cmp     ecx, 0Ch
0x18000221b  jz      short loc_180002242
0x18000221d  cmp     ecx, 16h
0x180002220  jz      short loc_180002237
0x180002222  cmp     ecx, 22h ; '"'
0x180002225  jz      short loc_180002237
0x180002227  cmp     ecx, 50h ; 'P'
0x18000222a  jz      short loc_18000224D
0x18000222c  mov     ecx, 80004005h; int
0x180002231  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002237  mov     ecx, 80070057h; int
0x18000223c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002242  mov     ecx, 8007000Eh; int
0x180002247  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000224d  mov     eax, ecx
0x18000224f  add     rsp, 28h
0x180002253  retn
```
