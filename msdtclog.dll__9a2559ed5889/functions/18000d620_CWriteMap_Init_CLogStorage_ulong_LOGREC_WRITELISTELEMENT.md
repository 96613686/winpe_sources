# CWriteMap::Init(CLogStorage *,ulong,_LOGREC *,_WRITELISTELEMENT *)

- ea: `0x18000d620`
- end: `0x18000d68e`
- name: `?Init@CWriteMap@@QEAAXPEAVCLogStorage@@KPEAU_LOGREC@@PEAU_WRITELISTELEMENT@@@Z`
- size: `110`
- prototype: `void __fastcall(CWriteMap *this, struct CLogStorage *, int, struct _LOGREC *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800084c8`
- `0x180008768`

## callees

- `0x18000d620`

## pseudocode

```c
void __fastcall CWriteMap::Init(CWriteMap *this, struct CLogStorage *a2, int a3, struct _LOGREC *a4)
{
  int v5; // ecx
  struct _LOGREC *v6; // rdx
  int v7; // ecx

  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 18) = 0;
  *(_DWORD *)this = a3;
  *((_QWORD *)this + 1) = a4;
  v5 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      v6 = a4;
      do
      {
        v5 += *((_DWORD *)v6 + 2);
        v6 = (struct _LOGREC *)((char *)v6 + 16);
        *((_DWORD *)this + 6) = v5;
        --a3;
      }
      while ( a3 );
    }
    *((_DWORD *)this + 10) = 0;
    *((_DWORD *)this + 14) = *((_DWORD *)a4 + 2);
    *((_QWORD *)this + 8) = *(_QWORD *)a4;
  }
  v7 = (v5 & 7) != 0 ? 8 - (v5 & 7) : 0;
  *((_DWORD *)this + 19) = v7;
  *((_DWORD *)this + 18) = v7;
}

```

## disassembly

```asm
0x18000d620  xor     r11d, r11d
0x18000d623  mov     [rcx+20h], rdx
0x18000d627  mov     [rcx+10h], r11
0x18000d62b  mov     r10, rcx
0x18000d62e  mov     [rcx+50h], r11d
0x18000d632  mov     [rcx+18h], r11d
0x18000d636  mov     [rcx+48h], r11d
0x18000d63a  mov     [rcx], r8d
0x18000d63d  mov     [rcx+8], r9
0x18000d641  mov     ecx, r11d
0x18000d644  test    r8d, r8d
0x18000d647  jz      short loc_18000D675
0x18000d649  test    r9, r9
0x18000d64c  jz      short loc_18000D662
0x18000d64e  mov     rdx, r9
0x18000d651  add     ecx, [rdx+8]
0x18000d654  lea     rdx, [rdx+10h]
0x18000d658  mov     [r10+18h], ecx
0x18000d65c  add     r8d, 0FFFFFFFFh
0x18000d660  jnz     short loc_18000D651
0x18000d662  mov     [r10+28h], r11d
0x18000d666  mov     eax, [r9+8]
0x18000d66a  mov     [r10+38h], eax
0x18000d66e  mov     rax, [r9]
0x18000d671  mov     [r10+40h], rax
0x18000d675  and     ecx, 7
0x18000d678  mov     eax, 8
0x18000d67d  sub     eax, ecx
0x18000d67f  neg     ecx
0x18000d681  sbb     ecx, ecx
0x18000d683  and     ecx, eax
0x18000d685  mov     [r10+4Ch], ecx
0x18000d689  mov     [r10+48h], ecx
0x18000d68d  retn
```
