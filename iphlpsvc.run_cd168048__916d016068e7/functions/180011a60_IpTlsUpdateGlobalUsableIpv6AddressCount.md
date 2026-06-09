# IpTlsUpdateGlobalUsableIpv6AddressCount

- ea: `0x180011a60`
- end: `0x180011e0c`
- name: `IpTlsUpdateGlobalUsableIpv6AddressCount`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012600`

## callees

- `0x18000d7b0`
- `0x180011a60`
- `0x180012540`
- `0x180012dbc`
- `0x180041934`
- `0x180041e04`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180011aad`
- `ntdll!RtlIpv6AddressToStringW` at `0x180011aad`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011b21`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011b21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d36`
- `NSI!NsiGetAllParameters` at `0x180011bd7`
- `NSI!NsiGetAllParameters` at `0x180011bd7`

## string_xrefs

- `0x180011adb`: `IpTlsUpdateGlobalUsableIpv6AddressCount:Address %s %s:`
- `0x180011ab9`: `Deleted`
- `0x180011c90`: `IpTlsUpdateGlobalUsableIpv6AddressCount:Useable Address found %s`
- `0x180011d9e`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180011dc3`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180011da5`: `IpTlsUpdateGlobalUsableIpv6AddressCount: Allocation failed:%hs:%d`

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
  __int64 v21; // [rsp+60h] [rbp-228h] BYREF
  __int128 v22; // [rsp+68h] [rbp-220h]
  __int128 v23; // [rsp+78h] [rbp-210h]
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
    v22 = 0;
    v23 = 0;
    memset_0(v24, 0, 0x58u);
    v21 = *(_QWORD *)(a1 + 32);
    LODWORD(v6) = NsiGetAllParameters(1, &NPI_MS_IPV6_MODULEID, 7, &v21);
    if ( !(_DWORD)v6 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
        LODWORD(v6) = McTemplateU0qztt_EventWriteTransfer(
                        v11,
                        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_V6_ADDRESS_CHANGE_CALLBACK,
                        *(_DWORD *)(a1 + 40),
                        (unsigned int)S,
                        8,
                        v27);
      if ( *(_QWORD *)((char *)&v22 + 4) != 0xF00000083LL )
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
0x180011a60  mov     [rsp+arg_8], rbx
0x180011a65  mov     [rsp+arg_10], rsi
0x180011a6a  push    rdi
0x180011a6b  sub     rsp, 280h
0x180011a72  mov     rax, cs:__security_cookie
0x180011a79  xor     rax, rsp
0x180011a7c  mov     [rsp+288h+var_18], rax
0x180011a84  mov     ebx, edx
0x180011a86  mov     rdi, rcx
0x180011a89  xor     edx, edx; Val
0x180011a8b  lea     rcx, [rsp+288h+S]; void *
0x180011a93  mov     r8d, 82h; Size
0x180011a99  call    memset_0
0x180011a9e  lea     rsi, [rdi+8]
0x180011aa2  mov     rcx, rsi; Addr
0x180011aa5  lea     rdx, [rsp+288h+S]; S
0x180011aad  call    cs:__imp_RtlIpv6AddressToStringW
0x180011ab4  nop     dword ptr [rax+rax+00h]
0x180011ab9  lea     rax, aDeleted; "Deleted"
0x180011ac0  cmp     ebx, 1
0x180011ac3  lea     r9, aAdded; "Added"
0x180011aca  mov     ecx, 10000000h
0x180011acf  cmovnz  r9, rax
0x180011ad3  lea     r8, [rsp+288h+S]
0x180011adb  lea     rdx, aIptlsupdateglo_0; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011ae2  call    EventWrite0
0x180011ae7  mov     rcx, rsi; Address
0x180011aea  call    Ipv6AddressScope
0x180011aef  cmp     eax, 0Eh
0x180011af2  jnz     loc_180011CAF
0x180011af8  cmp     ebx, 1
0x180011afb  jz      short loc_180011B3C
0x180011afd  mov     rbx, cs:g_IpTlsGlobalV6AddressList
0x180011b04  lea     rdi, g_IpTlsGlobalV6AddressList
0x180011b0b  cmp     rbx, rdi
0x180011b0e  jz      loc_180011CAF
0x180011b14  lea     rcx, [rbx+10h]; Source1
0x180011b18  mov     r8d, 10h; Length
0x180011b1e  mov     rdx, rsi; Source2
0x180011b21  call    cs:__imp_RtlCompareMemory
0x180011b28  nop     dword ptr [rax+rax+00h]
0x180011b2d  cmp     rax, 10h
0x180011b31  jz      loc_180011CE2
0x180011b37  mov     rbx, [rbx]
0x180011b3a  jmp     short loc_180011B0B
0x180011b3c  xor     edx, edx; Val
0x180011b3e  lea     rcx, [rsp+288h+var_198]; void *
0x180011b46  mov     r8d, 0F0h; Size
0x180011b4c  call    memset_0
0x180011b51  xorps   xmm0, xmm0
0x180011b54  lea     rcx, [rsp+288h+var_1F8]; void *
0x180011b5c  xor     edx, edx; Val
0x180011b5e  mov     r8d, 58h ; 'X'; Size
0x180011b64  movups  [rsp+288h+var_220], xmm0
0x180011b69  movups  [rsp+288h+var_210], xmm0
0x180011b6e  call    memset_0
0x180011b73  mov     rax, [rdi+20h]
0x180011b77  lea     r9, [rsp+288h+var_228]
0x180011b7c  mov     [rsp+288h+var_238], 20h ; ' '
0x180011b84  lea     rdx, NPI_MS_IPV6_MODULEID
0x180011b8b  mov     [rsp+288h+var_228], rax
0x180011b90  mov     r8d, 7
0x180011b96  lea     rax, [rsp+288h+var_220]
0x180011b9b  mov     ecx, 1
0x180011ba0  mov     [rsp+288h+var_240], rax
0x180011ba5  lea     rax, [rsp+288h+var_1F8]
0x180011bad  mov     [rsp+288h+var_248], 58h ; 'X'
0x180011bb5  mov     [rsp+288h+var_250], rax
0x180011bba  lea     rax, [rsp+288h+var_198]
0x180011bc2  mov     [rsp+288h+var_258], 0F0h
0x180011bca  mov     [rsp+288h+var_260], rax
0x180011bcf  mov     [rsp+288h+var_268], 8
0x180011bd7  call    cs:__imp_NsiGetAllParameters
0x180011bde  nop     dword ptr [rax+rax+00h]
0x180011be3  test    eax, eax
0x180011be5  jnz     loc_180011CAF
0x180011beb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011bf2  jnz     loc_180011D47
0x180011bf8  cmp     dword ptr [rsp+288h+var_220+4], 83h
0x180011c00  jz      loc_180011CD5
0x180011c06  mov     ecx, 30h ; '0'; dwBytes
0x180011c0b  call    MALLOC
0x180011c10  test    rax, rax
0x180011c13  jz      loc_180011D98
0x180011c19  xorps   xmm0, xmm0
0x180011c1c  movups  xmmword ptr [rax], xmm0
0x180011c1f  movups  xmmword ptr [rax+10h], xmm0
0x180011c23  movups  xmmword ptr [rax+20h], xmm0
0x180011c27  movups  xmm0, xmmword ptr [rsi]
0x180011c2a  movups  xmmword ptr [rax+10h], xmm0
0x180011c2e  mov     rcx, [rdi+20h]
0x180011c32  mov     [rax+20h], rcx
0x180011c36  movzx   ecx, [rsp+288h+var_F7]
0x180011c3e  mov     [rax+28h], cl
0x180011c41  cmp     [rsp+288h+var_1E8], 0
0x180011c49  jz      loc_180011D70
0x180011c4f  mov     rdx, cs:qword_1800CC448
0x180011c56  lea     rdi, g_IpTlsGlobalV6AddressList
0x180011c5d  cmp     [rdx], rdi
0x180011c60  jnz     loc_180011E05
0x180011c66  mov     [rax], rdi
0x180011c69  mov     [rax+8], rdx
0x180011c6d  mov     [rdx], rax
0x180011c70  mov     cs:qword_1800CC448, rax
0x180011c77  cmp     byte ptr [rax+28h], 0
0x180011c7b  jnz     short loc_180011CAF
0x180011c7d  cmp     byte ptr [rax+29h], 0
0x180011c81  jnz     short loc_180011CAF
0x180011c83  lea     r8, [rsp+288h+S]
0x180011c8b  mov     ecx, 10000000h
0x180011c90  lea     rdx, aIptlsupdateglo_1; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011c97  call    EventWrite0
0x180011c9c  inc     cs:g_IpTlsGlobalV6AddressCount
0x180011ca2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011ca9  jnz     loc_180011D79
0x180011caf  mov     rcx, [rsp+288h+var_18]
0x180011cb7  xor     rcx, rsp; StackCookie
0x180011cba  call    __security_check_cookie
0x180011cbf  lea     r11, [rsp+288h+var_8]
0x180011cc7  mov     rbx, [r11+18h]
0x180011ccb  mov     rsi, [r11+20h]
0x180011ccf  mov     rsp, r11
0x180011cd2  pop     rdi
0x180011cd3  retn
0x180011cd5  cmp     dword ptr [rsp+288h+var_220+8], 0Fh
0x180011cda  jnz     loc_180011C06
0x180011ce0  jmp     short loc_180011CAF
0x180011ce2  cmp     byte ptr [rbx+28h], 0
0x180011ce6  jnz     short loc_180011D01
0x180011ce8  cmp     byte ptr [rbx+29h], 0
0x180011cec  jnz     short loc_180011D01
0x180011cee  dec     cs:g_IpTlsGlobalV6AddressCount
0x180011cf4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180011cfb  jnz     loc_180011DE6
0x180011d01  mov     rax, [rbx]
0x180011d04  cmp     [rax+8], rbx
0x180011d08  jnz     loc_180011E05
0x180011d0e  mov     rcx, [rbx+8]
0x180011d12  cmp     [rcx], rbx
0x180011d15  jnz     loc_180011E05
0x180011d1b  mov     [rcx], rax
0x180011d1e  mov     [rax+8], rcx
0x180011d22  call    cs:__imp_GetProcessHeap
0x180011d29  nop     dword ptr [rax+rax+00h]
0x180011d2e  mov     r8, rbx; lpMem
0x180011d31  xor     edx, edx; dwFlags
0x180011d33  mov     rcx, rax; hHeap
0x180011d36  call    cs:__imp_HeapFree
0x180011d3d  nop     dword ptr [rax+rax+00h]
0x180011d42  jmp     loc_180011CAF
0x180011d47  movzx   eax, [rsp+288h+var_F7]
0x180011d4f  lea     r9, [rsp+288h+S]
0x180011d57  mov     r8d, [rdi+28h]
0x180011d5b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_V6_ADDRESS_CHANGE_CALLBACK
0x180011d62  mov     dword ptr [rsp+288h+var_260], eax
0x180011d66  call    McTemplateU0qztt_EventWriteTransfer
0x180011d6b  jmp     loc_180011BF8
0x180011d70  mov     byte ptr [rax+29h], 1
0x180011d74  jmp     loc_180011C4F
0x180011d79  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x180011d81  mov     dword ptr [rsp+288h+var_260], 1
0x180011d89  mov     [rsp+288h+var_268], r9d
0x180011d8e  call    McTemplateU0qttt_EventWriteTransfer
0x180011d93  jmp     loc_180011CAF
0x180011d98  mov     r9d, 879h
0x180011d9e  lea     r8, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180011da5  lea     rdx, aIptlsupdateglo; "IpTlsUpdateGlobalUsableIpv6AddressCount"...
0x180011dac  mov     ecx, 10000000h
0x180011db1  call    EventWrite0
0x180011db6  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180011dbd  jz      loc_180011CAF
0x180011dc3  lea     r9, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180011dca  mov     [rsp+288h+var_268], 87Eh
0x180011dd2  xor     r8d, r8d
0x180011dd5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180011ddc  call    McTemplateU0psq_EventWriteTransfer
0x180011de1  jmp     loc_180011CAF
0x180011de6  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x180011dee  mov     dword ptr [rsp+288h+var_260], 1
0x180011df6  mov     [rsp+288h+var_268], r9d
0x180011dfb  call    McTemplateU0qttt_EventWriteTransfer
0x180011e00  jmp     loc_180011D01
0x180011e05  mov     ecx, 3
0x180011e0a  int     29h; Win8: RtlFailFast(ecx)
```
