# NrptBlobToNrptRuleListVersion2

- ea: `0x18003d738`
- end: `0x18003dd60`
- name: `NrptBlobToNrptRuleListVersion2`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fe94`

## callees

- `0x18003d738`
- `0x180040258`
- `0x18004e580`
- `0x18007f140`
- `0x1800ded06`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003da6c`
- `msvcrt!memcpy_s` at `0x18003dabf`
- `msvcrt!memcpy_s` at `0x18003db04`
- `msvcrt!memcpy_s` at `0x18003da6c`
- `msvcrt!memcpy_s` at `0x18003dabf`
- `msvcrt!memcpy_s` at `0x18003db04`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003d951`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003d951`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003dcc6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003dcc6`
- `rtutils!TracePrintfExA` at `0x18003d835`
- `rtutils!TracePrintfExA` at `0x18003d8a1`
- `rtutils!TracePrintfExA` at `0x18003d8ff`
- `rtutils!TracePrintfExA` at `0x18003d9da`
- `rtutils!TracePrintfExA` at `0x18003db76`
- `rtutils!TracePrintfExA` at `0x18003dbd3`
- `rtutils!TracePrintfExA` at `0x18003dc30`
- `rtutils!TracePrintfExA` at `0x18003dc7e`
- `rtutils!TracePrintfExA` at `0x18003dd0d`
- `rtutils!TracePrintfExA` at `0x18003d835`
- `rtutils!TracePrintfExA` at `0x18003d8a1`
- `rtutils!TracePrintfExA` at `0x18003d8ff`
- `rtutils!TracePrintfExA` at `0x18003d9da`
- `rtutils!TracePrintfExA` at `0x18003db76`
- `rtutils!TracePrintfExA` at `0x18003dbd3`
- `rtutils!TracePrintfExA` at `0x18003dc30`
- `rtutils!TracePrintfExA` at `0x18003dc7e`
- `rtutils!TracePrintfExA` at `0x18003dd0d`

## string_xrefs

- `0x18003d895`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x18003dbc7`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x18003dc24`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 2.`
- `0x18003dc72`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 1.`
- `0x18003db6a`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 4.`

## pseudocode

```c
__int64 __fastcall NrptBlobToNrptRuleListVersion2(_DWORD *a1, unsigned int a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v5; // r15
  __int64 v7; // rsi
  _DWORD *v8; // rbx
  __int64 v9; // rbp
  unsigned int v10; // r14d
  _DWORD *v11; // rdi
  __int64 v12; // r13
  __int64 v13; // r9
  unsigned int v14; // edi
  __int64 v15; // rdx
  size_t v16; // rdi
  char *v17; // rax
  char *v18; // rbp
  char *v19; // r14
  rsize_t v20; // rdi
  char *v21; // r15
  char *v22; // r10
  unsigned int v23; // r8d
  unsigned __int64 v24; // rbx
  char *v25; // r8
  rsize_t v26; // rax
  char *v27; // r8
  SIZE_T v28; // rdx
  rsize_t v29; // rcx
  rsize_t v30; // rdi
  SIZE_T v31; // rdx
  __int64 v32; // rcx
  rsize_t v33; // rdi
  rsize_t v34; // rbx
  char *v35; // rdx
  unsigned int v36; // r8d
  bool v37; // zf
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  char *Source; // [rsp+30h] [rbp-58h]
  char *Sourcea; // [rsp+30h] [rbp-58h]
  rsize_t v43; // [rsp+38h] [rbp-50h]
  rsize_t v44; // [rsp+40h] [rbp-48h]
  SIZE_T dwBytes; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v46; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v47; // [rsp+A8h] [rbp+20h]

  v47 = a4;
  v5 = a3;
  v7 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a2, a3);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  v46 = 0;
  LODWORD(dwBytes) = 0;
  v10 = 0;
  v11 = a1;
  v12 = v5;
  while ( 1 )
  {
    if ( v10 >= (unsigned int)v7 )
    {
      if ( v9 == v5 )
      {
        v16 = (unsigned int)dwBytes;
        v17 = (char *)GlobalAlloc(0x40u, (unsigned int)dwBytes);
        v18 = v17;
        if ( v17 )
        {
          memset_0(v17, 0, v16);
          v19 = (char *)a1;
          v20 = v16 - (v7 << 6);
          v21 = v18;
          v22 = &v18[64 * v7];
          dwBytes = (SIZE_T)v22;
          if ( g_dwTraceId != -1 )
          {
            TracePrintfExA(g_dwTraceId, 0xCu, "PhonebookEntryToRasEntryAdvanced - Found %d NRPT Entries.", v7);
            v22 = (char *)dwBytes;
          }
          v23 = 0;
          while ( 1 )
          {
            v46 = v23;
            if ( v23 >= (unsigned int)v7 )
              break;
            v24 = (unsigned __int64)a1 + v12;
            v25 = v19 + 24;
            if ( v19 + 24 >= (char *)a1 + v12 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 1.");
              v14 = 111;
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_72;
              }
              v39 = 160;
LABEL_71:
              WPP_SF_d(v38[2], v39, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 111);
              goto LABEL_72;
            }
            *((_DWORD *)v21 + 3) = *((_DWORD *)v19 + 1);
            *((_DWORD *)v21 + 4) = *((_DWORD *)v19 + 2);
            *((_DWORD *)v21 + 5) = *((_DWORD *)v19 + 3);
            *((_DWORD *)v21 + 6) = *((_DWORD *)v19 + 4);
            *((_DWORD *)v21 + 2) = *(_DWORD *)v19;
            *((_DWORD *)v21 + 7) = *((_DWORD *)v19 + 5);
            v26 = 20LL * *((unsigned int *)v19 + 1);
            v43 = v26;
            Source = &v25[v26];
            if ( (unsigned __int64)&v25[v26] >= v24 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 2.");
              v14 = 111;
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_72;
              }
              v39 = 161;
              goto LABEL_71;
            }
            memcpy_s(v22, v20, v25, v26);
            v27 = Source;
            v28 = dwBytes;
            *((_QWORD *)v21 + 4) = dwBytes;
            v29 = 2LL * *((unsigned int *)v19 + 2);
            v44 = v29;
            Sourcea = &Source[v29];
            if ( (unsigned __int64)Sourcea > v24 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.");
              v14 = 111;
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_72;
              }
              v39 = 162;
              goto LABEL_71;
            }
            v30 = v20 - v43;
            dwBytes = v43 + v28;
            memcpy_s((void *const)(v43 + v28), v30, v27, v29);
            v31 = dwBytes;
            *((_QWORD *)v21 + 5) = dwBytes;
            v32 = 2LL * *((unsigned int *)v19 + 3);
            v19 = &Sourcea[v32];
            dwBytes = v32;
            if ( (unsigned __int64)&Sourcea[v32] > v24 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 4.");
              v14 = 111;
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v39 = 163;
                goto LABEL_71;
              }
LABEL_72:
              GlobalFree(v18);
              goto LABEL_74;
            }
            v33 = v30 - v44;
            v34 = v44 + v31;
            memcpy_s((void *const)(v44 + v31), v33, Sourcea, v32);
            v22 = (char *)(dwBytes + v34);
            v20 = v33 - dwBytes;
            *((_QWORD *)v21 + 7) = v34 & -(__int64)(dwBytes != 0);
            v35 = 0;
            v36 = v46;
            v37 = v46 == (_DWORD)v7 - 1;
            *((_QWORD *)v21 + 6) = 0;
            dwBytes = (SIZE_T)v22;
            if ( !v37 )
              v35 = v21 + 64;
            v23 = v36 + 1;
            *(_QWORD *)v21 = v35;
            v21 = v35;
          }
          v14 = 0;
          *a5 = v7;
          *v47 = v18;
          goto LABEL_74;
        }
        v14 = 14;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        v15 = 159;
      }
      else
      {
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "PhonebookEntryToRasEntryAdvanced - Invalid NRPT data in phonebook.");
          v8 = WPP_GLOBAL_Control;
        }
        v14 = 87;
        if ( v8 == (_DWORD *)&WPP_GLOBAL_Control || (v8[7] & 0x1000) == 0 || *((_BYTE *)v8 + 25) < 2u )
          goto LABEL_75;
        v15 = 158;
      }
      v13 = v14;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v8 + 2), v15, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
LABEL_74:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_75;
    }
    if ( v11 + 6 >= (_DWORD *)((char *)a1 + v5) )
    {
      if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(g_dwTraceId, 0xCu, "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.");
        v8 = WPP_GLOBAL_Control;
      }
      v13 = 111;
      v14 = 111;
      if ( v8 == (_DWORD *)&WPP_GLOBAL_Control || (v8[7] & 0x1000) == 0 || *((_BYTE *)v8 + 25) < 2u )
        goto LABEL_75;
      v15 = 156;
      goto LABEL_16;
    }
    if ( (unsigned int)CalculateBufferSizeForNrptRule(24, v11[1], v11[2], v11[3], (__int64)&v46, (__int64)&dwBytes) )
      break;
    v11 = (_DWORD *)((char *)v11 + v46);
    v9 += v46;
    ++v10;
  }
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "PhonebookEntryToRasEntryAdvanced - Invalid NRPT data in phonebook, integer overflow can lead to buffer overflow 3.");
    v8 = WPP_GLOBAL_Control;
  }
  v13 = 111;
  v14 = 111;
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
  {
    v15 = 157;
    goto LABEL_16;
  }
LABEL_75:
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "NrptBlobToNrptRuleList: exiting with error 0x%x", v14);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v8 + 2), 164, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18003d738  mov     [rsp+arg_10], rbx
0x18003d73d  mov     [rsp+arg_18], r9
0x18003d742  push    rbp
0x18003d743  push    rsi
0x18003d744  push    rdi
0x18003d745  push    r12
0x18003d747  push    r13
0x18003d749  push    r14
0x18003d74b  push    r15
0x18003d74d  sub     rsp, 50h
0x18003d751  mov     r15d, r8d
0x18003d754  mov     r12, rcx
0x18003d757  mov     esi, edx
0x18003d759  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d760  lea     rax, WPP_GLOBAL_Control
0x18003d767  cmp     rbx, rax
0x18003d76a  jz      short loc_18003D79F
0x18003d76c  test    dword ptr [rbx+1Ch], 1000h
0x18003d773  jz      short loc_18003D79F
0x18003d775  cmp     byte ptr [rbx+19h], 6
0x18003d779  jb      short loc_18003D79F
0x18003d77b  mov     rcx, [rbx+10h]
0x18003d77f  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18003d786  mov     edx, 9Bh
0x18003d78b  mov     dword ptr [rsp+88h+var_68], r15d
0x18003d790  mov     r9d, esi
0x18003d793  call    WPP_SF_Dd
0x18003d798  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d79f  xor     ebp, ebp
0x18003d7a1  mov     [rsp+88h+arg_8], 0
0x18003d7ac  mov     dword ptr [rsp+88h+dwBytes], ebp
0x18003d7b3  xor     r14d, r14d
0x18003d7b6  mov     rdi, r12
0x18003d7b9  mov     r13, r15
0x18003d7bc  or      edx, 0FFFFFFFFh
0x18003d7bf  cmp     r14d, esi
0x18003d7c2  jnb     loc_18003D8E4
0x18003d7c8  lea     rcx, [r12+r15]
0x18003d7cc  lea     rax, [rdi+18h]
0x18003d7d0  cmp     rax, rcx
0x18003d7d3  jnb     loc_18003D88B
0x18003d7d9  mov     r8d, [rdi+8]
0x18003d7dd  lea     rax, [rsp+88h+dwBytes]
0x18003d7e5  mov     edx, [rdi+4]
0x18003d7e8  mov     ecx, 18h
0x18003d7ed  mov     r9d, [rdi+0Ch]
0x18003d7f1  mov     [rsp+88h+var_60], rax
0x18003d7f6  lea     rax, [rsp+88h+arg_8]
0x18003d7fe  mov     [rsp+88h+var_68], rax
0x18003d803  call    CalculateBufferSizeForNrptRule
0x18003d808  test    eax, eax
0x18003d80a  jnz     short loc_18003D81E
0x18003d80c  mov     eax, [rsp+88h+arg_8]
0x18003d813  add     rdi, rax
0x18003d816  add     rbp, rax
0x18003d819  inc     r14d
0x18003d81c  jmp     short loc_18003D7BC
0x18003d81e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003d824  cmp     ecx, 0FFFFFFFFh
0x18003d827  jz      short loc_18003D842
0x18003d829  lea     r8, aPhonebookentry_7; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x18003d830  mov     edx, 0Ch; dwFlags
0x18003d835  call    cs:__imp_TracePrintfExA
0x18003d83b  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d842  mov     r9d, 6Fh ; 'o'
0x18003d848  mov     edi, r9d
0x18003d84b  lea     rsi, WPP_GLOBAL_Control
0x18003d852  cmp     rbx, rsi
0x18003d855  jz      loc_18003DCF3
0x18003d85b  test    dword ptr [rbx+1Ch], 1000h
0x18003d862  jz      loc_18003DCF3
0x18003d868  cmp     byte ptr [rbx+19h], 2
0x18003d86c  jb      loc_18003DCF3
0x18003d872  lea     edx, [r9+2Eh]
0x18003d876  mov     rcx, [rbx+10h]
0x18003d87a  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18003d881  call    WPP_SF_d
0x18003d886  jmp     loc_18003DCEC
0x18003d88b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003d891  cmp     ecx, edx
0x18003d893  jz      short loc_18003D8AE
0x18003d895  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x18003d89c  mov     edx, 0Ch; dwFlags
0x18003d8a1  call    cs:__imp_TracePrintfExA
0x18003d8a7  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d8ae  mov     r9d, 6Fh ; 'o'
0x18003d8b4  mov     edi, r9d
0x18003d8b7  lea     rsi, WPP_GLOBAL_Control
0x18003d8be  cmp     rbx, rsi
0x18003d8c1  jz      loc_18003DCF3
0x18003d8c7  test    dword ptr [rbx+1Ch], 1000h
0x18003d8ce  jz      loc_18003DCF3
0x18003d8d4  cmp     byte ptr [rbx+19h], 2
0x18003d8d8  jb      loc_18003DCF3
0x18003d8de  lea     edx, [r9+2Dh]
0x18003d8e2  jmp     short loc_18003D876
0x18003d8e4  cmp     rbp, r13
0x18003d8e7  jz      short loc_18003D943
0x18003d8e9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003d8ef  cmp     ecx, edx
0x18003d8f1  jz      short loc_18003D90C
0x18003d8f3  lea     r8, aPhonebookentry_2; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x18003d8fa  mov     edx, 0Ch; dwFlags
0x18003d8ff  call    cs:__imp_TracePrintfExA
0x18003d905  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d90c  mov     edi, 57h ; 'W'
0x18003d911  lea     rsi, WPP_GLOBAL_Control
0x18003d918  cmp     rbx, rsi
0x18003d91b  jz      loc_18003DCF3
0x18003d921  test    dword ptr [rbx+1Ch], 1000h
0x18003d928  jz      loc_18003DCF3
0x18003d92e  cmp     byte ptr [rbx+19h], 2
0x18003d932  jb      loc_18003DCF3
0x18003d938  lea     edx, [rdi+47h]
0x18003d93b  mov     r9d, edi
0x18003d93e  jmp     loc_18003D876
0x18003d943  mov     edi, dword ptr [rsp+88h+dwBytes]
0x18003d94a  mov     ecx, 40h ; '@'; uFlags
0x18003d94f  mov     edx, edi; dwBytes
0x18003d951  call    cs:__imp_GlobalAlloc
0x18003d957  mov     rbp, rax
0x18003d95a  test    rax, rax
0x18003d95d  jnz     short loc_18003D997
0x18003d95f  lea     edi, [rax+0Eh]
0x18003d962  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d969  lea     rsi, WPP_GLOBAL_Control
0x18003d970  cmp     rbx, rsi
0x18003d973  jz      loc_18003DCF3
0x18003d979  test    dword ptr [rbx+1Ch], 1000h
0x18003d980  jz      loc_18003DCF3
0x18003d986  cmp     byte ptr [rbx+19h], 2
0x18003d98a  jb      loc_18003DCF3
0x18003d990  mov     edx, 9Fh
0x18003d995  jmp     short loc_18003D93B
0x18003d997  mov     r8, rdi; Size
0x18003d99a  xor     edx, edx; Val
0x18003d99c  mov     rcx, rbp; void *
0x18003d99f  call    memset_0
0x18003d9a4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003d9aa  mov     rax, rsi
0x18003d9ad  shl     rax, 6
0x18003d9b1  mov     r14, r12
0x18003d9b4  sub     rdi, rax
0x18003d9b7  mov     r15, rbp
0x18003d9ba  lea     r10, [rax+rbp]
0x18003d9be  mov     [rsp+88h+dwBytes], r10
0x18003d9c6  cmp     ecx, 0FFFFFFFFh
0x18003d9c9  jz      short loc_18003D9E8
0x18003d9cb  mov     r9d, esi
0x18003d9ce  lea     r8, aPhonebookentry_3; "PhonebookEntryToRasEntryAdvanced - Foun"...
0x18003d9d5  mov     edx, 0Ch; dwFlags
0x18003d9da  call    cs:__imp_TracePrintfExA
0x18003d9e0  mov     r10, [rsp+88h+dwBytes]
0x18003d9e8  xor     r8d, r8d
0x18003d9eb  mov     [rsp+88h+arg_8], r8d
0x18003d9f3  cmp     r8d, esi
0x18003d9f6  jnb     loc_18003DCCE
0x18003d9fc  lea     rbx, [r12+r13]
0x18003da00  lea     r8, [r14+18h]; Source
0x18003da04  cmp     r8, rbx
0x18003da07  jnb     loc_18003DC67
0x18003da0d  mov     eax, [r14+4]
0x18003da11  mov     [r15+0Ch], eax
0x18003da15  mov     eax, [r14+8]
0x18003da19  mov     [r15+10h], eax
0x18003da1d  mov     eax, [r14+0Ch]
0x18003da21  mov     [r15+14h], eax
0x18003da25  mov     eax, [r14+10h]
0x18003da29  mov     [r15+18h], eax
0x18003da2d  mov     eax, [r14]
0x18003da30  mov     [r15+8], eax
0x18003da34  mov     eax, [r14+14h]
0x18003da38  mov     [r15+1Ch], eax
0x18003da3c  mov     eax, [r14+4]
0x18003da40  lea     rcx, [rax+rax*4]
0x18003da44  lea     rax, ds:0[rcx*4]
0x18003da4c  lea     rcx, [rax+r8]
0x18003da50  mov     [rsp+88h+var_50], rax
0x18003da55  mov     [rsp+88h+Source], rcx
0x18003da5a  cmp     rcx, rbx
0x18003da5d  jnb     loc_18003DC19
0x18003da63  mov     r9, rax; SourceSize
0x18003da66  mov     rdx, rdi; DestinationSize
0x18003da69  mov     rcx, r10; Destination
0x18003da6c  call    cs:__imp_memcpy_s
0x18003da72  mov     r8, [rsp+88h+Source]; Source
0x18003da77  mov     rdx, [rsp+88h+dwBytes]
0x18003da7f  mov     [r15+20h], rdx
0x18003da83  mov     eax, [r14+8]
0x18003da87  lea     rcx, [rax+rax]
0x18003da8b  lea     rax, [r8+rcx]
0x18003da8f  mov     [rsp+88h+var_48], rcx
0x18003da94  mov     [rsp+88h+Source], rax
0x18003da99  cmp     rax, rbx
0x18003da9c  ja      loc_18003DBBC
0x18003daa2  mov     rax, [rsp+88h+var_50]
0x18003daa7  mov     r9, rcx; SourceSize
0x18003daaa  sub     rdi, rax
0x18003daad  lea     r10, [rax+rdx]
0x18003dab1  mov     rdx, rdi; DestinationSize
0x18003dab4  mov     rcx, r10; Destination
0x18003dab7  mov     [rsp+88h+dwBytes], r10
0x18003dabf  call    cs:__imp_memcpy_s
0x18003dac5  mov     rdx, [rsp+88h+dwBytes]
0x18003dacd  mov     r8, [rsp+88h+Source]; Source
0x18003dad2  mov     [r15+28h], rdx
0x18003dad6  mov     eax, [r14+0Ch]
0x18003dada  lea     rcx, [rax+rax]
0x18003dade  lea     r14, [rcx+r8]
0x18003dae2  mov     [rsp+88h+dwBytes], rcx
0x18003daea  cmp     r14, rbx
0x18003daed  ja      short loc_18003DB5F
0x18003daef  mov     rax, [rsp+88h+var_48]
0x18003daf4  mov     r9, rcx; SourceSize
0x18003daf7  sub     rdi, rax
0x18003dafa  lea     rbx, [rax+rdx]
0x18003dafe  mov     rdx, rdi; DestinationSize
0x18003db01  mov     rcx, rbx; Destination
0x18003db04  call    cs:__imp_memcpy_s
0x18003db0a  mov     rdx, [rsp+88h+dwBytes]
0x18003db12  mov     rax, rdx
0x18003db15  neg     rax
0x18003db18  lea     rax, [r15+40h]
0x18003db1c  sbb     rcx, rcx
0x18003db1f  lea     r10, [rdx+rbx]
0x18003db23  and     rcx, rbx
0x18003db26  sub     rdi, rdx
0x18003db29  mov     [r15+38h], rcx
0x18003db2d  xor     edx, edx
0x18003db2f  mov     r8d, [rsp+88h+arg_8]
0x18003db37  lea     ecx, [rsi-1]
0x18003db3a  cmp     r8d, ecx
0x18003db3d  mov     qword ptr [r15+30h], 0
0x18003db45  mov     [rsp+88h+dwBytes], r10
0x18003db4d  cmovnz  rdx, rax
0x18003db51  inc     r8d
0x18003db54  mov     [r15], rdx
0x18003db57  mov     r15, rdx
0x18003db5a  jmp     loc_18003D9EB
0x18003db5f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003db65  cmp     ecx, 0FFFFFFFFh
0x18003db68  jz      short loc_18003DB7C
0x18003db6a  lea     r8, aPhonebookentry_0; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x18003db71  mov     edx, 0Ch; dwFlags
0x18003db76  call    cs:__imp_TracePrintfExA
0x18003db7c  mov     r9d, 6Fh ; 'o'
0x18003db82  mov     edi, r9d
0x18003db85  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db8c  lea     rsi, WPP_GLOBAL_Control
0x18003db93  cmp     rcx, rsi
0x18003db96  jz      loc_18003DCC3
0x18003db9c  test    dword ptr [rcx+1Ch], 1000h
0x18003dba3  jz      loc_18003DCC3
0x18003dba9  cmp     byte ptr [rcx+19h], 2
0x18003dbad  jb      loc_18003DCC3
0x18003dbb3  lea     edx, [r9+34h]
0x18003dbb7  jmp     loc_18003DCB3
0x18003dbbc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003dbc2  cmp     ecx, 0FFFFFFFFh
0x18003dbc5  jz      short loc_18003DBD9
0x18003dbc7  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x18003dbce  mov     edx, 0Ch; dwFlags
0x18003dbd3  call    cs:__imp_TracePrintfExA
0x18003dbd9  mov     r9d, 6Fh ; 'o'
0x18003dbdf  mov     edi, r9d
0x18003dbe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dbe9  lea     rsi, WPP_GLOBAL_Control
0x18003dbf0  cmp     rcx, rsi
0x18003dbf3  jz      loc_18003DCC3
0x18003dbf9  test    dword ptr [rcx+1Ch], 1000h
0x18003dc00  jz      loc_18003DCC3
0x18003dc06  cmp     byte ptr [rcx+19h], 2
0x18003dc0a  jb      loc_18003DCC3
0x18003dc10  lea     edx, [r9+33h]
0x18003dc14  jmp     loc_18003DCB3
0x18003dc19  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003dc1f  cmp     ecx, 0FFFFFFFFh
0x18003dc22  jz      short loc_18003DC36
0x18003dc24  lea     r8, aPhonebookentry_1; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x18003dc2b  mov     edx, 0Ch; dwFlags
0x18003dc30  call    cs:__imp_TracePrintfExA
0x18003dc36  mov     r9d, 6Fh ; 'o'
0x18003dc3c  mov     edi, r9d
0x18003dc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc46  lea     rsi, WPP_GLOBAL_Control
0x18003dc4d  cmp     rcx, rsi
0x18003dc50  jz      short loc_18003DCC3
0x18003dc52  test    dword ptr [rcx+1Ch], 1000h
0x18003dc59  jz      short loc_18003DCC3
0x18003dc5b  cmp     byte ptr [rcx+19h], 2
0x18003dc5f  jb      short loc_18003DCC3
0x18003dc61  lea     edx, [r9+32h]
0x18003dc65  jmp     short loc_18003DCB3
0x18003dc67  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003dc6d  cmp     ecx, 0FFFFFFFFh
0x18003dc70  jz      short loc_18003DC84
0x18003dc72  lea     r8, aPhonebookentry_4; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x18003dc79  mov     edx, 0Ch; dwFlags
0x18003dc7e  call    cs:__imp_TracePrintfExA
0x18003dc84  mov     r9d, 6Fh ; 'o'
  ... truncated ...
```
