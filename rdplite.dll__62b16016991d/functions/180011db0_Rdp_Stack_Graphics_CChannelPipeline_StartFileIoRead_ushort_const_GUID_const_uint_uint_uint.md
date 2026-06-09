# Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead(ushort const *,_GUID const &,uint,uint,uint)

- ea: `0x180011db0`
- end: `0x180011edc`
- name: `?StartFileIoRead@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXPEBGAEBU_GUID@@III@Z`
- size: `300`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CChannelPipeline *this, const unsigned __int16 *, const struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c410`
- `0x180011c64`

## callees

- `0x18000aff0`
- `0x18000cf28`
- `0x18000e5fc`
- `0x18000e794`
- `0x180011a7c`
- `0x180011b5c`
- `0x180011db0`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead(
        Rdp::Stack::Graphics::CChannelPipeline *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned int *a4)
{
  _DWORD *v4; // rbx
  unsigned int UInt32; // eax
  _DWORD *v9; // rsi
  unsigned int *v10; // r9
  unsigned int v11; // eax
  char *v12; // rcx
  const char *v13; // [rsp+28h] [rbp-60h]
  const char *v14; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (_DWORD *)((char *)this + 808);
  UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
             *((Rdp::Utils::Props **)this + 102),
             (struct IPropertyStore *)&PKEY_RdpIddMajorVersion,
             (const struct _tagpropertykey *)((char *)this + 808),
             a4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
    (const char *)UInt32,
    (int)"Failed to retrieve PKEY_RdpIddMajorVersion",
    v13);
  v9 = (_DWORD *)((char *)this + 812);
  v11 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
          *((Rdp::Utils::Props **)this + 102),
          (struct IPropertyStore *)&PKEY_RdpIddMinorVersion,
          (const struct _tagpropertykey *)((char *)this + 812),
          v10);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x65,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
    (const char *)v11,
    (int)"Failed to retrieve PKEY_RdpIddMinorVersion",
    v14);
  if ( *v4 == 6400 )
  {
    if ( *v9 != 3 )
    {
LABEL_3:
      if ( *v4 < 0x1B00u || !*v9 )
        goto LABEL_6;
      goto LABEL_5;
    }
    goto LABEL_5;
  }
  if ( *v4 != 6656 )
    goto LABEL_3;
  if ( *v9 == 3 )
LABEL_5:
    *((_BYTE *)this + 833) = 1;
LABEL_6:
  Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Reset((char *)this + 88);
  v12 = (char *)this + 568;
  if ( *((_BYTE *)this + 833) )
    Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___(
      v12,
      a2,
      a3);
  else
    Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___(
      v12,
      a2,
      a3);
  Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(this);
}

```

## disassembly

```asm
0x180011db0  push    rbx
0x180011db2  push    rbp
0x180011db3  push    rsi
0x180011db4  push    rdi
0x180011db5  push    r14
0x180011db7  push    r15
0x180011db9  sub     rsp, 58h
0x180011dbd  lea     rbx, [rcx+328h]
0x180011dc4  mov     rbp, r8
0x180011dc7  mov     r14, rdx
0x180011dca  mov     rdi, rcx
0x180011dcd  mov     rcx, [rcx+330h]; this
0x180011dd4  lea     rdx, PKEY_RdpIddMajorVersion; struct IPropertyStore *
0x180011ddb  mov     r8, rbx; struct _tagpropertykey *
0x180011dde  mov     r15d, r9d
0x180011de1  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180011de6  mov     rcx, [rsp+88h]; this
0x180011dee  lea     rdx, aFailedToRetrie_13; "Failed to retrieve PKEY_RdpIddMajorVers"...
0x180011df5  mov     qword ptr [rsp+88h+var_68], rdx; int
0x180011dfa  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011e01  mov     edx, 5Eh ; '^'; void *
0x180011e06  mov     r9d, eax; char *
0x180011e09  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011e0e  mov     rcx, [rdi+330h]; this
0x180011e15  lea     rsi, [rdi+32Ch]
0x180011e1c  mov     r8, rsi; struct _tagpropertykey *
0x180011e1f  lea     rdx, PKEY_RdpIddMinorVersion; struct IPropertyStore *
0x180011e26  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180011e2b  mov     rcx, [rsp+88h]; this
0x180011e33  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_RdpIddMinorVers"...
0x180011e3a  mov     qword ptr [rsp+88h+var_68], rdx; int
0x180011e3f  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011e46  mov     edx, 65h ; 'e'; void *
0x180011e4b  mov     r9d, eax; char *
0x180011e4e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011e53  cmp     dword ptr [rbx], 1900h
0x180011e59  jnz     short loc_180011EB4
0x180011e5b  cmp     dword ptr [rsi], 3
0x180011e5e  jz      short loc_180011E6D
0x180011e60  cmp     dword ptr [rbx], 1B00h
0x180011e66  jb      short loc_180011E74
0x180011e68  cmp     dword ptr [rsi], 1
0x180011e6b  jb      short loc_180011E74
0x180011e6d  mov     byte ptr [rdi+341h], 1
0x180011e74  lea     rcx, [rdi+58h]
0x180011e78  call    ?Reset@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAAXXZ; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Reset(void)
0x180011e7d  cmp     byte ptr [rdi+341h], 0
0x180011e84  lea     rax, [rsp+88h+arg_0]
0x180011e8c  mov     [rsp+88h+var_48], rax
0x180011e91  lea     rcx, [rdi+238h]
0x180011e98  mov     [rsp+88h+arg_0], rdi
0x180011ea0  mov     r8, rbp
0x180011ea3  mov     rdx, r14
0x180011ea6  jz      short loc_180011EC3
0x180011ea8  mov     [rsp+88h+var_60], r15d
0x180011ead  call    Rdp__Stack__Driver__CFileChannel_Rdp__Utils__TP__details__CCompletionPortIo___Open__Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____8____lambda_1___
0x180011eb2  jmp     short loc_180011EC8
0x180011eb4  cmp     dword ptr [rbx], 1A00h
0x180011eba  jnz     short loc_180011E60
0x180011ebc  cmp     dword ptr [rsi], 3
0x180011ebf  jz      short loc_180011E6D
0x180011ec1  jmp     short loc_180011E74
0x180011ec3  call    Rdp__Stack__Driver__CFileChannel_Rdp__Utils__TP__details__CCompletionPortIo___Open__Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____10____lambda_2___
0x180011ec8  mov     rcx, rdi; this
0x180011ecb  add     rsp, 58h
0x180011ecf  pop     r15
0x180011ed1  pop     r14
0x180011ed3  pop     rdi
0x180011ed4  pop     rsi
0x180011ed5  pop     rbp
0x180011ed6  pop     rbx
0x180011ed7  jmp     ?ScheduleNextReadRequest@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXXZ; Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(void)
```
