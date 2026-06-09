# UcpCreateClientSession

- ea: `0x1c0153670`
- end: `0x1c01539e3`
- name: `UcpCreateClientSession`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0057788`

## callees

- `0x1c0001ae0`
- `0x1c001a8ac`
- `0x1c0038a18`
- `0x1c003a7a4`
- `0x1c0048438`
- `0x1c0057a14`
- `0x1c0057c10`
- `0x1c008f374`
- `0x1c009e894`
- `0x1c0152f6c`
- `0x1c0153300`
- `0x1c01535dc`
- `0x1c0153670`
- `0x1c0153aec`
- `0x1c0154cb4`
- `0x1c0154df0`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c015394d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c015394d`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c015391f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c015391f`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01538fe`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01538fe`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c0153880`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c0153880`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153753`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c015398a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153753`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c015398a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c01536ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c01536ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015375f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015392b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153996`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015375f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015392b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153996`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01536d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01538ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01536d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01538ee`

## pseudocode

```c
__int64 __fastcall UcpCreateClientSession(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PVOID *a5)
{
  volatile signed __int32 *v6; // rbx
  PVOID *v9; // r12
  __int64 v10; // r13
  int Session; // edi
  char v12; // si
  __int64 v13; // r9
  ULONG_PTR v14; // rdx
  PVOID v15; // rcx
  int CurrentServerSilo; // eax
  volatile signed __int32 *v18; // rcx
  _QWORD *v19; // rbx
  __int64 v20; // rsi
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // [rsp+28h] [rbp-28h]
  volatile signed __int32 *v24; // [rsp+40h] [rbp-10h] BYREF
  PVOID v25; // [rsp+48h] [rbp-8h] BYREF
  PVOID P; // [rsp+90h] [rbp+40h] BYREF
  PVOID v27; // [rsp+98h] [rbp+48h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+50h]

  v28 = a3;
  v6 = 0;
  P = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v9 = a5;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_qZqqq(a1, a2, a1, a2, a3, a4, (char)a5);
  *v9 = 0;
  KeEnterCriticalRegion();
  v10 = a1 + 7624;
  ExAcquirePushLockExclusiveEx(a1 + 7624, 0);
  LOBYTE(a5) = 1;
  if ( *(_QWORD *)(a2 + 8) && UcpFindClientSession(a1, a2) )
  {
    Session = -1073741771;
LABEL_6:
    v12 = (char)a5;
    goto LABEL_7;
  }
  Session = UcClientObjectAccessCheck(a4);
  if ( Session < 0 )
    goto LABEL_6;
  Session = UcpAllocateClientSession(a1, a2, v28, &P);
  if ( Session < 0 )
    goto LABEL_6;
  Session = UcAllocateEndpointManager(a1, P, &v25);
  if ( Session < 0 )
    goto LABEL_6;
  CurrentServerSilo = PsGetCurrentServerSilo();
  Session = UxQuicCreateSession((_DWORD)P, 0, a1, CurrentServerSilo, (__int64)&v24);
  if ( Session < 0 || (Session = UcpAllocateClientSessionContext(a4, &v27), Session < 0) )
  {
    v6 = v24;
    goto LABEL_6;
  }
  *((_QWORD *)P + 11) = v25;
  _InterlockedIncrement((volatile signed __int32 *)v25 + 1);
  v18 = v24;
  *((_QWORD *)P + 12) = v24;
  _InterlockedIncrement(v18 + 1);
  v19 = P;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(v19[14]);
  UcpCoupleSessionContextAndSession(v27, P);
  ExReleaseCacheAwarePushLockExclusive(*((_QWORD *)P + 14));
  KeLeaveCriticalRegion();
  RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 7632), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)((char *)P + 32), 1u, 0);
  v20 = a1 + 7672;
  v21 = (char *)P + 56;
  v22 = *(_QWORD **)(v20 + 8);
  if ( *v22 != v20 )
    __fastfail(3u);
  *((_QWORD *)P + 8) = v22;
  *v21 = v20;
  *v22 = v21;
  *(_QWORD *)(v20 + 8) = v21;
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
  v12 = 0;
  v6 = v24;
  *v9 = v27;
  v27 = 0;
  v25 = 0;
  P = 0;
LABEL_7:
  if ( v27 )
  {
    _InterlockedAdd((volatile signed __int32 *)v27, 0xFFFFFFFF);
    UcpFreeClientSessionContext(v27);
    v6 = v24;
    v27 = 0;
  }
  if ( v12 )
  {
    ExReleasePushLockExclusiveEx(v10, 0);
    KeLeaveCriticalRegion();
  }
  if ( v6 )
  {
    UxQuicShutdownSession(v6);
    if ( _InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFF) == 1 )
    {
      v14 = (ULONG_PTR)(v24 + 8);
      if ( *((_QWORD *)v24 + 4) || *((_QWORD *)v24 + 6) || *((_QWORD *)v24 + 8) )
        UlBugCheckEx(1u, v14, (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x25Fu);
      LODWORD(v23) = -1;
      LOBYTE(v13) = 1;
      UlThreadPoolEnqueueWorkItem(0, v14, UxQuicFreeSession, v13, *((_QWORD *)v24 + 10), v23);
    }
  }
  if ( v25 )
  {
    UcCleanupEndpointManager(v25);
    v25 = 0;
  }
  v15 = P;
  if ( P )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
      UcFreeClientSession(v15);
    P = 0;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_D(21, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids);
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x1c0153670  mov     rax, rsp
0x1c0153673  mov     [rax+20h], rbx
0x1c0153677  mov     [rax+18h], r8
0x1c015367b  push    rbp
0x1c015367c  push    rsi
0x1c015367d  push    rdi
0x1c015367e  push    r12
0x1c0153680  push    r13
0x1c0153682  push    r14
0x1c0153684  push    r15
0x1c0153686  mov     rbp, rsp
0x1c0153689  sub     rsp, 50h
0x1c015368d  xor     edi, edi
0x1c015368f  mov     r15, r9
0x1c0153692  mov     ebx, edi
0x1c0153694  mov     [rbp+P], rdi
0x1c0153698  mov     [rbp+var_10], rbx
0x1c015369c  mov     r14, rdx
0x1c015369f  mov     rsi, rcx
0x1c01536a2  mov     [rbp+var_8], rdi
0x1c01536a6  mov     [rbp+arg_8], rdi
0x1c01536aa  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c01536b4  mov     r12, [rbp+arg_20]
0x1c01536b8  jz      short loc_1C01536D1
0x1c01536ba  mov     [rax-58h], r12
0x1c01536be  mov     [rax-60h], r9
0x1c01536c2  mov     r9, rdx
0x1c01536c5  mov     [rax-68h], r8
0x1c01536c9  mov     r8, rcx
0x1c01536cc  call    WPP_SF_qZqqq
0x1c01536d1  mov     [r12], rdi
0x1c01536d5  call    cs:__imp_KeEnterCriticalRegion
0x1c01536dc  nop     dword ptr [rax+rax+00h]
0x1c01536e1  lea     r13, [rsi+1DC8h]
0x1c01536e8  xor     edx, edx
0x1c01536ea  mov     rcx, r13
0x1c01536ed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c01536f4  nop     dword ptr [rax+rax+00h]
0x1c01536f9  mov     byte ptr [rbp+arg_20], 1
0x1c01536fd  cmp     [r14+8], rdi
0x1c0153701  jz      loc_1C0153834
0x1c0153707  mov     rdx, r14
0x1c015370a  mov     rcx, rsi
0x1c015370d  call    UcpFindClientSession
0x1c0153712  test    rax, rax
0x1c0153715  jz      loc_1C0153834
0x1c015371b  mov     edi, 0C0000035h
0x1c0153720  xor     r14d, r14d
0x1c0153723  mov     sil, byte ptr [rbp+arg_20]
0x1c0153727  mov     rax, [rbp+arg_8]
0x1c015372b  or      r15d, 0FFFFFFFFh
0x1c015372f  test    rax, rax
0x1c0153732  jz      short loc_1C0153749
0x1c0153734  lock add [rax], r15d
0x1c0153738  mov     rcx, [rbp+arg_8]; P
0x1c015373c  call    UcpFreeClientSessionContext
0x1c0153741  mov     rbx, [rbp+var_10]
0x1c0153745  mov     [rbp+arg_8], r14
0x1c0153749  test    sil, sil
0x1c015374c  jz      short loc_1C015376B
0x1c015374e  xor     edx, edx
0x1c0153750  mov     rcx, r13
0x1c0153753  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c015375a  nop     dword ptr [rax+rax+00h]
0x1c015375f  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153766  nop     dword ptr [rax+rax+00h]
0x1c015376b  test    rbx, rbx
0x1c015376e  jz      short loc_1C01537C9
0x1c0153770  mov     rcx, rbx
0x1c0153773  call    UxQuicShutdownSession
0x1c0153778  mov     eax, r15d
0x1c015377b  lock xadd [rbx+4], eax
0x1c0153780  add     eax, r15d
0x1c0153783  jnz     short loc_1C01537C9
0x1c0153785  mov     rax, [rbp+var_10]
0x1c0153789  mov     rcx, [rax+50h]
0x1c015378d  lea     rdx, [rax+20h]; BugCheckParameter2
0x1c0153791  cmp     [rdx], r14
0x1c0153794  jnz     loc_1C01539CB
0x1c015379a  cmp     [rdx+10h], r14
0x1c015379e  jnz     loc_1C01539CB
0x1c01537a4  cmp     [rdx+20h], r14
0x1c01537a8  jnz     loc_1C01539CB
0x1c01537ae  or      dword ptr [rsp+50h+var_28], 0FFFFFFFFh
0x1c01537b3  lea     r8, UxQuicFreeSession
0x1c01537ba  mov     [rsp+50h+var_30], rcx
0x1c01537bf  mov     r9b, 1
0x1c01537c2  xor     ecx, ecx
0x1c01537c4  call    UlThreadPoolEnqueueWorkItem
0x1c01537c9  mov     rcx, [rbp+var_8]; P
0x1c01537cd  test    rcx, rcx
0x1c01537d0  jz      short loc_1C01537DB
0x1c01537d2  call    UcCleanupEndpointManager
0x1c01537d7  mov     [rbp+var_8], r14
0x1c01537db  mov     rcx, [rbp+P]; P
0x1c01537df  test    rcx, rcx
0x1c01537e2  jz      short loc_1C01537F9
0x1c01537e4  mov     eax, r15d
0x1c01537e7  lock xadd [rcx], eax
0x1c01537eb  add     eax, r15d
0x1c01537ee  jnz     short loc_1C01537F5
0x1c01537f0  call    UcFreeClientSession
0x1c01537f5  mov     [rbp+P], r14
0x1c01537f9  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0153803  jz      short loc_1C0153819
0x1c0153805  mov     ecx, 15h
0x1c015380a  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0153811  mov     r8d, edi
0x1c0153814  call    WPP_SF_D
0x1c0153819  mov     rbx, [rsp+50h+arg_18]
0x1c0153821  mov     eax, edi
0x1c0153823  add     rsp, 50h
0x1c0153827  pop     r15
0x1c0153829  pop     r14
0x1c015382b  pop     r13
0x1c015382d  pop     r12
0x1c015382f  pop     rdi
0x1c0153830  pop     rsi
0x1c0153831  pop     rbp
0x1c0153832  retn
0x1c0153834  mov     rcx, r15
0x1c0153837  call    UcClientObjectAccessCheck
0x1c015383c  mov     edi, eax
0x1c015383e  test    eax, eax
0x1c0153840  js      loc_1C0153720
0x1c0153846  mov     r8, [rbp+arg_10]
0x1c015384a  lea     r9, [rbp+P]
0x1c015384e  mov     rdx, r14
0x1c0153851  mov     rcx, rsi
0x1c0153854  call    UcpAllocateClientSession
0x1c0153859  xor     r14d, r14d
0x1c015385c  mov     edi, eax
0x1c015385e  test    eax, eax
0x1c0153860  js      loc_1C0153723
0x1c0153866  mov     rdx, [rbp+P]
0x1c015386a  lea     r8, [rbp+var_8]
0x1c015386e  mov     rcx, rsi
0x1c0153871  call    UcAllocateEndpointManager
0x1c0153876  mov     edi, eax
0x1c0153878  test    eax, eax
0x1c015387a  js      loc_1C0153723
0x1c0153880  call    cs:__imp_PsGetCurrentServerSilo
0x1c0153887  nop     dword ptr [rax+rax+00h]
0x1c015388c  mov     rcx, [rbp+P]
0x1c0153890  mov     r8, rsi
0x1c0153893  mov     r9, rax
0x1c0153896  xor     edx, edx
0x1c0153898  lea     rax, [rbp+var_10]
0x1c015389c  mov     [rsp+50h+var_30], rax
0x1c01538a1  call    UxQuicCreateSession
0x1c01538a6  mov     edi, eax
0x1c01538a8  test    eax, eax
0x1c01538aa  js      loc_1C01539C2
0x1c01538b0  lea     rdx, [rbp+arg_8]
0x1c01538b4  mov     rcx, r15
0x1c01538b7  call    UcpAllocateClientSessionContext
0x1c01538bc  mov     edi, eax
0x1c01538be  test    eax, eax
0x1c01538c0  js      loc_1C01539C2
0x1c01538c6  mov     rax, [rbp+var_8]
0x1c01538ca  mov     rcx, [rbp+P]
0x1c01538ce  mov     [rcx+58h], rax
0x1c01538d2  mov     rax, [rbp+var_8]
0x1c01538d6  lock inc dword ptr [rax+4]
0x1c01538da  mov     rax, [rbp+P]
0x1c01538de  mov     rcx, [rbp+var_10]
0x1c01538e2  mov     [rax+60h], rcx
0x1c01538e6  lock inc dword ptr [rcx+4]
0x1c01538ea  mov     rbx, [rbp+P]
0x1c01538ee  call    cs:__imp_KeEnterCriticalRegion
0x1c01538f5  nop     dword ptr [rax+rax+00h]
0x1c01538fa  mov     rcx, [rbx+70h]
0x1c01538fe  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0153905  nop     dword ptr [rax+rax+00h]
0x1c015390a  mov     rdx, [rbp+P]
0x1c015390e  mov     rcx, [rbp+arg_8]
0x1c0153912  call    UcpCoupleSessionContextAndSession
0x1c0153917  mov     rcx, [rbp+P]
0x1c015391b  mov     rcx, [rcx+70h]
0x1c015391f  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0153926  nop     dword ptr [rax+rax+00h]
0x1c015392b  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153932  nop     dword ptr [rax+rax+00h]
0x1c0153937  mov     rdx, [rbp+P]
0x1c015393b  lea     rcx, [rsi+1DD0h]; HashTable
0x1c0153942  add     rdx, 20h ; ' '; Entry
0x1c0153946  lea     r8d, [r14+1]; Signature
0x1c015394a  xor     r9d, r9d; Context
0x1c015394d  call    cs:__imp_RtlInsertEntryHashTable
0x1c0153954  nop     dword ptr [rax+rax+00h]
0x1c0153959  mov     rax, [rbp+P]
0x1c015395d  add     rsi, 1DF8h
0x1c0153964  add     rax, 38h ; '8'
0x1c0153968  mov     rcx, [rsi+8]
0x1c015396c  cmp     [rcx], rsi
0x1c015396f  jz      short loc_1C0153977
0x1c0153971  lea     ecx, [r14+3]
0x1c0153975  int     29h; Win8: RtlFailFast(ecx)
0x1c0153977  mov     [rax+8], rcx
0x1c015397b  xor     edx, edx
0x1c015397d  mov     [rax], rsi
0x1c0153980  mov     [rcx], rax
0x1c0153983  mov     rcx, r13
0x1c0153986  mov     [rsi+8], rax
0x1c015398a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0153991  nop     dword ptr [rax+rax+00h]
0x1c0153996  call    cs:__imp_KeLeaveCriticalRegion
0x1c015399d  nop     dword ptr [rax+rax+00h]
0x1c01539a2  mov     rax, [rbp+arg_8]
0x1c01539a6  mov     sil, r14b
0x1c01539a9  mov     rbx, [rbp+var_10]
0x1c01539ad  mov     [r12], rax
0x1c01539b1  mov     [rbp+arg_8], r14
0x1c01539b5  mov     [rbp+var_8], r14
0x1c01539b9  mov     [rbp+P], r14
0x1c01539bd  jmp     loc_1C0153727
0x1c01539c2  mov     rbx, [rbp+var_10]
0x1c01539c6  jmp     loc_1C0153723
0x1c01539cb  mov     r9d, 25Fh; BugCheckParameter4
0x1c01539d1  lea     r8, aMinioHttpSysQu; "minio\\http\\sys\\quicconn.h"
0x1c01539d8  mov     ecx, 1; BugCheckParameter1
0x1c01539dd  call    UlBugCheckEx
```
