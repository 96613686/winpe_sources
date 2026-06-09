# CHistFolder::_LoadIntervalCache(void)

- ea: `0x180006140`
- end: `0x180006795`
- name: `?_LoadIntervalCache@CHistFolder@@IEAAJXZ`
- size: `1621`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004dc0`
- `0x180005c60`
- `0x18000679c`
- `0x180006e10`
- `0x1800072f0`

## callees

- `0x180006140`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1800065e9`
- `KERNEL32!CompareFileTime` at `0x180006646`
- `KERNEL32!CompareFileTime` at `0x180006715`
- `KERNEL32!CompareFileTime` at `0x1800065e9`
- `KERNEL32!CompareFileTime` at `0x180006646`
- `KERNEL32!CompareFileTime` at `0x180006715`
- `KERNEL32!lstrcmpiA` at `0x1800062a2`
- `KERNEL32!lstrcmpiA` at `0x1800062a2`
- `KERNEL32!SystemTimeToFileTime` at `0x1800061bc`
- `KERNEL32!SystemTimeToFileTime` at `0x18000647f`
- `KERNEL32!SystemTimeToFileTime` at `0x1800065d4`
- `KERNEL32!SystemTimeToFileTime` at `0x1800061bc`
- `KERNEL32!SystemTimeToFileTime` at `0x18000647f`
- `KERNEL32!SystemTimeToFileTime` at `0x1800065d4`
- `KERNEL32!LocalReAlloc` at `0x18000667b`
- `KERNEL32!LocalReAlloc` at `0x18000667b`
- `KERNEL32!GetLocalTime` at `0x1800061a5`
- `KERNEL32!GetLocalTime` at `0x1800061a5`
- `KERNEL32!LocalAlloc` at `0x180006264`
- `KERNEL32!LocalAlloc` at `0x180006264`
- `KERNEL32!LocalFree` at `0x18000677c`
- `KERNEL32!LocalFree` at `0x18000678a`
- `KERNEL32!LocalFree` at `0x18000677c`
- `KERNEL32!LocalFree` at `0x18000678a`
- `KERNEL32!GetLastError` at `0x18000672b`
- `KERNEL32!GetLastError` at `0x18000672b`
- `KERNEL32!LeaveCriticalSection` at `0x180006520`
- `KERNEL32!LeaveCriticalSection` at `0x180006520`
- `KERNEL32!EnterCriticalSection` at `0x180006502`
- `KERNEL32!EnterCriticalSection` at `0x180006502`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180006383`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180006383`
- `WININET!FindNextUrlCacheContainerA` at `0x180006314`
- `WININET!FindNextUrlCacheContainerA` at `0x180006314`
- `WININET!FindFirstUrlCacheContainerA` at `0x180006235`
- `WININET!FindFirstUrlCacheContainerA` at `0x180006235`
- `WININET!FindCloseUrlCache` at `0x18000649b`
- `WININET!FindCloseUrlCache` at `0x18000649b`

## pseudocode

```c
signed int __fastcall CHistFolder::_LoadIntervalCache(DWORD *this)
{
  unsigned int v2; // r14d
  int v3; // ebx
  DWORD v4; // eax
  DWORD v5; // r9d
  FILETIME *v6; // r13
  HANDLE FirstUrlCacheContainerA; // r15
  FILETIME *v8; // rdi
  char *v9; // rsi
  unsigned int v10; // r12d
  CHAR v11; // bl
  __int64 v12; // rax
  __int64 v13; // rax
  BOOL NextUrlCacheContainerA; // eax
  __int16 v15; // dx
  __int64 v16; // rax
  char *v17; // rbx
  char *v18; // r8
  LPSTR lpszName; // r8
  __int64 v20; // rax
  int j; // edx
  unsigned int v23; // ecx
  int v24; // r12d
  signed int result; // eax
  CHistFolder *v26; // rbx
  void *v27; // rcx
  __int64 v28; // rcx
  __int16 v29; // ax
  char *v30; // rax
  int i; // r8d
  DWORD cbContainerInfo; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pdwModified; // [rsp+24h] [rbp-DCh] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-D8h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-D0h] BYREF
  CHistFolder *v36; // [rsp+38h] [rbp-C8h]
  _INTERNET_CACHE_CONTAINER_INFOA ContainerInfo; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+270h] [rbp+170h] BYREF
  int v39; // [rsp+280h] [rbp+180h]
  __int16 v40; // [rsp+284h] [rbp+184h]
  __int16 v41; // [rsp+288h] [rbp+188h]
  __int16 v42; // [rsp+28Ch] [rbp+18Ch]
  __int16 v43; // [rsp+290h] [rbp+190h]
  __int16 v44; // [rsp+294h] [rbp+194h]
  __int16 v45; // [rsp+298h] [rbp+198h]
  __int16 v46; // [rsp+29Ch] [rbp+19Ch]
  __int16 v47; // [rsp+2A0h] [rbp+1A0h]
  __int16 v48; // [rsp+2A4h] [rbp+1A4h]
  __int16 v49; // [rsp+2A8h] [rbp+1A8h]
  __int16 v50; // [rsp+2ACh] [rbp+1ACh]
  __int16 v51; // [rsp+2B0h] [rbp+1B0h]
  __int16 v52; // [rsp+2B4h] [rbp+1B4h]
  __int16 v53; // [rsp+2B8h] [rbp+1B8h]
  __int16 v54; // [rsp+2BCh] [rbp+1BCh]

  v36 = (CHistFolder *)this;
  v2 = 0;
  pdwModified = 0;
  memset_0(&ContainerInfo, 0, 0x230u);
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  SystemTimeToFileTime(&SystemTime, &FileTime);
  v3 = 1;
  cbContainerInfo = 560;
  v4 = this[18];
  FileTime1 = (FILETIME)(864000000000LL
                       * ((__int64)(FileTime.dwLowDateTime | (HIDWORD(*(unsigned __int64 *)&FileTime) << 32))
                        / 864000000000LL));
  pdwModified = v4;
  if ( !*((_QWORD *)this + 11)
    || (v6 = (FILETIME *)(this + 19), CompareFileTime(&FileTime1, (const FILETIME *)(this + 19))) )
  {
    v5 = 0;
    v6 = (FILETIME *)(this + 19);
  }
  else
  {
    v5 = 1;
  }
  FirstUrlCacheContainerA = FindFirstUrlCacheContainerA(&pdwModified, &ContainerInfo, &cbContainerInfo, v5);
  if ( FirstUrlCacheContainerA )
  {
    v8 = v6;
  }
  else
  {
    result = GetLastError();
    if ( result != 259 )
    {
      if ( result == 12051 )
        return 0;
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v3 = 0;
    v8 = (FILETIME *)(this + 19);
  }
  FileTime = (struct _FILETIME)LocalAlloc(0x40u, 0x294u);
  v9 = (char *)FileTime;
  if ( !*(_QWORD *)&FileTime )
  {
LABEL_49:
    v24 = -2147024882;
    goto LABEL_30;
  }
  v10 = 11;
  while ( v3 )
  {
    v11 = ContainerInfo.lpszName[6];
    ContainerInfo.lpszName[6] = 0;
    if ( !lstrcmpiA(ContainerInfo.lpszName, "MSHist") )
    {
      ContainerInfo.lpszName[6] = v11;
      if ( v2 >= v10 )
      {
        v10 *= 2;
        v30 = (char *)LocalReAlloc(v9, 60LL * v10, 0x42u);
        if ( !v30 )
          goto LABEL_49;
        v9 = v30;
        FileTime = (struct _FILETIME)v30;
      }
      v12 = -1;
      do
        ++v12;
      while ( ContainerInfo.lpszName[v12] );
      if ( (unsigned int)(v12 - 22) <= 2 )
      {
        v13 = -1;
        do
          ++v13;
        while ( ContainerInfo.lpszCachePrefix[v13] );
        if ( v13 == 19 )
        {
          if ( ContainerInfo.lpszName )
          {
            v15 = 0;
            v16 = -1;
            do
              ++v16;
            while ( ContainerInfo.lpszName[v16] );
            if ( (_DWORD)v16 == 24 )
            {
              for ( i = 6; ; ++i )
              {
                if ( i >= 8 )
                  goto LABEL_21;
                if ( (unsigned __int8)(ContainerInfo.lpszName[i] - 48) > 9u )
                  break;
                v15 = ContainerInfo.lpszName[i] + 10 * v15 - 48;
              }
              v18 = &v9[60 * v2 + 58];
              *(_WORD *)v18 = -1;
LABEL_63:
              *(_WORD *)v18 = 0;
              goto LABEL_16;
            }
LABEL_21:
            v17 = &v9[60 * v2];
            *((_WORD *)v17 + 29) = v15;
            v18 = v17 + 58;
            if ( v15 == -1 )
              goto LABEL_63;
          }
          else
          {
            v17 = &v9[60 * v2];
            *((_WORD *)v17 + 29) = 0;
          }
          SHAnsiToUnicode(ContainerInfo.lpszCachePrefix, (PWSTR)v17 + 8, 20);
          lpszName = ContainerInfo.lpszName;
          v20 = -1;
          while ( ContainerInfo.lpszName[++v20] != 0 )
            ;
          for ( j = 0; j < 16; ++j )
          {
            v23 = lpszName[(int)v20 - 16 + j] - 48;
            *(&v39 + j) = v23;
            if ( v23 > 9 )
              goto LABEL_29;
          }
          SystemTime = 0;
          SystemTime.wYear = v42 + 10 * (v41 + 10 * (v40 + 10 * v39));
          SystemTime.wMonth = v44 + 10 * v43;
          SystemTime.wDay = v46 + 10 * v45;
          if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v17) )
            goto LABEL_29;
          SystemTime = 0;
          SystemTime.wYear = v50 + 10 * (v49 + 10 * (v48 + 10 * v47));
          SystemTime.wMonth = v52 + 10 * v51;
          SystemTime.wDay = v54 + 10 * v53;
          if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v17 + 1)
            || CompareFileTime((const FILETIME *)v17, (const FILETIME *)v17 + 1) >= 0 )
          {
            v9 = (char *)FileTime;
LABEL_29:
            v24 = -2147467259;
            goto LABEL_30;
          }
          v28 = *((unsigned int *)v17 + 2);
          *(FILETIME *)&SystemTime.wYear = FileTime1;
          if ( (unsigned int)((__int64)(v28 | ((unsigned __int64)*((unsigned int *)v17 + 3) << 32)) / 864000000000LL)
             - (unsigned int)(*(_QWORD *)v17 / 864000000000LL) != 1
            || CompareFileTime((const FILETIME *)v17, (const FILETIME *)&SystemTime) )
          {
            v29 = 25449;
          }
          else
          {
            v29 = 25444;
          }
          *((_WORD *)v17 + 28) = v29;
          ++v2;
        }
      }
    }
LABEL_16:
    cbContainerInfo = 560;
    NextUrlCacheContainerA = FindNextUrlCacheContainerA(FirstUrlCacheContainerA, &ContainerInfo, &cbContainerInfo);
    v9 = (char *)FileTime;
    v8 = v6;
    v3 = NextUrlCacheContainerA;
  }
  v26 = v36;
  v24 = 0;
  *((_DWORD *)v36 + 18) = pdwModified;
  *v8 = FileTime1;
  EnterCriticalSection(&g_csDll);
  v27 = (void *)*((_QWORD *)v26 + 11);
  if ( v27 )
    LocalFree(v27);
  *((_QWORD *)v26 + 11) = v9;
  LeaveCriticalSection(&g_csDll);
  v9 = 0;
  *((_DWORD *)v26 + 21) = v2;
LABEL_30:
  if ( FirstUrlCacheContainerA )
    FindCloseUrlCache(FirstUrlCacheContainerA);
  if ( v9 )
    LocalFree(v9);
  return v24;
}

```

## disassembly

```asm
0x180006140  mov     [rsp-8+arg_18], rbx
0x180006145  push    rbp
0x180006146  push    rdi
0x180006147  push    r13
0x180006149  push    r14
0x18000614b  push    r15
0x18000614d  lea     rbp, [rsp-1D0h]
0x180006155  sub     rsp, 2D0h
0x18000615c  mov     rax, cs:__security_cookie
0x180006163  xor     rax, rsp
0x180006166  mov     [rbp+1F0h+var_30], rax
0x18000616d  mov     rdi, rcx
0x180006170  mov     [rsp+2F0h+var_2B8], rcx
0x180006175  xor     r14d, r14d
0x180006178  lea     rcx, [rsp+2F0h+ContainerInfo]; void *
0x18000617d  xor     edx, edx; Val
0x18000617f  mov     [rsp+2F0h+pdwModified], r14d
0x180006184  mov     r8d, 230h; Size
0x18000618a  call    memset_0
0x18000618f  xorps   xmm0, xmm0
0x180006192  mov     [rsp+2F0h+cbContainerInfo], r14d
0x180006197  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000619e  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x1800061a5  call    cs:__imp_GetLocalTime
0x1800061ab  lea     rdx, [rsp+2F0h+FileTime]; lpFileTime
0x1800061b0  mov     qword ptr [rsp+2F0h+FileTime.dwLowDateTime], r14
0x1800061b5  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x1800061bc  call    cs:__imp_SystemTimeToFileTime
0x1800061c2  mov     rcx, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x1800061c7  mov     ebx, 1
0x1800061cc  mov     edx, ecx
0x1800061ce  mov     rax, rcx
0x1800061d1  shr     rax, 20h
0x1800061d5  mov     rcx, 0C92A69C000h
0x1800061df  shl     rax, 20h
0x1800061e3  or      rax, rdx
0x1800061e6  mov     [rsp+2F0h+cbContainerInfo], 230h
0x1800061ee  cqo
0x1800061f0  idiv    rcx
0x1800061f3  imul    rax, rcx
0x1800061f7  mov     rdx, rax
0x1800061fa  mov     eax, eax
0x1800061fc  sar     rdx, 20h
0x180006200  mov     edx, edx
0x180006202  shl     rdx, 20h
0x180006206  or      rdx, rax
0x180006209  mov     eax, [rdi+48h]
0x18000620c  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rdx
0x180006211  mov     [rsp+2F0h+pdwModified], eax
0x180006215  cmp     [rdi+58h], r14
0x180006219  jnz     loc_180006709
0x18000621f  mov     r9d, r14d; dwOptions
0x180006222  lea     r13, [rdi+4Ch]
0x180006226  lea     r8, [rsp+2F0h+cbContainerInfo]; lpcbContainerInfo
0x18000622b  lea     rdx, [rsp+2F0h+ContainerInfo]; lpContainerInfo
0x180006230  lea     rcx, [rsp+2F0h+pdwModified]; pdwModified
0x180006235  call    cs:__imp_FindFirstUrlCacheContainerA
0x18000623b  mov     r15, rax
0x18000623e  test    rax, rax
0x180006241  jz      loc_18000672B
0x180006247  mov     rdi, r13
0x18000624a  mov     [rsp+2F0h+arg_8], rsi
0x180006252  mov     edx, 294h; uBytes
0x180006257  mov     ecx, 40h ; '@'; uFlags
0x18000625c  mov     [rsp+2F0h+arg_10], r12
0x180006264  call    cs:__imp_LocalAlloc
0x18000626a  mov     qword ptr [rsp+2F0h+FileTime.dwLowDateTime], rax
0x18000626f  mov     rsi, rax
0x180006272  test    rax, rax
0x180006275  jz      loc_1800066A8
0x18000627b  mov     r12d, 0Bh
0x180006281  test    ebx, ebx
0x180006283  jz      loc_1800064E4
0x180006289  mov     rax, [rsp+2F0h+ContainerInfo.lpszName]
0x18000628e  lea     rdx, String2; "MSHist"
0x180006295  movzx   ebx, byte ptr [rax+6]
0x180006299  mov     byte ptr [rax+6], 0
0x18000629d  mov     rcx, [rsp+2F0h+ContainerInfo.lpszName]; lpString1
0x1800062a2  call    cs:__imp_lstrcmpiA
0x1800062a8  test    eax, eax
0x1800062aa  jnz     short loc_1800062FF
0x1800062ac  mov     rax, [rsp+2F0h+ContainerInfo.lpszName]
0x1800062b1  mov     [rax+6], bl
0x1800062b4  cmp     r14d, r12d
0x1800062b7  jnb     loc_180006668
0x1800062bd  mov     rcx, [rsp+2F0h+ContainerInfo.lpszName]
0x1800062c2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800062c9  nop     dword ptr [rax+00000000h]
0x1800062d0  inc     rax
0x1800062d3  cmp     byte ptr [rcx+rax], 0
0x1800062d7  jnz     short loc_1800062D0
0x1800062d9  add     eax, 0FFFFFFEAh
0x1800062dc  cmp     eax, 2
0x1800062df  ja      short loc_1800062FF
0x1800062e1  mov     rdx, [rsp+2F0h+ContainerInfo.lpszCachePrefix]
0x1800062e6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800062ed  nop     dword ptr [rax]
0x1800062f0  inc     rax
0x1800062f3  cmp     byte ptr [rdx+rax], 0
0x1800062f7  jnz     short loc_1800062F0
0x1800062f9  cmp     rax, 13h
0x1800062fd  jz      short loc_180006329
0x1800062ff  lea     r8, [rsp+2F0h+cbContainerInfo]; lpcbContainerInfo
0x180006304  mov     [rsp+2F0h+cbContainerInfo], 230h
0x18000630c  lea     rdx, [rsp+2F0h+ContainerInfo]; lpContainerInfo
0x180006311  mov     rcx, r15; hEnumHandle
0x180006314  call    cs:__imp_FindNextUrlCacheContainerA
0x18000631a  mov     rsi, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x18000631f  mov     rdi, r13
0x180006322  mov     ebx, eax
0x180006324  jmp     loc_180006281
0x180006329  test    rcx, rcx
0x18000632c  jz      loc_180006693
0x180006332  xor     edx, edx
0x180006334  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000633b  nop     dword ptr [rax+rax+00h]
0x180006340  inc     rax
0x180006343  cmp     [rcx+rax], dl
0x180006346  jnz     short loc_180006340
0x180006348  cmp     eax, 18h
0x18000634b  jz      loc_1800066B3
0x180006351  mov     eax, r14d
0x180006354  imul    rbx, rax, 3Ch ; '<'
0x180006358  mov     eax, 0FFFFh
0x18000635d  add     rbx, rsi
0x180006360  mov     [rbx+3Ah], dx
0x180006364  lea     r8, [rbx+3Ah]
0x180006368  cmp     dx, ax
0x18000636b  jz      loc_180006767
0x180006371  mov     rcx, [rsp+2F0h+ContainerInfo.lpszCachePrefix]; pszSrc
0x180006376  lea     rdx, [rbx+10h]; pwszDst
0x18000637a  mov     r8d, 14h; cwchBuf
0x180006380  mov     rdi, rbx
0x180006383  call    cs:__imp_SHAnsiToUnicode
0x180006389  mov     r8, [rsp+2F0h+ContainerInfo.lpszName]
0x18000638e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006395  nop     word ptr [rax+rax+00000000h]
0x1800063a0  cmp     byte ptr [r8+rax+1], 0
0x1800063a6  lea     rax, [rax+1]
0x1800063aa  jnz     short loc_1800063A0
0x1800063ac  lea     r9d, [rax-10h]
0x1800063b0  xor     edx, edx
0x1800063b2  cmp     edx, 10h
0x1800063b5  jge     short loc_1800063DD
0x1800063b7  lea     eax, [r9+rdx]
0x1800063bb  movsxd  rcx, eax
0x1800063be  movsxd  rax, edx
0x1800063c1  movsx   ecx, byte ptr [rcx+r8]
0x1800063c6  add     ecx, 0FFFFFFD0h
0x1800063c9  mov     [rbp+rax*4+1F0h+var_70], ecx
0x1800063d0  cmp     ecx, 9
0x1800063d3  ja      loc_18000648D
0x1800063d9  inc     edx
0x1800063db  jmp     short loc_1800063B2
0x1800063dd  movzx   ecx, word ptr [rbp+1F0h+var_70]
0x1800063e4  xorps   xmm0, xmm0
0x1800063e7  movzx   eax, cx
0x1800063ea  mov     rdx, rbx; lpFileTime
0x1800063ed  shl     ax, 2
0x1800063f1  add     cx, ax
0x1800063f4  add     cx, cx
0x1800063f7  add     cx, [rbp+1F0h+var_6C]
0x1800063fe  movzx   eax, cx
0x180006401  shl     ax, 2
0x180006405  add     cx, ax
0x180006408  add     cx, cx
0x18000640b  add     cx, [rbp+1F0h+var_68]
0x180006412  movzx   eax, cx
0x180006415  shl     ax, 2
0x180006419  add     cx, ax
0x18000641c  add     cx, cx
0x18000641f  add     cx, [rbp+1F0h+var_64]
0x180006426  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18000642d  mov     [rbp+1F0h+SystemTime.wYear], cx
0x180006434  movzx   ecx, [rbp+1F0h+var_60]
0x18000643b  movzx   eax, cx
0x18000643e  shl     ax, 2
0x180006442  add     cx, ax
0x180006445  add     cx, cx
0x180006448  add     cx, [rbp+1F0h+var_5C]
0x18000644f  mov     [rbp+1F0h+SystemTime.wMonth], cx
0x180006456  movzx   ecx, [rbp+1F0h+var_58]
0x18000645d  movzx   eax, cx
0x180006460  shl     ax, 2
0x180006464  add     cx, ax
0x180006467  add     cx, cx
0x18000646a  add     cx, [rbp+1F0h+var_54]
0x180006471  mov     [rbp+1F0h+SystemTime.wDay], cx
0x180006478  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000647f  call    cs:__imp_SystemTimeToFileTime
0x180006485  test    eax, eax
0x180006487  jnz     loc_180006531
0x18000648d  mov     r12d, 80004005h
0x180006493  test    r15, r15
0x180006496  jz      short loc_1800064A1
0x180006498  mov     rcx, r15; hEnumHandle
0x18000649b  call    cs:__imp_FindCloseUrlCache
0x1800064a1  test    rsi, rsi
0x1800064a4  jnz     loc_180006787
0x1800064aa  mov     rsi, [rsp+2F0h+arg_8]
0x1800064b2  mov     eax, r12d
0x1800064b5  mov     r12, [rsp+2F0h+arg_10]
0x1800064bd  mov     rcx, [rbp+1F0h+var_30]
0x1800064c4  xor     rcx, rsp; StackCookie
0x1800064c7  call    __security_check_cookie
0x1800064cc  mov     rbx, [rsp+2F0h+arg_18]
0x1800064d4  add     rsp, 2D0h
0x1800064db  pop     r15
0x1800064dd  pop     r14
0x1800064df  pop     r13
0x1800064e1  pop     rdi
0x1800064e2  pop     rbp
0x1800064e3  retn
0x1800064e4  mov     eax, [rsp+2F0h+pdwModified]
0x1800064e8  lea     rcx, g_csDll; lpCriticalSection
0x1800064ef  mov     rbx, [rsp+2F0h+var_2B8]
0x1800064f4  xor     r12d, r12d
0x1800064f7  mov     [rbx+48h], eax
0x1800064fa  mov     rax, qword ptr [rsp+2F0h+FileTime1.dwLowDateTime]
0x1800064ff  mov     [rdi], rax
0x180006502  call    cs:__imp_EnterCriticalSection
0x180006508  mov     rcx, [rbx+58h]; hMem
0x18000650c  test    rcx, rcx
0x18000650f  jnz     loc_18000677C
0x180006515  lea     rcx, g_csDll; lpCriticalSection
0x18000651c  mov     [rbx+58h], rsi
0x180006520  call    cs:__imp_LeaveCriticalSection
0x180006526  xor     esi, esi
0x180006528  mov     [rbx+54h], r14d
0x18000652c  jmp     loc_180006493
0x180006531  movzx   ecx, [rbp+1F0h+var_50]
0x180006538  lea     rdx, [rbx+8]; lpFileTime
0x18000653c  movzx   eax, cx
0x18000653f  xorps   xmm0, xmm0
0x180006542  shl     ax, 2
0x180006546  add     cx, ax
0x180006549  add     cx, cx
0x18000654c  add     cx, [rbp+1F0h+var_4C]
0x180006553  movzx   eax, cx
0x180006556  shl     ax, 2
0x18000655a  add     cx, ax
0x18000655d  add     cx, cx
0x180006560  add     cx, [rbp+1F0h+var_48]
0x180006567  movzx   eax, cx
0x18000656a  shl     ax, 2
0x18000656e  add     cx, ax
0x180006571  add     cx, cx
0x180006574  add     cx, [rbp+1F0h+var_44]
0x18000657b  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x180006582  mov     [rbp+1F0h+SystemTime.wYear], cx
0x180006589  movzx   ecx, [rbp+1F0h+var_40]
0x180006590  movzx   eax, cx
0x180006593  shl     ax, 2
0x180006597  add     cx, ax
0x18000659a  add     cx, cx
0x18000659d  add     cx, [rbp+1F0h+var_3C]
0x1800065a4  mov     [rbp+1F0h+SystemTime.wMonth], cx
0x1800065ab  movzx   ecx, [rbp+1F0h+var_38]
0x1800065b2  movzx   eax, cx
0x1800065b5  shl     ax, 2
0x1800065b9  add     cx, ax
0x1800065bc  add     cx, cx
0x1800065bf  add     cx, [rbp+1F0h+var_34]
0x1800065c6  mov     [rbp+1F0h+SystemTime.wDay], cx
0x1800065cd  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x1800065d4  call    cs:__imp_SystemTimeToFileTime
0x1800065da  test    eax, eax
0x1800065dc  jz      loc_180006772
0x1800065e2  lea     rdx, [rbx+8]; lpFileTime2
0x1800065e6  mov     rcx, rbx; lpFileTime1
0x1800065e9  call    cs:__imp_CompareFileTime
0x1800065ef  test    eax, eax
0x1800065f1  jns     loc_180006772
0x1800065f7  mov     rax, qword ptr [rsp+2F0h+FileTime1.dwLowDateTime]
0x1800065fc  mov     r9, 0C92A69C000h
0x180006606  mov     ecx, [rdi+8]
0x180006609  mov     qword ptr [rbp+1F0h+SystemTime.wYear], rax
0x180006610  mov     eax, [rdi+0Ch]
0x180006613  shl     rax, 20h
0x180006617  or      rax, rcx
0x18000661a  mov     ecx, [rdi]
0x18000661c  cqo
0x18000661e  idiv    r9
0x180006621  mov     r8, rax
0x180006624  mov     eax, [rdi+4]
0x180006627  shl     rax, 20h
0x18000662b  or      rax, rcx
0x18000662e  cqo
0x180006630  idiv    r9
0x180006633  sub     r8d, eax
0x180006636  cmp     r8d, 1
0x18000663a  jnz     short loc_180006661
0x18000663c  lea     rdx, [rbp+1F0h+SystemTime]; lpFileTime2
0x180006643  mov     rcx, rbx; lpFileTime1
0x180006646  call    cs:__imp_CompareFileTime
0x18000664c  test    eax, eax
0x18000664e  jnz     short loc_180006661
0x180006650  mov     eax, 6364h
0x180006655  mov     [rbx+38h], ax
0x180006659  inc     r14d
  ... truncated ...
```
