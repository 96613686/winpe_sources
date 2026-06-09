# CLogScript::ResetInetLogLine(_INETLOGLINE &)

- ea: `0x18000894c`
- end: `0x1800089d7`
- name: `?ResetInetLogLine@CLogScript@@AEAAXAEAU_INETLOGLINE@@@Z`
- size: `139`
- prototype: `void __fastcall(CLogScript *__hidden this, struct _INETLOGLINE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000849c`
- `0x1800088b0`

## callees

- `0x18000894c`

## pseudocode

```c
void __fastcall CLogScript::ResetInetLogLine(CLogScript *this, struct _INETLOGLINE *a2)
{
  int v2; // eax
  int v3; // ecx
  __int64 v4; // rax

  v2 = *((_DWORD *)a2 + 40) - 1;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  v3 = 0;
  *((_QWORD *)a2 + 2) = 0;
  *((_QWORD *)a2 + 3) = 0;
  *((_QWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_QWORD *)a2 + 7) = 0;
  *((_QWORD *)a2 + 8) = 0;
  *((_QWORD *)a2 + 9) = 0;
  *((_QWORD *)a2 + 10) = 0;
  *((_QWORD *)a2 + 11) = 0;
  *((_QWORD *)a2 + 12) = 0;
  *((_QWORD *)a2 + 13) = 0;
  *((_QWORD *)a2 + 15) = 0;
  *((_QWORD *)a2 + 16) = 0;
  *((_QWORD *)a2 + 14) = 0;
  *((_QWORD *)a2 + 17) = 0;
  *((_QWORD *)a2 + 18) = 0;
  *((_QWORD *)a2 + 19) = 0;
  if ( v2 > 0 )
  {
    do
    {
      v4 = v3++;
      *((_QWORD *)a2 + 5 * v4 + 25) = 0;
    }
    while ( v3 < *((_DWORD *)a2 + 40) - 1 );
  }
}

```

## disassembly

```asm
0x18000894c  mov     eax, [rdx+0A0h]
0x180008952  xor     r8d, r8d
0x180008955  dec     eax
0x180008957  mov     [rdx], r8
0x18000895a  mov     [rdx+8], r8
0x18000895e  mov     ecx, r8d
0x180008961  mov     [rdx+10h], r8
0x180008965  mov     [rdx+18h], r8
0x180008969  mov     [rdx+20h], r8
0x18000896d  mov     [rdx+28h], r8
0x180008971  mov     [rdx+30h], r8
0x180008975  mov     [rdx+38h], r8
0x180008979  mov     [rdx+40h], r8
0x18000897d  mov     [rdx+48h], r8
0x180008981  mov     [rdx+50h], r8
0x180008985  mov     [rdx+58h], r8
0x180008989  mov     [rdx+60h], r8
0x18000898d  mov     [rdx+68h], r8
0x180008991  mov     [rdx+78h], r8
0x180008995  mov     [rdx+80h], r8
0x18000899c  mov     [rdx+70h], r8
0x1800089a0  mov     [rdx+88h], r8
0x1800089a7  mov     [rdx+90h], r8
0x1800089ae  mov     [rdx+98h], r8
0x1800089b5  test    eax, eax
0x1800089b7  jle     short locret_1800089D6
0x1800089b9  movsxd  rax, ecx
0x1800089bc  inc     ecx
0x1800089be  add     rax, 5
0x1800089c2  lea     rax, [rax+rax*4]
0x1800089c6  mov     [rdx+rax*8], r8
0x1800089ca  mov     eax, [rdx+0A0h]
0x1800089d0  dec     eax
0x1800089d2  cmp     ecx, eax
0x1800089d4  jl      short loc_1800089B9
0x1800089d6  retn
```
