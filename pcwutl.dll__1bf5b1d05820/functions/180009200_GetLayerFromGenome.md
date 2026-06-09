# GetLayerFromGenome

- ea: `0x180009200`
- end: `0x180009519`
- name: `GetLayerFromGenome`
- size: `793`
- prototype: `__int64 __fastcall(LPCWSTR lptstrFilename, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008c38`
- `0x180009200`
- `0x180009af0`
- `0x18000a60c`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180009402`
- `ADVAPI32!RegGetValueW` at `0x180009402`

## string_xrefs

- `0x1800093ef`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\CompatTS`

## pseudocode

```c
__int64 __fastcall GetLayerFromGenome(LPCWSTR lptstrFilename, unsigned __int16 *a2, int *a3)
{
  const unsigned __int16 *v4; // r14
  unsigned int v6; // edi
  int v7; // esi
  __int16 v8; // r15^4
  __int64 v9; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // r8
  unsigned __int16 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int16 *v16; // r8
  const wchar_t *v17; // rcx
  unsigned __int16 *v18; // rcx
  const wchar_t *v19; // rcx
  bool v20; // zf
  const wchar_t *v21; // rcx
  unsigned __int16 *v22; // rcx
  __int64 v23; // rax
  const wchar_t *v24; // rcx
  __int64 v25; // rdx
  unsigned __int16 *v26; // r8
  unsigned __int16 *v27; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v32[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v33[264]; // [rsp+260h] [rbp+160h] BYREF

  v31 = 0;
  v4 = a2;
  pcbData = 0;
  pvData = 0;
  v6 = 0;
  if ( !a2 )
    goto LABEL_54;
  v7 = 0;
  if ( (unsigned int)AhgGetGenome(&v31, lptstrFilename) )
    goto LABEL_52;
  v8 = WORD2(v31);
  if ( BYTE3(v31) != 5 )
  {
    if ( BYTE3(v31) != 6 )
    {
      if ( BYTE3(v31) <= 6u )
        goto LABEL_52;
      v9 = 2147483646;
      v10 = L"WIN8RTM";
      v11 = 260;
      v12 = (unsigned __int16 *)v4;
      do
      {
        if ( !v9 )
          break;
        if ( !*v10 )
          break;
        *v12++ = *v10++;
        --v9;
        --v11;
      }
      while ( v11 );
      v13 = v12 - 1;
      if ( v11 )
        v13 = v12;
      *v13 = 0;
      if ( !v11 )
        goto LABEL_52;
      v6 = 1;
      goto LABEL_50;
    }
    v14 = 260;
    v15 = 2147483646;
    v16 = (unsigned __int16 *)v4;
    if ( BYTE2(v31) )
    {
      if ( BYTE2(v31) != 1 )
      {
        v17 = L"WIN8RTM";
        do
        {
          if ( !v15 )
            break;
          if ( !*v17 )
            break;
          *v16++ = *v17++;
          --v15;
          --v14;
        }
        while ( v14 );
        v18 = v16 - 1;
        if ( v14 )
          v18 = v16;
        *v18 = 0;
        if ( v14 )
          v6 = 1;
LABEL_38:
        pcbData = 4;
        if ( RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\CompatTS",
               L"VistaPlus",
               0x10u,
               0,
               &pvData,
               &pcbData) )
        {
          LOBYTE(v7) = (v8 & 0x326) != 0;
        }
        else
        {
          LOBYTE(v7) = pvData == 1;
        }
        goto LABEL_49;
      }
      v19 = L"WIN7RTM";
      do
      {
        if ( !v15 )
          break;
        if ( !*v19 )
          break;
        *v16++ = *v19++;
        --v15;
        --v14;
      }
      while ( v14 );
      v20 = v14 == 0;
      LOBYTE(v6) = v14 != 0;
    }
    else
    {
      v21 = L"VISTASP2";
      do
      {
        if ( !v15 )
          break;
        if ( !*v21 )
          break;
        *v16++ = *v21++;
        --v15;
        --v14;
      }
      while ( v14 );
      v20 = v14 == 0;
      if ( v14 )
        v6 = 1;
    }
    v22 = v16 - 1;
    if ( !v20 )
      v22 = v16;
    *v22 = 0;
    goto LABEL_38;
  }
  v23 = 2147483646;
  v24 = L"WINXPSP3";
  v25 = 260;
  v26 = (unsigned __int16 *)v4;
  do
  {
    if ( !v23 )
      break;
    if ( !*v24 )
      break;
    *v26++ = *v24++;
    --v23;
    --v25;
  }
  while ( v25 );
  v27 = v26 - 1;
  if ( v25 )
    v27 = v26;
  *v27 = 0;
  if ( !v25 )
    goto LABEL_52;
  v6 = 1;
LABEL_49:
  if ( v6 )
  {
LABEL_50:
    if ( (unsigned int)RetrieveFileAndProgramId(lptstrFilename, v33, v32) )
      LogPCWGenomeEvent(lptstrFilename, v4, v7, v33, v32);
  }
LABEL_52:
  if ( a3 )
    *a3 = v7;
LABEL_54:
  if ( !v6 )
    v4 = &word_18001DAC4;
  AslLogCallPrintf(3, "GetLayerFromGenome", 1389, "Layer: %ws", v4);
  return v6;
}

```

## disassembly

```asm
0x180009200  mov     [rsp-8+arg_18], rbx
0x180009205  push    rbp
0x180009206  push    rsi
0x180009207  push    rdi
0x180009208  push    r12
0x18000920a  push    r13
0x18000920c  push    r14
0x18000920e  push    r15
0x180009210  lea     rbp, [rsp-380h]
0x180009218  sub     rsp, 480h
0x18000921f  mov     rax, cs:__security_cookie
0x180009226  xor     rax, rsp
0x180009229  mov     [rbp+3B0h+var_40], rax
0x180009230  xor     r10d, r10d
0x180009233  mov     r13, r8
0x180009236  mov     [rsp+4B0h+var_468], r10
0x18000923b  mov     r14, rdx
0x18000923e  mov     [rsp+4B0h+var_470], r10d
0x180009243  mov     r12, rcx
0x180009246  mov     [rsp+4B0h+var_46C], r10d
0x18000924b  mov     edi, r10d
0x18000924e  test    rdx, rdx
0x180009251  jz      loc_1800094BD
0x180009257  mov     rdx, rcx
0x18000925a  mov     esi, r10d
0x18000925d  lea     rcx, [rsp+4B0h+var_468]
0x180009262  call    AhgGetGenome
0x180009267  xor     r10d, r10d
0x18000926a  test    eax, eax
0x18000926c  jnz     loc_1800094B4
0x180009272  mov     r15, [rsp+4B0h+var_468]
0x180009277  mov     rdx, r15
0x18000927a  shr     rdx, 10h
0x18000927e  movzx   eax, dx
0x180009281  shr     ax, 8
0x180009285  movzx   r8d, al
0x180009289  mov     ecx, r8d
0x18000928c  sub     ecx, 5
0x18000928f  jz      loc_18000942A
0x180009295  cmp     ecx, 1
0x180009298  jz      short loc_1800092FB
0x18000929a  cmp     r8b, 6
0x18000929e  jbe     loc_1800094B4
0x1800092a4  mov     eax, 7FFFFFFEh
0x1800092a9  lea     rcx, aWin8rtm; "WIN8RTM"
0x1800092b0  mov     edx, 104h
0x1800092b5  lea     ebx, [r10+1]
0x1800092b9  mov     r8, r14
0x1800092bc  test    rax, rax
0x1800092bf  jz      short loc_1800092DF
0x1800092c1  movzx   r9d, word ptr [rcx]
0x1800092c5  test    r9w, r9w
0x1800092c9  jz      short loc_1800092DF
0x1800092cb  mov     [r8], r9w
0x1800092cf  add     rcx, 2
0x1800092d3  add     r8, 2
0x1800092d7  sub     rax, rbx
0x1800092da  sub     rdx, rbx
0x1800092dd  jnz     short loc_1800092BC
0x1800092df  test    rdx, rdx
0x1800092e2  lea     rcx, [r8-2]
0x1800092e6  cmovnz  rcx, r8
0x1800092ea  mov     [rcx], r10w
0x1800092ee  jz      loc_1800094B4
0x1800092f4  mov     edi, ebx
0x1800092f6  jmp     loc_18000947D
0x1800092fb  movzx   ecx, dl
0x1800092fe  test    dl, dl
0x180009300  mov     edx, 104h
0x180009305  mov     eax, 7FFFFFFEh
0x18000930a  mov     r8, r14
0x18000930d  mov     ebx, 1
0x180009312  jz      short loc_18000938A
0x180009314  cmp     ecx, ebx
0x180009316  jz      short loc_180009357
0x180009318  lea     rcx, aWin8rtm; "WIN8RTM"
0x18000931f  test    rax, rax
0x180009322  jz      short loc_180009342
0x180009324  movzx   r9d, word ptr [rcx]
0x180009328  test    r9w, r9w
0x18000932c  jz      short loc_180009342
0x18000932e  mov     [r8], r9w
0x180009332  add     rcx, 2
0x180009336  add     r8, 2
0x18000933a  sub     rax, rbx
0x18000933d  sub     rdx, rbx
0x180009340  jnz     short loc_18000931F
0x180009342  test    rdx, rdx
0x180009345  lea     rcx, [r8-2]
0x180009349  cmovnz  rcx, r8
0x18000934d  mov     [rcx], r10w
0x180009351  jz      short loc_1800093C6
0x180009353  mov     edi, ebx
0x180009355  jmp     short loc_1800093C6
0x180009357  lea     rcx, aWin7rtm; "WIN7RTM"
0x18000935e  test    rax, rax
0x180009361  jz      short loc_180009381
0x180009363  movzx   r9d, word ptr [rcx]
0x180009367  test    r9w, r9w
0x18000936b  jz      short loc_180009381
0x18000936d  mov     [r8], r9w
0x180009371  add     rcx, 2
0x180009375  add     r8, 2
0x180009379  sub     rax, rbx
0x18000937c  sub     rdx, rbx
0x18000937f  jnz     short loc_18000935E
0x180009381  test    rdx, rdx
0x180009384  setnz   dil
0x180009388  jmp     short loc_1800093BA
0x18000938a  lea     rcx, aVistasp2; "VISTASP2"
0x180009391  test    rax, rax
0x180009394  jz      short loc_1800093B4
0x180009396  movzx   r9d, word ptr [rcx]
0x18000939a  test    r9w, r9w
0x18000939e  jz      short loc_1800093B4
0x1800093a0  mov     [r8], r9w
0x1800093a4  add     rcx, 2
0x1800093a8  add     r8, 2
0x1800093ac  sub     rax, rbx
0x1800093af  sub     rdx, rbx
0x1800093b2  jnz     short loc_180009391
0x1800093b4  test    rdx, rdx
0x1800093b7  cmovnz  edi, ebx
0x1800093ba  lea     rcx, [r8-2]
0x1800093be  cmovnz  rcx, r8
0x1800093c2  mov     [rcx], r10w
0x1800093c6  lea     rax, [rsp+4B0h+var_470]
0x1800093cb  mov     [rsp+4B0h+var_470], 4
0x1800093d3  mov     [rsp+4B0h+pcbData], rax; pcbData
0x1800093d8  lea     r8, aVistaplus; "VistaPlus"
0x1800093df  lea     rax, [rsp+4B0h+var_46C]
0x1800093e4  mov     r9d, 10h; dwFlags
0x1800093ea  mov     [rsp+4B0h+pvData], rax; pvData
0x1800093ef  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800093f6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800093fd  mov     [rsp+4B0h+pdwType], r10; pdwType
0x180009402  call    cs:__imp_RegGetValueW
0x180009408  xor     r10d, r10d
0x18000940b  test    eax, eax
0x18000940d  jnz     short loc_180009419
0x18000940f  cmp     [rsp+4B0h+var_46C], ebx
0x180009413  setz    sil
0x180009417  jmp     short loc_180009479
0x180009419  shr     r15, 20h
0x18000941d  test    r15d, 326h
0x180009424  setnz   sil
0x180009428  jmp     short loc_180009479
0x18000942a  mov     eax, 7FFFFFFEh
0x18000942f  lea     rcx, aWinxpsp3; "WINXPSP3"
0x180009436  mov     edx, 104h
0x18000943b  mov     r8, r14
0x18000943e  mov     ebx, 1
0x180009443  test    rax, rax
0x180009446  jz      short loc_180009466
0x180009448  movzx   r9d, word ptr [rcx]
0x18000944c  test    r9w, r9w
0x180009450  jz      short loc_180009466
0x180009452  mov     [r8], r9w
0x180009456  add     rcx, 2
0x18000945a  add     r8, 2
0x18000945e  sub     rax, rbx
0x180009461  sub     rdx, rbx
0x180009464  jnz     short loc_180009443
0x180009466  test    rdx, rdx
0x180009469  lea     rcx, [r8-2]
0x18000946d  cmovnz  rcx, r8
0x180009471  mov     [rcx], r10w
0x180009475  jz      short loc_1800094B4
0x180009477  mov     edi, ebx
0x180009479  test    edi, edi
0x18000947b  jz      short loc_1800094B4
0x18000947d  lea     r8, [rsp+4B0h+var_460]
0x180009482  mov     rcx, r12
0x180009485  lea     rdx, [rbp+3B0h+var_250]
0x18000948c  call    RetrieveFileAndProgramId
0x180009491  test    eax, eax
0x180009493  jz      short loc_1800094B4
0x180009495  lea     rax, [rsp+4B0h+var_460]
0x18000949a  mov     r8d, esi; int
0x18000949d  lea     r9, [rbp+3B0h+var_250]; unsigned __int16 *
0x1800094a4  mov     [rsp+4B0h+pdwType], rax; unsigned __int16 *
0x1800094a9  mov     rdx, r14; unsigned __int16 *
0x1800094ac  mov     rcx, r12; lptstrFilename
0x1800094af  call    ?LogPCWGenomeEvent@@YAHPEBG0H00@Z; LogPCWGenomeEvent(ushort const *,ushort const *,int,ushort const *,ushort const *)
0x1800094b4  test    r13, r13
0x1800094b7  jz      short loc_1800094BD
0x1800094b9  mov     [r13+0], esi
0x1800094bd  test    edi, edi
0x1800094bf  lea     rax, word_18001DAC4
0x1800094c6  lea     r9, aLayerWs; "Layer: %ws"
0x1800094cd  mov     r8d, 56Dh
0x1800094d3  cmovz   r14, rax
0x1800094d7  lea     rdx, aGetlayerfromge_0; "GetLayerFromGenome"
0x1800094de  mov     ecx, 3
0x1800094e3  mov     [rsp+4B0h+pdwType], r14
0x1800094e8  call    AslLogCallPrintf
0x1800094ed  mov     eax, edi
0x1800094ef  mov     rcx, [rbp+3B0h+var_40]
0x1800094f6  xor     rcx, rsp; StackCookie
0x1800094f9  call    __security_check_cookie
0x1800094fe  mov     rbx, [rsp+4B0h+arg_18]
0x180009506  add     rsp, 480h
0x18000950d  pop     r15
0x18000950f  pop     r14
0x180009511  pop     r13
0x180009513  pop     r12
0x180009515  pop     rdi
0x180009516  pop     rsi
0x180009517  pop     rbp
0x180009518  retn
```
