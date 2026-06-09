# SoftwareKeyTransKey::DecryptKeyBlob(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180018a60`
- end: `0x180018bca`
- name: `?DecryptKeyBlob@SoftwareKeyTransKey@@MEAAJPEAEKPEAPEAEPEAK@Z`
- size: `362`
- prototype: `int(SoftwareKeyTransKey *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x18000dad8`
- `0x18001070c`
- `0x180010784`
- `0x1800146fc`
- `0x180018728`
- `0x180018a60`

## string_xrefs

- `0x180018b66`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SoftwareKeyTransKey::DecryptKeyBlob(
        SoftwareKeyTransKey *this,
        unsigned __int8 *a2,
        DWORD a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  _DWORD *v9; // r9
  int v10; // ebx
  unsigned __int8 *v11; // rax
  DWORD v13; // [rsp+20h] [rbp-81h]
  int v14; // [rsp+20h] [rbp-81h]
  unsigned __int8 *v15; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int8 *v16; // [rsp+48h] [rbp-59h] BYREF
  int *v17; // [rsp+50h] [rbp-51h] BYREF
  __int16 v18; // [rsp+58h] [rbp-49h]
  unsigned __int8 **v19; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v20[2]; // [rsp+68h] [rbp-39h] BYREF
  char v21; // [rsp+70h] [rbp-31h]
  const wchar_t *pPaddingInfo; // [rsp+78h] [rbp-29h] BYREF
  __int128 v23; // [rsp+80h] [rbp-21h]
  int v24; // [rsp+90h] [rbp-11h] BYREF
  char v25; // [rsp+94h] [rbp-Dh]
  char v26[16]; // [rsp+98h] [rbp-9h] BYREF
  _DWORD v27[4]; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v24 = 0;
  v25 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v24);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v25 && (v27[0] || v27[1] || v27[2] || v27[3]) )
      v9 = v27;
    else
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      byte_18002EC79,
      v26,
      v9);
  }
  v17 = &v24;
  v18 = 256;
  v23 = 0;
  pPaddingInfo = L"SHA1";
  LODWORD(v15) = 0;
  v16 = 0;
  v19 = &v16;
  *(_QWORD *)v20 = 0;
  v21 = 1;
  v10 = NgcUtils::PersistedDecryptData(*((_QWORD *)this + 1), a2, a3, &pPaddingInfo, v13, (PBYTE *)v20, &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&v19);
  if ( v10 >= 0 )
  {
    v11 = v16;
    v16 = 0;
    *a4 = v11;
    *a5 = (unsigned int)v15;
    v10 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
      (const char *)(unsigned int)v10,
      v14);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v16, 0);
  wil::details::ScopeExitFnGuard__lambda_6975b671a3a74a86685aa7996e7d27a7___::operator()(&v17);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018a60  push    rbp
0x180018a62  push    rbx
0x180018a63  push    rsi
0x180018a64  push    rdi
0x180018a65  push    r12
0x180018a67  push    r14
0x180018a69  push    r15
0x180018a6b  lea     rbp, [rsp-1Fh]
0x180018a70  sub     rsp, 0C0h
0x180018a77  mov     rax, cs:__security_cookie
0x180018a7e  xor     rax, rsp
0x180018a81  mov     [rbp+4Fh+var_38], rax
0x180018a85  mov     rdi, r9
0x180018a88  mov     r15d, r8d
0x180018a8b  mov     r14, rdx
0x180018a8e  mov     rbx, rcx
0x180018a91  mov     rsi, [rbp+4Fh+arg_20]
0x180018a95  xor     r12d, r12d
0x180018a98  mov     [rbp+4Fh+var_60], r12d
0x180018a9c  mov     [rbp+4Fh+var_5C], r12b
0x180018aa0  lea     rcx, [rbp+4Fh+var_60]
0x180018aa4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180018aa9  mov     eax, cs:dword_180037000
0x180018aaf  cmp     eax, 5
0x180018ab2  jbe     short loc_180018AF2
0x180018ab4  cmp     [rbp+4Fh+var_5C], r12b
0x180018ab8  jz      short loc_180018AD8
0x180018aba  cmp     [rbp+4Fh+var_48], r12d
0x180018abe  jnz     short loc_180018AD2
0x180018ac0  cmp     [rbp+4Fh+var_44], r12d
0x180018ac4  jnz     short loc_180018AD2
0x180018ac6  cmp     [rbp+4Fh+var_40], r12d
0x180018aca  jnz     short loc_180018AD2
0x180018acc  cmp     [rbp+4Fh+var_3C], r12d
0x180018ad0  jz      short loc_180018AD8
0x180018ad2  lea     r9, [rbp+4Fh+var_48]
0x180018ad6  jmp     short loc_180018ADB
0x180018ad8  mov     r9, r12
0x180018adb  lea     r8, [rbp+4Fh+var_58]
0x180018adf  lea     rdx, byte_18002EC79
0x180018ae6  lea     rcx, dword_180037000
0x180018aed  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018af2  lea     rax, [rbp+4Fh+var_60]
0x180018af6  mov     [rbp+4Fh+var_A0], rax
0x180018afa  mov     [rbp+4Fh+var_98], 100h
0x180018b00  xorps   xmm0, xmm0
0x180018b03  movdqu  [rbp+4Fh+var_70], xmm0
0x180018b08  lea     rax, aSha1; "SHA1"
0x180018b0f  mov     [rbp+4Fh+pPaddingInfo], rax
0x180018b13  mov     dword ptr [rbp+4Fh+var_B0], r12d
0x180018b17  mov     [rbp+4Fh+var_A8], r12
0x180018b1b  lea     rax, [rbp+4Fh+var_A8]
0x180018b1f  mov     [rbp+4Fh+var_90], rax
0x180018b23  mov     qword ptr [rbp+4Fh+var_88], r12
0x180018b27  mov     [rbp+4Fh+var_80], 1
0x180018b2b  lea     rax, [rbp+4Fh+var_B0]
0x180018b2f  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 **
0x180018b34  lea     rax, [rbp+4Fh+var_88]
0x180018b38  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned int
0x180018b3d  lea     r9, [rbp+4Fh+pPaddingInfo]; pPaddingInfo
0x180018b41  mov     r8d, r15d; cbInput
0x180018b44  mov     rdx, r14; pbInput
0x180018b47  mov     rcx, [rbx+8]; hKey
0x180018b4b  call    ?PersistedDecryptData@NgcUtils@@YAJ_KPEAEKPEAXKPEAPEAEPEAK@Z; NgcUtils::PersistedDecryptData(unsigned __int64,uchar *,ulong,void *,ulong,uchar * *,ulong *)
0x180018b50  mov     ebx, eax
0x180018b52  lea     rcx, [rbp+4Fh+var_90]
0x180018b56  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180018b5b  test    ebx, ebx
0x180018b5d  jns     short loc_180018B79
0x180018b5f  mov     rcx, [rbp+57h]; this
0x180018b63  mov     r9d, ebx; char *
0x180018b66  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018b6d  mov     edx, 7Eh ; '~'; void *
0x180018b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b77  jmp     short loc_180018B8C
0x180018b79  mov     rax, [rbp+4Fh+var_A8]
0x180018b7d  mov     [rbp+4Fh+var_A8], r12
0x180018b81  mov     [rdi], rax
0x180018b84  mov     eax, dword ptr [rbp+4Fh+var_B0]
0x180018b87  mov     [rsi], eax
0x180018b89  mov     ebx, r12d
0x180018b8c  xor     edx, edx
0x180018b8e  lea     rcx, [rbp+4Fh+var_A8]
0x180018b92  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180018b97  lea     rcx, [rbp+4Fh+var_A0]
0x180018b9b  call    wil__details__ScopeExitFnGuard__lambda_6975b671a3a74a86685aa7996e7d27a7_____operator__
0x180018ba0  nop
0x180018ba1  lea     rcx, [rbp+4Fh+var_60]
0x180018ba5  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180018baa  mov     eax, ebx
0x180018bac  mov     rcx, [rbp+4Fh+var_38]
0x180018bb0  xor     rcx, rsp; StackCookie
0x180018bb3  call    __security_check_cookie
0x180018bb8  add     rsp, 0C0h
0x180018bbf  pop     r15
0x180018bc1  pop     r14
0x180018bc3  pop     r12
0x180018bc5  pop     rdi
0x180018bc6  pop     rsi
0x180018bc7  pop     rbx
0x180018bc8  pop     rbp
0x180018bc9  retn
```
