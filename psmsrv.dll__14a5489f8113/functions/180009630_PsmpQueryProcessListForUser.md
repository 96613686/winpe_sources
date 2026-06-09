# PsmpQueryProcessListForUser

- ea: `0x180009630`
- end: `0x180009b33`
- name: `PsmpQueryProcessListForUser`
- size: `1283`
- prototype: `__int64 __fastcall(PSID Sid, int, WCHAR *, int, __int64, int, void *, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800092b4`
- `0x1800093d0`
- `0x180009630`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18001622c`
- `0x180017fa0`
- `0x180019c30`
- `0x18001b7e0`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800099db`
- `ntdll!RtlFreeHeap` at `0x180009a02`
- `ntdll!RtlFreeHeap` at `0x1800099db`
- `ntdll!RtlFreeHeap` at `0x180009a02`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009735`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800097a2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800098c2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009b14`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009b2b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009735`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800097a2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800098c2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009b14`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009b2b`
- `ntdll!NtQueryInformationJobObject` at `0x18000991a`
- `ntdll!NtQueryInformationJobObject` at `0x18000991a`
- `ntdll!RtlAllocateHeap` at `0x180009a2e`
- `ntdll!RtlAllocateHeap` at `0x180009a2e`
- `ntdll!RtlValidSid` at `0x180009692`
- `ntdll!RtlValidSid` at `0x180009692`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800097d1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800097d1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800097fc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800097fc`
- `ntdll!RtlEqualSid` at `0x180009776`
- `ntdll!RtlEqualSid` at `0x180009776`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800096e0`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009748`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800098a2`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800096e0`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009748`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800098a2`

## pseudocode

```c
__int64 __fastcall PsmpQueryProcessListForUser(
        PSID Sid,
        int a2,
        WCHAR *a3,
        int a4,
        __int64 a5,
        int a6,
        void *a7,
        _DWORD *a8)
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
  __int64 *HostJobContext; // rsi
  __int64 v27; // rax
  void *v28; // rbx
  unsigned int v29; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  _DWORD *v34; // r15
  ULONG v35; // r9d
  int *Heap; // r14
  int v37; // eax
  __int64 v38; // rcx
  signed __int32 **v39; // rdx
  __int64 v40; // rax
  ULONG ReturnLength; // [rsp+30h] [rbp-78h] BYREF
  int v42; // [rsp+34h] [rbp-74h]
  PSID Sid2; // [rsp+38h] [rbp-70h]
  _DWORD *v44; // [rsp+40h] [rbp-68h]
  void *v45; // [rsp+48h] [rbp-60h]
  __int128 JobInformation; // [rsp+50h] [rbp-58h] BYREF

  Sid2 = Sid;
  v45 = a7;
  v44 = a8;
  v42 = a4;
  JobInformation = 0;
  ReturnLength = 0;
  if ( RtlValidSid(Sid) )
  {
    v10 = -1;
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
LABEL_77:
                    PsmpDereferenceManagerContext((char *)v14);
                    goto LABEL_71;
                  }
                  v20 = j - 2;
                  if ( *(j - 1) == a2 )
                  {
                    if ( RtlEqualSid(*((PSID *)v20 + 5), Sid2) )
                      break;
                  }
LABEL_32:
                  ;
                }
                _m_prefetchw(v20);
                v21 = *v20;
                do
                {
                  if ( v21 <= 0 )
                    goto LABEL_32;
                  v16 = (unsigned int)v21;
                  v21 = _InterlockedCompareExchange(v20, v21 + 1, v21);
                }
                while ( v21 != (_DWORD)v16 );
                RtlReleaseSRWLockShared(v14 + 2, v16, v17, v18);
                if ( j == (signed __int32 *)8 )
                  goto LABEL_77;
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
                  v38 = *((_QWORD *)v20 + 1);
                  if ( *(signed __int32 **)(v38 + 8) != v20 + 2
                    || (v39 = (signed __int32 **)*((_QWORD *)v20 + 2), *v39 != v20 + 2) )
                  {
                    __fastfail(3u);
                  }
                  *v39 = (signed __int32 *)v38;
                  *(_QWORD *)(v38 + 8) = v39;
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
                }
                RtlReleaseSRWLockExclusive(v23 + 8);
                PsmpDereferenceManagerContext((char *)v14);
                if ( v24 )
                {
                  HostJobContext = 0;
                  if ( v42 != 2 )
                  {
                    switch ( v42 )
                    {
                      case 4:
                        RtlAcquireSRWLockShared(v24 + 41);
                        HostJobContext = PsmpFindHostJobContext((__int64)v24, a5);
                        RtlReleaseSRWLockShared(v24 + 41, v31, v32, v33);
                        if ( !HostJobContext )
                          goto LABEL_45;
                        v28 = (void *)HostJobContext[6];
                        goto LABEL_27;
                      case 8:
                        v40 = v24[851];
                        if ( v40 == a5 || v40 == -1 )
                        {
                          v28 = (void *)v24[25];
                          goto LABEL_27;
                        }
LABEL_45:
                        v29 = -1073741251;
                        break;
                      case 6:
                        v28 = (void *)v24[23];
                        goto LABEL_27;
                      default:
                        v29 = -1073741584;
                        break;
                    }
LABEL_29:
                    PsmpDereferenceApplicationEx((__int64)v24, 0);
                    return v29;
                  }
                  v27 = v24[850];
                  v28 = (void *)v24[24];
                  if ( v27 != a5 && v27 != -1 )
                    goto LABEL_45;
LABEL_27:
                  if ( !v28 )
                  {
                    v29 = -1073741275;
                    if ( !HostJobContext )
                      goto LABEL_29;
LABEL_51:
                    PsmpDereferenceHostContext(HostJobContext, 0);
                    goto LABEL_29;
                  }
                  v34 = v44;
                  if ( *v44 > 1u )
                  {
                    ReturnLength = 8 * *v44 + 8;
                    Heap = (int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength);
                    if ( Heap )
                    {
                      v35 = ReturnLength;
                      goto LABEL_39;
                    }
                    v29 = -1073741670;
                  }
                  else
                  {
                    v35 = 16;
                    Heap = (int *)&JobInformation;
                    ReturnLength = 16;
LABEL_39:
                    v29 = NtQueryInformationJobObject(v28, JobObjectBasicProcessIdList, Heap, v35, &ReturnLength);
                    if ( (int)(v29 + 0x80000000) < 0 || v29 == -2147483643 )
                    {
                      v37 = *Heap;
                      if ( *v34 < (unsigned int)*Heap )
                      {
                        v29 = -2147483643;
                      }
                      else
                      {
                        v29 = 0;
                        if ( !v37 )
                        {
                          *v34 = 0;
                          goto LABEL_48;
                        }
                        ReturnLength -= 8;
                        memcpy_0(v45, Heap + 2, ReturnLength);
                        v37 = *Heap;
                      }
                      *v34 = v37;
LABEL_48:
                      if ( Heap != (int *)&JobInformation )
                        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
                    }
                    else if ( Heap )
                    {
                      goto LABEL_48;
                    }
                  }
                  if ( !HostJobContext )
                    goto LABEL_29;
                  goto LABEL_51;
                }
              }
              goto LABEL_71;
            }
          }
        }
      }
      RtlReleaseSRWLockShared(&PsmpManagerLock, v12, i, &PsmpManagerList);
    }
LABEL_71:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
        (_DWORD)a3,
        a2);
    return (unsigned int)-1073741772;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids);
    return (unsigned int)-1073741585;
  }
}

```

## disassembly

```asm
0x180009630  mov     [rsp+arg_8], rbx
0x180009635  push    rbp
0x180009636  push    rsi
0x180009637  push    rdi
0x180009638  push    r12
0x18000963a  push    r13
0x18000963c  push    r14
0x18000963e  push    r15
0x180009640  sub     rsp, 70h
0x180009644  mov     rax, cs:__security_cookie
0x18000964b  xor     rax, rsp
0x18000964e  mov     [rsp+0A8h+var_48], rax
0x180009653  mov     rax, rcx
0x180009656  mov     [rsp+0A8h+Sid2], rcx
0x18000965b  mov     rcx, [rsp+0A8h+arg_30]
0x180009663  xorps   xmm0, xmm0
0x180009666  mov     [rsp+0A8h+var_60], rcx
0x18000966b  mov     r15, r8
0x18000966e  mov     rcx, [rsp+0A8h+arg_38]
0x180009676  mov     ebp, edx
0x180009678  mov     [rsp+0A8h+var_68], rcx
0x18000967d  mov     rcx, rax; Sid
0x180009680  mov     [rsp+0A8h+var_74], r9d
0x180009685  movups  [rsp+0A8h+JobInformation], xmm0
0x18000968a  mov     [rsp+0A8h+var_78], 0
0x180009692  call    cs:__imp_RtlValidSid
0x180009698  test    al, al
0x18000969a  jz      loc_180009A9B
0x1800096a0  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800096a7  nop     word ptr [rax+rax+00000000h]
0x1800096b0  cmp     word ptr [r15+rdi*2+2], 0
0x1800096b7  lea     rdi, [rdi+1]
0x1800096bb  jnz     short loc_1800096B0
0x1800096bd  mov     esi, [rsp+0A8h+arg_28]
0x1800096c4  test    esi, 0FFFFFFF3h
0x1800096ca  jnz     loc_180009ACD
0x1800096d0  cmp     esi, 0Ch
0x1800096d3  jz      loc_180009ACD
0x1800096d9  lea     rcx, PsmpManagerLock
0x1800096e0  call    cs:__imp_RtlAcquireSRWLockShared
0x1800096e6  mov     r8, cs:PsmpManagerList
0x1800096ed  lea     r9, PsmpManagerList
0x1800096f4  cmp     r8, r9
0x1800096f7  jz      loc_180009B24
0x1800096fd  cmp     ebp, [r8-14h]
0x180009701  lea     rbx, [r8-28h]
0x180009705  jnz     loc_180009882
0x18000970b  cmp     esi, [rbx+10h]
0x18000970e  jnz     loc_180009882
0x180009714  prefetchw byte ptr [rbx]
0x180009717  mov     eax, [rbx]
0x180009719  test    eax, eax
0x18000971b  jle     loc_180009882
0x180009721  mov     edx, eax
0x180009723  lea     ecx, [rax+1]
0x180009726  lock cmpxchg [rbx], ecx
0x18000972a  cmp     eax, edx
0x18000972c  jnz     short loc_180009719
0x18000972e  lea     rcx, PsmpManagerLock
0x180009735  call    cs:__imp_RtlReleaseSRWLockShared
0x18000973b  test    rbx, rbx
0x18000973e  jz      loc_180009ACD
0x180009744  lea     rcx, [rbx+8]
0x180009748  call    cs:__imp_RtlAcquireSRWLockShared
0x18000974e  mov     r14, [rbx+18h]
0x180009752  lea     r12, [rbx+18h]
0x180009756  cmp     r14, r12
0x180009759  jz      loc_180009B10
0x18000975f  cmp     [r14-4], ebp
0x180009763  lea     rsi, [r14-8]
0x180009767  jnz     loc_18000988A
0x18000976d  mov     rdx, [rsp+0A8h+Sid2]; Sid2
0x180009772  mov     rcx, [rsi+28h]; Sid1
0x180009776  call    cs:__imp_RtlEqualSid
0x18000977c  test    al, al
0x18000977e  jz      loc_18000988A
0x180009784  prefetchw byte ptr [rsi]
0x180009787  mov     eax, [rsi]
0x180009789  test    eax, eax
0x18000978b  jle     loc_18000988A
0x180009791  mov     edx, eax
0x180009793  lea     ecx, [rax+1]
0x180009796  lock cmpxchg [rsi], ecx
0x18000979a  cmp     eax, edx
0x18000979c  jnz     short loc_180009789
0x18000979e  lea     rcx, [rbx+8]
0x1800097a2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800097a8  test    rsi, rsi
0x1800097ab  jz      loc_180009B1A
0x1800097b1  lea     r9, ds:2[rdi*2]
0x1800097b9  mov     r8, r15
0x1800097bc  mov     rdx, rsi
0x1800097bf  xor     ecx, ecx
0x1800097c1  call    PsmpFindApplication
0x1800097c6  mov     r14, [rsi+38h]
0x1800097ca  mov     rdi, rax
0x1800097cd  lea     rcx, [r14+8]
0x1800097d1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800097d7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800097de  lock xadd [rsi], eax
0x1800097e2  dec     eax
0x1800097e4  cmp     eax, 0FFFFFFFFh
0x1800097e7  jz      loc_1800098DA
0x1800097ed  test    eax, 7FFFFFFFh
0x1800097f2  jz      loc_1800099AB
0x1800097f8  lea     rcx, [r14+8]
0x1800097fc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009802  mov     rcx, rbx; P
0x180009805  call    PsmpDereferenceManagerContext
0x18000980a  test    rdi, rdi
0x18000980d  jz      loc_180009ACD
0x180009813  mov     eax, [rsp+0A8h+var_74]
0x180009817  xor     esi, esi
0x180009819  cmp     eax, 2
0x18000981c  jnz     short loc_180009892
0x18000981e  mov     rax, [rdi+1A90h]
0x180009825  mov     rbx, [rdi+0C0h]
0x18000982c  cmp     rax, [rsp+0A8h+arg_20]
0x180009834  jnz     loc_180009968
0x18000983a  test    rbx, rbx
0x18000983d  jnz     loc_1800098E4
0x180009843  mov     ebx, 0C0000225h
0x180009848  test    rsi, rsi
0x18000984b  jnz     loc_18000999C
0x180009851  xor     edx, edx
0x180009853  mov     rcx, rdi
0x180009856  call    PsmpDereferenceApplicationEx
0x18000985b  mov     eax, ebx
0x18000985d  mov     rcx, [rsp+0A8h+var_48]
0x180009862  xor     rcx, rsp; StackCookie
0x180009865  call    __security_check_cookie
0x18000986a  mov     rbx, [rsp+0A8h+arg_8]
0x180009872  add     rsp, 70h
0x180009876  pop     r15
0x180009878  pop     r14
0x18000987a  pop     r13
0x18000987c  pop     r12
0x18000987e  pop     rdi
0x18000987f  pop     rsi
0x180009880  pop     rbp
0x180009881  retn
0x180009882  mov     r8, [r8]
0x180009885  jmp     loc_1800096F4
0x18000988a  mov     r14, [r14]
0x18000988d  jmp     loc_180009756
0x180009892  cmp     eax, 4
0x180009895  jnz     loc_180009A4A
0x18000989b  lea     rcx, [rdi+148h]
0x1800098a2  call    cs:__imp_RtlAcquireSRWLockShared
0x1800098a8  mov     rdx, [rsp+0A8h+arg_20]
0x1800098b0  mov     rcx, rdi
0x1800098b3  call    PsmpFindHostJobContext
0x1800098b8  lea     rcx, [rdi+148h]
0x1800098bf  mov     rsi, rax
0x1800098c2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800098c8  test    rsi, rsi
0x1800098cb  jz      loc_180009972
0x1800098d1  mov     rbx, [rsi+30h]
0x1800098d5  jmp     loc_18000983A
0x1800098da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800098df  jmp     loc_1800097F8
0x1800098e4  mov     r15, [rsp+0A8h+var_68]
0x1800098e9  mov     eax, [r15]
0x1800098ec  cmp     eax, 1
0x1800098ef  ja      loc_180009A11
0x1800098f5  mov     r9d, 10h; JobInformationLength
0x1800098fb  lea     r14, [rsp+0A8h+JobInformation]
0x180009900  mov     [rsp+0A8h+var_78], r9d
0x180009905  lea     rax, [rsp+0A8h+var_78]
0x18000990a  mov     r8, r14; JobInformation
0x18000990d  mov     edx, 3; JobInformationClass
0x180009912  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x180009917  mov     rcx, rbx; JobHandle
0x18000991a  call    cs:__imp_NtQueryInformationJobObject
0x180009920  mov     ebx, eax
0x180009922  mov     eax, 80000000h
0x180009927  lea     ecx, [rbx+rax]
0x18000992a  test    eax, ecx
0x18000992c  jz      short loc_18000997C
0x18000992e  mov     eax, [r14]
0x180009931  cmp     [r15], eax
0x180009934  jb      loc_1800099E6
0x18000993a  xor     ebx, ebx
0x18000993c  test    eax, eax
0x18000993e  jz      loc_180009A91
0x180009944  mov     eax, [rsp+0A8h+var_78]
0x180009948  lea     rdx, [r14+8]; Src
0x18000994c  mov     rcx, [rsp+0A8h+var_60]; void *
0x180009951  add     eax, 0FFFFFFF8h
0x180009954  mov     r8d, eax; Size
0x180009957  mov     [rsp+0A8h+var_78], eax
0x18000995b  call    memcpy_0
0x180009960  mov     eax, [r14]
0x180009963  mov     [r15], eax
0x180009966  jmp     short loc_180009989
0x180009968  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000996c  jz      loc_18000983A
0x180009972  mov     ebx, 0C000023Dh
0x180009977  jmp     loc_180009851
0x18000997c  cmp     ebx, 80000005h
0x180009982  jz      short loc_18000992E
0x180009984  test    r14, r14
0x180009987  jz      short loc_180009993
0x180009989  lea     rax, [rsp+0A8h+JobInformation]
0x18000998e  cmp     r14, rax
0x180009991  jnz     short loc_1800099F0
0x180009993  test    rsi, rsi
0x180009996  jz      loc_180009851
0x18000999c  xor     edx, edx
0x18000999e  mov     rcx, rsi
0x1800099a1  call    PsmpDereferenceHostContext
0x1800099a6  jmp     loc_180009851
0x1800099ab  mov     rcx, [rsi+8]
0x1800099af  lea     rax, [rsi+8]
0x1800099b3  cmp     [rcx+8], rax
0x1800099b7  jnz     short loc_180009A0A
0x1800099b9  mov     rdx, [rax+8]
0x1800099bd  cmp     [rdx], rax
0x1800099c0  jnz     short loc_180009A0A
0x1800099c2  mov     [rdx], rcx
0x1800099c5  mov     r8, rsi; P
0x1800099c8  mov     [rcx+8], rdx
0x1800099cc  xor     edx, edx; Flags
0x1800099ce  mov     rcx, gs:60h
0x1800099d7  mov     rcx, [rcx+30h]; HeapHandle
0x1800099db  call    cs:__imp_RtlFreeHeap
0x1800099e1  jmp     loc_1800097F8
0x1800099e6  mov     ebx, 80000005h
0x1800099eb  jmp     loc_180009963
0x1800099f0  mov     rcx, gs:60h
0x1800099f9  mov     r8, r14; P
0x1800099fc  xor     edx, edx; Flags
0x1800099fe  mov     rcx, [rcx+30h]; HeapHandle
0x180009a02  call    cs:__imp_RtlFreeHeap
0x180009a08  jmp     short loc_180009993
0x180009a0a  mov     ecx, 3
0x180009a0f  int     29h; Win8: RtlFailFast(ecx)
0x180009a11  lea     eax, ds:8[rax*8]
0x180009a18  xor     edx, edx; Flags
0x180009a1a  mov     [rsp+0A8h+var_78], eax
0x180009a1e  mov     rcx, gs:60h
0x180009a27  mov     r8d, eax; Size
0x180009a2a  mov     rcx, [rcx+30h]; HeapHandle
0x180009a2e  call    cs:__imp_RtlAllocateHeap
0x180009a34  mov     r14, rax
0x180009a37  test    rax, rax
0x180009a3a  jz      loc_180009B06
0x180009a40  mov     r9d, [rsp+0A8h+var_78]
0x180009a45  jmp     loc_180009905
0x180009a4a  cmp     eax, 8
0x180009a4d  jnz     short loc_180009A76
0x180009a4f  mov     rax, [rdi+1A98h]
0x180009a56  cmp     rax, [rsp+0A8h+arg_20]
0x180009a5e  jz      short loc_180009A6A
0x180009a60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009a64  jnz     loc_180009972
0x180009a6a  mov     rbx, [rdi+0C8h]
0x180009a71  jmp     loc_18000983A
0x180009a76  cmp     eax, 6
0x180009a79  jz      short loc_180009A85
0x180009a7b  mov     ebx, 0C00000F0h
0x180009a80  jmp     loc_180009851
0x180009a85  mov     rbx, [rdi+0B8h]
0x180009a8c  jmp     loc_18000983A
0x180009a91  xor     eax, eax
0x180009a93  mov     [r15], eax
0x180009a96  jmp     loc_180009989
0x180009a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aa2  test    byte ptr [rcx+1Ch], 2
0x180009aa6  jz      short loc_180009AC3
0x180009aa8  cmp     byte ptr [rcx+19h], 2
0x180009aac  jb      short loc_180009AC3
0x180009aae  mov     rcx, [rcx+10h]
0x180009ab2  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180009ab9  mov     edx, 35h ; '5'
0x180009abe  call    WPP_SF_
0x180009ac3  mov     ebx, 0C00000EFh
0x180009ac8  jmp     loc_18000985B
0x180009acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ad4  test    byte ptr [rcx+1Ch], 2
0x180009ad8  jz      short loc_180009AFC
0x180009ada  cmp     byte ptr [rcx+19h], 2
0x180009ade  jb      short loc_180009AFC
0x180009ae0  mov     rcx, [rcx+10h]
0x180009ae4  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180009aeb  mov     edx, 36h ; '6'
0x180009af0  mov     dword ptr [rsp+0A8h+ReturnLength], ebp
0x180009af4  mov     r9, r15
0x180009af7  call    WPP_SF_Sd
0x180009afc  mov     ebx, 0C0000034h
0x180009b01  jmp     loc_18000985B
0x180009b06  mov     ebx, 0C000009Ah
0x180009b0b  jmp     loc_180009993
0x180009b10  lea     rcx, [rbx+8]
0x180009b14  call    cs:__imp_RtlReleaseSRWLockShared
0x180009b1a  mov     rcx, rbx; P
0x180009b1d  call    PsmpDereferenceManagerContext
0x180009b22  jmp     short loc_180009ACD
0x180009b24  lea     rcx, PsmpManagerLock
0x180009b2b  call    cs:__imp_RtlReleaseSRWLockShared
  ... truncated ...
```
