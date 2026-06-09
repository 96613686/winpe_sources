# KpsHttpReceiveRequestEntityIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x180020d0c`
- end: `0x1800210ed`
- name: `?KpsHttpReceiveRequestEntityIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `993`
- prototype: `void __fastcall(ULONG, __int64, LPOVERLAPPED *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x18001ada8`
- `0x18001ae38`
- `0x18001ae7c`
- `0x18001e728`
- `0x180020d0c`
- `0x1800222f0`
- `0x180022d38`
- `0x180024be0`
- `0x180026404`
- `0x180026a08`
- `0x180026de0`
- `0x180030168`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180020ed5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180020ed5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020f48`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020fc9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020f48`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180020fc9`
- `ntdll!RtlLeaveCriticalSection` at `0x18002105a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002105a`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180020f2e`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180020f2e`

## string_xrefs

- `0x180020d98`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180020feb`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpReceiveRequestEntityIoCompletion(ULONG a1, __int64 a2, LPOVERLAPPED *a3)
{
  int v4; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  LPOVERLAPPED v8; // rdx
  __int64 Internal_low; // r9
  unsigned int v10; // eax
  LPOVERLAPPED v11; // rcx
  unsigned int Internal_high; // eax
  void *v13; // rax
  ULONG EntityBufferLength; // esi
  char *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r8
  LPOVERLAPPED v18; // rbx
  PULONG BytesReturned; // [rsp+28h] [rbp-60h]
  PULONG BytesReturneda; // [rsp+28h] [rbp-60h]
  _BYTE v21[16]; // [rsp+40h] [rbp-48h] BYREF

  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, a3, *a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      v7 = 106;
      LODWORD(BytesReturned) = 2004;
LABEL_8:
      WPP_SF_Dsd(
        v6[2],
        v7,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        a1,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        BytesReturned);
LABEL_52:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  v8 = *a3;
  Internal_low = LODWORD((*a3)[3].Internal);
  v10 = v4 + Internal_low;
  if ( v4 + (int)Internal_low < (unsigned int)Internal_low )
  {
    a1 = -1073741675;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    {
      WPP_SF_dD(v6[2], 107, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Internal_low, v4);
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  a1 = 0;
  if ( v10 > dword_18003A9C0 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    {
      WPP_SF_dD(v6[2], 108, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v10, dword_18003A9C0);
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  if ( v10 != HIDWORD(v8[3].Internal) )
  {
    if ( v10 >= HIDWORD(v8[3].Internal) )
    {
      a1 = 1359;
      goto LABEL_53;
    }
    LODWORD(v8[3].Internal) = v10;
    v15 = (char *)(*a3)[2].hEvent + LODWORD((*a3)[3].Internal);
    EntityBufferLength = HIDWORD((*a3)[3].Internal) - LODWORD((*a3)[3].Internal);
    goto LABEL_26;
  }
  LODWORD(v8[3].Internal) = v10;
  v11 = *a3;
  Internal_high = HIDWORD((*a3)[3].Internal);
  if ( Internal_high + 3072 < Internal_high )
  {
    HIDWORD(v11[3].Internal) = -1;
    a1 = -1073741675;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        HIDWORD((*a3)[3].Internal));
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  HIDWORD(v11[3].Internal) = Internal_high + 3072;
  v13 = KpsReAllocMem(HIDWORD((*a3)[3].Internal), (*a3)[2].hEvent);
  if ( v13 )
  {
    EntityBufferLength = 3072;
    (*a3)[2].hEvent = v13;
    v15 = (char *)(*a3)[2].hEvent + LODWORD((*a3)[3].Internal);
LABEL_26:
    StartThreadpoolIo(pio);
    if ( *a3 && _InterlockedIncrement64((volatile signed __int64 *)&(*a3)[10].hEvent) <= 1 )
      __fastfail(0xEu);
    a1 = HttpReceiveRequestEntityBody(
           RequestQueueHandle,
           *((_QWORD *)(*a3)[1].hEvent + 2),
           0,
           v15,
           EntityBufferLength,
           0,
           *a3);
    if ( a1 == 38 )
    {
      CancelThreadpoolIo(pio);
      if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(v16, HttpRequestReceived, v17, a1 - 37, v21);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          LODWORD((*a3)[3].Internal));
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3);
      KpsProcessProxyRequest((struct _KPS_IO **)a3);
    }
    else if ( a1 == 997 || !a1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl) )
      {
        v18 = *a3;
        KpsStartTimeoutTimer((struct _KPS_IO *)*a3);
        v18[10].Offset = 2;
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
        LODWORD(BytesReturneda) = 2088;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          a1,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          BytesReturneda);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3);
    }
    goto LABEL_52;
  }
  a1 = 8;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 110;
    LODWORD(BytesReturned) = 2040;
    goto LABEL_8;
  }
LABEL_53:
  if ( *a3 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_D(v6[2], 113, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, a1);
}

```

## disassembly

```asm
0x180020d0c  push    rbx
0x180020d0e  push    rsi
0x180020d0f  push    rdi
0x180020d10  push    r14
0x180020d12  push    r15
0x180020d14  sub     rsp, 60h
0x180020d18  mov     rax, cs:__security_cookie
0x180020d1f  xor     rax, rsp
0x180020d22  mov     [rsp+88h+var_38], rax
0x180020d27  mov     rdi, r8
0x180020d2a  mov     rbx, rdx
0x180020d2d  mov     esi, ecx
0x180020d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d36  lea     r14, WPP_GLOBAL_Control
0x180020d3d  cmp     rcx, r14
0x180020d40  jz      short loc_180020D69
0x180020d42  test    byte ptr [rcx+1Ch], 20h
0x180020d46  jz      short loc_180020D69
0x180020d48  mov     r9, [r8]
0x180020d4b  mov     edx, 69h ; 'i'
0x180020d50  mov     rcx, [rcx+10h]
0x180020d54  mov     [rsp+88h+BytesReturned], rbx; BytesReturned
0x180020d59  mov     [rsp+88h+EntityBufferLength], esi
0x180020d5d  call    WPP_SF_qDI
0x180020d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d69  lea     r15, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020d70  test    esi, esi
0x180020d72  jz      short loc_180020DB4
0x180020d74  cmp     rcx, r14
0x180020d77  jz      loc_18002109F
0x180020d7d  test    byte ptr [rcx+1Ch], 1
0x180020d81  jz      loc_18002109F
0x180020d87  mov     edx, 6Ah ; 'j'
0x180020d8c  mov     dword ptr [rsp+88h+BytesReturned], 7D4h
0x180020d94  mov     rcx, [rcx+10h]
0x180020d98  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180020d9f  mov     r9d, esi
0x180020da2  mov     qword ptr [rsp+88h+EntityBufferLength], rax
0x180020da7  mov     r8, r15
0x180020daa  call    WPP_SF_Dsd
0x180020daf  jmp     loc_180021098
0x180020db4  mov     rdx, [rdi]
0x180020db7  mov     r9d, [rdx+60h]
0x180020dbb  lea     eax, [rbx+r9]
0x180020dbf  cmp     eax, r9d
0x180020dc2  jb      loc_180021073
0x180020dc8  mov     r8d, cs:dword_18003A9C0
0x180020dcf  xor     esi, esi
0x180020dd1  cmp     eax, r8d
0x180020dd4  jbe     short loc_180020DF9
0x180020dd6  cmp     rcx, r14
0x180020dd9  jz      loc_18002109F
0x180020ddf  test    byte ptr [rcx+1Ch], 2
0x180020de3  jz      loc_18002109F
0x180020de9  lea     edx, [rsi+6Ch]
0x180020dec  mov     [rsp+88h+EntityBufferLength], r8d
0x180020df1  mov     r9d, eax
0x180020df4  jmp     loc_18002108C
0x180020df9  cmp     eax, [rdx+64h]
0x180020dfc  jnz     loc_180020EB4
0x180020e02  mov     [rdx+60h], eax
0x180020e05  mov     rcx, [rdi]
0x180020e08  mov     eax, [rcx+64h]
0x180020e0b  lea     edx, [rax+0C00h]
0x180020e11  cmp     edx, eax
0x180020e13  jb      short loc_180020E74
0x180020e15  mov     [rcx+64h], edx
0x180020e18  mov     rax, [rdi]
0x180020e1b  mov     ecx, [rax+64h]; unsigned __int64
0x180020e1e  mov     rdx, [rax+58h]; void *
0x180020e22  call    ?KpsReAllocMem@@YAPEAX_KPEAX@Z; KpsReAllocMem(unsigned __int64,void *)
0x180020e27  mov     rcx, rax
0x180020e2a  test    rax, rax
0x180020e2d  jnz     short loc_180020E5C
0x180020e2f  lea     esi, [rax+8]
0x180020e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e39  cmp     rcx, r14
0x180020e3c  jz      loc_18002109F
0x180020e42  test    byte ptr [rcx+1Ch], 1
0x180020e46  jz      loc_18002109F
0x180020e4c  lea     edx, [rax+6Eh]
0x180020e4f  mov     dword ptr [rsp+88h+BytesReturned], 7F8h
0x180020e57  jmp     loc_180020D94
0x180020e5c  mov     rax, [rdi]
0x180020e5f  mov     esi, 0C00h
0x180020e64  mov     [rax+58h], rcx
0x180020e68  mov     rax, [rdi]
0x180020e6b  mov     ebx, [rax+60h]
0x180020e6e  add     rbx, [rax+58h]
0x180020e72  jmp     short loc_180020ECE
0x180020e74  or      dword ptr [rcx+64h], 0FFFFFFFFh
0x180020e78  mov     esi, 0C0000095h
0x180020e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e84  cmp     rcx, r14
0x180020e87  jz      loc_18002109F
0x180020e8d  test    byte ptr [rcx+1Ch], 2
0x180020e91  jz      loc_18002109F
0x180020e97  mov     r9, [rdi]
0x180020e9a  mov     edx, 6Dh ; 'm'
0x180020e9f  mov     rcx, [rcx+10h]
0x180020ea3  mov     r8, r15
0x180020ea6  mov     r9d, [r9+64h]
0x180020eaa  call    WPP_SF_D
0x180020eaf  jmp     loc_180021098
0x180020eb4  jnb     loc_18002106C
0x180020eba  mov     [rdx+60h], eax
0x180020ebd  mov     rax, [rdi]
0x180020ec0  mov     ecx, [rax+60h]
0x180020ec3  mov     esi, [rax+64h]
0x180020ec6  mov     ebx, ecx
0x180020ec8  add     rbx, [rax+58h]
0x180020ecc  sub     esi, ecx
0x180020ece  mov     rcx, cs:pio; pio
0x180020ed5  call    cs:__imp_StartThreadpoolIo
0x180020edc  nop     dword ptr [rax+rax+00h]
0x180020ee1  mov     rcx, [rdi]
0x180020ee4  test    rcx, rcx
0x180020ee7  jz      short loc_180020F07
0x180020ee9  mov     eax, 1
0x180020eee  lock xadd [rcx+158h], rax
0x180020ef7  inc     rax
0x180020efa  cmp     rax, 1
0x180020efe  jg      short loc_180020F07
0x180020f00  mov     ecx, 0Eh
0x180020f05  int     29h; Win8: RtlFailFast(ecx)
0x180020f07  mov     rcx, [rdi]
0x180020f0a  mov     r9, rbx; EntityBuffer
0x180020f0d  mov     [rsp+88h+Overlapped], rcx; Overlapped
0x180020f12  xor     r8d, r8d; Flags
0x180020f15  and     [rsp+88h+BytesReturned], 0
0x180020f1b  mov     [rsp+88h+EntityBufferLength], esi; EntityBufferLength
0x180020f1f  mov     rax, [rcx+38h]
0x180020f23  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x180020f2a  mov     rdx, [rax+10h]; RequestId
0x180020f2e  call    cs:__imp_HttpReceiveRequestEntityBody
0x180020f35  nop     dword ptr [rax+rax+00h]
0x180020f3a  mov     esi, eax
0x180020f3c  cmp     eax, 26h ; '&'
0x180020f3f  jnz     short loc_180020FB6
0x180020f41  mov     rcx, cs:pio; pio
0x180020f48  call    cs:__imp_CancelThreadpoolIo
0x180020f4f  nop     dword ptr [rax+rax+00h]
0x180020f54  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 10h
0x180020f5b  jz      short loc_180020F77
0x180020f5d  lea     rax, [rsp+88h+var_48]
0x180020f62  lea     r9d, [rsi-25h]
0x180020f66  mov     qword ptr [rsp+88h+EntityBufferLength], rax
0x180020f6b  lea     rdx, HttpRequestReceived
0x180020f72  call    McGenEventWrite_EventWriteTransfer
0x180020f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f7e  cmp     rcx, r14
0x180020f81  jz      short loc_180020FA1
0x180020f83  test    byte ptr [rcx+1Ch], 4
0x180020f87  jz      short loc_180020FA1
0x180020f89  mov     r9, [rdi]
0x180020f8c  mov     edx, 6Fh ; 'o'
0x180020f91  mov     rcx, [rcx+10h]
0x180020f95  mov     r8, r15
0x180020f98  mov     r9d, [r9+60h]
0x180020f9c  call    WPP_SF_D
0x180020fa1  mov     rcx, rdi; this
0x180020fa4  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180020fa9  mov     rcx, rdi; struct KpsIoLockedRef *
0x180020fac  call    ?KpsProcessProxyRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsProcessProxyRequest(KpsIoLockedRef &)
0x180020fb1  jmp     loc_180021098
0x180020fb6  cmp     esi, 3E5h
0x180020fbc  jz      short loc_180021019
0x180020fbe  test    esi, esi
0x180020fc0  jz      short loc_180021019
0x180020fc2  mov     rcx, cs:pio; pio
0x180020fc9  call    cs:__imp_CancelThreadpoolIo
0x180020fd0  nop     dword ptr [rax+rax+00h]
0x180020fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fdc  cmp     rcx, r14
0x180020fdf  jz      short loc_18002100F
0x180020fe1  test    byte ptr [rcx+1Ch], 1
0x180020fe5  jz      short loc_18002100F
0x180020fe7  mov     rcx, [rcx+10h]
0x180020feb  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180020ff2  mov     edx, 70h ; 'p'
0x180020ff7  mov     dword ptr [rsp+88h+BytesReturned], 828h
0x180020fff  mov     r9d, esi
0x180021002  mov     qword ptr [rsp+88h+EntityBufferLength], rax
0x180021007  mov     r8, r15
0x18002100a  call    WPP_SF_Dsd
0x18002100f  mov     rcx, rdi; this
0x180021012  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180021017  jmp     short loc_180021098
0x180021019  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x180021020  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x180021025  test    al, al
0x180021027  jz      short loc_18002103E
0x180021029  mov     rbx, [rdi]
0x18002102c  mov     rcx, rbx; struct _KPS_IO *
0x18002102f  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x180021034  mov     dword ptr [rbx+150h], 2
0x18002103e  cmp     qword ptr [rdi], 0
0x180021042  jz      short loc_180021098
0x180021044  mov     rcx, rdi; this
0x180021047  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18002104c  test    al, al
0x18002104e  jnz     short loc_180021066
0x180021050  mov     rcx, [rdi]
0x180021053  add     rcx, 120h; CriticalSection
0x18002105a  call    cs:__imp_RtlLeaveCriticalSection
0x180021061  nop     dword ptr [rax+rax+00h]
0x180021066  and     qword ptr [rdi], 0
0x18002106a  jmp     short loc_180021098
0x18002106c  mov     esi, 54Fh
0x180021071  jmp     short loc_18002109F
0x180021073  mov     esi, 0C0000095h
0x180021078  cmp     rcx, r14
0x18002107b  jz      short loc_18002109F
0x18002107d  test    byte ptr [rcx+1Ch], 2
0x180021081  jz      short loc_18002109F
0x180021083  mov     edx, 6Bh ; 'k'
0x180021088  mov     [rsp+88h+EntityBufferLength], ebx
0x18002108c  mov     rcx, [rcx+10h]
0x180021090  mov     r8, r15
0x180021093  call    WPP_SF_dD
0x180021098  mov     rcx, cs:WPP_GLOBAL_Control
0x18002109f  cmp     qword ptr [rdi], 0
0x1800210a3  jz      short loc_1800210B4
0x1800210a5  mov     rcx, rdi; this
0x1800210a8  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x1800210ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210b4  cmp     rcx, r14
0x1800210b7  jz      short loc_1800210D3
0x1800210b9  test    byte ptr [rcx+1Ch], 20h
0x1800210bd  jz      short loc_1800210D3
0x1800210bf  mov     rcx, [rcx+10h]
0x1800210c3  mov     edx, 71h ; 'q'
0x1800210c8  mov     r9d, esi
0x1800210cb  mov     r8, r15
0x1800210ce  call    WPP_SF_D
0x1800210d3  mov     rcx, [rsp+88h+var_38]
0x1800210d8  xor     rcx, rsp; StackCookie
0x1800210db  call    __security_check_cookie
0x1800210e0  add     rsp, 60h
0x1800210e4  pop     r15
0x1800210e6  pop     r14
0x1800210e8  pop     rdi
0x1800210e9  pop     rsi
0x1800210ea  pop     rbx
0x1800210eb  retn
```
