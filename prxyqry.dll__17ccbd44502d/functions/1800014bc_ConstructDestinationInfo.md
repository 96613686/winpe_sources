# ConstructDestinationInfo

- ea: `0x1800014bc`
- end: `0x180001a58`
- name: `ConstructDestinationInfo`
- size: `1436`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, unsigned __int64, _WORD *, _WORD *, void *Src, void *, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021c0`

## callees

- `0x1800014bc`
- `0x180002fa0`
- `0x1800031f5`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000173c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000173c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001754`

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
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  _WORD *v23; // rax
  __int64 v24; // r14
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r13
  HANDLE ProcessHeap; // rax
  _DWORD *v31; // rax
  _DWORD *v32; // rsi
  __int64 v33; // r9
  unsigned __int64 v34; // rax
  __int64 v35; // r8
  _WORD *v36; // rdx
  _WORD *v37; // rcx
  unsigned int v38; // r8d
  unsigned __int64 v39; // rdx
  _WORD *v40; // r11
  __int64 v41; // rcx
  _WORD *v42; // rax
  _WORD *v43; // rcx
  unsigned int v44; // ecx
  unsigned __int64 v45; // rax
  _WORD *v46; // r8
  _WORD *v47; // rdx
  _WORD *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned int v54; // [rsp+90h] [rbp+18h]

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
    LastError = 87;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v20 = 24;
      goto LABEL_103;
    }
    return LastError;
  }
  v13 = v12 + 1;
  if ( v12 + 1 < v12
    || (v14 = 2 * v13, v54 = 2 * v13, !is_mul_ok(v13, 2u))
    || (v15 = v14 + 52, v14 >= 0xFFFFFFFFFFFFFFCCuLL) )
  {
    LastError = 534;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v20 = 25;
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
      LastError = 87;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 26;
LABEL_103:
        WPP_SF_d(v19[2], v20, a3);
        return LastError;
      }
      return LastError;
    }
    v21 = a3 + 1;
    if ( a3 + 1 < a3 || (v22 = 2 * v21, v16 = 2 * v21, !is_mul_ok(v21, 2u)) || v22 + v15 < v15 )
    {
      LastError = 534;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 27;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += v22;
  }
  v23 = a5;
  v24 = 0;
  if ( a5 )
  {
    v25 = 0x7FFFFFFF;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v25;
    }
    while ( v25 );
    v26 = (0x7FFFFFFF - v25) & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64);
    if ( !v25 )
    {
      LastError = 87;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 28;
        goto LABEL_103;
      }
      return LastError;
    }
    v27 = v26 + 1;
    if ( v26 + 1 < v26 || (v28 = 2 * v27, v24 = 2 * v27, !is_mul_ok(v27, 2u)) || v28 + v15 < v15 )
    {
      LastError = 534;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 29;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += v28;
  }
  v29 = 0;
  if ( Src )
  {
    if ( v15 + 16 < v15 )
    {
      LastError = 534;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 30;
        goto LABEL_103;
      }
      return LastError;
    }
    v29 = 16;
    v15 += 16LL;
  }
  if ( (_DWORD)Size && a7 )
  {
    if ( v15 + (unsigned int)Size < v15 )
    {
      LastError = 534;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 31;
        goto LABEL_103;
      }
      return LastError;
    }
    v15 += (unsigned int)Size;
  }
  ProcessHeap = GetProcessHeap();
  v31 = HeapAlloc(ProcessHeap, 8u, v15);
  v32 = v31;
  if ( v31 )
  {
    v33 = 2147483646;
    v31[3] = v54;
    v31[2] = 52;
    v34 = (unsigned __int64)v54 >> 1;
    if ( v34 )
    {
      v35 = 2147483646;
      v36 = v32 + 13;
      do
      {
        if ( !v35 )
          break;
        if ( !*v9 )
          break;
        *v36++ = *v9++;
        --v35;
        --v34;
      }
      while ( v34 );
      v37 = v36 - 1;
      if ( v34 )
        v37 = v36;
      *v37 = 0;
    }
    if ( v16 )
    {
      v38 = v54 + v32[2];
      v32[5] = v16;
      v39 = (unsigned __int64)(unsigned int)v16 >> 1;
      v32[4] = v38;
      if ( v39 )
      {
        v40 = a4;
        v41 = 2147483646;
        v42 = (_WORD *)((char *)v32 + v38);
        do
        {
          if ( !v41 )
            break;
          if ( !*v40 )
            break;
          *v42++ = *v40++;
          --v41;
          --v39;
        }
        while ( v39 );
        v43 = v42 - 1;
        if ( v39 )
          v43 = v42;
        *v43 = 0;
      }
    }
    if ( v24 )
    {
      v44 = v16 + v54 + 52;
      v32[7] = v24;
      v45 = (unsigned __int64)(unsigned int)v24 >> 1;
      v32[6] = v44;
      if ( v45 )
      {
        v46 = a5;
        v47 = (_WORD *)((char *)v32 + v44);
        do
        {
          if ( !v33 )
            break;
          if ( !*v46 )
            break;
          *v47++ = *v46++;
          --v33;
          --v45;
        }
        while ( v45 );
        v48 = v47 - 1;
        if ( v45 )
          v48 = v47;
        *v48 = 0;
      }
    }
    if ( v29 )
    {
      v49 = (unsigned int)v24 + (_DWORD)v16 + v54 + 52;
      v32[9] = v29;
      v32[8] = v49;
      memcpy_0((char *)v32 + v49, Src, (unsigned int)v29);
    }
    if ( a7 && (_DWORD)Size )
    {
      v32[11] = Size;
      v50 = (_DWORD)v16 + (_DWORD)v24 + (_DWORD)v29 + v54 + 52;
      v32[10] = v50;
      memcpy_0((char *)v32 + v50, a7, (unsigned int)Size);
    }
    *a1 = v32;
    *a2 = v15;
  }
  else
  {
    LastError = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v20 = 32;
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
0x1800014ee  jz      loc_180001A0F
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
0x180001525  jz      loc_180001A0F
0x18000152b  lea     rcx, [rdx+1]
0x18000152f  cmp     rcx, rdx
0x180001532  jb      loc_1800019E0
0x180001538  mov     rax, rbp
0x18000153b  mov     [rsp+78h+arg_10], rbx
0x180001543  mul     rcx
0x180001546  mov     [rsp+78h+arg_10], rax
0x18000154e  test    rdx, rdx
0x180001551  jnz     loc_1800019E0
0x180001557  lea     rdi, [rax+34h]
0x18000155b  cmp     rdi, 34h ; '4'
0x18000155f  jb      loc_1800019E0
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
0x1800015b3  jz      loc_180001A44
0x1800015b9  test    byte ptr [rcx+1Ch], 40h
0x1800015bd  jz      loc_180001A44
0x1800015c3  cmp     [rcx+19h], sil
0x1800015c7  jb      loc_180001A44
0x1800015cd  lea     edx, [r9-3Dh]
0x1800015d1  jmp     loc_180001A3B
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
0x18000164d  jz      loc_180001A44
0x180001653  test    byte ptr [rcx+1Ch], 40h
0x180001657  jz      loc_180001A44
0x18000165d  cmp     [rcx+19h], sil
0x180001661  jb      loc_180001A44
0x180001667  lea     edx, [r9-3Bh]
0x18000166b  jmp     loc_180001A3B
0x180001670  mov     r9d, 216h
0x180001676  mov     ebx, r9d
0x180001679  mov     rcx, cs:WPP_GLOBAL_Control
0x180001680  lea     rax, WPP_GLOBAL_Control
0x180001687  cmp     rcx, rax
0x18000168a  jz      loc_180001A44
0x180001690  test    byte ptr [rcx+1Ch], 40h
0x180001694  jz      loc_180001A44
0x18000169a  cmp     [rcx+19h], sil
0x18000169e  jb      loc_180001A44
0x1800016a4  mov     edx, 1Bh
0x1800016a9  jmp     loc_180001A3B
0x1800016ae  lea     rcx, [rdx+1]
0x1800016b2  cmp     rcx, rdx
0x1800016b5  jb      loc_180001798
0x1800016bb  mov     rax, rbp
0x1800016be  mul     rcx
0x1800016c1  mov     r14, rax
0x1800016c4  test    rdx, rdx
0x1800016c7  jnz     loc_180001798
0x1800016cd  lea     rcx, [rax+rdi]
0x1800016d1  cmp     rcx, rdi
0x1800016d4  jb      loc_180001798
0x1800016da  mov     rdi, rcx
0x1800016dd  mov     r13, rbx
0x1800016e0  cmp     [rsp+78h+Src], rbx
0x1800016e8  jz      short loc_180001700
0x1800016ea  lea     rax, [rdi+10h]
0x1800016ee  cmp     rax, rdi
0x1800016f1  jb      loc_1800017D6
0x1800016f7  mov     r13d, 10h
0x1800016fd  mov     rdi, rax
0x180001700  mov     ebp, dword ptr [rsp+78h+Size]
0x180001707  test    ebp, ebp
0x180001709  jz      short loc_180001725
0x18000170b  cmp     [rsp+78h+arg_30], rbx
0x180001713  jz      short loc_180001725
0x180001715  lea     rcx, [rdi+rbp]
0x180001719  cmp     rcx, rdi
0x18000171c  jb      loc_180001814
0x180001722  mov     rdi, rcx
0x180001725  call    cs:__imp_GetProcessHeap
0x18000172c  nop     dword ptr [rax+rax+00h]
0x180001731  mov     r8, rdi; dwBytes
0x180001734  mov     edx, 8; dwFlags
0x180001739  mov     rcx, rax; hHeap
0x18000173c  call    cs:__imp_HeapAlloc
0x180001743  nop     dword ptr [rax+rax+00h]
0x180001748  mov     rsi, rax
0x18000174b  test    rax, rax
0x18000174e  jnz     loc_180001852
0x180001754  call    cs:__imp_GetLastError
0x18000175b  nop     dword ptr [rax+rax+00h]
0x180001760  mov     ebx, eax
0x180001762  mov     rcx, cs:WPP_GLOBAL_Control
0x180001769  lea     rax, WPP_GLOBAL_Control
0x180001770  cmp     rcx, rax
0x180001773  jz      loc_180001A44
0x180001779  test    byte ptr [rcx+1Ch], 40h
0x18000177d  jz      loc_180001A44
0x180001783  cmp     byte ptr [rcx+19h], 1
0x180001787  jb      loc_180001A44
0x18000178d  lea     edx, [rsi+20h]
0x180001790  mov     r9d, ebx
0x180001793  jmp     loc_180001A3B
0x180001798  mov     r9d, 216h
0x18000179e  mov     ebx, r9d
0x1800017a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017a8  lea     rax, WPP_GLOBAL_Control
0x1800017af  cmp     rcx, rax
0x1800017b2  jz      loc_180001A44
0x1800017b8  test    byte ptr [rcx+1Ch], 40h
0x1800017bc  jz      loc_180001A44
0x1800017c2  cmp     [rcx+19h], sil
0x1800017c6  jb      loc_180001A44
0x1800017cc  mov     edx, 1Dh
0x1800017d1  jmp     loc_180001A3B
0x1800017d6  mov     r9d, 216h
0x1800017dc  mov     ebx, r9d
0x1800017df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017e6  lea     rax, WPP_GLOBAL_Control
0x1800017ed  cmp     rcx, rax
0x1800017f0  jz      loc_180001A44
0x1800017f6  test    byte ptr [rcx+1Ch], 40h
0x1800017fa  jz      loc_180001A44
0x180001800  cmp     [rcx+19h], sil
0x180001804  jb      loc_180001A44
0x18000180a  mov     edx, 1Eh
0x18000180f  jmp     loc_180001A3B
0x180001814  mov     r9d, 216h
0x18000181a  mov     ebx, r9d
0x18000181d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001824  lea     rax, WPP_GLOBAL_Control
0x18000182b  cmp     rcx, rax
0x18000182e  jz      loc_180001A44
0x180001834  test    byte ptr [rcx+1Ch], 40h
0x180001838  jz      loc_180001A44
0x18000183e  cmp     [rcx+19h], sil
0x180001842  jb      loc_180001A44
0x180001848  mov     edx, 1Fh
0x18000184d  jmp     loc_180001A3B
0x180001852  mov     r10d, dword ptr [rsp+78h+arg_10]
0x18000185a  mov     r9d, 7FFFFFFEh
0x180001860  mov     [rax+0Ch], r10d
0x180001864  mov     dword ptr [rax+8], 34h ; '4'
0x18000186b  mov     eax, r10d
0x18000186e  shr     rax, 1
0x180001871  jz      short loc_1800018B0
0x180001873  mov     r8d, r9d
0x180001876  lea     rdx, [rsi+34h]
0x18000187a  test    r8, r8
0x18000187d  jz      short loc_18000189C
0x18000187f  movzx   ecx, word ptr [r15]
0x180001883  test    cx, cx
0x180001886  jz      short loc_18000189C
0x180001888  mov     [rdx], cx
0x18000188b  add     r15, 2
0x18000188f  add     rdx, 2
0x180001893  dec     r8
0x180001896  sub     rax, 1
0x18000189a  jnz     short loc_18000187A
0x18000189c  xor     r15d, r15d
0x18000189f  lea     rcx, [rdx-2]
0x1800018a3  test    rax, rax
0x1800018a6  cmovnz  rcx, rdx
0x1800018aa  mov     [rcx], r15w
0x1800018ae  jmp     short loc_1800018B3
0x1800018b0  xor     r15d, r15d
0x1800018b3  test    r12, r12
0x1800018b6  jz      short loc_180001912
0x1800018b8  mov     r8d, [rsi+8]
0x1800018bc  mov     edx, r12d
0x1800018bf  add     r8d, r10d
0x1800018c2  mov     [rsi+14h], edx
0x1800018c5  shr     rdx, 1
0x1800018c8  mov     [rsi+10h], r8d
0x1800018cc  jz      short loc_180001912
0x1800018ce  mov     r11, [rsp+78h+arg_18]
0x1800018d6  mov     rcx, r9
0x1800018d9  mov     eax, r8d
0x1800018dc  add     rax, rsi
0x1800018df  test    rcx, rcx
0x1800018e2  jz      short loc_180001903
0x1800018e4  movzx   r8d, word ptr [r11]
0x1800018e8  test    r8w, r8w
0x1800018ec  jz      short loc_180001903
0x1800018ee  mov     [rax], r8w
0x1800018f2  add     r11, 2
0x1800018f6  add     rax, 2
0x1800018fa  dec     rcx
0x1800018fd  sub     rdx, 1
0x180001901  jnz     short loc_1800018DF
0x180001903  test    rdx, rdx
0x180001906  lea     rcx, [rax-2]
0x18000190a  cmovnz  rcx, rax
0x18000190e  mov     [rcx], r15w
0x180001912  test    r14, r14
0x180001915  jz      short loc_18000196A
0x180001917  mov     eax, r14d
0x18000191a  lea     ecx, [r10+34h]
0x18000191e  add     ecx, r12d
0x180001921  mov     [rsi+1Ch], eax
0x180001924  shr     rax, 1
0x180001927  mov     [rsi+18h], ecx
0x18000192a  jz      short loc_18000196A
0x18000192c  mov     r8, [rsp+78h+arg_20]
0x180001934  mov     edx, ecx
0x180001936  add     rdx, rsi
0x180001939  test    r9, r9
0x18000193c  jz      short loc_18000195B
0x18000193e  movzx   ecx, word ptr [r8]
0x180001942  test    cx, cx
0x180001945  jz      short loc_18000195B
0x180001947  mov     [rdx], cx
0x18000194a  add     r8, 2
0x18000194e  add     rdx, 2
0x180001952  dec     r9
0x180001955  sub     rax, 1
0x180001959  jnz     short loc_180001939
0x18000195b  test    rax, rax
  ... truncated ...
```
