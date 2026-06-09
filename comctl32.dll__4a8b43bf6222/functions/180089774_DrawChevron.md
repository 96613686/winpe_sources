# DrawChevron

- ea: `0x180089774`
- end: `0x180089958`
- name: `DrawChevron`
- size: `484`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b20c`

## callees

- `0x1800115f0`
- `0x1800877b4`
- `0x180089774`

## import_xrefs

- `GDI32!SelectObject` at `0x1800897e4`
- `GDI32!SelectObject` at `0x180089937`
- `GDI32!SelectObject` at `0x1800897e4`
- `GDI32!SelectObject` at `0x180089937`
- `GDI32!PatBlt` at `0x180089873`
- `GDI32!PatBlt` at `0x180089898`
- `GDI32!PatBlt` at `0x1800898f3`
- `GDI32!PatBlt` at `0x180089914`
- `GDI32!PatBlt` at `0x180089873`
- `GDI32!PatBlt` at `0x180089898`
- `GDI32!PatBlt` at `0x1800898f3`
- `GDI32!PatBlt` at `0x180089914`
- `USER32!GetSysColorBrush` at `0x1800897d8`
- `USER32!GetSysColorBrush` at `0x1800897d8`
- `USER32!CopyRect` at `0x1800897a5`
- `USER32!CopyRect` at `0x1800897a5`
- `USER32!OffsetRect` at `0x1800897cd`
- `USER32!OffsetRect` at `0x1800897cd`

## pseudocode

```c
HGDIOBJ __fastcall DrawChevron(HDC hdc, const RECT *a2, unsigned int a3)
{
  HBRUSH SysColorBrush; // rax
  int v6; // r8d
  int h; // edi
  int v8; // r13d
  int v9; // r12d
  int v10; // esi
  int v11; // eax
  int v12; // r12d
  int v13; // eax
  int v14; // esi
  int v15; // r13d
  int v16; // ebx
  int v17; // eax
  int v19; // [rsp+30h] [rbp-30h]
  int v20; // [rsp+30h] [rbp-30h]
  HGDIOBJ v21; // [rsp+38h] [rbp-28h]
  struct tagRECT rcDst; // [rsp+40h] [rbp-20h] BYREF

  rcDst = 0;
  CopyRect(&rcDst, a2);
  DrawBlankButton(hdc, &rcDst, a3);
  if ( (a3 & 0x10) != 0 )
    OffsetRect(&rcDst, 1, 1);
  SysColorBrush = GetSysColorBrush(18);
  v21 = SelectObject(hdc, SysColorBrush);
  v6 = a3 & 1;
  h = 2 * v6 + 2;
  if ( (a3 & 4) != 0 )
  {
    v8 = (rcDst.left + rcDst.right - 4 * h) / 2;
    if ( (a3 & 2) != 0 )
      v9 = h + rcDst.top + 4;
    else
      v9 = (rcDst.top + rcDst.bottom) / 2;
    v10 = -h;
    if ( -h <= h )
    {
      v19 = 4 * v6 + 4;
      do
      {
        PatBlt(hdc, v8, v10 + v9, h, 1, 0xF00021u);
        PatBlt(hdc, v8 + v19, v10 + v9, h, 1, 0xF00021u);
        v11 = v10++ >> 31;
        v8 = (v11 & 2) + v8 - 1;
      }
      while ( v10 <= h );
    }
  }
  else
  {
    v12 = rcDst.top + 1;
    v13 = (rcDst.left + rcDst.right) / 2;
    v14 = -h;
    v20 = v13;
    if ( -h <= h )
    {
      v15 = 4 * v6 + 4;
      do
      {
        v16 = v14 + v13;
        PatBlt(hdc, v14 + v13, v12, 1, h, 0xF00021u);
        PatBlt(hdc, v16, v12 + v15, 1, h, 0xF00021u);
        v17 = v14++;
        v12 += ((v17 >> 31) & 2) - 1;
        v13 = v20;
      }
      while ( v14 <= h );
    }
  }
  return SelectObject(hdc, v21);
}

```

## disassembly

```asm
0x180089774  push    rbp
0x180089776  push    rbx
0x180089777  push    rsi
0x180089778  push    rdi
0x180089779  push    r12
0x18008977b  push    r13
0x18008977d  push    r14
0x18008977f  mov     rbp, rsp
0x180089782  sub     rsp, 60h
0x180089786  mov     rax, cs:__security_cookie
0x18008978d  xor     rax, rsp
0x180089790  mov     [rbp+var_10], rax
0x180089794  mov     r14, rcx
0x180089797  xorps   xmm0, xmm0
0x18008979a  lea     rcx, [rbp+rcDst]; lprcDst
0x18008979e  mov     ebx, r8d
0x1800897a1  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800897a5  call    cs:__imp_CopyRect
0x1800897ab  mov     r8d, ebx; unsigned int
0x1800897ae  lea     rdx, [rbp+rcDst]; lprcDst
0x1800897b2  mov     rcx, r14; hdc
0x1800897b5  call    ?DrawBlankButton@@YAXPEAUHDC__@@PEAUtagRECT@@K@Z; DrawBlankButton(HDC__ *,tagRECT *,ulong)
0x1800897ba  mov     edi, 1
0x1800897bf  test    bl, 10h
0x1800897c2  jz      short loc_1800897D3
0x1800897c4  mov     r8d, edi; dy
0x1800897c7  lea     rcx, [rbp+rcDst]; lprc
0x1800897cb  mov     edx, edi; dx
0x1800897cd  call    cs:__imp_OffsetRect
0x1800897d3  mov     ecx, 12h; nIndex
0x1800897d8  call    cs:__imp_GetSysColorBrush
0x1800897de  mov     rdx, rax; h
0x1800897e1  mov     rcx, r14; hdc
0x1800897e4  call    cs:__imp_SelectObject
0x1800897ea  mov     r8d, ebx
0x1800897ed  mov     [rbp+var_28], rax
0x1800897f1  mov     eax, [rbp+rcDst.right]
0x1800897f4  and     r8d, edi
0x1800897f7  lea     edi, ds:2[r8*2]
0x1800897ff  test    bl, 4
0x180089802  jz      loc_1800898B4
0x180089808  lea     ecx, ds:0[rdi*4]
0x18008980f  sub     eax, ecx
0x180089811  add     eax, [rbp+rcDst.left]
0x180089814  cdq
0x180089815  sub     eax, edx
0x180089817  sar     eax, 1
0x180089819  mov     r13d, eax
0x18008981c  test    bl, 2
0x18008981f  jz      short loc_18008982E
0x180089821  mov     r12d, [rbp+rcDst.top]
0x180089825  add     r12d, 4
0x180089829  add     r12d, edi
0x18008982c  jmp     short loc_18008983C
0x18008982e  mov     eax, [rbp+rcDst.bottom]
0x180089831  add     eax, [rbp+rcDst.top]
0x180089834  cdq
0x180089835  sub     eax, edx
0x180089837  sar     eax, 1
0x180089839  mov     r12d, eax
0x18008983c  mov     esi, edi
0x18008983e  neg     esi
0x180089840  cmp     esi, edi
0x180089842  jg      loc_180089930
0x180089848  lea     eax, ds:4[r8*4]
0x180089850  mov     [rbp+var_30], eax
0x180089853  lea     ebx, [rsi+r12]
0x180089857  mov     [rsp+60h+rop], 0F00021h; rop
0x18008985f  mov     r8d, ebx; y
0x180089862  mov     [rsp+60h+h], 1; h
0x18008986a  mov     r9d, edi; w
0x18008986d  mov     edx, r13d; x
0x180089870  mov     rcx, r14; hdc
0x180089873  call    cs:__imp_PatBlt
0x180089879  mov     edx, [rbp+var_30]
0x18008987c  mov     r9d, edi; w
0x18008987f  add     edx, r13d; x
0x180089882  mov     [rsp+60h+rop], 0F00021h; rop
0x18008988a  mov     r8d, ebx; y
0x18008988d  mov     [rsp+60h+h], 1; h
0x180089895  mov     rcx, r14; hdc
0x180089898  call    cs:__imp_PatBlt
0x18008989e  mov     eax, esi
0x1800898a0  dec     r13d
0x1800898a3  sar     eax, 1Fh
0x1800898a6  inc     esi
0x1800898a8  and     eax, 2
0x1800898ab  add     r13d, eax
0x1800898ae  cmp     esi, edi
0x1800898b0  jle     short loc_180089853
0x1800898b2  jmp     short loc_180089930
0x1800898b4  add     eax, [rbp+rcDst.left]
0x1800898b7  mov     esi, edi
0x1800898b9  mov     r12d, [rbp+rcDst.top]
0x1800898bd  cdq
0x1800898be  sub     eax, edx
0x1800898c0  inc     r12d
0x1800898c3  sar     eax, 1
0x1800898c5  neg     esi
0x1800898c7  mov     [rbp+var_30], eax
0x1800898ca  cmp     esi, edi
0x1800898cc  jg      short loc_180089930
0x1800898ce  lea     r13d, ds:4[r8*4]
0x1800898d6  lea     ebx, [rsi+rax]
0x1800898d9  mov     [rsp+60h+rop], 0F00021h; rop
0x1800898e1  mov     edx, ebx; x
0x1800898e3  mov     [rsp+60h+h], edi; h
0x1800898e7  mov     r9d, 1; w
0x1800898ed  mov     r8d, r12d; y
0x1800898f0  mov     rcx, r14; hdc
0x1800898f3  call    cs:__imp_PatBlt
0x1800898f9  lea     r8d, [r12+r13]; y
0x1800898fd  mov     [rsp+60h+rop], 0F00021h; rop
0x180089905  mov     r9d, 1; w
0x18008990b  mov     [rsp+60h+h], edi; h
0x18008990f  mov     edx, ebx; x
0x180089911  mov     rcx, r14; hdc
0x180089914  call    cs:__imp_PatBlt
0x18008991a  mov     eax, esi
0x18008991c  inc     esi
0x18008991e  sar     eax, 1Fh
0x180089921  and     eax, 2
0x180089924  dec     eax
0x180089926  add     r12d, eax
0x180089929  mov     eax, [rbp+var_30]
0x18008992c  cmp     esi, edi
0x18008992e  jle     short loc_1800898D6
0x180089930  mov     rdx, [rbp+var_28]; h
0x180089934  mov     rcx, r14; hdc
0x180089937  call    cs:__imp_SelectObject
0x18008993d  mov     rcx, [rbp+var_10]
0x180089941  xor     rcx, rsp; StackCookie
0x180089944  call    __security_check_cookie
0x180089949  add     rsp, 60h
0x18008994d  pop     r14
0x18008994f  pop     r13
0x180089951  pop     r12
0x180089953  pop     rdi
0x180089954  pop     rsi
0x180089955  pop     rbx
0x180089956  pop     rbp
0x180089957  retn
```
