# PerfGetLangId(ulong,uchar,ushort *,ulong)

- ea: `0x180010328`
- end: `0x180010428`
- name: `?PerfGetLangId@@YAXKEPEAGK@Z`
- size: `256`
- prototype: `void __fastcall(unsigned int, unsigned __int8, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093a8`
- `0x180010f28`
- `0x180011180`
- `0x1800113b0`

## callees

- `0x180010328`

## pseudocode

```c
void __fastcall PerfGetLangId(unsigned __int16 a1, char a2, unsigned __int16 *a3, unsigned int a4)
{
  if ( a2 )
  {
    *a3 = (char)((HIBYTE(a1) & 0xF) + ((HIBYTE(a1) & 0xFu) < 0xA ? 48 : 87));
    a3[1] = (char)(((unsigned __int8)a1 >> 4) + ((unsigned __int8)((unsigned __int8)a1 >> 4) < 0xAu ? 48 : 87));
    a3[2] = (char)((a1 & 0xF) + ((a1 & 0xFu) < 0xA ? 48 : 87));
    a3[3] = 0;
  }
  else if ( a4 >= 5 )
  {
    *a3 = (char)((a1 >> 12) + 87 + ((unsigned __int16)(a1 >> 12) < 0xAu ? 0xD9 : 0));
    a3[1] = (char)((HIBYTE(a1) & 0xF) + 87 + ((HIBYTE(a1) & 0xFu) < 0xA ? 0xD9 : 0));
    a3[2] = (char)(((unsigned __int8)a1 >> 4) + ((unsigned __int8)((unsigned __int8)a1 >> 4) < 0xAu ? 48 : 87));
    a3[3] = (char)((a1 & 0xF) + ((a1 & 0xFu) < 0xA ? 48 : 87));
    a3[4] = 0;
  }
}

```

## disassembly

```asm
0x180010328  mov     r10d, ecx
0x18001032b  test    dl, dl
0x18001032d  jz      short loc_180010397
0x18001032f  mov     r9w, 0Ah
0x180010334  mov     r11b, 0D9h
0x180010337  movzx   edx, r10w
0x18001033b  shr     dx, 8
0x18001033f  and     dx, 0Fh
0x180010343  cmp     dx, r9w
0x180010347  sbb     al, al
0x180010349  shr     cx, 4
0x18001034d  and     al, r11b
0x180010350  and     cx, 0Fh
0x180010354  add     al, 57h ; 'W'
0x180010356  add     al, dl
0x180010358  movsx   eax, al
0x18001035b  cmp     cx, r9w
0x18001035f  mov     [r8], ax
0x180010363  sbb     al, al
0x180010365  and     r10w, 0Fh
0x18001036a  and     al, r11b
0x18001036d  add     al, 57h ; 'W'
0x18001036f  add     al, cl
0x180010371  movsx   eax, al
0x180010374  cmp     r10w, r9w
0x180010378  mov     [r8+2], ax
0x18001037d  sbb     al, al
0x18001037f  and     al, r11b
0x180010382  add     al, 57h ; 'W'
0x180010384  add     al, r10b
0x180010387  movsx   eax, al
0x18001038a  mov     [r8+4], ax
0x18001038f  xor     eax, eax
0x180010391  mov     [r8+6], ax
0x180010396  retn
0x180010397  cmp     r9d, 5
0x18001039b  jb      locret_180010427
0x1800103a1  shr     cx, 0Ch
0x1800103a5  mov     r9w, 0Ah
0x1800103aa  cmp     cx, r9w
0x1800103ae  mov     r11b, 0D9h
0x1800103b1  sbb     al, al
0x1800103b3  add     cl, 57h ; 'W'
0x1800103b6  and     al, r11b
0x1800103b9  add     al, cl
0x1800103bb  movzx   ecx, r10w
0x1800103bf  movsx   eax, al
0x1800103c2  mov     [r8], ax
0x1800103c6  shr     cx, 8
0x1800103ca  and     cx, 0Fh
0x1800103ce  cmp     cx, r9w
0x1800103d2  sbb     al, al
0x1800103d4  add     cl, 57h ; 'W'
0x1800103d7  and     al, r11b
0x1800103da  add     al, cl
0x1800103dc  movzx   ecx, r10w
0x1800103e0  movsx   eax, al
0x1800103e3  mov     [r8+2], ax
0x1800103e8  shr     cx, 4
0x1800103ec  and     cx, 0Fh
0x1800103f0  cmp     cx, r9w
0x1800103f4  sbb     al, al
0x1800103f6  and     r10w, 0Fh
0x1800103fb  and     al, r11b
0x1800103fe  add     al, 57h ; 'W'
0x180010400  add     al, cl
0x180010402  movsx   eax, al
0x180010405  cmp     r10w, r9w
0x180010409  mov     [r8+4], ax
0x18001040e  sbb     al, al
0x180010410  and     al, r11b
0x180010413  add     al, 57h ; 'W'
0x180010415  add     al, r10b
0x180010418  movsx   eax, al
0x18001041b  mov     [r8+6], ax
0x180010420  xor     eax, eax
0x180010422  mov     [r8+8], ax
0x180010427  retn
```
