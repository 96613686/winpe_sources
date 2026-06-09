# CPrivacIEDatabase::_AddConfirmedTracker(char const *)

- ea: `0x1810a46b8`
- end: `0x1810a48bd`
- name: `?_AddConfirmedTracker@CPrivacIEDatabase@@AEAAJPEBD@Z`
- size: `517`
- prototype: `__int64 __fastcall(CPrivacIEDatabase *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1810a34b0`

## callees

- `0x18005e684`
- `0x18070fa60`
- `0x1810a46b8`
- `0x1810a4d24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1810a4725`
- `KERNEL32!GetLastError` at `0x1810a479c`
- `KERNEL32!GetLastError` at `0x1810a484c`
- `KERNEL32!GetLastError` at `0x1810a4725`
- `KERNEL32!GetLastError` at `0x1810a479c`
- `KERNEL32!GetLastError` at `0x1810a484c`
- `KERNEL32!LeaveCriticalSection` at `0x1810a489a`
- `KERNEL32!LeaveCriticalSection` at `0x1810a489a`
- `KERNEL32!EnterCriticalSection` at `0x1810a46f8`
- `KERNEL32!EnterCriticalSection` at `0x1810a46f8`
- `WININET!CommitUrlCacheEntryA` at `0x1810a483c`
- `WININET!CommitUrlCacheEntryA` at `0x1810a483c`
- `WININET!DeleteUrlCacheEntryA` at `0x1810a477f`
- `WININET!DeleteUrlCacheEntryA` at `0x1810a477f`
- `WININET!GetUrlCacheEntryInfoA` at `0x1810a470e`
- `WININET!GetUrlCacheEntryInfoA` at `0x1810a4751`
- `WININET!GetUrlCacheEntryInfoA` at `0x1810a470e`
- `WININET!GetUrlCacheEntryInfoA` at `0x1810a4751`

## pseudocode

```c
__int64 __fastcall CPrivacIEDatabase::_AddConfirmedTracker(CPrivacIEDatabase *this, const char *a2)
{
  signed int updated; // ebx
  struct _sConfirmedTrackers *v4; // r14
  struct _INTERNET_CACHE_ENTRY_INFOA *v5; // rax
  struct _INTERNET_CACHE_ENTRY_INFOA *v6; // rdi
  CPrivacIEDatabase *v7; // rcx
  signed int LastError; // eax
  void *v9; // r8
  LPBYTE v10; // r14
  const CHAR *v11; // rcx
  signed int v12; // eax
  void *v13; // rdx
  DWORD cbCacheEntryInfo; // [rsp+50h] [rbp-20h] BYREF
  DWORD cchHeaderInfo; // [rsp+54h] [rbp-1Ch] BYREF
  FILETIME LastModifiedTime; // [rsp+58h] [rbp-18h] BYREF
  LPBYTE lpHeaderInfo; // [rsp+60h] [rbp-10h] BYREF

  updated = 0;
  LastModifiedTime.dwLowDateTime = 0;
  cchHeaderInfo = 0;
  cbCacheEntryInfo = 0;
  lpHeaderInfo = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( GetUrlCacheEntryInfoA(*((LPCSTR *)this + 13), 0, &cbCacheEntryInfo) )
    goto LABEL_24;
  v4 = 0;
  if ( GetLastError() == 122 )
  {
    v5 = (struct _INTERNET_CACHE_ENTRY_INFOA *)operator new(cbCacheEntryInfo);
    v6 = v5;
    if ( !v5 )
    {
      updated = -2147024882;
      goto LABEL_24;
    }
    if ( GetUrlCacheEntryInfoA(*((LPCSTR *)this + 13), v5, &cbCacheEntryInfo) )
    {
      if ( v6->dwHeaderInfoSize > 0x14 && (v4 = (struct _sConfirmedTrackers *)v6->lpHeaderInfo, *(_DWORD *)v4 == 65521) )
      {
        cchHeaderInfo = v6->dwHeaderInfoSize;
      }
      else
      {
        DeleteUrlCacheEntryA(*((LPCSTR *)this + 13));
        v4 = 0;
      }
    }
    goto LABEL_14;
  }
  v6 = 0;
  LastError = GetLastError();
  updated = LastError;
  if ( LastError > 0 )
    updated = (unsigned __int16)LastError | 0x80070000;
  if ( updated >= 0 || updated == -2147024894 )
  {
LABEL_14:
    updated = CPrivacIEDatabase::_UpdateConfirmedTracker(
                v7,
                a2,
                v4,
                (struct _sConfirmedTrackers **)&lpHeaderInfo,
                &cchHeaderInfo,
                (int *)&LastModifiedTime);
    if ( updated >= 0 && LastModifiedTime.dwLowDateTime )
    {
      v10 = lpHeaderInfo;
      v11 = (const CHAR *)*((_QWORD *)this + 13);
      LastModifiedTime = 0;
      if ( CommitUrlCacheEntryA(v11, 0, 0, 0, 0x20004u, lpHeaderInfo, cchHeaderInfo, 0, 0) )
      {
        v13 = (void *)*((_QWORD *)this + 15);
        if ( v13 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v13, v9);
        *((_QWORD *)this + 15) = v10;
      }
      else
      {
        v12 = GetLastError();
        updated = v12;
        if ( v12 > 0 )
          updated = (unsigned __int16)v12 | 0x80070000;
      }
    }
    if ( v6 )
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v6, v9);
  }
LABEL_24:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1810a46b8  mov     [rsp-28h+arg_10], rbx
0x1810a46bd  mov     [rsp-28h+arg_8], rdx
0x1810a46c2  mov     [rsp-28h+arg_0], rcx
0x1810a46c7  push    rbp
0x1810a46c8  push    rsi
0x1810a46c9  push    rdi
0x1810a46ca  push    r14
0x1810a46cc  push    r15
0x1810a46ce  mov     rbp, rsp
0x1810a46d1  sub     rsp, 70h
0x1810a46d5  mov     rsi, [rbp+arg_0]
0x1810a46d9  xor     ebx, ebx
0x1810a46db  mov     [rbp+LastModifiedTime.dwLowDateTime], 0
0x1810a46e2  mov     [rbp+var_1C], 0
0x1810a46e9  mov     [rbp+cbCacheEntryInfo], 0
0x1810a46f0  lea     rcx, [rsi+18h]; lpCriticalSection
0x1810a46f4  mov     [rbp+var_10], rbx
0x1810a46f8  call    cs:__imp_EnterCriticalSection
0x1810a46ff  nop     dword ptr [rax+rax+00h]
0x1810a4704  mov     rcx, [rsi+68h]; lpszUrlName
0x1810a4708  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1810a470c  xor     edx, edx; lpCacheEntryInfo
0x1810a470e  call    cs:__imp_GetUrlCacheEntryInfoA
0x1810a4715  nop     dword ptr [rax+rax+00h]
0x1810a471a  test    eax, eax
0x1810a471c  jnz     loc_1810A4896
0x1810a4722  xor     r14d, r14d
0x1810a4725  call    cs:__imp_GetLastError
0x1810a472c  nop     dword ptr [rax+rax+00h]
0x1810a4731  cmp     eax, 7Ah ; 'z'
0x1810a4734  jnz     short loc_1810A479A
0x1810a4736  mov     ecx, [rbp+cbCacheEntryInfo]
0x1810a4739  call    ??2@YAPEAX_KW4PrivacyLibraryAllocatorCategory@@@Z; operator new(unsigned __int64,PrivacyLibraryAllocatorCategory)
0x1810a473e  mov     rdi, rax
0x1810a4741  test    rax, rax
0x1810a4744  jz      short loc_1810A4790
0x1810a4746  mov     rcx, [rsi+68h]; lpszUrlName
0x1810a474a  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1810a474e  mov     rdx, rax; lpCacheEntryInfo
0x1810a4751  call    cs:__imp_GetUrlCacheEntryInfoA
0x1810a4758  nop     dword ptr [rax+rax+00h]
0x1810a475d  test    eax, eax
0x1810a475f  jz      short loc_1810A47C7
0x1810a4761  mov     eax, [rdi+58h]
0x1810a4764  cmp     eax, 14h
0x1810a4767  jbe     short loc_1810A477B
0x1810a4769  mov     r14, [rdi+50h]
0x1810a476d  cmp     dword ptr [r14], 0FFF1h
0x1810a4774  jnz     short loc_1810A477B
0x1810a4776  mov     [rbp+var_1C], eax
0x1810a4779  jmp     short loc_1810A47C7
0x1810a477b  mov     rcx, [rsi+68h]; lpszUrlName
0x1810a477f  call    cs:__imp_DeleteUrlCacheEntryA
0x1810a4786  nop     dword ptr [rax+rax+00h]
0x1810a478b  xor     r14d, r14d
0x1810a478e  jmp     short loc_1810A47C7
0x1810a4790  mov     ebx, 8007000Eh
0x1810a4795  jmp     loc_1810A4896
0x1810a479a  xor     edi, edi
0x1810a479c  call    cs:__imp_GetLastError
0x1810a47a3  nop     dword ptr [rax+rax+00h]
0x1810a47a8  mov     ebx, eax
0x1810a47aa  test    eax, eax
0x1810a47ac  jle     short loc_1810A47B7
0x1810a47ae  movzx   ebx, ax
0x1810a47b1  or      ebx, 80070000h
0x1810a47b7  test    ebx, ebx
0x1810a47b9  jns     short loc_1810A47C7
0x1810a47bb  cmp     ebx, 80070002h
0x1810a47c1  jnz     loc_1810A4896
0x1810a47c7  mov     rdx, [rbp+arg_8]; char *
0x1810a47cb  lea     rax, [rbp+LastModifiedTime]
0x1810a47cf  mov     [rsp+70h+lpHeaderInfo], rax; int *
0x1810a47d4  lea     r9, [rbp+var_10]; struct _sConfirmedTrackers **
0x1810a47d8  lea     rax, [rbp+var_1C]
0x1810a47dc  mov     r8, r14; struct _sConfirmedTrackers *
0x1810a47df  mov     qword ptr [rsp+70h+CacheEntryType], rax; unsigned int *
0x1810a47e4  call    ?_UpdateConfirmedTracker@CPrivacIEDatabase@@AEAAJPEBDPEAU_sConfirmedTrackers@@PEAPEAU2@PEAKPEAH@Z; CPrivacIEDatabase::_UpdateConfirmedTracker(char const *,_sConfirmedTrackers *,_sConfirmedTrackers * *,ulong *,int *)
0x1810a47e9  mov     ebx, eax
0x1810a47eb  test    eax, eax
0x1810a47ed  js      loc_1810A4882
0x1810a47f3  cmp     [rbp+LastModifiedTime.dwLowDateTime], 0
0x1810a47f7  jz      loc_1810A4882
0x1810a47fd  mov     ecx, [rbp+var_1C]
0x1810a4800  xor     edx, edx; lpszLocalFileName
0x1810a4802  mov     r14, [rbp+var_10]
0x1810a4806  mov     [rsp+70h+lpszOriginalUrl], 0; lpszOriginalUrl
0x1810a480f  mov     [rsp+70h+lpszFileExtension], 0; lpszFileExtension
0x1810a4818  mov     [rsp+70h+cchHeaderInfo], ecx; cchHeaderInfo
0x1810a481c  mov     rcx, [rsi+68h]; lpszUrlName
0x1810a4820  mov     qword ptr [rbp+LastModifiedTime.dwLowDateTime], 0
0x1810a4828  mov     r8, qword ptr [rbp+LastModifiedTime.dwLowDateTime]; ExpireTime
0x1810a482c  mov     [rsp+70h+lpHeaderInfo], r14; lpHeaderInfo
0x1810a4831  mov     r9, r8; LastModifiedTime
0x1810a4834  mov     [rsp+70h+CacheEntryType], 20004h; CacheEntryType
0x1810a483c  call    cs:__imp_CommitUrlCacheEntryA
0x1810a4843  nop     dword ptr [rax+rax+00h]
0x1810a4848  test    eax, eax
0x1810a484a  jnz     short loc_1810A4869
0x1810a484c  call    cs:__imp_GetLastError
0x1810a4853  nop     dword ptr [rax+rax+00h]
0x1810a4858  mov     ebx, eax
0x1810a485a  test    eax, eax
0x1810a485c  jle     short loc_1810A4882
0x1810a485e  movzx   ebx, ax
0x1810a4861  or      ebx, 80070000h
0x1810a4867  jmp     short loc_1810A4882
0x1810a4869  mov     rdx, [rsi+78h]; void *
0x1810a486d  test    rdx, rdx
0x1810a4870  jz      short loc_1810A487E
0x1810a4872  mov     rcx, cs:g_hProcessHeap; this
0x1810a4879  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1810a487e  mov     [rsi+78h], r14
0x1810a4882  test    rdi, rdi
0x1810a4885  jz      short loc_1810A4896
0x1810a4887  mov     rcx, cs:g_hProcessHeap; this
0x1810a488e  mov     rdx, rdi; void *
0x1810a4891  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1810a4896  lea     rcx, [rsi+18h]; lpCriticalSection
0x1810a489a  call    cs:__imp_LeaveCriticalSection
0x1810a48a1  nop     dword ptr [rax+rax+00h]
0x1810a48a6  mov     eax, ebx
0x1810a48a8  mov     rbx, [rsp+70h+arg_10]
0x1810a48b0  add     rsp, 70h
0x1810a48b4  pop     r15
0x1810a48b6  pop     r14
0x1810a48b8  pop     rdi
0x1810a48b9  pop     rsi
0x1810a48ba  pop     rbp
0x1810a48bb  retn
```
