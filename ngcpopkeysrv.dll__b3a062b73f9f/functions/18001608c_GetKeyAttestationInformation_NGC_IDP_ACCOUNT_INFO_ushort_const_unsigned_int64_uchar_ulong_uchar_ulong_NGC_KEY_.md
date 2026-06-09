# GetKeyAttestationInformation(_NGC_IDP_ACCOUNT_INFO *,ushort const *,unsigned __int64,uchar * *,ulong *,uchar * *,ulong *,_NGC_KEY_STATUS *)

- ea: `0x18001608c`
- end: `0x180016321`
- name: `?GetKeyAttestationInformation@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_KPEAPEAEPEAK34PEAW4_NGC_KEY_STATUS@@@Z`
- size: `661`
- prototype: `int(struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, unsigned __int64, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, enum _NGC_KEY_STATUS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012430`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180011e48`
- `0x1800140bc`
- `0x1800141e4`
- `0x180015608`
- `0x180015bf0`
- `0x18001608c`
- `0x18001cf48`

## string_xrefs

- `0x18001614b`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800161d5`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x18001626e`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetKeyAttestationInformation(
        NgcUtils **a1,
        NgcUtils *a2,
        NgcUtils *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        enum _NGC_KEY_STATUS *a8)
{
  int v10; // ebx
  enum _NGC_KEY_STATUS *v11; // r12
  int Aik; // ebx
  __int64 v13; // r8
  unsigned int v15; // r14d
  unsigned int v16; // ecx
  int NCryptBinaryBlob; // r13d
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // rax
  unsigned int *v20; // [rsp+20h] [rbp-58h]
  int v21; // [rsp+20h] [rbp-58h]
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 *v23; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v24; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int8 **v25; // [rsp+58h] [rbp-20h] BYREF
  _BCryptBufferDesc v26; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v10 = 3;
  v11 = a8;
  *(_DWORD *)a8 = 3;
  if ( !a4 && !a6 )
  {
    LODWORD(a8) = 0;
    if ( (int)NgcGetPregenAikStatus((__int64)&a8) >= 0 )
      v10 = ConvertRetryTypeToKeyStatus((unsigned int)a8);
    *(_DWORD *)v11 = v10;
    return 0;
  }
  LODWORD(a8) = 0;
  hObject = 0;
  Aik = GetAik(1u, a1, a2, 0, &hObject, (__int64)&a8, 0);
  if ( Aik < 0 )
  {
    *(_DWORD *)v11 = ConvertRetryTypeToKeyStatus((unsigned int)a8);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)Aik,
      (int)v20);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    return (unsigned int)Aik;
  }
  v15 = 0;
  LODWORD(a8) = 0;
  v23 = 0;
  if ( a3 && a4 && a5 )
  {
    v25 = &v23;
    *(_QWORD *)&v26.ulVersion = 0;
    LOBYTE(v26.pBuffers) = 1;
    Aik = NgcUtils::GetAttestationStatement(a3, hObject, v13, &v26, (unsigned __int8 **)&a8);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v25);
    if ( Aik < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)Aik,
        (int)v20);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v23,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      return (unsigned int)Aik;
    }
    v15 = (unsigned int)a8;
  }
  v16 = 0;
  LODWORD(a8) = 0;
  v24 = 0;
  if ( a6 && a7 )
  {
    v25 = &v24;
    *(_QWORD *)&v26.ulVersion = 0;
    LOBYTE(v26.pBuffers) = 1;
    NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(
                         hObject,
                         L"SmartCardKeyCertificate",
                         (const unsigned __int16 *)&v26,
                         (unsigned __int8 **)&a8,
                         v20);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v25);
    if ( NCryptBinaryBlob < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)NCryptBinaryBlob,
        v21);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v24,
        0);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v23,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      return (unsigned int)NCryptBinaryBlob;
    }
    v16 = (unsigned int)a8;
  }
  if ( a4 )
  {
    v18 = v23;
    v23 = 0;
    *a4 = v18;
  }
  if ( a5 )
    *a5 = v15;
  if ( a6 )
  {
    v19 = v24;
    v24 = 0;
    *a6 = v19;
  }
  if ( a7 )
    *a7 = v16;
  *(_DWORD *)v11 = 7;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v24, 0);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v23, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return 0;
}

```

## disassembly

```asm
0x18001608c  push    rbp
0x18001608e  push    rbx
0x18001608f  push    rsi
0x180016090  push    rdi
0x180016091  push    r12
0x180016093  push    r13
0x180016095  push    r14
0x180016097  push    r15
0x180016099  mov     rbp, rsp
0x18001609c  sub     rsp, 78h
0x1800160a0  mov     rsi, r9
0x1800160a3  mov     r13, r8
0x1800160a6  mov     ebx, 3
0x1800160ab  mov     r12, [rbp+arg_38]
0x1800160b2  mov     [r12], ebx
0x1800160b6  mov     rdi, [rbp+arg_28]
0x1800160ba  xor     r14d, r14d
0x1800160bd  test    r9, r9
0x1800160c0  jnz     short loc_1800160F4
0x1800160c2  test    rdi, rdi
0x1800160c5  jnz     short loc_1800160F4
0x1800160c7  mov     dword ptr [rbp+arg_38], r14d
0x1800160ce  lea     rcx, [rbp+arg_38]
0x1800160d5  call    NgcGetPregenAikStatus
0x1800160da  test    eax, eax
0x1800160dc  js      short loc_1800160EB
0x1800160de  mov     ecx, dword ptr [rbp+arg_38]
0x1800160e4  call    ?ConvertRetryTypeToKeyStatus@@YA?AW4_NGC_KEY_STATUS@@W4DelayRetryAction@@@Z; ConvertRetryTypeToKeyStatus(DelayRetryAction)
0x1800160e9  mov     ebx, eax
0x1800160eb  mov     [r12], ebx
0x1800160ef  jmp     loc_18001630E
0x1800160f4  mov     [rbp+hObject], r14
0x1800160f8  mov     dword ptr [rbp+arg_38], r14d
0x1800160ff  mov     [rbp+hObject], r14
0x180016103  mov     [rsp+78h+var_48], r14
0x180016108  lea     rax, [rbp+arg_38]
0x18001610f  mov     [rsp+78h+var_50], rax; unsigned int *
0x180016114  lea     rax, [rbp+hObject]
0x180016118  mov     [rsp+78h+var_58], rax; int
0x18001611d  xor     r9d, r9d
0x180016120  mov     r8, rdx
0x180016123  mov     rdx, rcx
0x180016126  lea     ecx, [r9+1]
0x18001612a  call    ?GetAik@@YAJW4PregenKeyType@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_NPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z; GetAik(PregenKeyType,_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,unsigned __int64 *,DelayRetryAction *,ushort * *)
0x18001612f  mov     ebx, eax
0x180016131  test    eax, eax
0x180016133  jns     short loc_18001616E
0x180016135  mov     ecx, dword ptr [rbp+arg_38]
0x18001613b  call    ?ConvertRetryTypeToKeyStatus@@YA?AW4_NGC_KEY_STATUS@@W4DelayRetryAction@@@Z; ConvertRetryTypeToKeyStatus(DelayRetryAction)
0x180016140  mov     [r12], eax
0x180016144  mov     rcx, [rbp+40h]; this
0x180016148  mov     r9d, ebx; char *
0x18001614b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016152  mov     edx, 0FFh; void *
0x180016157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001615c  nop
0x18001615d  lea     rcx, [rbp+hObject]
0x180016161  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016166  nop
0x180016167  mov     eax, ebx
0x180016169  jmp     loc_180016310
0x18001616e  xor     r14d, r14d
0x180016171  mov     dword ptr [rbp+arg_38], r14d
0x180016178  mov     [rbp+var_30], r14
0x18001617c  mov     r15, [rbp+arg_20]
0x180016180  test    r13, r13
0x180016183  jz      loc_180016209
0x180016189  test    rsi, rsi
0x18001618c  jz      short loc_180016209
0x18001618e  test    r15, r15
0x180016191  jz      short loc_180016209
0x180016193  lea     rax, [rbp+var_30]
0x180016197  mov     [rbp+var_20], rax
0x18001619b  mov     qword ptr [rbp+var_18.ulVersion], r14
0x18001619f  mov     byte ptr [rbp+var_18.pBuffers], 1
0x1800161a3  lea     rax, [rbp+arg_38]
0x1800161aa  mov     [rsp+78h+var_58], rax; int
0x1800161af  lea     r9, [rbp+var_18]; struct _BCryptBufferDesc *
0x1800161b3  mov     rdx, [rbp+hObject]; unsigned __int64
0x1800161b7  mov     rcx, r13; this
0x1800161ba  call    ?GetAttestationStatement@NgcUtils@@YAJ_K0PEAU_BCryptBufferDesc@@PEAPEAEPEAK@Z; NgcUtils::GetAttestationStatement(unsigned __int64,unsigned __int64,_BCryptBufferDesc *,uchar * *,ulong *)
0x1800161bf  mov     ebx, eax
0x1800161c1  lea     rcx, [rbp+var_20]
0x1800161c5  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800161ca  test    ebx, ebx
0x1800161cc  jns     short loc_180016202
0x1800161ce  mov     rcx, [rbp+40h]; this
0x1800161d2  mov     r9d, ebx; char *
0x1800161d5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800161dc  mov     edx, 10Fh; void *
0x1800161e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161e6  nop
0x1800161e7  xor     edx, edx
0x1800161e9  lea     rcx, [rbp+var_30]
0x1800161ed  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800161f2  nop
0x1800161f3  lea     rcx, [rbp+hObject]
0x1800161f7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800161fc  nop
0x1800161fd  jmp     loc_180016167
0x180016202  mov     r14d, dword ptr [rbp+arg_38]
0x180016209  xor     ecx, ecx
0x18001620b  mov     dword ptr [rbp+arg_38], ecx
0x180016211  mov     [rbp+var_28], rcx
0x180016215  mov     rbx, [rbp+arg_30]
0x180016219  test    rdi, rdi
0x18001621c  jz      loc_1800162AD
0x180016222  test    rbx, rbx
0x180016225  jz      loc_1800162AD
0x18001622b  lea     rax, [rbp+var_28]
0x18001622f  mov     [rbp+var_20], rax
0x180016233  mov     qword ptr [rbp+var_18.ulVersion], rcx
0x180016237  mov     byte ptr [rbp+var_18.pBuffers], 1
0x18001623b  lea     r9, [rbp+arg_38]; unsigned __int8 **
0x180016242  lea     r8, [rbp+var_18]; unsigned __int16 *
0x180016246  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18001624d  mov     rcx, [rbp+hObject]; hObject
0x180016251  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x180016256  mov     r13d, eax
0x180016259  lea     rcx, [rbp+var_20]
0x18001625d  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016262  test    r13d, r13d
0x180016265  jns     short loc_1800162A7
0x180016267  mov     rcx, [rbp+40h]; this
0x18001626b  mov     r9d, r13d; char *
0x18001626e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016275  mov     edx, 11Bh; void *
0x18001627a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001627f  nop
0x180016280  xor     edx, edx
0x180016282  lea     rcx, [rbp+var_28]
0x180016286  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001628b  nop
0x18001628c  xor     edx, edx
0x18001628e  lea     rcx, [rbp+var_30]
0x180016292  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016297  nop
0x180016298  lea     rcx, [rbp+hObject]
0x18001629c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800162a1  nop
0x1800162a2  mov     eax, r13d
0x1800162a5  jmp     short loc_180016310
0x1800162a7  mov     ecx, dword ptr [rbp+arg_38]
0x1800162ad  test    rsi, rsi
0x1800162b0  jz      short loc_1800162C1
0x1800162b2  mov     rax, [rbp+var_30]
0x1800162b6  mov     [rbp+var_30], 0
0x1800162be  mov     [rsi], rax
0x1800162c1  test    r15, r15
0x1800162c4  jz      short loc_1800162C9
0x1800162c6  mov     [r15], r14d
0x1800162c9  test    rdi, rdi
0x1800162cc  jz      short loc_1800162DD
0x1800162ce  mov     rax, [rbp+var_28]
0x1800162d2  mov     [rbp+var_28], 0
0x1800162da  mov     [rdi], rax
0x1800162dd  test    rbx, rbx
0x1800162e0  jz      short loc_1800162E4
0x1800162e2  mov     [rbx], ecx
0x1800162e4  mov     dword ptr [r12], 7
0x1800162ec  xor     edx, edx
0x1800162ee  lea     rcx, [rbp+var_28]
0x1800162f2  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800162f7  nop
0x1800162f8  xor     edx, edx
0x1800162fa  lea     rcx, [rbp+var_30]
0x1800162fe  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016303  nop
0x180016304  lea     rcx, [rbp+hObject]
0x180016308  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001630d  nop
0x18001630e  xor     eax, eax
0x180016310  add     rsp, 78h
0x180016314  pop     r15
0x180016316  pop     r14
0x180016318  pop     r13
0x18001631a  pop     r12
0x18001631c  pop     rdi
0x18001631d  pop     rsi
0x18001631e  pop     rbx
0x18001631f  pop     rbp
0x180016320  retn
```
