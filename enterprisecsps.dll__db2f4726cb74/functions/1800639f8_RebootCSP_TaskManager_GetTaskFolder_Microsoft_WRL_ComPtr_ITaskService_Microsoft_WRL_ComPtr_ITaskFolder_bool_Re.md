# RebootCSP::TaskManager::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskService> &,Microsoft::WRL::ComPtr<ITaskFolder> &,bool,RecurrenceFrequency)

- ea: `0x1800639f8`
- end: `0x180063d8d`
- name: `?GetTaskFolder@TaskManager@RebootCSP@@AEAAJAEAV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskFolder@@@45@_NW4RecurrenceFrequency@@@Z`
- size: `917`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180063d94`
- `0x180064670`

## callees

- `0x1800091b0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18002031c`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800639f8`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180063a96`
- `OLEAUT32!__imp_SysFreeString` at `0x180063b47`
- `OLEAUT32!__imp_SysFreeString` at `0x180063c27`
- `OLEAUT32!__imp_SysFreeString` at `0x180063d1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180063a96`
- `OLEAUT32!__imp_SysFreeString` at `0x180063b47`
- `OLEAUT32!__imp_SysFreeString` at `0x180063c27`
- `OLEAUT32!__imp_SysFreeString` at `0x180063d1b`
- `DMCmnUtils!DeleteRebootCSPTaskInRegistry` at `0x180063d58`
- `DMCmnUtils!DeleteRebootCSPTaskInRegistry` at `0x180063d58`

## string_xrefs

- `0x180063c6e`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RebootCSP::TaskManager::GetTaskFolder(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        char a4,
        unsigned int a5)
{
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD *, __int64 *); // r14
  const unsigned __int16 *v11; // rax
  _QWORD *v12; // rdx
  int v13; // r14d
  BSTR *v14; // rbx
  BSTR v15; // rcx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD *, void **); // rdi
  _QWORD *v18; // rdx
  int v19; // edi
  BSTR *v20; // rbx
  BSTR v21; // rcx
  __int64 v22; // rdx
  void *v23; // rbx
  __int64 (__fastcall *v24)(void *, __int64, __int128 *, __int64 *); // rdi
  const unsigned __int16 *v25; // rax
  _variant_t *v26; // rax
  __int128 v27; // xmm6
  __int64 v28; // xmm7_8
  const unsigned __int16 *v29; // rax
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  BSTR *v32; // rbx
  BSTR v33; // rcx
  __int64 v35; // rbx
  void (__fastcall *v36)(__int64, __int64, _QWORD); // rdi
  const unsigned __int16 *v37; // rax
  _bstr_t *v38; // rax
  __int64 v39; // rdx
  BSTR *v40; // rbx
  BSTR v41; // rcx
  __int64 v42; // rax
  int v43; // [rsp+28h] [rbp-51h]
  __int128 v44; // [rsp+38h] [rbp-41h] BYREF
  __int64 v45; // [rsp+48h] [rbp-31h]
  _BYTE v46[24]; // [rsp+58h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  void *Block; // [rsp+E0h] [rbp+67h] BYREF
  void *v49; // [rsp+E8h] [rbp+6Fh] BYREF

  v9 = *a2;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)*a2 + 56LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a3);
  v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 128);
  v12 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v11);
  if ( v12 )
    v12 = (_QWORD *)*v12;
  v13 = v10(v9, v12, a3);
  v14 = (BSTR *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v14 )
  {
    if ( *v14 )
    {
      SysFreeString(*v14);
      *v14 = 0;
    }
    v15 = v14[1];
    if ( v15 )
    {
      operator delete(v15);
      v14[1] = 0;
    }
    operator delete(v14);
  }
  if ( (unsigned int)(v13 + 2147024894) <= 1 )
  {
    Block = 0;
    v16 = *a2;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD *, void **))(*(_QWORD *)*a2 + 56LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&Block);
    v18 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v49, L"\\");
    if ( v18 )
      v18 = (_QWORD *)*v18;
    v19 = v17(v16, v18, &Block);
    v20 = (BSTR *)v49;
    if ( v49 && _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 && v20 )
    {
      if ( *v20 )
      {
        SysFreeString(*v20);
        *v20 = 0;
      }
      v21 = v20[1];
      if ( v21 )
      {
        operator delete(v21);
        v20[1] = 0;
      }
      operator delete(v20);
    }
    if ( v19 < 0 )
    {
      v22 = 286;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v19,
        v43);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&Block);
      return (unsigned int)v19;
    }
    v23 = Block;
    v24 = *(__int64 (__fastcall **)(void *, __int64, __int128 *, __int64 *))(*(_QWORD *)Block + 88LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a3);
    v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 160);
    v26 = _variant_t::_variant_t((_variant_t *)v46, v25);
    v27 = *(_OWORD *)v26;
    v28 = *((_QWORD *)v26 + 2);
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 128);
    v30 = _bstr_t::_bstr_t((_bstr_t *)&v49, v29);
    if ( *(_QWORD *)v30 )
      v31 = **(_QWORD **)v30;
    else
      v31 = 0;
    v44 = v27;
    v45 = v28;
    v19 = v24(v23, v31, &v44, a3);
    v32 = (BSTR *)v49;
    if ( v49 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 && v32 )
      {
        if ( *v32 )
        {
          SysFreeString(*v32);
          *v32 = 0;
        }
        v33 = v32[1];
        if ( v33 )
        {
          operator delete(v33);
          v32[1] = 0;
        }
        operator delete(v32);
      }
      v49 = 0;
    }
    _variant_t::~_variant_t((_variant_t *)v46);
    if ( v19 < 0 )
    {
      v22 = 288;
      goto LABEL_38;
    }
    *(_BYTE *)(a1 + 224) = 1;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&Block);
  }
  if ( v13 >= 0 && a4 )
  {
    v35 = *a3;
    v36 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)*a3 + 120LL);
    v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 192);
    v38 = _bstr_t::_bstr_t((_bstr_t *)&Block, v37);
    if ( *(_QWORD *)v38 )
      v39 = **(_QWORD **)v38;
    else
      v39 = 0;
    v36(v35, v39, 0);
    v40 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v40 )
    {
      if ( *v40 )
      {
        SysFreeString(*v40);
        *v40 = 0;
      }
      v41 = v40[1];
      if ( v41 )
      {
        operator delete(v41);
        v40[1] = 0;
      }
      operator delete(v40);
    }
    v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 64);
    DeleteRebootCSPTaskInRegistry(v42, a5);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800639f8  mov     rax, rsp
0x1800639fb  mov     [rax+20h], rbx
0x1800639ff  push    rbp
0x180063a00  push    rsi
0x180063a01  push    rdi
0x180063a02  push    r12
0x180063a04  push    r13
0x180063a06  push    r14
0x180063a08  push    r15
0x180063a0a  lea     rbp, [rax-57h]
0x180063a0e  sub     rsp, 90h
0x180063a15  movaps  xmmword ptr [rax-48h], xmm6
0x180063a19  movaps  xmmword ptr [rax-58h], xmm7
0x180063a1d  mov     r13b, r9b
0x180063a20  mov     r15, r8
0x180063a23  mov     rdi, rdx
0x180063a26  mov     rsi, rcx
0x180063a29  mov     rbx, [rdx]
0x180063a2c  mov     rax, [rbx]
0x180063a2f  mov     r14, [rax+38h]
0x180063a33  mov     rcx, r8
0x180063a36  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063a3b  lea     r12, [rsi+80h]
0x180063a42  mov     rcx, r12
0x180063a45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063a4a  mov     rdx, rax; unsigned __int16 *
0x180063a4d  lea     rcx, [rbp+4Fh+Block]; this
0x180063a51  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063a56  nop
0x180063a57  mov     rdx, [rax]
0x180063a5a  test    rdx, rdx
0x180063a5d  jz      short loc_180063A62
0x180063a5f  mov     rdx, [rdx]
0x180063a62  mov     r8, r15
0x180063a65  mov     rcx, rbx
0x180063a68  mov     rax, r14
0x180063a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a70  mov     r14d, eax
0x180063a73  mov     rbx, [rbp+4Fh+Block]
0x180063a77  test    rbx, rbx
0x180063a7a  jz      short loc_180063ACC
0x180063a7c  or      ecx, 0FFFFFFFFh
0x180063a7f  lock xadd [rbx+10h], ecx
0x180063a84  cmp     ecx, 1
0x180063a87  jnz     short loc_180063ACC
0x180063a89  test    rbx, rbx
0x180063a8c  jz      short loc_180063ACC
0x180063a8e  mov     rcx, [rbx]; bstrString
0x180063a91  test    rcx, rcx
0x180063a94  jz      short loc_180063AA9
0x180063a96  call    cs:__imp_SysFreeString
0x180063a9d  nop     dword ptr [rax+rax+00h]
0x180063aa2  mov     qword ptr [rbx], 0
0x180063aa9  mov     rcx, [rbx+8]; Block
0x180063aad  test    rcx, rcx
0x180063ab0  jz      short loc_180063ABF
0x180063ab2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063ab7  mov     qword ptr [rbx+8], 0
0x180063abf  mov     edx, 18h
0x180063ac4  mov     rcx, rbx; Block
0x180063ac7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063acc  lea     eax, [r14+7FF8FFFEh]
0x180063ad3  cmp     eax, 1
0x180063ad6  ja      loc_180063CA1
0x180063adc  mov     [rbp+4Fh+Block], 0
0x180063ae4  mov     rbx, [rdi]
0x180063ae7  mov     rax, [rbx]
0x180063aea  mov     rdi, [rax+38h]
0x180063aee  lea     rcx, [rbp+4Fh+Block]
0x180063af2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063af7  lea     rdx, StringValue; "\\"
0x180063afe  lea     rcx, [rbp+4Fh+arg_10]; this
0x180063b02  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063b07  nop
0x180063b08  mov     rdx, [rax]
0x180063b0b  test    rdx, rdx
0x180063b0e  jz      short loc_180063B13
0x180063b10  mov     rdx, [rdx]
0x180063b13  lea     r8, [rbp+4Fh+Block]
0x180063b17  mov     rcx, rbx
0x180063b1a  mov     rax, rdi
0x180063b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b22  mov     edi, eax
0x180063b24  mov     rbx, [rbp+4Fh+arg_10]
0x180063b28  test    rbx, rbx
0x180063b2b  jz      short loc_180063B7D
0x180063b2d  or      ecx, 0FFFFFFFFh
0x180063b30  lock xadd [rbx+10h], ecx
0x180063b35  cmp     ecx, 1
0x180063b38  jnz     short loc_180063B7D
0x180063b3a  test    rbx, rbx
0x180063b3d  jz      short loc_180063B7D
0x180063b3f  mov     rcx, [rbx]; bstrString
0x180063b42  test    rcx, rcx
0x180063b45  jz      short loc_180063B5A
0x180063b47  call    cs:__imp_SysFreeString
0x180063b4e  nop     dword ptr [rax+rax+00h]
0x180063b53  mov     qword ptr [rbx], 0
0x180063b5a  mov     rcx, [rbx+8]; Block
0x180063b5e  test    rcx, rcx
0x180063b61  jz      short loc_180063B70
0x180063b63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063b68  mov     qword ptr [rbx+8], 0
0x180063b70  mov     edx, 18h
0x180063b75  mov     rcx, rbx; Block
0x180063b78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063b7d  test    edi, edi
0x180063b7f  jns     short loc_180063B8B
0x180063b81  mov     edx, 11Eh
0x180063b86  jmp     loc_180063C6B
0x180063b8b  mov     rbx, [rbp+4Fh+Block]
0x180063b8f  mov     rax, [rbx]
0x180063b92  mov     rdi, [rax+58h]
0x180063b96  mov     rcx, r15
0x180063b99  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063b9e  lea     rcx, [rsi+0A0h]
0x180063ba5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063baa  mov     rdx, rax; unsigned __int16 *
0x180063bad  lea     rcx, [rbp+4Fh+var_70]; this
0x180063bb1  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180063bb6  nop
0x180063bb7  movups  xmm6, xmmword ptr [rax]
0x180063bba  movsd   xmm7, qword ptr [rax+10h]
0x180063bbf  mov     rcx, r12
0x180063bc2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063bc7  mov     rdx, rax; unsigned __int16 *
0x180063bca  lea     rcx, [rbp+4Fh+arg_10]; this
0x180063bce  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063bd3  nop
0x180063bd4  mov     rdx, [rax]
0x180063bd7  xor     r12d, r12d
0x180063bda  test    rdx, rdx
0x180063bdd  jz      short loc_180063BE4
0x180063bdf  mov     rdx, [rdx]
0x180063be2  jmp     short loc_180063BE7
0x180063be4  mov     rdx, r12
0x180063be7  movaps  [rbp+4Fh+var_90], xmm6
0x180063beb  movsd   [rbp+4Fh+var_80], xmm7
0x180063bf0  mov     r9, r15
0x180063bf3  lea     r8, [rbp+4Fh+var_90]
0x180063bf7  mov     rcx, rbx
0x180063bfa  mov     rax, rdi
0x180063bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c02  mov     edi, eax
0x180063c04  mov     rbx, [rbp+4Fh+arg_10]
0x180063c08  test    rbx, rbx
0x180063c0b  jz      short loc_180063C59
0x180063c0d  or      ecx, 0FFFFFFFFh
0x180063c10  lock xadd [rbx+10h], ecx
0x180063c15  cmp     ecx, 1
0x180063c18  jnz     short loc_180063C55
0x180063c1a  test    rbx, rbx
0x180063c1d  jz      short loc_180063C55
0x180063c1f  mov     rcx, [rbx]; bstrString
0x180063c22  test    rcx, rcx
0x180063c25  jz      short loc_180063C36
0x180063c27  call    cs:__imp_SysFreeString
0x180063c2e  nop     dword ptr [rax+rax+00h]
0x180063c33  mov     [rbx], r12
0x180063c36  mov     rcx, [rbx+8]; Block
0x180063c3a  test    rcx, rcx
0x180063c3d  jz      short loc_180063C48
0x180063c3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063c44  mov     [rbx+8], r12
0x180063c48  mov     edx, 18h
0x180063c4d  mov     rcx, rbx; Block
0x180063c50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063c55  mov     [rbp+4Fh+arg_10], r12
0x180063c59  lea     rcx, [rbp+4Fh+var_70]; this
0x180063c5d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063c62  test    edi, edi
0x180063c64  jns     short loc_180063C8F
0x180063c66  mov     edx, 120h; void *
0x180063c6b  mov     r9d, edi; char *
0x180063c6e  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180063c75  mov     rcx, [rbp+57h]; this
0x180063c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063c7e  nop
0x180063c7f  lea     rcx, [rbp+4Fh+Block]
0x180063c83  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063c88  mov     eax, edi
0x180063c8a  jmp     loc_180063D67
0x180063c8f  mov     byte ptr [rsi+0E0h], 1
0x180063c96  lea     rcx, [rbp+4Fh+Block]
0x180063c9a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063c9f  jmp     short loc_180063CA4
0x180063ca1  xor     r12d, r12d
0x180063ca4  test    r14d, r14d
0x180063ca7  js      loc_180063D64
0x180063cad  test    r13b, r13b
0x180063cb0  jz      loc_180063D64
0x180063cb6  mov     rbx, [r15]
0x180063cb9  mov     rax, [rbx]
0x180063cbc  mov     rdi, [rax+78h]
0x180063cc0  lea     rcx, [rsi+0C0h]
0x180063cc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063ccc  mov     rdx, rax; unsigned __int16 *
0x180063ccf  lea     rcx, [rbp+4Fh+Block]; this
0x180063cd3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063cd8  nop
0x180063cd9  mov     rdx, [rax]
0x180063cdc  test    rdx, rdx
0x180063cdf  jz      short loc_180063CE6
0x180063ce1  mov     rdx, [rdx]
0x180063ce4  jmp     short loc_180063CE9
0x180063ce6  mov     rdx, r12
0x180063ce9  xor     r8d, r8d
0x180063cec  mov     rcx, rbx
0x180063cef  mov     rax, rdi
0x180063cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cf7  nop
0x180063cf8  mov     rbx, [rbp+4Fh+Block]
0x180063cfc  test    rbx, rbx
0x180063cff  jz      short loc_180063D49
0x180063d01  or      eax, 0FFFFFFFFh
0x180063d04  lock xadd [rbx+10h], eax
0x180063d09  cmp     eax, 1
0x180063d0c  jnz     short loc_180063D49
0x180063d0e  test    rbx, rbx
0x180063d11  jz      short loc_180063D49
0x180063d13  mov     rcx, [rbx]; bstrString
0x180063d16  test    rcx, rcx
0x180063d19  jz      short loc_180063D2A
0x180063d1b  call    cs:__imp_SysFreeString
0x180063d22  nop     dword ptr [rax+rax+00h]
0x180063d27  mov     [rbx], r12
0x180063d2a  mov     rcx, [rbx+8]; Block
0x180063d2e  test    rcx, rcx
0x180063d31  jz      short loc_180063D3C
0x180063d33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063d38  mov     [rbx+8], r12
0x180063d3c  mov     edx, 18h
0x180063d41  mov     rcx, rbx; Block
0x180063d44  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063d49  lea     rcx, [rsi+40h]
0x180063d4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063d52  mov     rcx, rax
0x180063d55  mov     edx, [rbp+4Fh+arg_20]
0x180063d58  call    cs:__imp_?DeleteRebootCSPTaskInRegistry@@YAXPEBGW4RecurrenceFrequency@@@Z; DeleteRebootCSPTaskInRegistry(ushort const *,RecurrenceFrequency)
0x180063d5f  nop     dword ptr [rax+rax+00h]
0x180063d64  mov     eax, r14d
0x180063d67  lea     r11, [rsp+0C0h+var_30]
0x180063d6f  mov     rbx, [r11+58h]
0x180063d73  movaps  xmm6, xmmword ptr [r11-10h]
0x180063d78  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180063d7d  mov     rsp, r11
0x180063d80  pop     r15
0x180063d82  pop     r14
0x180063d84  pop     r13
0x180063d86  pop     r12
0x180063d88  pop     rdi
0x180063d89  pop     rsi
0x180063d8a  pop     rbp
0x180063d8b  retn
```
