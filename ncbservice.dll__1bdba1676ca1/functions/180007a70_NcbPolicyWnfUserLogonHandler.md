# NcbPolicyWnfUserLogonHandler

- ea: `0x180007a70`
- end: `0x180007cdc`
- name: `NcbPolicyWnfUserLogonHandler`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000723c`
- `0x180007260`
- `0x1800075c4`
- `0x1800076e0`
- `0x180007a70`
- `0x180007cf0`
- `0x180009990`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001d8e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ac3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ac3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bf5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007a9b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b00`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180007bb9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180007bb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007ae0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007ae0`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180007c46`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180007c46`

## string_xrefs

- `0x180007c79`: `NcbPolicy: NcbPolicyAddUserLockscreenAppsUnderLock couldn't convert user SID to string`
- `0x180007ccb`: `Failed to get User Sid Status`

## pseudocode

```c
__int64 __fastcall NcbPolicyWnfUserLogonHandler(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  void *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  __int64 active; // rbx
  int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // r8d
  __int64 v20; // rbx
  LPWSTR StringSid; // [rsp+30h] [rbp-58h] BYREF
  int v22; // [rsp+38h] [rbp-50h] BYREF
  __int64 v23; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v24[16]; // [rsp+48h] [rbp-40h] BYREF
  const wchar_t *v25; // [rsp+58h] [rbp-30h]
  __int64 v26; // [rsp+60h] [rbp-28h]
  LPWSTR *p_StringSid; // [rsp+68h] [rbp-20h]
  __int64 v28; // [rsp+70h] [rbp-18h]

  v5 = a5 + 5;
  if ( IsValidSid(a5 + 5) && a5 != (unsigned int *)-20LL )
  {
    v6 = *a5;
    EnterCriticalSection(&g_NcbPolicyLock);
    NcbPolicyCleanupPoliciesUnderLock(v5);
    StringSid = 0;
    if ( ConvertSidToStringSidW(v5, &StringSid) )
    {
      NcbPolicyEnumerateUserLockscreenApps((unsigned __int8 *)v5, (__int64)StringSid);
      LocalFree(StringSid);
    }
    else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        v8,
        v7,
        L"NcbPolicy: NcbPolicyAddUserLockscreenAppsUnderLock couldn't convert user SID to string",
        0);
    }
    LeaveCriticalSection(&g_NcbPolicyLock);
    NcbPolicyPolicyChangeCallback(0);
    v22 = 0;
    v23 = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      LODWORD(StringSid) = 0;
      v25 = L"NcbPolicy: NcbPolicyConsoleSessionChangeHandlerHelper called";
      v26 = 122;
      p_StringSid = &StringSid;
      v28 = 4;
      McGenEventWrite_EventWriteTransfer(v9, NcbApiStatus, v10, 3, v24);
    }
    while ( 1 )
    {
      v11 = g_NcbPolicyReference;
      if ( (g_NcbPolicyReference & 1) != 0 )
        break;
      if ( v11 == _InterlockedCompareExchange(&g_NcbPolicyReference, g_NcbPolicyReference + 2, g_NcbPolicyReference) )
      {
        EnterCriticalSection(&g_NcbPolicyLock);
        active = WTSGetActiveConsoleSessionId();
        if ( (unsigned __int8)NcbPolicyIsInteractiveUserLogonSession(active, v6, &v22, &v23)
          || (LODWORD(active) = v22, v22 != -1) )
        {
          v14 = g_NcbPolicyCurrentConsoleSessionId;
          if ( (_DWORD)active != g_NcbPolicyCurrentConsoleSessionId )
          {
            v14 = active;
            g_NcbPolicyCurrentConsoleSessionId = active;
          }
        }
        else
        {
          v14 = g_NcbPolicyCurrentConsoleSessionId;
        }
        LeaveCriticalSection(&g_NcbPolicyLock);
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v16,
            v15,
            L"NcbPolicy: NcbPolicyConsoleSessionChangeHandlerHelper invokes NCB registrar callback",
            0);
        ((void (__fastcall *)(__int64))g_NcbPolicyChangeCallback)(2);
        NcbPolicyDereference();
        v20 = v23;
        if ( v23 )
        {
          NcbCCResetSignal(v23, 0, v19, 0, v6 == v14, 1);
          BiFreeMemory(v20);
        }
        else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          McTemplateU0zq_EventWriteTransfer(v18, v17, L"Failed to get User Sid Status", 1168);
        }
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007a70  mov     [rsp+arg_8], rbx
0x180007a75  push    rdi
0x180007a76  sub     rsp, 80h
0x180007a7d  mov     rax, cs:__security_cookie
0x180007a84  xor     rax, rsp
0x180007a87  mov     [rsp+88h+var_10], rax
0x180007a8c  mov     rdi, [rsp+88h+arg_20]
0x180007a94  lea     rbx, [rdi+14h]
0x180007a98  mov     rcx, rbx; pSid
0x180007a9b  call    cs:__imp_IsValidSid
0x180007aa1  test    eax, eax
0x180007aa3  jz      loc_180007B42
0x180007aa9  test    rbx, rbx
0x180007aac  jz      loc_180007B42
0x180007ab2  mov     edi, [rdi]
0x180007ab4  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007abb  mov     [rsp+88h+arg_0], rsi
0x180007ac3  call    cs:__imp_EnterCriticalSection
0x180007ac9  mov     rcx, rbx; Sid1
0x180007acc  call    NcbPolicyCleanupPoliciesUnderLock
0x180007ad1  xor     esi, esi
0x180007ad3  lea     rdx, [rsp+88h+StringSid]; StringSid
0x180007ad8  mov     rcx, rbx; Sid
0x180007adb  mov     [rsp+88h+StringSid], rsi
0x180007ae0  call    cs:__imp_ConvertSidToStringSidW
0x180007ae6  test    eax, eax
0x180007ae8  jz      loc_180007C69
0x180007aee  mov     rdx, [rsp+88h+StringSid]
0x180007af3  mov     rcx, rbx; Sid
0x180007af6  call    NcbPolicyEnumerateUserLockscreenApps
0x180007afb  mov     rcx, [rsp+88h+StringSid]; hMem
0x180007b00  call    cs:__imp_LocalFree
0x180007b06  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007b0d  call    cs:__imp_LeaveCriticalSection
0x180007b13  xor     ecx, ecx
0x180007b15  call    NcbPolicyPolicyChangeCallback
0x180007b1a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180007b21  mov     [rsp+88h+var_50], esi
0x180007b25  mov     [rsp+88h+var_48], rsi
0x180007b2a  jnz     short loc_180007B62
0x180007b2c  mov     eax, cs:g_NcbPolicyReference
0x180007b32  test    al, 1
0x180007b34  jz      loc_180007C8A
0x180007b3a  mov     rsi, [rsp+88h+arg_0]
0x180007b42  xor     eax, eax
0x180007b44  mov     rcx, [rsp+88h+var_10]
0x180007b49  xor     rcx, rsp; StackCookie
0x180007b4c  call    __security_check_cookie
0x180007b51  mov     rbx, [rsp+88h+arg_8]
0x180007b59  add     rsp, 80h
0x180007b60  pop     rdi
0x180007b61  retn
0x180007b62  lea     rax, aNcbpolicyNcbpo_7; "NcbPolicy: NcbPolicyConsoleSessionChang"...
0x180007b69  mov     dword ptr [rsp+88h+StringSid], esi
0x180007b6d  mov     [rsp+88h+var_30], rax
0x180007b72  lea     rdx, NcbApiStatus
0x180007b79  lea     rax, [rsp+88h+StringSid]
0x180007b7e  mov     [rsp+88h+var_28], 7Ah ; 'z'
0x180007b87  mov     [rsp+88h+var_20], rax
0x180007b8c  mov     r9d, 3
0x180007b92  lea     rax, [rsp+88h+var_40]
0x180007b97  mov     [rsp+88h+var_18], 4
0x180007ba0  mov     [rsp+88h+var_68], rax
0x180007ba5  call    McGenEventWrite_EventWriteTransfer
0x180007baa  jmp     short loc_180007B2C
0x180007bac  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007bb3  call    cs:__imp_EnterCriticalSection
0x180007bb9  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180007bbf  lea     r9, [rsp+88h+var_48]
0x180007bc4  mov     edx, edi
0x180007bc6  mov     ecx, eax
0x180007bc8  lea     r8, [rsp+88h+var_50]
0x180007bcd  mov     ebx, eax
0x180007bcf  call    NcbPolicyIsInteractiveUserLogonSession
0x180007bd4  test    al, al
0x180007bd6  jz      loc_180007CA0
0x180007bdc  mov     esi, cs:g_NcbPolicyCurrentConsoleSessionId
0x180007be2  cmp     ebx, esi
0x180007be4  jz      short loc_180007BEE
0x180007be6  mov     esi, ebx
0x180007be8  mov     cs:g_NcbPolicyCurrentConsoleSessionId, ebx
0x180007bee  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007bf5  call    cs:__imp_LeaveCriticalSection
0x180007bfb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180007c02  jnz     short loc_180007C58
0x180007c04  mov     rax, cs:g_NcbPolicyChangeCallback
0x180007c0b  mov     ecx, 2
0x180007c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c15  call    NcbPolicyDereference
0x180007c1a  mov     rbx, [rsp+88h+var_48]
0x180007c1f  test    rbx, rbx
0x180007c22  jz      loc_180007CB8
0x180007c28  xor     r9d, r9d
0x180007c2b  mov     [rsp+88h+var_60], 1
0x180007c30  xor     edx, edx
0x180007c32  mov     rcx, rbx
0x180007c35  cmp     edi, esi
0x180007c37  jnz     short loc_180007C51
0x180007c39  mov     byte ptr [rsp+88h+var_68], 1
0x180007c3e  call    NcbCCResetSignal
0x180007c43  mov     rcx, rbx
0x180007c46  call    cs:__imp_BiFreeMemory
0x180007c4c  jmp     loc_180007B3A
0x180007c51  mov     byte ptr [rsp+88h+var_68], 0
0x180007c56  jmp     short loc_180007C3E
0x180007c58  xor     r9d, r9d
0x180007c5b  lea     r8, aNcbpolicyNcbpo_5; "NcbPolicy: NcbPolicyConsoleSessionChang"...
0x180007c62  call    McTemplateU0zq_EventWriteTransfer
0x180007c67  jmp     short loc_180007C04
0x180007c69  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180007c70  jz      loc_180007B06
0x180007c76  xor     r9d, r9d
0x180007c79  lea     r8, aNcbpolicyNcbpo_12; "NcbPolicy: NcbPolicyAddUserLockscreenAp"...
0x180007c80  call    McTemplateU0zq_EventWriteTransfer
0x180007c85  jmp     loc_180007B06
0x180007c8a  lea     ecx, [rax+2]
0x180007c8d  lock cmpxchg cs:g_NcbPolicyReference, ecx
0x180007c95  jnz     loc_180007B2C
0x180007c9b  jmp     loc_180007BAC
0x180007ca0  mov     ebx, [rsp+88h+var_50]
0x180007ca4  cmp     ebx, 0FFFFFFFFh
0x180007ca7  jnz     loc_180007BDC
0x180007cad  mov     esi, cs:g_NcbPolicyCurrentConsoleSessionId
0x180007cb3  jmp     loc_180007BEE
0x180007cb8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180007cbf  jz      loc_180007B3A
0x180007cc5  mov     r9d, 490h
0x180007ccb  lea     r8, aFailedToGetUse; "Failed to get User Sid Status"
0x180007cd2  call    McTemplateU0zq_EventWriteTransfer
0x180007cd7  jmp     loc_180007B3A
```
