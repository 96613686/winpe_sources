# sqlite3PagerOpen

- ea: `0x140064690`
- end: `0x140064c35`
- name: `sqlite3PagerOpen`
- size: `1445`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004efa0`

## callees

- `0x1400026c0`
- `0x14003fd18`
- `0x140048f54`
- `0x1400490a4`
- `0x1400504f4`
- `0x140054178`
- `0x140062c2c`
- `0x140062d60`
- `0x140063aac`
- `0x140064690`
- `0x140064e78`
- `0x140065028`
- `0x140066240`
- `0x14008ac90`
- `0x14008f690`
- `0x1400a7308`
- `0x1400a8010`

## pseudocode

```c
__int64 __fastcall sqlite3PagerOpen(__int64 a1, __int64 *a2, _BYTE *a3, __int64 a4, char a5, int a6, unsigned int a7)
{
  int v7; // r13d
  int v8; // r15d
  _BYTE *v9; // rdi
  _BYTE *v11; // r14
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // esi
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // ebp
  unsigned int v19; // ebx
  _BYTE *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r15
  _BYTE *i; // rsi
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  _BYTE *v28; // rdx
  _BYTE *v29; // rcx
  size_t v30; // r12
  __int64 v31; // rax
  __int64 v32; // rsi
  __int64 result; // rax
  __int64 v34; // rax
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  char *v37; // rax
  char *v38; // rbx
  char *v39; // rbx
  char *v40; // rbx
  unsigned int v41; // r12d
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rax
  __int16 v45; // bx
  unsigned int v46; // ecx
  char v47; // r14
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(); // rbx
  __int64 v50; // rdx
  char v51; // bl
  int v52; // ebx
  int v53; // [rsp+30h] [rbp-58h]
  signed int v54; // [rsp+30h] [rbp-58h]
  char *v55; // [rsp+30h] [rbp-58h]
  void *Src; // [rsp+38h] [rbp-50h]
  size_t Size; // [rsp+40h] [rbp-48h]
  unsigned int v60; // [rsp+A8h] [rbp+20h] BYREF

  v7 = a6;
  v8 = 0;
  a7 = 4096;
  v9 = a3;
  v60 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 80;
  v14 = 1;
  if ( *(int *)(a1 + 4) > 80 )
    v13 = *(_DWORD *)(a1 + 4);
  v15 = (a5 & 2) == 0;
  v53 = v13;
  *a2 = 0;
  if ( !v15 )
  {
    v60 = 1;
    if ( a3 )
    {
      if ( *a3 )
      {
        v16 = sqlite3DbStrDup(0, a3);
        v11 = (_BYTE *)v16;
        if ( v16 )
        {
          v17 = -1;
          do
            ++v17;
          while ( *(_BYTE *)(v16 + v17) );
          v12 = v17 & 0x3FFFFFFF;
          Src = 0;
          v9 = 0;
          v18 = 0;
          goto LABEL_30;
        }
        return 7;
      }
    }
  }
  Src = 0;
  v18 = 0;
  if ( a3 && *a3 )
  {
    v19 = *(_DWORD *)(a1 + 8) + 1;
    v20 = (_BYTE *)sqlite3Malloc((int)(2 * v19));
    v11 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _BYTE *))(a1 + 64))(a1, v9, v19, v20);
      if ( v18 == 512 )
        v18 = (v7 & 0x1000000) != 0 ? 0x60E : 0;
      v21 = -1;
      do
        ++v21;
      while ( v11[v21] );
      v22 = -1;
      do
        ++v22;
      while ( v9[v22] );
      v23 = (__int64)&v9[(v22 & 0x3FFFFFFF) + 1];
      Src = (void *)v23;
      for ( i = (_BYTE *)v23; *i; i = &v28[v27 + 1] )
      {
        v25 = -1;
        do
          ++v25;
        while ( i[v25] );
        v26 = v25 + 1;
        v27 = -1;
        v28 = &i[v26];
        do
          ++v27;
        while ( v28[v27] );
      }
      if ( !v18 )
      {
        v14 = (_DWORD)i - v23 + 1;
        v12 = v21 & 0x3FFFFFFF;
        if ( (signed int)((v21 & 0x3FFFFFFF) + 8) <= *(_DWORD *)(a1 + 8) )
        {
          v8 = 0;
          goto LABEL_30;
        }
        v8 = 0;
        v18 = sqlite3CantopenError(60986);
        if ( !v18 )
          goto LABEL_30;
      }
      v29 = v11;
LABEL_69:
      sqlite3_free(v29);
      return v18;
    }
    return 7;
  }
LABEL_30:
  Size = v14;
  v54 = (v53 + 7) & 0xFFFFFFF8;
  v30 = v12;
  v31 = sqlite3MallocZero(((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 422 + v14 + (__int64)(2 * v54) + 3LL * v12);
  v32 = v31;
  if ( !v31 )
  {
    if ( v11 )
      sqlite3_free(v11);
    return 7;
  }
  v34 = v31 + 312;
  *(_QWORD *)(v32 + 288) = v34;
  *(_QWORD *)(v32 + 72) = v34 + 80;
  v35 = v34 + 80 + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_QWORD *)(v32 + 88) = v35;
  v36 = v35 + v54;
  *(_QWORD *)(v32 + 80) = v36;
  v37 = (char *)(v36 + v54 + 12LL);
  *(_QWORD *)(v54 + v36) = v32;
  v55 = v37;
  *(_QWORD *)(v32 + 216) = v37;
  if ( v12 )
  {
    memcpy_0(v37, v11, v12);
    v38 = &v55[v12 + 1];
    if ( Src )
    {
      memcpy_0(v38, Src, Size);
      v39 = &v38[Size];
    }
    else
    {
      v39 = v38 + 1;
    }
    *(_QWORD *)(v32 + 224) = v39;
    memcpy_0(v39, v11, v30);
    *(_QWORD *)&v39[v30] = 0x6C616E72756F6A2DLL;
    v40 = &v39[v30 + 9];
    *(_QWORD *)(v32 + 304) = v40;
    memcpy_0(v40, v11, v30);
    *(_DWORD *)&v40[v30] = 1818326829;
    if ( v11 )
      sqlite3_free(v11);
  }
  else
  {
    *(_QWORD *)(v32 + 224) = 0;
    *(_QWORD *)(v32 + 304) = 0;
  }
  v41 = v60;
  *(_QWORD *)v32 = a1;
  *(_DWORD *)(v32 + 180) = v7;
  if ( !v9 || !*v9 )
    goto LABEL_55;
  v42 = *(_QWORD *)(v32 + 72);
  v43 = *(_QWORD *)(v32 + 216);
  v60 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, unsigned int *))(a1 + 40))(
          a1,
          v43,
          v42,
          v7 & 0x1087F7F,
          &v60);
  v7 = v60 & 1;
  v8 = (v60 >> 7) & 1;
  *(_BYTE *)(v32 + 20) = (v60 & 0x80) != 0;
  if ( !v18 )
  {
    v44 = **(_QWORD **)(v32 + 72);
    if ( v44 )
      v45 = (*(__int64 (**)(void))(v44 + 96))();
    else
      v45 = 0;
    if ( !v7 )
    {
      setSectorSize(v32);
      v46 = *(_DWORD *)(v32 + 184);
      if ( v46 > 0x1000 )
      {
        if ( v46 > 0x2000 )
          v46 = 0x2000;
        a7 = v46;
      }
    }
    *(_BYTE *)(v32 + 17) = sqlite3_uri_boolean(*(_QWORD *)(v32 + 216), "nolock", 0);
    if ( (v45 & 0x2000) != 0 || (unsigned int)sqlite3_uri_boolean(*(_QWORD *)(v32 + 216), "immutable", 0) )
    {
      LOBYTE(v7) = 1;
LABEL_55:
      *(_WORD *)(v32 + 21) = 1025;
      LOBYTE(v7) = v7 & 1;
      *(_BYTE *)(v32 + 17) = 1;
      v47 = 1;
      goto LABEL_56;
    }
  }
  v47 = 0;
LABEL_56:
  if ( v18 )
    goto LABEL_68;
  v18 = sqlite3PagerSetPagesize(v32, &a7, 0xFFFFFFFFLL);
  if ( v18 )
    goto LABEL_68;
  v48 = *(_QWORD *)(v32 + 288);
  v49 = 0;
  if ( !v41 )
    v49 = pagerStress;
  memset_0(*(void **)(v32 + 288), 0, 0x50u);
  v50 = a7;
  *(_DWORD *)(v48 + 40) = v18 + 1;
  *(_DWORD *)(v48 + 36) = v18 + 1;
  *(_BYTE *)(v48 + 48) = (v18 + 1) ^ v41;
  *(_DWORD *)(v48 + 44) = 136;
  *(_BYTE *)(v48 + 49) = 2;
  *(_QWORD *)(v48 + 56) = v49;
  *(_QWORD *)(v48 + 64) = v32;
  *(_DWORD *)(v48 + 32) = 100;
  v18 = sqlite3PcacheSetPageSize(v48, v50);
  if ( v18 )
  {
LABEL_68:
    sqlite3OsClose(*(_QWORD *)(v32 + 72));
    pcache1Free(*(_QWORD *)(v32 + 280));
    v29 = (_BYTE *)v32;
    goto LABEL_69;
  }
  v51 = ~a5;
  *(_DWORD *)(v32 + 188) = 0x3FFFFFFF;
  v52 = v51 & 1;
  *(_BYTE *)(v32 + 16) = v47;
  *(_BYTE *)(v32 + 10) = v52;
  *(_BYTE *)(v32 + 8) = v47;
  *(_BYTE *)(v32 + 23) = v47;
  *(_BYTE *)(v32 + 19) = v41;
  *(_BYTE *)(v32 + 18) = v7;
  sqlite3PagerSetFlags(v32, 35);
  *(_WORD *)(v32 + 176) = 136;
  *(_QWORD *)(v32 + 208) = -1;
  setSectorSize(v32);
  if ( v52 )
  {
    if ( v41 || v8 )
      *(_BYTE *)(v32 + 9) = 4;
  }
  else
  {
    *(_BYTE *)(v32 + 9) = 2;
  }
  *(_QWORD *)(v32 + 264) = pageReinit;
  setGetterMethod(v32);
  result = 0;
  *a2 = v32;
  return result;
}

```

## disassembly

```asm
0x140064690  mov     rax, rsp
0x140064693  mov     [rax+18h], rbx
0x140064697  mov     [rax+20h], r9d
0x14006469b  mov     [rax+10h], rdx
0x14006469f  mov     [rax+8], rcx
0x1400646a3  push    rbp
0x1400646a4  push    rsi
0x1400646a5  push    rdi
0x1400646a6  push    r12
0x1400646a8  push    r13
0x1400646aa  push    r14
0x1400646ac  push    r15
0x1400646ae  sub     rsp, 50h
0x1400646b2  mov     r13d, [rsp+88h+arg_28]
0x1400646ba  xor     r15d, r15d
0x1400646bd  mov     dword ptr [rax+38h], 1000h
0x1400646c4  mov     rdi, r8
0x1400646c7  mov     r12, rcx
0x1400646ca  mov     [rsp+88h+arg_18], r15d
0x1400646d2  mov     r14d, r15d
0x1400646d5  mov     ebx, r15d
0x1400646d8  lea     eax, [r15+50h]
0x1400646dc  cmp     [rcx+4], eax
0x1400646df  lea     esi, [r15+1]
0x1400646e3  cmovg   eax, [rcx+4]
0x1400646e7  test    [rsp+88h+arg_20], 2
0x1400646ef  mov     dword ptr [rsp+88h+var_58], eax
0x1400646f3  mov     [rdx], r15
0x1400646f6  jz      short loc_140064742
0x1400646f8  mov     [rsp+88h+arg_18], esi
0x1400646ff  test    r8, r8
0x140064702  jz      short loc_140064742
0x140064704  cmp     [r8], r15b
0x140064707  jz      short loc_140064742
0x140064709  mov     rdx, r8
0x14006470c  xor     ecx, ecx
0x14006470e  call    sqlite3DbStrDup
0x140064713  mov     r14, rax
0x140064716  test    rax, rax
0x140064719  jz      loc_1400648A8
0x14006471f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140064723  inc     rbx
0x140064726  cmp     [rax+rbx], r15b
0x14006472a  jnz     short loc_140064723
0x14006472c  and     ebx, 3FFFFFFFh
0x140064732  mov     [rsp+88h+Src], r15
0x140064737  mov     rdi, r15
0x14006473a  mov     ebp, r15d
0x14006473d  jmp     loc_140064848
0x140064742  mov     [rsp+88h+Src], r15
0x140064747  mov     ebp, r15d
0x14006474a  test    rdi, rdi
0x14006474d  jz      loc_140064848
0x140064753  cmp     [r8], r15b
0x140064756  jz      loc_140064848
0x14006475c  mov     ebx, [rcx+8]
0x14006475f  inc     ebx
0x140064761  lea     eax, [rbx+rbx]
0x140064764  movsxd  rcx, eax
0x140064767  call    sqlite3Malloc
0x14006476c  mov     r14, rax
0x14006476f  test    rax, rax
0x140064772  jz      loc_1400648A8
0x140064778  mov     [rax], r15b
0x14006477b  mov     r9, rax
0x14006477e  mov     rax, [r12+40h]
0x140064783  mov     r8d, ebx
0x140064786  mov     rdx, rdi
0x140064789  mov     rcx, r12
0x14006478c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064791  mov     ebp, eax
0x140064793  cmp     eax, 200h
0x140064798  jnz     short loc_1400647AC
0x14006479a  mov     eax, r13d
0x14006479d  and     eax, 1000000h
0x1400647a2  neg     eax
0x1400647a4  sbb     ebp, ebp
0x1400647a6  and     ebp, 60Eh
0x1400647ac  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400647b0  mov     rcx, r9
0x1400647b3  inc     rcx
0x1400647b6  cmp     [r14+rcx], r15b
0x1400647ba  jnz     short loc_1400647B3
0x1400647bc  mov     rax, r9
0x1400647bf  inc     rax
0x1400647c2  cmp     [rdi+rax], r15b
0x1400647c6  jnz     short loc_1400647BF
0x1400647c8  and     eax, 3FFFFFFFh
0x1400647cd  lea     r15, [rdi+1]
0x1400647d1  add     r15, rax
0x1400647d4  xor     r8d, r8d
0x1400647d7  mov     [rsp+88h+Src], r15
0x1400647dc  mov     rsi, r15
0x1400647df  cmp     [r15], r8b
0x1400647e2  jz      short loc_14006480F
0x1400647e4  mov     rax, r9
0x1400647e7  inc     rax
0x1400647ea  cmp     [rsi+rax], r8b
0x1400647ee  jnz     short loc_1400647E7
0x1400647f0  lea     rdx, [rax+1]
0x1400647f4  mov     rax, r9
0x1400647f7  add     rdx, rsi
0x1400647fa  inc     rax
0x1400647fd  cmp     [rdx+rax], r8b
0x140064801  jnz     short loc_1400647FA
0x140064803  lea     rsi, [rax+1]
0x140064807  add     rsi, rdx
0x14006480a  cmp     [rsi], r8b
0x14006480d  jnz     short loc_1400647E4
0x14006480f  test    ebp, ebp
0x140064811  jnz     short loc_14006483D
0x140064813  and     ecx, 3FFFFFFFh
0x140064819  sub     esi, r15d
0x14006481c  inc     esi
0x14006481e  mov     ebx, ecx
0x140064820  lea     eax, [rcx+8]
0x140064823  cmp     eax, [r12+8]
0x140064828  jle     short loc_140064845
0x14006482a  mov     ecx, 0EE3Ah
0x14006482f  call    sqlite3CantopenError
0x140064834  xor     r15d, r15d
0x140064837  mov     ebp, eax
0x140064839  test    eax, eax
0x14006483b  jz      short loc_140064848
0x14006483d  mov     rcx, r14
0x140064840  jmp     loc_140064C16
0x140064845  xor     r15d, r15d
0x140064848  mov     eax, dword ptr [rsp+88h+var_58]
0x14006484c  mov     rdx, [rsp+88h+arg_0]
0x140064854  add     eax, 7
0x140064857  and     eax, 0FFFFFFF8h
0x14006485a  movsxd  rcx, esi
0x14006485d  mov     [rsp+88h+Size], rcx
0x140064862  mov     dword ptr [rsp+88h+var_58], eax
0x140064866  add     eax, eax
0x140064868  movsxd  r8, dword ptr [rdx+4]
0x14006486c  add     r8, 7
0x140064870  movsxd  rdx, eax
0x140064873  add     rdx, rcx
0x140064876  mov     r12d, ebx
0x140064879  and     r8, 0FFFFFFFFFFFFFFF8h
0x14006487d  add     r8, 1A6h
0x140064884  add     rdx, r8
0x140064887  lea     rcx, [r12+r12*2]
0x14006488b  add     rcx, rdx; Size
0x14006488e  call    sqlite3MallocZero
0x140064893  mov     rsi, rax
0x140064896  test    rax, rax
0x140064899  jnz     short loc_1400648B2
0x14006489b  test    r14, r14
0x14006489e  jz      short loc_1400648A8
0x1400648a0  mov     rcx, r14
0x1400648a3  call    sqlite3_free
0x1400648a8  mov     eax, 7
0x1400648ad  jmp     loc_140064C1D
0x1400648b2  movsxd  rdx, dword ptr [rsp+88h+var_58]
0x1400648b7  add     rax, 138h
0x1400648bd  mov     [rsi+120h], rax
0x1400648c4  lea     rcx, [rax+50h]
0x1400648c8  mov     rax, [rsp+88h+arg_0]
0x1400648d0  mov     [rsi+48h], rcx
0x1400648d4  movsxd  rax, dword ptr [rax+4]
0x1400648d8  add     rax, 7
0x1400648dc  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400648e0  add     rax, rcx
0x1400648e3  mov     [rsi+58h], rax
0x1400648e7  lea     rcx, [rax+rdx]
0x1400648eb  lea     rax, [rdx+0Ch]
0x1400648ef  mov     [rsi+50h], rcx
0x1400648f3  add     rax, rcx
0x1400648f6  mov     [rdx+rcx], rsi
0x1400648fa  mov     [rsp+88h+var_58], rax
0x1400648ff  mov     [rsi+0D8h], rax
0x140064906  test    ebx, ebx
0x140064908  jz      loc_14006499D
0x14006490e  mov     r8, r12; Size
0x140064911  mov     rdx, r14; Src
0x140064914  mov     rcx, rax; void *
0x140064917  call    memcpy_0
0x14006491c  mov     rax, [rsp+88h+Src]
0x140064921  inc     ebx
0x140064923  add     rbx, [rsp+88h+var_58]
0x140064928  test    rax, rax
0x14006492b  jz      short loc_140064944
0x14006492d  mov     r8, [rsp+88h+Size]; Size
0x140064932  mov     rdx, rax; Src
0x140064935  mov     rcx, rbx; void *
0x140064938  call    memcpy_0
0x14006493d  add     rbx, [rsp+88h+Size]
0x140064942  jmp     short loc_140064947
0x140064944  inc     rbx
0x140064947  mov     r8, r12; Size
0x14006494a  mov     [rsi+0E0h], rbx
0x140064951  mov     rdx, r14; Src
0x140064954  mov     rcx, rbx; void *
0x140064957  call    memcpy_0
0x14006495c  mov     rax, 6C616E72756F6A2Dh
0x140064966  mov     r8, r12; Size
0x140064969  mov     [r12+rbx], rax
0x14006496d  mov     rdx, r14; Src
0x140064970  add     rbx, 9
0x140064974  add     rbx, r12
0x140064977  mov     rcx, rbx; void *
0x14006497a  mov     [rsi+130h], rbx
0x140064981  call    memcpy_0
0x140064986  mov     dword ptr [rbx+r12], 6C61772Dh
0x14006498e  test    r14, r14
0x140064991  jz      short loc_1400649B3
0x140064993  mov     rcx, r14
0x140064996  call    sqlite3_free
0x14006499b  jmp     short loc_1400649B3
0x14006499d  mov     qword ptr [rsi+0E0h], 0
0x1400649a8  mov     qword ptr [rsi+130h], 0
0x1400649b3  mov     rax, [rsp+88h+arg_0]
0x1400649bb  mov     r12d, [rsp+88h+arg_18]
0x1400649c3  mov     [rsi], rax
0x1400649c6  mov     [rsi+0B4h], r13d
0x1400649cd  test    rdi, rdi
0x1400649d0  jz      loc_140064AC5
0x1400649d6  cmp     byte ptr [rdi], 0
0x1400649d9  jz      loc_140064AC5
0x1400649df  mov     r8, [rsi+48h]
0x1400649e3  lea     rcx, [rsp+88h+arg_18]
0x1400649eb  mov     rdx, [rsi+0D8h]
0x1400649f2  and     r13d, 1087F7Fh
0x1400649f9  mov     [rsp+88h+var_68], rcx
0x1400649fe  mov     r9d, r13d
0x140064a01  mov     rcx, rax
0x140064a04  mov     [rsp+88h+arg_18], 0
0x140064a0f  mov     rax, [rax+28h]
0x140064a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064a18  mov     r13d, [rsp+88h+arg_18]
0x140064a20  mov     ebp, eax
0x140064a22  mov     r15d, r13d
0x140064a25  and     r13d, 1
0x140064a29  shr     r15d, 7
0x140064a2d  and     r15d, 1
0x140064a31  mov     [rsi+14h], r15b
0x140064a35  test    eax, eax
0x140064a37  jnz     loc_140064BC3
0x140064a3d  mov     rcx, [rsi+48h]
0x140064a41  mov     rax, [rcx]
0x140064a44  test    rax, rax
0x140064a47  jnz     short loc_140064A4D
0x140064a49  xor     ebx, ebx
0x140064a4b  jmp     short loc_140064A58
0x140064a4d  mov     rax, [rax+60h]
0x140064a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064a56  mov     ebx, eax
0x140064a58  mov     edi, 2000h
0x140064a5d  test    r13d, r13d
0x140064a60  jnz     short loc_140064A84
0x140064a62  mov     rcx, rsi
0x140064a65  call    setSectorSize
0x140064a6a  mov     ecx, [rsi+0B8h]
0x140064a70  cmp     ecx, 1000h
0x140064a76  jbe     short loc_140064A84
0x140064a78  cmp     ecx, edi
0x140064a7a  cmova   ecx, edi
0x140064a7d  mov     [rsp+88h+arg_30], ecx
0x140064a84  mov     rcx, [rsi+0D8h]
0x140064a8b  lea     rdx, aNolock; "nolock"
0x140064a92  xor     r8d, r8d
0x140064a95  call    sqlite3_uri_boolean
0x140064a9a  mov     [rsi+11h], al
0x140064a9d  test    edi, ebx
0x140064a9f  jnz     short loc_140064ABF
0x140064aa1  mov     rcx, [rsi+0D8h]
0x140064aa8  lea     rdx, aImmutable; "immutable"
0x140064aaf  xor     r8d, r8d
0x140064ab2  call    sqlite3_uri_boolean
0x140064ab7  test    eax, eax
0x140064ab9  jz      loc_140064BC3
0x140064abf  mov     r13d, 1
0x140064ac5  mov     word ptr [rsi+15h], 401h
0x140064acb  and     r13d, 1
0x140064acf  mov     byte ptr [rsi+11h], 1
0x140064ad3  mov     r14b, 1
0x140064ad6  test    ebp, ebp
0x140064ad8  jnz     loc_140064BFE
0x140064ade  or      r8d, 0FFFFFFFFh
0x140064ae2  lea     rdx, [rsp+88h+arg_30]
0x140064aea  mov     rcx, rsi
0x140064aed  call    sqlite3PagerSetPagesize
0x140064af2  mov     ebp, eax
0x140064af4  test    eax, eax
0x140064af6  jnz     loc_140064BFE
0x140064afc  mov     rdi, [rsi+120h]
0x140064b03  lea     rax, pagerStress
0x140064b0a  xor     ebx, ebx
0x140064b0c  lea     r8d, [rbp+50h]; Size
0x140064b10  test    r12d, r12d
0x140064b13  mov     rcx, rdi; void *
0x140064b16  cmovz   rbx, rax
0x140064b1a  xor     edx, edx; Val
0x140064b1c  call    memset_0
0x140064b21  mov     edx, [rsp+88h+arg_30]
0x140064b28  lea     ecx, [rbp+1]
0x140064b2b  mov     al, r12b
0x140064b2e  mov     [rdi+28h], ecx
  ... truncated ...
```
