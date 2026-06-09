# Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::SecurityFilterHelper(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::shared_ptr<Microsoft::Basix::WinUtils::CertContext> const &,bool,bool,bool)

- ea: `0x180155674`
- end: `0x1801558e8`
- name: `??0SecurityFilterHelper@Sspi@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@VCertContext@WinUtils@Basix@Microsoft@@@6@_N22@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180146ef4`

## callees

- `0x18000da90`
- `0x180024700`
- `0x180155024`
- `0x1801551bc`
- `0x180155674`
- `0x180157348`
- `0x180157350`
- `0x1802e9b68`
- `0x18032f050`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `Secur32!InitSecurityInterfaceW` at `0x1801556fd`
- `Secur32!InitSecurityInterfaceW` at `0x1801556fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::SecurityFilterHelper(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        char a4,
        unsigned int TokenSize,
        char a6)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  PSecurityFunctionTableW inited; // rax
  int v11; // edx
  char v12; // r8
  int v13; // ecx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  __int64 v20; // [rsp+20h] [rbp-89h] BYREF
  volatile signed __int32 *v21; // [rsp+28h] [rbp-81h]
  _BYTE v22[32]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+60h] [rbp-49h] BYREF

  *(_QWORD *)a1 = &Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::`vftable';
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 104) = a4;
  *(_BYTE *)(a1 + 105) = TokenSize;
  *(_BYTE *)(a1 + 106) = a6;
  *(_DWORD *)(a1 + 108) = 1096;
  v8 = a1 + 112;
  *(_OWORD *)v8 = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 0;
  v9 = a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  std::string::_Construct<2,char const *>(v8, a2, v9);
  inited = InitSecurityInterfaceW();
  *(_QWORD *)(a1 + 8) = inited;
  if ( !inited )
  {
    std::string::string(&v20, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\sspihelper.cpp");
    std::string::string(v22, "Failed to query SSPI dispatch table");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v22, &v20, 32);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  if ( !inited->SetContextAttributesW )
    inited->SetContextAttributesW = SetContextAttributesW_0;
  *(_QWORD *)(a1 + 64) = -1;
  *(_QWORD *)(a1 + 56) = -1;
  *(_QWORD *)(a1 + 48) = -1;
  *(_QWORD *)(a1 + 40) = -1;
  *(_OWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v11 = 33052;
    *(_DWORD *)(a1 + 36) = 33052;
    if ( *(_BYTE *)(a1 + 106) )
    {
      v11 = 33054;
      *(_DWORD *)(a1 + 36) = 33054;
    }
    v12 = *(_BYTE *)(a1 + 105);
    v13 = v11 | (v12 != 0 ? 1024 : 0x10000);
  }
  else
  {
    *(_DWORD *)(a1 + 36) = 16668;
    v12 = *(_BYTE *)(a1 + 105);
    v13 = v12 != 0 ? 17692 : 49436;
  }
  *(_DWORD *)(a1 + 36) = v13;
  if ( v12 )
  {
    TokenSize = Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::GetTokenSize((Microsoft::Basix::Dct::Sspi::SecurityFilterHelper *)a1);
    v14 = (__int64 *)std::make_shared<Microsoft::Basix::Dct::Sspi::SspiDtlsTokenIBuffer,unsigned int>(&v20, &TokenSize);
  }
  else
  {
    TokenSize = Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::GetTokenSize((Microsoft::Basix::Dct::Sspi::SecurityFilterHelper *)a1);
    v14 = (__int64 *)std::make_shared<Microsoft::Basix::Dct::Sspi::SspiTlsTokenIBuffer,unsigned int>(&v20, &TokenSize);
  }
  v15 = *v14;
  v16 = v14[1];
  *v14 = 0;
  v14[1] = 0;
  v17 = *(volatile signed __int32 **)(a1 + 80);
  *(_QWORD *)(a1 + 80) = v16;
  *(_QWORD *)(a1 + 72) = v15;
  if ( v17 )
  {
    if ( !_InterlockedDecrement(v17 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( !_InterlockedDecrement(v17 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = v21;
  if ( v21 )
  {
    if ( !_InterlockedDecrement(v21 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( !_InterlockedDecrement(v18 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::InitializeCredentials(a1, a3);
  return a1;
}

```

## disassembly

```asm
0x180155674  mov     rax, rsp
0x180155677  mov     [rax+10h], rbx
0x18015567b  mov     [rax+18h], rsi
0x18015567f  mov     [rax+20h], rdi
0x180155683  mov     [rax+8], rcx
0x180155687  push    rbp
0x180155688  push    r14
0x18015568a  push    r15
0x18015568c  lea     rbp, [rax-4Fh]
0x180155690  mov     eax, 0E0h
0x180155695  call    _alloca_probe
0x18015569a  sub     rsp, rax
0x18015569d  mov     rsi, r8
0x1801556a0  mov     rbx, rcx
0x1801556a3  lea     rax, ??_7SecurityFilterHelper@Sspi@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::`vftable'
0x1801556aa  mov     [rcx], rax
0x1801556ad  xor     r15d, r15d
0x1801556b0  mov     [rcx+48h], r15
0x1801556b4  mov     [rcx+50h], r15
0x1801556b8  mov     [rcx+58h], r15
0x1801556bc  mov     [rcx+60h], r15
0x1801556c0  mov     [rcx+68h], r9b
0x1801556c4  mov     al, byte ptr [rbp+47h+arg_20]
0x1801556c7  mov     [rcx+69h], al
0x1801556ca  mov     al, [rbp+47h+arg_28]
0x1801556cd  mov     [rcx+6Ah], al
0x1801556d0  mov     dword ptr [rcx+6Ch], 448h
0x1801556d7  add     rcx, 70h ; 'p'
0x1801556db  xorps   xmm0, xmm0
0x1801556de  movups  xmmword ptr [rcx], xmm0
0x1801556e1  mov     [rcx+10h], r15
0x1801556e5  mov     [rcx+18h], r15
0x1801556e9  mov     r8, [rdx+10h]
0x1801556ed  cmp     qword ptr [rdx+18h], 0Fh
0x1801556f2  jbe     short loc_1801556F7
0x1801556f4  mov     rdx, [rdx]
0x1801556f7  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1801556fc  nop
0x1801556fd  call    cs:__imp_InitSecurityInterfaceW
0x180155703  mov     [rbx+8], rax
0x180155707  test    rax, rax
0x18015570a  jz      loc_18015589C
0x180155710  cmp     [rax+0D8h], r15
0x180155717  jnz     short loc_180155727
0x180155719  lea     rcx, SetContextAttributesW_0
0x180155720  mov     [rax+0D8h], rcx
0x180155727  or      r14, 0FFFFFFFFFFFFFFFFh
0x18015572b  mov     [rbx+40h], r14
0x18015572f  mov     [rbx+38h], r14
0x180155733  mov     [rbx+30h], r14
0x180155737  mov     [rbx+28h], r14
0x18015573b  xorps   xmm0, xmm0
0x18015573e  xor     eax, eax
0x180155740  movups  xmmword ptr [rbx+10h], xmm0
0x180155744  mov     [rbx+20h], eax
0x180155747  cmp     [rbx+68h], r15b
0x18015574b  jz      short loc_18015577E
0x18015574d  mov     edx, 811Ch
0x180155752  mov     [rbx+24h], edx
0x180155755  cmp     [rbx+6Ah], r15b
0x180155759  jz      short loc_180155763
0x18015575b  mov     edx, 811Eh
0x180155760  mov     [rbx+24h], edx
0x180155763  mov     r8b, [rbx+69h]
0x180155767  mov     al, r8b
0x18015576a  neg     al
0x18015576c  sbb     ecx, ecx
0x18015576e  and     ecx, 0FFFF0400h
0x180155774  add     ecx, 10000h
0x18015577a  or      ecx, edx
0x18015577c  jmp     short loc_18015579C
0x18015577e  mov     dword ptr [rbx+24h], 411Ch
0x180155785  mov     r8b, [rbx+69h]
0x180155789  mov     al, r8b
0x18015578c  neg     al
0x18015578e  sbb     ecx, ecx
0x180155790  and     ecx, 0FFFF8400h
0x180155796  add     ecx, 0C11Ch
0x18015579c  mov     [rbx+24h], ecx
0x18015579f  mov     rcx, rbx; this
0x1801557a2  test    r8b, r8b
0x1801557a5  jnz     short loc_1801557BF
0x1801557a7  call    ?GetTokenSize@SecurityFilterHelper@Sspi@Dct@Basix@Microsoft@@IEAAIXZ; Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::GetTokenSize(void)
0x1801557ac  mov     [rbp+47h+arg_20], eax
0x1801557af  lea     rdx, [rbp+47h+arg_20]
0x1801557b3  lea     rcx, [rsp+0F0h+var_D0]
0x1801557b8  call    ??$make_shared@VSspiTlsTokenIBuffer@Sspi@Dct@Basix@Microsoft@@I@std@@YA?AV?$shared_ptr@VSspiTlsTokenIBuffer@Sspi@Dct@Basix@Microsoft@@@0@$$QEAI@Z; std::make_shared<Microsoft::Basix::Dct::Sspi::SspiTlsTokenIBuffer,uint>(uint &&)
0x1801557bd  jmp     short loc_1801557D5
0x1801557bf  call    ?GetTokenSize@SecurityFilterHelper@Sspi@Dct@Basix@Microsoft@@IEAAIXZ; Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::GetTokenSize(void)
0x1801557c4  mov     [rbp+47h+arg_20], eax
0x1801557c7  lea     rdx, [rbp+47h+arg_20]
0x1801557cb  lea     rcx, [rsp+0F0h+var_D0]
0x1801557d0  call    ??$make_shared@VSspiDtlsTokenIBuffer@Sspi@Dct@Basix@Microsoft@@I@std@@YA?AV?$shared_ptr@VSspiDtlsTokenIBuffer@Sspi@Dct@Basix@Microsoft@@@0@$$QEAI@Z; std::make_shared<Microsoft::Basix::Dct::Sspi::SspiDtlsTokenIBuffer,uint>(uint &&)
0x1801557d5  mov     rcx, [rax]
0x1801557d8  mov     rdx, [rax+8]
0x1801557dc  mov     [rax], r15
0x1801557df  mov     [rax+8], r15
0x1801557e3  mov     rdi, [rbx+50h]
0x1801557e7  test    rdi, rdi
0x1801557ea  mov     [rbx+50h], rdx
0x1801557ee  mov     [rbx+48h], rcx
0x1801557f2  jz      short loc_18015582D
0x1801557f4  mov     eax, r14d
0x1801557f7  lock xadd [rdi+8], eax
0x1801557fc  add     eax, r14d
0x1801557ff  jnz     short loc_18015582D
0x180155801  mov     rax, [rdi]
0x180155804  mov     rcx, rdi
0x180155807  mov     rax, [rax]
0x18015580a  call    cs:__guard_dispatch_icall_fptr
0x180155810  mov     eax, r14d
0x180155813  lock xadd [rdi+0Ch], eax
0x180155818  add     eax, r14d
0x18015581b  jnz     short loc_18015582D
0x18015581d  mov     rax, [rdi]
0x180155820  mov     rcx, rdi
0x180155823  mov     rax, [rax+8]
0x180155827  call    cs:__guard_dispatch_icall_fptr
0x18015582d  mov     rdi, [rsp+0F0h+var_C8]
0x180155832  test    rdi, rdi
0x180155835  jz      short loc_180155870
0x180155837  mov     eax, r14d
0x18015583a  lock xadd [rdi+8], eax
0x18015583f  add     eax, r14d
0x180155842  jnz     short loc_180155870
0x180155844  mov     rax, [rdi]
0x180155847  mov     rcx, rdi
0x18015584a  mov     rax, [rax]
0x18015584d  call    cs:__guard_dispatch_icall_fptr
0x180155853  mov     eax, r14d
0x180155856  lock xadd [rdi+0Ch], eax
0x18015585b  add     eax, r14d
0x18015585e  jnz     short loc_180155870
0x180155860  mov     rax, [rdi]
0x180155863  mov     rcx, rdi
0x180155866  mov     rax, [rax+8]
0x18015586a  call    cs:__guard_dispatch_icall_fptr
0x180155870  mov     rdx, rsi
0x180155873  mov     rcx, rbx
0x180155876  call    ?InitializeCredentials@SecurityFilterHelper@Sspi@Dct@Basix@Microsoft@@IEAAXAEBV?$shared_ptr@VCertContext@WinUtils@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::Sspi::SecurityFilterHelper::InitializeCredentials(std::shared_ptr<Microsoft::Basix::WinUtils::CertContext> const &)
0x18015587b  nop
0x18015587c  mov     rax, rbx
0x18015587f  lea     r11, [rsp+0F0h+var_10]
0x180155887  mov     rbx, [r11+28h]
0x18015588b  mov     rsi, [r11+30h]
0x18015588f  mov     rdi, [r11+38h]
0x180155893  mov     rsp, r11
0x180155896  pop     r15
0x180155898  pop     r14
0x18015589a  pop     rbp
0x18015589b  retn
0x18015589c  lea     rdx, aCW1SSrcLibbasi_44; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1801558a3  lea     rcx, [rsp+0F0h+var_D0]
0x1801558a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801558ad  nop
0x1801558ae  lea     rdx, aFailedToQueryS; "Failed to query SSPI dispatch table"
0x1801558b5  lea     rcx, [rbp+47h+var_B0]
0x1801558b9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801558be  nop
0x1801558bf  mov     r9d, 20h ; ' '
0x1801558c5  lea     r8, [rsp+0F0h+var_D0]
0x1801558ca  lea     rdx, [rbp+47h+var_B0]
0x1801558ce  lea     rcx, [rbp+47h+pExceptionObject]
0x1801558d2  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x1801558d7  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x1801558de  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1801558e2  call    _CxxThrowException
```
