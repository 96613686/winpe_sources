# CdConvertNameToCdName

- ea: `0x140016024`
- end: `0x14001608b`
- name: `CdConvertNameToCdName`
- size: `103`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c8b4`
- `0x140011138`
- `0x140012a14`

## callees

- `0x140016024`

## pseudocode

```c
__int64 __fastcall CdConvertNameToCdName(__int64 a1, unsigned __int16 *a2)
{
  unsigned __int64 v2; // r9
  __int64 v3; // r8
  _WORD *v4; // r11
  _WORD *v5; // rax
  __int64 result; // rax
  unsigned __int16 v7; // r9

  v2 = *a2;
  v3 = 0;
  v4 = (_WORD *)*((_QWORD *)a2 + 1);
  v5 = v4;
  if ( *a2 )
  {
    do
    {
      if ( *v5 == 59 )
        break;
      ++v5;
      v3 = (unsigned int)(v3 + 2);
    }
    while ( (unsigned int)v3 < (unsigned int)v2 );
  }
  result = 0;
  a2[8] = 0;
  if ( v3 + 2 < v2 )
  {
    v7 = v2 - v3 - 2;
    result = (__int64)v4 + (unsigned int)v3 + 2;
    a2[8] = v7;
    *((_QWORD *)a2 + 3) = result;
    a2[9] = v7;
  }
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x140016024  mov     [rsp+arg_0], rbx
0x140016029  movzx   r9d, word ptr [rdx]
0x14001602d  xor     r8d, r8d
0x140016030  mov     r11, [rdx+8]
0x140016034  mov     rax, r11
0x140016037  lea     ebx, [r8+2]
0x14001603b  test    r9d, r9d
0x14001603e  jz      short loc_140016051
0x140016040  cmp     word ptr [rax], 3Bh ; ';'
0x140016044  jz      short loc_140016051
0x140016046  add     rax, rbx
0x140016049  add     r8d, ebx
0x14001604c  cmp     r8d, r9d
0x14001604f  jb      short loc_140016040
0x140016051  xor     eax, eax
0x140016053  mov     r10d, r8d
0x140016056  lea     rcx, [r8+2]
0x14001605a  mov     [rdx+10h], ax
0x14001605e  cmp     rcx, r9
0x140016061  jnb     short loc_140016080
0x140016063  sub     r9w, r8w
0x140016067  lea     rax, [r11+2]
0x14001606b  sub     r9w, bx
0x14001606f  add     rax, r10
0x140016072  mov     [rdx+10h], r9w
0x140016077  mov     [rdx+18h], rax
0x14001607b  mov     [rdx+12h], r9w
0x140016080  mov     rbx, [rsp+arg_0]
0x140016085  mov     [rdx], r8w
0x140016089  retn
```
