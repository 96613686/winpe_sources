# CResource::Delete(void)

- ea: `0x180133e20`
- end: `0x180133fdc`
- name: `?Delete@CResource@@IEAAXXZ`
- size: `444`
- prototype: `void __fastcall(CResource *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180133cf0`
- `0x180134f5c`

## callees

- `0x180050270`
- `0x1800516b0`
- `0x180133e20`
- `0x180133fe4`
- `0x180200468`
- `0x180200488`
- `0x180202804`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180133f5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180133f5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180133eab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180133eab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180133e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180133e6f`

## string_xrefs

- `0x180133fa9`: `onecoreuap\windows\dwm\dwmcore\common\threadcontext.cpp`

## pseudocode

```c
void __fastcall CResource::Delete(CResource *this)
{
  __int64 v1; // rbx
  int v3; // edi
  CComposition *v4; // rcx
  CResource **Value; // rdi
  const char *v6; // r9
  const char *v7; // r9
  CResource *v8; // rcx
  CResource *v9; // rax
  CResource *v10; // rax
  CThreadContext *v11; // rax
  CThreadContext *v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)this + 2));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 56LL))(v1);
  }
  if ( *((_BYTE *)g_pComposition + 6466) || (v3 = *((_DWORD *)g_pComposition + 1426), GetCurrentThreadId() == v3) )
  {
    Value = (CResource **)TlsGetValue(CThreadContext::s_dwTlsIndex);
    if ( !Value )
    {
      v11 = (CThreadContext *)MIDL_user_allocate(0x1C0u);
      if ( !v11 || (v12 = CThreadContext::CThreadContext(v11), (Value = (CResource **)v12) == 0) )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\common\\threadcontext.cpp",
          (const char *)0x8007000ELL,
          v13);
      }
      TlsSetValue(CThreadContext::s_dwTlsIndex, v12);
    }
    if ( *Value )
    {
      if ( *Value == this )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
          v6);
      v9 = Value[2];
      if ( v9 )
        *((_QWORD *)v9 + 8) = this;
      else
        Value[1] = this;
      Value[2] = this;
    }
    else
    {
      *Value = this;
      (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
      while ( 1 )
      {
        v8 = Value[1];
        if ( !v8 )
          break;
        v10 = (CResource *)*((_QWORD *)v8 + 8);
        Value[1] = v10;
        if ( !v10 )
          Value[2] = 0;
        if ( *((_DWORD *)v8 + 2) != -1 )
        {
          Value[3] = v8;
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
            v7);
        }
        (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
      }
      *Value = 0;
    }
  }
  else
  {
    CComposition::AddDelayDeleteResource(v4, this);
  }
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180133e20  mov     [rsp+arg_0], rbx
0x180133e25  mov     [rsp+arg_8], rsi
0x180133e2a  push    rdi
0x180133e2b  sub     rsp, 30h
0x180133e2f  mov     rbx, [rcx+10h]
0x180133e33  mov     rsi, rcx
0x180133e36  test    rbx, rbx
0x180133e39  jz      short loc_180133E59
0x180133e3b  mov     rax, [rbx]
0x180133e3e  mov     rcx, rbx
0x180133e41  mov     rax, [rax+8]
0x180133e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133e4a  mov     rax, [rbx]
0x180133e4d  mov     rcx, rbx
0x180133e50  mov     rax, [rax+38h]
0x180133e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133e59  mov     rdi, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180133e60  cmp     byte ptr [rdi+1942h], 0
0x180133e67  jnz     short loc_180133EA5
0x180133e69  mov     edi, [rdi+1648h]
0x180133e6f  call    cs:__imp_GetCurrentThreadId
0x180133e75  cmp     eax, edi
0x180133e77  jz      short loc_180133EA5
0x180133e79  mov     rdx, rsi; struct CResource *
0x180133e7c  call    ?AddDelayDeleteResource@CComposition@@QEAAXPEAVCResource@@@Z; CComposition::AddDelayDeleteResource(CResource *)
0x180133e81  test    rbx, rbx
0x180133e84  jz      short loc_180133E95
0x180133e86  mov     rax, [rbx]
0x180133e89  mov     rcx, rbx
0x180133e8c  mov     rax, [rax+10h]
0x180133e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133e95  mov     rbx, [rsp+38h+arg_0]
0x180133e9a  mov     rsi, [rsp+38h+arg_8]
0x180133e9f  add     rsp, 30h
0x180133ea3  pop     rdi
0x180133ea4  retn
0x180133ea5  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180133eab  call    cs:__imp_TlsGetValue
0x180133eb1  mov     rdi, rax
0x180133eb4  test    rax, rax
0x180133eb7  jz      short loc_180133F36
0x180133eb9  mov     rax, [rdi]
0x180133ebc  test    rax, rax
0x180133ebf  jnz     short loc_180133EE8
0x180133ec1  mov     [rdi], rsi
0x180133ec4  mov     edx, 1
0x180133ec9  mov     rax, [rsi]
0x180133ecc  mov     rcx, rsi
0x180133ecf  mov     rax, [rax+20h]
0x180133ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133ed8  xor     esi, esi
0x180133eda  mov     rcx, [rdi+8]
0x180133ede  test    rcx, rcx
0x180133ee1  jnz     short loc_180133F00
0x180133ee3  mov     [rdi], rsi
0x180133ee6  jmp     short loc_180133E81
0x180133ee8  cmp     rax, rsi
0x180133eeb  jz      short loc_180133F69
0x180133eed  mov     rax, [rdi+10h]
0x180133ef1  test    rax, rax
0x180133ef4  jz      short loc_180133F30
0x180133ef6  mov     [rax+40h], rsi
0x180133efa  mov     [rdi+10h], rsi
0x180133efe  jmp     short loc_180133E81
0x180133f00  mov     rax, [rcx+40h]
0x180133f04  mov     [rdi+8], rax
0x180133f08  test    rax, rax
0x180133f0b  jnz     short loc_180133F11
0x180133f0d  mov     [rdi+10h], rsi
0x180133f11  mov     eax, [rcx+8]
0x180133f14  cmp     eax, 0FFFFFFFFh
0x180133f17  jnz     loc_180133FC1
0x180133f1d  mov     rax, [rcx]
0x180133f20  mov     edx, 1
0x180133f25  mov     rax, [rax+20h]
0x180133f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133f2e  jmp     short loc_180133EDA
0x180133f30  mov     [rdi+8], rsi
0x180133f34  jmp     short loc_180133EFA
0x180133f36  mov     ecx, 1C0h; size
0x180133f3b  call    MIDL_user_allocate
0x180133f40  test    rax, rax
0x180133f43  jz      short loc_180133F80
0x180133f45  mov     rcx, rax; this
0x180133f48  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x180133f4d  mov     rdi, rax
0x180133f50  test    rax, rax
0x180133f53  jz      short loc_180133F80
0x180133f55  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180133f5b  mov     rdx, rax; lpTlsValue
0x180133f5e  call    cs:__imp_TlsSetValue
0x180133f64  jmp     loc_180133EB9
0x180133f69  mov     rcx, [rsp+38h]; this
0x180133f6e  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x180133f75  mov     edx, 2Ah ; '*'; void *
0x180133f7a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180133f80  xor     esi, esi
0x180133f82  mov     r9d, 8007000Eh; int
0x180133f88  mov     [rsp+38h+var_10], rsi; void *
0x180133f8d  xor     r8d, r8d; unsigned int
0x180133f90  xor     edx, edx; int *
0x180133f92  mov     [rsp+38h+var_18], 28h ; '('; int
0x180133f9a  mov     ecx, 14h; unsigned int
0x180133f9f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180133fa4  mov     rcx, [rsp+38h]; this
0x180133fa9  lea     r8, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\dwmcore\\comm"...
0x180133fb0  mov     r9d, 8007000Eh; char *
0x180133fb6  mov     edx, 44h ; 'D'; void *
0x180133fbb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180133fc1  mov     [rdi+18h], rcx
0x180133fc5  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x180133fcc  mov     rcx, [rsp+38h]; this
0x180133fd1  mov     edx, 56h ; 'V'; void *
0x180133fd6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
