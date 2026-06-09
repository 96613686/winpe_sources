# AddOrRemoveIpEntryUnderLock

- ea: `0x180063eb4`
- end: `0x180064232`
- name: `AddOrRemoveIpEntryUnderLock`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800662cc`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x180049998`
- `0x18004a204`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x180063eb4`
- `0x1800646b8`
- `0x1800664d4`
- `0x180066630`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x1800640b6`
- `ntdll!RtlIpv6AddressToStringW` at `0x180064169`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800640b6`
- `ntdll!RtlIpv6AddressToStringW` at `0x180064169`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064138`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064138`
- `ntdll!RtlInsertEntryHashTable` at `0x180064075`
- `ntdll!RtlInsertEntryHashTable` at `0x180064075`

## string_xrefs

- `0x180063f53`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800641af`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
_QWORD *__fastcall AddOrRemoveIpEntryUnderLock(__int64 a1, __int64 a2, char a3)
{
  _QWORD *result; // rax
  char v7; // si
  const struct in6_addr *v8; // rbp
  _QWORD *v9; // rbx
  __int64 v10; // r14
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  int v13; // ecx
  int v14; // ecx
  _QWORD *v15; // r14
  _QWORD *v16; // rcx
  _QWORD *v17; // rbx
  __m128i v18; // xmm1
  __int64 v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  int v27; // ecx
  WCHAR S[72]; // [rsp+30h] [rbp-B8h] BYREF

  result = memset_0(S, 0, 0x82u);
  if ( *(_WORD *)a2 == 23 )
  {
    result = *(_QWORD **)(a1 + 288);
    if ( *(_DWORD *)(a2 + 40) == *((_DWORD *)result + 266) )
    {
      if ( !a3 || (v7 = 1, (unsigned int)(*(_DWORD *)(a2 + 64) - 3) > 1) )
        v7 = 0;
      v8 = (const struct in6_addr *)(a2 + 8);
      result = (_QWORD *)LookupClientAddressMapping(a1, v8);
      v9 = result;
      if ( v7 )
      {
        result = (_QWORD *)IpTlsRemoveConflictEntries(a1, v8);
        if ( v9 )
        {
          v10 = v9[5];
          if ( !v10 )
            return result;
          v11 = v9[6];
          if ( *(_QWORD **)(v11 + 8) != v9 + 6 )
            goto LABEL_32;
          v12 = (_QWORD *)v9[7];
          if ( (_QWORD *)*v12 != v9 + 6 )
            goto LABEL_32;
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          RemoveClientAddressMapping((__int64)v9);
          EventWrite0(
            0x20000000,
            L"(%s: Dereference client context (%p) %S:%d",
            *(_QWORD *)(*(_QWORD *)(v10 + 40) + 288LL) + 56LL,
            v10,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            1466);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v13,
              (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
              v10,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              186);
          DereferenceClientContextEx(v10);
        }
        result = (_QWORD *)MALLOC(0x40u);
        v15 = result;
        if ( result )
        {
          memset_0(result, 0, 0x40u);
          *(struct in6_addr *)(v15 + 3) = *v8;
          v16 = *(_QWORD **)(a1 + 16);
          if ( *v16 != a1 + 8 )
            goto LABEL_32;
          v17 = v15 + 6;
          v15[6] = a1 + 8;
          v15[7] = v16;
          *v16 = v15 + 6;
          *(_QWORD *)(a1 + 16) = v15 + 6;
          v18 = _mm_loadu_si128((const __m128i *)(v15 + 3));
          if ( !(unsigned __int8)RtlInsertEntryHashTable(
                                   a1 + 104,
                                   v15,
                                   (v18.m128i_i64[0] ^ _mm_srli_si128(v18, 8).m128i_u64[0]) & 0xFFFFFFFF3FFFFFFFuLL
                                 | 0x80000000,
                                   0) )
          {
            v19 = *v17;
            if ( *(_QWORD **)(*v17 + 8LL) == v17 )
            {
              v20 = (_QWORD *)v15[7];
              if ( (_QWORD *)*v20 == v17 )
              {
                *v20 = v19;
                *(_QWORD *)(v19 + 8) = v20;
                v21 = v15;
                return (_QWORD *)FREE(v21);
              }
            }
            goto LABEL_32;
          }
          result = RtlIpv6AddressToStringW(v8, S);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
            return (_QWORD *)McTemplateU0zz_EventWriteTransfer(
                               v22,
                               EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING,
                               *(_QWORD *)(a1 + 288) + 56LL,
                               S);
        }
        else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
        {
          return (_QWORD *)McTemplateU0psq_EventWriteTransfer(
                             v14,
                             (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
                             0,
                             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
                             239);
        }
      }
      else
      {
        if ( !result )
          return result;
        v23 = result[5];
        if ( !v23 )
        {
          RtlRemoveEntryHashTable(a1 + 104, result, 0);
          v24 = v9[6];
          if ( *(_QWORD **)(v24 + 8) == v9 + 6 )
          {
            v25 = (_QWORD *)v9[7];
            if ( (_QWORD *)*v25 == v9 + 6 )
            {
              *v25 = v24;
              *(_QWORD *)(v24 + 8) = v25;
              RtlIpv6AddressToStringW(v8, S);
              if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
                McTemplateU0zz_EventWriteTransfer(
                  v26,
                  EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING,
                  *(_QWORD *)(a1 + 288) + 56LL,
                  S);
              v21 = v9;
              return (_QWORD *)FREE(v21);
            }
          }
LABEL_32:
          __fastfail(3u);
        }
        EventWrite0(
          0x20000000,
          L"(%s: Dereference client context (%p) %S:%d",
          *(_QWORD *)(*(_QWORD *)(v23 + 40) + 288LL) + 56LL);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v27,
            (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
            v9[5],
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            6);
        return (_QWORD *)DereferenceClientContextEx(v9[5]);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180063eb4  mov     [rsp+arg_10], rbx
0x180063eb9  mov     [rsp+arg_18], rbp
0x180063ebe  push    rsi
0x180063ebf  push    rdi
0x180063ec0  push    r14
0x180063ec2  sub     rsp, 0D0h
0x180063ec9  mov     rax, cs:__security_cookie
0x180063ed0  xor     rax, rsp
0x180063ed3  mov     [rsp+0E8h+var_28], rax
0x180063edb  mov     bl, r8b
0x180063ede  mov     rbp, rdx
0x180063ee1  mov     rdi, rcx
0x180063ee4  xor     edx, edx; Val
0x180063ee6  mov     r8d, 82h; Size
0x180063eec  lea     rcx, [rsp+0E8h+S]; void *
0x180063ef1  call    memset_0
0x180063ef6  cmp     word ptr [rbp+0], 17h
0x180063efb  jnz     loc_180064209
0x180063f01  mov     rax, [rdi+120h]
0x180063f08  mov     ecx, [rax+428h]
0x180063f0e  cmp     [rbp+28h], ecx
0x180063f11  jnz     loc_180064209
0x180063f17  test    bl, bl
0x180063f19  jz      short loc_180063F2A
0x180063f1b  mov     eax, [rbp+40h]
0x180063f1e  mov     esi, 1
0x180063f23  sub     eax, 3
0x180063f26  cmp     eax, esi
0x180063f28  jbe     short loc_180063F2D
0x180063f2a  xor     sil, sil
0x180063f2d  add     rbp, 8
0x180063f31  mov     rcx, rdi
0x180063f34  mov     rdx, rbp
0x180063f37  call    LookupClientAddressMapping
0x180063f3c  mov     rbx, rax
0x180063f3f  test    sil, sil
0x180063f42  jz      loc_18006411C
0x180063f48  mov     rdx, rbp
0x180063f4b  mov     rcx, rdi
0x180063f4e  call    IpTlsRemoveConflictEntries
0x180063f53  lea     rsi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063f5a  test    rbx, rbx
0x180063f5d  jz      loc_180063FF5
0x180063f63  mov     r14, [rbx+28h]
0x180063f67  test    r14, r14
0x180063f6a  jz      loc_180064209
0x180063f70  lea     rax, [rbx+30h]
0x180063f74  mov     rcx, [rax]
0x180063f77  cmp     [rcx+8], rax
0x180063f7b  jnz     loc_1800641A4
0x180063f81  mov     rdx, [rax+8]
0x180063f85  cmp     [rdx], rax
0x180063f88  jnz     loc_1800641A4
0x180063f8e  mov     [rdx], rcx
0x180063f91  mov     [rcx+8], rdx
0x180063f95  mov     rcx, rbx
0x180063f98  call    RemoveClientAddressMapping
0x180063f9d  mov     rax, [r14+28h]
0x180063fa1  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x180063fa8  mov     ebx, 5BAh
0x180063fad  mov     r9, r14
0x180063fb0  mov     [rsp+0E8h+var_C0], ebx
0x180063fb4  mov     ecx, 20000000h
0x180063fb9  mov     [rsp+0E8h+var_C8], rsi
0x180063fbe  mov     r8, [rax+120h]
0x180063fc5  add     r8, 38h ; '8'
0x180063fc9  call    EventWrite0
0x180063fce  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063fd5  jz      short loc_180063FED
0x180063fd7  mov     r9, rsi
0x180063fda  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x180063fde  mov     r8, r14
0x180063fe1  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x180063fe8  call    McTemplateU0psq_EventWriteTransfer
0x180063fed  mov     rcx, r14
0x180063ff0  call    DereferenceClientContextEx
0x180063ff5  mov     ebx, 40h ; '@'
0x180063ffa  mov     ecx, ebx; dwBytes
0x180063ffc  call    MALLOC
0x180064001  mov     r14, rax
0x180064004  test    rax, rax
0x180064007  jz      loc_1800640F0
0x18006400d  mov     r8d, ebx; Size
0x180064010  xor     edx, edx; Val
0x180064012  mov     rcx, rax; void *
0x180064015  call    memset_0
0x18006401a  movups  xmm0, xmmword ptr [rbp+0]
0x18006401e  lea     rax, [rdi+8]
0x180064022  movdqu  xmmword ptr [r14+18h], xmm0
0x180064028  mov     rcx, [rax+8]
0x18006402c  cmp     [rcx], rax
0x18006402f  jnz     loc_1800641A4
0x180064035  lea     rbx, [r14+30h]
0x180064039  xor     r9d, r9d
0x18006403c  mov     [rbx], rax
0x18006403f  mov     rdx, r14
0x180064042  mov     [rbx+8], rcx
0x180064046  mov     [rcx], rbx
0x180064049  lea     rcx, [rdi+68h]
0x18006404d  mov     [rax+8], rbx
0x180064051  mov     eax, 80000000h
0x180064056  movdqu  xmm1, xmmword ptr [r14+18h]
0x18006405c  movdqa  xmm0, xmm1
0x180064060  psrldq  xmm0, 8
0x180064065  xorps   xmm1, xmm0
0x180064068  movq    r8, xmm1
0x18006406d  btr     r8, 1Eh
0x180064072  or      r8, rax
0x180064075  call    cs:__imp_RtlInsertEntryHashTable
0x18006407c  nop     dword ptr [rax+rax+00h]
0x180064081  test    al, al
0x180064083  jnz     short loc_1800640AE
0x180064085  mov     rax, [rbx]
0x180064088  cmp     [rax+8], rbx
0x18006408c  jnz     loc_1800641A4
0x180064092  mov     rcx, [rbx+8]
0x180064096  cmp     [rcx], rbx
0x180064099  jnz     loc_1800641A4
0x18006409f  mov     [rcx], rax
0x1800640a2  mov     [rax+8], rcx
0x1800640a6  mov     rcx, r14
0x1800640a9  jmp     loc_18006419D
0x1800640ae  lea     rdx, [rsp+0E8h+S]; S
0x1800640b3  mov     rcx, rbp; Addr
0x1800640b6  call    cs:__imp_RtlIpv6AddressToStringW
0x1800640bd  nop     dword ptr [rax+rax+00h]
0x1800640c2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800640c9  jz      loc_180064209
0x1800640cf  mov     r8, [rdi+120h]
0x1800640d6  lea     r9, [rsp+0E8h+S]
0x1800640db  add     r8, 38h ; '8'
0x1800640df  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING
0x1800640e6  call    McTemplateU0zz_EventWriteTransfer
0x1800640eb  jmp     loc_180064209
0x1800640f0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800640f7  jz      loc_180064209
0x1800640fd  mov     r9, rsi
0x180064100  mov     dword ptr [rsp+0E8h+var_C8], 5EFh
0x180064108  xor     r8d, r8d
0x18006410b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180064112  call    McTemplateU0psq_EventWriteTransfer
0x180064117  jmp     loc_180064209
0x18006411c  test    rbx, rbx
0x18006411f  jz      loc_180064209
0x180064125  mov     r9, [rax+28h]
0x180064129  test    r9, r9
0x18006412c  jnz     short loc_1800641AB
0x18006412e  lea     rcx, [rdi+68h]
0x180064132  xor     r8d, r8d
0x180064135  mov     rdx, rbx
0x180064138  call    cs:__imp_RtlRemoveEntryHashTable
0x18006413f  nop     dword ptr [rax+rax+00h]
0x180064144  lea     rax, [rbx+30h]
0x180064148  mov     rdx, [rax]
0x18006414b  cmp     [rdx+8], rax
0x18006414f  jnz     short loc_1800641A4
0x180064151  mov     rcx, [rax+8]
0x180064155  cmp     [rcx], rax
0x180064158  jnz     short loc_1800641A4
0x18006415a  mov     [rcx], rdx
0x18006415d  mov     [rdx+8], rcx
0x180064161  lea     rdx, [rsp+0E8h+S]; S
0x180064166  mov     rcx, rbp; Addr
0x180064169  call    cs:__imp_RtlIpv6AddressToStringW
0x180064170  nop     dword ptr [rax+rax+00h]
0x180064175  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006417c  jz      short loc_18006419A
0x18006417e  mov     r8, [rdi+120h]
0x180064185  lea     r9, [rsp+0E8h+S]
0x18006418a  add     r8, 38h ; '8'
0x18006418e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x180064195  call    McTemplateU0zz_EventWriteTransfer
0x18006419a  mov     rcx, rbx
0x18006419d  call    FREE
0x1800641a2  jmp     short loc_180064209
0x1800641a4  mov     ecx, 3
0x1800641a9  int     29h; Win8: RtlFailFast(ecx)
0x1800641ab  mov     rax, [r9+28h]
0x1800641af  lea     rsi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800641b6  mov     edi, 606h
0x1800641bb  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x1800641c2  mov     [rsp+0E8h+var_C0], edi
0x1800641c6  mov     ecx, 20000000h
0x1800641cb  mov     [rsp+0E8h+var_C8], rsi
0x1800641d0  mov     r8, [rax+120h]
0x1800641d7  add     r8, 38h ; '8'
0x1800641db  call    EventWrite0
0x1800641e0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800641e7  jz      short loc_180064200
0x1800641e9  mov     r8, [rbx+28h]
0x1800641ed  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x1800641f4  mov     r9, rsi
0x1800641f7  mov     dword ptr [rsp+0E8h+var_C8], edi
0x1800641fb  call    McTemplateU0psq_EventWriteTransfer
0x180064200  mov     rcx, [rbx+28h]
0x180064204  call    DereferenceClientContextEx
0x180064209  mov     rcx, [rsp+0E8h+var_28]
0x180064211  xor     rcx, rsp; StackCookie
0x180064214  call    __security_check_cookie
0x180064219  lea     r11, [rsp+0E8h+var_18]
0x180064221  mov     rbx, [r11+30h]
0x180064225  mov     rbp, [r11+38h]
0x180064229  mov     rsp, r11
0x18006422c  pop     r14
0x18006422e  pop     rdi
0x18006422f  pop     rsi
0x180064230  retn
```
