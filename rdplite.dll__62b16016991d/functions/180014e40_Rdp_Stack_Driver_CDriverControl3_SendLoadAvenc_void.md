# Rdp::Stack::Driver::CDriverControl3::SendLoadAvenc(void)

- ea: `0x180014e40`
- end: `0x180015036`
- name: `?SendLoadAvenc@CDriverControl3@Driver@Stack@Rdp@@AEAAXXZ`
- size: `502`
- prototype: `void __fastcall(Rdp::Stack::Driver::CDriverControl3 *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015650`

## callees

- `0x1800036f0`
- `0x180004154`
- `0x18000af58`
- `0x18000cf28`
- `0x180012144`
- `0x18001261c`
- `0x180014054`
- `0x1800140a8`
- `0x180014e40`

## string_xrefs

- `0x180014e91`: `Failed to retrieve PKEY_EncodingDllGuid property`
- `0x180014eda`: `Failed to retrieve PKEY_OutProcEncodingProcessorClsid property`
- `0x180014f95`: `Failed to set EncoderDllName`

## pseudocode

```c
void __fastcall Rdp::Stack::Driver::CDriverControl3::SendLoadAvenc(
        Rdp::Stack::Driver::CDriverControl3 *this,
        __int64 a2,
        __int64 a3,
        struct _GUID *a4)
{
  Rdp::Utils::Props *v5; // rcx
  unsigned int Guid; // eax
  Rdp::Utils::Props *v7; // rcx
  struct _GUID *v8; // r9
  unsigned int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  char *v12; // rdx
  __int64 v13; // rbx
  char *v14; // rcx
  void *v15; // rcx
  unsigned int v16; // eax
  const char *v17; // [rsp+28h] [rbp-D8h]
  const char *v18; // [rsp+28h] [rbp-D8h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  const char *v20; // [rsp+28h] [rbp-D8h]
  struct _OVERLAPPED *v21; // [rsp+38h] [rbp-C8h]
  DWORD v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _tagpropertykey v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v25[3]; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+8Ch] [rbp-74h] BYREF
  GUID fmtid; // [rsp+294h] [rbp+194h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v5 = (Rdp::Utils::Props *)*((_QWORD *)this + 11);
  v23 = xmmword_1800301B8;
  Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(
           v5,
           (struct IPropertyStore *)&PKEY_EncodingDllGuid,
           (const struct _tagpropertykey *)&v23,
           a4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x420,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)Guid,
    (int)"Failed to retrieve PKEY_EncodingDllGuid property",
    v17);
  v7 = (Rdp::Utils::Props *)*((_QWORD *)this + 11);
  v24[0].fmtid = (GUID)xmmword_1800301B8;
  v9 = Rdp::Utils::Props::IPropertyStore_GetGuid(
         v7,
         (struct IPropertyStore *)&PKEY_OutProcEncodingProcessorClsid,
         v24,
         v8);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x42B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v9,
    (int)"Failed to retrieve PKEY_OutProcEncodingProcessorClsid property",
    v18);
  memset_0(v25, 0, 0x224u);
  v25[2] = 1;
  v25[0] = 548;
  fmtid = v24[0].fmtid;
  v10 = (_QWORD *)Rdp::Stack::Driver::CDriverControl3::LookupEncoderDllName(
                    (__int64)this,
                    (__int64)v24,
                    (const GUID *)&v23);
  if ( v10[3] > 7u )
    v10 = (_QWORD *)*v10;
  v11 = 2147483646;
  v12 = &v26;
  v13 = 260;
  do
  {
    if ( !v11 )
      break;
    if ( !*(_WORD *)v10 )
      break;
    *(_WORD *)v12 = *(_WORD *)v10;
    v10 = (_QWORD *)((char *)v10 + 2);
    v12 += 2;
    --v11;
    --v13;
  }
  while ( v13 );
  v14 = v12 - 2;
  if ( v13 )
    v14 = v12;
  *(_WORD *)v14 = 0;
  std::wstring::_Tidy_deallocate(v24);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x43A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    v13 == 0 ? (const char *)0x8007007ALL : 0,
    (int)"Failed to set EncoderDllName",
    v19);
  v15 = (void *)*((_QWORD *)this + 16);
  v22 = 0;
  v16 = Rdp::Stack::Driver::CDriverControl3::InternalDeviceIoControl(v15, 0x80000040, v25, 0x224u, 0, 0, &v22, v21);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x447,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v16,
    (int)"Failed to send RDPIDD_OPCODE_TYPE_LOAD_AVENC",
    v20);
}

```

## disassembly

```asm
0x180014e40  push    rbp
0x180014e42  push    rbx
0x180014e43  push    rsi
0x180014e44  push    rdi
0x180014e45  lea     rbp, [rsp-1C8h]
0x180014e4d  sub     rsp, 2C8h
0x180014e54  mov     rax, cs:__security_cookie
0x180014e5b  xor     rax, rsp
0x180014e5e  mov     [rbp+1E0h+var_30], rax
0x180014e65  movups  xmm0, cs:xmmword_1800301B8
0x180014e6c  mov     rdi, rcx
0x180014e6f  lea     r8, [rsp+2E0h+var_298]; struct _tagpropertykey *
0x180014e74  mov     rcx, [rcx+58h]; this
0x180014e78  lea     rdx, PKEY_EncodingDllGuid; struct IPropertyStore *
0x180014e7f  movdqu  xmmword ptr [rsp+2E0h+var_298.fmtid.Data1], xmm0
0x180014e85  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x180014e8a  mov     rcx, [rbp+1E8h]; this
0x180014e91  lea     rdx, aFailedToRetrie_16; "Failed to retrieve PKEY_EncodingDllGuid"...
0x180014e98  mov     [rsp+2E0h+var_2C0], rdx; int
0x180014e9d  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014ea4  mov     edx, 420h; void *
0x180014ea9  mov     r9d, eax; char *
0x180014eac  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014eb1  movups  xmm0, cs:xmmword_1800301B8
0x180014eb8  mov     rcx, [rdi+58h]; this
0x180014ebc  lea     r8, [rsp+2E0h+var_298.pid]; struct _tagpropertykey *
0x180014ec1  lea     rdx, PKEY_OutProcEncodingProcessorClsid; struct IPropertyStore *
0x180014ec8  movdqu  xmmword ptr [rsp+2E0h+var_298.pid], xmm0
0x180014ece  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x180014ed3  mov     rcx, [rbp+1E8h]; this
0x180014eda  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_OutProcEncoding"...
0x180014ee1  mov     [rsp+2E0h+var_2C0], rdx; int
0x180014ee6  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014eed  mov     edx, 42Bh; void *
0x180014ef2  mov     r9d, eax; char *
0x180014ef5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014efa  xor     edx, edx; Val
0x180014efc  lea     rcx, [rbp+1E0h+var_260]; void *
0x180014f00  mov     r8d, 224h; Size
0x180014f06  call    memset_0
0x180014f0b  movups  xmm0, xmmword ptr [rsp+2E0h+var_298.pid]
0x180014f10  lea     r8, [rsp+2E0h+var_298]
0x180014f15  mov     [rbp+1E0h+var_258], 1
0x180014f1c  lea     rdx, [rsp+2E0h+var_298.pid]
0x180014f21  mov     [rbp+1E0h+var_260], 224h
0x180014f28  mov     rcx, rdi
0x180014f2b  movdqu  [rbp+1E0h+var_4C], xmm0
0x180014f33  call    ?LookupEncoderDllName@CDriverControl3@Driver@Stack@Rdp@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Rdp::Stack::Driver::CDriverControl3::LookupEncoderDllName(_GUID const &)
0x180014f38  cmp     qword ptr [rax+18h], 7
0x180014f3d  jbe     short loc_180014F42
0x180014f3f  mov     rax, [rax]
0x180014f42  mov     ecx, 7FFFFFFEh
0x180014f47  lea     rdx, [rbp+1E0h+var_254]
0x180014f4b  mov     ebx, 104h
0x180014f50  xor     esi, esi
0x180014f52  test    rcx, rcx
0x180014f55  jz      short loc_180014F76
0x180014f57  movzx   r8d, word ptr [rax]
0x180014f5b  test    r8w, r8w
0x180014f5f  jz      short loc_180014F76
0x180014f61  mov     [rdx], r8w
0x180014f65  add     rax, 2
0x180014f69  add     rdx, 2
0x180014f6d  dec     rcx
0x180014f70  sub     rbx, 1
0x180014f74  jnz     short loc_180014F52
0x180014f76  lea     rcx, [rdx-2]
0x180014f7a  test    rbx, rbx
0x180014f7d  cmovnz  rcx, rdx
0x180014f81  mov     [rcx], si
0x180014f84  lea     rcx, [rsp+2E0h+var_298.pid]
0x180014f89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014f8e  mov     rcx, [rbp+1E8h]; this
0x180014f95  lea     rax, aFailedToSetEnc; "Failed to set EncoderDllName"
0x180014f9c  neg     rbx
0x180014f9f  mov     [rsp+2E0h+var_2C0], rax; int
0x180014fa4  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014fab  mov     edx, 43Ah; void *
0x180014fb0  sbb     r9d, r9d
0x180014fb3  not     r9d
0x180014fb6  and     r9d, 8007007Ah; char *
0x180014fbd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014fc2  mov     rcx, [rdi+80h]; void *
0x180014fc9  lea     rax, [rsp+2E0h+var_2A0]
0x180014fce  mov     [rsp+2E0h+var_2B0], rax; LPDWORD
0x180014fd3  lea     r8, [rbp+1E0h+var_260]; void *
0x180014fd7  mov     dword ptr [rsp+2E0h+var_2B8], esi; char *
0x180014fdb  mov     r9d, 224h; unsigned int
0x180014fe1  mov     edx, 80000040h; unsigned int
0x180014fe6  mov     [rsp+2E0h+var_2C0], rsi; void *
0x180014feb  mov     [rsp+2E0h+var_2A0], esi
0x180014fef  call    ?InternalDeviceIoControl@CDriverControl3@Driver@Stack@Rdp@@SAHPEAXK0K0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CDriverControl3::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *,_OVERLAPPED *)
0x180014ff4  mov     rcx, [rbp+1E8h]; this
0x180014ffb  lea     rdx, aFailedToSendRd_6; "Failed to send RDPIDD_OPCODE_TYPE_LOAD_"...
0x180015002  mov     [rsp+2E0h+var_2C0], rdx; int
0x180015007  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001500e  mov     edx, 447h; void *
0x180015013  mov     r9d, eax; char *
0x180015016  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001501b  mov     rcx, [rbp+1E0h+var_30]
0x180015022  xor     rcx, rsp; StackCookie
0x180015025  call    __security_check_cookie
0x18001502a  add     rsp, 2C8h
0x180015031  pop     rdi
0x180015032  pop     rsi
0x180015033  pop     rbx
0x180015034  pop     rbp
0x180015035  retn
```
