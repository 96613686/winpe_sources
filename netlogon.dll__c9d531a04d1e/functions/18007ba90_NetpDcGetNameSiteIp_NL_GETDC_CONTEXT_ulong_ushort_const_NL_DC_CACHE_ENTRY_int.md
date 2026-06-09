# NetpDcGetNameSiteIp(_NL_GETDC_CONTEXT *,ulong,ushort const *,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x18007ba90`
- end: `0x18007c23d`
- name: `?NetpDcGetNameSiteIp@@YAKPEAU_NL_GETDC_CONTEXT@@KPEBGPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `1965`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, int, const unsigned __int16 *, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007af44`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000ba1c`
- `0x18000e270`
- `0x18001852c`
- `0x1800782b8`
- `0x180078738`
- `0x18007ba90`
- `0x18007c244`
- `0x18007ca2c`
- `0x18007cdf8`
- `0x18007e390`
- `0x180081ab4`
- `0x180081b1c`
- `0x180081f18`
- `0x180082e88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bbb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bd46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bbb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bd46`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007bcdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007bcdf`
- `netutils!NetApiBufferFree` at `0x18007bbef`
- `netutils!NetApiBufferFree` at `0x18007bdd5`
- `netutils!NetApiBufferFree` at `0x18007bbef`
- `netutils!NetApiBufferFree` at `0x18007bdd5`

## string_xrefs

- `0x18007c16d`: `NetpDcGetNameIp: %ws: IP Not configured from DnsQuery.\n`

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
  _QWORD *v9; // rsi
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
            (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
    v17 = dword_1800EF21C[8 * *((int *)a1 + 2)] != 40;
  DcOpen = NetpDcGetDcOpen(Src, a2 | 2u, a3, *((struct _GUID **)a1 + 13), v16, *((_DWORD *)a1 + 3) & 0x94C1, v34, &v37);
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
    v18 = dword_1800F11A0;
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
                (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
        &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
              &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *((_QWORD *)a1 + 9),
              DcOpen,
              DcOpen);
          _InterlockedAdd64(&qword_1800F1E50, 1u);
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
    WPP_SF_S(*((_QWORD *)v31 + 2), v32, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids, *((_QWORD *)a1 + 9));
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
      &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
0x18007ba90  push    rbp
0x18007ba92  push    rbx
0x18007ba93  push    rsi
0x18007ba94  push    rdi
0x18007ba95  push    r12
0x18007ba97  push    r13
0x18007ba99  push    r14
0x18007ba9b  push    r15
0x18007ba9d  lea     rbp, [rsp-1C8h]
0x18007baa5  sub     rsp, 2C8h
0x18007baac  mov     rax, cs:__security_cookie
0x18007bab3  xor     rax, rsp
0x18007bab6  mov     [rbp+200h+var_50], rax
0x18007babd  xor     r14d, r14d
0x18007bac0  mov     [rbp+200h+var_258], r9
0x18007bac4  mov     r15d, edx
0x18007bac7  mov     [rsp+300h+var_2B0], r14
0x18007bacc  mov     rdi, rcx
0x18007bacf  mov     [rsp+300h+hMem], r14
0x18007bad4  mov     rcx, [rbp+200h+arg_20]
0x18007badb  lea     rdx, [rsp+300h+var_2A0]
0x18007bae0  mov     [rsp+300h+var_2D8], rdx; unsigned int *
0x18007bae5  mov     r12, r8
0x18007bae8  mov     [rsp+300h+var_2E0], rcx; int *
0x18007baed  lea     r8d, [r14+1]; int
0x18007baf1  mov     [rbp+200h+var_260], rcx
0x18007baf5  xor     edx, edx; struct _NL_DC_ADDRESS *
0x18007baf7  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x18007bafa  mov     [rsp+300h+var_298], r14d
0x18007baff  mov     esi, r14d
0x18007bb02  mov     [rsp+300h+var_2A0], r14d
0x18007bb07  mov     [rbp+200h+var_278], r14
0x18007bb0b  mov     r13d, r14d
0x18007bb0e  mov     [rbp+200h+lpMultiByteStr], r14
0x18007bb12  mov     [rbp+200h+nSize], 100h
0x18007bb19  mov     [rsp+300h+var_2C0], r14
0x18007bb1e  call    ?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z; NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)
0x18007bb23  mov     ebx, eax
0x18007bb25  cmp     eax, 79h ; 'y'
0x18007bb28  jz      short loc_18007BB85
0x18007bb2a  test    eax, eax
0x18007bb2c  jz      short loc_18007BBA9
0x18007bb2e  mov     r8, [rdi+48h]
0x18007bb32  lea     rdx, aNetpdcgetnamei_7; "NetpDcGetNameIp: %ws: Cannot NetpDcPing"...
0x18007bb39  mov     r9d, eax
0x18007bb3c  mov     ecx, 100h; unsigned int
0x18007bb41  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007bb46  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb4d  mov     r15b, 4
0x18007bb50  test    [rcx+1Ch], r15b
0x18007bb54  jz      short loc_18007BBA9
0x18007bb56  lea     esi, [r14+2]
0x18007bb5a  cmp     [rcx+19h], sil
0x18007bb5e  jb      short loc_18007BB7B
0x18007bb60  mov     r9, [rdi+48h]
0x18007bb64  lea     edx, [rsi+1Fh]
0x18007bb67  mov     rcx, [rcx+10h]
0x18007bb6b  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007bb72  mov     dword ptr [rsp+300h+var_2E0], ebx
0x18007bb76  call    WPP_SF_SL
0x18007bb7b  mov     rsi, [rsp+300h+var_2B0]
0x18007bb80  mov     r15, r13
0x18007bb83  jmp     short loc_18007BBAC
0x18007bb85  mov     rcx, [rdi+38h]; lpWideCharStr
0x18007bb89  xor     r8d, r8d; int
0x18007bb8c  xor     edx, edx; lpMultiByteStr
0x18007bb8e  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18007bb93  mov     [rsp+300h+Src], rax
0x18007bb98  mov     r14, rax
0x18007bb9b  test    rax, rax
0x18007bb9e  jnz     loc_18007BC27
0x18007bba4  mov     ebx, 8
0x18007bba9  mov     r15, rsi
0x18007bbac  mov     rcx, [rsp+300h+hMem]; hMem
0x18007bbb1  test    rcx, rcx
0x18007bbb4  jz      short loc_18007BBBC
0x18007bbb6  call    cs:__imp_LocalFree
0x18007bbbc  test    rsi, rsi
0x18007bbbf  jz      short loc_18007BBC9
0x18007bbc1  mov     rcx, rsi; hMem
0x18007bbc4  call    ?NetpDcGetDcClose@@YAXPEAX@Z; NetpDcGetDcClose(void *)
0x18007bbc9  test    r14, r14
0x18007bbcc  jz      short loc_18007BBD6
0x18007bbce  mov     rcx, r14
0x18007bbd1  call    NetpMemoryFree
0x18007bbd6  mov     rax, [rbp+200h+var_278]
0x18007bbda  test    rax, rax
0x18007bbdd  jz      short loc_18007BBE7
0x18007bbdf  mov     rcx, rax
0x18007bbe2  call    NetpMemoryFree
0x18007bbe7  test    r13, r13
0x18007bbea  jz      short loc_18007BBF5
0x18007bbec  mov     rcx, r13; Buffer
0x18007bbef  call    cs:__imp_NetApiBufferFree
0x18007bbf5  test    r15, r15
0x18007bbf8  jz      short loc_18007BC02
0x18007bbfa  mov     rcx, r15
0x18007bbfd  call    NetpMemoryFree
0x18007bc02  mov     eax, ebx
0x18007bc04  mov     rcx, [rbp+200h+var_50]
0x18007bc0b  xor     rcx, rsp; StackCookie
0x18007bc0e  call    __security_check_cookie
0x18007bc13  add     rsp, 2C8h
0x18007bc1a  pop     r15
0x18007bc1c  pop     r14
0x18007bc1e  pop     r13
0x18007bc20  pop     r12
0x18007bc22  pop     rdi
0x18007bc23  pop     rsi
0x18007bc24  pop     rbx
0x18007bc25  pop     rbp
0x18007bc26  retn
0x18007bc27  mov     rcx, [rdi+40h]; lpWideCharStr
0x18007bc2b  test    rcx, rcx
0x18007bc2e  jz      short loc_18007BC4B
0x18007bc30  xor     r8d, r8d; int
0x18007bc33  xor     edx, edx; lpMultiByteStr
0x18007bc35  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18007bc3a  mov     [rbp+200h+var_278], rax
0x18007bc3e  mov     rcx, rax
0x18007bc41  test    rax, rax
0x18007bc44  jnz     short loc_18007BC4E
0x18007bc46  jmp     loc_18007BBA4
0x18007bc4b  mov     rcx, rsi
0x18007bc4e  xor     r14b, r14b
0x18007bc51  test    r12, r12
0x18007bc54  jz      short loc_18007BC76
0x18007bc56  movsxd  rax, dword ptr [rdi+8]
0x18007bc5a  lea     rdx, dword_1800EF21C
0x18007bc61  shl     rax, 5
0x18007bc65  movzx   r14d, r14b
0x18007bc69  cmp     dword ptr [rax+rdx], 28h ; '('
0x18007bc6d  mov     edx, 1
0x18007bc72  cmovnz  r14d, edx
0x18007bc76  mov     eax, [rdi+0Ch]
0x18007bc79  lea     rdx, [rsp+300h+var_2B0]
0x18007bc7e  mov     r9, [rdi+68h]; struct _GUID *
0x18007bc82  and     eax, 94C1h
0x18007bc87  mov     [rsp+300h+var_2C8], rdx; void **
0x18007bc8c  mov     esi, 2
0x18007bc91  mov     dword ptr [rsp+300h+var_2D8], eax; unsigned int
0x18007bc95  or      r15d, esi
0x18007bc98  mov     [rsp+300h+var_2E0], rcx; char *
0x18007bc9d  mov     r8, r12; unsigned __int16 *
0x18007bca0  mov     rcx, [rsp+300h+Src]; Src
0x18007bca5  mov     edx, r15d; unsigned int
0x18007bca8  call    ?NetpDcGetDcOpen@@YAKPEBDKPEBGPEAU_GUID@@0KEPEAPEAX@Z; NetpDcGetDcOpen(char const *,ulong,ushort const *,_GUID *,char const *,ulong,uchar,void * *)
0x18007bcad  mov     ebx, eax
0x18007bcaf  test    eax, eax
0x18007bcb1  jnz     loc_18007C233
0x18007bcb7  cmp     [rdi+0E8h], r13b
0x18007bcbe  lea     r8, [rbp+200h+nSize]; nSize
0x18007bcc2  mov     ebx, 4B0h
0x18007bcc7  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x18007bccb  cmovz   ebx, cs:dword_1800F11A0
0x18007bcd2  lea     ecx, [rsi+1]; NameType
0x18007bcd5  mov     [rbp+200h+var_27C], ebx
0x18007bcd8  mov     [rdi+0C4h], r13d
0x18007bcdf  call    cs:__imp_GetComputerNameExW
0x18007bce5  mov     [rsp+300h+var_29C], eax
0x18007bce9  mov     ebx, eax
0x18007bceb  test    eax, eax
0x18007bced  jz      short loc_18007BD1C
0x18007bcef  xor     r8d, r8d; int
0x18007bcf2  lea     rcx, [rbp+200h+Buffer]; lpWideCharStr
0x18007bcf6  xor     edx, edx; lpMultiByteStr
0x18007bcf8  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18007bcfd  mov     [rsp+300h+var_2C0], rax
0x18007bd02  mov     r15, rax
0x18007bd05  test    rax, rax
0x18007bd08  jnz     short loc_18007BD1C
0x18007bd0a  mov     r14, [rsp+300h+Src]
0x18007bd0f  lea     ebx, [rsi+6]
0x18007bd12  mov     rsi, [rsp+300h+var_2B0]
0x18007bd17  jmp     loc_18007BBAC
0x18007bd1c  mov     eax, [rsp+300h+var_2A0]
0x18007bd20  lea     r12, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007bd27  mov     [rsp+300h+var_2A0], eax
0x18007bd2b  mov     r15b, 4
0x18007bd2e  mov     [rsp+300h+var_2B8], r13b
0x18007bd33  mov     rcx, [rsp+300h+hMem]; hMem
0x18007bd38  mov     [rsp+300h+var_290], 0
0x18007bd41  test    rcx, rcx
0x18007bd44  jz      short loc_18007BD55
0x18007bd46  call    cs:__imp_LocalFree
0x18007bd4c  mov     [rsp+300h+hMem], 0
0x18007bd55  mov     eax, ebx
0x18007bd57  mov     [rsp+300h+var_298], 0
0x18007bd5f  neg     eax
0x18007bd61  sbb     rcx, rcx
0x18007bd64  and     rcx, [rsp+300h+var_2C0]
0x18007bd69  test    r14b, r14b
0x18007bd6c  jz      short loc_18007BD77
0x18007bd6e  lea     rax, [rdi+0C0h]
0x18007bd75  jmp     short loc_18007BD79
0x18007bd77  xor     eax, eax
0x18007bd79  mov     edx, [rdi+10h]
0x18007bd7c  lea     r9, [rsp+300h+hMem]; struct _SOCKET_ADDRESS **
0x18007bd81  mov     [rsp+300h+var_2D0], rcx; char *
0x18007bd86  lea     r8, [rsp+300h+var_298]; unsigned int *
0x18007bd8b  mov     rcx, [rsp+300h+var_2B0]; void *
0x18007bd90  and     edx, 10000h
0x18007bd96  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x18007bd9b  lea     rax, [rbp+200h+lpMultiByteStr]
0x18007bd9f  shl     edx, 7; unsigned int
0x18007bda2  mov     [rsp+300h+var_2E0], rax; char **
0x18007bda7  call    ?NetpDcGetDcNext@@YAKPEAXKPEAKPEAPEAU_SOCKET_ADDRESS@@PEAPEAD1PEAD@Z; NetpDcGetDcNext(void *,ulong,ulong *,_SOCKET_ADDRESS * *,char * *,ulong *,char *)
0x18007bdac  mov     ebx, eax
0x18007bdae  test    eax, eax
0x18007bdb0  jnz     loc_18007BF35
0x18007bdb6  mov     word ptr [rdi+0E4h], 101h
0x18007bdbf  lea     eax, [rbx+1]
0x18007bdc2  test    r14b, r14b
0x18007bdc5  jz      short loc_18007BDCD
0x18007bdc7  or      [rdi+0ECh], eax
0x18007bdcd  test    r13, r13
0x18007bdd0  jz      short loc_18007BDDE
0x18007bdd2  mov     rcx, r13; Buffer
0x18007bdd5  call    cs:__imp_NetApiBufferFree
0x18007bddb  xor     r13d, r13d
0x18007bdde  mov     rcx, [rbp+200h+lpMultiByteStr]; lpMultiByteStr
0x18007bde2  test    rcx, rcx
0x18007bde5  jz      short loc_18007BE1B
0x18007bde7  lea     rax, [rbp+200h+var_268]
0x18007bdeb  mov     [rbp+200h+var_268], 0
0x18007bdf3  xor     r9d, r9d; unsigned __int16 *
0x18007bdf6  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x18007bdfb  xor     r8d, r8d; unsigned int
0x18007bdfe  or      edx, 0FFFFFFFFh; cbMultiByte
0x18007be01  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18007be06  test    eax, eax
0x18007be08  jnz     loc_18007C020
0x18007be0e  mov     r13, [rbp+200h+var_268]
0x18007be12  test    r13, r13
0x18007be15  jz      loc_18007C023
0x18007be1b  mov     r9d, [rsp+300h+var_298]; unsigned int
0x18007be20  lea     rax, [rsp+300h+var_290]
0x18007be25  mov     r8, [rsp+300h+hMem]; struct _SOCKET_ADDRESS *
0x18007be2a  mov     rdx, r13; unsigned __int16 *
0x18007be2d  mov     [rsp+300h+var_2D8], rax; struct _NL_DC_ADDRESS **
0x18007be32  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x18007be35  mov     byte ptr [rsp+300h+var_2E0], r14b; char
0x18007be3a  call    ?NetpDcProcessAddressList@@YAKPEAU_NL_GETDC_CONTEXT@@PEAGPEAU_SOCKET_ADDRESS@@KEPEAPEAU_NL_DC_ADDRESS@@@Z; NetpDcProcessAddressList(_NL_GETDC_CONTEXT *,ushort *,_SOCKET_ADDRESS *,ulong,uchar,_NL_DC_ADDRESS * *)
0x18007be3f  mov     ebx, eax
0x18007be41  test    eax, eax
0x18007be43  jnz     loc_18007BF21
0x18007be49  mov     rdx, [rsp+300h+var_290]; struct _NL_DC_ADDRESS *
0x18007be4e  lea     ecx, [rax+1]
0x18007be51  mov     ebx, [rsp+300h+var_29C]
0x18007be55  mov     [rsp+300h+var_2B8], cl
0x18007be59  test    rdx, rdx
0x18007be5c  jz      loc_18007BD33
0x18007be62  mov     r9, [rbp+200h+var_258]; struct _NL_DC_CACHE_ENTRY **
0x18007be66  mov     r8d, ecx; int
0x18007be69  mov     dword ptr [rsp+300h+var_290], eax
0x18007be6d  mov     rcx, rdi; struct _NL_GETDC_CONTEXT *
0x18007be70  lea     rax, [rsp+300h+var_290]
0x18007be75  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x18007be7a  mov     rax, [rbp+200h+var_260]
0x18007be7e  mov     [rsp+300h+var_2E0], rax; int *
0x18007be83  call    ?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z; NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)
0x18007be88  mov     ebx, eax
0x18007be8a  mov     eax, dword ptr [rsp+300h+var_290]
0x18007be8e  test    eax, eax
0x18007be90  jz      short loc_18007BE9D
0x18007be92  mov     edx, 1
0x18007be97  add     [rdi+0B8h], edx
0x18007be9d  cmp     ebx, 79h ; 'y'
0x18007bea0  jnz     loc_18007C02D
0x18007bea6  add     [rsp+300h+var_2A0], eax
0x18007beaa  mov     r9d, [rdi+0B8h]
0x18007beb1  mov     ebx, [rbp+200h+var_27C]
0x18007beb4  cmp     r9d, ebx
0x18007beb7  jb      loc_18007C017
0x18007bebd  mov     r8, [rdi+48h]
0x18007bec1  lea     rdx, aNetpdcgetnames_0; "NetpDcGetNameSiteIp: %ws: Reached the D"...
0x18007bec8  mov     ecx, 100h; unsigned int
0x18007becd  mov     dword ptr [rsp+300h+var_2E0], ebx
0x18007bed1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007bed6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bedd  test    [rcx+1Ch], r15b
0x18007bee1  jz      short loc_18007BF04
0x18007bee3  cmp     [rcx+19h], sil
0x18007bee7  jb      short loc_18007BF04
0x18007bee9  mov     eax, [rdi+0B8h]
0x18007beef  mov     r9, [rdi+48h]
0x18007bef3  mov     rcx, [rcx+10h]
0x18007bef7  mov     dword ptr [rsp+300h+var_2D8], ebx
0x18007befb  mov     dword ptr [rsp+300h+var_2E0], eax
0x18007beff  call    WPP_SF_SLL
0x18007bf04  cmp     [rsp+300h+var_2A0], 0
0x18007bf09  jz      loc_18007C204
0x18007bf0f  cmp     dword ptr [rdi+0BCh], 0
0x18007bf16  jz      loc_18007C204
0x18007bf1c  mov     ebx, 79h ; 'y'
0x18007bf21  mov     rsi, [rsp+300h+var_2B0]
0x18007bf26  mov     r14, [rsp+300h+Src]
0x18007bf2b  mov     r15, [rsp+300h+var_2C0]
0x18007bf30  jmp     loc_18007BBAC
0x18007bf35  cmp     ebx, 232Bh
  ... truncated ...
```
