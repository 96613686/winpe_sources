# CDetourDis::CopyBytesJump(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400033c0`
- end: `0x140003423`
- name: `?CopyBytesJump@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `99`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400033c0`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyBytesJump(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // r10
  int v6; // ecx
  unsigned __int8 *result; // rax

  v4 = (char)a4[1];
  **((_QWORD **)this + 4) = &a4[v4 + 2];
  v6 = v4 - (_DWORD)a3 + (_DWORD)a4;
  if ( *a4 == 0xEB )
  {
    *a3 = -23;
    result = a4 + 2;
    *(_DWORD *)(a3 + 1) = v6 - 3;
    **((_DWORD **)this + 5) = 3;
  }
  else
  {
    *a3 = 15;
    a3[1] = *a4 & 0xF | 0x80;
    *(_DWORD *)(a3 + 2) = v6 - 4;
    **((_DWORD **)this + 5) = 4;
    return a4 + 2;
  }
  return result;
}

```

## disassembly

```asm
0x1400033c0  movsx   r10, byte ptr [r9+1]
0x1400033c5  lea     rdx, [r9+2]
0x1400033c9  mov     rax, [rcx+20h]
0x1400033cd  add     rdx, r10
0x1400033d0  sub     r10d, r8d
0x1400033d3  mov     r11, rcx
0x1400033d6  mov     [rax], rdx
0x1400033d9  cmp     byte ptr [r9], 0EBh
0x1400033dd  lea     ecx, [r10+r9]
0x1400033e1  jnz     short loc_1400033FD
0x1400033e3  mov     byte ptr [r8], 0E9h
0x1400033e7  lea     rax, [r9+2]
0x1400033eb  add     ecx, 0FFFFFFFDh
0x1400033ee  mov     [r8+1], ecx
0x1400033f2  mov     rcx, [r11+28h]
0x1400033f6  mov     dword ptr [rcx], 3
0x1400033fc  retn
0x1400033fd  mov     byte ptr [r8], 0Fh
0x140003401  movzx   eax, byte ptr [r9]
0x140003405  and     al, 0Fh
0x140003407  or      al, 80h
0x140003409  mov     [r8+1], al
0x14000340d  lea     eax, [rcx-4]
0x140003410  mov     [r8+2], eax
0x140003414  mov     rax, [r11+28h]
0x140003418  mov     dword ptr [rax], 4
0x14000341e  lea     rax, [r9+2]
0x140003422  retn
```
