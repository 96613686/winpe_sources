# CopyIniFormToFormInfo(_INIFORM *,ulong,uchar *,unsigned __int64,uchar * const)

- ea: `0x180012690`
- end: `0x180012a2b`
- name: `?CopyIniFormToFormInfo@@YAPEAEPEAU_INIFORM@@KPEAE_KQEAE@Z`
- size: `923`
- prototype: `unsigned __int8 *__fastcall(struct _INIFORM *, unsigned int, unsigned __int8 *, unsigned __int64, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180094340`
- `0x180095034`

## callees

- `0x180012690`
- `0x180046650`
- `0x180047318`
- `0x18005481c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800127cd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800127cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012905`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001298b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001299b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012905`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001298b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001299b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a1e`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800127e9`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180012a02`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800127e9`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180012a02`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800129c0`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800129c0`
- `SPOOLSS!DllFreeSplStr` at `0x1800127d9`
- `SPOOLSS!DllFreeSplStr` at `0x1800127d9`
- `SPOOLSS!DllFreeSplMem` at `0x180012856`
- `SPOOLSS!DllFreeSplMem` at `0x180012875`
- `SPOOLSS!DllFreeSplMem` at `0x180012a0e`
- `SPOOLSS!DllFreeSplMem` at `0x180012856`
- `SPOOLSS!DllFreeSplMem` at `0x180012875`
- `SPOOLSS!DllFreeSplMem` at `0x180012a0e`
- `SPOOLSS!DllAllocSplMem` at `0x180012713`
- `SPOOLSS!DllAllocSplMem` at `0x180012922`
- `SPOOLSS!DllAllocSplMem` at `0x180012713`
- `SPOOLSS!DllAllocSplMem` at `0x180012922`
- `SPOOLSS!AllocSplStr` at `0x180012790`
- `SPOOLSS!AllocSplStr` at `0x1800127bb`
- `SPOOLSS!AllocSplStr` at `0x1800129ef`
- `SPOOLSS!AllocSplStr` at `0x180012790`
- `SPOOLSS!AllocSplStr` at `0x1800127bb`
- `SPOOLSS!AllocSplStr` at `0x1800129ef`
- `SPOOLSS!PackStrings` at `0x18001282d`
- `SPOOLSS!PackStrings` at `0x180012948`
- `SPOOLSS!PackStrings` at `0x18001282d`
- `SPOOLSS!PackStrings` at `0x180012948`

## pseudocode

```c
unsigned __int8 *__fastcall CopyIniFormToFormInfo(
        struct _INIFORM *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned __int64 a4,
        unsigned __int8 *const a5)
{
  unsigned __int8 *v5; // r13
  int v8; // ebx
  __int64 v9; // r14
  int v10; // edx
  _QWORD *v11; // r12
  _BYTE *v12; // rdx
  __int64 v13; // r15
  __int64 v14; // rax
  size_t v16; // r8
  unsigned __int8 *v17; // rax
  _WORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rsi
  wchar_t *v21; // rax
  wchar_t *v22; // r14
  LANGID ThreadUILanguage; // cx
  __int64 v24; // rax
  __int64 v25; // rsi
  __int64 v27; // r14
  const WCHAR *v28; // rcx
  __int64 v29; // [rsp+20h] [rbp-268h]
  unsigned __int8 *v30; // [rsp+28h] [rbp-260h]
  WCHAR pszOutBuf[264]; // [rsp+30h] [rbp-258h] BYREF

  v5 = a5;
  if ( a1 && a3 && a5 )
  {
    if ( a2 == 1 )
    {
      if ( a4 < 0x28 )
      {
LABEL_40:
        SetLastError(0x7Au);
        return 0;
      }
      v9 = 0;
    }
    else
    {
      if ( a2 == 2 && a4 < 0x58 )
        goto LABEL_40;
      v8 = 0;
      v9 = 0;
      v10 = a2 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
          return 0;
        v11 = (_QWORD *)DllAllocSplMem(88);
        if ( v11 )
        {
          v12 = (_BYTE *)*((_QWORD *)a1 + 9);
          v13 = 0;
          v29 = 0;
          if ( v12 )
          {
            v14 = -1;
            while ( v12[++v14] != 0 )
              ;
            v16 = (unsigned int)(v14 + 1);
            v5 = &a5[-v16];
            v30 = v5;
            memcpy_0(&a5[-v16], v12, v16);
            v17 = v5;
          }
          else
          {
            v30 = a5;
            v17 = 0;
          }
          *((_QWORD *)a3 + 5) = v17;
          *v11 = *((_QWORD *)a1 + 3);
          v18 = (_WORD *)*((_QWORD *)a1 + 10);
          if ( v18 )
          {
            *((_DWORD *)a3 + 16) = 0;
            if ( *v18 == 64 )
            {
              v19 = AllocSplStr(v18);
              v20 = v19;
              if ( v19 )
              {
                v21 = wcschr((const wchar_t *)(v19 + 2), 0x2Cu);
                v22 = v21;
                if ( v21 )
                {
                  *v21 = 0;
                  v13 = AllocSplStr(v20 + 2);
                  if ( v13 )
                    *((_DWORD *)a3 + 16) = _o__wtoi(v22 + 1);
                }
                DllFreeSplStr(v20);
                v5 = v30;
              }
            }
          }
          v11[1] = v13;
          ThreadUILanguage = GetThreadUILanguage();
          *((_WORD *)a3 + 40) = ThreadUILanguage;
          v24 = *((_QWORD *)a1 + 11);
          v25 = 0;
          while ( v24 )
          {
            if ( *(_WORD *)v24 == ThreadUILanguage )
            {
              v25 = *(_QWORD *)(v24 + 8);
              break;
            }
            v24 = *(_QWORD *)(v24 + 16);
          }
          if ( !v25 )
          {
            v28 = (const WCHAR *)*((_QWORD *)a1 + 10);
            if ( !v28 )
              goto LABEL_53;
            v29 = 0;
            *((_WORD *)a3 + 40) = 0;
            v27 = 0;
            if ( SHLoadIndirectString(v28, pszOutBuf, 0x104u, 0) >= 0 )
            {
              v29 = AllocSplStr(pszOutBuf);
              v27 = v29;
              if ( v29 )
                *((_WORD *)a3 + 40) = GetThreadUILanguage();
            }
            v25 = v27;
            if ( !v27 )
LABEL_53:
              *((_WORD *)a3 + 40) = 0;
          }
          v11[2] = v25;
          v9 = PackStrings(v11, a3, "\b", v5);
          if ( v9 )
          {
            *((_DWORD *)a3 + 12) = 0;
            if ( v13 )
            {
              *((_DWORD *)a3 + 12) = 2;
              v8 = 2;
            }
            if ( v25 )
            {
              v8 |= 4u;
              *((_DWORD *)a3 + 12) = v8;
            }
            if ( !v8 )
              *((_DWORD *)a3 + 12) = 1;
            *(_DWORD *)a3 = *((_DWORD *)a1 + 15);
            *((_QWORD *)a3 + 2) = *(_QWORD *)((char *)a1 + 36);
            *(_OWORD *)(a3 + 24) = *(_OWORD *)((char *)a1 + 44);
          }
          else
          {
            SetLastError(0x57u);
          }
          if ( v13 )
            DllFreeSplMem(v13);
          if ( v29 )
            DllFreeSplMem(v29);
          goto LABEL_31;
        }
        goto LABEL_49;
      }
    }
    v11 = (_QWORD *)DllAllocSplMem(40);
    if ( v11 )
    {
      *v11 = *((_QWORD *)a1 + 3);
      v9 = PackStrings(v11, a3, &FormInfo1Strings, a5);
      if ( v9 )
      {
        *(_DWORD *)a3 = *((_DWORD *)a1 + 15);
        *((_QWORD *)a3 + 2) = *(_QWORD *)((char *)a1 + 36);
        *(_OWORD *)(a3 + 24) = *(_OWORD *)((char *)a1 + 44);
      }
      else
      {
        SetLastError(0x57u);
      }
      goto LABEL_31;
    }
LABEL_49:
    SetLastError(8u);
LABEL_31:
    DllFreeSplMem(v11);
    return (unsigned __int8 *)v9;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180012690  mov     r11, rsp
0x180012693  push    rbp
0x180012694  push    rdi
0x180012695  push    r13
0x180012697  sub     rsp, 270h
0x18001269e  mov     rax, cs:__security_cookie
0x1800126a5  xor     rax, rsp
0x1800126a8  mov     [rsp+288h+var_48], rax
0x1800126b0  mov     r13, [rsp+288h+arg_20]
0x1800126b8  mov     rdi, r8
0x1800126bb  mov     rbp, rcx
0x1800126be  test    rcx, rcx
0x1800126c1  jz      loc_180012A19
0x1800126c7  test    r8, r8
0x1800126ca  jz      loc_180012A19
0x1800126d0  test    r13, r13
0x1800126d3  jz      loc_180012A19
0x1800126d9  mov     [r11+10h], rbx
0x1800126dd  mov     [r11-28h], r12
0x1800126e1  mov     [r11-30h], r14
0x1800126e5  cmp     edx, 1
0x1800126e8  jz      loc_180012912
0x1800126ee  cmp     edx, 2
0x1800126f1  jz      loc_1800128F6
0x1800126f7  xor     ebx, ebx
0x1800126f9  mov     r14d, ebx
0x1800126fc  sub     edx, 1
0x1800126ff  jz      loc_18001291D
0x180012705  cmp     edx, 1
0x180012708  jnz     loc_18001290B
0x18001270e  mov     ecx, 58h ; 'X'
0x180012713  call    cs:__imp_DllAllocSplMem
0x180012719  mov     r12, rax
0x18001271c  test    rax, rax
0x18001271f  jz      loc_180012986
0x180012725  mov     rdx, [rbp+48h]; Src
0x180012729  mov     [rsp+288h+var_20], rsi
0x180012731  mov     [rsp+288h+var_38], r15
0x180012739  mov     r15d, ebx
0x18001273c  mov     [rsp+288h+var_268], rbx
0x180012741  test    rdx, rdx
0x180012744  jz      loc_180012979
0x18001274a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012751  cmp     [rdx+rax+1], bl
0x180012755  lea     rax, [rax+1]
0x180012759  jnz     short loc_180012751
0x18001275b  lea     r8d, [rax+1]; Size
0x18001275f  sub     r13, r8
0x180012762  mov     rcx, r13; void *
0x180012765  mov     [rsp+288h+var_260], r13
0x18001276a  call    memcpy_0
0x18001276f  mov     rax, r13
0x180012772  mov     [rdi+28h], rax
0x180012776  mov     rax, [rbp+18h]
0x18001277a  mov     [r12], rax
0x18001277e  mov     rcx, [rbp+50h]
0x180012782  test    rcx, rcx
0x180012785  jz      short loc_1800127E4
0x180012787  mov     [rdi+40h], ebx
0x18001278a  cmp     word ptr [rcx], 40h ; '@'
0x18001278e  jnz     short loc_1800127E4
0x180012790  call    cs:__imp_AllocSplStr
0x180012796  mov     rsi, rax
0x180012799  test    rax, rax
0x18001279c  jz      short loc_1800127E4
0x18001279e  mov     edx, 2Ch ; ','; Ch
0x1800127a3  lea     rcx, [rax+2]; Str
0x1800127a7  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x1800127ac  mov     r14, rax
0x1800127af  test    rax, rax
0x1800127b2  jz      short loc_1800127D6
0x1800127b4  lea     rcx, [rsi+2]
0x1800127b8  mov     [rax], bx
0x1800127bb  call    cs:__imp_AllocSplStr
0x1800127c1  mov     r15, rax
0x1800127c4  test    rax, rax
0x1800127c7  jz      short loc_1800127D6
0x1800127c9  lea     rcx, [r14+2]
0x1800127cd  call    cs:__imp__o__wtoi
0x1800127d3  mov     [rdi+40h], eax
0x1800127d6  mov     rcx, rsi
0x1800127d9  call    cs:__imp_DllFreeSplStr
0x1800127df  mov     r13, [rsp+288h+var_260]
0x1800127e4  mov     [r12+8], r15
0x1800127e9  call    cs:__imp_GetThreadUILanguage
0x1800127ef  movzx   ecx, ax
0x1800127f2  mov     [rdi+50h], ax
0x1800127f6  mov     rax, [rbp+58h]
0x1800127fa  mov     rsi, rbx
0x1800127fd  test    rax, rax
0x180012800  jz      short loc_18001280F
0x180012802  cmp     [rax], cx
0x180012805  jnz     loc_180012970
0x18001280b  mov     rsi, [rax+8]
0x18001280f  test    rsi, rsi
0x180012812  jz      loc_1800129DF
0x180012818  mov     r9, r13
0x18001281b  mov     [r12+10h], rsi
0x180012820  lea     r8, ?FormInfo2Strings@@3QBKB; "\b"
0x180012827  mov     rdx, rdi
0x18001282a  mov     rcx, r12
0x18001282d  call    cs:__imp_PackStrings
0x180012833  mov     r14, rax
0x180012836  test    rax, rax
0x180012839  jnz     short loc_1800128B2
0x18001283b  mov     ecx, 57h ; 'W'; dwErrCode
0x180012840  call    cs:__imp_SetLastError
0x180012846  mov     rsi, [rsp+288h+var_20]
0x18001284e  test    r15, r15
0x180012851  jz      short loc_18001285C
0x180012853  mov     rcx, r15
0x180012856  call    cs:__imp_DllFreeSplMem
0x18001285c  mov     rcx, [rsp+288h+var_268]
0x180012861  mov     r15, [rsp+288h+var_38]
0x180012869  test    rcx, rcx
0x18001286c  jnz     loc_180012A0E
0x180012872  mov     rcx, r12
0x180012875  call    cs:__imp_DllFreeSplMem
0x18001287b  mov     rax, r14
0x18001287e  mov     r12, [rsp+288h+var_28]
0x180012886  mov     rbx, [rsp+288h+arg_8]
0x18001288e  mov     r14, [rsp+288h+var_30]
0x180012896  mov     rcx, [rsp+288h+var_48]
0x18001289e  xor     rcx, rsp; StackCookie
0x1800128a1  call    __security_check_cookie
0x1800128a6  add     rsp, 270h
0x1800128ad  pop     r13
0x1800128af  pop     rdi
0x1800128b0  pop     rbp
0x1800128b1  retn
0x1800128b2  mov     [rdi+30h], ebx
0x1800128b5  test    r15, r15
0x1800128b8  jz      short loc_1800128C6
0x1800128ba  mov     dword ptr [rdi+30h], 2
0x1800128c1  mov     ebx, 2
0x1800128c6  test    rsi, rsi
0x1800128c9  jz      short loc_1800128D1
0x1800128cb  or      ebx, 4
0x1800128ce  mov     [rdi+30h], ebx
0x1800128d1  test    ebx, ebx
0x1800128d3  jnz     short loc_1800128DC
0x1800128d5  mov     dword ptr [rdi+30h], 1
0x1800128dc  mov     eax, [rbp+3Ch]
0x1800128df  mov     [rdi], eax
0x1800128e1  mov     rax, [rbp+24h]
0x1800128e5  mov     [rdi+10h], rax
0x1800128e9  movups  xmm0, xmmword ptr [rbp+2Ch]
0x1800128ed  movups  xmmword ptr [rdi+18h], xmm0
0x1800128f1  jmp     loc_180012846
0x1800128f6  cmp     r9, 58h ; 'X'
0x1800128fa  jnb     loc_1800126F7
0x180012900  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180012905  call    cs:__imp_SetLastError
0x18001290b  xor     eax, eax
0x18001290d  jmp     loc_18001287E
0x180012912  cmp     r9, 28h ; '('
0x180012916  jb      short loc_180012900
0x180012918  xor     ebx, ebx
0x18001291a  mov     r14d, ebx
0x18001291d  mov     ecx, 28h ; '('
0x180012922  call    cs:__imp_DllAllocSplMem
0x180012928  mov     r12, rax
0x18001292b  test    rax, rax
0x18001292e  jz      short loc_180012986
0x180012930  mov     rax, [rbp+18h]
0x180012934  lea     r8, ?FormInfo1Strings@@3QBKB; ulong const near * const FormInfo1Strings
0x18001293b  mov     r9, r13
0x18001293e  mov     [r12], rax
0x180012942  mov     rdx, rdi
0x180012945  mov     rcx, r12
0x180012948  call    cs:__imp_PackStrings
0x18001294e  mov     r14, rax
0x180012951  test    rax, rax
0x180012954  jz      short loc_180012996
0x180012956  mov     eax, [rbp+3Ch]
0x180012959  mov     [rdi], eax
0x18001295b  mov     rax, [rbp+24h]
0x18001295f  mov     [rdi+10h], rax
0x180012963  movups  xmm0, xmmword ptr [rbp+2Ch]
0x180012967  movups  xmmword ptr [rdi+18h], xmm0
0x18001296b  jmp     loc_180012872
0x180012970  mov     rax, [rax+10h]
0x180012974  jmp     loc_1800127FD
0x180012979  mov     [rsp+288h+var_260], r13
0x18001297e  mov     rax, rbx
0x180012981  jmp     loc_180012772
0x180012986  mov     ecx, 8; dwErrCode
0x18001298b  call    cs:__imp_SetLastError
0x180012991  jmp     loc_180012872
0x180012996  mov     ecx, 57h ; 'W'; dwErrCode
0x18001299b  call    cs:__imp_SetLastError
0x1800129a1  jmp     loc_180012872
0x1800129a6  xor     r9d, r9d; ppvReserved
0x1800129a9  mov     [rsp+288h+var_268], rbx
0x1800129ae  mov     r8d, 104h; cchOutBuf
0x1800129b4  mov     [rdi+50h], bx
0x1800129b8  lea     rdx, [rsp+288h+pszOutBuf]; pszOutBuf
0x1800129bd  mov     r14, rbx
0x1800129c0  call    cs:__imp_SHLoadIndirectString
0x1800129c6  test    eax, eax
0x1800129c8  jns     short loc_1800129EA
0x1800129ca  mov     rsi, r14
0x1800129cd  test    r14, r14
0x1800129d0  jnz     loc_180012818
0x1800129d6  mov     [rdi+50h], bx
0x1800129da  jmp     loc_180012818
0x1800129df  mov     rcx, [rbp+50h]; pszSource
0x1800129e3  test    rcx, rcx
0x1800129e6  jz      short loc_1800129D6
0x1800129e8  jmp     short loc_1800129A6
0x1800129ea  lea     rcx, [rsp+288h+pszOutBuf]
0x1800129ef  call    cs:__imp_AllocSplStr
0x1800129f5  mov     [rsp+288h+var_268], rax
0x1800129fa  mov     r14, rax
0x1800129fd  test    rax, rax
0x180012a00  jz      short loc_1800129CA
0x180012a02  call    cs:__imp_GetThreadUILanguage
0x180012a08  mov     [rdi+50h], ax
0x180012a0c  jmp     short loc_1800129CA
0x180012a0e  call    cs:__imp_DllFreeSplMem
0x180012a14  jmp     loc_180012872
0x180012a19  mov     ecx, 57h ; 'W'; dwErrCode
0x180012a1e  call    cs:__imp_SetLastError
0x180012a24  xor     eax, eax
0x180012a26  jmp     loc_180012896
```
