# CREDENTIALS_CACHE::Insert(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001e7e4`
- end: `0x18001ea17`
- name: `?Insert@CREDENTIALS_CACHE@@QEAAJPEBG0000@Z`
- size: `563`
- prototype: `int(CREDENTIALS_CACHE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001bd7c`
- `0x18001d8a0`

## callees

- `0x180002504`
- `0x18001e014`
- `0x18001e14c`
- `0x18001e7e4`
- `0x180047050`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001e93a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001e93a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8a4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8a4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8be`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8be`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001e9cb`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001e9cb`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001e88b`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001e88b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e97d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e97d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9b6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e82d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e901`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e82d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e901`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001e8d9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001e8d9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001e948`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001e948`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e9df`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e9ee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e9df`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e9ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CREDENTIALS_CACHE::Insert(
        CREDENTIALS_CACHE *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  const unsigned __int16 *v10; // rbx
  int CacheKey; // esi
  CREDENTIALS_CACHE_ENTRY *v12; // rdi
  CReaderWriterLock3 *v13; // rbx
  CREDENTIALS_CACHE_ENTRY *v14; // rcx
  unsigned __int16 *v15; // rax
  CREDENTIALS_CACHE_ENTRY *v16; // rcx
  CREDENTIALS_CACHE_ENTRY *v18; // [rsp+20h] [rbp-C9h] BYREF
  wchar_t *v19[7]; // [rsp+30h] [rbp-B9h] BYREF
  unsigned __int16 v20[68]; // [rsp+68h] [rbp-81h] BYREF

  v10 = a6;
  STRU::STRU((STRU *)v19, v20, 0x40u);
  if ( a2 && a4 && a5 && a3 )
  {
    CacheKey = CREDENTIALS_CACHE_KEY::CreateCacheKey(v19, a2, a4, a5);
    if ( CacheKey >= 0 )
    {
      v18 = 0;
      if ( (unsigned int)CLKRHashTable::FindKey(this, v19, &v18) )
      {
        v15 = (unsigned __int16 *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry);
        v12 = (CREDENTIALS_CACHE_ENTRY *)v15;
        v18 = (CREDENTIALS_CACHE_ENTRY *)v15;
        if ( v15 )
        {
          *((_DWORD *)v15 + 5) = 1;
          STRU::STRU((STRU *)(v15 + 12), v15 + 40, 0x40u);
          *((_DWORD *)v12 + 52) = 2;
          *((_DWORD *)v12 + 53) = 0;
          *((_DWORD *)v12 + 54) = 0;
          STRA::STRA((CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 224), (char *)v12 + 280, 0x41u);
          STRU::STRU((char *)v12 + 352);
          *((_DWORD *)v12 + 4) = 1131561794;
          *(_QWORD *)v12 = 0;
          *((_QWORD *)v12 + 1) = 0;
        }
        else
        {
          v12 = 0;
        }
        if ( v12 )
        {
          CacheKey = STRU::Copy((CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 24), v19[4]);
          if ( CacheKey >= 0 )
          {
            CacheKey = CREDENTIALS_CACHE_ENTRY::GenPasswordHash(v16, a3, (CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 224));
            if ( CacheKey >= 0 )
            {
              if ( !a6 )
                v10 = &WideCharStr;
              CacheKey = STRU::Copy((CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 352), v10);
              if ( CacheKey >= 0 )
                CLKRHashTable::InsertRecord(this, v12, 0);
            }
          }
          goto LABEL_20;
        }
        CacheKey = -2147024888;
      }
      else
      {
        v12 = v18;
        v13 = (CREDENTIALS_CACHE_ENTRY *)((char *)v18 + 212);
        CReaderWriterLock3::WriteLock((CREDENTIALS_CACHE_ENTRY *)((char *)v18 + 212));
        CacheKey = CREDENTIALS_CACHE_ENTRY::GenPasswordHash(v14, a3, (CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 224));
        CReaderWriterLock3::WriteUnlock(v13);
        if ( v12 )
LABEL_20:
          CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(v12);
      }
    }
    STRU::~STRU(v19);
    return (unsigned int)CacheKey;
  }
  STRU::~STRU(v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001e7e4  push    rbp
0x18001e7e6  push    rbx
0x18001e7e7  push    rsi
0x18001e7e8  push    rdi
0x18001e7e9  push    r12
0x18001e7eb  push    r14
0x18001e7ed  push    r15
0x18001e7ef  lea     rbp, [rsp-17h]
0x18001e7f4  sub     rsp, 100h
0x18001e7fb  mov     rax, cs:__security_cookie
0x18001e802  xor     rax, rsp
0x18001e805  mov     [rbp+47h+var_40], rax
0x18001e809  mov     rdi, r9
0x18001e80c  mov     r14, r8
0x18001e80f  mov     r12, rdx
0x18001e812  mov     r15, rcx
0x18001e815  mov     rbx, [rbp+47h+arg_28]
0x18001e819  mov     rsi, [rbp+47h+arg_20]
0x18001e81d  mov     r8d, 40h ; '@'
0x18001e823  lea     rdx, [rsp+130h+var_C8]
0x18001e828  lea     rcx, [rsp+130h+var_100]
0x18001e82d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e833  nop
0x18001e834  test    r12, r12
0x18001e837  jz      loc_18001E9E9
0x18001e83d  test    rdi, rdi
0x18001e840  jz      loc_18001E9E9
0x18001e846  test    rsi, rsi
0x18001e849  jz      loc_18001E9E9
0x18001e84f  test    r14, r14
0x18001e852  jz      loc_18001E9E9
0x18001e858  mov     r9, rsi; unsigned __int16 *
0x18001e85b  mov     r8, rdi; unsigned __int16 *
0x18001e85e  mov     rdx, r12; unsigned __int16 *
0x18001e861  lea     rcx, [rsp+130h+var_100]; this
0x18001e866  call    ?CreateCacheKey@CREDENTIALS_CACHE_KEY@@QEAAJPEBG00@Z; CREDENTIALS_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ushort const *)
0x18001e86b  mov     esi, eax
0x18001e86d  test    eax, eax
0x18001e86f  js      loc_18001E9DA
0x18001e875  mov     [rsp+130h+var_110], 0
0x18001e87e  lea     r8, [rsp+130h+var_110]
0x18001e883  lea     rdx, [rsp+130h+var_100]
0x18001e888  mov     rcx, r15
0x18001e88b  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001e891  test    eax, eax
0x18001e893  jnz     short loc_18001E8D2
0x18001e895  mov     rdi, [rsp+130h+var_110]
0x18001e89a  lea     rbx, [rdi+0D4h]
0x18001e8a1  mov     rcx, rbx
0x18001e8a4  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001e8aa  lea     r8, [rdi+0E0h]; struct STRA *
0x18001e8b1  mov     rdx, r14; unsigned __int16 *
0x18001e8b4  call    ?GenPasswordHash@CREDENTIALS_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; CREDENTIALS_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x18001e8b9  mov     esi, eax
0x18001e8bb  mov     rcx, rbx
0x18001e8be  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001e8c4  test    rdi, rdi
0x18001e8c7  jz      loc_18001E9DA
0x18001e8cd  jmp     loc_18001E9D1
0x18001e8d2  mov     rcx, cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x18001e8d9  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001e8df  mov     rdi, rax
0x18001e8e2  mov     [rsp+130h+var_110], rax
0x18001e8e7  test    rax, rax
0x18001e8ea  jz      short loc_18001E966
0x18001e8ec  mov     dword ptr [rax+14h], 1
0x18001e8f3  lea     rcx, [rax+18h]
0x18001e8f7  lea     rdx, [rcx+38h]
0x18001e8fb  mov     r8d, 40h ; '@'
0x18001e901  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e907  nop
0x18001e908  mov     dword ptr [rdi+0D0h], 2
0x18001e912  mov     dword ptr [rdi+0D4h], 0
0x18001e91c  mov     dword ptr [rdi+0D8h], 0
0x18001e926  lea     rdx, [rdi+118h]
0x18001e92d  lea     rcx, [rdi+0E0h]
0x18001e934  mov     r8d, 41h ; 'A'
0x18001e93a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18001e940  nop
0x18001e941  lea     rcx, [rdi+160h]
0x18001e948  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001e94e  mov     dword ptr [rdi+10h], 43724342h
0x18001e955  mov     qword ptr [rdi], 0
0x18001e95c  mov     qword ptr [rdi+8], 0
0x18001e964  jmp     short loc_18001E968
0x18001e966  xor     edi, edi
0x18001e968  test    rdi, rdi
0x18001e96b  jnz     short loc_18001E974
0x18001e96d  mov     esi, 80070008h
0x18001e972  jmp     short loc_18001E9DA
0x18001e974  lea     rcx, [rdi+18h]
0x18001e978  mov     rdx, [rsp+130h+var_E0]
0x18001e97d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e983  mov     esi, eax
0x18001e985  test    eax, eax
0x18001e987  js      short loc_18001E9D1
0x18001e989  lea     r8, [rdi+0E0h]; struct STRA *
0x18001e990  mov     rdx, r14; unsigned __int16 *
0x18001e993  call    ?GenPasswordHash@CREDENTIALS_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; CREDENTIALS_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x18001e998  mov     esi, eax
0x18001e99a  test    eax, eax
0x18001e99c  js      short loc_18001E9D1
0x18001e99e  lea     rax, WideCharStr
0x18001e9a5  test    rbx, rbx
0x18001e9a8  cmovz   rbx, rax
0x18001e9ac  lea     rcx, [rdi+160h]
0x18001e9b3  mov     rdx, rbx
0x18001e9b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e9bc  mov     esi, eax
0x18001e9be  test    eax, eax
0x18001e9c0  js      short loc_18001E9D1
0x18001e9c2  xor     r8d, r8d
0x18001e9c5  mov     rdx, rdi
0x18001e9c8  mov     rcx, r15
0x18001e9cb  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18001e9d1  mov     rcx, rdi; this
0x18001e9d4  call    ?DereferenceCacheEntry@CREDENTIALS_CACHE_ENTRY@@QEAAXXZ; CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(void)
0x18001e9d9  nop
0x18001e9da  lea     rcx, [rsp+130h+var_100]
0x18001e9df  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e9e5  mov     eax, esi
0x18001e9e7  jmp     short loc_18001E9F9
0x18001e9e9  lea     rcx, [rsp+130h+var_100]
0x18001e9ee  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e9f4  mov     eax, 80070057h
0x18001e9f9  mov     rcx, [rbp+47h+var_40]
0x18001e9fd  xor     rcx, rsp; StackCookie
0x18001ea00  call    __security_check_cookie
0x18001ea05  add     rsp, 100h
0x18001ea0c  pop     r15
0x18001ea0e  pop     r14
0x18001ea10  pop     r12
0x18001ea12  pop     rdi
0x18001ea13  pop     rsi
0x18001ea14  pop     rbx
0x18001ea15  pop     rbp
0x18001ea16  retn
```
