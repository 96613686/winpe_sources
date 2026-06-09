# PsmpQuerySharedCommit2

- ea: `0x180008840`
- end: `0x180008cb1`
- name: `PsmpQuerySharedCommit2`
- size: `1137`
- prototype: `__int64 __fastcall(void *, int, WCHAR *, int, __int64, int, PVOID JobInformation)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008840`
- `0x1800092b4`
- `0x1800093d0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18001720c`
- `0x180017fa0`
- `0x180019c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180008b5c`
- `ntdll!RtlFreeHeap` at `0x180008b5c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008901`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000896e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c69`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c7b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008901`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000896e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c69`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c7b`
- `ntdll!NtQueryInformationJobObject` at `0x180008a63`
- `ntdll!NtQueryInformationJobObject` at `0x180008c58`
- `ntdll!NtQueryInformationJobObject` at `0x180008a63`
- `ntdll!NtQueryInformationJobObject` at `0x180008c58`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000899d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800089ec`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000899d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800089ec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800089c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008a7b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008b8a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800089c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008a7b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008b8a`
- `ntdll!RtlEqualSid` at `0x180008942`
- `ntdll!RtlEqualSid` at `0x180008942`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800088a4`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008914`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800088a4`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008914`

## pseudocode

```c
__int64 __fastcall PsmpQuerySharedCommit2(
        void *a1,
        int a2,
        WCHAR *a3,
        int a4,
        __int64 a5,
        int a6,
        PVOID JobInformation)
{
  __int64 v9; // rbx
  __int64 v11; // rdx
  _UNKNOWN **i; // r8
  signed __int32 *v13; // rdi
  signed __int32 v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  signed __int32 *j; // r14
  signed __int32 *v19; // rsi
  signed __int32 v20; // eax
  _QWORD *Application; // rax
  __int64 v22; // rbx
  _QWORD *v23; // r14
  signed __int32 v24; // eax
  __int64 *HostJobContext; // rsi
  __int64 *v26; // rbp
  void *v27; // r15
  __int64 *v28; // rax
  __int64 v29; // rdx
  void *v30; // rcx
  unsigned int InformationJobObject; // ebx
  __int64 v33; // rcx
  signed __int32 **v34; // rdx
  __int64 v35; // rcx

  v9 = -1;
  while ( a3[++v9] != 0 )
    ;
  if ( (a6 & 0xFFFFFFF3) == 0 && a6 != 12 )
  {
    RtlAcquireSRWLockShared(&PsmpManagerLock);
    for ( i = (_UNKNOWN **)PsmpManagerList; i != &PsmpManagerList; i = (_UNKNOWN **)*i )
    {
      v13 = (signed __int32 *)(i - 5);
      if ( a2 == *((_DWORD *)i - 5) && a6 == v13[4] )
      {
        _m_prefetchw(v13);
        v14 = *v13;
        while ( v14 > 0 )
        {
          v11 = (unsigned int)v14;
          v14 = _InterlockedCompareExchange(v13, v14 + 1, v14);
          if ( v14 == (_DWORD)v11 )
          {
            RtlReleaseSRWLockShared(&PsmpManagerLock, v11, i, &PsmpManagerList);
            if ( v13 )
            {
              RtlAcquireSRWLockShared(v13 + 2);
              for ( j = (signed __int32 *)*((_QWORD *)v13 + 3); ; j = *(signed __int32 **)j )
              {
                if ( j == v13 + 6 )
                {
                  RtlReleaseSRWLockShared(v13 + 2, v15, v16, v17);
LABEL_36:
                  PsmpDereferenceManagerContext((char *)v13);
                  goto LABEL_37;
                }
                v19 = j - 2;
                if ( *(j - 1) == a2 )
                {
                  if ( RtlEqualSid(*((PSID *)v19 + 5), a1) )
                    break;
                }
LABEL_35:
                ;
              }
              _m_prefetchw(v19);
              v20 = *v19;
              do
              {
                if ( v20 <= 0 )
                  goto LABEL_35;
                v15 = (unsigned int)v20;
                v20 = _InterlockedCompareExchange(v19, v20 + 1, v20);
              }
              while ( v20 != (_DWORD)v15 );
              RtlReleaseSRWLockShared(v13 + 2, v15, v16, v17);
              if ( j == (signed __int32 *)8 )
                goto LABEL_36;
              Application = PsmpFindApplication(0, (__int64)(j - 2), a3, 2 * v9 + 2);
              v22 = *((_QWORD *)v19 + 7);
              v23 = Application;
              RtlAcquireSRWLockExclusive(v22 + 8);
              v24 = _InterlockedDecrement(v19);
              if ( v24 == -1 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs();
              }
              else if ( (v24 & 0x7FFFFFFF) == 0 )
              {
                v33 = *((_QWORD *)v19 + 1);
                if ( *(signed __int32 **)(v33 + 8) != v19 + 2
                  || (v34 = (signed __int32 **)*((_QWORD *)v19 + 2), *v34 != v19 + 2) )
                {
                  __fastfail(3u);
                }
                *v34 = (signed __int32 *)v33;
                *(_QWORD *)(v33 + 8) = v34;
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
              }
              RtlReleaseSRWLockExclusive(v22 + 8);
              PsmpDereferenceManagerContext((char *)v13);
              if ( v23 )
              {
                HostJobContext = 0;
                RtlAcquireSRWLockExclusive(v23 + 41);
                if ( a4 == 4 )
                {
                  HostJobContext = PsmpFindHostJobContext((__int64)v23, a5);
                  if ( !HostJobContext )
                  {
                    RtlReleaseSRWLockExclusive(v23 + 41);
                    PsmpDereferenceApplicationEx((__int64)v23, 0);
                    return 3221225524LL;
                  }
                }
                v26 = 0;
                v27 = 0;
                v28 = 0;
                switch ( a4 )
                {
                  case 2:
                    v29 = v23[850];
                    v30 = (void *)v23[24];
                    if ( v29 != a5 && v29 != -1 )
                      goto LABEL_58;
LABEL_27:
                    if ( v30 )
                    {
                      v27 = v30;
                      v26 = v28;
                      goto LABEL_29;
                    }
                    if ( v28 )
                    {
                      PsmpDereferenceHostContext(v28, 0);
                      InformationJobObject = NtQueryInformationJobObject(
                                               0,
                                               MaxJobObjectInfoClass|JobObjectBasicAccountingInformation|0x10,
                                               JobInformation,
                                               8u,
                                               0);
                    }
                    else
                    {
LABEL_29:
                      InformationJobObject = NtQueryInformationJobObject(
                                               v27,
                                               MaxJobObjectInfoClass|JobObjectBasicAccountingInformation|0x10,
                                               JobInformation,
                                               8u,
                                               0);
                      if ( v26 )
                        PsmpDereferenceHostContext(v26, 0);
                    }
                    break;
                  case 4:
                    v28 = PsmpFindHostJobContext((__int64)v23, a5);
                    if ( !v28 )
                      goto LABEL_58;
                    v30 = (void *)v28[6];
                    goto LABEL_27;
                  case 6:
                    v30 = (void *)v23[23];
                    goto LABEL_27;
                  case 8:
                    v35 = v23[851];
                    if ( v35 == -1 || v35 == a5 )
                    {
                      v30 = (void *)v23[25];
                      goto LABEL_27;
                    }
LABEL_58:
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      WPP_SF_ii(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        55,
                        &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
                        v23[12],
                        a5);
                    InformationJobObject = -1073741811;
                    break;
                  default:
                    goto LABEL_29;
                }
                RtlReleaseSRWLockExclusive(v23 + 41);
                if ( HostJobContext )
                  PsmpDereferenceHostContext(HostJobContext, 0);
                PsmpDereferenceApplicationEx((__int64)v23, 0);
                return InformationJobObject;
              }
            }
            goto LABEL_37;
          }
        }
      }
    }
    RtlReleaseSRWLockShared(&PsmpManagerLock, v11, i, &PsmpManagerList);
  }
LABEL_37:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
      (_DWORD)a3,
      a2);
  return 3221225524LL;
}

```

## disassembly

```asm
0x180008840  mov     [rsp+arg_18], r9d
0x180008845  mov     [rsp+Sid2], rcx
0x18000884a  push    rbx
0x18000884b  push    rbp
0x18000884c  push    rsi
0x18000884d  push    r15
0x18000884f  sub     rsp, 48h
0x180008853  mov     r15, r8
0x180008856  mov     ebp, edx
0x180008858  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000885f  nop
0x180008860  cmp     word ptr [r8+rbx*2+2], 0
0x180008867  lea     rbx, [rbx+1]
0x18000886b  jnz     short loc_180008860
0x18000886d  mov     esi, [rsp+68h+arg_28]
0x180008874  mov     [rsp+68h+arg_8], rdi
0x180008879  mov     [rsp+68h+var_28], r12
0x18000887e  mov     [rsp+68h+var_30], r13
0x180008883  mov     [rsp+68h+var_38], r14
0x180008888  test    esi, 0FFFFFFF3h
0x18000888e  jnz     loc_180008AAC
0x180008894  cmp     esi, 0Ch
0x180008897  jz      loc_180008AAC
0x18000889d  lea     rcx, PsmpManagerLock
0x1800088a4  call    cs:__imp_RtlAcquireSRWLockShared
0x1800088aa  mov     r8, cs:PsmpManagerList
0x1800088b1  lea     r9, PsmpManagerList
0x1800088b8  nop     dword ptr [rax+rax+00000000h]
0x1800088c0  cmp     r8, r9
0x1800088c3  jz      loc_180008C74
0x1800088c9  cmp     ebp, [r8-14h]
0x1800088cd  lea     rdi, [r8-28h]
0x1800088d1  jnz     loc_180008A94
0x1800088d7  cmp     esi, [rdi+10h]
0x1800088da  jnz     loc_180008A94
0x1800088e0  prefetchw byte ptr [rdi]
0x1800088e3  mov     eax, [rdi]
0x1800088e5  test    eax, eax
0x1800088e7  jle     loc_180008A94
0x1800088ed  mov     edx, eax
0x1800088ef  lea     ecx, [rax+1]
0x1800088f2  lock cmpxchg [rdi], ecx
0x1800088f6  cmp     eax, edx
0x1800088f8  jnz     short loc_1800088E5
0x1800088fa  lea     rcx, PsmpManagerLock
0x180008901  call    cs:__imp_RtlReleaseSRWLockShared
0x180008907  test    rdi, rdi
0x18000890a  jz      loc_180008AAC
0x180008910  lea     rcx, [rdi+8]
0x180008914  call    cs:__imp_RtlAcquireSRWLockShared
0x18000891a  mov     r14, [rdi+18h]
0x18000891e  lea     r12, [rdi+18h]
0x180008922  cmp     r14, r12
0x180008925  jz      loc_180008C65
0x18000892b  cmp     [r14-4], ebp
0x18000892f  lea     rsi, [r14-8]
0x180008933  jnz     loc_180008A9C
0x180008939  mov     rdx, [rsp+68h+Sid2]; Sid2
0x18000893e  mov     rcx, [rsi+28h]; Sid1
0x180008942  call    cs:__imp_RtlEqualSid
0x180008948  test    al, al
0x18000894a  jz      loc_180008A9C
0x180008950  prefetchw byte ptr [rsi]
0x180008953  mov     eax, [rsi]
0x180008955  test    eax, eax
0x180008957  jle     loc_180008A9C
0x18000895d  mov     edx, eax
0x18000895f  lea     ecx, [rax+1]
0x180008962  lock cmpxchg [rsi], ecx
0x180008966  cmp     eax, edx
0x180008968  jnz     short loc_180008955
0x18000896a  lea     rcx, [rdi+8]
0x18000896e  call    cs:__imp_RtlReleaseSRWLockShared
0x180008974  test    rsi, rsi
0x180008977  jz      loc_180008AA4
0x18000897d  lea     r9, ds:2[rbx*2]
0x180008985  mov     r8, r15
0x180008988  mov     rdx, rsi
0x18000898b  xor     ecx, ecx
0x18000898d  call    PsmpFindApplication
0x180008992  mov     rbx, [rsi+38h]
0x180008996  mov     r14, rax
0x180008999  lea     rcx, [rbx+8]
0x18000899d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800089a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800089aa  lock xadd [rsi], eax
0x1800089ae  dec     eax
0x1800089b0  cmp     eax, 0FFFFFFFFh
0x1800089b3  jz      loc_180008AE0
0x1800089b9  test    eax, 7FFFFFFFh
0x1800089be  jz      loc_180008B2C
0x1800089c4  lea     rcx, [rbx+8]
0x1800089c8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800089ce  mov     rcx, rdi; P
0x1800089d1  call    PsmpDereferenceManagerContext
0x1800089d6  test    r14, r14
0x1800089d9  jz      loc_180008AAC
0x1800089df  xor     r13d, r13d
0x1800089e2  lea     rcx, [r14+148h]
0x1800089e9  mov     esi, r13d
0x1800089ec  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800089f2  mov     r12d, [rsp+68h+arg_18]
0x1800089fa  mov     rbx, [rsp+68h+arg_20]
0x180008a02  cmp     r12d, 4
0x180008a06  jz      loc_180008B67
0x180008a0c  mov     rbp, r13
0x180008a0f  mov     r15, r13
0x180008a12  mov     rax, r13
0x180008a15  cmp     r12d, 2
0x180008a19  jnz     loc_180008AF6
0x180008a1f  mov     rdx, [r14+1A90h]
0x180008a26  mov     rcx, [r14+0C0h]
0x180008a2d  cmp     rdx, rbx
0x180008a30  jnz     loc_180008BAC
0x180008a36  test    rcx, rcx
0x180008a39  jnz     loc_180008BA1
0x180008a3f  test    rax, rax
0x180008a42  jnz     loc_180008C34
0x180008a48  mov     r8, [rsp+68h+JobInformation]; JobInformation
0x180008a50  mov     r9d, 8; JobInformationLength
0x180008a56  mov     edx, 1Dh; JobInformationClass
0x180008a5b  mov     [rsp+68h+ReturnLength], r13; ReturnLength
0x180008a60  mov     rcx, r15; JobHandle
0x180008a63  call    cs:__imp_NtQueryInformationJobObject
0x180008a69  mov     ebx, eax
0x180008a6b  test    rbp, rbp
0x180008a6e  jnz     loc_180008B1D
0x180008a74  lea     rcx, [r14+148h]
0x180008a7b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008a81  test    rsi, rsi
0x180008a84  jnz     short loc_180008AEA
0x180008a86  xor     edx, edx
0x180008a88  mov     rcx, r14
0x180008a8b  call    PsmpDereferenceApplicationEx
0x180008a90  mov     eax, ebx
0x180008a92  jmp     short loc_180008AC2
0x180008a94  mov     r8, [r8]
0x180008a97  jmp     loc_1800088C0
0x180008a9c  mov     r14, [r14]
0x180008a9f  jmp     loc_180008922
0x180008aa4  mov     rcx, rdi; P
0x180008aa7  call    PsmpDereferenceManagerContext
0x180008aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ab3  test    byte ptr [rcx+1Ch], 2
0x180008ab7  jnz     loc_180008C86
0x180008abd  mov     eax, 0C0000034h
0x180008ac2  mov     r14, [rsp+68h+var_38]
0x180008ac7  mov     r13, [rsp+68h+var_30]
0x180008acc  mov     r12, [rsp+68h+var_28]
0x180008ad1  mov     rdi, [rsp+68h+arg_8]
0x180008ad6  add     rsp, 48h
0x180008ada  pop     r15
0x180008adc  pop     rsi
0x180008add  pop     rbp
0x180008ade  pop     rbx
0x180008adf  retn
0x180008ae0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008ae5  jmp     loc_1800089C4
0x180008aea  xor     edx, edx
0x180008aec  mov     rcx, rsi
0x180008aef  call    PsmpDereferenceHostContext
0x180008af4  jmp     short loc_180008A86
0x180008af6  cmp     r12d, 4
0x180008afa  jnz     loc_180008BBF
0x180008b00  mov     rdx, rbx
0x180008b03  mov     rcx, r14
0x180008b06  call    PsmpFindHostJobContext
0x180008b0b  test    rax, rax
0x180008b0e  jz      loc_180008BF9
0x180008b14  mov     rcx, [rax+30h]
0x180008b18  jmp     loc_180008A36
0x180008b1d  xor     edx, edx
0x180008b1f  mov     rcx, rbp
0x180008b22  call    PsmpDereferenceHostContext
0x180008b27  jmp     loc_180008A74
0x180008b2c  mov     rcx, [rsi+8]
0x180008b30  lea     rax, [rsi+8]
0x180008b34  cmp     [rcx+8], rax
0x180008b38  jnz     short loc_180008BB8
0x180008b3a  mov     rdx, [rax+8]
0x180008b3e  cmp     [rdx], rax
0x180008b41  jnz     short loc_180008BB8
0x180008b43  mov     [rdx], rcx
0x180008b46  mov     r8, rsi; P
0x180008b49  mov     [rcx+8], rdx
0x180008b4d  xor     edx, edx; Flags
0x180008b4f  mov     rcx, gs:60h
0x180008b58  mov     rcx, [rcx+30h]; HeapHandle
0x180008b5c  call    cs:__imp_RtlFreeHeap
0x180008b62  jmp     loc_1800089C4
0x180008b67  mov     rdx, rbx
0x180008b6a  mov     rcx, r14
0x180008b6d  call    PsmpFindHostJobContext
0x180008b72  mov     rsi, rax
0x180008b75  test    rax, rax
0x180008b78  jnz     loc_180008A0C
0x180008b7e  lea     rcx, [r14+148h]
0x180008b85  mov     ebx, 0C0000034h
0x180008b8a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008b90  xor     edx, edx
0x180008b92  mov     rcx, r14
0x180008b95  call    PsmpDereferenceApplicationEx
0x180008b9a  mov     eax, ebx
0x180008b9c  jmp     loc_180008AC2
0x180008ba1  mov     r15, rcx
0x180008ba4  mov     rbp, rax
0x180008ba7  jmp     loc_180008A48
0x180008bac  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180008bb0  jz      loc_180008A36
0x180008bb6  jmp     short loc_180008BF9
0x180008bb8  mov     ecx, 3
0x180008bbd  int     29h; Win8: RtlFailFast(ecx)
0x180008bbf  cmp     r12d, 6
0x180008bc3  jz      short loc_180008BE8
0x180008bc5  cmp     r12d, 8
0x180008bc9  jnz     loc_180008A48
0x180008bcf  mov     rcx, [r14+1A98h]
0x180008bd6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008bda  jnz     short loc_180008BF4
0x180008bdc  mov     rcx, [r14+0C8h]
0x180008be3  jmp     loc_180008A36
0x180008be8  mov     rcx, [r14+0B8h]
0x180008bef  jmp     loc_180008A36
0x180008bf4  cmp     rcx, rbx
0x180008bf7  jz      short loc_180008BDC
0x180008bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c00  test    byte ptr [rcx+1Ch], 2
0x180008c04  jz      short loc_180008C2A
0x180008c06  cmp     byte ptr [rcx+19h], 2
0x180008c0a  jb      short loc_180008C2A
0x180008c0c  mov     r9, [r14+60h]
0x180008c10  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180008c17  mov     rcx, [rcx+10h]
0x180008c1b  mov     edx, 37h ; '7'
0x180008c20  mov     [rsp+68h+ReturnLength], rbx
0x180008c25  call    WPP_SF_ii
0x180008c2a  mov     ebx, 0C000000Dh
0x180008c2f  jmp     loc_180008A74
0x180008c34  xor     edx, edx
0x180008c36  mov     rcx, rax
0x180008c39  call    PsmpDereferenceHostContext
0x180008c3e  mov     r8, [rsp+68h+JobInformation]; JobInformation
0x180008c46  mov     r9d, 8; JobInformationLength
0x180008c4c  mov     edx, 1Dh; JobInformationClass
0x180008c51  mov     [rsp+68h+ReturnLength], r13; ReturnLength
0x180008c56  xor     ecx, ecx; JobHandle
0x180008c58  call    cs:__imp_NtQueryInformationJobObject
0x180008c5e  mov     ebx, eax
0x180008c60  jmp     loc_180008A74
0x180008c65  lea     rcx, [rdi+8]
0x180008c69  call    cs:__imp_RtlReleaseSRWLockShared
0x180008c6f  jmp     loc_180008AA4
0x180008c74  lea     rcx, PsmpManagerLock
0x180008c7b  call    cs:__imp_RtlReleaseSRWLockShared
0x180008c81  jmp     loc_180008AAC
0x180008c86  cmp     byte ptr [rcx+19h], 2
0x180008c8a  jb      loc_180008ABD
0x180008c90  mov     rcx, [rcx+10h]
0x180008c94  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180008c9b  mov     edx, 38h ; '8'
0x180008ca0  mov     dword ptr [rsp+68h+ReturnLength], ebp
0x180008ca4  mov     r9, r15
0x180008ca7  call    WPP_SF_Sd
0x180008cac  jmp     loc_180008ABD
```
