# AddOrRemoveIpEntryUnderLock

- ea: `0x180063ed4`
- end: `0x180064252`
- name: `AddOrRemoveIpEntryUnderLock`
- size: `894`
- prototype: `_QWORD *__fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800662ec`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x180049958`
- `0x18004a1c4`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x180063ed4`
- `0x1800646d8`
- `0x1800664f4`
- `0x180066650`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x1800640d6`
- `ntdll!RtlIpv6AddressToStringW` at `0x180064189`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800640d6`
- `ntdll!RtlIpv6AddressToStringW` at `0x180064189`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064158`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064158`
- `ntdll!RtlInsertEntryHashTable` at `0x180064095`
- `ntdll!RtlInsertEntryHashTable` at `0x180064095`

## string_xrefs

- `0x180063f73`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800641cf`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
          RemoveClientAddressMapping(v9);
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
0x180063ed4  mov     [rsp+arg_10], rbx
0x180063ed9  mov     [rsp+arg_18], rbp
0x180063ede  push    rsi
0x180063edf  push    rdi
0x180063ee0  push    r14
0x180063ee2  sub     rsp, 0D0h
0x180063ee9  mov     rax, cs:__security_cookie
0x180063ef0  xor     rax, rsp
0x180063ef3  mov     [rsp+0E8h+var_28], rax
0x180063efb  mov     bl, r8b
0x180063efe  mov     rbp, rdx
0x180063f01  mov     rdi, rcx
0x180063f04  xor     edx, edx; Val
0x180063f06  mov     r8d, 82h; Size
0x180063f0c  lea     rcx, [rsp+0E8h+S]; void *
0x180063f11  call    memset_0
0x180063f16  cmp     word ptr [rbp+0], 17h
0x180063f1b  jnz     loc_180064229
0x180063f21  mov     rax, [rdi+120h]
0x180063f28  mov     ecx, [rax+428h]
0x180063f2e  cmp     [rbp+28h], ecx
0x180063f31  jnz     loc_180064229
0x180063f37  test    bl, bl
0x180063f39  jz      short loc_180063F4A
0x180063f3b  mov     eax, [rbp+40h]
0x180063f3e  mov     esi, 1
0x180063f43  sub     eax, 3
0x180063f46  cmp     eax, esi
0x180063f48  jbe     short loc_180063F4D
0x180063f4a  xor     sil, sil
0x180063f4d  add     rbp, 8
0x180063f51  mov     rcx, rdi
0x180063f54  mov     rdx, rbp
0x180063f57  call    LookupClientAddressMapping
0x180063f5c  mov     rbx, rax
0x180063f5f  test    sil, sil
0x180063f62  jz      loc_18006413C
0x180063f68  mov     rdx, rbp
0x180063f6b  mov     rcx, rdi
0x180063f6e  call    IpTlsRemoveConflictEntries
0x180063f73  lea     rsi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063f7a  test    rbx, rbx
0x180063f7d  jz      loc_180064015
0x180063f83  mov     r14, [rbx+28h]
0x180063f87  test    r14, r14
0x180063f8a  jz      loc_180064229
0x180063f90  lea     rax, [rbx+30h]
0x180063f94  mov     rcx, [rax]
0x180063f97  cmp     [rcx+8], rax
0x180063f9b  jnz     loc_1800641C4
0x180063fa1  mov     rdx, [rax+8]
0x180063fa5  cmp     [rdx], rax
0x180063fa8  jnz     loc_1800641C4
0x180063fae  mov     [rdx], rcx
0x180063fb1  mov     [rcx+8], rdx
0x180063fb5  mov     rcx, rbx
0x180063fb8  call    RemoveClientAddressMapping
0x180063fbd  mov     rax, [r14+28h]
0x180063fc1  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x180063fc8  mov     ebx, 5BAh
0x180063fcd  mov     r9, r14
0x180063fd0  mov     [rsp+0E8h+var_C0], ebx
0x180063fd4  mov     ecx, 20000000h
0x180063fd9  mov     [rsp+0E8h+var_C8], rsi
0x180063fde  mov     r8, [rax+120h]
0x180063fe5  add     r8, 38h ; '8'
0x180063fe9  call    EventWrite0
0x180063fee  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180063ff5  jz      short loc_18006400D
0x180063ff7  mov     r9, rsi
0x180063ffa  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x180063ffe  mov     r8, r14
0x180064001  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x180064008  call    McTemplateU0psq_EventWriteTransfer
0x18006400d  mov     rcx, r14
0x180064010  call    DereferenceClientContextEx
0x180064015  mov     ebx, 40h ; '@'
0x18006401a  mov     ecx, ebx; dwBytes
0x18006401c  call    MALLOC
0x180064021  mov     r14, rax
0x180064024  test    rax, rax
0x180064027  jz      loc_180064110
0x18006402d  mov     r8d, ebx; Size
0x180064030  xor     edx, edx; Val
0x180064032  mov     rcx, rax; void *
0x180064035  call    memset_0
0x18006403a  movups  xmm0, xmmword ptr [rbp+0]
0x18006403e  lea     rax, [rdi+8]
0x180064042  movdqu  xmmword ptr [r14+18h], xmm0
0x180064048  mov     rcx, [rax+8]
0x18006404c  cmp     [rcx], rax
0x18006404f  jnz     loc_1800641C4
0x180064055  lea     rbx, [r14+30h]
0x180064059  xor     r9d, r9d
0x18006405c  mov     [rbx], rax
0x18006405f  mov     rdx, r14
0x180064062  mov     [rbx+8], rcx
0x180064066  mov     [rcx], rbx
0x180064069  lea     rcx, [rdi+68h]
0x18006406d  mov     [rax+8], rbx
0x180064071  mov     eax, 80000000h
0x180064076  movdqu  xmm1, xmmword ptr [r14+18h]
0x18006407c  movdqa  xmm0, xmm1
0x180064080  psrldq  xmm0, 8
0x180064085  xorps   xmm1, xmm0
0x180064088  movq    r8, xmm1
0x18006408d  btr     r8, 1Eh
0x180064092  or      r8, rax
0x180064095  call    cs:__imp_RtlInsertEntryHashTable
0x18006409c  nop     dword ptr [rax+rax+00h]
0x1800640a1  test    al, al
0x1800640a3  jnz     short loc_1800640CE
0x1800640a5  mov     rax, [rbx]
0x1800640a8  cmp     [rax+8], rbx
0x1800640ac  jnz     loc_1800641C4
0x1800640b2  mov     rcx, [rbx+8]
0x1800640b6  cmp     [rcx], rbx
0x1800640b9  jnz     loc_1800641C4
0x1800640bf  mov     [rcx], rax
0x1800640c2  mov     [rax+8], rcx
0x1800640c6  mov     rcx, r14
0x1800640c9  jmp     loc_1800641BD
0x1800640ce  lea     rdx, [rsp+0E8h+S]; S
0x1800640d3  mov     rcx, rbp; Addr
0x1800640d6  call    cs:__imp_RtlIpv6AddressToStringW
0x1800640dd  nop     dword ptr [rax+rax+00h]
0x1800640e2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800640e9  jz      loc_180064229
0x1800640ef  mov     r8, [rdi+120h]
0x1800640f6  lea     r9, [rsp+0E8h+S]
0x1800640fb  add     r8, 38h ; '8'
0x1800640ff  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_ADD_CLIENT_ADDRESS_MAPPING
0x180064106  call    McTemplateU0zz_EventWriteTransfer
0x18006410b  jmp     loc_180064229
0x180064110  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180064117  jz      loc_180064229
0x18006411d  mov     r9, rsi
0x180064120  mov     dword ptr [rsp+0E8h+var_C8], 5EFh
0x180064128  xor     r8d, r8d
0x18006412b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180064132  call    McTemplateU0psq_EventWriteTransfer
0x180064137  jmp     loc_180064229
0x18006413c  test    rbx, rbx
0x18006413f  jz      loc_180064229
0x180064145  mov     r9, [rax+28h]
0x180064149  test    r9, r9
0x18006414c  jnz     short loc_1800641CB
0x18006414e  lea     rcx, [rdi+68h]
0x180064152  xor     r8d, r8d
0x180064155  mov     rdx, rbx
0x180064158  call    cs:__imp_RtlRemoveEntryHashTable
0x18006415f  nop     dword ptr [rax+rax+00h]
0x180064164  lea     rax, [rbx+30h]
0x180064168  mov     rdx, [rax]
0x18006416b  cmp     [rdx+8], rax
0x18006416f  jnz     short loc_1800641C4
0x180064171  mov     rcx, [rax+8]
0x180064175  cmp     [rcx], rax
0x180064178  jnz     short loc_1800641C4
0x18006417a  mov     [rcx], rdx
0x18006417d  mov     [rdx+8], rcx
0x180064181  lea     rdx, [rsp+0E8h+S]; S
0x180064186  mov     rcx, rbp; Addr
0x180064189  call    cs:__imp_RtlIpv6AddressToStringW
0x180064190  nop     dword ptr [rax+rax+00h]
0x180064195  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006419c  jz      short loc_1800641BA
0x18006419e  mov     r8, [rdi+120h]
0x1800641a5  lea     r9, [rsp+0E8h+S]
0x1800641aa  add     r8, 38h ; '8'
0x1800641ae  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x1800641b5  call    McTemplateU0zz_EventWriteTransfer
0x1800641ba  mov     rcx, rbx
0x1800641bd  call    FREE
0x1800641c2  jmp     short loc_180064229
0x1800641c4  mov     ecx, 3
0x1800641c9  int     29h; Win8: RtlFailFast(ecx)
0x1800641cb  mov     rax, [r9+28h]
0x1800641cf  lea     rsi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800641d6  mov     edi, 606h
0x1800641db  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x1800641e2  mov     [rsp+0E8h+var_C0], edi
0x1800641e6  mov     ecx, 20000000h
0x1800641eb  mov     [rsp+0E8h+var_C8], rsi
0x1800641f0  mov     r8, [rax+120h]
0x1800641f7  add     r8, 38h ; '8'
0x1800641fb  call    EventWrite0
0x180064200  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180064207  jz      short loc_180064220
0x180064209  mov     r8, [rbx+28h]
0x18006420d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x180064214  mov     r9, rsi
0x180064217  mov     dword ptr [rsp+0E8h+var_C8], edi
0x18006421b  call    McTemplateU0psq_EventWriteTransfer
0x180064220  mov     rcx, [rbx+28h]
0x180064224  call    DereferenceClientContextEx
0x180064229  mov     rcx, [rsp+0E8h+var_28]
0x180064231  xor     rcx, rsp; StackCookie
0x180064234  call    __security_check_cookie
0x180064239  lea     r11, [rsp+0E8h+var_18]
0x180064241  mov     rbx, [r11+30h]
0x180064245  mov     rbp, [r11+38h]
0x180064249  mov     rsp, r11
0x18006424c  pop     r14
0x18006424e  pop     rdi
0x18006424f  pop     rsi
0x180064250  retn
```
