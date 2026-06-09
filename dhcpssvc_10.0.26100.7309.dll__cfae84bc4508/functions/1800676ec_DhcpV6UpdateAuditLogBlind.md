# DhcpV6UpdateAuditLogBlind

- ea: `0x1800676ec`
- end: `0x180067dca`
- name: `DhcpV6UpdateAuditLogBlind`
- size: `1758`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180067e24`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800052d4`
- `0x180005408`
- `0x180062964`
- `0x18006308c`
- `0x1800676ec`
- `0x18008f478`
- `0x18008f540`
- `0x18008f7f0`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!_wstrtime` at `0x180067813`
- `msvcrt!_wstrtime` at `0x180067813`
- `msvcrt!_wstrdate` at `0x180067803`
- `msvcrt!_wstrdate` at `0x180067803`
- `KERNEL32!HeapAlloc` at `0x180067919`
- `KERNEL32!HeapAlloc` at `0x180067919`
- `KERNEL32!WriteFile` at `0x180067c8e`
- `KERNEL32!WriteFile` at `0x180067c8e`
- `KERNEL32!GetLastError` at `0x180067ca2`
- `KERNEL32!GetLastError` at `0x180067ca2`
- `KERNEL32!HeapFree` at `0x180067ced`
- `KERNEL32!HeapFree` at `0x180067d05`
- `KERNEL32!HeapFree` at `0x180067d22`
- `KERNEL32!HeapFree` at `0x180067d63`
- `KERNEL32!HeapFree` at `0x180067d7b`
- `KERNEL32!HeapFree` at `0x180067d98`
- `KERNEL32!HeapFree` at `0x180067ced`
- `KERNEL32!HeapFree` at `0x180067d05`
- `KERNEL32!HeapFree` at `0x180067d22`
- `KERNEL32!HeapFree` at `0x180067d63`
- `KERNEL32!HeapFree` at `0x180067d7b`
- `KERNEL32!HeapFree` at `0x180067d98`
- `USER32!OemToCharBuffA` at `0x180067c6c`
- `USER32!OemToCharBuffA` at `0x180067c6c`

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
  PWSTR v12; // r12
  const wchar_t *v13; // rax
  __int64 v14; // rbx
  const size_t *v15; // rax
  const size_t *v16; // rax
  int *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  DWORD LastError; // ebx
  SIZE_T v29; // rdi
  wchar_t *v30; // r15
  int v31; // r14d
  wchar_t *v32; // rsi
  PWSTR v33; // rax
  HRESULT v34; // eax
  CHAR *v35; // rsi
  SIZE_T v36; // rax
  CHAR *i; // rcx
  unsigned __int64 v38; // rcx
  DWORD v39; // ebx
  size_t v40; // rdi
  DWORD pszFormat; // [rsp+28h] [rbp-D8h]
  DWORD pszFormata; // [rsp+28h] [rbp-D8h]
  DWORD pszFormatb; // [rsp+28h] [rbp-D8h]
  DWORD pszFormatc; // [rsp+28h] [rbp-D8h]
  __int64 v46; // [rsp+30h] [rbp-D0h]
  size_t pcbRemaining; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+80h] [rbp-80h]
  DWORD NumberOfBytesWritten; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int8 *v51; // [rsp+88h] [rbp-78h]
  const size_t *v52; // [rsp+90h] [rbp-70h]
  const size_t *v53; // [rsp+98h] [rbp-68h]
  STRSAFE_LPCWSTR v54; // [rsp+A0h] [rbp-60h]
  PCSZ SourceString; // [rsp+A8h] [rbp-58h]
  wchar_t v56[12]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Buffer[12]; // [rsp+C8h] [rbp-38h] BYREF
  int v58; // [rsp+E0h] [rbp-20h] BYREF
  char v59[76]; // [rsp+E4h] [rbp-1Ch] BYREF
  int v60; // [rsp+130h] [rbp+30h] BYREF
  char v61[76]; // [rsp+134h] [rbp+34h] BYREF
  _WORD v62[280]; // [rsp+180h] [rbp+80h] BYREF

  v12 = 0;
  v49 = a1;
  SourceString = a9;
  v51 = a4;
  v13 = L"%.2d,%s,%s,%s,%s,%s,";
  NumberOfBytesWritten = 0;
  if ( a7 )
    v13 = L"%.2d,%s,%s,%s,%s,%s,%ld";
  pcbRemaining = 0;
  v54 = v13;
  v58 = 48;
  memset_0(v59, 0, sizeof(v59));
  v60 = 48;
  memset_0(v61, 0, sizeof(v61));
  if ( !DhcpGlobalAuditLogFlag )
    return 0;
  v14 = -1;
  if ( DhcpV6AuditLogHandle == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids);
    return 0;
  }
  if ( (unsigned int)GetUserAndDomainName(v62) )
    v62[0] = 0;
  _wstrdate(Buffer);
  _wstrtime(v56);
  v15 = &Annotation;
  if ( a2 )
    v15 = a2;
  v53 = v15;
  v16 = &Annotation;
  if ( a6 )
    v16 = a6;
  v52 = v16;
  if ( a3 )
  {
    v17 = &v58;
    if ( (unsigned int)MemAddr6ConvertIpv6AddrToString(a3, &v58) )
      v17 = (int *)&Annotation;
  }
  else
  {
    v17 = (int *)&Annotation;
  }
  if ( a10 )
    MemAddr6ConvertIpv6AddrToString(a10, &v60);
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)v52 + v18) );
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)v53 + v19) );
  v20 = v19 + v18;
  v21 = -1;
  do
    ++v21;
  while ( *((_WORD *)v17 + v21) );
  v22 = v21 + v20;
  v23 = -1;
  do
    ++v23;
  while ( v56[v23] );
  v24 = v23 + v22;
  v25 = -1;
  do
    ++v25;
  while ( Buffer[v25] );
  v26 = v25 + v24;
  do
    ++v14;
  while ( v62[v14] );
  v27 = v14 + v26;
  LastError = 8;
  v29 = 2 * (v27 + 2 * (a5 + 180LL));
  v30 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, v29);
  if ( v30 )
  {
    ppszDestEnd = v30;
    v31 = 0;
    if ( StringCbPrintfExW(v30, v29, &ppszDestEnd, &pcbRemaining, 0x1000u, v54) >= 0 )
    {
      if ( v51 && a5 )
      {
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%ld,", a5) >= 0 )
        {
          while ( 1 )
          {
            LODWORD(v46) = *v51++;
            if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%.2X", v46) < 0 )
              break;
            if ( ++v31 >= a5 )
              goto LABEL_43;
          }
          LastError = 13;
          goto LABEL_72;
        }
      }
      else if ( StringCbCopyExW(ppszDestEnd, pcbRemaining, L",,", &ppszDestEnd, &pcbRemaining, pszFormat) >= 0 )
      {
LABEL_43:
        if ( StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%ls") >= 0 )
        {
          v32 = ppszDestEnd;
          if ( StringCbCopyExW(ppszDestEnd, pcbRemaining, L"\r\n", 0, &pcbRemaining, pszFormata) >= 0 )
          {
            if ( a8 && SourceString )
            {
              v33 = DhcpOemToUnicodeN(SourceString, 0, (unsigned __int16)a8 + 1);
              v12 = v33;
              if ( !v33 )
              {
LABEL_72:
                HeapFree(gDhcpHeap, 0, v30);
                if ( v12 )
                  HeapFree(gDhcpHeap, 0, v12);
                goto LABEL_74;
              }
              v34 = StringCbPrintfExW(v32, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L"%s", v33);
            }
            else
            {
              v34 = StringCbCopyExW(v32, pcbRemaining, L",,", &ppszDestEnd, &pcbRemaining, pszFormatb);
            }
            if ( v34 >= 0
              && StringCbPrintfExW(ppszDestEnd, pcbRemaining, &ppszDestEnd, &pcbRemaining, 0x1000u, L",%s") >= 0
              && StringCbCopyExW(ppszDestEnd, pcbRemaining, L",\r\n", 0, &pcbRemaining, pszFormatc) >= 0 )
            {
              v35 = (CHAR *)DhcpUnicodeToOem(v30);
              if ( v35 )
              {
                if ( v29 > 0x7FFFFFFF )
                  goto LABEL_65;
                v36 = v29;
                for ( i = v35; v36; --v36 )
                {
                  if ( !*i )
                    break;
                  ++i;
                }
                v38 = v36 ? v29 - v36 : 0LL;
                if ( v36 )
                {
                  v39 = -1;
                  if ( v38 <= 0xFFFFFFFF )
                    v39 = v38;
                }
                else
                {
LABEL_65:
                  v39 = -1;
                  v40 = (v29 - pcbRemaining) >> 1;
                  if ( v40 <= 0xFFFFFFFF )
                    v39 = v40;
                }
                OemToCharBuffA(v35, v35, v39);
                if ( !WriteFile(DhcpV6AuditLogHandle, v35, v39, &NumberOfBytesWritten, 0) )
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
                  HeapFree(gDhcpHeap, 0, v35);
                  goto LABEL_72;
                }
                HeapFree(gDhcpHeap, 0, v35);
              }
              HeapFree(gDhcpHeap, 0, v30);
              if ( v12 )
                HeapFree(gDhcpHeap, 0, v12);
              return 0;
            }
          }
        }
      }
    }
    LastError = 13;
    goto LABEL_72;
  }
LABEL_74:
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
0x1800676ec  push    rbp
0x1800676ee  push    rbx
0x1800676ef  push    rsi
0x1800676f0  push    rdi
0x1800676f1  push    r12
0x1800676f3  push    r13
0x1800676f5  push    r14
0x1800676f7  push    r15
0x1800676f9  lea     rbp, [rsp-2C8h]
0x180067701  sub     rsp, 3C8h
0x180067708  mov     rax, cs:__security_cookie
0x18006770f  xor     rax, rsp
0x180067712  mov     [rbp+300h+var_50], rax
0x180067719  mov     rax, [rbp+300h+arg_40]
0x180067720  mov     r14, rdx
0x180067723  mov     r15, [rbp+300h+arg_28]
0x18006772a  xor     edx, edx; Val
0x18006772c  cmp     [rbp+300h+arg_30], edx
0x180067732  mov     rsi, r8
0x180067735  mov     rdi, [rbp+300h+arg_48]
0x18006773c  mov     r12d, edx
0x18006773f  mov     [rbp+300h+var_380], ecx
0x180067742  lea     rcx, a2dSSSSSLd; "%.2d,%s,%s,%s,%s,%s,%ld"
0x180067749  mov     [rbp+300h+SourceString], rax
0x18006774d  lea     ebx, [rdx+4Ch]
0x180067750  lea     r13d, [rdx+30h]
0x180067754  mov     [rbp+300h+var_378], r9
0x180067758  lea     rax, a2dSSSSS; "%.2d,%s,%s,%s,%s,%s,"
0x18006775f  mov     [rbp+300h+NumberOfBytesWritten], edx
0x180067762  cmovnz  rax, rcx
0x180067766  mov     [rsp+400h+pcbRemaining], rdx
0x18006776b  mov     r8d, ebx; Size
0x18006776e  mov     [rbp+300h+var_360], rax
0x180067772  lea     rcx, [rbp+300h+var_31C]; void *
0x180067776  mov     [rbp+300h+var_320], r13d
0x18006777a  call    memset_0
0x18006777f  mov     r8d, ebx; Size
0x180067782  mov     [rbp+300h+var_2D0], r13d
0x180067786  xor     edx, edx; Val
0x180067788  lea     rcx, [rbp+300h+var_2CC]; void *
0x18006778c  call    memset_0
0x180067791  xor     r13d, r13d
0x180067794  cmp     cs:DhcpGlobalAuditLogFlag, r13d
0x18006779b  jz      loc_180067DA4
0x1800677a1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800677a5  cmp     cs:DhcpV6AuditLogHandle, rbx
0x1800677ac  jnz     short loc_1800677E7
0x1800677ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800677b5  lea     rax, WPP_GLOBAL_Control
0x1800677bc  cmp     rcx, rax
0x1800677bf  jz      loc_180067DA4
0x1800677c5  test    byte ptr [rcx+1Ch], 10h
0x1800677c9  jz      loc_180067DA4
0x1800677cf  mov     rcx, [rcx+10h]
0x1800677d3  lea     edx, [rbx+0Fh]
0x1800677d6  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x1800677dd  call    WPP_SF_
0x1800677e2  jmp     loc_180067DA4
0x1800677e7  lea     rcx, [rbp+300h+var_280]
0x1800677ee  call    GetUserAndDomainName
0x1800677f3  test    eax, eax
0x1800677f5  jz      short loc_1800677FF
0x1800677f7  mov     [rbp+300h+var_280], r13w
0x1800677ff  lea     rcx, [rbp+300h+Buffer]; Buffer
0x180067803  call    cs:__imp__wstrdate
0x18006780a  nop     dword ptr [rax+rax+00h]
0x18006780f  lea     rcx, [rbp+300h+var_350]; Buffer
0x180067813  call    cs:__imp__wstrtime
0x18006781a  nop     dword ptr [rax+rax+00h]
0x18006781f  test    r14, r14
0x180067822  lea     r13, Annotation
0x180067829  mov     rax, r13
0x18006782c  cmovnz  rax, r14
0x180067830  test    r15, r15
0x180067833  mov     [rbp+300h+var_368], rax
0x180067837  mov     rax, r13
0x18006783a  cmovnz  rax, r15
0x18006783e  xor     r15d, r15d
0x180067841  mov     [rbp+300h+var_370], rax
0x180067845  test    rsi, rsi
0x180067848  jnz     short loc_18006784F
0x18006784a  mov     r14, r13
0x18006784d  jmp     short loc_180067865
0x18006784f  lea     rdx, [rbp+300h+var_320]
0x180067853  mov     rcx, rsi
0x180067856  call    MemAddr6ConvertIpv6AddrToString
0x18006785b  test    eax, eax
0x18006785d  lea     r14, [rbp+300h+var_320]
0x180067861  cmovnz  r14, r13
0x180067865  test    rdi, rdi
0x180067868  jz      short loc_180067883
0x18006786a  lea     rdx, [rbp+300h+var_2D0]
0x18006786e  mov     rcx, rdi
0x180067871  call    MemAddr6ConvertIpv6AddrToString
0x180067876  test    eax, eax
0x180067878  lea     rcx, [rbp+300h+var_2D0]
0x18006787c  cmovnz  rcx, r13
0x180067880  mov     r13, rcx
0x180067883  mov     rax, [rbp+300h+var_370]
0x180067887  mov     rcx, rbx
0x18006788a  inc     rcx
0x18006788d  cmp     [rax+rcx*2], r15w
0x180067892  jnz     short loc_18006788A
0x180067894  mov     rdx, [rbp+300h+var_368]
0x180067898  mov     rax, rbx
0x18006789b  inc     rax
0x18006789e  cmp     [rdx+rax*2], r15w
0x1800678a3  jnz     short loc_18006789B
0x1800678a5  add     rcx, rax
0x1800678a8  mov     rax, rbx
0x1800678ab  inc     rax
0x1800678ae  cmp     [r14+rax*2], r15w
0x1800678b3  jnz     short loc_1800678AB
0x1800678b5  add     rcx, rax
0x1800678b8  lea     rdx, [rbp+300h+var_350]
0x1800678bc  mov     rax, rbx
0x1800678bf  inc     rax
0x1800678c2  cmp     [rdx+rax*2], r15w
0x1800678c7  jnz     short loc_1800678BF
0x1800678c9  add     rcx, rax
0x1800678cc  lea     rdx, [rbp+300h+Buffer]
0x1800678d0  mov     rax, rbx
0x1800678d3  inc     rax
0x1800678d6  cmp     [rdx+rax*2], r15w
0x1800678db  jnz     short loc_1800678D3
0x1800678dd  add     rcx, rax
0x1800678e0  lea     rax, [rbp+300h+var_280]
0x1800678e7  inc     rbx
0x1800678ea  cmp     [rax+rbx*2], r15w
0x1800678ef  jnz     short loc_1800678E7
0x1800678f1  mov     esi, [rbp+300h+arg_20]
0x1800678f7  add     rcx, rbx
0x1800678fa  mov     ebx, 8
0x1800678ff  mov     edx, ebx; dwFlags
0x180067901  lea     rax, [rsi+0B4h]
0x180067908  lea     rdi, [rcx+rax*2]
0x18006790c  mov     rcx, cs:gDhcpHeap; hHeap
0x180067913  add     rdi, rdi
0x180067916  mov     r8, rdi; dwBytes
0x180067919  call    cs:__imp_HeapAlloc
0x180067920  nop     dword ptr [rax+rax+00h]
0x180067925  mov     r15, rax
0x180067928  lea     eax, [rbx-7]
0x18006792b  test    r15, r15
0x18006792e  jnz     short loc_180067938
0x180067930  xor     r14d, r14d
0x180067933  jmp     loc_180067D33
0x180067938  mov     eax, [rbp+300h+arg_30]
0x18006793e  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067943  mov     [rsp+400h+var_3A0], eax
0x180067947  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x18006794c  mov     rax, [rbp+300h+var_370]
0x180067950  mov     rdx, rdi; cbDest
0x180067953  mov     [rsp+400h+var_3A8], rax
0x180067958  mov     rcx, r15; pszDest
0x18006795b  mov     rax, [rbp+300h+var_368]
0x18006795f  mov     [rsp+400h+var_3B0], r14
0x180067964  mov     [rsp+400h+var_3B8], rax
0x180067969  lea     rax, [rbp+300h+var_350]
0x18006796d  mov     [rsp+400h+var_3C0], rax
0x180067972  lea     rax, [rbp+300h+Buffer]
0x180067976  mov     [rsp+400h+var_3C8], rax
0x18006797b  mov     eax, [rbp+300h+var_380]
0x18006797e  mov     dword ptr [rsp+400h+var_3D0], eax
0x180067982  mov     rax, [rbp+300h+var_360]
0x180067986  mov     [rsp+400h+pszFormat], rax; dwFlags
0x18006798b  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067993  mov     [rsp+400h+ppszDestEnd], r15
0x180067998  call    StringCbPrintfExW
0x18006799d  xor     r14d, r14d
0x1800679a0  test    eax, eax
0x1800679a2  jns     short loc_1800679AE
0x1800679a4  mov     ebx, 0Dh
0x1800679a9  jmp     loc_180067CF9
0x1800679ae  cmp     [rbp+300h+var_378], r14
0x1800679b2  jz      loc_180067A5A
0x1800679b8  test    esi, esi
0x1800679ba  jz      loc_180067A5A
0x1800679c0  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x1800679c5  lea     rax, aLd_0; ",%ld,"
0x1800679cc  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x1800679d1  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x1800679d6  mov     dword ptr [rsp+400h+var_3D0], esi
0x1800679da  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x1800679df  mov     [rsp+400h+pszFormat], rax; pszFormat
0x1800679e4  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x1800679ec  call    StringCbPrintfExW
0x1800679f1  test    eax, eax
0x1800679f3  js      short loc_1800679A4
0x1800679f5  test    esi, esi
0x1800679f7  jz      loc_180067A87
0x1800679fd  mov     rcx, [rbp+300h+var_378]
0x180067a01  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067a06  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067a0b  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067a10  movzx   eax, byte ptr [rcx]
0x180067a13  inc     rcx
0x180067a16  mov     dword ptr [rsp+400h+var_3D0], eax
0x180067a1a  lea     rax, a2x; "%.2X"
0x180067a21  mov     [rbp+300h+var_378], rcx
0x180067a25  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067a2a  mov     [rsp+400h+pszFormat], rax; pszFormat
0x180067a2f  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067a37  call    StringCbPrintfExW
0x180067a3c  test    eax, eax
0x180067a3e  js      short loc_180067A4D
0x180067a40  inc     r14d
0x180067a43  cmp     r14d, esi
0x180067a46  jb      short loc_1800679FD
0x180067a48  xor     r14d, r14d
0x180067a4b  jmp     short loc_180067A87
0x180067a4d  mov     ebx, 0Dh
0x180067a52  xor     r14d, r14d
0x180067a55  jmp     loc_180067CF9
0x180067a5a  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067a5f  lea     rax, [rsp+400h+pcbRemaining]
0x180067a64  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067a69  lea     r9, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067a6e  lea     r8, asc_1800E4904; ",,"
0x180067a75  mov     qword ptr [rsp+400h+dwFlags], rax; pcbRemaining
0x180067a7a  call    StringCbCopyExW
0x180067a7f  test    eax, eax
0x180067a81  js      loc_1800679A4
0x180067a87  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067a8c  lea     rax, [rbp+300h+var_280]
0x180067a93  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067a98  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067a9d  mov     [rsp+400h+var_3D0], rax
0x180067aa2  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067aa7  lea     rax, aLs; ",%ls"
0x180067aae  mov     [rsp+400h+pszFormat], rax; dwFlags
0x180067ab3  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067abb  call    StringCbPrintfExW
0x180067ac0  test    eax, eax
0x180067ac2  js      loc_1800679A4
0x180067ac8  mov     rsi, [rsp+400h+ppszDestEnd]
0x180067acd  lea     rax, [rsp+400h+pcbRemaining]
0x180067ad2  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067ad7  lea     r8, asc_1800DC530; "\r\n"
0x180067ade  mov     rcx, rsi; pszDest
0x180067ae1  mov     qword ptr [rsp+400h+dwFlags], rax; pcbRemaining
0x180067ae6  xor     r9d, r9d; ppszDestEnd
0x180067ae9  call    StringCbCopyExW
0x180067aee  test    eax, eax
0x180067af0  js      loc_1800679A4
0x180067af6  mov     r8, [rbp+300h+arg_38]
0x180067afd  test    r8, r8
0x180067b00  jz      loc_180067C13
0x180067b06  mov     rax, [rbp+300h+SourceString]
0x180067b0a  test    rax, rax
0x180067b0d  jz      loc_180067C13
0x180067b13  inc     r8w
0x180067b17  xor     edx, edx
0x180067b19  mov     rcx, rax; SourceString
0x180067b1c  call    DhcpOemToUnicodeN
0x180067b21  mov     r12, rax
0x180067b24  test    rax, rax
0x180067b27  jz      loc_180067CF9
0x180067b2d  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067b32  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067b37  mov     [rsp+400h+var_3D0], rax
0x180067b3c  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067b41  lea     rax, aS_0; "%s"
0x180067b48  mov     rcx, rsi; pszDest
0x180067b4b  mov     [rsp+400h+pszFormat], rax; pszFormat
0x180067b50  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067b58  call    StringCbPrintfExW
0x180067b5d  test    eax, eax
0x180067b5f  js      loc_1800679A4
0x180067b65  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067b6a  lea     rax, aS; ",%s"
0x180067b71  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067b76  lea     r9, [rsp+400h+pcbRemaining]; pcbRemaining
0x180067b7b  mov     [rsp+400h+var_3D0], r13
0x180067b80  lea     r8, [rsp+400h+ppszDestEnd]; ppszDestEnd
0x180067b85  mov     [rsp+400h+pszFormat], rax; dwFlags
0x180067b8a  mov     [rsp+400h+dwFlags], 1000h; dwFlags
0x180067b92  call    StringCbPrintfExW
0x180067b97  test    eax, eax
0x180067b99  js      loc_1800679A4
0x180067b9f  mov     rdx, [rsp+400h+pcbRemaining]; cbDest
0x180067ba4  lea     rax, [rsp+400h+pcbRemaining]
0x180067ba9  mov     rcx, [rsp+400h+ppszDestEnd]; pszDest
0x180067bae  lea     r8, asc_1800E4928; ",\r\n"
0x180067bb5  xor     r9d, r9d; ppszDestEnd
0x180067bb8  mov     qword ptr [rsp+400h+dwFlags], rax; pcbRemaining
0x180067bbd  call    StringCbCopyExW
0x180067bc2  test    eax, eax
0x180067bc4  js      loc_1800679A4
0x180067bca  xor     edx, edx
0x180067bcc  mov     rcx, r15; SourceString
0x180067bcf  call    DhcpUnicodeToOem
0x180067bd4  mov     rsi, rax
0x180067bd7  test    rax, rax
0x180067bda  jz      loc_180067D6F
0x180067be0  cmp     rdi, 7FFFFFFFh
0x180067be7  ja      short loc_180067C50
0x180067be9  mov     rax, rdi
0x180067bec  mov     rcx, rsi
0x180067bef  test    rdi, rdi
  ... truncated ...
```
