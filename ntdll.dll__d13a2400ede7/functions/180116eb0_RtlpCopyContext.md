# RtlpCopyContext

- ea: `0x180116eb0`
- end: `0x18011790e`
- name: `RtlpCopyContext`
- size: `2654`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180115ac0`
- `0x180116430`

## callees

- `0x1800b9c90`
- `0x180116eb0`
- `0x180164280`

## pseudocode

```c
__int64 __fastcall RtlpCopyContext(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // esi
  char v6; // di
  __int64 XStateChunk; // rax
  unsigned int v8; // r10d
  _OWORD *v9; // r11
  __int64 v10; // rcx
  __int64 v11; // rax
  char v12; // di
  __int64 v13; // rax
  unsigned int v14; // r10d
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  _OWORD *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // r10d
  char v21; // r11
  __int64 v22; // r8
  unsigned int v23; // esi
  const void *v24; // r11
  __int64 v25; // rcx
  unsigned int v26; // eax
  char v27; // di
  __int64 v28; // rax
  unsigned int v29; // r10d
  __int64 v30; // rcx
  void *v31; // rcx

  if ( a2 == a1 )
  {
    result = *(_DWORD *)(a2 + 48) & 0x10004F;
    *(_DWORD *)(a1 + 48) = result;
    return result;
  }
  v5 = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 48) = 0;
  if ( (*(_DWORD *)(a2 + 48) & v5 & 0x100040) == 0x100040 )
  {
    *(_DWORD *)(a1 + 48) = 1048640;
    if ( ((MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x800) == 0
      || (v6 = MEMORY[0x7FFE03EC], (MEMORY[0x7FFE03EC] & 0xFFFFFFF8) != 0) )
    {
      v9 = 0;
      if ( ((MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x800) == 0 )
        goto LABEL_91;
    }
    else
    {
      XStateChunk = RtlpLocateXStateChunk(a2 + 1232);
      v9 = (_OWORD *)XStateChunk;
      if ( XStateChunk )
      {
        if ( (v6 & 2) != 0 )
        {
          v10 = *(_QWORD *)(XStateChunk + 8);
          if ( (v10 & 0x800) != 0 )
          {
            v11 = v8;
            if ( (v10 & 4) != 0 )
            {
              _mm_lfence();
              v11 = v8 + MEMORY[0x7FFE060C];
            }
            if ( (v10 & 8) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 8) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0610] + v11);
            }
            if ( (v10 & 0x10) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x10) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0614] + v11);
            }
            if ( (v10 & 0x20) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x20) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0618] + v11);
            }
            if ( (v10 & 0x40) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x40) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE061C] + v11);
            }
            if ( (v10 & 0x80u) != 0LL )
            {
              _mm_lfence();
              if ( MEMORY[0x7FFE05F8] < 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0620] + v11);
            }
            if ( (v10 & 0x100) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x100) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0624] + v11);
            }
            if ( (v10 & 0x200) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x200) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE0628] + v11);
            }
            if ( (v10 & 0x400) != 0 )
            {
              _mm_lfence();
              if ( (MEMORY[0x7FFE05F8] & 0x400) != 0 )
                LODWORD(v11) = (v11 + 63) & 0xFFFFFFC0;
              v11 = (unsigned int)(MEMORY[0x7FFE062C] + v11);
            }
            if ( (MEMORY[0x7FFE05F8] & 0x800) != 0 )
              v11 = ((_DWORD)v11 + 63) & 0xFFFFFFC0;
            v9 = (_OWORD *)((char *)v9 + v11 - 512);
          }
          else
          {
            v9 = 0;
          }
        }
        else
        {
          v9 = (_OWORD *)(MEMORY[0x7FFE0448] - 512LL + XStateChunk);
        }
      }
    }
    v12 = MEMORY[0x7FFE03EC];
    if ( (MEMORY[0x7FFE03EC] & 0xFFFFFFF8) == 0 )
    {
      v13 = RtlpLocateXStateChunk(a1 + 1232);
      v15 = v13;
      if ( v13 )
      {
        if ( (v12 & 2) == 0 )
        {
          v18 = (_OWORD *)(v13 + MEMORY[0x7FFE0448] - 512LL);
LABEL_92:
          if ( v9 && v18 )
          {
            *v18 = *v9;
            *(_QWORD *)(*(int *)(a1 + 1248) + a1 + 1232) |= *(_DWORD *)(*(int *)(a2 + 1248) + a2 + 1232) & 0x800;
          }
          goto LABEL_95;
        }
        v16 = *(_QWORD *)(v13 + 8);
        if ( (v16 & 0x800) != 0 )
        {
          v17 = v14;
          if ( (v16 & 4) != 0 )
            v17 = v14 + MEMORY[0x7FFE060C];
          if ( (v16 & 8) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 8) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0610] + v17);
          }
          if ( (v16 & 0x10) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x10) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0614] + v17);
          }
          if ( (v16 & 0x20) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x20) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0618] + v17);
          }
          if ( (v16 & 0x40) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x40) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE061C] + v17);
          }
          if ( (v16 & 0x80u) != 0LL )
          {
            if ( MEMORY[0x7FFE05F8] < 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0620] + v17);
          }
          if ( (v16 & 0x100) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x100) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0624] + v17);
          }
          if ( (v16 & 0x200) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x200) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE0628] + v17);
          }
          if ( (v16 & 0x400) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x400) != 0 )
              LODWORD(v17) = (v17 + 63) & 0xFFFFFFC0;
            v17 = (unsigned int)(MEMORY[0x7FFE062C] + v17);
          }
          if ( (MEMORY[0x7FFE05F8] & 0x800) != 0 )
            v17 = ((_DWORD)v17 + 63) & 0xFFFFFFC0;
          v18 = (_OWORD *)(v15 + v17 - 512);
          goto LABEL_92;
        }
      }
    }
LABEL_91:
    v18 = 0;
    goto LABEL_92;
  }
LABEL_95:
  if ( (*(_DWORD *)(a2 + 48) & v5 & 0x100040) == 0x100040 )
  {
    *(_DWORD *)(a1 + 48) |= 0x100040u;
    if ( ((MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x80000) == 0 || (MEMORY[0x7FFE03EC] & 0xFFFFFFF8) != 0 )
    {
      v23 = 0;
      v24 = 0;
      if ( ((MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x80000) == 0 )
        goto LABEL_248;
    }
    else
    {
      v19 = RtlpLocateXStateChunk(a2 + 1232);
      v22 = v19;
      if ( v19 )
      {
        if ( (v21 & 2) != 0 )
        {
          v25 = *(_QWORD *)(v19 + 8);
          v23 = MEMORY[0x7FFE0650];
          if ( (v25 & 0x80000) != 0 )
          {
            v26 = v20;
            if ( (v25 & 4) != 0 )
              v26 = v20 + MEMORY[0x7FFE060C];
            if ( (v25 & 8) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 8) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0610];
            }
            if ( (v25 & 0x10) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x10) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0614];
            }
            if ( (v25 & 0x20) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x20) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0618];
            }
            if ( (v25 & 0x40) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x40) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE061C];
            }
            if ( (v25 & 0x80u) != 0LL )
            {
              if ( MEMORY[0x7FFE05F8] < 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0620];
            }
            if ( (v25 & 0x100) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x100) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0624];
            }
            if ( (v25 & 0x200) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x200) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0628];
            }
            if ( (v25 & 0x400) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x400) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE062C];
            }
            if ( (v25 & 0x800) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x800) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0630];
            }
            if ( (v25 & 0x1000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x1000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0634];
            }
            if ( (v25 & 0x2000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x2000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0638];
            }
            if ( (v25 & 0x4000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x4000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE063C];
            }
            if ( (v25 & 0x8000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x8000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0640];
            }
            if ( (v25 & 0x10000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x10000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0644];
            }
            if ( (v25 & 0x20000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x20000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE0648];
            }
            if ( (v25 & 0x40000) != 0 )
            {
              if ( (MEMORY[0x7FFE05F8] & 0x40000) != 0 )
                v26 = (v26 + 63) & 0xFFFFFFC0;
              v26 += MEMORY[0x7FFE064C];
            }
            if ( (MEMORY[0x7FFE05F8] & 0x80000) != 0 )
              v26 = (v26 + 63) & 0xFFFFFFC0;
            v24 = (const void *)(v22 + v26 - 512LL);
          }
          else
          {
            v24 = 0;
          }
        }
        else
        {
          v23 = MEMORY[0x7FFE048C];
          v24 = (const void *)(v19 + MEMORY[0x7FFE0488] - 512LL);
        }
      }
      else
      {
        v23 = 0;
        v24 = 0;
      }
    }
    v27 = MEMORY[0x7FFE03EC];
    if ( (MEMORY[0x7FFE03EC] & 0xFFFFFFF8) == 0 )
    {
      v28 = RtlpLocateXStateChunk(a1 + 1232);
      if ( v28 )
      {
        if ( (v27 & 2) == 0 )
        {
          v31 = (void *)(v28 + MEMORY[0x7FFE0488] - 512LL);
          goto LABEL_249;
        }
        v30 = *(_QWORD *)(v28 + 8);
        if ( (v30 & 0x80000) != 0 )
        {
          if ( (v30 & 4) != 0 )
            v29 += MEMORY[0x7FFE060C];
          if ( (v30 & 8) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 8) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0610];
          }
          if ( (v30 & 0x10) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x10) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0614];
          }
          if ( (v30 & 0x20) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x20) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0618];
          }
          if ( (v30 & 0x40) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x40) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE061C];
          }
          if ( (v30 & 0x80u) != 0LL )
          {
            if ( MEMORY[0x7FFE05F8] < 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0620];
          }
          if ( (v30 & 0x100) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x100) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0624];
          }
          if ( (v30 & 0x200) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x200) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0628];
          }
          if ( (v30 & 0x400) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x400) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE062C];
          }
          if ( (v30 & 0x800) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x800) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0630];
          }
          if ( (v30 & 0x1000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x1000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0634];
          }
          if ( (v30 & 0x2000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x2000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0638];
          }
          if ( (v30 & 0x4000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x4000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE063C];
          }
          if ( (v30 & 0x8000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x8000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0640];
          }
          if ( (v30 & 0x10000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x10000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0644];
          }
          if ( (v30 & 0x20000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x20000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE0648];
          }
          if ( (v30 & 0x40000) != 0 )
          {
            if ( (MEMORY[0x7FFE05F8] & 0x40000) != 0 )
              v29 = (v29 + 63) & 0xFFFFFFC0;
            v29 += MEMORY[0x7FFE064C];
          }
          if ( (MEMORY[0x7FFE05F8] & 0x80000) != 0 )
            v29 = (v29 + 63) & 0xFFFFFFC0;
          v31 = (void *)(v28 + v29 - 512LL);
          goto LABEL_249;
        }
      }
    }
LABEL_248:
    v31 = 0;
LABEL_249:
    if ( v24 )
    {
      if ( v31 )
      {
        memmove(v31, v24, v23);
        *(_QWORD *)(*(int *)(a1 + 1248) + a1 + 1232) |= *(_DWORD *)(*(int *)(a2 + 1248) + a2 + 1232) & 0x80000;
      }
    }
  }
  *(_DWORD *)(a1 + 48) |= *(_DWORD *)(a2 + 48) & 0x10000F;
  *(_QWORD *)(a1 + 248) = *(_QWORD *)(a2 + 248);
  *(_QWORD *)(a1 + 144) = *(_QWORD *)(a2 + 144);
  *(_QWORD *)(a1 + 152) = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a1 + 160) = *(_QWORD *)(a2 + 160);
  *(_QWORD *)(a1 + 168) = *(_QWORD *)(a2 + 168);
  *(_QWORD *)(a1 + 176) = *(_QWORD *)(a2 + 176);
  *(_QWORD *)(a1 + 216) = *(_QWORD *)(a2 + 216);
  *(_QWORD *)(a1 + 224) = *(_QWORD *)(a2 + 224);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(a2 + 232);
  *(_QWORD *)(a1 + 240) = *(_QWORD *)(a2 + 240);
  *(_OWORD *)(a1 + 512) = *(_OWORD *)(a2 + 512);
  *(_OWORD *)(a1 + 528) = *(_OWORD *)(a2 + 528);
  *(_OWORD *)(a1 + 544) = *(_OWORD *)(a2 + 544);
  *(_OWORD *)(a1 + 560) = *(_OWORD *)(a2 + 560);
  *(_OWORD *)(a1 + 576) = *(_OWORD *)(a2 + 576);
  *(_OWORD *)(a1 + 592) = *(_OWORD *)(a2 + 592);
  *(_OWORD *)(a1 + 608) = *(_OWORD *)(a2 + 608);
  *(_OWORD *)(a1 + 624) = *(_OWORD *)(a2 + 624);
  *(_OWORD *)(a1 + 640) = *(_OWORD *)(a2 + 640);
  *(_OWORD *)(a1 + 656) = *(_OWORD *)(a2 + 656);
  *(_WORD *)(a1 + 56) = *(_WORD *)(a2 + 56);
  *(_WORD *)(a1 + 66) = *(_WORD *)(a2 + 66);
  *(_DWORD *)(a1 + 52) = *(_DWORD *)(a2 + 52);
  result = *(unsigned int *)(a2 + 68);
  *(_DWORD *)(a1 + 68) = result;
  *(_OWORD *)(a1 + 256) = *(_OWORD *)(a2 + 256);
  *(_OWORD *)(a1 + 272) = *(_OWORD *)(a2 + 272);
  *(_OWORD *)(a1 + 288) = *(_OWORD *)(a2 + 288);
  *(_OWORD *)(a1 + 304) = *(_OWORD *)(a2 + 304);
  *(_OWORD *)(a1 + 320) = *(_OWORD *)(a2 + 320);
  *(_OWORD *)(a1 + 336) = *(_OWORD *)(a2 + 336);
  *(_OWORD *)(a1 + 352) = *(_OWORD *)(a2 + 352);
  *(_OWORD *)(a1 + 368) = *(_OWORD *)(a2 + 368);
  *(_OWORD *)(a1 + 384) = *(_OWORD *)(a2 + 384);
  *(_OWORD *)(a1 + 400) = *(_OWORD *)(a2 + 400);
  return result;
}

```

## disassembly

```asm
0x180116eb0  mov     [rsp+arg_10], rbx
0x180116eb5  push    rbp
0x180116eb6  sub     rsp, 20h
0x180116eba  mov     rbp, rdx
0x180116ebd  mov     rbx, rcx
0x180116ec0  cmp     rdx, rcx
0x180116ec3  jnz     short loc_180116EDC
0x180116ec5  mov     eax, [rdx+30h]
0x180116ec8  and     eax, 10004Fh
0x180116ecd  mov     [rcx+30h], eax
0x180116ed0  mov     rbx, [rsp+28h+arg_10]
0x180116ed5  add     rsp, 20h
0x180116ed9  pop     rbp
0x180116eda  retn
0x180116edc  mov     [rsp+28h+arg_0], rsi
0x180116ee1  mov     r10d, 240h
0x180116ee7  mov     esi, [rcx+30h]
0x180116eea  mov     eax, esi
0x180116eec  mov     dword ptr [rcx+30h], 0
0x180116ef3  and     eax, [rdx+30h]
0x180116ef6  and     eax, 100040h
0x180116efb  mov     [rsp+28h+arg_8], rdi
0x180116f00  cmp     eax, 100040h
0x180116f05  jnz     loc_18011721D
0x180116f0b  mov     [rcx+30h], eax
0x180116f0e  mov     eax, ds:7FFE03D8h
0x180116f15  or      eax, ds:7FFE0708h
0x180116f1c  and     eax, 800h
0x180116f21  jz      loc_180117091
0x180116f27  mov     edi, ds:7FFE03ECh
0x180116f2e  test    edi, 0FFFFFFF8h
0x180116f34  jnz     loc_180117091
0x180116f3a  lea     rcx, [rdx+4D0h]
0x180116f41  call    RtlpLocateXStateChunk
0x180116f46  mov     r11, rax
0x180116f49  test    rax, rax
0x180116f4c  jz      loc_18011709D
0x180116f52  test    dil, 2
0x180116f56  jz      loc_18011707F
0x180116f5c  mov     rcx, [rax+8]
0x180116f60  bt      rcx, 0Bh
0x180116f65  jb      short loc_180116F6F
0x180116f67  xor     r11d, r11d
0x180116f6a  jmp     loc_18011709D
0x180116f6f  mov     rdx, ds:7FFE05F8h
0x180116f77  mov     eax, r10d
0x180116f7a  test    cl, 4
0x180116f7d  jz      short loc_180116F8C
0x180116f7f  lfence
0x180116f82  mov     eax, ds:7FFE060Ch
0x180116f89  add     eax, r10d
0x180116f8c  test    cl, 8
0x180116f8f  jz      short loc_180116FA6
0x180116f91  lfence
0x180116f94  test    dl, 8
0x180116f97  jz      short loc_180116F9F
0x180116f99  add     eax, 3Fh ; '?'
0x180116f9c  and     eax, 0FFFFFFC0h
0x180116f9f  add     eax, ds:7FFE0610h
0x180116fa6  test    cl, 10h
0x180116fa9  jz      short loc_180116FC0
0x180116fab  lfence
0x180116fae  test    dl, 10h
0x180116fb1  jz      short loc_180116FB9
0x180116fb3  add     eax, 3Fh ; '?'
0x180116fb6  and     eax, 0FFFFFFC0h
0x180116fb9  add     eax, ds:7FFE0614h
0x180116fc0  test    cl, 20h
0x180116fc3  jz      short loc_180116FDA
0x180116fc5  lfence
0x180116fc8  test    dl, 20h
0x180116fcb  jz      short loc_180116FD3
0x180116fcd  add     eax, 3Fh ; '?'
0x180116fd0  and     eax, 0FFFFFFC0h
0x180116fd3  add     eax, ds:7FFE0618h
0x180116fda  test    cl, 40h
0x180116fdd  jz      short loc_180116FF4
0x180116fdf  lfence
0x180116fe2  test    dl, 40h
0x180116fe5  jz      short loc_180116FED
0x180116fe7  add     eax, 3Fh ; '?'
0x180116fea  and     eax, 0FFFFFFC0h
0x180116fed  add     eax, ds:7FFE061Ch
0x180116ff4  test    cl, cl
0x180116ff6  jns     short loc_18011700C
0x180116ff8  lfence
0x180116ffb  test    dl, dl
0x180116ffd  jns     short loc_180117005
0x180116fff  add     eax, 3Fh ; '?'
0x180117002  and     eax, 0FFFFFFC0h
0x180117005  add     eax, ds:7FFE0620h
0x18011700c  bt      rcx, 8
0x180117011  jnb     short loc_18011702A
0x180117013  lfence
0x180117016  bt      rdx, 8
0x18011701b  jnb     short loc_180117023
0x18011701d  add     eax, 3Fh ; '?'
0x180117020  and     eax, 0FFFFFFC0h
0x180117023  add     eax, ds:7FFE0624h
0x18011702a  bt      rcx, 9
0x18011702f  jnb     short loc_180117048
0x180117031  lfence
0x180117034  bt      rdx, 9
0x180117039  jnb     short loc_180117041
0x18011703b  add     eax, 3Fh ; '?'
0x18011703e  and     eax, 0FFFFFFC0h
0x180117041  add     eax, ds:7FFE0628h
0x180117048  bt      rcx, 0Ah
0x18011704d  jnb     short loc_180117066
0x18011704f  lfence
0x180117052  bt      rdx, 0Ah
0x180117057  jnb     short loc_18011705F
0x180117059  add     eax, 3Fh ; '?'
0x18011705c  and     eax, 0FFFFFFC0h
0x18011705f  add     eax, ds:7FFE062Ch
0x180117066  bt      rdx, 0Bh
0x18011706b  jnb     short loc_180117073
0x18011706d  add     eax, 3Fh ; '?'
0x180117070  and     eax, 0FFFFFFC0h
0x180117073  add     r11, 0FFFFFFFFFFFFFE00h
0x18011707a  add     r11, rax
0x18011707d  jmp     short loc_18011709D
0x18011707f  mov     eax, ds:7FFE0448h
0x180117086  add     rax, 0FFFFFFFFFFFFFE00h
0x18011708c  add     r11, rax
0x18011708f  jmp     short loc_18011709D
0x180117091  xor     r11d, r11d
0x180117094  test    rax, rax
0x180117097  jz      loc_1801171E7
0x18011709d  mov     edi, ds:7FFE03ECh
0x1801170a4  test    edi, 0FFFFFFF8h
0x1801170aa  jnz     loc_1801171E7
0x1801170b0  lea     rcx, [rbx+4D0h]
0x1801170b7  call    RtlpLocateXStateChunk
0x1801170bc  mov     r8, rax
0x1801170bf  test    rax, rax
0x1801170c2  jz      loc_1801171E7
0x1801170c8  test    dil, 2
0x1801170cc  jz      loc_1801171D5
0x1801170d2  mov     rcx, [rax+8]
0x1801170d6  bt      rcx, 0Bh
0x1801170db  jnb     loc_1801171E7
0x1801170e1  mov     rdx, ds:7FFE05F8h
0x1801170e9  mov     eax, r10d
0x1801170ec  test    cl, 4
0x1801170ef  jz      short loc_1801170FB
0x1801170f1  mov     eax, ds:7FFE060Ch
0x1801170f8  add     eax, r10d
0x1801170fb  test    cl, 8
0x1801170fe  jz      short loc_180117112
0x180117100  test    dl, 8
0x180117103  jz      short loc_18011710B
0x180117105  add     eax, 3Fh ; '?'
0x180117108  and     eax, 0FFFFFFC0h
0x18011710b  add     eax, ds:7FFE0610h
0x180117112  test    cl, 10h
0x180117115  jz      short loc_180117129
0x180117117  test    dl, 10h
0x18011711a  jz      short loc_180117122
0x18011711c  add     eax, 3Fh ; '?'
0x18011711f  and     eax, 0FFFFFFC0h
0x180117122  add     eax, ds:7FFE0614h
0x180117129  test    cl, 20h
0x18011712c  jz      short loc_180117140
0x18011712e  test    dl, 20h
0x180117131  jz      short loc_180117139
0x180117133  add     eax, 3Fh ; '?'
0x180117136  and     eax, 0FFFFFFC0h
0x180117139  add     eax, ds:7FFE0618h
0x180117140  test    cl, 40h
0x180117143  jz      short loc_180117157
0x180117145  test    dl, 40h
0x180117148  jz      short loc_180117150
0x18011714a  add     eax, 3Fh ; '?'
0x18011714d  and     eax, 0FFFFFFC0h
0x180117150  add     eax, ds:7FFE061Ch
0x180117157  test    cl, cl
0x180117159  jns     short loc_18011716C
0x18011715b  test    dl, dl
0x18011715d  jns     short loc_180117165
0x18011715f  add     eax, 3Fh ; '?'
0x180117162  and     eax, 0FFFFFFC0h
0x180117165  add     eax, ds:7FFE0620h
0x18011716c  bt      rcx, 8
0x180117171  jnb     short loc_180117187
0x180117173  bt      rdx, 8
0x180117178  jnb     short loc_180117180
0x18011717a  add     eax, 3Fh ; '?'
0x18011717d  and     eax, 0FFFFFFC0h
0x180117180  add     eax, ds:7FFE0624h
0x180117187  bt      rcx, 9
0x18011718c  jnb     short loc_1801171A2
0x18011718e  bt      rdx, 9
0x180117193  jnb     short loc_18011719B
0x180117195  add     eax, 3Fh ; '?'
0x180117198  and     eax, 0FFFFFFC0h
0x18011719b  add     eax, ds:7FFE0628h
0x1801171a2  bt      rcx, 0Ah
0x1801171a7  jnb     short loc_1801171BD
0x1801171a9  bt      rdx, 0Ah
0x1801171ae  jnb     short loc_1801171B6
0x1801171b0  add     eax, 3Fh ; '?'
0x1801171b3  and     eax, 0FFFFFFC0h
0x1801171b6  add     eax, ds:7FFE062Ch
0x1801171bd  bt      rdx, 0Bh
0x1801171c2  jnb     short loc_1801171CA
0x1801171c4  add     eax, 3Fh ; '?'
0x1801171c7  and     eax, 0FFFFFFC0h
0x1801171ca  add     rax, 0FFFFFFFFFFFFFE00h
0x1801171d0  add     rax, r8
0x1801171d3  jmp     short loc_1801171E9
0x1801171d5  mov     eax, ds:7FFE0448h
0x1801171dc  add     rax, 0FFFFFFFFFFFFFE00h
0x1801171e2  add     rax, r8
0x1801171e5  jmp     short loc_1801171E9
0x1801171e7  xor     eax, eax
0x1801171e9  test    r11, r11
0x1801171ec  jz      short loc_18011721D
0x1801171ee  test    rax, rax
0x1801171f1  jz      short loc_18011721D
0x1801171f3  movups  xmm0, xmmword ptr [r11]
0x1801171f7  movups  xmmword ptr [rax], xmm0
0x1801171fa  movsxd  rax, dword ptr [rbp+4E0h]
0x180117201  movsxd  rdx, dword ptr [rbx+4E0h]
0x180117208  mov     ecx, [rax+rbp+4D0h]
0x18011720f  and     ecx, 800h
0x180117215  or      [rdx+rbx+4D0h], rcx
0x18011721d  and     esi, [rbp+30h]
0x180117220  and     esi, 100040h
0x180117226  cmp     esi, 100040h
0x18011722c  jnz     loc_18011772D
0x180117232  or      [rbx+30h], esi
0x180117235  mov     eax, ds:7FFE03D8h
0x18011723c  or      eax, ds:7FFE0708h
0x180117243  and     eax, 80000h
0x180117248  jz      loc_18011748F
0x18011724e  mov     r11d, ds:7FFE03ECh
0x180117256  test    r11d, 0FFFFFFF8h
0x18011725d  jnz     loc_18011748F
0x180117263  lea     rcx, [rbp+4D0h]
0x18011726a  call    RtlpLocateXStateChunk
0x18011726f  mov     r8, rax
0x180117272  test    rax, rax
0x180117275  jnz     short loc_180117281
0x180117277  xor     esi, esi
0x180117279  xor     r11d, r11d
0x18011727c  jmp     loc_18011749D
0x180117281  test    r11b, 2
0x180117285  jz      loc_180117475
0x18011728b  mov     rcx, [rax+8]
0x18011728f  mov     esi, ds:7FFE0650h
0x180117296  bt      rcx, 13h
0x18011729b  jb      short loc_1801172A5
0x18011729d  xor     r11d, r11d
0x1801172a0  jmp     loc_18011749D
0x1801172a5  mov     rdx, ds:7FFE05F8h
0x1801172ad  mov     eax, r10d
0x1801172b0  test    cl, 4
0x1801172b3  jz      short loc_1801172BF
0x1801172b5  mov     eax, ds:7FFE060Ch
0x1801172bc  add     eax, r10d
0x1801172bf  test    cl, 8
0x1801172c2  jz      short loc_1801172D6
0x1801172c4  test    dl, 8
0x1801172c7  jz      short loc_1801172CF
0x1801172c9  add     eax, 3Fh ; '?'
0x1801172cc  and     eax, 0FFFFFFC0h
0x1801172cf  add     eax, ds:7FFE0610h
0x1801172d6  test    cl, 10h
0x1801172d9  jz      short loc_1801172ED
0x1801172db  test    dl, 10h
0x1801172de  jz      short loc_1801172E6
0x1801172e0  add     eax, 3Fh ; '?'
0x1801172e3  and     eax, 0FFFFFFC0h
0x1801172e6  add     eax, ds:7FFE0614h
0x1801172ed  test    cl, 20h
0x1801172f0  jz      short loc_180117304
0x1801172f2  test    dl, 20h
0x1801172f5  jz      short loc_1801172FD
0x1801172f7  add     eax, 3Fh ; '?'
0x1801172fa  and     eax, 0FFFFFFC0h
0x1801172fd  add     eax, ds:7FFE0618h
0x180117304  test    cl, 40h
0x180117307  jz      short loc_18011731B
0x180117309  test    dl, 40h
0x18011730c  jz      short loc_180117314
0x18011730e  add     eax, 3Fh ; '?'
0x180117311  and     eax, 0FFFFFFC0h
0x180117314  add     eax, ds:7FFE061Ch
0x18011731b  test    cl, cl
0x18011731d  jns     short loc_180117330
0x18011731f  test    dl, dl
0x180117321  jns     short loc_180117329
0x180117323  add     eax, 3Fh ; '?'
0x180117326  and     eax, 0FFFFFFC0h
0x180117329  add     eax, ds:7FFE0620h
0x180117330  bt      rcx, 8
0x180117335  jnb     short loc_18011734B
0x180117337  bt      rdx, 8
0x18011733c  jnb     short loc_180117344
  ... truncated ...
```
