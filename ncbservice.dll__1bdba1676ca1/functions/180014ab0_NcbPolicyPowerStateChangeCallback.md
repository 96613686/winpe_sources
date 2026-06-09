# NcbPolicyPowerStateChangeCallback

- ea: `0x180014ab0`
- end: `0x180014c64`
- name: `NcbPolicyPowerStateChangeCallback`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000723c`
- `0x1800075c4`
- `0x18000a0a0`
- `0x18000a160`
- `0x180014ab0`
- `0x18001d8e0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180014ae6`
- `ntdll!RtlCompareMemory` at `0x180014ae6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c1f`

## pseudocode

```c
__int64 __fastcall NcbPolicyPowerStateChangeCallback(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  char v7; // al
  int v8; // ebx
  char v10; // bl
  int v11; // r8d
  int v12; // [rsp+30h] [rbp-58h] BYREF
  GUID Source2; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+48h] [rbp-40h] BYREF
  const wchar_t *v15; // [rsp+58h] [rbp-30h]
  __int64 v16; // [rsp+60h] [rbp-28h]
  int *v17; // [rsp+68h] [rbp-20h]
  __int64 v18; // [rsp+70h] [rbp-18h]

  Source2 = GUID_LOW_POWER_EPOCH;
  if ( RtlCompareMemory(a3, &Source2, 0x10u) != 16 || a3[4] != 4 )
    return 0;
  v7 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
  v8 = a3[5];
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v12 = v8;
    v15 = L"NcbPolicy: NcbPolicyPowerStateChangeCallback received PDC notification: ";
    v16 = 146;
    v17 = &v12;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(v5, (const EVENT_DESCRIPTOR *)NcbApiStatus, v6, 3u, &v14);
    v7 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
  }
  if ( v8 )
  {
    if ( v8 != 1 )
      return 0;
    v10 = 0;
    if ( (v7 & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"NcbPolicy: NcbPolicyPowerStateChangeCallback entering CS ", 0);
    EnterCriticalSection(&g_NcbPolicyLock);
    g_NcbPolicyOsIsInCs = 1;
    LeaveCriticalSection(&g_NcbPolicyLock);
    goto LABEL_17;
  }
  v10 = 0;
  if ( (v7 & 1) != 0 )
  {
    v12 = 0;
    v15 = L"NcbPolicy: NcbPolicyPowerStateChangeCallback exiting CS ";
    v16 = 114;
    v17 = &v12;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(v5, (const EVENT_DESCRIPTOR *)NcbApiStatus, v6, 3u, &v14);
  }
  EnterCriticalSection(&g_NcbPolicyLock);
  if ( g_NcbPolicyOsIsInCs )
  {
    g_NcbPolicyOsIsInCs = 0;
    v10 = 1;
  }
  LeaveCriticalSection(&g_NcbPolicyLock);
  if ( v10 )
  {
LABEL_17:
    NcbPolicyPolicyChangeCallback(1);
    if ( v10 )
      NcbCCResetSignal(0, 0, v11, 1, 0, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180014ab0  push    rbx
0x180014ab2  sub     rsp, 80h
0x180014ab9  mov     rax, cs:__security_cookie
0x180014ac0  xor     rax, rsp
0x180014ac3  mov     [rsp+88h+var_10], rax
0x180014ac8  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180014acf  mov     rbx, r8
0x180014ad2  lea     rdx, [rsp+88h+Source2]; Source2
0x180014ad7  mov     r8d, 10h; Length
0x180014add  mov     rcx, rbx; Source1
0x180014ae0  movdqu  [rsp+88h+Source2], xmm0
0x180014ae6  call    cs:__imp_RtlCompareMemory
0x180014aec  cmp     rax, 10h
0x180014af0  jnz     short loc_180014B60
0x180014af2  cmp     dword ptr [rbx+10h], 4
0x180014af6  jnz     short loc_180014B60
0x180014af8  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180014afe  mov     ebx, [rbx+14h]
0x180014b01  test    al, 1
0x180014b03  jz      short loc_180014B53
0x180014b05  lea     rax, aNcbpolicyNcbpo_19; "NcbPolicy: NcbPolicyPowerStateChangeCal"...
0x180014b0c  mov     [rsp+88h+var_58], ebx
0x180014b10  mov     [rsp+88h+var_30], rax
0x180014b15  lea     rdx, NcbApiStatus
0x180014b1c  lea     rax, [rsp+88h+var_58]
0x180014b21  mov     [rsp+88h+var_28], 92h
0x180014b2a  mov     [rsp+88h+var_20], rax
0x180014b2f  mov     r9d, 3
0x180014b35  lea     rax, [rsp+88h+var_40]
0x180014b3a  mov     [rsp+88h+var_18], 4
0x180014b43  mov     [rsp+88h+var_68], rax
0x180014b48  call    McGenEventWrite_EventWriteTransfer
0x180014b4d  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180014b53  test    ebx, ebx
0x180014b55  jz      short loc_180014B78
0x180014b57  cmp     ebx, 1
0x180014b5a  jz      loc_180014BFE
0x180014b60  xor     eax, eax
0x180014b62  mov     rcx, [rsp+88h+var_10]
0x180014b67  xor     rcx, rsp; StackCookie
0x180014b6a  call    __security_check_cookie
0x180014b6f  add     rsp, 80h
0x180014b76  pop     rbx
0x180014b77  retn
0x180014b78  xor     bl, bl
0x180014b7a  test    al, 1
0x180014b7c  jz      short loc_180014BCA
0x180014b7e  lea     rax, aNcbpolicyNcbpo_0; "NcbPolicy: NcbPolicyPowerStateChangeCal"...
0x180014b85  mov     [rsp+88h+var_58], 0
0x180014b8d  mov     [rsp+88h+var_30], rax
0x180014b92  lea     rdx, NcbApiStatus
0x180014b99  lea     rax, [rsp+88h+var_58]
0x180014b9e  mov     [rsp+88h+var_28], 72h ; 'r'
0x180014ba7  mov     [rsp+88h+var_20], rax
0x180014bac  mov     r9d, 3
0x180014bb2  lea     rax, [rsp+88h+var_40]
0x180014bb7  mov     [rsp+88h+var_18], 4
0x180014bc0  mov     [rsp+88h+var_68], rax
0x180014bc5  call    McGenEventWrite_EventWriteTransfer
0x180014bca  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180014bd1  call    cs:__imp_EnterCriticalSection
0x180014bd7  cmp     cs:g_NcbPolicyOsIsInCs, bl
0x180014bdd  jz      short loc_180014BE7
0x180014bdf  mov     cs:g_NcbPolicyOsIsInCs, bl
0x180014be5  mov     bl, 1
0x180014be7  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180014bee  call    cs:__imp_LeaveCriticalSection
0x180014bf4  test    bl, bl
0x180014bf6  jz      loc_180014B60
0x180014bfc  jmp     short loc_180014C25
0x180014bfe  xor     bl, bl
0x180014c00  test    al, 1
0x180014c02  jnz     short loc_180014C53
0x180014c04  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180014c0b  call    cs:__imp_EnterCriticalSection
0x180014c11  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180014c18  mov     cs:g_NcbPolicyOsIsInCs, 1
0x180014c1f  call    cs:__imp_LeaveCriticalSection
0x180014c25  mov     ecx, 1
0x180014c2a  call    NcbPolicyPolicyChangeCallback
0x180014c2f  test    bl, bl
0x180014c31  jz      loc_180014B60
0x180014c37  xor     edx, edx
0x180014c39  mov     [rsp+88h+var_60], 1
0x180014c3e  xor     ecx, ecx
0x180014c40  mov     byte ptr [rsp+88h+var_68], 0
0x180014c45  lea     r9d, [rdx+1]
0x180014c49  call    NcbCCResetSignal
0x180014c4e  jmp     loc_180014B60
0x180014c53  xor     r9d, r9d
0x180014c56  lea     r8, aNcbpolicyNcbpo_2; "NcbPolicy: NcbPolicyPowerStateChangeCal"...
0x180014c5d  call    McTemplateU0zq_EventWriteTransfer
0x180014c62  jmp     short loc_180014C04
```
