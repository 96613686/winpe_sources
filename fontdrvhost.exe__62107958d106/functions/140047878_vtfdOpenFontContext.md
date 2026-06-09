# vtfdOpenFontContext

- ea: `0x140047878`
- end: `0x1400479ea`
- name: `vtfdOpenFontContext`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400476e4`
- `0x14007c96c`

## callees

- `0x140015cdc`
- `0x140047878`
- `0x140048348`
- `0x14007cc84`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1400479d1`
- `KERNEL32!GlobalFree` at `0x1400479d1`
- `KERNEL32!GlobalAlloc` at `0x140047917`
- `KERNEL32!GlobalAlloc` at `0x140047917`

## pseudocode

```c
_DWORD *__fastcall vtfdOpenFontContext(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v3; // eax
  __int64 i; // rdx
  __int64 v5; // rcx
  unsigned __int8 *v6; // rax
  int v7; // r14d
  int v8; // r15d
  int v9; // r12d
  unsigned __int32 v10; // ebp
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  _DWORD *result; // rax
  int v14; // eax

  v1 = *(_QWORD *)(a1 + 24);
  if ( !v1 )
    return 0;
  v3 = *(_DWORD *)(a1 + 4);
  if ( !v3 || v3 > *(_DWORD *)(v1 + 36) )
    return 0;
  if ( !*(_DWORD *)(v1 + 32) )
  {
    if ( !EngMapFontFileFD(*(_QWORD *)(v1 + 8), (PULONG *)(v1 + 16), (ULONG *)(v1 + 24)) )
      return 0;
    for ( i = 0;
          (unsigned int)i < *(_DWORD *)(v1 + 36);
          *(_QWORD *)(v1 + 16 * v5 + 40) = *(_QWORD *)(v1 + 16) + *(int *)(v1 + 16 * v5 + 48) )
    {
      v5 = 3 * i;
      i = (unsigned int)(i + 1);
    }
  }
  v6 = *(unsigned __int8 **)(v1 + 48LL * (unsigned int)(*(_DWORD *)(a1 + 4) - 1) + 40);
  v7 = v6[115];
  v8 = v6[114];
  v9 = v6[113];
  v10 = _byteswap_ulong(v6[116]);
  v11 = GlobalAlloc(0, 0x80u);
  v12 = v11;
  if ( !v11 )
  {
    if ( !*(_DWORD *)(v1 + 32) )
      EngUnmapFontFileFD(*(_QWORD *)(v1 + 8));
    return 0;
  }
  *((_QWORD *)v11 + 14) = v1 + 48LL * (unsigned int)(*(_DWORD *)(a1 + 4) - 1) + 40;
  *((_QWORD *)v11 + 1) = *(_QWORD *)(v1 + 48LL * (unsigned int)(*(_DWORD *)(a1 + 4) - 1) + 80);
  v14 = 0;
  v12[30] = 0;
  if ( (*(_DWORD *)(a1 + 12) & 0x2000) != 0 )
  {
    v12[30] = 1;
    v14 = 1;
  }
  if ( (*(_DWORD *)(a1 + 12) & 0x4000) != 0 )
    v12[30] = v14 | 2;
  v12[31] = v10 | v9 | ((v8 | (v7 << 8)) << 8);
  if ( !(unsigned int)bInitXform(v12, -1) )
  {
    if ( !*(_DWORD *)(v1 + 32) )
      EngUnmapFontFileFD(*(_QWORD *)(v1 + 8));
    GlobalFree(v12);
    return 0;
  }
  *(_QWORD *)v12 = v1;
  result = v12;
  ++*(_DWORD *)(v1 + 32);
  return result;
}

```

## disassembly

```asm
0x140047878  push    rbx
0x14004787a  push    rbp
0x14004787b  push    rsi
0x14004787c  push    rdi
0x14004787d  push    r12
0x14004787f  push    r14
0x140047881  push    r15
0x140047883  sub     rsp, 20h
0x140047887  mov     rbx, [rcx+18h]
0x14004788b  mov     rsi, rcx
0x14004788e  test    rbx, rbx
0x140047891  jz      loc_140047933
0x140047897  mov     eax, [rcx+4]
0x14004789a  cmp     eax, 1
0x14004789d  jb      loc_140047933
0x1400478a3  cmp     eax, [rbx+24h]
0x1400478a6  ja      loc_140047933
0x1400478ac  cmp     dword ptr [rbx+20h], 0
0x1400478b0  jnz     short loc_1400478EA
0x1400478b2  mov     rcx, [rbx+8]; iFile
0x1400478b6  lea     r8, [rbx+18h]; pcjBuf
0x1400478ba  lea     rdx, [rbx+10h]; ppjBuf
0x1400478be  call    EngMapFontFileFD
0x1400478c3  test    eax, eax
0x1400478c5  jz      short loc_140047933
0x1400478c7  xor     edx, edx
0x1400478c9  cmp     [rbx+24h], edx
0x1400478cc  jbe     short loc_1400478EA
0x1400478ce  lea     rcx, [rdx+rdx*2]
0x1400478d2  inc     edx
0x1400478d4  add     rcx, rcx
0x1400478d7  movsxd  rax, dword ptr [rbx+rcx*8+30h]
0x1400478dc  add     rax, [rbx+10h]
0x1400478e0  mov     [rbx+rcx*8+28h], rax
0x1400478e5  cmp     edx, [rbx+24h]
0x1400478e8  jb      short loc_1400478CE
0x1400478ea  mov     eax, [rsi+4]
0x1400478ed  mov     edx, 80h; dwBytes
0x1400478f2  dec     eax
0x1400478f4  lea     rcx, [rax+rax*2]
0x1400478f8  add     rcx, rcx
0x1400478fb  mov     rax, [rbx+rcx*8+28h]
0x140047900  xor     ecx, ecx; uFlags
0x140047902  movzx   ebp, byte ptr [rax+74h]
0x140047906  movzx   r14d, byte ptr [rax+73h]
0x14004790b  movzx   r15d, byte ptr [rax+72h]
0x140047910  movzx   r12d, byte ptr [rax+71h]
0x140047915  bswap   ebp
0x140047917  call    cs:__imp_GlobalAlloc
0x14004791d  mov     rdi, rax
0x140047920  test    rax, rax
0x140047923  jnz     short loc_140047944
0x140047925  cmp     [rbx+20h], eax
0x140047928  jnz     short loc_140047933
0x14004792a  mov     rcx, [rbx+8]; iFile
0x14004792e  call    EngUnmapFontFileFD
0x140047933  xor     eax, eax
0x140047935  add     rsp, 20h
0x140047939  pop     r15
0x14004793b  pop     r14
0x14004793d  pop     r12
0x14004793f  pop     rdi
0x140047940  pop     rsi
0x140047941  pop     rbp
0x140047942  pop     rbx
0x140047943  retn
0x140047944  mov     eax, [rsi+4]
0x140047947  mov     edx, r14d
0x14004794a  shl     edx, 8
0x14004794d  or      edx, r15d
0x140047950  shl     edx, 8
0x140047953  or      edx, r12d
0x140047956  or      edx, ebp
0x140047958  mov     ebp, 1
0x14004795d  sub     eax, ebp
0x14004795f  lea     rax, [rax+rax*2]
0x140047963  shl     rax, 4
0x140047967  add     rax, 28h ; '('
0x14004796b  add     rax, rbx
0x14004796e  mov     [rdi+70h], rax
0x140047972  mov     eax, [rsi+4]
0x140047975  sub     eax, ebp
0x140047977  lea     rax, [rax+rax*2]
0x14004797b  add     rax, rax
0x14004797e  mov     rax, [rbx+rax*8+50h]
0x140047983  mov     [rdi+8], rax
0x140047987  xor     eax, eax
0x140047989  mov     dword ptr [rdi+78h], 0
0x140047990  test    dword ptr [rsi+0Ch], 2000h
0x140047997  jz      short loc_14004799E
0x140047999  mov     [rdi+78h], ebp
0x14004799c  mov     eax, ebp
0x14004799e  test    dword ptr [rsi+0Ch], 4000h
0x1400479a5  jz      short loc_1400479AD
0x1400479a7  or      eax, 2
0x1400479aa  mov     [rdi+78h], eax
0x1400479ad  mov     [rdi+7Ch], edx
0x1400479b0  mov     rcx, rdi
0x1400479b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400479b7  call    bInitXform
0x1400479bc  test    eax, eax
0x1400479be  jnz     short loc_1400479DC
0x1400479c0  cmp     [rbx+20h], eax
0x1400479c3  jnz     short loc_1400479CE
0x1400479c5  mov     rcx, [rbx+8]; iFile
0x1400479c9  call    EngUnmapFontFileFD
0x1400479ce  mov     rcx, rdi; hMem
0x1400479d1  call    cs:__imp_GlobalFree
0x1400479d7  jmp     loc_140047933
0x1400479dc  mov     [rdi], rbx
0x1400479df  mov     rax, rdi
0x1400479e2  add     [rbx+20h], ebp
0x1400479e5  jmp     loc_140047935
```
