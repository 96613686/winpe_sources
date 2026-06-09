# SiteCache_PrivSearch(ushort const *,_ITEMIDLIST const *,IMalloc *,CFtpSite * *)

- ea: `0x18001ff7c`
- end: `0x180020095`
- name: `?SiteCache_PrivSearch@@YAJPEBGPEFBU_ITEMIDLIST@@PEAUIMalloc@@PEAPEAVCFtpSite@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(LPCWSTR psz, const struct _ITEMIDLIST *, IUnknown *punk, struct CFtpSite **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fea8`

## callees

- `0x18001965c`
- `0x1800196e4`
- `0x18001f418`
- `0x18001ff7c`
- `0x180026a4c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020039`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020039`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002005c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020080`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002005c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020080`

## pseudocode

```c
__int64 __fastcall SiteCache_PrivSearch(LPCWSTR psz, struct _ITEMIDLIST *a2, IUnknown *punk, struct CFtpSite **a4)
{
  struct CFtpSite *v8; // rbx
  unsigned int v9; // edi
  CFtpList *v10; // rcx
  int v11; // eax
  void *p; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  EnterCriticalSection(&g_csDll);
  v10 = g_FtpSiteCache;
  if ( !g_FtpSiteCache )
  {
    if ( (int)CFtpList_Create(0, 0, 10, &g_FtpSiteCache) < 0 )
      goto LABEL_11;
    v10 = g_FtpSiteCache;
  }
  p = CFtpList::Find(v10, (int (*)(const void *, const void *, __int64))_CompareSites, psz);
  v8 = (struct CFtpSite *)p;
  if ( !p )
  {
    v11 = CFtpSite_Create(a2, psz, punk, (struct CFtpSite **)&p);
    v8 = (struct CFtpSite *)p;
    v9 = v11;
    if ( v11 >= 0 )
    {
      if ( DPA_InsertPtr(*((HDPA *)g_FtpSiteCache + 2), 0x7FFFFFFF, p) < 0 )
      {
        v9 = -2147024882;
        EnterCriticalSection(&g_csDll);
        if ( v8 )
          (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v8 + 16LL))(v8);
        v8 = 0;
        LeaveCriticalSection(&g_csDll);
      }
      else
      {
        v9 = 0;
      }
    }
  }
LABEL_11:
  *a4 = v8;
  if ( v8 )
    (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v8 + 8LL))(v8);
  LeaveCriticalSection(&g_csDll);
  return v9;
}

```

## disassembly

```asm
0x18001ff7c  push    rbx
0x18001ff7e  push    rbp
0x18001ff7f  push    rsi
0x18001ff80  push    rdi
0x18001ff81  push    r14
0x18001ff83  push    r15
0x18001ff85  sub     rsp, 28h
0x18001ff89  mov     rsi, rcx
0x18001ff8c  mov     r14, r9
0x18001ff8f  lea     rcx, g_csDll; lpCriticalSection
0x18001ff96  mov     rbp, r8
0x18001ff99  mov     r15, rdx
0x18001ff9c  xor     ebx, ebx
0x18001ff9e  xor     edi, edi
0x18001ffa0  call    cs:__imp_EnterCriticalSection
0x18001ffa6  mov     rcx, cs:?g_FtpSiteCache@@3PEAVCFtpList@@EA; int
0x18001ffad  test    rcx, rcx
0x18001ffb0  jnz     short loc_18001FFD3
0x18001ffb2  lea     r9, ?g_FtpSiteCache@@3PEAVCFtpList@@EA; struct CFtpList **
0x18001ffb9  xor     edx, edx; int (*)(void *, void *)
0x18001ffbb  lea     r8d, [rbx+0Ah]; unsigned int
0x18001ffbf  call    ?CFtpList_Create@@YAJHP6AHPEAX0@ZIPEAPEAVCFtpList@@@Z; CFtpList_Create(int,int (*)(void *,void *),uint,CFtpList * *)
0x18001ffc4  test    eax, eax
0x18001ffc6  js      loc_180020062
0x18001ffcc  mov     rcx, cs:?g_FtpSiteCache@@3PEAVCFtpList@@EA; this
0x18001ffd3  mov     r8, rsi; void *
0x18001ffd6  lea     rdx, ?_CompareSites@@YAHPEBX0_J@Z; int (*)(const void *, const void *, __int64)
0x18001ffdd  call    ?Find@CFtpList@@QEAAPEAXP6AHPEBX0_J@Z0@Z; CFtpList::Find(int (*)(void const *,void const *,__int64),void const *)
0x18001ffe2  mov     [rsp+58h+p], rax
0x18001ffe7  mov     rbx, rax
0x18001ffea  test    rax, rax
0x18001ffed  jnz     short loc_180020062
0x18001ffef  lea     r9, [rsp+58h+p]; struct CFtpSite **
0x18001fff4  mov     r8, rbp; punk
0x18001fff7  mov     rdx, rsi; psz
0x18001fffa  mov     rcx, r15; struct _ITEMIDLIST *
0x18001fffd  call    ?CFtpSite_Create@@YAJPEFBU_ITEMIDLIST@@PEBGPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; CFtpSite_Create(_ITEMIDLIST const *,ushort const *,IMalloc *,CFtpSite * *)
0x180020002  mov     rbx, [rsp+58h+p]
0x180020007  mov     edi, eax
0x180020009  test    eax, eax
0x18002000b  js      short loc_180020062
0x18002000d  mov     rcx, cs:?g_FtpSiteCache@@3PEAVCFtpList@@EA; CFtpList * g_FtpSiteCache
0x180020014  mov     r8, rbx; p
0x180020017  mov     edx, 7FFFFFFFh; i
0x18002001c  mov     rcx, [rcx+10h]; hdpa
0x180020020  call    DPA_InsertPtr
0x180020025  test    eax, eax
0x180020027  js      short loc_18002002D
0x180020029  xor     edi, edi
0x18002002b  jmp     short loc_180020062
0x18002002d  lea     rcx, g_csDll; lpCriticalSection
0x180020034  mov     edi, 8007000Eh
0x180020039  call    cs:__imp_EnterCriticalSection
0x18002003f  test    rbx, rbx
0x180020042  jz      short loc_180020053
0x180020044  mov     rax, [rbx]
0x180020047  mov     rcx, rbx
0x18002004a  mov     rax, [rax+10h]
0x18002004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020053  xor     ebx, ebx
0x180020055  lea     rcx, g_csDll; lpCriticalSection
0x18002005c  call    cs:__imp_LeaveCriticalSection
0x180020062  mov     [r14], rbx
0x180020065  test    rbx, rbx
0x180020068  jz      short loc_180020079
0x18002006a  mov     rax, [rbx]
0x18002006d  mov     rcx, rbx
0x180020070  mov     rax, [rax+8]
0x180020074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020079  lea     rcx, g_csDll; lpCriticalSection
0x180020080  call    cs:__imp_LeaveCriticalSection
0x180020086  mov     eax, edi
0x180020088  add     rsp, 28h
0x18002008c  pop     r15
0x18002008e  pop     r14
0x180020090  pop     rdi
0x180020091  pop     rsi
0x180020092  pop     rbp
0x180020093  pop     rbx
0x180020094  retn
```
