# EapLm::Peer::BaseEapMethodConfig::LoadConfig(void)

- ea: `0x1800213a8`
- end: `0x1800216d3`
- name: `?LoadConfig@BaseEapMethodConfig@Peer@EapLm@@IEAAXXZ`
- size: `811`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodConfig *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020590`

## callees

- `0x18000eb74`
- `0x180015534`
- `0x1800165a4`
- `0x18001729c`
- `0x18001736c`
- `0x180020514`
- `0x1800213a8`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002a974`
- `0x18002ab2c`
- `0x18002ac10`

## string_xrefs

- `0x1800216c6`: `LoadConfig`
- `0x1800213ff`: `RegistryKey::Open`
- `0x18002165e`: `registry`
- `0x1800216bf`: `Peer: Path, FriendlyName`

## pseudocode

```c
void __fastcall EapLm::Peer::BaseEapMethodConfig::LoadConfig(EapLm::Peer::BaseEapMethodConfig *this)
{
  __int64 v2; // rax
  const wchar_t *v3; // rax
  __int64 v4; // rax
  int v5; // ecx
  int v6; // r9d
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r10
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r10
  _DWORD *v21; // rsi
  _DWORD *v22; // r14
  _DWORD *v23; // r15
  __int64 v24; // [rsp+40h] [rbp-18h] BYREF
  int v25; // [rsp+48h] [rbp-10h]

  v24 = 0;
  v25 = 1;
  v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 32);
  if ( (unsigned int)RegistryKey::Open(&v24, -2147483646, v2, 1) )
  {
    v3 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 32);
    EapHost::EapException::Throw(L"RegistryKey::Open", v3, -2147024809);
  }
  v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 456);
  if ( (unsigned int)RegistryKey::QueryValue(&v24, v4, (char *)this + 264) == 1
    || (v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 488),
        (unsigned int)RegistryKey::QueryValue(&v24, v7, (char *)this + 296) == 1) )
  {
    v21 = (_DWORD *)((char *)this + 24);
    v22 = (_DWORD *)((char *)this + 20);
    v23 = (_DWORD *)((char *)this + 28);
    if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
    {
      LOBYTE(v6) = *((_BYTE *)this + 16);
      McTemplateU0suqqq_EtwEventWriteTransfer(
        v5,
        (unsigned int)PeerMethodRegAccessFailure,
        (unsigned int)"registry",
        v6,
        *v23,
        *v22,
        *v21);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids,
        (unsigned int)*v23,
        *((unsigned __int8 *)this + 16),
        *v22,
        *v21);
    EapHost::EapException::Throw(L"LoadConfig", L"Peer: Path, FriendlyName", -2147024809);
  }
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 520);
  RegistryKey::QueryValue(&v24, v8, (char *)this + 257);
  v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 552);
  RegistryKey::QueryValue(&v24, v9, (char *)this + 258);
  if ( *((_BYTE *)this + 258) )
    *((_BYTE *)this + 257) = 1;
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 584);
  RegistryKey::QueryValue(&v24, v10, (char *)this + 259);
  v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 616);
  RegistryKey::QueryValue(&v24, v11, (char *)this + 260);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(
    (char *)this + 328,
    (char *)this + 264);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 648);
  RegistryKey::QueryValue(&v24, v12, (char *)this + 328);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 328);
    WPP_SF_S(*(_QWORD *)(v14 + 16), 12, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids, v13);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(
    (char *)this + 360,
    (char *)this + 264);
  v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 680);
  RegistryKey::QueryValue(&v24, v15, (char *)this + 360);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 360);
    WPP_SF_S(*(_QWORD *)(v17 + 16), 13, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids, v16);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(
    (char *)this + 392,
    (char *)this + 264);
  v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 712);
  RegistryKey::QueryValue(&v24, v18, (char *)this + 392);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 392);
    WPP_SF_S(*(_QWORD *)(v20 + 16), 14, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids, v19);
  }
  *((_BYTE *)this + 256) = 0;
  *((_BYTE *)this + 64) = 0;
  RegistryKey::Clear((RegistryKey *)&v24);
}

```

## disassembly

```asm
0x1800213a8  push    rbp
0x1800213aa  push    rbx
0x1800213ab  push    rsi
0x1800213ac  push    rdi
0x1800213ad  push    r14
0x1800213af  push    r15
0x1800213b1  mov     rbp, rsp
0x1800213b4  sub     rsp, 58h
0x1800213b8  mov     rdi, rcx
0x1800213bb  xor     r15d, r15d
0x1800213be  mov     [rbp+var_18], r15
0x1800213c2  mov     [rbp+var_10], 1
0x1800213c9  add     rcx, 20h ; ' '
0x1800213cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800213d2  lea     r9d, [r15+1]
0x1800213d6  mov     r8, rax
0x1800213d9  mov     rdx, 0FFFFFFFF80000002h
0x1800213e0  lea     rcx, [rbp+var_18]
0x1800213e4  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800213e9  test    eax, eax
0x1800213eb  jz      short loc_18002140C
0x1800213ed  lea     rcx, [rdi+20h]
0x1800213f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800213f6  mov     r8d, 80070057h; int
0x1800213fc  mov     rdx, rax; wchar_t *
0x1800213ff  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x180021406  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18002140c  lea     rcx, [rdi+1C8h]
0x180021413  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021418  lea     r14, [rdi+108h]
0x18002141f  mov     r8, r14
0x180021422  mov     rdx, rax
0x180021425  lea     rcx, [rbp+var_18]
0x180021429  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002142e  cmp     eax, 1
0x180021431  jz      loc_180021631
0x180021437  lea     rcx, [rdi+1E8h]
0x18002143e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021443  lea     r8, [rdi+128h]
0x18002144a  mov     rdx, rax
0x18002144d  lea     rcx, [rbp+var_18]
0x180021451  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x180021456  cmp     eax, 1
0x180021459  jz      loc_180021631
0x18002145f  lea     rcx, [rdi+208h]
0x180021466  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002146b  lea     rsi, [rdi+101h]
0x180021472  mov     r8, rsi
0x180021475  mov     rdx, rax
0x180021478  lea     rcx, [rbp+var_18]
0x18002147c  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x180021481  lea     rcx, [rdi+228h]
0x180021488  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002148d  lea     rbx, [rdi+102h]
0x180021494  mov     r8, rbx
0x180021497  mov     rdx, rax
0x18002149a  lea     rcx, [rbp+var_18]
0x18002149e  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x1800214a3  cmp     [rbx], r15b
0x1800214a6  jz      short loc_1800214AB
0x1800214a8  mov     byte ptr [rsi], 1
0x1800214ab  lea     rcx, [rdi+248h]
0x1800214b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800214b7  lea     r8, [rdi+103h]
0x1800214be  mov     rdx, rax
0x1800214c1  lea     rcx, [rbp+var_18]
0x1800214c5  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEA_N@Z; RegistryKey::QueryValue(wchar_t const *,bool &)
0x1800214ca  lea     rcx, [rdi+268h]
0x1800214d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800214d6  lea     r8, [rdi+104h]
0x1800214dd  mov     rdx, rax
0x1800214e0  lea     rcx, [rbp+var_18]
0x1800214e4  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x1800214e9  lea     rsi, [rdi+148h]
0x1800214f0  mov     rdx, r14
0x1800214f3  mov     rcx, rsi
0x1800214f6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800214fb  lea     rcx, [rdi+288h]
0x180021502  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021507  mov     r8, rsi
0x18002150a  mov     rdx, rax
0x18002150d  lea     rcx, [rbp+var_18]
0x180021511  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x180021516  lea     rbx, WPP_GLOBAL_Control
0x18002151d  mov     r10, cs:WPP_GLOBAL_Control
0x180021524  cmp     r10, rbx
0x180021527  jz      short loc_180021550
0x180021529  test    byte ptr [r10+1Ch], 4
0x18002152e  jz      short loc_180021550
0x180021530  mov     rcx, rsi
0x180021533  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021538  mov     edx, 0Ch
0x18002153d  mov     r9, rax
0x180021540  lea     r8, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids
0x180021547  mov     rcx, [r10+10h]
0x18002154b  call    WPP_SF_S
0x180021550  lea     rsi, [rdi+168h]
0x180021557  mov     rdx, r14
0x18002155a  mov     rcx, rsi
0x18002155d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180021562  lea     rcx, [rdi+2A8h]
0x180021569  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002156e  mov     r8, rsi
0x180021571  mov     rdx, rax
0x180021574  lea     rcx, [rbp+var_18]
0x180021578  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002157d  mov     r10, cs:WPP_GLOBAL_Control
0x180021584  cmp     r10, rbx
0x180021587  jz      short loc_1800215B0
0x180021589  test    byte ptr [r10+1Ch], 4
0x18002158e  jz      short loc_1800215B0
0x180021590  mov     rcx, rsi
0x180021593  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021598  mov     edx, 0Dh
0x18002159d  mov     r9, rax
0x1800215a0  lea     r8, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids
0x1800215a7  mov     rcx, [r10+10h]
0x1800215ab  call    WPP_SF_S
0x1800215b0  lea     rsi, [rdi+188h]
0x1800215b7  mov     rdx, r14
0x1800215ba  mov     rcx, rsi
0x1800215bd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800215c2  lea     rcx, [rdi+2C8h]
0x1800215c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800215ce  mov     r8, rsi
0x1800215d1  mov     rdx, rax
0x1800215d4  lea     rcx, [rbp+var_18]
0x1800215d8  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x1800215dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800215e4  cmp     r10, rbx
0x1800215e7  jz      short loc_180021610
0x1800215e9  test    byte ptr [r10+1Ch], 4
0x1800215ee  jz      short loc_180021610
0x1800215f0  mov     rcx, rsi
0x1800215f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800215f8  mov     edx, 0Eh
0x1800215fd  mov     r9, rax
0x180021600  lea     r8, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids
0x180021607  mov     rcx, [r10+10h]
0x18002160b  call    WPP_SF_S
0x180021610  mov     [rdi+100h], r15b
0x180021617  mov     [rdi+40h], r15b
0x18002161b  lea     rcx, [rbp+var_18]; this
0x18002161f  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180021624  add     rsp, 58h
0x180021628  pop     r15
0x18002162a  pop     r14
0x18002162c  pop     rdi
0x18002162d  pop     rsi
0x18002162e  pop     rbx
0x18002162f  pop     rbp
0x180021630  retn
0x180021631  lea     rsi, [rdi+18h]
0x180021635  lea     r14, [rdi+14h]
0x180021639  lea     r15, [rdi+1Ch]
0x18002163d  test    cs:Microsoft_Windows_EapHostEnableBits, 1
0x180021644  jz      short loc_180021671
0x180021646  mov     eax, [rsi]
0x180021648  mov     [rsp+58h+var_28], eax
0x18002164c  mov     eax, [r14]
0x18002164f  mov     [rsp+58h+var_30], eax
0x180021653  mov     eax, [r15]
0x180021656  mov     [rsp+58h+var_38], eax
0x18002165a  mov     r9b, [rdi+10h]
0x18002165e  lea     r8, aRegistry; "registry"
0x180021665  lea     rdx, PeerMethodRegAccessFailure
0x18002166c  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x180021671  lea     rbx, WPP_GLOBAL_Control
0x180021678  mov     rcx, cs:WPP_GLOBAL_Control
0x18002167f  cmp     rcx, rbx
0x180021682  jz      short loc_1800216B9
0x180021684  test    byte ptr [rcx+1Ch], 1
0x180021688  jz      short loc_1800216B9
0x18002168a  movzx   r8d, byte ptr [rdi+10h]
0x18002168f  mov     edx, 0Bh
0x180021694  mov     eax, [rsi]
0x180021696  mov     [rsp+58h+var_28], eax
0x18002169a  mov     eax, [r14]
0x18002169d  mov     [rsp+58h+var_30], eax
0x1800216a1  mov     [rsp+58h+var_38], r8d
0x1800216a6  mov     r9d, [r15]
0x1800216a9  lea     r8, WPP_45d70cafa4923834a06a90f9bf298a76_Traceguids
0x1800216b0  mov     rcx, [rcx+10h]
0x1800216b4  call    WPP_SF_dddd
0x1800216b9  mov     r8d, 80070057h; int
0x1800216bf  lea     rdx, aPeerPathFriend; "Peer: Path, FriendlyName"
0x1800216c6  lea     rcx, aLoadconfig; "LoadConfig"
0x1800216cd  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
