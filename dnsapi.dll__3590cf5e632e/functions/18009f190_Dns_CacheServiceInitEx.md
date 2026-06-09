# Dns_CacheServiceInitEx

- ea: `0x18009f190`
- end: `0x18009f5a2`
- name: `Dns_CacheServiceInitEx`
- size: `1042`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ee5c`
- `0x18006e4e8`
- `0x180079544`
- `0x180083954`
- `0x180084968`
- `0x180084c4c`
- `0x180087178`
- `0x1800875f4`
- `0x18008813c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x180093f74`
- `0x18009f190`
- `0x18009fd4c`
- `0x1800cafec`
- `0x1800ce078`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f394`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f42b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f394`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f42b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f40f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f450`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f40f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f450`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18009f28a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18009f28a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18009f330`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18009f330`
- `WS2_32!__imp_WSAStartup` at `0x18009f2c3`
- `WS2_32!__imp_WSAStartup` at `0x18009f2c3`

## pseudocode

```c
__int64 __fastcall Dns_CacheServiceInitEx(int a1, __int128 **a2, unsigned int a3)
{
  size_t v3; // rsi
  int v6; // ecx
  unsigned int v7; // ebx
  __int128 **v8; // r14
  unsigned int SocketClosingWork; // eax
  __int64 v10; // rdx
  __int128 *v11; // rax
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  char v18[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 *v19; // [rsp+200h] [rbp+100h]
  __int64 v20; // [rsp+208h] [rbp+108h]
  int *v21; // [rsp+210h] [rbp+110h]
  __int64 v22; // [rsp+218h] [rbp+118h]
  LPCSTR retaddr; // [rsp+258h] [rbp+158h]

  v3 = a3;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_dqd(v6, 10, (unsigned int)WPP_91e50558be533056065562a944b5a4a4_Traceguids, a1, (__int64)a2);
  if ( g_fVelocitySuppressInternalExports && !g_DnsIsCache && !(unsigned int)Dns_IsCallerDns(retaddr) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v7 = 120;
    goto LABEL_51;
  }
  if ( !a2 )
    goto LABEL_8;
  if ( g_fVelocityZtdnsProbing )
  {
    if ( a1 != 2 || (_DWORD)v3 != 16 || !a2[1] || !*a2 )
      goto LABEL_8;
    v8 = a2;
  }
  else
  {
    if ( a1 != 1 )
      goto LABEL_8;
    v8 = 0;
    if ( (_DWORD)v3 != 144 )
      goto LABEL_8;
  }
  g_DnsIsCache = 1;
  g_hSettingsSemaphore = CreateSemaphoreW(0, 10, 10, 0);
  if ( !g_hSettingsSemaphore )
  {
LABEL_8:
    v7 = 87;
    goto LABEL_51;
  }
  SocketClosingWork = DnsCreateSocketClosingWork();
  v7 = SocketClosingWork;
  if ( SocketClosingWork )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return v7;
    v10 = 11;
  }
  else if ( g_fVelocityDisableInternalExports )
  {
    SocketClosingWork = WSAStartup(0x202u, &WSAData);
    v7 = SocketClosingWork;
    if ( !SocketClosingWork )
    {
      g_fWinsockStarted = 1;
      goto LABEL_25;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return v7;
    v10 = 12;
  }
  else
  {
    SocketClosingWork = DnsInitWinsock();
    v7 = SocketClosingWork;
    if ( !SocketClosingWork )
    {
LABEL_25:
      SocketClosingWork = DnsInitDdr();
      v7 = SocketClosingWork;
      if ( SocketClosingWork )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          return v7;
        v10 = 14;
      }
      else
      {
        SocketClosingWork = DotCleanupInitialize();
        v7 = SocketClosingWork;
        if ( SocketClosingWork )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            return v7;
          v10 = 15;
        }
        else
        {
          g_DnsCacheServiceStopPending = 0;
          AdaptiveTimeout_InitializeGlobals();
          if ( (unsigned int)RtlGetCurrentServiceSessionId() )
          {
            g_IsArgon = 1;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_(1035, v7 + 16, WPP_91e50558be533056065562a944b5a4a4_Traceguids);
          }
          SocketClosingWork = InitializeDnsApiStatistics();
          v7 = SocketClosingWork;
          if ( SocketClosingWork )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              return v7;
            v10 = 17;
          }
          else
          {
            SocketClosingWork = InitializeDnsStatistics();
            v7 = SocketClosingWork;
            if ( !SocketClosingWork )
            {
              if ( g_fVelocityZtdnsProbing )
              {
                AcquireSRWLockExclusive(&g_rwResolverDataLock);
                v11 = *v8;
                g_ResolverData = **v8;
                xmmword_180112C10 = v11[1];
                xmmword_180112C20 = v11[2];
                xmmword_180112C30 = v11[3];
                xmmword_180112C40 = v11[4];
                xmmword_180112C50 = v11[5];
                xmmword_180112C60 = v11[6];
                xmmword_180112C70 = v11[7];
                xmmword_180112C80 = v11[8];
                ReleaseSRWLockExclusive(&g_rwResolverDataLock);
                *(_QWORD *)v8[1] = NetInfo_BuildEx2;
              }
              else
              {
                AcquireSRWLockExclusive(&g_rwResolverDataLock);
                memcpy_0(&g_ResolverData, a2, v3);
                ReleaseSRWLockExclusive(&g_rwResolverDataLock);
              }
              if ( (unsigned int)dword_180111218 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180111218, 0x200000000000LL) )
              {
                v16 = 0x2000000;
                v19 = &v16;
                v15 = g_DnsIsCache;
                v21 = &v15;
                v20 = 8;
                v22 = 4;
                tlgWriteTransfer_EtwEventWriteTransfer(4, (unsigned int)byte_180101A93, v12, v13, 4, (__int64)v18);
              }
              goto LABEL_51;
            }
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              return v7;
            v10 = 18;
          }
        }
      }
      goto LABEL_50;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return v7;
    v10 = 13;
  }
LABEL_50:
  WPP_SF_d(1035, v10, WPP_91e50558be533056065562a944b5a4a4_Traceguids, SocketClosingWork);
LABEL_51:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 19, WPP_91e50558be533056065562a944b5a4a4_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18009f190  mov     [rsp-8+arg_18], rbx
0x18009f195  push    rbp
0x18009f196  push    rsi
0x18009f197  push    rdi
0x18009f198  push    r13
0x18009f19a  push    r14
0x18009f19c  lea     rbp, [rsp-130h]
0x18009f1a4  sub     rsp, 230h
0x18009f1ab  mov     rax, cs:__security_cookie
0x18009f1b2  xor     rax, rsp
0x18009f1b5  mov     [rbp+150h+var_30], rax
0x18009f1bc  mov     esi, r8d
0x18009f1bf  mov     rdi, rdx
0x18009f1c2  mov     ebx, ecx
0x18009f1c4  xor     edx, edx; Val
0x18009f1c6  mov     r8d, 198h; Size
0x18009f1cc  lea     rcx, [rsp+250h+WSAData]; void *
0x18009f1d1  call    memset_0
0x18009f1d6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f1dd  lea     r13, WPP_91e50558be533056065562a944b5a4a4_Traceguids
0x18009f1e4  jz      short loc_18009F1FF
0x18009f1e6  mov     edx, 0Ah
0x18009f1eb  mov     dword ptr [rsp+250h+var_228], esi
0x18009f1ef  mov     r9d, ebx
0x18009f1f2  mov     [rsp+250h+var_230], rdi
0x18009f1f7  mov     r8, r13
0x18009f1fa  call    WPP_SF_dqd
0x18009f1ff  cmp     cs:g_fVelocitySuppressInternalExports, 0
0x18009f206  jz      short loc_18009F230
0x18009f208  cmp     cs:g_DnsIsCache, 0
0x18009f20f  jnz     short loc_18009F230
0x18009f211  mov     rcx, [rbp+158h]; lpModuleName
0x18009f218  call    Dns_IsCallerDns
0x18009f21d  test    eax, eax
0x18009f21f  jnz     short loc_18009F230
0x18009f221  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f226  mov     ebx, 78h ; 'x'
0x18009f22b  jmp     loc_18009F55B
0x18009f230  test    rdi, rdi
0x18009f233  jnz     short loc_18009F23F
0x18009f235  mov     ebx, 57h ; 'W'
0x18009f23a  jmp     loc_18009F55B
0x18009f23f  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18009f246  jz      short loc_18009F264
0x18009f248  cmp     ebx, 2
0x18009f24b  jnz     short loc_18009F235
0x18009f24d  cmp     esi, 10h
0x18009f250  jnz     short loc_18009F235
0x18009f252  cmp     qword ptr [rdi+8], 0
0x18009f257  jz      short loc_18009F235
0x18009f259  cmp     qword ptr [rdi], 0
0x18009f25d  jz      short loc_18009F235
0x18009f25f  mov     r14, rdi
0x18009f262  jmp     short loc_18009F274
0x18009f264  cmp     ebx, 1
0x18009f267  jnz     short loc_18009F235
0x18009f269  xor     r14d, r14d
0x18009f26c  cmp     esi, 90h
0x18009f272  jnz     short loc_18009F235
0x18009f274  xor     r9d, r9d; lpName
0x18009f277  mov     cs:g_DnsIsCache, 1
0x18009f281  xor     ecx, ecx; lpSemaphoreAttributes
0x18009f283  lea     edx, [r9+0Ah]; lInitialCount
0x18009f287  mov     r8d, edx; lMaximumCount
0x18009f28a  call    cs:__imp_CreateSemaphoreW
0x18009f291  nop     dword ptr [rax+rax+00h]
0x18009f296  mov     cs:g_hSettingsSemaphore, rax
0x18009f29d  test    rax, rax
0x18009f2a0  jz      short loc_18009F235
0x18009f2a2  call    DnsCreateSocketClosingWork
0x18009f2a7  mov     ebx, eax
0x18009f2a9  test    eax, eax
0x18009f2ab  jnz     loc_18009F53D
0x18009f2b1  cmp     cs:g_fVelocityDisableInternalExports, eax
0x18009f2b7  jz      short loc_18009F2F8
0x18009f2b9  mov     ecx, 202h; wVersionRequested
0x18009f2be  lea     rdx, [rsp+250h+WSAData]; lpWSAData
0x18009f2c3  call    cs:__imp_WSAStartup
0x18009f2ca  nop     dword ptr [rax+rax+00h]
0x18009f2cf  mov     ebx, eax
0x18009f2d1  test    eax, eax
0x18009f2d3  jnz     short loc_18009F2E1
0x18009f2d5  mov     cs:g_fWinsockStarted, 1
0x18009f2df  jmp     short loc_18009F307
0x18009f2e1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f2e8  jz      loc_18009F579
0x18009f2ee  mov     edx, 0Ch
0x18009f2f3  jmp     loc_18009F54B
0x18009f2f8  call    DnsInitWinsock
0x18009f2fd  mov     ebx, eax
0x18009f2ff  test    eax, eax
0x18009f301  jnz     loc_18009F52D
0x18009f307  call    DnsInitDdr
0x18009f30c  mov     ebx, eax
0x18009f30e  test    eax, eax
0x18009f310  jnz     loc_18009F51D
0x18009f316  call    DotCleanupInitialize
0x18009f31b  mov     ebx, eax
0x18009f31d  test    eax, eax
0x18009f31f  jnz     loc_18009F50D
0x18009f325  mov     cs:g_DnsCacheServiceStopPending, eax
0x18009f32b  call    AdaptiveTimeout_InitializeGlobals
0x18009f330  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18009f337  nop     dword ptr [rax+rax+00h]
0x18009f33c  test    eax, eax
0x18009f33e  jz      short loc_18009F363
0x18009f340  mov     cs:g_IsArgon, 1
0x18009f34a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f351  jz      short loc_18009F363
0x18009f353  lea     edx, [rbx+10h]
0x18009f356  mov     ecx, 40Bh
0x18009f35b  mov     r8, r13
0x18009f35e  call    WPP_SF_
0x18009f363  call    InitializeDnsApiStatistics
0x18009f368  mov     ebx, eax
0x18009f36a  test    eax, eax
0x18009f36c  jnz     loc_18009F4FD
0x18009f372  call    InitializeDnsStatistics
0x18009f377  mov     ebx, eax
0x18009f379  test    eax, eax
0x18009f37b  jnz     loc_18009F4E9
0x18009f381  cmp     cs:g_fVelocityZtdnsProbing, eax
0x18009f387  lea     rcx, g_rwResolverDataLock; SRWLock
0x18009f38e  jz      loc_18009F42B
0x18009f394  call    cs:__imp_AcquireSRWLockExclusive
0x18009f39b  nop     dword ptr [rax+rax+00h]
0x18009f3a0  mov     rax, [r14]
0x18009f3a3  lea     rcx, g_rwResolverDataLock; SRWLock
0x18009f3aa  movups  xmm0, xmmword ptr [rax]
0x18009f3ad  movups  cs:g_ResolverData, xmm0
0x18009f3b4  movups  xmm1, xmmword ptr [rax+10h]
0x18009f3b8  movups  cs:xmmword_180112C10, xmm1
0x18009f3bf  movups  xmm0, xmmword ptr [rax+20h]
0x18009f3c3  movups  cs:xmmword_180112C20, xmm0
0x18009f3ca  movups  xmm1, xmmword ptr [rax+30h]
0x18009f3ce  movups  cs:xmmword_180112C30, xmm1
0x18009f3d5  movups  xmm0, xmmword ptr [rax+40h]
0x18009f3d9  movups  cs:xmmword_180112C40, xmm0
0x18009f3e0  movups  xmm1, xmmword ptr [rax+50h]
0x18009f3e4  movups  cs:xmmword_180112C50, xmm1
0x18009f3eb  movups  xmm0, xmmword ptr [rax+60h]
0x18009f3ef  movups  cs:xmmword_180112C60, xmm0
0x18009f3f6  movups  xmm1, xmmword ptr [rax+70h]
0x18009f3fa  movups  cs:xmmword_180112C70, xmm1
0x18009f401  movups  xmm0, xmmword ptr [rax+80h]
0x18009f408  movups  cs:xmmword_180112C80, xmm0
0x18009f40f  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f416  nop     dword ptr [rax+rax+00h]
0x18009f41b  mov     rax, [r14+8]
0x18009f41f  lea     rcx, NetInfo_BuildEx2
0x18009f426  mov     [rax], rcx
0x18009f429  jmp     short loc_18009F45C
0x18009f42b  call    cs:__imp_AcquireSRWLockExclusive
0x18009f432  nop     dword ptr [rax+rax+00h]
0x18009f437  mov     r8, rsi; Size
0x18009f43a  lea     rcx, g_ResolverData; void *
0x18009f441  mov     rdx, rdi; Src
0x18009f444  call    memcpy_0
0x18009f449  lea     rcx, g_rwResolverDataLock; SRWLock
0x18009f450  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f457  nop     dword ptr [rax+rax+00h]
0x18009f45c  mov     eax, cs:dword_180111218
0x18009f462  cmp     eax, 5
0x18009f465  jbe     loc_18009F55B
0x18009f46b  mov     rdx, 200000000000h
0x18009f475  lea     rcx, dword_180111218
0x18009f47c  call    _tlgKeywordOn
0x18009f481  test    al, al
0x18009f483  jz      loc_18009F55B
0x18009f489  lea     rax, [rsp+250h+var_218]
0x18009f48e  mov     [rsp+250h+var_218], 2000000h
0x18009f497  mov     [rbp+150h+var_50], rax
0x18009f49e  lea     rdx, byte_180101A93
0x18009f4a5  mov     eax, cs:g_DnsIsCache
0x18009f4ab  mov     ecx, 4
0x18009f4b0  mov     [rsp+250h+var_220], eax
0x18009f4b4  lea     rax, [rsp+250h+var_220]
0x18009f4b9  mov     [rbp+150h+var_40], rax
0x18009f4c0  lea     rax, [rbp+150h+var_70]
0x18009f4c7  mov     [rsp+250h+var_228], rax
0x18009f4cc  mov     dword ptr [rsp+250h+var_230], ecx
0x18009f4d0  mov     [rbp+150h+var_48], 8
0x18009f4db  mov     [rbp+150h+var_38], rcx
0x18009f4e2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18009f4e7  jmp     short loc_18009F55B
0x18009f4e9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f4f0  jz      loc_18009F579
0x18009f4f6  mov     edx, 12h
0x18009f4fb  jmp     short loc_18009F54B
0x18009f4fd  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f504  jz      short loc_18009F579
0x18009f506  mov     edx, 11h
0x18009f50b  jmp     short loc_18009F54B
0x18009f50d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f514  jz      short loc_18009F579
0x18009f516  mov     edx, 0Fh
0x18009f51b  jmp     short loc_18009F54B
0x18009f51d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f524  jz      short loc_18009F579
0x18009f526  mov     edx, 0Eh
0x18009f52b  jmp     short loc_18009F54B
0x18009f52d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f534  jz      short loc_18009F579
0x18009f536  mov     edx, 0Dh
0x18009f53b  jmp     short loc_18009F54B
0x18009f53d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f544  jz      short loc_18009F579
0x18009f546  mov     edx, 0Bh
0x18009f54b  mov     r9d, eax
0x18009f54e  mov     r8, r13
0x18009f551  mov     ecx, 40Bh
0x18009f556  call    WPP_SF_d
0x18009f55b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f562  jz      short loc_18009F579
0x18009f564  mov     edx, 13h
0x18009f569  mov     ecx, 40Bh
0x18009f56e  mov     r9d, ebx
0x18009f571  mov     r8, r13
0x18009f574  call    WPP_SF_d
0x18009f579  mov     eax, ebx
0x18009f57b  mov     rcx, [rbp+150h+var_30]
0x18009f582  xor     rcx, rsp; StackCookie
0x18009f585  call    __security_check_cookie
0x18009f58a  mov     rbx, [rsp+250h+arg_18]
0x18009f592  add     rsp, 230h
0x18009f599  pop     r14
0x18009f59b  pop     r13
0x18009f59d  pop     rdi
0x18009f59e  pop     rsi
0x18009f59f  pop     rbp
0x18009f5a0  retn
```
