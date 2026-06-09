# ttfdQueryGlyphOutline(_TT_FONTCONTEXT *,ulong,_GLYPHDATA *,_PATHOBJ *)

- ea: `0x140029a44`
- end: `0x140029b9d`
- name: `?ttfdQueryGlyphOutline@@YAHPEAU_TT_FONTCONTEXT@@KPEAU_GLYPHDATA@@PEAU_PATHOBJ@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(struct _TT_FONTCONTEXT *, unsigned int, struct _GLYPHDATA *, PATHOBJ *ppo)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015890`

## callees

- `0x140026b1c`
- `0x140029a44`
- `0x140029ba4`
- `0x1400517c8`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140029b77`
- `KERNEL32!GlobalFree` at `0x140029b8c`
- `KERNEL32!GlobalFree` at `0x140029b77`
- `KERNEL32!GlobalFree` at `0x140029b8c`
- `KERNEL32!GlobalAlloc` at `0x140029ade`
- `KERNEL32!GlobalAlloc` at `0x140029ade`

## pseudocode

```c
__int64 __fastcall ttfdQueryGlyphOutline(
        struct _TT_FONTCONTEXT *a1,
        unsigned int a2,
        struct _GLYPHDATA *a3,
        PATHOBJ *ppo)
{
  int v4; // eax
  int TrueTypeOutlineVertical; // eax
  signed int TTOutline; // eax
  unsigned int v12; // edi
  struct tagTTPOLYGONHEADER *v13; // rax
  int v14; // eax
  unsigned int Path; // eax
  void *v16; // rcx
  unsigned int v17; // edi
  void *v18; // rcx

  v4 = *((_DWORD *)a1 + 77);
  if ( !ppo )
  {
    if ( v4 )
      TrueTypeOutlineVertical = lQueryTrueTypeOutlineVertical(a1, 0, a2, 1, 0, a3, 0, 0);
    else
      TrueTypeOutlineVertical = lQueryTTOutline(a1, 0, a2, 1, 0, a3, 0, 0);
    return !TrueTypeOutlineVertical;
  }
  if ( v4 )
    TTOutline = lQueryTrueTypeOutlineVertical(a1, 0, a2, 0, 0, 0, 0, 0);
  else
    TTOutline = lQueryTTOutline(a1, 0, a2, 0, 0, 0, 0, 0);
  v12 = TTOutline;
  if ( TTOutline == -1 )
    return 0;
  if ( TTOutline )
  {
    v13 = (struct tagTTPOLYGONHEADER *)GlobalAlloc(0, TTOutline);
    *((_QWORD *)a1 + 3) = v13;
    if ( v13 )
      goto LABEL_11;
    return 0;
  }
  *((_QWORD *)a1 + 3) = 0;
  v13 = 0;
LABEL_11:
  if ( *((_DWORD *)a1 + 77) )
    v14 = lQueryTrueTypeOutlineVertical(a1, 0, a2, 0, 0, a3, v12, v13);
  else
    v14 = lQueryTTOutline(a1, 0, a2, 0, 0, a3, v12, v13);
  if ( v14 == -1 )
  {
    v18 = (void *)*((_QWORD *)a1 + 3);
    if ( v18 )
    {
      GlobalFree(v18);
      *((_QWORD *)a1 + 3) = 0;
    }
    return 0;
  }
  Path = bGeneratePath(ppo, *((POINTFIX **)a1 + 3), v12, 0, 0, 0);
  v16 = (void *)*((_QWORD *)a1 + 3);
  v17 = Path;
  if ( v16 )
  {
    GlobalFree(v16);
    *((_QWORD *)a1 + 3) = 0;
  }
  return v17;
}

```

## disassembly

```asm
0x140029a44  mov     r11, rsp
0x140029a47  push    rbx
0x140029a48  push    rbp
0x140029a49  push    rsi
0x140029a4a  push    rdi
0x140029a4b  push    r14
0x140029a4d  push    r15
0x140029a4f  sub     rsp, 48h
0x140029a53  mov     eax, [rcx+134h]
0x140029a59  xor     r15d, r15d
0x140029a5c  mov     rbp, r8
0x140029a5f  mov     [r11-40h], r15
0x140029a63  mov     r8d, edx; unsigned int
0x140029a66  mov     [r11-48h], r15d
0x140029a6a  mov     esi, edx
0x140029a6c  mov     r14, r9
0x140029a6f  xor     edx, edx; int
0x140029a71  mov     rbx, rcx
0x140029a74  test    r9, r9
0x140029a77  jnz     short loc_140029AAC
0x140029a79  mov     [r11-50h], rbp
0x140029a7d  lea     r9d, [r14+1]; int
0x140029a81  mov     [r11-58h], r15d
0x140029a85  test    eax, eax
0x140029a87  jnz     loc_140029B50
0x140029a8d  call    ?lQueryTTOutline@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTTOutline(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029a92  test    eax, eax
0x140029a94  jnz     loc_140029B96
0x140029a9a  mov     eax, 1
0x140029a9f  add     rsp, 48h
0x140029aa3  pop     r15
0x140029aa5  pop     r14
0x140029aa7  pop     rdi
0x140029aa8  pop     rsi
0x140029aa9  pop     rbp
0x140029aaa  pop     rbx
0x140029aab  retn
0x140029aac  xor     r9d, r9d; int
0x140029aaf  mov     [rsp+78h+var_50], r15; struct _GLYPHDATA *
0x140029ab4  mov     dword ptr [rsp+78h+var_58], r15d; int
0x140029ab9  test    eax, eax
0x140029abb  jnz     loc_140029B5A
0x140029ac1  call    ?lQueryTTOutline@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTTOutline(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029ac6  mov     edi, eax
0x140029ac8  cmp     eax, 0FFFFFFFFh
0x140029acb  jz      loc_140029B96
0x140029ad1  test    eax, eax
0x140029ad3  jz      loc_140029B6B
0x140029ad9  movsxd  rdx, eax; dwBytes
0x140029adc  xor     ecx, ecx; uFlags
0x140029ade  call    cs:__imp_GlobalAlloc
0x140029ae4  mov     [rbx+18h], rax
0x140029ae8  test    rax, rax
0x140029aeb  jz      loc_140029B96
0x140029af1  mov     [rsp+78h+var_40], rax; struct tagTTPOLYGONHEADER *
0x140029af6  xor     r9d, r9d; int
0x140029af9  mov     [rsp+78h+var_48], edi; unsigned int
0x140029afd  xor     edx, edx; int
0x140029aff  mov     r8d, esi; unsigned int
0x140029b02  mov     [rsp+78h+var_50], rbp; struct _GLYPHDATA *
0x140029b07  mov     rcx, rbx; struct _TT_FONTCONTEXT *
0x140029b0a  mov     dword ptr [rsp+78h+var_58], r15d; int
0x140029b0f  cmp     [rbx+134h], r15d
0x140029b16  jnz     short loc_140029B64
0x140029b18  call    ?lQueryTTOutline@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTTOutline(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029b1d  cmp     eax, 0FFFFFFFFh
0x140029b20  jz      short loc_140029B83
0x140029b22  mov     rdx, [rbx+18h]; struct tagTTPOLYGONHEADER *
0x140029b26  xor     r9d, r9d; unsigned int *
0x140029b29  mov     dword ptr [rsp+78h+var_50], r15d; unsigned int
0x140029b2e  mov     r8d, edi; unsigned int
0x140029b31  mov     rcx, r14; ppo
0x140029b34  mov     [rsp+78h+var_58], r15; struct tagTTPOLYGONHEADER *
0x140029b39  call    ?bGeneratePath@@YAHPEAU_PATHOBJ@@PEAUtagTTPOLYGONHEADER@@KPEAK1K@Z; bGeneratePath(_PATHOBJ *,tagTTPOLYGONHEADER *,ulong,ulong *,tagTTPOLYGONHEADER *,ulong)
0x140029b3e  mov     rcx, [rbx+18h]; struct _TT_FONTCONTEXT *
0x140029b42  mov     edi, eax
0x140029b44  test    rcx, rcx
0x140029b47  jnz     short loc_140029B77
0x140029b49  mov     eax, edi
0x140029b4b  jmp     loc_140029A9F
0x140029b50  call    ?lQueryTrueTypeOutlineVertical@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTrueTypeOutlineVertical(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029b55  jmp     loc_140029A92
0x140029b5a  call    ?lQueryTrueTypeOutlineVertical@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTrueTypeOutlineVertical(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029b5f  jmp     loc_140029AC6
0x140029b64  call    ?lQueryTrueTypeOutlineVertical@@YAJPEAU_TT_FONTCONTEXT@@HKHHPEAU_GLYPHDATA@@KPEAUtagTTPOLYGONHEADER@@@Z; lQueryTrueTypeOutlineVertical(_TT_FONTCONTEXT *,int,ulong,int,int,_GLYPHDATA *,ulong,tagTTPOLYGONHEADER *)
0x140029b69  jmp     short loc_140029B1D
0x140029b6b  mov     [rbx+18h], r15
0x140029b6f  mov     rax, r15
0x140029b72  jmp     loc_140029AF1
0x140029b77  call    cs:__imp_GlobalFree
0x140029b7d  mov     [rbx+18h], r15
0x140029b81  jmp     short loc_140029B49
0x140029b83  mov     rcx, [rbx+18h]; hMem
0x140029b87  test    rcx, rcx
0x140029b8a  jz      short loc_140029B96
0x140029b8c  call    cs:__imp_GlobalFree
0x140029b92  mov     [rbx+18h], r15
0x140029b96  xor     eax, eax
0x140029b98  jmp     loc_140029A9F
```
