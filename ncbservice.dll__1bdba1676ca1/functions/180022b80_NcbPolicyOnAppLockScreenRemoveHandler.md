# NcbPolicyOnAppLockScreenRemoveHandler

- ea: `0x180022b80`
- end: `0x180022c4d`
- name: `NcbPolicyOnAppLockScreenRemoveHandler`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022e70`

## callees

- `0x1800075c4`
- `0x18000a0a0`
- `0x18000e1d0`
- `0x18000ed20`
- `0x180012b20`
- `0x180022b80`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180022c04`
- `ntdll!RtlRemoveEntryHashTable` at `0x180022c04`
- `ntdll!RtlFreeSid` at `0x180022c3c`
- `ntdll!RtlFreeSid` at `0x180022c3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022bca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022c1a`

## string_xrefs

- `0x180022ba0`: `NcbPolicy: NcbPolicyOnAppLockScreenRemoveHandler called - `

## pseudocode

```c
PVOID __fastcall NcbPolicyOnAppLockScreenRemoveHandler(unsigned __int16 *a1, __int64 a2, unsigned __int8 *a3)
{
  PVOID result; // rax
  void *v7; // rdi
  char v8; // si
  __int64 MatchingPolicyUnderLock; // rax
  __int64 v10; // rbx

  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(a1, a2, L"NcbPolicy: NcbPolicyOnAppLockScreenRemoveHandler called - ", 0);
  result = (PVOID)PackageFullNameToSid(a2);
  v7 = result;
  if ( result )
  {
    v8 = 0;
    EnterCriticalSection(&g_NcbPolicyLock);
    MatchingPolicyUnderLock = NcbPolicyFindMatchingPolicyUnderLock(a3, v7, a1, 0, 0, 0);
    v10 = MatchingPolicyUnderLock;
    if ( MatchingPolicyUnderLock )
    {
      RtlRemoveEntryHashTable(g_NcbPolicies, MatchingPolicyUnderLock, 0);
      --g_NcbPolicyCounter;
      v8 = 1;
    }
    LeaveCriticalSection(&g_NcbPolicyLock);
    if ( v10 )
      NcbPolicyFreePolicy(v10);
    if ( v8 )
      NcbPolicyPolicyChangeCallback(0);
    return RtlFreeSid(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180022b80  push    rbx
0x180022b82  push    rbp
0x180022b83  push    rsi
0x180022b84  push    rdi
0x180022b85  push    r14
0x180022b87  sub     rsp, 30h
0x180022b8b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022b92  mov     rbp, r8
0x180022b95  mov     rbx, rdx
0x180022b98  mov     r14, rcx
0x180022b9b  jz      short loc_180022BAC
0x180022b9d  xor     r9d, r9d
0x180022ba0  lea     r8, aNcbpolicyNcbpo_16; "NcbPolicy: NcbPolicyOnAppLockScreenRemo"...
0x180022ba7  call    McTemplateU0zq_EventWriteTransfer
0x180022bac  mov     rcx, rbx
0x180022baf  call    PackageFullNameToSid
0x180022bb4  mov     rdi, rax
0x180022bb7  test    rax, rax
0x180022bba  jz      loc_180022C42
0x180022bc0  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180022bc7  xor     sil, sil
0x180022bca  call    cs:__imp_EnterCriticalSection
0x180022bd0  xor     r9d, r9d
0x180022bd3  mov     [rsp+58h+var_30], sil; char
0x180022bd8  mov     r8, r14
0x180022bdb  mov     [rsp+58h+var_38], 0; __int64
0x180022be4  mov     rdx, rdi; PSID
0x180022be7  mov     rcx, rbp; Sid1
0x180022bea  call    NcbPolicyFindMatchingPolicyUnderLock
0x180022bef  mov     rbx, rax
0x180022bf2  test    rax, rax
0x180022bf5  jz      short loc_180022C13
0x180022bf7  xor     r8d, r8d
0x180022bfa  lea     rcx, g_NcbPolicies
0x180022c01  mov     rdx, rax
0x180022c04  call    cs:__imp_RtlRemoveEntryHashTable
0x180022c0a  dec     cs:g_NcbPolicyCounter
0x180022c10  mov     sil, 1
0x180022c13  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180022c1a  call    cs:__imp_LeaveCriticalSection
0x180022c20  test    rbx, rbx
0x180022c23  jz      short loc_180022C2D
0x180022c25  mov     rcx, rbx
0x180022c28  call    NcbPolicyFreePolicy
0x180022c2d  test    sil, sil
0x180022c30  jz      short loc_180022C39
0x180022c32  xor     ecx, ecx
0x180022c34  call    NcbPolicyPolicyChangeCallback
0x180022c39  mov     rcx, rdi; Sid
0x180022c3c  call    cs:__imp_RtlFreeSid
0x180022c42  add     rsp, 30h
0x180022c46  pop     r14
0x180022c48  pop     rdi
0x180022c49  pop     rsi
0x180022c4a  pop     rbp
0x180022c4b  pop     rbx
0x180022c4c  retn
```
