# OpenSymmetricPopKeyTransportKey(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool)

- ea: `0x180012858`
- end: `0x180012a01`
- name: `?OpenSymmetricPopKeyTransportKey@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_N@Z`
- size: `425`
- prototype: `__int64 __fastcall(struct NgcKeyTransportKey *, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, unsigned int, ULONG SecurityDescriptorSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800122c8`

## callees

- `0x18000b0dc`
- `0x18000b0fc`
- `0x180011de4`
- `0x180012858`
- `0x180018eec`
- `0x1800193d4`
- `0x180019424`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800128ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800128ce`

## string_xrefs

- `0x1800128e7`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x1800129a4`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x1800129eb`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x180012968`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180012986`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OpenSymmetricPopKeyTransportKey(
        struct NgcKeyTransportKey *a1,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        ULONG SecurityDescriptorSize)
{
  int v9; // eax
  unsigned int LastError; // ebx
  BOOL v11; // ebx
  const char *v12; // r9
  HLOCAL v13; // rcx
  int v15; // edi
  int v16; // eax
  HLOCAL v17; // rcx
  unsigned int v18; // [rsp+20h] [rbp-58h]
  unsigned int v19; // [rsp+20h] [rbp-58h]
  unsigned int v20; // [rsp+20h] [rbp-58h]
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES v22; // [rsp+38h] [rbp-40h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-20h] BYREF
  char v25; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v9 = NgcKeyTransportKey::OpenKey(a1, a2, a3);
  LastError = v9;
  if ( (_BYTE)SecurityDescriptorSize && (v9 == -2146893807 || v9 == -2146893802) )
  {
    SecurityDescriptorSize = 0;
    hMem = 0;
    p_hMem = &hMem;
    SecurityDescriptor = 0;
    v25 = 1;
    v11 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)",
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( !v11 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7A,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
                    v12);
      goto LABEL_6;
    }
    *(_QWORD *)&v22.nLength = 24;
    *(_QWORD *)&v22.bInheritHandle = 0;
    v22.lpSecurityDescriptor = hMem;
    v15 = NgcKeyTransportKey::CreateKeyAndAddNewKeyMapping(a1, a2, a3, &v22, a4);
    if ( v15 == -2147024816 )
    {
      v16 = NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(a1, a2, a3);
      LastError = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
          (const char *)(unsigned int)v16,
          v19);
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
          (const char *)LastError,
          v20);
LABEL_6:
        v13 = hMem;
        hMem = 0;
        if ( v13 )
          LocalFree(v13);
        return LastError;
      }
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v15,
        v19);
      LastError = v15;
      goto LABEL_15;
    }
    if ( v15 < 0 )
      goto LABEL_13;
    v17 = hMem;
    hMem = 0;
    if ( v17 )
      LocalFree(v17);
  }
  else if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
      (const char *)(unsigned int)v9,
      v18);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x180012858  push    rbp
0x18001285a  push    rbx
0x18001285b  push    rsi
0x18001285c  push    rdi
0x18001285d  push    r14
0x18001285f  push    r15
0x180012861  mov     rbp, rsp
0x180012864  sub     rsp, 78h
0x180012868  mov     edi, r9d
0x18001286b  mov     rsi, r8
0x18001286e  mov     r14, rdx
0x180012871  mov     r15, rcx
0x180012874  call    ?OpenKey@NgcKeyTransportKey@@QEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z; NgcKeyTransportKey::OpenKey(_NGC_IDP_ACCOUNT_INFO *,ushort const *)
0x180012879  mov     ebx, eax
0x18001287b  cmp     byte ptr [rbp+SecurityDescriptorSize], 0
0x18001287f  jz      loc_1800129E0
0x180012885  cmp     eax, 80090011h
0x18001288a  jz      short loc_180012897
0x18001288c  cmp     eax, 80090016h
0x180012891  jnz     loc_1800129E0
0x180012897  mov     [rbp+SecurityDescriptorSize], 0
0x18001289e  mov     [rbp+hMem], 0
0x1800128a6  lea     rax, [rbp+hMem]
0x1800128aa  mov     [rbp+var_28], rax
0x1800128ae  mov     [rbp+SecurityDescriptor], 0
0x1800128b6  mov     [rbp+var_18], 1
0x1800128ba  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800128be  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800128c2  mov     edx, 1; StringSDRevision
0x1800128c7  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)"
0x1800128ce  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800128d4  mov     ebx, eax
0x1800128d6  lea     rcx, [rbp+var_28]
0x1800128da  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800128df  test    ebx, ebx
0x1800128e1  jnz     short loc_180012916
0x1800128e3  mov     rcx, [rbp+30h]; this
0x1800128e7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800128ee  lea     edx, [rbx+7Ah]; void *
0x1800128f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800128f6  mov     ebx, eax
0x1800128f8  mov     rcx, [rbp+hMem]; hMem
0x1800128fc  mov     [rbp+hMem], 0
0x180012904  test    rcx, rcx
0x180012907  jz      short loc_18001290F
0x180012909  call    cs:__imp_LocalFree
0x18001290f  mov     eax, ebx
0x180012911  jmp     loc_1800129D3
0x180012916  mov     qword ptr [rbp+var_40.nLength], 18h
0x18001291e  mov     qword ptr [rbp+var_40.bInheritHandle], 0
0x180012926  mov     rax, [rbp+hMem]
0x18001292a  mov     [rbp+var_40.lpSecurityDescriptor], rax
0x18001292e  mov     [rsp+78h+var_58], edi; int
0x180012932  lea     r9, [rbp+var_40]; struct _SECURITY_ATTRIBUTES *
0x180012936  mov     r8, rsi; unsigned __int16 *
0x180012939  mov     rdx, r14; struct _NGC_IDP_ACCOUNT_INFO *
0x18001293c  mov     rcx, r15; this
0x18001293f  call    ?CreateKeyAndAddNewKeyMapping@NgcKeyTransportKey@@AEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAU_SECURITY_ATTRIBUTES@@K@Z; NgcKeyTransportKey::CreateKeyAndAddNewKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,_SECURITY_ATTRIBUTES *,ulong)
0x180012944  mov     edi, eax
0x180012946  cmp     eax, 80070050h
0x18001294b  jnz     short loc_18001297B
0x18001294d  mov     r8, rsi; unsigned __int16 *
0x180012950  mov     rdx, r14; struct _NGC_IDP_ACCOUNT_INFO *
0x180012953  mov     rcx, r15; this
0x180012956  call    ?OpenKeyBasedOnKeyDatabase@NgcKeyTransportKey@@AEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z; NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(_NGC_IDP_ACCOUNT_INFO *,ushort const *)
0x18001295b  mov     ebx, eax
0x18001295d  test    eax, eax
0x18001295f  jns     short loc_18001297F
0x180012961  mov     rcx, [rbp+30h]; this
0x180012965  mov     r9d, eax; char *
0x180012968  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001296f  mov     edx, 0FFh; void *
0x180012974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012979  jmp     short loc_18001299D
0x18001297b  test    edi, edi
0x18001297d  jns     short loc_1800129BA
0x18001297f  mov     rcx, [rbp+30h]; this
0x180012983  mov     r9d, edi; char *
0x180012986  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001298d  mov     edx, 102h; void *
0x180012992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012997  test    edi, edi
0x180012999  jns     short loc_1800129BA
0x18001299b  mov     ebx, edi
0x18001299d  mov     rcx, [rbp+30h]; this
0x1800129a1  mov     r9d, ebx; char *
0x1800129a4  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800129ab  mov     edx, 84h; void *
0x1800129b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129b5  jmp     loc_1800128F8
0x1800129ba  mov     rcx, [rbp+hMem]; hMem
0x1800129be  mov     [rbp+hMem], 0
0x1800129c6  test    rcx, rcx
0x1800129c9  jz      short loc_1800129D1
0x1800129cb  call    cs:__imp_LocalFree
0x1800129d1  xor     eax, eax
0x1800129d3  add     rsp, 78h
0x1800129d7  pop     r15
0x1800129d9  pop     r14
0x1800129db  pop     rdi
0x1800129dc  pop     rsi
0x1800129dd  pop     rbx
0x1800129de  pop     rbp
0x1800129df  retn
0x1800129e0  test    ebx, ebx
0x1800129e2  jns     short loc_1800129D1
0x1800129e4  mov     rcx, [rbp+30h]; this
0x1800129e8  mov     r9d, ebx; char *
0x1800129eb  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800129f2  mov     edx, 88h; void *
0x1800129f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129fc  jmp     loc_18001290F
```
