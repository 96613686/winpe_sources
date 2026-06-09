# UcpCreateClientSession

- ea: `0x1400bcdc4`
- end: `0x1400bd1e2`
- name: `UcpCreateClientSession`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14015bdd4`

## callees

- `0x14000a350`
- `0x140022610`
- `0x1400bcdc4`
- `0x1400bd1e8`
- `0x1400bd7e4`
- `0x1401095bc`
- `0x14012fc88`
- `0x14015beb8`
- `0x14015c530`
- `0x14015c688`
- `0x140167810`
- `0x140167c40`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400bcf0b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400bcf0b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bcfdf`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bcfdf`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bcfbb`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bcfbb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcfeb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd038`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd0ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcfeb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd038`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd0ba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd02c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd0ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd02c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd0ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bcea7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bcea7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bce96`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcfab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bce96`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcfab`

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
  int v29[2]; // [rsp+28h] [rbp-D8h]
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-C0h] BYREF
  PVOID P; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35[18]; // [rsp+70h] [rbp-90h] BYREF

  v5 = 0;
  v34 = a2;
  BugCheckParameter2 = 0;
  v32 = 0;
  v9 = 0;
  P = 0;
  memset(v35, 0, sizeof(v35));
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
  {
    WPP_SF_qqqi(1053, 18, WPP_3de096d7bee33433074a41eaae020079_Traceguids, a1, a2, a3, a5);
    v9 = (volatile signed __int32 *)P;
  }
  *a5 = 0;
  v33 = a1 + 8712;
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
      ExReleasePushLockExclusiveEx(v33, 0);
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
  Session = UcpAllocateClientSession(a1, v34, &BugCheckParameter2);
  if ( Session < 0 )
    goto LABEL_15;
  *(_DWORD *)(BugCheckParameter2 + 40) = v13 != 0 ? 0x104 : 0;
  v35[0] |= 0xD0004uLL;
  v35[3] = 0;
  LODWORD(v35[11]) = 20000;
  *(_DWORD *)((char *)&v35[11] + 6) = 196608;
  PsGetCurrentServerSilo();
  Session = UxQuicCreateSession(BugCheckParameter2, (__int64)v35, v13 != 0 ? 0x104 : 0, (__int64)&v32);
  if ( Session < 0 || (Session = UcpAllocateClientSessionContext(a3, &P), Session < 0) )
  {
LABEL_15:
    v9 = (volatile signed __int32 *)P;
    goto LABEL_16;
  }
  *(_QWORD *)(BugCheckParameter2 + 48) = v32;
  v14 = v32 + 4;
  v15 = _InterlockedIncrement((volatile signed __int32 *)(v32 + 4));
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
  v20 = v33;
  *(_QWORD *)(v17 + 8) = v19;
  ExReleasePushLockExclusiveEx(v20, 0);
  KeLeaveCriticalRegion();
  *a5 = P;
  P = 0;
  BugCheckParameter2 = 0;
LABEL_23:
  v22 = (_QWORD *)v32;
  if ( v32 )
  {
    v23 = v32 + 4;
    v24 = _InterlockedDecrement((volatile signed __int32 *)(v32 + 4));
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, v23, 1u, v24);
    if ( !v24 )
    {
      v25 = (ULONG_PTR)(v22 + 4);
      if ( v22[4] || v22[6] || v22[8] )
        UlBugCheckEx(1u, v25, (ULONG_PTR)"minio\\http\\sys\\quicconn.h", 0x3E7u);
      v29[0] = -1;
      LOBYTE(v11) = 1;
      UlThreadPoolEnqueueWorkItem(0, v25, UxQuicFreeSession, v11, v22[10], *(_QWORD *)v29);
    }
    v32 = 0;
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
    WPP_SF_d(1053, 19, WPP_3de096d7bee33433074a41eaae020079_Traceguids, (unsigned int)Session);
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x1400bcdc4  mov     [rsp-8+arg_18], rbx
0x1400bcdc9  push    rbp
0x1400bcdca  push    rsi
0x1400bcdcb  push    rdi
0x1400bcdcc  push    r12
0x1400bcdce  push    r13
0x1400bcdd0  push    r14
0x1400bcdd2  push    r15
0x1400bcdd4  lea     rbp, [rsp-10h]
0x1400bcdd9  sub     rsp, 110h
0x1400bcde0  mov     rax, cs:__security_cookie
0x1400bcde7  xor     rax, rsp
0x1400bcdea  mov     [rbp+40h+var_40], rax
0x1400bcdee  mov     r12, [rbp+40h+arg_20]
0x1400bcdf2  xor     r13d, r13d
0x1400bcdf5  mov     r15, r8
0x1400bcdf8  mov     [rsp+140h+var_E0], rdx
0x1400bcdfd  mov     rsi, rdx
0x1400bce00  mov     [rsp+140h+BugCheckParameter2], r13
0x1400bce05  mov     r14, rcx
0x1400bce08  mov     [rsp+140h+var_F0], r13
0x1400bce0d  mov     ebx, r13d
0x1400bce10  lea     rcx, [rsp+140h+var_D0]; void *
0x1400bce15  xor     edx, edx; Val
0x1400bce17  mov     [rsp+140h+P], rbx
0x1400bce1c  mov     r8d, 90h; Size
0x1400bce22  mov     edi, r9d
0x1400bce25  call    memset
0x1400bce2a  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bce31  jz      short loc_1400BCE5F
0x1400bce33  mov     [rsp+140h+var_110], r12
0x1400bce38  lea     edx, [r13+12h]
0x1400bce3c  mov     qword ptr [rsp+140h+var_118], r15
0x1400bce41  lea     r8, WPP_3de096d7bee33433074a41eaae020079_Traceguids
0x1400bce48  mov     ecx, 41Dh
0x1400bce4d  mov     [rsp+140h+var_120], rsi
0x1400bce52  mov     r9, r14
0x1400bce55  call    WPP_SF_qqqi
0x1400bce5a  mov     rbx, [rsp+140h+P]
0x1400bce5f  mov     [r12], r13
0x1400bce63  lea     rsi, [r14+2208h]
0x1400bce6a  mov     [rsp+140h+var_E8], rsi
0x1400bce6f  mov     ecx, 3
0x1400bce74  test    dil, 1
0x1400bce78  jz      short loc_1400BCE87
0x1400bce7a  xor     r15d, r15d
0x1400bce7d  mov     esi, 0C000000Dh
0x1400bce82  jmp     loc_1400BD066
0x1400bce87  and     dil, 2
0x1400bce8b  neg     dil
0x1400bce8e  sbb     ebx, ebx
0x1400bce90  and     ebx, 104h
0x1400bce96  call    cs:__imp_KeEnterCriticalRegion
0x1400bce9d  nop     dword ptr [rax+rax+00h]
0x1400bcea2  xor     edx, edx
0x1400bcea4  mov     rcx, rsi
0x1400bcea7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400bceae  nop     dword ptr [rax+rax+00h]
0x1400bceb3  mov     rcx, r15
0x1400bceb6  mov     r13b, 1
0x1400bceb9  call    UcClientObjectAccessCheck
0x1400bcebe  mov     esi, eax
0x1400bcec0  test    eax, eax
0x1400bcec2  js      loc_1400BD059
0x1400bcec8  mov     rdx, [rsp+140h+var_E0]
0x1400bcecd  lea     r8, [rsp+140h+BugCheckParameter2]
0x1400bced2  mov     rcx, r14
0x1400bced5  call    UcpAllocateClientSession
0x1400bceda  mov     esi, eax
0x1400bcedc  test    eax, eax
0x1400bcede  js      loc_1400BD059
0x1400bcee4  mov     rax, [rsp+140h+BugCheckParameter2]
0x1400bcee9  mov     [rax+28h], ebx
0x1400bceec  or      [rsp+140h+var_D0], 0D0004h
0x1400bcef5  mov     [rbp+40h+var_B8], 0
0x1400bcefd  mov     [rbp+40h+var_78], 4E20h
0x1400bcf04  mov     [rbp+40h+var_72], 30000h
0x1400bcf0b  call    cs:__imp_PsGetCurrentServerSilo
0x1400bcf12  nop     dword ptr [rax+rax+00h]
0x1400bcf17  mov     rcx, [rsp+140h+BugCheckParameter2]; BugCheckParameter2
0x1400bcf1c  mov     r8, r14
0x1400bcf1f  mov     r9, rax
0x1400bcf22  xor     edx, edx
0x1400bcf24  lea     rax, [rsp+140h+var_F0]
0x1400bcf29  mov     [rsp+140h+var_110], rax; __int64
0x1400bcf2e  lea     rax, [rsp+140h+var_D0]
0x1400bcf33  mov     [rsp+140h+var_118], ebx; int
0x1400bcf37  mov     [rsp+140h+var_120], rax; __int64
0x1400bcf3c  call    UxQuicCreateSession
0x1400bcf41  mov     esi, eax
0x1400bcf43  test    eax, eax
0x1400bcf45  js      loc_1400BD059
0x1400bcf4b  lea     rdx, [rsp+140h+P]
0x1400bcf50  mov     rcx, r15
0x1400bcf53  call    UcpAllocateClientSessionContext
0x1400bcf58  xor     r15d, r15d
0x1400bcf5b  mov     esi, eax
0x1400bcf5d  test    eax, eax
0x1400bcf5f  js      loc_1400BD05C
0x1400bcf65  mov     rax, [rsp+140h+var_F0]
0x1400bcf6a  mov     rcx, [rsp+140h+BugCheckParameter2]
0x1400bcf6f  mov     [rcx+30h], rax
0x1400bcf73  lea     eax, [r15+1]
0x1400bcf77  mov     rdx, [rsp+140h+var_F0]
0x1400bcf7c  add     rdx, 4; BugCheckParameter2
0x1400bcf80  lock xadd [rdx], eax
0x1400bcf84  inc     eax
0x1400bcf86  or      edi, 0FFFFFFFFh
0x1400bcf89  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bcf90  jz      short loc_1400BCFA6
0x1400bcf92  cmp     eax, edi
0x1400bcf94  jg      short loc_1400BCFA6
0x1400bcf96  movsxd  r9, eax; BugCheckParameter4
0x1400bcf99  lea     ecx, [rdi+4]; BugCheckParameter1
0x1400bcf9c  lea     r8d, [r15+40h]; BugCheckParameter3
0x1400bcfa0  call    UlBugCheckEx
0x1400bcfa6  mov     rbx, [rsp+140h+BugCheckParameter2]
0x1400bcfab  call    cs:__imp_KeEnterCriticalRegion
0x1400bcfb2  nop     dword ptr [rax+rax+00h]
0x1400bcfb7  mov     rcx, [rbx+40h]
0x1400bcfbb  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bcfc2  nop     dword ptr [rax+rax+00h]
0x1400bcfc7  mov     rdx, [rsp+140h+BugCheckParameter2]
0x1400bcfcc  mov     rcx, [rsp+140h+P]
0x1400bcfd1  call    UcpCoupleSessionContextAndSession
0x1400bcfd6  mov     rcx, [rsp+140h+BugCheckParameter2]
0x1400bcfdb  mov     rcx, [rcx+40h]
0x1400bcfdf  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bcfe6  nop     dword ptr [rax+rax+00h]
0x1400bcfeb  call    cs:__imp_KeLeaveCriticalRegion
0x1400bcff2  nop     dword ptr [rax+rax+00h]
0x1400bcff7  add     r14, 2210h
0x1400bcffe  mov     rcx, [r14+8]
0x1400bd002  cmp     [rcx], r14
0x1400bd005  jz      short loc_1400BD00E
0x1400bd007  mov     ecx, 3
0x1400bd00c  int     29h; Win8: RtlFailFast(ecx)
0x1400bd00e  mov     rax, [rsp+140h+BugCheckParameter2]
0x1400bd013  xor     edx, edx
0x1400bd015  add     rax, 8
0x1400bd019  mov     [rax+8], rcx
0x1400bd01d  mov     [rax], r14
0x1400bd020  mov     [rcx], rax
0x1400bd023  mov     rcx, [rsp+140h+var_E8]
0x1400bd028  mov     [r14+8], rax
0x1400bd02c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd033  nop     dword ptr [rax+rax+00h]
0x1400bd038  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd03f  nop     dword ptr [rax+rax+00h]
0x1400bd044  mov     rax, [rsp+140h+P]
0x1400bd049  mov     [r12], rax
0x1400bd04d  mov     [rsp+140h+P], r15
0x1400bd052  mov     [rsp+140h+BugCheckParameter2], r15
0x1400bd057  jmp     short loc_1400BD0C6
0x1400bd059  xor     r15d, r15d
0x1400bd05c  mov     rbx, [rsp+140h+P]
0x1400bd061  mov     ecx, 3; BugCheckParameter1
0x1400bd066  or      edi, 0FFFFFFFFh
0x1400bd069  test    rbx, rbx
0x1400bd06c  jz      short loc_1400BD0A2
0x1400bd06e  mov     eax, edi
0x1400bd070  lock xadd [rbx], eax
0x1400bd074  add     eax, edi
0x1400bd076  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd07d  jz      short loc_1400BD093
0x1400bd07f  cmp     eax, edi
0x1400bd081  jg      short loc_1400BD093
0x1400bd083  movsxd  r9, eax; BugCheckParameter4
0x1400bd086  lea     r8d, [rdi+2]; BugCheckParameter3
0x1400bd08a  mov     rdx, rbx; BugCheckParameter2
0x1400bd08d  call    UlBugCheckEx
0x1400bd093  mov     rcx, [rsp+140h+P]; P
0x1400bd098  call    UcpFreeClientSessionContext
0x1400bd09d  mov     [rsp+140h+P], r15
0x1400bd0a2  test    r13b, r13b
0x1400bd0a5  jz      short loc_1400BD0C6
0x1400bd0a7  mov     rcx, [rsp+140h+var_E8]
0x1400bd0ac  xor     edx, edx
0x1400bd0ae  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd0b5  nop     dword ptr [rax+rax+00h]
0x1400bd0ba  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd0c1  nop     dword ptr [rax+rax+00h]
0x1400bd0c6  mov     rcx, [rsp+140h+var_F0]
0x1400bd0cb  test    rcx, rcx
0x1400bd0ce  jz      short loc_1400BD13B
0x1400bd0d0  lea     rdx, [rcx+4]; BugCheckParameter2
0x1400bd0d4  mov     eax, edi
0x1400bd0d6  lock xadd [rdx], eax
0x1400bd0da  add     eax, edi
0x1400bd0dc  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd0e3  jz      short loc_1400BD0FB
0x1400bd0e5  cmp     eax, edi
0x1400bd0e7  jg      short loc_1400BD0FB
0x1400bd0e9  mov     ecx, 3; BugCheckParameter1
0x1400bd0ee  movsxd  r9, eax; BugCheckParameter4
0x1400bd0f1  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400bd0f5  call    UlBugCheckEx
0x1400bd0fb  test    eax, eax
0x1400bd0fd  jnz     short loc_1400BD136
0x1400bd0ff  lea     rdx, [rcx+20h]; BugCheckParameter2
0x1400bd103  cmp     [rdx], r15
0x1400bd106  jnz     short loc_1400BD170
0x1400bd108  cmp     [rdx+10h], r15
0x1400bd10c  jnz     short loc_1400BD170
0x1400bd10e  cmp     [rdx+20h], r15
0x1400bd112  jnz     short loc_1400BD170
0x1400bd114  mov     rax, [rcx+50h]
0x1400bd118  lea     r8, UxQuicFreeSession
0x1400bd11f  xor     ecx, ecx
0x1400bd121  mov     [rsp+140h+var_118], 0FFFFFFFFh
0x1400bd129  mov     r9b, 1
0x1400bd12c  mov     [rsp+140h+var_120], rax
0x1400bd131  call    UlThreadPoolEnqueueWorkItem
0x1400bd136  mov     [rsp+140h+var_F0], r15
0x1400bd13b  mov     rcx, [rsp+140h+BugCheckParameter2]; P
0x1400bd140  test    rcx, rcx
0x1400bd143  jz      short loc_1400BD196
0x1400bd145  mov     eax, edi
0x1400bd147  lock xadd [rcx], eax
0x1400bd14b  add     eax, edi
0x1400bd14d  cmp     cs:UxDebugCheckRefcount, r15b
0x1400bd154  jz      short loc_1400BD188
0x1400bd156  cmp     eax, edi
0x1400bd158  jg      short loc_1400BD188
0x1400bd15a  mov     r8d, 1; BugCheckParameter3
0x1400bd160  movsxd  r9, eax; BugCheckParameter4
0x1400bd163  mov     rdx, rcx; BugCheckParameter2
0x1400bd166  lea     ecx, [r8+2]; BugCheckParameter1
0x1400bd16a  call    UlBugCheckEx
0x1400bd170  mov     r9d, 3E7h; BugCheckParameter4
0x1400bd176  lea     r8, aMinioHttpSysQu; "minio\\http\\sys\\quicconn.h"
0x1400bd17d  mov     ecx, 1; BugCheckParameter1
0x1400bd182  call    UlBugCheckEx
0x1400bd188  test    eax, eax
0x1400bd18a  jnz     short loc_1400BD191
0x1400bd18c  call    UcFreeClientSession
0x1400bd191  mov     [rsp+140h+BugCheckParameter2], r15
0x1400bd196  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd19d  jz      short loc_1400BD1B8
0x1400bd19f  mov     edx, 13h
0x1400bd1a4  lea     r8, WPP_3de096d7bee33433074a41eaae020079_Traceguids
0x1400bd1ab  mov     ecx, 41Dh
0x1400bd1b0  mov     r9d, esi
0x1400bd1b3  call    WPP_SF_d
0x1400bd1b8  mov     eax, esi
0x1400bd1ba  mov     rcx, [rbp+40h+var_40]
0x1400bd1be  xor     rcx, rsp; StackCookie
0x1400bd1c1  call    __security_check_cookie
0x1400bd1c6  mov     rbx, [rsp+140h+arg_18]
0x1400bd1ce  add     rsp, 110h
0x1400bd1d5  pop     r15
0x1400bd1d7  pop     r14
0x1400bd1d9  pop     r13
0x1400bd1db  pop     r12
0x1400bd1dd  pop     rdi
0x1400bd1de  pop     rsi
0x1400bd1df  pop     rbp
0x1400bd1e0  retn
```
