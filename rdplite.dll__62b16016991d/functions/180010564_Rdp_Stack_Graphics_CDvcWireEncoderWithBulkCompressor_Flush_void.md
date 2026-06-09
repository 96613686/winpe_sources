# Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::Flush(void)

- ea: `0x180010564`
- end: `0x18001068e`
- name: `?Flush@CDvcWireEncoderWithBulkCompressor@Graphics@Stack@Rdp@@QEAAXXZ`
- size: `298`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800103b4`

## callees

- `0x18000cf28`
- `0x180012934`
- `0x18002a010`

## string_xrefs

- `0x1800105f8`: `Failed to compress buffer`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::Flush(
        Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor *this)
{
  _QWORD *v1; // rbx
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // eax
  char *v7; // [rsp+28h] [rbp-30h]
  char *v8; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char *v10; // [rsp+60h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 48);
  v10 = (char *)(*((_QWORD *)this + 4)
               + 4 * (((*((_QWORD *)this + 4) + 65534LL) & 0xFFFFFFFFFFFF0001uLL) / 0xFFFF)
               + ((*((_QWORD *)this + 4) + 65534LL) & 0xFFFFFFFFFFFF0001uLL) / 0xFFFF
               + 7);
  std::vector<unsigned char>::reserve((char *)this + 48, v10);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, _DWORD, _QWORD, _DWORD, char **))(**((_QWORD **)this + 385)
                                                                                                  + 48LL))(
         *((_QWORD *)this + 385),
         *((_QWORD *)this + 1),
         *((unsigned int *)this + 8),
         (char *)this + 72,
         *((_DWORD *)this + 768),
         *v1,
         (_DWORD)v10,
         &v10);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xFD,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/DvcWireEncoder.h",
    (const char *)v3,
    (int)"Failed to compress buffer",
    v7);
  v4 = *(_QWORD *)this;
  v5 = *v1;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 768) = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64, int, _DWORD, int, _QWORD))(*(_QWORD *)v4 + 24LL))(
         v4,
         v10,
         v5,
         2,
         1,
         (_DWORD)v10,
         3,
         0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x10C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/DvcWireEncoder.h",
    (const char *)v6,
    (int)"Failed to send caps confirm",
    v8);
}

```

## disassembly

```asm
0x180010564  mov     [rsp+arg_8], rbx
0x180010569  push    rdi
0x18001056a  sub     rsp, 50h
0x18001056e  mov     r8, [rcx+20h]
0x180010572  lea     rbx, [rcx+30h]
0x180010576  mov     rdi, rcx
0x180010579  mov     rax, 8000800080008001h
0x180010583  mov     rcx, rbx
0x180010586  lea     rdx, [r8+0FFFEh]
0x18001058d  and     rdx, 0FFFFFFFFFFFF0001h
0x180010594  mul     rdx
0x180010597  shr     rdx, 0Fh
0x18001059b  lea     rax, [r8+rdx*4]
0x18001059f  add     rdx, 7
0x1800105a3  add     rdx, rax
0x1800105a6  mov     [rsp+58h+arg_0], rdx
0x1800105ab  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x1800105b0  mov     rcx, [rdi+0C08h]
0x1800105b7  lea     rdx, [rsp+58h+arg_0]
0x1800105bc  mov     r8d, [rdi+20h]
0x1800105c0  lea     r9, [rdi+48h]
0x1800105c4  mov     [rsp+58h+var_20], rdx
0x1800105c9  mov     edx, dword ptr [rsp+58h+arg_0]
0x1800105cd  mov     rax, [rcx]
0x1800105d0  mov     [rsp+58h+var_28], edx
0x1800105d4  mov     rdx, [rbx]
0x1800105d7  mov     [rsp+58h+var_30], rdx; char *
0x1800105dc  mov     edx, [rdi+0C00h]
0x1800105e2  mov     rax, [rax+30h]
0x1800105e6  mov     [rsp+58h+var_38], edx
0x1800105ea  mov     rdx, [rdi+8]
0x1800105ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f3  mov     rcx, [rsp+58h]; this
0x1800105f8  lea     rdx, aFailedToCompre; "Failed to compress buffer"
0x1800105ff  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180010604  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001060b  mov     edx, 0FDh; void *
0x180010610  mov     r9d, eax; char *
0x180010613  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010618  mov     rcx, [rdi]
0x18001061b  xor     edx, edx
0x18001061d  mov     r8, [rbx]
0x180010620  mov     r9d, 2
0x180010626  mov     [rsp+58h+var_20], rdx
0x18001062b  mov     [rdi+20h], rdx
0x18001062f  mov     [rdi+28h], rdx
0x180010633  mov     [rdi+0C00h], edx
0x180010639  mov     rax, [rcx]
0x18001063c  mov     rdx, [rsp+58h+arg_0]
0x180010641  mov     [rsp+58h+var_28], 3
0x180010649  mov     dword ptr [rsp+58h+var_30], edx; char *
0x18001064d  mov     rax, [rax+18h]
0x180010651  mov     [rsp+58h+var_38], 1
0x180010659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001065e  mov     rcx, [rsp+58h]; this
0x180010663  lea     rdx, aFailedToSendCa; "Failed to send caps confirm"
0x18001066a  mov     qword ptr [rsp+58h+var_38], rdx; int
0x18001066f  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010676  mov     edx, 10Ch; void *
0x18001067b  mov     r9d, eax; char *
0x18001067e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010683  mov     rbx, [rsp+58h+arg_8]
0x180010688  add     rsp, 50h
0x18001068c  pop     rdi
0x18001068d  retn
```
