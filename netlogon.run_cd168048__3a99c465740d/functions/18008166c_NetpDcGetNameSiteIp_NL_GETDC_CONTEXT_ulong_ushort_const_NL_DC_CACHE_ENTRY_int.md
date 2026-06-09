# NetpDcGetNameSiteIp(_NL_GETDC_CONTEXT *,ulong,ushort const *,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x18008166c`
- end: `0x180081e38`
- name: `?NetpDcGetNameSiteIp@@YAKPEAU_NL_GETDC_CONTEXT@@KPEBGPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `1996`
- prototype: `unsigned int(struct _NL_GETDC_CONTEXT *, unsigned int, const unsigned __int16 *, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080b08`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000c130`
- `0x18000e910`
- `0x18001906c`
- `0x18007dd80`
- `0x18007e224`
- `0x18008166c`
- `0x180081e40`
- `0x180082698`
- `0x180082a84`
- `0x1800840dc`
- `0x180087b10`
- `0x180087b98`
- `0x180087f94`
- `0x180088fe8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081935`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800818c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800818c8`
- `netutils!NetApiBufferFree` at `0x1800817d1`
- `netutils!NetApiBufferFree` at `0x1800819ca`
- `netutils!NetApiBufferFree` at `0x1800817d1`
- `netutils!NetApiBufferFree` at `0x1800819ca`

## string_xrefs

- `0x180081d68`: `NetpDcGetNameIp: %ws: IP Not configured from DnsQuery.\n`

## pseudocode

```c
__int64 __fastcall NetpDcGetNameSiteIp(
        struct _NL_GETDC_CONTEXT *a1,
        int a2,
        const unsigned __int16 *a3,
        struct _NL_DC_CACHE_ENTRY **a4,
        int *a5)
{
  char *v5; // r14
  HLOCAL v9; // rsi
  unsigned __int16 *v10; // r13
  unsigned int v11; // eax
  unsigned int DcOpen; // ebx
  unsigned __int64 v13; // r15
  const WCHAR *v15; // rcx
  const char *v16; // rcx
  char v17; // r14
  int v18; // ebx
  BOOL v19; // ebx
  unsigned int *v20; // rax
  unsigned int DcNext; // eax
  struct _NL_DC_ADDRESS *v22; // rdx
  int v23; // eax
  char v24; // bl
  int v25; // edx
  int v26; // r8d
  unsigned int PingResponse; // eax
  ScannerInfoNameMappings *v28; // rcx
  int v29; // edx
  __int64 v30; // r8
  ScannerInfoNameMappings *v31; // rcx
  __int64 v32; // rdx
  char **v33; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v34; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v35; // [rsp+40h] [rbp-C0h]
  char v36; // [rsp+48h] [rbp-B8h]
  HLOCAL v37; // [rsp+50h] [rbp-B0h] BYREF
  char *Src; // [rsp+58h] [rbp-A8h]
  unsigned int v39; // [rsp+60h] [rbp-A0h] BYREF
  BOOL ComputerName; // [rsp+64h] [rbp-9Ch]
  unsigned int v41; // [rsp+68h] [rbp-98h] BYREF
  struct _NL_DC_ADDRESS *v42; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  DWORD nSize; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v45; // [rsp+84h] [rbp-7Ch]
  char *Utf8StrFromWStr; // [rsp+88h] [rbp-78h]
  LPCCH lpMultiByteStr; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v48; // [rsp+98h] [rbp-68h] BYREF
  int *v49; // [rsp+A0h] [rbp-60h]
  struct _NL_DC_CACHE_ENTRY **v50; // [rsp+A8h] [rbp-58h]
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = 0;
  v50 = a4;
  v37 = 0;
  hMem = 0;
  v49 = a5;
  v41 = 0;
  v9 = 0;
  v39 = 0;
  Utf8StrFromWStr = 0;
  v10 = 0;
  lpMultiByteStr = 0;
  nSize = 256;
  v35 = 0;
  v11 = NetpDcPingListIp(a1, 0, 1, a4, a5, &v39);
  DcOpen = v11;
  if ( v11 != 121 )
  {
    if ( v11 )
    {
      NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: Cannot NetpDcPingListIp. %ld\n", *((_QWORD *)a1 + 9), v11);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
            *((_QWORD *)a1 + 9),
            DcOpen);
        goto LABEL_6;
      }
    }
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  Src = NetpCreateUtf8StrFromWStr(*((LPCWCH *)a1 + 7), 0, 0);
  v5 = Src;
  if ( !Src )
  {
LABEL_8:
    DcOpen = 8;
    goto LABEL_9;
  }
  v15 = (const WCHAR *)*((_QWORD *)a1 + 8);
  if ( v15 )
  {
    Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(v15, 0, 0);
    v16 = Utf8StrFromWStr;
    if ( !Utf8StrFromWStr )
      goto LABEL_8;
  }
  else
  {
    v16 = 0;
  }
  v17 = 0;
  if ( a3 )
    v17 = dword_1800F621C[8 * *((int *)a1 + 2)] != 40;
  DcOpen = NetpDcGetDcOpen(Src, a2 | 2, a3, *((struct _GUID **)a1 + 13), v16, *((_DWORD *)a1 + 3) & 0x94C1, v34, &v37);
  if ( DcOpen )
  {
    v5 = Src;
LABEL_6:
    v9 = v37;
    v13 = 0;
    goto LABEL_10;
  }
  v18 = 1200;
  if ( !*((_BYTE *)a1 + 232) )
    v18 = dword_1800F81A0;
  v45 = v18;
  *((_DWORD *)a1 + 49) = 0;
  ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize);
  v19 = ComputerName;
  if ( ComputerName )
  {
    v35 = (unsigned __int64)NetpCreateUtf8StrFromWStr(Buffer, 0, 0);
    v13 = v35;
    if ( !v35 )
    {
      v5 = Src;
      DcOpen = 8;
      v9 = v37;
      goto LABEL_10;
    }
  }
  v36 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v42 = 0;
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      v41 = 0;
      v20 = v17 ? (unsigned int *)((char *)a1 + 192) : 0LL;
      DcNext = NetpDcGetDcNext(
                 v37,
                 (*((_DWORD *)a1 + 4) & 0x10000) << 7,
                 &v41,
                 (struct _SOCKET_ADDRESS **)&hMem,
                 (char **)&lpMultiByteStr,
                 v20,
                 (char *)(v35 & -(__int64)v19));
      DcOpen = DcNext;
      if ( DcNext )
        break;
      *((_WORD *)a1 + 114) = 257;
      if ( v17 )
        *((_DWORD *)a1 + 59) |= 1u;
      if ( v10 )
      {
        NetApiBufferFree(v10);
        v10 = 0;
      }
      if ( lpMultiByteStr )
      {
        v48 = 0;
        if ( NetpAllocWStrFromUtf8StrAsRequired(lpMultiByteStr, 0xFFFFFFFF, 0, 0, &v48) )
        {
          v10 = 0;
LABEL_77:
          DcOpen = 8;
          goto LABEL_61;
        }
        v10 = v48;
        if ( !v48 )
          goto LABEL_77;
      }
      DcOpen = NetpDcProcessAddressList(a1, v10, (struct _SOCKET_ADDRESS *)hMem, v41, v17, &v42);
      if ( DcOpen )
        goto LABEL_61;
      v22 = v42;
      v19 = ComputerName;
      v36 = 1;
      if ( v42 )
      {
        LODWORD(v42) = 0;
        DcOpen = NetpDcPingListIp(a1, v22, 1, v50, v49, (unsigned int *)&v42);
        v23 = (int)v42;
        if ( (_DWORD)v42 )
          ++*((_DWORD *)a1 + 46);
        if ( DcOpen != 121 )
        {
          if ( DcOpen )
          {
            NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: Cannot NetpDcPingListIp. %ld\n", *((_QWORD *)a1 + 9), DcOpen);
            v28 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v29 = 39;
LABEL_86:
              WPP_SF_SL(
                *((_QWORD *)v28 + 2),
                v29,
                (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                *((_QWORD *)a1 + 9),
                DcOpen);
              goto LABEL_61;
            }
          }
          goto LABEL_61;
        }
        v39 += v23;
        v24 = v45;
        if ( *((_DWORD *)a1 + 46) >= v45 )
        {
          NlPrintRoutine(0x100u, L"NetpDcGetNameSiteIp: %ws: Reached the DC limit %lu %lu\n", *((_QWORD *)a1 + 9));
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_SLL(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, *((_QWORD *)a1 + 9), *((_DWORD *)a1 + 46), v24);
          goto LABEL_58;
        }
LABEL_75:
        v19 = ComputerName;
      }
    }
    if ( DcNext != 9003 )
      break;
    *((_WORD *)a1 + 114) = 257;
    if ( v17 )
      ++*((_DWORD *)a1 + 49);
    NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: cannot find A record.\n", *((_QWORD *)a1 + 9));
    v19 = ComputerName;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
        *((_QWORD *)a1 + 9));
  }
  if ( DcNext != 1101 )
  {
    if ( DcNext == 259 )
    {
      *((_BYTE *)a1 + 229) = 1;
    }
    else
    {
      if ( DcNext != 1460 && DcNext != 9002 )
      {
        v30 = *((_QWORD *)a1 + 9);
        if ( DcNext - 9851 <= 1 )
        {
          NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: IP Not configured from DnsQuery.\n", v30);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
              *((_QWORD *)a1 + 9));
          DcOpen = 9851;
        }
        else
        {
          LODWORD(v33) = DcNext;
          NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: Unknown error from DnsQuery. %ld 0x%lx\n", v30, DcNext, v33);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sll(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
              *((_QWORD *)a1 + 9),
              DcOpen,
              DcOpen);
          _InterlockedAdd64(&qword_1800F8E10, 1u);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 360LL) + 208LL), 1u);
        }
        goto LABEL_61;
      }
      *((_BYTE *)a1 + 228) = 1;
    }
    if ( v36 )
    {
LABEL_58:
      if ( v39 && *((_DWORD *)a1 + 47) )
      {
        DcOpen = 121;
        goto LABEL_61;
      }
      NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: Couldn't ping any DCs.\n", *((_QWORD *)a1 + 9));
      v31 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_106;
      v32 = 42;
    }
    else
    {
      NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: No data returned from DnsQuery.\n", *((_QWORD *)a1 + 9));
      v31 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_106;
      v32 = 41;
    }
    WPP_SF_S(*((_QWORD *)v31 + 2), v32, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids, *((_QWORD *)a1 + 9));
LABEL_106:
    DcOpen = 1355;
    goto LABEL_61;
  }
  if ( !v39 )
    goto LABEL_74;
  NlPrintRoutine(0x100u, L"NetpDcGetNameIp: %ws: site specific SRV records done.\n", *((_QWORD *)a1 + 9));
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
      *((_QWORD *)a1 + 9));
  PingResponse = NetpDcGetPingResponse(a1, 0xC8u, v50, v49);
  DcOpen = PingResponse;
  if ( PingResponse == 121 )
  {
LABEL_74:
    v17 = 0;
    goto LABEL_75;
  }
  if ( PingResponse )
  {
    NlPrintRoutine(
      0x100u,
      L"NetpDcGetNameIp: %ws: Cannot NetpDcGetPingResponse. %ld\n",
      *((_QWORD *)a1 + 9),
      PingResponse);
    v28 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 36;
      goto LABEL_86;
    }
  }
LABEL_61:
  v9 = v37;
  v5 = Src;
  v13 = v35;
LABEL_10:
  if ( hMem )
    LocalFree(hMem);
  if ( v9 )
    NetpDcGetDcClose(v9);
  if ( v5 )
    NetpMemoryFree(v5);
  if ( Utf8StrFromWStr )
    NetpMemoryFree(Utf8StrFromWStr);
  if ( v10 )
    NetApiBufferFree(v10);
  if ( v13 )
    NetpMemoryFree(v13);
  return DcOpen;
}

```

## disassembly

```asm
0x18008166c  push    rbp
0x18008166e  push    rbx
0x18008166f  push    rsi
0x180081670  push    rdi
0x180081671  push    r12
0x180081673  push    r13
0x180081675  push    r14
0x180081677  push    r15
0x180081679  lea     rbp, [rsp-1C8h]
0x180081681  sub     rsp, 2C8h
0x180081688  mov     rax, cs:__security_cookie
0x18008168f  xor     rax, rsp
0x180081692  mov     [rbp+200h+var_50], rax
0x180081699  xor     r14d, r14d
0x18008169c  mov     [rbp+200h+var_258], r9
0x1800816a0  mov     r15d, edx
0x1800816a3  mov     [rsp+300h+var_2B0], r14
0x1800816a8  mov     rdi, rcx
0x1800816ab  mov     [rsp+300h+hMem], r14
0x1800816b0  mov     rcx, [rbp+200h+arg_20]
0x1800816b7  lea     rdx, [rsp+300h+var_2A0]
0x1800816bc  mov     [rsp+300h+var_2D8], rdx; unsigned int *
0x1800816c1  mov     r12, r8
0x1800816c4  mov     [rsp+300h+var_2E0], rcx; int *
0x1800816c9  lea     r8d, [r14+1]; int
0x1800816cd  mov     [rbp+200h+var_260], rcx
0x1800816d1  xor     edx, edx; struct _NL_DC_ADDRESS *
0x1800816d3  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x1800816d6  mov     [rsp+300h+var_298], r14d
0x1800816db  mov     esi, r14d
0x1800816de  mov     [rsp+300h+var_2A0], r14d
0x1800816e3  mov     [rbp+200h+var_278], r14
0x1800816e7  mov     r13d, r14d
0x1800816ea  mov     [rbp+200h+lpMultiByteStr], r14
0x1800816ee  mov     [rbp+200h+nSize], 100h
0x1800816f5  mov     [rsp+300h+var_2C0], r14
0x1800816fa  call    ?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z; NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)
0x1800816ff  mov     ebx, eax
0x180081701  cmp     eax, 79h ; 'y'
0x180081704  jz      short loc_180081761
0x180081706  test    eax, eax
0x180081708  jz      short loc_180081785
0x18008170a  mov     r8, [rdi+48h]
0x18008170e  lea     rdx, aNetpdcgetnamei_7; "NetpDcGetNameIp: %ws: Cannot NetpDcPing"...
0x180081715  mov     r9d, eax
0x180081718  mov     ecx, 100h; unsigned int
0x18008171d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180081722  mov     rcx, cs:WPP_GLOBAL_Control
0x180081729  mov     r15b, 4
0x18008172c  test    [rcx+1Ch], r15b
0x180081730  jz      short loc_180081785
0x180081732  lea     esi, [r14+2]
0x180081736  cmp     [rcx+19h], sil
0x18008173a  jb      short loc_180081757
0x18008173c  mov     r9, [rdi+48h]
0x180081740  lea     edx, [rsi+1Fh]
0x180081743  mov     rcx, [rcx+10h]
0x180081747  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18008174e  mov     dword ptr [rsp+300h+var_2E0], ebx
0x180081752  call    WPP_SF_SL
0x180081757  mov     rsi, [rsp+300h+var_2B0]
0x18008175c  mov     r15, r13
0x18008175f  jmp     short loc_180081788
0x180081761  mov     rcx, [rdi+38h]; lpWideCharStr
0x180081765  xor     r8d, r8d; int
0x180081768  xor     edx, edx; lpMultiByteStr
0x18008176a  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18008176f  mov     [rsp+300h+Src], rax
0x180081774  mov     r14, rax
0x180081777  test    rax, rax
0x18008177a  jnz     loc_180081810
0x180081780  mov     ebx, 8
0x180081785  mov     r15, rsi
0x180081788  mov     rcx, [rsp+300h+hMem]; hMem
0x18008178d  test    rcx, rcx
0x180081790  jz      short loc_18008179E
0x180081792  call    cs:__imp_LocalFree
0x180081799  nop     dword ptr [rax+rax+00h]
0x18008179e  test    rsi, rsi
0x1800817a1  jz      short loc_1800817AB
0x1800817a3  mov     rcx, rsi; hMem
0x1800817a6  call    ?NetpDcGetDcClose@@YAXPEAX@Z; NetpDcGetDcClose(void *)
0x1800817ab  test    r14, r14
0x1800817ae  jz      short loc_1800817B8
0x1800817b0  mov     rcx, r14
0x1800817b3  call    NetpMemoryFree
0x1800817b8  mov     rax, [rbp+200h+var_278]
0x1800817bc  test    rax, rax
0x1800817bf  jz      short loc_1800817C9
0x1800817c1  mov     rcx, rax
0x1800817c4  call    NetpMemoryFree
0x1800817c9  test    r13, r13
0x1800817cc  jz      short loc_1800817DD
0x1800817ce  mov     rcx, r13; Buffer
0x1800817d1  call    cs:__imp_NetApiBufferFree
0x1800817d8  nop     dword ptr [rax+rax+00h]
0x1800817dd  test    r15, r15
0x1800817e0  jz      short loc_1800817EA
0x1800817e2  mov     rcx, r15
0x1800817e5  call    NetpMemoryFree
0x1800817ea  mov     eax, ebx
0x1800817ec  mov     rcx, [rbp+200h+var_50]
0x1800817f3  xor     rcx, rsp; StackCookie
0x1800817f6  call    __security_check_cookie
0x1800817fb  add     rsp, 2C8h
0x180081802  pop     r15
0x180081804  pop     r14
0x180081806  pop     r13
0x180081808  pop     r12
0x18008180a  pop     rdi
0x18008180b  pop     rsi
0x18008180c  pop     rbx
0x18008180d  pop     rbp
0x18008180e  retn
0x180081810  mov     rcx, [rdi+40h]; lpWideCharStr
0x180081814  test    rcx, rcx
0x180081817  jz      short loc_180081834
0x180081819  xor     r8d, r8d; int
0x18008181c  xor     edx, edx; lpMultiByteStr
0x18008181e  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180081823  mov     [rbp+200h+var_278], rax
0x180081827  mov     rcx, rax
0x18008182a  test    rax, rax
0x18008182d  jnz     short loc_180081837
0x18008182f  jmp     loc_180081780
0x180081834  mov     rcx, rsi
0x180081837  xor     r14b, r14b
0x18008183a  test    r12, r12
0x18008183d  jz      short loc_18008185F
0x18008183f  movsxd  rax, dword ptr [rdi+8]
0x180081843  lea     rdx, dword_1800F621C
0x18008184a  shl     rax, 5
0x18008184e  movzx   r14d, r14b
0x180081852  cmp     dword ptr [rax+rdx], 28h ; '('
0x180081856  mov     edx, 1
0x18008185b  cmovnz  r14d, edx
0x18008185f  mov     eax, [rdi+0Ch]
0x180081862  lea     rdx, [rsp+300h+var_2B0]
0x180081867  mov     r9, [rdi+68h]; struct _GUID *
0x18008186b  and     eax, 94C1h
0x180081870  mov     [rsp+300h+var_2C8], rdx; void **
0x180081875  mov     esi, 2
0x18008187a  mov     dword ptr [rsp+300h+var_2D8], eax; unsigned int
0x18008187e  or      r15d, esi
0x180081881  mov     [rsp+300h+var_2E0], rcx; char *
0x180081886  mov     r8, r12; unsigned __int16 *
0x180081889  mov     rcx, [rsp+300h+Src]; Src
0x18008188e  mov     edx, r15d; unsigned int
0x180081891  call    ?NetpDcGetDcOpen@@YAKPEBDKPEBGPEAU_GUID@@0KEPEAPEAX@Z; NetpDcGetDcOpen(char const *,ulong,ushort const *,_GUID *,char const *,ulong,uchar,void * *)
0x180081896  mov     ebx, eax
0x180081898  test    eax, eax
0x18008189a  jnz     loc_180081E2E
0x1800818a0  cmp     [rdi+0E8h], r13b
0x1800818a7  lea     r8, [rbp+200h+nSize]; nSize
0x1800818ab  mov     ebx, 4B0h
0x1800818b0  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x1800818b4  cmovz   ebx, cs:dword_1800F81A0
0x1800818bb  lea     ecx, [rsi+1]; NameType
0x1800818be  mov     [rbp+200h+var_27C], ebx
0x1800818c1  mov     [rdi+0C4h], r13d
0x1800818c8  call    cs:__imp_GetComputerNameExW
0x1800818cf  nop     dword ptr [rax+rax+00h]
0x1800818d4  mov     [rsp+300h+var_29C], eax
0x1800818d8  mov     ebx, eax
0x1800818da  test    eax, eax
0x1800818dc  jz      short loc_18008190B
0x1800818de  xor     r8d, r8d; int
0x1800818e1  lea     rcx, [rbp+200h+Buffer]; lpWideCharStr
0x1800818e5  xor     edx, edx; lpMultiByteStr
0x1800818e7  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800818ec  mov     [rsp+300h+var_2C0], rax
0x1800818f1  mov     r15, rax
0x1800818f4  test    rax, rax
0x1800818f7  jnz     short loc_18008190B
0x1800818f9  mov     r14, [rsp+300h+Src]
0x1800818fe  lea     ebx, [rsi+6]
0x180081901  mov     rsi, [rsp+300h+var_2B0]
0x180081906  jmp     loc_180081788
0x18008190b  mov     eax, [rsp+300h+var_2A0]
0x18008190f  lea     r12, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180081916  mov     [rsp+300h+var_2A0], eax
0x18008191a  mov     r15b, 4
0x18008191d  mov     [rsp+300h+var_2B8], r13b
0x180081922  mov     rcx, [rsp+300h+hMem]; hMem
0x180081927  mov     [rsp+300h+var_290], 0
0x180081930  test    rcx, rcx
0x180081933  jz      short loc_18008194A
0x180081935  call    cs:__imp_LocalFree
0x18008193c  nop     dword ptr [rax+rax+00h]
0x180081941  mov     [rsp+300h+hMem], 0
0x18008194a  mov     eax, ebx
0x18008194c  mov     [rsp+300h+var_298], 0
0x180081954  neg     eax
0x180081956  sbb     rcx, rcx
0x180081959  and     rcx, [rsp+300h+var_2C0]
0x18008195e  test    r14b, r14b
0x180081961  jz      short loc_18008196C
0x180081963  lea     rax, [rdi+0C0h]
0x18008196a  jmp     short loc_18008196E
0x18008196c  xor     eax, eax
0x18008196e  mov     edx, [rdi+10h]
0x180081971  lea     r9, [rsp+300h+hMem]; struct _SOCKET_ADDRESS **
0x180081976  mov     [rsp+300h+var_2D0], rcx; char *
0x18008197b  lea     r8, [rsp+300h+var_298]; unsigned int *
0x180081980  mov     rcx, [rsp+300h+var_2B0]; void *
0x180081985  and     edx, 10000h
0x18008198b  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x180081990  lea     rax, [rbp+200h+lpMultiByteStr]
0x180081994  shl     edx, 7; unsigned int
0x180081997  mov     [rsp+300h+var_2E0], rax; char **
0x18008199c  call    ?NetpDcGetDcNext@@YAKPEAXKPEAKPEAPEAU_SOCKET_ADDRESS@@PEAPEAD1PEAD@Z; NetpDcGetDcNext(void *,ulong,ulong *,_SOCKET_ADDRESS * *,char * *,ulong *,char *)
0x1800819a1  mov     ebx, eax
0x1800819a3  test    eax, eax
0x1800819a5  jnz     loc_180081B30
0x1800819ab  mov     word ptr [rdi+0E4h], 101h
0x1800819b4  lea     eax, [rbx+1]
0x1800819b7  test    r14b, r14b
0x1800819ba  jz      short loc_1800819C2
0x1800819bc  or      [rdi+0ECh], eax
0x1800819c2  test    r13, r13
0x1800819c5  jz      short loc_1800819D9
0x1800819c7  mov     rcx, r13; Buffer
0x1800819ca  call    cs:__imp_NetApiBufferFree
0x1800819d1  nop     dword ptr [rax+rax+00h]
0x1800819d6  xor     r13d, r13d
0x1800819d9  mov     rcx, [rbp+200h+lpMultiByteStr]; lpMultiByteStr
0x1800819dd  test    rcx, rcx
0x1800819e0  jz      short loc_180081A16
0x1800819e2  lea     rax, [rbp+200h+var_268]
0x1800819e6  mov     [rbp+200h+var_268], 0
0x1800819ee  xor     r9d, r9d; unsigned __int16 *
0x1800819f1  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x1800819f6  xor     r8d, r8d; unsigned int
0x1800819f9  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800819fc  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x180081a01  test    eax, eax
0x180081a03  jnz     loc_180081C1B
0x180081a09  mov     r13, [rbp+200h+var_268]
0x180081a0d  test    r13, r13
0x180081a10  jz      loc_180081C1E
0x180081a16  mov     r9d, [rsp+300h+var_298]; unsigned int
0x180081a1b  lea     rax, [rsp+300h+var_290]
0x180081a20  mov     r8, [rsp+300h+hMem]; struct _SOCKET_ADDRESS *
0x180081a25  mov     rdx, r13; unsigned __int16 *
0x180081a28  mov     [rsp+300h+var_2D8], rax; struct _NL_DC_ADDRESS **
0x180081a2d  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x180081a30  mov     byte ptr [rsp+300h+var_2E0], r14b; char
0x180081a35  call    ?NetpDcProcessAddressList@@YAKPEAU_NL_GETDC_CONTEXT@@PEAGPEAU_SOCKET_ADDRESS@@KEPEAPEAU_NL_DC_ADDRESS@@@Z; NetpDcProcessAddressList(_NL_GETDC_CONTEXT *,ushort *,_SOCKET_ADDRESS *,ulong,uchar,_NL_DC_ADDRESS * *)
0x180081a3a  mov     ebx, eax
0x180081a3c  test    eax, eax
0x180081a3e  jnz     loc_180081B1C
0x180081a44  mov     rdx, [rsp+300h+var_290]; struct _NL_DC_ADDRESS *
0x180081a49  lea     ecx, [rax+1]
0x180081a4c  mov     ebx, [rsp+300h+var_29C]
0x180081a50  mov     [rsp+300h+var_2B8], cl
0x180081a54  test    rdx, rdx
0x180081a57  jz      loc_180081922
0x180081a5d  mov     r9, [rbp+200h+var_258]; struct _NL_DC_CACHE_ENTRY **
0x180081a61  mov     r8d, ecx; int
0x180081a64  mov     dword ptr [rsp+300h+var_290], eax
0x180081a68  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x180081a6b  lea     rax, [rsp+300h+var_290]
0x180081a70  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x180081a75  mov     rax, [rbp+200h+var_260]
0x180081a79  mov     [rsp+300h+var_2E0], rax; int *
0x180081a7e  call    ?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z; NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)
0x180081a83  mov     ebx, eax
0x180081a85  mov     eax, dword ptr [rsp+300h+var_290]
0x180081a89  test    eax, eax
0x180081a8b  jz      short loc_180081A98
0x180081a8d  mov     edx, 1
0x180081a92  add     [rdi+0B8h], edx
0x180081a98  cmp     ebx, 79h ; 'y'
0x180081a9b  jnz     loc_180081C28
0x180081aa1  add     [rsp+300h+var_2A0], eax
0x180081aa5  mov     r9d, [rdi+0B8h]
0x180081aac  mov     ebx, [rbp+200h+var_27C]
0x180081aaf  cmp     r9d, ebx
0x180081ab2  jb      loc_180081C12
0x180081ab8  mov     r8, [rdi+48h]
0x180081abc  lea     rdx, aNetpdcgetnames_0; "NetpDcGetNameSiteIp: %ws: Reached the D"...
0x180081ac3  mov     ecx, 100h; unsigned int
0x180081ac8  mov     dword ptr [rsp+300h+var_2E0], ebx
0x180081acc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180081ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ad8  test    [rcx+1Ch], r15b
0x180081adc  jz      short loc_180081AFF
0x180081ade  cmp     [rcx+19h], sil
0x180081ae2  jb      short loc_180081AFF
0x180081ae4  mov     eax, [rdi+0B8h]
0x180081aea  mov     r9, [rdi+48h]
0x180081aee  mov     rcx, [rcx+10h]
0x180081af2  mov     dword ptr [rsp+300h+var_2D8], ebx
0x180081af6  mov     dword ptr [rsp+300h+var_2E0], eax
0x180081afa  call    WPP_SF_SLL
0x180081aff  cmp     [rsp+300h+var_2A0], 0
0x180081b04  jz      loc_180081DFF
0x180081b0a  cmp     dword ptr [rdi+0BCh], 0
0x180081b11  jz      loc_180081DFF
0x180081b17  mov     ebx, 79h ; 'y'
  ... truncated ...
```
