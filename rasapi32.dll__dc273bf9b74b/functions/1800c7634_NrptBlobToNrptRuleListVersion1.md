# NrptBlobToNrptRuleListVersion1

- ea: `0x1800c7634`
- end: `0x1800c7c5c`
- name: `NrptBlobToNrptRuleListVersion1`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fe94`

## callees

- `0x180040258`
- `0x18004e580`
- `0x18007f140`
- `0x1800c7634`
- `0x1800ded06`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800c7968`
- `msvcrt!memcpy_s` at `0x1800c79bb`
- `msvcrt!memcpy_s` at `0x1800c7a00`
- `msvcrt!memcpy_s` at `0x1800c7968`
- `msvcrt!memcpy_s` at `0x1800c79bb`
- `msvcrt!memcpy_s` at `0x1800c7a00`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c784d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c784d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c7bc2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c7bc2`
- `rtutils!TracePrintfExA` at `0x1800c7731`
- `rtutils!TracePrintfExA` at `0x1800c779d`
- `rtutils!TracePrintfExA` at `0x1800c77fb`
- `rtutils!TracePrintfExA` at `0x1800c78d6`
- `rtutils!TracePrintfExA` at `0x1800c7a72`
- `rtutils!TracePrintfExA` at `0x1800c7acf`
- `rtutils!TracePrintfExA` at `0x1800c7b2c`
- `rtutils!TracePrintfExA` at `0x1800c7b7a`
- `rtutils!TracePrintfExA` at `0x1800c7c09`
- `rtutils!TracePrintfExA` at `0x1800c7731`
- `rtutils!TracePrintfExA` at `0x1800c779d`
- `rtutils!TracePrintfExA` at `0x1800c77fb`
- `rtutils!TracePrintfExA` at `0x1800c78d6`
- `rtutils!TracePrintfExA` at `0x1800c7a72`
- `rtutils!TracePrintfExA` at `0x1800c7acf`
- `rtutils!TracePrintfExA` at `0x1800c7b2c`
- `rtutils!TracePrintfExA` at `0x1800c7b7a`
- `rtutils!TracePrintfExA` at `0x1800c7c09`

## string_xrefs

- `0x1800c7791`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x1800c7ac3`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x1800c7b20`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 2.`
- `0x1800c7b6e`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 1.`
- `0x1800c7a66`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 4.`

## pseudocode

```c
__int64 __fastcall NrptBlobToNrptRuleListVersion1(_DWORD *a1, unsigned int a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
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
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a2, a3);
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
            v25 = v19 + 20;
            if ( v19 + 20 >= (char *)a1 + v12 )
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
              v39 = 150;
LABEL_71:
              WPP_SF_d(v38[2], v39, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 111);
              goto LABEL_72;
            }
            *((_DWORD *)v21 + 3) = *((_DWORD *)v19 + 1);
            *((_DWORD *)v21 + 4) = *((_DWORD *)v19 + 2);
            *((_DWORD *)v21 + 5) = *((_DWORD *)v19 + 3);
            *((_DWORD *)v21 + 6) = *((_DWORD *)v19 + 4);
            *((_DWORD *)v21 + 2) = *(_DWORD *)v19;
            *((_DWORD *)v21 + 7) = 0;
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
              v39 = 151;
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
              v39 = 152;
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
                v39 = 153;
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
        v15 = 149;
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
        v15 = 148;
      }
      v13 = v14;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v8 + 2), v15, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
LABEL_74:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_75;
    }
    if ( v11 + 5 >= (_DWORD *)((char *)a1 + v5) )
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
      v15 = 146;
      goto LABEL_16;
    }
    if ( (unsigned int)CalculateBufferSizeForNrptRule(20, v11[1], v11[2], v11[3], (__int64)&v46, (__int64)&dwBytes) )
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
      "PhonebookEntryToRasEntryAdvanced - Invalid NRPT data in phonebook, integer overflow can lead to buffer overflow 2.");
    v8 = WPP_GLOBAL_Control;
  }
  v13 = 111;
  v14 = 111;
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
  {
    v15 = 147;
    goto LABEL_16;
  }
LABEL_75:
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "NrptBlobToNrptRuleList: exiting with error 0x%x", v14);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v8 + 2), 154, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x1800c7634  mov     [rsp+arg_10], rbx
0x1800c7639  mov     [rsp+arg_18], r9
0x1800c763e  push    rbp
0x1800c763f  push    rsi
0x1800c7640  push    rdi
0x1800c7641  push    r12
0x1800c7643  push    r13
0x1800c7645  push    r14
0x1800c7647  push    r15
0x1800c7649  sub     rsp, 50h
0x1800c764d  mov     r15d, r8d
0x1800c7650  mov     r12, rcx
0x1800c7653  mov     esi, edx
0x1800c7655  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c765c  lea     rax, WPP_GLOBAL_Control
0x1800c7663  cmp     rbx, rax
0x1800c7666  jz      short loc_1800C769B
0x1800c7668  test    dword ptr [rbx+1Ch], 1000h
0x1800c766f  jz      short loc_1800C769B
0x1800c7671  cmp     byte ptr [rbx+19h], 6
0x1800c7675  jb      short loc_1800C769B
0x1800c7677  mov     rcx, [rbx+10h]
0x1800c767b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c7682  mov     edx, 91h
0x1800c7687  mov     dword ptr [rsp+88h+var_68], r15d
0x1800c768c  mov     r9d, esi
0x1800c768f  call    WPP_SF_Dd
0x1800c7694  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c769b  xor     ebp, ebp
0x1800c769d  mov     [rsp+88h+arg_8], 0
0x1800c76a8  mov     dword ptr [rsp+88h+dwBytes], ebp
0x1800c76af  xor     r14d, r14d
0x1800c76b2  mov     rdi, r12
0x1800c76b5  mov     r13, r15
0x1800c76b8  or      edx, 0FFFFFFFFh
0x1800c76bb  cmp     r14d, esi
0x1800c76be  jnb     loc_1800C77E0
0x1800c76c4  lea     rcx, [r12+r15]
0x1800c76c8  lea     rax, [rdi+14h]
0x1800c76cc  cmp     rax, rcx
0x1800c76cf  jnb     loc_1800C7787
0x1800c76d5  mov     r8d, [rdi+8]
0x1800c76d9  lea     rax, [rsp+88h+dwBytes]
0x1800c76e1  mov     edx, [rdi+4]
0x1800c76e4  mov     ecx, 14h
0x1800c76e9  mov     r9d, [rdi+0Ch]
0x1800c76ed  mov     [rsp+88h+var_60], rax
0x1800c76f2  lea     rax, [rsp+88h+arg_8]
0x1800c76fa  mov     [rsp+88h+var_68], rax
0x1800c76ff  call    CalculateBufferSizeForNrptRule
0x1800c7704  test    eax, eax
0x1800c7706  jnz     short loc_1800C771A
0x1800c7708  mov     eax, [rsp+88h+arg_8]
0x1800c770f  add     rdi, rax
0x1800c7712  add     rbp, rax
0x1800c7715  inc     r14d
0x1800c7718  jmp     short loc_1800C76B8
0x1800c771a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7720  cmp     ecx, 0FFFFFFFFh
0x1800c7723  jz      short loc_1800C773E
0x1800c7725  lea     r8, aPhonebookentry; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x1800c772c  mov     edx, 0Ch; dwFlags
0x1800c7731  call    cs:__imp_TracePrintfExA
0x1800c7737  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c773e  mov     r9d, 6Fh ; 'o'
0x1800c7744  mov     edi, r9d
0x1800c7747  lea     rsi, WPP_GLOBAL_Control
0x1800c774e  cmp     rbx, rsi
0x1800c7751  jz      loc_1800C7BEF
0x1800c7757  test    dword ptr [rbx+1Ch], 1000h
0x1800c775e  jz      loc_1800C7BEF
0x1800c7764  cmp     byte ptr [rbx+19h], 2
0x1800c7768  jb      loc_1800C7BEF
0x1800c776e  lea     edx, [r9+24h]
0x1800c7772  mov     rcx, [rbx+10h]
0x1800c7776  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c777d  call    WPP_SF_d
0x1800c7782  jmp     loc_1800C7BE8
0x1800c7787  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c778d  cmp     ecx, edx
0x1800c778f  jz      short loc_1800C77AA
0x1800c7791  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7798  mov     edx, 0Ch; dwFlags
0x1800c779d  call    cs:__imp_TracePrintfExA
0x1800c77a3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c77aa  mov     r9d, 6Fh ; 'o'
0x1800c77b0  mov     edi, r9d
0x1800c77b3  lea     rsi, WPP_GLOBAL_Control
0x1800c77ba  cmp     rbx, rsi
0x1800c77bd  jz      loc_1800C7BEF
0x1800c77c3  test    dword ptr [rbx+1Ch], 1000h
0x1800c77ca  jz      loc_1800C7BEF
0x1800c77d0  cmp     byte ptr [rbx+19h], 2
0x1800c77d4  jb      loc_1800C7BEF
0x1800c77da  lea     edx, [r9+23h]
0x1800c77de  jmp     short loc_1800C7772
0x1800c77e0  cmp     rbp, r13
0x1800c77e3  jz      short loc_1800C783F
0x1800c77e5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c77eb  cmp     ecx, edx
0x1800c77ed  jz      short loc_1800C7808
0x1800c77ef  lea     r8, aPhonebookentry_2; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x1800c77f6  mov     edx, 0Ch; dwFlags
0x1800c77fb  call    cs:__imp_TracePrintfExA
0x1800c7801  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c7808  mov     edi, 57h ; 'W'
0x1800c780d  lea     rsi, WPP_GLOBAL_Control
0x1800c7814  cmp     rbx, rsi
0x1800c7817  jz      loc_1800C7BEF
0x1800c781d  test    dword ptr [rbx+1Ch], 1000h
0x1800c7824  jz      loc_1800C7BEF
0x1800c782a  cmp     byte ptr [rbx+19h], 2
0x1800c782e  jb      loc_1800C7BEF
0x1800c7834  lea     edx, [rdi+3Dh]
0x1800c7837  mov     r9d, edi
0x1800c783a  jmp     loc_1800C7772
0x1800c783f  mov     edi, dword ptr [rsp+88h+dwBytes]
0x1800c7846  mov     ecx, 40h ; '@'; uFlags
0x1800c784b  mov     edx, edi; dwBytes
0x1800c784d  call    cs:__imp_GlobalAlloc
0x1800c7853  mov     rbp, rax
0x1800c7856  test    rax, rax
0x1800c7859  jnz     short loc_1800C7893
0x1800c785b  lea     edi, [rax+0Eh]
0x1800c785e  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c7865  lea     rsi, WPP_GLOBAL_Control
0x1800c786c  cmp     rbx, rsi
0x1800c786f  jz      loc_1800C7BEF
0x1800c7875  test    dword ptr [rbx+1Ch], 1000h
0x1800c787c  jz      loc_1800C7BEF
0x1800c7882  cmp     byte ptr [rbx+19h], 2
0x1800c7886  jb      loc_1800C7BEF
0x1800c788c  mov     edx, 95h
0x1800c7891  jmp     short loc_1800C7837
0x1800c7893  mov     r8, rdi; Size
0x1800c7896  xor     edx, edx; Val
0x1800c7898  mov     rcx, rbp; void *
0x1800c789b  call    memset_0
0x1800c78a0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c78a6  mov     rax, rsi
0x1800c78a9  shl     rax, 6
0x1800c78ad  mov     r14, r12
0x1800c78b0  sub     rdi, rax
0x1800c78b3  mov     r15, rbp
0x1800c78b6  lea     r10, [rax+rbp]
0x1800c78ba  mov     [rsp+88h+dwBytes], r10
0x1800c78c2  cmp     ecx, 0FFFFFFFFh
0x1800c78c5  jz      short loc_1800C78E4
0x1800c78c7  mov     r9d, esi
0x1800c78ca  lea     r8, aPhonebookentry_3; "PhonebookEntryToRasEntryAdvanced - Foun"...
0x1800c78d1  mov     edx, 0Ch; dwFlags
0x1800c78d6  call    cs:__imp_TracePrintfExA
0x1800c78dc  mov     r10, [rsp+88h+dwBytes]
0x1800c78e4  xor     r8d, r8d
0x1800c78e7  mov     [rsp+88h+arg_8], r8d
0x1800c78ef  cmp     r8d, esi
0x1800c78f2  jnb     loc_1800C7BCA
0x1800c78f8  lea     rbx, [r12+r13]
0x1800c78fc  lea     r8, [r14+14h]; Source
0x1800c7900  cmp     r8, rbx
0x1800c7903  jnb     loc_1800C7B63
0x1800c7909  mov     eax, [r14+4]
0x1800c790d  mov     [r15+0Ch], eax
0x1800c7911  mov     eax, [r14+8]
0x1800c7915  mov     [r15+10h], eax
0x1800c7919  mov     eax, [r14+0Ch]
0x1800c791d  mov     [r15+14h], eax
0x1800c7921  mov     eax, [r14+10h]
0x1800c7925  mov     [r15+18h], eax
0x1800c7929  mov     eax, [r14]
0x1800c792c  mov     [r15+8], eax
0x1800c7930  mov     dword ptr [r15+1Ch], 0
0x1800c7938  mov     eax, [r14+4]
0x1800c793c  lea     rcx, [rax+rax*4]
0x1800c7940  lea     rax, ds:0[rcx*4]
0x1800c7948  lea     rcx, [rax+r8]
0x1800c794c  mov     [rsp+88h+var_50], rax
0x1800c7951  mov     [rsp+88h+Source], rcx
0x1800c7956  cmp     rcx, rbx
0x1800c7959  jnb     loc_1800C7B15
0x1800c795f  mov     r9, rax; SourceSize
0x1800c7962  mov     rdx, rdi; DestinationSize
0x1800c7965  mov     rcx, r10; Destination
0x1800c7968  call    cs:__imp_memcpy_s
0x1800c796e  mov     r8, [rsp+88h+Source]; Source
0x1800c7973  mov     rdx, [rsp+88h+dwBytes]
0x1800c797b  mov     [r15+20h], rdx
0x1800c797f  mov     eax, [r14+8]
0x1800c7983  lea     rcx, [rax+rax]
0x1800c7987  lea     rax, [r8+rcx]
0x1800c798b  mov     [rsp+88h+var_48], rcx
0x1800c7990  mov     [rsp+88h+Source], rax
0x1800c7995  cmp     rax, rbx
0x1800c7998  ja      loc_1800C7AB8
0x1800c799e  mov     rax, [rsp+88h+var_50]
0x1800c79a3  mov     r9, rcx; SourceSize
0x1800c79a6  sub     rdi, rax
0x1800c79a9  lea     r10, [rax+rdx]
0x1800c79ad  mov     rdx, rdi; DestinationSize
0x1800c79b0  mov     rcx, r10; Destination
0x1800c79b3  mov     [rsp+88h+dwBytes], r10
0x1800c79bb  call    cs:__imp_memcpy_s
0x1800c79c1  mov     rdx, [rsp+88h+dwBytes]
0x1800c79c9  mov     r8, [rsp+88h+Source]; Source
0x1800c79ce  mov     [r15+28h], rdx
0x1800c79d2  mov     eax, [r14+0Ch]
0x1800c79d6  lea     rcx, [rax+rax]
0x1800c79da  lea     r14, [rcx+r8]
0x1800c79de  mov     [rsp+88h+dwBytes], rcx
0x1800c79e6  cmp     r14, rbx
0x1800c79e9  ja      short loc_1800C7A5B
0x1800c79eb  mov     rax, [rsp+88h+var_48]
0x1800c79f0  mov     r9, rcx; SourceSize
0x1800c79f3  sub     rdi, rax
0x1800c79f6  lea     rbx, [rax+rdx]
0x1800c79fa  mov     rdx, rdi; DestinationSize
0x1800c79fd  mov     rcx, rbx; Destination
0x1800c7a00  call    cs:__imp_memcpy_s
0x1800c7a06  mov     rdx, [rsp+88h+dwBytes]
0x1800c7a0e  mov     rax, rdx
0x1800c7a11  neg     rax
0x1800c7a14  lea     rax, [r15+40h]
0x1800c7a18  sbb     rcx, rcx
0x1800c7a1b  lea     r10, [rdx+rbx]
0x1800c7a1f  and     rcx, rbx
0x1800c7a22  sub     rdi, rdx
0x1800c7a25  mov     [r15+38h], rcx
0x1800c7a29  xor     edx, edx
0x1800c7a2b  mov     r8d, [rsp+88h+arg_8]
0x1800c7a33  lea     ecx, [rsi-1]
0x1800c7a36  cmp     r8d, ecx
0x1800c7a39  mov     qword ptr [r15+30h], 0
0x1800c7a41  mov     [rsp+88h+dwBytes], r10
0x1800c7a49  cmovnz  rdx, rax
0x1800c7a4d  inc     r8d
0x1800c7a50  mov     [r15], rdx
0x1800c7a53  mov     r15, rdx
0x1800c7a56  jmp     loc_1800C78E7
0x1800c7a5b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7a61  cmp     ecx, 0FFFFFFFFh
0x1800c7a64  jz      short loc_1800C7A78
0x1800c7a66  lea     r8, aPhonebookentry_0; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7a6d  mov     edx, 0Ch; dwFlags
0x1800c7a72  call    cs:__imp_TracePrintfExA
0x1800c7a78  mov     r9d, 6Fh ; 'o'
0x1800c7a7e  mov     edi, r9d
0x1800c7a81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7a88  lea     rsi, WPP_GLOBAL_Control
0x1800c7a8f  cmp     rcx, rsi
0x1800c7a92  jz      loc_1800C7BBF
0x1800c7a98  test    dword ptr [rcx+1Ch], 1000h
0x1800c7a9f  jz      loc_1800C7BBF
0x1800c7aa5  cmp     byte ptr [rcx+19h], 2
0x1800c7aa9  jb      loc_1800C7BBF
0x1800c7aaf  lea     edx, [r9+2Ah]
0x1800c7ab3  jmp     loc_1800C7BAF
0x1800c7ab8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7abe  cmp     ecx, 0FFFFFFFFh
0x1800c7ac1  jz      short loc_1800C7AD5
0x1800c7ac3  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7aca  mov     edx, 0Ch; dwFlags
0x1800c7acf  call    cs:__imp_TracePrintfExA
0x1800c7ad5  mov     r9d, 6Fh ; 'o'
0x1800c7adb  mov     edi, r9d
0x1800c7ade  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7ae5  lea     rsi, WPP_GLOBAL_Control
0x1800c7aec  cmp     rcx, rsi
0x1800c7aef  jz      loc_1800C7BBF
0x1800c7af5  test    dword ptr [rcx+1Ch], 1000h
0x1800c7afc  jz      loc_1800C7BBF
0x1800c7b02  cmp     byte ptr [rcx+19h], 2
0x1800c7b06  jb      loc_1800C7BBF
0x1800c7b0c  lea     edx, [r9+29h]
0x1800c7b10  jmp     loc_1800C7BAF
0x1800c7b15  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7b1b  cmp     ecx, 0FFFFFFFFh
0x1800c7b1e  jz      short loc_1800C7B32
0x1800c7b20  lea     r8, aPhonebookentry_1; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7b27  mov     edx, 0Ch; dwFlags
0x1800c7b2c  call    cs:__imp_TracePrintfExA
0x1800c7b32  mov     r9d, 6Fh ; 'o'
0x1800c7b38  mov     edi, r9d
0x1800c7b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7b42  lea     rsi, WPP_GLOBAL_Control
0x1800c7b49  cmp     rcx, rsi
0x1800c7b4c  jz      short loc_1800C7BBF
0x1800c7b4e  test    dword ptr [rcx+1Ch], 1000h
0x1800c7b55  jz      short loc_1800C7BBF
0x1800c7b57  cmp     byte ptr [rcx+19h], 2
0x1800c7b5b  jb      short loc_1800C7BBF
0x1800c7b5d  lea     edx, [r9+28h]
0x1800c7b61  jmp     short loc_1800C7BAF
0x1800c7b63  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7b69  cmp     ecx, 0FFFFFFFFh
0x1800c7b6c  jz      short loc_1800C7B80
0x1800c7b6e  lea     r8, aPhonebookentry_4; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7b75  mov     edx, 0Ch; dwFlags
0x1800c7b7a  call    cs:__imp_TracePrintfExA
0x1800c7b80  mov     r9d, 6Fh ; 'o'
0x1800c7b86  mov     edi, r9d
  ... truncated ...
```
