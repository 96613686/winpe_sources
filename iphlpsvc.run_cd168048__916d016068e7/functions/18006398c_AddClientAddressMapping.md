# AddClientAddressMapping

- ea: `0x18006398c`
- end: `0x180063eab`
- name: `AddClientAddressMapping`
- size: `1311`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049bc8`
- `0x180066dd0`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x180049998`
- `0x18004a418`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x18006398c`
- `0x1800646b8`
- `0x18006478c`
- `0x180066630`
- `0x1800666f4`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x1800639e1`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063a71`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063acf`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063d1e`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800639e1`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063a71`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063acf`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063d1e`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063af2`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b13`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063af2`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b13`
- `ntdll!RtlInsertEntryHashTable` at `0x180063c9e`
- `ntdll!RtlInsertEntryHashTable` at `0x180063c9e`

## string_xrefs

- `0x180063a2f`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180063dd8`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
char __fastcall AddClientAddressMapping(__int64 a1, const struct in6_addr *a2, unsigned __int8 a3)
{
  __int64 v3; // rbx
  int v5; // r13d
  unsigned __int8 v7; // si
  _QWORD *v8; // r14
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rax
  _QWORD *v20; // r15
  __m128i v21; // xmm1
  unsigned __int64 v22; // xmm1_8
  unsigned __int64 v23; // r8
  __int64 v24; // rcx
  char inserted; // r14
  __int64 v26; // rcx
  int v27; // ecx
  const wchar_t *v28; // r8
  __int64 v29; // rax
  _QWORD *v30; // rcx
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+28h] [rbp-D8h]
  __int64 v35; // [rsp+28h] [rbp-D8h]
  __int64 v36; // [rsp+28h] [rbp-D8h]
  WCHAR S[72]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v38[72]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v5 = a3;
  v7 = 0;
  memset_0(S, 0, 0x82u);
  RtlIpv6AddressToStringW(a2, S);
  EventWrite0(
    0x10000000,
    L"%s: AddClientAddressMapping: For %s conflict = %i",
    *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
    S,
    v5);
  v8 = (_QWORD *)(a1 + 16);
  v9 = *(_QWORD **)(a1 + 16);
  while ( v9 != v8 )
  {
    v9 = (_QWORD *)*v9;
    ++v7;
  }
  if ( v7 == *(_DWORD *)(v3 + 24) )
  {
    *(_BYTE *)(a1 + 32) = 1;
    v10 = *(_QWORD **)(a1 + 24);
    if ( (_QWORD *)*v10 != v8 )
      goto LABEL_42;
    v11 = (_QWORD *)v10[1];
    if ( (_QWORD *)*v11 != v10 )
      goto LABEL_42;
    *(_QWORD *)(a1 + 24) = v11;
    v12 = v10 - 6;
    *v11 = v8;
    RtlIpv6AddressToStringW((const struct in6_addr *)(v12 + 3), S);
    EventWrite0(
      0x10000000,
      L"%s: AddClientAddressMapping: Reclaimed the mapping entry for %s",
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
      S);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v13,
        EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING,
        *(_QWORD *)(v3 + 288) + 56LL,
        S);
    RtlIpv6AddressToStringW(a2, S);
    if ( (v12[2] & 0x40000000) != 0 )
    {
      RtlRemoveEntryHashTable(v3 + 184, v12, 0);
      IpTlsRemoveConflictEntries(v3, v12 + 3);
    }
    else
    {
      RtlRemoveEntryHashTable(v3 + 104, v12, 0);
    }
LABEL_21:
    *(struct in6_addr *)(v12 + 3) = *a2;
    v19 = *v8;
    if ( *(_QWORD **)(*v8 + 8LL) == v8 )
    {
      v20 = v12 + 6;
      v12[6] = v19;
      v12[7] = v8;
      *(_QWORD *)(v19 + 8) = v12 + 6;
      *v8 = v12 + 6;
      v21 = _mm_loadu_si128((const __m128i *)a2);
      v22 = v21.m128i_i64[0] ^ _mm_srli_si128(v21, 8).m128i_u64[0];
      if ( (_BYTE)v5 )
      {
        v23 = v22 | 0xC0000000;
        v24 = v3 + 184;
      }
      else
      {
        v23 = v22 & 0xFFFFFFFF3FFFFFFFuLL | 0x80000000;
        v24 = v3 + 104;
      }
      inserted = RtlInsertEntryHashTable(v24, v12, v23, 0);
      if ( inserted )
      {
        LODWORD(v33) = v5;
        EventWrite0(
          0x10000000,
          L"%s: AddClientAddressMapping: Success for %s conflict = %i",
          *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
          S,
          v33);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v26,
            EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING,
            *(_QWORD *)(v3 + 288) + 56LL,
            S);
        if ( (_BYTE)v5 )
        {
          IpTlsRemoveConflictEntries(v3, v3 + 16LL * *(unsigned int *)(v3 + 772) + 372);
          *(struct in6_addr *)(v3 + 16LL * *(unsigned int *)(v3 + 772) + 372) = *a2;
          *(_DWORD *)(v3 + 772) = (*(_DWORD *)(v3 + 772) + 1) % 0x19u;
        }
        else
        {
          IpTlsUpdatePerfCountersForClient(a1);
          v38[0] = 0;
          RtlIpv6AddressToStringW(a2, v38);
          if ( (Microsoft_Windows_IphlpsvcEnableBits & 4) != 0 )
          {
            v28 = L"Unknown";
            if ( *(_QWORD *)(a1 + 112) )
              v28 = *(const wchar_t **)(a1 + 112);
            McTemplateU0zzz_EventWriteTransfer(
              v27,
              (unsigned int)EVENT_IPHLPSVC_IPHTTPS_CLIENT_CONNECTED,
              (_DWORD)v28,
              a1 + 124,
              (__int64)v38);
          }
        }
        return inserted;
      }
      v29 = *v20;
      if ( *(_QWORD **)(*v20 + 8LL) == v20 )
      {
        v30 = (_QWORD *)v12[7];
        if ( (_QWORD *)*v30 == v20 )
        {
          *v30 = v29;
          *(_QWORD *)(v29 + 8) = v30;
          LODWORD(v34) = 943;
          EventWrite0(
            0x20000000,
            L"(%s: Dereference Server interface(%p) %S:%d",
            *(_QWORD *)(v3 + 288) + 56LL,
            v3,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            v34);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v31,
              (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE,
              v3,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              175);
          DereferenceServerInterfaceEx(v3);
          LODWORD(v36) = 944;
          EventWrite0(
            0x20000000,
            L"(%s: Dereference client context (%p) %S:%d",
            *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
            a1,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            v36);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v32,
              (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
              a1,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              176);
          DereferenceClientContextEx(a1);
          FREE(v12);
          return inserted;
        }
      }
    }
LABEL_42:
    __fastfail(3u);
  }
  v14 = MALLOC(0x40u);
  v12 = (_QWORD *)v14;
  if ( v14 )
  {
    *(_QWORD *)(v14 + 40) = a1;
    EventWrite0(
      0x20000000,
      L"(%s: Reference Server interface(%p)%S:%d",
      *(_QWORD *)(v3 + 288) + 56LL,
      v3,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      877);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v17,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE,
        v3,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        109);
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 280));
    LODWORD(v35) = 878;
    EventWrite0(
      0x20000000,
      L"(%s: Reference client context (%p)%S:%d",
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
      a1,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v35);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v18,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
        a1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        110);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 56));
    goto LABEL_21;
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v15,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
      0,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      104);
  return 0;
}

```

## disassembly

```asm
0x18006398c  mov     [rsp-8+arg_18], rbx
0x180063991  push    rbp
0x180063992  push    rsi
0x180063993  push    rdi
0x180063994  push    r12
0x180063996  push    r13
0x180063998  push    r14
0x18006399a  push    r15
0x18006399c  lea     rbp, [rsp-60h]
0x1800639a1  sub     rsp, 160h
0x1800639a8  mov     rax, cs:__security_cookie
0x1800639af  xor     rax, rsp
0x1800639b2  mov     [rbp+90h+var_40], rax
0x1800639b6  mov     rbx, [rcx+28h]
0x1800639ba  mov     r12, rdx
0x1800639bd  movzx   r13d, r8b
0x1800639c1  mov     rdi, rcx
0x1800639c4  xor     edx, edx; Val
0x1800639c6  lea     rcx, [rsp+190h+S]; void *
0x1800639cb  mov     r8d, 82h; Size
0x1800639d1  xor     sil, sil
0x1800639d4  call    memset_0
0x1800639d9  lea     rdx, [rsp+190h+S]; S
0x1800639de  mov     rcx, r12; Addr
0x1800639e1  call    cs:__imp_RtlIpv6AddressToStringW
0x1800639e8  nop     dword ptr [rax+rax+00h]
0x1800639ed  mov     rax, [rdi+28h]
0x1800639f1  lea     r9, [rsp+190h+S]
0x1800639f6  lea     rdx, aSAddclientaddr_0; "%s: AddClientAddressMapping: For %s con"...
0x1800639fd  mov     dword ptr [rsp+190h+var_170], r13d
0x180063a02  mov     ecx, 10000000h
0x180063a07  mov     r8, [rax+120h]
0x180063a0e  add     r8, 38h ; '8'
0x180063a12  call    EventWrite0
0x180063a17  lea     r14, [rdi+10h]
0x180063a1b  mov     rax, [r14]
0x180063a1e  jmp     short loc_180063A26
0x180063a20  mov     rax, [rax]
0x180063a23  inc     sil
0x180063a26  cmp     rax, r14
0x180063a29  jnz     short loc_180063A20
0x180063a2b  movzx   eax, sil
0x180063a2f  lea     r15, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063a36  cmp     eax, [rbx+18h]
0x180063a39  jnz     loc_180063B24
0x180063a3f  mov     byte ptr [rdi+20h], 1
0x180063a43  mov     rsi, [r14+8]
0x180063a47  cmp     [rsi], r14
0x180063a4a  jnz     loc_180063EA4
0x180063a50  mov     rax, [rsi+8]
0x180063a54  cmp     [rax], rsi
0x180063a57  jnz     loc_180063EA4
0x180063a5d  mov     [r14+8], rax
0x180063a61  lea     rdx, [rsp+190h+S]; S
0x180063a66  add     rsi, 0FFFFFFFFFFFFFFD0h
0x180063a6a  mov     [rax], r14
0x180063a6d  lea     rcx, [rsi+18h]; Addr
0x180063a71  call    cs:__imp_RtlIpv6AddressToStringW
0x180063a78  nop     dword ptr [rax+rax+00h]
0x180063a7d  mov     rax, [rdi+28h]
0x180063a81  lea     r9, [rsp+190h+S]
0x180063a86  lea     rdx, aSAddclientaddr_1; "%s: AddClientAddressMapping: Reclaimed "...
0x180063a8d  mov     ecx, 10000000h
0x180063a92  mov     r8, [rax+120h]
0x180063a99  add     r8, 38h ; '8'
0x180063a9d  call    EventWrite0
0x180063aa2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180063aa9  jz      short loc_180063AC7
0x180063aab  mov     r8, [rbx+120h]
0x180063ab2  lea     r9, [rsp+190h+S]
0x180063ab7  add     r8, 38h ; '8'
0x180063abb  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x180063ac2  call    McTemplateU0zz_EventWriteTransfer
0x180063ac7  lea     rdx, [rsp+190h+S]; S
0x180063acc  mov     rcx, r12; Addr
0x180063acf  call    cs:__imp_RtlIpv6AddressToStringW
0x180063ad6  nop     dword ptr [rax+rax+00h]
0x180063adb  mov     eax, [rsi+10h]
0x180063ade  xor     r8d, r8d
0x180063ae1  mov     rdx, rsi
0x180063ae4  bt      rax, 1Eh
0x180063ae9  jnb     short loc_180063B0F
0x180063aeb  lea     rcx, [rbx+0B8h]
0x180063af2  call    cs:__imp_RtlRemoveEntryHashTable
0x180063af9  nop     dword ptr [rax+rax+00h]
0x180063afe  lea     rdx, [rsi+18h]
0x180063b02  mov     rcx, rbx
0x180063b05  call    IpTlsRemoveConflictEntries
0x180063b0a  jmp     loc_180063C34
0x180063b0f  lea     rcx, [rbx+68h]
0x180063b13  call    cs:__imp_RtlRemoveEntryHashTable
0x180063b1a  nop     dword ptr [rax+rax+00h]
0x180063b1f  jmp     loc_180063C34
0x180063b24  mov     ecx, 40h ; '@'; dwBytes
0x180063b29  call    MALLOC
0x180063b2e  mov     rsi, rax
0x180063b31  test    rax, rax
0x180063b34  jnz     short loc_180063B83
0x180063b36  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180063b3d  jz      short loc_180063B59
0x180063b3f  mov     r9, r15
0x180063b42  mov     dword ptr [rsp+190h+var_170], 368h
0x180063b4a  xor     r8d, r8d
0x180063b4d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180063b54  call    McTemplateU0psq_EventWriteTransfer
0x180063b59  xor     al, al
0x180063b5b  mov     rcx, [rbp+90h+var_40]
0x180063b5f  xor     rcx, rsp; StackCookie
0x180063b62  call    __security_check_cookie
0x180063b67  mov     rbx, [rsp+190h+arg_18]
0x180063b6f  add     rsp, 160h
0x180063b76  pop     r15
0x180063b78  pop     r14
0x180063b7a  pop     r13
0x180063b7c  pop     r12
0x180063b7e  pop     rdi
0x180063b7f  pop     rsi
0x180063b80  pop     rbp
0x180063b81  retn
0x180063b83  mov     [rax+28h], rdi
0x180063b87  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180063b8e  mov     r8, [rbx+120h]
0x180063b95  mov     r9, rbx
0x180063b98  add     r8, 38h ; '8'
0x180063b9c  mov     dword ptr [rsp+190h+var_168], 36Dh
0x180063ba4  mov     ecx, 20000000h
0x180063ba9  mov     [rsp+190h+var_170], r15
0x180063bae  call    EventWrite0
0x180063bb3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063bba  jz      short loc_180063BD6
0x180063bbc  mov     r9, r15
0x180063bbf  mov     dword ptr [rsp+190h+var_170], 36Dh
0x180063bc7  mov     r8, rbx
0x180063bca  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x180063bd1  call    McTemplateU0psq_EventWriteTransfer
0x180063bd6  lock inc dword ptr [rbx+118h]
0x180063bdd  mov     rax, [rdi+28h]
0x180063be1  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180063be8  mov     dword ptr [rsp+190h+var_168], 36Eh
0x180063bf0  mov     r9, rdi
0x180063bf3  mov     ecx, 20000000h
0x180063bf8  mov     [rsp+190h+var_170], r15
0x180063bfd  mov     r8, [rax+120h]
0x180063c04  add     r8, 38h ; '8'
0x180063c08  call    EventWrite0
0x180063c0d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063c14  jz      short loc_180063C30
0x180063c16  mov     r9, r15
0x180063c19  mov     dword ptr [rsp+190h+var_170], 36Eh
0x180063c21  mov     r8, rdi
0x180063c24  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180063c2b  call    McTemplateU0psq_EventWriteTransfer
0x180063c30  lock inc dword ptr [rdi+38h]
0x180063c34  movups  xmm0, xmmword ptr [r12]
0x180063c39  movdqu  xmmword ptr [rsi+18h], xmm0
0x180063c3e  mov     rax, [r14]
0x180063c41  cmp     [rax+8], r14
0x180063c45  jnz     loc_180063EA4
0x180063c4b  lea     r15, [rsi+30h]
0x180063c4f  xor     r9d, r9d
0x180063c52  mov     [r15], rax
0x180063c55  mov     rdx, rsi
0x180063c58  mov     [r15+8], r14
0x180063c5c  mov     [rax+8], r15
0x180063c60  mov     eax, 80000000h
0x180063c65  mov     [r14], r15
0x180063c68  movdqu  xmm1, xmmword ptr [r12]
0x180063c6e  movdqa  xmm0, xmm1
0x180063c72  psrldq  xmm0, 8
0x180063c77  xorps   xmm1, xmm0
0x180063c7a  movq    r8, xmm1
0x180063c7f  or      r8, rax
0x180063c82  test    r13b, r13b
0x180063c85  jz      short loc_180063C95
0x180063c87  bts     r8, 1Eh
0x180063c8c  lea     rcx, [rbx+0B8h]
0x180063c93  jmp     short loc_180063C9E
0x180063c95  btr     r8, 1Eh
0x180063c9a  lea     rcx, [rbx+68h]
0x180063c9e  call    cs:__imp_RtlInsertEntryHashTable
0x180063ca5  nop     dword ptr [rax+rax+00h]
0x180063caa  mov     r14b, al
0x180063cad  test    al, al
0x180063caf  jz      loc_180063DBB
0x180063cb5  mov     rax, [rdi+28h]
0x180063cb9  lea     r9, [rsp+190h+S]
0x180063cbe  lea     rdx, aSAddclientaddr; "%s: AddClientAddressMapping: Success fo"...
0x180063cc5  mov     dword ptr [rsp+190h+var_170], r13d
0x180063cca  mov     ecx, 10000000h
0x180063ccf  mov     r8, [rax+120h]
0x180063cd6  add     r8, 38h ; '8'
0x180063cda  call    EventWrite0
0x180063cdf  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180063ce6  jz      short loc_180063D04
0x180063ce8  mov     r8, [rbx+120h]
0x180063cef  lea     r9, [rsp+190h+S]
0x180063cf4  add     r8, 38h ; '8'
0x180063cf8  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING
0x180063cff  call    McTemplateU0zz_EventWriteTransfer
0x180063d04  test    r13b, r13b
0x180063d07  jnz     short loc_180063D66
0x180063d09  mov     rcx, rdi
0x180063d0c  call    IpTlsUpdatePerfCountersForClient
0x180063d11  xor     eax, eax
0x180063d13  lea     rdx, [rbp+90h+var_D0]; S
0x180063d17  mov     rcx, r12; Addr
0x180063d1a  mov     [rbp+90h+var_D0], ax
0x180063d1e  call    cs:__imp_RtlIpv6AddressToStringW
0x180063d25  nop     dword ptr [rax+rax+00h]
0x180063d2a  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 4
0x180063d31  jz      loc_180063E9C
0x180063d37  cmp     qword ptr [rdi+70h], 0
0x180063d3c  lea     rax, [rbp+90h+var_D0]
0x180063d40  lea     r8, aUnknown; "Unknown"
0x180063d47  mov     [rsp+190h+var_170], rax
0x180063d4c  cmovnz  r8, [rdi+70h]
0x180063d51  lea     r9, [rdi+7Ch]
0x180063d55  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_CLIENT_CONNECTED
0x180063d5c  call    McTemplateU0zzz_EventWriteTransfer
0x180063d61  jmp     loc_180063E9C
0x180063d66  mov     edx, [rbx+304h]
0x180063d6c  mov     rcx, rbx
0x180063d6f  shl     rdx, 4
0x180063d73  add     rdx, 174h
0x180063d7a  add     rdx, rbx
0x180063d7d  call    IpTlsRemoveConflictEntries
0x180063d82  mov     eax, [rbx+304h]
0x180063d88  movups  xmm0, xmmword ptr [r12]
0x180063d8d  add     rax, rax
0x180063d90  movdqu  xmmword ptr [rbx+rax*8+174h], xmm0
0x180063d99  mov     ecx, [rbx+304h]
0x180063d9f  mov     eax, 51EB851Fh
0x180063da4  inc     ecx
0x180063da6  mul     ecx
0x180063da8  shr     edx, 3
0x180063dab  imul    eax, edx, 19h
0x180063dae  sub     ecx, eax
0x180063db0  mov     [rbx+304h], ecx
0x180063db6  jmp     loc_180063E9C
0x180063dbb  mov     rax, [r15]
0x180063dbe  cmp     [rax+8], r15
0x180063dc2  jnz     loc_180063EA4
0x180063dc8  mov     rcx, [r15+8]
0x180063dcc  cmp     [rcx], r15
0x180063dcf  jnz     loc_180063EA4
0x180063dd5  mov     [rcx], rax
0x180063dd8  lea     r15, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063ddf  mov     [rax+8], rcx
0x180063de3  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x180063dea  mov     r8, [rbx+120h]
0x180063df1  mov     r12d, 3AFh
0x180063df7  mov     r13d, 20000000h
0x180063dfd  mov     dword ptr [rsp+190h+var_168], r12d
0x180063e02  add     r8, 38h ; '8'
0x180063e06  mov     [rsp+190h+var_170], r15
0x180063e0b  mov     r9, rbx
0x180063e0e  mov     ecx, r13d
0x180063e11  call    EventWrite0
0x180063e16  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063e1d  jz      short loc_180063E36
0x180063e1f  mov     r9, r15
0x180063e22  mov     dword ptr [rsp+190h+var_170], r12d
0x180063e27  mov     r8, rbx
0x180063e2a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x180063e31  call    McTemplateU0psq_EventWriteTransfer
0x180063e36  mov     rcx, rbx
0x180063e39  call    DereferenceServerInterfaceEx
0x180063e3e  mov     rax, [rdi+28h]
0x180063e42  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x180063e49  mov     ebx, 3B0h
0x180063e4e  mov     r9, rdi
0x180063e51  mov     dword ptr [rsp+190h+var_168], ebx
0x180063e55  mov     ecx, r13d
0x180063e58  mov     [rsp+190h+var_170], r15
0x180063e5d  mov     r8, [rax+120h]
0x180063e64  add     r8, 38h ; '8'
0x180063e68  call    EventWrite0
0x180063e6d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063e74  jz      short loc_180063E8C
0x180063e76  mov     r9, r15
0x180063e79  mov     dword ptr [rsp+190h+var_170], ebx
0x180063e7d  mov     r8, rdi
0x180063e80  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x180063e87  call    McTemplateU0psq_EventWriteTransfer
0x180063e8c  mov     rcx, rdi
0x180063e8f  call    DereferenceClientContextEx
0x180063e94  mov     rcx, rsi
0x180063e97  call    FREE
0x180063e9c  mov     al, r14b
0x180063e9f  jmp     loc_180063B5B
0x180063ea4  mov     ecx, 3
0x180063ea9  int     29h; Win8: RtlFailFast(ecx)
```
