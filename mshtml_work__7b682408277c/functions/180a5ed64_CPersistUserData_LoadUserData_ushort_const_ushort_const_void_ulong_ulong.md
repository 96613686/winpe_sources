# CPersistUserData::LoadUserData(ushort const *,ushort const *,void * *,ulong *,ulong)

- ea: `0x180a5ed64`
- end: `0x180a5f080`
- name: `?LoadUserData@CPersistUserData@@AEAAJPEBG0PEAPEAXPEAKK@Z`
- size: `796`
- prototype: `int(CPersistUserData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, void **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180a60250`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x180a5e08c`
- `0x180a5e4ec`
- `0x180a5ed64`
- `0x180b5c9c4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a5eef9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a5eef9`
- `KERNEL32!CompareFileTime` at `0x180a5ef10`
- `KERNEL32!CompareFileTime` at `0x180a5ef27`
- `KERNEL32!CompareFileTime` at `0x180a5f010`
- `KERNEL32!CompareFileTime` at `0x180a5ef10`
- `KERNEL32!CompareFileTime` at `0x180a5ef27`
- `KERNEL32!CompareFileTime` at `0x180a5f010`
- `KERNEL32!GetLastError` at `0x180a5ee62`
- `KERNEL32!GetLastError` at `0x180a5eecb`
- `KERNEL32!GetLastError` at `0x180a5ef98`
- `KERNEL32!GetLastError` at `0x180a5ee62`
- `KERNEL32!GetLastError` at `0x180a5eecb`
- `KERNEL32!GetLastError` at `0x180a5ef98`
- `WININET!UnlockUrlCacheEntryStream` at `0x180a5f059`
- `WININET!UnlockUrlCacheEntryStream` at `0x180a5f059`
- `WININET!ReadUrlCacheEntryStream` at `0x180a5ef88`
- `WININET!ReadUrlCacheEntryStream` at `0x180a5eff9`
- `WININET!ReadUrlCacheEntryStream` at `0x180a5ef88`
- `WININET!ReadUrlCacheEntryStream` at `0x180a5eff9`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a5ee4a`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a5eeb7`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a5ee4a`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a5eeb7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180a5efc3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180a5efc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180a5ee21`
- `OLEAUT32!__imp_SysFreeString` at `0x180a5ee21`

## pseudocode

```c
__int64 __fastcall CPersistUserData::LoadUserData(
        CPersistUserData *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        BSTR *a4,
        unsigned int *dwLen,
        __int16 Buffer)
{
  unsigned int *v6; // r13
  struct _INTERNET_CACHE_ENTRY_INFOW *v7; // rsi
  WCHAR *v8; // rdi
  BSTR v9; // r15
  HANDLE v10; // r14
  int CacheUrlFromDirPath; // ebx
  __int64 result; // rax
  struct _INTERNET_CACHE_ENTRY_INFOW *v15; // rax
  void *v16; // r8
  void *v17; // r8
  __int64 v18; // r8
  struct _INTERNET_CACHE_ENTRY_INFOW *v19; // rax
  unsigned int dwSizeLow; // eax
  signed int LastError; // eax
  BSTR v22; // rax
  unsigned int v23; // eax
  DWORD cbCacheEntryInfo; // [rsp+30h] [rbp-20h] BYREF
  int v25; // [rsp+34h] [rbp-1Ch]
  LPCWSTR lpszUrlName; // [rsp+38h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-8h] BYREF

  v6 = dwLen;
  v7 = 0;
  v8 = 0;
  FileTime1 = 0;
  v9 = 0;
  lpszUrlName = 0;
  v10 = 0;
  v25 = 0;
  if ( dwLen )
  {
    result = CPersistUserData::EnsureCacheContainer(this);
    if ( (_DWORD)result )
      return result;
    CacheUrlFromDirPath = CPersistUserData::GetCacheUrlFromDirPath(a2, a3, (unsigned __int16 **)&lpszUrlName);
    if ( CacheUrlFromDirPath )
      goto LABEL_7;
    v15 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 1396, a3);
    v7 = v15;
    if ( !v15 )
    {
      CacheUrlFromDirPath = -2147024882;
LABEL_7:
      v8 = (WCHAR *)lpszUrlName;
      goto LABEL_8;
    }
    v8 = (WCHAR *)lpszUrlName;
    cbCacheEntryInfo = 1396;
    v10 = RetrieveUrlCacheEntryStreamW(lpszUrlName, v15, &cbCacheEntryInfo, 0, 0);
    if ( !v10 )
    {
      CacheUrlFromDirPath = GetLastError();
      if ( CacheUrlFromDirPath == 122 )
      {
        MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v7, a3);
        v19 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<0>(
                                                      g_hProcessHeap,
                                                      cbCacheEntryInfo,
                                                      v18);
        v7 = v19;
        if ( !v19 )
        {
LABEL_13:
          CacheUrlFromDirPath = -2147024882;
          goto LABEL_8;
        }
        v10 = RetrieveUrlCacheEntryStreamW(v8, v19, &cbCacheEntryInfo, 0, 0);
        if ( v10 )
          goto LABEL_20;
        CacheUrlFromDirPath = GetLastError();
      }
      if ( CacheUrlFromDirPath )
      {
        if ( CacheUrlFromDirPath <= 0 )
          goto LABEL_8;
        CacheUrlFromDirPath = (unsigned __int16)CacheUrlFromDirPath;
        goto LABEL_19;
      }
    }
LABEL_20:
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &v7->ExpireTime) && CompareFileTime(&SystemTimeAsFileTime, &v7->ExpireTime) > 0 )
    {
      DeleteUrlCacheEntryBugW(v8);
      CacheUrlFromDirPath = -2147024894;
      goto LABEL_8;
    }
    LODWORD(dwLen) = 0;
    dwSizeLow = v7->dwSizeLow;
    LODWORD(dwLen) = dwSizeLow;
    if ( !a4 )
    {
      *v6 = dwSizeLow;
      CacheUrlFromDirPath = -2147024774;
      goto LABEL_8;
    }
    LODWORD(lpszUrlName) = 2;
    Buffer = 0;
    if ( ReadUrlCacheEntryStream(v10, 0, &Buffer, (LPDWORD)&lpszUrlName, 0) )
    {
      LODWORD(dwLen) = (_DWORD)dwLen - 2;
      v22 = SysAllocStringLen(0, (unsigned int)dwLen >> 1);
      v25 = 1;
      v9 = v22;
      if ( !v22 )
        goto LABEL_13;
      if ( ReadUrlCacheEntryStream(v10, 2u, v22, (LPDWORD)&dwLen, 0) )
      {
        if ( CompareFileTime(&FileTime1, &v7->ExpireTime) )
          *((_QWORD *)this + 6) = v7->ExpireTime;
        v23 = (unsigned int)dwLen;
        *a4 = v9;
        v9 = 0;
        CacheUrlFromDirPath = 0;
        *v6 = v23;
        goto LABEL_8;
      }
    }
    LastError = GetLastError();
    CacheUrlFromDirPath = LastError;
    if ( LastError <= 0 )
      goto LABEL_8;
    CacheUrlFromDirPath = (unsigned __int16)LastError;
LABEL_19:
    CacheUrlFromDirPath |= 0x80070000;
    goto LABEL_8;
  }
  CacheUrlFromDirPath = -2147467261;
LABEL_8:
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v8, a3);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v7, v16);
  if ( v25 )
    SysFreeString(v9);
  else
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v9, v17);
  if ( v10 )
    UnlockUrlCacheEntryStream(v10, 0);
  return (unsigned int)CacheUrlFromDirPath;
}

```

## disassembly

```asm
0x180a5ed64  mov     [rsp-38h+arg_8], rbx
0x180a5ed69  mov     [rsp-38h+arg_18], r9
0x180a5ed6e  mov     [rsp-38h+arg_0], rcx
0x180a5ed73  push    rbp
0x180a5ed74  push    rsi
0x180a5ed75  push    rdi
0x180a5ed76  push    r12
0x180a5ed78  push    r13
0x180a5ed7a  push    r14
0x180a5ed7c  push    r15
0x180a5ed7e  mov     rbp, rsp
0x180a5ed81  sub     rsp, 50h
0x180a5ed85  mov     r13, [rbp+dwLen]
0x180a5ed89  xor     esi, esi
0x180a5ed8b  xor     edi, edi
0x180a5ed8d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rsi
0x180a5ed91  xor     r15d, r15d
0x180a5ed94  mov     [rbp+lpszUrlName], rdi
0x180a5ed98  xor     r14d, r14d
0x180a5ed9b  mov     [rbp+var_1C], esi
0x180a5ed9e  mov     rbx, r8
0x180a5eda1  mov     r12, rdx
0x180a5eda4  test    r13, r13
0x180a5eda7  jnz     short loc_180A5EDB0
0x180a5eda9  mov     ebx, 80004003h
0x180a5edae  jmp     short loc_180A5EDF6
0x180a5edb0  call    ?EnsureCacheContainer@CPersistUserData@@AEAAJXZ; CPersistUserData::EnsureCacheContainer(void)
0x180a5edb5  test    eax, eax
0x180a5edb7  jnz     loc_180A5F067
0x180a5edbd  lea     r8, [rbp+lpszUrlName]; unsigned __int16 **
0x180a5edc1  mov     rdx, rbx; Source
0x180a5edc4  mov     rcx, r12; pcszURL
0x180a5edc7  call    ?GetCacheUrlFromDirPath@CPersistUserData@@CAJPEBG0PEAPEAG@Z; CPersistUserData::GetCacheUrlFromDirPath(ushort const *,ushort const *,ushort * *)
0x180a5edcc  mov     ebx, eax
0x180a5edce  test    eax, eax
0x180a5edd0  jnz     short loc_180A5EDF2
0x180a5edd2  mov     rcx, cs:g_hProcessHeap
0x180a5edd9  mov     ebx, 574h
0x180a5edde  mov     edx, ebx
0x180a5ede0  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a5ede5  mov     rsi, rax
0x180a5ede8  test    rax, rax
0x180a5edeb  jnz     short loc_180A5EE32
0x180a5eded  mov     ebx, 8007000Eh
0x180a5edf2  mov     rdi, [rbp+lpszUrlName]
0x180a5edf6  mov     rcx, cs:g_hProcessHeap; this
0x180a5edfd  mov     rdx, rdi; void *
0x180a5ee00  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a5ee05  mov     rcx, cs:g_hProcessHeap; this
0x180a5ee0c  mov     rdx, rsi; void *
0x180a5ee0f  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a5ee14  cmp     [rbp+var_1C], 0
0x180a5ee18  jz      loc_180A5F040
0x180a5ee1e  mov     rcx, r15; bstrString
0x180a5ee21  call    cs:__imp_SysFreeString
0x180a5ee28  nop     dword ptr [rax+rax+00h]
0x180a5ee2d  jmp     loc_180A5F04F
0x180a5ee32  mov     [rsp+50h+dwReserved], edi; dwReserved
0x180a5ee36  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a5ee3a  mov     rdi, [rbp+lpszUrlName]
0x180a5ee3e  xor     r9d, r9d; fRandomRead
0x180a5ee41  mov     rcx, rdi; lpszUrlName
0x180a5ee44  mov     [rbp+cbCacheEntryInfo], ebx
0x180a5ee47  mov     rdx, rsi; lpCacheEntryInfo
0x180a5ee4a  call    cs:__imp_RetrieveUrlCacheEntryStreamW
0x180a5ee51  nop     dword ptr [rax+rax+00h]
0x180a5ee56  mov     r14, rax
0x180a5ee59  test    rax, rax
0x180a5ee5c  jnz     loc_180A5EEF1
0x180a5ee62  call    cs:__imp_GetLastError
0x180a5ee69  nop     dword ptr [rax+rax+00h]
0x180a5ee6e  mov     ebx, eax
0x180a5ee70  cmp     eax, 7Ah ; 'z'
0x180a5ee73  jnz     short loc_180A5EED9
0x180a5ee75  mov     rcx, cs:g_hProcessHeap; this
0x180a5ee7c  mov     rdx, rsi; void *
0x180a5ee7f  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a5ee84  mov     edx, [rbp+cbCacheEntryInfo]
0x180a5ee87  mov     rcx, cs:g_hProcessHeap
0x180a5ee8e  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a5ee93  mov     rsi, rax
0x180a5ee96  test    rax, rax
0x180a5ee99  jnz     short loc_180A5EEA5
0x180a5ee9b  mov     ebx, 8007000Eh
0x180a5eea0  jmp     loc_180A5EDF6
0x180a5eea5  xor     r9d, r9d; fRandomRead
0x180a5eea8  mov     [rsp+50h+dwReserved], r15d; dwReserved
0x180a5eead  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a5eeb1  mov     rdx, rax; lpCacheEntryInfo
0x180a5eeb4  mov     rcx, rdi; lpszUrlName
0x180a5eeb7  call    cs:__imp_RetrieveUrlCacheEntryStreamW
0x180a5eebe  nop     dword ptr [rax+rax+00h]
0x180a5eec3  mov     r14, rax
0x180a5eec6  test    rax, rax
0x180a5eec9  jnz     short loc_180A5EEF1
0x180a5eecb  call    cs:__imp_GetLastError
0x180a5eed2  nop     dword ptr [rax+rax+00h]
0x180a5eed7  mov     ebx, eax
0x180a5eed9  test    ebx, ebx
0x180a5eedb  jz      short loc_180A5EEF1
0x180a5eedd  jle     loc_180A5EDF6
0x180a5eee3  movzx   ebx, bx
0x180a5eee6  or      ebx, 80070000h
0x180a5eeec  jmp     loc_180A5EDF6
0x180a5eef1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180a5eef5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x180a5eef9  call    cs:__imp_GetSystemTimeAsFileTime
0x180a5ef00  nop     dword ptr [rax+rax+00h]
0x180a5ef05  lea     rbx, [rsi+34h]
0x180a5ef09  mov     rdx, rbx; lpFileTime2
0x180a5ef0c  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180a5ef10  call    cs:__imp_CompareFileTime
0x180a5ef17  nop     dword ptr [rax+rax+00h]
0x180a5ef1c  test    eax, eax
0x180a5ef1e  jz      short loc_180A5EF49
0x180a5ef20  mov     rdx, rbx; lpFileTime2
0x180a5ef23  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180a5ef27  call    cs:__imp_CompareFileTime
0x180a5ef2e  nop     dword ptr [rax+rax+00h]
0x180a5ef33  test    eax, eax
0x180a5ef35  jle     short loc_180A5EF49
0x180a5ef37  mov     rcx, rdi; unsigned __int16 *
0x180a5ef3a  call    ?DeleteUrlCacheEntryBugW@@YAHPEBG@Z; DeleteUrlCacheEntryBugW(ushort const *)
0x180a5ef3f  mov     ebx, 80070002h
0x180a5ef44  jmp     loc_180A5EDF6
0x180a5ef49  mov     r12, [rbp+arg_18]
0x180a5ef4d  mov     dword ptr [rbp+dwLen], r15d
0x180a5ef51  mov     eax, [rsi+24h]
0x180a5ef54  mov     dword ptr [rbp+dwLen], eax
0x180a5ef57  test    r12, r12
0x180a5ef5a  jnz     short loc_180A5EF6A
0x180a5ef5c  mov     [r13+0], eax
0x180a5ef60  mov     ebx, 8007007Ah
0x180a5ef65  jmp     loc_180A5EDF6
0x180a5ef6a  xor     eax, eax
0x180a5ef6c  mov     dword ptr [rbp+lpszUrlName], 2
0x180a5ef73  lea     r9, [rbp+lpszUrlName]; lpdwLen
0x180a5ef77  mov     [rbp+Buffer], ax
0x180a5ef7b  lea     r8, [rbp+Buffer]; lpBuffer
0x180a5ef7f  mov     [rsp+50h+dwReserved], eax; Reserved
0x180a5ef83  xor     edx, edx; dwLocation
0x180a5ef85  mov     rcx, r14; hUrlCacheStream
0x180a5ef88  call    cs:__imp_ReadUrlCacheEntryStream
0x180a5ef8f  nop     dword ptr [rax+rax+00h]
0x180a5ef94  test    eax, eax
0x180a5ef96  jnz     short loc_180A5EFB6
0x180a5ef98  call    cs:__imp_GetLastError
0x180a5ef9f  nop     dword ptr [rax+rax+00h]
0x180a5efa4  mov     ebx, eax
0x180a5efa6  test    eax, eax
0x180a5efa8  jle     loc_180A5EDF6
0x180a5efae  movzx   ebx, ax
0x180a5efb1  jmp     loc_180A5EEE6
0x180a5efb6  mov     edx, dword ptr [rbp+dwLen]
0x180a5efb9  xor     ecx, ecx; strIn
0x180a5efbb  add     edx, 0FFFFFFFEh
0x180a5efbe  mov     dword ptr [rbp+dwLen], edx
0x180a5efc1  shr     edx, 1; ui
0x180a5efc3  call    cs:__imp_SysAllocStringLen
0x180a5efca  nop     dword ptr [rax+rax+00h]
0x180a5efcf  mov     [rbp+var_1C], 1
0x180a5efd6  mov     r15, rax
0x180a5efd9  test    rax, rax
0x180a5efdc  jz      loc_180A5EE9B
0x180a5efe2  lea     r9, [rbp+dwLen]; lpdwLen
0x180a5efe6  mov     [rsp+50h+dwReserved], 0; Reserved
0x180a5efee  mov     r8, rax; lpBuffer
0x180a5eff1  mov     edx, 2; dwLocation
0x180a5eff6  mov     rcx, r14; hUrlCacheStream
0x180a5eff9  call    cs:__imp_ReadUrlCacheEntryStream
0x180a5f000  nop     dword ptr [rax+rax+00h]
0x180a5f005  test    eax, eax
0x180a5f007  jz      short loc_180A5EF98
0x180a5f009  mov     rdx, rbx; lpFileTime2
0x180a5f00c  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180a5f010  call    cs:__imp_CompareFileTime
0x180a5f017  nop     dword ptr [rax+rax+00h]
0x180a5f01c  test    eax, eax
0x180a5f01e  jz      short loc_180A5F02B
0x180a5f020  mov     rcx, [rbp+arg_0]
0x180a5f024  mov     rax, [rbx]
0x180a5f027  mov     [rcx+30h], rax
0x180a5f02b  mov     eax, dword ptr [rbp+dwLen]
0x180a5f02e  mov     [r12], r15
0x180a5f032  xor     r15d, r15d
0x180a5f035  xor     ebx, ebx
0x180a5f037  mov     [r13+0], eax
0x180a5f03b  jmp     loc_180A5EDF6
0x180a5f040  mov     rcx, cs:g_hProcessHeap; this
0x180a5f047  mov     rdx, r15; void *
0x180a5f04a  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a5f04f  test    r14, r14
0x180a5f052  jz      short loc_180A5F065
0x180a5f054  xor     edx, edx; Reserved
0x180a5f056  mov     rcx, r14; hUrlCacheStream
0x180a5f059  call    cs:__imp_UnlockUrlCacheEntryStream
0x180a5f060  nop     dword ptr [rax+rax+00h]
0x180a5f065  mov     eax, ebx
0x180a5f067  mov     rbx, [rsp+50h+arg_8]
0x180a5f06f  add     rsp, 50h
0x180a5f073  pop     r15
0x180a5f075  pop     r14
0x180a5f077  pop     r13
0x180a5f079  pop     r12
0x180a5f07b  pop     rdi
0x180a5f07c  pop     rsi
0x180a5f07d  pop     rbp
0x180a5f07e  retn
```
