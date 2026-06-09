# Areg_RegistrationThread

- ea: `0x180036b50`
- end: `0x180036f44`
- name: `Areg_RegistrationThread`
- size: `1012`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180026134`
- `0x180033fc4`
- `0x180036530`
- `0x180036b50`
- `0x180037634`
- `0x180037cfc`
- `0x1800410d0`
- `0x18004abac`
- `0x18007bcb4`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!Security_ContextListTimeout` at `0x180036e97`
- `DNSAPI!Security_ContextListTimeout` at `0x180036e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036eb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180036c5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180036c5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036e84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036e84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ef2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036d97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036d97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036bdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036c85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036bdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036c85`

## pseudocode

```c
__int64 __fastcall Areg_RegistrationThread(PVOID Parameter)
{
  int v2; // ebx
  DWORD v3; // esi
  int v4; // edi
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int NextEntryFromList; // eax
  int v10; // ebx
  void *v11; // rbx
  int v12; // [rsp+80h] [rbp+8h] BYREF
  void *v13; // [rsp+88h] [rbp+10h] BYREF

  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1047, 59, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  if ( !g_hAregRegKey )
    return 87;
  v2 = 0;
  v12 = 0;
  v3 = 0;
  v4 = 0;
  g_fAregThreadRunning = 1;
  if ( g_fAregAtBoot && !g_fAregPurge )
  {
    v2 = 5;
    v12 = 5;
    v4 = GetTickCount64() / 0x3E8 + 5;
  }
  while ( !g_fAregThreadStop )
  {
LABEL_9:
    if ( !v2 && v3 )
    {
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_(1055, 60, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
      v2 = 3600;
      v12 = 3600;
    }
    if ( SBYTE2(xmmword_1800AB5A0) < 0 )
      WPP_SF_d(1047, 61, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (unsigned int)v2);
    v5 = WaitForSingleObject(g_hAregWakeEvent, 1000 * v2);
    v3 = v5;
    if ( SBYTE2(xmmword_1800AB5A0) < 0 )
      WPP_SF_ddddddd(v7, v6, v8, v5);
    if ( !g_fAregAtBoot || g_fAregPurge )
    {
      while ( 1 )
      {
        while ( 1 )
        {
LABEL_26:
          v13 = 0;
          if ( g_fAregThreadStop )
            goto LABEL_50;
          NextEntryFromList = areg_GetNextEntryFromList(&v13, &v12);
          if ( g_fAregThreadStop )
          {
            v11 = v13;
            if ( *((_QWORD *)v13 + 41) )
              areg_SignalUpdateStatus((char *)v13 + 328, 1223);
            areg_FreeEntry(v11);
            goto LABEL_50;
          }
          if ( NextEntryFromList != 2 )
            break;
          areg_ProcessEntry((unsigned int *)v13);
        }
        if ( NextEntryFromList == 1 )
        {
          if ( g_fAregAtBoot )
            goto LABEL_35;
          if ( !g_fAregPurge )
          {
            v2 = v12;
            goto LABEL_9;
          }
        }
        if ( g_fAregAtBoot || g_fAregPurge )
        {
LABEL_35:
          if ( g_fAregPurgeInitiated )
            goto LABEL_41;
          if ( g_fAregPurge )
            areg_ResetAdaptersInRegistry();
          areg_DeregisterUnusedAdapterInRegistry();
          if ( g_fAregPurge )
            g_fAregPurgeInitiated = 1;
          g_fAregAtBoot = 0;
        }
        else
        {
LABEL_41:
          EnterCriticalSection(&g_AregThreadCs);
          v10 = 1;
          if ( SBYTE2(xmmword_1800AB5A0) < 0 )
            WPP_SF_(1047, 64, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
          if ( g_fAregThreadStop || !g_fAregThreadCheckBeforeExit )
            goto LABEL_51;
          g_fAregThreadCheckBeforeExit = 0;
          LeaveCriticalSection(&g_AregThreadCs);
        }
      }
    }
    v2 = v4 - GetTickCount64() / 0x3E8;
    v12 = v2;
    if ( v2 <= 0 )
    {
      v12 = 0;
      goto LABEL_26;
    }
    if ( SBYTE2(xmmword_1800AB5A0) < 0 )
      WPP_SF_d(1047, 63, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (unsigned int)v2);
  }
LABEL_50:
  v10 = 0;
LABEL_51:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 65, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  if ( !v10 )
    EnterCriticalSection(&g_AregThreadCs);
  g_fAregThreadRunning = 0;
  EnterCriticalSection(&g_AregListCs);
  g_fAregAtBoot = 0;
  g_fAregPurge = 0;
  g_fAregPurgeInitiated = 0;
  areg_FreeEntryList();
  qword_1800AC818 = (__int64)&g_AregEntryList;
  g_AregEntryList = &g_AregEntryList;
  LeaveCriticalSection(&g_AregListCs);
  if ( !g_fVelocityRpcUpdate )
    Security_ContextListTimeout(1);
  if ( g_hAregThread && !g_AregThreadWaitCount )
  {
    CloseHandle(g_hAregThread);
    g_hAregThread = 0;
  }
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1047, 66, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 67, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  LeaveCriticalSection(&g_AregThreadCs);
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1047, 68, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 69, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180036b50  mov     [rsp+arg_10], rbx
0x180036b55  mov     [rsp+arg_18], rbp
0x180036b5a  push    rsi
0x180036b5b  push    rdi
0x180036b5c  push    r13
0x180036b5e  push    r14
0x180036b60  push    r15
0x180036b62  sub     rsp, 50h
0x180036b66  xor     ebp, ebp
0x180036b68  lea     r14, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180036b6f  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036b76  mov     r15d, 417h
0x180036b7c  jge     short loc_180036B8C
0x180036b7e  lea     edx, [rbp+3Bh]
0x180036b81  mov     ecx, r15d
0x180036b84  mov     r8, r14
0x180036b87  call    WPP_SF_
0x180036b8c  cmp     cs:g_hAregRegKey, rbp
0x180036b93  jnz     short loc_180036B9F
0x180036b95  mov     eax, 57h ; 'W'
0x180036b9a  jmp     loc_180036F2B
0x180036b9f  cmp     cs:g_fAregAtBoot, ebp
0x180036ba5  mov     ebx, ebp
0x180036ba7  mov     [rsp+78h+arg_0], ebx
0x180036bae  mov     esi, ebp
0x180036bb0  mov     edi, ebp
0x180036bb2  mov     cs:g_fAregThreadRunning, 1
0x180036bbc  mov     r13, 624DD2F1A9FBE77h
0x180036bc6  jz      short loc_180036BFA
0x180036bc8  cmp     cs:g_fAregPurge, ebp
0x180036bce  jnz     short loc_180036BFA
0x180036bd0  mov     ebx, 5
0x180036bd5  mov     [rsp+78h+arg_0], ebx
0x180036bdc  call    cs:__imp_GetTickCount64
0x180036be2  mov     rdi, rax
0x180036be5  mov     rax, r13
0x180036be8  mul     rdi
0x180036beb  sub     rdi, rdx
0x180036bee  shr     rdi, 1
0x180036bf1  add     rdi, rdx
0x180036bf4  shr     rdi, 9
0x180036bf8  add     edi, ebx
0x180036bfa  lea     r13, g_AregThreadCs
0x180036c01  jmp     loc_180036CD3
0x180036c06  test    ebx, ebx
0x180036c08  jnz     short loc_180036C33
0x180036c0a  test    esi, esi
0x180036c0c  jz      short loc_180036C33
0x180036c0e  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x180036c15  jge     short loc_180036C27
0x180036c17  lea     edx, [rbx+3Ch]
0x180036c1a  mov     ecx, 41Fh
0x180036c1f  mov     r8, r14
0x180036c22  call    WPP_SF_
0x180036c27  mov     ebx, 0E10h
0x180036c2c  mov     [rsp+78h+arg_0], ebx
0x180036c33  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036c3a  jge     short loc_180036C4F
0x180036c3c  mov     edx, 3Dh ; '='
0x180036c41  mov     ecx, r15d
0x180036c44  mov     r9d, ebx
0x180036c47  mov     r8, r14
0x180036c4a  call    WPP_SF_d
0x180036c4f  mov     rcx, cs:g_hAregWakeEvent; hHandle
0x180036c56  imul    edx, ebx, 3E8h; dwMilliseconds
0x180036c5c  call    cs:__imp_WaitForSingleObject
0x180036c62  mov     esi, eax
0x180036c64  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036c6b  jge     short loc_180036C75
0x180036c6d  mov     r9d, eax
0x180036c70  call    WPP_SF_ddddddd
0x180036c75  cmp     cs:g_fAregAtBoot, ebp
0x180036c7b  jz      short loc_180036CEB
0x180036c7d  cmp     cs:g_fAregPurge, ebp
0x180036c83  jnz     short loc_180036CEB
0x180036c85  call    cs:__imp_GetTickCount64
0x180036c8b  mov     rcx, rax
0x180036c8e  mov     ebx, edi
0x180036c90  mov     rax, 624DD2F1A9FBE77h
0x180036c9a  mul     rcx
0x180036c9d  sub     rcx, rdx
0x180036ca0  shr     rcx, 1
0x180036ca3  add     rcx, rdx
0x180036ca6  shr     rcx, 9
0x180036caa  sub     ebx, ecx
0x180036cac  mov     [rsp+78h+arg_0], ebx
0x180036cb3  test    ebx, ebx
0x180036cb5  jle     short loc_180036CE4
0x180036cb7  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036cbe  jge     short loc_180036CD3
0x180036cc0  mov     edx, 3Fh ; '?'
0x180036cc5  mov     ecx, r15d
0x180036cc8  mov     r9d, ebx
0x180036ccb  mov     r8, r14
0x180036cce  call    WPP_SF_d
0x180036cd3  cmp     cs:g_fAregThreadStop, ebp
0x180036cd9  jz      loc_180036C06
0x180036cdf  jmp     loc_180036E0F
0x180036ce4  mov     [rsp+78h+arg_0], ebp
0x180036ceb  cmp     cs:g_fAregThreadStop, ebp
0x180036cf1  mov     [rsp+78h+arg_8], rbp
0x180036cf9  jnz     loc_180036E0F
0x180036cff  lea     rdx, [rsp+78h+arg_0]
0x180036d07  lea     rcx, [rsp+78h+arg_8]
0x180036d0f  call    areg_GetNextEntryFromList
0x180036d14  cmp     cs:g_fAregThreadStop, ebp
0x180036d1a  mov     ecx, eax
0x180036d1c  jnz     loc_180036DE9
0x180036d22  cmp     eax, 2
0x180036d25  jnz     short loc_180036D3C
0x180036d27  mov     edx, cs:g_fAregPurge
0x180036d2d  mov     rcx, [rsp+78h+arg_8]; void *
0x180036d35  call    areg_ProcessEntry
0x180036d3a  jmp     short loc_180036CEB
0x180036d3c  mov     eax, cs:g_fAregPurge
0x180036d42  mov     edx, cs:g_fAregAtBoot
0x180036d48  cmp     ecx, 1
0x180036d4b  jnz     short loc_180036D59
0x180036d4d  test    edx, edx
0x180036d4f  jnz     short loc_180036D61
0x180036d51  test    eax, eax
0x180036d53  jz      loc_180036DDD
0x180036d59  test    edx, edx
0x180036d5b  jnz     short loc_180036D61
0x180036d5d  test    eax, eax
0x180036d5f  jz      short loc_180036D94
0x180036d61  cmp     cs:g_fAregPurgeInitiated, ebp
0x180036d67  jnz     short loc_180036D94
0x180036d69  test    eax, eax
0x180036d6b  jz      short loc_180036D72
0x180036d6d  call    areg_ResetAdaptersInRegistry
0x180036d72  call    areg_DeregisterUnusedAdapterInRegistry
0x180036d77  cmp     cs:g_fAregPurge, ebp
0x180036d7d  jz      short loc_180036D89
0x180036d7f  mov     cs:g_fAregPurgeInitiated, 1
0x180036d89  mov     cs:g_fAregAtBoot, ebp
0x180036d8f  jmp     loc_180036CEB
0x180036d94  mov     rcx, r13; lpCriticalSection
0x180036d97  call    cs:__imp_EnterCriticalSection
0x180036d9d  mov     ebx, 1
0x180036da2  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036da9  jge     short loc_180036DB9
0x180036dab  lea     edx, [rbx+3Fh]
0x180036dae  mov     ecx, r15d
0x180036db1  mov     r8, r14
0x180036db4  call    WPP_SF_
0x180036db9  cmp     cs:g_fAregThreadStop, ebp
0x180036dbf  jnz     short loc_180036E11
0x180036dc1  cmp     cs:g_fAregThreadCheckBeforeExit, ebp
0x180036dc7  jz      short loc_180036E11
0x180036dc9  mov     rcx, r13; lpCriticalSection
0x180036dcc  mov     cs:g_fAregThreadCheckBeforeExit, ebp
0x180036dd2  call    cs:__imp_LeaveCriticalSection
0x180036dd8  jmp     loc_180036CEB
0x180036ddd  mov     ebx, [rsp+78h+arg_0]
0x180036de4  jmp     loc_180036C06
0x180036de9  mov     rbx, [rsp+78h+arg_8]
0x180036df1  lea     rcx, [rbx+148h]
0x180036df8  cmp     [rcx], rbp
0x180036dfb  jz      short loc_180036E07
0x180036dfd  mov     edx, 4C7h
0x180036e02  call    areg_SignalUpdateStatus
0x180036e07  mov     rcx, rbx; void *
0x180036e0a  call    areg_FreeEntry
0x180036e0f  mov     ebx, ebp
0x180036e11  mov     dil, 8
0x180036e14  mov     esi, 40Bh
0x180036e19  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x180036e20  jz      short loc_180036E31
0x180036e22  mov     edx, 41h ; 'A'
0x180036e27  mov     ecx, esi
0x180036e29  mov     r8, r14
0x180036e2c  call    WPP_SF_
0x180036e31  test    ebx, ebx
0x180036e33  jnz     short loc_180036E3E
0x180036e35  mov     rcx, r13; lpCriticalSection
0x180036e38  call    cs:__imp_EnterCriticalSection
0x180036e3e  lea     rcx, g_AregListCs; lpCriticalSection
0x180036e45  mov     cs:g_fAregThreadRunning, ebp
0x180036e4b  call    cs:__imp_EnterCriticalSection
0x180036e51  mov     cs:g_fAregAtBoot, ebp
0x180036e57  mov     cs:g_fAregPurge, ebp
0x180036e5d  mov     cs:g_fAregPurgeInitiated, ebp
0x180036e63  call    areg_FreeEntryList
0x180036e68  lea     rax, g_AregEntryList
0x180036e6f  lea     rcx, g_AregListCs; lpCriticalSection
0x180036e76  mov     cs:qword_1800AC818, rax
0x180036e7d  mov     cs:g_AregEntryList, rax
0x180036e84  call    cs:__imp_LeaveCriticalSection
0x180036e8a  cmp     cs:g_fVelocityRpcUpdate, ebp
0x180036e90  jnz     short loc_180036E9D
0x180036e92  mov     ecx, 1
0x180036e97  call    cs:__imp_Security_ContextListTimeout
0x180036e9d  mov     rcx, cs:g_hAregThread; hObject
0x180036ea4  test    rcx, rcx
0x180036ea7  jz      short loc_180036EBE
0x180036ea9  cmp     cs:g_AregThreadWaitCount, ebp
0x180036eaf  jnz     short loc_180036EBE
0x180036eb1  call    cs:__imp_CloseHandle
0x180036eb7  mov     cs:g_hAregThread, rbp
0x180036ebe  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036ec5  jge     short loc_180036ED7
0x180036ec7  mov     edx, 42h ; 'B'
0x180036ecc  mov     ecx, r15d
0x180036ecf  mov     r8, r14
0x180036ed2  call    WPP_SF_
0x180036ed7  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x180036ede  jz      short loc_180036EEF
0x180036ee0  mov     edx, 43h ; 'C'
0x180036ee5  mov     ecx, esi
0x180036ee7  mov     r8, r14
0x180036eea  call    WPP_SF_
0x180036eef  mov     rcx, r13; lpCriticalSection
0x180036ef2  call    cs:__imp_LeaveCriticalSection
0x180036ef8  cmp     byte ptr cs:xmmword_1800AB5A0+2, bpl
0x180036eff  jge     short loc_180036F11
0x180036f01  mov     edx, 44h ; 'D'
0x180036f06  mov     ecx, r15d
0x180036f09  mov     r8, r14
0x180036f0c  call    WPP_SF_
0x180036f11  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x180036f18  jz      short loc_180036F29
0x180036f1a  mov     edx, 45h ; 'E'
0x180036f1f  mov     ecx, esi
0x180036f21  mov     r8, r14
0x180036f24  call    WPP_SF_
0x180036f29  xor     eax, eax
0x180036f2b  lea     r11, [rsp+78h+var_28]
0x180036f30  mov     rbx, [r11+40h]
0x180036f34  mov     rbp, [r11+48h]
0x180036f38  mov     rsp, r11
0x180036f3b  pop     r15
0x180036f3d  pop     r14
0x180036f3f  pop     r13
0x180036f41  pop     rdi
0x180036f42  pop     rsi
0x180036f43  retn
```
