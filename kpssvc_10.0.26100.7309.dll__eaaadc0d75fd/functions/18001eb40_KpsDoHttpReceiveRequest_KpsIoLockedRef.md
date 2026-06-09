# KpsDoHttpReceiveRequest(KpsIoLockedRef &)

- ea: `0x18001eb40`
- end: `0x18001ede5`
- name: `?KpsDoHttpReceiveRequest@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `677`
- prototype: `void __fastcall(LPOVERLAPPED *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800210f4`
- `0x180021b10`

## callees

- `0x18001ada8`
- `0x18001ae38`
- `0x18001eb40`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x1800300f4`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ec2c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ec2c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ecaa`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001ecaa`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ed86`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ed86`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18001ec82`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18001ec82`

## string_xrefs

- `0x18001ebf3`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001ed0c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpReceiveRequest(LPOVERLAPPED *this)
{
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  ULONG v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  LPOVERLAPPED v7; // rbx
  int v8; // [rsp+28h] [rbp-50h]
  __int64 v9; // [rsp+28h] [rbp-50h]
  unsigned int v10; // [rsp+40h] [rbp-38h] BYREF
  char v11[16]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int *v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+60h] [rbp-18h]
  int v14; // [rsp+64h] [rbp-14h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_22;
  LODWORD((*this)[2].Internal) = 0;
  HIDWORD((*this)[2].Internal) = 2048;
  (*this)[1].hEvent = KpsAllocMem(HIDWORD((*this)[2].Internal));
  if ( (*this)[1].hEvent )
  {
    LODWORD((*this)[1].Internal) = 1;
    StartThreadpoolIo(pio);
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    v4 = HttpReceiveHttpRequest(
           RequestQueueHandle,
           0,
           0,
           (PHTTP_REQUEST)(*this)[1].hEvent,
           HIDWORD((*this)[2].Internal),
           0,
           *this);
    v2 = v4;
    if ( v4 == 997 || !v4 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
      {
        v7 = *this;
        KpsStartTimeoutTimer((struct _KPS_IO *)*this);
        v7[10].Offset = 2;
      }
    }
    else
    {
      CancelThreadpoolIo(pio);
      if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
      {
        v14 = 0;
        v12 = &v10;
        v10 = v2;
        v13 = 4;
        McGenEventWrite_EventWriteTransfer(v5, HttpReceiveHttpRequestFailure, v6, 2, v11);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(v9) = 1682;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v2,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          v9);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
    }
    goto LABEL_22;
  }
  v2 = 8;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 1660;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      77,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      8,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      v8);
LABEL_22:
    v3 = WPP_GLOBAL_Control;
  }
  if ( *this )
  {
    if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*this)[9]);
    *this = 0;
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_D(v3[2], 79, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
}

```

## disassembly

```asm
0x18001eb40  mov     [rsp+arg_8], rbx
0x18001eb45  mov     [rsp+arg_10], rsi
0x18001eb4a  mov     [rsp+arg_18], rdi
0x18001eb4f  push    r14
0x18001eb51  sub     rsp, 70h
0x18001eb55  mov     rax, cs:__security_cookie
0x18001eb5c  xor     rax, rsp
0x18001eb5f  mov     [rsp+78h+var_10], rax
0x18001eb64  mov     rdi, rcx
0x18001eb67  xor     esi, esi
0x18001eb69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb70  lea     r14, WPP_GLOBAL_Control
0x18001eb77  cmp     rcx, r14
0x18001eb7a  jz      short loc_18001EB98
0x18001eb7c  test    byte ptr [rcx+1Ch], 20h
0x18001eb80  jz      short loc_18001EB98
0x18001eb82  mov     r9, [rdi]
0x18001eb85  lea     edx, [rsi+4Ch]
0x18001eb88  mov     rcx, [rcx+10h]
0x18001eb8c  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001eb93  call    WPP_SF_q
0x18001eb98  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001eb9d  test    al, al
0x18001eb9f  jz      loc_18001ED63
0x18001eba5  mov     rax, [rdi]
0x18001eba8  and     [rax+40h], esi
0x18001ebab  mov     rax, [rdi]
0x18001ebae  mov     dword ptr [rax+44h], 800h
0x18001ebb5  mov     rax, [rdi]
0x18001ebb8  mov     ecx, [rax+44h]; unsigned __int64
0x18001ebbb  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18001ebc0  mov     rcx, [rdi]
0x18001ebc3  mov     [rcx+38h], rax
0x18001ebc7  mov     rax, [rdi]
0x18001ebca  cmp     [rax+38h], rsi
0x18001ebce  jnz     short loc_18001EC1E
0x18001ebd0  mov     esi, 8
0x18001ebd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebdc  cmp     rcx, r14
0x18001ebdf  jz      loc_18001ED6A
0x18001ebe5  test    byte ptr [rcx+1Ch], 1
0x18001ebe9  jz      loc_18001ED6A
0x18001ebef  mov     rcx, [rcx+10h]
0x18001ebf3  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ebfa  lea     edx, [rsi+45h]
0x18001ebfd  mov     dword ptr [rsp+78h+var_50], 67Ch
0x18001ec05  mov     r9d, esi
0x18001ec08  mov     qword ptr [rsp+78h+RequestBufferLength], rax
0x18001ec0d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001ec14  call    WPP_SF_Dsd
0x18001ec19  jmp     loc_18001ED63
0x18001ec1e  mov     dword ptr [rax+20h], 1
0x18001ec25  mov     rcx, cs:pio; pio
0x18001ec2c  call    cs:__imp_StartThreadpoolIo
0x18001ec33  nop     dword ptr [rax+rax+00h]
0x18001ec38  mov     rcx, [rdi]
0x18001ec3b  test    rcx, rcx
0x18001ec3e  jz      short loc_18001EC5E
0x18001ec40  mov     eax, 1
0x18001ec45  lock xadd [rcx+158h], rax
0x18001ec4e  inc     rax
0x18001ec51  cmp     rax, 1
0x18001ec55  jg      short loc_18001EC5E
0x18001ec57  mov     ecx, 0Eh
0x18001ec5c  int     29h; Win8: RtlFailFast(ecx)
0x18001ec5e  mov     rax, [rdi]
0x18001ec61  xor     r8d, r8d; Flags
0x18001ec64  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001ec6b  mov     [rsp+78h+Overlapped], rax; Overlapped
0x18001ec70  and     [rsp+78h+var_50], rsi
0x18001ec75  mov     edx, [rax+44h]
0x18001ec78  mov     r9, [rax+38h]; RequestBuffer
0x18001ec7c  mov     [rsp+78h+RequestBufferLength], edx; RequestBufferLength
0x18001ec80  xor     edx, edx; RequestId
0x18001ec82  call    cs:__imp_HttpReceiveHttpRequest
0x18001ec89  nop     dword ptr [rax+rax+00h]
0x18001ec8e  mov     esi, eax
0x18001ec90  cmp     eax, 3E5h
0x18001ec95  jz      loc_18001ED3E
0x18001ec9b  test    eax, eax
0x18001ec9d  jz      loc_18001ED3E
0x18001eca3  mov     rcx, cs:pio; pio
0x18001ecaa  call    cs:__imp_CancelThreadpoolIo
0x18001ecb1  nop     dword ptr [rax+rax+00h]
0x18001ecb6  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18001ecbd  jz      short loc_18001ECF6
0x18001ecbf  and     [rsp+78h+var_14], 0
0x18001ecc4  lea     rax, [rsp+78h+var_38]
0x18001ecc9  mov     [rsp+78h+var_20], rax
0x18001ecce  lea     rdx, HttpReceiveHttpRequestFailure
0x18001ecd5  lea     rax, [rsp+78h+var_30]
0x18001ecda  mov     [rsp+78h+var_38], esi
0x18001ecde  mov     r9d, 2
0x18001ece4  mov     qword ptr [rsp+78h+RequestBufferLength], rax
0x18001ece9  mov     [rsp+78h+var_18], 4
0x18001ecf1  call    McGenEventWrite_EventWriteTransfer
0x18001ecf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecfd  cmp     rcx, r14
0x18001ed00  jz      short loc_18001ED34
0x18001ed02  test    byte ptr [rcx+1Ch], 1
0x18001ed06  jz      short loc_18001ED34
0x18001ed08  mov     rcx, [rcx+10h]
0x18001ed0c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ed13  mov     edx, 4Eh ; 'N'
0x18001ed18  mov     dword ptr [rsp+78h+var_50], 692h
0x18001ed20  mov     r9d, esi
0x18001ed23  mov     qword ptr [rsp+78h+RequestBufferLength], rax
0x18001ed28  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001ed2f  call    WPP_SF_Dsd
0x18001ed34  mov     rcx, rdi; this
0x18001ed37  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ed3c  jmp     short loc_18001ED63
0x18001ed3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001ed45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001ed4a  test    al, al
0x18001ed4c  jz      short loc_18001ED63
0x18001ed4e  mov     rbx, [rdi]
0x18001ed51  mov     rcx, rbx; struct _KPS_IO *
0x18001ed54  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001ed59  mov     dword ptr [rbx+150h], 2
0x18001ed63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed6a  cmp     qword ptr [rdi], 0
0x18001ed6e  jz      short loc_18001ED9D
0x18001ed70  mov     rcx, rdi; this
0x18001ed73  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ed78  test    al, al
0x18001ed7a  jnz     short loc_18001ED92
0x18001ed7c  mov     rcx, [rdi]
0x18001ed7f  add     rcx, 120h; CriticalSection
0x18001ed86  call    cs:__imp_RtlLeaveCriticalSection
0x18001ed8d  nop     dword ptr [rax+rax+00h]
0x18001ed92  and     qword ptr [rdi], 0
0x18001ed96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed9d  cmp     rcx, r14
0x18001eda0  jz      short loc_18001EDC0
0x18001eda2  test    byte ptr [rcx+1Ch], 20h
0x18001eda6  jz      short loc_18001EDC0
0x18001eda8  mov     rcx, [rcx+10h]
0x18001edac  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001edb3  mov     edx, 4Fh ; 'O'
0x18001edb8  mov     r9d, esi
0x18001edbb  call    WPP_SF_D
0x18001edc0  mov     rcx, [rsp+78h+var_10]
0x18001edc5  xor     rcx, rsp; StackCookie
0x18001edc8  call    __security_check_cookie
0x18001edcd  lea     r11, [rsp+78h+var_8]
0x18001edd2  mov     rbx, [r11+18h]
0x18001edd6  mov     rsi, [r11+20h]
0x18001edda  mov     rdi, [r11+28h]
0x18001edde  mov     rsp, r11
0x18001ede1  pop     r14
0x18001ede3  retn
```
