# RtlpCopyContext

- ea: `0x180115ab0`
- end: `0x18011650e`
- name: `RtlpCopyContext`
- size: `2654`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801146d0`
- `0x180115040`

## callees

- `0x1800b5ec0`
- `0x180115ab0`
- `0x180163a80`

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
0x180115ab0  mov     [rsp+arg_10], rbx
0x180115ab5  push    rbp
0x180115ab6  sub     rsp, 20h
0x180115aba  mov     rbp, rdx
0x180115abd  mov     rbx, rcx
0x180115ac0  cmp     rdx, rcx
0x180115ac3  jnz     short loc_180115ADC
0x180115ac5  mov     eax, [rdx+30h]
0x180115ac8  and     eax, 10004Fh
0x180115acd  mov     [rcx+30h], eax
0x180115ad0  mov     rbx, [rsp+28h+arg_10]
0x180115ad5  add     rsp, 20h
0x180115ad9  pop     rbp
0x180115ada  retn
0x180115adc  mov     [rsp+28h+arg_0], rsi
0x180115ae1  mov     r10d, 240h
0x180115ae7  mov     esi, [rcx+30h]
0x180115aea  mov     eax, esi
0x180115aec  mov     dword ptr [rcx+30h], 0
0x180115af3  and     eax, [rdx+30h]
0x180115af6  and     eax, 100040h
0x180115afb  mov     [rsp+28h+arg_8], rdi
0x180115b00  cmp     eax, 100040h
0x180115b05  jnz     loc_180115E1D
0x180115b0b  mov     [rcx+30h], eax
0x180115b0e  mov     eax, ds:7FFE03D8h
0x180115b15  or      eax, ds:7FFE0708h
0x180115b1c  and     eax, 800h
0x180115b21  jz      loc_180115C91
0x180115b27  mov     edi, ds:7FFE03ECh
0x180115b2e  test    edi, 0FFFFFFF8h
0x180115b34  jnz     loc_180115C91
0x180115b3a  lea     rcx, [rdx+4D0h]
0x180115b41  call    RtlpLocateXStateChunk
0x180115b46  mov     r11, rax
0x180115b49  test    rax, rax
0x180115b4c  jz      loc_180115C9D
0x180115b52  test    dil, 2
0x180115b56  jz      loc_180115C7F
0x180115b5c  mov     rcx, [rax+8]
0x180115b60  bt      rcx, 0Bh
0x180115b65  jb      short loc_180115B6F
0x180115b67  xor     r11d, r11d
0x180115b6a  jmp     loc_180115C9D
0x180115b6f  mov     rdx, ds:7FFE05F8h
0x180115b77  mov     eax, r10d
0x180115b7a  test    cl, 4
0x180115b7d  jz      short loc_180115B8C
0x180115b7f  lfence
0x180115b82  mov     eax, ds:7FFE060Ch
0x180115b89  add     eax, r10d
0x180115b8c  test    cl, 8
0x180115b8f  jz      short loc_180115BA6
0x180115b91  lfence
0x180115b94  test    dl, 8
0x180115b97  jz      short loc_180115B9F
0x180115b99  add     eax, 3Fh ; '?'
0x180115b9c  and     eax, 0FFFFFFC0h
0x180115b9f  add     eax, ds:7FFE0610h
0x180115ba6  test    cl, 10h
0x180115ba9  jz      short loc_180115BC0
0x180115bab  lfence
0x180115bae  test    dl, 10h
0x180115bb1  jz      short loc_180115BB9
0x180115bb3  add     eax, 3Fh ; '?'
0x180115bb6  and     eax, 0FFFFFFC0h
0x180115bb9  add     eax, ds:7FFE0614h
0x180115bc0  test    cl, 20h
0x180115bc3  jz      short loc_180115BDA
0x180115bc5  lfence
0x180115bc8  test    dl, 20h
0x180115bcb  jz      short loc_180115BD3
0x180115bcd  add     eax, 3Fh ; '?'
0x180115bd0  and     eax, 0FFFFFFC0h
0x180115bd3  add     eax, ds:7FFE0618h
0x180115bda  test    cl, 40h
0x180115bdd  jz      short loc_180115BF4
0x180115bdf  lfence
0x180115be2  test    dl, 40h
0x180115be5  jz      short loc_180115BED
0x180115be7  add     eax, 3Fh ; '?'
0x180115bea  and     eax, 0FFFFFFC0h
0x180115bed  add     eax, ds:7FFE061Ch
0x180115bf4  test    cl, cl
0x180115bf6  jns     short loc_180115C0C
0x180115bf8  lfence
0x180115bfb  test    dl, dl
0x180115bfd  jns     short loc_180115C05
0x180115bff  add     eax, 3Fh ; '?'
0x180115c02  and     eax, 0FFFFFFC0h
0x180115c05  add     eax, ds:7FFE0620h
0x180115c0c  bt      rcx, 8
0x180115c11  jnb     short loc_180115C2A
0x180115c13  lfence
0x180115c16  bt      rdx, 8
0x180115c1b  jnb     short loc_180115C23
0x180115c1d  add     eax, 3Fh ; '?'
0x180115c20  and     eax, 0FFFFFFC0h
0x180115c23  add     eax, ds:7FFE0624h
0x180115c2a  bt      rcx, 9
0x180115c2f  jnb     short loc_180115C48
0x180115c31  lfence
0x180115c34  bt      rdx, 9
0x180115c39  jnb     short loc_180115C41
0x180115c3b  add     eax, 3Fh ; '?'
0x180115c3e  and     eax, 0FFFFFFC0h
0x180115c41  add     eax, ds:7FFE0628h
0x180115c48  bt      rcx, 0Ah
0x180115c4d  jnb     short loc_180115C66
0x180115c4f  lfence
0x180115c52  bt      rdx, 0Ah
0x180115c57  jnb     short loc_180115C5F
0x180115c59  add     eax, 3Fh ; '?'
0x180115c5c  and     eax, 0FFFFFFC0h
0x180115c5f  add     eax, ds:7FFE062Ch
0x180115c66  bt      rdx, 0Bh
0x180115c6b  jnb     short loc_180115C73
0x180115c6d  add     eax, 3Fh ; '?'
0x180115c70  and     eax, 0FFFFFFC0h
0x180115c73  add     r11, 0FFFFFFFFFFFFFE00h
0x180115c7a  add     r11, rax
0x180115c7d  jmp     short loc_180115C9D
0x180115c7f  mov     eax, ds:7FFE0448h
0x180115c86  add     rax, 0FFFFFFFFFFFFFE00h
0x180115c8c  add     r11, rax
0x180115c8f  jmp     short loc_180115C9D
0x180115c91  xor     r11d, r11d
0x180115c94  test    rax, rax
0x180115c97  jz      loc_180115DE7
0x180115c9d  mov     edi, ds:7FFE03ECh
0x180115ca4  test    edi, 0FFFFFFF8h
0x180115caa  jnz     loc_180115DE7
0x180115cb0  lea     rcx, [rbx+4D0h]
0x180115cb7  call    RtlpLocateXStateChunk
0x180115cbc  mov     r8, rax
0x180115cbf  test    rax, rax
0x180115cc2  jz      loc_180115DE7
0x180115cc8  test    dil, 2
0x180115ccc  jz      loc_180115DD5
0x180115cd2  mov     rcx, [rax+8]
0x180115cd6  bt      rcx, 0Bh
0x180115cdb  jnb     loc_180115DE7
0x180115ce1  mov     rdx, ds:7FFE05F8h
0x180115ce9  mov     eax, r10d
0x180115cec  test    cl, 4
0x180115cef  jz      short loc_180115CFB
0x180115cf1  mov     eax, ds:7FFE060Ch
0x180115cf8  add     eax, r10d
0x180115cfb  test    cl, 8
0x180115cfe  jz      short loc_180115D12
0x180115d00  test    dl, 8
0x180115d03  jz      short loc_180115D0B
0x180115d05  add     eax, 3Fh ; '?'
0x180115d08  and     eax, 0FFFFFFC0h
0x180115d0b  add     eax, ds:7FFE0610h
0x180115d12  test    cl, 10h
0x180115d15  jz      short loc_180115D29
0x180115d17  test    dl, 10h
0x180115d1a  jz      short loc_180115D22
0x180115d1c  add     eax, 3Fh ; '?'
0x180115d1f  and     eax, 0FFFFFFC0h
0x180115d22  add     eax, ds:7FFE0614h
0x180115d29  test    cl, 20h
0x180115d2c  jz      short loc_180115D40
0x180115d2e  test    dl, 20h
0x180115d31  jz      short loc_180115D39
0x180115d33  add     eax, 3Fh ; '?'
0x180115d36  and     eax, 0FFFFFFC0h
0x180115d39  add     eax, ds:7FFE0618h
0x180115d40  test    cl, 40h
0x180115d43  jz      short loc_180115D57
0x180115d45  test    dl, 40h
0x180115d48  jz      short loc_180115D50
0x180115d4a  add     eax, 3Fh ; '?'
0x180115d4d  and     eax, 0FFFFFFC0h
0x180115d50  add     eax, ds:7FFE061Ch
0x180115d57  test    cl, cl
0x180115d59  jns     short loc_180115D6C
0x180115d5b  test    dl, dl
0x180115d5d  jns     short loc_180115D65
0x180115d5f  add     eax, 3Fh ; '?'
0x180115d62  and     eax, 0FFFFFFC0h
0x180115d65  add     eax, ds:7FFE0620h
0x180115d6c  bt      rcx, 8
0x180115d71  jnb     short loc_180115D87
0x180115d73  bt      rdx, 8
0x180115d78  jnb     short loc_180115D80
0x180115d7a  add     eax, 3Fh ; '?'
0x180115d7d  and     eax, 0FFFFFFC0h
0x180115d80  add     eax, ds:7FFE0624h
0x180115d87  bt      rcx, 9
0x180115d8c  jnb     short loc_180115DA2
0x180115d8e  bt      rdx, 9
0x180115d93  jnb     short loc_180115D9B
0x180115d95  add     eax, 3Fh ; '?'
0x180115d98  and     eax, 0FFFFFFC0h
0x180115d9b  add     eax, ds:7FFE0628h
0x180115da2  bt      rcx, 0Ah
0x180115da7  jnb     short loc_180115DBD
0x180115da9  bt      rdx, 0Ah
0x180115dae  jnb     short loc_180115DB6
0x180115db0  add     eax, 3Fh ; '?'
0x180115db3  and     eax, 0FFFFFFC0h
0x180115db6  add     eax, ds:7FFE062Ch
0x180115dbd  bt      rdx, 0Bh
0x180115dc2  jnb     short loc_180115DCA
0x180115dc4  add     eax, 3Fh ; '?'
0x180115dc7  and     eax, 0FFFFFFC0h
0x180115dca  add     rax, 0FFFFFFFFFFFFFE00h
0x180115dd0  add     rax, r8
0x180115dd3  jmp     short loc_180115DE9
0x180115dd5  mov     eax, ds:7FFE0448h
0x180115ddc  add     rax, 0FFFFFFFFFFFFFE00h
0x180115de2  add     rax, r8
0x180115de5  jmp     short loc_180115DE9
0x180115de7  xor     eax, eax
0x180115de9  test    r11, r11
0x180115dec  jz      short loc_180115E1D
0x180115dee  test    rax, rax
0x180115df1  jz      short loc_180115E1D
0x180115df3  movups  xmm0, xmmword ptr [r11]
0x180115df7  movups  xmmword ptr [rax], xmm0
0x180115dfa  movsxd  rax, dword ptr [rbp+4E0h]
0x180115e01  movsxd  rdx, dword ptr [rbx+4E0h]
0x180115e08  mov     ecx, [rax+rbp+4D0h]
0x180115e0f  and     ecx, 800h
0x180115e15  or      [rdx+rbx+4D0h], rcx
0x180115e1d  and     esi, [rbp+30h]
0x180115e20  and     esi, 100040h
0x180115e26  cmp     esi, 100040h
0x180115e2c  jnz     loc_18011632D
0x180115e32  or      [rbx+30h], esi
0x180115e35  mov     eax, ds:7FFE03D8h
0x180115e3c  or      eax, ds:7FFE0708h
0x180115e43  and     eax, 80000h
0x180115e48  jz      loc_18011608F
0x180115e4e  mov     r11d, ds:7FFE03ECh
0x180115e56  test    r11d, 0FFFFFFF8h
0x180115e5d  jnz     loc_18011608F
0x180115e63  lea     rcx, [rbp+4D0h]
0x180115e6a  call    RtlpLocateXStateChunk
0x180115e6f  mov     r8, rax
0x180115e72  test    rax, rax
0x180115e75  jnz     short loc_180115E81
0x180115e77  xor     esi, esi
0x180115e79  xor     r11d, r11d
0x180115e7c  jmp     loc_18011609D
0x180115e81  test    r11b, 2
0x180115e85  jz      loc_180116075
0x180115e8b  mov     rcx, [rax+8]
0x180115e8f  mov     esi, ds:7FFE0650h
0x180115e96  bt      rcx, 13h
0x180115e9b  jb      short loc_180115EA5
0x180115e9d  xor     r11d, r11d
0x180115ea0  jmp     loc_18011609D
0x180115ea5  mov     rdx, ds:7FFE05F8h
0x180115ead  mov     eax, r10d
0x180115eb0  test    cl, 4
0x180115eb3  jz      short loc_180115EBF
0x180115eb5  mov     eax, ds:7FFE060Ch
0x180115ebc  add     eax, r10d
0x180115ebf  test    cl, 8
0x180115ec2  jz      short loc_180115ED6
0x180115ec4  test    dl, 8
0x180115ec7  jz      short loc_180115ECF
0x180115ec9  add     eax, 3Fh ; '?'
0x180115ecc  and     eax, 0FFFFFFC0h
0x180115ecf  add     eax, ds:7FFE0610h
0x180115ed6  test    cl, 10h
0x180115ed9  jz      short loc_180115EED
0x180115edb  test    dl, 10h
0x180115ede  jz      short loc_180115EE6
0x180115ee0  add     eax, 3Fh ; '?'
0x180115ee3  and     eax, 0FFFFFFC0h
0x180115ee6  add     eax, ds:7FFE0614h
0x180115eed  test    cl, 20h
0x180115ef0  jz      short loc_180115F04
0x180115ef2  test    dl, 20h
0x180115ef5  jz      short loc_180115EFD
0x180115ef7  add     eax, 3Fh ; '?'
0x180115efa  and     eax, 0FFFFFFC0h
0x180115efd  add     eax, ds:7FFE0618h
0x180115f04  test    cl, 40h
0x180115f07  jz      short loc_180115F1B
0x180115f09  test    dl, 40h
0x180115f0c  jz      short loc_180115F14
0x180115f0e  add     eax, 3Fh ; '?'
0x180115f11  and     eax, 0FFFFFFC0h
0x180115f14  add     eax, ds:7FFE061Ch
0x180115f1b  test    cl, cl
0x180115f1d  jns     short loc_180115F30
0x180115f1f  test    dl, dl
0x180115f21  jns     short loc_180115F29
0x180115f23  add     eax, 3Fh ; '?'
0x180115f26  and     eax, 0FFFFFFC0h
0x180115f29  add     eax, ds:7FFE0620h
0x180115f30  bt      rcx, 8
0x180115f35  jnb     short loc_180115F4B
0x180115f37  bt      rdx, 8
0x180115f3c  jnb     short loc_180115F44
  ... truncated ...
```
