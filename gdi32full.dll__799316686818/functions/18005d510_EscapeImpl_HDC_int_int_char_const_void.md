# EscapeImpl(HDC__ *,int,int,char const *,void *)

- ea: `0x18005d510`
- end: `0x18005db83`
- name: `?EscapeImpl@@YAHPEAUHDC__@@HHPEBDPEAX@Z`
- size: `1651`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int@<edx>, int@<r8d>, const char *@<r9>, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18005d510`
- `0x18005db8c`
- `0x18005f7e0`
- `0x180079540`
- `0x180093320`
- `0x180093a70`
- `0x180093ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d78d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d78d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005db4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005db4c`
- `GDI32!EndDoc` at `0x18005d94a`
- `GDI32!EndDoc` at `0x18005d94a`
- `GDI32!EndPage` at `0x18005d68c`
- `GDI32!EndPage` at `0x18005d708`
- `GDI32!EndPage` at `0x18005d68c`
- `GDI32!EndPage` at `0x18005d708`
- `GDI32!GetDeviceCaps` at `0x18005d6c1`
- `GDI32!GetDeviceCaps` at `0x18005d6d2`
- `GDI32!GetDeviceCaps` at `0x18005d804`
- `GDI32!GetDeviceCaps` at `0x18005d814`
- `GDI32!GetDeviceCaps` at `0x18005d833`
- `GDI32!GetDeviceCaps` at `0x18005d851`
- `GDI32!GetDeviceCaps` at `0x18005d6c1`
- `GDI32!GetDeviceCaps` at `0x18005d6d2`
- `GDI32!GetDeviceCaps` at `0x18005d804`
- `GDI32!GetDeviceCaps` at `0x18005d814`
- `GDI32!GetDeviceCaps` at `0x18005d833`
- `GDI32!GetDeviceCaps` at `0x18005d851`
- `GDI32!StartPage` at `0x18005d683`
- `GDI32!StartPage` at `0x18005d6ff`
- `GDI32!StartPage` at `0x18005d683`
- `GDI32!StartPage` at `0x18005d6ff`
- `GDI32!AbortDoc` at `0x18005d6e7`
- `GDI32!AbortDoc` at `0x18005d6e7`
- `GDI32!ExtEscape` at `0x18005d76b`
- `GDI32!ExtEscape` at `0x18005d7e8`
- `GDI32!ExtEscape` at `0x18005d76b`
- `GDI32!ExtEscape` at `0x18005d7e8`
- `GDI32!pldcGet` at `0x18005d59a`
- `GDI32!pldcGet` at `0x18005d59a`
- `GDI32!GdiSetLastError` at `0x18005d95a`
- `GDI32!GdiSetLastError` at `0x18005d95a`
- `USER32!GetAppCompatFlags` at `0x18005d63c`
- `USER32!GetAppCompatFlags` at `0x18005d63c`

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
0x18005d510  push    rbp
0x18005d512  push    rbx
0x18005d513  push    rsi
0x18005d514  push    rdi
0x18005d515  push    r12
0x18005d517  push    r13
0x18005d519  push    r14
0x18005d51b  push    r15
0x18005d51d  mov     rbp, rsp
0x18005d520  sub     rsp, 68h
0x18005d524  xor     r15d, r15d
0x18005d527  mov     eax, ecx
0x18005d529  and     eax, 7F0000h
0x18005d52e  mov     qword ptr [rbp+var_38.cbSize], r15
0x18005d532  mov     dword ptr [rbp+var_38+24h], r15d
0x18005d536  mov     rsi, r9
0x18005d539  mov     [rbp+arg_0], r15d
0x18005d53d  mov     r12d, r8d
0x18005d540  mov     ebx, edx
0x18005d542  mov     r14, rcx
0x18005d545  mov     r13d, eax
0x18005d548  cmp     eax, 660000h
0x18005d54d  jnz     short loc_18005D559
0x18005d54f  call    MF16_Escape
0x18005d554  jmp     loc_18005DB72
0x18005d559  cmp     ebx, 5
0x18005d55c  jz      loc_18005DB42
0x18005d562  mov     r10d, 8
0x18005d568  cmp     ebx, r10d
0x18005d56b  jz      loc_18005DA2B
0x18005d571  mov     rdi, [rbp+arg_20]
0x18005d575  cmp     ebx, 100h
0x18005d57b  jz      loc_18005DA14
0x18005d581  cmp     ebx, 0C01h
0x18005d587  jz      loc_18005D986
0x18005d58d  cmp     r13d, 10000h
0x18005d594  jz      loc_18005D967
0x18005d59a  call    cs:__imp_pldcGet
0x18005d5a0  xor     r9d, r9d
0x18005d5a3  mov     r15, rax
0x18005d5a6  test    rax, rax
0x18005d5a9  jz      loc_18005D955
0x18005d5af  cmp     r13d, 660000h
0x18005d5b6  jz      loc_18005D955
0x18005d5bc  cmp     ebx, 19h
0x18005d5bf  jg      loc_18005D85E
0x18005d5c5  jz      loc_18005D88A
0x18005d5cb  cmp     ebx, 0Bh
0x18005d5ce  jg      loc_18005D71B
0x18005d5d4  jz      loc_18005D947
0x18005d5da  sub     ebx, 1
0x18005d5dd  jz      loc_18005D6F2
0x18005d5e3  sub     ebx, 1
0x18005d5e6  jz      loc_18005D6E4
0x18005d5ec  sub     ebx, 1
0x18005d5ef  jz      short loc_18005D630
0x18005d5f1  sub     ebx, 6
0x18005d5f4  jz      short loc_18005D620
0x18005d5f6  cmp     ebx, 1
0x18005d5f9  jnz     loc_18005D902
0x18005d5ff  xorps   xmm0, xmm0
0x18005d602  mov     [rbp+var_38.lpszDocName], rsi
0x18005d606  lea     rdx, [rbp+var_38]; lpdi
0x18005d60a  mov     [rbp+var_38.fwType], r9d
0x18005d60e  mov     rcx, r14; hdc
0x18005d611  movdqu  xmmword ptr [rbp+var_38.lpszOutput], xmm0
0x18005d616  call    StartDocA
0x18005d61b  jmp     loc_18005D771
0x18005d620  mov     rdx, rsi; proc
0x18005d623  mov     rcx, r14; hdc
0x18005d626  call    SetAbortProc
0x18005d62b  jmp     loc_18005DB72
0x18005d630  mov     ebx, 200h
0x18005d635  test    [rax+8], ebx
0x18005d638  jz      short loc_18005D6AD
0x18005d63a  xor     ecx, ecx
0x18005d63c  call    cs:__imp_GetAppCompatFlags
0x18005d642  test    al, 22h
0x18005d644  jz      short loc_18005D65B
0x18005d646  mov     eax, [r15+8]
0x18005d64a  mov     ecx, 400h
0x18005d64f  test    ecx, eax
0x18005d651  jz      short loc_18005D6A7
0x18005d653  btr     eax, 0Ah
0x18005d657  mov     [r15+8], eax
0x18005d65b  test    rdi, rdi
0x18005d65e  jz      short loc_18005D66F
0x18005d660  mov     qword ptr [rdi+8], 0
0x18005d668  mov     qword ptr [rdi], 0
0x18005d66f  btr     dword ptr [r15+8], 9
0x18005d675  mov     ebx, 100h
0x18005d67a  test    [r15+8], ebx
0x18005d67e  jz      short loc_18005D689
0x18005d680  mov     rcx, r14; hdc
0x18005d683  call    cs:__imp_StartPage
0x18005d689  mov     rcx, r14; hdc
0x18005d68c  call    cs:__imp_EndPage
0x18005d692  test    eax, eax
0x18005d694  jle     loc_18005D773
0x18005d69a  or      dword ptr [r15+8], 10000100h
0x18005d6a2  jmp     loc_18005DB72
0x18005d6a7  or      eax, ecx
0x18005d6a9  mov     [r15+8], eax
0x18005d6ad  test    rdi, rdi
0x18005d6b0  jz      short loc_18005D6DB
0x18005d6b2  mov     edx, 8; index
0x18005d6b7  mov     qword ptr [rdi], 0
0x18005d6be  mov     rcx, r14; hdc
0x18005d6c1  call    cs:__imp_GetDeviceCaps
0x18005d6c7  mov     edx, 0Ah; index
0x18005d6cc  mov     rcx, r14; hdc
0x18005d6cf  mov     [rdi+8], eax
0x18005d6d2  call    cs:__imp_GetDeviceCaps
0x18005d6d8  mov     [rdi+0Ch], eax
0x18005d6db  or      [r15+8], ebx
0x18005d6df  jmp     loc_18005DA0A
0x18005d6e4  mov     rcx, r14; hdc
0x18005d6e7  call    cs:__imp_AbortDoc
0x18005d6ed  jmp     loc_18005DB72
0x18005d6f2  mov     ebx, 100h
0x18005d6f7  test    [rax+8], ebx
0x18005d6fa  jz      short loc_18005D705
0x18005d6fc  mov     rcx, r14; hdc
0x18005d6ff  call    cs:__imp_StartPage
0x18005d705  mov     rcx, r14; hdc
0x18005d708  call    cs:__imp_EndPage
0x18005d70e  test    eax, eax
0x18005d710  jle     short loc_18005D773
0x18005d712  or      [r15+8], ebx
0x18005d716  jmp     loc_18005DB72
0x18005d71b  sub     ebx, 0Ch
0x18005d71e  jz      loc_18005D840
0x18005d724  sub     ebx, 1
0x18005d727  jz      loc_18005D822
0x18005d72d  sub     ebx, 1
0x18005d730  jz      loc_18005D7F3
0x18005d736  sub     ebx, 3
0x18005d739  jz      loc_18005D7C6
0x18005d73f  cmp     ebx, 2
0x18005d742  jnz     loc_18005D902
0x18005d748  test    rsi, rsi
0x18005d74b  jz      loc_18005DB47
0x18005d751  movzx   r8d, word ptr [rsi]
0x18005d755  lea     edx, [rbx+11h]; iEscape
0x18005d758  mov     [rsp+68h+lpOutData], r9; lpOutData
0x18005d75d  add     r8d, ebx; cjInput
0x18005d760  mov     [rsp+68h+cjOutput], r9d; cjOutput
0x18005d765  mov     rcx, r14; hdc
0x18005d768  mov     r9, rsi; lpInData
0x18005d76b  call    cs:__imp_ExtEscape
0x18005d771  test    eax, eax
0x18005d773  jns     loc_18005DB72
0x18005d779  test    dword ptr [r15+8], 10000h
0x18005d781  jz      short loc_18005D78D
0x18005d783  mov     eax, 0FFFFFFFEh
0x18005d788  jmp     loc_18005DB72
0x18005d78d  call    cs:__imp_GetLastError
0x18005d793  mov     edx, eax
0x18005d795  cmp     eax, 8
0x18005d798  jz      short loc_18005D7BC
0x18005d79a  cmp     eax, 3Fh ; '?'
0x18005d79d  jz      short loc_18005D7B2
0x18005d79f  or      ecx, 0FFFFFFFFh
0x18005d7a2  mov     eax, 0FFFFFFFCh
0x18005d7a7  cmp     edx, 70h ; 'p'
0x18005d7aa  cmovnz  eax, ecx
0x18005d7ad  jmp     loc_18005DB72
0x18005d7b2  mov     eax, 0FFFFFFFDh
0x18005d7b7  jmp     loc_18005DB72
0x18005d7bc  mov     eax, 0FFFFFFFBh
0x18005d7c1  jmp     loc_18005DB72
0x18005d7c6  mov     rax, rdi
0x18005d7c9  mov     [rsp+68h+lpOutData], rdi; lpOutData
0x18005d7ce  neg     rax
0x18005d7d1  mov     edx, 11h; iEscape
0x18005d7d6  sbb     ecx, ecx
0x18005d7d8  and     ecx, 4
0x18005d7db  mov     [rsp+68h+cjOutput], ecx; cjOutput
0x18005d7df  mov     r8d, r12d; cjInput
0x18005d7e2  mov     r9, rsi; lpInData
0x18005d7e5  mov     rcx, r14; hdc
0x18005d7e8  call    cs:__imp_ExtEscape
0x18005d7ee  jmp     loc_18005DB72
0x18005d7f3  test    rdi, rdi
0x18005d7f6  jz      loc_18005DA0A
0x18005d7fc  mov     edx, 72h ; 'r'; index
0x18005d801  mov     rcx, r14; hdc
0x18005d804  call    cs:__imp_GetDeviceCaps
0x18005d80a  mov     edx, 73h ; 's'; index
0x18005d80f  mov     rcx, r14; hdc
0x18005d812  mov     [rdi], eax
0x18005d814  call    cs:__imp_GetDeviceCaps
0x18005d81a  mov     [rdi+4], eax
0x18005d81d  jmp     loc_18005DA0A
0x18005d822  test    rdi, rdi
0x18005d825  jz      loc_18005DA0A
0x18005d82b  mov     edx, 70h ; 'p'; index
0x18005d830  mov     rcx, r14; hdc
0x18005d833  call    cs:__imp_GetDeviceCaps
0x18005d839  mov     edx, 71h ; 'q'
0x18005d83e  jmp     short loc_18005D80F
0x18005d840  test    rdi, rdi
0x18005d843  jz      loc_18005DA0A
0x18005d849  mov     edx, 6Eh ; 'n'; index
0x18005d84e  mov     rcx, r14; hdc
0x18005d851  call    cs:__imp_GetDeviceCaps
0x18005d857  mov     edx, 6Fh ; 'o'
0x18005d85c  jmp     short loc_18005D80F
0x18005d85e  mov     eax, 100Eh
0x18005d863  cmp     ebx, eax
0x18005d865  jg      short loc_18005D8DB
0x18005d867  jz      short loc_18005D8B3
0x18005d869  mov     ecx, ebx
0x18005d86b  sub     ecx, 25h ; '%'
0x18005d86e  jz      short loc_18005D88A
0x18005d870  sub     ecx, 1
0x18005d873  jz      short loc_18005D88A
0x18005d875  sub     ecx, 4
0x18005d878  jz      short loc_18005D89C
0x18005d87a  sub     ecx, 1D8h
0x18005d880  jz      short loc_18005D88A
0x18005d882  sub     ecx, 0DFEh
0x18005d888  jnz     short loc_18005D8F8
0x18005d88a  mov     [rsp+68h+lpOutData], r9
0x18005d88f  mov     [rsp+68h+cjOutput], r9d
0x18005d894  movzx   edx, bx
0x18005d897  jmp     loc_18005D7DF
0x18005d89c  mov     [rsp+68h+lpOutData], rdi
0x18005d8a1  mov     edx, 2Ah ; '*'
0x18005d8a6  mov     [rsp+68h+cjOutput], 10h
0x18005d8ae  jmp     loc_18005D7DF
0x18005d8b3  xorps   xmm0, xmm0
0x18005d8b6  mov     [rbp+var_38.fwType], r9d
0x18005d8ba  lea     rax, aRaw; "RAW"
0x18005d8c1  mov     rcx, r14; hdc
0x18005d8c4  lea     rdx, [rbp+var_38]; lpdi
0x18005d8c8  mov     [rbp+var_38.lpszDatatype], rax
0x18005d8cc  movdqu  xmmword ptr [rbp+var_38.lpszDocName], xmm0
0x18005d8d1  call    StartDocA
0x18005d8d6  jmp     loc_18005DB72
0x18005d8db  mov     ecx, ebx
0x18005d8dd  sub     ecx, 100Fh
0x18005d8e3  jz      loc_18005DA0A
0x18005d8e9  sub     ecx, 1
0x18005d8ec  jz      short loc_18005D947
0x18005d8ee  sub     ecx, 3
0x18005d8f1  jz      short loc_18005D922
0x18005d8f3  sub     ecx, 1
0x18005d8f6  jz      short loc_18005D90A
0x18005d8f8  sub     ecx, 1
0x18005d8fb  jz      short loc_18005D88A
0x18005d8fd  cmp     ecx, 1
0x18005d900  jz      short loc_18005D88A
0x18005d902  mov     eax, r9d
0x18005d905  jmp     loc_18005DB72
0x18005d90a  mov     r9, rsi; lpIn
0x18005d90d  mov     r8d, r12d; cjIn
0x18005d910  mov     edx, 1014h; iEscape
0x18005d915  mov     rcx, r14; hdc
0x18005d918  call    DrawEscape
0x18005d91d  jmp     loc_18005DB72
0x18005d922  test    rsi, rsi
0x18005d925  jz      loc_18005DB47
0x18005d92b  movzx   r8d, word ptr [rsi]
0x18005d92f  mov     edx, 1013h
0x18005d934  mov     [rsp+68h+lpOutData], r9
0x18005d939  add     r8d, 2
0x18005d93d  mov     [rsp+68h+cjOutput], r9d
0x18005d942  jmp     loc_18005D7E2
0x18005d947  mov     rcx, r14; hdc
0x18005d94a  call    cs:__imp_EndDoc
0x18005d950  jmp     loc_18005DB72
0x18005d955  mov     ecx, 6
0x18005d95a  call    cs:__imp_GdiSetLastError
0x18005d960  xor     eax, eax
0x18005d962  jmp     loc_18005DB72
0x18005d967  mov     eax, r15d
0x18005d96a  cmp     ebx, 0Eh
0x18005d96d  jnz     loc_18005DB72
0x18005d973  test    rdi, rdi
0x18005d976  jz      loc_18005DB72
0x18005d97c  xor     ecx, ecx
0x18005d97e  mov     [rdi], rcx
0x18005d981  jmp     loc_18005DB72
0x18005d986  test    rdi, rdi
0x18005d989  jz      loc_18005DA14
0x18005d98f  cmp     r12d, 28h ; '('
0x18005d993  jb      short loc_18005DA14
0x18005d995  mov     [rdi], r15d
0x18005d998  test    rsi, rsi
0x18005d99b  jz      loc_18005DB47
0x18005d9a1  mov     ecx, [r9+10h]
0x18005d9a5  mov     edx, 0Fh
0x18005d9aa  lea     r8d, [rdx-0Bh]
0x18005d9ae  test    ecx, ecx
0x18005d9b0  jz      short loc_18005D9DC
0x18005d9b2  sub     ecx, 1
0x18005d9b5  jz      short loc_18005D9D3
0x18005d9b7  sub     ecx, 1
0x18005d9ba  jz      short loc_18005DA01
  ... truncated ...
```
