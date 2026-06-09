# NetpDcUpdateDomainEntry(_NL_DC_DOMAIN_ENTRY *,_GUID *,ushort const *,ushort const *,ushort const *)

- ea: `0x180009064`
- end: `0x1800094f5`
- name: `?NetpDcUpdateDomainEntry@@YAHPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG22@Z`
- size: `1169`
- prototype: `__int64 __fastcall(struct _NL_DC_DOMAIN_ENTRY *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000be30`
- `0x18007f110`

## callees

- `0x180003170`
- `0x180006fa8`
- `0x180007278`
- `0x180009064`
- `0x18000d418`
- `0x18000d450`
- `0x18000ed10`
- `0x18001852c`
- `0x180018690`
- `0x18001a260`
- `0x18001a30c`
- `0x18007fc38`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009088`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094dc`
- `netutils!NetApiBufferFree` at `0x1800091bf`
- `netutils!NetApiBufferFree` at `0x1800092cc`
- `netutils!NetApiBufferFree` at `0x1800091bf`
- `netutils!NetApiBufferFree` at `0x1800092cc`
- `netutils!NetApiBufferAllocate` at `0x1800091e8`
- `netutils!NetApiBufferAllocate` at `0x1800091e8`
- `netutils!NetpwNameCompare` at `0x1800090c9`
- `netutils!NetpwNameCompare` at `0x1800090c9`

## string_xrefs

- `0x1800090ee`: `NetpDcUpdateDomainEntry: Netbios domain name '%ws' too long\n`
- `0x180009146`: `Cache: %ws %ws: Set netbios domain name\n`
- `0x18000922c`: `Cache: %ws %ws: Set DNS domain name\n`
- `0x1800092ef`: `Cache: %ws %ws: Set resolved single label DNS domain name as %ws\n`
- `0x18000937a`: `Cache: %ws %ws: is now a duplicate of %ws %ws\n`
- `0x180009435`: `Cache: %ws %ws: grab entry %ld from %ws %ws\n`

## pseudocode

```c
__int64 __fastcall NetpDcUpdateDomainEntry(
        struct _NL_DC_DOMAIN_ENTRY *a1,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *Src)
{
  __int64 v9; // r14
  unsigned int v10; // esi
  __int64 v11; // rbp
  int v12; // r15d
  unsigned __int64 v13; // rax
  const unsigned __int16 *v14; // rcx
  void *v15; // rcx
  DWORD v16; // ebp
  LPVOID v17; // r9
  __int64 v18; // rax
  unsigned __int16 *v19; // rdi
  const unsigned __int16 *v20; // rcx
  void *v21; // rcx
  __int64 v22; // rax
  struct _NL_DC_DOMAIN_ENTRY *DomainEntry; // rax
  unsigned int i; // ebp
  _OWORD *v25; // rdx
  struct _NL_DC_DOMAIN_ENTRY *v26; // rdi
  __int64 v28; // [rsp+20h] [rbp-68h]
  LPVOID Buffer; // [rsp+90h] [rbp+8h] BYREF

  EnterCriticalSection(&NlDcCritSect);
  v9 = 0;
  v10 = 1;
  if ( !*((_BYTE *)a1 + 88) )
  {
    v11 = -1;
    v12 = 0;
    if ( a3 )
    {
      if ( !*((_WORD *)a1 + 18) || (unsigned int)NetpwNameCompare((char *)a1 + 36, a3, 6) )
      {
        v13 = -1;
        do
          ++v13;
        while ( a3[v13] );
        if ( v13 > 0xF )
        {
          NlPrintRoutine(0x100u, L"NetpDcUpdateDomainEntry: Netbios domain name '%ws' too long\n", a3);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids, a3);
          goto LABEL_11;
        }
        wcscpy_s((wchar_t *)a1 + 18, 0x10u, a3);
        v12 = 1;
        NlPrintRoutine(0x20000u, L"Cache: %ws %ws: Set netbios domain name\n", (char *)a1 + 36, *((_QWORD *)a1 + 9));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)&WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids,
            (_DWORD)a1 + 36,
            *((_QWORD *)a1 + 9));
      }
      v9 = 0;
    }
    if ( a4 )
    {
      v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 9);
      if ( !v14 || !(unsigned int)NlEqualDnsName(v14, a4) )
      {
        v15 = (void *)*((_QWORD *)a1 + 9);
        if ( v15 )
          NetApiBufferFree(v15);
        Buffer = 0;
        do
          ++v11;
        while ( a4[v11] );
        v16 = 2 * v11 + 2;
        if ( NetApiBufferAllocate(v16, &Buffer) )
        {
          *((_QWORD *)a1 + 9) = 0;
LABEL_11:
          v10 = 0;
          goto LABEL_57;
        }
        memcpy_0(Buffer, a4, v16);
        v17 = Buffer;
        *((_QWORD *)a1 + 9) = Buffer;
        if ( !v17 )
          goto LABEL_11;
        v12 = 1;
        NlPrintRoutine(0x20000u, L"Cache: %ws %ws: Set DNS domain name\n", (char *)a1 + 36);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)&WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids,
            (_DWORD)a1 + 36,
            *((_QWORD *)a1 + 9));
      }
    }
    if ( a2 )
    {
      v18 = *(_QWORD *)((char *)a1 + 20) - *(_QWORD *)&a2->Data1;
      if ( !v18 )
        v18 = *(_QWORD *)((char *)a1 + 28) - *(_QWORD *)a2->Data4;
      if ( !v18 )
      {
        v12 = 1;
        *(struct _GUID *)((char *)a1 + 20) = *a2;
      }
    }
    v19 = Src;
    if ( !Src || (v20 = (const unsigned __int16 *)*((_QWORD *)a1 + 10)) != 0 && (unsigned int)NlEqualDnsName(v20, Src) )
    {
      if ( !v12 )
        goto LABEL_57;
    }
    else
    {
      v21 = (void *)*((_QWORD *)a1 + 10);
      if ( v21 )
        NetApiBufferFree(v21);
      v22 = NetpAllocWStrFromWStr(v19);
      *((_QWORD *)a1 + 10) = v22;
      if ( !v22 )
        goto LABEL_11;
      NlPrintRoutine(
        0x20000u,
        L"Cache: %ws %ws: Set resolved single label DNS domain name as %ws\n",
        (char *)a1 + 36,
        *((_QWORD *)a1 + 9),
        v22);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)&WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids,
          (_DWORD)a1 + 36,
          *((_QWORD *)a1 + 9),
          *((_QWORD *)a1 + 10));
    }
    DomainEntry = NetpDcFindDomainEntry(
                    (struct _GUID *)((char *)a1 + 20),
                    (const unsigned __int16 *)a1 + 18,
                    *((const unsigned __int16 **)a1 + 9),
                    a1,
                    1);
    while ( 1 )
    {
      v26 = DomainEntry;
      if ( !DomainEntry )
        break;
      NlPrintRoutine(
        0x20000u,
        L"Cache: %ws %ws: is now a duplicate of %ws %ws\n",
        (char *)a1 + 36,
        *((_QWORD *)a1 + 9),
        (char *)DomainEntry + 36,
        *((_QWORD *)DomainEntry + 9));
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SSSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)&WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids,
          (_DWORD)a1 + 36,
          *((_QWORD *)a1 + 9),
          (__int64)v26 + 36,
          *((_QWORD *)v26 + 9));
      for ( i = 0; i < 6; ++i )
      {
        if ( *((struct _NL_DC_DOMAIN_ENTRY **)a1 + 5 * v9 + 12) == (struct _NL_DC_DOMAIN_ENTRY *)((char *)a1
                                                                                                + 40 * v9
                                                                                                + 96) )
        {
          v25 = (_OWORD *)((char *)v26 + 40 * v9 + 96);
          if ( *(_OWORD **)v25 != v25 )
          {
            *(_OWORD *)((char *)a1 + 40 * v9 + 96) = *v25;
            *((_QWORD *)a1 + 5 * v9 + 14) = 0;
            *((_QWORD *)a1 + 5 * v9 + 16) = 0;
            *((_BYTE *)a1 + 40 * v9 + 120) = 0;
            *((_QWORD *)v26 + 5 * v9 + 13) = v25;
            *(_QWORD *)v25 = v25;
            LODWORD(v28) = i;
            NlPrintRoutine(
              0x20000u,
              L"Cache: %ws %ws: grab entry %ld from %ws %ws\n",
              (char *)a1 + 36,
              *((_QWORD *)a1 + 9),
              v28,
              (char *)v26 + 36,
              *((_QWORD *)v26 + 9));
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_SSlSS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                *((_QWORD *)a1 + 9),
                i,
                (__int64)v26 + 36,
                *((_QWORD *)v26 + 9));
          }
        }
        ++v9;
      }
      NetpDcDeleteDomainEntry((struct _NL_DC_DOMAIN_ENTRY ***)v26);
      NetpDcDerefDomainEntry(v26);
      DomainEntry = NetpDcFindDomainEntry(
                      (struct _GUID *)((char *)a1 + 20),
                      (const unsigned __int16 *)a1 + 18,
                      *((const unsigned __int16 **)a1 + 9),
                      a1,
                      1);
      v9 = 0;
    }
  }
LABEL_57:
  LeaveCriticalSection(&NlDcCritSect);
  return v10;
}

```

## disassembly

```asm
0x180009064  push    rbx
0x180009066  push    rbp
0x180009067  push    rsi
0x180009068  push    rdi
0x180009069  push    r12
0x18000906b  push    r13
0x18000906d  push    r14
0x18000906f  push    r15
0x180009071  sub     rsp, 48h
0x180009075  mov     rbx, rcx
0x180009078  mov     r12, r9
0x18000907b  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009082  mov     rdi, r8
0x180009085  mov     r13, rdx
0x180009088  call    cs:__imp_EnterCriticalSection
0x18000908e  xor     r14d, r14d
0x180009091  mov     esi, 1
0x180009096  cmp     [rbx+58h], r14b
0x18000909a  jnz     loc_1800094D5
0x1800090a0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800090a4  mov     r15d, r14d
0x1800090a7  test    rdi, rdi
0x1800090aa  jz      loc_180009194
0x1800090b0  lea     r14, [rbx+24h]
0x1800090b4  xor     ecx, ecx
0x1800090b6  cmp     [r14], cx
0x1800090ba  jz      short loc_1800090D9
0x1800090bc  xor     r9d, r9d
0x1800090bf  lea     r8d, [rsi+5]
0x1800090c3  mov     rdx, rdi
0x1800090c6  mov     rcx, r14
0x1800090c9  call    cs:__imp_NetpwNameCompare
0x1800090cf  xor     ecx, ecx
0x1800090d1  test    eax, eax
0x1800090d3  jz      loc_180009191
0x1800090d9  mov     rax, rbp
0x1800090dc  inc     rax
0x1800090df  cmp     [rdi+rax*2], cx
0x1800090e3  jnz     short loc_1800090DC
0x1800090e5  mov     r8, rdi; Source
0x1800090e8  cmp     rax, 0Fh
0x1800090ec  jbe     short loc_180009135
0x1800090ee  lea     rdx, aNetpdcupdatedo; "NetpDcUpdateDomainEntry: Netbios domain"...
0x1800090f5  mov     ecx, 100h; unsigned int
0x1800090fa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800090ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009106  test    byte ptr [rcx+1Ch], 4
0x18000910a  jz      short loc_18000912A
0x18000910c  cmp     byte ptr [rcx+19h], 2
0x180009110  jb      short loc_18000912A
0x180009112  mov     rcx, [rcx+10h]
0x180009116  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x18000911d  mov     edx, 1Dh
0x180009122  mov     r9, rdi
0x180009125  call    WPP_SF_S
0x18000912a  xor     r14d, r14d
0x18000912d  mov     esi, r14d
0x180009130  jmp     loc_1800094D5
0x180009135  mov     edx, 10h; SizeInWords
0x18000913a  mov     rcx, r14; Destination
0x18000913d  call    wcscpy_s
0x180009142  mov     r9, [rbx+48h]
0x180009146  lea     rdx, aCacheWsWsSetNe; "Cache: %ws %ws: Set netbios domain name"...
0x18000914d  mov     r8, r14
0x180009150  mov     ecx, 20000h; unsigned int
0x180009155  mov     r15d, esi
0x180009158  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000915d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009164  test    byte ptr [rcx+1Ch], 4
0x180009168  jz      short loc_180009191
0x18000916a  cmp     byte ptr [rcx+19h], 4
0x18000916e  jb      short loc_180009191
0x180009170  mov     rax, [rbx+48h]
0x180009174  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x18000917b  mov     rcx, [rcx+10h]
0x18000917f  mov     edx, 1Eh
0x180009184  mov     r9, r14
0x180009187  mov     [rsp+88h+var_68], rax
0x18000918c  call    WPP_SF_SS
0x180009191  xor     r14d, r14d
0x180009194  test    r12, r12
0x180009197  jz      loc_180009270
0x18000919d  mov     rcx, [rbx+48h]; unsigned __int16 *
0x1800091a1  test    rcx, rcx
0x1800091a4  jz      short loc_1800091B6
0x1800091a6  mov     rdx, r12; unsigned __int16 *
0x1800091a9  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800091ae  test    eax, eax
0x1800091b0  jnz     loc_180009270
0x1800091b6  mov     rcx, [rbx+48h]; Buffer
0x1800091ba  test    rcx, rcx
0x1800091bd  jz      short loc_1800091C5
0x1800091bf  call    cs:__imp_NetApiBufferFree
0x1800091c5  mov     [rsp+88h+Buffer], r14
0x1800091cd  inc     rbp
0x1800091d0  cmp     [r12+rbp*2], r14w
0x1800091d5  jnz     short loc_1800091CD
0x1800091d7  lea     ebp, ds:2[rbp*2]
0x1800091de  mov     ecx, ebp; ByteCount
0x1800091e0  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800091e8  call    cs:__imp_NetApiBufferAllocate
0x1800091ee  test    eax, eax
0x1800091f0  jz      short loc_1800091FB
0x1800091f2  mov     [rbx+48h], r14
0x1800091f6  jmp     loc_18000912D
0x1800091fb  mov     rcx, [rsp+88h+Buffer]; void *
0x180009203  mov     rdx, r12; Src
0x180009206  mov     r8d, ebp; Size
0x180009209  call    memcpy_0
0x18000920e  mov     r9, [rsp+88h+Buffer]
0x180009216  mov     [rbx+48h], r9
0x18000921a  test    r9, r9
0x18000921d  jz      loc_18000912D
0x180009223  lea     r8, [rbx+24h]
0x180009227  mov     ecx, 20000h; unsigned int
0x18000922c  lea     rdx, aCacheWsWsSetDn; "Cache: %ws %ws: Set DNS domain name\n"
0x180009233  mov     r15d, esi
0x180009236  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000923b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009242  test    byte ptr [rcx+1Ch], 4
0x180009246  jz      short loc_180009270
0x180009248  cmp     byte ptr [rcx+19h], 4
0x18000924c  jb      short loc_180009270
0x18000924e  mov     rax, [rbx+48h]
0x180009252  lea     r9, [rbx+24h]
0x180009256  mov     rcx, [rcx+10h]
0x18000925a  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x180009261  mov     edx, 1Fh
0x180009266  mov     [rsp+88h+var_68], rax
0x18000926b  call    WPP_SF_SS
0x180009270  test    r13, r13
0x180009273  jz      short loc_180009299
0x180009275  mov     rax, [rbx+14h]
0x180009279  sub     rax, [r13+0]
0x18000927d  jnz     short loc_180009287
0x18000927f  mov     rax, [rbx+1Ch]
0x180009283  sub     rax, [r13+8]
0x180009287  test    rax, rax
0x18000928a  jnz     short loc_180009299
0x18000928c  movups  xmm0, xmmword ptr [r13+0]
0x180009291  mov     r15d, esi
0x180009294  movdqu  xmmword ptr [rbx+14h], xmm0
0x180009299  mov     rdi, [rsp+88h+Src]
0x1800092a1  test    rdi, rdi
0x1800092a4  jz      loc_180009345
0x1800092aa  mov     rcx, [rbx+50h]; unsigned __int16 *
0x1800092ae  test    rcx, rcx
0x1800092b1  jz      short loc_1800092C3
0x1800092b3  mov     rdx, rdi; unsigned __int16 *
0x1800092b6  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800092bb  test    eax, eax
0x1800092bd  jnz     loc_180009345
0x1800092c3  mov     rcx, [rbx+50h]; Buffer
0x1800092c7  test    rcx, rcx
0x1800092ca  jz      short loc_1800092D2
0x1800092cc  call    cs:__imp_NetApiBufferFree
0x1800092d2  mov     rcx, rdi; Src
0x1800092d5  call    NetpAllocWStrFromWStr
0x1800092da  mov     [rbx+50h], rax
0x1800092de  test    rax, rax
0x1800092e1  jz      loc_18000912D
0x1800092e7  mov     r9, [rbx+48h]
0x1800092eb  lea     r8, [rbx+24h]
0x1800092ef  lea     rdx, aCacheWsWsSetRe; "Cache: %ws %ws: Set resolved single lab"...
0x1800092f6  mov     [rsp+88h+var_68], rax
0x1800092fb  mov     ecx, 20000h; unsigned int
0x180009300  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000930c  test    byte ptr [rcx+1Ch], 4
0x180009310  jz      short loc_18000934E
0x180009312  cmp     byte ptr [rcx+19h], 4
0x180009316  jb      short loc_18000934E
0x180009318  mov     rax, [rbx+50h]
0x18000931c  lea     r9, [rbx+24h]
0x180009320  mov     rcx, [rcx+10h]
0x180009324  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x18000932b  mov     qword ptr [rsp+88h+var_60], rax
0x180009330  mov     edx, 20h ; ' '
0x180009335  mov     rax, [rbx+48h]
0x180009339  mov     [rsp+88h+var_68], rax
0x18000933e  call    WPP_SF_SSS
0x180009343  jmp     short loc_18000934E
0x180009345  test    r15d, r15d
0x180009348  jz      loc_1800094D5
0x18000934e  mov     r8, [rbx+48h]; unsigned __int16 *
0x180009352  lea     r15, [rbx+24h]
0x180009356  mov     rdx, r15; unsigned __int16 *
0x180009359  mov     dword ptr [rsp+88h+var_68], esi; int
0x18000935d  lea     rcx, [rbx+14h]; struct _GUID *
0x180009361  mov     r9, rbx; struct _NL_DC_DOMAIN_ENTRY *
0x180009364  call    ?NetpDcFindDomainEntry@@YAPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG1PEAU1@H@Z; NetpDcFindDomainEntry(_GUID *,ushort const *,ushort const *,_NL_DC_DOMAIN_ENTRY *,int)
0x180009369  jmp     loc_1800094C9
0x18000936e  mov     rcx, [rdi+48h]
0x180009372  lea     r12, [rdi+24h]
0x180009376  mov     r9, [rbx+48h]
0x18000937a  lea     rdx, aCacheWsWsIsNow; "Cache: %ws %ws: is now a duplicate of %"...
0x180009381  mov     qword ptr [rsp+88h+var_60], rcx
0x180009386  mov     r8, r15
0x180009389  mov     ecx, 20000h; unsigned int
0x18000938e  mov     [rsp+88h+var_68], r12
0x180009393  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939f  test    byte ptr [rcx+1Ch], 4
0x1800093a3  jz      short loc_1800093DA
0x1800093a5  cmp     byte ptr [rcx+19h], 4
0x1800093a9  jb      short loc_1800093DA
0x1800093ab  mov     rax, [rdi+48h]
0x1800093af  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x1800093b6  mov     rcx, [rcx+10h]
0x1800093ba  mov     edx, 21h ; '!'
0x1800093bf  mov     [rsp+88h+var_58], rax
0x1800093c4  mov     r9, r15
0x1800093c7  mov     rax, [rbx+48h]
0x1800093cb  mov     qword ptr [rsp+88h+var_60], r12
0x1800093d0  mov     [rsp+88h+var_68], rax
0x1800093d5  call    WPP_SF_SSSS
0x1800093da  mov     ebp, r14d
0x1800093dd  xor     r13d, r13d
0x1800093e0  lea     rcx, [r14+r14*4]
0x1800093e4  lea     rax, [rbx+60h]
0x1800093e8  lea     rax, [rax+rcx*8]
0x1800093ec  cmp     [rax], rax
0x1800093ef  jnz     loc_180009491
0x1800093f5  lea     rdx, [rcx+0Ch]
0x1800093f9  lea     rdx, [rdi+rdx*8]
0x1800093fd  cmp     [rdx], rdx
0x180009400  jz      loc_180009491
0x180009406  movups  xmm0, xmmword ptr [rdx]
0x180009409  lea     rax, [r14+r14*4]
0x18000940d  mov     r8, r15
0x180009410  movdqu  xmmword ptr [rbx+rcx*8+60h], xmm0
0x180009416  mov     [rbx+rcx*8+70h], r13
0x18000941b  mov     [rbx+rcx*8+80h], r13
0x180009423  mov     [rbx+rax*8+78h], r13b
0x180009428  mov     [rdi+rcx*8+68h], rdx
0x18000942d  mov     ecx, 20000h; unsigned int
0x180009432  mov     [rdx], rdx
0x180009435  lea     rdx, aCacheWsWsGrabE; "Cache: %ws %ws: grab entry %ld from %ws"...
0x18000943c  mov     rax, [rdi+48h]
0x180009440  mov     r9, [rbx+48h]
0x180009444  mov     [rsp+88h+var_58], rax
0x180009449  mov     qword ptr [rsp+88h+var_60], r12
0x18000944e  mov     dword ptr [rsp+88h+var_68], ebp
0x180009452  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009457  mov     rcx, cs:WPP_GLOBAL_Control
0x18000945e  test    byte ptr [rcx+1Ch], 4
0x180009462  jz      short loc_180009491
0x180009464  cmp     byte ptr [rcx+19h], 4
0x180009468  jb      short loc_180009491
0x18000946a  mov     rax, [rdi+48h]
0x18000946e  mov     r9, r15
0x180009471  mov     rcx, [rcx+10h]; LoggerHandle
0x180009475  mov     [rsp+88h+var_50], rax; __int64
0x18000947a  mov     rax, [rbx+48h]
0x18000947e  mov     [rsp+88h+var_58], r12; __int64
0x180009483  mov     dword ptr [rsp+88h+var_60], ebp; char
0x180009487  mov     [rsp+88h+var_68], rax; __int64
0x18000948c  call    WPP_SF_SSlSS
0x180009491  add     ebp, esi
0x180009493  add     r14, rsi
0x180009496  cmp     ebp, 6
0x180009499  jb      loc_1800093E0
0x18000949f  mov     rcx, rdi; struct _NL_DC_DOMAIN_ENTRY *
0x1800094a2  call    ?NetpDcDeleteDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDeleteDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x1800094a7  mov     rcx, rdi; struct _NL_DC_DOMAIN_ENTRY *
0x1800094aa  call    ?NetpDcDerefDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDerefDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x1800094af  mov     r8, [rbx+48h]; unsigned __int16 *
0x1800094b3  lea     rcx, [rbx+14h]; struct _GUID *
0x1800094b7  mov     r9, rbx; struct _NL_DC_DOMAIN_ENTRY *
0x1800094ba  mov     dword ptr [rsp+88h+var_68], esi; int
0x1800094be  mov     rdx, r15; unsigned __int16 *
0x1800094c1  call    ?NetpDcFindDomainEntry@@YAPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG1PEAU1@H@Z; NetpDcFindDomainEntry(_GUID *,ushort const *,ushort const *,_NL_DC_DOMAIN_ENTRY *,int)
0x1800094c6  xor     r14d, r14d
0x1800094c9  mov     rdi, rax
0x1800094cc  test    rax, rax
0x1800094cf  jnz     loc_18000936E
0x1800094d5  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800094dc  call    cs:__imp_LeaveCriticalSection
0x1800094e2  mov     eax, esi
0x1800094e4  add     rsp, 48h
0x1800094e8  pop     r15
0x1800094ea  pop     r14
0x1800094ec  pop     r13
0x1800094ee  pop     r12
0x1800094f0  pop     rdi
0x1800094f1  pop     rsi
0x1800094f2  pop     rbp
0x1800094f3  pop     rbx
0x1800094f4  retn
```
