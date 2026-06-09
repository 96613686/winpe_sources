# ScriptDiagnostics::EdpServer::DevToolsManager::GetEdgeDevToolsVersion(ushort const * *,ushort const * *,ushort const * *)

- ea: `0x180022a6c`
- end: `0x180022d7e`
- name: `?GetEdgeDevToolsVersion@DevToolsManager@EdpServer@ScriptDiagnostics@@SAXPEAPEBG00@Z`
- size: `786`
- prototype: `void __fastcall(const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800229b8`

## callees

- `0x18001b178`
- `0x180020c1c`
- `0x180022a6c`
- `0x180022d84`
- `0x180025ebc`
- `0x18002b020`
- `0x18002b040`
- `0x18002b530`
- `0x18002c5b0`
- `0x1800737ec`
- `0x180073888`
- `0x180073af4`
- `0x180073b88`
- `0x18007401c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180022ad8`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180022ad8`
- `urlmon!UrlMkGetSessionOption` at `0x180022b0a`
- `urlmon!UrlMkGetSessionOption` at `0x180022b0a`

## string_xrefs

- `0x180022cf0`: `Cannot find browser user agent.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ScriptDiagnostics::EdpServer::DevToolsManager::GetEdgeDevToolsVersion(
        const unsigned __int16 **a1,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3)
{
  __int64 v4; // rdx
  __int64 *v5; // r12
  const unsigned __int16 *v6; // r15
  __int64 v7; // r8
  __int64 v8; // r8
  char *v9; // r9
  char *v10; // rdx
  __int64 v11; // rcx
  __int64 *v12; // rdi
  char *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rsi
  _QWORD *v16; // r14
  __int64 v17; // rax
  char *v18; // rbx
  __int64 trivial_2; // rax
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 *v24; // rax
  DWORD pdwBufferLengthOut; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 **v26; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 **v27; // [rsp+40h] [rbp-C0h]
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __m128i v31; // [rsp+78h] [rbp-88h]
  _BYTE pBuffer[272]; // [rsp+90h] [rbp-70h] BYREF

  v27 = a3;
  v26 = a2;
  std::string::string(&v30);
  v5 = &qword_1800B7060;
  v6 = (const unsigned __int16 *)&qword_1800B7080;
  if ( (_QWORD)xmmword_1800B7090 )
    goto LABEL_28;
  LOBYTE(v4) = 1;
  IEConfiguration_SetBool(536870927, v4);
  memset_0(pBuffer, 0, 0x105u);
  pdwBufferLengthOut = 0;
  UrlMkGetSessionOption(0x10000001u, pBuffer, 0x105u, &pdwBufferLengthOut, 0);
  v28 = 0;
  si128 = 0;
  v7 = -1;
  do
    ++v7;
  while ( pBuffer[v7] );
  std::string::_Construct<1,char const *>(&v28, pBuffer);
  std::string::_Tidy_deallocate(&v30);
  v30 = v28;
  v31 = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v28) = 0;
  std::string::_Tidy_deallocate(&v28);
  if ( v31.m128i_i64[1] > 0xFuLL )
  {
    v10 = (char *)v30;
    v9 = (char *)(v30 + v31.m128i_i64[0]);
  }
  else
  {
    v9 = (char *)&v30 + v31.m128i_i64[0];
    v10 = (char *)&v30;
  }
  v28 = 0;
  si128 = 0;
  if ( v10 == v9 )
    std::wstring::_Construct_empty(&v28);
  else
    std::wstring::_Construct_from_iter<char *,char *,unsigned __int64>(&v28, v10, v8, v9 - v10);
  std::wstring::operator=(&qword_1800B7060, &v28);
  std::wstring::_Tidy_deallocate(&v28);
  v12 = &qword_1800B7060;
  if ( *((_QWORD *)&xmmword_1800B7070 + 1) > 7u )
    v12 = (__int64 *)qword_1800B7060;
  if ( (unsigned __int64)xmmword_1800B7070 < 5 )
  {
    v15 = -1;
  }
  else
  {
    v13 = (char *)v12 + 2 * xmmword_1800B7070;
    v14 = _std_search_2(v12, v13, L"Edge/");
    if ( (char *)v14 == v13 )
    {
LABEL_27:
      std::wstring::_Assign<unsigned short>(&qword_1800B7080, L"Cannot find browser version.");
      std::wstring::_Assign<unsigned short>(&qword_1800B7060, L"Cannot find browser user agent.");
      goto LABEL_28;
    }
    v15 = (v14 - (__int64)v12) >> 1;
  }
  if ( v15 == -1 )
    goto LABEL_27;
  v16 = (_QWORD *)std::wstring::substr(v11, &v28, v15, -1);
  v17 = v16[2];
  if ( v16[3] > 7u )
    v16 = (_QWORD *)*v16;
  if ( !v17 || (v18 = (char *)v16 + 2 * v17, trivial_2 = _std_find_trivial_2(v16, v18, 32), (char *)trivial_2 == v18) )
    v20 = -1;
  else
    v20 = (trivial_2 - (__int64)v16) >> 1;
  std::wstring::_Tidy_deallocate(&v28);
  if ( v20 == -1 )
    v22 = -1;
  else
    v22 = v20 - v15;
  v23 = std::wstring::substr(v21, &v28, v15, v22);
  std::wstring::operator=(&qword_1800B7080, v23);
  std::wstring::_Tidy_deallocate(&v28);
LABEL_28:
  if ( *((_QWORD *)&xmmword_1800B7090 + 1) > 7u )
    v6 = (const unsigned __int16 *)qword_1800B7080;
  *a1 = v6;
  v24 = &qword_1800B7040;
  if ( (unsigned __int64)qword_1800B7058 > 7 )
    v24 = (__int64 *)qword_1800B7040;
  *v26 = (const unsigned __int16 *)v24;
  if ( *((_QWORD *)&xmmword_1800B7070 + 1) > 7u )
    v5 = (__int64 *)qword_1800B7060;
  *v27 = (const unsigned __int16 *)v5;
  std::string::_Tidy_deallocate(&v30);
}

```

## disassembly

```asm
0x180022a6c  mov     [rsp-8+arg_18], rbx
0x180022a71  push    rbp
0x180022a72  push    rsi
0x180022a73  push    rdi
0x180022a74  push    r12
0x180022a76  push    r13
0x180022a78  push    r14
0x180022a7a  push    r15
0x180022a7c  lea     rbp, [rsp-0B0h]
0x180022a84  sub     rsp, 1B0h
0x180022a8b  mov     rax, cs:__security_cookie
0x180022a92  xor     rax, rsp
0x180022a95  mov     [rbp+0E0h+var_40], rax
0x180022a9c  mov     [rsp+1E0h+var_1A0], r8
0x180022aa1  mov     [rsp+1E0h+var_1A8], rdx
0x180022aa6  mov     r13, rcx
0x180022aa9  lea     rcx, [rsp+1E0h+var_178]
0x180022aae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180022ab3  nop
0x180022ab4  lea     r12, qword_1800B7060
0x180022abb  lea     r15, qword_1800B7080
0x180022ac2  xor     edi, edi
0x180022ac4  cmp     qword ptr cs:xmmword_1800B7090, rdi
0x180022acb  jnz     loc_180022CFF
0x180022ad1  mov     dl, 1
0x180022ad3  mov     ecx, 2000000Fh
0x180022ad8  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x180022ade  mov     ebx, 105h
0x180022ae3  mov     r8d, ebx; Size
0x180022ae6  xor     edx, edx; Val
0x180022ae8  lea     rcx, [rbp+0E0h+pBuffer]; void *
0x180022aec  call    memset_0
0x180022af1  mov     [rsp+1E0h+pdwBufferLengthOut], edi
0x180022af5  mov     [rsp+1E0h+dwReserved], edi; dwReserved
0x180022af9  lea     r9, [rsp+1E0h+pdwBufferLengthOut]; pdwBufferLengthOut
0x180022afe  mov     r8d, ebx; dwBufferLength
0x180022b01  lea     rdx, [rbp+0E0h+pBuffer]; pBuffer
0x180022b05  mov     ecx, 10000001h; dwOption
0x180022b0a  call    cs:__imp_UrlMkGetSessionOption
0x180022b10  xorps   xmm0, xmm0
0x180022b13  movups  [rsp+1E0h+var_198], xmm0
0x180022b18  xorps   xmm1, xmm1
0x180022b1b  movdqu  [rsp+1E0h+var_188], xmm1
0x180022b21  lea     rax, [rbp+0E0h+pBuffer]
0x180022b25  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022b29  mov     r8, rbx
0x180022b2c  inc     r8
0x180022b2f  cmp     [rax+r8], dil
0x180022b33  jnz     short loc_180022B2C
0x180022b35  lea     rdx, [rbp+0E0h+pBuffer]
0x180022b39  lea     rcx, [rsp+1E0h+var_198]
0x180022b3e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180022b43  lea     rcx, [rsp+1E0h+var_178]
0x180022b48  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022b4d  movups  xmm0, [rsp+1E0h+var_198]
0x180022b52  movups  [rsp+1E0h+var_178], xmm0
0x180022b57  movups  xmm1, [rsp+1E0h+var_188]
0x180022b5c  movups  [rsp+1E0h+var_168], xmm1
0x180022b61  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180022b69  movdqu  [rsp+1E0h+var_188], xmm0
0x180022b6f  mov     byte ptr [rsp+1E0h+var_198], dil
0x180022b74  lea     rcx, [rsp+1E0h+var_198]
0x180022b79  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022b7e  mov     r9, qword ptr [rsp+1E0h+var_168]
0x180022b83  cmp     qword ptr [rbp+0E0h+var_168+8], 0Fh
0x180022b88  ja      short loc_180022B99
0x180022b8a  lea     rcx, [rsp+1E0h+var_178]
0x180022b8f  add     r9, rcx
0x180022b92  lea     rdx, [rsp+1E0h+var_178]
0x180022b97  jmp     short loc_180022BA1
0x180022b99  mov     rdx, qword ptr [rsp+1E0h+var_178]
0x180022b9e  add     r9, rdx
0x180022ba1  xorps   xmm0, xmm0
0x180022ba4  movups  [rsp+1E0h+var_198], xmm0
0x180022ba9  xorps   xmm1, xmm1
0x180022bac  movdqu  [rsp+1E0h+var_188], xmm1
0x180022bb2  lea     rcx, [rsp+1E0h+var_198]
0x180022bb7  cmp     rdx, r9
0x180022bba  jnz     short loc_180022BC3
0x180022bbc  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180022bc1  jmp     short loc_180022BCB
0x180022bc3  sub     r9, rdx
0x180022bc6  call    ??$_Construct_from_iter@PEADPEAD_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXPEADQEAD_K@Z; std::wstring::_Construct_from_iter<char *,char *,unsigned __int64>(char *,char * const,unsigned __int64)
0x180022bcb  lea     rdx, [rsp+1E0h+var_198]
0x180022bd0  mov     rcx, r12
0x180022bd3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022bd8  lea     rcx, [rsp+1E0h+var_198]
0x180022bdd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022be2  mov     rax, qword ptr cs:xmmword_1800B7070
0x180022be9  mov     rdi, r12
0x180022bec  cmp     qword ptr cs:xmmword_1800B7070+8, 7
0x180022bf4  cmova   rdi, cs:qword_1800B7060
0x180022bfc  mov     r9d, 5
0x180022c02  cmp     rax, r9
0x180022c05  jb      short loc_180022C35
0x180022c07  lea     rbx, [rdi+rax*2]
0x180022c0b  lea     r8, aEdge; "Edge/"
0x180022c12  mov     rdx, rbx
0x180022c15  mov     rcx, rdi
0x180022c18  call    __std_search_2
0x180022c1d  mov     rsi, rax
0x180022c20  cmp     rax, rbx
0x180022c23  jz      loc_180022CD5
0x180022c29  sub     rsi, rdi
0x180022c2c  sar     rsi, 1
0x180022c2f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022c33  jmp     short loc_180022C38
0x180022c35  mov     rsi, rbx
0x180022c38  cmp     rsi, rbx
0x180022c3b  jz      loc_180022CD5
0x180022c41  mov     r9, rbx
0x180022c44  mov     r8, rsi
0x180022c47  lea     rdx, [rsp+1E0h+var_198]
0x180022c4c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180022c51  mov     r14, rax
0x180022c54  mov     rax, [rax+10h]
0x180022c58  cmp     qword ptr [r14+18h], 7
0x180022c5d  jbe     short loc_180022C62
0x180022c5f  mov     r14, [r14]
0x180022c62  test    rax, rax
0x180022c65  jz      short loc_180022C94
0x180022c67  lea     rbx, [r14+rax*2]
0x180022c6b  mov     r8d, 20h ; ' '
0x180022c71  mov     rdx, rbx
0x180022c74  mov     rcx, r14
0x180022c77  call    __std_find_trivial_2
0x180022c7c  mov     rdi, rax
0x180022c7f  cmp     rax, rbx
0x180022c82  jz      short loc_180022C90
0x180022c84  sub     rdi, r14
0x180022c87  sar     rdi, 1
0x180022c8a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022c8e  jmp     short loc_180022C97
0x180022c90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022c94  mov     rdi, rbx
0x180022c97  lea     rcx, [rsp+1E0h+var_198]
0x180022c9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022ca1  mov     r8, rsi
0x180022ca4  lea     rdx, [rsp+1E0h+var_198]
0x180022ca9  cmp     rdi, rbx
0x180022cac  jz      short loc_180022CB6
0x180022cae  sub     rdi, rsi
0x180022cb1  mov     r9, rdi
0x180022cb4  jmp     short loc_180022CB9
0x180022cb6  mov     r9, rbx
0x180022cb9  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180022cbe  mov     rdx, rax
0x180022cc1  mov     rcx, r15
0x180022cc4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022cc9  lea     rcx, [rsp+1E0h+var_198]
0x180022cce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022cd3  jmp     short loc_180022CFF
0x180022cd5  mov     r8d, 1Ch
0x180022cdb  lea     rdx, aCannotFindBrow; "Cannot find browser version."
0x180022ce2  mov     rcx, r15
0x180022ce5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022cea  mov     r8d, 1Fh
0x180022cf0  lea     rdx, aCannotFindBrow_0; "Cannot find browser user agent."
0x180022cf7  mov     rcx, r12
0x180022cfa  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022cff  cmp     qword ptr cs:xmmword_1800B7090+8, 7
0x180022d07  cmova   r15, cs:qword_1800B7080
0x180022d0f  mov     [r13+0], r15
0x180022d13  lea     rax, qword_1800B7040
0x180022d1a  cmp     cs:qword_1800B7058, 7
0x180022d22  cmova   rax, cs:qword_1800B7040
0x180022d2a  mov     rcx, [rsp+1E0h+var_1A8]
0x180022d2f  mov     [rcx], rax
0x180022d32  cmp     qword ptr cs:xmmword_1800B7070+8, 7
0x180022d3a  cmova   r12, cs:qword_1800B7060
0x180022d42  mov     rax, [rsp+1E0h+var_1A0]
0x180022d47  mov     [rax], r12
0x180022d4a  lea     rcx, [rsp+1E0h+var_178]
0x180022d4f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022d54  mov     rcx, [rbp+0E0h+var_40]
0x180022d5b  xor     rcx, rsp; StackCookie
0x180022d5e  call    __security_check_cookie
0x180022d63  mov     rbx, [rsp+1E0h+arg_18]
0x180022d6b  add     rsp, 1B0h
0x180022d72  pop     r15
0x180022d74  pop     r14
0x180022d76  pop     r13
0x180022d78  pop     r12
0x180022d7a  pop     rdi
0x180022d7b  pop     rsi
0x180022d7c  pop     rbp
0x180022d7d  retn
```
