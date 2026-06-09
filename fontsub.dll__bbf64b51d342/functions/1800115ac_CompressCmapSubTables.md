# CompressCmapSubTables

- ea: `0x1800115ac`
- end: `0x1800118b5`
- name: `CompressCmapSubTables`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800118bc`

## callees

- `0x18000f198`
- `0x180011538`
- `0x180011574`
- `0x1800115ac`
- `0x180019804`
- `0x180019ec0`
- `0x18001a2cc`
- `0x18001a76c`
- `0x18001a808`

## pseudocode

```c
__int64 __fastcall CompressCmapSubTables(
        _QWORD *a1,
        __int64 a2,
        unsigned __int16 a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int16 v7; // r14
  __int64 v9; // rdi
  unsigned __int16 updated; // bx
  unsigned int v12; // r13d
  unsigned __int16 i; // dx
  unsigned __int16 j; // r8
  unsigned __int16 v15; // r9
  int v17; // edx
  __int64 v18; // rcx
  unsigned __int16 v19; // r15
  int v20; // r8d
  __int64 v21; // rbp
  unsigned int v22; // ecx
  unsigned int v23; // esi
  __int64 v24; // r9
  int v25; // eax
  _QWORD *v26; // rbp
  unsigned __int16 v27; // r12
  unsigned __int16 v28; // bp
  unsigned int v29; // r13d
  unsigned __int16 v30; // ax
  unsigned __int16 v31; // bp
  unsigned __int16 k; // dx
  __int64 v33; // rax
  unsigned int v34; // esi
  _WORD v35[2]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 v36; // [rsp+34h] [rbp-64h]
  unsigned int v37; // [rsp+38h] [rbp-60h]
  int v38; // [rsp+3Ch] [rbp-5Ch]
  int v39; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-54h]

  v7 = a3;
  LOWORD(v40) = 0;
  v39 = 0;
  v35[0] = 0;
  v9 = Mem_Alloc(8LL * a3);
  if ( !v9 )
    return 1005;
  updated = 0;
  v12 = 0;
  for ( i = 0; i < v7; ++i )
  {
    for ( j = 0; j < i; ++j )
    {
      if ( *(_DWORD *)(a2 + 8LL * i + 4) < *(_DWORD *)(a2 + 8LL * *(unsigned __int16 *)(v9 + 8LL * j) + 4) )
      {
        v15 = i;
        do
        {
          *(_WORD *)(v9 + 8LL * v15) = *(_WORD *)(v9 + 8LL * v15 - 8);
          --v15;
        }
        while ( v15 > j );
        break;
      }
    }
    *(_WORD *)(v9 + 8LL * j) = i;
  }
  v17 = 0;
  v18 = a2;
  v19 = 0;
  v20 = a4;
  while ( v19 < v7 )
  {
    v21 = 8LL * *(unsigned __int16 *)(v9 + 8LL * v19);
    if ( v19 && *(_DWORD *)(v18 + v21 + 4) == v17 )
    {
      *(_DWORD *)(v9 + 8LL * v19 + 4) = *(_DWORD *)(v9 + 8LL * v19 - 4);
    }
    else
    {
      updated = ReadCmapLength(a1, &v39, (unsigned int)(*(_DWORD *)(v18 + v21 + 4) + v20), v35);
      if ( updated )
        goto LABEL_31;
      v22 = a5;
      v23 = (a5 + 1) & 0xFFFFFFFE;
      v37 = v22;
      v36 = v23 - v22;
      if ( v12 + v40 + (unsigned __int16)(v23 - v22) > a6 )
      {
        updated = 1007;
        goto LABEL_31;
      }
      v24 = v40;
      *(_DWORD *)(v9 + 8LL * v19 + 4) = v23 - a4;
      v25 = *(_DWORD *)(a2 + v21 + 4);
      v26 = a1;
      v38 = v25;
      updated = CopyBlock(a1, v23, (unsigned int)(v25 + a4), v24);
      if ( updated )
        goto LABEL_32;
      v27 = v36;
      v28 = 0;
      v29 = v37;
      do
      {
        if ( v28 >= v27 )
          break;
        v30 = WriteByte(a1, 0, v29 + v28++);
        updated = v30;
      }
      while ( !v30 );
      a5 = v40 + v23;
      v20 = a4;
      v7 = a3;
      v12 = a5 - a4;
      v18 = a2;
      v17 = v38;
    }
    ++v19;
  }
  v31 = 0;
  if ( !updated )
  {
    for ( k = 0; k < v7; *(_DWORD *)(a2 + 8LL * *(unsigned __int16 *)(v9 + 8 * v33) + 4) = *(_DWORD *)(v9 + 8 * v33 + 4) )
      v33 = k++;
    v34 = a4 + (unsigned __int16)GetGenericSize(CMAP_HEADER_CONTROL);
    if ( v7 )
    {
      do
      {
        updated = WriteGeneric((__int64)a1, a2 + 8LL * v31, 8u, (unsigned __int8 *)CMAP_TABLELOC_CONTROL, v34, v35);
        if ( updated )
          break;
        ++v31;
        v34 += v35[0];
      }
      while ( v31 < v7 );
    }
  }
LABEL_31:
  v26 = a1;
LABEL_32:
  Mem_Free(v9);
  if ( !updated )
    updated = UpdateDirEntry(v26, "cmap", v12);
  *a7 = v12;
  return updated;
}

```

## disassembly

```asm
0x1800115ac  mov     rax, rsp
0x1800115af  mov     [rax+20h], r9d
0x1800115b3  mov     [rax+18h], r8w
0x1800115b8  mov     [rax+10h], rdx
0x1800115bc  mov     [rax+8], rcx
0x1800115c0  push    rbx
0x1800115c1  push    rbp
0x1800115c2  push    rsi
0x1800115c3  push    rdi
0x1800115c4  push    r12
0x1800115c6  push    r13
0x1800115c8  push    r14
0x1800115ca  push    r15
0x1800115cc  sub     rsp, 58h
0x1800115d0  xor     eax, eax
0x1800115d2  movzx   r14d, r8w
0x1800115d6  mov     [rsp+98h+var_56], eax
0x1800115da  mov     ecx, r14d
0x1800115dd  xor     ebp, ebp
0x1800115df  shl     rcx, 3; Size
0x1800115e3  mov     r12, rdx
0x1800115e6  mov     [rsp+40h], eax
0x1800115ea  mov     [rsp+98h+var_68], bp
0x1800115ef  call    Mem_Alloc
0x1800115f4  mov     rdi, rax
0x1800115f7  test    rax, rax
0x1800115fa  jnz     short loc_180011606
0x1800115fc  mov     eax, 3EDh
0x180011601  jmp     loc_1800118A4
0x180011606  mov     ebx, ebp
0x180011608  mov     r13d, ebp
0x18001160b  mov     edx, ebp
0x18001160d  cmp     bp, r14w
0x180011611  jnb     short loc_18001166B
0x180011613  mov     r8d, ebp
0x180011616  movzx   r9d, dx
0x18001161a  cmp     r8w, dx
0x18001161e  jnb     short loc_18001165A
0x180011620  movzx   eax, r8w
0x180011624  movzx   ecx, word ptr [rdi+rax*8]
0x180011628  mov     eax, [r12+rcx*8+4]
0x18001162d  cmp     [r12+r9*8+4], eax
0x180011632  jb      short loc_18001163A
0x180011634  inc     r8w
0x180011638  jmp     short loc_18001161A
0x18001163a  movzx   r9d, dx
0x18001163e  movzx   ecx, r9w
0x180011642  movzx   eax, word ptr [rdi+rcx*8-8]
0x180011647  mov     [rdi+rcx*8], ax
0x18001164b  mov     eax, 0FFFFh
0x180011650  add     r9w, ax
0x180011654  cmp     r9w, r8w
0x180011658  ja      short loc_18001163E
0x18001165a  movzx   eax, r8w
0x18001165e  mov     [rdi+rax*8], dx
0x180011662  inc     dx
0x180011665  cmp     dx, r14w
0x180011669  jb      short loc_180011613
0x18001166b  mov     esi, [rsp+98h+arg_20]
0x180011672  mov     edx, ebp
0x180011674  mov     rcx, [rsp+98h+arg_8]
0x18001167c  mov     r15d, ebp
0x18001167f  mov     r8d, [rsp+98h+arg_18]
0x180011687  xor     r9d, r9d
0x18001168a  cmp     r15w, r14w
0x18001168e  jnb     loc_1800117D2
0x180011694  movzx   r12d, r15w
0x180011698  movzx   eax, word ptr [rdi+r12*8]
0x18001169d  lea     rbp, ds:0[rax*8]
0x1800116a5  test    r15w, r15w
0x1800116a9  jz      short loc_1800116C0
0x1800116ab  cmp     [rcx+rbp+4], edx
0x1800116af  jnz     short loc_1800116C0
0x1800116b1  mov     eax, [rdi+r12*8-4]
0x1800116b6  mov     [rdi+r12*8+4], eax
0x1800116bb  jmp     loc_1800117BF
0x1800116c0  add     r8d, [rcx+rbp+4]
0x1800116c5  lea     r9, [rsp+98h+var_68]
0x1800116ca  mov     rcx, [rsp+98h+arg_0]
0x1800116d2  lea     rdx, [rsp+98h+var_58]
0x1800116d7  call    ReadCmapLength
0x1800116dc  movzx   ebx, ax
0x1800116df  test    ax, ax
0x1800116e2  jnz     loc_18001186C
0x1800116e8  mov     ecx, esi
0x1800116ea  inc     esi
0x1800116ec  and     esi, 0FFFFFFFEh
0x1800116ef  mov     [rsp+98h+var_60], ecx
0x1800116f3  movzx   eax, si
0x1800116f6  sub     ax, cx
0x1800116f9  mov     [rsp+98h+var_64], ax
0x1800116fe  movzx   eax, ax
0x180011701  add     eax, [rsp+98h+var_56+2]
0x180011705  add     eax, r13d
0x180011708  cmp     eax, [rsp+98h+arg_28]
0x18001170f  ja      loc_1800117C8
0x180011715  mov     ecx, [rsp+98h+arg_18]
0x18001171c  mov     eax, esi
0x18001171e  mov     r9d, [rsp+98h+var_56+2]
0x180011723  sub     eax, ecx
0x180011725  mov     [rdi+r12*8+4], eax
0x18001172a  mov     edx, esi
0x18001172c  mov     rax, [rsp+98h+arg_8]
0x180011734  mov     eax, [rax+rbp+4]
0x180011738  mov     rbp, [rsp+98h+arg_0]
0x180011740  mov     [rsp+98h+var_5C], eax
0x180011744  lea     r8d, [rax+rcx]
0x180011748  mov     rcx, rbp
0x18001174b  call    CopyBlock
0x180011750  movzx   ebx, ax
0x180011753  xor     eax, eax
0x180011755  test    bx, bx
0x180011758  jnz     loc_180011874
0x18001175e  movzx   r12d, [rsp+98h+var_64]
0x180011764  mov     ebp, eax
0x180011766  mov     r13d, [rsp+98h+var_60]
0x18001176b  mov     r14, [rsp+98h+arg_0]
0x180011773  cmp     bp, r12w
0x180011777  jnb     short loc_180011795
0x180011779  movzx   r8d, bp
0x18001177d  xor     edx, edx
0x18001177f  add     r8d, r13d
0x180011782  mov     rcx, r14
0x180011785  call    WriteByte
0x18001178a  inc     bp
0x18001178d  movzx   ebx, ax
0x180011790  test    ax, ax
0x180011793  jz      short loc_180011773
0x180011795  add     esi, [rsp+98h+var_56+2]
0x180011799  mov     r8d, [rsp+98h+arg_18]
0x1800117a1  mov     r13d, esi
0x1800117a4  movzx   r14d, [rsp+98h+arg_10]
0x1800117ad  sub     r13d, r8d
0x1800117b0  mov     rcx, [rsp+98h+arg_8]
0x1800117b8  xor     r9d, r9d
0x1800117bb  mov     edx, [rsp+98h+var_5C]
0x1800117bf  inc     r15w
0x1800117c3  jmp     loc_18001168A
0x1800117c8  mov     ebx, 3EFh
0x1800117cd  jmp     loc_18001186C
0x1800117d2  xor     ebp, ebp
0x1800117d4  test    bx, bx
0x1800117d7  jnz     loc_18001186C
0x1800117dd  mov     r12, [rsp+98h+arg_8]
0x1800117e5  mov     edx, ebp
0x1800117e7  cmp     bp, r14w
0x1800117eb  jnb     short loc_180011806
0x1800117ed  movzx   eax, dx
0x1800117f0  inc     dx
0x1800117f3  movzx   ecx, word ptr [rdi+rax*8]
0x1800117f7  mov     eax, [rdi+rax*8+4]
0x1800117fb  mov     [r12+rcx*8+4], eax
0x180011800  cmp     dx, r14w
0x180011804  jb      short loc_1800117ED
0x180011806  lea     rcx, CMAP_HEADER_CONTROL
0x18001180d  call    GetGenericSize
0x180011812  movzx   esi, ax
0x180011815  xor     r15d, r15d
0x180011818  add     esi, [rsp+98h+arg_18]
0x18001181f  cmp     r15w, r14w
0x180011823  jnb     short loc_18001186C
0x180011825  mov     rcx, [rsp+98h+arg_0]
0x18001182d  lea     r9, CMAP_TABLELOC_CONTROL
0x180011834  movzx   eax, bp
0x180011837  mov     r8d, 8
0x18001183d  lea     rdx, [r12+rax*8]
0x180011841  lea     rax, [rsp+98h+var_68]
0x180011846  mov     [rsp+98h+var_70], rax
0x18001184b  mov     [rsp+98h+var_78], esi
0x18001184f  call    WriteGeneric
0x180011854  movzx   ebx, ax
0x180011857  test    ax, ax
0x18001185a  jnz     short loc_18001186C
0x18001185c  movzx   eax, [rsp+98h+var_68]
0x180011861  inc     bp
0x180011864  add     esi, eax
0x180011866  cmp     bp, r14w
0x18001186a  jb      short loc_180011825
0x18001186c  mov     rbp, [rsp+98h+arg_0]
0x180011874  mov     rcx, rdi
0x180011877  call    Mem_Free
0x18001187c  test    bx, bx
0x18001187f  jnz     short loc_180011896
0x180011881  mov     r8d, r13d
0x180011884  lea     rdx, aCmap; "cmap"
0x18001188b  mov     rcx, rbp
0x18001188e  call    UpdateDirEntry
0x180011893  movzx   ebx, ax
0x180011896  mov     rax, [rsp+98h+arg_30]
0x18001189e  mov     [rax], r13d
0x1800118a1  movzx   eax, bx
0x1800118a4  add     rsp, 58h
0x1800118a8  pop     r15
0x1800118aa  pop     r14
0x1800118ac  pop     r13
0x1800118ae  pop     r12
0x1800118b0  pop     rdi
0x1800118b1  pop     rsi
0x1800118b2  pop     rbp
0x1800118b3  pop     rbx
0x1800118b4  retn
```
