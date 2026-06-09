# EscapeImpl(HDC__ *,int,int,char const *,void *)

- ea: `0x180061640`
- end: `0x180061d2a`
- name: `?EscapeImpl@@YAHPEAUHDC__@@HHPEBDPEAX@Z`
- size: `1770`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int@<edx>, int@<r8d>, const char *@<r9>, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180061640`
- `0x180061d30`
- `0x180063e50`
- `0x18007e0f0`
- `0x180098fd0`
- `0x180099790`
- `0x180099a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800618fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800618fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061cec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061cec`
- `GDI32!EndDoc` at `0x180061ade`
- `GDI32!EndDoc` at `0x180061ade`
- `GDI32!EndPage` at `0x1800617d2`
- `GDI32!EndPage` at `0x18006186c`
- `GDI32!EndPage` at `0x1800617d2`
- `GDI32!EndPage` at `0x18006186c`
- `GDI32!GetDeviceCaps` at `0x18006180d`
- `GDI32!GetDeviceCaps` at `0x180061824`
- `GDI32!GetDeviceCaps` at `0x180061980`
- `GDI32!GetDeviceCaps` at `0x180061996`
- `GDI32!GetDeviceCaps` at `0x1800619bb`
- `GDI32!GetDeviceCaps` at `0x1800619df`
- `GDI32!GetDeviceCaps` at `0x18006180d`
- `GDI32!GetDeviceCaps` at `0x180061824`
- `GDI32!GetDeviceCaps` at `0x180061980`
- `GDI32!GetDeviceCaps` at `0x180061996`
- `GDI32!GetDeviceCaps` at `0x1800619bb`
- `GDI32!GetDeviceCaps` at `0x1800619df`
- `GDI32!StartPage` at `0x1800617c3`
- `GDI32!StartPage` at `0x18006185d`
- `GDI32!StartPage` at `0x1800617c3`
- `GDI32!StartPage` at `0x18006185d`
- `GDI32!AbortDoc` at `0x18006183f`
- `GDI32!AbortDoc` at `0x18006183f`
- `GDI32!ExtEscape` at `0x1800618d5`
- `GDI32!ExtEscape` at `0x18006195e`
- `GDI32!ExtEscape` at `0x1800618d5`
- `GDI32!ExtEscape` at `0x18006195e`
- `GDI32!pldcGet` at `0x1800616ca`
- `GDI32!pldcGet` at `0x1800616ca`
- `GDI32!GdiSetLastError` at `0x180061af4`
- `GDI32!GdiSetLastError` at `0x180061af4`
- `USER32!GetAppCompatFlags` at `0x180061776`
- `USER32!GetAppCompatFlags` at `0x180061776`

## pseudocode

```c
int __fastcall EscapeImpl(HDC hdc, int a2, unsigned int a3, char *a4, struct tagPALETTEENTRY *a5)
{
  unsigned int v9; // r13d
  int result; // eax
  struct tagPALETTEENTRY *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // r15
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // eax
  bool v19; // sf
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  DWORD LastError; // eax
  DWORD v25; // edx
  int v26; // edx
  int v27; // r8d
  int DeviceCaps; // eax
  int v29; // edx
  int v30; // ecx
  const CHAR *v31; // r9
  int v32; // r8d
  int v33; // edx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  bool v37; // zf
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  bool v44; // zf
  bool v45; // zf
  unsigned int v46; // edx
  int cjOutput; // [rsp+20h] [rbp-48h]
  CHAR *lpOutData; // [rsp+28h] [rbp-40h]
  DOCINFOA v49; // [rsp+30h] [rbp-38h] BYREF
  int v50; // [rsp+B0h] [rbp+48h] BYREF

  *(_QWORD *)&v49.cbSize = 0;
  *(&v49.fwType + 1) = 0;
  v50 = 0;
  v9 = (unsigned int)hdc & 0x7F0000;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x660000 )
    return MF16_Escape();
  if ( a2 == 5 )
  {
    if ( !a4 )
      goto LABEL_156;
    result = GetSystemPaletteEntries(hdc, *(__int16 *)a4, 1u, a5);
    if ( !result )
      return -1;
    return result;
  }
  if ( a2 == 8 )
  {
    if ( !a4 )
      goto LABEL_156;
    v38 = *(unsigned __int16 *)a4;
    v32 = 4;
    if ( v38 == 25 )
      goto LABEL_154;
    if ( v38 > 0x19 )
    {
      if ( v38 > 0x1002 )
      {
        switch ( v38 )
        {
          case 0x100Eu:
          case 0x100Fu:
          case 0x1010u:
            return v9 != 0x10000;
          case 0x1013u:
            goto LABEL_154;
          case 0x1014u:
            v50 = 4116;
            v31 = (const CHAR *)&v50;
            v33 = 8;
            return DrawEscape(hdc, v33, v32, v31);
        }
        v46 = v38 - 4117;
        v45 = v38 == 4117;
      }
      else
      {
        switch ( v38 )
        {
          case 0x1002u:
          case 0x25u:
          case 0x26u:
          case 0x2Au:
            goto LABEL_154;
          case 0x100u:
            return 1;
          case 0x202u:
            goto LABEL_154;
          case 0xC01u:
            return 1;
        }
        v46 = v38 - 4096;
        v45 = v38 == 4096;
      }
      if ( !v45 && v46 != 1 )
        return 0;
    }
    else
    {
      if ( v38 <= 0xA )
      {
        if ( v38 == 10 )
          return v9 != 0x10000;
        v39 = v38 - 1;
        if ( !v39 )
          return v9 != 0x10000;
        v40 = v39 - 1;
        if ( !v40 )
          return v9 != 0x10000;
        v41 = v40 - 1;
        if ( !v41 )
          return v9 != 0x10000;
        v42 = v41 - 2;
        if ( !v42 )
          return v9 != 0x10000;
        v43 = v42 - 3;
        if ( !v43 )
          return v9 != 0x10000;
        v44 = v43 == 1;
LABEL_133:
        if ( v44 )
          return v9 != 0x10000;
        return 0;
      }
      if ( v38 == 11 || v38 == 12 || v38 == 13 || v38 == 14 )
        return v9 != 0x10000;
      if ( v38 != 17 )
      {
        v44 = v38 == 19;
        goto LABEL_133;
      }
    }
LABEL_154:
    v50 = *(unsigned __int16 *)a4;
    return ExtEscape(hdc, 8, 4, (LPCSTR)&v50, 0, 0);
  }
  v11 = a5;
  if ( a2 == 256 )
    return GetETM(hdc) != 0;
  if ( a2 == 3073 )
  {
    if ( a5 && a3 >= 0x28 )
    {
      *a5 = 0;
      if ( !a4 )
        goto LABEL_156;
      v34 = *((_DWORD *)a4 + 4);
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( !v35 )
        {
          v37 = *((_WORD *)a4 + 7) == 8;
          goto LABEL_103;
        }
        v36 = v35 - 1;
        if ( v36 )
        {
          if ( v36 != 1 )
            return 1;
          if ( *((_WORD *)a4 + 7) == 16 )
          {
LABEL_113:
            *v11 = (struct tagPALETTEENTRY)15;
            return 1;
          }
          v37 = *((_WORD *)a4 + 7) == 32;
LABEL_103:
          if ( !v37 )
            return 1;
          goto LABEL_113;
        }
      }
      else if ( *((_WORD *)a4 + 7) == 1
             || *((_WORD *)a4 + 7) == 4
             || *((_WORD *)a4 + 7) == 8
             || *((_WORD *)a4 + 7) == 16
             || *((_WORD *)a4 + 7) == 24
             || *((_WORD *)a4 + 7) == 32 )
      {
        *v11 = (struct tagPALETTEENTRY)15;
      }
      if ( *((_WORD *)a4 + 7) != 4 )
        return 1;
      goto LABEL_113;
    }
    return GetETM(hdc) != 0;
  }
  if ( v9 != 0x10000 )
  {
    v12 = pldcGet(hdc);
    v13 = v12;
    if ( !v12 || v9 == 6684672 )
    {
      GdiSetLastError(6);
      return 0;
    }
    if ( a2 <= 25 )
    {
      if ( a2 != 25 )
      {
        if ( a2 <= 11 )
        {
          if ( a2 != 11 )
          {
            v14 = a2 - 1;
            if ( !v14 )
            {
              if ( (*(_DWORD *)(v12 + 8) & 0x100) != 0 )
                StartPage(hdc);
              result = EndPage(hdc);
              v19 = result < 0;
              if ( result > 0 )
              {
                *(_DWORD *)(v13 + 8) |= 0x100u;
                return result;
              }
              goto LABEL_48;
            }
            v15 = v14 - 1;
            if ( !v15 )
              return AbortDoc(hdc);
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 6;
              if ( !v17 )
                return SetAbortProc(hdc, (ABORTPROC)a4);
              if ( v17 == 1 )
              {
                v49.lpszDocName = a4;
                memset(&v49.lpszOutput, 0, 20);
                result = StartDocA(hdc, &v49);
LABEL_47:
                v19 = result < 0;
LABEL_48:
                if ( v19 )
                {
                  if ( (*(_DWORD *)(v13 + 8) & 0x10000) != 0 )
                  {
                    return -2;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v25 = LastError;
                    if ( LastError == 8 )
                    {
                      return -5;
                    }
                    else if ( LastError == 63 )
                    {
                      return -3;
                    }
                    else
                    {
                      result = -4;
                      if ( v25 != 112 )
                        return -1;
                    }
                  }
                }
                return result;
              }
              return 0;
            }
            if ( (*(_DWORD *)(v12 + 8) & 0x200) != 0 )
            {
              if ( (GetAppCompatFlags(0) & 0x22) == 0 )
                goto LABEL_25;
              v18 = *(_DWORD *)(v13 + 8);
              if ( (v18 & 0x400) != 0 )
              {
                *(_DWORD *)(v13 + 8) = v18 & 0xFFFFFBFF;
LABEL_25:
                if ( v11 )
                {
                  *(_QWORD *)&v11[2].peRed = 0;
                  *(_QWORD *)&v11->peRed = 0;
                }
                *(_DWORD *)(v13 + 8) &= ~0x200u;
                if ( (*(_DWORD *)(v13 + 8) & 0x100) != 0 )
                  StartPage(hdc);
                result = EndPage(hdc);
                v19 = result < 0;
                if ( result > 0 )
                {
                  *(_DWORD *)(v13 + 8) |= 0x10000100u;
                  return result;
                }
                goto LABEL_48;
              }
              *(_DWORD *)(v13 + 8) = v18 | 0x400;
            }
            if ( v11 )
            {
              *(_QWORD *)&v11->peRed = 0;
              v11[2] = (struct tagPALETTEENTRY)GetDeviceCaps(hdc, 8);
              v11[3] = (struct tagPALETTEENTRY)GetDeviceCaps(hdc, 10);
            }
            *(_DWORD *)(v13 + 8) |= 0x200u;
            return 1;
          }
          return EndDoc(hdc);
        }
        v20 = a2 - 12;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 3;
              if ( v23 )
              {
                if ( v23 != 2 )
                  return 0;
                if ( a4 )
                {
                  result = ExtEscape(hdc, 19, *(unsigned __int16 *)a4 + 2, a4, 0, 0);
                  goto LABEL_47;
                }
LABEL_156:
                SetLastError(0x57u);
                return -1;
              }
              lpOutData = (CHAR *)v11;
              v26 = 17;
              cjOutput = v11 != 0 ? 4 : 0;
              goto LABEL_59;
            }
            if ( !v11 )
              return 1;
            DeviceCaps = GetDeviceCaps(hdc, 114);
            v29 = 115;
          }
          else
          {
            if ( !v11 )
              return 1;
            DeviceCaps = GetDeviceCaps(hdc, 112);
            v29 = 113;
          }
        }
        else
        {
          if ( !v11 )
            return 1;
          DeviceCaps = GetDeviceCaps(hdc, 110);
          v29 = 111;
        }
        *v11 = (struct tagPALETTEENTRY)DeviceCaps;
        v11[1] = (struct tagPALETTEENTRY)GetDeviceCaps(hdc, v29);
        return 1;
      }
      goto LABEL_75;
    }
    if ( a2 <= 4110 )
    {
      switch ( a2 )
      {
        case 4110:
          v49.fwType = 0;
          v49.lpszDatatype = "RAW";
          *(_OWORD *)&v49.lpszDocName = 0;
          return StartDocA(hdc, &v49);
        case 37:
        case 38:
          goto LABEL_75;
        case 42:
          lpOutData = (CHAR *)v11;
          v26 = 42;
          cjOutput = 16;
          goto LABEL_59;
      }
      if ( a2 == 514 || (v30 = a2 - 4096, a2 == 4096) )
      {
LABEL_75:
        lpOutData = 0;
        cjOutput = 0;
        v26 = (unsigned __int16)a2;
LABEL_59:
        v27 = a3;
        return ExtEscape(hdc, v26, v27, a4, cjOutput, lpOutData);
      }
LABEL_82:
      if ( (unsigned int)(v30 - 1) >= 2 )
        return 0;
      goto LABEL_75;
    }
    switch ( a2 )
    {
      case 4111:
        return 1;
      case 4112:
        return EndDoc(hdc);
      case 4115:
        if ( !a4 )
          goto LABEL_156;
        v26 = 4115;
        lpOutData = 0;
        v27 = *(unsigned __int16 *)a4 + 2;
        cjOutput = 0;
        return ExtEscape(hdc, v26, v27, a4, cjOutput, lpOutData);
    }
    v30 = a2 - 4116;
    if ( a2 != 4116 )
      goto LABEL_82;
    v31 = a4;
    v32 = a3;
    v33 = 4116;
    return DrawEscape(hdc, v33, v32, v31);
  }
  result = 0;
  if ( a2 == 14 && a5 )
    *(_QWORD *)&a5->peRed = 0;
  return result;
}

```

## disassembly

```asm
0x180061640  push    rbp
0x180061642  push    rbx
0x180061643  push    rsi
0x180061644  push    rdi
0x180061645  push    r12
0x180061647  push    r13
0x180061649  push    r14
0x18006164b  push    r15
0x18006164d  mov     rbp, rsp
0x180061650  sub     rsp, 68h
0x180061654  xor     r15d, r15d
0x180061657  mov     eax, ecx
0x180061659  and     eax, 7F0000h
0x18006165e  mov     qword ptr [rbp+var_38.cbSize], r15
0x180061662  mov     dword ptr [rbp+var_38+24h], r15d
0x180061666  mov     rsi, r9
0x180061669  mov     [rbp+arg_0], r15d
0x18006166d  mov     r12d, r8d
0x180061670  mov     ebx, edx
0x180061672  mov     r14, rcx
0x180061675  mov     r13d, eax
0x180061678  cmp     eax, 660000h
0x18006167d  jnz     short loc_180061689
0x18006167f  call    MF16_Escape
0x180061684  jmp     loc_180061D18
0x180061689  cmp     ebx, 5
0x18006168c  jz      loc_180061CE2
0x180061692  mov     r10d, 8
0x180061698  cmp     ebx, r10d
0x18006169b  jz      loc_180061BCB
0x1800616a1  mov     rdi, [rbp+arg_20]
0x1800616a5  cmp     ebx, 100h
0x1800616ab  jz      loc_180061BB4
0x1800616b1  cmp     ebx, 0C01h
0x1800616b7  jz      loc_180061B26
0x1800616bd  cmp     r13d, 10000h
0x1800616c4  jz      loc_180061B07
0x1800616ca  call    cs:__imp_pldcGet
0x1800616d1  nop     dword ptr [rax+rax+00h]
0x1800616d6  xor     r9d, r9d
0x1800616d9  mov     r15, rax
0x1800616dc  test    rax, rax
0x1800616df  jz      loc_180061AEF
0x1800616e5  cmp     r13d, 660000h
0x1800616ec  jz      loc_180061AEF
0x1800616f2  cmp     ebx, 19h
0x1800616f5  jg      loc_1800619F2
0x1800616fb  jz      loc_180061A1E
0x180061701  cmp     ebx, 0Bh
0x180061704  jg      loc_180061885
0x18006170a  jz      loc_180061ADB
0x180061710  sub     ebx, 1
0x180061713  jz      loc_180061850
0x180061719  sub     ebx, 1
0x18006171c  jz      loc_18006183C
0x180061722  sub     ebx, 1
0x180061725  jz      short loc_180061766
0x180061727  sub     ebx, 6
0x18006172a  jz      short loc_180061756
0x18006172c  cmp     ebx, 1
0x18006172f  jnz     loc_180061A96
0x180061735  xorps   xmm0, xmm0
0x180061738  mov     [rbp+var_38.lpszDocName], rsi
0x18006173c  lea     rdx, [rbp+var_38]; lpdi
0x180061740  mov     [rbp+var_38.fwType], r9d
0x180061744  mov     rcx, r14; hdc
0x180061747  movdqu  xmmword ptr [rbp+var_38.lpszOutput], xmm0
0x18006174c  call    StartDocA
0x180061751  jmp     loc_1800618E1
0x180061756  mov     rdx, rsi; proc
0x180061759  mov     rcx, r14; hdc
0x18006175c  call    SetAbortProc
0x180061761  jmp     loc_180061D18
0x180061766  mov     ebx, 200h
0x18006176b  test    [rax+8], ebx
0x18006176e  jz      loc_1800617F9
0x180061774  xor     ecx, ecx
0x180061776  call    cs:__imp_GetAppCompatFlags
0x18006177d  nop     dword ptr [rax+rax+00h]
0x180061782  test    al, 22h
0x180061784  jz      short loc_18006179B
0x180061786  mov     eax, [r15+8]
0x18006178a  mov     ecx, 400h
0x18006178f  test    ecx, eax
0x180061791  jz      short loc_1800617F3
0x180061793  btr     eax, 0Ah
0x180061797  mov     [r15+8], eax
0x18006179b  test    rdi, rdi
0x18006179e  jz      short loc_1800617AF
0x1800617a0  mov     qword ptr [rdi+8], 0
0x1800617a8  mov     qword ptr [rdi], 0
0x1800617af  btr     dword ptr [r15+8], 9
0x1800617b5  mov     ebx, 100h
0x1800617ba  test    [r15+8], ebx
0x1800617be  jz      short loc_1800617CF
0x1800617c0  mov     rcx, r14; hdc
0x1800617c3  call    cs:__imp_StartPage
0x1800617ca  nop     dword ptr [rax+rax+00h]
0x1800617cf  mov     rcx, r14; hdc
0x1800617d2  call    cs:__imp_EndPage
0x1800617d9  nop     dword ptr [rax+rax+00h]
0x1800617de  test    eax, eax
0x1800617e0  jle     loc_1800618E3
0x1800617e6  or      dword ptr [r15+8], 10000100h
0x1800617ee  jmp     loc_180061D18
0x1800617f3  or      eax, ecx
0x1800617f5  mov     [r15+8], eax
0x1800617f9  test    rdi, rdi
0x1800617fc  jz      short loc_180061833
0x1800617fe  mov     edx, 8; index
0x180061803  mov     qword ptr [rdi], 0
0x18006180a  mov     rcx, r14; hdc
0x18006180d  call    cs:__imp_GetDeviceCaps
0x180061814  nop     dword ptr [rax+rax+00h]
0x180061819  mov     edx, 0Ah; index
0x18006181e  mov     rcx, r14; hdc
0x180061821  mov     [rdi+8], eax
0x180061824  call    cs:__imp_GetDeviceCaps
0x18006182b  nop     dword ptr [rax+rax+00h]
0x180061830  mov     [rdi+0Ch], eax
0x180061833  or      [r15+8], ebx
0x180061837  jmp     loc_180061BAA
0x18006183c  mov     rcx, r14; hdc
0x18006183f  call    cs:__imp_AbortDoc
0x180061846  nop     dword ptr [rax+rax+00h]
0x18006184b  jmp     loc_180061D18
0x180061850  mov     ebx, 100h
0x180061855  test    [rax+8], ebx
0x180061858  jz      short loc_180061869
0x18006185a  mov     rcx, r14; hdc
0x18006185d  call    cs:__imp_StartPage
0x180061864  nop     dword ptr [rax+rax+00h]
0x180061869  mov     rcx, r14; hdc
0x18006186c  call    cs:__imp_EndPage
0x180061873  nop     dword ptr [rax+rax+00h]
0x180061878  test    eax, eax
0x18006187a  jle     short loc_1800618E3
0x18006187c  or      [r15+8], ebx
0x180061880  jmp     loc_180061D18
0x180061885  sub     ebx, 0Ch
0x180061888  jz      loc_1800619CE
0x18006188e  sub     ebx, 1
0x180061891  jz      loc_1800619AA
0x180061897  sub     ebx, 1
0x18006189a  jz      loc_18006196F
0x1800618a0  sub     ebx, 3
0x1800618a3  jz      loc_18006193C
0x1800618a9  cmp     ebx, 2
0x1800618ac  jnz     loc_180061A96
0x1800618b2  test    rsi, rsi
0x1800618b5  jz      loc_180061CE7
0x1800618bb  movzx   r8d, word ptr [rsi]
0x1800618bf  lea     edx, [rbx+11h]; iEscape
0x1800618c2  mov     [rsp+68h+lpOutData], r9; lpOutData
0x1800618c7  add     r8d, ebx; cjInput
0x1800618ca  mov     [rsp+68h+cjOutput], r9d; cjOutput
0x1800618cf  mov     rcx, r14; hdc
0x1800618d2  mov     r9, rsi; lpInData
0x1800618d5  call    cs:__imp_ExtEscape
0x1800618dc  nop     dword ptr [rax+rax+00h]
0x1800618e1  test    eax, eax
0x1800618e3  jns     loc_180061D18
0x1800618e9  test    dword ptr [r15+8], 10000h
0x1800618f1  jz      short loc_1800618FD
0x1800618f3  mov     eax, 0FFFFFFFEh
0x1800618f8  jmp     loc_180061D18
0x1800618fd  call    cs:__imp_GetLastError
0x180061904  nop     dword ptr [rax+rax+00h]
0x180061909  mov     edx, eax
0x18006190b  cmp     eax, 8
0x18006190e  jz      short loc_180061932
0x180061910  cmp     eax, 3Fh ; '?'
0x180061913  jz      short loc_180061928
0x180061915  or      ecx, 0FFFFFFFFh
0x180061918  mov     eax, 0FFFFFFFCh
0x18006191d  cmp     edx, 70h ; 'p'
0x180061920  cmovnz  eax, ecx
0x180061923  jmp     loc_180061D18
0x180061928  mov     eax, 0FFFFFFFDh
0x18006192d  jmp     loc_180061D18
0x180061932  mov     eax, 0FFFFFFFBh
0x180061937  jmp     loc_180061D18
0x18006193c  mov     rax, rdi
0x18006193f  mov     [rsp+68h+lpOutData], rdi; lpOutData
0x180061944  neg     rax
0x180061947  mov     edx, 11h; iEscape
0x18006194c  sbb     ecx, ecx
0x18006194e  and     ecx, 4
0x180061951  mov     [rsp+68h+cjOutput], ecx; cjOutput
0x180061955  mov     r8d, r12d; cjInput
0x180061958  mov     r9, rsi; lpInData
0x18006195b  mov     rcx, r14; hdc
0x18006195e  call    cs:__imp_ExtEscape
0x180061965  nop     dword ptr [rax+rax+00h]
0x18006196a  jmp     loc_180061D18
0x18006196f  test    rdi, rdi
0x180061972  jz      loc_180061BAA
0x180061978  mov     edx, 72h ; 'r'; index
0x18006197d  mov     rcx, r14; hdc
0x180061980  call    cs:__imp_GetDeviceCaps
0x180061987  nop     dword ptr [rax+rax+00h]
0x18006198c  mov     edx, 73h ; 's'; index
0x180061991  mov     rcx, r14; hdc
0x180061994  mov     [rdi], eax
0x180061996  call    cs:__imp_GetDeviceCaps
0x18006199d  nop     dword ptr [rax+rax+00h]
0x1800619a2  mov     [rdi+4], eax
0x1800619a5  jmp     loc_180061BAA
0x1800619aa  test    rdi, rdi
0x1800619ad  jz      loc_180061BAA
0x1800619b3  mov     edx, 70h ; 'p'; index
0x1800619b8  mov     rcx, r14; hdc
0x1800619bb  call    cs:__imp_GetDeviceCaps
0x1800619c2  nop     dword ptr [rax+rax+00h]
0x1800619c7  mov     edx, 71h ; 'q'
0x1800619cc  jmp     short loc_180061991
0x1800619ce  test    rdi, rdi
0x1800619d1  jz      loc_180061BAA
0x1800619d7  mov     edx, 6Eh ; 'n'; index
0x1800619dc  mov     rcx, r14; hdc
0x1800619df  call    cs:__imp_GetDeviceCaps
0x1800619e6  nop     dword ptr [rax+rax+00h]
0x1800619eb  mov     edx, 6Fh ; 'o'
0x1800619f0  jmp     short loc_180061991
0x1800619f2  mov     eax, 100Eh
0x1800619f7  cmp     ebx, eax
0x1800619f9  jg      short loc_180061A6F
0x1800619fb  jz      short loc_180061A47
0x1800619fd  mov     ecx, ebx
0x1800619ff  sub     ecx, 25h ; '%'
0x180061a02  jz      short loc_180061A1E
0x180061a04  sub     ecx, 1
0x180061a07  jz      short loc_180061A1E
0x180061a09  sub     ecx, 4
0x180061a0c  jz      short loc_180061A30
0x180061a0e  sub     ecx, 1D8h
0x180061a14  jz      short loc_180061A1E
0x180061a16  sub     ecx, 0DFEh
0x180061a1c  jnz     short loc_180061A8C
0x180061a1e  mov     [rsp+68h+lpOutData], r9
0x180061a23  mov     [rsp+68h+cjOutput], r9d
0x180061a28  movzx   edx, bx
0x180061a2b  jmp     loc_180061955
0x180061a30  mov     [rsp+68h+lpOutData], rdi
0x180061a35  mov     edx, 2Ah ; '*'
0x180061a3a  mov     [rsp+68h+cjOutput], 10h
0x180061a42  jmp     loc_180061955
0x180061a47  xorps   xmm0, xmm0
0x180061a4a  mov     [rbp+var_38.fwType], r9d
0x180061a4e  lea     rax, aRaw; "RAW"
0x180061a55  mov     rcx, r14; hdc
0x180061a58  lea     rdx, [rbp+var_38]; lpdi
0x180061a5c  mov     [rbp+var_38.lpszDatatype], rax
0x180061a60  movdqu  xmmword ptr [rbp+var_38.lpszDocName], xmm0
0x180061a65  call    StartDocA
0x180061a6a  jmp     loc_180061D18
0x180061a6f  mov     ecx, ebx
0x180061a71  sub     ecx, 100Fh
0x180061a77  jz      loc_180061BAA
0x180061a7d  sub     ecx, 1
0x180061a80  jz      short loc_180061ADB
0x180061a82  sub     ecx, 3
0x180061a85  jz      short loc_180061AB6
0x180061a87  sub     ecx, 1
0x180061a8a  jz      short loc_180061A9E
0x180061a8c  sub     ecx, 1
0x180061a8f  jz      short loc_180061A1E
0x180061a91  cmp     ecx, 1
0x180061a94  jz      short loc_180061A1E
0x180061a96  mov     eax, r9d
0x180061a99  jmp     loc_180061D18
0x180061a9e  mov     r9, rsi; lpIn
0x180061aa1  mov     r8d, r12d; cjIn
0x180061aa4  mov     edx, 1014h; iEscape
0x180061aa9  mov     rcx, r14; hdc
0x180061aac  call    DrawEscape
0x180061ab1  jmp     loc_180061D18
0x180061ab6  test    rsi, rsi
0x180061ab9  jz      loc_180061CE7
0x180061abf  movzx   r8d, word ptr [rsi]
0x180061ac3  mov     edx, 1013h
0x180061ac8  mov     [rsp+68h+lpOutData], r9
0x180061acd  add     r8d, 2
0x180061ad1  mov     [rsp+68h+cjOutput], r9d
0x180061ad6  jmp     loc_180061958
0x180061adb  mov     rcx, r14; hdc
0x180061ade  call    cs:__imp_EndDoc
0x180061ae5  nop     dword ptr [rax+rax+00h]
0x180061aea  jmp     loc_180061D18
0x180061aef  mov     ecx, 6
0x180061af4  call    cs:__imp_GdiSetLastError
0x180061afb  nop     dword ptr [rax+rax+00h]
0x180061b00  xor     eax, eax
0x180061b02  jmp     loc_180061D18
0x180061b07  mov     eax, r15d
0x180061b0a  cmp     ebx, 0Eh
0x180061b0d  jnz     loc_180061D18
0x180061b13  test    rdi, rdi
0x180061b16  jz      loc_180061D18
0x180061b1c  xor     ecx, ecx
  ... truncated ...
```
