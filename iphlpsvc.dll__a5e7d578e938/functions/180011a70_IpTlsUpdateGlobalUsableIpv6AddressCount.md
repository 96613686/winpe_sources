# IpTlsUpdateGlobalUsableIpv6AddressCount

- ea: `0x180011a70`
- end: `0x180011e1c`
- name: `IpTlsUpdateGlobalUsableIpv6AddressCount`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012610`

## callees

- `0x18000d7c0`
- `0x180011a70`
- `0x180012550`
- `0x180012dcc`
- `0x1800418f4`
- `0x180041dc4`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180011abd`
- `ntdll!RtlIpv6AddressToStringW` at `0x180011abd`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011b31`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011b31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d46`
- `NSI!NsiGetAllParameters` at `0x180011be7`
- `NSI!NsiGetAllParameters` at `0x180011be7`

## string_xrefs

- `0x180011aeb`: `IpTlsUpdateGlobalUsableIpv6AddressCount:Address %s %s:`
- `0x180011ac9`: `Deleted`
- `0x180011ca0`: `IpTlsUpdateGlobalUsableIpv6AddressCount:Useable Address found %s`
- `0x180011dae`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180011dd3`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180011db5`: `IpTlsUpdateGlobalUsableIpv6AddressCount: Allocation failed:%hs:%d`

## pseudocode

```c
int __fastcall IpTlsUpdateGlobalUsableIpv6AddressCount(__int64 a1, int a2)
{
  _OWORD *v4; // rsi
  const wchar_t *v5; // r9
  SIZE_T v6; // rax
  LPVOID *i; // rbx
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // ecx
  SIZE_T *v12; // rdx
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  _QWORD *v16; // rax
  LPVOID *v17; // rcx
  HANDLE ProcessHeap; // rax
  int v19; // ecx
  int v21; // [rsp+20h] [rbp-268h]
  __int64 v22; // [rsp+60h] [rbp-228h] BYREF
  _OWORD v23[2]; // [rsp+68h] [rbp-220h] BYREF
  _BYTE v24[16]; // [rsp+90h] [rbp-1F8h] BYREF
  int v25; // [rsp+A0h] [rbp-1E8h]
  _BYTE v26[161]; // [rsp+F0h] [rbp-198h] BYREF
  char v27; // [rsp+191h] [rbp-F7h]
  WCHAR S[72]; // [rsp+1E0h] [rbp-A8h] BYREF

  memset_0(S, 0, 0x82u);
  v4 = (_OWORD *)(a1 + 8);
  RtlIpv6AddressToStringW((const struct in6_addr *)(a1 + 8), S);
  v5 = L"Added";
  if ( a2 != 1 )
    v5 = L"Deleted";
  EventWrite0(0x10000000, L"IpTlsUpdateGlobalUsableIpv6AddressCount:Address %s %s:", S, v5);
  LODWORD(v6) = Ipv6AddressScope((const UCHAR *)(a1 + 8));
  if ( (_DWORD)v6 == 14 )
  {
    if ( a2 != 1 )
    {
      for ( i = (LPVOID *)g_IpTlsGlobalV6AddressList; ; i = (LPVOID *)*i )
      {
        if ( i == &g_IpTlsGlobalV6AddressList )
          return v6;
        v6 = RtlCompareMemory(i + 2, v4, 0x10u);
        if ( v6 == 16 )
          break;
      }
      if ( !*((_BYTE *)i + 40) && !*((_BYTE *)i + 41) )
      {
        --g_IpTlsGlobalV6AddressCount;
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
          McTemplateU0qttt_EventWriteTransfer(
            v9,
            v8,
            v10,
            (unsigned __int8)g_IpTlsInternetConnectivityPresent,
            g_IpTlsInternetConnectivityPresent,
            1);
      }
      v16 = *i;
      if ( *((LPVOID **)*i + 1) == i )
      {
        v17 = (LPVOID *)i[1];
        if ( *v17 == i )
        {
          *v17 = v16;
          v16[1] = v17;
          ProcessHeap = GetProcessHeap();
          LODWORD(v6) = HeapFree(ProcessHeap, 0, i);
          return v6;
        }
      }
LABEL_32:
      __fastfail(3u);
    }
    memset_0(v26, 0, 0xF0u);
    memset(v23, 0, sizeof(v23));
    memset_0(v24, 0, 0x58u);
    v22 = *(_QWORD *)(a1 + 32);
    LODWORD(v6) = NsiGetAllParameters(1, &NPI_MS_IPV6_MODULEID, 7, &v22, 8, v26, 240, v24, 88, v23, 32);
    if ( !(_DWORD)v6 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
        LODWORD(v6) = McTemplateU0qztt_EventWriteTransfer(
                        v11,
                        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_V6_ADDRESS_CHANGE_CALLBACK,
                        *(_DWORD *)(a1 + 40),
                        (unsigned int)S,
                        v21,
                        v27);
      if ( *(_QWORD *)((char *)v23 + 4) != 0xF00000083LL )
      {
        v6 = MALLOC(0x30u);
        if ( v6 )
        {
          *(_OWORD *)v6 = 0;
          *(_OWORD *)(v6 + 16) = 0;
          *(_OWORD *)(v6 + 32) = 0;
          *(_OWORD *)(v6 + 16) = *v4;
          *(_QWORD *)(v6 + 32) = *(_QWORD *)(a1 + 32);
          *(_BYTE *)(v6 + 40) = v27;
          if ( !v25 )
            *(_BYTE *)(v6 + 41) = 1;
          v12 = (SIZE_T *)qword_1800CC448;
          if ( *(LPVOID **)qword_1800CC448 != &g_IpTlsGlobalV6AddressList )
            goto LABEL_32;
          *(_QWORD *)v6 = &g_IpTlsGlobalV6AddressList;
          *(_QWORD *)(v6 + 8) = v12;
          *v12 = v6;
          qword_1800CC448 = v6;
          if ( !*(_BYTE *)(v6 + 40) && !*(_BYTE *)(v6 + 41) )
          {
            LODWORD(v6) = EventWrite0(
                            0x10000000,
                            L"IpTlsUpdateGlobalUsableIpv6AddressCount:Useable Address found %s",
                            S);
            ++g_IpTlsGlobalV6AddressCount;
            if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
              LODWORD(v6) = McTemplateU0qttt_EventWriteTransfer(
                              v14,
                              v13,
                              v15,
                              (unsigned __int8)g_IpTlsInternetConnectivityPresent,
                              g_IpTlsInternetConnectivityPresent,
                              1);
          }
        }
        else
        {
          LODWORD(v6) = EventWrite0(
                          0x10000000,
                          L"IpTlsUpdateGlobalUsableIpv6AddressCount: Allocation failed:%hs:%d",
                          "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
                          2169);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
            LODWORD(v6) = McTemplateU0psq_EventWriteTransfer(
                            v19,
                            (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
                            0,
                            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
                            126);
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180011a70  mov     [rsp+arg_8], rbx
0x180011a75  mov     [rsp+arg_10], rsi
0x180011a7a  push    rdi
0x180011a7b  sub     rsp, 280h
0x180011a82  mov     rax, cs:__security_cookie
0x180011a89  xor     rax, rsp
0x180011a8c  mov     [rsp+288h+var_18], rax
0x180011a94  mov     ebx, edx
0x180011a96  mov     rdi, rcx
0x180011a99  xor     edx, edx; Val
0x180011a9b  lea     rcx, [rsp+288h+S]; void *
0x180011aa3  mov     r8d, 82h; Size
0x180011aa9  call    memset_0
0x180011aae  lea     rsi, [rdi+8]
0x180011ab2  mov     rcx, rsi; Addr
0x180011ab5  lea     rdx, [rsp+288h+S]; S
0x180011abd  call    cs:__imp_RtlIpv6AddressToStringW
0x180011ac4  nop     dword ptr [rax+rax+00h]
0x180011ac9  lea     rax, aDeleted; "Deleted"
0x180011ad0  cmp     ebx, 1
0x180011ad3  lea     r9, aAdded; "Added"
0x180011ada  mov     ecx, 10000000h
0x180011adf  cmovnz  r9, rax
0x180011ae3  lea     r8, [rsp+288h+S]
0x180011aeb  lea     rdx, aIptlsupdateglo_0; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011af2  call    EventWrite0
0x180011af7  mov     rcx, rsi; Address
0x180011afa  call    Ipv6AddressScope
0x180011aff  cmp     eax, 0Eh
0x180011b02  jnz     loc_180011CBF
0x180011b08  cmp     ebx, 1
0x180011b0b  jz      short loc_180011B4C
0x180011b0d  mov     rbx, cs:g_IpTlsGlobalV6AddressList
0x180011b14  lea     rdi, g_IpTlsGlobalV6AddressList
0x180011b1b  cmp     rbx, rdi
0x180011b1e  jz      loc_180011CBF
0x180011b24  lea     rcx, [rbx+10h]; Source1
0x180011b28  mov     r8d, 10h; Length
0x180011b2e  mov     rdx, rsi; Source2
0x180011b31  call    cs:__imp_RtlCompareMemory
0x180011b38  nop     dword ptr [rax+rax+00h]
0x180011b3d  cmp     rax, 10h
0x180011b41  jz      loc_180011CF2
0x180011b47  mov     rbx, [rbx]
0x180011b4a  jmp     short loc_180011B1B
0x180011b4c  xor     edx, edx; Val
0x180011b4e  lea     rcx, [rsp+288h+var_198]; void *
0x180011b56  mov     r8d, 0F0h; Size
0x180011b5c  call    memset_0
0x180011b61  xorps   xmm0, xmm0
0x180011b64  lea     rcx, [rsp+288h+var_1F8]; void *
0x180011b6c  xor     edx, edx; Val
0x180011b6e  mov     r8d, 58h ; 'X'; Size
0x180011b74  movups  [rsp+288h+var_220], xmm0
0x180011b79  movups  [rsp+288h+var_210], xmm0
0x180011b7e  call    memset_0
0x180011b83  mov     rax, [rdi+20h]
0x180011b87  lea     r9, [rsp+288h+var_228]
0x180011b8c  mov     [rsp+288h+var_238], 20h ; ' '
0x180011b94  lea     rdx, NPI_MS_IPV6_MODULEID
0x180011b9b  mov     [rsp+288h+var_228], rax
0x180011ba0  mov     r8d, 7
0x180011ba6  lea     rax, [rsp+288h+var_220]
0x180011bab  mov     ecx, 1
0x180011bb0  mov     [rsp+288h+var_240], rax
0x180011bb5  lea     rax, [rsp+288h+var_1F8]
0x180011bbd  mov     [rsp+288h+var_248], 58h ; 'X'
0x180011bc5  mov     [rsp+288h+var_250], rax
0x180011bca  lea     rax, [rsp+288h+var_198]
0x180011bd2  mov     [rsp+288h+var_258], 0F0h
0x180011bda  mov     [rsp+288h+var_260], rax
0x180011bdf  mov     [rsp+288h+var_268], 8
0x180011be7  call    cs:__imp_NsiGetAllParameters
0x180011bee  nop     dword ptr [rax+rax+00h]
0x180011bf3  test    eax, eax
0x180011bf5  jnz     loc_180011CBF
0x180011bfb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011c02  jnz     loc_180011D57
0x180011c08  cmp     dword ptr [rsp+288h+var_220+4], 83h
0x180011c10  jz      loc_180011CE5
0x180011c16  mov     ecx, 30h ; '0'; dwBytes
0x180011c1b  call    MALLOC
0x180011c20  test    rax, rax
0x180011c23  jz      loc_180011DA8
0x180011c29  xorps   xmm0, xmm0
0x180011c2c  movups  xmmword ptr [rax], xmm0
0x180011c2f  movups  xmmword ptr [rax+10h], xmm0
0x180011c33  movups  xmmword ptr [rax+20h], xmm0
0x180011c37  movups  xmm0, xmmword ptr [rsi]
0x180011c3a  movups  xmmword ptr [rax+10h], xmm0
0x180011c3e  mov     rcx, [rdi+20h]
0x180011c42  mov     [rax+20h], rcx
0x180011c46  movzx   ecx, [rsp+288h+var_F7]
0x180011c4e  mov     [rax+28h], cl
0x180011c51  cmp     [rsp+288h+var_1E8], 0
0x180011c59  jz      loc_180011D80
0x180011c5f  mov     rdx, cs:qword_1800CC448
0x180011c66  lea     rdi, g_IpTlsGlobalV6AddressList
0x180011c6d  cmp     [rdx], rdi
0x180011c70  jnz     loc_180011E15
0x180011c76  mov     [rax], rdi
0x180011c79  mov     [rax+8], rdx
0x180011c7d  mov     [rdx], rax
0x180011c80  mov     cs:qword_1800CC448, rax
0x180011c87  cmp     byte ptr [rax+28h], 0
0x180011c8b  jnz     short loc_180011CBF
0x180011c8d  cmp     byte ptr [rax+29h], 0
0x180011c91  jnz     short loc_180011CBF
0x180011c93  lea     r8, [rsp+288h+S]
0x180011c9b  mov     ecx, 10000000h
0x180011ca0  lea     rdx, aIptlsupdateglo_1; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011ca7  call    EventWrite0
0x180011cac  inc     cs:g_IpTlsGlobalV6AddressCount
0x180011cb2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011cb9  jnz     loc_180011D89
0x180011cbf  mov     rcx, [rsp+288h+var_18]
0x180011cc7  xor     rcx, rsp; StackCookie
0x180011cca  call    __security_check_cookie
0x180011ccf  lea     r11, [rsp+288h+var_8]
0x180011cd7  mov     rbx, [r11+18h]
0x180011cdb  mov     rsi, [r11+20h]
0x180011cdf  mov     rsp, r11
0x180011ce2  pop     rdi
0x180011ce3  retn
0x180011ce5  cmp     dword ptr [rsp+288h+var_220+8], 0Fh
0x180011cea  jnz     loc_180011C16
0x180011cf0  jmp     short loc_180011CBF
0x180011cf2  cmp     byte ptr [rbx+28h], 0
0x180011cf6  jnz     short loc_180011D11
0x180011cf8  cmp     byte ptr [rbx+29h], 0
0x180011cfc  jnz     short loc_180011D11
0x180011cfe  dec     cs:g_IpTlsGlobalV6AddressCount
0x180011d04  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011d0b  jnz     loc_180011DF6
0x180011d11  mov     rax, [rbx]
0x180011d14  cmp     [rax+8], rbx
0x180011d18  jnz     loc_180011E15
0x180011d1e  mov     rcx, [rbx+8]
0x180011d22  cmp     [rcx], rbx
0x180011d25  jnz     loc_180011E15
0x180011d2b  mov     [rcx], rax
0x180011d2e  mov     [rax+8], rcx
0x180011d32  call    cs:__imp_GetProcessHeap
0x180011d39  nop     dword ptr [rax+rax+00h]
0x180011d3e  mov     r8, rbx; lpMem
0x180011d41  xor     edx, edx; dwFlags
0x180011d43  mov     rcx, rax; hHeap
0x180011d46  call    cs:__imp_HeapFree
0x180011d4d  nop     dword ptr [rax+rax+00h]
0x180011d52  jmp     loc_180011CBF
0x180011d57  movzx   eax, [rsp+288h+var_F7]
0x180011d5f  lea     r9, [rsp+288h+S]
0x180011d67  mov     r8d, [rdi+28h]
0x180011d6b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_V6_ADDRESS_CHANGE_CALLBACK
0x180011d72  mov     dword ptr [rsp+288h+var_260], eax
0x180011d76  call    McTemplateU0qztt_EventWriteTransfer
0x180011d7b  jmp     loc_180011C08
0x180011d80  mov     byte ptr [rax+29h], 1
0x180011d84  jmp     loc_180011C5F
0x180011d89  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x180011d91  mov     dword ptr [rsp+288h+var_260], 1
0x180011d99  mov     [rsp+288h+var_268], r9d
0x180011d9e  call    McTemplateU0qttt_EventWriteTransfer
0x180011da3  jmp     loc_180011CBF
0x180011da8  mov     r9d, 879h
0x180011dae  lea     r8, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180011db5  lea     rdx, aIptlsupdateglo; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011dbc  mov     ecx, 10000000h
0x180011dc1  call    EventWrite0
0x180011dc6  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180011dcd  jz      loc_180011CBF
0x180011dd3  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180011dda  mov     [rsp+288h+var_268], 87Eh
0x180011de2  xor     r8d, r8d
0x180011de5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180011dec  call    McTemplateU0psq_EventWriteTransfer
0x180011df1  jmp     loc_180011CBF
0x180011df6  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x180011dfe  mov     dword ptr [rsp+288h+var_260], 1
0x180011e06  mov     [rsp+288h+var_268], r9d
0x180011e0b  call    McTemplateU0qttt_EventWriteTransfer
0x180011e10  jmp     loc_180011D11
0x180011e15  mov     ecx, 3
0x180011e1a  int     29h; Win8: RtlFailFast(ecx)
```
