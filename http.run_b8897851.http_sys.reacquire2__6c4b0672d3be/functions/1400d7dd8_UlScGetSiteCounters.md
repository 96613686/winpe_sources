# UlScGetSiteCounters

- ea: `0x1400d7dd8`
- end: `0x1400d7ff6`
- name: `UlScGetSiteCounters`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140016960`

## callees

- `0x14000a350`
- `0x1400b1cf8`
- `0x1400d742c`
- `0x1400d7dd8`
- `0x1400d8428`
- `0x1400d8510`
- `0x1401d9dd8`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7e5c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7e5c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7f3c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7f3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7f2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7f48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7f2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7f48`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7ea1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7ea1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7f1f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7f1f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7e47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7e88`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7e47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7e88`

## pseudocode

```c
__int64 __fastcall UlScGetSiteCounters(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // ebp
  __int64 v9; // rsi
  unsigned int *v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rbx
  int ServerSessionFromId; // edi
  unsigned int v14; // eax
  char *v15; // rax
  char *v16; // r12
  char *v17; // rdx
  int v18; // eax
  PVOID P; // [rsp+90h] [rbp+8h] BYREF

  v5 = a4;
  P = 0;
  v9 = a3;
  v10 = a5;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqqdq(1049, 27, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids, a1, a2, a3, a4, a5);
  *v10 = 0;
  v11 = *(_QWORD *)(a1 + 56);
  KeEnterCriticalRegion();
  v12 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v11 + 1368), 0);
  ServerSessionFromId = UlGetServerSessionFromId(a1, a2, &P);
  if ( ServerSessionFromId >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1408LL, 0);
    v14 = 72 * *((_DWORD *)P + 22);
    if ( a3 && v14 <= v5 )
    {
      v15 = (char *)P + 72;
      v16 = (char *)*((_QWORD *)P + 9);
      while ( v16 != v15 && v5 >= 0x48 )
      {
        UlpCopyUrlGroupCounters(v16 + 16, v9);
        UlpScResetSiteCounters(v16 - 8);
        v9 += 72;
        v16 = *(char **)v16;
        v5 -= 72;
        v15 = (char *)P + 72;
      }
    }
    else
    {
      *v10 = v14;
      ServerSessionFromId = -2147483643;
    }
    ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1408LL, 0);
    KeLeaveCriticalRegion();
  }
  ExReleaseCacheAwarePushLockSharedEx(v12, 0);
  KeLeaveCriticalRegion();
  if ( P )
  {
    v17 = (char *)P + 4;
    v18 = _InterlockedDecrement((volatile signed __int32 *)P + 1);
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v17, 0xBu, v18);
    if ( !v18 )
      UlFreeServerSession(P);
    P = 0;
  }
  if ( ServerSessionFromId >= 0 )
    *v10 = v9 - a3;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLd(1049, 28, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids, a3, *v10, ServerSessionFromId);
  return (unsigned int)ServerSessionFromId;
}

```

## disassembly

```asm
0x1400d7dd8  mov     rax, rsp
0x1400d7ddb  push    rbx
0x1400d7ddc  push    rbp
0x1400d7ddd  push    rsi
0x1400d7dde  push    rdi
0x1400d7ddf  push    r12
0x1400d7de1  push    r13
0x1400d7de3  push    r14
0x1400d7de5  push    r15
0x1400d7de7  sub     rsp, 48h
0x1400d7deb  mov     ebp, r9d
0x1400d7dee  mov     qword ptr [rax+8], 0
0x1400d7df6  mov     r15, r8
0x1400d7df9  mov     rdi, rdx
0x1400d7dfc  mov     r13, rcx
0x1400d7dff  mov     rsi, r8
0x1400d7e02  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7e09  mov     r14, [rsp+88h+arg_20]
0x1400d7e11  jz      short loc_1400D7E3C
0x1400d7e13  mov     [rax-50h], r14
0x1400d7e17  mov     edx, 1Bh
0x1400d7e1c  mov     [rax-58h], r9d
0x1400d7e20  mov     ecx, 419h
0x1400d7e25  mov     [rax-60h], r8
0x1400d7e29  mov     r9, r13
0x1400d7e2c  lea     r8, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids
0x1400d7e33  mov     [rax-68h], rdi
0x1400d7e37  call    WPP_SF_qqqdq
0x1400d7e3c  mov     dword ptr [r14], 0
0x1400d7e43  mov     rbx, [r13+38h]
0x1400d7e47  call    cs:__imp_KeEnterCriticalRegion
0x1400d7e4e  nop     dword ptr [rax+rax+00h]
0x1400d7e53  mov     rcx, [rbx+558h]
0x1400d7e5a  xor     edx, edx
0x1400d7e5c  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d7e63  nop     dword ptr [rax+rax+00h]
0x1400d7e68  lea     r8, [rsp+88h+P]
0x1400d7e70  mov     rdx, rdi
0x1400d7e73  mov     rcx, r13
0x1400d7e76  mov     rbx, rax
0x1400d7e79  call    UlGetServerSessionFromId
0x1400d7e7e  mov     edi, eax
0x1400d7e80  test    eax, eax
0x1400d7e82  js      loc_1400D7F37
0x1400d7e88  call    cs:__imp_KeEnterCriticalRegion
0x1400d7e8f  nop     dword ptr [rax+rax+00h]
0x1400d7e94  mov     rcx, [r13+38h]
0x1400d7e98  xor     edx, edx
0x1400d7e9a  add     rcx, 580h
0x1400d7ea1  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400d7ea8  nop     dword ptr [rax+rax+00h]
0x1400d7ead  mov     rdx, [rsp+88h+P]
0x1400d7eb5  mov     ecx, [rdx+58h]
0x1400d7eb8  lea     eax, [rcx+rcx*8]
0x1400d7ebb  shl     eax, 3
0x1400d7ebe  test    r15, r15
0x1400d7ec1  jz      short loc_1400D7F0A
0x1400d7ec3  cmp     eax, ebp
0x1400d7ec5  ja      short loc_1400D7F0A
0x1400d7ec7  lea     rax, [rdx+48h]
0x1400d7ecb  mov     r12, [rax]
0x1400d7ece  jmp     short loc_1400D7F03
0x1400d7ed0  cmp     ebp, 48h ; 'H'
0x1400d7ed3  jb      short loc_1400D7F12
0x1400d7ed5  lea     rcx, [r12+10h]
0x1400d7eda  mov     rdx, rsi
0x1400d7edd  call    UlpCopyUrlGroupCounters
0x1400d7ee2  lea     rcx, [r12-8]
0x1400d7ee7  call    UlpScResetSiteCounters
0x1400d7eec  mov     rax, [rsp+88h+P]
0x1400d7ef4  add     rsi, 48h ; 'H'
0x1400d7ef8  mov     r12, [r12]
0x1400d7efc  add     ebp, 0FFFFFFB8h
0x1400d7eff  add     rax, 48h ; 'H'
0x1400d7f03  cmp     r12, rax
0x1400d7f06  jnz     short loc_1400D7ED0
0x1400d7f08  jmp     short loc_1400D7F12
0x1400d7f0a  mov     [r14], eax
0x1400d7f0d  mov     edi, 80000005h
0x1400d7f12  mov     rcx, [r13+38h]
0x1400d7f16  xor     edx, edx
0x1400d7f18  add     rcx, 580h
0x1400d7f1f  call    cs:__imp_ExReleasePushLockSharedEx
0x1400d7f26  nop     dword ptr [rax+rax+00h]
0x1400d7f2b  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7f32  nop     dword ptr [rax+rax+00h]
0x1400d7f37  xor     edx, edx
0x1400d7f39  mov     rcx, rbx
0x1400d7f3c  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d7f43  nop     dword ptr [rax+rax+00h]
0x1400d7f48  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7f4f  nop     dword ptr [rax+rax+00h]
0x1400d7f54  mov     rdx, [rsp+88h+P]
0x1400d7f5c  test    rdx, rdx
0x1400d7f5f  jz      short loc_1400D7FAB
0x1400d7f61  add     rdx, 4; BugCheckParameter2
0x1400d7f65  or      eax, 0FFFFFFFFh
0x1400d7f68  lock xadd [rdx], eax
0x1400d7f6c  dec     eax
0x1400d7f6e  cmp     cs:UxDebugCheckRefcount, 0
0x1400d7f75  jz      short loc_1400D7F8E
0x1400d7f77  cmp     eax, 0FFFFFFFFh
0x1400d7f7a  jg      short loc_1400D7F8E
0x1400d7f7c  mov     ecx, 3; BugCheckParameter1
0x1400d7f81  movsxd  r9, eax; BugCheckParameter4
0x1400d7f84  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d7f88  call    UlBugCheckEx
0x1400d7f8e  test    eax, eax
0x1400d7f90  jnz     short loc_1400D7F9F
0x1400d7f92  mov     rcx, [rsp+88h+P]; P
0x1400d7f9a  call    UlFreeServerSession
0x1400d7f9f  mov     [rsp+88h+P], 0
0x1400d7fab  test    edi, edi
0x1400d7fad  js      short loc_1400D7FB5
0x1400d7faf  sub     esi, r15d
0x1400d7fb2  mov     [r14], esi
0x1400d7fb5  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7fbc  jz      short loc_1400D7FE2
0x1400d7fbe  mov     eax, [r14]
0x1400d7fc1  lea     r8, WPP_f3e171eb2e923c9a4ea2a4f5cdc0687b_Traceguids
0x1400d7fc8  mov     edx, 1Ch
0x1400d7fcd  mov     [rsp+88h+var_60], edi
0x1400d7fd1  mov     ecx, 419h
0x1400d7fd6  mov     [rsp+88h+var_68], eax
0x1400d7fda  mov     r9, r15
0x1400d7fdd  call    WPP_SF_qLd
0x1400d7fe2  mov     eax, edi
0x1400d7fe4  add     rsp, 48h
0x1400d7fe8  pop     r15
0x1400d7fea  pop     r14
0x1400d7fec  pop     r13
0x1400d7fee  pop     r12
0x1400d7ff0  pop     rdi
0x1400d7ff1  pop     rsi
0x1400d7ff2  pop     rbp
0x1400d7ff3  pop     rbx
0x1400d7ff4  retn
```
