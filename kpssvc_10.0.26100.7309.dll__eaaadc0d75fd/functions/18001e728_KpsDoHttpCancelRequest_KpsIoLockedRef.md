# KpsDoHttpCancelRequest(KpsIoLockedRef &)

- ea: `0x18001e728`
- end: `0x18001e8df`
- name: `?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `439`
- prototype: `void __fastcall(LPOVERLAPPED *this)`
- caller_count: `15`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e8e8`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x1800202d0`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800222f0`
- `0x1800223fc`
- `0x180022708`
- `0x180022a5c`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x18002fe08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001e798`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001e798`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e7fb`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e7fb`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e88f`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e88f`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18001e7db`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18001e7db`

## string_xrefs

- `0x18001e81c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpCancelRequest(LPOVERLAPPED *this)
{
  ULONG v2; // esi
  ULONG v3; // eax
  LPOVERLAPPED v4; // rbx
  int v5; // [rsp+28h] [rbp-10h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  KpsPerfUpdate(4u);
  LODWORD((*this)[1].Internal) = 7;
  if ( KpsServiceReady() )
  {
    StartThreadpoolIo(pio);
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    v3 = HttpCancelHttpRequest(RequestQueueHandle, *((_QWORD *)(*this)[1].hEvent + 2), *this);
    v2 = v3;
    if ( v3 == 997 || !v3 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
      {
        v4 = *this;
        KpsStartTimeoutTimer((struct _KPS_IO *)*this);
        v4[10].Offset = 2;
      }
    }
    else
    {
      CancelThreadpoolIo(pio);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 1268;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v2,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          v5);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
    }
  }
  if ( *this )
  {
    if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*this)[9]);
    *this = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
}

```

## disassembly

```asm
0x18001e728  mov     [rsp+arg_0], rbx
0x18001e72d  mov     [rsp+arg_8], rbp
0x18001e732  mov     [rsp+arg_10], rsi
0x18001e737  push    rdi
0x18001e738  sub     rsp, 30h
0x18001e73c  mov     rdi, rcx
0x18001e73f  xor     esi, esi
0x18001e741  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e748  lea     rbp, WPP_GLOBAL_Control
0x18001e74f  cmp     rcx, rbp
0x18001e752  jz      short loc_18001E770
0x18001e754  test    byte ptr [rcx+1Ch], 20h
0x18001e758  jz      short loc_18001E770
0x18001e75a  mov     r9, [rdi]
0x18001e75d  lea     edx, [rsi+36h]
0x18001e760  mov     rcx, [rcx+10h]
0x18001e764  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e76b  call    WPP_SF_q
0x18001e770  mov     ecx, 4; unsigned int
0x18001e775  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x18001e77a  mov     rax, [rdi]
0x18001e77d  mov     dword ptr [rax+20h], 7
0x18001e784  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001e789  test    al, al
0x18001e78b  jz      loc_18001E873
0x18001e791  mov     rcx, cs:pio; pio
0x18001e798  call    cs:__imp_StartThreadpoolIo
0x18001e79f  nop     dword ptr [rax+rax+00h]
0x18001e7a4  mov     rcx, [rdi]
0x18001e7a7  mov     ebx, 1
0x18001e7ac  test    rcx, rcx
0x18001e7af  jz      short loc_18001E7C9
0x18001e7b1  mov     eax, ebx
0x18001e7b3  lock xadd [rcx+158h], rax
0x18001e7bc  add     rax, rbx
0x18001e7bf  cmp     rax, rbx
0x18001e7c2  jg      short loc_18001E7C9
0x18001e7c4  lea     ecx, [rbx+0Dh]
0x18001e7c7  int     29h; Win8: RtlFailFast(ecx)
0x18001e7c9  mov     r8, [rdi]; Overlapped
0x18001e7cc  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001e7d3  mov     rax, [r8+38h]
0x18001e7d7  mov     rdx, [rax+10h]; RequestId
0x18001e7db  call    cs:__imp_HttpCancelHttpRequest
0x18001e7e2  nop     dword ptr [rax+rax+00h]
0x18001e7e7  mov     esi, eax
0x18001e7e9  cmp     eax, 3E5h
0x18001e7ee  jz      short loc_18001E84E
0x18001e7f0  test    eax, eax
0x18001e7f2  jz      short loc_18001E84E
0x18001e7f4  mov     rcx, cs:pio; pio
0x18001e7fb  call    cs:__imp_CancelThreadpoolIo
0x18001e802  nop     dword ptr [rax+rax+00h]
0x18001e807  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e80e  cmp     rcx, rbp
0x18001e811  jz      short loc_18001E844
0x18001e813  test    [rcx+1Ch], bl
0x18001e816  jz      short loc_18001E844
0x18001e818  mov     rcx, [rcx+10h]
0x18001e81c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001e823  mov     edx, 37h ; '7'
0x18001e828  mov     [rsp+38h+var_10], 4F4h
0x18001e830  mov     r9d, esi
0x18001e833  mov     [rsp+38h+var_18], rax
0x18001e838  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e83f  call    WPP_SF_Dsd
0x18001e844  mov     rcx, rdi; this
0x18001e847  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001e84c  jmp     short loc_18001E873
0x18001e84e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001e855  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001e85a  test    al, al
0x18001e85c  jz      short loc_18001E873
0x18001e85e  mov     rbx, [rdi]
0x18001e861  mov     rcx, rbx; struct _KPS_IO *
0x18001e864  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001e869  mov     dword ptr [rbx+150h], 2
0x18001e873  cmp     qword ptr [rdi], 0
0x18001e877  jz      short loc_18001E89F
0x18001e879  mov     rcx, rdi; this
0x18001e87c  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001e881  test    al, al
0x18001e883  jnz     short loc_18001E89B
0x18001e885  mov     rcx, [rdi]
0x18001e888  add     rcx, 120h; CriticalSection
0x18001e88f  call    cs:__imp_RtlLeaveCriticalSection
0x18001e896  nop     dword ptr [rax+rax+00h]
0x18001e89b  and     qword ptr [rdi], 0
0x18001e89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8a6  cmp     rcx, rbp
0x18001e8a9  jz      short loc_18001E8C9
0x18001e8ab  test    byte ptr [rcx+1Ch], 20h
0x18001e8af  jz      short loc_18001E8C9
0x18001e8b1  mov     rcx, [rcx+10h]
0x18001e8b5  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e8bc  mov     edx, 38h ; '8'
0x18001e8c1  mov     r9d, esi
0x18001e8c4  call    WPP_SF_D
0x18001e8c9  mov     rbx, [rsp+38h+arg_0]
0x18001e8ce  mov     rbp, [rsp+38h+arg_8]
0x18001e8d3  mov     rsi, [rsp+38h+arg_10]
0x18001e8d8  add     rsp, 30h
0x18001e8dc  pop     rdi
0x18001e8dd  retn
```
