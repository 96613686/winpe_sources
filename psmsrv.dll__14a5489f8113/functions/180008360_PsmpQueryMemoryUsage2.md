# PsmpQueryMemoryUsage2

- ea: `0x180008360`
- end: `0x180008837`
- name: `PsmpQueryMemoryUsage2`
- size: `1239`
- prototype: `__int64 __fastcall(void *, int, WCHAR *, int, __int64, int, PSID *, PSID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008360`
- `0x1800092b4`
- `0x1800093d0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18001720c`
- `0x180017fa0`
- `0x180019c30`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800086b4`
- `ntdll!RtlFreeHeap` at `0x1800086b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008461`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800084ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087ef`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008801`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008461`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800084ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087ef`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008801`
- `ntdll!NtQueryInformationJobObject` at `0x1800086d8`
- `ntdll!NtQueryInformationJobObject` at `0x1800086d8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800084fd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008548`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800084fd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008548`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008528`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800085be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008734`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008528`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800085be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008734`
- `ntdll!RtlEqualSid` at `0x1800084a2`
- `ntdll!RtlEqualSid` at `0x1800084a2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000840a`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008474`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000840a`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008474`

## pseudocode

```c
__int64 __fastcall PsmpQueryMemoryUsage2(void *a1, int a2, WCHAR *a3, int a4, __int64 a5, int a6, PSID *a7, PSID *a8)
{
  __int64 v10; // rdi
  __int64 v12; // rdx
  _UNKNOWN **i; // r8
  signed __int32 *v14; // rbx
  signed __int32 v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  signed __int32 *j; // r14
  signed __int32 *v20; // rsi
  signed __int32 v21; // eax
  _QWORD *Application; // rax
  __int64 v23; // r14
  _QWORD *v24; // rdi
  signed __int32 v25; // eax
  __int64 *HostJobContext; // rbp
  __int64 *v27; // rbx
  __int64 v28; // rax
  void *v29; // rcx
  unsigned int v30; // ebx
  __int64 *v32; // rax
  __int64 v33; // rcx
  signed __int32 **v34; // rdx
  __int64 v35; // rax
  PSID Sid2[2]; // [rsp+50h] [rbp-58h] BYREF

  v10 = -1;
  Sid2[0] = a1;
  while ( a3[++v10] != 0 )
    ;
  if ( (a6 & 0xFFFFFFF3) == 0 && a6 != 12 )
  {
    RtlAcquireSRWLockShared(&PsmpManagerLock);
    for ( i = (_UNKNOWN **)PsmpManagerList; i != &PsmpManagerList; i = (_UNKNOWN **)*i )
    {
      v14 = (signed __int32 *)(i - 5);
      if ( a2 == *((_DWORD *)i - 5) && a6 == v14[4] )
      {
        _m_prefetchw(v14);
        v15 = *v14;
        while ( v15 > 0 )
        {
          v12 = (unsigned int)v15;
          v15 = _InterlockedCompareExchange(v14, v15 + 1, v15);
          if ( v15 == (_DWORD)v12 )
          {
            RtlReleaseSRWLockShared(&PsmpManagerLock, v12, i, &PsmpManagerList);
            if ( v14 )
            {
              RtlAcquireSRWLockShared(v14 + 2);
              for ( j = (signed __int32 *)*((_QWORD *)v14 + 3); ; j = *(signed __int32 **)j )
              {
                if ( j == v14 + 6 )
                {
                  RtlReleaseSRWLockShared(v14 + 2, v16, v17, v18);
LABEL_37:
                  PsmpDereferenceManagerContext((char *)v14);
                  goto LABEL_38;
                }
                v20 = j - 2;
                if ( *(j - 1) == a2 )
                {
                  if ( RtlEqualSid(*((PSID *)v20 + 5), Sid2[0]) )
                    break;
                }
LABEL_36:
                ;
              }
              _m_prefetchw(v20);
              v21 = *v20;
              do
              {
                if ( v21 <= 0 )
                  goto LABEL_36;
                v16 = (unsigned int)v21;
                v21 = _InterlockedCompareExchange(v20, v21 + 1, v21);
              }
              while ( v21 != (_DWORD)v16 );
              RtlReleaseSRWLockShared(v14 + 2, v16, v17, v18);
              if ( j == (signed __int32 *)8 )
                goto LABEL_37;
              Application = PsmpFindApplication(0, (__int64)(j - 2), a3, 2 * v10 + 2);
              v23 = *((_QWORD *)v20 + 7);
              v24 = Application;
              RtlAcquireSRWLockExclusive(v23 + 8);
              v25 = _InterlockedDecrement(v20);
              if ( v25 == -1 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs();
              }
              else if ( (v25 & 0x7FFFFFFF) == 0 )
              {
                v33 = *((_QWORD *)v20 + 1);
                if ( *(signed __int32 **)(v33 + 8) != v20 + 2
                  || (v34 = (signed __int32 **)*((_QWORD *)v20 + 2), *v34 != v20 + 2) )
                {
                  __fastfail(3u);
                }
                *v34 = (signed __int32 *)v33;
                *(_QWORD *)(v33 + 8) = v34;
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
              }
              RtlReleaseSRWLockExclusive(v23 + 8);
              PsmpDereferenceManagerContext((char *)v14);
              if ( v24 )
              {
                HostJobContext = 0;
                RtlAcquireSRWLockExclusive(v24 + 41);
                if ( a4 == 4 )
                {
                  HostJobContext = PsmpFindHostJobContext((__int64)v24, a5);
                  if ( !HostJobContext )
                  {
                    v30 = -1073741772;
                    RtlReleaseSRWLockExclusive(v24 + 41);
LABEL_34:
                    PsmpDereferenceApplicationEx((__int64)v24, 0);
                    return v30;
                  }
                }
                *(_OWORD *)Sid2 = 0;
                if ( !a7 && !a8 )
                {
                  v30 = -1073741811;
LABEL_32:
                  RtlReleaseSRWLockExclusive(v24 + 41);
                  if ( HostJobContext )
                    PsmpDereferenceHostContext(HostJobContext, 0);
                  goto LABEL_34;
                }
                v27 = 0;
                switch ( a4 )
                {
                  case 2:
                    v28 = v24[850];
                    v29 = (void *)v24[24];
                    if ( v28 != a5 && v28 != -1 )
                      goto LABEL_63;
                    goto LABEL_28;
                  case 4:
                    v32 = PsmpFindHostJobContext((__int64)v24, a5);
                    v27 = v32;
                    if ( !v32 )
                    {
LABEL_63:
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        WPP_SF_ii(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          51,
                          &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
                          v24[12],
                          a5);
                      v30 = -1073741811;
                      goto LABEL_32;
                    }
                    v29 = (void *)v32[6];
LABEL_28:
                    if ( v29 )
                    {
                      NtQueryInformationJobObject(v29, MaxJobObjectInfoClass|0x10, Sid2, 0x10u, 0);
                      if ( a7 )
                        *a7 = Sid2[0];
                      if ( a8 )
                        *a8 = Sid2[1];
                      if ( v27 )
                        PsmpDereferenceHostContext(v27, 0);
                      v30 = 0;
                      goto LABEL_32;
                    }
                    if ( v27 )
                      PsmpDereferenceHostContext(v27, 0);
                    break;
                  case 6:
                    v29 = (void *)v24[23];
                    goto LABEL_28;
                  case 8:
                    v35 = v24[851];
                    if ( v35 != a5 && v35 != -1 )
                      goto LABEL_63;
                    v29 = (void *)v24[25];
                    goto LABEL_28;
                }
                v30 = -1073741772;
                goto LABEL_32;
              }
            }
            goto LABEL_38;
          }
        }
      }
    }
    RtlReleaseSRWLockShared(&PsmpManagerLock, v12, i, &PsmpManagerList);
  }
LABEL_38:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
      (_DWORD)a3,
      a2);
  return 3221225524LL;
}

```

## disassembly

```asm
0x180008360  push    rbp
0x180008362  push    rsi
0x180008363  push    rdi
0x180008364  push    r15
0x180008366  sub     rsp, 88h
0x18000836d  mov     rax, cs:__security_cookie
0x180008374  xor     rax, rsp
0x180008377  mov     [rsp+0A8h+var_48], rax
0x18000837c  mov     rax, [rsp+0A8h+arg_20]
0x180008384  mov     r15, r8
0x180008387  mov     [rsp+0A8h+var_70], rax
0x18000838c  mov     ebp, edx
0x18000838e  mov     rax, [rsp+0A8h+arg_30]
0x180008396  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000839d  mov     [rsp+0A8h+var_60], rax
0x1800083a2  mov     rax, [rsp+0A8h+arg_38]
0x1800083aa  mov     [rsp+0A8h+var_68], rax
0x1800083af  mov     [rsp+0A8h+var_78], r9d
0x1800083b4  mov     [rsp+0A8h+Sid2], rcx
0x1800083b9  nop     dword ptr [rax+00000000h]
0x1800083c0  cmp     word ptr [r8+rdi*2+2], 0
0x1800083c7  lea     rdi, [rdi+1]
0x1800083cb  jnz     short loc_1800083C0
0x1800083cd  mov     esi, [rsp+0A8h+arg_28]
0x1800083d4  mov     [rsp+0A8h+arg_8], rbx
0x1800083dc  mov     [rsp+0A8h+var_28], r12
0x1800083e4  mov     [rsp+0A8h+var_30], r13
0x1800083e9  mov     [rsp+0A8h+var_38], r14
0x1800083ee  test    esi, 0FFFFFFF3h
0x1800083f4  jnz     loc_1800085EF
0x1800083fa  cmp     esi, 0Ch
0x1800083fd  jz      loc_1800085EF
0x180008403  lea     rcx, PsmpManagerLock
0x18000840a  call    cs:__imp_RtlAcquireSRWLockShared
0x180008410  mov     r8, cs:PsmpManagerList
0x180008417  lea     r9, PsmpManagerList
0x18000841e  xchg    ax, ax
0x180008420  cmp     r8, r9
0x180008423  jz      loc_1800087FA
0x180008429  cmp     ebp, [r8-14h]
0x18000842d  lea     rbx, [r8-28h]
0x180008431  jnz     loc_1800085D7
0x180008437  cmp     esi, [rbx+10h]
0x18000843a  jnz     loc_1800085D7
0x180008440  prefetchw byte ptr [rbx]
0x180008443  mov     eax, [rbx]
0x180008445  test    eax, eax
0x180008447  jle     loc_1800085D7
0x18000844d  mov     edx, eax
0x18000844f  lea     ecx, [rax+1]
0x180008452  lock cmpxchg [rbx], ecx
0x180008456  cmp     eax, edx
0x180008458  jnz     short loc_180008445
0x18000845a  lea     rcx, PsmpManagerLock
0x180008461  call    cs:__imp_RtlReleaseSRWLockShared
0x180008467  test    rbx, rbx
0x18000846a  jz      loc_1800085EF
0x180008470  lea     rcx, [rbx+8]
0x180008474  call    cs:__imp_RtlAcquireSRWLockShared
0x18000847a  mov     r14, [rbx+18h]
0x18000847e  lea     r12, [rbx+18h]
0x180008482  cmp     r14, r12
0x180008485  jz      loc_1800087EB
0x18000848b  cmp     [r14-4], ebp
0x18000848f  lea     rsi, [r14-8]
0x180008493  jnz     loc_1800085DF
0x180008499  mov     rdx, [rsp+0A8h+Sid2]; Sid2
0x18000849e  mov     rcx, [rsi+28h]; Sid1
0x1800084a2  call    cs:__imp_RtlEqualSid
0x1800084a8  test    al, al
0x1800084aa  jz      loc_1800085DF
0x1800084b0  prefetchw byte ptr [rsi]
0x1800084b3  mov     eax, [rsi]
0x1800084b5  test    eax, eax
0x1800084b7  jle     loc_1800085DF
0x1800084bd  mov     edx, eax
0x1800084bf  lea     ecx, [rax+1]
0x1800084c2  lock cmpxchg [rsi], ecx
0x1800084c6  cmp     eax, edx
0x1800084c8  jnz     short loc_1800084B5
0x1800084ca  lea     rcx, [rbx+8]
0x1800084ce  call    cs:__imp_RtlReleaseSRWLockShared
0x1800084d4  test    rsi, rsi
0x1800084d7  jz      loc_1800085E7
0x1800084dd  lea     r9, ds:2[rdi*2]
0x1800084e5  mov     r8, r15
0x1800084e8  mov     rdx, rsi
0x1800084eb  xor     ecx, ecx
0x1800084ed  call    PsmpFindApplication
0x1800084f2  mov     r14, [rsi+38h]
0x1800084f6  mov     rdi, rax
0x1800084f9  lea     rcx, [r14+8]
0x1800084fd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008503  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000850a  lock xadd [rsi], eax
0x18000850e  dec     eax
0x180008510  cmp     eax, 0FFFFFFFFh
0x180008513  jz      loc_180008639
0x180008519  test    eax, 7FFFFFFFh
0x18000851e  jz      loc_18000867C
0x180008524  lea     rcx, [r14+8]
0x180008528  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000852e  mov     rcx, rbx; P
0x180008531  call    PsmpDereferenceManagerContext
0x180008536  test    rdi, rdi
0x180008539  jz      loc_1800085EF
0x18000853f  lea     rcx, [rdi+148h]
0x180008546  xor     ebp, ebp
0x180008548  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000854e  mov     r14d, [rsp+0A8h+var_78]
0x180008553  mov     r12, [rsp+0A8h+var_70]
0x180008558  cmp     r14d, 4
0x18000855c  jz      loc_180008711
0x180008562  mov     r15, [rsp+0A8h+var_60]
0x180008567  xorps   xmm0, xmm0
0x18000856a  mov     r13, [rsp+0A8h+var_68]
0x18000856f  movups  xmmword ptr [rsp+0A8h+Sid2], xmm0
0x180008574  test    r15, r15
0x180008577  jz      loc_180008797
0x18000857d  xor     ebx, ebx
0x18000857f  cmp     r14d, 2
0x180008583  jnz     loc_180008652
0x180008589  mov     rax, [rdi+1A90h]
0x180008590  mov     rcx, [rdi+0C0h]; JobHandle
0x180008597  cmp     rax, r12
0x18000859a  jnz     loc_18000873F
0x1800085a0  test    rcx, rcx
0x1800085a3  jnz     loc_1800086BF
0x1800085a9  test    rbx, rbx
0x1800085ac  jnz     loc_1800087DC
0x1800085b2  mov     ebx, 0C0000034h
0x1800085b7  lea     rcx, [rdi+148h]
0x1800085be  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800085c4  test    rbp, rbp
0x1800085c7  jnz     short loc_180008643
0x1800085c9  xor     edx, edx
0x1800085cb  mov     rcx, rdi
0x1800085ce  call    PsmpDereferenceApplicationEx
0x1800085d3  mov     eax, ebx
0x1800085d5  jmp     short loc_180008605
0x1800085d7  mov     r8, [r8]
0x1800085da  jmp     loc_180008420
0x1800085df  mov     r14, [r14]
0x1800085e2  jmp     loc_180008482
0x1800085e7  mov     rcx, rbx; P
0x1800085ea  call    PsmpDereferenceManagerContext
0x1800085ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085f6  test    byte ptr [rcx+1Ch], 2
0x1800085fa  jnz     loc_18000880C
0x180008600  mov     eax, 0C0000034h
0x180008605  mov     r14, [rsp+0A8h+var_38]
0x18000860a  mov     r13, [rsp+0A8h+var_30]
0x18000860f  mov     r12, [rsp+0A8h+var_28]
0x180008617  mov     rbx, [rsp+0A8h+arg_8]
0x18000861f  mov     rcx, [rsp+0A8h+var_48]
0x180008624  xor     rcx, rsp; StackCookie
0x180008627  call    __security_check_cookie
0x18000862c  add     rsp, 88h
0x180008633  pop     r15
0x180008635  pop     rdi
0x180008636  pop     rsi
0x180008637  pop     rbp
0x180008638  retn
0x180008639  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000863e  jmp     loc_180008524
0x180008643  xor     edx, edx
0x180008645  mov     rcx, rbp
0x180008648  call    PsmpDereferenceHostContext
0x18000864d  jmp     loc_1800085C9
0x180008652  cmp     r14d, 4
0x180008656  jnz     loc_180008752
0x18000865c  mov     rdx, r12
0x18000865f  mov     rcx, rdi
0x180008662  call    PsmpFindHostJobContext
0x180008667  mov     rbx, rax
0x18000866a  test    rax, rax
0x18000866d  jz      loc_180008774
0x180008673  mov     rcx, [rax+30h]
0x180008677  jmp     loc_1800085A0
0x18000867c  mov     rcx, [rsi+8]
0x180008680  lea     rax, [rsi+8]
0x180008684  cmp     [rcx+8], rax
0x180008688  jnz     loc_18000874B
0x18000868e  mov     rdx, [rax+8]
0x180008692  cmp     [rdx], rax
0x180008695  jnz     loc_18000874B
0x18000869b  mov     [rdx], rcx
0x18000869e  mov     r8, rsi; P
0x1800086a1  mov     [rcx+8], rdx
0x1800086a5  xor     edx, edx; Flags
0x1800086a7  mov     rcx, gs:60h
0x1800086b0  mov     rcx, [rcx+30h]; HeapHandle
0x1800086b4  call    cs:__imp_RtlFreeHeap
0x1800086ba  jmp     loc_180008524
0x1800086bf  mov     r9d, 10h; JobInformationLength
0x1800086c5  mov     [rsp+0A8h+ReturnLength], 0; ReturnLength
0x1800086ce  lea     r8, [rsp+0A8h+Sid2]; JobInformation
0x1800086d3  mov     edx, 1Ch; JobInformationClass
0x1800086d8  call    cs:__imp_NtQueryInformationJobObject
0x1800086de  test    r15, r15
0x1800086e1  jz      short loc_1800086EB
0x1800086e3  mov     rax, [rsp+0A8h+Sid2]
0x1800086e8  mov     [r15], rax
0x1800086eb  test    r13, r13
0x1800086ee  jnz     short loc_180008706
0x1800086f0  test    rbx, rbx
0x1800086f3  jz      short loc_1800086FF
0x1800086f5  xor     edx, edx
0x1800086f7  mov     rcx, rbx
0x1800086fa  call    PsmpDereferenceHostContext
0x1800086ff  xor     ebx, ebx
0x180008701  jmp     loc_1800085B7
0x180008706  mov     rax, [rsp+0A8h+Sid2+8]
0x18000870b  mov     [r13+0], rax
0x18000870f  jmp     short loc_1800086F0
0x180008711  mov     rdx, r12
0x180008714  mov     rcx, rdi
0x180008717  call    PsmpFindHostJobContext
0x18000871c  mov     rbp, rax
0x18000871f  test    rax, rax
0x180008722  jnz     loc_180008562
0x180008728  lea     rcx, [rdi+148h]
0x18000872f  mov     ebx, 0C0000034h
0x180008734  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000873a  jmp     loc_1800085C9
0x18000873f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008743  jz      loc_1800085A0
0x180008749  jmp     short loc_180008774
0x18000874b  mov     ecx, 3
0x180008750  int     29h; Win8: RtlFailFast(ecx)
0x180008752  cmp     r14d, 6
0x180008756  jz      short loc_18000878B
0x180008758  cmp     r14d, 8
0x18000875c  jnz     loc_1800085B2
0x180008762  mov     rax, [rdi+1A98h]
0x180008769  cmp     rax, r12
0x18000876c  jz      short loc_1800087AA
0x18000876e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008772  jz      short loc_1800087AA
0x180008774  mov     rcx, cs:WPP_GLOBAL_Control
0x18000877b  test    byte ptr [rcx+1Ch], 2
0x18000877f  jnz     short loc_1800087B6
0x180008781  mov     ebx, 0C000000Dh
0x180008786  jmp     loc_1800085B7
0x18000878b  mov     rcx, [rdi+0B8h]
0x180008792  jmp     loc_1800085A0
0x180008797  test    r13, r13
0x18000879a  jnz     loc_18000857D
0x1800087a0  mov     ebx, 0C000000Dh
0x1800087a5  jmp     loc_1800085B7
0x1800087aa  mov     rcx, [rdi+0C8h]
0x1800087b1  jmp     loc_1800085A0
0x1800087b6  cmp     byte ptr [rcx+19h], 2
0x1800087ba  jb      short loc_180008781
0x1800087bc  mov     r9, [rdi+60h]
0x1800087c0  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x1800087c7  mov     rcx, [rcx+10h]
0x1800087cb  mov     edx, 33h ; '3'
0x1800087d0  mov     [rsp+0A8h+ReturnLength], r12
0x1800087d5  call    WPP_SF_ii
0x1800087da  jmp     short loc_180008781
0x1800087dc  xor     edx, edx
0x1800087de  mov     rcx, rbx
0x1800087e1  call    PsmpDereferenceHostContext
0x1800087e6  jmp     loc_1800085B2
0x1800087eb  lea     rcx, [rbx+8]
0x1800087ef  call    cs:__imp_RtlReleaseSRWLockShared
0x1800087f5  jmp     loc_1800085E7
0x1800087fa  lea     rcx, PsmpManagerLock
0x180008801  call    cs:__imp_RtlReleaseSRWLockShared
0x180008807  jmp     loc_1800085EF
0x18000880c  cmp     byte ptr [rcx+19h], 2
0x180008810  jb      loc_180008600
0x180008816  mov     rcx, [rcx+10h]
0x18000881a  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180008821  mov     edx, 34h ; '4'
0x180008826  mov     dword ptr [rsp+0A8h+ReturnLength], ebp
0x18000882a  mov     r9, r15
0x18000882d  call    WPP_SF_Sd
0x180008832  jmp     loc_180008600
```
