# KpsDoHttpSendPostResponse(KpsIoLockedRef &)

- ea: `0x18001f048`
- end: `0x18001f388`
- name: `?KpsDoHttpSendPostResponse@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `832`
- prototype: `void __fastcall(LPOVERLAPPED *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022708`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001f048`
- `0x180022d38`
- `0x180024be0`
- `0x1800255d0`
- `0x180026404`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f1f3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f1f3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f27b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f27b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f30c`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f30c`
- `HTTPAPI!HttpSendHttpResponse` at `0x18001f25b`
- `HTTPAPI!HttpSendHttpResponse` at `0x18001f25b`

## string_xrefs

- `0x18001f166`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001f29c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoHttpSendPostResponse(LPOVERLAPPED *this)
{
  int v2; // esi
  LPOVERLAPPED v3; // r9
  _QWORD *v4; // rcx
  __int64 v5; // rax
  LPOVERLAPPED v6; // rcx
  ULONG v7; // eax
  LPOVERLAPPED v8; // rbx
  int v9; // [rsp+30h] [rbp-D8h]
  __int64 v10; // [rsp+30h] [rbp-D8h]
  __int128 v11; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+68h] [rbp-A0h]
  HTTP_RESPONSE HttpResponse; // [rsp+78h] [rbp-90h] BYREF
  char v14[16]; // [rsp+2B8h] [rbp+1B0h] BYREF

  v2 = 0;
  strcpy(v14, "4294967295");
  memset_0(&HttpResponse, 0, sizeof(HttpResponse));
  v11 = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_26;
  v3 = *this;
  *(_DWORD *)&HttpResponse.StatusCode = 131272;
  HttpResponse.pReason = "OK";
  v2 = StringCchPrintfA(v14, 0xBu, "%lu", LODWORD(v3[8].hEvent));
  if ( v2 >= 0 )
  {
    HttpResponse.Headers.KnownHeaders[12].pRawValue = v14;
    v5 = -1;
    do
      ++v5;
    while ( v14[v5] );
    v6 = *this;
    HttpResponse.Headers.KnownHeaders[12].RawValueLength = v5;
    *((_QWORD *)&v11 + 1) = v6[8].Pointer;
    LODWORD(v12) = v6[8].hEvent;
    HttpResponse.pEntityChunks = (PHTTP_DATA_CHUNK)&v11;
    HttpResponse.EntityChunkCount = 1;
    LODWORD(v6[1].Internal) = 4;
    StartThreadpoolIo(pio);
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)&(*this)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    v7 = HttpSendHttpResponse(
           RequestQueueHandle,
           *((_QWORD *)(*this)[1].hEvent + 2),
           1u,
           &HttpResponse,
           0,
           0,
           0,
           0,
           *this,
           0);
    v2 = v7;
    if ( v7 == 997 || !v7 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
      {
        v8 = *this;
        KpsStartTimeoutTimer((struct _KPS_IO *)*this);
        v8[10].Offset = 2;
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
        LODWORD(v10) = 1143;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v2,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          v10);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
    }
    goto LABEL_26;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 1109;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      v2,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      v9);
LABEL_26:
    v4 = WPP_GLOBAL_Control;
  }
  if ( *this )
  {
    KpsDoHttpCancelRequest(this);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_D(v4[2], 49, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, (unsigned int)v2);
}

```

## disassembly

```asm
0x18001f048  mov     rax, rsp
0x18001f04b  mov     [rax+10h], rbx
0x18001f04f  mov     [rax+18h], rsi
0x18001f053  mov     [rax+20h], rdi
0x18001f057  push    rbp
0x18001f058  push    r12
0x18001f05a  push    r13
0x18001f05c  lea     rbp, [rax-1E8h]
0x18001f063  sub     rsp, 2D0h
0x18001f06a  mov     rax, cs:__security_cookie
0x18001f071  xor     rax, rsp
0x18001f074  mov     [rbp+1E0h+var_20], rax
0x18001f07b  movzx   eax, word ptr cs:a4294967295+8; "95"
0x18001f082  mov     rdi, rcx
0x18001f085  movsd   xmm0, qword ptr cs:a4294967295; "4294967295"
0x18001f08d  lea     rcx, [rsp+2E0h+HttpResponse]; void *
0x18001f092  mov     word ptr [rbp+1E0h+var_30+8], ax
0x18001f099  xor     esi, esi
0x18001f09b  mov     al, byte ptr cs:a4294967295+0Ah; ""
0x18001f0a1  xor     edx, edx; Val
0x18001f0a3  mov     r8d, 238h; Size
0x18001f0a9  mov     [rbp+1E0h+var_30+0Ah], al
0x18001f0af  movsd   qword ptr [rbp+1E0h+var_30], xmm0
0x18001f0b7  call    memset_0
0x18001f0bc  xorps   xmm0, xmm0
0x18001f0bf  movups  [rsp+2E0h+var_298+8], xmm0
0x18001f0c4  movups  xmmword ptr [rsp+2E0h+var_288+8], xmm0
0x18001f0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0d0  lea     r12, WPP_GLOBAL_Control
0x18001f0d7  cmp     rcx, r12
0x18001f0da  jz      short loc_18001F0F8
0x18001f0dc  test    byte ptr [rcx+1Ch], 20h
0x18001f0e0  jz      short loc_18001F0F8
0x18001f0e2  mov     r9, [rdi]
0x18001f0e5  lea     edx, [rsi+2Eh]
0x18001f0e8  mov     rcx, [rcx+10h]
0x18001f0ec  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f0f3  call    WPP_SF_q
0x18001f0f8  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001f0fd  test    al, al
0x18001f0ff  jz      loc_18001F31C
0x18001f105  mov     r9, [rdi]
0x18001f108  lea     rax, aOk; "OK"
0x18001f10f  mov     dword ptr [rsp+2E0h+HttpResponse.StatusCode], 200C8h
0x18001f117  lea     r8, aLu; "%lu"
0x18001f11e  mov     [rbp+1E0h+HttpResponse.pReason], rax
0x18001f122  lea     rcx, [rbp+1E0h+var_30]; char *
0x18001f129  mov     r13d, 2
0x18001f12f  mov     r9d, [r9+118h]
0x18001f136  lea     edx, [r13+9]; unsigned __int64
0x18001f13a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001f13f  mov     esi, eax
0x18001f141  test    eax, eax
0x18001f143  jns     short loc_18001F191
0x18001f145  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f14c  cmp     rcx, r12
0x18001f14f  jz      loc_18001F323
0x18001f155  lea     ebx, [r13-1]
0x18001f159  test    [rcx+1Ch], bl
0x18001f15c  jz      loc_18001F323
0x18001f162  mov     rcx, [rcx+10h]
0x18001f166  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001f16d  lea     edx, [rbx+2Eh]
0x18001f170  mov     dword ptr [rsp+2E0h+var_2B8], 455h
0x18001f178  mov     r9d, esi
0x18001f17b  mov     [rsp+2E0h+var_2C0], rax
0x18001f180  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f187  call    WPP_SF_Dsd
0x18001f18c  jmp     loc_18001F31C
0x18001f191  lea     rax, [rbp+1E0h+var_30]
0x18001f198  mov     [rbp+1E0h+HttpResponse.Headers.KnownHeaders.pRawValue+0C0h], rax
0x18001f19c  lea     rcx, [rbp+1E0h+var_30]
0x18001f1a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f1a7  inc     rax
0x18001f1aa  cmp     byte ptr [rcx+rax], 0
0x18001f1ae  jnz     short loc_18001F1A7
0x18001f1b0  mov     rcx, [rdi]
0x18001f1b3  mov     ebx, 1
0x18001f1b8  mov     [rbp+1E0h+HttpResponse.Headers.KnownHeaders.RawValueLength+0C0h], ax
0x18001f1bc  mov     rax, [rcx+110h]
0x18001f1c3  mov     qword ptr [rsp+2E0h+var_288], rax
0x18001f1c8  mov     eax, [rcx+118h]
0x18001f1ce  mov     dword ptr [rsp+2E0h+var_288+8], eax
0x18001f1d2  lea     rax, [rsp+2E0h+var_298+8]
0x18001f1d7  mov     [rbp+1E0h+HttpResponse.pEntityChunks], rax
0x18001f1de  mov     [rbp+1E0h+HttpResponse.EntityChunkCount], bx
0x18001f1e5  mov     dword ptr [rcx+20h], 4
0x18001f1ec  mov     rcx, cs:pio; pio
0x18001f1f3  call    cs:__imp_StartThreadpoolIo
0x18001f1fa  nop     dword ptr [rax+rax+00h]
0x18001f1ff  mov     rcx, [rdi]
0x18001f202  test    rcx, rcx
0x18001f205  jz      short loc_18001F21F
0x18001f207  mov     eax, ebx
0x18001f209  lock xadd [rcx+158h], rax
0x18001f212  add     rax, rbx
0x18001f215  cmp     rax, rbx
0x18001f218  jg      short loc_18001F21F
0x18001f21a  lea     ecx, [rbx+0Dh]
0x18001f21d  int     29h; Win8: RtlFailFast(ecx)
0x18001f21f  and     qword ptr [rsp+2E0h+var_298], 0
0x18001f225  lea     r9, [rsp+2E0h+HttpResponse]; HttpResponse
0x18001f22a  mov     rcx, [rdi]
0x18001f22d  mov     r8d, ebx; Flags
0x18001f230  mov     [rsp+2E0h+Overlapped], rcx; Overlapped
0x18001f235  and     dword ptr [rsp+2E0h+var_2A8], 0
0x18001f23a  and     qword ptr [rsp+2E0h+var_2B0], 0
0x18001f240  mov     rax, [rcx+38h]
0x18001f244  and     [rsp+2E0h+var_2B8], 0
0x18001f24a  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x18001f251  and     [rsp+2E0h+var_2C0], 0
0x18001f257  mov     rdx, [rax+10h]; RequestId
0x18001f25b  call    cs:__imp_HttpSendHttpResponse
0x18001f262  nop     dword ptr [rax+rax+00h]
0x18001f267  mov     esi, eax
0x18001f269  cmp     eax, 3E5h
0x18001f26e  jz      short loc_18001F2CE
0x18001f270  test    eax, eax
0x18001f272  jz      short loc_18001F2CE
0x18001f274  mov     rcx, cs:pio; pio
0x18001f27b  call    cs:__imp_CancelThreadpoolIo
0x18001f282  nop     dword ptr [rax+rax+00h]
0x18001f287  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f28e  cmp     rcx, r12
0x18001f291  jz      short loc_18001F2C4
0x18001f293  test    [rcx+1Ch], bl
0x18001f296  jz      short loc_18001F2C4
0x18001f298  mov     rcx, [rcx+10h]
0x18001f29c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001f2a3  mov     edx, 30h ; '0'
0x18001f2a8  mov     dword ptr [rsp+2E0h+var_2B8], 477h
0x18001f2b0  mov     r9d, esi
0x18001f2b3  mov     [rsp+2E0h+var_2C0], rax
0x18001f2b8  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f2bf  call    WPP_SF_Dsd
0x18001f2c4  mov     rcx, rdi; this
0x18001f2c7  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001f2cc  jmp     short loc_18001F31C
0x18001f2ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x18001f2d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18001f2da  test    al, al
0x18001f2dc  jz      short loc_18001F2F0
0x18001f2de  mov     rbx, [rdi]
0x18001f2e1  mov     rcx, rbx; struct _KPS_IO *
0x18001f2e4  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001f2e9  mov     [rbx+150h], r13d
0x18001f2f0  cmp     qword ptr [rdi], 0
0x18001f2f4  jz      short loc_18001F31C
0x18001f2f6  mov     rcx, rdi; this
0x18001f2f9  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001f2fe  test    al, al
0x18001f300  jnz     short loc_18001F318
0x18001f302  mov     rcx, [rdi]
0x18001f305  add     rcx, 120h; CriticalSection
0x18001f30c  call    cs:__imp_RtlLeaveCriticalSection
0x18001f313  nop     dword ptr [rax+rax+00h]
0x18001f318  and     qword ptr [rdi], 0
0x18001f31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f323  cmp     qword ptr [rdi], 0
0x18001f327  jz      short loc_18001F338
0x18001f329  mov     rcx, rdi; this
0x18001f32c  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x18001f331  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f338  cmp     rcx, r12
0x18001f33b  jz      short loc_18001F35B
0x18001f33d  test    byte ptr [rcx+1Ch], 20h
0x18001f341  jz      short loc_18001F35B
0x18001f343  mov     rcx, [rcx+10h]
0x18001f347  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f34e  mov     edx, 31h ; '1'
0x18001f353  mov     r9d, esi
0x18001f356  call    WPP_SF_D
0x18001f35b  mov     rcx, [rbp+1E0h+var_20]
0x18001f362  xor     rcx, rsp; StackCookie
0x18001f365  call    __security_check_cookie
0x18001f36a  lea     r11, [rsp+2E0h+var_10]
0x18001f372  mov     rbx, [r11+28h]
0x18001f376  mov     rsi, [r11+30h]
0x18001f37a  mov     rdi, [r11+38h]
0x18001f37e  mov     rsp, r11
0x18001f381  pop     r13
0x18001f383  pop     r12
0x18001f385  pop     rbp
0x18001f386  retn
```
