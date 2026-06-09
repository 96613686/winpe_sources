# KpsDoHttpReceiveRequestEntity(KpsIoLockedRef &)

- ea: `0x18001edec`
- end: `0x18001f042`
- name: `?KpsDoHttpReceiveRequestEntity@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `598`
- prototype: `void __fastcall(LPOVERLAPPED *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800208d8`
- `0x1800210f4`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001edec`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x1800300f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001eec9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001eec9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ef47`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ef47`
- `ntdll!RtlLeaveCriticalSection` at `0x18001efdc`
- `ntdll!RtlLeaveCriticalSection` at `0x18001efdc`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x18001ef27`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x18001ef27`

## string_xrefs

- `0x18001ee90`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001ef69`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpReceiveRequestEntity(LPOVERLAPPED *this)
{
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  ULONG v4; // eax
  LPOVERLAPPED v5; // rbx
  int v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+28h] [rbp-20h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_24;
  LODWORD((*this)[3].Internal) = 0;
  HIDWORD((*this)[3].Internal) = 3072;
  (*this)[2].hEvent = KpsAllocMem(HIDWORD((*this)[3].Internal));
  if ( (*this)[2].hEvent )
  {
    LODWORD((*this)[1].Internal) = 5;
    StartThreadpoolIo(pio);
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    v4 = HttpReceiveRequestEntityBody(
           RequestQueueHandle,
           *((_QWORD *)(*this)[1].hEvent + 2),
           0,
           (*this)[2].hEvent,
           HIDWORD((*this)[3].Internal),
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
        LODWORD(v7) = 1212;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
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
    v6 = 1191;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      8,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      v6);
LABEL_24:
    v3 = WPP_GLOBAL_Control;
  }
  if ( *this )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)this);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_D(v3[2], 53, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
}

```

## disassembly

```asm
0x18001edec  mov     [rsp+arg_0], rbx
0x18001edf1  mov     [rsp+arg_8], rsi
0x18001edf6  mov     [rsp+arg_10], rdi
0x18001edfb  push    r14
0x18001edfd  sub     rsp, 40h
0x18001ee01  mov     rdi, rcx
0x18001ee04  xor     esi, esi
0x18001ee06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee0d  lea     r14, WPP_GLOBAL_Control
0x18001ee14  cmp     rcx, r14
0x18001ee17  jz      short loc_18001EE35
0x18001ee19  test    byte ptr [rcx+1Ch], 20h
0x18001ee1d  jz      short loc_18001EE35
0x18001ee1f  mov     r9, [rdi]
0x18001ee22  lea     edx, [rsi+32h]
0x18001ee25  mov     rcx, [rcx+10h]
0x18001ee29  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001ee30  call    WPP_SF_q
0x18001ee35  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001ee3a  test    al, al
0x18001ee3c  jz      loc_18001EFEC
0x18001ee42  mov     rax, [rdi]
0x18001ee45  and     [rax+60h], esi
0x18001ee48  mov     rax, [rdi]
0x18001ee4b  mov     dword ptr [rax+64h], 0C00h
0x18001ee52  mov     rax, [rdi]
0x18001ee55  mov     ecx, [rax+64h]; unsigned __int64
0x18001ee58  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18001ee5d  mov     rcx, [rdi]
0x18001ee60  mov     [rcx+58h], rax
0x18001ee64  mov     rax, [rdi]
0x18001ee67  cmp     [rax+58h], rsi
0x18001ee6b  jnz     short loc_18001EEBB
0x18001ee6d  mov     esi, 8
0x18001ee72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee79  cmp     rcx, r14
0x18001ee7c  jz      loc_18001EFF3
0x18001ee82  test    byte ptr [rcx+1Ch], 1
0x18001ee86  jz      loc_18001EFF3
0x18001ee8c  mov     rcx, [rcx+10h]
0x18001ee90  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ee97  lea     edx, [rsi+2Bh]
0x18001ee9a  mov     dword ptr [rsp+48h+var_20], 4A7h
0x18001eea2  mov     r9d, esi
0x18001eea5  mov     qword ptr [rsp+48h+EntityBufferLength], rax
0x18001eeaa  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001eeb1  call    WPP_SF_Dsd
0x18001eeb6  jmp     loc_18001EFEC
0x18001eebb  mov     dword ptr [rax+20h], 5
0x18001eec2  mov     rcx, cs:pio; pio
0x18001eec9  call    cs:__imp_StartThreadpoolIo
0x18001eed0  nop     dword ptr [rax+rax+00h]
0x18001eed5  mov     rcx, [rdi]
0x18001eed8  test    rcx, rcx
0x18001eedb  jz      short loc_18001EEFB
0x18001eedd  mov     eax, 1
0x18001eee2  lock xadd [rcx+158h], rax
0x18001eeeb  inc     rax
0x18001eeee  cmp     rax, 1
0x18001eef2  jg      short loc_18001EEFB
0x18001eef4  mov     ecx, 0Eh
0x18001eef9  int     29h; Win8: RtlFailFast(ecx)
0x18001eefb  mov     r8, [rdi]
0x18001eefe  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001ef05  mov     [rsp+48h+Overlapped], r8; Overlapped
0x18001ef0a  and     [rsp+48h+var_20], rsi
0x18001ef0f  mov     rax, [r8+38h]
0x18001ef13  mov     r10d, [r8+64h]
0x18001ef17  mov     r9, [r8+58h]; EntityBuffer
0x18001ef1b  xor     r8d, r8d; Flags
0x18001ef1e  mov     [rsp+48h+EntityBufferLength], r10d; EntityBufferLength
0x18001ef23  mov     rdx, [rax+10h]; RequestId
0x18001ef27  call    cs:__imp_HttpReceiveRequestEntityBody
0x18001ef2e  nop     dword ptr [rax+rax+00h]
0x18001ef33  mov     esi, eax
0x18001ef35  cmp     eax, 3E5h
0x18001ef3a  jz      short loc_18001EF9B
0x18001ef3c  test    eax, eax
0x18001ef3e  jz      short loc_18001EF9B
0x18001ef40  mov     rcx, cs:pio; pio
0x18001ef47  call    cs:__imp_CancelThreadpoolIo
0x18001ef4e  nop     dword ptr [rax+rax+00h]
0x18001ef53  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef5a  cmp     rcx, r14
0x18001ef5d  jz      short loc_18001EF91
0x18001ef5f  test    byte ptr [rcx+1Ch], 1
0x18001ef63  jz      short loc_18001EF91
0x18001ef65  mov     rcx, [rcx+10h]
0x18001ef69  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ef70  mov     edx, 34h ; '4'
0x18001ef75  mov     dword ptr [rsp+48h+var_20], 4BCh
0x18001ef7d  mov     r9d, esi
0x18001ef80  mov     qword ptr [rsp+48h+EntityBufferLength], rax
0x18001ef85  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001ef8c  call    WPP_SF_Dsd
0x18001ef91  mov     rcx, rdi; this
0x18001ef94  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ef99  jmp     short loc_18001EFEC
0x18001ef9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001efa2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001efa7  test    al, al
0x18001efa9  jz      short loc_18001EFC0
0x18001efab  mov     rbx, [rdi]
0x18001efae  mov     rcx, rbx; struct _KPS_IO *
0x18001efb1  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001efb6  mov     dword ptr [rbx+150h], 2
0x18001efc0  cmp     qword ptr [rdi], 0
0x18001efc4  jz      short loc_18001EFEC
0x18001efc6  mov     rcx, rdi; this
0x18001efc9  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001efce  test    al, al
0x18001efd0  jnz     short loc_18001EFE8
0x18001efd2  mov     rcx, [rdi]
0x18001efd5  add     rcx, 120h; CriticalSection
0x18001efdc  call    cs:__imp_RtlLeaveCriticalSection
0x18001efe3  nop     dword ptr [rax+rax+00h]
0x18001efe8  and     qword ptr [rdi], 0
0x18001efec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eff3  cmp     qword ptr [rdi], 0
0x18001eff7  jz      short loc_18001F008
0x18001eff9  mov     rcx, rdi; this
0x18001effc  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x18001f001  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f008  cmp     rcx, r14
0x18001f00b  jz      short loc_18001F02B
0x18001f00d  test    byte ptr [rcx+1Ch], 20h
0x18001f011  jz      short loc_18001F02B
0x18001f013  mov     rcx, [rcx+10h]
0x18001f017  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f01e  mov     edx, 35h ; '5'
0x18001f023  mov     r9d, esi
0x18001f026  call    WPP_SF_D
0x18001f02b  mov     rbx, [rsp+48h+arg_0]
0x18001f030  mov     rsi, [rsp+48h+arg_8]
0x18001f035  mov     rdi, [rsp+48h+arg_10]
0x18001f03a  add     rsp, 40h
0x18001f03e  pop     r14
0x18001f040  retn
```
