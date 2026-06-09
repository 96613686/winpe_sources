# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)

- ea: `0x180018b6c`
- end: `0x180018ba6`
- name: `?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z`
- size: `58`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001964c`
- `0x180020dbc`
- `0x1800210fc`
- `0x180021208`

## callees

- `0x180007cc4`
- `0x180018b6c`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
        unsigned __int16 **a1,
        __int64 a2)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  unsigned __int16 v4; // cx

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v2 = *a1;
  v3 = a2 - (_QWORD)*a1;
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != *(unsigned __int16 *)((char *)v2 + v3) )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return v4 < *(unsigned __int16 *)((char *)v2 + v3) ? -1 : 1;
}

```

## disassembly

```asm
0x180018b6c  sub     rsp, 28h
0x180018b70  test    rdx, rdx
0x180018b73  jnz     short loc_180018B80
0x180018b75  mov     ecx, 80004005h; int
0x180018b7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018b80  mov     rax, [rcx]
0x180018b83  sub     rdx, rax
0x180018b86  movzx   ecx, word ptr [rax]
0x180018b89  cmp     cx, [rax+rdx]
0x180018b8d  jnz     short loc_180018B9C
0x180018b8f  add     rax, 2
0x180018b93  test    cx, cx
0x180018b96  jnz     short loc_180018B86
0x180018b98  xor     eax, eax
0x180018b9a  jmp     short loc_180018BA1
0x180018b9c  sbb     eax, eax
0x180018b9e  or      eax, 1
0x180018ba1  add     rsp, 28h
0x180018ba5  retn
```
