# ListView_OnSetWorkAreas

- ea: `0x1800598d8`
- end: `0x180059c6a`
- name: `ListView_OnSetWorkAreas`
- size: `914`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x18002eab0`
- `0x18002ec60`
- `0x18002ee60`
- `0x1800514a8`
- `0x180052bb8`
- `0x180052cf8`
- `0x1800598d8`
- `0x18005a314`
- `0x180075770`
- `0x180075c34`
- `0x18008e3b0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180059bbe`
- `GDI32!DeleteObject` at `0x180059bbe`
- `KERNEL32!LocalAlloc` at `0x180059977`
- `KERNEL32!LocalAlloc` at `0x180059977`
- `USER32!PtInRect` at `0x180059a89`
- `USER32!PtInRect` at `0x180059b5b`
- `USER32!PtInRect` at `0x180059a89`
- `USER32!PtInRect` at `0x180059b5b`
- `USER32!RedrawWindow` at `0x180059c39`
- `USER32!RedrawWindow` at `0x180059c39`
- `USER32!CopyRect` at `0x1800599a4`
- `USER32!CopyRect` at `0x1800599a4`
- `USER32!EqualRect` at `0x1800599fd`
- `USER32!EqualRect` at `0x180059acf`
- `USER32!EqualRect` at `0x1800599fd`
- `USER32!EqualRect` at `0x180059acf`
- `USER32!IsRectEmpty` at `0x180059949`
- `USER32!IsRectEmpty` at `0x180059949`

## pseudocode

```c
int __fastcall ListView_OnSetWorkAreas(__int64 a1, int a2, const RECT *a3)
{
  __int64 v3; // r14
  const void **v4; // rdi
  int v5; // r13d
  HLOCAL v9; // rax
  int v10; // eax
  int i; // esi
  const RECT *v12; // rbp
  int v13; // esi
  struct _DPA *v14; // rsi
  int v15; // r13d
  int v16; // r12d
  void *v17; // r15
  __int64 v18; // rbp
  __int16 *v19; // r8
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  char *v22; // rax
  void *v23; // rcx
  POINT pt; // [rsp+30h] [rbp-168h]
  struct tagRECT rcDst; // [rsp+38h] [rbp-160h] BYREF
  _DWORD v27[64]; // [rsp+50h] [rbp-148h] BYREF

  v3 = *(int *)(a1 + 172);
  v4 = (const void **)(a1 + 176);
  v5 = *(_DWORD *)(a1 + 16);
  if ( (int)v3 > 0 )
    memmove(v27, *v4, 16 * v3);
  if ( a2 && a3 && (!IsRectEmpty(a3) || (*(_DWORD *)(a1 + 32) & 0x400000) != 0) )
  {
    if ( a2 >= 16 )
      a2 = 16;
    *(_DWORD *)(a1 + 172) = a2;
    if ( !*v4 )
    {
      v9 = LocalAlloc(0x40u, 0x100u);
      *v4 = v9;
      if ( !v9 )
        return (int)v9;
    }
    v10 = *(_DWORD *)(a1 + 172);
    for ( i = 0; i < v10; ++i )
    {
      CopyRect((LPRECT)*v4 + i, &a3[i]);
      v10 = *(_DWORD *)(a1 + 172);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 172) = 0;
    v10 = 0;
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 || v10 <= 0 )
    goto LABEL_54;
  if ( v10 == (_DWORD)v3 )
  {
    v12 = (const RECT *)*v4;
    v13 = 0;
    if ( (int)v3 <= 0 )
      goto LABEL_54;
    while ( EqualRect(&v12[v13], (const RECT *)&v27[4 * v13]) )
    {
      if ( ++v13 >= (int)v3 )
        goto LABEL_54;
    }
  }
  v14 = 0;
  v15 = v5 & 0x100;
  ListView_Recompute(a1);
  v16 = 0;
  if ( *(int *)(a1 + 512) <= 0 )
    goto LABEL_49;
  do
  {
    v17 = (void *)v16;
    v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) + 8LL * v16);
    if ( *(_DWORD *)(v18 + 8) == 0x7FFFFFFF || *(_DWORD *)(v18 + 12) == 0x7FFFFFFF )
      goto LABEL_44;
    v19 = (__int16 *)(v18 + 26);
    if ( (int)v3 <= 0 )
    {
      if ( !(unsigned int)ListView_FindWorkArea(a1, *(_QWORD *)(v18 + 8), v19) && !v15 )
        goto LABEL_36;
    }
    else
    {
      v20 = *v19;
      if ( (int)v20 < *(_DWORD *)(a1 + 172) )
      {
        if ( !v15 )
        {
          v21 = 16 * v20;
          if ( !EqualRect((const RECT *)*v4 + v20, (const RECT *)&v27[4 * v20]) )
          {
            v22 = (char *)*v4;
            rcDst = 0;
            *(_DWORD *)(v18 + 8) += *(_DWORD *)&v22[v21] - v27[v21 / 4];
            *(_DWORD *)(v18 + 12) += *(_DWORD *)((char *)*v4 + v21 + 4) - v27[v21 / 4 + 1];
            ListView_GetRects(a1, v16, 0, 0, &rcDst, 0);
            pt.x = *(_DWORD *)(v18 + 8) + (rcDst.right - rcDst.left) / 2;
            pt.y = *(_DWORD *)(v18 + 12) + (rcDst.bottom - rcDst.top) / 2;
            if ( !PtInRect((const RECT *)((char *)*v4 + v21), pt) )
            {
              v17 = (void *)v16;
LABEL_36:
              if ( v14 || (v14 = DPA_CreateEx(4, 0)) != 0 )
                DPA_InsertPtr(v14, 0x7FFFFFFF, v17);
            }
          }
        }
      }
      else
      {
        *v19 = 0;
        if ( !v15 )
        {
          if ( PtInRect((const RECT *)*v4, *(POINT *)(v18 + 8)) )
          {
            *(_DWORD *)(v18 + 8) = *((_DWORD *)*v4 + 2) + 1;
            *(_DWORD *)(a1 + 320) = -1;
          }
          goto LABEL_36;
        }
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      v23 = *(void **)(v18 + 40);
      if ( v23 )
      {
        if ( v23 != (void *)-1LL )
          DeleteObject(v23);
        *(_QWORD *)(v18 + 40) = 0;
      }
    }
LABEL_44:
    ++v16;
  }
  while ( v16 < *(_DWORD *)(a1 + 512) );
  if ( v14 )
  {
    if ( *(int *)v14 > 0 )
      ListView_BullyIconsOnWorkarea(a1);
    DPA_Destroy(v14);
  }
LABEL_49:
  if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    ListView_RecalcRegion(a1, 1);
  if ( (*(_DWORD *)(a1 + 16) & 0x100) != 0 && (*(_BYTE *)(a1 + 16) & 1) == 0 )
    ListView_OnArrange(a1, 0);
LABEL_54:
  LODWORD(v9) = RedrawWindow(*(HWND *)a1, 0, 0, 5u);
  return (int)v9;
}

```

## disassembly

```asm
0x1800598d8  mov     [rsp+arg_8], rbx
0x1800598dd  push    rbp
0x1800598de  push    rsi
0x1800598df  push    rdi
0x1800598e0  push    r12
0x1800598e2  push    r13
0x1800598e4  push    r14
0x1800598e6  push    r15
0x1800598e8  sub     rsp, 160h
0x1800598ef  mov     rax, cs:__security_cookie
0x1800598f6  xor     rax, rsp
0x1800598f9  mov     [rsp+198h+var_48], rax
0x180059901  movsxd  r14, dword ptr [rcx+0ACh]
0x180059908  lea     rdi, [rcx+0B0h]
0x18005990f  mov     r13d, [rcx+10h]
0x180059913  xor     r15d, r15d
0x180059916  mov     rbp, r8
0x180059919  mov     esi, edx
0x18005991b  mov     rbx, rcx
0x18005991e  test    r14d, r14d
0x180059921  jle     short loc_180059937
0x180059923  mov     rdx, [rdi]; Src
0x180059926  lea     rcx, [rsp+198h+var_148]; void *
0x18005992b  mov     r8, r14
0x18005992e  shl     r8, 4; Size
0x180059932  call    memmove
0x180059937  mov     r12d, 100h
0x18005993d  test    esi, esi
0x18005993f  jz      short loc_1800599B8
0x180059941  test    rbp, rbp
0x180059944  jz      short loc_1800599B8
0x180059946  mov     rcx, rbp; lprc
0x180059949  call    cs:__imp_IsRectEmpty
0x18005994f  test    eax, eax
0x180059951  jz      short loc_18005995C
0x180059953  test    dword ptr [rbx+20h], 400000h
0x18005995a  jz      short loc_1800599B8
0x18005995c  mov     eax, 10h
0x180059961  cmp     esi, eax
0x180059963  cmovge  esi, eax
0x180059966  mov     [rbx+0ACh], esi
0x18005996c  cmp     [rdi], r15
0x18005996f  jnz     short loc_180059989
0x180059971  mov     rdx, r12; uBytes
0x180059974  lea     ecx, [rax+30h]; uFlags
0x180059977  call    cs:__imp_LocalAlloc
0x18005997d  mov     [rdi], rax
0x180059980  test    rax, rax
0x180059983  jz      loc_180059C3F
0x180059989  mov     eax, [rbx+0ACh]
0x18005998f  mov     esi, r15d
0x180059992  test    eax, eax
0x180059994  jle     short loc_1800599C2
0x180059996  movsxd  rcx, esi
0x180059999  shl     rcx, 4
0x18005999d  lea     rdx, [rcx+rbp]; lprcSrc
0x1800599a1  add     rcx, [rdi]; lprcDst
0x1800599a4  call    cs:__imp_CopyRect
0x1800599aa  mov     eax, [rbx+0ACh]
0x1800599b0  inc     esi
0x1800599b2  cmp     esi, eax
0x1800599b4  jl      short loc_180059996
0x1800599b6  jmp     short loc_1800599C2
0x1800599b8  mov     [rbx+0ACh], r15d
0x1800599bf  mov     eax, r15d
0x1800599c2  test    dword ptr [rbx+10h], 1000h
0x1800599c9  jnz     loc_180059C2B
0x1800599cf  test    eax, eax
0x1800599d1  jle     loc_180059C2B
0x1800599d7  cmp     eax, r14d
0x1800599da  jnz     short loc_180059A13
0x1800599dc  mov     rbp, [rdi]
0x1800599df  mov     esi, r15d
0x1800599e2  test    r14d, r14d
0x1800599e5  jle     loc_180059C2B
0x1800599eb  mov     eax, esi
0x1800599ed  lea     rdx, [rsp+198h+var_148]
0x1800599f2  shl     rax, 4
0x1800599f6  add     rdx, rax; lprc2
0x1800599f9  lea     rcx, [rax+rbp]; lprc1
0x1800599fd  call    cs:__imp_EqualRect
0x180059a03  test    eax, eax
0x180059a05  jz      short loc_180059A13
0x180059a07  inc     esi
0x180059a09  cmp     esi, r14d
0x180059a0c  jl      short loc_1800599EB
0x180059a0e  jmp     loc_180059C2B
0x180059a13  mov     rcx, rbx; int
0x180059a16  mov     rsi, r15
0x180059a19  and     r13d, r12d
0x180059a1c  call    ListView_Recompute
0x180059a21  mov     r12d, r15d
0x180059a24  cmp     [rbx+200h], r15d
0x180059a2b  jle     loc_180059BF9
0x180059a31  mov     rax, [rbx+40h]
0x180059a35  movsxd  r15, r12d
0x180059a38  mov     rcx, [rax+8]
0x180059a3c  mov     rbp, [rcx+r15*8]
0x180059a40  cmp     dword ptr [rbp+8], 7FFFFFFFh
0x180059a47  jz      loc_180059BCC
0x180059a4d  cmp     dword ptr [rbp+0Ch], 7FFFFFFFh
0x180059a54  jz      loc_180059BCC
0x180059a5a  lea     r8, [rbp+1Ah]
0x180059a5e  test    r14d, r14d
0x180059a61  jle     loc_180059B6A
0x180059a67  movsx   rax, word ptr [r8]
0x180059a6b  cmp     eax, [rbx+0ACh]
0x180059a71  jl      short loc_180059AB1
0x180059a73  xor     eax, eax
0x180059a75  mov     [r8], ax
0x180059a79  test    r13d, r13d
0x180059a7c  jnz     loc_180059BA6
0x180059a82  mov     rdx, [rbp+8]; pt
0x180059a86  mov     rcx, [rdi]; lprc
0x180059a89  call    cs:__imp_PtInRect
0x180059a8f  test    eax, eax
0x180059a91  jz      loc_180059B7F
0x180059a97  mov     rax, [rdi]
0x180059a9a  mov     ecx, [rax+8]
0x180059a9d  inc     ecx
0x180059a9f  mov     [rbp+8], ecx
0x180059aa2  mov     dword ptr [rbx+140h], 0FFFFFFFFh
0x180059aac  jmp     loc_180059B7F
0x180059ab1  test    r13d, r13d
0x180059ab4  jnz     loc_180059BA6
0x180059aba  mov     rcx, [rdi]
0x180059abd  lea     rdx, [rsp+198h+var_148]
0x180059ac2  mov     r15, rax
0x180059ac5  shl     r15, 4
0x180059ac9  add     rdx, r15; lprc2
0x180059acc  add     rcx, r15; lprc1
0x180059acf  call    cs:__imp_EqualRect
0x180059ad5  test    eax, eax
0x180059ad7  jnz     loc_180059BA6
0x180059add  mov     rax, [rdi]
0x180059ae0  xorps   xmm0, xmm0
0x180059ae3  movups  xmmword ptr [rsp+198h+rcDst.left], xmm0
0x180059ae8  mov     [rsp+198h+var_170], 0; LPRECT
0x180059af1  xor     r9d, r9d; int
0x180059af4  xor     r8d, r8d; int
0x180059af7  mov     edx, r12d; int
0x180059afa  mov     ecx, [r15+rax]
0x180059afe  sub     ecx, [rsp+r15+198h+var_148]
0x180059b03  add     [rbp+8], ecx
0x180059b06  mov     rax, [rdi]
0x180059b09  mov     ecx, [r15+rax+4]
0x180059b0e  lea     rax, [rsp+198h+rcDst]
0x180059b13  sub     ecx, [rsp+r15+198h+var_144]
0x180059b18  add     [rbp+0Ch], ecx
0x180059b1b  mov     rcx, rbx; int
0x180059b1e  mov     [rsp+198h+lprcDst], rax; lprcDst
0x180059b23  call    ListView_GetRects
0x180059b28  mov     eax, [rsp+198h+rcDst.right]
0x180059b2c  sub     eax, [rsp+198h+rcDst.left]
0x180059b30  mov     rcx, [rdi]
0x180059b33  cdq
0x180059b34  sub     eax, edx
0x180059b36  add     rcx, r15; lprc
0x180059b39  sar     eax, 1
0x180059b3b  add     eax, [rbp+8]
0x180059b3e  mov     [rsp+198h+pt.x], eax
0x180059b42  mov     eax, [rsp+198h+rcDst.bottom]
0x180059b46  sub     eax, [rsp+198h+rcDst.top]
0x180059b4a  cdq
0x180059b4b  sub     eax, edx
0x180059b4d  sar     eax, 1
0x180059b4f  add     eax, [rbp+0Ch]
0x180059b52  mov     [rsp+198h+pt.y], eax
0x180059b56  mov     rdx, qword ptr [rsp+198h+pt.x]; pt
0x180059b5b  call    cs:__imp_PtInRect
0x180059b61  test    eax, eax
0x180059b63  jnz     short loc_180059BA6
0x180059b65  movsxd  r15, r12d
0x180059b68  jmp     short loc_180059B7F
0x180059b6a  mov     rdx, [rbp+8]
0x180059b6e  mov     rcx, rbx
0x180059b71  call    ListView_FindWorkArea
0x180059b76  test    eax, eax
0x180059b78  jnz     short loc_180059BA6
0x180059b7a  test    r13d, r13d
0x180059b7d  jnz     short loc_180059BA6
0x180059b7f  test    rsi, rsi
0x180059b82  jnz     short loc_180059B96
0x180059b84  xor     edx, edx; hheap
0x180059b86  lea     ecx, [rsi+4]; cpGrow
0x180059b89  call    DPA_CreateEx
0x180059b8e  mov     rsi, rax
0x180059b91  test    rax, rax
0x180059b94  jz      short loc_180059BA6
0x180059b96  mov     r8, r15; p
0x180059b99  mov     edx, 7FFFFFFFh; i
0x180059b9e  mov     rcx, rsi; hdpa
0x180059ba1  call    DPA_InsertPtr
0x180059ba6  test    dword ptr [rbx+4Ch], 200h
0x180059bad  jz      short loc_180059BCC
0x180059baf  mov     rcx, [rbp+28h]; ho
0x180059bb3  test    rcx, rcx
0x180059bb6  jz      short loc_180059BCC
0x180059bb8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180059bbc  jz      short loc_180059BC4
0x180059bbe  call    cs:__imp_DeleteObject
0x180059bc4  mov     qword ptr [rbp+28h], 0
0x180059bcc  inc     r12d
0x180059bcf  cmp     r12d, [rbx+200h]
0x180059bd6  jl      loc_180059A31
0x180059bdc  test    rsi, rsi
0x180059bdf  jz      short loc_180059BF9
0x180059be1  cmp     dword ptr [rsi], 0
0x180059be4  jle     short loc_180059BF1
0x180059be6  mov     rdx, rsi
0x180059be9  mov     rcx, rbx
0x180059bec  call    ListView_BullyIconsOnWorkarea
0x180059bf1  mov     rcx, rsi; hdpa
0x180059bf4  call    DPA_Destroy
0x180059bf9  test    dword ptr [rbx+4Ch], 200h
0x180059c00  jz      short loc_180059C12
0x180059c02  mov     edx, 1
0x180059c07  mov     rcx, rbx; int
0x180059c0a  mov     r8d, edx
0x180059c0d  call    ListView_RecalcRegion
0x180059c12  test    dword ptr [rbx+10h], 100h
0x180059c19  jz      short loc_180059C2B
0x180059c1b  test    byte ptr [rbx+10h], 1
0x180059c1f  jnz     short loc_180059C2B
0x180059c21  xor     edx, edx
0x180059c23  mov     rcx, rbx
0x180059c26  call    ListView_OnArrange
0x180059c2b  mov     rcx, [rbx]; hWnd
0x180059c2e  mov     r9d, 5; flags
0x180059c34  xor     r8d, r8d; hrgnUpdate
0x180059c37  xor     edx, edx; lprcUpdate
0x180059c39  call    cs:__imp_RedrawWindow
0x180059c3f  mov     rcx, [rsp+198h+var_48]
0x180059c47  xor     rcx, rsp; StackCookie
0x180059c4a  call    __security_check_cookie
0x180059c4f  mov     rbx, [rsp+198h+arg_8]
0x180059c57  add     rsp, 160h
0x180059c5e  pop     r15
0x180059c60  pop     r14
0x180059c62  pop     r13
0x180059c64  pop     r12
0x180059c66  pop     rdi
0x180059c67  pop     rsi
0x180059c68  pop     rbp
0x180059c69  retn
```
