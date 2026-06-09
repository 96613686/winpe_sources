# DhcpRenewThread

- ea: `0x180021db0`
- end: `0x180021fdc`
- name: `DhcpRenewThread`
- size: `556`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002534`
- `0x180015428`
- `0x180019afc`
- `0x18001cef0`
- `0x180021c14`
- `0x180021db0`
- `0x180042934`
- `0x180042a74`
- `0x180049750`
- `0x180049ae8`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021e76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021f62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021e76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021f62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ed0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ed0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021ebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021ebd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021e61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021f4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021e61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021f4e`

## pseudocode

```c
__int64 __fastcall DhcpRenewThread(char *Parameter)
{
  char *v1; // r15
  int v2; // r13d
  __int64 v3; // rbx
  unsigned int v4; // r12d
  char *v5; // rdi
  _QWORD v7[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v8; // [rsp+48h] [rbp-30h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF

  v7[0] = v7;
  v7[1] = v7;
  v1 = Parameter;
  v9 = 0;
  v2 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_J_guid_(
      (_DWORD)Parameter,
      113,
      (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids,
      *((_QWORD *)Parameter + 3),
      (__int64)(Parameter + 2112));
    Parameter = v1;
  }
  v3 = *((_QWORD *)v1 + 3);
  v9 = *((_OWORD *)Parameter + 132);
  v4 = DhcpSetThreadCompartmentId(*((_DWORD *)v1 + 13));
  if ( !v4 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v1 + 84);
    v2 = 1;
    *((_DWORD *)v1 + 162) = 1;
    ReleaseSRWLockExclusive((PSRWLOCK)v1 + 84);
    while ( 1 )
    {
      v8 = 0;
      ExchangeRenewalParameters(v1, &v8, v7);
      if ( !v8 )
        break;
      DhcpProcessRenewalOperation(v1, v8, v7);
      if ( (_QWORD *)v7[0] != v7 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_(1025, 115, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
        FinishCompletionList(v7, 1223);
        goto LABEL_14;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 592));
      v5 = (char *)*((_QWORD *)v1 + 79);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 592));
      if ( v5 == v1 + 632 )
        goto LABEL_15;
    }
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 114, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
LABEL_14:
    v4 = 5023;
  }
LABEL_15:
  FinishCompletionList(v7, 1223);
  if ( v2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v1 + 84);
    *((_DWORD *)v1 + 162) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v1 + 84);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 4, 0xFFFFFFFF) == 1 )
    DhcpDestroyContextEx((__int64)v1);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_DJ_guid_(1028, 116, (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v4, v3, (__int64)&v9);
  return v4;
}

```

## disassembly

```asm
0x180021db0  push    rbp
0x180021db2  push    rbx
0x180021db3  push    rsi
0x180021db4  push    rdi
0x180021db5  push    r12
0x180021db7  push    r13
0x180021db9  push    r14
0x180021dbb  push    r15
0x180021dbd  mov     rbp, rsp
0x180021dc0  sub     rsp, 78h
0x180021dc4  mov     rax, cs:__security_cookie
0x180021dcb  xor     rax, rsp
0x180021dce  mov     [rbp+var_18], rax
0x180021dd2  lea     rax, [rbp+var_40]
0x180021dd6  mov     [rbp+CompartmentId], 0
0x180021ddd  mov     [rbp+var_40], rax
0x180021de1  xorps   xmm0, xmm0
0x180021de4  lea     rax, [rbp+var_40]
0x180021de8  mov     [rbp+var_48], 0
0x180021def  mov     [rbp+var_38], rax
0x180021df3  mov     r15, rcx
0x180021df6  movups  [rbp+var_28], xmm0
0x180021dfa  xor     r13d, r13d
0x180021dfd  test    byte ptr cs:xmmword_1800616A0, 10h
0x180021e04  jz      short loc_180021E29
0x180021e06  mov     r9, [rcx+18h]
0x180021e0a  lea     rax, [rcx+840h]
0x180021e11  lea     edx, [r13+71h]
0x180021e15  mov     [rsp+78h+var_58], rax
0x180021e1a  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180021e21  call    WPP_SF_J_guid_
0x180021e26  mov     rcx, r15
0x180021e29  mov     rbx, [r15+18h]
0x180021e2d  lea     r8, [rbp+var_48]
0x180021e31  mov     eax, 840h
0x180021e36  lea     rdx, [rbp+CompartmentId]
0x180021e3a  movups  xmm0, xmmword ptr [rax+rcx]
0x180021e3e  movdqu  [rbp+var_28], xmm0
0x180021e43  mov     ecx, [r15+34h]; CompartmentId
0x180021e47  call    DhcpSetThreadCompartmentId
0x180021e4c  mov     r12d, eax
0x180021e4f  test    eax, eax
0x180021e51  jnz     loc_180021F31
0x180021e57  lea     rdi, [r15+2A0h]
0x180021e5e  mov     rcx, rdi; SRWLock
0x180021e61  call    cs:__imp_AcquireSRWLockExclusive
0x180021e67  lea     r13d, [r12+1]
0x180021e6c  mov     rcx, rdi; SRWLock
0x180021e6f  mov     [r15+288h], r13d
0x180021e76  call    cs:__imp_ReleaseSRWLockExclusive
0x180021e7c  lea     r8, [rbp+var_40]
0x180021e80  mov     [rbp+var_30], 0
0x180021e88  lea     rdx, [rbp+var_30]
0x180021e8c  mov     rcx, r15
0x180021e8f  call    ExchangeRenewalParameters
0x180021e94  mov     rdx, [rbp+var_30]
0x180021e98  test    rdx, rdx
0x180021e9b  jz      short loc_180021F0C
0x180021e9d  lea     r8, [rbp+var_40]
0x180021ea1  mov     rcx, r15
0x180021ea4  call    DhcpProcessRenewalOperation
0x180021ea9  lea     rax, [rbp+var_40]
0x180021ead  cmp     [rbp+var_40], rax
0x180021eb1  jnz     short loc_180021EDD
0x180021eb3  lea     r14, [r15+250h]
0x180021eba  mov     rcx, r14; lpCriticalSection
0x180021ebd  call    cs:__imp_EnterCriticalSection
0x180021ec3  lea     rsi, [r15+278h]
0x180021eca  mov     rcx, r14; lpCriticalSection
0x180021ecd  mov     rdi, [rsi]
0x180021ed0  call    cs:__imp_LeaveCriticalSection
0x180021ed6  cmp     rdi, rsi
0x180021ed9  jnz     short loc_180021E7C
0x180021edb  jmp     short loc_180021F31
0x180021edd  test    byte ptr cs:xmmword_1800616A0, 2
0x180021ee4  jz      short loc_180021EFC
0x180021ee6  mov     edx, 73h ; 's'
0x180021eeb  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180021ef2  mov     ecx, 401h
0x180021ef7  call    WPP_SF_
0x180021efc  mov     edx, 4C7h
0x180021f01  lea     rcx, [rbp+var_40]
0x180021f05  call    FinishCompletionList
0x180021f0a  jmp     short loc_180021F2B
0x180021f0c  test    byte ptr cs:xmmword_1800616A0, 2
0x180021f13  jz      short loc_180021F2B
0x180021f15  mov     edx, 72h ; 'r'
0x180021f1a  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180021f21  mov     ecx, 401h
0x180021f26  call    WPP_SF_
0x180021f2b  mov     r12d, 139Fh
0x180021f31  mov     edx, 4C7h
0x180021f36  lea     rcx, [rbp+var_40]
0x180021f3a  call    FinishCompletionList
0x180021f3f  test    r13d, r13d
0x180021f42  jz      short loc_180021F68
0x180021f44  lea     rdi, [r15+2A0h]
0x180021f4b  mov     rcx, rdi; SRWLock
0x180021f4e  call    cs:__imp_AcquireSRWLockExclusive
0x180021f54  mov     rcx, rdi; SRWLock
0x180021f57  mov     dword ptr [r15+288h], 0
0x180021f62  call    cs:__imp_ReleaseSRWLockExclusive
0x180021f68  cmp     [rbp+var_48], 0
0x180021f6c  jz      short loc_180021F76
0x180021f6e  mov     ecx, [rbp+CompartmentId]; CompartmentId
0x180021f71  call    DhcpRevertThreadCompartmentId
0x180021f76  or      eax, 0FFFFFFFFh
0x180021f79  lock xadd [r15+10h], eax
0x180021f7f  cmp     eax, 1
0x180021f82  jnz     short loc_180021F8C
0x180021f84  mov     rcx, r15
0x180021f87  call    DhcpDestroyContextEx
0x180021f8c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180021f93  jz      short loc_180021FBC
0x180021f95  lea     rax, [rbp+var_28]
0x180021f99  mov     edx, 74h ; 't'
0x180021f9e  mov     [rsp+78h+var_50], rax
0x180021fa3  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180021faa  mov     ecx, 404h
0x180021faf  mov     [rsp+78h+var_58], rbx
0x180021fb4  mov     r9d, r12d
0x180021fb7  call    WPP_SF_DJ_guid_
0x180021fbc  mov     eax, r12d
0x180021fbf  mov     rcx, [rbp+var_18]
0x180021fc3  xor     rcx, rsp; StackCookie
0x180021fc6  call    __security_check_cookie
0x180021fcb  add     rsp, 78h
0x180021fcf  pop     r15
0x180021fd1  pop     r14
0x180021fd3  pop     r13
0x180021fd5  pop     r12
0x180021fd7  pop     rdi
0x180021fd8  pop     rsi
0x180021fd9  pop     rbx
0x180021fda  pop     rbp
0x180021fdb  retn
```
