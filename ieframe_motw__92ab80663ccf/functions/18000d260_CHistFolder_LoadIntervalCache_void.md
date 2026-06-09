# CHistFolder::_LoadIntervalCache(void)

- ea: `0x18000d260`
- end: `0x18000d921`
- name: `?_LoadIntervalCache@CHistFolder@@IEAAJXZ`
- size: `1729`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bdb0`
- `0x18000cd50`
- `0x18000d928`
- `0x18000e020`
- `0x18000e550`

## callees

- `0x18000d260`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000d748`
- `KERNEL32!CompareFileTime` at `0x18000d7ab`
- `KERNEL32!CompareFileTime` at `0x18000d889`
- `KERNEL32!CompareFileTime` at `0x18000d748`
- `KERNEL32!CompareFileTime` at `0x18000d7ab`
- `KERNEL32!CompareFileTime` at `0x18000d889`
- `KERNEL32!lstrcmpiA` at `0x18000d3e1`
- `KERNEL32!lstrcmpiA` at `0x18000d3e1`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d2e2`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d5bf`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d72d`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d2e2`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d5bf`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d72d`
- `KERNEL32!LocalReAlloc` at `0x18000d7e6`
- `KERNEL32!LocalReAlloc` at `0x18000d7e6`
- `KERNEL32!GetLocalTime` at `0x18000d2c5`
- `KERNEL32!GetLocalTime` at `0x18000d2c5`
- `KERNEL32!LocalAlloc` at `0x18000d396`
- `KERNEL32!LocalAlloc` at `0x18000d396`
- `KERNEL32!LocalFree` at `0x18000d8fc`
- `KERNEL32!LocalFree` at `0x18000d910`
- `KERNEL32!LocalFree` at `0x18000d8fc`
- `KERNEL32!LocalFree` at `0x18000d910`
- `KERNEL32!GetLastError` at `0x18000d8a5`
- `KERNEL32!GetLastError` at `0x18000d8a5`
- `KERNEL32!LeaveCriticalSection` at `0x18000d673`
- `KERNEL32!LeaveCriticalSection` at `0x18000d673`
- `KERNEL32!EnterCriticalSection` at `0x18000d64f`
- `KERNEL32!EnterCriticalSection` at `0x18000d64f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000d4c4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000d4c4`
- `WININET!FindNextUrlCacheContainerA` at `0x18000d454`
- `WININET!FindNextUrlCacheContainerA` at `0x18000d454`
- `WININET!FindFirstUrlCacheContainerA` at `0x18000d361`
- `WININET!FindFirstUrlCacheContainerA` at `0x18000d361`
- `WININET!FindCloseUrlCache` at `0x18000d5e1`
- `WININET!FindCloseUrlCache` at `0x18000d5e1`

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
0x18000d260  mov     [rsp-8+arg_18], rbx
0x18000d265  push    rbp
0x18000d266  push    rdi
0x18000d267  push    r13
0x18000d269  push    r14
0x18000d26b  push    r15
0x18000d26d  lea     rbp, [rsp-1D0h]
0x18000d275  sub     rsp, 2D0h
0x18000d27c  mov     rax, cs:__security_cookie
0x18000d283  xor     rax, rsp
0x18000d286  mov     [rbp+1F0h+var_30], rax
0x18000d28d  mov     rdi, rcx
0x18000d290  mov     [rsp+2F0h+var_2B8], rcx
0x18000d295  xor     r14d, r14d
0x18000d298  lea     rcx, [rsp+2F0h+ContainerInfo]; void *
0x18000d29d  xor     edx, edx; Val
0x18000d29f  mov     [rsp+2F0h+pdwModified], r14d
0x18000d2a4  mov     r8d, 230h; Size
0x18000d2aa  call    memset_0
0x18000d2af  xorps   xmm0, xmm0
0x18000d2b2  mov     [rsp+2F0h+cbContainerInfo], r14d
0x18000d2b7  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000d2be  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18000d2c5  call    cs:__imp_GetLocalTime
0x18000d2cc  nop     dword ptr [rax+rax+00h]
0x18000d2d1  lea     rdx, [rsp+2F0h+FileTime]; lpFileTime
0x18000d2d6  mov     qword ptr [rsp+2F0h+FileTime.dwLowDateTime], r14
0x18000d2db  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000d2e2  call    cs:__imp_SystemTimeToFileTime
0x18000d2e9  nop     dword ptr [rax+rax+00h]
0x18000d2ee  mov     rcx, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x18000d2f3  mov     ebx, 1
0x18000d2f8  mov     edx, ecx
0x18000d2fa  mov     rax, rcx
0x18000d2fd  shr     rax, 20h
0x18000d301  mov     rcx, 0C92A69C000h
0x18000d30b  shl     rax, 20h
0x18000d30f  or      rax, rdx
0x18000d312  mov     [rsp+2F0h+cbContainerInfo], 230h
0x18000d31a  cqo
0x18000d31c  idiv    rcx
0x18000d31f  imul    rax, rcx
0x18000d323  mov     rdx, rax
0x18000d326  mov     eax, eax
0x18000d328  sar     rdx, 20h
0x18000d32c  mov     edx, edx
0x18000d32e  shl     rdx, 20h
0x18000d332  or      rdx, rax
0x18000d335  mov     eax, [rdi+48h]
0x18000d338  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rdx
0x18000d33d  mov     [rsp+2F0h+pdwModified], eax
0x18000d341  cmp     [rdi+58h], r14
0x18000d345  jnz     loc_18000D87D
0x18000d34b  mov     r9d, r14d; dwOptions
0x18000d34e  lea     r13, [rdi+4Ch]
0x18000d352  lea     r8, [rsp+2F0h+cbContainerInfo]; lpcbContainerInfo
0x18000d357  lea     rdx, [rsp+2F0h+ContainerInfo]; lpContainerInfo
0x18000d35c  lea     rcx, [rsp+2F0h+pdwModified]; pdwModified
0x18000d361  call    cs:__imp_FindFirstUrlCacheContainerA
0x18000d368  nop     dword ptr [rax+rax+00h]
0x18000d36d  mov     r15, rax
0x18000d370  test    rax, rax
0x18000d373  jz      loc_18000D8A5
0x18000d379  mov     rdi, r13
0x18000d37c  mov     [rsp+2F0h+arg_8], rsi
0x18000d384  mov     edx, 294h; uBytes
0x18000d389  mov     ecx, 40h ; '@'; uFlags
0x18000d38e  mov     [rsp+2F0h+arg_10], r12
0x18000d396  call    cs:__imp_LocalAlloc
0x18000d39d  nop     dword ptr [rax+rax+00h]
0x18000d3a2  mov     qword ptr [rsp+2F0h+FileTime.dwLowDateTime], rax
0x18000d3a7  mov     rsi, rax
0x18000d3aa  test    rax, rax
0x18000d3ad  jz      loc_18000D819
0x18000d3b3  mov     r12d, 0Bh
0x18000d3b9  nop     dword ptr [rax+00000000h]
0x18000d3c0  test    ebx, ebx
0x18000d3c2  jz      loc_18000D631
0x18000d3c8  mov     rax, [rsp+2F0h+ContainerInfo.lpszName]
0x18000d3cd  lea     rdx, aMshist; "MSHist"
0x18000d3d4  movzx   ebx, byte ptr [rax+6]
0x18000d3d8  mov     byte ptr [rax+6], 0
0x18000d3dc  mov     rcx, [rsp+2F0h+ContainerInfo.lpszName]; lpString1
0x18000d3e1  call    cs:__imp_lstrcmpiA
0x18000d3e8  nop     dword ptr [rax+rax+00h]
0x18000d3ed  test    eax, eax
0x18000d3ef  jnz     short loc_18000D43F
0x18000d3f1  mov     rax, [rsp+2F0h+ContainerInfo.lpszName]
0x18000d3f6  mov     [rax+6], bl
0x18000d3f9  cmp     r14d, r12d
0x18000d3fc  jnb     loc_18000D7D3
0x18000d402  mov     rcx, [rsp+2F0h+ContainerInfo.lpszName]
0x18000d407  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d40e  xchg    ax, ax
0x18000d410  inc     rax
0x18000d413  cmp     byte ptr [rcx+rax], 0
0x18000d417  jnz     short loc_18000D410
0x18000d419  add     eax, 0FFFFFFEAh
0x18000d41c  cmp     eax, 2
0x18000d41f  ja      short loc_18000D43F
0x18000d421  mov     rdx, [rsp+2F0h+ContainerInfo.lpszCachePrefix]
0x18000d426  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d42d  nop     dword ptr [rax]
0x18000d430  inc     rax
0x18000d433  cmp     byte ptr [rdx+rax], 0
0x18000d437  jnz     short loc_18000D430
0x18000d439  cmp     rax, 13h
0x18000d43d  jz      short loc_18000D46F
0x18000d43f  lea     r8, [rsp+2F0h+cbContainerInfo]; lpcbContainerInfo
0x18000d444  mov     [rsp+2F0h+cbContainerInfo], 230h
0x18000d44c  lea     rdx, [rsp+2F0h+ContainerInfo]; lpContainerInfo
0x18000d451  mov     rcx, r15; hEnumHandle
0x18000d454  call    cs:__imp_FindNextUrlCacheContainerA
0x18000d45b  nop     dword ptr [rax+rax+00h]
0x18000d460  mov     rsi, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x18000d465  mov     rdi, r13
0x18000d468  mov     ebx, eax
0x18000d46a  jmp     loc_18000D3C0
0x18000d46f  test    rcx, rcx
0x18000d472  jz      loc_18000D804
0x18000d478  xor     edx, edx
0x18000d47a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d481  inc     rax
0x18000d484  cmp     [rcx+rax], dl
0x18000d487  jnz     short loc_18000D481
0x18000d489  cmp     eax, 18h
0x18000d48c  jz      loc_18000D824
0x18000d492  mov     eax, r14d
0x18000d495  imul    rbx, rax, 3Ch ; '<'
0x18000d499  mov     eax, 0FFFFh
0x18000d49e  add     rbx, rsi
0x18000d4a1  mov     [rbx+3Ah], dx
0x18000d4a5  lea     r8, [rbx+3Ah]
0x18000d4a9  cmp     dx, ax
0x18000d4ac  jz      loc_18000D8E7
0x18000d4b2  mov     rcx, [rsp+2F0h+ContainerInfo.lpszCachePrefix]; pszSrc
0x18000d4b7  lea     rdx, [rbx+10h]; pwszDst
0x18000d4bb  mov     r8d, 14h; cwchBuf
0x18000d4c1  mov     rdi, rbx
0x18000d4c4  call    cs:__imp_SHAnsiToUnicode
0x18000d4cb  nop     dword ptr [rax+rax+00h]
0x18000d4d0  mov     r8, [rsp+2F0h+ContainerInfo.lpszName]
0x18000d4d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d4dc  nop     dword ptr [rax+00h]
0x18000d4e0  cmp     byte ptr [r8+rax+1], 0
0x18000d4e6  lea     rax, [rax+1]
0x18000d4ea  jnz     short loc_18000D4E0
0x18000d4ec  lea     r9d, [rax-10h]
0x18000d4f0  xor     edx, edx
0x18000d4f2  cmp     edx, 10h
0x18000d4f5  jge     short loc_18000D51D
0x18000d4f7  lea     eax, [r9+rdx]
0x18000d4fb  movsxd  rcx, eax
0x18000d4fe  movsxd  rax, edx
0x18000d501  movsx   ecx, byte ptr [rcx+r8]
0x18000d506  add     ecx, 0FFFFFFD0h
0x18000d509  mov     [rbp+rax*4+1F0h+var_70], ecx
0x18000d510  cmp     ecx, 9
0x18000d513  ja      loc_18000D5D3
0x18000d519  inc     edx
0x18000d51b  jmp     short loc_18000D4F2
0x18000d51d  movzx   ecx, word ptr [rbp+1F0h+var_70]
0x18000d524  xorps   xmm0, xmm0
0x18000d527  movzx   eax, cx
0x18000d52a  mov     rdx, rbx; lpFileTime
0x18000d52d  shl     ax, 2
0x18000d531  add     cx, ax
0x18000d534  add     cx, cx
0x18000d537  add     cx, [rbp+1F0h+var_6C]
0x18000d53e  movzx   eax, cx
0x18000d541  shl     ax, 2
0x18000d545  add     cx, ax
0x18000d548  add     cx, cx
0x18000d54b  add     cx, [rbp+1F0h+var_68]
0x18000d552  movzx   eax, cx
0x18000d555  shl     ax, 2
0x18000d559  add     cx, ax
0x18000d55c  add     cx, cx
0x18000d55f  add     cx, [rbp+1F0h+var_64]
0x18000d566  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18000d56d  mov     [rbp+1F0h+SystemTime.wYear], cx
0x18000d574  movzx   ecx, [rbp+1F0h+var_60]
0x18000d57b  movzx   eax, cx
0x18000d57e  shl     ax, 2
0x18000d582  add     cx, ax
0x18000d585  add     cx, cx
0x18000d588  add     cx, [rbp+1F0h+var_5C]
0x18000d58f  mov     [rbp+1F0h+SystemTime.wMonth], cx
0x18000d596  movzx   ecx, [rbp+1F0h+var_58]
0x18000d59d  movzx   eax, cx
0x18000d5a0  shl     ax, 2
0x18000d5a4  add     cx, ax
0x18000d5a7  add     cx, cx
0x18000d5aa  add     cx, [rbp+1F0h+var_54]
0x18000d5b1  mov     [rbp+1F0h+SystemTime.wDay], cx
0x18000d5b8  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000d5bf  call    cs:__imp_SystemTimeToFileTime
0x18000d5c6  nop     dword ptr [rax+rax+00h]
0x18000d5cb  test    eax, eax
0x18000d5cd  jnz     loc_18000D68A
0x18000d5d3  mov     r12d, 80004005h
0x18000d5d9  test    r15, r15
0x18000d5dc  jz      short loc_18000D5ED
0x18000d5de  mov     rcx, r15; hEnumHandle
0x18000d5e1  call    cs:__imp_FindCloseUrlCache
0x18000d5e8  nop     dword ptr [rax+rax+00h]
0x18000d5ed  test    rsi, rsi
0x18000d5f0  jnz     loc_18000D90D
0x18000d5f6  mov     rsi, [rsp+2F0h+arg_8]
0x18000d5fe  mov     eax, r12d
0x18000d601  mov     r12, [rsp+2F0h+arg_10]
0x18000d609  mov     rcx, [rbp+1F0h+var_30]
0x18000d610  xor     rcx, rsp; StackCookie
0x18000d613  call    __security_check_cookie
0x18000d618  mov     rbx, [rsp+2F0h+arg_18]
0x18000d620  add     rsp, 2D0h
0x18000d627  pop     r15
0x18000d629  pop     r14
0x18000d62b  pop     r13
0x18000d62d  pop     rdi
0x18000d62e  pop     rbp
0x18000d62f  retn
0x18000d631  mov     eax, [rsp+2F0h+pdwModified]
0x18000d635  lea     rcx, g_csDll; lpCriticalSection
0x18000d63c  mov     rbx, [rsp+2F0h+var_2B8]
0x18000d641  xor     r12d, r12d
0x18000d644  mov     [rbx+48h], eax
0x18000d647  mov     rax, qword ptr [rsp+2F0h+FileTime1.dwLowDateTime]
0x18000d64c  mov     [rdi], rax
0x18000d64f  call    cs:__imp_EnterCriticalSection
0x18000d656  nop     dword ptr [rax+rax+00h]
0x18000d65b  mov     rcx, [rbx+58h]; hMem
0x18000d65f  test    rcx, rcx
0x18000d662  jnz     loc_18000D8FC
0x18000d668  lea     rcx, g_csDll; lpCriticalSection
0x18000d66f  mov     [rbx+58h], rsi
0x18000d673  call    cs:__imp_LeaveCriticalSection
0x18000d67a  nop     dword ptr [rax+rax+00h]
0x18000d67f  xor     esi, esi
0x18000d681  mov     [rbx+54h], r14d
0x18000d685  jmp     loc_18000D5D9
0x18000d68a  movzx   ecx, [rbp+1F0h+var_50]
0x18000d691  lea     rdx, [rbx+8]; lpFileTime
0x18000d695  movzx   eax, cx
0x18000d698  xorps   xmm0, xmm0
0x18000d69b  shl     ax, 2
0x18000d69f  add     cx, ax
0x18000d6a2  add     cx, cx
0x18000d6a5  add     cx, [rbp+1F0h+var_4C]
0x18000d6ac  movzx   eax, cx
0x18000d6af  shl     ax, 2
0x18000d6b3  add     cx, ax
0x18000d6b6  add     cx, cx
0x18000d6b9  add     cx, [rbp+1F0h+var_48]
0x18000d6c0  movzx   eax, cx
0x18000d6c3  shl     ax, 2
0x18000d6c7  add     cx, ax
0x18000d6ca  add     cx, cx
0x18000d6cd  add     cx, [rbp+1F0h+var_44]
0x18000d6d4  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18000d6db  mov     [rbp+1F0h+SystemTime.wYear], cx
0x18000d6e2  movzx   ecx, [rbp+1F0h+var_40]
0x18000d6e9  movzx   eax, cx
0x18000d6ec  shl     ax, 2
0x18000d6f0  add     cx, ax
0x18000d6f3  add     cx, cx
0x18000d6f6  add     cx, [rbp+1F0h+var_3C]
0x18000d6fd  mov     [rbp+1F0h+SystemTime.wMonth], cx
0x18000d704  movzx   ecx, [rbp+1F0h+var_38]
0x18000d70b  movzx   eax, cx
0x18000d70e  shl     ax, 2
0x18000d712  add     cx, ax
0x18000d715  add     cx, cx
0x18000d718  add     cx, [rbp+1F0h+var_34]
0x18000d71f  mov     [rbp+1F0h+SystemTime.wDay], cx
0x18000d726  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000d72d  call    cs:__imp_SystemTimeToFileTime
0x18000d734  nop     dword ptr [rax+rax+00h]
0x18000d739  test    eax, eax
0x18000d73b  jz      loc_18000D8F2
0x18000d741  lea     rdx, [rbx+8]; lpFileTime2
0x18000d745  mov     rcx, rbx; lpFileTime1
0x18000d748  call    cs:__imp_CompareFileTime
0x18000d74f  nop     dword ptr [rax+rax+00h]
0x18000d754  test    eax, eax
0x18000d756  jns     loc_18000D8F2
0x18000d75c  mov     rax, qword ptr [rsp+2F0h+FileTime1.dwLowDateTime]
0x18000d761  mov     r9, 0C92A69C000h
0x18000d76b  mov     ecx, [rdi+8]
0x18000d76e  mov     qword ptr [rbp+1F0h+SystemTime.wYear], rax
0x18000d775  mov     eax, [rdi+0Ch]
0x18000d778  shl     rax, 20h
0x18000d77c  or      rax, rcx
0x18000d77f  mov     ecx, [rdi]
0x18000d781  cqo
0x18000d783  idiv    r9
0x18000d786  mov     r8, rax
0x18000d789  mov     eax, [rdi+4]
0x18000d78c  shl     rax, 20h
0x18000d790  or      rax, rcx
  ... truncated ...
```
