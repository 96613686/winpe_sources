# PsmpIsProcessInApplicationForUser

- ea: `0x180008f10`
- end: `0x1800092ac`
- name: `PsmpIsProcessInApplicationForUser`
- size: `924`
- prototype: `_BOOL8 __fastcall(void *, int, WCHAR *, int, __int64, int, HANDLE ProcessHandle)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008f10`
- `0x1800092b4`
- `0x1800093d0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18001622c`
- `0x180019c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800091aa`
- `ntdll!RtlFreeHeap` at `0x1800091aa`
- `ntdll!NtIsProcessInJob` at `0x1800091bd`
- `ntdll!NtIsProcessInJob` at `0x1800091bd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008fd5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009042`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009162`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000928f`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800092a1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008fd5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009042`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009162`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000928f`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800092a1`
- `ntdll!RtlValidSid` at `0x180008f33`
- `ntdll!RtlValidSid` at `0x180008f33`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009071`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009071`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000909c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000909c`
- `ntdll!RtlEqualSid` at `0x180009016`
- `ntdll!RtlEqualSid` at `0x180009016`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008f80`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008fe8`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009142`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008f80`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008fe8`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009142`

## pseudocode

```c
_BOOL8 __fastcall PsmpIsProcessInApplicationForUser(
        void *a1,
        int a2,
        WCHAR *a3,
        int a4,
        __int64 a5,
        int a6,
        HANDLE ProcessHandle)
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
  _QWORD *v23; // rbp
  signed __int32 v24; // eax
  __int64 *HostJobContext; // rdi
  __int64 v26; // rax
  void *v27; // rdx
  bool v28; // bl
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  signed __int32 *v33; // rcx
  signed __int32 **v34; // rdx
  __int64 v35; // rax

  if ( RtlValidSid(a1) )
  {
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
LABEL_35:
                    PsmpDereferenceManagerContext((char *)v13);
                    return 0;
                  }
                  v19 = j - 2;
                  if ( *(j - 1) == a2 )
                  {
                    if ( RtlEqualSid(*((PSID *)v19 + 5), a1) )
                      break;
                  }
LABEL_34:
                  ;
                }
                _m_prefetchw(v19);
                v20 = *v19;
                do
                {
                  if ( v20 <= 0 )
                    goto LABEL_34;
                  v15 = (unsigned int)v20;
                  v20 = _InterlockedCompareExchange(v19, v20 + 1, v20);
                }
                while ( v20 != (_DWORD)v15 );
                RtlReleaseSRWLockShared(v13 + 2, v15, v16, v17);
                if ( j == (signed __int32 *)8 )
                  goto LABEL_35;
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
                  v33 = *(signed __int32 **)j;
                  if ( *(signed __int32 **)(*(_QWORD *)j + 8LL) != j
                    || (v34 = (signed __int32 **)*((_QWORD *)v19 + 2), *v34 != j) )
                  {
                    __fastfail(3u);
                  }
                  *v34 = v33;
                  *((_QWORD *)v33 + 1) = v34;
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, j - 2);
                }
                RtlReleaseSRWLockExclusive(v22 + 8);
                PsmpDereferenceManagerContext((char *)v13);
                if ( v23 )
                {
                  HostJobContext = 0;
                  if ( a4 == 2 )
                  {
                    v26 = v23[850];
                    v27 = (void *)v23[24];
                    if ( v26 != a5 && v26 != -1 )
                      goto LABEL_30;
LABEL_27:
                    if ( !v27 )
                    {
                      if ( HostJobContext )
                        PsmpDereferenceHostContext(HostJobContext, 0);
                      goto LABEL_30;
                    }
                    v28 = NtIsProcessInJob(ProcessHandle, v27) == 292;
                    if ( HostJobContext )
                      PsmpDereferenceHostContext(HostJobContext, 0);
                  }
                  else
                  {
                    switch ( a4 )
                    {
                      case 4:
                        RtlAcquireSRWLockShared(v23 + 41);
                        HostJobContext = PsmpFindHostJobContext((__int64)v23, a5);
                        RtlReleaseSRWLockShared(v23 + 41, v30, v31, v32);
                        if ( !HostJobContext )
                          break;
                        v27 = (void *)HostJobContext[6];
                        goto LABEL_27;
                      case 6:
                        v27 = (void *)v23[23];
                        goto LABEL_27;
                      case 8:
                        v35 = v23[851];
                        if ( v35 == -1 || v35 == a5 )
                        {
                          v27 = (void *)v23[25];
                          goto LABEL_27;
                        }
                        break;
                    }
LABEL_30:
                    v28 = 0;
                  }
                  PsmpDereferenceApplicationEx((__int64)v23, 0);
                  return v28;
                }
              }
              return 0;
            }
          }
        }
      }
      RtlReleaseSRWLockShared(&PsmpManagerLock, v11, i, &PsmpManagerList);
    }
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180008f10  mov     [rsp+arg_8], rbx
0x180008f15  mov     [rsp+arg_18], r9d
0x180008f1a  mov     [rsp+Sid2], rcx
0x180008f1f  push    rbp
0x180008f20  push    rsi
0x180008f21  push    rdi
0x180008f22  push    r12
0x180008f24  push    r13
0x180008f26  push    r14
0x180008f28  push    r15
0x180008f2a  sub     rsp, 20h
0x180008f2e  mov     r15, r8
0x180008f31  mov     ebp, edx
0x180008f33  call    cs:__imp_RtlValidSid
0x180008f39  test    al, al
0x180008f3b  jz      loc_180009231
0x180008f41  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008f48  nop     dword ptr [rax+rax+00000000h]
0x180008f50  cmp     word ptr [r15+rbx*2+2], 0
0x180008f57  lea     rbx, [rbx+1]
0x180008f5b  jnz     short loc_180008F50
0x180008f5d  mov     esi, [rsp+58h+arg_28]
0x180008f64  test    esi, 0FFFFFFF3h
0x180008f6a  jnz     loc_180009124
0x180008f70  cmp     esi, 0Ch
0x180008f73  jz      loc_180009124
0x180008f79  lea     rcx, PsmpManagerLock
0x180008f80  call    cs:__imp_RtlAcquireSRWLockShared
0x180008f86  mov     r8, cs:PsmpManagerList
0x180008f8d  lea     r9, PsmpManagerList
0x180008f94  cmp     r8, r9
0x180008f97  jz      loc_18000929A
0x180008f9d  cmp     ebp, [r8-14h]
0x180008fa1  lea     rdi, [r8-28h]
0x180008fa5  jnz     loc_18000910C
0x180008fab  cmp     esi, [rdi+10h]
0x180008fae  jnz     loc_18000910C
0x180008fb4  prefetchw byte ptr [rdi]
0x180008fb7  mov     eax, [rdi]
0x180008fb9  test    eax, eax
0x180008fbb  jle     loc_18000910C
0x180008fc1  mov     edx, eax
0x180008fc3  lea     ecx, [rax+1]
0x180008fc6  lock cmpxchg [rdi], ecx
0x180008fca  cmp     eax, edx
0x180008fcc  jnz     short loc_180008FB9
0x180008fce  lea     rcx, PsmpManagerLock
0x180008fd5  call    cs:__imp_RtlReleaseSRWLockShared
0x180008fdb  test    rdi, rdi
0x180008fde  jz      loc_180009124
0x180008fe4  lea     rcx, [rdi+8]
0x180008fe8  call    cs:__imp_RtlAcquireSRWLockShared
0x180008fee  mov     r14, [rdi+18h]
0x180008ff2  lea     r12, [rdi+18h]
0x180008ff6  cmp     r14, r12
0x180008ff9  jz      loc_18000928B
0x180008fff  cmp     [r14-4], ebp
0x180009003  lea     rsi, [r14-8]
0x180009007  jnz     loc_180009114
0x18000900d  mov     rdx, [rsp+58h+Sid2]; Sid2
0x180009012  mov     rcx, [rsi+28h]; Sid1
0x180009016  call    cs:__imp_RtlEqualSid
0x18000901c  test    al, al
0x18000901e  jz      loc_180009114
0x180009024  prefetchw byte ptr [rsi]
0x180009027  mov     eax, [rsi]
0x180009029  test    eax, eax
0x18000902b  jle     loc_180009114
0x180009031  mov     edx, eax
0x180009033  lea     ecx, [rax+1]
0x180009036  lock cmpxchg [rsi], ecx
0x18000903a  cmp     eax, edx
0x18000903c  jnz     short loc_180009029
0x18000903e  lea     rcx, [rdi+8]
0x180009042  call    cs:__imp_RtlReleaseSRWLockShared
0x180009048  test    rsi, rsi
0x18000904b  jz      loc_18000911C
0x180009051  lea     r9, ds:2[rbx*2]
0x180009059  mov     r8, r15
0x18000905c  mov     rdx, rsi
0x18000905f  xor     ecx, ecx
0x180009061  call    PsmpFindApplication
0x180009066  mov     rbx, [rsi+38h]
0x18000906a  mov     rbp, rax
0x18000906d  lea     rcx, [rbx+8]
0x180009071  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009077  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000907e  lock xadd [rsi], eax
0x180009082  dec     eax
0x180009084  cmp     eax, 0FFFFFFFFh
0x180009087  jz      loc_180009128
0x18000908d  test    eax, 7FFFFFFFh
0x180009092  jz      loc_18000917A
0x180009098  lea     rcx, [rbx+8]
0x18000909c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800090a2  mov     rcx, rdi; P
0x1800090a5  call    PsmpDereferenceManagerContext
0x1800090aa  test    rbp, rbp
0x1800090ad  jz      short loc_180009124
0x1800090af  mov     eax, [rsp+58h+arg_18]
0x1800090b3  xor     edi, edi
0x1800090b5  cmp     eax, 2
0x1800090b8  jnz     short loc_180009132
0x1800090ba  mov     rax, [rbp+1A90h]
0x1800090c1  mov     rdx, [rbp+0C0h]; JobHandle
0x1800090c8  cmp     rax, [rsp+58h+arg_20]
0x1800090d0  jnz     loc_1800091E8
0x1800090d6  test    rdx, rdx
0x1800090d9  jnz     loc_1800091B5
0x1800090df  test    rdi, rdi
0x1800090e2  jnz     loc_18000927C
0x1800090e8  xor     bl, bl
0x1800090ea  xor     edx, edx
0x1800090ec  mov     rcx, rbp
0x1800090ef  call    PsmpDereferenceApplicationEx
0x1800090f4  movzx   eax, bl
0x1800090f7  mov     rbx, [rsp+58h+arg_8]
0x1800090fc  add     rsp, 20h
0x180009100  pop     r15
0x180009102  pop     r14
0x180009104  pop     r13
0x180009106  pop     r12
0x180009108  pop     rdi
0x180009109  pop     rsi
0x18000910a  pop     rbp
0x18000910b  retn
0x18000910c  mov     r8, [r8]
0x18000910f  jmp     loc_180008F94
0x180009114  mov     r14, [r14]
0x180009117  jmp     loc_180008FF6
0x18000911c  mov     rcx, rdi; P
0x18000911f  call    PsmpDereferenceManagerContext
0x180009124  xor     bl, bl
0x180009126  jmp     short loc_1800090F4
0x180009128  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000912d  jmp     loc_180009098
0x180009132  cmp     eax, 4
0x180009135  jnz     loc_1800091FE
0x18000913b  lea     rcx, [rbp+148h]
0x180009142  call    cs:__imp_RtlAcquireSRWLockShared
0x180009148  mov     rdx, [rsp+58h+arg_20]
0x180009150  mov     rcx, rbp
0x180009153  call    PsmpFindHostJobContext
0x180009158  lea     rcx, [rbp+148h]
0x18000915f  mov     rdi, rax
0x180009162  call    cs:__imp_RtlReleaseSRWLockShared
0x180009168  test    rdi, rdi
0x18000916b  jz      loc_1800090E8
0x180009171  mov     rdx, [rdi+30h]
0x180009175  jmp     loc_1800090D6
0x18000917a  mov     rcx, [rsi+8]
0x18000917e  lea     rax, [rsi+8]
0x180009182  cmp     [rcx+8], rax
0x180009186  jnz     short loc_1800091F7
0x180009188  mov     rdx, [rax+8]
0x18000918c  cmp     [rdx], rax
0x18000918f  jnz     short loc_1800091F7
0x180009191  mov     [rdx], rcx
0x180009194  mov     r8, rsi; P
0x180009197  mov     [rcx+8], rdx
0x18000919b  xor     edx, edx; Flags
0x18000919d  mov     rcx, gs:60h
0x1800091a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800091aa  call    cs:__imp_RtlFreeHeap
0x1800091b0  jmp     loc_180009098
0x1800091b5  mov     rcx, [rsp+58h+ProcessHandle]; ProcessHandle
0x1800091bd  call    cs:__imp_NtIsProcessInJob
0x1800091c3  cmp     eax, 124h
0x1800091c8  jnz     loc_180009275
0x1800091ce  mov     bl, 1
0x1800091d0  test    rdi, rdi
0x1800091d3  jz      loc_1800090EA
0x1800091d9  xor     edx, edx
0x1800091db  mov     rcx, rdi
0x1800091de  call    PsmpDereferenceHostContext
0x1800091e3  jmp     loc_1800090EA
0x1800091e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800091ec  jz      loc_1800090D6
0x1800091f2  jmp     loc_1800090E8
0x1800091f7  mov     ecx, 3
0x1800091fc  int     29h; Win8: RtlFailFast(ecx)
0x1800091fe  cmp     eax, 6
0x180009201  jz      short loc_180009225
0x180009203  cmp     eax, 8
0x180009206  jnz     loc_1800090E8
0x18000920c  mov     rax, [rbp+1A98h]
0x180009213  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009217  jnz     short loc_180009266
0x180009219  mov     rdx, [rbp+0C8h]
0x180009220  jmp     loc_1800090D6
0x180009225  mov     rdx, [rbp+0B8h]
0x18000922c  jmp     loc_1800090D6
0x180009231  mov     rcx, cs:WPP_GLOBAL_Control
0x180009238  test    byte ptr [rcx+1Ch], 2
0x18000923c  jz      loc_180009124
0x180009242  cmp     byte ptr [rcx+19h], 2
0x180009246  jb      loc_180009124
0x18000924c  mov     rcx, [rcx+10h]
0x180009250  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180009257  mov     edx, 2Ch ; ','
0x18000925c  call    WPP_SF_
0x180009261  jmp     loc_180009124
0x180009266  cmp     rax, [rsp+58h+arg_20]
0x18000926e  jz      short loc_180009219
0x180009270  jmp     loc_1800090E8
0x180009275  xor     bl, bl
0x180009277  jmp     loc_1800091D0
0x18000927c  xor     edx, edx
0x18000927e  mov     rcx, rdi
0x180009281  call    PsmpDereferenceHostContext
0x180009286  jmp     loc_1800090E8
0x18000928b  lea     rcx, [rdi+8]
0x18000928f  call    cs:__imp_RtlReleaseSRWLockShared
0x180009295  jmp     loc_18000911C
0x18000929a  lea     rcx, PsmpManagerLock
0x1800092a1  call    cs:__imp_RtlReleaseSRWLockShared
0x1800092a7  jmp     loc_180009124
```
