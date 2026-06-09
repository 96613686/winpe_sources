# Reg_DoRegisterAdapter

- ea: `0x18003e9b0`
- end: `0x18003ebb0`
- name: `Reg_DoRegisterAdapter`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180017430`

## callees

- `0x180004aa8`
- `0x180027ef0`
- `0x18003e1d4`
- `0x18003e9b0`
- `0x180046ec0`
- `0x18004b858`
- `0x180085fb8`
- `0x180086384`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!NetInfo_GetAdapterByName` at `0x18003eadb`
- `DNSAPI!NetInfo_GetAdapterByName` at `0x18003eadb`
- `DNSAPI!DnsTraceServerConfig` at `0x18003eb35`
- `DNSAPI!DnsTraceServerConfig` at `0x18003eb35`
- `DNSAPI!NetInfo_Free` at `0x18003eb5e`
- `DNSAPI!NetInfo_Free` at `0x18003eb5e`
- `DNSAPI!FlushDnsPolicyUnreachableStatus` at `0x18003ea66`
- `DNSAPI!FlushDnsPolicyUnreachableStatus` at `0x18003ea66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eb6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eb6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea39`

## pseudocode

```c
__int64 __fastcall Reg_DoRegisterAdapter(__int64 a1, int a2)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 AdapterByName; // rax
  int v9[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)v9 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SD(1035, 33, (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, a1, a2);
  if ( !a1 )
    return 87;
  if ( g_ResolverStatus == 213909760 )
  {
    v5 = 0;
    EnterCriticalSection(&g_HostRegQueuingCS);
    if ( g_fStopFlag )
      goto LABEL_25;
    if ( (a2 & 0x20) == 0 )
    {
      UpdateNetworkInfo(0, 0);
      UpdateNetworkInfo(0, 1);
      FlushDnsPolicyUnreachableStatus();
    }
    if ( g_fStopFlag )
      goto LABEL_25;
    if ( g_fVelocityNetinfoCleanup )
    {
      v6 = GrabNetworkInfo(0, (__int64 *)v9, 0);
      v5 = v6;
      if ( v6 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v7 = 34;
LABEL_24:
          WPP_SF_d(1035, v7, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, v6);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
    }
    else
    {
      v6 = GrabNetworkInfoOld(0, 1, (__int64 *)v9, 0);
      v5 = v6;
      if ( v6 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v7 = 35;
          goto LABEL_24;
        }
LABEL_25:
        NetInfo_Free(*(_QWORD *)v9);
        LeaveCriticalSection(&g_HostRegQueuingCS);
        goto LABEL_26;
      }
    }
    if ( !g_fStopFlag )
    {
      AdapterByName = NetInfo_GetAdapterByName(*(_QWORD *)v9, a1);
      if ( AdapterByName )
      {
        v5 = reg_RegisterSingleAdapter(*(__int64 *)v9, AdapterByName, a2, 0x10000000, 0);
        DnsTraceServerConfig(*(_QWORD *)v9, 1, 1);
      }
      else
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_S(1035, 36, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, a1);
        v5 = 123;
      }
    }
    goto LABEL_25;
  }
  v5 = 1062;
LABEL_26:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 37, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18003e9b0  mov     [rsp+arg_10], rbx
0x18003e9b5  mov     [rsp+arg_18], rsi
0x18003e9ba  push    rdi
0x18003e9bb  push    r12
0x18003e9bd  push    r15
0x18003e9bf  sub     rsp, 40h
0x18003e9c3  mov     rax, cs:__security_cookie
0x18003e9ca  xor     rax, rsp
0x18003e9cd  mov     [rsp+58h+var_20], rax
0x18003e9d2  mov     esi, edx
0x18003e9d4  mov     qword ptr [rsp+58h+var_28], 0
0x18003e9dd  mov     rdi, rcx
0x18003e9e0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e9e7  lea     r12, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids
0x18003e9ee  mov     r15d, 40Bh
0x18003e9f4  jz      short loc_18003EA0D
0x18003e9f6  mov     edx, 21h ; '!'
0x18003e9fb  mov     dword ptr [rsp+58h+var_38], esi
0x18003e9ff  mov     ecx, r15d
0x18003ea02  mov     r9, rdi
0x18003ea05  mov     r8, r12
0x18003ea08  call    WPP_SF_SD
0x18003ea0d  test    rdi, rdi
0x18003ea10  jnz     short loc_18003EA1A
0x18003ea12  lea     eax, [rdi+57h]
0x18003ea15  jmp     loc_18003EB8F
0x18003ea1a  cmp     cs:g_ResolverStatus, 0CC00100h
0x18003ea24  jz      short loc_18003EA30
0x18003ea26  mov     ebx, 426h
0x18003ea2b  jmp     loc_18003EB71
0x18003ea30  lea     rcx, g_HostRegQueuingCS; lpCriticalSection
0x18003ea37  xor     ebx, ebx
0x18003ea39  call    cs:__imp_EnterCriticalSection
0x18003ea3f  mov     eax, cs:g_fStopFlag
0x18003ea45  test    eax, eax
0x18003ea47  jnz     loc_18003EB59
0x18003ea4d  test    sil, 20h
0x18003ea51  jnz     short loc_18003EA6C
0x18003ea53  xor     edx, edx
0x18003ea55  xor     ecx, ecx
0x18003ea57  call    UpdateNetworkInfo
0x18003ea5c  lea     edx, [rbx+1]
0x18003ea5f  xor     ecx, ecx
0x18003ea61  call    UpdateNetworkInfo
0x18003ea66  call    cs:__imp_FlushDnsPolicyUnreachableStatus
0x18003ea6c  mov     eax, cs:g_fStopFlag
0x18003ea72  test    eax, eax
0x18003ea74  jnz     loc_18003EB59
0x18003ea7a  xor     ecx, ecx
0x18003ea7c  cmp     cs:g_fVelocityNetinfoCleanup, ebx
0x18003ea82  jz      short loc_18003EAAE
0x18003ea84  xor     r8d, r8d
0x18003ea87  lea     rdx, [rsp+58h+var_28]
0x18003ea8c  call    GrabNetworkInfo
0x18003ea91  mov     ebx, eax
0x18003ea93  test    eax, eax
0x18003ea95  jz      short loc_18003EAC5
0x18003ea97  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003ea9e  jz      loc_18003EB59
0x18003eaa4  mov     edx, 22h ; '"'
0x18003eaa9  jmp     loc_18003EB4B
0x18003eaae  xor     r9d, r9d
0x18003eab1  lea     r8, [rsp+58h+var_28]
0x18003eab6  lea     edx, [r9+1]
0x18003eaba  call    GrabNetworkInfoOld
0x18003eabf  mov     ebx, eax
0x18003eac1  test    eax, eax
0x18003eac3  jnz     short loc_18003EB3D
0x18003eac5  mov     eax, cs:g_fStopFlag
0x18003eacb  test    eax, eax
0x18003eacd  jnz     loc_18003EB59
0x18003ead3  mov     rcx, qword ptr [rsp+58h+var_28]
0x18003ead8  mov     rdx, rdi
0x18003eadb  call    cs:__imp_NetInfo_GetAdapterByName
0x18003eae1  test    rax, rax
0x18003eae4  jnz     short loc_18003EB07
0x18003eae6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003eaed  jz      short loc_18003EB00
0x18003eaef  lea     edx, [rax+24h]
0x18003eaf2  mov     ecx, r15d
0x18003eaf5  mov     r9, rdi
0x18003eaf8  mov     r8, r12
0x18003eafb  call    WPP_SF_S
0x18003eb00  mov     ebx, 7Bh ; '{'
0x18003eb05  jmp     short loc_18003EB59
0x18003eb07  mov     rcx, qword ptr [rsp+58h+var_28]; int
0x18003eb0c  mov     r9d, 10000000h; int
0x18003eb12  mov     r8d, esi; int
0x18003eb15  mov     [rsp+58h+var_38], 0; void *
0x18003eb1e  mov     rdx, rax; int
0x18003eb21  call    reg_RegisterSingleAdapter
0x18003eb26  mov     rcx, qword ptr [rsp+58h+var_28]
0x18003eb2b  mov     edx, 1
0x18003eb30  mov     r8d, edx
0x18003eb33  mov     ebx, eax
0x18003eb35  call    cs:__imp_DnsTraceServerConfig
0x18003eb3b  jmp     short loc_18003EB59
0x18003eb3d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003eb44  jz      short loc_18003EB59
0x18003eb46  mov     edx, 23h ; '#'
0x18003eb4b  mov     r9d, eax
0x18003eb4e  mov     r8, r12
0x18003eb51  mov     ecx, r15d
0x18003eb54  call    WPP_SF_d
0x18003eb59  mov     rcx, qword ptr [rsp+58h+var_28]
0x18003eb5e  call    cs:__imp_NetInfo_Free
0x18003eb64  lea     rcx, g_HostRegQueuingCS; lpCriticalSection
0x18003eb6b  call    cs:__imp_LeaveCriticalSection
0x18003eb71  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003eb78  jz      short loc_18003EB8D
0x18003eb7a  mov     edx, 25h ; '%'
0x18003eb7f  mov     ecx, r15d
0x18003eb82  mov     r9d, ebx
0x18003eb85  mov     r8, r12
0x18003eb88  call    WPP_SF_d
0x18003eb8d  mov     eax, ebx
0x18003eb8f  mov     rcx, [rsp+58h+var_20]
0x18003eb94  xor     rcx, rsp; StackCookie
0x18003eb97  call    __security_check_cookie
0x18003eb9c  mov     rbx, [rsp+58h+arg_10]
0x18003eba1  mov     rsi, [rsp+58h+arg_18]
0x18003eba6  add     rsp, 40h
0x18003ebaa  pop     r15
0x18003ebac  pop     r12
0x18003ebae  pop     rdi
0x18003ebaf  retn
```
