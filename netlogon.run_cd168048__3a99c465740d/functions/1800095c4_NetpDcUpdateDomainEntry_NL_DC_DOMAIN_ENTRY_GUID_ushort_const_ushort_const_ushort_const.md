# NetpDcUpdateDomainEntry(_NL_DC_DOMAIN_ENTRY *,_GUID *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800095c4`
- end: `0x180009a7a`
- name: `?NetpDcUpdateDomainEntry@@YAHPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG22@Z`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(struct _NL_DC_DOMAIN_ENTRY *@<rcx>, struct _GUID *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c4e8`
- `0x180084eac`

## callees

- `0x180003250`
- `0x180007234`
- `0x180007518`
- `0x1800095c4`
- `0x18000d9a4`
- `0x18000d9dc`
- `0x18000f3c0`
- `0x18001906c`
- `0x1800191e4`
- `0x18001af4c`
- `0x18001b000`
- `0x180085abc`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a5a`
- `netutils!NetApiBufferFree` at `0x18000972b`
- `netutils!NetApiBufferFree` at `0x180009844`
- `netutils!NetApiBufferFree` at `0x18000972b`
- `netutils!NetApiBufferFree` at `0x180009844`
- `netutils!NetApiBufferAllocate` at `0x18000975a`
- `netutils!NetApiBufferAllocate` at `0x18000975a`
- `netutils!NetpwNameCompare` at `0x18000962f`
- `netutils!NetpwNameCompare` at `0x18000962f`

## string_xrefs

- `0x18000965a`: `NetpDcUpdateDomainEntry: Netbios domain name '%ws' too long\n`
- `0x1800096b2`: `Cache: %ws %ws: Set netbios domain name\n`
- `0x1800097a4`: `Cache: %ws %ws: Set DNS domain name\n`
- `0x18000986d`: `Cache: %ws %ws: Set resolved single label DNS domain name as %ws\n`
- `0x1800098f8`: `Cache: %ws %ws: is now a duplicate of %ws %ws\n`
- `0x1800099b3`: `Cache: %ws %ws: grab entry %ld from %ws %ws\n`

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
      NetpDcDeleteDomainEntry(v26);
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
0x1800095c4  push    rbx
0x1800095c6  push    rbp
0x1800095c7  push    rsi
0x1800095c8  push    rdi
0x1800095c9  push    r12
0x1800095cb  push    r13
0x1800095cd  push    r14
0x1800095cf  push    r15
0x1800095d1  sub     rsp, 48h
0x1800095d5  mov     rbx, rcx
0x1800095d8  mov     r12, r9
0x1800095db  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800095e2  mov     rdi, r8
0x1800095e5  mov     r13, rdx
0x1800095e8  call    cs:__imp_EnterCriticalSection
0x1800095ef  nop     dword ptr [rax+rax+00h]
0x1800095f4  xor     r14d, r14d
0x1800095f7  mov     esi, 1
0x1800095fc  cmp     [rbx+58h], r14b
0x180009600  jnz     loc_180009A53
0x180009606  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000960a  mov     r15d, r14d
0x18000960d  test    rdi, rdi
0x180009610  jz      loc_180009700
0x180009616  lea     r14, [rbx+24h]
0x18000961a  xor     ecx, ecx
0x18000961c  cmp     [r14], cx
0x180009620  jz      short loc_180009645
0x180009622  xor     r9d, r9d
0x180009625  lea     r8d, [rsi+5]
0x180009629  mov     rdx, rdi
0x18000962c  mov     rcx, r14
0x18000962f  call    cs:__imp_NetpwNameCompare
0x180009636  nop     dword ptr [rax+rax+00h]
0x18000963b  xor     ecx, ecx
0x18000963d  test    eax, eax
0x18000963f  jz      loc_1800096FD
0x180009645  mov     rax, rbp
0x180009648  inc     rax
0x18000964b  cmp     [rdi+rax*2], cx
0x18000964f  jnz     short loc_180009648
0x180009651  mov     r8, rdi; Source
0x180009654  cmp     rax, 0Fh
0x180009658  jbe     short loc_1800096A1
0x18000965a  lea     rdx, aNetpdcupdatedo; "NetpDcUpdateDomainEntry: Netbios domain"...
0x180009661  mov     ecx, 100h; unsigned int
0x180009666  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000966b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009672  test    byte ptr [rcx+1Ch], 4
0x180009676  jz      short loc_180009696
0x180009678  cmp     byte ptr [rcx+19h], 2
0x18000967c  jb      short loc_180009696
0x18000967e  mov     rcx, [rcx+10h]
0x180009682  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x180009689  mov     edx, 1Dh
0x18000968e  mov     r9, rdi
0x180009691  call    WPP_SF_S
0x180009696  xor     r14d, r14d
0x180009699  mov     esi, r14d
0x18000969c  jmp     loc_180009A53
0x1800096a1  mov     edx, 10h; SizeInWords
0x1800096a6  mov     rcx, r14; Destination
0x1800096a9  call    wcscpy_s
0x1800096ae  mov     r9, [rbx+48h]
0x1800096b2  lea     rdx, aCacheWsWsSetNe; "Cache: %ws %ws: Set netbios domain name"...
0x1800096b9  mov     r8, r14
0x1800096bc  mov     ecx, 20000h; unsigned int
0x1800096c1  mov     r15d, esi
0x1800096c4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800096c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096d0  test    byte ptr [rcx+1Ch], 4
0x1800096d4  jz      short loc_1800096FD
0x1800096d6  cmp     byte ptr [rcx+19h], 4
0x1800096da  jb      short loc_1800096FD
0x1800096dc  mov     rax, [rbx+48h]
0x1800096e0  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x1800096e7  mov     rcx, [rcx+10h]
0x1800096eb  mov     edx, 1Eh
0x1800096f0  mov     r9, r14
0x1800096f3  mov     [rsp+88h+var_68], rax
0x1800096f8  call    WPP_SF_SS
0x1800096fd  xor     r14d, r14d
0x180009700  test    r12, r12
0x180009703  jz      loc_1800097E8
0x180009709  mov     rcx, [rbx+48h]; unsigned __int16 *
0x18000970d  test    rcx, rcx
0x180009710  jz      short loc_180009722
0x180009712  mov     rdx, r12; unsigned __int16 *
0x180009715  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18000971a  test    eax, eax
0x18000971c  jnz     loc_1800097E8
0x180009722  mov     rcx, [rbx+48h]; Buffer
0x180009726  test    rcx, rcx
0x180009729  jz      short loc_180009737
0x18000972b  call    cs:__imp_NetApiBufferFree
0x180009732  nop     dword ptr [rax+rax+00h]
0x180009737  mov     [rsp+88h+Buffer], r14
0x18000973f  inc     rbp
0x180009742  cmp     [r12+rbp*2], r14w
0x180009747  jnz     short loc_18000973F
0x180009749  lea     ebp, ds:2[rbp*2]
0x180009750  mov     ecx, ebp; ByteCount
0x180009752  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18000975a  call    cs:__imp_NetApiBufferAllocate
0x180009761  nop     dword ptr [rax+rax+00h]
0x180009766  test    eax, eax
0x180009768  jz      short loc_180009773
0x18000976a  mov     [rbx+48h], r14
0x18000976e  jmp     loc_180009699
0x180009773  mov     rcx, [rsp+88h+Buffer]; void *
0x18000977b  mov     rdx, r12; Src
0x18000977e  mov     r8d, ebp; Size
0x180009781  call    memcpy_0
0x180009786  mov     r9, [rsp+88h+Buffer]
0x18000978e  mov     [rbx+48h], r9
0x180009792  test    r9, r9
0x180009795  jz      loc_180009699
0x18000979b  lea     r8, [rbx+24h]
0x18000979f  mov     ecx, 20000h; unsigned int
0x1800097a4  lea     rdx, aCacheWsWsSetDn; "Cache: %ws %ws: Set DNS domain name\n"
0x1800097ab  mov     r15d, esi
0x1800097ae  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800097b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097ba  test    byte ptr [rcx+1Ch], 4
0x1800097be  jz      short loc_1800097E8
0x1800097c0  cmp     byte ptr [rcx+19h], 4
0x1800097c4  jb      short loc_1800097E8
0x1800097c6  mov     rax, [rbx+48h]
0x1800097ca  lea     r9, [rbx+24h]
0x1800097ce  mov     rcx, [rcx+10h]
0x1800097d2  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x1800097d9  mov     edx, 1Fh
0x1800097de  mov     [rsp+88h+var_68], rax
0x1800097e3  call    WPP_SF_SS
0x1800097e8  test    r13, r13
0x1800097eb  jz      short loc_180009811
0x1800097ed  mov     rax, [rbx+14h]
0x1800097f1  sub     rax, [r13+0]
0x1800097f5  jnz     short loc_1800097FF
0x1800097f7  mov     rax, [rbx+1Ch]
0x1800097fb  sub     rax, [r13+8]
0x1800097ff  test    rax, rax
0x180009802  jnz     short loc_180009811
0x180009804  movups  xmm0, xmmword ptr [r13+0]
0x180009809  mov     r15d, esi
0x18000980c  movdqu  xmmword ptr [rbx+14h], xmm0
0x180009811  mov     rdi, [rsp+88h+Src]
0x180009819  test    rdi, rdi
0x18000981c  jz      loc_1800098C3
0x180009822  mov     rcx, [rbx+50h]; unsigned __int16 *
0x180009826  test    rcx, rcx
0x180009829  jz      short loc_18000983B
0x18000982b  mov     rdx, rdi; unsigned __int16 *
0x18000982e  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180009833  test    eax, eax
0x180009835  jnz     loc_1800098C3
0x18000983b  mov     rcx, [rbx+50h]; Buffer
0x18000983f  test    rcx, rcx
0x180009842  jz      short loc_180009850
0x180009844  call    cs:__imp_NetApiBufferFree
0x18000984b  nop     dword ptr [rax+rax+00h]
0x180009850  mov     rcx, rdi; Src
0x180009853  call    NetpAllocWStrFromWStr
0x180009858  mov     [rbx+50h], rax
0x18000985c  test    rax, rax
0x18000985f  jz      loc_180009699
0x180009865  mov     r9, [rbx+48h]
0x180009869  lea     r8, [rbx+24h]
0x18000986d  lea     rdx, aCacheWsWsSetRe; "Cache: %ws %ws: Set resolved single lab"...
0x180009874  mov     [rsp+88h+var_68], rax
0x180009879  mov     ecx, 20000h; unsigned int
0x18000987e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009883  mov     rcx, cs:WPP_GLOBAL_Control
0x18000988a  test    byte ptr [rcx+1Ch], 4
0x18000988e  jz      short loc_1800098CC
0x180009890  cmp     byte ptr [rcx+19h], 4
0x180009894  jb      short loc_1800098CC
0x180009896  mov     rax, [rbx+50h]
0x18000989a  lea     r9, [rbx+24h]
0x18000989e  mov     rcx, [rcx+10h]
0x1800098a2  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x1800098a9  mov     qword ptr [rsp+88h+var_60], rax
0x1800098ae  mov     edx, 20h ; ' '
0x1800098b3  mov     rax, [rbx+48h]
0x1800098b7  mov     [rsp+88h+var_68], rax
0x1800098bc  call    WPP_SF_SSS
0x1800098c1  jmp     short loc_1800098CC
0x1800098c3  test    r15d, r15d
0x1800098c6  jz      loc_180009A53
0x1800098cc  mov     r8, [rbx+48h]; unsigned __int16 *
0x1800098d0  lea     r15, [rbx+24h]
0x1800098d4  mov     rdx, r15; unsigned __int16 *
0x1800098d7  mov     dword ptr [rsp+88h+var_68], esi; int
0x1800098db  lea     rcx, [rbx+14h]; struct _GUID *
0x1800098df  mov     r9, rbx; struct _NL_DC_DOMAIN_ENTRY *
0x1800098e2  call    ?NetpDcFindDomainEntry@@YAPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG1PEAU1@H@Z; NetpDcFindDomainEntry(_GUID *,ushort const *,ushort const *,_NL_DC_DOMAIN_ENTRY *,int)
0x1800098e7  jmp     loc_180009A47
0x1800098ec  mov     rcx, [rdi+48h]
0x1800098f0  lea     r12, [rdi+24h]
0x1800098f4  mov     r9, [rbx+48h]
0x1800098f8  lea     rdx, aCacheWsWsIsNow; "Cache: %ws %ws: is now a duplicate of %"...
0x1800098ff  mov     qword ptr [rsp+88h+var_60], rcx
0x180009904  mov     r8, r15
0x180009907  mov     ecx, 20000h; unsigned int
0x18000990c  mov     [rsp+88h+var_68], r12
0x180009911  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009916  mov     rcx, cs:WPP_GLOBAL_Control
0x18000991d  test    byte ptr [rcx+1Ch], 4
0x180009921  jz      short loc_180009958
0x180009923  cmp     byte ptr [rcx+19h], 4
0x180009927  jb      short loc_180009958
0x180009929  mov     rax, [rdi+48h]
0x18000992d  lea     r8, WPP_3d1b0ae6cdb737ab4ae89c9dc7c526bc_Traceguids
0x180009934  mov     rcx, [rcx+10h]
0x180009938  mov     edx, 21h ; '!'
0x18000993d  mov     [rsp+88h+var_58], rax
0x180009942  mov     r9, r15
0x180009945  mov     rax, [rbx+48h]
0x180009949  mov     qword ptr [rsp+88h+var_60], r12
0x18000994e  mov     [rsp+88h+var_68], rax
0x180009953  call    WPP_SF_SSSS
0x180009958  mov     ebp, r14d
0x18000995b  xor     r13d, r13d
0x18000995e  lea     rcx, [r14+r14*4]
0x180009962  lea     rax, [rbx+60h]
0x180009966  lea     rax, [rax+rcx*8]
0x18000996a  cmp     [rax], rax
0x18000996d  jnz     loc_180009A0F
0x180009973  lea     rdx, [rcx+0Ch]
0x180009977  lea     rdx, [rdi+rdx*8]
0x18000997b  cmp     [rdx], rdx
0x18000997e  jz      loc_180009A0F
0x180009984  movups  xmm0, xmmword ptr [rdx]
0x180009987  lea     rax, [r14+r14*4]
0x18000998b  mov     r8, r15
0x18000998e  movdqu  xmmword ptr [rbx+rcx*8+60h], xmm0
0x180009994  mov     [rbx+rcx*8+70h], r13
0x180009999  mov     [rbx+rcx*8+80h], r13
0x1800099a1  mov     [rbx+rax*8+78h], r13b
0x1800099a6  mov     [rdi+rcx*8+68h], rdx
0x1800099ab  mov     ecx, 20000h; unsigned int
0x1800099b0  mov     [rdx], rdx
0x1800099b3  lea     rdx, aCacheWsWsGrabE; "Cache: %ws %ws: grab entry %ld from %ws"...
0x1800099ba  mov     rax, [rdi+48h]
0x1800099be  mov     r9, [rbx+48h]
0x1800099c2  mov     [rsp+88h+var_58], rax
0x1800099c7  mov     qword ptr [rsp+88h+var_60], r12
0x1800099cc  mov     dword ptr [rsp+88h+var_68], ebp
0x1800099d0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800099d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099dc  test    byte ptr [rcx+1Ch], 4
0x1800099e0  jz      short loc_180009A0F
0x1800099e2  cmp     byte ptr [rcx+19h], 4
0x1800099e6  jb      short loc_180009A0F
0x1800099e8  mov     rax, [rdi+48h]
0x1800099ec  mov     r9, r15
0x1800099ef  mov     rcx, [rcx+10h]; LoggerHandle
0x1800099f3  mov     [rsp+88h+var_50], rax; __int64
0x1800099f8  mov     rax, [rbx+48h]
0x1800099fc  mov     [rsp+88h+var_58], r12; __int64
0x180009a01  mov     dword ptr [rsp+88h+var_60], ebp; char
0x180009a05  mov     [rsp+88h+var_68], rax; __int64
0x180009a0a  call    WPP_SF_SSlSS
0x180009a0f  add     ebp, esi
0x180009a11  add     r14, rsi
0x180009a14  cmp     ebp, 6
0x180009a17  jb      loc_18000995E
0x180009a1d  mov     rcx, rdi; struct _NL_DC_DOMAIN_ENTRY *
0x180009a20  call    ?NetpDcDeleteDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDeleteDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x180009a25  mov     rcx, rdi; struct _NL_DC_DOMAIN_ENTRY *
0x180009a28  call    ?NetpDcDerefDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDerefDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x180009a2d  mov     r8, [rbx+48h]; unsigned __int16 *
0x180009a31  lea     rcx, [rbx+14h]; struct _GUID *
0x180009a35  mov     r9, rbx; struct _NL_DC_DOMAIN_ENTRY *
0x180009a38  mov     dword ptr [rsp+88h+var_68], esi; int
0x180009a3c  mov     rdx, r15; unsigned __int16 *
0x180009a3f  call    ?NetpDcFindDomainEntry@@YAPEAU_NL_DC_DOMAIN_ENTRY@@PEAU_GUID@@PEBG1PEAU1@H@Z; NetpDcFindDomainEntry(_GUID *,ushort const *,ushort const *,_NL_DC_DOMAIN_ENTRY *,int)
0x180009a44  xor     r14d, r14d
0x180009a47  mov     rdi, rax
0x180009a4a  test    rax, rax
0x180009a4d  jnz     loc_1800098EC
0x180009a53  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009a5a  call    cs:__imp_LeaveCriticalSection
0x180009a61  nop     dword ptr [rax+rax+00h]
0x180009a66  mov     eax, esi
0x180009a68  add     rsp, 48h
0x180009a6c  pop     r15
0x180009a6e  pop     r14
0x180009a70  pop     r13
0x180009a72  pop     r12
0x180009a74  pop     rdi
0x180009a75  pop     rsi
0x180009a76  pop     rbp
0x180009a77  pop     rbx
0x180009a78  retn
```
