# KpsHttpReceiveClientCertIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x1800208d8`
- end: `0x180020d05`
- name: `?KpsHttpReceiveClientCertIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `1069`
- prototype: `void __fastcall(unsigned int, __int64, LPOVERLAPPED *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18001ae7c`
- `0x18001e728`
- `0x18001edec`
- `0x1800208d8`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026de0`
- `0x180030168`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800209d2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800209d2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020a50`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020a50`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ae8`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ae8`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180020a30`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180020a30`

## string_xrefs

- `0x1800209a8`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180020a72`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180020b45`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpReceiveClientCertIoCompletion(unsigned int a1, __int64 a2, LPOVERLAPPED *a3)
{
  DWORD v4; // ebp
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  LPOVERLAPPED v8; // rdx
  ULONG_PTR InternalHigh; // rax
  void *v10; // rax
  int v11; // edx
  ULONG v12; // eax
  LPOVERLAPPED v13; // rbx
  unsigned int *v14; // rdx
  __int64 v15; // r8
  _DWORD *hEvent; // rax
  PULONG BytesReceived; // [rsp+28h] [rbp-70h]
  PULONG BytesReceiveda; // [rsp+28h] [rbp-70h]
  int v19; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v20[16]; // [rsp+48h] [rbp-50h] BYREF
  int *v21; // [rsp+58h] [rbp-40h]
  int v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+64h] [rbp-34h]

  v4 = a2;
  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, a3, *a3, a1, a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a1 == 234 )
  {
    v8 = *a3;
    InternalHigh = (*a3)[2].InternalHigh;
    if ( *(_DWORD *)(InternalHigh + 4) >= 0xFFFFFFE0 )
    {
      v8[2].Offset = -1;
      v6 = -1073741675;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 89;
        LODWORD(BytesReceived) = 1842;
        goto LABEL_10;
      }
    }
    else
    {
      v8[2].Offset = *(_DWORD *)(InternalHigh + 4) + 32;
      v10 = KpsReAllocMem((*a3)[2].Offset, (void *)(*a3)[2].InternalHigh);
      if ( v10 )
      {
        (*a3)[2].InternalHigh = (ULONG_PTR)v10;
        StartThreadpoolIo(pio);
        if ( *a3 && _InterlockedIncrement64((volatile signed __int64 *)&(*a3)[10].hEvent) <= 1 )
          __fastfail(0xEu);
        v12 = HttpReceiveClientCertificate(
                RequestQueueHandle,
                *((_QWORD *)(*a3)[1].hEvent + 1),
                0,
                (PHTTP_SSL_CLIENT_CERT_INFO)(*a3)[2].InternalHigh,
                (*a3)[2].Offset,
                0,
                *a3);
        v6 = v12;
        if ( v12 == 997 || !v12 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
          {
            v13 = *a3;
            KpsStartTimeoutTimer((struct _KPS_IO *)*a3);
            v13[10].Offset = 2;
          }
          if ( *a3 )
          {
            if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3) )
              RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&(*a3)[9]);
            *a3 = 0;
          }
        }
        else
        {
          CancelThreadpoolIo(pio);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LODWORD(BytesReceiveda) = 1870;
            WPP_SF_Dsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              91,
              (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
              v6,
              (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
              BytesReceiveda);
          }
          KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3);
        }
        goto LABEL_52;
      }
      v6 = 8;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 90;
        LODWORD(BytesReceived) = 1850;
LABEL_10:
        WPP_SF_Dsd(
          v7[2],
          v11,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          v6,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReceived);
LABEL_52:
        v7 = WPP_GLOBAL_Control;
      }
    }
  }
  else if ( a1 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      LODWORD(BytesReceived) = 1886;
      WPP_SF_Dsd(
        v7[2],
        92,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        a1,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        BytesReceived);
      v7 = WPP_GLOBAL_Control;
    }
    v6 = a1;
  }
  else
  {
    (*a3)[2].Offset = v4;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        (*a3)[2].Offset,
        *(_DWORD *)(*a3)[2].InternalHigh);
      v7 = WPP_GLOBAL_Control;
    }
    v14 = (unsigned int *)(*a3)[2].InternalHigh;
    if ( *((_QWORD *)v14 + 1) )
    {
      v15 = *v14;
      if ( (_DWORD)v15 )
      {
        if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 0x10) != 0 )
        {
          v23 = 0;
          v21 = &v19;
          v19 = v15;
          v22 = 4;
          McGenEventWrite_EventWriteTransfer(v7, ClientCertNotValid, v15, 2, v20);
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
        {
          WPP_SF_D(v7[2], 95, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *(unsigned int *)(*a3)[2].InternalHigh);
          goto LABEL_52;
        }
      }
      else
      {
        hEvent = (*a3)[1].hEvent;
        if ( hEvent[9] == 6 && (*(_BYTE *)hEvent & 1) != 0 )
        {
          KpsDoHttpReceiveRequestEntity(a3);
          goto LABEL_52;
        }
      }
    }
    else
    {
      if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 0x10) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(v7, ClientCertRequired, a3, 1, v20);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      {
        WPP_SF_(v7[2], 94, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
        goto LABEL_52;
      }
    }
  }
  if ( *a3 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_D(v7[2], 96, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v6);
}

```

## disassembly

```asm
0x1800208d8  mov     [rsp+arg_8], rbx
0x1800208dd  push    rbp
0x1800208de  push    rsi
0x1800208df  push    rdi
0x1800208e0  push    r12
0x1800208e2  push    r15
0x1800208e4  sub     rsp, 70h
0x1800208e8  mov     rax, cs:__security_cookie
0x1800208ef  xor     rax, rsp
0x1800208f2  mov     [rsp+98h+var_30], rax
0x1800208f7  mov     rdi, r8
0x1800208fa  mov     rbp, rdx
0x1800208fd  mov     ebx, ecx
0x1800208ff  xor     esi, esi
0x180020901  mov     rcx, cs:WPP_GLOBAL_Control
0x180020908  lea     r15, WPP_GLOBAL_Control
0x18002090f  cmp     rcx, r15
0x180020912  jz      short loc_180020939
0x180020914  test    byte ptr [rcx+1Ch], 20h
0x180020918  jz      short loc_180020939
0x18002091a  mov     r9, [r8]
0x18002091d  lea     edx, [rsi+58h]
0x180020920  mov     rcx, [rcx+10h]
0x180020924  mov     [rsp+98h+BytesReceived], rbp; BytesReceived
0x180020929  mov     [rsp+98h+SslClientCertInfoSize], ebx
0x18002092d  call    WPP_SF_qDI
0x180020932  mov     rcx, cs:WPP_GLOBAL_Control
0x180020939  lea     r12, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020940  cmp     ebx, 0EAh
0x180020946  jnz     loc_180020B32
0x18002094c  mov     rdx, [rdi]
0x18002094f  mov     rax, [rdx+48h]
0x180020953  mov     ecx, [rax+4]
0x180020956  add     ecx, 20h ; ' '
0x180020959  cmp     ecx, 20h ; ' '
0x18002095c  jb      loc_180020AFD
0x180020962  mov     [rdx+50h], ecx
0x180020965  mov     rax, [rdi]
0x180020968  mov     ecx, [rax+50h]; unsigned __int64
0x18002096b  mov     rdx, [rax+48h]; void *
0x18002096f  call    ?KpsReAllocMem@@YAPEAX_KPEAX@Z; KpsReAllocMem(unsigned __int64,void *)
0x180020974  mov     rcx, rax
0x180020977  test    rax, rax
0x18002097a  jnz     short loc_1800209C4
0x18002097c  lea     esi, [rax+8]
0x18002097f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020986  cmp     rcx, r15
0x180020989  jz      loc_180020CAF
0x18002098f  test    byte ptr [rcx+1Ch], 1
0x180020993  jz      loc_180020CAF
0x180020999  lea     edx, [rax+5Ah]
0x18002099c  mov     dword ptr [rsp+98h+BytesReceived], 73Ah
0x1800209a4  mov     rcx, [rcx+10h]
0x1800209a8  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800209af  mov     r9d, esi
0x1800209b2  mov     qword ptr [rsp+98h+SslClientCertInfoSize], rax
0x1800209b7  mov     r8, r12
0x1800209ba  call    WPP_SF_Dsd
0x1800209bf  jmp     loc_180020CA8
0x1800209c4  mov     rax, [rdi]
0x1800209c7  mov     [rax+48h], rcx
0x1800209cb  mov     rcx, cs:pio; pio
0x1800209d2  call    cs:__imp_StartThreadpoolIo
0x1800209d9  nop     dword ptr [rax+rax+00h]
0x1800209de  mov     rcx, [rdi]
0x1800209e1  test    rcx, rcx
0x1800209e4  jz      short loc_180020A04
0x1800209e6  mov     eax, 1
0x1800209eb  lock xadd [rcx+158h], rax
0x1800209f4  inc     rax
0x1800209f7  cmp     rax, 1
0x1800209fb  jg      short loc_180020A04
0x1800209fd  mov     ecx, 0Eh
0x180020a02  int     29h; Win8: RtlFailFast(ecx)
0x180020a04  mov     r8, [rdi]
0x180020a07  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x180020a0e  mov     [rsp+98h+Overlapped], r8; Overlapped
0x180020a13  and     [rsp+98h+BytesReceived], rsi
0x180020a18  mov     rax, [r8+38h]
0x180020a1c  mov     r10d, [r8+50h]
0x180020a20  mov     r9, [r8+48h]; SslClientCertInfo
0x180020a24  xor     r8d, r8d; Flags
0x180020a27  mov     [rsp+98h+SslClientCertInfoSize], r10d; SslClientCertInfoSize
0x180020a2c  mov     rdx, [rax+8]; ConnectionId
0x180020a30  call    cs:__imp_HttpReceiveClientCertificate
0x180020a37  nop     dword ptr [rax+rax+00h]
0x180020a3c  mov     esi, eax
0x180020a3e  cmp     eax, 3E5h
0x180020a43  jz      short loc_180020AA3
0x180020a45  test    eax, eax
0x180020a47  jz      short loc_180020AA3
0x180020a49  mov     rcx, cs:pio; pio
0x180020a50  call    cs:__imp_CancelThreadpoolIo
0x180020a57  nop     dword ptr [rax+rax+00h]
0x180020a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a63  cmp     rcx, r15
0x180020a66  jz      short loc_180020A96
0x180020a68  test    byte ptr [rcx+1Ch], 1
0x180020a6c  jz      short loc_180020A96
0x180020a6e  mov     rcx, [rcx+10h]
0x180020a72  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180020a79  mov     edx, 5Bh ; '['
0x180020a7e  mov     dword ptr [rsp+98h+BytesReceived], 74Eh
0x180020a86  mov     r9d, esi
0x180020a89  mov     qword ptr [rsp+98h+SslClientCertInfoSize], rax
0x180020a8e  mov     r8, r12
0x180020a91  call    WPP_SF_Dsd
0x180020a96  mov     rcx, rdi; this
0x180020a99  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180020a9e  jmp     loc_180020CA8
0x180020aa3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x180020aaa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x180020aaf  test    al, al
0x180020ab1  jz      short loc_180020AC8
0x180020ab3  mov     rbx, [rdi]
0x180020ab6  mov     rcx, rbx; struct _KPS_IO *
0x180020ab9  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x180020abe  mov     dword ptr [rbx+150h], 2
0x180020ac8  cmp     qword ptr [rdi], 0
0x180020acc  jz      loc_180020CA8
0x180020ad2  mov     rcx, rdi; this
0x180020ad5  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180020ada  test    al, al
0x180020adc  jnz     short loc_180020AF4
0x180020ade  mov     rcx, [rdi]
0x180020ae1  add     rcx, 120h; CriticalSection
0x180020ae8  call    cs:__imp_RtlLeaveCriticalSection
0x180020aef  nop     dword ptr [rax+rax+00h]
0x180020af4  and     qword ptr [rdi], 0
0x180020af8  jmp     loc_180020CA8
0x180020afd  or      dword ptr [rdx+50h], 0FFFFFFFFh
0x180020b01  mov     esi, 0C0000095h
0x180020b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b0d  cmp     rcx, r15
0x180020b10  jz      loc_180020CAF
0x180020b16  test    byte ptr [rcx+1Ch], 1
0x180020b1a  jz      loc_180020CAF
0x180020b20  mov     edx, 59h ; 'Y'
0x180020b25  mov     dword ptr [rsp+98h+BytesReceived], 732h
0x180020b2d  jmp     loc_1800209A4
0x180020b32  test    ebx, ebx
0x180020b34  jz      short loc_180020B77
0x180020b36  cmp     rcx, r15
0x180020b39  jz      short loc_180020B70
0x180020b3b  test    byte ptr [rcx+1Ch], 1
0x180020b3f  jz      short loc_180020B70
0x180020b41  mov     rcx, [rcx+10h]
0x180020b45  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180020b4c  mov     edx, 5Ch ; '\'
0x180020b51  mov     dword ptr [rsp+98h+BytesReceived], 75Eh
0x180020b59  mov     r9d, ebx
0x180020b5c  mov     qword ptr [rsp+98h+SslClientCertInfoSize], rax
0x180020b61  mov     r8, r12
0x180020b64  call    WPP_SF_Dsd
0x180020b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b70  mov     esi, ebx
0x180020b72  jmp     loc_180020CAF
0x180020b77  mov     rax, [rdi]
0x180020b7a  mov     [rax+50h], ebp
0x180020b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b84  cmp     rcx, r15
0x180020b87  jz      short loc_180020BB8
0x180020b89  test    byte ptr [rcx+1Ch], 4
0x180020b8d  jz      short loc_180020BB8
0x180020b8f  mov     r9, [rdi]
0x180020b92  mov     edx, 5Dh ; ']'
0x180020b97  mov     rcx, [rcx+10h]
0x180020b9b  mov     r8, r12
0x180020b9e  mov     rax, [r9+48h]
0x180020ba2  mov     r9d, [r9+50h]
0x180020ba6  mov     eax, [rax]
0x180020ba8  mov     [rsp+98h+SslClientCertInfoSize], eax
0x180020bac  call    WPP_SF_dD
0x180020bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bb8  mov     rax, [rdi]
0x180020bbb  mov     rdx, [rax+48h]
0x180020bbf  cmp     [rdx+8], rsi
0x180020bc3  jnz     short loc_180020C1A
0x180020bc5  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 10h
0x180020bcc  jz      short loc_180020BF1
0x180020bce  lea     rax, [rsp+98h+var_50]
0x180020bd3  mov     r9d, 1
0x180020bd9  lea     rdx, ClientCertRequired
0x180020be0  mov     qword ptr [rsp+98h+SslClientCertInfoSize], rax
0x180020be5  call    McGenEventWrite_EventWriteTransfer
0x180020bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bf1  cmp     rcx, r15
0x180020bf4  jz      loc_180020CAF
0x180020bfa  test    byte ptr [rcx+1Ch], 1
0x180020bfe  jz      loc_180020CAF
0x180020c04  mov     rcx, [rcx+10h]
0x180020c08  mov     edx, 5Eh ; '^'
0x180020c0d  mov     r8, r12
0x180020c10  call    WPP_SF_
0x180020c15  jmp     loc_180020CA8
0x180020c1a  mov     r8d, [rdx]
0x180020c1d  test    r8d, r8d
0x180020c20  jz      short loc_180020C91
0x180020c22  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 10h
0x180020c29  jz      short loc_180020C69
0x180020c2b  and     [rsp+98h+var_34], esi
0x180020c2f  lea     rax, [rsp+98h+var_58]
0x180020c34  mov     [rsp+98h+var_40], rax
0x180020c39  lea     rdx, ClientCertNotValid
0x180020c40  lea     rax, [rsp+98h+var_50]
0x180020c45  mov     [rsp+98h+var_58], r8d
0x180020c4a  mov     r9d, 2
0x180020c50  mov     qword ptr [rsp+98h+SslClientCertInfoSize], rax
0x180020c55  mov     [rsp+98h+var_38], 4
0x180020c5d  call    McGenEventWrite_EventWriteTransfer
0x180020c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c69  cmp     rcx, r15
0x180020c6c  jz      short loc_180020CAF
0x180020c6e  test    byte ptr [rcx+1Ch], 1
0x180020c72  jz      short loc_180020CAF
0x180020c74  mov     rax, [rdi]
0x180020c77  mov     edx, 5Fh ; '_'
0x180020c7c  mov     rcx, [rcx+10h]
0x180020c80  mov     r8, r12
0x180020c83  mov     r9, [rax+48h]
0x180020c87  mov     r9d, [r9]
0x180020c8a  call    WPP_SF_D
0x180020c8f  jmp     short loc_180020CA8
0x180020c91  mov     rax, [rax+38h]
0x180020c95  cmp     dword ptr [rax+24h], 6
0x180020c99  jnz     short loc_180020CAF
0x180020c9b  test    byte ptr [rax], 1
0x180020c9e  jz      short loc_180020CAF
0x180020ca0  mov     rcx, rdi; this
0x180020ca3  call    ?KpsDoHttpReceiveRequestEntity@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpReceiveRequestEntity(KpsIoLockedRef &)
0x180020ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020caf  cmp     qword ptr [rdi], 0
0x180020cb3  jz      short loc_180020CC4
0x180020cb5  mov     rcx, rdi; this
0x180020cb8  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180020cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cc4  cmp     rcx, r15
0x180020cc7  jz      short loc_180020CE3
0x180020cc9  test    byte ptr [rcx+1Ch], 20h
0x180020ccd  jz      short loc_180020CE3
0x180020ccf  mov     rcx, [rcx+10h]
0x180020cd3  mov     edx, 60h ; '`'
0x180020cd8  mov     r9d, esi
0x180020cdb  mov     r8, r12
0x180020cde  call    WPP_SF_D
0x180020ce3  mov     rcx, [rsp+98h+var_30]
0x180020ce8  xor     rcx, rsp; StackCookie
0x180020ceb  call    __security_check_cookie
0x180020cf0  mov     rbx, [rsp+98h+arg_8]
0x180020cf8  add     rsp, 70h
0x180020cfc  pop     r15
0x180020cfe  pop     r12
0x180020d00  pop     rdi
0x180020d01  pop     rsi
0x180020d02  pop     rbp
0x180020d03  retn
```
