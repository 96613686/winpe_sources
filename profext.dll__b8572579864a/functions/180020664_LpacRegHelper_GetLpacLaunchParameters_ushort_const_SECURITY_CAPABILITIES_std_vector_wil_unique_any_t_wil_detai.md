# LpacRegHelper::GetLpacLaunchParameters(ushort const *,_SECURITY_CAPABILITIES *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,std::vector<_SID_AND_ATTRIBUTES,std::allocator<_SID_AND_ATTRIBUTES>> &,unsigned __int64 * *,ulong)

- ea: `0x180020664`
- end: `0x180020891`
- name: `?GetLpacLaunchParameters@LpacRegHelper@@SAJPEBGPEAU_SECURITY_CAPABILITIES@@AEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAV?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@4@PEAPEA_KK@Z`
- size: `557`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001de80`

## callees

- `0x180004594`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000f884`
- `0x18001e374`
- `0x18001fed0`
- `0x180020664`
- `0x180020898`
- `0x180020ab0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180020717`
- `ntdll!RtlFreeSid` at `0x180020717`

## string_xrefs

- `0x18002069f`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18002078c`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800207e4`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LpacRegHelper::GetLpacLaunchParameters(
        char *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned __int64 **a5)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned __int64 **v11; // r14
  PSID v12; // rbx
  int LpacSecurityCapabilities; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  void *v16; // rcx
  int LpacMitigationPolicy; // eax
  void *v18; // rax
  unsigned __int64 *v19; // rax
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+20h] [rbp-40h]
  int v23; // [rsp+20h] [rbp-40h]
  DWORD v24; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 *v28; // [rsp+48h] [rbp-18h] BYREF
  __int64 v29; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  void *v31; // [rsp+90h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v9 = 553;
      goto LABEL_3;
    }
    v11 = a5;
    if ( !a5 )
    {
      v9 = 554;
      goto LABEL_3;
    }
    Sid = 0;
    v26 = 0;
    v25 = 0;
    v31 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v25,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v12 = Sid;
    if ( Sid )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
      RtlFreeSid(v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
    }
    Sid = 0;
    LpacSecurityCapabilities = LpacRegHelper::DeriveLpacInfo(a1, &Sid, &v26, 0, &v25, &v31);
    v10 = LpacSecurityCapabilities;
    if ( LpacSecurityCapabilities >= 0 )
    {
      LpacSecurityCapabilities = LpacRegHelper::GetLpacSecurityCapabilities(v14, v26, v25, (__int64)v31, a3, a4);
      v10 = LpacSecurityCapabilities;
      if ( LpacSecurityCapabilities >= 0 )
      {
        v28 = 0;
        v29 = 0;
        wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v28);
        LpacMitigationPolicy = LpacRegHelper::GetLpacMitigationPolicy(v16, v26, v25, v31, &v28, v24);
        v10 = LpacMitigationPolicy;
        if ( LpacMitigationPolicy >= 0 )
        {
          v18 = v31;
          v31 = 0;
          *a2 = v18;
          a2[1] = *a4;
          a2[2] = (unsigned int)((__int64)(a4[1] - *a4) >> 4);
          v19 = v28;
          v28 = 0;
          v29 = 0;
          *v11 = v19;
          wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v28);
          v10 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24A,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
            (const char *)(unsigned int)LpacMitigationPolicy,
            v23);
          wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v28);
        }
        goto LABEL_18;
      }
      v15 = 576;
    }
    else
    {
      v15 = 567;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)LpacSecurityCapabilities,
      v22);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    return v10;
  }
  v9 = 552;
LABEL_3:
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
    (const char *)0x80070057LL,
    v21);
  return v10;
}

```

## disassembly

```asm
0x180020664  mov     [rsp-28h+arg_8], rbx
0x180020669  mov     [rsp-28h+arg_10], rsi
0x18002066e  push    rbp
0x18002066f  push    rdi
0x180020670  push    r12
0x180020672  push    r14
0x180020674  push    r15
0x180020676  mov     rbp, rsp
0x180020679  sub     rsp, 60h
0x18002067d  mov     rsi, r9
0x180020680  mov     r12, r8
0x180020683  mov     rdi, rdx
0x180020686  mov     r15, rcx
0x180020689  test    rcx, rcx
0x18002068c  jnz     short loc_1800206B0
0x18002068e  mov     edx, 228h; void *
0x180020693  mov     ebx, 80070057h
0x180020698  mov     rcx, [rbp+28h]; this
0x18002069c  mov     r9d, ebx; char *
0x18002069f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800206a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206ab  jmp     loc_180020875
0x1800206b0  test    rdi, rdi
0x1800206b3  jnz     short loc_1800206BC
0x1800206b5  mov     edx, 229h
0x1800206ba  jmp     short loc_180020693
0x1800206bc  mov     r14, [rbp+arg_20]
0x1800206c0  test    r14, r14
0x1800206c3  jnz     short loc_1800206CC
0x1800206c5  mov     edx, 22Ah
0x1800206ca  jmp     short loc_180020693
0x1800206cc  mov     [rbp+Sid], 0
0x1800206d4  mov     [rbp+var_28], 0
0x1800206dc  mov     [rbp+var_30], 0
0x1800206e4  mov     [rbp+arg_0], 0
0x1800206ec  xor     edx, edx
0x1800206ee  lea     rcx, [rbp+var_30]
0x1800206f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800206f7  xor     edx, edx
0x1800206f9  lea     rcx, [rbp+var_28]
0x1800206fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180020702  mov     rbx, [rbp+Sid]
0x180020706  test    rbx, rbx
0x180020709  jz      short loc_18002072C
0x18002070b  lea     rcx, [rbp+var_18]; this
0x18002070f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020714  mov     rcx, rbx; Sid
0x180020717  call    cs:__imp_RtlFreeSid
0x18002071e  nop     dword ptr [rax+rax+00h]
0x180020723  lea     rcx, [rbp+var_18]; this
0x180020727  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002072c  mov     [rbp+Sid], 0
0x180020734  lea     rax, [rbp+arg_0]
0x180020738  mov     qword ptr [rsp+60h+var_38], rax; void **
0x18002073d  lea     rax, [rbp+var_30]
0x180020741  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x180020746  xor     r9d, r9d; unsigned __int16 **
0x180020749  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18002074d  lea     rdx, [rbp+Sid]; void **
0x180020751  mov     rcx, r15; char *
0x180020754  call    ?DeriveLpacInfo@LpacRegHelper@@CAJPEBGPEAPEAXPEAPEAG221@Z; LpacRegHelper::DeriveLpacInfo(ushort const *,void * *,ushort * *,ushort * *,ushort * *,void * *)
0x180020759  mov     ebx, eax
0x18002075b  test    eax, eax
0x18002075d  jns     short loc_180020766
0x18002075f  mov     edx, 237h
0x180020764  jmp     short loc_18002078C
0x180020766  mov     qword ptr [rsp+60h+var_38], rsi; DWORD
0x18002076b  mov     [rsp+60h+var_40], r12; int
0x180020770  mov     r9, [rbp+arg_0]
0x180020774  mov     r8, [rbp+var_30]
0x180020778  mov     rdx, [rbp+var_28]
0x18002077c  call    ?GetLpacSecurityCapabilities@LpacRegHelper@@CAJPEAXPEBG10AEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAV?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@3@@Z; LpacRegHelper::GetLpacSecurityCapabilities(void *,ushort const *,ushort const *,void *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &,std::vector<_SID_AND_ATTRIBUTES> &)
0x180020781  mov     ebx, eax
0x180020783  test    eax, eax
0x180020785  jns     short loc_1800207A4
0x180020787  mov     edx, 240h; void *
0x18002078c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020793  mov     r9d, eax; char *
0x180020796  mov     rcx, [rbp+28h]; this
0x18002079a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002079f  jmp     loc_18002084E
0x1800207a4  mov     [rbp+var_18], 0
0x1800207ac  mov     [rbp+var_10], 0
0x1800207b4  lea     rcx, [rbp+var_18]
0x1800207b8  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800207bd  lea     rax, [rbp+var_18]
0x1800207c1  mov     [rsp+60h+var_40], rax; int
0x1800207c6  mov     r9, [rbp+arg_0]; void *
0x1800207ca  mov     r8, [rbp+var_30]; unsigned __int16 *
0x1800207ce  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x1800207d2  call    ?GetLpacMitigationPolicy@LpacRegHelper@@CAJPEAXPEBG10PEAPEA_KK@Z; LpacRegHelper::GetLpacMitigationPolicy(void *,ushort const *,ushort const *,void *,unsigned __int64 * *,ulong)
0x1800207d7  mov     ebx, eax
0x1800207d9  test    eax, eax
0x1800207db  jns     short loc_180020801
0x1800207dd  mov     rcx, [rbp+28h]; this
0x1800207e1  mov     r9d, eax; char *
0x1800207e4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800207eb  mov     edx, 24Ah; void *
0x1800207f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800207f5  nop
0x1800207f6  lea     rcx, [rbp+var_18]
0x1800207fa  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800207ff  jmp     short loc_18002084E
0x180020801  mov     rax, [rbp+arg_0]
0x180020805  mov     [rbp+arg_0], 0
0x18002080d  mov     [rdi], rax
0x180020810  mov     rax, [rsi]
0x180020813  mov     [rdi+8], rax
0x180020817  mov     rax, [rsi+8]
0x18002081b  sub     rax, [rsi]
0x18002081e  sar     rax, 4
0x180020822  mov     [rdi+10h], eax
0x180020825  mov     dword ptr [rdi+14h], 0
0x18002082c  mov     rax, [rbp+var_18]
0x180020830  mov     [rbp+var_18], 0
0x180020838  mov     [rbp+var_10], 0
0x180020840  mov     [r14], rax
0x180020843  lea     rcx, [rbp+var_18]
0x180020847  call    ?reset@?$unique_any_array_ptr@_KU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<unsigned __int64,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18002084c  xor     ebx, ebx
0x18002084e  lea     rcx, [rbp+arg_0]
0x180020852  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020857  nop
0x180020858  lea     rcx, [rbp+var_30]
0x18002085c  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020861  nop
0x180020862  lea     rcx, [rbp+var_28]
0x180020866  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18002086b  nop
0x18002086c  lea     rcx, [rbp+Sid]
0x180020870  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020875  mov     eax, ebx
0x180020877  lea     r11, [rsp+60h+var_s0]
0x18002087c  mov     rbx, [r11+38h]
0x180020880  mov     rsi, [r11+40h]
0x180020884  mov     rsp, r11
0x180020887  pop     r15
0x180020889  pop     r14
0x18002088b  pop     r12
0x18002088d  pop     rdi
0x18002088e  pop     rbp
0x18002088f  retn
```
