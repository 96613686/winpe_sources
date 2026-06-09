# NetpSrvOpen

- ea: `0x1800304c4`
- end: `0x180030a83`
- name: `NetpSrvOpen`
- size: `1471`
- prototype: `__int64 __fastcall(PCSTR pszName, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002dd00`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x180026b40`
- `0x1800301b0`
- `0x1800304c4`
- `0x180030b00`
- `0x180030b9c`
- `0x180030c40`
- `0x180030d04`
- `0x180030d5c`
- `0x180031040`

## import_xrefs

- `msvcrt!qsort` at `0x1800307cf`
- `msvcrt!qsort` at `0x1800307cf`
- `ntdll!NtQuerySystemTime` at `0x180030518`
- `ntdll!NtQuerySystemTime` at `0x180030518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800306f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800306f0`
- `DNSAPI!DnsFree` at `0x180030a50`
- `DNSAPI!DnsFree` at `0x180030a50`
- `DNSAPI!DnsQuery_UTF8` at `0x180030591`
- `DNSAPI!DnsQuery_UTF8` at `0x180030591`

## pseudocode

```c
__int64 __fastcall NetpSrvOpen(PCSTR pszName, __int64 a2, _QWORD *a3)
{
  PDNS_RECORD v5; // r15
  int v6; // r12d
  char v7; // r13
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  PDNS_RECORD v14; // rax
  WORD wPreference; // dx
  unsigned int v16; // edi
  unsigned __int64 v17; // rax
  unsigned int v18; // r14d
  _QWORD *v19; // rax
  __int64 v20; // r8
  _QWORD *v21; // rbx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rax
  unsigned int i; // edi
  void *QuadPart; // r14
  _WORD *v28; // rax
  const wchar_t *v29; // r9
  __int64 *j; // rdi
  const CHAR *v31; // rcx
  int v32; // edx
  int v33; // r8d
  void *v34; // r14
  const wchar_t *v35; // r9
  const wchar_t *v36; // r9
  const wchar_t *v37; // r9
  PDNS_RECORD ppQueryResults; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *v40; // [rsp+48h] [rbp-18h]
  union _LARGE_INTEGER SystemTime; // [rsp+50h] [rbp-10h] BYREF

  v40 = a3;
  ppQueryResults = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( !NetpSrvRandomInitialized )
  {
    SystemTime.QuadPart = 0;
    NtQuerySystemTime(&SystemTime);
    NetpSrvRandomInitialized = 1;
    v8 = BYTE1(SystemTime.LowPart) + 1;
    a2 = v8
       | ((BYTE2(SystemTime.u.LowPart) << 16) - 0x10000)
       | ((BYTE2(SystemTime.u.LowPart) | (BYTE1(SystemTime.LowPart) << 16)) << 8);
    NetpSrvSeed = v8
                | ((BYTE2(SystemTime.u.LowPart) << 16) - 0x10000)
                | ((BYTE2(SystemTime.u.LowPart) | (BYTE1(SystemTime.LowPart) << 16)) << 8);
  }
  *a3 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, pszName);
  v9 = DnsQuery_UTF8(pszName, 0x21u, 8u, 0, &ppQueryResults, 0);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 11;
      v13 = v9;
LABEL_90:
      WPP_SF_D(v11[2], v12, WPP_23051530b2693a98e584d03d688af52b_Traceguids, v13);
    }
LABEL_91:
    if ( ppQueryResults )
      DnsFree(ppQueryResults, DnsFreeRecordList);
  }
  else
  {
    v14 = ppQueryResults;
    if ( ppQueryResults )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_23051530b2693a98e584d03d688af52b_Traceguids);
        v14 = ppQueryResults;
      }
      wPreference = v14->Data.MX.wPreference;
      v16 = 0;
      while ( 1 )
      {
        if ( v14->wType == 33 )
        {
          if ( v16 + 1 < v16 )
          {
            v11 = WPP_GLOBAL_Control;
            v10 = 534;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_91;
            v12 = 14;
            goto LABEL_89;
          }
          ++v16;
          if ( !v14->Data.MX.Pad )
            v14->Data.MX.Pad = 1;
          if ( v14->Data.MX.wPreference != wPreference )
            v7 = 1;
        }
        else if ( v14->wType == 1 )
        {
          v5 = v14;
LABEL_31:
          v17 = 8LL * v16;
          if ( v17 > 0xFFFFFFFF )
          {
            v11 = WPP_GLOBAL_Control;
            v10 = 534;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_91;
            v12 = 15;
          }
          else
          {
            v18 = v17 + 48;
            if ( (int)v17 + 48 >= (unsigned int)v17 )
            {
              v19 = LocalAlloc(0x40u, v18);
              v21 = v19;
              if ( v19 )
              {
                v19[1] = ppQueryResults;
                v22 = 0;
                ppQueryResults = 0;
                v23 = (__int64 *)v19[1];
                *((_DWORD *)v19 + 9) = v16;
                v19[2] = v5;
                *(_DWORD *)v19 = 8;
                if ( v23 )
                {
                  v20 = 1;
                  do
                  {
                    if ( *((_WORD *)v23 + 8) == 33 )
                    {
                      v24 = (unsigned int)v22;
                      v22 = (unsigned int)(v22 + 1);
                      v21[v24 + 5] = v23;
                    }
                    else if ( *((_WORD *)v23 + 8) == 1 )
                    {
                      break;
                    }
                    v23 = (__int64 *)*v23;
                  }
                  while ( v23 );
                }
                if ( v7 )
                {
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_23051530b2693a98e584d03d688af52b_Traceguids);
                  qsort(v21 + 5, *((unsigned int *)v21 + 9), 8u, NetpSrvComparePriority);
                }
                *((_DWORD *)v21 + 6) = -1;
                *((_DWORD *)v21 + 8) = 0;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  v25 = (_QWORD *)v21[2];
                  while ( v25 )
                  {
                    v25 = (_QWORD *)*v25;
                    ++v6;
                  }
                  WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v20, *((unsigned int *)v21 + 9), v6);
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    for ( i = 0; i < *((_DWORD *)v21 + 9); ++i )
                    {
                      SystemTime.QuadPart = 0;
                      NetpConvertUTF8ToUnicode(*(LPCCH *)(v21[i + 5] + 32LL));
                      QuadPart = (void *)SystemTime.QuadPart;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                      {
                        v29 = L"<conversion error>";
                        if ( SystemTime.QuadPart )
                          LODWORD(v29) = SystemTime.LowPart;
                        v28 = (_WORD *)v21[i + 5];
                        WPP_SF_SDddd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          (unsigned __int16)v28[22],
                          (unsigned __int16)v28[21],
                          (_DWORD)v29,
                          v28[8],
                          v28[20],
                          v28[21],
                          v28[22]);
                      }
                      LocalFree(QuadPart);
                    }
                    for ( j = (__int64 *)v21[2]; j; j = (__int64 *)*j )
                    {
                      v31 = (const CHAR *)j[1];
                      SystemTime.QuadPart = 0;
                      NetpConvertUTF8ToUnicode(v31);
                      v34 = (void *)SystemTime.QuadPart;
                      if ( *((_WORD *)j + 8) == 1 )
                      {
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                        {
                          v35 = L"<conversion error>";
                          if ( SystemTime.QuadPart )
                            LODWORD(v35) = SystemTime.LowPart;
                          WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, (_DWORD)v35, 1, *((_DWORD *)j + 8));
                        }
                      }
                      else if ( *((_WORD *)j + 8) == 28 )
                      {
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                        {
                          v36 = L"<conversion error>";
                          if ( SystemTime.QuadPart )
                            LODWORD(v36) = SystemTime.LowPart;
                          WPP_SF_SD_IPV6_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v32,
                            v33,
                            (_DWORD)v36,
                            28,
                            (__int64)(j + 4));
                        }
                      }
                      else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                      {
                        v37 = L"<conversion error>";
                        if ( SystemTime.QuadPart )
                          LODWORD(v37) = SystemTime.LowPart;
                        WPP_SF_SD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          23,
                          (unsigned int)WPP_23051530b2693a98e584d03d688af52b_Traceguids,
                          (_DWORD)v37,
                          *((_WORD *)j + 8));
                      }
                      LocalFree(v34);
                    }
                  }
                }
                *v40 = v21;
                v10 = 0;
              }
              else
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    WPP_23051530b2693a98e584d03d688af52b_Traceguids,
                    v18);
                v10 = 8;
              }
              goto LABEL_91;
            }
            v11 = WPP_GLOBAL_Control;
            v10 = 534;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_91;
            v12 = 16;
          }
LABEL_89:
          v13 = 534;
          goto LABEL_90;
        }
        v14 = v14->pNext;
        if ( !v14 )
          goto LABEL_31;
      }
    }
    v10 = 1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)ppQueryResults + 12),
        WPP_23051530b2693a98e584d03d688af52b_Traceguids);
      goto LABEL_91;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800304c4  mov     [rsp-38h+arg_8], rbx
0x1800304c9  push    rbp
0x1800304ca  push    rsi
0x1800304cb  push    rdi
0x1800304cc  push    r12
0x1800304ce  push    r13
0x1800304d0  push    r14
0x1800304d2  push    r15
0x1800304d4  mov     rbp, rsp
0x1800304d7  sub     rsp, 60h
0x1800304db  mov     rax, cs:__security_cookie
0x1800304e2  xor     rax, rsp
0x1800304e5  mov     [rbp+var_8], rax
0x1800304e9  xor     r14d, r14d
0x1800304ec  mov     [rbp+var_18], r8
0x1800304f0  cmp     cs:NetpSrvRandomInitialized, r14b
0x1800304f7  mov     rdi, r8
0x1800304fa  mov     rbx, rcx
0x1800304fd  mov     [rbp+var_20], r14
0x180030501  mov     r15d, r14d
0x180030504  mov     r12d, r14d
0x180030507  lea     esi, [r14+1]
0x18003050b  mov     r13b, r14b
0x18003050e  jnz     short loc_180030552
0x180030510  lea     rcx, [rbp+SystemTime]; SystemTime
0x180030514  mov     qword ptr [rbp+SystemTime], r14
0x180030518  call    cs:__imp_NtQuerySystemTime
0x18003051f  nop     dword ptr [rax+rax+00h]
0x180030524  movzx   ecx, byte ptr [rbp+SystemTime+1]
0x180030528  movzx   eax, byte ptr [rbp+SystemTime+2]
0x18003052c  mov     edx, ecx
0x18003052e  shl     edx, 10h
0x180030531  or      edx, eax
0x180030533  mov     cs:NetpSrvRandomInitialized, sil
0x18003053a  shl     eax, 10h
0x18003053d  sub     eax, 10000h
0x180030542  shl     edx, 8
0x180030545  or      edx, eax
0x180030547  lea     eax, [rcx+1]
0x18003054a  or      edx, eax
0x18003054c  mov     cs:NetpSrvSeed, edx
0x180030552  mov     [rdi], r14
0x180030555  mov     rcx, cs:WPP_GLOBAL_Control
0x18003055c  test    [rcx+1Ch], sil
0x180030560  jz      short loc_180030574
0x180030562  cmp     byte ptr [rcx+19h], 4
0x180030566  jb      short loc_180030574
0x180030568  mov     rcx, [rcx+10h]
0x18003056c  mov     r9, rbx
0x18003056f  call    WPP_SF_sD
0x180030574  mov     edx, 21h ; '!'; wType
0x180030579  mov     [rsp+60h+pReserved], r14; pReserved
0x18003057e  lea     rax, [rbp+var_20]
0x180030582  xor     r9d, r9d; pExtra
0x180030585  mov     rcx, rbx; pszName
0x180030588  mov     [rsp+60h+ppQueryResults], rax; ppQueryResults
0x18003058d  lea     r8d, [rdx-19h]; Options
0x180030591  call    cs:__imp_DnsQuery_UTF8
0x180030598  nop     dword ptr [rax+rax+00h]
0x18003059d  mov     ebx, eax
0x18003059f  test    eax, eax
0x1800305a1  jz      short loc_1800305D5
0x1800305a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305aa  mov     r13d, esi
0x1800305ad  test    [rcx+1Ch], r13b
0x1800305b1  jz      loc_180030A44
0x1800305b7  cmp     byte ptr [rcx+19h], 2
0x1800305bb  jb      loc_180030A44
0x1800305c1  mov     edx, 0Bh
0x1800305c6  lea     r8, WPP_23051530b2693a98e584d03d688af52b_Traceguids
0x1800305cd  mov     r9d, eax
0x1800305d0  jmp     loc_180030A3B
0x1800305d5  mov     rax, [rbp+var_20]
0x1800305d9  test    rax, rax
0x1800305dc  jnz     short loc_180030616
0x1800305de  mov     r13d, esi
0x1800305e1  mov     ebx, esi
0x1800305e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305ea  test    [rcx+1Ch], r13b
0x1800305ee  jz      loc_180030A5C
0x1800305f4  cmp     byte ptr [rcx+19h], 2
0x1800305f8  jb      loc_180030A5C
0x1800305fe  mov     rcx, [rcx+10h]
0x180030602  lea     edx, [rax+0Ch]
0x180030605  lea     r8, WPP_23051530b2693a98e584d03d688af52b_Traceguids
0x18003060c  call    WPP_SF_
0x180030611  jmp     loc_180030A44
0x180030616  mov     rcx, cs:WPP_GLOBAL_Control
0x18003061d  lea     rsi, WPP_23051530b2693a98e584d03d688af52b_Traceguids
0x180030624  mov     r8d, 1
0x18003062a  test    [rcx+1Ch], r8b
0x18003062e  jz      short loc_180030650
0x180030630  cmp     byte ptr [rcx+19h], 4
0x180030634  jb      short loc_180030650
0x180030636  mov     rcx, [rcx+10h]
0x18003063a  lea     edx, [r8+0Ch]
0x18003063e  mov     r8, rsi
0x180030641  call    WPP_SF_
0x180030646  mov     rax, [rbp+var_20]
0x18003064a  mov     r8d, 1
0x180030650  movzx   edx, word ptr [rax+28h]
0x180030654  mov     edi, r14d
0x180030657  mov     r9d, 21h ; '!'
0x18003065d  cmp     [rax+10h], r9w
0x180030662  jnz     short loc_180030684
0x180030664  lea     ecx, [rdi+1]
0x180030667  cmp     ecx, edi
0x180030669  jb      short loc_180030695
0x18003066b  mov     edi, ecx
0x18003066d  cmp     [rax+2Ah], r14w
0x180030672  jnz     short loc_180030679
0x180030674  mov     [rax+2Ah], r8w
0x180030679  cmp     [rax+28h], dx
0x18003067d  jz      short loc_18003068B
0x18003067f  mov     r13b, r8b
0x180030682  jmp     short loc_18003068B
0x180030684  cmp     [rax+10h], r8w
0x180030689  jz      short loc_1800306C4
0x18003068b  mov     rax, [rax]
0x18003068e  test    rax, rax
0x180030691  jnz     short loc_18003065D
0x180030693  jmp     short loc_1800306C7
0x180030695  mov     rcx, cs:WPP_GLOBAL_Control
0x18003069c  mov     r13d, 1
0x1800306a2  mov     ebx, 216h
0x1800306a7  test    [rcx+1Ch], r13b
0x1800306ab  jz      loc_180030A44
0x1800306b1  cmp     byte ptr [rcx+19h], 2
0x1800306b5  jb      loc_180030A44
0x1800306bb  lea     edx, [r13+0Dh]
0x1800306bf  jmp     loc_180030A35
0x1800306c4  mov     r15, rax
0x1800306c7  mov     eax, edi
0x1800306c9  mov     ecx, 0FFFFFFFFh
0x1800306ce  shl     rax, 3
0x1800306d2  cmp     rax, rcx
0x1800306d5  ja      loc_180030A13
0x1800306db  lea     r14d, [rax+30h]
0x1800306df  cmp     r14d, eax
0x1800306e2  jb      loc_1800309EF
0x1800306e8  mov     edx, r14d; uBytes
0x1800306eb  mov     ecx, 40h ; '@'; uFlags
0x1800306f0  call    cs:__imp_LocalAlloc
0x1800306f7  nop     dword ptr [rax+rax+00h]
0x1800306fc  mov     rbx, rax
0x1800306ff  test    rax, rax
0x180030702  jnz     short loc_180030737
0x180030704  mov     rcx, cs:WPP_GLOBAL_Control
0x18003070b  lea     r13d, [rax+1]
0x18003070f  test    [rcx+1Ch], r13b
0x180030713  jz      short loc_18003072D
0x180030715  cmp     byte ptr [rcx+19h], 2
0x180030719  jb      short loc_18003072D
0x18003071b  mov     rcx, [rcx+10h]
0x18003071f  lea     edx, [rax+11h]
0x180030722  mov     r9d, r14d
0x180030725  mov     r8, rsi
0x180030728  call    WPP_SF_D
0x18003072d  mov     ebx, 8
0x180030732  jmp     loc_180030A44
0x180030737  mov     rax, [rbp+var_20]
0x18003073b  xor     r14d, r14d
0x18003073e  mov     [rbx+8], rax
0x180030742  mov     edx, r14d
0x180030745  mov     [rbp+var_20], r14
0x180030749  mov     rcx, [rbx+8]
0x18003074d  mov     [rbx+24h], edi
0x180030750  mov     [rbx+10h], r15
0x180030754  mov     dword ptr [rbx], 8
0x18003075a  test    rcx, rcx
0x18003075d  jz      short loc_18003078D
0x18003075f  lea     eax, [r14+21h]
0x180030763  lea     r8d, [r14+1]
0x180030767  cmp     [rcx+10h], ax
0x18003076b  jnz     short loc_18003077E
0x18003076d  mov     eax, edx
0x18003076f  add     edx, r8d
0x180030772  mov     [rbx+rax*8+28h], rcx
0x180030777  mov     eax, 21h ; '!'
0x18003077c  jmp     short loc_180030785
0x18003077e  cmp     [rcx+10h], r8w
0x180030783  jz      short loc_18003078D
0x180030785  mov     rcx, [rcx]
0x180030788  test    rcx, rcx
0x18003078b  jnz     short loc_180030767
0x18003078d  test    r13b, r13b
0x180030790  jz      short loc_1800307DD
0x180030792  mov     rcx, cs:WPP_GLOBAL_Control
0x180030799  mov     r13d, 1
0x18003079f  test    [rcx+1Ch], r13b
0x1800307a3  jz      short loc_1800307BB
0x1800307a5  cmp     byte ptr [rcx+19h], 5
0x1800307a9  jb      short loc_1800307BB
0x1800307ab  mov     rcx, [rcx+10h]
0x1800307af  lea     edx, [r13+11h]
0x1800307b3  mov     r8, rsi
0x1800307b6  call    WPP_SF_
0x1800307bb  mov     edx, [rbx+24h]; NumOfElements
0x1800307be  lea     rcx, [rbx+28h]; Base
0x1800307c2  lea     r9, NetpSrvComparePriority; CompareFunction
0x1800307c9  mov     r8d, 8; SizeOfElements
0x1800307cf  call    cs:__imp_qsort
0x1800307d6  nop     dword ptr [rax+rax+00h]
0x1800307db  jmp     short loc_1800307E3
0x1800307dd  mov     r13d, 1
0x1800307e3  or      dword ptr [rbx+18h], 0FFFFFFFFh
0x1800307e7  mov     [rbx+20h], r14d
0x1800307eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307f2  test    [rcx+1Ch], r13b
0x1800307f6  jz      loc_1800309E3
0x1800307fc  cmp     byte ptr [rcx+19h], 4
0x180030800  jb      loc_1800309E3
0x180030806  mov     rax, [rbx+10h]
0x18003080a  jmp     short loc_180030812
0x18003080c  mov     rax, [rax]
0x18003080f  add     r12d, r13d
0x180030812  test    rax, rax
0x180030815  jnz     short loc_18003080C
0x180030817  mov     r9d, [rbx+24h]
0x18003081b  mov     rcx, [rcx+10h]
0x18003081f  mov     dword ptr [rsp+60h+ppQueryResults], r12d
0x180030824  call    WPP_SF_dd
0x180030829  mov     rax, cs:WPP_GLOBAL_Control
0x180030830  test    [rax+1Ch], r13b
0x180030834  jz      loc_1800309E3
0x18003083a  cmp     byte ptr [rax+19h], 5
0x18003083e  jb      loc_1800309E3
0x180030844  lea     r12, aConversionErro; "<conversion error>"
0x18003084b  mov     edi, r14d
0x18003084e  cmp     [rbx+24h], r14d
0x180030852  jbe     loc_1800308E7
0x180030858  mov     r15d, edi
0x18003085b  lea     rdx, [rbp+SystemTime]
0x18003085f  mov     qword ptr [rbp+SystemTime], r14
0x180030863  mov     rcx, [rbx+r15*8+28h]
0x180030868  mov     rcx, [rcx+20h]; lpMultiByteStr
0x18003086c  call    NetpConvertUTF8ToUnicode
0x180030871  mov     rcx, cs:WPP_GLOBAL_Control
0x180030878  mov     r14, qword ptr [rbp+SystemTime]
0x18003087c  test    [rcx+1Ch], r13b
0x180030880  jz      short loc_1800308C6
0x180030882  cmp     byte ptr [rcx+19h], 5
0x180030886  jb      short loc_1800308C6
0x180030888  mov     rax, [rbx+r15*8+28h]
0x18003088d  test    r14, r14
0x180030890  mov     rcx, [rcx+10h]
0x180030894  mov     r9, r12
0x180030897  cmovnz  r9, r14
0x18003089b  movzx   edx, word ptr [rax+2Ch]
0x18003089f  movzx   r8d, word ptr [rax+2Ah]
0x1800308a4  movzx   r10d, word ptr [rax+28h]
0x1800308a9  movzx   r11d, word ptr [rax+10h]
0x1800308ae  mov     [rsp+60h+var_28], edx
0x1800308b2  mov     [rsp+60h+var_30], r8d
0x1800308b7  mov     dword ptr [rsp+60h+pReserved], r10d
0x1800308bc  mov     dword ptr [rsp+60h+ppQueryResults], r11d
0x1800308c1  call    WPP_SF_SDddd
0x1800308c6  mov     rcx, r14; hMem
0x1800308c9  call    cs:__imp_LocalFree
0x1800308d0  nop     dword ptr [rax+rax+00h]
0x1800308d5  add     edi, r13d
0x1800308d8  mov     r14d, 0
0x1800308de  cmp     edi, [rbx+24h]
0x1800308e1  jb      loc_180030858
0x1800308e7  mov     rdi, [rbx+10h]
0x1800308eb  test    rdi, rdi
0x1800308ee  jz      loc_1800309E3
0x1800308f4  mov     r15d, 1Ch
0x1800308fa  mov     rcx, [rdi+8]; lpMultiByteStr
0x1800308fe  lea     rdx, [rbp+SystemTime]
0x180030902  mov     qword ptr [rbp+SystemTime], r14
0x180030906  call    NetpConvertUTF8ToUnicode
0x18003090b  mov     r14, qword ptr [rbp+SystemTime]
0x18003090f  cmp     [rdi+10h], r13w
0x180030914  jnz     short loc_180030952
0x180030916  mov     rcx, cs:WPP_GLOBAL_Control
0x18003091d  test    [rcx+1Ch], r13b
0x180030921  jz      loc_1800309C5
0x180030927  cmp     byte ptr [rcx+19h], 5
0x18003092b  jb      loc_1800309C5
0x180030931  mov     eax, [rdi+20h]
0x180030934  test    r14, r14
0x180030937  mov     rcx, [rcx+10h]
0x18003093b  mov     r9, r12
0x18003093e  mov     dword ptr [rsp+60h+pReserved], eax
0x180030942  cmovnz  r9, r14
0x180030946  mov     dword ptr [rsp+60h+ppQueryResults], r13d
0x18003094b  call    WPP_SF_SDD
0x180030950  jmp     short loc_1800309C5
0x180030952  cmp     [rdi+10h], r15w
0x180030957  jnz     short loc_18003098F
0x180030959  mov     rcx, cs:WPP_GLOBAL_Control
0x180030960  test    [rcx+1Ch], r13b
0x180030964  jz      short loc_1800309C5
0x180030966  cmp     byte ptr [rcx+19h], 5
0x18003096a  jb      short loc_1800309C5
0x18003096c  mov     rcx, [rcx+10h]
0x180030970  lea     rax, [rdi+20h]
0x180030974  test    r14, r14
0x180030977  mov     [rsp+60h+pReserved], rax
  ... truncated ...
```
