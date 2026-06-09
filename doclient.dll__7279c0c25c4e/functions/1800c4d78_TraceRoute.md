# _TraceRoute

- ea: `0x1800c4d78`
- end: `0x1800c5025`
- name: `_TraceRoute`
- size: `685`
- prototype: `__int64 __usercall@<rax>(struct sockaddr_in6 *SourceAddress@<rcx>, struct sockaddr_in6 *DestinationAddress@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800c5050`

## callees

- `0x180008618`
- `0x180008b1c`
- `0x1800095a0`
- `0x1800c4b30`
- `0x1800c4d78`
- `0x1800c5328`
- `0x1800c5424`
- `0x1800f82f0`

## import_xrefs

- `IPHLPAPI!Icmp6CreateFile` at `0x1800c4e10`
- `IPHLPAPI!Icmp6CreateFile` at `0x1800c4e10`
- `IPHLPAPI!IcmpCreateFile` at `0x1800c4e18`
- `IPHLPAPI!IcmpCreateFile` at `0x1800c4e18`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fa8`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fb5`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fe7`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fa8`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fb5`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800c4fe7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall TraceRoute(
        struct sockaddr_in6 *SourceAddress,
        struct sockaddr_in6 *DestinationAddress,
        unsigned __int8 a3,
        DWORD a4,
        __int64 a5)
{
  unsigned __int64 v6; // r14
  _QWORD *v9; // rsi
  _QWORD *v10; // rbx
  char *File; // rax
  const char *v12; // r9
  void *v13; // rbx
  UCHAR v14; // al
  __m128i si128; // xmm6
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // edi
  DWORD v21; // [rsp+20h] [rbp-A8h]
  char *v22; // [rsp+30h] [rbp-98h] BYREF
  __int128 v23; // [rsp+38h] [rbp-90h] BYREF
  __m128i v24; // [rsp+48h] [rbp-80h]
  int v25; // [rsp+58h] [rbp-70h]
  __int16 v26; // [rsp+5Ch] [rbp-6Ch]
  struct ip_option_information RequestOptions; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v6 = a3;
  v9 = *(_QWORD **)(a5 + 8);
  v10 = *(_QWORD **)a5;
  if ( *(_QWORD **)a5 != v9 )
  {
    do
    {
      std::string::~string(v10);
      v10 += 5;
    }
    while ( v10 != v9 );
    v10 = *(_QWORD **)a5;
    *(_QWORD *)(a5 + 8) = *(_QWORD *)a5;
  }
  v22 = (char *)v6;
  if ( v6 > 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(a5 + 16) - (_QWORD)v10) >> 3) )
    std::vector<TraceHopData>::_Reallocate<0>(a5, &v22);
  if ( DestinationAddress->sin6_family == 23 )
    File = (char *)Icmp6CreateFile();
  else
    File = (char *)IcmpCreateFile();
  v13 = File;
  v22 = File;
  if ( (unsigned __int64)(File - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x12C,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\TraceRoute.cpp",
                           v12);
  RequestOptions = 0;
  v14 = 3;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    RequestOptions.Ttl = v14;
    if ( v14 > (unsigned __int8)v6 )
      break;
    v23 = 0;
    v24 = si128;
    LOBYTE(v23) = 0;
    v25 = 0;
    v26 = 0;
    v16 = SendEchoWithRetry(v13, SourceAddress, DestinationAddress, &RequestOptions, a4, &v23);
    switch ( v16 )
    {
      case 0u:
        v17 = *(_QWORD *)(a5 + 8);
        if ( v17 == *(_QWORD *)(a5 + 16) )
        {
          std::vector<TraceHopData>::_Emplace_reallocate<TraceHopData>(a5, v17, &v23);
        }
        else
        {
          *(_OWORD *)v17 = 0;
          *(_QWORD *)(v17 + 16) = 0;
          *(_QWORD *)(v17 + 24) = 0;
          *(_OWORD *)v17 = v23;
          *(__m128i *)(v17 + 16) = v24;
          v24 = si128;
          LOBYTE(v23) = 0;
          *(_DWORD *)(v17 + 32) = v25;
          *(_WORD *)(v17 + 36) = v26;
          *(_QWORD *)(a5 + 8) += 40LL;
        }
        std::string::~string(&v23);
        goto LABEL_24;
      case 0x2B05u:
        v18 = *(_QWORD *)(a5 + 8);
        if ( v18 == *(_QWORD *)(a5 + 16) )
        {
          std::vector<TraceHopData>::_Emplace_reallocate<TraceHopData>(a5, v18, &v23);
        }
        else
        {
          *(_OWORD *)v18 = 0;
          *(_QWORD *)(v18 + 16) = 0;
          *(_QWORD *)(v18 + 24) = 0;
          *(_OWORD *)v18 = v23;
          *(__m128i *)(v18 + 16) = v24;
          v24 = si128;
          LOBYTE(v23) = 0;
          *(_DWORD *)(v18 + 32) = v25;
          *(_WORD *)(v18 + 36) = v26;
          *(_QWORD *)(a5 + 8) += 40LL;
        }
        break;
      case 0x2B02u:
        break;
      default:
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x147,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\TraceRoute.cpp",
                (const char *)v16,
                v21);
        std::string::~string(&v23);
        IcmpCloseHandle(v13);
        return v19;
    }
    std::string::~string(&v23);
    v14 = RequestOptions.Ttl + 1;
  }
LABEL_24:
  IcmpCloseHandle(v13);
  return 0;
}

```

## disassembly

```asm
0x1800c4d78  mov     rax, rsp
0x1800c4d7b  push    rbx
0x1800c4d7c  push    rsi
0x1800c4d7d  push    rdi
0x1800c4d7e  push    r12
0x1800c4d80  push    r13
0x1800c4d82  push    r14
0x1800c4d84  push    r15
0x1800c4d86  sub     rsp, 90h
0x1800c4d8d  movaps  xmmword ptr [rax-48h], xmm6
0x1800c4d91  mov     rax, cs:__security_cookie
0x1800c4d98  xor     rax, rsp
0x1800c4d9b  mov     [rsp+0C8h+var_58], rax
0x1800c4da0  mov     r12d, r9d
0x1800c4da3  movzx   r14d, r8b
0x1800c4da7  mov     r15, rdx
0x1800c4daa  mov     r13, rcx
0x1800c4dad  mov     rdi, [rsp+0C8h+arg_20]
0x1800c4db5  mov     rsi, [rdi+8]
0x1800c4db9  mov     rbx, [rdi]
0x1800c4dbc  cmp     rbx, rsi
0x1800c4dbf  jz      short loc_1800C4DD9
0x1800c4dc1  mov     rcx, rbx; void *
0x1800c4dc4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c4dc9  add     rbx, 28h ; '('
0x1800c4dcd  cmp     rbx, rsi
0x1800c4dd0  jnz     short loc_1800C4DC1
0x1800c4dd2  mov     rbx, [rdi]
0x1800c4dd5  mov     [rdi+8], rbx
0x1800c4dd9  mov     [rsp+0C8h+var_98], r14
0x1800c4dde  mov     rax, [rdi+10h]
0x1800c4de2  sub     rax, rbx
0x1800c4de5  sar     rax, 3
0x1800c4de9  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x1800c4df3  imul    rax, rdx
0x1800c4df7  cmp     r14, rax
0x1800c4dfa  jbe     short loc_1800C4E09
0x1800c4dfc  lea     rdx, [rsp+0C8h+var_98]
0x1800c4e01  mov     rcx, rdi
0x1800c4e04  call    ??$_Reallocate@$0A@@?$vector@UTraceHopData@@V?$allocator@UTraceHopData@@@std@@@std@@AEAAXAEA_K@Z; std::vector<TraceHopData>::_Reallocate<0>(unsigned __int64 &)
0x1800c4e09  cmp     word ptr [r15], 17h
0x1800c4e0e  jnz     short loc_1800C4E18
0x1800c4e10  call    cs:__imp_Icmp6CreateFile
0x1800c4e16  jmp     short loc_1800C4E1E
0x1800c4e18  call    cs:__imp_IcmpCreateFile
0x1800c4e1e  mov     rbx, rax
0x1800c4e21  mov     [rsp+0C8h+var_98], rax
0x1800c4e26  lea     rax, [rax-1]
0x1800c4e2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c4e2e  ja      loc_1800C4FBF
0x1800c4e34  xorps   xmm0, xmm0
0x1800c4e37  movups  xmmword ptr [rsp+0C8h+RequestOptions.Ttl], xmm0
0x1800c4e3c  mov     al, 3
0x1800c4e3e  xor     esi, esi
0x1800c4e40  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800c4e48  mov     [rsp+0C8h+RequestOptions.Ttl], al
0x1800c4e4c  cmp     al, r14b
0x1800c4e4f  ja      loc_1800C4FB2
0x1800c4e55  xorps   xmm0, xmm0
0x1800c4e58  movups  [rsp+0C8h+var_90], xmm0
0x1800c4e5d  movdqu  [rsp+0C8h+var_80], xmm6
0x1800c4e63  mov     byte ptr [rsp+0C8h+var_90], sil
0x1800c4e68  mov     [rsp+0C8h+var_70], esi
0x1800c4e6c  mov     [rsp+0C8h+var_6C], si
0x1800c4e71  lea     rax, [rsp+0C8h+var_90]
0x1800c4e76  mov     [rsp+0C8h+var_A0], rax; void *
0x1800c4e7b  mov     [rsp+0C8h+var_A8], r12d; unsigned int
0x1800c4e80  lea     r9, [rsp+0C8h+RequestOptions]; RequestOptions
0x1800c4e85  mov     r8, r15; DestinationAddress
0x1800c4e88  mov     rdx, r13; SourceAddress
0x1800c4e8b  mov     rcx, rbx; IcmpHandle
0x1800c4e8e  call    _SendEchoWithRetry
0x1800c4e93  test    eax, eax
0x1800c4e95  jnz     short loc_1800C4EFF
0x1800c4e97  mov     rdx, [rdi+8]
0x1800c4e9b  cmp     rdx, [rdi+10h]
0x1800c4e9f  jz      short loc_1800C4EE2
0x1800c4ea1  xorps   xmm0, xmm0
0x1800c4ea4  movups  xmmword ptr [rdx], xmm0
0x1800c4ea7  mov     [rdx+10h], rsi
0x1800c4eab  mov     [rdx+18h], rsi
0x1800c4eaf  movups  xmm0, [rsp+0C8h+var_90]
0x1800c4eb4  movups  xmmword ptr [rdx], xmm0
0x1800c4eb7  movups  xmm1, [rsp+0C8h+var_80]
0x1800c4ebc  movups  xmmword ptr [rdx+10h], xmm1
0x1800c4ec0  movdqu  [rsp+0C8h+var_80], xmm6
0x1800c4ec6  mov     byte ptr [rsp+0C8h+var_90], sil
0x1800c4ecb  mov     eax, [rsp+0C8h+var_70]
0x1800c4ecf  mov     [rdx+20h], eax
0x1800c4ed2  movzx   eax, [rsp+0C8h+var_6C]
0x1800c4ed7  mov     [rdx+24h], ax
0x1800c4edb  add     qword ptr [rdi+8], 28h ; '('
0x1800c4ee0  jmp     short loc_1800C4EF0
0x1800c4ee2  lea     r8, [rsp+0C8h+var_90]
0x1800c4ee7  mov     rcx, rdi
0x1800c4eea  call    ??$_Emplace_reallocate@UTraceHopData@@@?$vector@UTraceHopData@@V?$allocator@UTraceHopData@@@std@@@std@@AEAAPEAUTraceHopData@@QEAU2@$$QEAU2@@Z; std::vector<TraceHopData>::_Emplace_reallocate<TraceHopData>(TraceHopData * const,TraceHopData &&)
0x1800c4eef  nop
0x1800c4ef0  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800c4ef5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c4efa  jmp     loc_1800C4FB2
0x1800c4eff  cmp     eax, 2B05h
0x1800c4f04  jnz     short loc_1800C4F60
0x1800c4f06  mov     rdx, [rdi+8]
0x1800c4f0a  cmp     rdx, [rdi+10h]
0x1800c4f0e  jz      short loc_1800C4F51
0x1800c4f10  xorps   xmm0, xmm0
0x1800c4f13  movups  xmmword ptr [rdx], xmm0
0x1800c4f16  mov     [rdx+10h], rsi
0x1800c4f1a  mov     [rdx+18h], rsi
0x1800c4f1e  movups  xmm0, [rsp+0C8h+var_90]
0x1800c4f23  movups  xmmword ptr [rdx], xmm0
0x1800c4f26  movups  xmm1, [rsp+0C8h+var_80]
0x1800c4f2b  movups  xmmword ptr [rdx+10h], xmm1
0x1800c4f2f  movdqu  [rsp+0C8h+var_80], xmm6
0x1800c4f35  mov     byte ptr [rsp+0C8h+var_90], sil
0x1800c4f3a  mov     eax, [rsp+0C8h+var_70]
0x1800c4f3e  mov     [rdx+20h], eax
0x1800c4f41  movzx   eax, [rsp+0C8h+var_6C]
0x1800c4f46  mov     [rdx+24h], ax
0x1800c4f4a  add     qword ptr [rdi+8], 28h ; '('
0x1800c4f4f  jmp     short loc_1800C4F67
0x1800c4f51  lea     r8, [rsp+0C8h+var_90]
0x1800c4f56  mov     rcx, rdi
0x1800c4f59  call    ??$_Emplace_reallocate@UTraceHopData@@@?$vector@UTraceHopData@@V?$allocator@UTraceHopData@@@std@@@std@@AEAAPEAUTraceHopData@@QEAU2@$$QEAU2@@Z; std::vector<TraceHopData>::_Emplace_reallocate<TraceHopData>(TraceHopData * const,TraceHopData &&)
0x1800c4f5e  jmp     short loc_1800C4F67
0x1800c4f60  cmp     eax, 2B02h
0x1800c4f65  jnz     short loc_1800C4F7C
0x1800c4f67  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800c4f6c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c4f71  mov     al, [rsp+0C8h+RequestOptions.Ttl]
0x1800c4f75  inc     al
0x1800c4f77  jmp     loc_1800C4E48
0x1800c4f7c  mov     rcx, [rsp+0C8h]; this
0x1800c4f84  mov     r9d, eax; char *
0x1800c4f87  lea     r8, aCW1SSrcDeliver_109; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c4f8e  mov     edx, 147h; void *
0x1800c4f93  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c4f98  mov     edi, eax
0x1800c4f9a  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800c4f9f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c4fa4  nop
0x1800c4fa5  mov     rcx, rbx; IcmpHandle
0x1800c4fa8  call    cs:__imp_IcmpCloseHandle
0x1800c4fae  mov     eax, edi
0x1800c4fb0  jmp     short loc_1800C4FFC
0x1800c4fb2  mov     rcx, rbx; IcmpHandle
0x1800c4fb5  call    cs:__imp_IcmpCloseHandle
0x1800c4fbb  xor     eax, eax
0x1800c4fbd  jmp     short loc_1800C4FFC
0x1800c4fbf  mov     rcx, [rsp+0C8h]; this
0x1800c4fc7  lea     r8, aCW1SSrcDeliver_109; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c4fce  mov     edx, 12Ch; void *
0x1800c4fd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c4fd8  mov     edi, eax
0x1800c4fda  lea     rcx, [rbx-1]
0x1800c4fde  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800c4fe2  ja      short loc_1800C4FED
0x1800c4fe4  mov     rcx, rbx; IcmpHandle
0x1800c4fe7  call    cs:__imp_IcmpCloseHandle
0x1800c4fed  mov     eax, edi
0x1800c4fef  jmp     short loc_1800C4FFC
0x1800c4ff1  mov     eax, dword ptr [rsp+0C8h+var_98]
0x1800c4ff5  jmp     short loc_1800C4FFC
0x1800c4ff7  mov     eax, 8007000Eh
0x1800c4ffc  mov     rcx, [rsp+0C8h+var_58]
0x1800c5001  xor     rcx, rsp; StackCookie
0x1800c5004  call    __security_check_cookie
0x1800c5009  movaps  xmm6, [rsp+0C8h+var_48]
0x1800c5011  add     rsp, 90h
0x1800c5018  pop     r15
0x1800c501a  pop     r14
0x1800c501c  pop     r13
0x1800c501e  pop     r12
0x1800c5020  pop     rdi
0x1800c5021  pop     rsi
0x1800c5022  pop     rbx
0x1800c5023  retn
```
