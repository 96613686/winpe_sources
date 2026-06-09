# IPHelper::RemoveIPAddress(_NET_LUID_LH const &,uint,sockaddr_storage const &,uchar,bool)

- ea: `0x18008b23c`
- end: `0x18008b3fe`
- name: `?RemoveIPAddress@IPHelper@@SAXAEBT_NET_LUID_LH@@IAEBUsockaddr_storage@@E_N@Z`
- size: `450`
- prototype: `static void(const union _NET_LUID_LH *, unsigned int, const struct sockaddr_storage *, unsigned __int8, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180157738`
- `0x180161e38`

## callees

- `0x18005f0c0`
- `0x18005ff2a`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x180077910`
- `0x18007dc48`
- `0x1800887c4`
- `0x1800887dc`
- `0x180089aa4`
- `0x180089ac0`
- `0x180089adc`
- `0x18008a7cc`
- `0x18008b23c`
- `0x18008b50c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18008b2bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18008b2bc`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008b28b`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008b28b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008b333`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008b333`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x18008b2e4`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x18008b2e4`

## string_xrefs

- `0x18008b3ec`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008b26a`: `IPHelper::RemoveIPAddress`
- `0x18008b31d`: `IPHelper::RemoveIPAddress`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall IPHelper::RemoveIPAddress(
        const union _NET_LUID_LH *a1,
        unsigned int a2,
        const struct sockaddr_storage *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  signed int v9; // ebx
  bool v10; // sf
  const unsigned __int16 *v11; // rax
  unsigned int v12; // eax
  _BYTE v13[16]; // [rsp+40h] [rbp-C0h] BYREF
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v16[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v17[24]; // [rsp+D8h] [rbp-28h] BYREF
  int v18[6]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v19[24]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v20[24]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v21[24]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  HNSTraceProvider::TraceEnter("IPHelper::RemoveIPAddress", 0x174u);
  memset_0(&Row, 0, sizeof(Row));
  InitializeUnicastIpAddressEntry(&Row);
  Row.InterfaceLuid = (NET_LUID)a1->Value;
  Row.OnLinkPrefixLength = 8;
  Row.DadState = NldsPreferred;
  if ( a3 )
  {
    Row.Address.Ipv4 = *(SOCKADDR_IN *)&a3->ss_family;
  }
  else
  {
    Row.Address.Ipv4 = 0;
    *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    invalid_parameter_noinfo();
  }
  IPHelper::SetCurrentThreadCompartmentId(v13, a2);
  v9 = InternalDeleteUnicastIpAddressEntry(1, &Row);
  if ( v9 )
  {
    IPHelper::Ipv4ToString(v15, &a3->__ss_pad1[2]);
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( v10 )
    {
      HNSEventType::HNSEventType((HNSEventType *)v21, v9);
      HNSEventType::HNSEventType((HNSEventType *)v20, a1->Value);
      HNSEventType::HNSEventType((HNSEventType *)v19, a2);
      HNSEventType::HNSEventType((HNSEventType *)v18, 8u);
      v11 = (const unsigned __int16 *)std::wstring::c_str(v15);
      HNSEventType::HNSEventType((HNSEventType *)v17, v11);
      HNSEventType::HNSEventType((HNSEventType *)v16, 0);
      EventWrite(&SET_IPADDRESS_FAILED, (struct HNSEventType *)v21, v20, v19);
      v12 = wil::verify_hresult<long>((unsigned int)v9);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)v12,
        (int)v18);
    }
    std::wstring::~wstring(v15);
  }
  HNSTraceProvider::TraceSuccess("IPHelper::RemoveIPAddress", 0x19Eu);
  if ( v13[0] )
    SetCurrentThreadCompartmentId(0);
}

```

## disassembly

```asm
0x18008b23c  push    rbp
0x18008b23e  push    rbx
0x18008b23f  push    rsi
0x18008b240  push    rdi
0x18008b241  push    r14
0x18008b243  lea     rbp, [rsp-60h]
0x18008b248  sub     rsp, 160h
0x18008b24f  mov     rax, cs:__security_cookie
0x18008b256  xor     rax, rsp
0x18008b259  mov     [rbp+80h+var_30], rax
0x18008b25d  mov     rdi, r8
0x18008b260  mov     esi, edx
0x18008b262  mov     r14, rcx
0x18008b265  mov     edx, 174h; unsigned int
0x18008b26a  lea     rcx, aIphelperRemove_0; "IPHelper::RemoveIPAddress"
0x18008b271  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18008b276  xor     edx, edx; Val
0x18008b278  lea     r8d, [rdx+50h]; Size
0x18008b27c  lea     rcx, [rsp+180h+Row]; void *
0x18008b281  call    memset_0
0x18008b286  lea     rcx, [rsp+180h+Row]; Row
0x18008b28b  call    cs:__imp_InitializeUnicastIpAddressEntry
0x18008b291  mov     rax, [r14]
0x18008b294  mov     qword ptr [rsp+180h+Row.InterfaceLuid], rax
0x18008b299  mov     [rbp+80h+Row.OnLinkPrefixLength], 8
0x18008b29d  mov     [rbp+80h+Row.DadState], 4
0x18008b2a4  test    rdi, rdi
0x18008b2a7  jz      short loc_18008B2B4
0x18008b2a9  movups  xmm0, xmmword ptr [rdi]
0x18008b2ac  movdqu  xmmword ptr [rsp+180h+Row.Address], xmm0
0x18008b2b2  jmp     short loc_18008B2CD
0x18008b2b4  xorps   xmm0, xmm0
0x18008b2b7  movups  xmmword ptr [rsp+180h+Row.Address], xmm0
0x18008b2bc  call    cs:__imp__o__errno
0x18008b2c2  mov     dword ptr [rax], 16h
0x18008b2c8  call    _invalid_parameter_noinfo
0x18008b2cd  mov     edx, esi
0x18008b2cf  lea     rcx, [rsp+180h+var_140]
0x18008b2d4  call    ?SetCurrentThreadCompartmentId@IPHelper@@SA?AV?$unique_call@P6AXXZ$1?ClearCompartment@IPHelper@@SAXXZ$00@wil@@I@Z; IPHelper::SetCurrentThreadCompartmentId(uint)
0x18008b2d9  nop
0x18008b2da  lea     rdx, [rsp+180h+Row]
0x18008b2df  mov     ecx, 1
0x18008b2e4  call    cs:__imp_InternalDeleteUnicastIpAddressEntry
0x18008b2ea  mov     ebx, eax
0x18008b2ec  test    eax, eax
0x18008b2ee  jz      short loc_18008B318
0x18008b2f0  lea     rdx, [rdi+4]
0x18008b2f4  lea     rcx, [rbp+80h+var_E0]
0x18008b2f8  call    ?Ipv4ToString@IPHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAE@Z; IPHelper::Ipv4ToString(uchar *)
0x18008b2fd  nop
0x18008b2fe  test    ebx, ebx
0x18008b300  jle     short loc_18008B30D
0x18008b302  movzx   ebx, bx
0x18008b305  or      ebx, 80070000h
0x18008b30b  test    ebx, ebx
0x18008b30d  js      short loc_18008B353
0x18008b30f  lea     rcx, [rbp+80h+var_E0]; void *
0x18008b313  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008b318  mov     edx, 19Eh; unsigned int
0x18008b31d  lea     rcx, aIphelperRemove_0; "IPHelper::RemoveIPAddress"
0x18008b324  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x18008b329  nop
0x18008b32a  cmp     [rsp+180h+var_140], 0
0x18008b32f  jz      short loc_18008B339
0x18008b331  xor     ecx, ecx; CompartmentId
0x18008b333  call    cs:__imp_SetCurrentThreadCompartmentId
0x18008b339  mov     rcx, [rbp+80h+var_30]
0x18008b33d  xor     rcx, rsp; StackCookie
0x18008b340  call    __security_check_cookie
0x18008b345  add     rsp, 160h
0x18008b34c  pop     r14
0x18008b34e  pop     rdi
0x18008b34f  pop     rsi
0x18008b350  pop     rbx
0x18008b351  pop     rbp
0x18008b352  retn
0x18008b353  mov     edx, ebx; int
0x18008b355  lea     rcx, [rbp+80h+var_48]; this
0x18008b359  call    ??0HNSEventType@@QEAA@J@Z; HNSEventType::HNSEventType(long)
0x18008b35e  mov     rdx, [r14]; unsigned __int64
0x18008b361  lea     rcx, [rbp+80h+var_60]; this
0x18008b365  call    ??0HNSEventType@@QEAA@_K@Z; HNSEventType::HNSEventType(unsigned __int64)
0x18008b36a  mov     edx, esi; unsigned int
0x18008b36c  lea     rcx, [rbp+80h+var_78]; this
0x18008b370  call    ??0HNSEventType@@QEAA@I@Z; HNSEventType::HNSEventType(uint)
0x18008b375  mov     edx, 8; unsigned int
0x18008b37a  lea     rcx, [rbp+80h+var_90]; this
0x18008b37e  call    ??0HNSEventType@@QEAA@I@Z; HNSEventType::HNSEventType(uint)
0x18008b383  lea     rcx, [rbp+80h+var_E0]
0x18008b387  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18008b38c  mov     rdx, rax; unsigned __int16 *
0x18008b38f  lea     rcx, [rbp+80h+var_A8]; this
0x18008b393  call    ??0HNSEventType@@QEAA@PEBG@Z; HNSEventType::HNSEventType(ushort const *)
0x18008b398  xor     edx, edx; int
0x18008b39a  lea     rcx, [rbp+80h+var_C0]; this
0x18008b39e  call    ??0HNSEventType@@QEAA@H@Z; HNSEventType::HNSEventType(int)
0x18008b3a3  mov     [rsp+180h+var_148], rdx
0x18008b3a8  lea     rax, [rbp+80h+var_C0]
0x18008b3ac  mov     [rsp+180h+var_150], rax
0x18008b3b1  lea     rax, [rbp+80h+var_A8]
0x18008b3b5  mov     [rsp+180h+var_158], rax
0x18008b3ba  lea     rax, [rbp+80h+var_90]
0x18008b3be  mov     qword ptr [rsp+180h+var_160], rax; int
0x18008b3c3  lea     r9, [rbp+80h+var_78]
0x18008b3c7  lea     r8, [rbp+80h+var_60]
0x18008b3cb  lea     rdx, [rbp+80h+var_48]; this
0x18008b3cf  lea     rcx, SET_IPADDRESS_FAILED; EventDescriptor
0x18008b3d6  call    ?EventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVHNSEventType@@ZZ; EventWrite(_EVENT_DESCRIPTOR const *,HNSEventType *,...)
0x18008b3db  mov     ecx, ebx
0x18008b3dd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18008b3e2  mov     r9d, eax; char *
0x18008b3e5  mov     rcx, [rbp+88h]; this
0x18008b3ec  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18008b3f3  mov     edx, 19Bh; void *
0x18008b3f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
