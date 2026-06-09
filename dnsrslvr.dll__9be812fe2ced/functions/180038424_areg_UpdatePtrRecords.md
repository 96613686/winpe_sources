# areg_UpdatePtrRecords

- ea: `0x180038424`
- end: `0x18003885c`
- name: `areg_UpdatePtrRecords`
- size: `1080`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x18003473c`
- `0x180037494`
- `0x180037cfc`

## callees

- `0x180012bb0`
- `0x1800377b8`
- `0x180038424`
- `0x18003efb8`
- `0x180046ec0`
- `0x180047818`
- `0x18004a860`
- `0x18007a760`
- `0x18007c834`
- `0x180086700`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x1800384d4`
- `DNSAPI!DnsModifyRecordsInSet_W` at `0x180038702`
- `DNSAPI!DnsModifyRecordsInSet_W` at `0x180038702`
- `DNSAPI!DnsReplaceRecordSetW` at `0x1800386ca`
- `DNSAPI!DnsReplaceRecordSetW` at `0x1800386ca`

## string_xrefs

- `0x1800384c8`: `Entering areg_UpdatePtrRecords:`
- `0x180038720`: `Replace`
- `0x180038719`: `Modify (remove)`

## pseudocode

```c
__int64 __fastcall areg_UpdatePtrRecords(__int64 a1, int a2, int a3)
{
  unsigned int v3; // r14d
  int v4; // edi
  __int64 result; // rax
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // rdx
  __int64 v11; // r13
  DNS_STATUS v12; // ecx
  DNS_STATUS v13; // edx
  _WORD *v14; // rax
  bool v15; // zf
  bool v16; // zf
  DNS_RECORDA *PtrRecord; // rax
  DNS_RECORDA *v18; // rax
  DNS_RECORDA *v19; // r14
  DWORD v20; // edx
  DNS_STATUS v21; // eax
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  DWORD v25; // r8d
  DNS_STATUS v26; // edi
  const char *v27; // r9
  DNS_STATUS v28; // eax
  DNS_STATUS v29; // eax
  int pReserved; // [rsp+20h] [rbp-E0h]
  DNS_STATUS v31; // [rsp+30h] [rbp-D0h]
  DNS_STATUS v32; // [rsp+34h] [rbp-CCh]
  unsigned int v33; // [rsp+38h] [rbp-C8h]
  int v34; // [rsp+3Ch] [rbp-C4h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+50h] [rbp-B0h]
  PDNS_RECORD pReplaceSet[3]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD pExtraInfo[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  char v42[66]; // [rsp+8Eh] [rbp-72h] BYREF
  _DWORD v43[6]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-18h]

  v3 = *(_DWORD *)(a1 + 236);
  v4 = a3;
  v33 = v3;
  v37 = *(_QWORD *)(a1 + 32);
  *(_OWORD *)pReplaceSet = 0;
  memset_0(pExtraInfo, 0, 0x60u);
  memset_0(v43, 0, 0x60u);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qDD(1035, 149, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, a1, a2, v4);
  DnsPrint_AregEntry("Entering areg_UpdatePtrRecords:", a1);
  result = *(_QWORD *)DnsGlobals;
  if ( !DnsGlobals[60] )
    return result;
  v8 = *(_QWORD *)(a1 + 48);
  v9 = *(_QWORD *)(a1 + 40);
  if ( a2 && !DnsGlobals[6] )
  {
    v8 &= -(__int64)(*(_DWORD *)(a1 + 268) != 0);
    result = (unsigned int)-*(_DWORD *)(a1 + 264);
    v9 &= -(__int64)(*(_DWORD *)(a1 + 264) != 0);
  }
  if ( !v8 && !v9 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v10 = 150;
      return WPP_SF_(1035, v10, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    }
    return result;
  }
  v11 = *(_QWORD *)(a1 + 88);
  if ( !v11 )
    return result;
  v12 = 0;
  v13 = 0;
  result = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  if ( !*(_DWORD *)(v11 + 4) )
    goto LABEL_67;
  do
  {
    v14 = (_WORD *)(v11 + (result << 6) + 32);
    v36 = (__int64)v14;
    if ( *v14 == 2 )
    {
      v15 = (*(_BYTE *)(a1 + 244) & 8) == 0;
    }
    else
    {
      if ( *v14 != 23 )
        goto LABEL_18;
      v15 = (*(_BYTE *)(a1 + 248) & 8) == 0;
    }
    if ( v15 )
      goto LABEL_65;
LABEL_18:
    if ( v4 && !a2 )
    {
      if ( *v14 == 2 )
      {
        if ( (*(_BYTE *)(a1 + 244) & 8) == 0 )
          goto LABEL_27;
        v16 = *(_DWORD *)(a1 + 276) == 0;
      }
      else
      {
        if ( *v14 != 23 || (*(_BYTE *)(a1 + 248) & 8) == 0 )
          goto LABEL_27;
        v16 = *(_DWORD *)(a1 + 280) == 0;
      }
      if ( v16 )
        goto LABEL_65;
    }
LABEL_27:
    pReplaceSet[0] = 0;
    pReplaceSet[1] = (PDNS_RECORD)pReplaceSet;
    if ( v9 && *(_DWORD *)(a1 + 340) == 2 )
    {
      PtrRecord = (DNS_RECORDA *)Dns_CreatePtrRecordExEx(v14, v37, v9, v3);
      if ( PtrRecord )
      {
        pReplaceSet[1]->pNext = PtrRecord;
        pReplaceSet[1] = PtrRecord;
      }
      v14 = (_WORD *)v36;
    }
    if ( v8 )
    {
      v18 = (DNS_RECORDA *)Dns_CreatePtrRecordExEx(v14, v37, v8, v3);
      if ( v18 )
      {
        pReplaceSet[1]->pNext = v18;
        pReplaceSet[1] = v18;
      }
    }
    v19 = pReplaceSet[0];
    if ( !pReplaceSet[0] )
      goto LABEL_64;
    memset_0(pExtraInfo, 0, 0x60u);
    pExtraInfo[0] = -2147483647;
    pExtraInfo[1] = 96;
    v41 = 2;
    memset_0(v43, 0, 0x60u);
    v44 = *(_QWORD *)(a1 + 96);
    v40 = v43;
    v43[0] = -2147483647;
    v43[1] = 96;
    v43[4] = 10;
    if ( !g_fVelocityRpcUpdate )
    {
      if ( a2 )
      {
        v20 = 512;
        goto LABEL_39;
      }
      v25 = 512;
LABEL_44:
      v21 = DnsModifyRecordsInSet_W(0, v19, v25, 0, pExtraInfo, 0);
      goto LABEL_45;
    }
    if ( !a2 )
    {
      v25 = 0;
      goto LABEL_44;
    }
    v20 = 0;
LABEL_39:
    v21 = DnsReplaceRecordSetW(v19, v20, 0, pExtraInfo, 0);
LABEL_45:
    v26 = v21;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v27 = "Replace";
      if ( !a2 )
        v27 = "Modify (remove)";
      WPP_SF_ssD(v23, v22, v24, (_DWORD)v27, pReserved, v21);
    }
    if ( a2 && *(_DWORD *)(a1 + 300) || (areg_LogRegistration(a1, v26, 4, a2 == 0, (__int64)v42, v36), a2) )
    {
      if ( !v26 )
      {
        if ( (*(_BYTE *)(a1 + 244) & 8) != 0 )
          *(_DWORD *)(a1 + 276) = 1;
        if ( (*(_BYTE *)(a1 + 248) & 8) != 0 )
          *(_DWORD *)(a1 + 280) = 1;
      }
    }
    else if ( v26 )
    {
      v28 = v31;
      if ( (*(_BYTE *)(a1 + 244) & 8) != 0 )
        v28 = v26;
      v31 = v28;
      v29 = v32;
      if ( (*(_BYTE *)(a1 + 248) & 8) != 0 )
        v29 = v26;
      v32 = v29;
    }
    Dns_RecordListFree(v19);
    v4 = a3;
LABEL_64:
    v3 = v33;
LABEL_65:
    result = (unsigned int)(v34 + 1);
    v34 = result;
  }
  while ( (unsigned int)result < *(_DWORD *)(v11 + 4) );
  v12 = v31;
  v13 = v32;
LABEL_67:
  if ( !a2 )
  {
    if ( (*(_BYTE *)(a1 + 244) & 8) != 0 && !v12 )
      *(_DWORD *)(a1 + 276) = 0;
    if ( (*(_BYTE *)(a1 + 248) & 8) != 0 && !v13 )
      *(_DWORD *)(a1 + 280) = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v10 = 152;
    return WPP_SF_(1035, v10, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180038424  push    rbp
0x180038426  push    rbx
0x180038427  push    rsi
0x180038428  push    rdi
0x180038429  push    r12
0x18003842b  push    r13
0x18003842d  push    r14
0x18003842f  push    r15
0x180038431  lea     rbp, [rsp-48h]
0x180038436  sub     rsp, 148h
0x18003843d  mov     rax, cs:__security_cookie
0x180038444  xor     rax, rsp
0x180038447  mov     [rbp+80h+var_50], rax
0x18003844b  mov     r14d, [rcx+0ECh]
0x180038452  mov     edi, r8d
0x180038455  mov     rax, [rcx+20h]
0x180038459  mov     esi, edx
0x18003845b  mov     [rsp+180h+var_140], r8d
0x180038460  mov     rbx, rcx
0x180038463  xorps   xmm0, xmm0
0x180038466  mov     [rsp+180h+var_148], r14d
0x18003846b  mov     r15d, 60h ; '`'
0x180038471  mov     [rsp+180h+var_130], rax
0x180038476  mov     r8d, r15d; Size
0x180038479  lea     rcx, [rsp+180h+pExtraInfo]; void *
0x18003847e  xor     edx, edx; Val
0x180038480  movups  xmmword ptr [rsp+180h+pReplaceSet], xmm0
0x180038485  call    memset_0
0x18003848a  mov     r8d, r15d; Size
0x18003848d  lea     rcx, [rbp+80h+var_B0]; void *
0x180038491  xor     edx, edx; Val
0x180038493  call    memset_0
0x180038498  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003849f  mov     r13d, 40Bh
0x1800384a5  jz      short loc_1800384C5
0x1800384a7  lea     edx, [r15+35h]
0x1800384ab  mov     dword ptr [rsp+180h+var_158], edi
0x1800384af  mov     ecx, r13d
0x1800384b2  mov     dword ptr [rsp+180h+pReserved], esi
0x1800384b6  mov     r9, rbx
0x1800384b9  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800384c0  call    WPP_SF_qDD
0x1800384c5  mov     rdx, rbx
0x1800384c8  lea     rcx, aEnteringAregUp; "Entering areg_UpdatePtrRecords:"
0x1800384cf  call    DnsPrint_AregEntry
0x1800384d4  mov     rax, cs:__imp_DnsGlobals
0x1800384db  cmp     dword ptr [rax+0F0h], 0
0x1800384e2  jz      loc_18003883C
0x1800384e8  mov     r15, [rbx+30h]
0x1800384ec  mov     r12, [rbx+28h]
0x1800384f0  test    esi, esi
0x1800384f2  jz      short loc_180038516
0x1800384f4  cmp     dword ptr [rax+18h], 0
0x1800384f8  jnz     short loc_180038516
0x1800384fa  mov     eax, [rbx+10Ch]
0x180038500  neg     eax
0x180038502  mov     eax, [rbx+108h]
0x180038508  sbb     rcx, rcx
0x18003850b  and     r15, rcx
0x18003850e  neg     eax
0x180038510  sbb     rcx, rcx
0x180038513  and     r12, rcx
0x180038516  test    r15, r15
0x180038519  jnz     short loc_18003853A
0x18003851b  test    r12, r12
0x18003851e  jnz     short loc_18003853A
0x180038520  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038527  jz      loc_18003883C
0x18003852d  mov     edx, 96h
0x180038532  mov     ecx, r13d
0x180038535  jmp     loc_180038830
0x18003853a  mov     r13, [rbx+58h]
0x18003853e  test    r13, r13
0x180038541  jz      loc_18003883C
0x180038547  xor     ecx, ecx
0x180038549  xor     edx, edx
0x18003854b  xor     eax, eax
0x18003854d  mov     [rsp+180h+var_150], ecx
0x180038551  mov     [rsp+180h+var_14C], edx
0x180038555  mov     [rsp+180h+var_144], eax
0x180038559  cmp     [r13+4], eax
0x18003855d  jbe     loc_1800387F3
0x180038563  lea     edx, [rcx+2]
0x180038566  shl     rax, 6
0x18003856a  add     rax, 20h ; ' '
0x18003856e  add     rax, r13
0x180038571  mov     [rsp+180h+var_138], rax
0x180038576  cmp     [rax], dx
0x180038579  jnz     short loc_180038584
0x18003857b  test    byte ptr [rbx+0F4h], 8
0x180038582  jmp     short loc_180038591
0x180038584  cmp     word ptr [rax], 17h
0x180038588  jnz     short loc_180038597
0x18003858a  test    byte ptr [rbx+0F8h], 8
0x180038591  jz      loc_1800387D7
0x180038597  test    edi, edi
0x180038599  jz      short loc_1800385D1
0x18003859b  test    esi, esi
0x18003859d  jnz     short loc_1800385D1
0x18003859f  cmp     [rax], dx
0x1800385a2  jnz     short loc_1800385B5
0x1800385a4  test    byte ptr [rbx+0F4h], 8
0x1800385ab  jz      short loc_1800385D1
0x1800385ad  cmp     [rbx+114h], esi
0x1800385b3  jmp     short loc_1800385CB
0x1800385b5  cmp     word ptr [rax], 17h
0x1800385b9  jnz     short loc_1800385D1
0x1800385bb  test    byte ptr [rbx+0F8h], 8
0x1800385c2  jz      short loc_1800385D1
0x1800385c4  cmp     dword ptr [rbx+118h], 0
0x1800385cb  jz      loc_1800387D7
0x1800385d1  mov     [rsp+180h+pReplaceSet], 0
0x1800385da  lea     rcx, [rsp+180h+pReplaceSet]
0x1800385df  mov     [rsp+180h+pReplaceSet+8], rcx
0x1800385e4  test    r12, r12
0x1800385e7  jz      short loc_18003861B
0x1800385e9  cmp     [rbx+154h], edx
0x1800385ef  jnz     short loc_18003861B
0x1800385f1  mov     rdx, [rsp+180h+var_130]
0x1800385f6  mov     r9d, r14d
0x1800385f9  mov     r8, r12
0x1800385fc  mov     rcx, rax
0x1800385ff  call    Dns_CreatePtrRecordExEx
0x180038604  test    rax, rax
0x180038607  jz      short loc_180038616
0x180038609  mov     rcx, [rsp+180h+pReplaceSet+8]
0x18003860e  mov     [rcx], rax
0x180038611  mov     [rsp+180h+pReplaceSet+8], rax
0x180038616  mov     rax, [rsp+180h+var_138]
0x18003861b  test    r15, r15
0x18003861e  jz      short loc_180038645
0x180038620  mov     rdx, [rsp+180h+var_130]
0x180038625  mov     r9d, r14d
0x180038628  mov     r8, r15
0x18003862b  mov     rcx, rax
0x18003862e  call    Dns_CreatePtrRecordExEx
0x180038633  test    rax, rax
0x180038636  jz      short loc_180038645
0x180038638  mov     rcx, [rsp+180h+pReplaceSet+8]
0x18003863d  mov     [rcx], rax
0x180038640  mov     [rsp+180h+pReplaceSet+8], rax
0x180038645  mov     r14, [rsp+180h+pReplaceSet]
0x18003864a  test    r14, r14
0x18003864d  jz      loc_1800387CD
0x180038653  mov     edi, 60h ; '`'
0x180038658  lea     rcx, [rsp+180h+pExtraInfo]; void *
0x18003865d  mov     r8d, edi; Size
0x180038660  xor     edx, edx; Val
0x180038662  call    memset_0
0x180038667  mov     r8d, edi; Size
0x18003866a  mov     [rsp+180h+pExtraInfo], 80000001h
0x180038672  xor     edx, edx; Val
0x180038674  mov     [rsp+180h+var_10C], edi
0x180038678  lea     rcx, [rbp+80h+var_B0]; void *
0x18003867c  mov     [rbp+80h+var_100], 2
0x180038683  call    memset_0
0x180038688  mov     rax, [rbx+60h]
0x18003868c  mov     [rbp+80h+var_98], rax
0x180038690  lea     rax, [rbp+80h+var_B0]
0x180038694  mov     [rsp+180h+var_108], rax
0x180038699  xor     eax, eax
0x18003869b  cmp     cs:g_fVelocityRpcUpdate, eax
0x1800386a1  mov     [rbp+80h+var_B0], 80000001h
0x1800386a8  mov     [rbp+80h+var_AC], edi
0x1800386ab  mov     [rbp+80h+var_A0], 0Ah
0x1800386b2  jz      short loc_1800386D7
0x1800386b4  test    esi, esi
0x1800386b6  jz      short loc_1800386D2
0x1800386b8  xor     r8d, r8d; hContext
0x1800386bb  xor     edx, edx; Options
0x1800386bd  lea     r9, [rsp+180h+pExtraInfo]; pExtraInfo
0x1800386c2  mov     [rsp+180h+pReserved], rax; pReserved
0x1800386c7  mov     rcx, r14; pReplaceSet
0x1800386ca  call    cs:__imp_DnsReplaceRecordSetW
0x1800386d0  jmp     short loc_180038708
0x1800386d2  xor     r8d, r8d
0x1800386d5  jmp     short loc_1800386EB
0x1800386d7  test    esi, esi
0x1800386d9  jz      short loc_1800386E5
0x1800386db  xor     r8d, r8d
0x1800386de  mov     edx, 200h
0x1800386e3  jmp     short loc_1800386BD
0x1800386e5  mov     r8d, 200h; Options
0x1800386eb  mov     [rsp+180h+var_158], rax; pReserved
0x1800386f0  xor     r9d, r9d; hCredentials
0x1800386f3  lea     rax, [rsp+180h+pExtraInfo]
0x1800386f8  mov     rdx, r14; pDeleteRecords
0x1800386fb  xor     ecx, ecx; pAddRecords
0x1800386fd  mov     [rsp+180h+pReserved], rax; pExtraList
0x180038702  call    cs:__imp_DnsModifyRecordsInSet_W
0x180038708  mov     edi, eax
0x18003870a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038711  jz      short loc_180038730
0x180038713  test    esi, esi
0x180038715  mov     dword ptr [rsp+180h+var_158], edi
0x180038719  lea     rax, aModifyRemove; "Modify (remove)"
0x180038720  lea     r9, aReplace; "Replace"
0x180038727  cmovz   r9, rax
0x18003872b  call    WPP_SF_ssD
0x180038730  test    esi, esi
0x180038732  jz      short loc_18003873D
0x180038734  cmp     dword ptr [rbx+12Ch], 0
0x18003873b  jnz     short loc_18003876D
0x18003873d  mov     rax, [rsp+180h+var_138]
0x180038742  xor     r9d, r9d
0x180038745  mov     [rsp+180h+var_158], rax
0x18003874a  test    esi, esi
0x18003874c  lea     rax, [rbp+80h+var_F2]
0x180038750  mov     r8d, 4
0x180038756  setz    r9b
0x18003875a  mov     [rsp+180h+pReserved], rax
0x18003875f  mov     edx, edi
0x180038761  mov     rcx, rbx
0x180038764  call    areg_LogRegistration
0x180038769  test    esi, esi
0x18003876b  jz      short loc_180038799
0x18003876d  test    edi, edi
0x18003876f  jnz     short loc_1800387C1
0x180038771  test    byte ptr [rbx+0F4h], 8
0x180038778  jz      short loc_180038784
0x18003877a  mov     dword ptr [rbx+114h], 1
0x180038784  test    byte ptr [rbx+0F8h], 8
0x18003878b  jz      short loc_1800387C1
0x18003878d  mov     dword ptr [rbx+118h], 1
0x180038797  jmp     short loc_1800387C1
0x180038799  test    edi, edi
0x18003879b  jz      short loc_1800387C1
0x18003879d  test    byte ptr [rbx+0F4h], 8
0x1800387a4  mov     eax, [rsp+180h+var_150]
0x1800387a8  cmovnz  eax, edi
0x1800387ab  test    byte ptr [rbx+0F8h], 8
0x1800387b2  mov     [rsp+180h+var_150], eax
0x1800387b6  mov     eax, [rsp+180h+var_14C]
0x1800387ba  cmovnz  eax, edi
0x1800387bd  mov     [rsp+180h+var_14C], eax
0x1800387c1  mov     rcx, r14
0x1800387c4  call    Dns_RecordListFree
0x1800387c9  mov     edi, [rsp+180h+var_140]
0x1800387cd  mov     r14d, [rsp+180h+var_148]
0x1800387d2  mov     edx, 2
0x1800387d7  mov     eax, [rsp+180h+var_144]
0x1800387db  inc     eax
0x1800387dd  mov     [rsp+180h+var_144], eax
0x1800387e1  cmp     eax, [r13+4]
0x1800387e5  jb      loc_180038566
0x1800387eb  mov     ecx, [rsp+180h+var_150]
0x1800387ef  mov     edx, [rsp+180h+var_14C]
0x1800387f3  test    esi, esi
0x1800387f5  jnz     short loc_18003881D
0x1800387f7  test    byte ptr [rbx+0F4h], 8
0x1800387fe  jz      short loc_18003880A
0x180038800  test    ecx, ecx
0x180038802  jnz     short loc_18003880A
0x180038804  mov     [rbx+114h], ecx
0x18003880a  test    byte ptr [rbx+0F8h], 8
0x180038811  jz      short loc_18003881D
0x180038813  test    edx, edx
0x180038815  jnz     short loc_18003881D
0x180038817  mov     [rbx+118h], edx
0x18003881d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038824  jz      short loc_18003883C
0x180038826  mov     edx, 98h
0x18003882b  mov     ecx, 40Bh
0x180038830  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180038837  call    WPP_SF_
0x18003883c  mov     rcx, [rbp+80h+var_50]
0x180038840  xor     rcx, rsp; StackCookie
0x180038843  call    __security_check_cookie
0x180038848  add     rsp, 148h
0x18003884f  pop     r15
0x180038851  pop     r14
0x180038853  pop     r13
0x180038855  pop     r12
0x180038857  pop     rdi
0x180038858  pop     rsi
0x180038859  pop     rbx
0x18003885a  pop     rbp
0x18003885b  retn
```
