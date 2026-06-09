# GrabZtProbeNetworkInfo

- ea: `0x18004bf54`
- end: `0x18004c15b`
- name: `GrabZtProbeNetworkInfo`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e860`

## callees

- `0x180005bd0`
- `0x180005d50`
- `0x180040cd4`
- `0x180046ec0`
- `0x18004b808`
- `0x18004bf54`
- `0x18007a6e8`
- `0x180086b1c`
- `0x180086f78`

## import_xrefs

- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004c046`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004c046`
- `DNSAPI!DnsTraceServerConfig` at `0x18004c077`
- `DNSAPI!DnsTraceServerConfig` at `0x18004c077`
- `DNSAPI!NetInfo_Free` at `0x18004c0e2`
- `DNSAPI!NetInfo_Free` at `0x18004c0f0`
- `DNSAPI!NetInfo_Free` at `0x18004c0e2`
- `DNSAPI!NetInfo_Free` at `0x18004c0f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c0d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c0d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c00e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c00e`

## pseudocode

```c
__int64 __fastcall GrabZtProbeNetworkInfo(__int64 a1, _QWORD *a2, void **a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  _BOOL8 v13; // rdx
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  __int64 v16; // [rsp+38h] [rbp-38h] BYREF
  void *v17; // [rsp+40h] [rbp-30h] BYREF
  __int128 v18; // [rsp+48h] [rbp-28h] BYREF
  int v19; // [rsp+58h] [rbp-18h] BYREF

  v15 = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qq(1035, 35, (unsigned int)WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, (_DWORD)a2, (__int64)a3);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 && a3 && a1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF__SOCKADDR_(a1, 36, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, a1 + 16);
    EnterCriticalSection(&g_csResolverNetInfo);
    *((_QWORD *)&v18 + 1) = a1;
    LODWORD(v18) = 1;
    v8 = DnsApi_NetInfo_BuildEx2(&v18, v7, &v19, &v15);
    v6 = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_24;
      v9 = 37;
    }
    else
    {
      *(_DWORD *)(v15 + 48) = 0;
      v8 = NetInfo_CreatePerNetworkNetinfo(v15, &v16);
      v6 = v8;
      if ( v8 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_24;
        v9 = 38;
      }
      else
      {
        *(_DWORD *)(v16 + 48) = 0;
        v8 = CreateServerMapView(v15, &v17);
        v6 = v8;
        if ( !v8 )
        {
          DnsTraceServerConfig(v15, 1, 1);
          *a2 = v16;
          *a3 = v17;
          v16 = 0;
          v17 = 0;
LABEL_24:
          LeaveCriticalSection(&g_csResolverNetInfo);
          goto LABEL_25;
        }
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_24;
        v9 = 39;
      }
    }
    WPP_SF_d(1035, v9, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v8);
    goto LABEL_24;
  }
  v6 = 87;
LABEL_25:
  NetInfo_Free(v15);
  v15 = 0;
  NetInfo_Free(v16);
  v16 = 0;
  DeRefServerMapView(v17);
  if ( a2 )
  {
    v13 = *a2 != 0;
    if ( (v6 == 0) != v13 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v13, v11, v12);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 40, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18004bf54  push    rbp
0x18004bf56  push    rbx
0x18004bf57  push    rsi
0x18004bf58  push    rdi
0x18004bf59  push    r12
0x18004bf5b  push    r13
0x18004bf5d  push    r14
0x18004bf5f  mov     rbp, rsp
0x18004bf62  sub     rsp, 70h
0x18004bf66  mov     rax, cs:__security_cookie
0x18004bf6d  xor     rax, rsp
0x18004bf70  mov     [rbp+var_10], rax
0x18004bf74  xor     r14d, r14d
0x18004bf77  xorps   xmm0, xmm0
0x18004bf7a  mov     [rbp+var_40], r14
0x18004bf7e  mov     rsi, r8
0x18004bf81  mov     [rbp+var_38], r14
0x18004bf85  mov     rdi, rdx
0x18004bf88  mov     [rbp+var_30], r14
0x18004bf8c  mov     rbx, rcx
0x18004bf8f  mov     [rbp+var_18], r14d
0x18004bf93  movups  [rbp+var_28], xmm0
0x18004bf97  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bf9e  lea     r12, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18004bfa5  mov     r13d, 40Bh
0x18004bfab  jz      short loc_18004BFC4
0x18004bfad  mov     [rsp+70h+var_50], r8
0x18004bfb2  lea     edx, [r14+23h]
0x18004bfb6  mov     r8, r12
0x18004bfb9  mov     ecx, r13d
0x18004bfbc  mov     r9, rdi
0x18004bfbf  call    WPP_SF_qq
0x18004bfc4  test    rdi, rdi
0x18004bfc7  jz      short loc_18004BFCC
0x18004bfc9  mov     [rdi], r14
0x18004bfcc  test    rsi, rsi
0x18004bfcf  jz      short loc_18004BFD4
0x18004bfd1  mov     [rsi], r14
0x18004bfd4  test    rdi, rdi
0x18004bfd7  jnz     short loc_18004BFE3
0x18004bfd9  mov     ebx, 57h ; 'W'
0x18004bfde  jmp     loc_18004C0DE
0x18004bfe3  test    rsi, rsi
0x18004bfe6  jz      short loc_18004BFD9
0x18004bfe8  test    rbx, rbx
0x18004bfeb  jz      short loc_18004BFD9
0x18004bfed  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bff4  jz      short loc_18004C007
0x18004bff6  lea     r9, [rbx+10h]
0x18004bffa  mov     edx, 24h ; '$'
0x18004bfff  mov     r8, r12
0x18004c002  call    WPP_SF__SOCKADDR_
0x18004c007  lea     rcx, g_csResolverNetInfo; lpCriticalSection
0x18004c00e  call    cs:__imp_EnterCriticalSection
0x18004c014  lea     r9, [rbp+var_40]
0x18004c018  mov     qword ptr [rbp+var_28+8], rbx
0x18004c01c  lea     r8, [rbp+var_18]
0x18004c020  mov     dword ptr [rbp+var_28], 1
0x18004c027  lea     rcx, [rbp+var_28]
0x18004c02b  call    DnsApi_NetInfo_BuildEx2
0x18004c030  mov     ebx, eax
0x18004c032  test    eax, eax
0x18004c034  jnz     short loc_18004C0B5
0x18004c036  mov     rax, [rbp+var_40]
0x18004c03a  lea     rdx, [rbp+var_38]
0x18004c03e  mov     [rax+30h], r14d
0x18004c042  mov     rcx, [rbp+var_40]
0x18004c046  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18004c04c  mov     ebx, eax
0x18004c04e  test    eax, eax
0x18004c050  jnz     short loc_18004C0A5
0x18004c052  mov     rax, [rbp+var_38]
0x18004c056  lea     rdx, [rbp+var_30]
0x18004c05a  mov     [rax+30h], r14d
0x18004c05e  mov     rcx, [rbp+var_40]
0x18004c062  call    CreateServerMapView
0x18004c067  mov     ebx, eax
0x18004c069  test    eax, eax
0x18004c06b  jnz     short loc_18004C095
0x18004c06d  mov     rcx, [rbp+var_40]
0x18004c071  lea     edx, [rax+1]
0x18004c074  mov     r8d, edx
0x18004c077  call    cs:__imp_DnsTraceServerConfig
0x18004c07d  mov     rax, [rbp+var_38]
0x18004c081  mov     [rdi], rax
0x18004c084  mov     rax, [rbp+var_30]
0x18004c088  mov     [rsi], rax
0x18004c08b  mov     [rbp+var_38], r14
0x18004c08f  mov     [rbp+var_30], r14
0x18004c093  jmp     short loc_18004C0D1
0x18004c095  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004c09c  jz      short loc_18004C0D1
0x18004c09e  mov     edx, 27h ; '''
0x18004c0a3  jmp     short loc_18004C0C3
0x18004c0a5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004c0ac  jz      short loc_18004C0D1
0x18004c0ae  mov     edx, 26h ; '&'
0x18004c0b3  jmp     short loc_18004C0C3
0x18004c0b5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004c0bc  jz      short loc_18004C0D1
0x18004c0be  mov     edx, 25h ; '%'
0x18004c0c3  mov     r9d, eax
0x18004c0c6  mov     r8, r12
0x18004c0c9  mov     ecx, r13d
0x18004c0cc  call    WPP_SF_d
0x18004c0d1  lea     rcx, g_csResolverNetInfo; lpCriticalSection
0x18004c0d8  call    cs:__imp_LeaveCriticalSection
0x18004c0de  mov     rcx, [rbp+var_40]
0x18004c0e2  call    cs:__imp_NetInfo_Free
0x18004c0e8  mov     rcx, [rbp+var_38]
0x18004c0ec  mov     [rbp+var_40], r14
0x18004c0f0  call    cs:__imp_NetInfo_Free
0x18004c0f6  mov     rcx, [rbp+var_30]; void *
0x18004c0fa  mov     [rbp+var_38], r14
0x18004c0fe  call    DeRefServerMapView
0x18004c103  test    rdi, rdi
0x18004c106  jz      short loc_18004C122
0x18004c108  cmp     [rdi], r14
0x18004c10b  mov     edx, r14d
0x18004c10e  mov     eax, r14d
0x18004c111  setnz   dl
0x18004c114  test    ebx, ebx
0x18004c116  setz    al
0x18004c119  cmp     eax, edx
0x18004c11b  jz      short loc_18004C122
0x18004c11d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004c122  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004c129  jz      short loc_18004C13E
0x18004c12b  mov     edx, 28h ; '('
0x18004c130  mov     ecx, r13d
0x18004c133  mov     r9d, ebx
0x18004c136  mov     r8, r12
0x18004c139  call    WPP_SF_d
0x18004c13e  mov     eax, ebx
0x18004c140  mov     rcx, [rbp+var_10]
0x18004c144  xor     rcx, rsp; StackCookie
0x18004c147  call    __security_check_cookie
0x18004c14c  add     rsp, 70h
0x18004c150  pop     r14
0x18004c152  pop     r13
0x18004c154  pop     r12
0x18004c156  pop     rdi
0x18004c157  pop     rsi
0x18004c158  pop     rbx
0x18004c159  pop     rbp
0x18004c15a  retn
```
