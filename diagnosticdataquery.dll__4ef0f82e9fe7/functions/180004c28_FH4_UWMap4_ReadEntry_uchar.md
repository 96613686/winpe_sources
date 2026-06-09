# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x180004c28`
- end: `0x180004cc4`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `156`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047a0`
- `0x180004cf4`
- `0x180004dc8`

## callees

- `0x180004c28`

## pseudocode

```c
void __fastcall FH4::UWMap4::ReadEntry(FH4::UWMap4 *this, unsigned __int8 **a2)
{
  __int64 v4; // rcx
  unsigned __int8 *v5; // r8
  unsigned int v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int *v10; // rdx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax

  v4 = **a2 & 0xF;
  v5 = &(*a2)[-*((char *)&FH4::s_negLengthTab + v4)];
  v6 = *((_DWORD *)v5 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v4);
  *a2 = v5;
  v7 = v6 & 3;
  *((_DWORD *)this + 4) = v6 >> 2;
  *((_DWORD *)this + 5) = v7;
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    v9 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v9;
    v10 = (int *)*a2;
    v11 = *(_BYTE *)v10 & 0xF;
    v12 = (unsigned __int8 *)v10 - *((char *)&FH4::s_negLengthTab + v11);
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *a2 = v12;
    *((_DWORD *)this + 7) = v13;
  }
  else if ( v7 == 3 )
  {
    v8 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v8;
  }
}

```

## disassembly

```asm
0x180004c28  mov     r8, [rdx]
0x180004c2b  lea     r11, cs:180000000h
0x180004c32  mov     r10, rcx
0x180004c35  mov     r9, rdx
0x180004c38  movzx   ecx, byte ptr [r8]
0x180004c3c  and     ecx, 0Fh
0x180004c3f  movsx   rax, byte ptr [rcx+r11+10238h]
0x180004c48  mov     cl, [rcx+r11+10248h]
0x180004c50  sub     r8, rax
0x180004c53  mov     eax, [r8-4]
0x180004c57  shr     eax, cl
0x180004c59  mov     ecx, eax
0x180004c5b  mov     [rdx], r8
0x180004c5e  and     ecx, 3
0x180004c61  shr     eax, 2
0x180004c64  mov     [r10+10h], eax
0x180004c68  mov     [r10+14h], ecx
0x180004c6c  lea     eax, [rcx-1]
0x180004c6f  cmp     eax, 1
0x180004c72  jbe     short loc_180004C8A
0x180004c74  cmp     ecx, 3
0x180004c77  jnz     short locret_180004CC3
0x180004c79  mov     rax, [rdx]
0x180004c7c  mov     ecx, [rax]
0x180004c7e  add     rax, 4
0x180004c82  mov     [rdx], rax
0x180004c85  mov     [r10+18h], ecx
0x180004c89  retn
0x180004c8a  mov     rax, [rdx]
0x180004c8d  mov     ecx, [rax]
0x180004c8f  add     rax, 4
0x180004c93  mov     [rdx], rax
0x180004c96  mov     [r10+18h], ecx
0x180004c9a  mov     rdx, [rdx]
0x180004c9d  movzx   ecx, byte ptr [rdx]
0x180004ca0  and     ecx, 0Fh
0x180004ca3  movsx   rax, byte ptr [rcx+r11+10238h]
0x180004cac  mov     cl, [rcx+r11+10248h]
0x180004cb4  sub     rdx, rax
0x180004cb7  mov     eax, [rdx-4]
0x180004cba  shr     eax, cl
0x180004cbc  mov     [r9], rdx
0x180004cbf  mov     [r10+1Ch], eax
0x180004cc3  retn
```
