# KpsDoHttpSendResponse(KpsIoLockedRef &,ushort,char *,char *)

- ea: `0x18001f390`
- end: `0x18001f5e3`
- name: `?KpsDoHttpSendResponse@@YAXAEAVKpsIoLockedRef@@GPEAD1@Z`
- size: `595`
- prototype: `void __fastcall(LPOVERLAPPED *this, __int64, char *, char *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800222f0`
- `0x180022708`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001f390`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026e48`
- `0x18002cc3c`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f454`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f454`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f4dc`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f4dc`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f570`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f570`
- `HTTPAPI!HttpSendHttpResponse` at `0x18001f4bc`
- `HTTPAPI!HttpSendHttpResponse` at `0x18001f4bc`

## string_xrefs

- `0x18001f4fd`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpSendResponse(LPOVERLAPPED *this, __int64 a2, char *a3, char *a4)
{
  ULONG v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8
  ULONG v8; // eax
  LPOVERLAPPED v9; // rbx
  __int64 v10; // [rsp+28h] [rbp-2A0h]
  HTTP_RESPONSE HttpResponse; // [rsp+70h] [rbp-258h] BYREF

  v5 = 0;
  memset_0(&HttpResponse, 0, sizeof(HttpResponse));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qds(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, *this);
  if ( !KpsServiceReady() )
    goto LABEL_20;
  *(_DWORD *)&HttpResponse.StatusCode = 1704339;
  HttpResponse.pReason = "blocked by KPSSVC policies";
  HttpResponse.Headers.KnownHeaders[12].pRawValue = "text/html";
  HttpResponse.Headers.KnownHeaders[12].RawValueLength = 9;
  LODWORD((*this)[1].Internal) = 3;
  StartThreadpoolIo(pio);
  if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
    __fastfail(0xEu);
  v8 = HttpSendHttpResponse(
         RequestQueueHandle,
         *((_QWORD *)(*this)[1].hEvent + 2),
         0,
         &HttpResponse,
         0,
         0,
         0,
         0,
         *this,
         0);
  v5 = v8;
  if ( v8 != 997 && v8 )
  {
    CancelThreadpoolIo(pio);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(v10) = 1056;
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        v5,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        v10);
    }
    KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
LABEL_20:
    if ( *this )
      KpsDoHttpCancelRequest((struct KpsIoLockedRef *)this);
    goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
  {
    v9 = *this;
    KpsStartTimeoutTimer((struct _KPS_IO *)*this);
    v9[10].Offset = 2;
  }
  if ( *this )
  {
    if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*this)[9]);
    *this = 0;
    goto LABEL_20;
  }
LABEL_22:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v5);
}

```

## disassembly

```asm
0x18001f390  mov     [rsp+arg_8], rbx
0x18001f395  mov     [rsp+arg_10], rsi
0x18001f39a  mov     [rsp+arg_18], rdi
0x18001f39f  push    r14
0x18001f3a1  sub     rsp, 2C0h
0x18001f3a8  mov     rax, cs:__security_cookie
0x18001f3af  xor     rax, rsp
0x18001f3b2  mov     [rsp+2C8h+var_18], rax
0x18001f3ba  mov     rdi, rcx
0x18001f3bd  xor     esi, esi
0x18001f3bf  lea     rcx, [rsp+2C8h+HttpResponse]; void *
0x18001f3c4  xor     edx, edx; Val
0x18001f3c6  mov     r8d, 238h; Size
0x18001f3cc  call    memset_0
0x18001f3d1  xorps   xmm0, xmm0
0x18001f3d4  movups  [rsp+2C8h+var_278], xmm0
0x18001f3d9  movups  [rsp+2C8h+var_268], xmm0
0x18001f3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3e5  lea     r14, WPP_GLOBAL_Control
0x18001f3ec  cmp     rcx, r14
0x18001f3ef  jz      short loc_18001F403
0x18001f3f1  test    byte ptr [rcx+1Ch], 20h
0x18001f3f5  jz      short loc_18001F403
0x18001f3f7  mov     r9, [rdi]
0x18001f3fa  mov     rcx, [rcx+10h]
0x18001f3fe  call    WPP_SF_qds
0x18001f403  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001f408  test    al, al
0x18001f40a  jz      loc_18001F580
0x18001f410  lea     rax, aBlockedByKpssv; "blocked by KPSSVC policies"
0x18001f417  mov     dword ptr [rsp+2C8h+HttpResponse.StatusCode], 1A0193h
0x18001f41f  mov     [rsp+2C8h+HttpResponse.pReason], rax
0x18001f427  lea     rax, aTextHtml; "text/html"
0x18001f42e  mov     [rsp+2C8h+HttpResponse.Headers.KnownHeaders.pRawValue+0C0h], rax
0x18001f436  mov     eax, 9
0x18001f43b  mov     [rsp+2C8h+HttpResponse.Headers.KnownHeaders.RawValueLength+0C0h], ax
0x18001f443  mov     rax, [rdi]
0x18001f446  mov     dword ptr [rax+20h], 3
0x18001f44d  mov     rcx, cs:pio; pio
0x18001f454  call    cs:__imp_StartThreadpoolIo
0x18001f45b  nop     dword ptr [rax+rax+00h]
0x18001f460  mov     rcx, [rdi]
0x18001f463  mov     ebx, 1
0x18001f468  test    rcx, rcx
0x18001f46b  jz      short loc_18001F485
0x18001f46d  mov     eax, ebx
0x18001f46f  lock xadd [rcx+158h], rax
0x18001f478  add     rax, rbx
0x18001f47b  cmp     rax, rbx
0x18001f47e  jg      short loc_18001F485
0x18001f480  lea     ecx, [rbx+0Dh]
0x18001f483  int     29h; Win8: RtlFailFast(ecx)
0x18001f485  and     [rsp+2C8h+var_280], rsi
0x18001f48a  lea     r9, [rsp+2C8h+HttpResponse]; HttpResponse
0x18001f48f  mov     rcx, [rdi]
0x18001f492  xor     r8d, r8d; Flags
0x18001f495  mov     [rsp+2C8h+Overlapped], rcx; Overlapped
0x18001f49a  and     [rsp+2C8h+var_290], esi
0x18001f49e  and     [rsp+2C8h+var_298], rsi
0x18001f4a3  mov     rax, [rcx+38h]
0x18001f4a7  and     [rsp+2C8h+var_2A0], rsi
0x18001f4ac  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001f4b3  and     [rsp+2C8h+var_2A8], rsi
0x18001f4b8  mov     rdx, [rax+10h]; RequestId
0x18001f4bc  call    cs:__imp_HttpSendHttpResponse
0x18001f4c3  nop     dword ptr [rax+rax+00h]
0x18001f4c8  mov     esi, eax
0x18001f4ca  cmp     eax, 3E5h
0x18001f4cf  jz      short loc_18001F52F
0x18001f4d1  test    eax, eax
0x18001f4d3  jz      short loc_18001F52F
0x18001f4d5  mov     rcx, cs:pio; pio
0x18001f4dc  call    cs:__imp_CancelThreadpoolIo
0x18001f4e3  nop     dword ptr [rax+rax+00h]
0x18001f4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ef  cmp     rcx, r14
0x18001f4f2  jz      short loc_18001F525
0x18001f4f4  test    [rcx+1Ch], bl
0x18001f4f7  jz      short loc_18001F525
0x18001f4f9  mov     rcx, [rcx+10h]
0x18001f4fd  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001f504  mov     edx, 2Ch ; ','
0x18001f509  mov     dword ptr [rsp+2C8h+var_2A0], 420h
0x18001f511  mov     r9d, esi
0x18001f514  mov     [rsp+2C8h+var_2A8], rax
0x18001f519  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f520  call    WPP_SF_Dsd
0x18001f525  mov     rcx, rdi; this
0x18001f528  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001f52d  jmp     short loc_18001F580
0x18001f52f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001f536  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001f53b  test    al, al
0x18001f53d  jz      short loc_18001F554
0x18001f53f  mov     rbx, [rdi]
0x18001f542  mov     rcx, rbx; struct _KPS_IO *
0x18001f545  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001f54a  mov     dword ptr [rbx+150h], 2
0x18001f554  cmp     qword ptr [rdi], 0
0x18001f558  jz      short loc_18001F58E
0x18001f55a  mov     rcx, rdi; this
0x18001f55d  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001f562  test    al, al
0x18001f564  jnz     short loc_18001F57C
0x18001f566  mov     rcx, [rdi]
0x18001f569  add     rcx, 120h; CriticalSection
0x18001f570  call    cs:__imp_RtlLeaveCriticalSection
0x18001f577  nop     dword ptr [rax+rax+00h]
0x18001f57c  and     qword ptr [rdi], 0
0x18001f580  cmp     qword ptr [rdi], 0
0x18001f584  jz      short loc_18001F58E
0x18001f586  mov     rcx, rdi; this
0x18001f589  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x18001f58e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f595  cmp     rcx, r14
0x18001f598  jz      short loc_18001F5B8
0x18001f59a  test    byte ptr [rcx+1Ch], 20h
0x18001f59e  jz      short loc_18001F5B8
0x18001f5a0  mov     rcx, [rcx+10h]
0x18001f5a4  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f5ab  mov     edx, 2Dh ; '-'
0x18001f5b0  mov     r9d, esi
0x18001f5b3  call    WPP_SF_D
0x18001f5b8  mov     rcx, [rsp+2C8h+var_18]
0x18001f5c0  xor     rcx, rsp; StackCookie
0x18001f5c3  call    __security_check_cookie
0x18001f5c8  lea     r11, [rsp+2C8h+var_8]
0x18001f5d0  mov     rbx, [r11+18h]
0x18001f5d4  mov     rsi, [r11+20h]
0x18001f5d8  mov     rdi, [r11+28h]
0x18001f5dc  mov     rsp, r11
0x18001f5df  pop     r14
0x18001f5e1  retn
```
