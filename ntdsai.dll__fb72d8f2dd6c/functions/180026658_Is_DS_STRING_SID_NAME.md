# Is_DS_STRING_SID_NAME

- ea: `0x180026658`
- end: `0x180026b3f`
- name: `Is_DS_STRING_SID_NAME`
- size: `1255`
- prototype: `__int64 __fastcall(LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800234f0`
- `0x180026620`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001ea60`
- `0x180021aa3`
- `0x18002343c`
- `0x180024f34`
- `0x180026658`
- `0x18002770c`
- `0x1801c4a34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026681`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026681`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800266ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800266ed`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x1800268ec`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18002692c`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x1800268ec`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18002692c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026938`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180453cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180453cd1`
- `ntdll!RtlLengthSid` at `0x180026782`
- `ntdll!RtlLengthSid` at `0x180026782`
- `LSASRV!LsaIForestTrustFindMatch` at `0x180026952`
- `LSASRV!LsaIForestTrustFindMatch` at `0x180026952`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800269b2`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800269b2`

## pseudocode

```c
__int64 __fastcall Is_DS_STRING_SID_NAME(LPCWSTR StringSid, __int128 *a2)
{
  _QWORD *Value; // r13
  int v6; // esi
  void *v7; // r12
  ULONG v8; // ebx
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  unsigned int v11; // r15d
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // ecx
  void *v15; // rax
  int v16; // esi
  int v17; // r8d
  int v18; // r9d
  PSID Sid; // [rsp+50h] [rbp-250h] BYREF
  void *v20; // [rsp+58h] [rbp-248h]
  void *Src[2]; // [rsp+60h] [rbp-240h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-230h] BYREF
  __int128 v23; // [rsp+80h] [rbp-220h] BYREF
  __int128 v24; // [rsp+90h] [rbp-210h]
  __int128 v25; // [rsp+A0h] [rbp-200h]
  __int128 v26; // [rsp+B0h] [rbp-1F0h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-1E0h]
  __int128 v28; // [rsp+D0h] [rbp-1D0h]
  _BYTE v29[168]; // [rsp+E8h] [rbp-1B8h] BYREF
  _BYTE *v30; // [rsp+190h] [rbp-110h]
  _BYTE v31[24]; // [rsp+198h] [rbp-108h] BYREF
  int v32; // [rsp+1B0h] [rbp-F0h]
  int v33; // [rsp+1B8h] [rbp-E8h]
  int *v34; // [rsp+1C0h] [rbp-E0h]
  DWORD cbDomainSid; // [rsp+2B0h] [rbp+10h] BYREF
  int v36; // [rsp+2B8h] [rbp+18h] BYREF
  int v37; // [rsp+2C0h] [rbp+20h] BYREF

  Value = TlsGetValue(dwTSindex);
  Sid = 0;
  memset_0(v29, 0, 0x160u);
  v36 = 655436;
  *(_OWORD *)Src = 0;
  cbDomainSid = 0;
  *((_DWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 3) = 0;
  *((_QWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 5) = 0;
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    CommonParseExit(0, a2);
    return 0;
  }
  v22[1] = Value;
  v6 = 0;
  v7 = 0;
  v20 = 0;
  v31[8] = 73;
  v31[16] = 0;
  v32 = 0;
  v33 = 4;
  v34 = &v36;
  v29[8] = 78;
  v30 = v31;
  v8 = RtlLengthSid(Sid);
  v23 = *a2;
  v24 = a2[1];
  v25 = a2[2];
  v9 = *a2;
  v26 = *a2;
  v27 = v24;
  v10 = v25;
  v28 = v25;
  v11 = Is_SIMPLE_ATTR_NAME(589970, (_DWORD)Sid, v8, (unsigned int)v29, (__int64)&v23);
  v12 = *(_DWORD *)gfADAM;
  if ( *(_DWORD *)gfADAM )
  {
    v13 = 1;
    v14 = 2;
    LODWORD(v27) = 2;
  }
  else
  {
    v13 = Is_SIMPLE_ATTR_NAME(590433, (_DWORD)Sid, v8, (unsigned int)v29, (__int64)&v26);
    v10 = v28;
    v14 = v27;
    v9 = v26;
    v12 = *(_DWORD *)gfADAM;
  }
  if ( v11 && (_DWORD)v24 == 3 || v13 && v14 == 3 )
    goto LABEL_14;
  if ( !v11 )
  {
    if ( !v13 || v14 == 2 )
    {
LABEL_21:
      v13 = 0;
      *((_DWORD *)a2 + 4) = 2;
      if ( !v12 )
      {
        cbDomainSid = 0;
        GetWindowsAccountDomainSid(Sid, 0, &cbDomainSid);
        v7 = (void *)THAlloc_((_DWORD)Value, 1, cbDomainSid, 1, 0, 52298567);
        v20 = v7;
        if ( GetWindowsAccountDomainSid(Sid, v7, &cbDomainSid) )
        {
          if ( (int)LsaIForestTrustFindMatch(0, v7, Src) >= 0 )
          {
            v15 = (void *)THAlloc_((_DWORD)Value, 1, (unsigned int)LOWORD(Src[0]) + 2, 1, 0, 52298589);
            *((_QWORD *)a2 + 4) = v15;
            memcpy_0(v15, Src[1], LOWORD(Src[0]));
            *(_WORD *)(*((_QWORD *)a2 + 4) + 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1)) = 0;
            LsaIFree_LSAPR_UNICODE_STRING_BUFFER(Src);
            *((_DWORD *)a2 + 4) = (*(_DWORD *)a2 & 8 | 0x14u) >> 2;
            v13 = 1;
          }
        }
        else
        {
          SetLastError(0);
          *((_DWORD *)a2 + 4) = 2;
        }
      }
      goto LABEL_50;
    }
LABEL_28:
    if ( v13 && (v14 & 0xFFFFFFFD) != 0 )
    {
      *((_DWORD *)a2 + 4) = v14;
      goto LABEL_50;
    }
    v13 = 1;
    if ( !v11 || (_DWORD)v24 )
    {
      *a2 = v9;
      a2[1] = v27;
      a2[2] = v10;
      v6 = 1;
    }
    else
    {
      *a2 = v23;
      a2[1] = v24;
      a2[2] = v25;
    }
    if ( v12 )
    {
      *((_DWORD *)a2 + 4) = 0;
      goto LABEL_50;
    }
    v37 = 0;
    v22[0] = 0;
    if ( !(unsigned int)DBFindDSName(Value[697], *((_QWORD *)a2 + 3))
      && !(unsigned int)GetAttSecure((_DWORD)Value, 590126, *((_QWORD *)a2 + 3), (unsigned int)&v37, (__int64)v22) )
    {
      if ( *(_DWORD *)v22[0] == 0x10000000 || *(_DWORD *)v22[0] == 268435457 )
      {
        v16 = v6 != 0 ? -12 : -8;
        goto LABEL_49;
      }
      if ( *(_DWORD *)v22[0] == 0x20000000 || *(_DWORD *)v22[0] == 536870913 )
      {
        v16 = 4 * (v6 ^ 1) - 13;
        goto LABEL_49;
      }
      if ( *(_DWORD *)v22[0] == 805306368 || (unsigned int)(*(_DWORD *)v22[0] - 805306369) <= 1 )
      {
        v16 = 4 * (v6 ^ 1) - 11;
LABEL_49:
        *((_DWORD *)a2 + 4) = v16;
        goto LABEL_50;
      }
    }
    v16 = 4 * (v6 ^ 1) - 14;
    goto LABEL_49;
  }
  if ( (_DWORD)v24 || !v13 || v14 )
  {
    if ( !v13 && (_DWORD)v24 == 2 )
      goto LABEL_21;
    if ( (v24 & 0xFFFFFFFD) != 0 )
    {
      v13 = v11;
      *((_DWORD *)a2 + 4) = v24;
      goto LABEL_50;
    }
    goto LABEL_28;
  }
LABEL_14:
  v13 = 1;
  *((_DWORD *)a2 + 4) = 3;
LABEL_50:
  LocalFree(Sid);
  if ( v7 )
    THFreeAux((_DWORD)Value, (_DWORD)v7, v17, v18, 52298715);
  CommonParseExit(1, a2);
  return v13;
}

```

## disassembly

```asm
0x180026658  mov     rax, rsp
0x18002665b  push    rbx
0x18002665c  push    rsi
0x18002665d  push    rdi
0x18002665e  push    r12
0x180026660  push    r13
0x180026662  push    r14
0x180026664  push    r15
0x180026666  sub     rsp, 250h
0x18002666d  movaps  xmmword ptr [rax-48h], xmm6
0x180026671  movaps  xmmword ptr [rax-58h], xmm7
0x180026675  mov     rdi, rdx
0x180026678  mov     rbx, rcx
0x18002667b  mov     ecx, cs:dwTSindex; dwTlsIndex
0x180026681  call    cs:__imp_TlsGetValue
0x180026687  mov     r13, rax
0x18002668a  mov     [rsp+288h+Sid], 0
0x180026693  xor     edx, edx; Val
0x180026695  mov     r8d, 160h; Size
0x18002669b  lea     rcx, [rsp+288h+var_1B8]; void *
0x1800266a3  call    memset_0
0x1800266a8  mov     [rsp+288h+arg_10], 0A004Ch
0x1800266b3  xorps   xmm0, xmm0
0x1800266b6  movups  xmmword ptr [rsp+288h+Src], xmm0
0x1800266bb  mov     [rsp+288h+cbDomainSid], 0
0x1800266c6  mov     dword ptr [rdi+10h], 0
0x1800266cd  mov     qword ptr [rdi+18h], 0
0x1800266d5  mov     qword ptr [rdi+20h], 0
0x1800266dd  mov     qword ptr [rdi+28h], 0
0x1800266e5  lea     rdx, [rsp+288h+Sid]; Sid
0x1800266ea  mov     rcx, rbx; StringSid
0x1800266ed  call    cs:__imp_ConvertStringSidToSidW
0x1800266f3  test    eax, eax
0x1800266f5  jnz     short loc_180026724
0x1800266f7  mov     rdx, rdi
0x1800266fa  xor     ecx, ecx
0x1800266fc  call    CommonParseExit
0x180026701  xor     eax, eax
0x180026703  lea     r11, [rsp+288h+var_38]
0x18002670b  movaps  xmm6, xmmword ptr [r11-10h]
0x180026710  movaps  xmm7, xmmword ptr [r11-20h]
0x180026715  mov     rsp, r11
0x180026718  pop     r15
0x18002671a  pop     r14
0x18002671c  pop     r13
0x18002671e  pop     r12
0x180026720  pop     rdi
0x180026721  pop     rsi
0x180026722  pop     rbx
0x180026723  retn
0x180026724  mov     [rsp+288h+var_228], r13
0x180026729  xor     esi, esi
0x18002672b  xor     r12d, r12d
0x18002672e  mov     [rsp+288h+var_248], r12
0x180026733  mov     [rsp+288h+var_100], 49h ; 'I'
0x18002673b  mov     [rsp+288h+var_F8], sil
0x180026743  mov     [rsp+288h+var_F0], esi
0x18002674a  mov     [rsp+288h+var_E8], 4
0x180026755  lea     rax, [rsp+288h+arg_10]
0x18002675d  mov     [rsp+288h+var_E0], rax
0x180026765  mov     [rsp+288h+var_1B0], 4Eh ; 'N'
0x18002676d  lea     rax, [rsp+288h+var_108]
0x180026775  mov     [rsp+288h+var_110], rax
0x18002677d  mov     rcx, [rsp+288h+Sid]; Sid
0x180026782  call    cs:__imp_RtlLengthSid
0x180026788  mov     ebx, eax
0x18002678a  movups  xmm0, xmmword ptr [rdi]
0x18002678d  movups  [rsp+288h+var_220], xmm0
0x180026792  movups  xmm1, xmmword ptr [rdi+10h]
0x180026796  movups  [rsp+288h+var_210], xmm1
0x18002679b  movups  xmm0, xmmword ptr [rdi+20h]
0x18002679f  movups  [rsp+288h+var_200], xmm0
0x1800267a7  movups  xmm6, xmmword ptr [rdi]
0x1800267aa  movups  [rsp+288h+var_1F0], xmm6
0x1800267b2  movups  [rsp+288h+var_1E0], xmm1
0x1800267ba  movups  xmm7, xmm0
0x1800267bd  movups  [rsp+288h+var_1D0], xmm0
0x1800267c5  lea     rax, [rsp+288h+var_220]
0x1800267ca  mov     [rsp+288h+var_268], rax
0x1800267cf  lea     r9, [rsp+288h+var_1B8]
0x1800267d7  mov     r8d, ebx
0x1800267da  mov     rdx, [rsp+288h+Sid]
0x1800267df  mov     ecx, 90092h
0x1800267e4  call    Is_SIMPLE_ATTR_NAME
0x1800267e9  mov     r15d, eax
0x1800267ec  mov     edx, cs:gfADAM
0x1800267f2  test    edx, edx
0x1800267f4  jz      short loc_180026809
0x1800267f6  lea     r14d, [rsi+1]
0x1800267fa  mov     ebx, r14d
0x1800267fd  lea     ecx, [rsi+2]
0x180026800  mov     dword ptr [rsp+288h+var_1E0], ecx
0x180026807  jmp     short loc_180026855
0x180026809  lea     rax, [rsp+288h+var_1F0]
0x180026811  mov     [rsp+288h+var_268], rax
0x180026816  lea     r9, [rsp+288h+var_1B8]
0x18002681e  mov     r8d, ebx
0x180026821  mov     rdx, [rsp+288h+Sid]
0x180026826  mov     ecx, 90261h
0x18002682b  call    Is_SIMPLE_ATTR_NAME
0x180026830  mov     ebx, eax
0x180026832  mov     r14d, 1
0x180026838  movups  xmm7, [rsp+288h+var_1D0]
0x180026840  mov     ecx, dword ptr [rsp+288h+var_1E0]
0x180026847  movups  xmm6, [rsp+288h+var_1F0]
0x18002684f  mov     edx, cs:gfADAM
0x180026855  mov     eax, dword ptr [rsp+288h+var_210]
0x180026859  test    r15d, r15d
0x18002685c  jz      short loc_180026863
0x18002685e  cmp     eax, 3
0x180026861  jz      short loc_18002687D
0x180026863  test    ebx, ebx
0x180026865  jz      short loc_18002686C
0x180026867  cmp     ecx, 3
0x18002686a  jz      short loc_18002687D
0x18002686c  test    r15d, r15d
0x18002686f  jz      short loc_180026895
0x180026871  test    eax, eax
0x180026873  jnz     short loc_180026890
0x180026875  test    ebx, ebx
0x180026877  jz      short loc_180026890
0x180026879  test    ecx, ecx
0x18002687b  jnz     short loc_180026890
0x18002687d  mov     ebx, r14d
0x180026880  mov     [rsp+288h+var_258], ebx
0x180026884  mov     dword ptr [rdi+10h], 3
0x18002688b  jmp     loc_180026B0A
0x180026890  test    r15d, r15d
0x180026893  jnz     short loc_1800268B0
0x180026895  test    ebx, ebx
0x180026897  jz      short loc_1800268C1
0x180026899  test    r15d, r15d
0x18002689c  jnz     short loc_1800268B0
0x18002689e  test    ebx, ebx
0x1800268a0  jz      short loc_1800268A7
0x1800268a2  cmp     ecx, 2
0x1800268a5  jz      short loc_1800268C1
0x1800268a7  test    r15d, r15d
0x1800268aa  jz      loc_1800269ED
0x1800268b0  test    ebx, ebx
0x1800268b2  jnz     loc_1800269D2
0x1800268b8  cmp     eax, 2
0x1800268bb  jnz     loc_1800269D2
0x1800268c1  xor     ebx, ebx
0x1800268c3  mov     [rsp+288h+var_258], ebx
0x1800268c7  mov     dword ptr [rdi+10h], 2
0x1800268ce  test    edx, edx
0x1800268d0  jnz     loc_180026B0A
0x1800268d6  mov     [rsp+288h+cbDomainSid], ebx
0x1800268dd  lea     r8, [rsp+288h+cbDomainSid]; cbDomainSid
0x1800268e5  xor     edx, edx; pDomainSid
0x1800268e7  mov     rcx, [rsp+288h+Sid]; pSid
0x1800268ec  call    cs:__imp_GetWindowsAccountDomainSid
0x1800268f2  mov     r8d, [rsp+288h+cbDomainSid]
0x1800268fa  mov     [rsp+288h+var_260], 31E0347h
0x180026902  mov     dword ptr [rsp+288h+var_268], ebx
0x180026906  mov     r9d, r14d
0x180026909  mov     rdx, r14
0x18002690c  mov     rcx, r13
0x18002690f  call    THAlloc_
0x180026914  mov     r12, rax
0x180026917  mov     [rsp+288h+var_248], rax
0x18002691c  lea     r8, [rsp+288h+cbDomainSid]; cbDomainSid
0x180026924  mov     rdx, rax; pDomainSid
0x180026927  mov     rcx, [rsp+288h+Sid]; pSid
0x18002692c  call    cs:__imp_GetWindowsAccountDomainSid
0x180026932  xor     ecx, ecx; dwErrCode
0x180026934  test    eax, eax
0x180026936  jnz     short loc_18002694A
0x180026938  call    cs:__imp_SetLastError
0x18002693e  mov     dword ptr [rdi+10h], 2
0x180026945  jmp     loc_180026B0A
0x18002694a  lea     r8, [rsp+288h+Src]
0x18002694f  mov     rdx, r12
0x180026952  call    cs:__imp_LsaIForestTrustFindMatch
0x180026958  test    eax, eax
0x18002695a  js      loc_180026B0A
0x180026960  movzx   r8d, word ptr [rsp+288h+Src]
0x180026966  add     r8, 2
0x18002696a  mov     [rsp+288h+var_260], 31E035Dh
0x180026972  mov     dword ptr [rsp+288h+var_268], ebx
0x180026976  mov     r9d, r14d
0x180026979  mov     rdx, r14
0x18002697c  mov     rcx, r13
0x18002697f  call    THAlloc_
0x180026984  mov     [rdi+20h], rax
0x180026988  movzx   r8d, word ptr [rsp+288h+Src]; Size
0x18002698e  mov     rdx, [rsp+288h+Src+8]; Src
0x180026993  mov     rcx, rax; void *
0x180026996  call    memcpy_0
0x18002699b  movzx   edx, word ptr [rsp+288h+Src]
0x1800269a0  shr     rdx, 1
0x1800269a3  mov     rcx, [rdi+20h]
0x1800269a7  xor     eax, eax
0x1800269a9  mov     [rcx+rdx*2], ax
0x1800269ad  lea     rcx, [rsp+288h+Src]
0x1800269b2  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x1800269b8  mov     eax, [rdi]
0x1800269ba  and     eax, 8
0x1800269bd  or      eax, 14h
0x1800269c0  shr     eax, 2
0x1800269c3  mov     [rdi+10h], eax
0x1800269c6  mov     ebx, r14d
0x1800269c9  mov     [rsp+288h+var_258], ebx
0x1800269cd  jmp     loc_180026B0A
0x1800269d2  test    r15d, r15d
0x1800269d5  jz      short loc_1800269ED
0x1800269d7  test    eax, 0FFFFFFFDh
0x1800269dc  jz      short loc_1800269ED
0x1800269de  mov     ebx, r15d
0x1800269e1  mov     [rsp+288h+var_258], ebx
0x1800269e5  mov     [rdi+10h], eax
0x1800269e8  jmp     loc_180026B0A
0x1800269ed  test    ebx, ebx
0x1800269ef  jz      short loc_180026A05
0x1800269f1  test    ecx, 0FFFFFFFDh
0x1800269f7  jz      short loc_180026A05
0x1800269f9  mov     [rsp+288h+var_258], ebx
0x1800269fd  mov     [rdi+10h], ecx
0x180026a00  jmp     loc_180026B0A
0x180026a05  mov     ebx, r14d
0x180026a08  mov     [rsp+288h+var_258], ebx
0x180026a0c  test    r15d, r15d
0x180026a0f  jz      short loc_180026A34
0x180026a11  test    eax, eax
0x180026a13  jnz     short loc_180026A34
0x180026a15  movups  xmm0, [rsp+288h+var_220]
0x180026a1a  movups  xmmword ptr [rdi], xmm0
0x180026a1d  movups  xmm1, [rsp+288h+var_210]
0x180026a22  movups  xmmword ptr [rdi+10h], xmm1
0x180026a26  movups  xmm0, [rsp+288h+var_200]
0x180026a2e  movups  xmmword ptr [rdi+20h], xmm0
0x180026a32  jmp     short loc_180026A4A
0x180026a34  movups  xmmword ptr [rdi], xmm6
0x180026a37  movups  xmm0, [rsp+288h+var_1E0]
0x180026a3f  movups  xmmword ptr [rdi+10h], xmm0
0x180026a43  movups  xmmword ptr [rdi+20h], xmm7
0x180026a47  mov     esi, r14d
0x180026a4a  test    edx, edx
0x180026a4c  jz      short loc_180026A5A
0x180026a4e  mov     dword ptr [rdi+10h], 0
0x180026a55  jmp     loc_180026B0A
0x180026a5a  mov     [rsp+288h+arg_18], 0
0x180026a65  mov     [rsp+288h+var_230], 0
0x180026a6e  mov     rdx, [rdi+18h]
0x180026a72  mov     rcx, [r13+15C8h]
0x180026a79  call    DBFindDSName
0x180026a7e  test    eax, eax
0x180026a80  jnz     short loc_180026AFD
0x180026a82  lea     rax, [rsp+288h+var_230]
0x180026a87  mov     [rsp+288h+var_268], rax
0x180026a8c  lea     r9, [rsp+288h+arg_18]
0x180026a94  mov     r8, [rdi+18h]
0x180026a98  mov     edx, 9012Eh
0x180026a9d  mov     rcx, r13
0x180026aa0  call    GetAttSecure
0x180026aa5  test    eax, eax
0x180026aa7  jnz     short loc_180026AFD
0x180026aa9  mov     rcx, [rsp+288h+var_230]
0x180026aae  mov     edx, [rcx]
0x180026ab0  sub     edx, 10000000h
0x180026ab6  jz      short loc_180026AF1
0x180026ab8  sub     edx, 1
0x180026abb  jz      short loc_180026AF1
0x180026abd  mov     eax, 0FFFFFFFh
0x180026ac2  sub     edx, eax
0x180026ac4  jz      short loc_180026AE5
0x180026ac6  sub     edx, 1
0x180026ac9  jz      short loc_180026AE5
0x180026acb  sub     edx, eax
0x180026acd  jz      short loc_180026AD9
0x180026acf  sub     edx, 1
0x180026ad2  jz      short loc_180026AD9
0x180026ad4  cmp     edx, 1
0x180026ad7  jnz     short loc_180026AFD
0x180026ad9  xor     esi, r14d
0x180026adc  lea     esi, ds:0FFFFFFFFFFFFFFF5h[rsi*4]
0x180026ae3  jmp     short loc_180026B07
0x180026ae5  xor     esi, r14d
0x180026ae8  lea     esi, ds:0FFFFFFFFFFFFFFF3h[rsi*4]
0x180026aef  jmp     short loc_180026B07
0x180026af1  neg     esi
0x180026af3  sbb     esi, esi
0x180026af5  and     esi, 0FFFFFFFCh
0x180026af8  add     esi, 0FFFFFFF8h
0x180026afb  jmp     short loc_180026B07
0x180026afd  xor     esi, r14d
0x180026b00  lea     esi, ds:0FFFFFFFFFFFFFFF2h[rsi*4]
0x180026b07  mov     [rdi+10h], esi
0x180026b0a  mov     rcx, [rsp+288h+Sid]; hMem
0x180026b0f  call    cs:__imp_LocalFree
0x180026b15  test    r12, r12
0x180026b18  jz      short loc_180026B2D
0x180026b1a  mov     dword ptr [rsp+288h+var_268], 31E03DBh
0x180026b22  mov     rdx, r12
0x180026b25  mov     rcx, r13
0x180026b28  call    THFreeAux
0x180026b2d  mov     rdx, rdi
0x180026b30  mov     ecx, r14d
0x180026b33  call    CommonParseExit
  ... truncated ...
```
