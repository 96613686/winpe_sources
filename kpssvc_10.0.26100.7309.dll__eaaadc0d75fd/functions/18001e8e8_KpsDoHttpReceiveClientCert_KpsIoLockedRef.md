# KpsDoHttpReceiveClientCert(KpsIoLockedRef &)

- ea: `0x18001e8e8`
- end: `0x18001eb38`
- name: `?KpsDoHttpReceiveClientCert@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `592`
- prototype: `void __fastcall(LPOVERLAPPED *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800210f4`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001e8e8`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x1800300f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001e9bf`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001e9bf`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ea3d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ea3d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ead2`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ead2`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x18001ea1d`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x18001ea1d`

## string_xrefs

- `0x18001e986`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001ea5f`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpReceiveClientCert(LPOVERLAPPED *this)
{
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  ULONG v4; // eax
  LPOVERLAPPED v5; // rbx
  int v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+28h] [rbp-20h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_24;
  (*this)[2].Offset = 2048;
  (*this)[2].InternalHigh = (ULONG_PTR)KpsAllocMem((*this)[2].Offset);
  if ( (*this)[2].InternalHigh )
  {
    LODWORD((*this)[1].Internal) = 2;
    StartThreadpoolIo(pio);
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    v4 = HttpReceiveClientCertificate(
           RequestQueueHandle,
           *((_QWORD *)(*this)[1].hEvent + 1),
           0,
           (PHTTP_SSL_CLIENT_CERT_INFO)(*this)[2].InternalHigh,
           (*this)[2].Offset,
           0,
           *this);
    v2 = v4;
    if ( v4 == 997 || !v4 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
      {
        v5 = *this;
        KpsStartTimeoutTimer((struct _KPS_IO *)*this);
        v5[10].Offset = 2;
      }
      if ( *this )
      {
        if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*this)[9]);
        *this = 0;
      }
    }
    else
    {
      CancelThreadpoolIo(pio);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(v7) = 972;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v2,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          v7);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
    }
    goto LABEL_24;
  }
  v2 = 8;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 951;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      8,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      v6);
LABEL_24:
    v3 = WPP_GLOBAL_Control;
  }
  if ( *this )
  {
    KpsDoHttpCancelRequest(this);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_D(v3[2], 42, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
}

```

## disassembly

```asm
0x18001e8e8  mov     [rsp+arg_0], rbx
0x18001e8ed  mov     [rsp+arg_8], rsi
0x18001e8f2  mov     [rsp+arg_10], rdi
0x18001e8f7  push    r14
0x18001e8f9  sub     rsp, 40h
0x18001e8fd  mov     rdi, rcx
0x18001e900  xor     esi, esi
0x18001e902  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e909  lea     r14, WPP_GLOBAL_Control
0x18001e910  cmp     rcx, r14
0x18001e913  jz      short loc_18001E931
0x18001e915  test    byte ptr [rcx+1Ch], 20h
0x18001e919  jz      short loc_18001E931
0x18001e91b  mov     r9, [rdi]
0x18001e91e  lea     edx, [rsi+27h]
0x18001e921  mov     rcx, [rcx+10h]
0x18001e925  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e92c  call    WPP_SF_q
0x18001e931  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001e936  test    al, al
0x18001e938  jz      loc_18001EAE2
0x18001e93e  mov     rax, [rdi]
0x18001e941  mov     dword ptr [rax+50h], 800h
0x18001e948  mov     rax, [rdi]
0x18001e94b  mov     ecx, [rax+50h]; unsigned __int64
0x18001e94e  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18001e953  mov     rcx, [rdi]
0x18001e956  mov     [rcx+48h], rax
0x18001e95a  mov     rax, [rdi]
0x18001e95d  cmp     [rax+48h], rsi
0x18001e961  jnz     short loc_18001E9B1
0x18001e963  mov     esi, 8
0x18001e968  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e96f  cmp     rcx, r14
0x18001e972  jz      loc_18001EAE9
0x18001e978  test    byte ptr [rcx+1Ch], 1
0x18001e97c  jz      loc_18001EAE9
0x18001e982  mov     rcx, [rcx+10h]
0x18001e986  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001e98d  lea     edx, [rsi+20h]
0x18001e990  mov     dword ptr [rsp+48h+var_20], 3B7h
0x18001e998  mov     r9d, esi
0x18001e99b  mov     qword ptr [rsp+48h+SslClientCertInfoSize], rax
0x18001e9a0  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e9a7  call    WPP_SF_Dsd
0x18001e9ac  jmp     loc_18001EAE2
0x18001e9b1  mov     dword ptr [rax+20h], 2
0x18001e9b8  mov     rcx, cs:pio; pio
0x18001e9bf  call    cs:__imp_StartThreadpoolIo
0x18001e9c6  nop     dword ptr [rax+rax+00h]
0x18001e9cb  mov     rcx, [rdi]
0x18001e9ce  test    rcx, rcx
0x18001e9d1  jz      short loc_18001E9F1
0x18001e9d3  mov     eax, 1
0x18001e9d8  lock xadd [rcx+158h], rax
0x18001e9e1  inc     rax
0x18001e9e4  cmp     rax, 1
0x18001e9e8  jg      short loc_18001E9F1
0x18001e9ea  mov     ecx, 0Eh
0x18001e9ef  int     29h; Win8: RtlFailFast(ecx)
0x18001e9f1  mov     r8, [rdi]
0x18001e9f4  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001e9fb  mov     [rsp+48h+Overlapped], r8; Overlapped
0x18001ea00  and     [rsp+48h+var_20], rsi
0x18001ea05  mov     rax, [r8+38h]
0x18001ea09  mov     r10d, [r8+50h]
0x18001ea0d  mov     r9, [r8+48h]; SslClientCertInfo
0x18001ea11  xor     r8d, r8d; Flags
0x18001ea14  mov     [rsp+48h+SslClientCertInfoSize], r10d; SslClientCertInfoSize
0x18001ea19  mov     rdx, [rax+8]; ConnectionId
0x18001ea1d  call    cs:__imp_HttpReceiveClientCertificate
0x18001ea24  nop     dword ptr [rax+rax+00h]
0x18001ea29  mov     esi, eax
0x18001ea2b  cmp     eax, 3E5h
0x18001ea30  jz      short loc_18001EA91
0x18001ea32  test    eax, eax
0x18001ea34  jz      short loc_18001EA91
0x18001ea36  mov     rcx, cs:pio; pio
0x18001ea3d  call    cs:__imp_CancelThreadpoolIo
0x18001ea44  nop     dword ptr [rax+rax+00h]
0x18001ea49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea50  cmp     rcx, r14
0x18001ea53  jz      short loc_18001EA87
0x18001ea55  test    byte ptr [rcx+1Ch], 1
0x18001ea59  jz      short loc_18001EA87
0x18001ea5b  mov     rcx, [rcx+10h]
0x18001ea5f  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ea66  mov     edx, 29h ; ')'
0x18001ea6b  mov     dword ptr [rsp+48h+var_20], 3CCh
0x18001ea73  mov     r9d, esi
0x18001ea76  mov     qword ptr [rsp+48h+SslClientCertInfoSize], rax
0x18001ea7b  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001ea82  call    WPP_SF_Dsd
0x18001ea87  mov     rcx, rdi; this
0x18001ea8a  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ea8f  jmp     short loc_18001EAE2
0x18001ea91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001ea98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001ea9d  test    al, al
0x18001ea9f  jz      short loc_18001EAB6
0x18001eaa1  mov     rbx, [rdi]
0x18001eaa4  mov     rcx, rbx; struct _KPS_IO *
0x18001eaa7  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001eaac  mov     dword ptr [rbx+150h], 2
0x18001eab6  cmp     qword ptr [rdi], 0
0x18001eaba  jz      short loc_18001EAE2
0x18001eabc  mov     rcx, rdi; this
0x18001eabf  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001eac4  test    al, al
0x18001eac6  jnz     short loc_18001EADE
0x18001eac8  mov     rcx, [rdi]
0x18001eacb  add     rcx, 120h; CriticalSection
0x18001ead2  call    cs:__imp_RtlLeaveCriticalSection
0x18001ead9  nop     dword ptr [rax+rax+00h]
0x18001eade  and     qword ptr [rdi], 0
0x18001eae2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eae9  cmp     qword ptr [rdi], 0
0x18001eaed  jz      short loc_18001EAFE
0x18001eaef  mov     rcx, rdi; this
0x18001eaf2  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x18001eaf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eafe  cmp     rcx, r14
0x18001eb01  jz      short loc_18001EB21
0x18001eb03  test    byte ptr [rcx+1Ch], 20h
0x18001eb07  jz      short loc_18001EB21
0x18001eb09  mov     rcx, [rcx+10h]
0x18001eb0d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001eb14  mov     edx, 2Ah ; '*'
0x18001eb19  mov     r9d, esi
0x18001eb1c  call    WPP_SF_D
0x18001eb21  mov     rbx, [rsp+48h+arg_0]
0x18001eb26  mov     rsi, [rsp+48h+arg_8]
0x18001eb2b  mov     rdi, [rsp+48h+arg_10]
0x18001eb30  add     rsp, 40h
0x18001eb34  pop     r14
0x18001eb36  retn
```
