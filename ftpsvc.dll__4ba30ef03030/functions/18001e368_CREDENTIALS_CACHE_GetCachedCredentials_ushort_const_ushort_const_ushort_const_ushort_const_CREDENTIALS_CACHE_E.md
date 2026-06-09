# CREDENTIALS_CACHE::GetCachedCredentials(ushort const *,ushort const *,ushort const *,ushort const *,CREDENTIALS_CACHE_ENTRY * *)

- ea: `0x18001e368`
- end: `0x18001e534`
- name: `?GetCachedCredentials@CREDENTIALS_CACHE@@QEAAJPEBG000PEAPEAVCREDENTIALS_CACHE_ENTRY@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CREDENTIALS_CACHE *this, const unsigned __int16 *, const BYTE *, const unsigned __int16 *, unsigned __int16 *, struct CREDENTIALS_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c2fc`

## callees

- `0x180002504`
- `0x18001e014`
- `0x18001e14c`
- `0x18001e368`
- `0x180047050`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001e46a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001e46a`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18001e49f`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18001e49f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e452`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e452`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001e48b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001e4ad`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001e48b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001e4ad`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001e435`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001e435`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e3b6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e3b6`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e4bf`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e4bf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e4fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e50b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e4fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e50b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CREDENTIALS_CACHE::GetCachedCredentials(
        CREDENTIALS_CACHE *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct CREDENTIALS_CACHE_ENTRY **a6)
{
  int CacheKey; // ebx
  int Key; // eax
  struct CREDENTIALS_CACHE_ENTRY *v12; // rcx
  char *v13; // rsi
  CREDENTIALS_CACHE_ENTRY *v14; // rcx
  BOOL v15; // esi
  struct CREDENTIALS_CACHE_ENTRY *v17; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[56]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *v19[7]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[68]; // [rsp+98h] [rbp-68h] BYREF
  char v21[80]; // [rsp+120h] [rbp+20h] BYREF

  STRU::STRU((STRU *)v19, v20, 0x40u);
  if ( a2 && a3 && a5 && a4 && a6 )
  {
    *a6 = 0;
    if ( *((_DWORD *)this + 19) )
    {
      CacheKey = CREDENTIALS_CACHE_KEY::CreateCacheKey(v19, a2, a4, a5);
      if ( CacheKey < 0 )
      {
LABEL_18:
        STRU::~STRU(v19);
        return (unsigned int)CacheKey;
      }
      *a6 = 0;
      v17 = 0;
      Key = CLKRHashTable::FindKey(this, v19, &v17);
      v12 = v17;
      *a6 = v17;
      if ( !Key )
      {
        CReaderWriterLock3::ReadLock((struct CREDENTIALS_CACHE_ENTRY *)((char *)v12 + 212));
        v13 = (char *)*a6;
        STRA::STRA((STRA *)v18, v21, 0x41u);
        CacheKey = CREDENTIALS_CACHE_ENTRY::GenPasswordHash(v14, a3, (struct STRA *)v18);
        if ( CacheKey >= 0 )
        {
          v15 = STRA::Equals((STRA *)(v13 + 224), (const struct STRA *)v18);
          STRA::~STRA((STRA *)v18);
          CacheKey = 0;
        }
        else
        {
          v15 = 0;
          STRA::~STRA((STRA *)v18);
        }
        CReaderWriterLock3::ReadUnlock((struct CREDENTIALS_CACHE_ENTRY *)((char *)*a6 + 212));
        if ( CacheKey < 0 )
        {
          CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(*a6);
          *a6 = 0;
          goto LABEL_18;
        }
        if ( v15 )
          goto LABEL_18;
      }
      if ( !*a6 )
        goto LABEL_18;
      CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(*a6);
      *a6 = 0;
    }
    CacheKey = -2147023570;
    goto LABEL_18;
  }
  STRU::~STRU(v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001e368  push    rbp
0x18001e36a  push    rbx
0x18001e36b  push    rsi
0x18001e36c  push    rdi
0x18001e36d  push    r12
0x18001e36f  push    r14
0x18001e371  push    r15
0x18001e373  lea     rbp, [rsp-80h]
0x18001e378  sub     rsp, 180h
0x18001e37f  mov     rax, cs:__security_cookie
0x18001e386  xor     rax, rsp
0x18001e389  mov     [rbp+0B0h+var_40], rax
0x18001e38d  mov     rbx, r9
0x18001e390  mov     r15, r8
0x18001e393  mov     r12, rdx
0x18001e396  mov     rsi, rcx
0x18001e399  mov     r14, [rbp+0B0h+arg_20]
0x18001e3a0  mov     rdi, [rbp+0B0h+arg_28]
0x18001e3a7  mov     r8d, 40h ; '@'
0x18001e3ad  lea     rdx, [rbp+0B0h+var_118]
0x18001e3b1  lea     rcx, [rsp+1B0h+var_150]
0x18001e3b6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e3bc  nop
0x18001e3bd  test    r12, r12
0x18001e3c0  jz      loc_18001E506
0x18001e3c6  test    r15, r15
0x18001e3c9  jz      loc_18001E506
0x18001e3cf  test    r14, r14
0x18001e3d2  jz      loc_18001E506
0x18001e3d8  test    rbx, rbx
0x18001e3db  jz      loc_18001E506
0x18001e3e1  test    rdi, rdi
0x18001e3e4  jz      loc_18001E506
0x18001e3ea  mov     qword ptr [rdi], 0
0x18001e3f1  cmp     dword ptr [rsi+4Ch], 0
0x18001e3f5  jz      loc_18001E4F2
0x18001e3fb  mov     r9, r14; unsigned __int16 *
0x18001e3fe  mov     r8, rbx; unsigned __int16 *
0x18001e401  mov     rdx, r12; unsigned __int16 *
0x18001e404  lea     rcx, [rsp+1B0h+var_150]; this
0x18001e409  call    ?CreateCacheKey@CREDENTIALS_CACHE_KEY@@QEAAJPEBG00@Z; CREDENTIALS_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ushort const *)
0x18001e40e  mov     ebx, eax
0x18001e410  test    eax, eax
0x18001e412  js      loc_18001E4F7
0x18001e418  mov     qword ptr [rdi], 0
0x18001e41f  mov     [rsp+1B0h+var_190], 0
0x18001e428  lea     r8, [rsp+1B0h+var_190]
0x18001e42d  lea     rdx, [rsp+1B0h+var_150]
0x18001e432  mov     rcx, rsi
0x18001e435  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001e43b  mov     rcx, [rsp+1B0h+var_190]
0x18001e440  mov     [rdi], rcx
0x18001e443  test    eax, eax
0x18001e445  jnz     loc_18001E4DE
0x18001e44b  add     rcx, 0D4h
0x18001e452  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001e458  mov     rsi, [rdi]
0x18001e45b  mov     r8d, 41h ; 'A'
0x18001e461  lea     rdx, [rbp+0B0h+var_90]
0x18001e465  lea     rcx, [rsp+1B0h+var_188]
0x18001e46a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18001e470  nop
0x18001e471  lea     r8, [rsp+1B0h+var_188]; struct STRA *
0x18001e476  mov     rdx, r15; unsigned __int16 *
0x18001e479  call    ?GenPasswordHash@CREDENTIALS_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; CREDENTIALS_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x18001e47e  mov     ebx, eax
0x18001e480  test    eax, eax
0x18001e482  jns     short loc_18001E493
0x18001e484  xor     esi, esi
0x18001e486  lea     rcx, [rsp+1B0h+var_188]
0x18001e48b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001e491  jmp     short loc_18001E4B5
0x18001e493  lea     rcx, [rsi+0E0h]
0x18001e49a  lea     rdx, [rsp+1B0h+var_188]
0x18001e49f  call    cs:__imp_?Equals@STRA@@QEBA_NAEBV1@@Z; STRA::Equals(STRA const &)
0x18001e4a5  movzx   esi, al
0x18001e4a8  lea     rcx, [rsp+1B0h+var_188]
0x18001e4ad  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001e4b3  xor     ebx, ebx
0x18001e4b5  mov     rcx, [rdi]
0x18001e4b8  add     rcx, 0D4h
0x18001e4bf  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001e4c5  test    ebx, ebx
0x18001e4c7  jns     short loc_18001E4DA
0x18001e4c9  mov     rcx, [rdi]; this
0x18001e4cc  call    ?DereferenceCacheEntry@CREDENTIALS_CACHE_ENTRY@@QEAAXXZ; CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(void)
0x18001e4d1  mov     qword ptr [rdi], 0
0x18001e4d8  jmp     short loc_18001E4F7
0x18001e4da  test    esi, esi
0x18001e4dc  jnz     short loc_18001E4F7
0x18001e4de  mov     rcx, [rdi]; this
0x18001e4e1  test    rcx, rcx
0x18001e4e4  jz      short loc_18001E4F7
0x18001e4e6  call    ?DereferenceCacheEntry@CREDENTIALS_CACHE_ENTRY@@QEAAXXZ; CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(void)
0x18001e4eb  mov     qword ptr [rdi], 0
0x18001e4f2  mov     ebx, 8007052Eh
0x18001e4f7  lea     rcx, [rsp+1B0h+var_150]
0x18001e4fc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e502  mov     eax, ebx
0x18001e504  jmp     short loc_18001E516
0x18001e506  lea     rcx, [rsp+1B0h+var_150]
0x18001e50b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e511  mov     eax, 80070057h
0x18001e516  mov     rcx, [rbp+0B0h+var_40]
0x18001e51a  xor     rcx, rsp; StackCookie
0x18001e51d  call    __security_check_cookie
0x18001e522  add     rsp, 180h
0x18001e529  pop     r15
0x18001e52b  pop     r14
0x18001e52d  pop     r12
0x18001e52f  pop     rdi
0x18001e530  pop     rsi
0x18001e531  pop     rbx
0x18001e532  pop     rbp
0x18001e533  retn
```
