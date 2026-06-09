# AddClientAddressMapping

- ea: `0x1800639ac`
- end: `0x180063ecb`
- name: `AddClientAddressMapping`
- size: `1311`
- prototype: `char __fastcall(__int64, const struct in6_addr *, unsigned __int8)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049b88`
- `0x180066df0`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x180049958`
- `0x18004a3d8`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x1800639ac`
- `0x1800646d8`
- `0x1800647ac`
- `0x180066650`
- `0x180066714`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180063a01`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063a91`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063aef`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063d3e`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063a01`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063a91`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063aef`
- `ntdll!RtlIpv6AddressToStringW` at `0x180063d3e`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b12`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b33`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b12`
- `ntdll!RtlRemoveEntryHashTable` at `0x180063b33`
- `ntdll!RtlInsertEntryHashTable` at `0x180063cbe`
- `ntdll!RtlInsertEntryHashTable` at `0x180063cbe`

## string_xrefs

- `0x180063a4f`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180063df8`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
0x1800639ac  mov     [rsp-8+arg_18], rbx
0x1800639b1  push    rbp
0x1800639b2  push    rsi
0x1800639b3  push    rdi
0x1800639b4  push    r12
0x1800639b6  push    r13
0x1800639b8  push    r14
0x1800639ba  push    r15
0x1800639bc  lea     rbp, [rsp-60h]
0x1800639c1  sub     rsp, 160h
0x1800639c8  mov     rax, cs:__security_cookie
0x1800639cf  xor     rax, rsp
0x1800639d2  mov     [rbp+90h+var_40], rax
0x1800639d6  mov     rbx, [rcx+28h]
0x1800639da  mov     r12, rdx
0x1800639dd  movzx   r13d, r8b
0x1800639e1  mov     rdi, rcx
0x1800639e4  xor     edx, edx; Val
0x1800639e6  lea     rcx, [rsp+190h+S]; void *
0x1800639eb  mov     r8d, 82h; Size
0x1800639f1  xor     sil, sil
0x1800639f4  call    memset_0
0x1800639f9  lea     rdx, [rsp+190h+S]; S
0x1800639fe  mov     rcx, r12; Addr
0x180063a01  call    cs:__imp_RtlIpv6AddressToStringW
0x180063a08  nop     dword ptr [rax+rax+00h]
0x180063a0d  mov     rax, [rdi+28h]
0x180063a11  lea     r9, [rsp+190h+S]
0x180063a16  lea     rdx, aSAddclientaddr_0; "%s: AddClientAddressMapping: For %s con"...
0x180063a1d  mov     dword ptr [rsp+190h+var_170], r13d
0x180063a22  mov     ecx, 10000000h
0x180063a27  mov     r8, [rax+120h]
0x180063a2e  add     r8, 38h ; '8'
0x180063a32  call    EventWrite0
0x180063a37  lea     r14, [rdi+10h]
0x180063a3b  mov     rax, [r14]
0x180063a3e  jmp     short loc_180063A46
0x180063a40  mov     rax, [rax]
0x180063a43  inc     sil
0x180063a46  cmp     rax, r14
0x180063a49  jnz     short loc_180063A40
0x180063a4b  movzx   eax, sil
0x180063a4f  lea     r15, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063a56  cmp     eax, [rbx+18h]
0x180063a59  jnz     loc_180063B44
0x180063a5f  mov     byte ptr [rdi+20h], 1
0x180063a63  mov     rsi, [r14+8]
0x180063a67  cmp     [rsi], r14
0x180063a6a  jnz     loc_180063EC4
0x180063a70  mov     rax, [rsi+8]
0x180063a74  cmp     [rax], rsi
0x180063a77  jnz     loc_180063EC4
0x180063a7d  mov     [r14+8], rax
0x180063a81  lea     rdx, [rsp+190h+S]; S
0x180063a86  add     rsi, 0FFFFFFFFFFFFFFD0h
0x180063a8a  mov     [rax], r14
0x180063a8d  lea     rcx, [rsi+18h]; Addr
0x180063a91  call    cs:__imp_RtlIpv6AddressToStringW
0x180063a98  nop     dword ptr [rax+rax+00h]
0x180063a9d  mov     rax, [rdi+28h]
0x180063aa1  lea     r9, [rsp+190h+S]
0x180063aa6  lea     rdx, aSAddclientaddr_1; "%s: AddClientAddressMapping: Reclaimed "...
0x180063aad  mov     ecx, 10000000h
0x180063ab2  mov     r8, [rax+120h]
0x180063ab9  add     r8, 38h ; '8'
0x180063abd  call    EventWrite0
0x180063ac2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180063ac9  jz      short loc_180063AE7
0x180063acb  mov     r8, [rbx+120h]
0x180063ad2  lea     r9, [rsp+190h+S]
0x180063ad7  add     r8, 38h ; '8'
0x180063adb  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x180063ae2  call    McTemplateU0zz_EventWriteTransfer
0x180063ae7  lea     rdx, [rsp+190h+S]; S
0x180063aec  mov     rcx, r12; Addr
0x180063aef  call    cs:__imp_RtlIpv6AddressToStringW
0x180063af6  nop     dword ptr [rax+rax+00h]
0x180063afb  mov     eax, [rsi+10h]
0x180063afe  xor     r8d, r8d
0x180063b01  mov     rdx, rsi
0x180063b04  bt      rax, 1Eh
0x180063b09  jnb     short loc_180063B2F
0x180063b0b  lea     rcx, [rbx+0B8h]
0x180063b12  call    cs:__imp_RtlRemoveEntryHashTable
0x180063b19  nop     dword ptr [rax+rax+00h]
0x180063b1e  lea     rdx, [rsi+18h]
0x180063b22  mov     rcx, rbx
0x180063b25  call    IpTlsRemoveConflictEntries
0x180063b2a  jmp     loc_180063C54
0x180063b2f  lea     rcx, [rbx+68h]
0x180063b33  call    cs:__imp_RtlRemoveEntryHashTable
0x180063b3a  nop     dword ptr [rax+rax+00h]
0x180063b3f  jmp     loc_180063C54
0x180063b44  mov     ecx, 40h ; '@'; dwBytes
0x180063b49  call    MALLOC
0x180063b4e  mov     rsi, rax
0x180063b51  test    rax, rax
0x180063b54  jnz     short loc_180063BA3
0x180063b56  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180063b5d  jz      short loc_180063B79
0x180063b5f  mov     r9, r15
0x180063b62  mov     dword ptr [rsp+190h+var_170], 368h
0x180063b6a  xor     r8d, r8d
0x180063b6d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180063b74  call    McTemplateU0psq_EventWriteTransfer
0x180063b79  xor     al, al
0x180063b7b  mov     rcx, [rbp+90h+var_40]
0x180063b7f  xor     rcx, rsp; StackCookie
0x180063b82  call    __security_check_cookie
0x180063b87  mov     rbx, [rsp+190h+arg_18]
0x180063b8f  add     rsp, 160h
0x180063b96  pop     r15
0x180063b98  pop     r14
0x180063b9a  pop     r13
0x180063b9c  pop     r12
0x180063b9e  pop     rdi
0x180063b9f  pop     rsi
0x180063ba0  pop     rbp
0x180063ba1  retn
0x180063ba3  mov     [rax+28h], rdi
0x180063ba7  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180063bae  mov     r8, [rbx+120h]
0x180063bb5  mov     r9, rbx
0x180063bb8  add     r8, 38h ; '8'
0x180063bbc  mov     dword ptr [rsp+190h+var_168], 36Dh
0x180063bc4  mov     ecx, 20000000h
0x180063bc9  mov     [rsp+190h+var_170], r15
0x180063bce  call    EventWrite0
0x180063bd3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063bda  jz      short loc_180063BF6
0x180063bdc  mov     r9, r15
0x180063bdf  mov     dword ptr [rsp+190h+var_170], 36Dh
0x180063be7  mov     r8, rbx
0x180063bea  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x180063bf1  call    McTemplateU0psq_EventWriteTransfer
0x180063bf6  lock inc dword ptr [rbx+118h]
0x180063bfd  mov     rax, [rdi+28h]
0x180063c01  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180063c08  mov     dword ptr [rsp+190h+var_168], 36Eh
0x180063c10  mov     r9, rdi
0x180063c13  mov     ecx, 20000000h
0x180063c18  mov     [rsp+190h+var_170], r15
0x180063c1d  mov     r8, [rax+120h]
0x180063c24  add     r8, 38h ; '8'
0x180063c28  call    EventWrite0
0x180063c2d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063c34  jz      short loc_180063C50
0x180063c36  mov     r9, r15
0x180063c39  mov     dword ptr [rsp+190h+var_170], 36Eh
0x180063c41  mov     r8, rdi
0x180063c44  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180063c4b  call    McTemplateU0psq_EventWriteTransfer
0x180063c50  lock inc dword ptr [rdi+38h]
0x180063c54  movups  xmm0, xmmword ptr [r12]
0x180063c59  movdqu  xmmword ptr [rsi+18h], xmm0
0x180063c5e  mov     rax, [r14]
0x180063c61  cmp     [rax+8], r14
0x180063c65  jnz     loc_180063EC4
0x180063c6b  lea     r15, [rsi+30h]
0x180063c6f  xor     r9d, r9d
0x180063c72  mov     [r15], rax
0x180063c75  mov     rdx, rsi
0x180063c78  mov     [r15+8], r14
0x180063c7c  mov     [rax+8], r15
0x180063c80  mov     eax, 80000000h
0x180063c85  mov     [r14], r15
0x180063c88  movdqu  xmm1, xmmword ptr [r12]
0x180063c8e  movdqa  xmm0, xmm1
0x180063c92  psrldq  xmm0, 8
0x180063c97  xorps   xmm1, xmm0
0x180063c9a  movq    r8, xmm1
0x180063c9f  or      r8, rax
0x180063ca2  test    r13b, r13b
0x180063ca5  jz      short loc_180063CB5
0x180063ca7  bts     r8, 1Eh
0x180063cac  lea     rcx, [rbx+0B8h]
0x180063cb3  jmp     short loc_180063CBE
0x180063cb5  btr     r8, 1Eh
0x180063cba  lea     rcx, [rbx+68h]
0x180063cbe  call    cs:__imp_RtlInsertEntryHashTable
0x180063cc5  nop     dword ptr [rax+rax+00h]
0x180063cca  mov     r14b, al
0x180063ccd  test    al, al
0x180063ccf  jz      loc_180063DDB
0x180063cd5  mov     rax, [rdi+28h]
0x180063cd9  lea     r9, [rsp+190h+S]
0x180063cde  lea     rdx, aSAddclientaddr; "%s: AddClientAddressMapping: Success fo"...
0x180063ce5  mov     dword ptr [rsp+190h+var_170], r13d
0x180063cea  mov     ecx, 10000000h
0x180063cef  mov     r8, [rax+120h]
0x180063cf6  add     r8, 38h ; '8'
0x180063cfa  call    EventWrite0
0x180063cff  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180063d06  jz      short loc_180063D24
0x180063d08  mov     r8, [rbx+120h]
0x180063d0f  lea     r9, [rsp+190h+S]
0x180063d14  add     r8, 38h ; '8'
0x180063d18  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING
0x180063d1f  call    McTemplateU0zz_EventWriteTransfer
0x180063d24  test    r13b, r13b
0x180063d27  jnz     short loc_180063D86
0x180063d29  mov     rcx, rdi
0x180063d2c  call    IpTlsUpdatePerfCountersForClient
0x180063d31  xor     eax, eax
0x180063d33  lea     rdx, [rbp+90h+var_D0]; S
0x180063d37  mov     rcx, r12; Addr
0x180063d3a  mov     [rbp+90h+var_D0], ax
0x180063d3e  call    cs:__imp_RtlIpv6AddressToStringW
0x180063d45  nop     dword ptr [rax+rax+00h]
0x180063d4a  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 4
0x180063d51  jz      loc_180063EBC
0x180063d57  cmp     qword ptr [rdi+70h], 0
0x180063d5c  lea     rax, [rbp+90h+var_D0]
0x180063d60  lea     r8, aUnknown; "Unknown"
0x180063d67  mov     [rsp+190h+var_170], rax
0x180063d6c  cmovnz  r8, [rdi+70h]
0x180063d71  lea     r9, [rdi+7Ch]
0x180063d75  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_CLIENT_CONNECTED
0x180063d7c  call    McTemplateU0zzz_EventWriteTransfer
0x180063d81  jmp     loc_180063EBC
0x180063d86  mov     edx, [rbx+304h]
0x180063d8c  mov     rcx, rbx
0x180063d8f  shl     rdx, 4
0x180063d93  add     rdx, 174h
0x180063d9a  add     rdx, rbx
0x180063d9d  call    IpTlsRemoveConflictEntries
0x180063da2  mov     eax, [rbx+304h]
0x180063da8  movups  xmm0, xmmword ptr [r12]
0x180063dad  add     rax, rax
0x180063db0  movdqu  xmmword ptr [rbx+rax*8+174h], xmm0
0x180063db9  mov     ecx, [rbx+304h]
0x180063dbf  mov     eax, 51EB851Fh
0x180063dc4  inc     ecx
0x180063dc6  mul     ecx
0x180063dc8  shr     edx, 3
0x180063dcb  imul    eax, edx, 19h
0x180063dce  sub     ecx, eax
0x180063dd0  mov     [rbx+304h], ecx
0x180063dd6  jmp     loc_180063EBC
0x180063ddb  mov     rax, [r15]
0x180063dde  cmp     [rax+8], r15
0x180063de2  jnz     loc_180063EC4
0x180063de8  mov     rcx, [r15+8]
0x180063dec  cmp     [rcx], r15
0x180063def  jnz     loc_180063EC4
0x180063df5  mov     [rcx], rax
0x180063df8  lea     r15, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063dff  mov     [rax+8], rcx
0x180063e03  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x180063e0a  mov     r8, [rbx+120h]
0x180063e11  mov     r12d, 3AFh
0x180063e17  mov     r13d, 20000000h
0x180063e1d  mov     dword ptr [rsp+190h+var_168], r12d
0x180063e22  add     r8, 38h ; '8'
0x180063e26  mov     [rsp+190h+var_170], r15
0x180063e2b  mov     r9, rbx
0x180063e2e  mov     ecx, r13d
0x180063e31  call    EventWrite0
0x180063e36  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063e3d  jz      short loc_180063E56
0x180063e3f  mov     r9, r15
0x180063e42  mov     dword ptr [rsp+190h+var_170], r12d
0x180063e47  mov     r8, rbx
0x180063e4a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x180063e51  call    McTemplateU0psq_EventWriteTransfer
0x180063e56  mov     rcx, rbx
0x180063e59  call    DereferenceServerInterfaceEx
0x180063e5e  mov     rax, [rdi+28h]
0x180063e62  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x180063e69  mov     ebx, 3B0h
0x180063e6e  mov     r9, rdi
0x180063e71  mov     dword ptr [rsp+190h+var_168], ebx
0x180063e75  mov     ecx, r13d
0x180063e78  mov     [rsp+190h+var_170], r15
0x180063e7d  mov     r8, [rax+120h]
0x180063e84  add     r8, 38h ; '8'
0x180063e88  call    EventWrite0
0x180063e8d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063e94  jz      short loc_180063EAC
0x180063e96  mov     r9, r15
0x180063e99  mov     dword ptr [rsp+190h+var_170], ebx
0x180063e9d  mov     r8, rdi
0x180063ea0  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x180063ea7  call    McTemplateU0psq_EventWriteTransfer
0x180063eac  mov     rcx, rdi
0x180063eaf  call    DereferenceClientContextEx
0x180063eb4  mov     rcx, rsi
0x180063eb7  call    FREE
0x180063ebc  mov     al, r14b
0x180063ebf  jmp     loc_180063B7B
0x180063ec4  mov     ecx, 3
0x180063ec9  int     29h; Win8: RtlFailFast(ecx)
```
