# PrinterFinder::IsAssociated(ushort const *)

- ea: `0x140007acc`
- end: `0x140007d80`
- name: `?IsAssociated@PrinterFinder@@QEAA_NPEBG@Z`
- size: `692`
- prototype: `bool(PrinterFinder *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000d2a4`

## callees

- `0x140002600`
- `0x14000315c`
- `0x1400034f8`
- `0x14000452c`
- `0x140007acc`
- `0x14000b8ac`
- `0x14000b8f4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140007b2f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140007d01`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140007b2f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140007d01`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140007aff`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140007ceb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140007c94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140007c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007cbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007cd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007cd1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140007cc9`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140007d11`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140007cc9`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140007d11`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x140007c7a`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x140007c7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall PrinterFinder::IsAssociated(PrinterFinder *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  _QWORD *v9; // rcx
  char **v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rsi
  __int64 v13; // rbx
  int ObjectQuery; // eax
  DWORD v15; // eax
  const char *v16; // r9
  __int64 v17; // rsi
  DWORD LastError; // ebx
  __int64 v19; // rax
  char v21; // [rsp+60h] [rbp-49h] BYREF
  __int64 v22; // [rsp+68h] [rbp-41h]
  __int64 v23; // [rsp+70h] [rbp-39h]
  __int128 v24; // [rsp+78h] [rbp-31h]
  int v25; // [rsp+88h] [rbp-21h]
  int v26; // [rsp+8Ch] [rbp-1Dh]
  __int64 v27; // [rsp+90h] [rbp-19h]
  int v28; // [rsp+98h] [rbp-11h]
  int v29; // [rsp+9Ch] [rbp-Dh]
  __int64 *v30; // [rsp+A0h] [rbp-9h]
  __int128 v31; // [rsp+A8h] [rbp-1h]
  int v32; // [rsp+B8h] [rbp+Fh]
  int v33; // [rsp+BCh] [rbp+13h]
  __int64 v34; // [rsp+C0h] [rbp+17h]
  char *v35; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Looking for aepId \"");
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, a2);
  v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, L"\" in AEP store...");
  std::basic_ostream<unsigned short>::operator<<(v6, std::endl<unsigned short,std::char_traits<unsigned short>>);
  *((_WORD *)this + 100) = 0;
  v8 = (_QWORD *)((char *)this + 136);
  *((_QWORD *)this + 19) = 0;
  if ( *((_QWORD *)this + 20) > 7u )
    v8 = (_QWORD *)*v8;
  *(_WORD *)v8 = 0;
  v9 = (_QWORD *)((char *)this + 168);
  *((_QWORD *)this + 23) = 0;
  if ( *((_QWORD *)this + 24) > 7u )
    v9 = (_QWORD *)*v9;
  *(_WORD *)v9 = 0;
  v10 = (char **)((char *)this + 208);
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > *((_QWORD *)this + 29) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v10, v11, v7, a2);
  }
  else
  {
    if ( *((_QWORD *)this + 29) <= 7u )
      v12 = (char *)this + 208;
    else
      v12 = *v10;
    *((_QWORD *)this + 28) = v11;
    v13 = 2 * v11;
    memmove_0(v12, a2, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
  }
  v23 = 2;
  v24 = DEVPKEY_Aep_ProtocolId;
  v25 = 5;
  v26 = 0;
  v27 = 0;
  v28 = 13;
  v29 = 16;
  v30 = DAF_ProtocolId_WSD;
  v34 = 1;
  v21 = -1;
  v31 = DEVPKEY_DasParam_AepStoreOnly;
  v32 = 4;
  v33 = 17;
  v35 = &v21;
  v22 = 0;
  ObjectQuery = DevCreateObjectQueryEx(5, 0, 4, (char *)this + 8);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)ObjectQuery,
      1);
  v15 = WaitForSingleObject(*(HANDLE *)this, 0xEA60u);
  if ( v15 == 258 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)0x800705B4LL,
      1);
  if ( v15 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      v16);
  v17 = v22;
  if ( v22 )
  {
    LastError = GetLastError();
    DevCloseObjectQuery(v17);
    SetLastError(LastError);
  }
  v22 = 0;
  if ( *((_QWORD *)this + 23) )
    return 1;
  v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"  Cannot find the printer.");
  std::basic_ostream<unsigned short>::operator<<(v19, std::endl<unsigned short,std::char_traits<unsigned short>>);
  if ( v22 )
    DevCloseObjectQuery(v22);
  return 0;
}

```

## disassembly

```asm
0x140007acc  mov     [rsp-8+arg_10], rbx
0x140007ad1  push    rbp
0x140007ad2  push    rsi
0x140007ad3  push    rdi
0x140007ad4  push    r14
0x140007ad6  push    r15
0x140007ad8  lea     rbp, [rsp-37h]
0x140007add  sub     rsp, 0E0h
0x140007ae4  mov     rax, cs:__security_cookie
0x140007aeb  xor     rax, rsp
0x140007aee  mov     [rbp+57h+var_30], rax
0x140007af2  mov     r14, rdx
0x140007af5  mov     rdi, rcx
0x140007af8  lea     rdx, aLookingForAepi; "Looking for aepId \""
0x140007aff  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140007b06  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140007b0b  mov     rcx, rax
0x140007b0e  mov     rdx, r14
0x140007b11  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140007b16  mov     rcx, rax
0x140007b19  lea     rdx, aInAepStore; "\" in AEP store..."
0x140007b20  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140007b25  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140007b2c  mov     rcx, rax
0x140007b2f  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x140007b35  xor     r15d, r15d
0x140007b38  mov     [rdi+0C8h], r15w
0x140007b40  lea     rcx, [rdi+88h]
0x140007b47  mov     [rcx+10h], r15
0x140007b4b  cmp     qword ptr [rcx+18h], 7
0x140007b50  jbe     short loc_140007B55
0x140007b52  mov     rcx, [rcx]
0x140007b55  mov     [rcx], r15w
0x140007b59  lea     rcx, [rdi+0A8h]
0x140007b60  mov     [rcx+10h], r15
0x140007b64  cmp     qword ptr [rcx+18h], 7
0x140007b69  jbe     short loc_140007B6E
0x140007b6b  mov     rcx, [rcx]
0x140007b6e  mov     [rcx], r15w
0x140007b72  lea     rcx, [rdi+0D0h]
0x140007b79  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140007b7d  inc     rdx
0x140007b80  cmp     [r14+rdx*2], r15w
0x140007b85  jnz     short loc_140007B7D
0x140007b87  cmp     rdx, [rcx+18h]
0x140007b8b  ja      short loc_140007BB9
0x140007b8d  cmp     qword ptr [rcx+18h], 7
0x140007b92  jbe     short loc_140007B99
0x140007b94  mov     rsi, [rcx]
0x140007b97  jmp     short loc_140007B9C
0x140007b99  mov     rsi, rcx
0x140007b9c  mov     [rcx+10h], rdx
0x140007ba0  lea     rbx, [rdx+rdx]
0x140007ba4  mov     r8, rbx; Size
0x140007ba7  mov     rdx, r14; Src
0x140007baa  mov     rcx, rsi; void *
0x140007bad  call    memmove_0
0x140007bb2  mov     [rbx+rsi], r15w
0x140007bb7  jmp     short loc_140007BC1
0x140007bb9  mov     r9, r14
0x140007bbc  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140007bc1  mov     [rbp+57h+var_90], 2
0x140007bc9  movups  xmm0, cs:DEVPKEY_Aep_ProtocolId
0x140007bd0  movups  [rbp+57h+var_88], xmm0
0x140007bd4  mov     eax, cs:dword_1400175D0
0x140007bda  mov     [rbp+57h+var_78], eax
0x140007bdd  mov     [rbp+57h+var_74], r15d
0x140007be1  mov     [rbp+57h+var_70], r15
0x140007be5  mov     [rbp+57h+var_68], 0Dh
0x140007bec  mov     [rbp+57h+var_64], 10h
0x140007bf3  lea     rax, DAF_ProtocolId_WSD
0x140007bfa  mov     [rbp+57h+var_60], rax
0x140007bfe  mov     [rbp+57h+var_40], 1
0x140007c06  mov     [rbp+57h+var_A0], 0FFh
0x140007c0a  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x140007c11  movups  [rbp+57h+var_58], xmm0
0x140007c15  mov     eax, cs:dword_140017630
0x140007c1b  mov     [rbp+57h+var_48], eax
0x140007c1e  mov     [rbp+57h+var_44], 11h
0x140007c25  mov     r14d, 1
0x140007c2b  lea     rax, [rbp+57h+var_A0]
0x140007c2f  mov     [rbp+57h+var_38], rax
0x140007c33  mov     [rbp+57h+var_98], r15
0x140007c37  lea     r9, [rdi+8]
0x140007c3b  lea     rax, [rbp+57h+var_98]
0x140007c3f  mov     [rsp+100h+var_B0], rax
0x140007c44  mov     [rsp+100h+var_B8], rdi
0x140007c49  lea     rax, ?_OnQueryComplete@PrinterFinder@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; PrinterFinder::_OnQueryComplete(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x140007c50  mov     [rsp+100h+var_C0], rax
0x140007c55  lea     rax, [rbp+57h+var_58]
0x140007c59  mov     [rsp+100h+var_C8], rax
0x140007c5e  mov     [rsp+100h+var_D0], r14d
0x140007c63  lea     rax, [rbp+57h+var_90]
0x140007c67  mov     [rsp+100h+var_D8], rax
0x140007c6c  mov     [rsp+100h+var_E0], r14d; int
0x140007c71  xor     edx, edx
0x140007c73  lea     ecx, [rdx+5]
0x140007c76  lea     r8d, [r14+3]
0x140007c7a  call    cs:__imp_DevCreateObjectQueryEx
0x140007c80  mov     rcx, [rbp+5Fh]; this
0x140007c84  test    eax, eax
0x140007c86  js      loc_140007D53
0x140007c8c  mov     edx, 0EA60h; dwMilliseconds
0x140007c91  mov     rcx, [rdi]; hHandle
0x140007c94  call    cs:__imp_WaitForSingleObject
0x140007c9a  mov     rcx, [rbp+5Fh]; this
0x140007c9e  cmp     eax, 102h
0x140007ca3  jz      loc_140007D68
0x140007ca9  mov     rcx, [rbp+5Fh]; this
0x140007cad  test    eax, eax
0x140007caf  jnz     loc_140007D41
0x140007cb5  mov     rsi, [rbp+57h+var_98]
0x140007cb9  test    rsi, rsi
0x140007cbc  jz      short loc_140007CD7
0x140007cbe  call    cs:__imp_GetLastError
0x140007cc4  mov     ebx, eax
0x140007cc6  mov     rcx, rsi
0x140007cc9  call    cs:__imp_DevCloseObjectQuery
0x140007ccf  mov     ecx, ebx; dwErrCode
0x140007cd1  call    cs:__imp_SetLastError
0x140007cd7  mov     [rbp+57h+var_98], r15
0x140007cdb  cmp     [rdi+0B8h], r15
0x140007ce2  jnz     short loc_140007D1B
0x140007ce4  lea     rdx, aCannotFindTheP; "  Cannot find the printer."
0x140007ceb  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140007cf2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140007cf7  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140007cfe  mov     rcx, rax
0x140007d01  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x140007d07  nop
0x140007d08  mov     rcx, [rbp+57h+var_98]
0x140007d0c  test    rcx, rcx
0x140007d0f  jz      short loc_140007D17
0x140007d11  call    cs:__imp_DevCloseObjectQuery
0x140007d17  xor     al, al
0x140007d19  jmp     short loc_140007D1E
0x140007d1b  mov     al, r14b
0x140007d1e  mov     rcx, [rbp+57h+var_30]
0x140007d22  xor     rcx, rsp; StackCookie
0x140007d25  call    __security_check_cookie
0x140007d2a  mov     rbx, [rsp+100h+arg_10]
0x140007d32  add     rsp, 0E0h
0x140007d39  pop     r15
0x140007d3b  pop     r14
0x140007d3d  pop     rdi
0x140007d3e  pop     rsi
0x140007d3f  pop     rbp
0x140007d40  retn
0x140007d41  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140007d48  mov     edx, 72h ; 'r'; void *
0x140007d4d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140007d53  mov     r9d, eax; char *
0x140007d56  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140007d5d  mov     edx, 6Eh ; 'n'; void *
0x140007d62  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140007d68  mov     r9d, 800705B4h; char *
0x140007d6e  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140007d75  mov     edx, 71h ; 'q'; void *
0x140007d7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
