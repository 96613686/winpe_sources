# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x180017024`
- end: `0x1800170c0`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `156`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180016c34`
- `0x1800170c8`
- `0x18001719c`

## callees

- `0x180017024`

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
  v5 = &(*a2)[-*((char *)qword_180082058 + v4)];
  v6 = *((_DWORD *)v5 - 1) >> *((_BYTE *)&qword_180082058[2] + v4);
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
    v12 = (unsigned __int8 *)v10 - *((char *)qword_180082058 + v11);
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&qword_180082058[2] + v11);
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
0x180017024  mov     r8, [rdx]
0x180017027  lea     r11, cs:180000000h
0x18001702e  mov     r10, rcx
0x180017031  mov     r9, rdx
0x180017034  movzx   ecx, byte ptr [r8]
0x180017038  and     ecx, 0Fh
0x18001703b  movsx   rax, byte ptr [rcx+r11+82058h]
0x180017044  mov     cl, [rcx+r11+82068h]
0x18001704c  sub     r8, rax
0x18001704f  mov     eax, [r8-4]
0x180017053  shr     eax, cl
0x180017055  mov     ecx, eax
0x180017057  mov     [rdx], r8
0x18001705a  and     ecx, 3
0x18001705d  shr     eax, 2
0x180017060  mov     [r10+10h], eax
0x180017064  mov     [r10+14h], ecx
0x180017068  lea     eax, [rcx-1]
0x18001706b  cmp     eax, 1
0x18001706e  jbe     short loc_180017086
0x180017070  cmp     ecx, 3
0x180017073  jnz     short locret_1800170BF
0x180017075  mov     rax, [rdx]
0x180017078  mov     ecx, [rax]
0x18001707a  add     rax, 4
0x18001707e  mov     [rdx], rax
0x180017081  mov     [r10+18h], ecx
0x180017085  retn
0x180017086  mov     rax, [rdx]
0x180017089  mov     ecx, [rax]
0x18001708b  add     rax, 4
0x18001708f  mov     [rdx], rax
0x180017092  mov     [r10+18h], ecx
0x180017096  mov     rdx, [rdx]
0x180017099  movzx   ecx, byte ptr [rdx]
0x18001709c  and     ecx, 0Fh
0x18001709f  movsx   rax, byte ptr [rcx+r11+82058h]
0x1800170a8  mov     cl, [rcx+r11+82068h]
0x1800170b0  sub     rdx, rax
0x1800170b3  mov     eax, [rdx-4]
0x1800170b6  shr     eax, cl
0x1800170b8  mov     [r9], rdx
0x1800170bb  mov     [r10+1Ch], eax
0x1800170bf  retn
```
