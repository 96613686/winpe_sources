# CServerEnum::EnumServers(wchar_t *,ulong,int,int,wchar_t const *,ulong)

- ea: `0x1801a2850`
- end: `0x1801a2d4e`
- name: `?EnumServers@CServerEnum@@AEAAJPEA_WKHHPEB_WK@Z`
- size: `1278`
- prototype: `__int64 __fastcall(CServerEnum *__hidden this, wchar_t *, unsigned int, int, int, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801a00c0`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180013360`
- `0x180133fb4`
- `0x1801a2850`
- `0x1801a65e1`
- `0x1801ad380`
- `0x1801ad410`
- `0x1801ad440`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1801a2c05`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1801a2c05`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2970`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2984`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2998`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a29ac`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2970`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2984`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a2998`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a29ac`
- `KERNEL32!GetLastError` at `0x1801a2b66`
- `KERNEL32!GetLastError` at `0x1801a2b66`
- `KERNEL32!GetTickCount` at `0x1801a28b3`
- `KERNEL32!GetTickCount` at `0x1801a2a28`
- `KERNEL32!GetTickCount` at `0x1801a28b3`
- `KERNEL32!GetTickCount` at `0x1801a2a28`
- `KERNEL32!GetComputerNameW` at `0x1801a2b5c`
- `KERNEL32!GetComputerNameW` at `0x1801a2b5c`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a290c`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a290c`
- `ADVAPI32!RegEnumValueW` at `0x1801a2955`
- `ADVAPI32!RegEnumValueW` at `0x1801a2955`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1801a2cd5`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1801a2cd5`

## pseudocode

```c
__int64 __fastcall CServerEnum::EnumServers(
        CServerEnum *this,
        wchar_t *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        const wchar_t *a6,
        unsigned int a7)
{
  unsigned int v10; // esi
  DWORD TickCount; // r15d
  WCHAR *v13; // rbx
  DWORD v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rax
  SSRP::ServerEnum *v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rsi
  wchar_t *v21; // r14
  DWORD v22; // ecx
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  _WORD *v25; // rcx
  __int64 v26; // rdx
  __int16 v27; // ax
  _WORD *v28; // rax
  __int64 v29; // r12
  signed int LastError; // eax
  unsigned __int64 v31; // r15
  const wchar_t *v32; // r14
  unsigned __int64 v33; // rbx
  CExtVarBuffer *v34; // rcx
  int inserted; // eax
  wchar_t v36; // ax
  __int64 v37; // rax
  int v38; // eax
  unsigned __int64 v39; // rdx
  SSRP::ServerEnum *v41; // [rsp+40h] [rbp-C0h]
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD nSize; // [rsp+4Ch] [rbp-B4h] BYREF
  const wchar_t *Src; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-A8h]
  int v46; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v49[270]; // [rsp+72h] [rbp-8Eh] BYREF

  v46 = 1;
  v10 = 0;
  Buffer = 0;
  memset_0(v49, 0, 0x100u);
  nSize = 0;
  Src = 0;
  TickCount = GetTickCount();
  if ( a5 && (!a2 || !*a2) )
  {
    v13 = (WCHAR *)*((_QWORD *)this + 1);
    cchValueName = *((_DWORD *)this + 4);
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo", 0, 0x20019u, &hKey) )
    {
      if ( cchValueName )
      {
        do
        {
          v14 = v10++;
          if ( RegEnumValueW(hKey, v14, v13, &cchValueName, 0, 0, 0, 0) )
            break;
          if ( cchValueName
            && _wcsicmp(v13, L"Default")
            && _wcsicmp(v13, L"DSQUERY")
            && _wcsicmp(v13, L"SqlLocalizationFile")
            && _wcsicmp(v13, L"AutoAnsiToOem") )
          {
            v15 = cchValueName;
            *((_QWORD *)this + 3) += cchValueName + 1LL;
            v13 += v15 + 1;
          }
          cchValueName = *((_DWORD *)this + 4) - *((_DWORD *)this + 6);
        }
        while ( cchValueName );
        v10 = 0;
      }
    }
  }
  v16 = SNIServerEnumOpen(a2, a3, a4);
  v41 = (SSRP::ServerEnum *)v16;
  if ( v16 )
  {
    v18 = (SSRP::ServerEnum *)v16;
    while ( 1 )
    {
      v19 = *((_QWORD *)this + 3);
      v20 = *((_QWORD *)this + 2) - v19;
      v21 = (wchar_t *)(*((_QWORD *)this + 1) + 2 * v19);
      if ( a7 != -1 )
      {
        v22 = GetTickCount();
        if ( v22 - TickCount >= a7 )
          break;
        a7 -= v22 - TickCount;
        TickCount = v22;
      }
      *((_QWORD *)this + 3) += (int)SNIServerEnumReadEx(v18, v21, v20, &v46, a7);
      if ( !v46 )
        break;
      v23 = *((_QWORD *)this + 2);
      if ( v23 >= 0x72326 )
        break;
      v24 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD, unsigned __int64))(*(_QWORD *)g_pMO + 32LL))(
              g_pMO,
              *((_QWORD *)this + 1),
              2 * v23 + 64500);
      if ( !v24 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v10 = bidTraceHR(off_180262708[0], 172041, 2147942414LL);
        else
          v10 = -2147024882;
        goto LABEL_58;
      }
      *((_QWORD *)this + 2) += 32250LL;
      *((_QWORD *)this + 1) = v24;
    }
    if ( a6 )
    {
      v25 = (_WORD *)((char *)this + 40);
      v26 = 129;
      do
      {
        if ( v26 == -2147483517 )
          break;
        v27 = *(_WORD *)((char *)v25 + (char *)a6 - ((char *)this + 40));
        if ( !v27 )
          break;
        *v25++ = v27;
        --v26;
      }
      while ( v26 );
      v28 = v25 - 1;
      v29 = -1;
      if ( v26 )
        v28 = v25;
      v10 = 0;
      *v28 = 0;
      do
        ++v29;
      while ( *((_WORD *)this + v29 + 20) );
      nSize = 129;
      if ( !GetComputerNameW(&Buffer, &nSize) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_58:
        SNIServerEnumClose(v41);
        return v10;
      }
    }
    else
    {
      v29 = (__int64)Src;
      v10 = 0;
    }
    v31 = 0;
    v32 = (const wchar_t *)*((_QWORD *)this + 1);
    if ( *((_QWORD *)this + 3) )
    {
      while ( 1 )
      {
        v33 = -1;
        do
          ++v33;
        while ( v32[v33] );
        v34 = *(CExtVarBuffer **)this;
        hKey = 0;
        Src = v32;
        v45 = v33;
        inserted = CExtVarBuffer::InsertIntoExtBuffer(v34, &Src, (unsigned __int64 *)&hKey);
        v10 = inserted;
        if ( inserted < 0 )
          break;
        if ( a6 )
        {
          if ( v33 >= nSize && !_wcsnicmp(v32, &Buffer, nSize) )
          {
            v36 = v32[nSize];
            if ( !v36 || v36 == 59 )
            {
              if ( v36 == 59 )
              {
                StringCchPrintfW((wchar_t *)this + 149, 0x101u, L"%s%s", (char *)this + 40, &v32[nSize]);
                v37 = -1;
                Src = (const wchar_t *)((char *)this + 298);
                do
                  ++v37;
                while ( *((_WORD *)this + v37 + 149) );
                v45 = v37;
              }
              else
              {
                Src = (const wchar_t *)((char *)this + 40);
                v45 = v29;
              }
              v38 = CExtVarBuffer::InsertIntoExtBuffer(*(CExtVarBuffer **)this, &Src, (unsigned __int64 *)&hKey);
              v10 = v38;
              if ( v38 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_180262708[0], 253961, (unsigned int)v38);
                }
                goto LABEL_58;
              }
            }
          }
        }
        v31 += v33 + 1;
        v32 += v33 + 1;
        v10 = 0;
        if ( v31 >= *((_QWORD *)this + 3) )
          goto LABEL_56;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180262708[0], 219145, (unsigned int)inserted);
      }
    }
    else
    {
LABEL_56:
      v39 = *(_QWORD *)(*(_QWORD *)this + 8LL);
      if ( v39 > 2 )
        qsort((void *)(**(_QWORD **)this + *(_QWORD *)(*(_QWORD *)this + 32LL)), v39 - 1, 0x10u, EnumCompare);
    }
    goto LABEL_58;
  }
  return v10;
}

```

## disassembly

```asm
0x1801a2850  push    rbp
0x1801a2852  push    rbx
0x1801a2853  push    rsi
0x1801a2854  push    rdi
0x1801a2855  push    r12
0x1801a2857  push    r13
0x1801a2859  push    r14
0x1801a285b  push    r15
0x1801a285d  lea     rbp, [rsp-98h]
0x1801a2865  sub     rsp, 198h
0x1801a286c  mov     rax, cs:__security_cookie
0x1801a2873  xor     rax, rsp
0x1801a2876  mov     [rbp+0D0h+var_50], rax
0x1801a287d  mov     r12d, r8d
0x1801a2880  mov     [rsp+1D0h+var_170], 1
0x1801a2888  mov     r14, rdx
0x1801a288b  mov     rdi, rcx
0x1801a288e  xor     esi, esi
0x1801a2890  lea     rcx, [rsp+1D0h+var_15E]; void *
0x1801a2895  xor     edx, edx; Val
0x1801a2897  mov     [rsp+1D0h+Buffer], si
0x1801a289c  mov     r8d, 100h; Size
0x1801a28a2  mov     r13d, r9d
0x1801a28a5  call    memset_0
0x1801a28aa  mov     [rsp+1D0h+nSize], esi
0x1801a28ae  mov     [rsp+1D0h+Src], rsi
0x1801a28b3  call    cs:__imp_GetTickCount
0x1801a28b9  mov     r15d, eax
0x1801a28bc  mov     dword ptr [rsp+1D0h+var_190], eax
0x1801a28c0  cmp     [rbp+0D0h+arg_20], esi
0x1801a28c6  jz      loc_1801A29E1
0x1801a28cc  test    r14, r14
0x1801a28cf  jz      short loc_1801A28DB
0x1801a28d1  cmp     [r14], si
0x1801a28d5  jnz     loc_1801A29E1
0x1801a28db  mov     eax, [rdi+10h]
0x1801a28de  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x1801a28e5  mov     rbx, [rdi+8]
0x1801a28e9  mov     r9d, 20019h; samDesired
0x1801a28ef  mov     [rsp+1D0h+cchValueName], eax
0x1801a28f3  xor     r8d, r8d; ulOptions
0x1801a28f6  lea     rax, [rsp+1D0h+hKey]
0x1801a28fb  mov     [rsp+1D0h+hKey], rsi
0x1801a2900  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a2907  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1801a290c  call    cs:__imp_RegOpenKeyExW
0x1801a2912  test    eax, eax
0x1801a2914  jnz     loc_1801A29E1
0x1801a291a  cmp     [rsp+1D0h+cchValueName], esi
0x1801a291e  jz      loc_1801A29E1
0x1801a2924  xor     r15d, r15d
0x1801a2927  nop     word ptr [rax+rax+00000000h]
0x1801a2930  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801a2935  lea     r9, [rsp+1D0h+cchValueName]; lpcchValueName
0x1801a293a  mov     [rsp+1D0h+lpcbData], r15; lpcbData
0x1801a293f  mov     edx, esi; dwIndex
0x1801a2941  mov     [rsp+1D0h+lpData], r15; lpData
0x1801a2946  mov     r8, rbx; lpValueName
0x1801a2949  mov     [rsp+1D0h+lpType], r15; lpType
0x1801a294e  inc     esi
0x1801a2950  mov     [rsp+1D0h+phkResult], r15; lpReserved
0x1801a2955  call    cs:__imp_RegEnumValueW
0x1801a295b  test    eax, eax
0x1801a295d  jnz     short loc_1801A29DA
0x1801a295f  cmp     [rsp+1D0h+cchValueName], r15d
0x1801a2964  jz      short loc_1801A29CA
0x1801a2966  lea     rdx, aDefault_0; "Default"
0x1801a296d  mov     rcx, rbx; String1
0x1801a2970  call    cs:__imp__wcsicmp
0x1801a2976  test    eax, eax
0x1801a2978  jz      short loc_1801A29CA
0x1801a297a  lea     rdx, aDsquery; "DSQUERY"
0x1801a2981  mov     rcx, rbx; String1
0x1801a2984  call    cs:__imp__wcsicmp
0x1801a298a  test    eax, eax
0x1801a298c  jz      short loc_1801A29CA
0x1801a298e  lea     rdx, aSqllocalizatio; "SqlLocalizationFile"
0x1801a2995  mov     rcx, rbx; String1
0x1801a2998  call    cs:__imp__wcsicmp
0x1801a299e  test    eax, eax
0x1801a29a0  jz      short loc_1801A29CA
0x1801a29a2  lea     rdx, aAutoansitooem; "AutoAnsiToOem"
0x1801a29a9  mov     rcx, rbx; String1
0x1801a29ac  call    cs:__imp__wcsicmp
0x1801a29b2  test    eax, eax
0x1801a29b4  jz      short loc_1801A29CA
0x1801a29b6  mov     ecx, [rsp+1D0h+cchValueName]
0x1801a29ba  lea     rax, [rcx+1]
0x1801a29be  add     [rdi+18h], rax
0x1801a29c2  lea     rbx, [rbx+rcx*2]
0x1801a29c6  add     rbx, 2
0x1801a29ca  mov     eax, [rdi+10h]
0x1801a29cd  sub     eax, [rdi+18h]
0x1801a29d0  mov     [rsp+1D0h+cchValueName], eax
0x1801a29d4  jnz     loc_1801A2930
0x1801a29da  mov     r15d, dword ptr [rsp+1D0h+var_190]
0x1801a29df  xor     esi, esi
0x1801a29e1  mov     r8d, r13d
0x1801a29e4  mov     edx, r12d
0x1801a29e7  mov     rcx, r14
0x1801a29ea  call    SNIServerEnumOpen
0x1801a29ef  mov     [rsp+1D0h+var_190], rax
0x1801a29f4  test    rax, rax
0x1801a29f7  jz      loc_1801A2CE5
0x1801a29fd  mov     ebx, [rbp+0D0h+arg_30]
0x1801a2a03  mov     r12, rax
0x1801a2a06  nop     word ptr [rax+rax+00000000h]
0x1801a2a10  mov     rcx, [rdi+18h]
0x1801a2a14  mov     rax, [rdi+8]
0x1801a2a18  mov     rsi, [rdi+10h]
0x1801a2a1c  sub     rsi, rcx
0x1801a2a1f  lea     r14, [rax+rcx*2]
0x1801a2a23  cmp     ebx, 0FFFFFFFFh
0x1801a2a26  jz      short loc_1801A2A40
0x1801a2a28  call    cs:__imp_GetTickCount
0x1801a2a2e  mov     ecx, eax
0x1801a2a30  sub     eax, r15d
0x1801a2a33  cmp     eax, ebx
0x1801a2a35  jnb     loc_1801A2AD9
0x1801a2a3b  sub     ebx, eax
0x1801a2a3d  mov     r15d, ecx
0x1801a2a40  lea     r9, [rsp+1D0h+var_170]; int *
0x1801a2a45  mov     dword ptr [rsp+1D0h+phkResult], ebx; int
0x1801a2a49  mov     r8d, esi; int
0x1801a2a4c  mov     rdx, r14; wchar_t *
0x1801a2a4f  mov     rcx, r12; this
0x1801a2a52  call    SNIServerEnumReadEx
0x1801a2a57  movsxd  rcx, eax
0x1801a2a5a  add     [rdi+18h], rcx
0x1801a2a5e  cmp     [rsp+1D0h+var_170], 0
0x1801a2a63  jz      short loc_1801A2AD9
0x1801a2a65  mov     r8, [rdi+10h]
0x1801a2a69  cmp     r8, 72326h
0x1801a2a70  jnb     short loc_1801A2AD9
0x1801a2a72  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1801a2a79  lea     r8, ds:0FBF4h[r8*2]
0x1801a2a81  mov     rdx, [rdi+8]
0x1801a2a85  mov     rax, [rcx]
0x1801a2a88  mov     rax, [rax+20h]
0x1801a2a8c  call    cs:__guard_dispatch_icall_fptr
0x1801a2a92  test    rax, rax
0x1801a2a95  jz      short loc_1801A2AA8
0x1801a2a97  add     qword ptr [rdi+10h], 7DFAh
0x1801a2a9f  mov     [rdi+8], rax
0x1801a2aa3  jmp     loc_1801A2A10
0x1801a2aa8  test    byte ptr cs:_bidGblFlags, 2
0x1801a2aaf  jz      short loc_1801A2ACF
0x1801a2ab1  mov     rcx, cs:off_180262708; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\td"...
0x1801a2ab8  mov     edx, 2A009h
0x1801a2abd  mov     r8d, 8007000Eh
0x1801a2ac3  call    _bidTraceHR
0x1801a2ac8  mov     esi, eax
0x1801a2aca  jmp     loc_1801A2CDB
0x1801a2acf  mov     esi, 8007000Eh
0x1801a2ad4  jmp     loc_1801A2CDB
0x1801a2ad9  mov     r13, [rbp+0D0h+arg_28]
0x1801a2ae0  test    r13, r13
0x1801a2ae3  jz      loc_1801A2B84
0x1801a2ae9  lea     r9, [rdi+28h]
0x1801a2aed  mov     r8, r13
0x1801a2af0  mov     rcx, r9
0x1801a2af3  sub     r8, r9
0x1801a2af6  mov     edx, 81h
0x1801a2afb  nop     dword ptr [rax+rax+00h]
0x1801a2b00  lea     rax, [rdx+7FFFFF7Dh]
0x1801a2b07  test    rax, rax
0x1801a2b0a  jz      short loc_1801A2B23
0x1801a2b0c  movzx   eax, word ptr [r8+rcx]
0x1801a2b11  test    ax, ax
0x1801a2b14  jz      short loc_1801A2B23
0x1801a2b16  mov     [rcx], ax
0x1801a2b19  add     rcx, 2
0x1801a2b1d  sub     rdx, 1
0x1801a2b21  jnz     short loc_1801A2B00
0x1801a2b23  test    rdx, rdx
0x1801a2b26  lea     rax, [rcx-2]
0x1801a2b2a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1801a2b31  cmovnz  rax, rcx
0x1801a2b35  xor     esi, esi
0x1801a2b37  mov     [rax], si
0x1801a2b3a  nop     word ptr [rax+rax+00h]
0x1801a2b40  inc     r12
0x1801a2b43  cmp     [r9+r12*2], si
0x1801a2b48  jnz     short loc_1801A2B40
0x1801a2b4a  lea     rdx, [rsp+1D0h+nSize]; nSize
0x1801a2b4f  mov     [rsp+1D0h+nSize], 81h
0x1801a2b57  lea     rcx, [rsp+1D0h+Buffer]; lpBuffer
0x1801a2b5c  call    cs:__imp_GetComputerNameW
0x1801a2b62  test    eax, eax
0x1801a2b64  jnz     short loc_1801A2B8B
0x1801a2b66  call    cs:__imp_GetLastError
0x1801a2b6c  mov     esi, eax
0x1801a2b6e  test    eax, eax
0x1801a2b70  jle     loc_1801A2CDB
0x1801a2b76  movzx   esi, ax
0x1801a2b79  or      esi, 80070000h
0x1801a2b7f  jmp     loc_1801A2CDB
0x1801a2b84  mov     r12, [rsp+1D0h+Src]
0x1801a2b89  xor     esi, esi
0x1801a2b8b  cmp     qword ptr [rdi+18h], 0
0x1801a2b90  mov     r15, rsi
0x1801a2b93  mov     r14, [rdi+8]
0x1801a2b97  jbe     loc_1801A2CB1
0x1801a2b9d  nop     dword ptr [rax]
0x1801a2ba0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1801a2ba7  nop     word ptr [rax+rax+00000000h]
0x1801a2bb0  inc     rbx
0x1801a2bb3  cmp     word ptr [r14+rbx*2], 0
0x1801a2bb9  jnz     short loc_1801A2BB0
0x1801a2bbb  mov     rcx, [rdi]; this
0x1801a2bbe  lea     r8, [rsp+1D0h+hKey]; unsigned __int64 *
0x1801a2bc3  lea     rdx, [rsp+1D0h+Src]; Src
0x1801a2bc8  mov     [rsp+1D0h+hKey], rsi
0x1801a2bcd  mov     [rsp+1D0h+Src], r14
0x1801a2bd2  mov     [rsp+1D0h+var_178], rbx
0x1801a2bd7  call    ?InsertIntoExtBuffer@CExtVarBuffer@@QEAAJPEAXAEA_K@Z; CExtVarBuffer::InsertIntoExtBuffer(void *,unsigned __int64 &)
0x1801a2bdc  mov     esi, eax
0x1801a2bde  test    eax, eax
0x1801a2be0  js      loc_1801A2D2C
0x1801a2be6  test    r13, r13
0x1801a2be9  jz      loc_1801A2C97
0x1801a2bef  mov     r8d, [rsp+1D0h+nSize]; MaxCount
0x1801a2bf4  cmp     rbx, r8
0x1801a2bf7  jb      loc_1801A2C97
0x1801a2bfd  lea     rdx, [rsp+1D0h+Buffer]; String2
0x1801a2c02  mov     rcx, r14; String1
0x1801a2c05  call    cs:__imp__wcsnicmp
0x1801a2c0b  test    eax, eax
0x1801a2c0d  jnz     loc_1801A2C97
0x1801a2c13  mov     eax, [rsp+1D0h+nSize]
0x1801a2c17  lea     rdx, [r14+rax*2]
0x1801a2c1b  movzx   eax, word ptr [r14+rax*2]
0x1801a2c20  test    ax, ax
0x1801a2c23  jz      short loc_1801A2C2B
0x1801a2c25  cmp     ax, 3Bh ; ';'
0x1801a2c29  jnz     short loc_1801A2C97
0x1801a2c2b  lea     rcx, [rdi+28h]
0x1801a2c2f  cmp     ax, 3Bh ; ';'
0x1801a2c33  jnz     short loc_1801A2C75
0x1801a2c35  mov     [rsp+1D0h+phkResult], rdx
0x1801a2c3a  lea     rsi, [rdi+12Ah]
0x1801a2c41  mov     r9, rcx
0x1801a2c44  lea     r8, aSS_1; "%s%s"
0x1801a2c4b  mov     rcx, rsi; Buffer
0x1801a2c4e  mov     edx, 101h; unsigned __int64
0x1801a2c53  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801a2c58  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1801a2c5f  mov     [rsp+1D0h+Src], rsi
0x1801a2c64  inc     rax
0x1801a2c67  cmp     word ptr [rsi+rax*2], 0
0x1801a2c6c  jnz     short loc_1801A2C64
0x1801a2c6e  mov     [rsp+1D0h+var_178], rax
0x1801a2c73  jmp     short loc_1801A2C7F
0x1801a2c75  mov     [rsp+1D0h+Src], rcx
0x1801a2c7a  mov     [rsp+1D0h+var_178], r12
0x1801a2c7f  mov     rcx, [rdi]; this
0x1801a2c82  lea     r8, [rsp+1D0h+hKey]; unsigned __int64 *
0x1801a2c87  lea     rdx, [rsp+1D0h+Src]; Src
0x1801a2c8c  call    ?InsertIntoExtBuffer@CExtVarBuffer@@QEAAJPEAXAEA_K@Z; CExtVarBuffer::InsertIntoExtBuffer(void *,unsigned __int64 &)
0x1801a2c91  mov     esi, eax
0x1801a2c93  test    eax, eax
0x1801a2c95  js      short loc_1801A2D0A
0x1801a2c97  inc     r15
0x1801a2c9a  lea     r14, [r14+rbx*2]
0x1801a2c9e  add     r15, rbx
0x1801a2ca1  add     r14, 2
0x1801a2ca5  xor     esi, esi
0x1801a2ca7  cmp     r15, [rdi+18h]
0x1801a2cab  jb      loc_1801A2BA0
0x1801a2cb1  mov     rax, [rdi]
0x1801a2cb4  mov     rdx, [rax+8]
0x1801a2cb8  cmp     rdx, 2
0x1801a2cbc  jbe     short loc_1801A2CDB
0x1801a2cbe  mov     rcx, [rax+20h]
0x1801a2cc2  lea     r9, ?EnumCompare@@YAHPEBX0@Z; CompareFunction
0x1801a2cc9  add     rcx, [rax]; Base
0x1801a2ccc  dec     rdx; NumOfElements
0x1801a2ccf  mov     r8d, 10h; SizeOfElements
0x1801a2cd5  call    cs:__imp_qsort
0x1801a2cdb  mov     rcx, [rsp+1D0h+var_190]; this
0x1801a2ce0  call    SNIServerEnumClose
0x1801a2ce5  mov     eax, esi
0x1801a2ce7  mov     rcx, [rbp+0D0h+var_50]
0x1801a2cee  xor     rcx, rsp; StackCookie
0x1801a2cf1  call    __security_check_cookie
0x1801a2cf6  add     rsp, 198h
0x1801a2cfd  pop     r15
0x1801a2cff  pop     r14
0x1801a2d01  pop     r13
0x1801a2d03  pop     r12
0x1801a2d05  pop     rdi
0x1801a2d06  pop     rsi
0x1801a2d07  pop     rbx
0x1801a2d08  pop     rbp
0x1801a2d09  retn
0x1801a2d0a  test    byte ptr cs:_bidGblFlags, 2
0x1801a2d11  jz      short loc_1801A2CDB
0x1801a2d13  lfence
0x1801a2d16  mov     rcx, cs:off_180262708; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\td"...
0x1801a2d1d  mov     r8d, eax
  ... truncated ...
```
