# NrptBlobToNrptRuleListVersion0

- ea: `0x1800c70d0`
- end: `0x1800c762b`
- name: `NrptBlobToNrptRuleListVersion0`
- size: `1371`
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
- `0x1800c70d0`
- `0x1800ded06`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800c73fb`
- `msvcrt!memcpy_s` at `0x1800c7440`
- `msvcrt!memcpy_s` at `0x1800c73fb`
- `msvcrt!memcpy_s` at `0x1800c7440`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c72e6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c72e6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c7591`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c7591`
- `rtutils!TracePrintfExA` at `0x1800c71ca`
- `rtutils!TracePrintfExA` at `0x1800c7236`
- `rtutils!TracePrintfExA` at `0x1800c7294`
- `rtutils!TracePrintfExA` at `0x1800c736d`
- `rtutils!TracePrintfExA` at `0x1800c749e`
- `rtutils!TracePrintfExA` at `0x1800c74fb`
- `rtutils!TracePrintfExA` at `0x1800c7549`
- `rtutils!TracePrintfExA` at `0x1800c75d8`
- `rtutils!TracePrintfExA` at `0x1800c71ca`
- `rtutils!TracePrintfExA` at `0x1800c7236`
- `rtutils!TracePrintfExA` at `0x1800c7294`
- `rtutils!TracePrintfExA` at `0x1800c736d`
- `rtutils!TracePrintfExA` at `0x1800c749e`
- `rtutils!TracePrintfExA` at `0x1800c74fb`
- `rtutils!TracePrintfExA` at `0x1800c7549`
- `rtutils!TracePrintfExA` at `0x1800c75d8`

## string_xrefs

- `0x1800c722a`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x1800c7492`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.`
- `0x1800c74ef`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 2.`
- `0x1800c753d`: `PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 1.`

## pseudocode

```c
__int64 __fastcall NrptBlobToNrptRuleListVersion0(_DWORD *a1, unsigned int a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
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
  size_t v16; // rbp
  char *v17; // rax
  char *v18; // r14
  char *v19; // r15
  rsize_t v20; // rbp
  char *v21; // rdi
  char *v22; // r10
  unsigned int v23; // r8d
  char *v24; // rbx
  char *v25; // r8
  rsize_t v26; // rax
  SIZE_T v27; // rdx
  __int64 v28; // rcx
  rsize_t v29; // rbp
  rsize_t v30; // rbx
  SIZE_T v31; // rax
  unsigned int v32; // r8d
  char *v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  char *Source; // [rsp+30h] [rbp-48h]
  rsize_t v38; // [rsp+38h] [rbp-40h]
  SIZE_T dwBytes; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v40; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v41; // [rsp+98h] [rbp+20h]

  v41 = a4;
  v5 = a3;
  v7 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a2, a3);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  v40 = 0;
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
            v40 = v23;
            if ( v23 >= (unsigned int)v7 )
              break;
            v24 = (char *)a1 + v12;
            v25 = v19 + 8;
            if ( v19 + 8 >= (char *)a1 + v12 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 1.");
              v14 = 111;
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_65;
              }
              v35 = 141;
LABEL_64:
              WPP_SF_d(v34[2], v35, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 111);
              goto LABEL_65;
            }
            *((_DWORD *)v21 + 3) = *(_DWORD *)v19;
            *((_DWORD *)v21 + 4) = *((_DWORD *)v19 + 1);
            *(_QWORD *)(v21 + 20) = 0;
            *((_DWORD *)v21 + 2) = 2;
            *((_QWORD *)v21 + 6) = 0;
            *((_QWORD *)v21 + 7) = 0;
            v26 = 20LL * *(unsigned int *)v19;
            v38 = v26;
            Source = &v25[v26];
            if ( &v25[v26] >= v24 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 2.");
              v14 = 111;
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_65;
              }
              v35 = 142;
              goto LABEL_64;
            }
            memcpy_s(v22, v20, v25, v26);
            v27 = dwBytes;
            *((_QWORD *)v21 + 4) = dwBytes;
            v28 = 2LL * *((unsigned int *)v19 + 1);
            v19 = &Source[v28];
            dwBytes = v28;
            if ( &Source[v28] > v24 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.");
              v14 = 111;
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v35 = 143;
                goto LABEL_64;
              }
LABEL_65:
              GlobalFree(v18);
              goto LABEL_67;
            }
            v29 = v20 - v38;
            v30 = v38 + v27;
            memcpy_s((void *const)(v38 + v27), v29, Source, v28);
            v31 = dwBytes;
            v32 = v40;
            v20 = v29 - dwBytes;
            v33 = 0;
            *((_QWORD *)v21 + 5) = v30;
            v22 = (char *)(v31 + v30);
            dwBytes = v31 + v30;
            if ( v32 != (_DWORD)v7 - 1 )
              v33 = v21 + 64;
            v23 = v32 + 1;
            *(_QWORD *)v21 = v33;
            v21 = v33;
          }
          v14 = 0;
          *a5 = v7;
          *v41 = v18;
          goto LABEL_67;
        }
        v14 = 14;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v15 = 140;
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
          goto LABEL_68;
        v15 = 139;
      }
      v13 = v14;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v8 + 2), v15, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
LABEL_67:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_68;
    }
    if ( v11 + 2 >= (_DWORD *)((char *)a1 + v5) )
    {
      if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(g_dwTraceId, 0xCu, "PhonebookEntryToRasEntryAdvanced - NRPT Rules buffer read overflow 3.");
        v8 = WPP_GLOBAL_Control;
      }
      v13 = 111;
      v14 = 111;
      if ( v8 == (_DWORD *)&WPP_GLOBAL_Control || (v8[7] & 0x1000) == 0 || *((_BYTE *)v8 + 25) < 2u )
        goto LABEL_68;
      v15 = 137;
      goto LABEL_16;
    }
    if ( (unsigned int)CalculateBufferSizeForNrptRule(8, *v11, v11[1], 0, (__int64)&v40, (__int64)&dwBytes) )
      break;
    v11 = (_DWORD *)((char *)v11 + v40);
    v9 += v40;
    ++v10;
  }
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "PhonebookEntryToRasEntryAdvanced - Invalid NRPT data in phonebook, integer overflow can lead to buffer overflow 1.");
    v8 = WPP_GLOBAL_Control;
  }
  v13 = 111;
  v14 = 111;
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
  {
    v15 = 138;
    goto LABEL_16;
  }
LABEL_68:
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "NrptBlobToNrptRuleList: exiting with error 0x%x", v14);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v8 + 2), 144, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x1800c70d0  mov     [rsp+arg_10], rbx
0x1800c70d5  mov     [rsp+arg_18], r9
0x1800c70da  push    rbp
0x1800c70db  push    rsi
0x1800c70dc  push    rdi
0x1800c70dd  push    r12
0x1800c70df  push    r13
0x1800c70e1  push    r14
0x1800c70e3  push    r15
0x1800c70e5  sub     rsp, 40h
0x1800c70e9  mov     r15d, r8d
0x1800c70ec  mov     r12, rcx
0x1800c70ef  mov     esi, edx
0x1800c70f1  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c70f8  lea     rax, WPP_GLOBAL_Control
0x1800c70ff  cmp     rbx, rax
0x1800c7102  jz      short loc_1800C7137
0x1800c7104  test    dword ptr [rbx+1Ch], 1000h
0x1800c710b  jz      short loc_1800C7137
0x1800c710d  cmp     byte ptr [rbx+19h], 6
0x1800c7111  jb      short loc_1800C7137
0x1800c7113  mov     rcx, [rbx+10h]
0x1800c7117  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c711e  mov     edx, 88h
0x1800c7123  mov     dword ptr [rsp+78h+var_58], r15d
0x1800c7128  mov     r9d, esi
0x1800c712b  call    WPP_SF_Dd
0x1800c7130  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c7137  xor     ebp, ebp
0x1800c7139  mov     [rsp+78h+arg_8], 0
0x1800c7144  mov     dword ptr [rsp+78h+dwBytes], ebp
0x1800c714b  xor     r14d, r14d
0x1800c714e  mov     rdi, r12
0x1800c7151  mov     r13, r15
0x1800c7154  or      edx, 0FFFFFFFFh
0x1800c7157  cmp     r14d, esi
0x1800c715a  jnb     loc_1800C7279
0x1800c7160  lea     rcx, [r12+r15]
0x1800c7164  lea     rax, [rdi+8]
0x1800c7168  cmp     rax, rcx
0x1800c716b  jnb     loc_1800C7220
0x1800c7171  mov     r8d, [rdi+4]
0x1800c7175  lea     rax, [rsp+78h+dwBytes]
0x1800c717d  mov     edx, [rdi]
0x1800c717f  xor     r9d, r9d
0x1800c7182  mov     [rsp+78h+var_50], rax
0x1800c7187  lea     rax, [rsp+78h+arg_8]
0x1800c718f  mov     [rsp+78h+var_58], rax
0x1800c7194  lea     ecx, [r9+8]
0x1800c7198  call    CalculateBufferSizeForNrptRule
0x1800c719d  test    eax, eax
0x1800c719f  jnz     short loc_1800C71B3
0x1800c71a1  mov     eax, [rsp+78h+arg_8]
0x1800c71a8  add     rdi, rax
0x1800c71ab  add     rbp, rax
0x1800c71ae  inc     r14d
0x1800c71b1  jmp     short loc_1800C7154
0x1800c71b3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c71b9  cmp     ecx, 0FFFFFFFFh
0x1800c71bc  jz      short loc_1800C71D7
0x1800c71be  lea     r8, aPhonebookentry_5; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x1800c71c5  mov     edx, 0Ch; dwFlags
0x1800c71ca  call    cs:__imp_TracePrintfExA
0x1800c71d0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c71d7  mov     r9d, 6Fh ; 'o'
0x1800c71dd  mov     edi, r9d
0x1800c71e0  lea     rsi, WPP_GLOBAL_Control
0x1800c71e7  cmp     rbx, rsi
0x1800c71ea  jz      loc_1800C75BE
0x1800c71f0  test    dword ptr [rbx+1Ch], 1000h
0x1800c71f7  jz      loc_1800C75BE
0x1800c71fd  cmp     byte ptr [rbx+19h], 2
0x1800c7201  jb      loc_1800C75BE
0x1800c7207  lea     edx, [r9+1Bh]
0x1800c720b  mov     rcx, [rbx+10h]
0x1800c720f  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c7216  call    WPP_SF_d
0x1800c721b  jmp     loc_1800C75B7
0x1800c7220  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7226  cmp     ecx, edx
0x1800c7228  jz      short loc_1800C7243
0x1800c722a  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7231  mov     edx, 0Ch; dwFlags
0x1800c7236  call    cs:__imp_TracePrintfExA
0x1800c723c  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c7243  mov     r9d, 6Fh ; 'o'
0x1800c7249  mov     edi, r9d
0x1800c724c  lea     rsi, WPP_GLOBAL_Control
0x1800c7253  cmp     rbx, rsi
0x1800c7256  jz      loc_1800C75BE
0x1800c725c  test    dword ptr [rbx+1Ch], 1000h
0x1800c7263  jz      loc_1800C75BE
0x1800c7269  cmp     byte ptr [rbx+19h], 2
0x1800c726d  jb      loc_1800C75BE
0x1800c7273  lea     edx, [r9+1Ah]
0x1800c7277  jmp     short loc_1800C720B
0x1800c7279  cmp     rbp, r13
0x1800c727c  jz      short loc_1800C72D8
0x1800c727e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7284  cmp     ecx, edx
0x1800c7286  jz      short loc_1800C72A1
0x1800c7288  lea     r8, aPhonebookentry_2; "PhonebookEntryToRasEntryAdvanced - Inva"...
0x1800c728f  mov     edx, 0Ch; dwFlags
0x1800c7294  call    cs:__imp_TracePrintfExA
0x1800c729a  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c72a1  mov     edi, 57h ; 'W'
0x1800c72a6  lea     rsi, WPP_GLOBAL_Control
0x1800c72ad  cmp     rbx, rsi
0x1800c72b0  jz      loc_1800C75BE
0x1800c72b6  test    dword ptr [rbx+1Ch], 1000h
0x1800c72bd  jz      loc_1800C75BE
0x1800c72c3  cmp     byte ptr [rbx+19h], 2
0x1800c72c7  jb      loc_1800C75BE
0x1800c72cd  lea     edx, [rdi+34h]
0x1800c72d0  mov     r9d, edi
0x1800c72d3  jmp     loc_1800C720B
0x1800c72d8  mov     ebp, dword ptr [rsp+78h+dwBytes]
0x1800c72df  mov     ecx, 40h ; '@'; uFlags
0x1800c72e4  mov     edx, ebp; dwBytes
0x1800c72e6  call    cs:__imp_GlobalAlloc
0x1800c72ec  mov     r14, rax
0x1800c72ef  test    rax, rax
0x1800c72f2  jnz     short loc_1800C732A
0x1800c72f4  lea     edi, [rax+0Eh]
0x1800c72f7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c72fe  lea     rsi, WPP_GLOBAL_Control
0x1800c7305  cmp     rbx, rsi
0x1800c7308  jz      loc_1800C75BE
0x1800c730e  test    dword ptr [rbx+1Ch], 1000h
0x1800c7315  jz      loc_1800C75BE
0x1800c731b  cmp     byte ptr [rbx+19h], 2
0x1800c731f  jb      loc_1800C75BE
0x1800c7325  lea     edx, [rdi+7Eh]
0x1800c7328  jmp     short loc_1800C72D0
0x1800c732a  mov     r8, rbp; Size
0x1800c732d  xor     edx, edx; Val
0x1800c732f  mov     rcx, r14; void *
0x1800c7332  call    memset_0
0x1800c7337  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c733d  mov     rax, rsi
0x1800c7340  shl     rax, 6
0x1800c7344  mov     r15, r12
0x1800c7347  sub     rbp, rax
0x1800c734a  mov     rdi, r14
0x1800c734d  lea     r10, [rax+r14]
0x1800c7351  mov     [rsp+78h+dwBytes], r10
0x1800c7359  cmp     ecx, 0FFFFFFFFh
0x1800c735c  jz      short loc_1800C737B
0x1800c735e  mov     r9d, esi
0x1800c7361  lea     r8, aPhonebookentry_3; "PhonebookEntryToRasEntryAdvanced - Foun"...
0x1800c7368  mov     edx, 0Ch; dwFlags
0x1800c736d  call    cs:__imp_TracePrintfExA
0x1800c7373  mov     r10, [rsp+78h+dwBytes]
0x1800c737b  xor     r8d, r8d
0x1800c737e  mov     [rsp+78h+arg_8], r8d
0x1800c7386  cmp     r8d, esi
0x1800c7389  jnb     loc_1800C7599
0x1800c738f  lea     rbx, [r12+r13]
0x1800c7393  lea     r8, [r15+8]; Source
0x1800c7397  cmp     r8, rbx
0x1800c739a  jnb     loc_1800C7532
0x1800c73a0  mov     eax, [r15]
0x1800c73a3  mov     [rdi+0Ch], eax
0x1800c73a6  mov     eax, [r15+4]
0x1800c73aa  mov     [rdi+10h], eax
0x1800c73ad  mov     qword ptr [rdi+14h], 0
0x1800c73b5  mov     dword ptr [rdi+8], 2
0x1800c73bc  mov     qword ptr [rdi+30h], 0
0x1800c73c4  mov     qword ptr [rdi+38h], 0
0x1800c73cc  mov     eax, [r15]
0x1800c73cf  lea     rcx, [rax+rax*4]
0x1800c73d3  lea     rax, ds:0[rcx*4]
0x1800c73db  lea     rcx, [rax+r8]
0x1800c73df  mov     [rsp+78h+var_40], rax
0x1800c73e4  mov     [rsp+78h+Source], rcx
0x1800c73e9  cmp     rcx, rbx
0x1800c73ec  jnb     loc_1800C74E4
0x1800c73f2  mov     r9, rax; SourceSize
0x1800c73f5  mov     rdx, rbp; DestinationSize
0x1800c73f8  mov     rcx, r10; Destination
0x1800c73fb  call    cs:__imp_memcpy_s
0x1800c7401  mov     rdx, [rsp+78h+dwBytes]
0x1800c7409  mov     r8, [rsp+78h+Source]; Source
0x1800c740e  mov     [rdi+20h], rdx
0x1800c7412  mov     eax, [r15+4]
0x1800c7416  lea     rcx, [rax+rax]
0x1800c741a  lea     r15, [r8+rcx]
0x1800c741e  mov     [rsp+78h+dwBytes], rcx
0x1800c7426  cmp     r15, rbx
0x1800c7429  ja      short loc_1800C7487
0x1800c742b  mov     rax, [rsp+78h+var_40]
0x1800c7430  mov     r9, rcx; SourceSize
0x1800c7433  sub     rbp, rax
0x1800c7436  lea     rbx, [rax+rdx]
0x1800c743a  mov     rdx, rbp; DestinationSize
0x1800c743d  mov     rcx, rbx; Destination
0x1800c7440  call    cs:__imp_memcpy_s
0x1800c7446  mov     rax, [rsp+78h+dwBytes]
0x1800c744e  lea     ecx, [rsi-1]
0x1800c7451  mov     r8d, [rsp+78h+arg_8]
0x1800c7459  sub     rbp, rax
0x1800c745c  xor     edx, edx
0x1800c745e  mov     [rdi+28h], rbx
0x1800c7462  cmp     r8d, ecx
0x1800c7465  lea     r10, [rax+rbx]
0x1800c7469  lea     rax, [rdi+40h]
0x1800c746d  mov     [rsp+78h+dwBytes], r10
0x1800c7475  cmovnz  rdx, rax
0x1800c7479  inc     r8d
0x1800c747c  mov     [rdi], rdx
0x1800c747f  mov     rdi, rdx
0x1800c7482  jmp     loc_1800C737E
0x1800c7487  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c748d  cmp     ecx, 0FFFFFFFFh
0x1800c7490  jz      short loc_1800C74A4
0x1800c7492  lea     r8, aPhonebookentry_6; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7499  mov     edx, 0Ch; dwFlags
0x1800c749e  call    cs:__imp_TracePrintfExA
0x1800c74a4  mov     r9d, 6Fh ; 'o'
0x1800c74aa  mov     edi, r9d
0x1800c74ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c74b4  lea     rsi, WPP_GLOBAL_Control
0x1800c74bb  cmp     rcx, rsi
0x1800c74be  jz      loc_1800C758E
0x1800c74c4  test    dword ptr [rcx+1Ch], 1000h
0x1800c74cb  jz      loc_1800C758E
0x1800c74d1  cmp     byte ptr [rcx+19h], 2
0x1800c74d5  jb      loc_1800C758E
0x1800c74db  lea     edx, [r9+20h]
0x1800c74df  jmp     loc_1800C757E
0x1800c74e4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c74ea  cmp     ecx, 0FFFFFFFFh
0x1800c74ed  jz      short loc_1800C7501
0x1800c74ef  lea     r8, aPhonebookentry_1; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c74f6  mov     edx, 0Ch; dwFlags
0x1800c74fb  call    cs:__imp_TracePrintfExA
0x1800c7501  mov     r9d, 6Fh ; 'o'
0x1800c7507  mov     edi, r9d
0x1800c750a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7511  lea     rsi, WPP_GLOBAL_Control
0x1800c7518  cmp     rcx, rsi
0x1800c751b  jz      short loc_1800C758E
0x1800c751d  test    dword ptr [rcx+1Ch], 1000h
0x1800c7524  jz      short loc_1800C758E
0x1800c7526  cmp     byte ptr [rcx+19h], 2
0x1800c752a  jb      short loc_1800C758E
0x1800c752c  lea     edx, [r9+1Fh]
0x1800c7530  jmp     short loc_1800C757E
0x1800c7532  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c7538  cmp     ecx, 0FFFFFFFFh
0x1800c753b  jz      short loc_1800C754F
0x1800c753d  lea     r8, aPhonebookentry_4; "PhonebookEntryToRasEntryAdvanced - NRPT"...
0x1800c7544  mov     edx, 0Ch; dwFlags
0x1800c7549  call    cs:__imp_TracePrintfExA
0x1800c754f  mov     r9d, 6Fh ; 'o'
0x1800c7555  mov     edi, r9d
0x1800c7558  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c755f  lea     rsi, WPP_GLOBAL_Control
0x1800c7566  cmp     rcx, rsi
0x1800c7569  jz      short loc_1800C758E
0x1800c756b  test    dword ptr [rcx+1Ch], 1000h
0x1800c7572  jz      short loc_1800C758E
0x1800c7574  cmp     byte ptr [rcx+19h], 2
0x1800c7578  jb      short loc_1800C758E
0x1800c757a  lea     edx, [r9+1Eh]
0x1800c757e  mov     rcx, [rcx+10h]
0x1800c7582  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c7589  call    WPP_SF_d
0x1800c758e  mov     rcx, r14; hMem
0x1800c7591  call    cs:__imp_GlobalFree
0x1800c7597  jmp     short loc_1800C75B7
0x1800c7599  mov     rax, [rsp+78h+arg_20]
0x1800c75a1  xor     edi, edi
0x1800c75a3  mov     [rax], esi
0x1800c75a5  lea     rsi, WPP_GLOBAL_Control
0x1800c75ac  mov     rax, [rsp+78h+arg_18]
0x1800c75b4  mov     [rax], r14
0x1800c75b7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c75be  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c75c4  cmp     ecx, 0FFFFFFFFh
0x1800c75c7  jz      short loc_1800C75E5
0x1800c75c9  mov     r9d, edi
0x1800c75cc  lea     r8, aNrptblobtonrpt; "NrptBlobToNrptRuleList: exiting with er"...
0x1800c75d3  mov     edx, 0Ch; dwFlags
0x1800c75d8  call    cs:__imp_TracePrintfExA
0x1800c75de  mov     rbx, cs:WPP_GLOBAL_Control
0x1800c75e5  cmp     rbx, rsi
0x1800c75e8  jz      short loc_1800C7611
0x1800c75ea  test    dword ptr [rbx+1Ch], 1000h
0x1800c75f1  jz      short loc_1800C7611
0x1800c75f3  cmp     byte ptr [rbx+19h], 6
0x1800c75f7  jb      short loc_1800C7611
0x1800c75f9  mov     rcx, [rbx+10h]
0x1800c75fd  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c7604  mov     edx, 90h
0x1800c7609  mov     r9d, edi
0x1800c760c  call    WPP_SF_d
0x1800c7611  mov     rbx, [rsp+78h+arg_10]
0x1800c7619  mov     eax, edi
0x1800c761b  add     rsp, 40h
  ... truncated ...
```
