# Dns64RequestNAorPtrIssue

- ea: `0x18006ceb0`
- end: `0x18006d086`
- name: `Dns64RequestNAorPtrIssue`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006bdcc`

## callees

- `0x180012dcc`
- `0x180045d64`
- `0x1800616b4`
- `0x18006999c`
- `0x18006cde0`
- `0x18006ceb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cffa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d021`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d06f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d021`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d06f`
- `DNSAPI!DnsWriteReverseNameStringForIpAddressW` at `0x18006cf6d`
- `DNSAPI!DnsWriteReverseNameStringForIpAddressW` at `0x18006cf6d`
- `DNSAPI!DnsQueryEx` at `0x18006cfae`
- `DNSAPI!DnsQueryEx` at `0x18006cfae`

## string_xrefs

- `0x18006cecd`: `onecoreuap\net\netio\iphlpsvc\service\dns64req.c`
- `0x18006d036`: `onecoreuap\net\netio\iphlpsvc\service\dns64req.c`

## pseudocode

```c
void __fastcall Dns64RequestNAorPtrIssue(__int64 a1)
{
  int v2; // edx
  __int16 v3; // cx
  __int64 v4; // rax
  DNS_STATUS v5; // eax
  int v6; // ecx
  DNS_STATUS v7; // esi
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  int v9; // ecx

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 204));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      a1,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      a1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64req.c",
      6);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 736));
  v2 = *(_DWORD *)(**(_QWORD **)(a1 + 744) + 56LL);
  v3 = *(_WORD *)(a1 + 92);
  *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 576) = Dns64RequestNAComplete;
  *(_DWORD *)(a1 + 528) = 1;
  *(_WORD *)(a1 + 544) = v3;
  *(_QWORD *)(a1 + 552) = 71712;
  *(_DWORD *)(a1 + 568) = v2;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 584) = a1;
  if ( *(_DWORD *)(a1 + 624) )
  {
    ++g_Dns64AAAAMatchedIn6ArpaPtr;
    v4 = MALLOC(0x3Eu);
    *(_QWORD *)(a1 + 632) = v4;
    if ( v4 )
    {
      DnsWriteReverseNameStringForIpAddressW(v4, *(unsigned int *)(a1 + 628));
      *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 632);
    }
    else
    {
      *(_DWORD *)(a1 + 624) = 0;
    }
  }
  *(_DWORD *)(a1 + 592) = 1;
  v5 = DnsQueryEx((PDNS_QUERY_REQUEST)(a1 + 528), (PDNS_QUERY_RESULT)(a1 + 592), (PDNS_QUERY_CANCEL)(a1 + 496));
  v7 = v5;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0pzq_EventWriteTransfer(
      v6,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_FORWARD_ISSUE,
      a1,
      (unsigned int)&word_180087660,
      v5);
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
    if ( v7 == 9506 )
    {
      *(_DWORD *)(a1 + 480) = 1;
      LeaveCriticalSection(v8);
    }
    else
    {
      *(_DWORD *)(a1 + 596) = v7;
      *(_DWORD *)(a1 + 488) = 1;
      LeaveCriticalSection(v8);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v9,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          a1,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64req.c",
          58);
      Dns64RequestDereferenceEx(a1);
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 204));
    }
  }
  else
  {
    Dns64RequestNAComplete(a1, a1 + 592);
  }
}

```

## disassembly

```asm
0x18006ceb0  push    rbx
0x18006ceb2  push    rsi
0x18006ceb3  push    rdi
0x18006ceb4  push    r14
0x18006ceb6  sub     rsp, 38h
0x18006ceba  mov     rbx, rcx
0x18006cebd  lock inc dword ptr [rcx+0CCh]
0x18006cec4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006cecb  jz      short loc_18006CEEB
0x18006cecd  lea     r9, aOnecoreuapNetN_25; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ced4  mov     [rsp+58h+var_38], 306h
0x18006cedc  mov     r8, rcx
0x18006cedf  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006cee6  call    McTemplateU0psq_EventWriteTransfer
0x18006ceeb  lock inc dword ptr [rbx+2E0h]
0x18006cef2  mov     rax, [rbx+2E8h]
0x18006cef9  lea     rdi, [rbx+210h]
0x18006cf00  mov     rcx, [rax]
0x18006cf03  mov     rax, [rbx+60h]
0x18006cf07  mov     edx, [rcx+38h]
0x18006cf0a  movzx   ecx, word ptr [rbx+5Ch]
0x18006cf0e  mov     [rdi+8], rax
0x18006cf12  lea     rax, Dns64RequestNAComplete
0x18006cf19  mov     [rdi+30h], rax
0x18006cf1d  mov     dword ptr [rdi], 1
0x18006cf23  mov     [rdi+10h], cx
0x18006cf27  mov     qword ptr [rdi+18h], 11820h
0x18006cf2f  mov     [rdi+28h], edx
0x18006cf32  mov     qword ptr [rdi+20h], 0
0x18006cf3a  mov     [rdi+38h], rbx
0x18006cf3e  cmp     dword ptr [rbx+270h], 0
0x18006cf45  jz      short loc_18006CF93
0x18006cf47  inc     cs:g_Dns64AAAAMatchedIn6ArpaPtr
0x18006cf4e  mov     ecx, 3Eh ; '>'; dwBytes
0x18006cf53  call    MALLOC
0x18006cf58  mov     [rbx+278h], rax
0x18006cf5f  test    rax, rax
0x18006cf62  jz      short loc_18006CF89
0x18006cf64  mov     edx, [rbx+274h]
0x18006cf6a  mov     rcx, rax
0x18006cf6d  call    cs:__imp_DnsWriteReverseNameStringForIpAddressW
0x18006cf74  nop     dword ptr [rax+rax+00h]
0x18006cf79  mov     rax, [rbx+278h]
0x18006cf80  mov     [rbx+218h], rax
0x18006cf87  jmp     short loc_18006CF93
0x18006cf89  mov     dword ptr [rbx+270h], 0
0x18006cf93  lea     r14, [rbx+250h]
0x18006cf9a  mov     rcx, rdi; pQueryRequest
0x18006cf9d  mov     rdx, r14; pQueryResults
0x18006cfa0  mov     dword ptr [r14], 1
0x18006cfa7  lea     r8, [rbx+1F0h]; pCancelHandle
0x18006cfae  call    cs:__imp_DnsQueryEx
0x18006cfb5  nop     dword ptr [rax+rax+00h]
0x18006cfba  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006cfc1  mov     esi, eax
0x18006cfc3  jz      short loc_18006CFDF
0x18006cfc5  lea     r9, word_180087660
0x18006cfcc  mov     [rsp+58h+var_38], eax
0x18006cfd0  mov     r8, rbx
0x18006cfd3  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_FORWARD_ISSUE
0x18006cfda  call    McTemplateU0pzq_EventWriteTransfer
0x18006cfdf  test    esi, esi
0x18006cfe1  jnz     short loc_18006CFF3
0x18006cfe3  mov     rdx, r14
0x18006cfe6  mov     rcx, rbx
0x18006cfe9  call    Dns64RequestNAComplete
0x18006cfee  jmp     loc_18006D07B
0x18006cff3  lea     rdi, [rbx+18h]
0x18006cff7  mov     rcx, rdi; lpCriticalSection
0x18006cffa  call    cs:__imp_EnterCriticalSection
0x18006d001  nop     dword ptr [rax+rax+00h]
0x18006d006  mov     rcx, rdi; lpCriticalSection
0x18006d009  cmp     esi, 2522h
0x18006d00f  jz      short loc_18006D065
0x18006d011  mov     [rbx+254h], esi
0x18006d017  mov     dword ptr [rbx+1E8h], 1
0x18006d021  call    cs:__imp_LeaveCriticalSection
0x18006d028  nop     dword ptr [rax+rax+00h]
0x18006d02d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006d034  jz      short loc_18006D054
0x18006d036  lea     r9, aOnecoreuapNetN_25; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006d03d  mov     [rsp+58h+var_38], 33Ah
0x18006d045  mov     r8, rbx
0x18006d048  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006d04f  call    McTemplateU0psq_EventWriteTransfer
0x18006d054  mov     rcx, rbx
0x18006d057  call    Dns64RequestDereferenceEx
0x18006d05c  lock dec dword ptr [rbx+0CCh]
0x18006d063  jmp     short loc_18006D07B
0x18006d065  mov     dword ptr [rbx+1E0h], 1
0x18006d06f  call    cs:__imp_LeaveCriticalSection
0x18006d076  nop     dword ptr [rax+rax+00h]
0x18006d07b  add     rsp, 38h
0x18006d07f  pop     r14
0x18006d081  pop     rdi
0x18006d082  pop     rsi
0x18006d083  pop     rbx
0x18006d084  retn
```
