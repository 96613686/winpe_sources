# ProvOperations::GetOOBEProvisioningLogsPath(ushort * *)

- ea: `0x180012e94`
- end: `0x18001302c`
- name: `?GetOOBEProvisioningLogsPath@ProvOperations@@SAJPEAPEAG@Z`
- size: `408`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ebbc`
- `0x180010b40`
- `0x180011b88`

## callees

- `0x180005bb8`
- `0x180007674`
- `0x180012e94`
- `0x18002072c`
- `0x180020e98`
- `0x180020fe0`
- `0x18002490c`
- `0x180033ed0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012f9a`
- `msvcrt!memcpy_s` at `0x180012f9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012fcf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012fcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f7f`

## string_xrefs

- `0x180013007`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180013019`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvOperations::GetOOBEProvisioningLogsPath(unsigned __int16 **a1)
{
  unsigned int v2; // r14d
  void **ProvisioningDiagnosticsFolderPath; // rax
  const char *v5; // r9
  void **v6; // rbx
  __int64 v7; // rcx
  char *v8; // rax
  rsize_t v9; // r15
  unsigned __int16 *v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned __int16 *v13; // rdi
  wil *v14; // rcx
  void *Source[3]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = 0;
  if ( a1 )
  {
    try
    {
      *a1 = 0;
      ProvisioningDiagnosticsFolderPath = (void **)ProvisioningPaths::GetProvisioningDiagnosticsFolderPath(a1);
      v16 = 7;
      Source[2] = 0;
      LOWORD(Source[0]) = 0;
      std::wstring::assign(Source, ProvisioningDiagnosticsFolderPath, 0, 0xFFFFFFFFFFFFFFFFuLL);
      std::wstring::append(Source, L"DeviceProvisioning-OOBE-Diagnostics-GetLogs.cab");
      v6 = Source;
      if ( v16 >= 8 )
        v6 = (void **)Source[0];
      if ( !v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v5);
      v7 = 0x7FFFFFFF;
      v8 = (char *)v6;
      do
      {
        if ( !*(_WORD *)v8 )
          break;
        v8 += 2;
        --v7;
      }
      while ( v7 );
      v9 = 2 * ((v8 - (char *)v6) >> 1);
      v10 = (unsigned __int16 *)CoTaskMemAlloc(v9 + 2);
      v13 = v10;
      if ( v10 )
      {
        memcpy_s(v10, v9 + 2, v6, v9);
        v13[v9 / 2] = 0;
      }
      if ( !v13 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
      *a1 = v13;
      if ( v16 >= 8 )
        operator delete(Source[0]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x445, v11, v12);
      return (unsigned int)wil::ResultFromCaughtException(v14);
    }
    return v2;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)0x80004003LL,
      0);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180012e94  mov     [rsp+arg_8], rbx
0x180012e99  mov     [rsp+arg_10], rsi
0x180012e9e  push    rdi
0x180012e9f  push    r12
0x180012ea1  push    r13
0x180012ea3  push    r14
0x180012ea5  push    r15
0x180012ea7  sub     rsp, 60h
0x180012eab  mov     rax, cs:__security_cookie
0x180012eb2  xor     rax, rsp
0x180012eb5  mov     [rsp+88h+var_38], rax
0x180012eba  mov     rsi, rcx
0x180012ebd  xor     r13d, r13d
0x180012ec0  mov     [rsp+88h+var_68], r13d; int
0x180012ec5  mov     r14d, r13d
0x180012ec8  test    rcx, rcx
0x180012ecb  jnz     short loc_180012EF5
0x180012ecd  mov     rcx, [rsp+88h]; this
0x180012ed5  mov     ebx, 80004003h
0x180012eda  mov     r9d, ebx; char *
0x180012edd  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180012ee4  mov     edx, 43Bh; void *
0x180012ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012eee  mov     eax, ebx
0x180012ef0  jmp     loc_180012FE0
0x180012ef5  mov     [rcx], r13
0x180012ef8  call    ?GetProvisioningDiagnosticsFolderPath@ProvisioningPaths@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvisioningPaths::GetProvisioningDiagnosticsFolderPath(void)
0x180012efd  mov     rdx, rax
0x180012f00  mov     [rsp+88h+var_40], 7
0x180012f09  mov     [rsp+88h+var_48], r13
0x180012f0e  mov     word ptr [rsp+88h+Source], r13w
0x180012f14  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012f18  xor     r8d, r8d
0x180012f1b  lea     rcx, [rsp+88h+Source]; void *
0x180012f20  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012f25  nop
0x180012f26  lea     rdx, aDeviceprovisio_1; "DeviceProvisioning-OOBE-Diagnostics-Get"...
0x180012f2d  lea     rcx, [rsp+88h+Source]; Src
0x180012f32  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180012f37  lea     rbx, [rsp+88h+Source]
0x180012f3c  cmp     [rsp+88h+var_40], 8
0x180012f42  cmovnb  rbx, [rsp+88h+Source]
0x180012f48  mov     rcx, [rsp+88h]; this
0x180012f50  test    rbx, rbx
0x180012f53  jz      loc_180013007
0x180012f59  mov     ecx, 7FFFFFFFh
0x180012f5e  mov     rax, rbx
0x180012f61  cmp     [rax], r13w
0x180012f65  jz      short loc_180012F71
0x180012f67  add     rax, 2
0x180012f6b  sub     rcx, 1
0x180012f6f  jnz     short loc_180012F61
0x180012f71  sub     rax, rbx
0x180012f74  sar     rax, 1
0x180012f77  lea     r15, [rax+rax]
0x180012f7b  lea     rcx, [r15+2]; cb
0x180012f7f  call    cs:__imp_CoTaskMemAlloc
0x180012f85  mov     rdi, rax
0x180012f88  test    rax, rax
0x180012f8b  jz      short loc_180012FA5
0x180012f8d  mov     r9, r15; SourceSize
0x180012f90  mov     r8, rbx; Source
0x180012f93  lea     rdx, [r15+2]; DestinationSize
0x180012f97  mov     rcx, rax; Destination
0x180012f9a  call    cs:__imp_memcpy_s
0x180012fa0  mov     [r15+rdi], r13w
0x180012fa5  mov     [rsp+88h+var_60], rdi
0x180012faa  mov     [rsp+88h+var_68], 2
0x180012fb2  mov     rcx, [rsp+88h]; this
0x180012fba  test    rdi, rdi
0x180012fbd  jz      short loc_180013019
0x180012fbf  mov     [rsi], rdi
0x180012fc2  cmp     [rsp+88h+var_40], 8
0x180012fc8  jb      short loc_180012FD6
0x180012fca  mov     rcx, [rsp+88h+Source]
0x180012fcf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012fd5  nop
0x180012fd6  jmp     short loc_180012FDD
0x180012fd8  mov     r14d, [rsp+88h+var_68]
0x180012fdd  mov     eax, r14d
0x180012fe0  mov     rcx, [rsp+88h+var_38]
0x180012fe5  xor     rcx, rsp; StackCookie
0x180012fe8  call    __security_check_cookie
0x180012fed  lea     r11, [rsp+88h+var_28]
0x180012ff2  mov     rbx, [r11+38h]
0x180012ff6  mov     rsi, [r11+40h]
0x180012ffa  mov     rsp, r11
0x180012ffd  pop     r15
0x180012fff  pop     r14
0x180013001  pop     r13
0x180013003  pop     r12
0x180013005  pop     rdi
0x180013006  retn
0x180013007  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001300e  mov     edx, 0F89h; void *
0x180013013  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013019  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013020  mov     edx, 0FF8h; void *
0x180013025  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
