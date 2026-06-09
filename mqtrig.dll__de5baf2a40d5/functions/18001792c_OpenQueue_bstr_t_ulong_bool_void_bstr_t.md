# OpenQueue(_bstr_t,ulong,bool,void * *,_bstr_t *)

- ea: `0x18001792c`
- end: `0x180017c3c`
- name: `?OpenQueue@@YAJV_bstr_t@@K_NPEAPEAXPEAV1@@Z`
- size: `784`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, QUEUEHANDLE *, _bstr_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18000d520`

## callees

- `0x180002ec8`
- `0x180004dfc`
- `0x18000544c`
- `0x180005704`
- `0x180005740`
- `0x18000578c`
- `0x180005888`
- `0x180009ab0`
- `0x180014ae8`
- `0x1800175dc`
- `0x1800176ec`
- `0x180017890`
- `0x18001792c`

## import_xrefs

- `msvcrt!free` at `0x180017af8`
- `msvcrt!free` at `0x180017b8a`
- `msvcrt!free` at `0x180017bc5`
- `msvcrt!free` at `0x180017af8`
- `msvcrt!free` at `0x180017b8a`
- `msvcrt!free` at `0x180017bc5`
- `mqrt!MQOpenQueue` at `0x180017a87`
- `mqrt!MQOpenQueue` at `0x180017bba`
- `mqrt!MQOpenQueue` at `0x180017a87`
- `mqrt!MQOpenQueue` at `0x180017bba`
- `mqrt!MQPathNameToFormatName` at `0x180017ade`
- `mqrt!MQPathNameToFormatName` at `0x180017b38`
- `mqrt!MQPathNameToFormatName` at `0x180017ade`
- `mqrt!MQPathNameToFormatName` at `0x180017b38`

## pseudocode

```c
__int64 __fastcall OpenQueue(__int64 **a1, __int64 a2, __int64 a3, QUEUEHANDLE *a4, _bstr_t *a5)
{
  __int64 *v7; // rax
  __int64 *v8; // rax
  char v9; // r15
  __int64 v10; // rdx
  _QWORD *v11; // rax
  bool v12; // si
  _bstr_t *v13; // rax
  char v14; // bl
  __int64 *v15; // rax
  const WCHAR *v16; // rcx
  HRESULT v17; // eax
  HRESULT v18; // ebx
  WCHAR *v19; // rsi
  const WCHAR *v20; // rcx
  WCHAR *v21; // rax
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rcx
  void *v25; // [rsp+30h] [rbp-41h] BYREF
  DWORD dwFormatNameLength; // [rsp+38h] [rbp-39h] BYREF
  _QWORD v27[3]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v28; // [rsp+58h] [rbp-19h]
  __int128 v29; // [rsp+68h] [rbp-9h]
  _BYTE v30[40]; // [rsp+78h] [rbp+7h] BYREF

  v27[1] = a1;
  dwFormatNameLength = 0;
  _bstr_t::operator=(a5, &psz);
  v28 = 0;
  v29 = 0;
  v7 = *a1;
  v25 = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)v7 + 4);
  if ( (unsigned int)IsSystemQueue(&v25) )
  {
    v9 = 1;
    v12 = 1;
    _bstr_t::operator=(a5, a1);
  }
  else
  {
    v8 = *a1;
    v25 = v8;
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)v8 + 4);
    v9 = IsQueueLocal(&v25);
    if ( *a1 )
      v10 = **a1;
    else
      v10 = 0;
    v11 = (_QWORD *)std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
                      (__int64)v30,
                      v10);
    v12 = IsPrivateQPath(v11);
  }
  v13 = _bstr_t::_bstr_t((_bstr_t *)&v25, &psz);
  v14 = _bstr_t::operator==(a5, v13);
  _bstr_t::_Free((_bstr_t *)&v25);
  if ( v14 )
  {
    v15 = *a1;
    v27[0] = v15;
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)v15 + 4);
    v27[2] = v27;
    _bstr_t::_bstr_t((_bstr_t *)&v25, L"DIRECT=OS:");
    dwFormatNameLength = 1;
    _bstr_t::operator+=((struct _bstr_t *)&v25, (struct _bstr_t *)v27);
    _bstr_t::_Free((_bstr_t *)v27);
    _bstr_t::operator=(a5, &v25);
    _bstr_t::_Free((_bstr_t *)&v25);
  }
  if ( *(_QWORD *)a5 )
    v16 = **(const WCHAR ***)a5;
  else
    v16 = 0;
  v17 = MQOpenQueue(v16, 2u, 0, a4);
  v18 = v17;
  if ( v17 >= 0 )
    goto LABEL_41;
  if ( v17 == -1072824288 && (v9 || !v12) )
  {
    dwFormatNameLength = 512;
    v19 = (WCHAR *)MmAllocate(0x402u);
    v25 = v19;
    if ( *a1 )
      v20 = (const WCHAR *)**a1;
    else
      v20 = 0;
    v18 = MQPathNameToFormatName(v20, v19, &dwFormatNameLength);
    if ( v18 == -1072824289 )
    {
      v25 = 0;
      free(v19);
      v21 = (WCHAR *)MmAllocate(saturated_mul(dwFormatNameLength + 1, 2u));
      v19 = v21;
      v25 = v21;
      v22 = (const WCHAR *)*a1;
      if ( *a1 )
        v22 = *(const WCHAR **)v22;
      v18 = MQPathNameToFormatName(v22, v21, &dwFormatNameLength);
    }
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18);
      free(v19);
      goto LABEL_42;
    }
    _bstr_t::operator=(a5, v19);
    v23 = *(_QWORD *)a5 ? **(const WCHAR ***)a5 : 0LL;
    v18 = MQOpenQueue(v23, 2u, 0, a4);
    free(v19);
    if ( v18 >= 0 )
    {
LABEL_41:
      v18 = 0;
      goto LABEL_42;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18);
LABEL_42:
  _bstr_t::_Free((_bstr_t *)a1);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001792c  mov     [rsp-8+arg_8], rbx
0x180017931  mov     [rsp-8+arg_10], rsi
0x180017936  push    rbp
0x180017937  push    rdi
0x180017938  push    r12
0x18001793a  push    r14
0x18001793c  push    r15
0x18001793e  lea     rbp, [rsp-2Fh]
0x180017943  sub     rsp, 0A0h
0x18001794a  mov     r12, r9
0x18001794d  mov     rdi, rcx
0x180017950  mov     r14, [rbp+4Fh+arg_20]
0x180017954  mov     [rbp+4Fh+var_78], rcx
0x180017958  mov     [rbp+4Fh+dwFormatNameLength], 0
0x18001795f  lea     rdx, psz
0x180017966  mov     rcx, r14
0x180017969  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18001796e  xorps   xmm0, xmm0
0x180017971  movups  [rbp+4Fh+var_68], xmm0
0x180017975  movups  [rbp+4Fh+var_58], xmm0
0x180017979  mov     rax, [rdi]
0x18001797c  mov     [rbp+4Fh+var_90], rax
0x180017980  test    rax, rax
0x180017983  jz      short loc_180017989
0x180017985  lock inc dword ptr [rax+10h]
0x180017989  lea     rcx, [rbp+4Fh+var_90]
0x18001798d  call    ?IsSystemQueue@@YA?AW4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@V_bstr_t@@@Z; IsSystemQueue(_bstr_t)
0x180017992  test    eax, eax
0x180017994  jnz     short loc_1800179D7
0x180017996  mov     rax, [rdi]
0x180017999  mov     [rbp+4Fh+var_90], rax
0x18001799d  test    rax, rax
0x1800179a0  jz      short loc_1800179A6
0x1800179a2  lock inc dword ptr [rax+10h]
0x1800179a6  lea     rcx, [rbp+4Fh+var_90]
0x1800179aa  call    ?IsQueueLocal@@YA_NV_bstr_t@@@Z; IsQueueLocal(_bstr_t)
0x1800179af  mov     r15b, al
0x1800179b2  mov     rcx, [rdi]
0x1800179b5  test    rcx, rcx
0x1800179b8  jz      short loc_1800179BF
0x1800179ba  mov     rdx, [rcx]
0x1800179bd  jmp     short loc_1800179C1
0x1800179bf  xor     edx, edx
0x1800179c1  lea     rcx, [rbp+4Fh+var_48]
0x1800179c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x1800179ca  mov     rcx, rax
0x1800179cd  call    ?IsPrivateQPath@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; IsPrivateQPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>)
0x1800179d2  mov     sil, al
0x1800179d5  jmp     short loc_1800179E8
0x1800179d7  mov     r15b, 1
0x1800179da  mov     sil, r15b
0x1800179dd  mov     rdx, rdi
0x1800179e0  mov     rcx, r14
0x1800179e3  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800179e8  lea     rdx, psz; wchar_t *
0x1800179ef  lea     rcx, [rbp+4Fh+var_90]; this
0x1800179f3  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1800179f8  mov     rdx, rax
0x1800179fb  mov     rcx, r14
0x1800179fe  call    ??8_bstr_t@@QEBA_NAEBV0@@Z; _bstr_t::operator==(_bstr_t const &)
0x180017a03  mov     bl, al
0x180017a05  lea     rcx, [rbp+4Fh+var_90]; this
0x180017a09  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017a0e  test    bl, bl
0x180017a10  jz      short loc_180017A6E
0x180017a12  mov     rax, [rdi]
0x180017a15  mov     [rbp+4Fh+var_80], rax
0x180017a19  test    rax, rax
0x180017a1c  jz      short loc_180017A22
0x180017a1e  lock inc dword ptr [rax+10h]
0x180017a22  lea     rax, [rbp+4Fh+var_80]
0x180017a26  mov     [rbp+4Fh+var_70], rax
0x180017a2a  lea     rdx, aDirectOs; "DIRECT=OS:"
0x180017a31  lea     rcx, [rbp+4Fh+var_90]; this
0x180017a35  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180017a3a  mov     [rbp+4Fh+dwFormatNameLength], 1
0x180017a41  lea     rdx, [rbp+4Fh+var_80]; struct _bstr_t *
0x180017a45  lea     rcx, [rbp+4Fh+var_90]; struct _bstr_t *
0x180017a49  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180017a4e  nop
0x180017a4f  lea     rcx, [rbp+4Fh+var_80]; this
0x180017a53  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017a58  lea     rdx, [rbp+4Fh+var_90]
0x180017a5c  mov     rcx, r14
0x180017a5f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180017a64  nop
0x180017a65  lea     rcx, [rbp+4Fh+var_90]; this
0x180017a69  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017a6e  mov     rax, [r14]
0x180017a71  test    rax, rax
0x180017a74  jz      short loc_180017A7B
0x180017a76  mov     rcx, [rax]
0x180017a79  jmp     short loc_180017A7D
0x180017a7b  xor     ecx, ecx; lpwcsFormatName
0x180017a7d  mov     r9, r12; phQueue
0x180017a80  xor     r8d, r8d; dwShareMode
0x180017a83  lea     edx, [r8+2]; dwAccess
0x180017a87  call    cs:__imp_MQOpenQueue
0x180017a8d  mov     ebx, eax
0x180017a8f  test    eax, eax
0x180017a91  jns     loc_180017C14
0x180017a97  cmp     eax, 0C00E0020h
0x180017a9c  jnz     loc_180017BD0
0x180017aa2  test    r15b, r15b
0x180017aa5  jnz     short loc_180017AB0
0x180017aa7  test    sil, sil
0x180017aaa  jnz     loc_180017BD0
0x180017ab0  mov     [rbp+4Fh+dwFormatNameLength], 200h
0x180017ab7  mov     ecx, 402h; unsigned __int64
0x180017abc  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180017ac1  mov     rsi, rax
0x180017ac4  mov     [rbp+4Fh+var_90], rax
0x180017ac8  mov     rax, [rdi]
0x180017acb  test    rax, rax
0x180017ace  jz      short loc_180017AD5
0x180017ad0  mov     rcx, [rax]
0x180017ad3  jmp     short loc_180017AD7
0x180017ad5  xor     ecx, ecx; lpwcsPathName
0x180017ad7  lea     r8, [rbp+4Fh+dwFormatNameLength]; lpdwFormatNameLength
0x180017adb  mov     rdx, rsi; lpwcsFormatName
0x180017ade  call    cs:__imp_MQPathNameToFormatName
0x180017ae4  mov     ebx, eax
0x180017ae6  cmp     eax, 0C00E001Fh
0x180017aeb  jnz     short loc_180017B40
0x180017aed  mov     [rbp+4Fh+var_90], 0
0x180017af5  mov     rcx, rsi; Block
0x180017af8  call    cs:__imp_free
0x180017afe  nop
0x180017aff  mov     ecx, [rbp+4Fh+dwFormatNameLength]
0x180017b02  inc     ecx
0x180017b04  mov     eax, 2
0x180017b09  mul     rcx
0x180017b0c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017b13  cmovb   rax, rcx
0x180017b17  mov     rcx, rax; unsigned __int64
0x180017b1a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180017b1f  mov     rsi, rax
0x180017b22  mov     [rbp+4Fh+var_90], rax
0x180017b26  mov     rcx, [rdi]
0x180017b29  test    rcx, rcx
0x180017b2c  jz      short loc_180017B31
0x180017b2e  mov     rcx, [rcx]; lpwcsPathName
0x180017b31  lea     r8, [rbp+4Fh+dwFormatNameLength]; lpdwFormatNameLength
0x180017b35  mov     rdx, rax; lpwcsFormatName
0x180017b38  call    cs:__imp_MQPathNameToFormatName
0x180017b3e  mov     ebx, eax
0x180017b40  test    ebx, ebx
0x180017b42  jns     short loc_180017B96
0x180017b44  lea     rax, WPP_GLOBAL_Control
0x180017b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b52  cmp     rcx, rax
0x180017b55  jz      short loc_180017B87
0x180017b57  test    byte ptr [rcx+1Ch], 1
0x180017b5b  jz      short loc_180017B87
0x180017b5d  mov     rax, [rdi]
0x180017b60  test    rax, rax
0x180017b63  jz      short loc_180017B6A
0x180017b65  mov     r9, [rax]
0x180017b68  jmp     short loc_180017B6D
0x180017b6a  xor     r9d, r9d
0x180017b6d  mov     edx, 0Dh
0x180017b72  mov     dword ptr [rsp+0C0h+var_A0], ebx; char
0x180017b76  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x180017b7d  mov     rcx, [rcx+10h]; LoggerHandle
0x180017b81  call    WPP_SF_SD
0x180017b86  nop
0x180017b87  mov     rcx, rsi; Block
0x180017b8a  call    cs:__imp_free
0x180017b90  nop
0x180017b91  jmp     loc_180017C16
0x180017b96  mov     rdx, rsi
0x180017b99  mov     rcx, r14
0x180017b9c  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180017ba1  mov     rax, [r14]
0x180017ba4  test    rax, rax
0x180017ba7  jz      short loc_180017BAE
0x180017ba9  mov     rcx, [rax]
0x180017bac  jmp     short loc_180017BB0
0x180017bae  xor     ecx, ecx; lpwcsFormatName
0x180017bb0  mov     r9, r12; phQueue
0x180017bb3  xor     r8d, r8d; dwShareMode
0x180017bb6  lea     edx, [r8+2]; dwAccess
0x180017bba  call    cs:__imp_MQOpenQueue
0x180017bc0  mov     ebx, eax
0x180017bc2  mov     rcx, rsi; Block
0x180017bc5  call    cs:__imp_free
0x180017bcb  nop
0x180017bcc  test    ebx, ebx
0x180017bce  jns     short loc_180017C14
0x180017bd0  lea     rax, WPP_GLOBAL_Control
0x180017bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bde  cmp     rcx, rax
0x180017be1  jz      short loc_180017C16
0x180017be3  test    byte ptr [rcx+1Ch], 1
0x180017be7  jz      short loc_180017C16
0x180017be9  mov     rax, [rdi]
0x180017bec  test    rax, rax
0x180017bef  jz      short loc_180017BF6
0x180017bf1  mov     r9, [rax]
0x180017bf4  jmp     short loc_180017BF9
0x180017bf6  xor     r9d, r9d
0x180017bf9  mov     edx, 0Eh
0x180017bfe  mov     dword ptr [rsp+0C0h+var_A0], ebx; char
0x180017c02  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x180017c09  mov     rcx, [rcx+10h]; LoggerHandle
0x180017c0d  call    WPP_SF_SD
0x180017c12  jmp     short loc_180017C16
0x180017c14  xor     ebx, ebx
0x180017c16  mov     rcx, rdi; this
0x180017c19  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180017c1e  mov     eax, ebx
0x180017c20  lea     r11, [rsp+0C0h+var_20]
0x180017c28  mov     rbx, [r11+38h]
0x180017c2c  mov     rsi, [r11+40h]
0x180017c30  mov     rsp, r11
0x180017c33  pop     r15
0x180017c35  pop     r14
0x180017c37  pop     r12
0x180017c39  pop     rdi
0x180017c3a  pop     rbp
0x180017c3b  retn
```
