# KpsHttpReceiveRequestIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x1800210f4`
- end: `0x1800215ba`
- name: `?KpsHttpReceiveRequestIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `1222`
- prototype: `void __fastcall(unsigned int, __int64, LPOVERLAPPED *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x18001ada8`
- `0x18001ae38`
- `0x18001e520`
- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x1800203ac`
- `0x1800210f4`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026cc0`
- `0x180026de0`
- `0x18002fe08`
- `0x180030168`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002128c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002128c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180021303`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180021303`
- `ntdll!RtlLeaveCriticalSection` at `0x1800213a0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002140d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800213a0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002140d`
- `ntdll!RtlEnterCriticalSection` at `0x1800213d6`
- `ntdll!RtlEnterCriticalSection` at `0x1800213d6`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800212e3`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800212e3`

## string_xrefs

- `0x1800211b8`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180021251`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18002132b`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18002143c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x1800214a0`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpReceiveRequestIoCompletion(unsigned int a1, __int64 a2, LPOVERLAPPED *a3)
{
  unsigned int v3; // r14d
  int v4; // esi
  int v6; // r12d
  void *v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  _QWORD *v12; // r10
  ULONG v13; // eax
  LPOVERLAPPED v14; // rbx
  int v15; // edx
  int v16; // r8d
  LPOVERLAPPED v17; // rbx
  _DWORD *hEvent; // rcx
  PULONG BytesReturned; // [rsp+28h] [rbp-58h]
  struct _KPS_IO *v20; // [rsp+40h] [rbp-40h] BYREF
  struct _KPS_IO *lpMem; // [rsp+48h] [rbp-38h] BYREF
  char v22[16]; // [rsp+50h] [rbp-30h] BYREF
  struct _KPS_IO **v23; // [rsp+60h] [rbp-20h]
  int v24; // [rsp+68h] [rbp-18h]
  int v25; // [rsp+6Ch] [rbp-14h]

  v3 = 0;
  v4 = 0;
  lpMem = 0;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, a3, *a3, a1, a2);
  KpsPerfUpdate(1u);
  if ( a1 == 234 )
  {
    HIDWORD((*a3)[2].Internal) = v6;
    v8 = KpsReAllocMem(HIDWORD((*a3)[2].Internal), (*a3)[1].hEvent);
    if ( v8 )
    {
      (*a3)[1].hEvent = v8;
      StartThreadpoolIo(pio);
      if ( *a3 && _InterlockedIncrement64((volatile signed __int64 *)&(*a3)[10].hEvent) <= 1 )
        __fastfail(0xEu);
      v13 = HttpReceiveHttpRequest(
              RequestQueueHandle,
              *((_QWORD *)(*a3)[1].hEvent + 2),
              0,
              (PHTTP_REQUEST)(*a3)[1].hEvent,
              HIDWORD((*a3)[2].Internal),
              0,
              *a3);
      v4 = v13;
      if ( v13 == 997 || !v13 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
        {
          v14 = *a3;
          KpsStartTimeoutTimer((struct _KPS_IO *)*a3);
          v14[10].Offset = 2;
        }
        if ( *a3 )
        {
          if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3) )
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*a3)[9]);
          *a3 = 0;
        }
        goto LABEL_52;
      }
      CancelThreadpoolIo(pio);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(BytesReturned) = 1746;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v4,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReturned);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3);
    }
    else
    {
      v4 = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(BytesReturned) = 1726;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          8,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReturned);
      }
    }
  }
  v9 = KpsCreateKpsIo(&lpMem);
  v3 = v9;
  if ( v9 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
    {
      v25 = 0;
      LODWORD(v20) = v9;
      v24 = 4;
      v23 = &v20;
      McGenEventWrite_EventWriteTransfer(v10, CreateKpsIoFailure, v11, 2, v22);
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(BytesReturned) = 1765;
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        v3,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        BytesReturned);
LABEL_52:
      v12 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v20 = lpMem;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)lpMem + 288));
    lpMem = 0;
    KpsDoHttpReceiveRequest((LPOVERLAPPED *)&v20);
    v17 = (LPOVERLAPPED)v20;
    if ( v20 && !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)&v20) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&v17[9]);
    if ( a1 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(BytesReturned) = 1779;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          a1,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReturned);
        v12 = WPP_GLOBAL_Control;
      }
      v3 = a1;
    }
    else if ( v4 )
    {
      v3 = v4;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(BytesReturned) = 1787;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v4,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReturned);
        goto LABEL_52;
      }
    }
    else
    {
      LODWORD((*a3)[2].Internal) = v6;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (*a3)[2].Internal, *((_QWORD *)(*a3)[1].hEvent + 9));
        v12 = WPP_GLOBAL_Control;
      }
      if ( dword_18003A9A8 )
      {
        KpsDoHttpReceiveClientCert((struct KpsIoLockedRef *)a3);
        goto LABEL_52;
      }
      hEvent = (*a3)[1].hEvent;
      if ( hEvent[9] == 6 && (*(_BYTE *)hEvent & 1) != 0 )
      {
        KpsDoHttpReceiveRequestEntity(a3);
        goto LABEL_52;
      }
    }
  }
  if ( *a3 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a3);
    v12 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    KpsFreeKpsIo(lpMem);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x20) != 0 )
    WPP_SF_D(v12[2], 87, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v3);
}

```

## disassembly

```asm
0x1800210f4  mov     [rsp-28h+arg_8], rbx
0x1800210f9  mov     [rsp-28h+arg_18], rsi
0x1800210fe  push    rbp
0x1800210ff  push    rdi
0x180021100  push    r12
0x180021102  push    r14
0x180021104  push    r15
0x180021106  mov     rbp, rsp
0x180021109  sub     rsp, 80h
0x180021110  mov     rax, cs:__security_cookie
0x180021117  xor     rax, rsp
0x18002111a  mov     [rbp+var_10], rax
0x18002111e  xor     r14d, r14d
0x180021121  xor     esi, esi
0x180021123  and     [rbp+lpMem], rsi
0x180021127  mov     rdi, r8
0x18002112a  mov     r12, rdx
0x18002112d  mov     r15d, ecx
0x180021130  mov     rcx, cs:WPP_GLOBAL_Control
0x180021137  lea     rax, WPP_GLOBAL_Control
0x18002113e  cmp     rcx, rax
0x180021141  jz      short loc_180021162
0x180021143  test    byte ptr [rcx+1Ch], 20h
0x180021147  jz      short loc_180021162
0x180021149  mov     r9, [r8]
0x18002114c  lea     edx, [rsi+50h]
0x18002114f  mov     rcx, [rcx+10h]
0x180021153  mov     [rsp+80h+BytesReturned], r12; BytesReturned
0x180021158  mov     [rsp+80h+RequestBufferLength], r15d
0x18002115d  call    WPP_SF_qDI
0x180021162  mov     ebx, 1
0x180021167  mov     ecx, ebx; unsigned int
0x180021169  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x18002116e  cmp     r15d, 0EAh
0x180021175  jnz     short loc_1800211DE
0x180021177  mov     rax, [rdi]
0x18002117a  mov     [rax+44h], r12d
0x18002117e  mov     rax, [rdi]
0x180021181  mov     ecx, [rax+44h]; unsigned __int64
0x180021184  mov     rdx, [rax+38h]; void *
0x180021188  call    ?KpsReAllocMem@@YAPEAX_KPEAX@Z; KpsReAllocMem(unsigned __int64,void *)
0x18002118d  mov     rcx, rax
0x180021190  test    rax, rax
0x180021193  jnz     loc_18002127E
0x180021199  lea     esi, [rbx+7]
0x18002119c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211a3  lea     rax, WPP_GLOBAL_Control
0x1800211aa  cmp     rcx, rax
0x1800211ad  jz      short loc_1800211DE
0x1800211af  test    [rcx+1Ch], bl
0x1800211b2  jz      short loc_1800211DE
0x1800211b4  mov     rcx, [rcx+10h]
0x1800211b8  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800211bf  lea     edx, [rbx+50h]
0x1800211c2  mov     dword ptr [rsp+80h+BytesReturned], 6BEh
0x1800211ca  mov     r9d, esi
0x1800211cd  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x1800211d2  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800211d9  call    WPP_SF_Dsd
0x1800211de  lea     rcx, [rbp+lpMem]; struct _KPS_IO **
0x1800211e2  call    ?KpsCreateKpsIo@@YAKPEAPEAU_KPS_IO@@@Z; KpsCreateKpsIo(_KPS_IO * *)
0x1800211e7  mov     r14d, eax
0x1800211ea  test    eax, eax
0x1800211ec  jz      loc_1800213C7
0x1800211f2  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x1800211f9  jz      short loc_18002122C
0x1800211fb  and     [rbp+var_14], 0
0x1800211ff  lea     rdx, CreateKpsIoFailure
0x180021206  mov     dword ptr [rbp+var_40], eax
0x180021209  mov     r9d, 2
0x18002120f  lea     rax, [rbp+var_40]
0x180021213  mov     [rbp+var_18], 4
0x18002121a  mov     [rbp+var_20], rax
0x18002121e  lea     rax, [rbp+var_30]
0x180021222  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x180021227  call    McGenEventWrite_EventWriteTransfer
0x18002122c  mov     r10, cs:WPP_GLOBAL_Control
0x180021233  lea     rax, WPP_GLOBAL_Control
0x18002123a  cmp     r10, rax
0x18002123d  jz      loc_1800213BB
0x180021243  test    [r10+1Ch], bl
0x180021247  jz      loc_1800213BB
0x18002124d  mov     rcx, [r10+10h]
0x180021251  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180021258  mov     edx, 53h ; 'S'
0x18002125d  mov     dword ptr [rsp+80h+BytesReturned], 6E5h
0x180021265  mov     r9d, r14d
0x180021268  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x18002126d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021274  call    WPP_SF_Dsd
0x180021279  jmp     loc_1800213AF
0x18002127e  mov     rax, [rdi]
0x180021281  mov     [rax+38h], rcx
0x180021285  mov     rcx, cs:pio; pio
0x18002128c  call    cs:__imp_StartThreadpoolIo
0x180021293  nop     dword ptr [rax+rax+00h]
0x180021298  mov     rcx, [rdi]
0x18002129b  test    rcx, rcx
0x18002129e  jz      short loc_1800212BB
0x1800212a0  mov     rax, rbx
0x1800212a3  lock xadd [rcx+158h], rax
0x1800212ac  add     rax, rbx
0x1800212af  cmp     rax, rbx
0x1800212b2  jg      short loc_1800212BB
0x1800212b4  mov     ecx, 0Eh
0x1800212b9  int     29h; Win8: RtlFailFast(ecx)
0x1800212bb  mov     rax, [rdi]
0x1800212be  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x1800212c5  mov     [rsp+80h+Overlapped], rax; Overlapped
0x1800212ca  and     [rsp+80h+BytesReturned], rsi
0x1800212cf  mov     r8d, [rax+44h]
0x1800212d3  mov     r9, [rax+38h]; RequestBuffer
0x1800212d7  mov     [rsp+80h+RequestBufferLength], r8d; RequestBufferLength
0x1800212dc  xor     r8d, r8d; Flags
0x1800212df  mov     rdx, [r9+10h]; RequestId
0x1800212e3  call    cs:__imp_HttpReceiveHttpRequest
0x1800212ea  nop     dword ptr [rax+rax+00h]
0x1800212ef  mov     esi, eax
0x1800212f1  cmp     eax, 3E5h
0x1800212f6  jz      short loc_180021360
0x1800212f8  test    eax, eax
0x1800212fa  jz      short loc_180021360
0x1800212fc  mov     rcx, cs:pio; pio
0x180021303  call    cs:__imp_CancelThreadpoolIo
0x18002130a  nop     dword ptr [rax+rax+00h]
0x18002130f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021316  lea     rax, WPP_GLOBAL_Control
0x18002131d  cmp     rcx, rax
0x180021320  jz      short loc_180021353
0x180021322  test    [rcx+1Ch], bl
0x180021325  jz      short loc_180021353
0x180021327  mov     rcx, [rcx+10h]
0x18002132b  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180021332  mov     edx, 52h ; 'R'
0x180021337  mov     dword ptr [rsp+80h+BytesReturned], 6D2h
0x18002133f  mov     r9d, esi
0x180021342  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x180021347  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002134e  call    WPP_SF_Dsd
0x180021353  mov     rcx, rdi; this
0x180021356  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18002135b  jmp     loc_1800211DE
0x180021360  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x180021367  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x18002136c  test    al, al
0x18002136e  jz      short loc_180021385
0x180021370  mov     rbx, [rdi]
0x180021373  mov     rcx, rbx; struct _KPS_IO *
0x180021376  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18002137b  mov     dword ptr [rbx+150h], 2
0x180021385  cmp     [rdi], r14
0x180021388  jz      short loc_1800213AF
0x18002138a  mov     rcx, rdi; this
0x18002138d  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180021392  test    al, al
0x180021394  jnz     short loc_1800213AC
0x180021396  mov     rcx, [rdi]
0x180021399  add     rcx, 120h; CriticalSection
0x1800213a0  call    cs:__imp_RtlLeaveCriticalSection
0x1800213a7  nop     dword ptr [rax+rax+00h]
0x1800213ac  and     [rdi], r14
0x1800213af  lea     rbx, WPP_GLOBAL_Control
0x1800213b6  jmp     loc_18002153C
0x1800213bb  lea     rbx, WPP_GLOBAL_Control
0x1800213c2  jmp     loc_180021543
0x1800213c7  mov     rcx, [rbp+lpMem]
0x1800213cb  mov     [rbp+var_40], rcx
0x1800213cf  add     rcx, 120h; CriticalSection
0x1800213d6  call    cs:__imp_RtlEnterCriticalSection
0x1800213dd  nop     dword ptr [rax+rax+00h]
0x1800213e2  and     [rbp+lpMem], 0
0x1800213e7  lea     rcx, [rbp+var_40]; this
0x1800213eb  call    ?KpsDoHttpReceiveRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpReceiveRequest(KpsIoLockedRef &)
0x1800213f0  mov     rbx, [rbp+var_40]
0x1800213f4  test    rbx, rbx
0x1800213f7  jz      short loc_180021419
0x1800213f9  lea     rcx, [rbp+var_40]; this
0x1800213fd  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180021402  test    al, al
0x180021404  jnz     short loc_180021419
0x180021406  lea     rcx, [rbx+120h]; CriticalSection
0x18002140d  call    cs:__imp_RtlLeaveCriticalSection
0x180021414  nop     dword ptr [rax+rax+00h]
0x180021419  test    r15d, r15d
0x18002141c  jz      short loc_180021473
0x18002141e  mov     r10, cs:WPP_GLOBAL_Control
0x180021425  lea     rbx, WPP_GLOBAL_Control
0x18002142c  cmp     r10, rbx
0x18002142f  jz      short loc_18002146B
0x180021431  test    byte ptr [r10+1Ch], 1
0x180021436  jz      short loc_18002146B
0x180021438  mov     rcx, [r10+10h]
0x18002143c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180021443  mov     edx, 54h ; 'T'
0x180021448  mov     dword ptr [rsp+80h+BytesReturned], 6F3h
0x180021450  mov     r9d, r15d
0x180021453  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x180021458  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002145f  call    WPP_SF_Dsd
0x180021464  mov     r10, cs:WPP_GLOBAL_Control
0x18002146b  mov     r14d, r15d
0x18002146e  jmp     loc_180021543
0x180021473  test    esi, esi
0x180021475  jz      short loc_1800214CA
0x180021477  mov     r14d, esi
0x18002147a  mov     r10, cs:WPP_GLOBAL_Control
0x180021481  lea     rbx, WPP_GLOBAL_Control
0x180021488  cmp     r10, rbx
0x18002148b  jz      loc_180021543
0x180021491  test    byte ptr [r10+1Ch], 1
0x180021496  jz      loc_180021543
0x18002149c  mov     rcx, [r10+10h]
0x1800214a0  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800214a7  mov     edx, 55h ; 'U'
0x1800214ac  mov     dword ptr [rsp+80h+BytesReturned], 6FBh
0x1800214b4  mov     r9d, esi
0x1800214b7  mov     qword ptr [rsp+80h+RequestBufferLength], rax
0x1800214bc  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800214c3  call    WPP_SF_Dsd
0x1800214c8  jmp     short loc_18002153C
0x1800214ca  mov     rax, [rdi]
0x1800214cd  mov     [rax+40h], r12d
0x1800214d1  mov     r10, cs:WPP_GLOBAL_Control
0x1800214d8  lea     rbx, WPP_GLOBAL_Control
0x1800214df  cmp     r10, rbx
0x1800214e2  jz      short loc_18002150F
0x1800214e4  test    byte ptr [r10+1Ch], 4
0x1800214e9  jz      short loc_18002150F
0x1800214eb  mov     r9, [rdi]
0x1800214ee  mov     rax, [r9+38h]
0x1800214f2  mov     r9d, [r9+40h]
0x1800214f6  mov     rcx, [rax+48h]
0x1800214fa  mov     qword ptr [rsp+80h+RequestBufferLength], rcx
0x1800214ff  mov     rcx, [r10+10h]
0x180021503  call    WPP_SF_dS
0x180021508  mov     r10, cs:WPP_GLOBAL_Control
0x18002150f  cmp     cs:dword_18003A9A8, 0
0x180021516  jz      short loc_180021522
0x180021518  mov     rcx, rdi; this
0x18002151b  call    ?KpsDoHttpReceiveClientCert@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpReceiveClientCert(KpsIoLockedRef &)
0x180021520  jmp     short loc_18002153C
0x180021522  mov     rax, [rdi]
0x180021525  mov     rcx, [rax+38h]
0x180021529  cmp     dword ptr [rcx+24h], 6
0x18002152d  jnz     short loc_180021543
0x18002152f  test    byte ptr [rcx], 1
0x180021532  jz      short loc_180021543
0x180021534  mov     rcx, rdi; this
0x180021537  call    ?KpsDoHttpReceiveRequestEntity@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpReceiveRequestEntity(KpsIoLockedRef &)
0x18002153c  mov     r10, cs:WPP_GLOBAL_Control
0x180021543  cmp     qword ptr [rdi], 0
0x180021547  jz      short loc_180021558
0x180021549  mov     rcx, rdi; this
0x18002154c  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180021551  mov     r10, cs:WPP_GLOBAL_Control
0x180021558  mov     rcx, [rbp+lpMem]; lpMem
0x18002155c  test    rcx, rcx
0x18002155f  jz      short loc_18002156D
0x180021561  call    ?KpsFreeKpsIo@@YAXPEAU_KPS_IO@@@Z; KpsFreeKpsIo(_KPS_IO *)
0x180021566  mov     r10, cs:WPP_GLOBAL_Control
0x18002156d  cmp     r10, rbx
0x180021570  jz      short loc_180021591
0x180021572  test    byte ptr [r10+1Ch], 20h
0x180021577  jz      short loc_180021591
0x180021579  mov     rcx, [r10+10h]
0x18002157d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021584  mov     edx, 57h ; 'W'
0x180021589  mov     r9d, r14d
0x18002158c  call    WPP_SF_D
0x180021591  mov     rcx, [rbp+var_10]
0x180021595  xor     rcx, rsp; StackCookie
0x180021598  call    __security_check_cookie
0x18002159d  lea     r11, [rsp+80h+var_s0]
0x1800215a5  mov     rbx, [r11+38h]
0x1800215a9  mov     rsi, [r11+48h]
0x1800215ad  mov     rsp, r11
0x1800215b0  pop     r15
0x1800215b2  pop     r14
0x1800215b4  pop     r12
0x1800215b6  pop     rdi
0x1800215b7  pop     rbp
0x1800215b8  retn
```
