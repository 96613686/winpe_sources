# IP_RESTRICTION_LIST::ReverseDNSLookup(int,sockaddr *,int,void (*)(void *),void *,STRU *,long *,int *)

- ea: `0x180004110`
- end: `0x180004288`
- name: `?ReverseDNSLookup@IP_RESTRICTION_LIST@@SAJHPEAUsockaddr@@HP6AXPEAX@Z1PEAVSTRU@@PEAJPEAH@Z`
- size: `376`
- prototype: `__int64 __fastcall(int, struct sockaddr *, int, void (*)(void *), void *, struct STRU *, int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001b5c`
- `0x18000369c`

## callees

- `0x180001088`
- `0x1800010c8`
- `0x180003df4`
- `0x180004110`
- `0x180004290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800041a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800041a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004158`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004177`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004158`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004177`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180004194`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180004194`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000413e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000413e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004234`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004234`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004265`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004265`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST::ReverseDNSLookup(
        __int64 a1,
        struct sockaddr *a2,
        int a3,
        void (*a4)(void *),
        void *a5,
        struct STRU *a6,
        int *a7,
        int *a8)
{
  int v9; // edi
  int Key; // eax
  char *v12; // rbx
  int v13; // esi
  char *v14; // rax
  void *v15; // rsi
  void *Block; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  Block = 0;
  Key = CLKRHashTable::FindKey(&IP_RESTRICTION_LIST::sm_FastDNSLookupTable, a2, &Block);
  v12 = (char *)Block;
  if ( Key )
    goto LABEL_7;
  v13 = *((_DWORD *)Block + 55);
  if ( *((int *)Block + 1) < 0 )
  {
    if ( GetTickCount() - v13 <= 0x2BF20 )
    {
      *a7 = -2147023728;
      goto LABEL_14;
    }
    goto LABEL_6;
  }
  if ( GetTickCount() - v13 > 0x493E0 )
  {
LABEL_6:
    CLKRHashTable::DeleteRecord(&IP_RESTRICTION_LIST::sm_FastDNSLookupTable, v12);
LABEL_7:
    if ( !IP_RESTRICTION_LIST::sm_fLazyInitializeComplete )
    {
      EnterCriticalSection(&IP_RESTRICTION_LIST::sm_csLazyInitialize);
      v9 = IP_RESTRICTION_LIST::LazyInitialize();
      LeaveCriticalSection(&IP_RESTRICTION_LIST::sm_csLazyInitialize);
    }
    v14 = (char *)operator new(0x58u);
    v15 = v14;
    if ( v14 )
    {
      *((_QWORD *)v14 + 2) = a6;
      *((_QWORD *)v14 + 4) = a7;
      *(_DWORD *)v14 = 0;
      *((_QWORD *)v14 + 1) = a2;
      *((_DWORD *)v14 + 6) = a3;
      *((_QWORD *)v14 + 9) = 0;
      *((_QWORD *)v14 + 10) = 0;
      IP_RESTRICTION_LIST::ReverseDNSLookupThreadDoWork(0, 0, (struct _OVERLAPPED *)(v14 + 40));
      *a8 = 0;
      operator delete(v15);
    }
    else
    {
      v9 = -2147024882;
    }
    goto LABEL_14;
  }
  v9 = STRU::Copy(a6, *((const unsigned __int16 **)v12 + 5), *((_DWORD *)v12 + 14));
  if ( v9 >= 0 )
  {
    v9 = 0;
    *a8 = 0;
  }
LABEL_14:
  if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)v12, 0xFFFFFFFF) == 1 )
  {
    STRU::~STRU((STRU *)(v12 + 8));
    operator delete(v12);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004110  mov     rax, rsp
0x180004113  mov     [rax+8], rbx
0x180004117  mov     [rax+10h], rbp
0x18000411b  mov     [rax+20h], r9
0x18000411f  push    rsi
0x180004120  push    rdi
0x180004121  push    r14
0x180004123  sub     rsp, 20h
0x180004127  mov     r14d, r8d
0x18000412a  lea     rcx, ?sm_FastDNSLookupTable@IP_RESTRICTION_LIST@@0VFAST_DNS_LOOKUP_HASH@@A; FAST_DNS_LOOKUP_HASH IP_RESTRICTION_LIST::sm_FastDNSLookupTable
0x180004131  xor     edi, edi
0x180004133  lea     r8, [rax+20h]
0x180004137  mov     [rax+20h], rdi
0x18000413b  mov     rbp, rdx
0x18000413e  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180004144  mov     rbx, [rsp+38h+Block]
0x180004149  test    eax, eax
0x18000414b  jnz     short loc_18000419A
0x18000414d  mov     esi, [rbx+0DCh]
0x180004153  cmp     [rbx+4], edi
0x180004156  jge     short loc_180004177
0x180004158  call    cs:__imp_GetTickCount
0x18000415e  sub     eax, esi
0x180004160  cmp     eax, 2BF20h
0x180004165  ja      short loc_18000418A
0x180004167  mov     rax, [rsp+38h+arg_30]
0x18000416c  mov     dword ptr [rax], 80070490h
0x180004172  jmp     loc_180004250
0x180004177  call    cs:__imp_GetTickCount
0x18000417d  sub     eax, esi
0x18000417f  cmp     eax, 493E0h
0x180004184  jbe     loc_180004227
0x18000418a  mov     rdx, rbx
0x18000418d  lea     rcx, ?sm_FastDNSLookupTable@IP_RESTRICTION_LIST@@0VFAST_DNS_LOOKUP_HASH@@A; FAST_DNS_LOOKUP_HASH IP_RESTRICTION_LIST::sm_FastDNSLookupTable
0x180004194  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18000419a  cmp     cs:?sm_fLazyInitializeComplete@IP_RESTRICTION_LIST@@0HA, edi; int IP_RESTRICTION_LIST::sm_fLazyInitializeComplete
0x1800041a0  jnz     short loc_1800041C3
0x1800041a2  lea     rcx, ?sm_csLazyInitialize@IP_RESTRICTION_LIST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800041a9  call    cs:__imp_EnterCriticalSection
0x1800041af  call    ?LazyInitialize@IP_RESTRICTION_LIST@@SAJXZ; IP_RESTRICTION_LIST::LazyInitialize(void)
0x1800041b4  lea     rcx, ?sm_csLazyInitialize@IP_RESTRICTION_LIST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800041bb  mov     edi, eax
0x1800041bd  call    cs:__imp_LeaveCriticalSection
0x1800041c3  mov     ecx, 58h ; 'X'; Size
0x1800041c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041cd  mov     rsi, rax
0x1800041d0  test    rax, rax
0x1800041d3  jz      short loc_18000424B
0x1800041d5  mov     rcx, [rsp+38h+arg_28]
0x1800041da  lea     r8, [rax+28h]; struct _OVERLAPPED *
0x1800041de  mov     [rax+10h], rcx
0x1800041e2  xor     edx, edx; unsigned int
0x1800041e4  mov     rcx, [rsp+38h+arg_30]
0x1800041e9  mov     [rax+20h], rcx
0x1800041ed  xor     ecx, ecx; unsigned int
0x1800041ef  mov     dword ptr [rax], 0
0x1800041f5  mov     [rax+8], rbp
0x1800041f9  mov     [rax+18h], r14d
0x1800041fd  mov     qword ptr [rax+48h], 0
0x180004205  mov     qword ptr [rax+50h], 0
0x18000420d  call    ?ReverseDNSLookupThreadDoWork@IP_RESTRICTION_LIST@@CAXKKPEAU_OVERLAPPED@@@Z; IP_RESTRICTION_LIST::ReverseDNSLookupThreadDoWork(ulong,ulong,_OVERLAPPED *)
0x180004212  mov     rax, [rsp+38h+arg_38]
0x180004217  mov     dword ptr [rax], 0
0x18000421d  mov     rcx, rsi; Block
0x180004220  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004225  jmp     short loc_180004250
0x180004227  mov     r8d, [rbx+38h]
0x18000422b  mov     rdx, [rbx+28h]
0x18000422f  mov     rcx, [rsp+38h+arg_28]
0x180004234  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000423a  mov     edi, eax
0x18000423c  test    eax, eax
0x18000423e  js      short loc_180004250
0x180004240  mov     rax, [rsp+38h+arg_38]
0x180004245  xor     edi, edi
0x180004247  mov     [rax], edi
0x180004249  jmp     short loc_180004250
0x18000424b  mov     edi, 8007000Eh
0x180004250  test    rbx, rbx
0x180004253  jz      short loc_180004273
0x180004255  or      eax, 0FFFFFFFFh
0x180004258  lock xadd [rbx], eax
0x18000425c  cmp     eax, 1
0x18000425f  jnz     short loc_180004273
0x180004261  lea     rcx, [rbx+8]
0x180004265  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000426b  mov     rcx, rbx; Block
0x18000426e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004273  mov     rbx, [rsp+38h+arg_0]
0x180004278  mov     eax, edi
0x18000427a  mov     rbp, [rsp+38h+arg_8]
0x18000427f  add     rsp, 20h
0x180004283  pop     r14
0x180004285  pop     rdi
0x180004286  pop     rsi
0x180004287  retn
```
