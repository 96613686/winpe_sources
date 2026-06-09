# SetOfflineOriginUrlW(uchar * const,ushort const *,char const *,ulong,_FILETIME *)

- ea: `0x18001802c`
- end: `0x180018181`
- name: `?SetOfflineOriginUrlW@@YAXQEAEPEBGPEBDKPEAU_FILETIME@@@Z`
- size: `341`
- prototype: `void __fastcall(unsigned __int8 *const Buf2, BYTE *, const char *, char, FILETIME *lpFileTime1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009e30`

## callees

- `0x18001802c`
- `0x180018188`
- `0x180018290`
- `0x180026546`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001805e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001805e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001816a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001816a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800180ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800180ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001814e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001814e`

## pseudocode

```c
void __fastcall SetOfflineOriginUrlW(
        unsigned __int8 *const Buf2,
        BYTE *a2,
        const char *a3,
        char a4,
        FILETIME *lpFileTime1)
{
  __int64 v9; // rax
  unsigned int v10; // esi
  struct _OFFLINE_URL_CACHE_ENTRY *v11; // rbx
  int v12; // ecx
  int v13; // ebp
  FILETIME FileTime2; // [rsp+20h] [rbp-78h] BYREF
  struct _CRYPTOAPI_BLOB v15; // [rsp+28h] [rbp-70h] BYREF
  struct _CRYPTOAPI_BLOB v16; // [rsp+38h] [rbp-60h] BYREF

  *(&v16.cbData + 1) = 0;
  *(&v15.cbData + 1) = 0;
  FileTime2 = 0;
  GetSystemTimeAsFileTime(&FileTime2);
  if ( !lpFileTime1 || CompareFileTime(lpFileTime1, &FileTime2) <= 0 )
  {
    v16.pbData = a2;
    if ( a2 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)&a2[2 * v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    v10 = 2 * v9;
    v15.pbData = Buf2;
    v16.cbData = 2 * v9;
    v15.cbData = 32;
    EnterCriticalSection(&OfflineUrlCacheCriticalSection);
    v11 = pOfflineUrlCacheHead;
    v12 = 0x10000;
    if ( (unsigned int)a3 <= 0xFFFF )
      v12 = (int)a3;
    v13 = v12 | 0x20000;
    if ( (a4 & 4) == 0 )
      v13 = v12;
    while ( v11 )
    {
      if ( *((_DWORD *)v11 + 8) == v13
        && *(_DWORD *)v11 == v10
        && *((_DWORD *)v11 + 4) == 32
        && !memcmp_0(*((const void **)v11 + 3), Buf2, 0x20u)
        && (!v10 || !memcmp_0(*((const void **)v11 + 1), a2, v10)) )
      {
        goto LABEL_17;
      }
      v11 = (struct _OFFLINE_URL_CACHE_ENTRY *)*((_QWORD *)v11 + 6);
    }
    v11 = CreateAndAddOfflineUrlCacheEntry(&v16, &v15, a3, a4);
    if ( v11 )
LABEL_17:
      SetOfflineUrlTime((struct _OFFLINE_URL_CACHE_ENTRY *)((char *)v11 + 36), 0);
    LeaveCriticalSection(&OfflineUrlCacheCriticalSection);
  }
}

```

## disassembly

```asm
0x18001802c  mov     rax, rsp
0x18001802f  push    rbx
0x180018030  push    rbp
0x180018031  push    rsi
0x180018032  push    rdi
0x180018033  push    r12
0x180018035  push    r13
0x180018037  push    r14
0x180018039  push    r15
0x18001803b  sub     rsp, 58h
0x18001803f  xor     r13d, r13d
0x180018042  mov     r12, rcx
0x180018045  lea     rcx, [rax-78h]; lpSystemTimeAsFileTime
0x180018049  mov     [rax-5Ch], r13d
0x18001804d  mov     [rax-6Ch], r13d
0x180018051  mov     r15d, r9d
0x180018054  mov     [rax-78h], r13
0x180018058  mov     r14, r8
0x18001805b  mov     rdi, rdx
0x18001805e  call    cs:__imp_GetSystemTimeAsFileTime
0x180018064  mov     rcx, [rsp+98h+lpFileTime1]; lpFileTime1
0x18001806c  test    rcx, rcx
0x18001806f  jnz     loc_180018165
0x180018075  mov     [rsp+98h+var_60.pbData], rdi
0x18001807a  test    rdi, rdi
0x18001807d  jz      loc_180018179
0x180018083  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018087  inc     rax
0x18001808a  cmp     [rdi+rax*2], r13w
0x18001808f  jnz     short loc_180018087
0x180018091  lea     esi, [rax+rax]
0x180018094  mov     [rsp+98h+var_70.pbData], r12
0x180018099  lea     rcx, ?OfflineUrlCacheCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800180a0  mov     [rsp+98h+var_60.cbData], esi
0x1800180a4  mov     [rsp+98h+var_70.cbData], 20h ; ' '
0x1800180ac  call    cs:__imp_EnterCriticalSection
0x1800180b2  mov     rbx, cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x1800180b9  cmp     r14d, 0FFFFh
0x1800180c0  mov     ecx, 10000h
0x1800180c5  cmovbe  ecx, r14d
0x1800180c9  mov     ebp, ecx
0x1800180cb  bts     ebp, 11h
0x1800180cf  test    r15b, 4
0x1800180d3  cmovz   ebp, ecx
0x1800180d6  test    rbx, rbx
0x1800180d9  jz      short loc_18001812A
0x1800180db  cmp     [rbx+20h], ebp
0x1800180de  jnz     short loc_1800180E4
0x1800180e0  cmp     [rbx], esi
0x1800180e2  jz      short loc_1800180EA
0x1800180e4  mov     rbx, [rbx+30h]
0x1800180e8  jmp     short loc_1800180D6
0x1800180ea  cmp     dword ptr [rbx+10h], 20h ; ' '
0x1800180ee  jnz     short loc_1800180E4
0x1800180f0  mov     rcx, [rbx+18h]; Buf1
0x1800180f4  mov     r8d, 20h ; ' '; Size
0x1800180fa  mov     rdx, r12; Buf2
0x1800180fd  call    memcmp_0
0x180018102  test    eax, eax
0x180018104  jnz     short loc_1800180E4
0x180018106  test    esi, esi
0x180018108  jz      short loc_18001811D
0x18001810a  mov     rcx, [rbx+8]; Buf1
0x18001810e  mov     rdx, rdi; Buf2
0x180018111  mov     r8d, esi; Size
0x180018114  call    memcmp_0
0x180018119  test    eax, eax
0x18001811b  jnz     short loc_1800180E4
0x18001811d  lea     rcx, [rbx+24h]; struct _OFFLINE_URL_TIME_INFO *
0x180018121  xor     edx, edx; struct _FILETIME *
0x180018123  call    ?SetOfflineUrlTime@@YAXPEAU_OFFLINE_URL_TIME_INFO@@PEAU_FILETIME@@@Z; SetOfflineUrlTime(_OFFLINE_URL_TIME_INFO *,_FILETIME *)
0x180018128  jmp     short loc_180018147
0x18001812a  mov     r9d, r15d; unsigned int
0x18001812d  lea     rdx, [rsp+98h+var_70]; struct _CRYPTOAPI_BLOB *
0x180018132  mov     r8, r14; char *
0x180018135  lea     rcx, [rsp+98h+var_60]; struct _CRYPTOAPI_BLOB *
0x18001813a  call    ?CreateAndAddOfflineUrlCacheEntry@@YAPEAU_OFFLINE_URL_CACHE_ENTRY@@PEAU_CRYPTOAPI_BLOB@@0PEBDK@Z; CreateAndAddOfflineUrlCacheEntry(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,char const *,ulong)
0x18001813f  mov     rbx, rax
0x180018142  test    rax, rax
0x180018145  jnz     short loc_18001811D
0x180018147  lea     rcx, ?OfflineUrlCacheCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001814e  call    cs:__imp_LeaveCriticalSection
0x180018154  add     rsp, 58h
0x180018158  pop     r15
0x18001815a  pop     r14
0x18001815c  pop     r13
0x18001815e  pop     r12
0x180018160  pop     rdi
0x180018161  pop     rsi
0x180018162  pop     rbp
0x180018163  pop     rbx
0x180018164  retn
0x180018165  lea     rdx, [rsp+98h+FileTime2]; lpFileTime2
0x18001816a  call    cs:__imp_CompareFileTime
0x180018170  test    eax, eax
0x180018172  jg      short loc_180018154
0x180018174  jmp     loc_180018075
0x180018179  mov     eax, r13d
0x18001817c  jmp     loc_180018091
```
