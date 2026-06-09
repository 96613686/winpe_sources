# SaBlob_CreateFromRecords

- ea: `0x180015310`
- end: `0x180015603`
- name: `SaBlob_CreateFromRecords`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180016120`

## callees

- `0x180004410`
- `0x180015310`
- `0x18001560c`
- `0x18001571c`
- `0x1800164fc`
- `0x18001671c`
- `0x180020c40`
- `0x180022bd2`
- `0x18002a8b4`
- `0x180038118`
- `0x18003847c`
- `0x180038ffc`
- `0x18003ae8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015434`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155d6`

## string_xrefs

- `0x1800154a7`: `SaBlob after CreateFromRecords():`

## pseudocode

```c
__int64 __fastcall SaBlob_CreateFromRecords(__int64 *a1, __int64 a2, __int16 a3, _DWORD *a4, _DWORD *a5)
{
  __int64 *v6; // rbp
  unsigned int v7; // r14d
  __int64 *i; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // al
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rbx
  DWORD LastError; // edi
  __int64 v19; // rax
  _OWORD v20[8]; // [rsp+40h] [rbp-88h] BYREF

  v6 = 0;
  v7 = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qqqq(a1, 18, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, 0, a1, a4, a5);
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  for ( i = a1; i; i = (__int64 *)*i )
  {
    if ( (*((_DWORD *)i + 5) & 3u) <= 1 )
    {
      v11 = *((unsigned __int16 *)i + 8);
      if ( (unsigned int)v11 <= 0x22 )
      {
        v12 = 0x410000002LL;
        if ( _bittest64(&v12, v11) )
        {
          ++v7;
          if ( !v6 )
            v6 = i;
          if ( a4 && a5 && (_DWORD)v11 != 34 )
          {
            if ( (_WORD)v11 == 1 )
            {
              *a4 = *((_DWORD *)i + 6);
            }
            else
            {
              if ( *((_WORD *)i + 16)
                || *((_WORD *)i + 17)
                || *((_WORD *)i + 18)
                || *((_WORD *)i + 19)
                || *((_WORD *)i + 20)
                || (v13 = 1, *((_WORD *)i + 21) != 0xFFFF) )
              {
                v13 = 0;
              }
              v14 = *((_DWORD *)i + 6);
              if ( v13 )
                *a4 = v14;
              else
                *a5 = v14;
            }
          }
        }
      }
    }
  }
  v15 = SaBlob_Create(v7);
  v16 = v15;
  if ( v15 )
  {
    LastError = SaBlob_WriteRecords(v15, a1);
    if ( LastError )
    {
      if ( !*(_QWORD *)v16 && !*(_DWORD *)(v16 + 24) )
      {
        v19 = *(_QWORD *)(v16 + 8);
        if ( !v19 || !*(_DWORD *)(v19 + 4) )
          goto LABEL_54;
      }
      LastError = 0;
    }
    if ( a1 && (*((_WORD *)a1 + 8) == 12 || a3 == 12 && *((_WORD *)a1 + 8) == 5 && (*((_DWORD *)a1 + 5) & 3) == 1) )
    {
      memset_0(v20, 0, 0x40u);
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_S(1025, 19, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, a1[1]);
      if ( (unsigned int)DnsStringToDnsAddr(v20) )
      {
        SaBlob_WriteAddress(v16, v20);
        LastError = 0;
      }
    }
    if ( !*(_QWORD *)v16 && v6 )
      LastError = SaBlob_WriteNameOrAlias(v16, (_WORD *)v6[1], 0);
    Print_SaBlob("SaBlob after CreateFromRecords():", v16);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 21, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, v16);
    return v16;
  }
LABEL_54:
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_d(1025, 20, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, LastError);
  SaBlob_Free(v16);
  v16 = 0;
  SetLastError(LastError);
  return v16;
}

```

## disassembly

```asm
0x180015310  push    rbx
0x180015312  push    rbp
0x180015313  push    rsi
0x180015314  push    rdi
0x180015315  push    r12
0x180015317  push    r13
0x180015319  push    r14
0x18001531b  push    r15
0x18001531d  sub     rsp, 88h
0x180015324  xor     r12d, r12d
0x180015327  mov     rbx, r9
0x18001532a  mov     ebp, r12d
0x18001532d  mov     r14d, r12d
0x180015330  movzx   r15d, r8w
0x180015334  mov     rsi, rcx
0x180015337  test    byte ptr cs:xmmword_180063D60, 2
0x18001533e  mov     rdi, [rsp+0C8h+arg_20]
0x180015346  jnz     loc_1800154E6
0x18001534c  test    rbx, rbx
0x18001534f  jz      short loc_180015354
0x180015351  mov     [rbx], r12d
0x180015354  test    rdi, rdi
0x180015357  jz      short loc_18001535C
0x180015359  mov     [rdi], r12d
0x18001535c  mov     rcx, rsi
0x18001535f  mov     r13d, 1
0x180015365  test    rsi, rsi
0x180015368  jz      loc_18001541E
0x18001536e  mov     eax, [rcx+14h]
0x180015371  and     al, 3
0x180015373  cmp     al, r13b
0x180015376  ja      loc_180015412
0x18001537c  movzx   edx, word ptr [rcx+10h]
0x180015380  cmp     edx, 22h ; '"'
0x180015383  ja      loc_180015412
0x180015389  mov     r8, 410000002h
0x180015393  bt      r8, rdx
0x180015397  jnb     short loc_180015412
0x180015399  add     r14d, r13d
0x18001539c  test    rbp, rbp
0x18001539f  cmovz   rbp, rcx
0x1800153a3  test    rbx, rbx
0x1800153a6  jz      short loc_180015412
0x1800153a8  test    rdi, rdi
0x1800153ab  jz      short loc_180015412
0x1800153ad  cmp     edx, 22h ; '"'
0x1800153b0  jz      short loc_180015412
0x1800153b2  cmp     dx, r13w
0x1800153b6  jz      loc_1800154B5
0x1800153bc  cmp     [rcx+20h], r12w
0x1800153c1  jnz     loc_1800154C6
0x1800153c7  cmp     [rcx+22h], r12w
0x1800153cc  jnz     loc_1800154C6
0x1800153d2  cmp     [rcx+24h], r12w
0x1800153d7  jnz     loc_1800154C6
0x1800153dd  cmp     [rcx+26h], r12w
0x1800153e2  jnz     loc_1800154C6
0x1800153e8  cmp     [rcx+28h], r12w
0x1800153ed  jnz     loc_1800154C6
0x1800153f3  mov     eax, 0FFFFh
0x1800153f8  cmp     [rcx+2Ah], ax
0x1800153fc  mov     al, r13b
0x1800153ff  jnz     loc_1800154C6
0x180015405  mov     edx, [rcx+18h]
0x180015408  test    al, al
0x18001540a  jz      loc_1800154BF
0x180015410  mov     [rbx], edx
0x180015412  mov     rcx, [rcx]
0x180015415  test    rcx, rcx
0x180015418  jnz     loc_18001536E
0x18001541e  mov     ecx, r14d
0x180015421  call    SaBlob_Create
0x180015426  mov     rbx, rax
0x180015429  mov     r14d, 401h
0x18001542f  test    rax, rax
0x180015432  jnz     short loc_18001546F
0x180015434  call    cs:__imp_GetLastError
0x18001543b  nop     dword ptr [rax+rax+00h]
0x180015440  mov     edi, eax
0x180015442  test    edi, edi
0x180015444  jnz     loc_1800155A9
0x18001544a  test    byte ptr cs:xmmword_180063D60, 2
0x180015451  jnz     loc_1800155E7
0x180015457  mov     rax, rbx
0x18001545a  add     rsp, 88h
0x180015461  pop     r15
0x180015463  pop     r14
0x180015465  pop     r13
0x180015467  pop     r12
0x180015469  pop     rdi
0x18001546a  pop     rsi
0x18001546b  pop     rbp
0x18001546c  pop     rbx
0x18001546d  retn
0x18001546f  mov     rdx, rsi
0x180015472  mov     rcx, rbx
0x180015475  call    SaBlob_WriteRecords
0x18001547a  mov     edi, eax
0x18001547c  test    eax, eax
0x18001547e  jnz     loc_18001550E
0x180015484  test    rsi, rsi
0x180015487  jz      short loc_18001549F
0x180015489  cmp     word ptr [rsi+10h], 0Ch
0x18001548e  jz      loc_18001554D
0x180015494  cmp     r15w, 0Ch
0x180015499  jz      loc_180015534
0x18001549f  cmp     [rbx], r12
0x1800154a2  jz      short loc_1800154CE
0x1800154a4  mov     rdx, rbx
0x1800154a7  lea     rcx, aSablobAfterCre; "SaBlob after CreateFromRecords():"
0x1800154ae  call    Print_SaBlob
0x1800154b3  jmp     short loc_180015442
0x1800154b5  mov     eax, [rcx+18h]
0x1800154b8  mov     [rbx], eax
0x1800154ba  jmp     loc_180015412
0x1800154bf  mov     [rdi], edx
0x1800154c1  jmp     loc_180015412
0x1800154c6  mov     al, r12b
0x1800154c9  jmp     loc_180015405
0x1800154ce  test    rbp, rbp
0x1800154d1  jz      short loc_1800154A4
0x1800154d3  mov     rdx, [rbp+8]
0x1800154d7  xor     r8d, r8d
0x1800154da  mov     rcx, rbx
0x1800154dd  call    SaBlob_WriteNameOrAlias
0x1800154e2  mov     edi, eax
0x1800154e4  jmp     short loc_1800154A4
0x1800154e6  mov     [rsp+0C8h+var_98], rdi
0x1800154eb  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800154f2  mov     [rsp+0C8h+var_A0], rbx
0x1800154f7  mov     edx, 12h
0x1800154fc  xor     r9d, r9d
0x1800154ff  mov     [rsp+0C8h+var_A8], rsi
0x180015504  call    WPP_SF_qqqq
0x180015509  jmp     loc_18001534C
0x18001550e  cmp     [rbx], r12
0x180015511  jnz     short loc_18001552C
0x180015513  cmp     [rbx+18h], r12d
0x180015517  jnz     short loc_18001552C
0x180015519  mov     rax, [rbx+8]
0x18001551d  test    rax, rax
0x180015520  jz      loc_1800155A9
0x180015526  cmp     [rax+4], r12d
0x18001552a  jz      short loc_1800155A9
0x18001552c  mov     edi, r12d
0x18001552f  jmp     loc_180015484
0x180015534  cmp     word ptr [rsi+10h], 5
0x180015539  jnz     loc_18001549F
0x18001553f  mov     eax, [rsi+14h]
0x180015542  and     al, 3
0x180015544  cmp     al, r13b
0x180015547  jnz     loc_18001549F
0x18001554d  xor     edx, edx; Val
0x18001554f  lea     rcx, [rsp+0C8h+var_88]; void *
0x180015554  lea     r8d, [rdx+40h]; Size
0x180015558  call    memset_0
0x18001555d  test    byte ptr cs:xmmword_180063D60, 2
0x180015564  jz      short loc_18001557E
0x180015566  mov     r9, [rsi+8]
0x18001556a  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x180015571  mov     edx, 13h
0x180015576  mov     ecx, r14d
0x180015579  call    WPP_SF_S
0x18001557e  mov     rdx, [rsi+8]
0x180015582  lea     rcx, [rsp+0C8h+var_88]; void *
0x180015587  call    DnsStringToDnsAddr
0x18001558c  test    eax, eax
0x18001558e  jz      loc_18001549F
0x180015594  lea     rdx, [rsp+0C8h+var_88]
0x180015599  mov     rcx, rbx
0x18001559c  call    SaBlob_WriteAddress
0x1800155a1  mov     edi, r12d
0x1800155a4  jmp     loc_18001549F
0x1800155a9  test    byte ptr cs:xmmword_180063D60, 2
0x1800155b0  jz      short loc_1800155C9
0x1800155b2  mov     edx, 14h
0x1800155b7  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800155be  mov     ecx, r14d
0x1800155c1  mov     r9d, edi
0x1800155c4  call    WPP_SF_d
0x1800155c9  mov     rcx, rbx
0x1800155cc  call    SaBlob_Free
0x1800155d1  mov     ecx, edi; dwErrCode
0x1800155d3  mov     rbx, r12
0x1800155d6  call    cs:__imp_SetLastError
0x1800155dd  nop     dword ptr [rax+rax+00h]
0x1800155e2  jmp     loc_180015457
0x1800155e7  mov     edx, 15h
0x1800155ec  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800155f3  mov     ecx, r14d
0x1800155f6  mov     r9, rbx
0x1800155f9  call    WPP_SF_q
0x1800155fe  jmp     loc_180015457
```
