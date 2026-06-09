# VideoNewCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,int,long)

- ea: `0x18001a064`
- end: `0x18001a165`
- name: `?VideoNewCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1HJ@Z`
- size: `257`
- prototype: `void *__fastcall(enum tagColorConvertStatus *, const struct tagBITMAPINFOHEADER *, const struct tagBITMAPINFOHEADER *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a050`

## callees

- `0x18000a6d0`
- `0x18000a6dc`
- `0x180010bec`
- `0x18001a064`
- `0x18001f874`

## pseudocode

```c
_QWORD *__fastcall VideoNewCCCreate(
        enum tagColorConvertStatus *a1,
        const struct tagBITMAPINFOHEADER *a2,
        const struct tagBITMAPINFOHEADER *a3,
        int a4)
{
  LONG biWidth; // r15d
  LONG biHeight; // esi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v12; // rcx
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  LONG v14; // [rsp+38h] [rbp-40h]
  LONG v15; // [rsp+3Ch] [rbp-3Ch]

  biWidth = a2->biWidth;
  biHeight = -a2->biHeight;
  if ( a2->biHeight > 0 )
    biHeight = a2->biHeight;
  if ( a4 == 1 )
  {
    a3->biBitCount = 12;
    a3->biCompression = 825308240;
  }
  v9 = operator new(0x3C58u);
  v10 = v9;
  if ( v9 )
  {
    v9[1908] = 0;
    *((_DWORD *)v9 + 3819) = -1;
    *((_DWORD *)v9 + 3818) = -1;
    Init((struct DIRECTCOLORCONVFRM *)v9);
    v13 = 0;
    v14 = biWidth;
    v15 = biHeight;
    initEnCC(a1, a2, a3, v10, &v13);
    if ( !*(_DWORD *)a1 )
    {
      *((_DWORD *)v10 + 3821) = 0;
      return v10;
    }
    if ( *v10 )
    {
      operator delete((void *)*v10);
      *v10 = 0;
    }
    v12 = (void *)v10[1];
    if ( v12 )
    {
      operator delete(v12);
      v10[1] = 0;
    }
    operator delete(v10);
  }
  else
  {
    *(_DWORD *)a1 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a064  push    rbx
0x18001a066  push    rbp
0x18001a067  push    rsi
0x18001a068  push    rdi
0x18001a069  push    r14
0x18001a06b  push    r15
0x18001a06d  sub     rsp, 48h
0x18001a071  mov     esi, [rdx+8]
0x18001a074  mov     rdi, r8
0x18001a077  mov     r15d, [rdx+4]
0x18001a07b  neg     esi
0x18001a07d  mov     rbp, rdx
0x18001a080  mov     r14, rcx
0x18001a083  cmovs   esi, [rdx+8]
0x18001a087  cmp     r9d, 1
0x18001a08b  jnz     short loc_18001A09C
0x18001a08d  mov     word ptr [r8+0Eh], 0Ch
0x18001a094  mov     dword ptr [r8+10h], 31313450h
0x18001a09c  mov     ecx, 3C58h; Size
0x18001a0a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a0a6  mov     rbx, rax
0x18001a0a9  test    rax, rax
0x18001a0ac  jz      loc_18001A14F
0x18001a0b2  mov     qword ptr [rax+3BA0h], 0
0x18001a0bd  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x18001a0c0  or      eax, 0FFFFFFFFh
0x18001a0c3  mov     [rbx+3BACh], eax
0x18001a0c9  mov     [rbx+3BA8h], eax
0x18001a0cf  call    ?Init@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; Init(DIRECTCOLORCONVFRM *)
0x18001a0d4  lea     rax, [rsp+78h+var_48]
0x18001a0d9  mov     [rsp+78h+var_48], 0
0x18001a0e2  mov     r9, rbx
0x18001a0e5  mov     [rsp+78h+var_58], rax
0x18001a0ea  mov     r8, rdi
0x18001a0ed  mov     [rsp+78h+var_40], r15d
0x18001a0f2  mov     rdx, rbp
0x18001a0f5  mov     [rsp+78h+var_3C], esi
0x18001a0f9  mov     rcx, r14
0x18001a0fc  call    ?initEnCC@@YAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1PEAUDIRECTCOLORCONVFRM@@VCRct@@J@Z; initEnCC(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,DIRECTCOLORCONVFRM *,CRct,long)
0x18001a101  cmp     dword ptr [r14], 0
0x18001a105  jnz     short loc_18001A116
0x18001a107  mov     dword ptr [rbx+3BB4h], 0
0x18001a111  mov     rax, rbx
0x18001a114  jmp     short loc_18001A158
0x18001a116  mov     rcx, [rbx]; void *
0x18001a119  test    rcx, rcx
0x18001a11c  jz      short loc_18001A12A
0x18001a11e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a123  mov     qword ptr [rbx], 0
0x18001a12a  mov     rcx, [rbx+8]; void *
0x18001a12e  test    rcx, rcx
0x18001a131  jz      short loc_18001A140
0x18001a133  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a138  mov     qword ptr [rbx+8], 0
0x18001a140  mov     edx, 3C58h; unsigned __int64
0x18001a145  mov     rcx, rbx; void *
0x18001a148  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a14d  jmp     short loc_18001A156
0x18001a14f  mov     dword ptr [r14], 1
0x18001a156  xor     eax, eax
0x18001a158  add     rsp, 48h
0x18001a15c  pop     r15
0x18001a15e  pop     r14
0x18001a160  pop     rdi
0x18001a161  pop     rsi
0x18001a162  pop     rbp
0x18001a163  pop     rbx
0x18001a164  retn
```
