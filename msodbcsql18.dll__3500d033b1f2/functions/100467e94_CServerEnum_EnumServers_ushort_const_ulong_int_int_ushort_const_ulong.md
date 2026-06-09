# CServerEnum::EnumServers(ushort const *,ulong,int,int,ushort const *,ulong)

- ea: `0x100467e94`
- end: `0x10046831a`
- name: `?EnumServers@CServerEnum@@AEAAJPEBGKHH0K@Z`
- size: `1158`
- prototype: `__int64 __usercall@<rax>(CServerEnum *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, int@<r9d>, int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1004666ec`

## callees

- `0x100405948`
- `0x100442850`
- `0x1004428d0`
- `0x1004428f4`
- `0x100467e94`
- `0x1004684e4`
- `0x10046ca64`
- `0x100546a24`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x100468179`
- `KERNEL32!GetComputerNameW` at `0x100468179`
- `KERNEL32!GetLastError` at `0x100468183`
- `KERNEL32!GetLastError` at `0x100468183`
- `KERNEL32!GetTickCount` at `0x100467eef`
- `KERNEL32!GetTickCount` at `0x100468059`
- `KERNEL32!GetTickCount` at `0x100467eef`
- `KERNEL32!GetTickCount` at `0x100468059`
- `ADVAPI32!RegEnumValueW` at `0x100467f96`
- `ADVAPI32!RegEnumValueW` at `0x100467f96`
- `ADVAPI32!RegOpenKeyExW` at `0x100467f52`
- `ADVAPI32!RegOpenKeyExW` at `0x100467f52`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fb1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fc5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fd9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fed`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fb1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fc5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fd9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100467fed`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100468208`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100468208`

## pseudocode

```c
__int64 __fastcall CServerEnum::EnumServers(
        CServerEnum *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        char *a6,
        unsigned int a7)
{
  unsigned int v7; // r12d
  unsigned int v10; // ebx
  DWORD TickCount; // r15d
  DWORD v13; // r15d
  WCHAR *v14; // rsi
  DWORD v15; // edx
  __int64 v16; // rax
  SSRP::ServerEnum *v17; // r13
  __int64 v19; // rcx
  __int64 v20; // rsi
  unsigned __int16 *v21; // r14
  DWORD v22; // ecx
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r9
  unsigned int v26; // eax
  __int64 v27; // rdx
  _WORD *v28; // rcx
  __int16 v29; // ax
  _WORD *v30; // rax
  __int64 v31; // r12
  signed int LastError; // eax
  const wchar_t *v33; // r14
  unsigned __int64 v34; // rsi
  CExtVarBuffer *v35; // rcx
  int inserted; // eax
  __int64 v37; // r9
  const wchar_t *v38; // rcx
  __int64 v39; // rax
  __int64 v41; // r8
  __int64 v42; // rdx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v44; // [rsp+44h] [rbp-BCh]
  DWORD nSize; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *Source; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v49; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v51; // [rsp+70h] [rbp-90h]
  WCHAR Buffer[136]; // [rsp+80h] [rbp-80h] BYREF

  v7 = a3;
  LODWORD(v47) = a3;
  v46 = 1;
  v10 = 0;
  memset_0(Buffer, 0, 0x102u);
  TickCount = GetTickCount();
  v44 = TickCount;
  v51 = 0;
  if ( a5 && (!a2 || !*a2) )
  {
    cchValueName = *((_DWORD *)this + 4);
    v13 = 0;
    hKey = 0;
    v14 = (WCHAR *)*((_QWORD *)this + 1);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo", 0, 0x20019u, &hKey)
      && cchValueName )
    {
      do
      {
        v15 = v13++;
        if ( RegEnumValueW(hKey, v15, v14, &cchValueName, 0, 0, 0, 0) )
          break;
        if ( cchValueName
          && _wcsicmp(v14, L"Default")
          && _wcsicmp(v14, L"DSQUERY")
          && _wcsicmp(v14, L"SqlLocalizationFile")
          && _wcsicmp(v14, L"AutoAnsiToOem") )
        {
          v16 = cchValueName + 1;
          *((_QWORD *)this + 3) += v16;
          v14 += v16;
        }
        cchValueName = *((_DWORD *)this + 4) - *((_DWORD *)this + 6);
      }
      while ( cchValueName );
      v7 = v47;
    }
    TickCount = v44;
  }
  v17 = (SSRP::ServerEnum *)SNIServerEnumOpen(a2, v7, a4);
  if ( v17 )
  {
    while ( 1 )
    {
      v19 = *((_QWORD *)this + 3);
      v20 = *((_QWORD *)this + 2) - v19;
      v21 = (unsigned __int16 *)(*((_QWORD *)this + 1) + 2 * v19);
      if ( a7 != -1 )
      {
        v22 = GetTickCount();
        if ( v22 - TickCount >= a7 )
          break;
        a7 -= v22 - TickCount;
        TickCount = v22;
      }
      *((_QWORD *)this + 3) += (int)SNIServerEnumReadEx(v17, v21, v20, &v46, a7);
      if ( !v46 )
        break;
      v23 = *((_QWORD *)this + 2);
      if ( v23 >= 0x72326 )
        break;
      v24 = ((__int64 (__fastcall *)(struct IMalloc *, _QWORD, unsigned __int64))g_pMO->lpVtbl->Realloc)(
              g_pMO,
              *((_QWORD *)this + 1),
              2 * v23 + 64500);
      if ( !v24 )
      {
        if ( (bidGblFlags & 2) == 0 )
        {
          v10 = -2147024882;
          goto LABEL_59;
        }
        v26 = bidTraceHR(0, 167945, 2147942414LL, v25);
        goto LABEL_58;
      }
      *((_QWORD *)this + 2) += 32250LL;
      *((_QWORD *)this + 1) = v24;
    }
    if ( a6 )
    {
      v27 = 129;
      v28 = (_WORD *)((char *)this + 40);
      do
      {
        if ( v27 == -2147483517 )
          break;
        v29 = *(_WORD *)((char *)v28 + a6 - ((char *)this + 40));
        if ( !v29 )
          break;
        *v28++ = v29;
        --v27;
      }
      while ( v27 );
      v30 = v28 - 1;
      if ( v27 )
        v30 = v28;
      v31 = -1;
      *v30 = 0;
      do
        ++v31;
      while ( *((_WORD *)this + v31 + 20) );
      nSize = 129;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        v10 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v10 = LastError;
LABEL_59:
        SNIServerEnumClose(v17);
        return v10;
      }
    }
    else
    {
      v31 = 0;
    }
    v33 = (const wchar_t *)*((_QWORD *)this + 1);
    if ( !*((_QWORD *)this + 3) )
    {
LABEL_57:
      v26 = CServerEnum::SortEnumServers(this);
LABEL_58:
      v10 = v26;
      goto LABEL_59;
    }
    while ( 1 )
    {
      v34 = -1;
      do
        ++v34;
      while ( v33[v34] );
      v35 = *(CExtVarBuffer **)this;
      v47 = 0;
      Source = v33;
      v49 = v34;
      inserted = CExtVarBuffer::InsertIntoExtBuffer(v35, &Source, &v47);
      v10 = inserted;
      if ( inserted < 0 )
        break;
      if ( a6 )
      {
        if ( v34 >= nSize && !_wcsnicmp(v33, Buffer, nSize) )
        {
          v38 = &v33[nSize];
          if ( !*v38 || *v38 == 59 )
          {
            if ( *v38 == 59 )
            {
              StringCchPrintfW((unsigned __int16 *)this + 149, 0x101u, L"%s%s", (char *)this + 40, &v33[nSize]);
              v39 = -1;
              Source = (const wchar_t *)((char *)this + 298);
              do
                ++v39;
              while ( *((_WORD *)this + v39 + 149) );
              v49 = v39;
            }
            else
            {
              Source = (const wchar_t *)((char *)this + 40);
              v49 = v31;
            }
            v10 = CExtVarBuffer::InsertIntoExtBuffer(*(CExtVarBuffer **)this, &Source, &v47);
            if ( (v10 & 0x80000000) != 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_59;
              v41 = v10;
              v42 = 247817;
              goto LABEL_65;
            }
          }
        }
      }
      v33 += v34 + 1;
      v51 += v34 + 1;
      if ( v51 >= *((_QWORD *)this + 3) )
        goto LABEL_57;
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_59;
    v41 = (unsigned int)inserted;
    v42 = 213001;
LABEL_65:
    _mm_lfence();
    bidTraceHR(0, v42, v41, v37);
    goto LABEL_59;
  }
  return v10;
}

```

## disassembly

```asm
0x100467e94  push    rbp
0x100467e96  push    rbx
0x100467e97  push    rsi
0x100467e98  push    rdi
0x100467e99  push    r12
0x100467e9b  push    r13
0x100467e9d  push    r14
0x100467e9f  push    r15
0x100467ea1  lea     rbp, [rsp-0A8h]
0x100467ea9  sub     rsp, 1A8h
0x100467eb0  mov     rax, cs:__security_cookie
0x100467eb7  xor     rax, rsp
0x100467eba  mov     [rbp+0E0h+var_50], rax
0x100467ec1  mov     r12d, r8d
0x100467ec4  mov     dword ptr [rsp+1E0h+var_190], r8d
0x100467ec9  mov     r14, rdx
0x100467ecc  mov     [rsp+1E0h+var_194], 1
0x100467ed4  mov     rdi, rcx
0x100467ed7  xor     esi, esi
0x100467ed9  xor     edx, edx; Val
0x100467edb  lea     rcx, [rbp+0E0h+Buffer]; void *
0x100467edf  mov     r8d, 102h; Size
0x100467ee5  mov     ebx, esi
0x100467ee7  mov     r13d, r9d
0x100467eea  call    memset_0
0x100467eef  call    cs:__imp_GetTickCount
0x100467ef5  mov     r15d, eax
0x100467ef8  mov     [rsp+1E0h+var_19C], eax
0x100467efc  mov     [rsp+1E0h+var_170], rsi
0x100467f01  cmp     [rbp+0E0h+arg_20], esi
0x100467f07  jz      loc_100468021
0x100467f0d  test    r14, r14
0x100467f10  jz      short loc_100467F1C
0x100467f12  cmp     [r14], si
0x100467f16  jnz     loc_100468021
0x100467f1c  mov     eax, [rdi+10h]
0x100467f1f  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x100467f26  xor     ecx, ecx
0x100467f28  mov     [rsp+1E0h+cchValueName], eax
0x100467f2c  mov     r15d, ecx
0x100467f2f  mov     [rsp+1E0h+hKey], rsi
0x100467f34  mov     rsi, [rdi+8]
0x100467f38  lea     rax, [rsp+1E0h+hKey]
0x100467f3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100467f44  mov     [rsp+1E0h+phkResult], rax; phkResult
0x100467f49  mov     r9d, 20019h; samDesired
0x100467f4f  xor     r8d, r8d; ulOptions
0x100467f52  call    cs:__imp_RegOpenKeyExW
0x100467f58  xor     ecx, ecx
0x100467f5a  test    eax, eax
0x100467f5c  jnz     loc_10046801C
0x100467f62  cmp     [rsp+1E0h+cchValueName], ecx
0x100467f66  jz      loc_10046801C
0x100467f6c  xor     r12d, r12d
0x100467f6f  mov     rcx, [rsp+1E0h+hKey]; hKey
0x100467f74  lea     r9, [rsp+1E0h+cchValueName]; lpcchValueName
0x100467f79  mov     [rsp+1E0h+lpcbData], r12; lpcbData
0x100467f7e  mov     edx, r15d; dwIndex
0x100467f81  mov     [rsp+1E0h+lpData], r12; lpData
0x100467f86  mov     r8, rsi; lpValueName
0x100467f89  mov     [rsp+1E0h+lpType], r12; lpType
0x100467f8e  inc     r15d
0x100467f91  mov     [rsp+1E0h+phkResult], r12; lpReserved
0x100467f96  call    cs:__imp_RegEnumValueW
0x100467f9c  test    eax, eax
0x100467f9e  jnz     short loc_100468017
0x100467fa0  cmp     [rsp+1E0h+cchValueName], r12d
0x100467fa5  jz      short loc_100468007
0x100467fa7  lea     rdx, aDefault; "Default"
0x100467fae  mov     rcx, rsi; String1
0x100467fb1  call    cs:__imp__wcsicmp
0x100467fb7  test    eax, eax
0x100467fb9  jz      short loc_100468007
0x100467fbb  lea     rdx, aDsquery; "DSQUERY"
0x100467fc2  mov     rcx, rsi; String1
0x100467fc5  call    cs:__imp__wcsicmp
0x100467fcb  test    eax, eax
0x100467fcd  jz      short loc_100468007
0x100467fcf  lea     rdx, aSqllocalizatio; "SqlLocalizationFile"
0x100467fd6  mov     rcx, rsi; String1
0x100467fd9  call    cs:__imp__wcsicmp
0x100467fdf  test    eax, eax
0x100467fe1  jz      short loc_100468007
0x100467fe3  lea     rdx, aAutoansitooem; "AutoAnsiToOem"
0x100467fea  mov     rcx, rsi; String1
0x100467fed  call    cs:__imp__wcsicmp
0x100467ff3  test    eax, eax
0x100467ff5  jz      short loc_100468007
0x100467ff7  mov     eax, [rsp+1E0h+cchValueName]
0x100467ffb  inc     eax
0x100467ffd  mov     ecx, eax
0x100467fff  add     [rdi+18h], rcx
0x100468003  lea     rsi, [rsi+rax*2]
0x100468007  mov     eax, [rdi+10h]
0x10046800a  sub     eax, [rdi+18h]
0x10046800d  mov     [rsp+1E0h+cchValueName], eax
0x100468011  jnz     loc_100467F6F
0x100468017  mov     r12d, dword ptr [rsp+1E0h+var_190]
0x10046801c  mov     r15d, [rsp+1E0h+var_19C]
0x100468021  mov     r8d, r13d
0x100468024  mov     edx, r12d
0x100468027  mov     rcx, r14
0x10046802a  call    SNIServerEnumOpen
0x10046802f  mov     r13, rax
0x100468032  test    rax, rax
0x100468035  jz      loc_1004682C5
0x10046803b  mov     ebx, [rbp+0E0h+arg_30]
0x100468041  mov     rcx, [rdi+18h]
0x100468045  mov     rax, [rdi+8]
0x100468049  mov     rsi, [rdi+10h]
0x10046804d  sub     rsi, rcx
0x100468050  lea     r14, [rax+rcx*2]
0x100468054  cmp     ebx, 0FFFFFFFFh
0x100468057  jz      short loc_100468071
0x100468059  call    cs:__imp_GetTickCount
0x10046805f  mov     ecx, eax
0x100468061  sub     eax, r15d
0x100468064  cmp     eax, ebx
0x100468066  jnb     loc_100468104
0x10046806c  sub     ebx, eax
0x10046806e  mov     r15d, ecx
0x100468071  lea     r9, [rsp+1E0h+var_194]; int *
0x100468076  mov     dword ptr [rsp+1E0h+phkResult], ebx; int
0x10046807a  mov     r8d, esi; int
0x10046807d  mov     rdx, r14; unsigned __int16 *
0x100468080  mov     rcx, r13; this
0x100468083  call    SNIServerEnumReadEx
0x100468088  movsxd  rcx, eax
0x10046808b  xor     esi, esi
0x10046808d  add     [rdi+18h], rcx
0x100468091  cmp     [rsp+1E0h+var_194], esi
0x100468095  jz      short loc_100468104
0x100468097  mov     r8, [rdi+10h]
0x10046809b  cmp     r8, 72326h
0x1004680a2  jnb     short loc_100468104
0x1004680a4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004680ab  lea     r8, ds:0FBF4h[r8*2]
0x1004680b3  mov     rdx, [rdi+8]
0x1004680b7  mov     rax, [rcx]
0x1004680ba  mov     rax, [rax+20h]
0x1004680be  call    cs:__guard_dispatch_icall_fptr
0x1004680c4  test    rax, rax
0x1004680c7  jz      short loc_1004680DA
0x1004680c9  add     qword ptr [rdi+10h], 7DFAh
0x1004680d1  mov     [rdi+8], rax
0x1004680d5  jmp     loc_100468041
0x1004680da  test    byte ptr cs:_bidGblFlags, 2
0x1004680e1  jz      short loc_1004680FA
0x1004680e3  mov     edx, 29009h
0x1004680e8  xor     ecx, ecx
0x1004680ea  mov     r8d, 8007000Eh
0x1004680f0  call    _bidTraceHR
0x1004680f5  jmp     loc_1004682BB
0x1004680fa  mov     ebx, 8007000Eh
0x1004680ff  jmp     loc_1004682BD
0x100468104  mov     r15, [rbp+0E0h+arg_28]
0x10046810b  xor     ebx, ebx
0x10046810d  test    r15, r15
0x100468110  jz      loc_10046819C
0x100468116  lea     r9, [rdi+28h]
0x10046811a  mov     r10d, 81h
0x100468120  mov     r8, r15
0x100468123  mov     edx, r10d
0x100468126  mov     rcx, r9
0x100468129  sub     r8, r9
0x10046812c  lea     rax, [rdx+7FFFFF7Dh]
0x100468133  test    rax, rax
0x100468136  jz      short loc_10046814F
0x100468138  movzx   eax, word ptr [r8+rcx]
0x10046813d  test    ax, ax
0x100468140  jz      short loc_10046814F
0x100468142  mov     [rcx], ax
0x100468145  add     rcx, 2
0x100468149  sub     rdx, 1
0x10046814d  jnz     short loc_10046812C
0x10046814f  test    rdx, rdx
0x100468152  lea     rax, [rcx-2]
0x100468156  cmovnz  rax, rcx
0x10046815a  or      r12, 0FFFFFFFFFFFFFFFFh
0x10046815e  mov     [rax], bx
0x100468161  inc     r12
0x100468164  cmp     [r9+r12*2], bx
0x100468169  jnz     short loc_100468161
0x10046816b  lea     rdx, [rsp+1E0h+nSize]; nSize
0x100468170  mov     [rsp+1E0h+nSize], r10d
0x100468175  lea     rcx, [rbp+0E0h+Buffer]; lpBuffer
0x100468179  call    cs:__imp_GetComputerNameW
0x10046817f  test    eax, eax
0x100468181  jnz     short loc_10046819F
0x100468183  call    cs:__imp_GetLastError
0x100468189  movzx   ebx, ax
0x10046818c  or      ebx, 80070000h
0x100468192  test    eax, eax
0x100468194  cmovle  ebx, eax
0x100468197  jmp     loc_1004682BD
0x10046819c  mov     r12, rbx
0x10046819f  mov     r14, [rdi+8]
0x1004681a3  cmp     [rdi+18h], rbx
0x1004681a7  jbe     loc_1004682B3
0x1004681ad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1004681b1  inc     rsi
0x1004681b4  cmp     [r14+rsi*2], bx
0x1004681b9  jnz     short loc_1004681B1
0x1004681bb  mov     rcx, [rdi]; this
0x1004681be  lea     r8, [rsp+1E0h+var_190]; unsigned __int64 *
0x1004681c3  lea     rdx, [rsp+1E0h+Source]; Source
0x1004681c8  mov     [rsp+1E0h+var_190], rbx
0x1004681cd  mov     [rsp+1E0h+Source], r14
0x1004681d2  mov     [rsp+1E0h+var_180], rsi
0x1004681d7  call    ?InsertIntoExtBuffer@CExtVarBuffer@@QEAAJPEAXAEA_K@Z; CExtVarBuffer::InsertIntoExtBuffer(void *,unsigned __int64 &)
0x1004681dc  xor     ecx, ecx
0x1004681de  mov     ebx, eax
0x1004681e0  test    eax, eax
0x1004681e2  js      loc_1004682FF
0x1004681e8  xor     ebx, ebx
0x1004681ea  test    r15, r15
0x1004681ed  jz      loc_100468291
0x1004681f3  mov     r8d, [rsp+1E0h+nSize]; MaxCount
0x1004681f8  cmp     rsi, r8
0x1004681fb  jb      loc_100468291
0x100468201  lea     rdx, [rbp+0E0h+Buffer]; String2
0x100468205  mov     rcx, r14; String1
0x100468208  call    cs:__imp__wcsnicmp
0x10046820e  test    eax, eax
0x100468210  jnz     short loc_100468291
0x100468212  mov     eax, [rsp+1E0h+nSize]
0x100468216  lea     rcx, [r14+rax*2]
0x10046821a  cmp     [rcx], bx
0x10046821d  jz      short loc_100468225
0x10046821f  cmp     word ptr [rcx], 3Bh ; ';'
0x100468223  jnz     short loc_100468291
0x100468225  cmp     word ptr [rcx], 3Bh ; ';'
0x100468229  lea     rax, [rdi+28h]
0x10046822d  jnz     short loc_10046826D
0x10046822f  mov     [rsp+1E0h+phkResult], rcx
0x100468234  lea     rbx, [rdi+12Ah]
0x10046823b  mov     rcx, rbx; unsigned __int16 *
0x10046823e  lea     r8, aSS_4; "%s%s"
0x100468245  mov     r9, rax
0x100468248  mov     edx, 101h; unsigned __int64
0x10046824d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100468252  or      rax, 0FFFFFFFFFFFFFFFFh
0x100468256  mov     [rsp+1E0h+Source], rbx
0x10046825b  xor     ecx, ecx
0x10046825d  inc     rax
0x100468260  cmp     [rbx+rax*2], cx
0x100468264  jnz     short loc_10046825D
0x100468266  mov     [rsp+1E0h+var_180], rax
0x10046826b  jmp     short loc_100468277
0x10046826d  mov     [rsp+1E0h+Source], rax
0x100468272  mov     [rsp+1E0h+var_180], r12
0x100468277  mov     rcx, [rdi]; this
0x10046827a  lea     r8, [rsp+1E0h+var_190]; unsigned __int64 *
0x10046827f  lea     rdx, [rsp+1E0h+Source]; Source
0x100468284  call    ?InsertIntoExtBuffer@CExtVarBuffer@@QEAAJPEAXAEA_K@Z; CExtVarBuffer::InsertIntoExtBuffer(void *,unsigned __int64 &)
0x100468289  mov     ebx, eax
0x10046828b  test    eax, eax
0x10046828d  js      short loc_1004682EA
0x10046828f  xor     ebx, ebx
0x100468291  mov     rax, [rsp+1E0h+var_170]
0x100468296  lea     r14, [r14+rsi*2]
0x10046829a  inc     rax
0x10046829d  add     r14, 2
0x1004682a1  add     rax, rsi
0x1004682a4  mov     [rsp+1E0h+var_170], rax
0x1004682a9  cmp     rax, [rdi+18h]
0x1004682ad  jb      loc_1004681AD
0x1004682b3  mov     rcx, rdi; this
0x1004682b6  call    ?SortEnumServers@CServerEnum@@AEAAJXZ; CServerEnum::SortEnumServers(void)
0x1004682bb  mov     ebx, eax
0x1004682bd  mov     rcx, r13; this
0x1004682c0  call    SNIServerEnumClose
0x1004682c5  mov     eax, ebx
0x1004682c7  mov     rcx, [rbp+0E0h+var_50]
0x1004682ce  xor     rcx, rsp; StackCookie
0x1004682d1  call    __security_check_cookie
0x1004682d6  add     rsp, 1A8h
0x1004682dd  pop     r15
0x1004682df  pop     r14
0x1004682e1  pop     r13
0x1004682e3  pop     r12
0x1004682e5  pop     rdi
0x1004682e6  pop     rsi
0x1004682e7  pop     rbx
0x1004682e8  pop     rbp
0x1004682e9  retn
0x1004682ea  test    byte ptr cs:_bidGblFlags, 2
0x1004682f1  jz      short loc_1004682BD
0x1004682f3  mov     r8d, ebx
0x1004682f6  mov     edx, 3C809h
0x1004682fb  xor     ecx, ecx
0x1004682fd  jmp     short loc_100468310
0x1004682ff  test    byte ptr cs:_bidGblFlags, 2
0x100468306  jz      short loc_1004682BD
0x100468308  mov     r8d, eax
0x10046830b  mov     edx, 34009h
0x100468310  lfence
0x100468313  call    _bidTraceHR
0x100468318  jmp     short loc_1004682BD
```
