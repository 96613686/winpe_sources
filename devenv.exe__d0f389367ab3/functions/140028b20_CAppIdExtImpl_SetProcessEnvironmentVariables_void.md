# CAppIdExtImpl::SetProcessEnvironmentVariables(void)

- ea: `0x140028b20`
- end: `0x140028e63`
- name: `?SetProcessEnvironmentVariables@CAppIdExtImpl@@KAXXZ`
- size: `835`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002190`
- `0x140002650`
- `0x14001f6b4`
- `0x140028b20`
- `0x140028e70`
- `0x1400638f8`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x140028b64`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b78`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b87`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b96`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028ba5`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028ce7`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028e01`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028e2b`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b64`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b78`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b87`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028b96`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028ba5`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028ce7`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028e01`
- `KERNEL32!SetEnvironmentVariableW` at `0x140028e2b`
- `KERNEL32!GetModuleFileNameW` at `0x140028d97`
- `KERNEL32!GetModuleFileNameW` at `0x140028d97`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140028d26`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140028d7a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140028d26`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140028d7a`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x140028df0`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x140028e17`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x140028df0`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x140028e17`
- `ole32!CoCreateGuid` at `0x140028baf`
- `ole32!CoCreateGuid` at `0x140028baf`
- `ole32!StringFromGUID2` at `0x140028bc9`
- `ole32!StringFromGUID2` at `0x140028bc9`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x140028dd9`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x140028dd9`

## string_xrefs

- `0x140028b8f`: `ServiceHubLocationServicePipeName`
- `0x140028b9e`: `ServiceHubLogSessionKey`
- `0x140028ce0`: `ServiceHubHostServiceBrokerPipeName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CAppIdExtImpl::SetProcessEnvironmentVariables(void)
{
  unsigned __int64 v0; // rdi
  unsigned __int64 v1; // rax
  unsigned __int64 v2; // rax
  __int64 v3; // rsi
  unsigned __int64 v4; // rax
  void **v5; // rbx
  void **v6; // rax
  const WCHAR *p_lpValue_8; // rdx
  const struct std::nothrow_t *v8; // rdx
  void *v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rcx
  void *v12[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+68h] [rbp-A0h]
  __int128 lpValue_8; // [rsp+78h] [rbp-90h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h]
  GUID pguid; // [rsp+A0h] [rbp-68h] BYREF
  OLECHAR sz; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t Src[63]; // [rsp+BAh] [rbp-4Eh] BYREF
  wchar_t Drive[264]; // [rsp+138h] [rbp+30h] BYREF
  wchar_t Destination[264]; // [rsp+348h] [rbp+240h] BYREF
  WCHAR Filename[264]; // [rsp+558h] [rbp+450h] BYREF
  wchar_t Dir[264]; // [rsp+768h] [rbp+660h] BYREF
  wchar_t Source[264]; // [rsp+978h] [rbp+870h] BYREF

  SetEnvironmentVariableW(L"VSSKUEDITION", lpValue);
  SetEnvironmentVariableW(L"VSROOTSUFFIX", CAppIdExtImpl::ms_wszRegistrySuffix);
  SetEnvironmentVariableW(L"ELECTRON_RUN_AS_NODE", 0);
  SetEnvironmentVariableW(L"ServiceHubLocationServicePipeName", 0);
  SetEnvironmentVariableW(L"ServiceHubLogSessionKey", 0);
  if ( CoCreateGuid(&pguid) >= 0 )
  {
    StringFromGUID2(&pguid, &sz, 64);
    v0 = -1;
    v1 = -1;
    do
      ++v1;
    while ( Src[v1 - 1] );
    if ( v1 > 2 )
    {
      v2 = 2 * v1 - 2;
      if ( v2 >= 0x80 )
        _report_rangecheckfailure(&sz);
      *(wchar_t *)((char *)&Src[-1] + v2) = 0;
      *(_OWORD *)v12 = 0;
      v13 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v12, L"\\\\.\\pipe\\", 9);
      do
        ++v0;
      while ( Src[v0] );
      v3 = v13;
      v4 = *((_QWORD *)&v13 + 1) - v13;
      _mm_lfence();
      if ( v0 > v4 )
      {
        v6 = (void **)std::wstring::_Reallocate_grow_by<_lambda_7030d12a21dba11210293044e97fe9c7_,unsigned short const *,unsigned __int64>(
                        v12,
                        v0);
      }
      else
      {
        *(_QWORD *)&v13 = v0 + v13;
        v5 = v12;
        if ( *((_QWORD *)&v13 + 1) > 7u )
          v5 = (void **)v12[0];
        memmove_0((char *)v5 + 2 * v3, Src, 2 * v0);
        *((_WORD *)v5 + v3 + v0) = 0;
        v6 = v12;
      }
      lpValue_8 = 0;
      si128 = 0;
      lpValue_8 = *(_OWORD *)v6;
      si128 = *((__m128i *)v6 + 1);
      v6[2] = 0;
      v6[3] = (void *)7;
      *(_WORD *)v6 = 0;
      p_lpValue_8 = (const WCHAR *)&lpValue_8;
      if ( si128.m128i_i64[1] > 7uLL )
        p_lpValue_8 = (const WCHAR *)lpValue_8;
      SetEnvironmentVariableW(L"ServiceHubHostServiceBrokerPipeName", p_lpValue_8);
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v8 = (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 2);
        v9 = (void *)lpValue_8;
        if ( (unsigned __int64)v8 >= 0x1000 )
        {
          v8 = (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 41);
          v9 = *(void **)(lpValue_8 - 8);
          if ( (unsigned __int64)(lpValue_8 - (_QWORD)v9 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v9, v8);
      }
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(lpValue_8) = 0;
      if ( *((_QWORD *)&v13 + 1) > 7u )
      {
        v10 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v13 + 1) + 2);
        v11 = v12[0];
        if ( (unsigned __int64)v10 >= 0x1000 )
        {
          v10 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v13 + 1) + 41);
          v11 = (void *)*((_QWORD *)v12[0] - 1);
          if ( (unsigned __int64)((char *)v12[0] - (char *)v11 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v11, v10);
      }
    }
  }
  GetModuleFileNameW(0, Filename, 0x105u);
  if ( !_wsplitpath_s(Filename, Drive, 0x105u, Dir, 0x105u, Destination, 0x105u, Source, 0x105u) )
  {
    wcscat_s(Drive, 0x105u, Dir);
    SetEnvironmentVariableW(L"VSAPPIDDIR", Drive);
    wcscat_s(Destination, 0x105u, Source);
    SetEnvironmentVariableW(L"VSAPPIDNAME", Destination);
  }
}

```

## disassembly

```asm
0x140028b20  mov     rax, rsp
0x140028b23  mov     [rax+8], rbx
0x140028b27  mov     [rax+10h], rsi
0x140028b2b  mov     [rax+18h], rdi
0x140028b2f  mov     [rax+20h], r14
0x140028b33  push    rbp
0x140028b34  lea     rbp, [rax-0A98h]
0x140028b3b  sub     rsp, 0B90h
0x140028b42  mov     rax, cs:__security_cookie
0x140028b49  xor     rax, rsp
0x140028b4c  mov     [rbp+0A90h+var_10], rax
0x140028b53  xor     r14d, r14d
0x140028b56  mov     rdx, cs:lpValue; lpValue
0x140028b5d  lea     rcx, aVsskuedition; "VSSKUEDITION"
0x140028b64  call    cs:__imp_SetEnvironmentVariableW
0x140028b6a  mov     rdx, cs:?ms_wszRegistrySuffix@CAppIdExtImpl@@1PEAGEA; lpValue
0x140028b71  lea     rcx, aVsrootsuffix; "VSROOTSUFFIX"
0x140028b78  call    cs:__imp_SetEnvironmentVariableW
0x140028b7e  xor     edx, edx; lpValue
0x140028b80  lea     rcx, aElectronRunAsN; "ELECTRON_RUN_AS_NODE"
0x140028b87  call    cs:__imp_SetEnvironmentVariableW
0x140028b8d  xor     edx, edx; lpValue
0x140028b8f  lea     rcx, aServicehubloca; "ServiceHubLocationServicePipeName"
0x140028b96  call    cs:__imp_SetEnvironmentVariableW
0x140028b9c  xor     edx, edx; lpValue
0x140028b9e  lea     rcx, aServicehublogs; "ServiceHubLogSessionKey"
0x140028ba5  call    cs:__imp_SetEnvironmentVariableW
0x140028bab  lea     rcx, [rbp+0A90h+pguid]; pguid
0x140028baf  call    cs:__imp_CoCreateGuid
0x140028bb5  test    eax, eax
0x140028bb7  js      loc_140028D86
0x140028bbd  lea     r8d, [r14+40h]; cchMax
0x140028bc1  lea     rdx, [rbp+0A90h+sz]; lpsz
0x140028bc5  lea     rcx, [rbp+0A90h+pguid]; rguid
0x140028bc9  call    cs:__imp_StringFromGUID2
0x140028bcf  lea     rcx, [rbp+0A90h+sz]
0x140028bd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140028bd7  mov     rax, rdi
0x140028bda  inc     rax
0x140028bdd  cmp     [rcx+rax*2], r14w
0x140028be2  jnz     short loc_140028BDA
0x140028be4  cmp     rax, 2
0x140028be8  jbe     loc_140028D86
0x140028bee  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140028bf6  cmp     rax, 80h
0x140028bfc  jnb     loc_140028E5D
0x140028c02  mov     [rbp+rax+0A90h+sz], r14w
0x140028c08  xorps   xmm0, xmm0
0x140028c0b  movups  xmmword ptr [rsp+0B90h+var_B48+8], xmm0
0x140028c10  xorps   xmm1, xmm1
0x140028c13  movdqu  [rsp+0B90h+var_B38+8], xmm1
0x140028c19  mov     r8d, 9
0x140028c1f  lea     rdx, aPipe; "\\\\.\\pipe\\"
0x140028c26  lea     rcx, [rsp+0B90h+var_B48+8]
0x140028c2b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140028c30  lea     rax, [rbp+0A90h+Src]
0x140028c34  inc     rdi
0x140028c37  cmp     [rax+rdi*2], r14w
0x140028c3c  jnz     short loc_140028C34
0x140028c3e  mov     rsi, qword ptr [rsp+0B90h+var_B38+8]
0x140028c43  mov     rax, qword ptr [rsp+0B90h+lpValue]
0x140028c48  sub     rax, rsi
0x140028c4b  lfence
0x140028c4e  cmp     rdi, rax
0x140028c51  ja      short loc_140028C8A
0x140028c53  add     qword ptr [rsp+0B90h+var_B38+8], rdi
0x140028c58  lea     rbx, [rsp+0B90h+var_B48+8]
0x140028c5d  cmp     qword ptr [rsp+0B90h+lpValue], 7
0x140028c63  cmova   rbx, [rsp+0B90h+var_B48+8]
0x140028c69  lea     rcx, [rbx+rsi*2]; void *
0x140028c6d  lea     r8, [rdi+rdi]; Size
0x140028c71  lea     rdx, [rbp+0A90h+Src]; Src
0x140028c75  call    memmove_0
0x140028c7a  lea     rax, [rsi+rdi]
0x140028c7e  mov     [rbx+rax*2], r14w
0x140028c83  lea     rax, [rsp+0B90h+var_B48+8]
0x140028c88  jmp     short loc_140028CA0
0x140028c8a  mov     [rsp+0B90h+DirCount], rdi; __int64
0x140028c8f  lea     r9, [rbp+0A90h+Src]
0x140028c93  mov     rdx, rdi
0x140028c96  lea     rcx, [rsp+0B90h+var_B48+8]; Src
0x140028c9b  call    ??$_Reallocate_grow_by@V_lambda_7030d12a21dba11210293044e97fe9c7_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7030d12a21dba11210293044e97fe9c7_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_7030d12a21dba11210293044e97fe9c7_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_7030d12a21dba11210293044e97fe9c7_,ushort const *,unsigned __int64)
0x140028ca0  xorps   xmm0, xmm0
0x140028ca3  movups  xmmword ptr [rsp+0B90h+lpValue+8], xmm0
0x140028ca8  xorps   xmm1, xmm1
0x140028cab  movdqu  [rbp+0A90h+var_B10], xmm1
0x140028cb0  movups  xmm0, xmmword ptr [rax]
0x140028cb3  movups  xmmword ptr [rsp+0B90h+lpValue+8], xmm0
0x140028cb8  movups  xmm1, xmmword ptr [rax+10h]
0x140028cbc  movups  [rbp+0A90h+var_B10], xmm1
0x140028cc0  mov     [rax+10h], r14
0x140028cc4  mov     qword ptr [rax+18h], 7
0x140028ccc  mov     [rax], r14w
0x140028cd0  lea     rdx, [rsp+0B90h+lpValue+8]
0x140028cd5  cmp     qword ptr [rbp+0A90h+var_B10+8], 7
0x140028cda  cmova   rdx, qword ptr [rsp+0B90h+lpValue+8]; lpValue
0x140028ce0  lea     rcx, aServicehubhost; "ServiceHubHostServiceBrokerPipeName"
0x140028ce7  call    cs:__imp_SetEnvironmentVariableW
0x140028ced  mov     ebx, 1000h
0x140028cf2  mov     rdx, qword ptr [rbp+0A90h+var_B10+8]
0x140028cf6  cmp     rdx, 7
0x140028cfa  jbe     short loc_140028D32
0x140028cfc  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x140028d04  mov     rcx, qword ptr [rsp+0B90h+lpValue+8]; void *
0x140028d09  mov     rax, rcx
0x140028d0c  cmp     rdx, rbx
0x140028d0f  jb      short loc_140028D2D
0x140028d11  add     rdx, 27h ; '''
0x140028d15  mov     rcx, [rcx-8]
0x140028d19  sub     rax, rcx
0x140028d1c  add     rax, 0FFFFFFFFFFFFFFF8h
0x140028d20  cmp     rax, 1Fh
0x140028d24  jbe     short loc_140028D2D
0x140028d26  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x140028d2d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140028d32  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140028d3a  movdqu  [rbp+0A90h+var_B10], xmm0
0x140028d3f  mov     word ptr [rsp+0B90h+lpValue+8], r14w
0x140028d45  mov     rdx, qword ptr [rsp+0B90h+lpValue]
0x140028d4a  cmp     rdx, 7
0x140028d4e  jbe     short loc_140028D86
0x140028d50  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x140028d58  mov     rcx, [rsp+0B90h+var_B48+8]; void *
0x140028d5d  mov     rax, rcx
0x140028d60  cmp     rdx, rbx
0x140028d63  jb      short loc_140028D81
0x140028d65  add     rdx, 27h ; '''
0x140028d69  mov     rcx, [rcx-8]
0x140028d6d  sub     rax, rcx
0x140028d70  add     rax, 0FFFFFFFFFFFFFFF8h
0x140028d74  cmp     rax, 1Fh
0x140028d78  jbe     short loc_140028D81
0x140028d7a  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x140028d81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140028d86  mov     ebx, 105h
0x140028d8b  mov     r8d, ebx; nSize
0x140028d8e  lea     rdx, [rbp+0A90h+Filename]; lpFilename
0x140028d95  xor     ecx, ecx; hModule
0x140028d97  call    cs:__imp_GetModuleFileNameW
0x140028d9d  mov     [rsp+0B90h+ExtCount], rbx; ExtCount
0x140028da2  lea     rax, [rbp+0A90h+Source]
0x140028da9  mov     [rsp+0B90h+Ext], rax; Ext
0x140028dae  mov     [rsp+0B90h+FilenameCount], rbx; FilenameCount
0x140028db3  lea     rax, [rbp+0A90h+Destination]
0x140028dba  mov     [rsp+0B90h+var_B68], rax; Filename
0x140028dbf  mov     [rsp+0B90h+DirCount], rbx; DirCount
0x140028dc4  lea     r9, [rbp+0A90h+Dir]; Dir
0x140028dcb  mov     r8d, ebx; DriveCount
0x140028dce  lea     rdx, [rbp+0A90h+Drive]; Drive
0x140028dd2  lea     rcx, [rbp+0A90h+Filename]; FullPath
0x140028dd9  call    cs:__imp__wsplitpath_s
0x140028ddf  test    eax, eax
0x140028de1  jnz     short loc_140028E31
0x140028de3  lea     r8, [rbp+0A90h+Dir]; Source
0x140028dea  mov     edx, ebx; SizeInWords
0x140028dec  lea     rcx, [rbp+0A90h+Drive]; Destination
0x140028df0  call    cs:__imp_wcscat_s
0x140028df6  lea     rdx, [rbp+0A90h+Drive]; lpValue
0x140028dfa  lea     rcx, aVsappiddir; "VSAPPIDDIR"
0x140028e01  call    cs:__imp_SetEnvironmentVariableW
0x140028e07  lea     r8, [rbp+0A90h+Source]; Source
0x140028e0e  mov     edx, ebx; SizeInWords
0x140028e10  lea     rcx, [rbp+0A90h+Destination]; Destination
0x140028e17  call    cs:__imp_wcscat_s
0x140028e1d  lea     rdx, [rbp+0A90h+Destination]; lpValue
0x140028e24  lea     rcx, aVsappidname; "VSAPPIDNAME"
0x140028e2b  call    cs:__imp_SetEnvironmentVariableW
0x140028e31  mov     rcx, [rbp+0A90h+var_10]
0x140028e38  xor     rcx, rsp; StackCookie
0x140028e3b  call    __security_check_cookie
0x140028e40  lea     r11, [rsp+0B90h+var_s0]
0x140028e48  mov     rbx, [r11+10h]
0x140028e4c  mov     rsi, [r11+18h]
0x140028e50  mov     rdi, [r11+20h]
0x140028e54  mov     r14, [r11+28h]
0x140028e58  mov     rsp, r11
0x140028e5b  pop     rbp
0x140028e5c  retn
0x140028e5d  call    __report_rangecheckfailure
```
