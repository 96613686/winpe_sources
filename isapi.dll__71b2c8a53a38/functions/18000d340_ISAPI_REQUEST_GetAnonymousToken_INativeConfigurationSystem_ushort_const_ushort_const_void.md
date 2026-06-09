# ISAPI_REQUEST::GetAnonymousToken(INativeConfigurationSystem *,ushort const *,ushort const *,void * *)

- ea: `0x18000d340`
- end: `0x18000d5af`
- name: `?GetAnonymousToken@ISAPI_REQUEST@@QEAAJPEAVINativeConfigurationSystem@@PEBG1PEAPEAX@Z`
- size: `623`
- prototype: `__int64 __usercall@<rax>(ISAPI_REQUEST *__hidden this@<rcx>, struct INativeConfigurationSystem *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000eff0`

## callees

- `0x18000c898`
- `0x18000d340`
- `0x180011d4c`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d586`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d586`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d3d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d3d3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d42e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d457`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d42e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d457`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d39e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d39e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000d415`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000d43c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000d415`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000d43c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d3eb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d403`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d3eb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d403`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000d423`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000d423`

## string_xrefs

- `0x18000d47a`: `system.webServer/security/authentication/anonymousAuthentication`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetAnonymousToken(
        ISAPI_REQUEST *this,
        struct INativeConfigurationSystem *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void **a5)
{
  int Token; // ebx
  unsigned int CCH; // eax
  unsigned __int16 *Str; // rbx
  __int64 (__fastcall *v12)(struct INativeConfigurationSystem *, const wchar_t *, unsigned __int16 *, __int64 *, _QWORD, _QWORD); // rbx
  unsigned __int16 *v13; // rax
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v18; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v19[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[256]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v19, v20, 0x100u);
  v15 = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  Token = STRU::Copy((STRU *)v19, L"MACHINE/WEBROOT/APPHOST/");
  if ( Token >= 0 )
  {
    Token = STRU::Append((STRU *)v19, a3);
    if ( Token >= 0 )
    {
      Token = STRU::Append((STRU *)v19, a4);
      if ( Token >= 0 )
      {
        while ( 1 )
        {
          Str = STRU::QueryStr((STRU *)v19);
          if ( Str[STRU::QueryCCH((STRU *)v19) - 1] != 47 )
            break;
          CCH = STRU::QueryCCH((STRU *)v19);
          STRU::SetLen((STRU *)v19, CCH - 1);
        }
        v12 = *(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, unsigned __int16 *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL);
        v13 = STRU::QueryStr((STRU *)v19);
        Token = v12(a2, L"system.webServer/security/authentication/anonymousAuthentication", v13, &v15, 0, 0);
        if ( Token >= 0 )
        {
          Token = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                    v15,
                    L"userName",
                    &v18,
                    0,
                    0);
          if ( Token < 0
            || (Token = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                          v15,
                          L"password",
                          &v17,
                          0,
                          0),
                Token < 0)
            || (Token = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
                          v15,
                          L"logonMethod",
                          &v16,
                          0,
                          0),
                Token < 0)
            || (Token = TranslateLogonMethod(&v16), Token < 0) )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          else
          {
            Token = ISAPI_REQUEST::CreateToken(this, v18, v17, (unsigned __int16 *)&dword_18001C6FC, v16, a5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v19);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000d340  push    rbp
0x18000d342  push    rbx
0x18000d343  push    rsi
0x18000d344  push    rdi
0x18000d345  push    r12
0x18000d347  push    r14
0x18000d349  push    r15
0x18000d34b  lea     rbp, [rsp-1B0h]
0x18000d353  sub     rsp, 2B0h
0x18000d35a  mov     rax, cs:__security_cookie
0x18000d361  xor     rax, rsp
0x18000d364  mov     [rbp+1E0h+var_40], rax
0x18000d36b  mov     r12, [rbp+1E0h+arg_20]
0x18000d372  mov     rdi, r8
0x18000d375  mov     r14, rdx
0x18000d378  mov     r15, rcx
0x18000d37b  xor     edx, edx; Val
0x18000d37d  lea     rcx, [rbp+1E0h+var_240]; void *
0x18000d381  mov     r8d, 200h; Size
0x18000d387  mov     rsi, r9
0x18000d38a  call    memset_0
0x18000d38f  mov     r8d, 100h
0x18000d395  lea     rdx, [rbp+1E0h+var_240]
0x18000d399  lea     rcx, [rsp+2E0h+var_280]
0x18000d39e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d3a4  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x18000d3ab  mov     [rsp+2E0h+var_2A0], 0
0x18000d3b4  lea     rcx, [rsp+2E0h+var_280]
0x18000d3b9  mov     [rsp+2E0h+var_288], 0
0x18000d3c2  mov     [rsp+2E0h+var_290], 0
0x18000d3cb  mov     [rsp+2E0h+var_298], 0
0x18000d3d3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d3d9  mov     ebx, eax
0x18000d3db  test    eax, eax
0x18000d3dd  js      loc_18000D581
0x18000d3e3  mov     rdx, rdi
0x18000d3e6  lea     rcx, [rsp+2E0h+var_280]
0x18000d3eb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d3f1  mov     ebx, eax
0x18000d3f3  test    eax, eax
0x18000d3f5  js      loc_18000D581
0x18000d3fb  mov     rdx, rsi
0x18000d3fe  lea     rcx, [rsp+2E0h+var_280]
0x18000d403  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d409  mov     ebx, eax
0x18000d40b  test    eax, eax
0x18000d40d  js      loc_18000D581
0x18000d413  jmp     short loc_18000D429
0x18000d415  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000d41b  lea     rcx, [rsp+2E0h+var_280]
0x18000d420  lea     edx, [rax-1]
0x18000d423  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18000d429  lea     rcx, [rsp+2E0h+var_280]
0x18000d42e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d434  lea     rcx, [rsp+2E0h+var_280]
0x18000d439  mov     rbx, rax
0x18000d43c  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000d442  dec     eax
0x18000d444  lea     rcx, [rsp+2E0h+var_280]
0x18000d449  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x18000d44e  jz      short loc_18000D415
0x18000d450  mov     rax, [r14]
0x18000d453  mov     rbx, [rax+18h]
0x18000d457  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d45d  mov     [rsp+2E0h+var_2B8], 0
0x18000d466  lea     r9, [rsp+2E0h+var_2A0]
0x18000d46b  mov     r8, rax
0x18000d46e  mov     qword ptr [rsp+2E0h+var_2C0], 0
0x18000d477  mov     rax, rbx
0x18000d47a  lea     rdx, aSystemWebserve_3; "system.webServer/security/authenticatio"...
0x18000d481  mov     rcx, r14
0x18000d484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d489  mov     ebx, eax
0x18000d48b  test    eax, eax
0x18000d48d  js      loc_18000D581
0x18000d493  mov     rcx, [rsp+2E0h+var_2A0]
0x18000d498  lea     r8, [rsp+2E0h+var_288]
0x18000d49d  xor     r9d, r9d
0x18000d4a0  mov     qword ptr [rsp+2E0h+var_2C0], 0
0x18000d4a9  lea     rdx, aUsername; "userName"
0x18000d4b0  mov     rax, [rcx]
0x18000d4b3  mov     rax, [rax+40h]
0x18000d4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4bc  mov     ebx, eax
0x18000d4be  test    eax, eax
0x18000d4c0  jns     short loc_18000D4D6
0x18000d4c2  mov     rdx, [rsp+2E0h+var_2A0]
0x18000d4c7  mov     rcx, [rdx]
0x18000d4ca  mov     rax, [rcx+10h]
0x18000d4ce  mov     rcx, rdx
0x18000d4d1  jmp     loc_18000D57C
0x18000d4d6  mov     rcx, [rsp+2E0h+var_2A0]
0x18000d4db  lea     r8, [rsp+2E0h+var_290]
0x18000d4e0  xor     r9d, r9d
0x18000d4e3  mov     qword ptr [rsp+2E0h+var_2C0], 0
0x18000d4ec  lea     rdx, aPassword; "password"
0x18000d4f3  mov     rax, [rcx]
0x18000d4f6  mov     rax, [rax+40h]
0x18000d4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ff  mov     ebx, eax
0x18000d501  test    eax, eax
0x18000d503  js      short loc_18000D4C2
0x18000d505  mov     rcx, [rsp+2E0h+var_2A0]
0x18000d50a  lea     r8, [rsp+2E0h+var_298]
0x18000d50f  xor     r9d, r9d
0x18000d512  mov     qword ptr [rsp+2E0h+var_2C0], 0
0x18000d51b  lea     rdx, aLogonmethod; "logonMethod"
0x18000d522  mov     rax, [rcx]
0x18000d525  mov     rax, [rax+30h]
0x18000d529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d52e  mov     ebx, eax
0x18000d530  test    eax, eax
0x18000d532  js      short loc_18000D4C2
0x18000d534  lea     rcx, [rsp+2E0h+var_298]; unsigned int *
0x18000d539  call    ?TranslateLogonMethod@@YAJPEAK@Z; TranslateLogonMethod(ulong *)
0x18000d53e  mov     ebx, eax
0x18000d540  test    eax, eax
0x18000d542  js      loc_18000D4C2
0x18000d548  mov     eax, [rsp+2E0h+var_298]
0x18000d54c  lea     r9, dword_18001C6FC; unsigned __int16 *
0x18000d553  mov     r8, [rsp+2E0h+var_290]; unsigned __int16 *
0x18000d558  mov     rcx, r15; this
0x18000d55b  mov     rdx, [rsp+2E0h+var_288]; unsigned __int16 *
0x18000d560  mov     [rsp+2E0h+var_2B8], r12; void **
0x18000d565  mov     [rsp+2E0h+var_2C0], eax; unsigned int
0x18000d569  call    ?CreateToken@ISAPI_REQUEST@@QEAAJPEBG00KPEAPEAX@Z; ISAPI_REQUEST::CreateToken(ushort const *,ushort const *,ushort const *,ulong,void * *)
0x18000d56e  mov     rcx, [rsp+2E0h+var_2A0]
0x18000d573  mov     ebx, eax
0x18000d575  mov     rdx, [rcx]
0x18000d578  mov     rax, [rdx+10h]
0x18000d57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d581  lea     rcx, [rsp+2E0h+var_280]
0x18000d586  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d58c  mov     eax, ebx
0x18000d58e  mov     rcx, [rbp+1E0h+var_40]
0x18000d595  xor     rcx, rsp; StackCookie
0x18000d598  call    __security_check_cookie
0x18000d59d  add     rsp, 2B0h
0x18000d5a4  pop     r15
0x18000d5a6  pop     r14
0x18000d5a8  pop     r12
0x18000d5aa  pop     rdi
0x18000d5ab  pop     rsi
0x18000d5ac  pop     rbx
0x18000d5ad  pop     rbp
0x18000d5ae  retn
```
