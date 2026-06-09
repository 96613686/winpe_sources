# GetDnsRpcBindingHandleRef

- ea: `0x180014b5c`
- end: `0x180014dc5`
- name: `GetDnsRpcBindingHandleRef`
- size: `617`
- prototype: ``
- caller_count: `39`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014738`
- `0x1800161b0`
- `0x1800164d0`
- `0x1800167b4`
- `0x180064c40`
- `0x180074624`
- `0x18007578c`
- `0x180075af8`
- `0x180077dd4`
- `0x180078374`
- `0x180078574`
- `0x180085790`
- `0x180085f90`
- `0x1800893bc`
- `0x180090070`
- `0x1800901b0`
- `0x180090460`
- `0x18009062c`
- `0x180090860`
- `0x1800909d0`
- `0x180090d20`
- `0x180090e60`
- `0x180090fe0`
- `0x1800912f0`
- `0x180091460`
- `0x1800915a0`
- `0x180091710`
- `0x180091e84`
- `0x1800927c0`
- `0x180095968`
- `0x1800980e0`
- `0x1800982c0`
- `0x1800984e0`
- `0x180098670`
- `0x180098880`
- `0x180098aa0`
- `0x180098c80`
- `0x1800ac5c0`
- `0x1800ac8a0`

## callees

- `0x180014b5c`
- `0x1800160b0`
- `0x180016394`
- `0x1800163fc`
- `0x18003de30`
- `0x180062788`
- `0x180065520`
- `0x180067dc4`
- `0x18006cf08`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dfb48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014baf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014baf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014c39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014c39`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014c61`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014c61`

## pseudocode

```c
__int64 __fastcall GetDnsRpcBindingHandleRef(_QWORD *a1)
{
  signed int v1; // ebx
  RTL_SRWLOCK *v2; // rdi
  int v3; // r14d
  __int64 v5; // rax
  int v6; // r12d
  unsigned int v7; // ebx
  LPWSTR CommandLineW; // rax
  int started; // eax
  int v11; // eax
  signed int v12; // esi
  CWxRpcBinding *v13; // rdx
  int v14; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+20h] [rbp-30h]
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  CWxRpcBinding *v17; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v18; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+4Ch] [rbp-4h]

  v1 = 0;
  v2 = &g_srwDnsRpcBindingLock;
  v3 = 0;
  v20 = 0;
  v18 = &g_srwDnsRpcBindingLock;
  v16 = 0;
  v17 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1035, 10, WPP_96dab6e5195d34c67ab15726a5516004_Traceguids, CommandLineW);
  }
  WxZeroOut<DnsRpcBindingRef>(a1);
  AcquireSRWLockShared(&g_srwDnsRpcBindingLock);
  AutoInterface<CWxRpcBinding>::operator=(&v16, g_pRpcBinding);
  ReleaseSRWLockShared(&g_srwDnsRpcBindingLock);
  v5 = v16;
  v6 = 0;
  v19 = 0;
  if ( v16 )
    goto LABEL_4;
  v11 = CWxRpcBinding::CreateInstance(qword_1800EB130, L"DNSResolver", qword_1800F8D60, qword_1800F8DA8, v14, &v17);
  v12 = v11;
  if ( v11 >= 0 )
    goto LABEL_25;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v15 = g_fSkipServiceRestart;
    WPP_SF_Dl(
      (unsigned int)g_fSkipServiceRestart,
      11,
      WPP_96dab6e5195d34c67ab15726a5516004_Traceguids,
      (unsigned int)v11);
  }
  if ( g_fSkipServiceRestart )
  {
    v1 = v12;
    HIDWORD(v16) = 84;
    goto LABEL_5;
  }
  started = StartDnsServiceOnDemand();
  v1 = started;
  if ( started > 0 )
    v1 = (unsigned __int16)started | 0x80070000;
  if ( v1 < 0 )
  {
    HIDWORD(v16) = 87;
    goto LABEL_5;
  }
  v1 = CWxRpcBinding::CreateInstance(qword_1800EB130, L"DNSResolver", qword_1800F8D60, qword_1800F8DA8, v15, &v17);
  if ( v1 >= 0 )
  {
LABEL_25:
    AutoSrw::LockExclusive((AutoSrw *)&v18);
    v13 = g_pRpcBinding;
    if ( !g_pRpcBinding )
    {
      v13 = v17;
      g_pRpcBinding = v17;
      v17 = 0;
    }
    AutoInterface<CWxRpcBinding>::operator=(&v16, v13);
    AutoSrw::UnlockExclusive((AutoSrw *)&v18);
    v5 = v16;
    v3 = v20;
    v6 = v19;
    v2 = v18;
LABEL_4:
    a1[1] = *(_QWORD *)(v5 + 8);
    *a1 = v5;
    goto LABEL_5;
  }
  HIDWORD(v16) = 94;
LABEL_5:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 12, WPP_96dab6e5195d34c67ab15726a5516004_Traceguids, (unsigned int)v1);
  v7 = WX_WIN32_FROM_HR((unsigned int)v1);
  if ( v17 )
    CWxRpcBinding::Release(v17);
  if ( v6 )
    ReleaseSRWLockShared(v2);
  if ( v3 )
    ReleaseSRWLockExclusive(v2);
  return v7;
}

```

## disassembly

```asm
0x180014b5c  mov     [rsp-28h+arg_8], rbx
0x180014b61  mov     [rsp-28h+arg_10], rsi
0x180014b66  push    rbp
0x180014b67  push    rdi
0x180014b68  push    r12
0x180014b6a  push    r14
0x180014b6c  push    r15
0x180014b6e  mov     rbp, rsp
0x180014b71  sub     rsp, 50h
0x180014b75  xor     ebx, ebx
0x180014b77  lea     rdi, ?g_srwDnsRpcBindingLock@@3VWxSrw@@A; WxSrw g_srwDnsRpcBindingLock
0x180014b7e  xor     r14d, r14d
0x180014b81  mov     dword ptr [rbp+var_20+4], ebx
0x180014b84  mov     [rbp+var_4], r14d
0x180014b88  mov     r15, rcx
0x180014b8b  mov     [rbp+var_10], rdi
0x180014b8f  mov     [rbp+var_20], rbx
0x180014b93  mov     [rbp+var_18], rbx
0x180014b97  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180014b9e  jnz     loc_180014C61
0x180014ba4  mov     rcx, r15
0x180014ba7  call    ??$WxZeroOut@UDnsRpcBindingRef@@@@YAXPEAUDnsRpcBindingRef@@@Z; WxZeroOut<DnsRpcBindingRef>(DnsRpcBindingRef *)
0x180014bac  mov     rcx, rdi; SRWLock
0x180014baf  call    cs:__imp_AcquireSRWLockShared
0x180014bb6  nop     dword ptr [rax+rax+00h]
0x180014bbb  mov     rdx, cs:?g_pRpcBinding@@3PEAVCWxRpcBinding@@EA; CWxRpcBinding * g_pRpcBinding
0x180014bc2  lea     rcx, [rbp+var_20]
0x180014bc6  call    ??4?$AutoInterface@VCWxRpcBinding@@@@QEAAXPEAVCWxRpcBinding@@@Z; AutoInterface<CWxRpcBinding>::operator=(CWxRpcBinding *)
0x180014bcb  mov     rcx, rdi; SRWLock
0x180014bce  call    cs:__imp_ReleaseSRWLockShared
0x180014bd5  nop     dword ptr [rax+rax+00h]
0x180014bda  mov     rax, [rbp+var_20]
0x180014bde  xor     r12d, r12d
0x180014be1  mov     [rbp+var_8], r12d
0x180014be5  test    rax, rax
0x180014be8  jz      loc_180014CAF
0x180014bee  mov     rdx, [rax+8]
0x180014bf2  mov     [r15+8], rdx
0x180014bf6  mov     [r15], rax
0x180014bf9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180014c00  jnz     loc_180014DA7
0x180014c06  mov     ecx, ebx
0x180014c08  call    WX_WIN32_FROM_HR
0x180014c0d  mov     rcx, [rbp+var_18]; this
0x180014c11  mov     ebx, eax
0x180014c13  test    rcx, rcx
0x180014c16  jz      short loc_180014C1D
0x180014c18  call    ?Release@CWxRpcBinding@@QEAAKXZ; CWxRpcBinding::Release(void)
0x180014c1d  test    r12d, r12d
0x180014c20  jz      short loc_180014C31
0x180014c22  mov     rcx, rdi; SRWLock
0x180014c25  call    cs:__imp_ReleaseSRWLockShared
0x180014c2c  nop     dword ptr [rax+rax+00h]
0x180014c31  test    r14d, r14d
0x180014c34  jz      short loc_180014C45
0x180014c36  mov     rcx, rdi; SRWLock
0x180014c39  call    cs:__imp_ReleaseSRWLockExclusive
0x180014c40  nop     dword ptr [rax+rax+00h]
0x180014c45  lea     r11, [rsp+50h+var_s0]
0x180014c4a  mov     eax, ebx
0x180014c4c  mov     rbx, [r11+38h]
0x180014c50  mov     rsi, [r11+40h]
0x180014c54  mov     rsp, r11
0x180014c57  pop     r15
0x180014c59  pop     r14
0x180014c5b  pop     r12
0x180014c5d  pop     rdi
0x180014c5e  pop     rbp
0x180014c5f  retn
0x180014c61  call    cs:__imp_GetCommandLineW
0x180014c68  nop     dword ptr [rax+rax+00h]
0x180014c6d  mov     edx, 0Ah
0x180014c72  lea     r8, WPP_96dab6e5195d34c67ab15726a5516004_Traceguids
0x180014c79  mov     r9, rax
0x180014c7c  mov     ecx, 40Bh
0x180014c81  call    WPP_SF_S
0x180014c86  jmp     loc_180014BA4
0x180014c8b  call    StartDnsServiceOnDemand
0x180014c90  mov     ebx, eax
0x180014c92  test    eax, eax
0x180014c94  jle     short loc_180014C9F
0x180014c96  movzx   ebx, ax
0x180014c99  or      ebx, 80070000h
0x180014c9f  test    ebx, ebx
0x180014ca1  jns     short loc_180014D20
0x180014ca3  mov     dword ptr [rbp+var_20+4], 57h ; 'W'
0x180014caa  jmp     loc_180014BF9
0x180014caf  lea     rax, [rbp+var_18]
0x180014cb3  lea     r9, qword_1800F8DA8; void *
0x180014cba  mov     [rsp+50h+var_28], rax; struct CWxRpcBinding **
0x180014cbf  lea     r8, qword_1800F8D60; void *
0x180014cc6  lea     rdx, aDnsresolver; "DNSResolver"
0x180014ccd  lea     rcx, qword_1800EB130; void *
0x180014cd4  call    ?CreateInstance@CWxRpcBinding@@SAJPEAXPEBG00HPEAPEAV1@@Z; CWxRpcBinding::CreateInstance(void *,ushort const *,void *,void *,int,CWxRpcBinding * *)
0x180014cd9  mov     esi, eax
0x180014cdb  test    eax, eax
0x180014cdd  jns     short loc_180014D5C
0x180014cdf  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180014ce6  jz      short loc_180014D06
0x180014ce8  mov     ecx, cs:?g_fSkipServiceRestart@@3HA; int g_fSkipServiceRestart
0x180014cee  lea     r8, WPP_96dab6e5195d34c67ab15726a5516004_Traceguids
0x180014cf5  mov     edx, 0Bh
0x180014cfa  mov     [rsp+50h+var_30], ecx; int
0x180014cfe  mov     r9d, eax
0x180014d01  call    WPP_SF_Dl
0x180014d06  cmp     cs:?g_fSkipServiceRestart@@3HA, ebx; int g_fSkipServiceRestart
0x180014d0c  jz      loc_180014C8B
0x180014d12  mov     ebx, esi
0x180014d14  mov     dword ptr [rbp+var_20+4], 54h ; 'T'
0x180014d1b  jmp     loc_180014BF9
0x180014d20  lea     rax, [rbp+var_18]
0x180014d24  lea     r9, qword_1800F8DA8; void *
0x180014d2b  mov     [rsp+50h+var_28], rax; struct CWxRpcBinding **
0x180014d30  lea     r8, qword_1800F8D60; void *
0x180014d37  lea     rdx, aDnsresolver; "DNSResolver"
0x180014d3e  lea     rcx, qword_1800EB130; void *
0x180014d45  call    ?CreateInstance@CWxRpcBinding@@SAJPEAXPEBG00HPEAPEAV1@@Z; CWxRpcBinding::CreateInstance(void *,ushort const *,void *,void *,int,CWxRpcBinding * *)
0x180014d4a  mov     ebx, eax
0x180014d4c  test    eax, eax
0x180014d4e  jns     short loc_180014D5C
0x180014d50  mov     dword ptr [rbp+var_20+4], 5Eh ; '^'
0x180014d57  jmp     loc_180014BF9
0x180014d5c  lea     rcx, [rbp+var_10]; this
0x180014d60  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x180014d65  mov     rdx, cs:?g_pRpcBinding@@3PEAVCWxRpcBinding@@EA; CWxRpcBinding * g_pRpcBinding
0x180014d6c  test    rdx, rdx
0x180014d6f  jnz     short loc_180014D80
0x180014d71  mov     rdx, [rbp+var_18]
0x180014d75  mov     cs:?g_pRpcBinding@@3PEAVCWxRpcBinding@@EA, rdx; CWxRpcBinding * g_pRpcBinding
0x180014d7c  mov     [rbp+var_18], r12
0x180014d80  lea     rcx, [rbp+var_20]
0x180014d84  call    ??4?$AutoInterface@VCWxRpcBinding@@@@QEAAXPEAVCWxRpcBinding@@@Z; AutoInterface<CWxRpcBinding>::operator=(CWxRpcBinding *)
0x180014d89  lea     rcx, [rbp+var_10]; this
0x180014d8d  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x180014d92  mov     rax, [rbp+var_20]
0x180014d96  mov     r14d, [rbp+var_4]
0x180014d9a  mov     r12d, [rbp+var_8]
0x180014d9e  mov     rdi, [rbp+var_10]
0x180014da2  jmp     loc_180014BEE
0x180014da7  mov     edx, 0Ch
0x180014dac  lea     r8, WPP_96dab6e5195d34c67ab15726a5516004_Traceguids
0x180014db3  mov     ecx, 40Bh
0x180014db8  mov     r9d, ebx
0x180014dbb  call    WPP_SF_d
0x180014dc0  jmp     loc_180014C06
```
