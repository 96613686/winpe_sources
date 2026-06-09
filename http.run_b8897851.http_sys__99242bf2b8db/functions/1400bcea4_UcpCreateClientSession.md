# UcpCreateClientSession

- ea: `0x1400bcea4`
- end: `0x1400bd2c2`
- name: `UcpCreateClientSession`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14015bcc4`

## callees

- `0x14000a350`
- `0x140022610`
- `0x1400bcea4`
- `0x1400bd2c8`
- `0x1400bd8c4`
- `0x14010958c`
- `0x14012fb98`
- `0x14015bda8`
- `0x14015c420`
- `0x14015c578`
- `0x140167700`
- `0x140167b40`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400bcfeb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400bcfeb`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd0bf`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd0bf`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd09b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd09b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd0cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd118`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd19a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd0cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd118`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd19a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd10c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd18e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd10c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd18e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bcf87`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bcf87`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd08b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd08b`

## pseudocode

```c
__int64 __fastcall UcpCreateClientSession(__int64 a1, __int64 a2, __int64 a3, char a4, PVOID *a5)
{
  char v5; // r13
  volatile signed __int32 *v9; // rbx
  __int64 v11; // r9
  int Session; // esi
  char v13; // di
  ULONG_PTR v14; // rdx
  int v15; // eax
  ULONG_PTR v16; // rbx
  __int64 v17; // r14
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  _QWORD *v22; // rcx
  ULONG_PTR v23; // rdx
  int v24; // eax
  ULONG_PTR v25; // rdx
  void *v26; // rcx
  int v27; // eax
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-C0h] BYREF
  PVOID P; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34[18]; // [rsp+70h] [rbp-90h] BYREF

  v5 = 0;
  v33 = a2;
  BugCheckParameter2 = 0;
  v31 = 0;
  v9 = 0;
  P = 0;
  memset(v34, 0, sizeof(v34));
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
  {
    WPP_SF_qqqi(1053, 18, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, a1, a2, a3, a5);
    v9 = (volatile signed __int32 *)P;
  }
  *a5 = 0;
  v32 = a1 + 8712;
  if ( (a4 & 1) != 0 )
  {
    Session = -1073741811;
LABEL_16:
    if ( v9 )
    {
      v21 = _InterlockedDecrement(v9);
      if ( UxDebugCheckRefcount && v21 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v9, 1u, v21);
      UcpFreeClientSessionContext(P);
      P = 0;
    }
    if ( v5 )
    {
      ExReleasePushLockExclusiveEx(v32, 0);
      KeLeaveCriticalRegion();
    }
    goto LABEL_23;
  }
  v13 = -(a4 & 2);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 8712, 0);
  v5 = 1;
  Session = UcClientObjectAccessCheck(a3);
  if ( Session < 0 )
    goto LABEL_15;
  Session = UcpAllocateClientSession(a1, v33, &BugCheckParameter2);
  if ( Session < 0 )
    goto LABEL_15;
  *(_DWORD *)(BugCheckParameter2 + 40) = v13 != 0 ? 0x104 : 0;
  v34[0] |= 0xD0004uLL;
  v34[3] = 0;
  LODWORD(v34[11]) = 20000;
  *(_DWORD *)((char *)&v34[11] + 6) = 196608;
  PsGetCurrentServerSilo();
  Session = UxQuicCreateSession(BugCheckParameter2, (__int64)v34, v13 != 0 ? 0x104 : 0, (__int64)&v31);
  if ( Session < 0 || (Session = UcpAllocateClientSessionContext(a3, &P), Session < 0) )
  {
LABEL_15:
    v9 = (volatile signed __int32 *)P;
    goto LABEL_16;
  }
  *(_QWORD *)(BugCheckParameter2 + 48) = v31;
  v14 = v31 + 4;
  v15 = _InterlockedIncrement((volatile signed __int32 *)(v31 + 4));
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, v14, 0x40u, v15);
  v16 = BugCheckParameter2;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v16 + 64));
  UcpCoupleSessionContextAndSession(P, BugCheckParameter2);
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(BugCheckParameter2 + 64));
  KeLeaveCriticalRegion();
  v17 = a1 + 8720;
  v18 = *(_QWORD **)(v17 + 8);
  if ( *v18 != v17 )
    __fastfail(3u);
  v19 = (_QWORD *)(BugCheckParameter2 + 8);
  *(_QWORD *)(BugCheckParameter2 + 16) = v18;
  *v19 = v17;
  *v18 = v19;
  v20 = v32;
  *(_QWORD *)(v17 + 8) = v19;
  ExReleasePushLockExclusiveEx(v20, 0);
  KeLeaveCriticalRegion();
  *a5 = P;
  P = 0;
  BugCheckParameter2 = 0;
LABEL_23:
  v22 = (_QWORD *)v31;
  if ( v31 )
  {
    v23 = v31 + 4;
    v24 = _InterlockedDecrement((volatile signed __int32 *)(v31 + 4));
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, v23, 1u, v24);
    if ( !v24 )
    {
      v25 = (ULONG_PTR)(v22 + 4);
      if ( v22[4] || v22[6] || v22[8] )
        UlBugCheckEx(1u, v25, (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x3E7u);
      LOBYTE(v11) = 1;
      UlThreadPoolEnqueueWorkItem(0, v25, UxQuicFreeSession, v11, v22[10], -1);
    }
    v31 = 0;
  }
  v26 = (void *)BugCheckParameter2;
  if ( BugCheckParameter2 )
  {
    v27 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
    if ( UxDebugCheckRefcount && v27 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v26, 1u, v27);
    if ( !v27 )
      UcFreeClientSession(v26);
    BugCheckParameter2 = 0;
  }
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_d(1053, 19, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, (unsigned int)Session);
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x1400bcea4  mov     [rsp-8+arg_18], rbx
0x1400bcea9  push    rbp
0x1400bceaa  push    rsi
0x1400bceab  push    rdi
0x1400bceac  push    r12
0x1400bceae  push    r13
0x1400bceb0  push    r14
0x1400bceb2  push    r15
0x1400bceb4  lea     rbp, [rsp-10h]
0x1400bceb9  sub     rsp, 110h
0x1400bcec0  mov     rax, cs:__security_cookie
0x1400bcec7  xor     rax, rsp
0x1400bceca  mov     [rbp+40h+var_40], rax
0x1400bcece  mov     r12, [rbp+40h+arg_20]
0x1400bced2  xor     r13d, r13d
0x1400bced5  mov     r15, r8
0x1400bced8  mov     [rsp+140h+var_E0], rdx
0x1400bcedd  mov     rsi, rdx
0x1400bcee0  mov     [rsp+140h+BugCheckParameter2], r13
0x1400bcee5  mov     r14, rcx
0x1400bcee8  mov     [rsp+140h+var_F0], r13
0x1400bceed  mov     ebx, r13d
0x1400bcef0  lea     rcx, [rsp+140h+var_D0]; void *
0x1400bcef5  xor     edx, edx; Val
0x1400bcef7  mov     [rsp+140h+P], rbx
0x1400bcefc  mov     r8d, 90h; Size
0x1400bcf02  mov     edi, r9d
0x1400bcf05  call    memset
0x1400bcf0a  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bcf11  jz      short loc_1400BCF3F
0x1400bcf13  mov     [rsp+140h+var_110], r12
0x1400bcf18  lea     edx, [r13+12h]
0x1400bcf1c  mov     qword ptr [rsp+140h+var_118], r15
0x1400bcf21  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bcf28  mov     ecx, 41Dh
0x1400bcf2d  mov     [rsp+140h+var_120], rsi
0x1400bcf32  mov     r9, r14
0x1400bcf35  call    WPP_SF_qqqi
0x1400bcf3a  mov     rbx, [rsp+140h+P]
0x1400bcf3f  mov     [r12], r13
0x1400bcf43  lea     rsi, [r14+2208h]
0x1400bcf4a  mov     [rsp+140h+var_E8], rsi
0x1400bcf4f  mov     ecx, 3
0x1400bcf54  test    dil, 1
0x1400bcf58  jz      short loc_1400BCF67
0x1400bcf5a  xor     r15d, r15d
0x1400bcf5d  mov     esi, 0C000000Dh
0x1400bcf62  jmp     loc_1400BD146
0x1400bcf67  and     dil, 2
0x1400bcf6b  neg     dil
0x1400bcf6e  sbb     ebx, ebx
0x1400bcf70  and     ebx, 104h
0x1400bcf76  call    cs:__imp_KeEnterCriticalRegion
0x1400bcf7d  nop     dword ptr [rax+rax+00h]
0x1400bcf82  xor     edx, edx
0x1400bcf84  mov     rcx, rsi
0x1400bcf87  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400bcf8e  nop     dword ptr [rax+rax+00h]
0x1400bcf93  mov     rcx, r15
0x1400bcf96  mov     r13b, 1
0x1400bcf99  call    UcClientObjectAccessCheck
0x1400bcf9e  mov     esi, eax
0x1400bcfa0  test    eax, eax
0x1400bcfa2  js      loc_1400BD139
0x1400bcfa8  mov     rdx, [rsp+140h+var_E0]
0x1400bcfad  lea     r8, [rsp+140h+BugCheckParameter2]
0x1400bcfb2  mov     rcx, r14
0x1400bcfb5  call    UcpAllocateClientSession
0x1400bcfba  mov     esi, eax
0x1400bcfbc  test    eax, eax
0x1400bcfbe  js      loc_1400BD139
0x1400bcfc4  mov     rax, [rsp+140h+BugCheckParameter2]
0x1400bcfc9  mov     [rax+28h], ebx
0x1400bcfcc  or      [rsp+140h+var_D0], 0D0004h
0x1400bcfd5  mov     [rbp+40h+var_B8], 0
0x1400bcfdd  mov     [rbp+40h+var_78], 4E20h
0x1400bcfe4  mov     [rbp+40h+var_72], 30000h
0x1400bcfeb  call    cs:__imp_PsGetCurrentServerSilo
0x1400bcff2  nop     dword ptr [rax+rax+00h]
0x1400bcff7  mov     rcx, [rsp+140h+BugCheckParameter2]; BugCheckParameter2
0x1400bcffc  mov     r8, r14
0x1400bcfff  mov     r9, rax
0x1400bd002  xor     edx, edx
0x1400bd004  lea     rax, [rsp+140h+var_F0]
0x1400bd009  mov     [rsp+140h+var_110], rax; __int64
0x1400bd00e  lea     rax, [rsp+140h+var_D0]
0x1400bd013  mov     [rsp+140h+var_118], ebx; int
0x1400bd017  mov     [rsp+140h+var_120], rax; __int64
0x1400bd01c  call    UxQuicCreateSession
0x1400bd021  mov     esi, eax
0x1400bd023  test    eax, eax
0x1400bd025  js      loc_1400BD139
0x1400bd02b  lea     rdx, [rsp+140h+P]
0x1400bd030  mov     rcx, r15
0x1400bd033  call    UcpAllocateClientSessionContext
0x1400bd038  xor     r15d, r15d
0x1400bd03b  mov     esi, eax
0x1400bd03d  test    eax, eax
0x1400bd03f  js      loc_1400BD13C
0x1400bd045  mov     rax, [rsp+140h+var_F0]
0x1400bd04a  mov     rcx, [rsp+140h+BugCheckParameter2]
0x1400bd04f  mov     [rcx+30h], rax
0x1400bd053  lea     eax, [r15+1]
0x1400bd057  mov     rdx, [rsp+140h+var_F0]
0x1400bd05c  add     rdx, 4; BugCheckParameter2
0x1400bd060  lock xadd [rdx], eax
0x1400bd064  inc     eax
0x1400bd066  or      edi, 0FFFFFFFFh
0x1400bd069  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd070  jz      short loc_1400BD086
0x1400bd072  cmp     eax, edi
0x1400bd074  jg      short loc_1400BD086
0x1400bd076  movsxd  r9, eax; BugCheckParameter4
0x1400bd079  lea     ecx, [rdi+4]; BugCheckParameter1
0x1400bd07c  lea     r8d, [r15+40h]; BugCheckParameter3
0x1400bd080  call    UlBugCheckEx
0x1400bd086  mov     rbx, [rsp+140h+BugCheckParameter2]
0x1400bd08b  call    cs:__imp_KeEnterCriticalRegion
0x1400bd092  nop     dword ptr [rax+rax+00h]
0x1400bd097  mov     rcx, [rbx+40h]
0x1400bd09b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bd0a2  nop     dword ptr [rax+rax+00h]
0x1400bd0a7  mov     rdx, [rsp+140h+BugCheckParameter2]
0x1400bd0ac  mov     rcx, [rsp+140h+P]
0x1400bd0b1  call    UcpCoupleSessionContextAndSession
0x1400bd0b6  mov     rcx, [rsp+140h+BugCheckParameter2]
0x1400bd0bb  mov     rcx, [rcx+40h]
0x1400bd0bf  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bd0c6  nop     dword ptr [rax+rax+00h]
0x1400bd0cb  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd0d2  nop     dword ptr [rax+rax+00h]
0x1400bd0d7  add     r14, 2210h
0x1400bd0de  mov     rcx, [r14+8]
0x1400bd0e2  cmp     [rcx], r14
0x1400bd0e5  jz      short loc_1400BD0EE
0x1400bd0e7  mov     ecx, 3
0x1400bd0ec  int     29h; Win8: RtlFailFast(ecx)
0x1400bd0ee  mov     rax, [rsp+140h+BugCheckParameter2]
0x1400bd0f3  xor     edx, edx
0x1400bd0f5  add     rax, 8
0x1400bd0f9  mov     [rax+8], rcx
0x1400bd0fd  mov     [rax], r14
0x1400bd100  mov     [rcx], rax
0x1400bd103  mov     rcx, [rsp+140h+var_E8]
0x1400bd108  mov     [r14+8], rax
0x1400bd10c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd113  nop     dword ptr [rax+rax+00h]
0x1400bd118  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd11f  nop     dword ptr [rax+rax+00h]
0x1400bd124  mov     rax, [rsp+140h+P]
0x1400bd129  mov     [r12], rax
0x1400bd12d  mov     [rsp+140h+P], r15
0x1400bd132  mov     [rsp+140h+BugCheckParameter2], r15
0x1400bd137  jmp     short loc_1400BD1A6
0x1400bd139  xor     r15d, r15d
0x1400bd13c  mov     rbx, [rsp+140h+P]
0x1400bd141  mov     ecx, 3; BugCheckParameter1
0x1400bd146  or      edi, 0FFFFFFFFh
0x1400bd149  test    rbx, rbx
0x1400bd14c  jz      short loc_1400BD182
0x1400bd14e  mov     eax, edi
0x1400bd150  lock xadd [rbx], eax
0x1400bd154  add     eax, edi
0x1400bd156  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd15d  jz      short loc_1400BD173
0x1400bd15f  cmp     eax, edi
0x1400bd161  jg      short loc_1400BD173
0x1400bd163  movsxd  r9, eax; BugCheckParameter4
0x1400bd166  lea     r8d, [rdi+2]; BugCheckParameter3
0x1400bd16a  mov     rdx, rbx; BugCheckParameter2
0x1400bd16d  call    UlBugCheckEx
0x1400bd173  mov     rcx, [rsp+140h+P]; P
0x1400bd178  call    UcpFreeClientSessionContext
0x1400bd17d  mov     [rsp+140h+P], r15
0x1400bd182  test    r13b, r13b
0x1400bd185  jz      short loc_1400BD1A6
0x1400bd187  mov     rcx, [rsp+140h+var_E8]
0x1400bd18c  xor     edx, edx
0x1400bd18e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd195  nop     dword ptr [rax+rax+00h]
0x1400bd19a  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd1a1  nop     dword ptr [rax+rax+00h]
0x1400bd1a6  mov     rcx, [rsp+140h+var_F0]
0x1400bd1ab  test    rcx, rcx
0x1400bd1ae  jz      short loc_1400BD21B
0x1400bd1b0  lea     rdx, [rcx+4]; BugCheckParameter2
0x1400bd1b4  mov     eax, edi
0x1400bd1b6  lock xadd [rdx], eax
0x1400bd1ba  add     eax, edi
0x1400bd1bc  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd1c3  jz      short loc_1400BD1DB
0x1400bd1c5  cmp     eax, edi
0x1400bd1c7  jg      short loc_1400BD1DB
0x1400bd1c9  mov     ecx, 3; BugCheckParameter1
0x1400bd1ce  movsxd  r9, eax; BugCheckParameter4
0x1400bd1d1  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400bd1d5  call    UlBugCheckEx
0x1400bd1db  test    eax, eax
0x1400bd1dd  jnz     short loc_1400BD216
0x1400bd1df  lea     rdx, [rcx+20h]; BugCheckParameter2
0x1400bd1e3  cmp     [rdx], r15
0x1400bd1e6  jnz     short loc_1400BD250
0x1400bd1e8  cmp     [rdx+10h], r15
0x1400bd1ec  jnz     short loc_1400BD250
0x1400bd1ee  cmp     [rdx+20h], r15
0x1400bd1f2  jnz     short loc_1400BD250
0x1400bd1f4  mov     rax, [rcx+50h]
0x1400bd1f8  lea     r8, UxQuicFreeSession
0x1400bd1ff  xor     ecx, ecx
0x1400bd201  mov     [rsp+140h+var_118], 0FFFFFFFFh
0x1400bd209  mov     r9b, 1
0x1400bd20c  mov     [rsp+140h+var_120], rax
0x1400bd211  call    UlThreadPoolEnqueueWorkItem
0x1400bd216  mov     [rsp+140h+var_F0], r15
0x1400bd21b  mov     rcx, [rsp+140h+BugCheckParameter2]; P
0x1400bd220  test    rcx, rcx
0x1400bd223  jz      short loc_1400BD276
0x1400bd225  mov     eax, edi
0x1400bd227  lock xadd [rcx], eax
0x1400bd22b  add     eax, edi
0x1400bd22d  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd234  jz      short loc_1400BD268
0x1400bd236  cmp     eax, edi
0x1400bd238  jg      short loc_1400BD268
0x1400bd23a  mov     r8d, 1; BugCheckParameter3
0x1400bd240  movsxd  r9, eax; BugCheckParameter4
0x1400bd243  mov     rdx, rcx; BugCheckParameter2
0x1400bd246  lea     ecx, [r8+2]; BugCheckParameter1
0x1400bd24a  call    UlBugCheckEx
0x1400bd250  mov     r9d, 3E7h; BugCheckParameter4
0x1400bd256  lea     r8, aMinioHttpSysQu; "minio\\http\\sys\\quicconn.h"
0x1400bd25d  mov     ecx, 1; BugCheckParameter1
0x1400bd262  call    UlBugCheckEx
0x1400bd268  test    eax, eax
0x1400bd26a  jnz     short loc_1400BD271
0x1400bd26c  call    UcFreeClientSession
0x1400bd271  mov     [rsp+140h+BugCheckParameter2], r15
0x1400bd276  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd27d  jz      short loc_1400BD298
0x1400bd27f  mov     edx, 13h
0x1400bd284  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd28b  mov     ecx, 41Dh
0x1400bd290  mov     r9d, esi
0x1400bd293  call    WPP_SF_d
0x1400bd298  mov     eax, esi
0x1400bd29a  mov     rcx, [rbp+40h+var_40]
0x1400bd29e  xor     rcx, rsp; StackCookie
0x1400bd2a1  call    __security_check_cookie
0x1400bd2a6  mov     rbx, [rsp+140h+arg_18]
0x1400bd2ae  add     rsp, 110h
0x1400bd2b5  pop     r15
0x1400bd2b7  pop     r14
0x1400bd2b9  pop     r13
0x1400bd2bb  pop     r12
0x1400bd2bd  pop     rdi
0x1400bd2be  pop     rsi
0x1400bd2bf  pop     rbp
0x1400bd2c0  retn
```
