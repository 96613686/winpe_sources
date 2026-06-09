# CMQSigCertificate::_InitCryptProviderCreate(int,int)

- ea: `0x18001c3ec`
- end: `0x18001c6b5`
- name: `?_InitCryptProviderCreate@CMQSigCertificate@@AEAAJHH@Z`
- size: `713`
- prototype: `__int64 __fastcall(CMQSigCertificate *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bbb0`
- `0x18001cfc0`

## callees

- `0x180004074`
- `0x1800049ec`
- `0x180017430`
- `0x18001c3ec`
- `0x18002ba00`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x18001c452`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c46f`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c521`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c597`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c452`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c46f`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c521`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c597`
- `KERNEL32!GetLastError` at `0x18001c47d`
- `KERNEL32!GetLastError` at `0x18001c547`
- `KERNEL32!GetLastError` at `0x18001c5bd`
- `KERNEL32!GetLastError` at `0x18001c47d`
- `KERNEL32!GetLastError` at `0x18001c547`
- `KERNEL32!GetLastError` at `0x18001c5bd`

## string_xrefs

- `0x18001c41b`: `MSMQ_SERVICE`

## pseudocode

```c
__int64 __fastcall CMQSigCertificate::_InitCryptProviderCreate(CMQSigCertificate *this, int a2, int a3)
{
  HCRYPTPROV *v3; // rdi
  const WCHAR *v6; // rbx
  DWORD LastError; // eax
  int v8; // ebx
  __int64 v9; // r9
  char v10; // al
  char v11; // al
  __int64 v12; // r9
  __int16 v13; // [rsp+80h] [rbp+8h] BYREF
  int v14; // [rsp+98h] [rbp+20h] BYREF

  v3 = (HCRYPTPROV *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
    return 0;
  v6 = L"MSMQ_SERVICE";
  if ( !a3 )
    v6 = L"MSMQ";
  if ( a2 )
    CryptAcquireContextW(
      (HCRYPTPROV *)this + 2,
      v6,
      L"Microsoft Enhanced RSA and AES Cryptographic Provider",
      0x18u,
      (a3 != 0 ? 0x20 : 0) | 0x10);
  if ( CryptAcquireContextW(v3, v6, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, a3 != 0 ? 0x20 : 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == -2146893802 )
    goto LABEL_31;
  if ( LastError != -2146893798 )
  {
    v8 = -1072824319;
    v13 = 40;
    v14 = -1072824319;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v9 = mqwcslen(L"certifct/certpriv") + 1;
      CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2 * v9, L"certifct/certpriv", 2, &v13, 4, &v14, 0, 0);
    }
    return (unsigned int)v8;
  }
  if ( CryptAcquireContextW(
         v3,
         v6,
         L"Microsoft Enhanced RSA and AES Cryptographic Provider",
         0x18u,
         (a3 != 0 ? 0x20 : 0) | 0x10) )
  {
LABEL_31:
    if ( CryptAcquireContextW(
           v3,
           v6,
           L"Microsoft Enhanced RSA and AES Cryptographic Provider",
           0x18u,
           (a3 != 0 ? 0x20 : 0) | 8) )
    {
      v8 = 0;
      if ( a3 )
      {
        v8 = SetKeyContainerSecurity(*v3);
        if ( v8 < 0 )
        {
          v13 = 50;
          v14 = v8;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v12 = mqwcslen(L"certifct/certpriv") + 1;
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              1,
              2 * v12,
              L"certifct/certpriv",
              2,
              &v13,
              4,
              &v14,
              0,
              0);
          }
        }
      }
      return (unsigned int)v8;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), v11);
    }
    return 3222146056LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v10 = GetLastError();
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), v10);
    }
    return 3222146059LL;
  }
}

```

## disassembly

```asm
0x18001c3ec  mov     [rsp+arg_8], rbx
0x18001c3f1  mov     [rsp+arg_10], rbp
0x18001c3f6  push    rsi
0x18001c3f7  push    rdi
0x18001c3f8  push    r14
0x18001c3fa  sub     rsp, 60h
0x18001c3fe  lea     rdi, [rcx+10h]
0x18001c402  mov     ebp, r8d
0x18001c405  cmp     qword ptr [rdi], 0
0x18001c409  jz      short loc_18001C412
0x18001c40b  xor     eax, eax
0x18001c40d  jmp     loc_18001C6A0
0x18001c412  test    ebp, ebp
0x18001c414  lea     rax, SubsystemName; "MSMQ"
0x18001c41b  lea     rbx, aMsmqService; "MSMQ_SERVICE"
0x18001c422  cmovz   rbx, rax
0x18001c426  mov     eax, ebp
0x18001c428  neg     eax
0x18001c42a  sbb     esi, esi
0x18001c42c  and     esi, 20h
0x18001c42f  mov     r14d, esi
0x18001c432  or      r14d, 10h
0x18001c436  test    edx, edx
0x18001c438  jz      short loc_18001C458
0x18001c43a  mov     r9d, 18h; dwProvType
0x18001c440  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18001c445  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18001c44c  mov     rdx, rbx; szContainer
0x18001c44f  mov     rcx, rdi; phProv
0x18001c452  call    cs:__imp_CryptAcquireContextW
0x18001c458  mov     r9d, 18h; dwProvType
0x18001c45e  mov     [rsp+78h+dwFlags], esi; dwFlags
0x18001c462  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18001c469  mov     rdx, rbx; szContainer
0x18001c46c  mov     rcx, rdi; phProv
0x18001c46f  call    cs:__imp_CryptAcquireContextW
0x18001c475  test    eax, eax
0x18001c477  jnz     loc_18001C69C
0x18001c47d  call    cs:__imp_GetLastError
0x18001c483  cmp     eax, 80090016h
0x18001c488  jz      loc_18001C57D
0x18001c48e  cmp     eax, 8009001Ah
0x18001c493  jz      short loc_18001C509
0x18001c495  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001c49d  mov     eax, 28h ; '('
0x18001c4a2  mov     ebx, 0C00E0001h
0x18001c4a7  mov     [rsp+78h+arg_0], ax
0x18001c4af  mov     [rsp+78h+arg_18], ebx
0x18001c4b6  jz      loc_18001C69E
0x18001c4bc  lea     rdi, aCertifctCertpr; "certifct/certpriv"
0x18001c4c3  mov     rcx, rdi; wchar_t *
0x18001c4c6  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001c4cb  mov     [rsp+78h+var_28], 0
0x18001c4d4  lea     rcx, [rsp+78h+arg_0]
0x18001c4dc  mov     [rsp+78h+var_30], 0
0x18001c4e5  lea     r9d, [rax+1]
0x18001c4e9  lea     rax, [rsp+78h+arg_18]
0x18001c4f1  mov     [rsp+78h+var_38], rax
0x18001c4f6  mov     [rsp+78h+var_40], 4
0x18001c4ff  mov     [rsp+78h+var_48], rcx
0x18001c504  jmp     loc_18001C675
0x18001c509  mov     r9d, 18h; dwProvType
0x18001c50f  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18001c514  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18001c51b  mov     rdx, rbx; szContainer
0x18001c51e  mov     rcx, rdi; phProv
0x18001c521  call    cs:__imp_CryptAcquireContextW
0x18001c527  test    eax, eax
0x18001c529  jnz     short loc_18001C57D
0x18001c52b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c532  lea     rax, WPP_GLOBAL_Control
0x18001c539  cmp     rcx, rax
0x18001c53c  jz      short loc_18001C573
0x18001c53e  test    byte ptr [rcx+10Ch], 1
0x18001c545  jz      short loc_18001C573
0x18001c547  call    cs:__imp_GetLastError
0x18001c54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c554  lea     r8, WPP_bfaf9ec3fca3323507785858872d9f37_Traceguids
0x18001c55b  mov     edx, 0Ah
0x18001c560  mov     [rsp+78h+dwFlags], eax; char
0x18001c564  mov     r9, rbx
0x18001c567  mov     rcx, [rcx+100h]; LoggerHandle
0x18001c56e  call    WPP_SF_Sd
0x18001c573  mov     eax, 0C00E0C0Bh
0x18001c578  jmp     loc_18001C6A0
0x18001c57d  or      esi, 8
0x18001c580  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18001c587  mov     r9d, 18h; dwProvType
0x18001c58d  mov     [rsp+78h+dwFlags], esi; dwFlags
0x18001c591  mov     rdx, rbx; szContainer
0x18001c594  mov     rcx, rdi; phProv
0x18001c597  call    cs:__imp_CryptAcquireContextW
0x18001c59d  test    eax, eax
0x18001c59f  jnz     short loc_18001C5F3
0x18001c5a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5a8  lea     rax, WPP_GLOBAL_Control
0x18001c5af  cmp     rcx, rax
0x18001c5b2  jz      short loc_18001C5E9
0x18001c5b4  test    byte ptr [rcx+10Ch], 1
0x18001c5bb  jz      short loc_18001C5E9
0x18001c5bd  call    cs:__imp_GetLastError
0x18001c5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5ca  lea     r8, WPP_bfaf9ec3fca3323507785858872d9f37_Traceguids
0x18001c5d1  mov     edx, 0Bh
0x18001c5d6  mov     [rsp+78h+dwFlags], eax; char
0x18001c5da  mov     r9, rbx
0x18001c5dd  mov     rcx, [rcx+100h]; LoggerHandle
0x18001c5e4  call    WPP_SF_Sd
0x18001c5e9  mov     eax, 0C00E0C08h
0x18001c5ee  jmp     loc_18001C6A0
0x18001c5f3  xor     ebx, ebx
0x18001c5f5  test    ebp, ebp
0x18001c5f7  jz      loc_18001C69E
0x18001c5fd  mov     rcx, [rdi]; hProv
0x18001c600  call    ?SetKeyContainerSecurity@@YAJ_K@Z; SetKeyContainerSecurity(unsigned __int64)
0x18001c605  mov     ebx, eax
0x18001c607  test    eax, eax
0x18001c609  jns     loc_18001C69E
0x18001c60f  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001c617  mov     eax, 32h ; '2'
0x18001c61c  mov     [rsp+78h+arg_0], ax
0x18001c624  mov     [rsp+78h+arg_18], ebx
0x18001c62b  jz      short loc_18001C69E
0x18001c62d  lea     rdi, aCertifctCertpr; "certifct/certpriv"
0x18001c634  mov     rcx, rdi; wchar_t *
0x18001c637  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001c63c  mov     [rsp+78h+var_28], 0
0x18001c645  mov     [rsp+78h+var_30], 0
0x18001c64e  lea     r9d, [rax+1]
0x18001c652  lea     rax, [rsp+78h+arg_18]
0x18001c65a  mov     [rsp+78h+var_38], rax
0x18001c65f  lea     rax, [rsp+78h+arg_0]
0x18001c667  mov     [rsp+78h+var_40], 4
0x18001c670  mov     [rsp+78h+var_48], rax
0x18001c675  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001c67c  mov     edx, 1
0x18001c681  mov     r8d, edx
0x18001c684  mov     [rsp+78h+var_50], 2
0x18001c68d  add     r9, r9
0x18001c690  mov     qword ptr [rsp+78h+dwFlags], rdi
0x18001c695  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001c69a  jmp     short loc_18001C69E
0x18001c69c  xor     ebx, ebx
0x18001c69e  mov     eax, ebx
0x18001c6a0  lea     r11, [rsp+78h+var_18]
0x18001c6a5  mov     rbx, [r11+28h]
0x18001c6a9  mov     rbp, [r11+30h]
0x18001c6ad  mov     rsp, r11
0x18001c6b0  pop     r14
0x18001c6b2  pop     rdi
0x18001c6b3  pop     rsi
0x18001c6b4  retn
```
