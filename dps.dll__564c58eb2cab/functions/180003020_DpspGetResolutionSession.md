# DpspGetResolutionSession

- ea: `0x180003020`
- end: `0x18000348f`
- name: `DpspGetResolutionSession`
- size: `1135`
- prototype: `__int64 __fastcall(__int64, struct __SESSIONINFO **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004de4`
- `0x180013b4c`

## callees

- `0x1800013a0`
- `0x180003020`
- `0x180006c5c`
- `0x180008dc0`
- `0x180008ea0`
- `0x180008f10`
- `0x180009090`
- `0x18000a856`
- `0x18000bbd4`
- `0x18000f534`
- `0x180017818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000313e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000325c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000327f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000313e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000325c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000327f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003476`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000303e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000303e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032bd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003113`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003113`

## string_xrefs

- `0x180003186`: `DpspCreateSpecificSession`
- `0x1800033c6`: `DpspCreateSpecificSession`

## pseudocode

```c
__int64 __fastcall DpspGetResolutionSession(__int64 a1, struct __SESSIONINFO **a2)
{
  int v4; // r8d
  unsigned int v5; // ebx
  struct __SESSIONINFO *v6; // rsi
  struct __SESSIONINFO *v7; // r15
  __int64 v8; // rcx
  void *v9; // rax
  signed __int64 v10; // rdi
  int v11; // ebp
  int Args; // eax
  int v13; // r8d
  signed __int64 v14; // rax
  signed __int64 v15; // rbx
  unsigned int v16; // eax
  void *v17; // rax
  unsigned int v18; // eax
  void *v19; // rax
  __int64 v20; // rcx
  struct __SESSIONINFO *v21; // rax
  signed __int64 SessionHostFromSid; // [rsp+80h] [rbp+8h] BYREF

  EnterCriticalSection(&g_csDMList);
  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 1956;
      goto LABEL_3;
    }
    if ( !*(_QWORD *)(a1 + 768) )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (int)L"DpspGetSessionFromInstance",
        155,
        (int)L"Error = %d",
        87);
LABEL_8:
      v5 = -2147024809;
      goto LABEL_45;
    }
    v6 = g_pSessionHead;
    v7 = 0;
    if ( g_pSessionHead )
    {
      while ( 1 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 64));
        if ( *(_QWORD *)v6 == *(_QWORD *)(a1 + 40) && *((_QWORD *)v6 + 1) == *(_QWORD *)(a1 + 48) )
        {
          v8 = *((_QWORD *)v6 + 22);
          if ( v8 )
          {
            v7 = v6;
            if ( *(_DWORD *)(v8 + 40) == *(_DWORD *)(a1 + 108) )
            {
              if ( EqualSid(*(PSID *)(v8 + 32), *(PSID *)(a1 + 768)) )
                break;
            }
          }
        }
        if ( v6 )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 64));
        v6 = (struct __SESSIONINFO *)*((_QWORD *)v6 + 23);
        if ( !v6 )
          goto LABEL_21;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 64));
    }
    v5 = 0;
    if ( v6 )
      goto LABEL_44;
LABEL_21:
    if ( !v7 )
      goto LABEL_8;
    v9 = (void *)WdipAlloc(192);
    v10 = (signed __int64)v9;
    if ( !v9 )
    {
      v5 = -2147024882;
      LOBYTE(v11) = 14;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
        (int)L"DpspCreateSpecificSession",
        2022,
        (int)L"Error = %d",
        14);
LABEL_43:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspGetResolutionSession",
        1967,
        (int)L"Error = %d",
        v11);
      goto LABEL_45;
    }
    memset_0(v9, 0, 0xC0u);
    Args = WdipInitializeCriticalSection(v10 + 64);
    v11 = Args;
    if ( Args >= 0 )
    {
      WdipCopyGuid(v10, a1 + 40);
      v14 = _InterlockedExchangeAdd64(&g_ulConnectionId, 4u);
      *(_DWORD *)(v10 + 24) = 0;
      *(_QWORD *)(v10 + 168) = 0;
      *(_QWORD *)(v10 + 16) = (v14 + 4) | 1;
      EnterCriticalSection(&g_csHostList);
      SessionHostFromSid = DpspGetSessionHostFromSid(*(PSID *)(a1 + 768));
      v15 = SessionHostFromSid;
      if ( !SessionHostFromSid )
      {
        v11 = DpspCreateSpecificSessionHost(&SessionHostFromSid, *(void **)(a1 + 768), *(_DWORD *)(a1 + 108), 3);
        if ( v11 < 0 )
        {
          LeaveCriticalSection(&g_csHostList);
          v13 = 2054;
          LOBYTE(Args) = v11;
          goto LABEL_39;
        }
        v15 = SessionHostFromSid;
      }
      LeaveCriticalSection(&g_csHostList);
      *(_QWORD *)(v10 + 176) = v15;
      *(_DWORD *)(v10 + 28) = 0;
      *(_DWORD *)(v10 + 36) = 0;
      *(_DWORD *)(v10 + 32) = *((_DWORD *)v7 + 8);
      *(_DWORD *)(v10 + 40) = *((_DWORD *)v7 + 10);
      *(_DWORD *)(v10 + 56) = *((_DWORD *)v7 + 14);
      *(_DWORD *)(v10 + 156) = -1;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 64));
      *(_DWORD *)(v10 + 152) = *((_DWORD *)v7 + 38);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 64));
      *(_DWORD *)(v10 + 152) &= 0xFFFFFFF3;
      v16 = *((_DWORD *)v7 + 37);
      *(_DWORD *)(v10 + 148) = v16;
      v17 = (void *)WdipAlloc(v16);
      *(_QWORD *)(v10 + 128) = v17;
      if ( v17 )
      {
        memset_0(v17, 0, *(unsigned int *)(v10 + 148));
        Args = StringCbCopyW(*(unsigned __int16 **)(v10 + 128), *(unsigned int *)(v10 + 148), *((size_t **)v7 + 16));
        v11 = Args;
        if ( Args >= 0 )
        {
          if ( (*(_BYTE *)(v10 + 152) & 1) != 0 )
          {
            v18 = *((_DWORD *)v7 + 36);
            *(_DWORD *)(v10 + 144) = v18;
            v19 = (void *)WdipAlloc(v18);
            *(_QWORD *)(v10 + 136) = v19;
            if ( !v19 )
            {
              v11 = -2147024882;
              LOBYTE(Args) = 14;
              v13 = 2096;
              goto LABEL_39;
            }
            memset_0(v19, 0, *(unsigned int *)(v10 + 144));
            Args = StringCbCopyW(*(unsigned __int16 **)(v10 + 136), *(unsigned int *)(v10 + 144), *((size_t **)v7 + 17));
            v11 = Args;
            if ( Args < 0 )
            {
              v13 = 2103;
              goto LABEL_39;
            }
          }
          v6 = (struct __SESSIONINFO *)v10;
          *(_QWORD *)(v10 + 120) = v10 + 112;
          *(_QWORD *)(v10 + 112) = v10 + 112;
          v21 = g_pSessionHead;
          do
          {
            *(_QWORD *)(v10 + 184) = v21;
            v21 = (struct __SESSIONINFO *)_InterlockedCompareExchange64(
                                            (volatile signed __int64 *)&g_pSessionHead,
                                            v10,
                                            (signed __int64)v21);
          }
          while ( v21 != *(struct __SESSIONINFO **)(v10 + 184) );
LABEL_42:
          v5 = v11;
          if ( v11 < 0 )
            goto LABEL_43;
LABEL_44:
          *a2 = v6;
          goto LABEL_45;
        }
        v13 = 2089;
      }
      else
      {
        v11 = -2147024882;
        LOBYTE(Args) = 14;
        v13 = 2082;
      }
    }
    else
    {
      v13 = 2031;
    }
LABEL_39:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspCreateSpecificSession",
      v13,
      (int)L"Error = %d",
      Args);
    WdipDeleteCriticalSection(v10 + 64);
    WdipFree(*(_QWORD *)(v10 + 136));
    v20 = *(_QWORD *)(v10 + 128);
    *(_QWORD *)(v10 + 136) = 0;
    WdipFree(v20);
    *(_QWORD *)(v10 + 128) = 0;
    WdipFree(v10);
    goto LABEL_42;
  }
  v4 = 1955;
LABEL_3:
  v5 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (int)L"DpspGetResolutionSession",
    v4,
    (int)L"Error = %d",
    87);
LABEL_45:
  LeaveCriticalSection(&g_csDMList);
  return v5;
}

```

## disassembly

```asm
0x180003020  push    rbx
0x180003022  push    rbp
0x180003023  push    rsi
0x180003024  push    rdi
0x180003025  push    r12
0x180003027  push    r13
0x180003029  push    r14
0x18000302b  push    r15
0x18000302d  sub     rsp, 38h
0x180003031  mov     r14, rcx
0x180003034  mov     r12, rdx
0x180003037  lea     rcx, g_csDMList; lpCriticalSection
0x18000303e  call    cs:__imp_EnterCriticalSection
0x180003044  test    r14, r14
0x180003047  jnz     short loc_18000307B
0x180003049  mov     r8d, 7A3h; int
0x18000304f  mov     dword ptr [rsp+78h+Args], 57h ; 'W'; Args
0x180003057  mov     ebx, 80070057h
0x18000305c  lea     r9, aErrorD; "Error = %d"
0x180003063  lea     rdx, aDpspgetresolut; "DpspGetResolutionSession"
0x18000306a  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180003071  call    WdipTraceError
0x180003076  jmp     loc_18000346F
0x18000307b  test    r12, r12
0x18000307e  jnz     short loc_180003088
0x180003080  mov     r8d, 7A4h
0x180003086  jmp     short loc_18000304F
0x180003088  cmp     qword ptr [r14+300h], 0
0x180003090  jnz     short loc_1800030C4
0x180003092  lea     r9, aErrorD; "Error = %d"
0x180003099  mov     dword ptr [rsp+78h+Args], 57h ; 'W'; Args
0x1800030a1  mov     r8d, 9Bh; int
0x1800030a7  lea     rdx, aDpspgetsession; "DpspGetSessionFromInstance"
0x1800030ae  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800030b5  call    WdipTraceError
0x1800030ba  mov     ebx, 80070057h
0x1800030bf  jmp     loc_18000346F
0x1800030c4  mov     rsi, cs:g_pSessionHead
0x1800030cb  xor     r15d, r15d
0x1800030ce  test    rsi, rsi
0x1800030d1  jz      short loc_180003144
0x1800030d3  lea     rcx, [rsi+40h]; lpCriticalSection
0x1800030d7  call    cs:__imp_EnterCriticalSection
0x1800030dd  mov     rax, [rsi]
0x1800030e0  cmp     rax, [r14+28h]
0x1800030e4  jnz     short loc_18000311D
0x1800030e6  mov     rax, [rsi+8]
0x1800030ea  cmp     rax, [r14+30h]
0x1800030ee  jnz     short loc_18000311D
0x1800030f0  mov     rcx, [rsi+0B0h]
0x1800030f7  test    rcx, rcx
0x1800030fa  jz      short loc_18000311D
0x1800030fc  mov     eax, [r14+6Ch]
0x180003100  mov     r15, rsi
0x180003103  cmp     [rcx+28h], eax
0x180003106  jnz     short loc_18000311D
0x180003108  mov     rdx, [r14+300h]; pSid2
0x18000310f  mov     rcx, [rcx+20h]; pSid1
0x180003113  call    cs:__imp_EqualSid
0x180003119  test    eax, eax
0x18000311b  jnz     short loc_18000313A
0x18000311d  test    rsi, rsi
0x180003120  jz      short loc_18000312C
0x180003122  lea     rcx, [rsi+40h]; lpCriticalSection
0x180003126  call    cs:__imp_LeaveCriticalSection
0x18000312c  mov     rsi, [rsi+0B8h]
0x180003133  test    rsi, rsi
0x180003136  jnz     short loc_1800030D3
0x180003138  jmp     short loc_18000314F
0x18000313a  lea     rcx, [rsi+40h]; lpCriticalSection
0x18000313e  call    cs:__imp_LeaveCriticalSection
0x180003144  xor     ebx, ebx
0x180003146  test    rsi, rsi
0x180003149  jnz     loc_18000346B
0x18000314f  test    r15, r15
0x180003152  jz      loc_1800030BA
0x180003158  mov     ebx, 0C0h
0x18000315d  mov     ecx, ebx
0x18000315f  call    WdipAlloc
0x180003164  mov     rdi, rax
0x180003167  test    rax, rax
0x18000316a  jnz     short loc_1800031A0
0x18000316c  mov     ebx, 8007000Eh
0x180003171  mov     dword ptr [rsp+78h+Args], 0Eh; Args
0x180003179  lea     r9, aErrorD; "Error = %d"
0x180003180  mov     r8d, 7E6h; int
0x180003186  lea     rdx, aDpspcreatespec_0; "DpspCreateSpecificSession"
0x18000318d  mov     ebp, ebx
0x18000318f  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180003196  call    WdipTraceError
0x18000319b  jmp     loc_180003459
0x1800031a0  mov     r8, rbx; Size
0x1800031a3  xor     edx, edx; Val
0x1800031a5  mov     rcx, rdi; void *
0x1800031a8  call    memset_0
0x1800031ad  lea     rcx, [rdi+40h]
0x1800031b1  call    WdipInitializeCriticalSection
0x1800031b6  mov     ebp, eax
0x1800031b8  test    eax, eax
0x1800031ba  jns     short loc_1800031C7
0x1800031bc  mov     r8d, 7EFh
0x1800031c2  jmp     loc_1800033C3
0x1800031c7  lea     rdx, [r14+28h]
0x1800031cb  mov     rcx, rdi
0x1800031ce  call    WdipCopyGuid
0x1800031d3  mov     eax, 4
0x1800031d8  lock xadd cs:g_ulConnectionId, rax
0x1800031e1  add     rax, 4
0x1800031e5  mov     dword ptr [rdi+18h], 0
0x1800031ec  or      rax, 1
0x1800031f0  mov     qword ptr [rdi+0A8h], 0
0x1800031fb  lea     rcx, g_csHostList; lpCriticalSection
0x180003202  mov     [rdi+10h], rax
0x180003206  call    cs:__imp_EnterCriticalSection
0x18000320c  mov     edx, [r14+6Ch]
0x180003210  mov     ebp, 3
0x180003215  mov     rcx, [r14+300h]; pSid1
0x18000321c  mov     r8d, ebp
0x18000321f  call    DpspGetSessionHostFromSid
0x180003224  mov     [rsp+78h+arg_0], rax
0x18000322c  mov     rbx, rax
0x18000322f  test    rax, rax
0x180003232  jnz     short loc_180003278
0x180003234  mov     r8d, [r14+6Ch]
0x180003238  lea     rcx, [rsp+78h+arg_0]
0x180003240  mov     rdx, [r14+300h]
0x180003247  mov     r9d, ebp
0x18000324a  call    DpspCreateSpecificSessionHost
0x18000324f  mov     ebp, eax
0x180003251  test    eax, eax
0x180003253  jns     short loc_180003270
0x180003255  lea     rcx, g_csHostList; lpCriticalSection
0x18000325c  call    cs:__imp_LeaveCriticalSection
0x180003262  mov     r8d, 806h
0x180003268  movzx   eax, bp
0x18000326b  jmp     loc_1800033C6
0x180003270  mov     rbx, [rsp+78h+arg_0]
0x180003278  lea     rcx, g_csHostList; lpCriticalSection
0x18000327f  call    cs:__imp_LeaveCriticalSection
0x180003285  mov     [rdi+0B0h], rbx
0x18000328c  lea     rcx, [r15+40h]; lpCriticalSection
0x180003290  mov     dword ptr [rdi+1Ch], 0
0x180003297  mov     dword ptr [rdi+24h], 0
0x18000329e  mov     eax, [r15+20h]
0x1800032a2  mov     [rdi+20h], eax
0x1800032a5  mov     eax, [r15+28h]
0x1800032a9  mov     [rdi+28h], eax
0x1800032ac  mov     eax, [r15+38h]
0x1800032b0  mov     [rdi+38h], eax
0x1800032b3  mov     dword ptr [rdi+9Ch], 0FFFFFFFFh
0x1800032bd  call    cs:__imp_EnterCriticalSection
0x1800032c3  mov     eax, [r15+98h]
0x1800032ca  lea     rcx, [r15+40h]; lpCriticalSection
0x1800032ce  mov     [rdi+98h], eax
0x1800032d4  call    cs:__imp_LeaveCriticalSection
0x1800032da  and     dword ptr [rdi+98h], 0FFFFFFF3h
0x1800032e1  mov     eax, [r15+94h]
0x1800032e8  mov     ecx, eax
0x1800032ea  mov     [rdi+94h], eax
0x1800032f0  call    WdipAlloc
0x1800032f5  mov     [rdi+80h], rax
0x1800032fc  test    rax, rax
0x1800032ff  jnz     short loc_180003316
0x180003301  mov     ebp, 8007000Eh
0x180003306  mov     eax, 0Eh
0x18000330b  mov     r8d, 822h
0x180003311  jmp     loc_1800033C6
0x180003316  mov     r8d, [rdi+94h]; Size
0x18000331d  xor     edx, edx; Val
0x18000331f  mov     rcx, rax; void *
0x180003322  call    memset_0
0x180003327  mov     edx, [rdi+94h]; unsigned __int64
0x18000332d  mov     r8, [r15+80h]; unsigned __int16 *
0x180003334  mov     rcx, [rdi+80h]; unsigned __int16 *
0x18000333b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180003340  mov     ebp, eax
0x180003342  test    eax, eax
0x180003344  jns     short loc_18000334E
0x180003346  mov     r8d, 829h
0x18000334c  jmp     short loc_1800033C3
0x18000334e  test    byte ptr [rdi+98h], 1
0x180003355  jz      loc_180003425
0x18000335b  mov     eax, [r15+90h]
0x180003362  mov     ecx, eax
0x180003364  mov     [rdi+90h], eax
0x18000336a  call    WdipAlloc
0x18000336f  mov     [rdi+88h], rax
0x180003376  test    rax, rax
0x180003379  jnz     short loc_18000338D
0x18000337b  mov     ebp, 8007000Eh
0x180003380  mov     eax, 0Eh
0x180003385  mov     r8d, 830h
0x18000338b  jmp     short loc_1800033C6
0x18000338d  mov     r8d, [rdi+90h]; Size
0x180003394  xor     edx, edx; Val
0x180003396  mov     rcx, rax; void *
0x180003399  call    memset_0
0x18000339e  mov     edx, [rdi+90h]; unsigned __int64
0x1800033a4  mov     r8, [r15+88h]; unsigned __int16 *
0x1800033ab  mov     rcx, [rdi+88h]; unsigned __int16 *
0x1800033b2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800033b7  mov     ebp, eax
0x1800033b9  test    eax, eax
0x1800033bb  jns     short loc_180003425
0x1800033bd  mov     r8d, 837h; int
0x1800033c3  movzx   eax, ax
0x1800033c6  lea     rdx, aDpspcreatespec_0; "DpspCreateSpecificSession"
0x1800033cd  mov     dword ptr [rsp+78h+Args], eax; Args
0x1800033d1  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800033d8  lea     r9, aErrorD; "Error = %d"
0x1800033df  call    WdipTraceError
0x1800033e4  lea     rcx, [rdi+40h]
0x1800033e8  call    WdipDeleteCriticalSection
0x1800033ed  mov     rcx, [rdi+88h]
0x1800033f4  call    WdipFree
0x1800033f9  mov     rcx, [rdi+80h]
0x180003400  mov     qword ptr [rdi+88h], 0
0x18000340b  call    WdipFree
0x180003410  mov     rcx, rdi
0x180003413  mov     qword ptr [rdi+80h], 0
0x18000341e  call    WdipFree
0x180003423  jmp     short loc_180003453
0x180003425  lea     rax, [rdi+70h]
0x180003429  mov     rsi, rdi
0x18000342c  mov     [rax+8], rax
0x180003430  mov     [rax], rax
0x180003433  mov     rax, cs:g_pSessionHead
0x18000343a  mov     [rdi+0B8h], rax
0x180003441  lock cmpxchg cs:g_pSessionHead, rdi
0x18000344a  cmp     rax, [rdi+0B8h]
0x180003451  jnz     short loc_18000343A
0x180003453  mov     ebx, ebp
0x180003455  test    ebp, ebp
0x180003457  jns     short loc_18000346B
0x180003459  movzx   eax, bp
0x18000345c  mov     r8d, 7AFh
0x180003462  mov     dword ptr [rsp+78h+Args], eax
0x180003466  jmp     loc_18000305C
0x18000346b  mov     [r12], rsi
0x18000346f  lea     rcx, g_csDMList; lpCriticalSection
0x180003476  call    cs:__imp_LeaveCriticalSection
0x18000347c  mov     eax, ebx
0x18000347e  add     rsp, 38h
0x180003482  pop     r15
0x180003484  pop     r14
0x180003486  pop     r13
0x180003488  pop     r12
0x18000348a  pop     rdi
0x18000348b  pop     rsi
0x18000348c  pop     rbp
0x18000348d  pop     rbx
0x18000348e  retn
```
