# PrinterFinder::_FindPrinterOnNetwork(ushort const *)

- ea: `0x14000afac`
- end: `0x14000b467`
- name: `?_FindPrinterOnNetwork@PrinterFinder@@AEAA_NPEBG@Z`
- size: `1211`
- prototype: `bool(PrinterFinder *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005f00`

## callees

- `0x140002600`
- `0x14000315c`
- `0x1400034f8`
- `0x14000452c`
- `0x14000466c`
- `0x14000afac`
- `0x14000b8ac`
- `0x14000b8f4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b019`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b3e1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b019`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b3e1`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000afe9`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b3cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b36c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b39d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b3b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b3b0`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x14000b3a8`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x14000b3f2`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x14000b3a8`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x14000b3f2`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x14000b34f`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x14000b34f`

## string_xrefs

- `0x14000b138`: `/StableWSDiscoveryEndpoint/schemas-xmlsoap-org_ws_2005_04_discovery`
- `0x14000b150`: `/StableWSDiscoveryEndpoint/schemas-xmlsoap-org_ws_2005_04_discovery`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall PrinterFinder::_FindPrinterOnNetwork(PrinterFinder *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  _QWORD *v9; // rcx
  char **v10; // rbx
  char *v11; // rsi
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r15
  char *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // r14
  char *v18; // rsi
  int ObjectQuery; // eax
  DWORD v20; // eax
  const char *v21; // r9
  __int64 v22; // rax
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Looking for printer \"");
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, a2);
  v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, L"\" on the network...");
  std::basic_ostream<unsigned short>::operator<<(v6, std::endl<unsigned short,std::char_traits<unsigned short>>);
  *((_WORD *)this + 100) = 0;
  v8 = (_QWORD *)((char *)this + 168);
  *((_QWORD *)this + 23) = 0;
  if ( *((_QWORD *)this + 24) > 7u )
    v8 = (_QWORD *)*v8;
  *(_WORD *)v8 = 0;
  v9 = (_QWORD *)((char *)this + 208);
  *((_QWORD *)this + 28) = 0;
  if ( *((_QWORD *)this + 29) > 7u )
    v9 = (_QWORD *)*v9;
  *(_WORD *)v9 = 0;
  v10 = (char **)((char *)this + 136);
  if ( *((_QWORD *)this + 20) < 7u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char *)this + 136,
      7,
      v7,
      L"http://");
  }
  else
  {
    if ( *((_QWORD *)this + 20) <= 7u )
      v11 = (char *)this + 136;
    else
      v11 = *v10;
    *((_QWORD *)this + 19) = 7;
    memmove_0(v11, L"http://", 0xEu);
    *((_WORD *)v11 + 7) = 0;
  }
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = *((_QWORD *)this + 19);
  if ( v12 > *((_QWORD *)this + 20) - v13 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      (char *)this + 136,
      v12);
  }
  else
  {
    v14 = v13 + v12;
    *((_QWORD *)this + 19) = v13 + v12;
    if ( *((_QWORD *)this + 20) <= 7u )
      v15 = (char *)this + 136;
    else
      v15 = *v10;
    memmove_0(&v15[2 * v13], a2, 2 * v12);
    *(_WORD *)&v15[2 * v14] = 0;
  }
  v16 = *((_QWORD *)this + 19);
  if ( (unsigned __int64)(*((_QWORD *)this + 20) - v16) < 0x43 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      (char *)this + 136,
      67);
  }
  else
  {
    v17 = v16 + 67;
    *((_QWORD *)this + 19) = v16 + 67;
    if ( *((_QWORD *)this + 20) <= 7u )
      v18 = (char *)this + 136;
    else
      v18 = *v10;
    memmove_0(&v18[2 * v16], L"/StableWSDiscoveryEndpoint/schemas-xmlsoap-org_ws_2005_04_discovery", 0x86u);
    *(_WORD *)&v18[2 * v17] = 0;
  }
  ObjectQuery = DevCreateObjectQueryEx(5, 0, 4, (char *)this + 8);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)ObjectQuery,
      8);
  v20 = WaitForSingleObject(*(HANDLE *)this, 0xEA60u);
  if ( v20 == 258 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)0x800705B4LL,
      8);
  if ( v20 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      v21);
  if ( *((_QWORD *)this + 23) )
    return 1;
  v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"  Cannot find the printer.");
  std::basic_ostream<unsigned short>::operator<<(v22, std::endl<unsigned short,std::char_traits<unsigned short>>);
  return 0;
}

```

## disassembly

```asm
0x14000afac  mov     [rsp-8+arg_10], rbx
0x14000afb1  push    rbp
0x14000afb2  push    rsi
0x14000afb3  push    rdi
0x14000afb4  push    r12
0x14000afb6  push    r13
0x14000afb8  push    r14
0x14000afba  push    r15
0x14000afbc  lea     rbp, [rsp-160h]
0x14000afc4  sub     rsp, 260h
0x14000afcb  mov     rax, cs:__security_cookie
0x14000afd2  xor     rax, rsp
0x14000afd5  mov     [rbp+190h+var_40], rax
0x14000afdc  mov     r14, rdx
0x14000afdf  mov     rdi, rcx
0x14000afe2  lea     rdx, aLookingForPrin; "Looking for printer \""
0x14000afe9  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000aff0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000aff5  mov     rcx, rax
0x14000aff8  mov     rdx, r14
0x14000affb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b000  mov     rcx, rax
0x14000b003  lea     rdx, aOnTheNetwork; "\" on the network..."
0x14000b00a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b00f  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b016  mov     rcx, rax
0x14000b019  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b01f  xor     r12d, r12d
0x14000b022  mov     [rdi+0C8h], r12w
0x14000b02a  lea     rcx, [rdi+0A8h]
0x14000b031  mov     [rcx+10h], r12
0x14000b035  lea     r13d, [r12+7]
0x14000b03a  cmp     [rcx+18h], r13
0x14000b03e  jbe     short loc_14000B043
0x14000b040  mov     rcx, [rcx]
0x14000b043  mov     [rcx], r12w
0x14000b047  lea     rcx, [rdi+0D0h]
0x14000b04e  mov     [rcx+10h], r12
0x14000b052  cmp     [rcx+18h], r13
0x14000b056  jbe     short loc_14000B05B
0x14000b058  mov     rcx, [rcx]
0x14000b05b  mov     [rcx], r12w
0x14000b05f  lea     rbx, [rdi+88h]
0x14000b066  cmp     [rbx+18h], r13
0x14000b06a  jb      short loc_14000B096
0x14000b06c  jbe     short loc_14000B073
0x14000b06e  mov     rsi, [rbx]
0x14000b071  jmp     short loc_14000B076
0x14000b073  mov     rsi, rbx
0x14000b076  mov     [rbx+10h], r13
0x14000b07a  mov     r8d, 0Eh; Size
0x14000b080  lea     rdx, aHttp; "http://"
0x14000b087  mov     rcx, rsi; void *
0x14000b08a  call    memmove_0
0x14000b08f  mov     [rsi+0Eh], r12w
0x14000b094  jmp     short loc_14000B0A8
0x14000b096  lea     r9, aHttp; "http://"
0x14000b09d  mov     rdx, r13
0x14000b0a0  mov     rcx, rbx
0x14000b0a3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b0a8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b0ac  inc     rdx
0x14000b0af  cmp     [r14+rdx*2], r12w
0x14000b0b4  jnz     short loc_14000B0AC
0x14000b0b6  mov     rcx, [rbx+10h]
0x14000b0ba  mov     rax, [rbx+18h]
0x14000b0be  sub     rax, rcx
0x14000b0c1  cmp     rdx, rax
0x14000b0c4  ja      short loc_14000B0F3
0x14000b0c6  lea     r15, [rcx+rdx]
0x14000b0ca  mov     [rbx+10h], r15
0x14000b0ce  cmp     [rbx+18h], r13
0x14000b0d2  jbe     short loc_14000B0D9
0x14000b0d4  mov     rsi, [rbx]
0x14000b0d7  jmp     short loc_14000B0DC
0x14000b0d9  mov     rsi, rbx
0x14000b0dc  lea     r8, [rdx+rdx]; Size
0x14000b0e0  lea     rcx, [rsi+rcx*2]; void *
0x14000b0e4  mov     rdx, r14; Src
0x14000b0e7  call    memmove_0
0x14000b0ec  mov     [rsi+r15*2], r12w
0x14000b0f1  jmp     short loc_14000B103
0x14000b0f3  mov     [rsp+290h+var_270], rdx; __int64
0x14000b0f8  mov     r9, r14
0x14000b0fb  mov     rcx, rbx; Src
0x14000b0fe  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000b103  mov     rcx, [rbx+10h]
0x14000b107  mov     rax, [rbx+18h]
0x14000b10b  sub     rax, rcx
0x14000b10e  mov     edx, 43h ; 'C'
0x14000b113  cmp     rax, rdx
0x14000b116  jb      short loc_14000B14B
0x14000b118  lea     r14, [rcx+43h]
0x14000b11c  mov     [rbx+10h], r14
0x14000b120  cmp     [rbx+18h], r13
0x14000b124  jbe     short loc_14000B12B
0x14000b126  mov     rsi, [rbx]
0x14000b129  jmp     short loc_14000B12E
0x14000b12b  mov     rsi, rbx
0x14000b12e  lea     rcx, [rsi+rcx*2]; void *
0x14000b132  mov     r8d, 86h; Size
0x14000b138  lea     rdx, aStablewsdiscov; "/StableWSDiscoveryEndpoint/schemas-xmls"...
0x14000b13f  call    memmove_0
0x14000b144  mov     [rsi+r14*2], r12w
0x14000b149  jmp     short loc_14000B15F
0x14000b14b  mov     [rsp+290h+var_270], rdx; __int64
0x14000b150  lea     r9, aStablewsdiscov; "/StableWSDiscoveryEndpoint/schemas-xmls"...
0x14000b157  mov     rcx, rbx; Src
0x14000b15a  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000b15f  mov     [rbp+190h+var_200], 100000h
0x14000b166  xorps   xmm0, xmm0
0x14000b169  movups  [rbp+190h+var_1F8], xmm0
0x14000b16d  movups  [rbp+190h+var_1E8], xmm0
0x14000b171  movups  [rbp+190h+var_1D8], xmm0
0x14000b175  mov     [rbp+190h+var_1C8], 2
0x14000b17c  movups  xmm0, cs:DEVPKEY_Aep_ProtocolId
0x14000b183  movaps  [rbp+190h+var_1C0], xmm0
0x14000b187  mov     eax, cs:dword_1400175D0
0x14000b18d  mov     [rbp+190h+var_1B0], eax
0x14000b190  mov     [rbp+190h+var_1AC], r12d
0x14000b194  mov     [rbp+190h+var_1A8], r12
0x14000b198  mov     [rbp+190h+var_1A0], 0Dh
0x14000b19f  mov     [rbp+190h+var_19C], 10h
0x14000b1a6  lea     rax, DAF_ProtocolId_WSD
0x14000b1ad  mov     [rbp+190h+var_198], rax
0x14000b1b1  mov     [rbp+190h+var_190], 300000h
0x14000b1b8  xorps   xmm0, xmm0
0x14000b1bb  movups  [rbp+190h+var_188], xmm0
0x14000b1bf  movups  [rbp+190h+var_178], xmm0
0x14000b1c3  movups  [rbp+190h+var_168], xmm0
0x14000b1c7  mov     [rbp+190h+var_158], 2000h
0x14000b1ce  movups  xmm1, cs:DEVPKEY_Aep_Category
0x14000b1d5  movaps  [rbp+190h+var_150], xmm1
0x14000b1d9  mov     eax, cs:dword_140017600
0x14000b1df  mov     [rbp+190h+var_140], eax
0x14000b1e2  mov     [rbp+190h+var_13C], r12d
0x14000b1e6  mov     [rbp+190h+var_138], r12
0x14000b1ea  mov     r8d, 12h
0x14000b1f0  mov     [rbp+190h+var_130], r8d
0x14000b1f4  mov     [rbp+190h+var_12C], r8d
0x14000b1f8  lea     rcx, aPrintfax; "PrintFax"
0x14000b1ff  mov     [rbp+190h+var_128], rcx
0x14000b203  mov     edx, 1000h
0x14000b208  mov     [rbp+190h+var_120], edx
0x14000b20b  movups  [rbp+190h+var_118], xmm1
0x14000b20f  mov     [rbp+190h+var_108], eax
0x14000b215  mov     [rbp+190h+var_104], r12d
0x14000b21c  mov     [rbp+190h+var_100], r12
0x14000b223  mov     [rbp+190h+var_F8], r8d
0x14000b22a  mov     [rbp+190h+var_F4], 22h ; '"'
0x14000b234  lea     rcx, aPrintfaxPrinte; "PrintFax.Printer"
0x14000b23b  mov     [rbp+190h+var_F0], rcx
0x14000b242  mov     [rbp+190h+var_E8], edx
0x14000b248  movaps  [rbp+190h+var_E0], xmm1
0x14000b24f  mov     [rbp+190h+var_D0], eax
0x14000b255  mov     [rbp+190h+var_CC], r12d
0x14000b25c  mov     [rbp+190h+var_C8], r12
0x14000b263  mov     [rbp+190h+var_C0], r8d
0x14000b26a  mov     [rbp+190h+var_BC], 1Ah
0x14000b274  lea     rax, aPrintfaxMfp; "PrintFax.MFP"
0x14000b27b  mov     [rbp+190h+var_B8], rax
0x14000b282  mov     [rbp+190h+var_B0], 400000h
0x14000b28c  movups  [rbp+190h+var_A8], xmm0
0x14000b293  movups  [rbp+190h+var_98], xmm0
0x14000b29a  movups  [rbp+190h+var_88], xmm0
0x14000b2a1  mov     [rbp+190h+var_78], 200000h
0x14000b2ab  xorps   xmm1, xmm1
0x14000b2ae  movups  [rbp+190h+var_70], xmm1
0x14000b2b5  movups  [rbp+190h+var_60], xmm1
0x14000b2bc  movups  [rbp+190h+var_50], xmm1
0x14000b2c3  mov     [rbp+190h+var_20C], r12d
0x14000b2c7  movups  xmm0, cs:DEVPKEY_PNPX_RemoteAddress
0x14000b2ce  movups  [rsp+290h+var_228], xmm0
0x14000b2d3  mov     eax, cs:dword_140016638
0x14000b2d9  mov     [rsp+290h+var_218], eax
0x14000b2dd  mov     [rsp+290h+var_214], r8d
0x14000b2e2  mov     eax, [rdi+98h]
0x14000b2e8  lea     eax, ds:2[rax*2]
0x14000b2ef  mov     [rbp+190h+var_210], eax
0x14000b2f2  cmp     [rbx+18h], r13
0x14000b2f6  jbe     short loc_14000B2FB
0x14000b2f8  mov     rbx, [rbx]
0x14000b2fb  mov     [rbp+190h+var_208], rbx
0x14000b2ff  mov     [rsp+290h+var_230], r12
0x14000b304  lea     r9, [rdi+8]
0x14000b308  lea     rax, [rsp+290h+var_230]
0x14000b30d  mov     [rsp+290h+var_240], rax
0x14000b312  mov     [rsp+290h+var_248], rdi
0x14000b317  lea     rax, ?_OnQueryComplete@PrinterFinder@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; PrinterFinder::_OnQueryComplete(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x14000b31e  mov     [rsp+290h+var_250], rax
0x14000b323  lea     rax, [rsp+290h+var_228]
0x14000b328  mov     [rsp+290h+var_258], rax
0x14000b32d  mov     [rsp+290h+var_260], 1
0x14000b335  lea     rax, [rbp+190h+var_200]
0x14000b339  mov     [rsp+290h+var_268], rax
0x14000b33e  mov     dword ptr [rsp+290h+var_270], 8; int
0x14000b346  xor     edx, edx
0x14000b348  lea     ecx, [rdx+5]
0x14000b34b  lea     r8d, [rdx+4]
0x14000b34f  call    cs:__imp_DevCreateObjectQueryEx
0x14000b355  mov     rcx, [rbp+198h]; this
0x14000b35c  test    eax, eax
0x14000b35e  js      loc_14000B43A
0x14000b364  mov     edx, 0EA60h; dwMilliseconds
0x14000b369  mov     rcx, [rdi]; hHandle
0x14000b36c  call    cs:__imp_WaitForSingleObject
0x14000b372  mov     rcx, [rbp+198h]; this
0x14000b379  cmp     eax, 102h
0x14000b37e  jz      loc_14000B44F
0x14000b384  mov     rcx, [rbp+198h]; this
0x14000b38b  test    eax, eax
0x14000b38d  jnz     loc_14000B428
0x14000b393  mov     rsi, [rsp+290h+var_230]
0x14000b398  test    rsi, rsi
0x14000b39b  jz      short loc_14000B3B6
0x14000b39d  call    cs:__imp_GetLastError
0x14000b3a3  mov     ebx, eax
0x14000b3a5  mov     rcx, rsi
0x14000b3a8  call    cs:__imp_DevCloseObjectQuery
0x14000b3ae  mov     ecx, ebx; dwErrCode
0x14000b3b0  call    cs:__imp_SetLastError
0x14000b3b6  mov     [rsp+290h+var_230], r12
0x14000b3bb  cmp     [rdi+0B8h], r12
0x14000b3c2  jnz     short loc_14000B3FC
0x14000b3c4  lea     rdx, aCannotFindTheP; "  Cannot find the printer."
0x14000b3cb  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b3d2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b3d7  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b3de  mov     rcx, rax
0x14000b3e1  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b3e7  nop
0x14000b3e8  mov     rcx, [rsp+290h+var_230]
0x14000b3ed  test    rcx, rcx
0x14000b3f0  jz      short loc_14000B3F8
0x14000b3f2  call    cs:__imp_DevCloseObjectQuery
0x14000b3f8  xor     al, al
0x14000b3fa  jmp     short loc_14000B3FE
0x14000b3fc  mov     al, 1
0x14000b3fe  mov     rcx, [rbp+190h+var_40]
0x14000b405  xor     rcx, rsp; StackCookie
0x14000b408  call    __security_check_cookie
0x14000b40d  mov     rbx, [rsp+290h+arg_10]
0x14000b415  add     rsp, 260h
0x14000b41c  pop     r15
0x14000b41e  pop     r14
0x14000b420  pop     r13
0x14000b422  pop     r12
0x14000b424  pop     rdi
0x14000b425  pop     rsi
0x14000b426  pop     rbp
0x14000b427  retn
0x14000b428  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000b42f  mov     edx, 1E1h; void *
0x14000b434  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000b43a  mov     r9d, eax; char *
0x14000b43d  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000b444  mov     edx, 1DDh; void *
0x14000b449  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000b44f  mov     r9d, 800705B4h; char *
0x14000b455  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000b45c  mov     edx, 1E0h; void *
0x14000b461  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
