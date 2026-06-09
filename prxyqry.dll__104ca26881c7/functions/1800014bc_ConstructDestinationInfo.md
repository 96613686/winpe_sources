# ConstructDestinationInfo

- ea: `0x1800014bc`
- end: `0x180001a45`
- name: `ConstructDestinationInfo`
- size: `1417`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, void *, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002130`

## callees

- `0x1800014bc`
- `0x180002e04`
- `0x180003035`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001736`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001748`

## pseudocode

```c
__int64 __fastcall ConstructDestinationInfo(
        _QWORD *a1,
        _DWORD *a2,
        unsigned __int64 a3,
        _WORD *a4,
        _WORD *a5,
        void *Src,
        void *a7,
        size_t Size)
{
  DWORD LastError; // ebx
  _WORD *v9; // r15
  __int64 v10; // r10
  _WORD *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  SIZE_T v15; // rdi
  __int64 v16; // r12
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  _WORD *v24; // rax
  __int64 v25; // r14
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r13
  HANDLE ProcessHeap; // rax
  _DWORD *v32; // rax
  _DWORD *v33; // rsi
  __int64 v34; // r9
  unsigned __int64 v35; // rax
  __int64 v36; // r8
  _WORD *v37; // rdx
  _WORD *v38; // rcx
  unsigned int v39; // r8d
  unsigned __int64 v40; // rdx
  _WORD *v41; // r11
  __int64 v42; // rcx
  _WORD *v43; // rax
  _WORD *v44; // rcx
  unsigned int v45; // ecx
  unsigned __int64 v46; // rax
  _WORD *v47; // r8
  _WORD *v48; // rdx
  _WORD *v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v55; // [rsp+90h] [rbp+18h]

  LastError = 0;
  *a1 = 0;
  v9 = (_WORD *)a3;
  *a2 = 0;
  if ( !a3 )
    goto LABEL_99;
  v10 = 0x7FFFFFFF;
  v11 = (_WORD *)a3;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = (0x7FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
  if ( !v10 )
  {
LABEL_99:
    v19 = 87;
    LastError = 87;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v21 = 24;
      goto LABEL_103;
    }
    return LastError;
  }
  v13 = v12 + 1;
  if ( v12 + 1 < v12
    || (v14 = 2 * v13, v55 = 2 * v13, !is_mul_ok(v13, 2u))
    || (v15 = v14 + 52, v14 >= 0xFFFFFFFFFFFFFFCCuLL) )
  {
    v19 = 534;
    LastError = 534;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v21 = 25;
      goto LABEL_103;
    }
    return LastError;
  }
  v16 = 0;
  if ( a4 )
  {
    v17 = 0x7FFFFFFF;
    v18 = a4;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    a3 = (0x7FFFFFFF - v17) & -(__int64)(v17 != 0);
    if ( !v17 )
    {
      v19 = 87;
      LastError = 87;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 26;
LABEL_103:
        WPP_SF_d(v20[2], v21, a3, v19);
        return LastError;
      }
      return LastError;
    }
    v22 = a3 + 1;
    if ( a3 + 1 < a3 || (v23 = 2 * v22, v16 = 2 * v22, !is_mul_ok(v22, 2u)) || v23 + v15 < v15 )
    {
      v19 = 534;
      LastError = 534;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 27;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += v23;
  }
  v24 = a5;
  v25 = 0;
  if ( a5 )
  {
    v26 = 0x7FFFFFFF;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v26;
    }
    while ( v26 );
    v27 = (0x7FFFFFFF - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64);
    if ( !v26 )
    {
      v19 = 87;
      LastError = 87;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 28;
        goto LABEL_103;
      }
      return LastError;
    }
    v28 = v27 + 1;
    if ( v27 + 1 < v27 || (v29 = 2 * v28, v25 = 2 * v28, !is_mul_ok(v28, 2u)) || v29 + v15 < v15 )
    {
      v19 = 534;
      LastError = 534;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 29;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += v29;
  }
  v30 = 0;
  if ( Src )
  {
    if ( v15 + 16 < v15 )
    {
      v19 = 534;
      LastError = 534;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 30;
        goto LABEL_103;
      }
      return LastError;
    }
    v30 = 16;
    v15 += 16LL;
  }
  if ( (_DWORD)Size && a7 )
  {
    if ( v15 + (unsigned int)Size < v15 )
    {
      v19 = 534;
      LastError = 534;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v21 = 31;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += (unsigned int)Size;
  }
  ProcessHeap = GetProcessHeap();
  v32 = HeapAlloc(ProcessHeap, 8u, v15);
  v33 = v32;
  if ( v32 )
  {
    v34 = 2147483646;
    v32[3] = v55;
    v32[2] = 52;
    v35 = (unsigned __int64)v55 >> 1;
    if ( v35 )
    {
      v36 = 2147483646;
      v37 = v33 + 13;
      do
      {
        if ( !v36 )
          break;
        if ( !*v9 )
          break;
        *v37++ = *v9++;
        --v36;
        --v35;
      }
      while ( v35 );
      v38 = v37 - 1;
      if ( v35 )
        v38 = v37;
      *v38 = 0;
    }
    if ( v16 )
    {
      v39 = v55 + v33[2];
      v33[5] = v16;
      v40 = (unsigned __int64)(unsigned int)v16 >> 1;
      v33[4] = v39;
      if ( v40 )
      {
        v41 = a4;
        v42 = 2147483646;
        v43 = (_WORD *)((char *)v33 + v39);
        do
        {
          if ( !v42 )
            break;
          if ( !*v41 )
            break;
          *v43++ = *v41++;
          --v42;
          --v40;
        }
        while ( v40 );
        v44 = v43 - 1;
        if ( v40 )
          v44 = v43;
        *v44 = 0;
      }
    }
    if ( v25 )
    {
      v45 = v16 + v55 + 52;
      v33[7] = v25;
      v46 = (unsigned __int64)(unsigned int)v25 >> 1;
      v33[6] = v45;
      if ( v46 )
      {
        v47 = a5;
        v48 = (_WORD *)((char *)v33 + v45);
        do
        {
          if ( !v34 )
            break;
          if ( !*v47 )
            break;
          *v48++ = *v47++;
          --v34;
          --v46;
        }
        while ( v46 );
        v49 = v48 - 1;
        if ( v46 )
          v49 = v48;
        *v49 = 0;
      }
    }
    if ( v30 )
    {
      v50 = (unsigned int)v25 + (_DWORD)v16 + v55 + 52;
      v33[9] = v30;
      v33[8] = v50;
      memcpy_0((char *)v33 + v50, Src, (unsigned int)v30);
    }
    if ( a7 && (_DWORD)Size )
    {
      v33[11] = Size;
      v51 = (_DWORD)v16 + (_DWORD)v25 + (_DWORD)v30 + v55 + 52;
      v33[10] = v51;
      memcpy_0((char *)v33 + v51, a7, (unsigned int)Size);
    }
    *a1 = v33;
    *a2 = v15;
  }
  else
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v21 = 32;
      v19 = LastError;
      goto LABEL_103;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800014bc  mov     [rsp+arg_18], r9
0x1800014c1  mov     [rsp+arg_8], rdx
0x1800014c6  mov     [rsp+arg_0], rcx
0x1800014cb  push    rbx
0x1800014cc  push    rbp
0x1800014cd  push    rsi
0x1800014ce  push    rdi
0x1800014cf  push    r12
0x1800014d1  push    r13
0x1800014d3  push    r14
0x1800014d5  push    r15
0x1800014d7  sub     rsp, 38h
0x1800014db  xor     ebx, ebx
0x1800014dd  mov     r11, r9
0x1800014e0  mov     [rcx], rbx
0x1800014e3  mov     r15, r8
0x1800014e6  mov     [rdx], ebx
0x1800014e8  lea     esi, [rbx+1]
0x1800014eb  test    r8, r8
0x1800014ee  jz      loc_1800019FD
0x1800014f4  mov     r9d, 7FFFFFFFh
0x1800014fa  lea     ebp, [rbx+2]
0x1800014fd  mov     r10d, r9d
0x180001500  mov     rax, r8
0x180001503  cmp     [rax], bx
0x180001506  jz      short loc_180001510
0x180001508  add     rax, rbp
0x18000150b  sub     r10, rsi
0x18000150e  jnz     short loc_180001503
0x180001510  mov     rcx, r9
0x180001513  mov     rax, r10
0x180001516  sub     rcx, r10
0x180001519  neg     rax
0x18000151c  sbb     rdx, rdx
0x18000151f  and     rdx, rcx
0x180001522  test    r10, r10
0x180001525  jz      loc_1800019FD
0x18000152b  lea     rcx, [rdx+1]
0x18000152f  cmp     rcx, rdx
0x180001532  jb      loc_1800019CE
0x180001538  mov     rax, rbp
0x18000153b  mov     [rsp+78h+arg_10], rbx
0x180001543  mul     rcx
0x180001546  mov     [rsp+78h+arg_10], rax
0x18000154e  test    rdx, rdx
0x180001551  jnz     loc_1800019CE
0x180001557  lea     rdi, [rax+34h]
0x18000155b  cmp     rdi, 34h ; '4'
0x18000155f  jb      loc_1800019CE
0x180001565  mov     r12, rbx
0x180001568  test    r11, r11
0x18000156b  jz      loc_1800015FD
0x180001571  mov     rdx, r9
0x180001574  mov     rax, r11
0x180001577  cmp     [rax], bx
0x18000157a  jz      short loc_180001584
0x18000157c  add     rax, rbp
0x18000157f  sub     rdx, rsi
0x180001582  jnz     short loc_180001577
0x180001584  mov     rcx, r9
0x180001587  mov     rax, rdx
0x18000158a  sub     rcx, rdx
0x18000158d  neg     rax
0x180001590  sbb     r8, r8
0x180001593  and     r8, rcx
0x180001596  test    rdx, rdx
0x180001599  jnz     short loc_1800015D6
0x18000159b  lea     r9d, [rdx+57h]
0x18000159f  mov     ebx, r9d
0x1800015a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015a9  lea     rax, WPP_GLOBAL_Control
0x1800015b0  cmp     rcx, rax
0x1800015b3  jz      loc_180001A32
0x1800015b9  test    byte ptr [rcx+1Ch], 40h
0x1800015bd  jz      loc_180001A32
0x1800015c3  cmp     [rcx+19h], sil
0x1800015c7  jb      loc_180001A32
0x1800015cd  lea     edx, [r9-3Dh]
0x1800015d1  jmp     loc_180001A29
0x1800015d6  lea     rcx, [r8+1]
0x1800015da  cmp     rcx, r8
0x1800015dd  jb      loc_180001670
0x1800015e3  mov     rax, rbp
0x1800015e6  mul     rcx
0x1800015e9  mov     r12, rax
0x1800015ec  test    rdx, rdx
0x1800015ef  jnz     short loc_180001670
0x1800015f1  lea     rcx, [rax+rdi]
0x1800015f5  cmp     rcx, rdi
0x1800015f8  jb      short loc_180001670
0x1800015fa  mov     rdi, rcx
0x1800015fd  mov     rax, [rsp+78h+arg_20]
0x180001605  mov     r14, rbx
0x180001608  test    rax, rax
0x18000160b  jz      loc_1800016DD
0x180001611  mov     rcx, r9
0x180001614  cmp     [rax], bx
0x180001617  jz      short loc_180001621
0x180001619  add     rax, rbp
0x18000161c  sub     rcx, rsi
0x18000161f  jnz     short loc_180001614
0x180001621  sub     r9, rcx
0x180001624  mov     rax, rcx
0x180001627  neg     rax
0x18000162a  sbb     rdx, rdx
0x18000162d  and     rdx, r9
0x180001630  test    rcx, rcx
0x180001633  jnz     short loc_1800016AE
0x180001635  lea     r9d, [rcx+57h]
0x180001639  mov     ebx, r9d
0x18000163c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001643  lea     rax, WPP_GLOBAL_Control
0x18000164a  cmp     rcx, rax
0x18000164d  jz      loc_180001A32
0x180001653  test    byte ptr [rcx+1Ch], 40h
0x180001657  jz      loc_180001A32
0x18000165d  cmp     [rcx+19h], sil
0x180001661  jb      loc_180001A32
0x180001667  lea     edx, [r9-3Bh]
0x18000166b  jmp     loc_180001A29
0x180001670  mov     r9d, 216h
0x180001676  mov     ebx, r9d
0x180001679  mov     rcx, cs:WPP_GLOBAL_Control
0x180001680  lea     rax, WPP_GLOBAL_Control
0x180001687  cmp     rcx, rax
0x18000168a  jz      loc_180001A32
0x180001690  test    byte ptr [rcx+1Ch], 40h
0x180001694  jz      loc_180001A32
0x18000169a  cmp     [rcx+19h], sil
0x18000169e  jb      loc_180001A32
0x1800016a4  mov     edx, 1Bh
0x1800016a9  jmp     loc_180001A29
0x1800016ae  lea     rcx, [rdx+1]
0x1800016b2  cmp     rcx, rdx
0x1800016b5  jb      loc_180001786
0x1800016bb  mov     rax, rbp
0x1800016be  mul     rcx
0x1800016c1  mov     r14, rax
0x1800016c4  test    rdx, rdx
0x1800016c7  jnz     loc_180001786
0x1800016cd  lea     rcx, [rax+rdi]
0x1800016d1  cmp     rcx, rdi
0x1800016d4  jb      loc_180001786
0x1800016da  mov     rdi, rcx
0x1800016dd  mov     r13, rbx
0x1800016e0  cmp     [rsp+78h+Src], rbx
0x1800016e8  jz      short loc_180001700
0x1800016ea  lea     rax, [rdi+10h]
0x1800016ee  cmp     rax, rdi
0x1800016f1  jb      loc_1800017C4
0x1800016f7  mov     r13d, 10h
0x1800016fd  mov     rdi, rax
0x180001700  mov     ebp, dword ptr [rsp+78h+Size]
0x180001707  test    ebp, ebp
0x180001709  jz      short loc_180001725
0x18000170b  cmp     [rsp+78h+arg_30], rbx
0x180001713  jz      short loc_180001725
0x180001715  lea     rcx, [rdi+rbp]
0x180001719  cmp     rcx, rdi
0x18000171c  jb      loc_180001802
0x180001722  mov     rdi, rcx
0x180001725  call    cs:__imp_GetProcessHeap
0x18000172b  mov     r8, rdi; dwBytes
0x18000172e  mov     edx, 8; dwFlags
0x180001733  mov     rcx, rax; hHeap
0x180001736  call    cs:__imp_HeapAlloc
0x18000173c  mov     rsi, rax
0x18000173f  test    rax, rax
0x180001742  jnz     loc_180001840
0x180001748  call    cs:__imp_GetLastError
0x18000174e  mov     ebx, eax
0x180001750  mov     rcx, cs:WPP_GLOBAL_Control
0x180001757  lea     rax, WPP_GLOBAL_Control
0x18000175e  cmp     rcx, rax
0x180001761  jz      loc_180001A32
0x180001767  test    byte ptr [rcx+1Ch], 40h
0x18000176b  jz      loc_180001A32
0x180001771  cmp     byte ptr [rcx+19h], 1
0x180001775  jb      loc_180001A32
0x18000177b  lea     edx, [rsi+20h]
0x18000177e  mov     r9d, ebx
0x180001781  jmp     loc_180001A29
0x180001786  mov     r9d, 216h
0x18000178c  mov     ebx, r9d
0x18000178f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001796  lea     rax, WPP_GLOBAL_Control
0x18000179d  cmp     rcx, rax
0x1800017a0  jz      loc_180001A32
0x1800017a6  test    byte ptr [rcx+1Ch], 40h
0x1800017aa  jz      loc_180001A32
0x1800017b0  cmp     [rcx+19h], sil
0x1800017b4  jb      loc_180001A32
0x1800017ba  mov     edx, 1Dh
0x1800017bf  jmp     loc_180001A29
0x1800017c4  mov     r9d, 216h
0x1800017ca  mov     ebx, r9d
0x1800017cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017d4  lea     rax, WPP_GLOBAL_Control
0x1800017db  cmp     rcx, rax
0x1800017de  jz      loc_180001A32
0x1800017e4  test    byte ptr [rcx+1Ch], 40h
0x1800017e8  jz      loc_180001A32
0x1800017ee  cmp     [rcx+19h], sil
0x1800017f2  jb      loc_180001A32
0x1800017f8  mov     edx, 1Eh
0x1800017fd  jmp     loc_180001A29
0x180001802  mov     r9d, 216h
0x180001808  mov     ebx, r9d
0x18000180b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001812  lea     rax, WPP_GLOBAL_Control
0x180001819  cmp     rcx, rax
0x18000181c  jz      loc_180001A32
0x180001822  test    byte ptr [rcx+1Ch], 40h
0x180001826  jz      loc_180001A32
0x18000182c  cmp     [rcx+19h], sil
0x180001830  jb      loc_180001A32
0x180001836  mov     edx, 1Fh
0x18000183b  jmp     loc_180001A29
0x180001840  mov     r10d, dword ptr [rsp+78h+arg_10]
0x180001848  mov     r9d, 7FFFFFFEh
0x18000184e  mov     [rax+0Ch], r10d
0x180001852  mov     dword ptr [rax+8], 34h ; '4'
0x180001859  mov     eax, r10d
0x18000185c  shr     rax, 1
0x18000185f  jz      short loc_18000189E
0x180001861  mov     r8d, r9d
0x180001864  lea     rdx, [rsi+34h]
0x180001868  test    r8, r8
0x18000186b  jz      short loc_18000188A
0x18000186d  movzx   ecx, word ptr [r15]
0x180001871  test    cx, cx
0x180001874  jz      short loc_18000188A
0x180001876  mov     [rdx], cx
0x180001879  add     r15, 2
0x18000187d  add     rdx, 2
0x180001881  dec     r8
0x180001884  sub     rax, 1
0x180001888  jnz     short loc_180001868
0x18000188a  xor     r15d, r15d
0x18000188d  lea     rcx, [rdx-2]
0x180001891  test    rax, rax
0x180001894  cmovnz  rcx, rdx
0x180001898  mov     [rcx], r15w
0x18000189c  jmp     short loc_1800018A1
0x18000189e  xor     r15d, r15d
0x1800018a1  test    r12, r12
0x1800018a4  jz      short loc_180001900
0x1800018a6  mov     r8d, [rsi+8]
0x1800018aa  mov     edx, r12d
0x1800018ad  add     r8d, r10d
0x1800018b0  mov     [rsi+14h], edx
0x1800018b3  shr     rdx, 1
0x1800018b6  mov     [rsi+10h], r8d
0x1800018ba  jz      short loc_180001900
0x1800018bc  mov     r11, [rsp+78h+arg_18]
0x1800018c4  mov     rcx, r9
0x1800018c7  mov     eax, r8d
0x1800018ca  add     rax, rsi
0x1800018cd  test    rcx, rcx
0x1800018d0  jz      short loc_1800018F1
0x1800018d2  movzx   r8d, word ptr [r11]
0x1800018d6  test    r8w, r8w
0x1800018da  jz      short loc_1800018F1
0x1800018dc  mov     [rax], r8w
0x1800018e0  add     r11, 2
0x1800018e4  add     rax, 2
0x1800018e8  dec     rcx
0x1800018eb  sub     rdx, 1
0x1800018ef  jnz     short loc_1800018CD
0x1800018f1  test    rdx, rdx
0x1800018f4  lea     rcx, [rax-2]
0x1800018f8  cmovnz  rcx, rax
0x1800018fc  mov     [rcx], r15w
0x180001900  test    r14, r14
0x180001903  jz      short loc_180001958
0x180001905  mov     eax, r14d
0x180001908  lea     ecx, [r10+34h]
0x18000190c  add     ecx, r12d
0x18000190f  mov     [rsi+1Ch], eax
0x180001912  shr     rax, 1
0x180001915  mov     [rsi+18h], ecx
0x180001918  jz      short loc_180001958
0x18000191a  mov     r8, [rsp+78h+arg_20]
0x180001922  mov     edx, ecx
0x180001924  add     rdx, rsi
0x180001927  test    r9, r9
0x18000192a  jz      short loc_180001949
0x18000192c  movzx   ecx, word ptr [r8]
0x180001930  test    cx, cx
0x180001933  jz      short loc_180001949
0x180001935  mov     [rdx], cx
0x180001938  add     r8, 2
0x18000193c  add     rdx, 2
0x180001940  dec     r9
0x180001943  sub     rax, 1
0x180001947  jnz     short loc_180001927
0x180001949  test    rax, rax
0x18000194c  lea     rcx, [rdx-2]
0x180001950  cmovnz  rcx, rdx
0x180001954  mov     [rcx], r15w
  ... truncated ...
```
