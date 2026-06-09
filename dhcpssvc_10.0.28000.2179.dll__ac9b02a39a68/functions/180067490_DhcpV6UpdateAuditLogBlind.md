# DhcpV6UpdateAuditLogBlind

- ea: `0x180067490`
- end: `0x180067b6d`
- name: `DhcpV6UpdateAuditLogBlind`
- size: `1757`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180067bd0`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800052d4`
- `0x180005410`
- `0x1800626dc`
- `0x180062e10`
- `0x180067490`
- `0x18008f614`
- `0x18008f6d8`
- `0x18008f988`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!_wstrtime` at `0x1800675b7`
- `msvcrt!_wstrtime` at `0x1800675b7`
- `msvcrt!_wstrdate` at `0x1800675a7`
- `msvcrt!_wstrdate` at `0x1800675a7`
- `KERNEL32!HeapAlloc` at `0x1800676ba`
- `KERNEL32!HeapAlloc` at `0x1800676ba`
- `KERNEL32!WriteFile` at `0x180067a31`
- `KERNEL32!WriteFile` at `0x180067a31`
- `KERNEL32!GetLastError` at `0x180067a45`
- `KERNEL32!GetLastError` at `0x180067a45`
- `KERNEL32!HeapFree` at `0x180067a90`
- `KERNEL32!HeapFree` at `0x180067aa8`
- `KERNEL32!HeapFree` at `0x180067ac5`
- `KERNEL32!HeapFree` at `0x180067b06`
- `KERNEL32!HeapFree` at `0x180067b1e`
- `KERNEL32!HeapFree` at `0x180067b3b`
- `KERNEL32!HeapFree` at `0x180067a90`
- `KERNEL32!HeapFree` at `0x180067aa8`
- `KERNEL32!HeapFree` at `0x180067ac5`
- `KERNEL32!HeapFree` at `0x180067b06`
- `KERNEL32!HeapFree` at `0x180067b1e`
- `KERNEL32!HeapFree` at `0x180067b3b`
- `USER32!OemToCharBuffA` at `0x180067a0f`
- `USER32!OemToCharBuffA` at `0x180067a0f`

## pseudocode

```c
__int64 __fastcall DhcpV6UpdateAuditLogBlind(
        int a1,
        const size_t *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        const size_t *a6,
        int a7,
        __int64 a8,
        const char *a9,
        __int64 a10)
{
  void *v12; // r15
  const wchar_t *v13; // rax
  __int64 v14; // rbx
  const size_t *v15; // rax
  const size_t *v16; // r14
  int *v17; // rsi
  int v18; // eax
  __int64 v19; // r10
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdi
  DWORD LastError; // ebx
  SIZE_T v26; // rdi
  wchar_t *v27; // r12
  int v28; // esi
  wchar_t *v29; // rsi
  __int64 v30; // rax
  HRESULT v31; // eax
  CHAR *v32; // rsi
  SIZE_T v33; // rax
  CHAR *i; // rcx
  unsigned __int64 v35; // rcx
  DWORD v36; // ebx
  size_t v37; // rdi
  DWORD pszFormat; // [rsp+28h] [rbp-D8h]
  DWORD pszFormata; // [rsp+28h] [rbp-D8h]
  DWORD pszFormatb; // [rsp+28h] [rbp-D8h]
  DWORD pszFormatc; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+30h] [rbp-D0h]
  size_t pcbRemaining; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+78h] [rbp-88h] BYREF
  int v46; // [rsp+80h] [rbp-80h]
  DWORD NumberOfBytesWritten; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int8 *v48; // [rsp+88h] [rbp-78h]
  const size_t *v49; // [rsp+90h] [rbp-70h]
  const size_t *v50; // [rsp+98h] [rbp-68h]
  STRSAFE_LPCWSTR v51; // [rsp+A0h] [rbp-60h]
  PCSZ SourceString; // [rsp+A8h] [rbp-58h]
  wchar_t v53[12]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Buffer[12]; // [rsp+C8h] [rbp-38h] BYREF
  int v55; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v56[76]; // [rsp+E4h] [rbp-1Ch] BYREF
  int v57; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v58[76]; // [rsp+134h] [rbp+34h] BYREF
  _WORD v59[280]; // [rsp+180h] [rbp+80h] BYREF

  v12 = 0;
  v46 = a1;
  SourceString = a9;
  v48 = a4;
  v13 = L"%.2d,%s,%s,%s,%s,%s,";
  NumberOfBytesWritten = 0;
  if ( a7 )
    v13 = L"%.2d,%s,%s,%s,%s,%s,%ld";
  pcbRemaining = 0;
  v51 = v13;
  v55 = 48;
  memset_0(v56, 0, sizeof(v56));
  v57 = 48;
  memset_0(v58, 0, sizeof(v58));
  if ( !DhcpGlobalAuditLogFlag )
    return 0;
  v14 = -1;
  if ( DhcpV6AuditLogHandle == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids);
    return 0;
  }
  if ( (unsigned int)GetUserAndDomainName(v59) )
    v59[0] = 0;
  _wstrdate(Buffer);
  _wstrtime(v53);
  v15 = &Annotation;
  if ( a2 )
    v15 = a2;
  v16 = &Annotation;
  v49 = v15;
  if ( a6 )
    v16 = a6;
  v50 = v16;
  if ( a3 )
  {
    v18 = MemAddr6ConvertIpv6AddrToString(a3, &v55);
    v17 = &v55;
    if ( v18 )
      v17 = (int *)&Annotation;
  }
  else
  {
    v17 = (int *)&Annotation;
  }
  if ( a10 )
    MemAddr6ConvertIpv6AddrToString(a10, &v57);
  v19 = -1;
  do
    ++v19;
  while ( v59[v19] );
  v20 = -1;
  do
    ++v20;
  while ( Buffer[v20] );
  v21 = -1;
  do
    ++v21;
  while ( v53[v21] );
  v22 = -1;
  do
    ++v22;
  while ( *((_WORD *)v17 + v22) );
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)v49 + v23) );
  do
    ++v14;
  while ( *((_WORD *)v16 + v14) );
  v24 = v14 + v19 + v20 + v21 + 360 + v22 + 2LL * a5;
  LastError = 8;
  v26 = 2 * (v23 + v24);
  v27 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, v26);
  if ( v27 )
  {
    ppszDestEnd = v27;
    v28 = 0;
    if ( StringCbPrintfExW(v27, v26, &ppszDestEnd, &pcbRemaining, 0x1000u, v51) < 0 )
    {
LABEL_33:
      LastError = 13;
      goto LABEL_70;
    }
    if ( v48 && a5 )
    {
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%ld,", a5) >= 0 )
      {
        while ( 1 )
        {
          LODWORD(v43) = *v48++;
          if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v43) < 0 )
            break;
          if ( ++v28 >= a5 )
            goto LABEL_39;
        }
      }
      goto LABEL_33;
    }
    if ( StringCbCopyExW(ppszDestEnd, pcbRemaining, L",,", &ppszDestEnd, &pcbRemaining, pszFormat) >= 0 )
    {
LABEL_39:
      if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%ls") >= 0 )
      {
        v29 = ppszDestEnd;
        if ( StringCbCopyExW(ppszDestEnd, pcbRemaining, L"\r\n", 0, &pcbRemaining, pszFormata) >= 0 )
        {
          if ( a8 && SourceString )
          {
            v30 = DhcpOemToUnicodeN(SourceString);
            v12 = (void *)v30;
            if ( !v30 )
              goto LABEL_70;
            v31 = StringCbPrintfExW(v29, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%s", v30);
          }
          else
          {
            v31 = StringCbCopyExW(v29, pcbRemaining, L",,", &ppszDestEnd, &pcbRemaining, pszFormatb);
          }
          if ( v31 >= 0
            && StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%s") >= 0
            && StringCbCopyExW(ppszDestEnd, pcbRemaining, L",\r\n", 0, &pcbRemaining, pszFormatc) >= 0 )
          {
            v32 = (CHAR *)DhcpUnicodeToOem(v27);
            if ( v32 )
            {
              if ( v26 > 0x7FFFFFFF )
                goto LABEL_63;
              v33 = v26;
              for ( i = v32; v33; --v33 )
              {
                if ( !*i )
                  break;
                ++i;
              }
              v35 = v33 ? v26 - v33 : 0LL;
              if ( v33 )
              {
                v36 = -1;
                if ( v35 <= 0xFFFFFFFF )
                  v36 = v35;
              }
              else
              {
LABEL_63:
                v36 = -1;
                v37 = (v26 - pcbRemaining) >> 1;
                if ( v37 <= 0xFFFFFFFF )
                  v36 = v37;
              }
              OemToCharBuffA(v32, v32, v36);
              if ( !WriteFile(DhcpV6AuditLogHandle, v32, v36, &NumberOfBytesWritten, 0) )
              {
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    15,
                    &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids,
                    LastError);
                }
                HeapFree(gDhcpHeap, 0, v32);
                goto LABEL_70;
              }
              HeapFree(gDhcpHeap, 0, v32);
            }
            HeapFree(gDhcpHeap, 0, v27);
            if ( v12 )
              HeapFree(gDhcpHeap, 0, v12);
            return 0;
          }
        }
      }
    }
    LastError = 13;
LABEL_70:
    HeapFree(gDhcpHeap, 0, v27);
    if ( v12 )
      HeapFree(gDhcpHeap, 0, v12);
  }
  if ( !DhcpV6AuditLogErrorLogged )
  {
    DhcpV6AuditLogErrorLogged = 1;
    DhcpServerEventLog(10011, 1, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180067490  push    rbp
0x180067492  push    rbx
0x180067493  push    rsi
0x180067494  push    rdi
0x180067495  push    r12
0x180067497  push    r13
0x180067499  push    r14
0x18006749b  push    r15
0x18006749d  lea     rbp, [rsp-2C8h]
0x1800674a5  sub     rsp, 3C8h
0x1800674ac  mov     rax, cs:__security_cookie
0x1800674b3  xor     rax, rsp
0x1800674b6  mov     [rbp+300h+var_50], rax
0x1800674bd  mov     rax, [rbp+300h+arg_40]
0x1800674c4  mov     r14, rdx
0x1800674c7  mov     r12, [rbp+300h+arg_28]
0x1800674ce  xor     edx, edx; Val
0x1800674d0  cmp     [rbp+300h+arg_30], edx
0x1800674d6  mov     rsi, r8
0x1800674d9  mov     rdi, [rbp+300h+arg_48]
0x1800674e0  mov     r15d, edx
0x1800674e3  mov     [rbp+300h+var_380], ecx
0x1800674e6  lea     rcx, a2dSSSSSLd; "%.2d,%s,%s,%s,%s,%s,%ld"
0x1800674ed  mov     [rbp+300h+SourceString], rax
0x1800674f1  lea     ebx, [rdx+4Ch]
0x1800674f4  lea     r13d, [rdx+30h]
0x1800674f8  mov     [rbp+300h+var_378], r9
0x1800674fc  lea     rax, a2dSSSSS; "%.2d,%s,%s,%s,%s,%s,"
0x180067503  mov     [rbp+300h+NumberOfBytesWritten], edx
0x180067506  cmovnz  rax, rcx
0x18006750a  mov     [rsp+400h+pcbRemaining], rdx
0x18006750f  mov     r8d, ebx; Size
0x180067512  mov     [rbp+300h+var_360], rax
0x180067516  lea     rcx, [rbp+300h+var_31C]; void *
0x18006751a  mov     [rbp+300h+var_320], r13d
0x18006751e  call    memset_0
0x180067523  mov     r8d, ebx; Size
0x180067526  mov     [rbp+300h+var_2D0], r13d
0x18006752a  xor     edx, edx; Val
0x18006752c  lea     rcx, [rbp+300h+var_2CC]; void *
0x180067530  call    memset_0
0x180067535  xor     r13d, r13d
0x180067538  cmp     cs:DhcpGlobalAuditLogFlag, r13d
0x18006753f  jz      loc_180067B47
0x180067545  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180067549  cmp     cs:DhcpV6AuditLogHandle, rbx
0x180067550  jnz     short loc_18006758B
0x180067552  mov     rcx, cs:WPP_GLOBAL_Control
0x180067559  lea     rax, WPP_GLOBAL_Control
0x180067560  cmp     rcx, rax
0x180067563  jz      loc_180067B47
0x180067569  test    byte ptr [rcx+1Ch], 10h
0x18006756d  jz      loc_180067B47
0x180067573  mov     rcx, [rcx+10h]
0x180067577  lea     edx, [rbx+0Fh]
0x18006757a  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180067581  call    WPP_SF_
0x180067586  jmp     loc_180067B47
0x18006758b  lea     rcx, [rbp+300h+var_280]
0x180067592  call    GetUserAndDomainName
0x180067597  test    eax, eax
0x180067599  jz      short loc_1800675A3
0x18006759b  mov     [rbp+300h+var_280], r13w
0x1800675a3  lea     rcx, [rbp+300h+Buffer]; Buffer
0x1800675a7  call    cs:__imp__wstrdate
0x1800675ae  nop     dword ptr [rax+rax+00h]
0x1800675b3  lea     rcx, [rbp+300h+var_350]; Buffer
0x1800675b7  call    cs:__imp__wstrtime
0x1800675be  nop     dword ptr [rax+rax+00h]
0x1800675c3  test    r14, r14
0x1800675c6  lea     r13, Annotation
0x1800675cd  mov     rax, r13
0x1800675d0  cmovnz  rax, r14
0x1800675d4  test    r12, r12
0x1800675d7  mov     r14, r13
0x1800675da  mov     [rbp+300h+var_370], rax
0x1800675de  cmovnz  r14, r12
0x1800675e2  xor     r12d, r12d
0x1800675e5  mov     [rbp+300h+var_368], r14
0x1800675e9  test    rsi, rsi
0x1800675ec  jnz     short loc_1800675F3
0x1800675ee  mov     rsi, r13
0x1800675f1  jmp     short loc_180067609
0x1800675f3  lea     rdx, [rbp+300h+var_320]
0x1800675f7  mov     rcx, rsi
0x1800675fa  call    MemAddr6ConvertIpv6AddrToString
0x1800675ff  test    eax, eax
0x180067601  lea     rsi, [rbp+300h+var_320]
0x180067605  cmovnz  rsi, r13
0x180067609  test    rdi, rdi
0x18006760c  jz      short loc_180067627
0x18006760e  lea     rdx, [rbp+300h+var_2D0]
0x180067612  mov     rcx, rdi
0x180067615  call    MemAddr6ConvertIpv6AddrToString
0x18006761a  test    eax, eax
0x18006761c  lea     rcx, [rbp+300h+var_2D0]
0x180067620  cmovnz  rcx, r13
0x180067624  mov     r13, rcx
0x180067627  lea     rax, [rbp+300h+var_280]
0x18006762e  mov     r10, rbx
0x180067631  inc     r10
0x180067634  cmp     [rax+r10*2], r12w
0x180067639  jnz     short loc_180067631
0x18006763b  lea     rax, [rbp+300h+Buffer]
0x18006763f  mov     r9, rbx
0x180067642  inc     r9
0x180067645  cmp     [rax+r9*2], r12w
0x18006764a  jnz     short loc_180067642
0x18006764c  lea     rax, [rbp+300h+var_350]
0x180067650  mov     r8, rbx
0x180067653  inc     r8
0x180067656  cmp     [rax+r8*2], r12w
0x18006765b  jnz     short loc_180067653
0x18006765d  mov     rdx, rbx
0x180067660  inc     rdx
0x180067663  cmp     [rsi+rdx*2], r12w
0x180067668  jnz     short loc_180067660
0x18006766a  mov     rax, [rbp+300h+var_370]
0x18006766e  mov     rcx, rbx
0x180067671  inc     rcx
0x180067674  cmp     [rax+rcx*2], r12w
0x180067679  jnz     short loc_180067671
0x18006767b  inc     rbx
0x18006767e  cmp     [r14+rbx*2], r12w
0x180067683  jnz     short loc_18006767B
0x180067685  mov     r14d, [rbp+300h+arg_20]
0x18006768c  add     r8, 168h
0x180067693  lea     rdi, [rdx+r14*2]
0x180067697  add     rdi, r8
0x18006769a  add     rdi, r9
0x18006769d  add     rdi, r10
0x1800676a0  add     rdi, rbx
0x1800676a3  mov     ebx, 8
0x1800676a8  add     rdi, rcx
0x1800676ab  mov     edx, ebx; dwFlags
0x1800676ad  mov     rcx, cs:gDhcpHeap; hHeap
0x1800676b4  add     rdi, rdi
0x1800676b7  mov     r8, rdi; dwBytes
0x1800676ba  call    cs:__imp_HeapAlloc
0x1800676c1  nop     dword ptr [rax+rax+00h]
0x1800676c6  mov     r12, rax
0x1800676c9  lea     eax, [rbx-7]
0x1800676cc  test    r12, r12
0x1800676cf  jnz     short loc_1800676D9
0x1800676d1  xor     r14d, r14d
0x1800676d4  jmp     loc_180067AD6
0x1800676d9  mov     eax, [rbp+300h+arg_30]
0x1800676df  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x1800676e4  mov     [rsp+400h+var_3A0], eax
0x1800676e8  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x1800676ed  mov     rax, [rbp+300h+var_368]
0x1800676f1  mov     rdx, rdi; cbDest
0x1800676f4  mov     [rsp+400h+var_3A8], rax
0x1800676f9  mov     rcx, r12; pszDest
0x1800676fc  mov     rax, [rbp+300h+var_370]
0x180067700  mov     [rsp+400h+var_3B0], rsi
0x180067705  mov     [rsp+400h+var_3B8], rax
0x18006770a  lea     rax, [rbp+300h+var_350]
0x18006770e  mov     [rsp+400h+var_3C0], rax
0x180067713  lea     rax, [rbp+300h+Buffer]
0x180067717  mov     [rsp+400h+var_3C8], rax
0x18006771c  mov     eax, [rbp+300h+var_380]
0x18006771f  mov     dword ptr [rsp+400h+var_3D0], eax
0x180067723  mov     rax, [rbp+300h+var_360]
0x180067727  mov     [rsp+400h+pszFormat], rax; dwFlags
0x18006772c  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067734  mov     [rsp+400h+ppszDestEnd], r12
0x180067739  call    StringCbPrintfExW
0x18006773e  xor     esi, esi
0x180067740  test    eax, eax
0x180067742  jns     short loc_180067751
0x180067744  mov     ebx, 0Dh
0x180067749  xor     r14d, r14d
0x18006774c  jmp     loc_180067A9C
0x180067751  cmp     [rbp+300h+var_378], rsi
0x180067755  jz      loc_18006797C
0x18006775b  test    r14d, r14d
0x18006775e  jz      loc_18006797C
0x180067764  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067769  lea     rax, aLd_0; ",%ld,"
0x180067770  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067775  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x18006777a  mov     dword ptr [rsp+400h+var_3D0], r14d
0x18006777f  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067784  mov     [rsp+400h+pszFormat], rax; pszFormat
0x180067789  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067791  call    StringCbPrintfExW
0x180067796  test    eax, eax
0x180067798  js      short loc_180067744
0x18006779a  test    r14d, r14d
0x18006779d  jz      short loc_1800677ED
0x18006779f  mov     rcx, [rbp+300h+var_378]
0x1800677a3  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x1800677a8  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x1800677ad  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x1800677b2  movzx   eax, byte ptr [rcx]
0x1800677b5  inc     rcx
0x1800677b8  mov     dword ptr [rsp+400h+var_3D0], eax
0x1800677bc  lea     rax, a2x; "%.2X"
0x1800677c3  mov     [rbp+300h+var_378], rcx
0x1800677c7  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x1800677cc  mov     [rsp+400h+pszFormat], rax; pszFormat
0x1800677d1  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x1800677d9  call    StringCbPrintfExW
0x1800677de  test    eax, eax
0x1800677e0  js      loc_180067744
0x1800677e6  inc     esi
0x1800677e8  cmp     esi, r14d
0x1800677eb  jb      short loc_18006779F
0x1800677ed  xor     r14d, r14d
0x1800677f0  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x1800677f5  lea     rax, [rbp+300h+var_280]
0x1800677fc  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067801  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067806  mov     [rsp+400h+var_3D0], rax
0x18006780b  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067810  lea     rax, aLs; ",%ls"
0x180067817  mov     [rsp+400h+pszFormat], rax; dwFlags
0x18006781c  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067824  call    StringCbPrintfExW
0x180067829  test    eax, eax
0x18006782b  js      loc_1800679AC
0x180067831  mov     rsi, [rsp+400h+ppszDestEnd]
0x180067836  lea     rax, [rsp+400h+pcbRemaining]
0x18006783b  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067840  lea     r8, asc_1800DE530; "\r\n"
0x180067847  mov     rcx, rsi; pszDest
0x18006784a  mov     qword ptr [rsp+400h+dwFlags], rax; pcbRemaining
0x18006784f  xor     r9d, r9d; ppszDestEnd
0x180067852  call    StringCbCopyExW
0x180067857  test    eax, eax
0x180067859  js      loc_1800679AC
0x18006785f  mov     r8, [rbp+300h+arg_38]
0x180067866  test    r8, r8
0x180067869  jz      loc_1800679B6
0x18006786f  mov     rax, [rbp+300h+SourceString]
0x180067873  test    rax, rax
0x180067876  jz      loc_1800679B6
0x18006787c  inc     r8w
0x180067880  xor     edx, edx
0x180067882  mov     rcx, rax; SourceString
0x180067885  call    DhcpOemToUnicodeN
0x18006788a  mov     r15, rax
0x18006788d  test    rax, rax
0x180067890  jz      loc_180067A9C
0x180067896  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x18006789b  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x1800678a0  mov     [rsp+400h+var_3D0], rax
0x1800678a5  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x1800678aa  lea     rax, aS_0; "%s"
0x1800678b1  mov     rcx, rsi; pszDest
0x1800678b4  mov     [rsp+400h+pszFormat], rax; pszFormat
0x1800678b9  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x1800678c1  call    StringCbPrintfExW
0x1800678c6  test    eax, eax
0x1800678c8  js      loc_1800679AC
0x1800678ce  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x1800678d3  lea     rax, aS; ",%s"
0x1800678da  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x1800678df  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x1800678e4  mov     [rsp+400h+var_3D0], r13
0x1800678e9  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x1800678ee  mov     [rsp+400h+pszFormat], rax; dwFlags
0x1800678f3  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x1800678fb  call    StringCbPrintfExW
0x180067900  test    eax, eax
0x180067902  js      loc_1800679AC
0x180067908  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x18006790d  lea     rax, [rsp+400h+pcbRemaining]
0x180067912  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067917  lea     r8, asc_1800E68C8; ",\r\n"
0x18006791e  xor     r9d, r9d; ppszDestEnd
0x180067921  mov     qword ptr [rsp+400h+dwFlags], rax; pcbRemaining
0x180067926  call    StringCbCopyExW
0x18006792b  test    eax, eax
0x18006792d  js      short loc_1800679AC
0x18006792f  xor     edx, edx
0x180067931  mov     rcx, r12; SourceString
0x180067934  call    DhcpUnicodeToOem
0x180067939  mov     rsi, rax
0x18006793c  test    rax, rax
0x18006793f  jz      loc_180067B12
0x180067945  cmp     rdi, 7FFFFFFFh
0x18006794c  ja      loc_1800679F3
0x180067952  mov     rax, rdi
0x180067955  mov     rcx, rsi
0x180067958  test    rdi, rdi
0x18006795b  jz      short loc_18006796F
0x18006795d  mov     edx, 1
0x180067962  cmp     [rcx], r14b
0x180067965  jz      short loc_18006796F
0x180067967  add     rcx, rdx
0x18006796a  sub     rax, rdx
0x18006796d  jnz     short loc_180067962
0x18006796f  test    rax, rax
0x180067972  jz      short loc_1800679DE
0x180067974  mov     rcx, rdi
0x180067977  sub     rcx, rax
0x18006797a  jmp     short loc_1800679E1
0x18006797c  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
  ... truncated ...
```
