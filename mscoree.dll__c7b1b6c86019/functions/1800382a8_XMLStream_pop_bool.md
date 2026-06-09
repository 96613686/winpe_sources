# XMLStream::pop(bool)

- ea: `0x1800382a8`
- end: `0x180038319`
- name: `?pop@XMLStream@@AEAAJ_N@Z`
- size: `113`
- prototype: `__int64 __fastcall(XMLStream *__hidden this, bool)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800360a0`
- `0x1800361a0`
- `0x1800362f0`
- `0x180036600`
- `0x1800367c0`
- `0x180036980`
- `0x180036cd0`
- `0x180036ee0`
- `0x180037050`
- `0x180037640`
- `0x180037720`
- `0x1800377f0`
- `0x180037970`
- `0x180037e00`
- `0x1800383d0`

## callees

- `0x180034cf0`
- `0x1800382a8`

## pseudocode

```c
__int64 __fastcall XMLStream::pop(XMLStream *this, char a2)
{
  int v2; // eax
  __int64 v3; // r9

  v2 = *((_DWORD *)this + 8);
  if ( !v2 )
    return 2147549183LL;
  v3 = *((_QWORD *)this + 3) + *((_DWORD *)this + 4) * (v2 - 1);
  if ( !v3 )
    return 2147549183LL;
  if ( *((_BYTE *)this + 204) && !*((_BYTE *)this + 205) && a2 && *((_DWORD *)this + 20) != *(_DWORD *)(v3 + 24) )
    return 3222070619LL;
  *(_QWORD *)this = *(_QWORD *)v3;
  *((_WORD *)this + 4) = *(_WORD *)(v3 + 8);
  *((_QWORD *)this + 22) = *(_QWORD *)(v3 + 16);
  RawStack::_pop((XMLStream *)((char *)this + 16));
  return 0;
}

```

## disassembly

```asm
0x1800382a8  sub     rsp, 28h
0x1800382ac  mov     eax, [rcx+20h]
0x1800382af  test    eax, eax
0x1800382b1  jz      short loc_18003830F
0x1800382b3  dec     eax
0x1800382b5  imul    eax, [rcx+10h]
0x1800382b9  movsxd  r9, eax
0x1800382bc  add     r9, [rcx+18h]
0x1800382c0  jz      short loc_18003830F
0x1800382c2  cmp     byte ptr [rcx+0CCh], 0
0x1800382c9  jz      short loc_1800382E8
0x1800382cb  cmp     byte ptr [rcx+0CDh], 0
0x1800382d2  jnz     short loc_1800382E8
0x1800382d4  test    dl, dl
0x1800382d6  jz      short loc_1800382E8
0x1800382d8  mov     eax, [r9+18h]
0x1800382dc  cmp     [rcx+50h], eax
0x1800382df  jz      short loc_1800382E8
0x1800382e1  mov     eax, 0C00CE55Bh
0x1800382e6  jmp     short loc_180038314
0x1800382e8  mov     rax, [r9]
0x1800382eb  mov     [rcx], rax
0x1800382ee  movzx   eax, word ptr [r9+8]
0x1800382f3  mov     [rcx+8], ax
0x1800382f7  mov     rax, [r9+10h]
0x1800382fb  mov     [rcx+0B0h], rax
0x180038302  add     rcx, 10h; this
0x180038306  call    ?_pop@RawStack@@IEAAPEADXZ; RawStack::_pop(void)
0x18003830b  xor     eax, eax
0x18003830d  jmp     short loc_180038314
0x18003830f  mov     eax, 8000FFFFh
0x180038314  add     rsp, 28h
0x180038318  retn
```
