# CheckInputColorSpace

- ea: `0x18000f8a0`
- end: `0x1800105a4`
- name: `CheckInputColorSpace`
- size: `3332`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000ee40`
- `0x18001fc68`

## callees

- `0x18000f8a0`
- `0x180018b68`
- `0x18001c21c`
- `0x18001d15d`

## pseudocode

```c
__int64 __fastcall CheckInputColorSpace(__int64 *a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v5; // r10d
  unsigned int v8; // edi
  unsigned int v9; // ebp
  unsigned __int8 v10; // r11
  int v11; // r8d
  int v12; // r14d
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  __int64 v17; // rdx
  unsigned int v18; // ebp
  unsigned int v19; // ebp
  unsigned int v20; // ebp
  __int64 v21; // r9
  __int64 v22; // r9
  __int64 v23; // rdx
  bool v24; // zf
  int *v25; // r12
  int v26; // r13d
  int v27; // r15d
  int v28; // ecx
  char *v29; // rax
  __int64 v30; // rax
  int v31; // r10d
  __int64 v32; // r11
  __int64 v33; // r9
  int v34; // r10d
  __int64 v35; // rdx
  char *v36; // r8
  char *v37; // rcx
  char *v38; // rdx
  int v39; // eax
  unsigned int v40; // ebp
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r11
  __int64 v45; // r9
  int v46; // r8d
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  int *v51; // r15
  int v52; // ebp
  int v53; // r14d
  int v54; // eax
  char *v55; // rax
  unsigned int v56; // ecx
  char *v57; // rax
  __int16 v58; // [rsp+50h] [rbp+8h] BYREF

  v5 = a5;
  v58 = 0;
  if ( a5 != *((_DWORD *)a1 + 7) )
    return 2021;
  v8 = 0;
  v9 = *(_DWORD *)a2;
  v10 = 1;
  if ( (*(_DWORD *)a2 & 0x4000) != 0 && (v9 & 0x1F) != 0xA )
  {
    v10 = 2;
    v9 = v9 & 0xFFFF9FFF | 0x2000;
  }
  v11 = v10;
  v12 = 8 * v10;
  *(_DWORD *)a3 = v12;
  *(_DWORD *)(a3 + 8) = v12;
  if ( v9 == 8206 )
  {
    if ( a4 == 1380401696 )
    {
      v13 = *a1;
      *(_QWORD *)(a2 + 48) = *a1;
      *(_QWORD *)(a2 + 32) = v13 + 2 * (unsigned int)v10;
      goto LABEL_6;
    }
    return 2021;
  }
  if ( v9 == 2190 )
  {
    if ( a4 != 1380401696 )
      return 2021;
    v17 = *a1;
    *(_QWORD *)(a2 + 32) = *a1 + 2 * (unsigned int)v10;
    *(_QWORD *)(a2 + 40) = v17 + v10;
    *(_QWORD *)(a2 + 48) = v17;
LABEL_14:
    *(_QWORD *)(a2 + 56) = v17 + 3 * (unsigned int)v10;
LABEL_15:
    *(_DWORD *)(a3 + 40) = 32 * v10;
    *(_DWORD *)(a2 + 24) = 4 * v10;
    return v8;
  }
  if ( v9 <= 0x501 )
  {
    if ( v9 != 1281 )
    {
      switch ( v9 )
      {
        case 0xAu:
          if ( a4 != 1196573017 )
            return 2021;
          *(_QWORD *)(a2 + 32) = *a1;
          *(_DWORD *)(a2 + 24) = 2;
          *(_DWORD *)a3 = 16;
          *(_DWORD *)(a3 + 8) = 16;
          *(_DWORD *)(a3 + 40) = 16;
          return v8;
        case 0x81u:
LABEL_23:
          if ( a4 != 1380401696 )
            return 2021;
          v17 = *a1;
          *(_QWORD *)(a2 + 32) = *a1;
          *(_QWORD *)(a2 + 40) = v17 + v10;
          *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
          goto LABEL_14;
        case 0x8Au:
          if ( a4 != 1196573017 )
            return 2021;
          v30 = *a1;
          *(_QWORD *)(a2 + 32) = *a1;
          *(_QWORD *)(a2 + 40) = v30 + 2;
          *(_DWORD *)(a2 + 24) = 4;
          *(_DWORD *)a3 = 16;
          *(_DWORD *)(a3 + 8) = 16;
          *(_DWORD *)(a3 + 40) = 32;
          return v8;
        case 0x8Fu:
LABEL_141:
          if ( a4 != 1497588338 )
            return 2021;
          v17 = *a1;
          *(_QWORD *)(a2 + 32) = *a1;
          *(_QWORD *)(a2 + 40) = v17 + v10;
          *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
          goto LABEL_14;
        default:
          return 2017;
      }
    }
    goto LABEL_92;
  }
  if ( v9 <= 0xA01 )
  {
    if ( v9 != 2561 )
    {
      if ( v9 > 0x801 )
      {
        switch ( v9 )
        {
          case 0x802u:
            if ( a4 != 1129142603 && a4 != 1129142560 )
              return 2021;
            v17 = *a1;
            *(_QWORD *)(a2 + 32) = *a1;
            *(_QWORD *)(a2 + 40) = v17 + v10;
            *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
            goto LABEL_14;
          case 0x805u:
            if ( a4 != 1501067552 )
              return 2021;
            v17 = *a1;
            *(_QWORD *)(a2 + 32) = *a1;
            *(_QWORD *)(a2 + 40) = v17 + v10;
            *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
            goto LABEL_14;
          case 0x806u:
            if ( a4 != 1482250784 )
              return 2021;
            v17 = *a1;
            *(_QWORD *)(a2 + 32) = *a1;
            *(_QWORD *)(a2 + 40) = v17 + v10;
            *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
            goto LABEL_14;
          case 0x808u:
            if ( a4 != 1281450528 )
              return 2021;
            v17 = *a1;
            *(_QWORD *)(a2 + 32) = *a1;
            *(_QWORD *)(a2 + 40) = v17 + v10;
            *(_QWORD *)(a2 + 48) = v17 + 2 * (unsigned int)v10;
            goto LABEL_14;
          case 0x80Du:
            v31 = v5 + 1;
            if ( v31 > 0 )
            {
              v32 = *a1;
              v33 = 0;
              do
              {
                *(_QWORD *)(a2 + 8 * v33 + 32) = v32 + (int)v33 * v11;
                v33 = (unsigned int)(v33 + 1);
              }
              while ( (int)v33 < v31 );
            }
            v34 = v11 * v31;
            *(_DWORD *)(a2 + 24) = v34;
            v15 = 8 * v34;
            goto LABEL_8;
          case 0x80Fu:
            if ( a4 != 1497588338 )
              return 2021;
            v23 = *a1;
            goto LABEL_68;
          case 0x81Du:
            if ( a4 != 1129142560 && a4 != 1129142603 )
              return 2021;
            v35 = *a1;
            *(_QWORD *)(a2 + 40) = *a1 + 2 * (unsigned int)v10;
            *(_QWORD *)(a2 + 56) = v35;
            *(_QWORD *)(a2 + 48) = v35 + v10;
            *(_QWORD *)(a2 + 32) = v35 + 3 * (unsigned int)v10;
            goto LABEL_15;
          default:
            return 2017;
        }
      }
      if ( v9 != 2049 )
      {
        if ( v9 <= 0x50E )
        {
          if ( v9 == 1294 )
          {
            if ( a4 != 1380401696 )
              return 2021;
            v21 = 1;
          }
          else
          {
            v18 = v9 - 1285;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                v20 = v19 - 2;
                if ( v20 )
                {
                  if ( v20 == 5 )
                  {
                    v21 = 0;
                    return (unsigned int)Do555To8Setup(a2, a3, &a5, v21);
                  }
                  return 2017;
                }
                if ( a4 != 1281450528 )
                  return 2021;
                v21 = 0;
              }
              else
              {
                if ( a4 != 1482250784 )
                  return 2021;
                v21 = 0;
              }
            }
            else
            {
              if ( a4 != 1501067552 )
                return 2021;
              v21 = 0;
            }
          }
          return (unsigned int)Do555To8Setup(a2, a3, &a5, v21);
        }
        if ( v9 != 1537 )
        {
          if ( v9 == 1549 )
          {
            v22 = 0;
          }
          else
          {
            if ( v9 != 1550 )
              return 2017;
            if ( a4 != 1380401696 )
              return 2021;
            v22 = 1;
          }
          v8 = Do555To8Setup(a2, a3, &a5, v22);
          if ( !v8 )
            *(_DWORD *)a3 = 6;
          return v8;
        }
LABEL_92:
        if ( a4 == 1380401696 )
        {
          v8 = Do555To8Setup(a2, a3, &a5, 0);
          if ( !v8 && v9 == 1537 )
            *(_DWORD *)a3 = 6;
          return v8;
        }
        return 2021;
      }
LABEL_132:
      if ( a4 != 1380401696 )
        return 2021;
      v23 = *a1;
LABEL_68:
      *(_QWORD *)(a2 + 32) = v23 + v10;
      *(_QWORD *)(a2 + 40) = v23 + 2 * (unsigned int)v10;
      *(_QWORD *)(a2 + 48) = v23 + 3 * (unsigned int)v10;
      *(_QWORD *)(a2 + 56) = v23;
      goto LABEL_15;
    }
LABEL_64:
    if ( a4 != 1380401696 )
      return 2021;
LABEL_77:
    v25 = (int *)(a2 + 12);
    v26 = 6 * *(_DWORD *)(a2 + 8);
    v27 = 307200 / v26;
    if ( 307200 / v26 )
    {
      v28 = *v25;
      if ( 307200 / v26 <= *v25 )
        v28 = 307200 / v26;
      else
        v27 = *v25;
    }
    else
    {
      v27 = 1;
      v28 = 1;
    }
    *(_DWORD *)(a3 + 32) = 0;
    *(_DWORD *)a3 = 10;
    *(_DWORD *)(a3 + 8) = 16;
    v29 = (char *)malloc_0(v28 * v26);
    *(_QWORD *)(a3 + 16) = v29;
    *(_DWORD *)(a3 + 40) = 32;
    if ( v29 )
    {
      *v25 = v27;
      v36 = v29 + 2;
      v37 = v29 + 4;
      if ( v9 == 2574 )
      {
        v38 = v29;
      }
      else
      {
        v38 = v29 + 4;
        v37 = v29;
      }
      v39 = 14;
      if ( v9 != 2574 )
        v39 = 1;
      *(_DWORD *)a2 = v39;
      *(_QWORD *)(a2 + 32) = v37;
      *(_QWORD *)(a2 + 40) = v36;
      *(_QWORD *)(a2 + 48) = v38;
      *(_DWORD *)(a2 + 16) = v26;
      *(_DWORD *)(a2 + 24) = 6;
    }
    else
    {
      return 8;
    }
    return v8;
  }
  if ( v9 <= 0xB0C )
  {
    if ( v9 == 2828 )
      return 2017;
    switch ( v9 )
    {
      case 0xA03u:
      case 0xA04u:
      case 0xA05u:
      case 0xA06u:
      case 0xA07u:
      case 0xA08u:
      case 0xA0Du:
      case 0xA0Eu:
        switch ( v9 )
        {
          case 0xA03u:
            v24 = a4 == 1213421088;
            break;
          case 0xA04u:
            v24 = a4 == 1212961568;
            break;
          case 0xA05u:
            v24 = a4 == 1501067552;
            break;
          case 0xA06u:
            v24 = a4 == 1482250784;
            break;
          case 0xA07u:
            v24 = a4 == 1282766368;
            break;
          case 0xA08u:
            v24 = a4 == 1281450528;
            break;
          case 0xA0Eu:
            goto LABEL_64;
          default:
            if ( v5 != 3 && v9 == 2573 )
              return 2021;
            goto LABEL_77;
        }
        if ( !v24 )
          return 2021;
        goto LABEL_77;
      default:
        return 2017;
    }
  }
  if ( v9 <= 0x2001 )
  {
    if ( v9 == 8193 )
    {
      if ( a4 == 1380401696 )
      {
        v13 = *a1;
        *(_QWORD *)(a2 + 32) = *a1;
        *(_QWORD *)(a2 + 48) = v13 + 2 * (unsigned int)v10;
LABEL_6:
        *(_QWORD *)(a2 + 40) = v13 + v10;
        *(_DWORD *)(a2 + 24) = 3 * v10;
        v14 = 3 * v10;
LABEL_7:
        v15 = 8 * v14;
LABEL_8:
        *(_DWORD *)(a3 + 40) = v15;
        return v8;
      }
      return 2021;
    }
    v40 = v9 - 6273;
    if ( v40 )
    {
      if ( v40 == 14 )
      {
        if ( a4 != 1497588338 )
          return 2021;
        v41 = *a1;
        v42 = *a1 + 2 * (unsigned int)v10;
        *(_QWORD *)(a2 + 32) = v41 + v10;
        *(_QWORD *)(a2 + 40) = v42;
        *(_QWORD *)(a2 + 48) = v41 + 3 * (unsigned int)v10;
        *(_QWORD *)(a2 + 56) = v41;
        goto LABEL_15;
      }
      return 2017;
    }
    goto LABEL_132;
  }
  if ( v9 > 0x2710 )
    return 2017;
  if ( v9 == 10000 )
  {
    if ( a4 != 1852662636 )
      return 2021;
    v51 = (int *)(a2 + 12);
    v52 = 3 * *(_DWORD *)(a2 + 8);
    v53 = 307200 / v52;
    if ( 307200 / v52 )
    {
      v54 = *v51;
      if ( v53 > *v51 )
      {
        v53 = *v51;
LABEL_159:
        *(_DWORD *)(a3 + 32) = 0;
        *(_DWORD *)a3 = 8;
        *(_DWORD *)(a3 + 8) = 8;
        v55 = (char *)SmartNewPtr(v54 * v52, &v58);
        v56 = v58;
        *(_QWORD *)(a3 + 16) = v55;
        *(_DWORD *)(a3 + 40) = 32;
        if ( (_WORD)v56 )
        {
          return v56;
        }
        else
        {
          *v51 = v53;
          *(_QWORD *)(a2 + 32) = v55;
          v57 = v55 + 1;
          *(_DWORD *)a2 = 8200;
          *(_QWORD *)(a2 + 40) = v57;
          *(_QWORD *)(a2 + 48) = v57 + 1;
          *(_DWORD *)(a2 + 16) = v52;
          *(_DWORD *)(a2 + 24) = 3;
        }
        return v8;
      }
    }
    else
    {
      v53 = 1;
    }
    v54 = v53;
    goto LABEL_159;
  }
  switch ( v9 )
  {
    case 0x2008u:
      if ( a4 != 1281450528 )
        return 2021;
      goto LABEL_107;
    case 0x2009u:
      if ( a4 != 1129142560 )
        return 2021;
      goto LABEL_107;
    case 0x200Au:
      if ( a4 != 1196573017 )
        return 2021;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_DWORD *)(a2 + 24) = 1;
      *(_DWORD *)a3 = 8;
      *(_DWORD *)(a3 + 8) = 8;
      *(_DWORD *)(a3 + 40) = 8;
      return v8;
    case 0x200Du:
      if ( v5 > 0 )
      {
        v44 = *a1;
        v45 = 0;
        do
        {
          *(_QWORD *)(a2 + 8 * v45 + 32) = v44 + (int)v45 * v11;
          v45 = (unsigned int)(v45 + 1);
        }
        while ( (int)v45 < v5 );
      }
      v46 = v5 * v11;
      *(_DWORD *)(a2 + 24) = v46;
      v15 = 8 * v46;
      goto LABEL_8;
    case 0x200Fu:
      if ( a4 == 1497588338 )
      {
LABEL_107:
        v13 = *a1;
        *(_QWORD *)(a2 + 32) = *a1;
        *(_QWORD *)(a2 + 48) = v13 + 2 * (unsigned int)v10;
        goto LABEL_6;
      }
      v8 = 2021;
      break;
    case 0x2011u:
      if ( a4 != 893602898 )
        return 2021;
      v47 = *a1;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_QWORD *)(a2 + 40) = v47 + v10;
      *(_QWORD *)(a2 + 48) = v47 + 2 * (unsigned int)v10;
      *(_QWORD *)(a2 + 56) = v47 + 3 * (unsigned int)v10;
      *(_QWORD *)(a2 + 64) = v47 + 4 * (unsigned int)v10;
      *(_DWORD *)(a2 + 24) = 5 * v10;
      v14 = 5 * v10;
      goto LABEL_7;
    case 0x2012u:
      if ( a4 != 910380114 )
        return 2021;
      v48 = *a1;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_QWORD *)(a2 + 40) = v48 + v10;
      *(_QWORD *)(a2 + 48) = v48 + 2 * (unsigned int)v10;
      *(_QWORD *)(a2 + 56) = v48 + 3 * (unsigned int)v10;
      *(_QWORD *)(a2 + 64) = v48 + 4 * (unsigned int)v10;
      *(_QWORD *)(a2 + 72) = v48 + 5 * (unsigned int)v10;
      *(_DWORD *)(a2 + 24) = 6 * v10;
      v15 = 48 * v10;
      goto LABEL_8;
    case 0x2013u:
      if ( a4 != 927157330 )
        return 2021;
      v49 = *a1;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_QWORD *)(a2 + 40) = v49 + v10;
      *(_QWORD *)(a2 + 48) = v49 + 2 * (unsigned int)v10;
      *(_QWORD *)(a2 + 56) = v49 + 3 * (unsigned int)v10;
      *(_QWORD *)(a2 + 64) = v49 + 4 * (unsigned int)v10;
      *(_QWORD *)(a2 + 72) = v49 + 5 * (unsigned int)v10;
      *(_QWORD *)(a2 + 80) = v49 + 6 * (unsigned int)v10;
      *(_DWORD *)(a2 + 24) = 7 * v10;
      v15 = 56 * v10;
      goto LABEL_8;
    case 0x2014u:
      if ( a4 != 943934546 )
        return 2021;
      v50 = *a1;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_QWORD *)(a2 + 40) = v50 + v10;
      *(_QWORD *)(a2 + 48) = v50 + 2 * (unsigned int)v10;
      *(_QWORD *)(a2 + 56) = v50 + 3 * (unsigned int)v10;
      *(_QWORD *)(a2 + 64) = v50 + 4 * (unsigned int)v10;
      *(_QWORD *)(a2 + 72) = v50 + 5 * (unsigned int)v10;
      *(_QWORD *)(a2 + 80) = v50 + 6 * (unsigned int)v10;
      *(_QWORD *)(a2 + 88) = v50 + 7 * (unsigned int)v10;
      *(_DWORD *)(a3 + 40) = v10 << 6;
      *(_DWORD *)(a2 + 24) = v12;
      return v8;
    case 0x2081u:
      goto LABEL_23;
    case 0x208Au:
      if ( a4 != 1196573017 )
        return 2021;
      v43 = *a1;
      *(_QWORD *)(a2 + 32) = *a1;
      *(_QWORD *)(a2 + 40) = v43 + 1;
      *(_DWORD *)(a2 + 24) = 2;
      *(_DWORD *)a3 = 8;
      *(_DWORD *)(a3 + 8) = 8;
      *(_DWORD *)(a3 + 40) = 16;
      return v8;
    case 0x208Fu:
      goto LABEL_141;
    default:
      return 2017;
  }
  return v8;
}

```

## disassembly

```asm
0x18000f8a0  mov     [rsp+arg_18], rbx
0x18000f8a5  push    rsi
0x18000f8a6  push    rdi
0x18000f8a7  push    r12
0x18000f8a9  push    r13
0x18000f8ab  push    r15
0x18000f8ad  sub     rsp, 20h
0x18000f8b1  mov     r10d, [rsp+48h+arg_20]
0x18000f8b6  xor     eax, eax
0x18000f8b8  mov     rbx, rdx
0x18000f8bb  mov     rsi, r8
0x18000f8be  mov     rdx, rcx
0x18000f8c1  mov     [rsp+48h+arg_0], ax
0x18000f8c6  cmp     r10d, [rcx+1Ch]
0x18000f8ca  jnz     loc_18000F95F
0x18000f8d0  mov     [rsp+48h+arg_8], rbp
0x18000f8d5  xor     edi, edi
0x18000f8d7  mov     ebp, [rbx]
0x18000f8d9  mov     r11b, 1
0x18000f8dc  mov     [rsp+48h+arg_10], r14
0x18000f8e1  bt      ebp, 0Eh
0x18000f8e5  jb      loc_18000FAB3
0x18000f8eb  movzx   r8d, r11b
0x18000f8ef  lea     r14d, ds:0[r8*8]
0x18000f8f7  mov     [rsi], r14d
0x18000f8fa  mov     [rsi+8], r14d
0x18000f8fe  cmp     ebp, 200Eh
0x18000f904  jnz     short loc_18000F966
0x18000f906  cmp     r9d, 52474220h
0x18000f90d  jnz     loc_18000FA4A
0x18000f913  mov     rdx, [rcx]
0x18000f916  lea     ecx, [r8+r8]
0x18000f91a  add     rcx, rdx
0x18000f91d  mov     [rbx+30h], rdx
0x18000f921  mov     [rbx+20h], rcx
0x18000f925  movzx   eax, r11b
0x18000f929  add     rax, rdx
0x18000f92c  mov     [rbx+28h], rax
0x18000f930  lea     eax, [r8+r8*2]
0x18000f934  mov     [rbx+18h], eax
0x18000f937  lea     eax, [r8+r8*2]
0x18000f93b  shl     eax, 3
0x18000f93e  mov     [rsi+28h], eax
0x18000f941  mov     rbp, [rsp+48h+arg_8]
0x18000f946  mov     r14, [rsp+48h+arg_10]
0x18000f94b  mov     rbx, [rsp+48h+arg_18]
0x18000f950  mov     eax, edi
0x18000f952  add     rsp, 20h
0x18000f956  pop     r15
0x18000f958  pop     r13
0x18000f95a  pop     r12
0x18000f95c  pop     rdi
0x18000f95d  pop     rsi
0x18000f95e  retn
0x18000f95f  mov     edi, 7E5h
0x18000f964  jmp     short loc_18000F94B
0x18000f966  cmp     ebp, 88Eh
0x18000f96c  jnz     short loc_18000F9B8
0x18000f96e  cmp     r9d, 52474220h
0x18000f975  jnz     loc_18000FA4A
0x18000f97b  mov     rdx, [rcx]
0x18000f97e  lea     ecx, [r8+r8]
0x18000f982  add     rcx, rdx
0x18000f985  movzx   eax, r11b
0x18000f989  add     rax, rdx
0x18000f98c  mov     [rbx+20h], rcx
0x18000f990  mov     [rbx+28h], rax
0x18000f994  mov     [rbx+30h], rdx
0x18000f998  lea     ecx, [r8+r8*2]
0x18000f99c  add     rcx, rdx
0x18000f99f  mov     [rbx+38h], rcx
0x18000f9a3  lea     eax, ds:0[r8*4]
0x18000f9ab  shl     r8d, 5
0x18000f9af  mov     [rsi+28h], r8d
0x18000f9b3  mov     [rbx+18h], eax
0x18000f9b6  jmp     short loc_18000F941
0x18000f9b8  cmp     ebp, 501h
0x18000f9be  jbe     loc_18000FA54
0x18000f9c4  cmp     ebp, 0A01h
0x18000f9ca  ja      loc_18000FB2B
0x18000f9d0  jz      loc_18000FC7F
0x18000f9d6  cmp     ebp, 801h
0x18000f9dc  jbe     loc_18000FAD2
0x18000f9e2  add     ebp, 0FFFFF7FEh; switch 28 cases
0x18000f9e8  cmp     ebp, 1Bh
0x18000f9eb  ja      def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000f9f1  lea     r15, cs:180000000h
0x18000f9f8  movzx   eax, ds:(byte_1800103F4 - 180000000h)[r15+rbp]
0x18000fa01  mov     ecx, ds:(jpt_18000FA0C - 180000000h)[r15+rax*4]
0x18000fa09  add     rcx, r15
0x18000fa0c  jmp     rcx; switch jump
0x18000fa0e  cmp     r9d, 434D594Bh; jumptable 000000018000FA0C case 2050
0x18000fa15  jnz     loc_18000FEE8
0x18000fa1b  mov     rdx, [rdx]
0x18000fa1e  lea     ecx, [r8+r8]
0x18000fa22  movzx   eax, r11b
0x18000fa26  add     rax, rdx
0x18000fa29  mov     [rbx+20h], rdx
0x18000fa2d  add     rcx, rdx
0x18000fa30  mov     [rbx+28h], rax
0x18000fa34  mov     [rbx+30h], rcx
0x18000fa38  jmp     loc_18000F998
0x18000fa3d  cmp     r9d, 52474220h; jumptable 000000018000FA81 case 129
0x18000fa44  jz      loc_1800100BB
0x18000fa4a  mov     edi, 7E5h
0x18000fa4f  jmp     loc_18000F941
0x18000fa54  jz      loc_18000FE6A
0x18000fa5a  cmp     ebp, 8Fh; switch 144 cases
0x18000fa60  ja      def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fa66  lea     r15, cs:180000000h
0x18000fa6d  movzx   eax, ds:(byte_180010428 - 180000000h)[r15+rbp]
0x18000fa76  mov     ecx, ds:(jpt_18000FA81 - 180000000h)[r15+rax*4]
0x18000fa7e  add     rcx, r15
0x18000fa81  jmp     rcx; switch jump
0x18000fa83  cmp     r9d, 47524159h; jumptable 000000018000FA81 case 10
0x18000fa8a  jnz     short loc_18000FA4A
0x18000fa8c  mov     rax, [rdx]
0x18000fa8f  mov     [rbx+20h], rax
0x18000fa93  mov     dword ptr [rbx+18h], 2
0x18000fa9a  mov     dword ptr [rsi], 10h
0x18000faa0  mov     dword ptr [rsi+8], 10h
0x18000faa7  mov     dword ptr [rsi+28h], 10h
0x18000faae  jmp     loc_18000F941
0x18000fab3  mov     eax, ebp
0x18000fab5  and     eax, 1Fh
0x18000fab8  cmp     al, 0Ah
0x18000faba  jz      loc_18000F8EB
0x18000fac0  btr     ebp, 0Eh
0x18000fac4  mov     r11b, 2
0x18000fac7  or      ebp, 2000h
0x18000facd  jmp     loc_18000F8EB
0x18000fad2  jz      loc_180010082
0x18000fad8  cmp     ebp, 50Eh
0x18000fade  ja      loc_18000FBBA
0x18000fae4  jz      loc_18000FE4A
0x18000faea  sub     ebp, 505h
0x18000faf0  jz      loc_18000FE35
0x18000faf6  sub     ebp, 1
0x18000faf9  jz      loc_18000FE20
0x18000faff  sub     ebp, 2
0x18000fb02  jz      loc_18000FE0B
0x18000fb08  cmp     ebp, 5
0x18000fb0b  jnz     def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fb11  xor     r9d, r9d
0x18000fb14  lea     r8, [rsp+48h+arg_20]
0x18000fb19  mov     rdx, rsi
0x18000fb1c  mov     rcx, rbx
0x18000fb1f  call    Do555To8Setup
0x18000fb24  mov     edi, eax
0x18000fb26  jmp     loc_18000F941
0x18000fb2b  cmp     ebp, 0B0Ch
0x18000fb31  jbe     loc_18000FC0A
0x18000fb37  cmp     ebp, 2001h
0x18000fb3d  jbe     loc_180010035
0x18000fb43  cmp     ebp, 2710h
0x18000fb49  ja      short def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fb4b  jz      loc_180010330
0x18000fb51  add     ebp, 0FFFFDFF8h; switch 136 cases
0x18000fb57  cmp     ebp, 87h
0x18000fb5d  ja      short def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fb5f  lea     r15, cs:180000000h
0x18000fb66  movzx   eax, ds:(byte_1800104EC - 180000000h)[r15+rbp]
0x18000fb6f  mov     ecx, ds:(jpt_18000FB7A - 180000000h)[r15+rax*4]
0x18000fb77  add     rcx, r15
0x18000fb7a  jmp     rcx; switch jump
0x18000fb7c  cmp     r9d, 47524159h; jumptable 000000018000FB7A case 8202
0x18000fb83  jnz     loc_18000FA4A
0x18000fb89  mov     rax, [rdx]
0x18000fb8c  mov     [rbx+20h], rax
0x18000fb90  mov     dword ptr [rbx+18h], 1
0x18000fb97  mov     dword ptr [rsi], 8
0x18000fb9d  mov     dword ptr [rsi+8], 8
0x18000fba4  mov     dword ptr [rsi+28h], 8
0x18000fbab  jmp     loc_18000F941
0x18000fbb0  mov     edi, 7E1h; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fbb5  jmp     loc_18000F941
0x18000fbba  mov     eax, ebp
0x18000fbbc  sub     eax, 601h
0x18000fbc1  jz      loc_18000FE6A
0x18000fbc7  sub     eax, 0Ch
0x18000fbca  jz      loc_18000FE62
0x18000fbd0  cmp     eax, 1
0x18000fbd3  jnz     short def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fbd5  cmp     r9d, 52474220h
0x18000fbdc  jnz     loc_18000FA4A
0x18000fbe2  mov     r9d, eax
0x18000fbe5  lea     r8, [rsp+48h+arg_20]
0x18000fbea  mov     rdx, rsi
0x18000fbed  mov     rcx, rbx
0x18000fbf0  call    Do555To8Setup
0x18000fbf5  mov     edi, eax
0x18000fbf7  test    eax, eax
0x18000fbf9  jnz     loc_18000F941
0x18000fbff  mov     dword ptr [rsi], 6
0x18000fc05  jmp     loc_18000F941
0x18000fc0a  jz      short def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fc0c  lea     eax, [rbp-0A03h]; switch 12 cases
0x18000fc12  cmp     eax, 0Bh
0x18000fc15  ja      short def_18000FA0C; jumptable 000000018000FA0C default case, cases 2051,2052,2055,2057-2060,2062,2064-2076
0x18000fc17  lea     r15, cs:180000000h
0x18000fc1e  mov     eax, ds:(jpt_18000FC29 - 180000000h)[r15+rax*4]
0x18000fc26  add     rax, r15
0x18000fc29  jmp     rax; switch jump
0x18000fc2b  cmp     ebp, 0A03h; jumptable 000000018000FC29 cases 2563-2568,2573,2574
0x18000fc31  jz      loc_18000FD58
0x18000fc37  cmp     ebp, 0A04h
0x18000fc3d  jz      loc_18000FFF2
0x18000fc43  cmp     ebp, 0A05h
0x18000fc49  jz      loc_18000FFFE
0x18000fc4f  cmp     ebp, 0A06h
0x18000fc55  jz      loc_18001000A
0x18000fc5b  cmp     ebp, 0A07h
0x18000fc61  jz      loc_180010016
0x18000fc67  cmp     ebp, 0A08h
0x18000fc6d  jz      loc_180010022
0x18000fc73  cmp     ebp, 0A0Eh
0x18000fc79  jnz     loc_18000FFC0
0x18000fc7f  cmp     r9d, 52474220h
0x18000fc86  jnz     loc_18000FA4A
0x18000fc8c  jmp     loc_18000FD65
0x18000fc91  cmp     r9d, 59436272h; jumptable 000000018000FA0C case 2063
0x18000fc98  jnz     loc_18000FA4A
0x18000fc9e  mov     rdx, [rdx]
0x18000fca1  movzx   eax, r11b
0x18000fca5  lea     ecx, [r8+r8]
0x18000fca9  add     rcx, rdx
0x18000fcac  add     rax, rdx
0x18000fcaf  mov     [rbx+20h], rax
0x18000fcb3  mov     [rbx+28h], rcx
0x18000fcb7  lea     ecx, [r8+r8*2]
0x18000fcbb  add     rcx, rdx
0x18000fcbe  mov     [rbx+30h], rcx
0x18000fcc2  mov     [rbx+38h], rdx
0x18000fcc6  jmp     loc_18000F9A3
0x18000fccb  cmp     r9d, 4C616220h; jumptable 000000018000FA0C case 2056
0x18000fcd2  jnz     loc_18000FA4A
0x18000fcd8  mov     rdx, [rdx]
0x18000fcdb  lea     ecx, [r8+r8]
0x18000fcdf  movzx   eax, r11b
0x18000fce3  add     rax, rdx
0x18000fce6  mov     [rbx+20h], rdx
0x18000fcea  add     rcx, rdx
0x18000fced  mov     [rbx+28h], rax
0x18000fcf1  mov     [rbx+30h], rcx
0x18000fcf5  jmp     loc_18000F998
0x18000fcfa  cmp     r9d, 58595A20h; jumptable 000000018000FA0C case 2054
0x18000fd01  jnz     loc_18000FA4A
0x18000fd07  mov     rdx, [rdx]
0x18000fd0a  lea     ecx, [r8+r8]
0x18000fd0e  movzx   eax, r11b
0x18000fd12  add     rax, rdx
0x18000fd15  mov     [rbx+20h], rdx
0x18000fd19  add     rcx, rdx
0x18000fd1c  mov     [rbx+28h], rax
0x18000fd20  mov     [rbx+30h], rcx
0x18000fd24  jmp     loc_18000F998
0x18000fd29  cmp     r9d, 59787920h; jumptable 000000018000FA0C case 2053
0x18000fd30  jnz     loc_18000FA4A
0x18000fd36  mov     rdx, [rdx]
0x18000fd39  lea     ecx, [r8+r8]
0x18000fd3d  movzx   eax, r11b
0x18000fd41  add     rax, rdx
0x18000fd44  mov     [rbx+20h], rdx
0x18000fd48  add     rcx, rdx
0x18000fd4b  mov     [rbx+28h], rax
0x18000fd4f  mov     [rbx+30h], rcx
0x18000fd53  jmp     loc_18000F998
0x18000fd58  cmp     r9d, 48535620h
0x18000fd5f  jnz     loc_18000FA4A
0x18000fd65  mov     eax, [rbx+8]
0x18000fd68  lea     r12, [rbx+0Ch]
0x18000fd6c  mov     r14d, 1
0x18000fd72  lea     r13d, [rax+rax*2]
0x18000fd76  mov     eax, 4B000h
0x18000fd7b  add     r13d, r13d
0x18000fd7e  cdq
0x18000fd7f  idiv    r13d
0x18000fd82  mov     r15d, eax
0x18000fd85  test    eax, eax
0x18000fd87  jnz     loc_18000FF34
0x18000fd8d  mov     r15d, r14d
0x18000fd90  mov     ecx, r14d
0x18000fd93  mov     eax, r13d
0x18000fd96  mov     [rsi+20h], edi
0x18000fd99  imul    eax, ecx
0x18000fd9c  mov     dword ptr [rsi], 0Ah
0x18000fda2  mov     dword ptr [rsi+8], 10h
0x18000fda9  movsxd  rcx, eax; Size
0x18000fdac  call    malloc_0
0x18000fdb1  mov     [rsi+10h], rax
0x18000fdb5  mov     dword ptr [rsi+28h], 20h ; ' '
0x18000fdbc  test    rax, rax
0x18000fdbf  jnz     loc_18000FF7A
0x18000fdc5  mov     edi, 8
0x18000fdca  jmp     loc_18000F941
0x18000fdcf  cmp     r9d, 47524159h; jumptable 000000018000FA81 case 138
0x18000fdd6  jnz     loc_18000FA4A
0x18000fddc  mov     rax, [rdx]
0x18000fddf  mov     [rbx+20h], rax
0x18000fde3  add     rax, 2
  ... truncated ...
```
