# NgcSymmetricPopKey::EncryptGcm(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001eee0`
- end: `0x18001f03e`
- name: `?EncryptGcm@NgcSymmetricPopKey@@QEAAJPEAEK0K0K0K0K0KPEAPEAEPEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c7c`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x1800137f4`
- `0x180013c98`
- `0x18001e904`
- `0x18001eee0`

## string_xrefs

- `0x18001ef39`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001efda`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::EncryptGcm(
        NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        ULONG a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned __int8 *a12,
        unsigned int a13,
        unsigned __int8 **a14,
        unsigned int *a15)
{
  int v17; // eax
  int v18; // ebx
  unsigned __int8 *v19; // rcx
  int v21; // [rsp+20h] [rbp-71h]
  int v22; // [rsp+20h] [rbp-71h]
  unsigned __int8 *v23; // [rsp+30h] [rbp-61h]
  unsigned __int8 *v24; // [rsp+40h] [rbp-51h]
  unsigned int *v25; // [rsp+58h] [rbp-39h]
  unsigned __int8 *v26; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int8 *v27; // [rsp+68h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int8 **v29; // [rsp+78h] [rbp-19h] BYREF
  unsigned int v30[2]; // [rsp+80h] [rbp-11h] BYREF
  char v31; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+27h]

  hKey = 0;
  v17 = NgcSymmetricPopKey::CreateAesKey(this, (void *)0x1E1, a4, a5, a6, a7, &hKey);
  v18 = v17;
  if ( v17 >= 0 )
  {
    LODWORD(v26) = 0;
    v27 = 0;
    v29 = &v27;
    *(_QWORD *)v30 = 0;
    v31 = 1;
    LODWORD(v24) = a13;
    LODWORD(v23) = a11;
    v18 = NgcUtils::EncryptDataAuthenticated(
            hKey,
            a2,
            a3,
            (unsigned int)a8,
            a9,
            a10,
            v23,
            (unsigned int)a12,
            v24,
            (unsigned int)v30,
            &v26,
            v25);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v29);
    if ( v18 >= 0 )
    {
      v19 = v27;
      v27 = 0;
      *a14 = v19;
      *a15 = (unsigned int)v26;
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v27,
        0);
      v18 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
        (const char *)(unsigned int)v18,
        v22);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v27,
        0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)(unsigned int)v17,
      v21);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001eee0  push    rbp
0x18001eee2  push    rbx
0x18001eee3  push    rsi
0x18001eee4  push    rdi
0x18001eee5  lea     rbp, [rsp-7]
0x18001eeea  sub     rsp, 98h
0x18001eef1  mov     r10, r9
0x18001eef4  mov     edi, r8d
0x18001eef7  mov     rsi, rdx
0x18001eefa  mov     [rbp+1Fh+hKey], 0
0x18001ef02  lea     rax, [rbp+1Fh+hKey]
0x18001ef06  mov     [rsp+0B0h+var_80], rax; void **
0x18001ef0b  mov     eax, [rbp+1Fh+arg_30]
0x18001ef0e  mov     dword ptr [rsp+0B0h+var_88], eax; unsigned int
0x18001ef12  mov     rax, [rbp+1Fh+arg_28]
0x18001ef16  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18001ef1b  mov     r9d, [rbp+1Fh+arg_20]; unsigned int
0x18001ef1f  mov     r8, r10; unsigned __int8 *
0x18001ef22  mov     edx, 1E1h; void *
0x18001ef27  call    ?CreateAesKey@NgcSymmetricPopKey@@IEAAJPEAXPEAEK1KPEAPEAX@Z; NgcSymmetricPopKey::CreateAesKey(void *,uchar *,ulong,uchar *,ulong,void * *)
0x18001ef2c  mov     ebx, eax
0x18001ef2e  test    eax, eax
0x18001ef30  jns     short loc_18001EF4F
0x18001ef32  mov     rcx, [rbp+27h]; this
0x18001ef36  mov     r9d, eax; char *
0x18001ef39  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ef40  mov     edx, 0EFh; void *
0x18001ef45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef4a  jmp     loc_18001F027
0x18001ef4f  mov     dword ptr [rbp+1Fh+var_50], 0
0x18001ef56  mov     [rbp+1Fh+var_48], 0
0x18001ef5e  lea     rax, [rbp+1Fh+var_48]
0x18001ef62  mov     [rbp+1Fh+var_38], rax
0x18001ef66  mov     qword ptr [rbp+1Fh+var_30], 0
0x18001ef6e  mov     [rbp+1Fh+var_28], 1
0x18001ef72  lea     rax, [rbp+1Fh+var_50]
0x18001ef76  mov     [rsp+0B0h+var_60], rax; unsigned __int8 **
0x18001ef7b  lea     rax, [rbp+1Fh+var_30]
0x18001ef7f  mov     qword ptr [rsp+0B0h+var_68], rax; unsigned int
0x18001ef84  mov     eax, dword ptr [rbp+1Fh+arg_60]
0x18001ef8a  mov     dword ptr [rsp+0B0h+var_70], eax; unsigned __int8 *
0x18001ef8e  mov     rax, [rbp+1Fh+arg_58]
0x18001ef95  mov     qword ptr [rsp+0B0h+var_78], rax; unsigned int
0x18001ef9a  mov     eax, dword ptr [rbp+1Fh+arg_50]
0x18001ef9d  mov     dword ptr [rsp+0B0h+var_80], eax; unsigned __int8 *
0x18001efa1  mov     rax, [rbp+1Fh+arg_48]
0x18001efa5  mov     [rsp+0B0h+var_88], rax; PUCHAR
0x18001efaa  mov     eax, [rbp+1Fh+arg_40]
0x18001efad  mov     [rsp+0B0h+var_90], eax; int
0x18001efb1  mov     r9, [rbp+1Fh+arg_38]; unsigned int
0x18001efb5  mov     r8d, edi; cbInput
0x18001efb8  mov     rdx, rsi; pbInput
0x18001efbb  mov     rcx, [rbp+1Fh+hKey]; hKey
0x18001efbf  call    ?EncryptDataAuthenticated@NgcUtils@@YAJPEAXPEAEK1K1K1KPEAPEAEPEAK@Z; NgcUtils::EncryptDataAuthenticated(void *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001efc4  mov     ebx, eax
0x18001efc6  lea     rcx, [rbp+1Fh+var_38]
0x18001efca  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001efcf  test    ebx, ebx
0x18001efd1  jns     short loc_18001EFF8
0x18001efd3  mov     rcx, [rbp+27h]; this
0x18001efd7  mov     r9d, ebx; char *
0x18001efda  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001efe1  mov     edx, 0FFh; void *
0x18001efe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efeb  xor     edx, edx
0x18001efed  lea     rcx, [rbp+1Fh+var_48]
0x18001eff1  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001eff6  jmp     short loc_18001F027
0x18001eff8  mov     rcx, [rbp+1Fh+var_48]
0x18001effc  mov     [rbp+1Fh+var_48], 0
0x18001f004  mov     rax, [rbp+1Fh+arg_68]
0x18001f00b  mov     [rax], rcx
0x18001f00e  mov     rcx, [rbp+1Fh+arg_70]
0x18001f015  mov     eax, dword ptr [rbp+1Fh+var_50]
0x18001f018  mov     [rcx], eax
0x18001f01a  xor     edx, edx
0x18001f01c  lea     rcx, [rbp+1Fh+var_48]
0x18001f020  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001f025  xor     ebx, ebx
0x18001f027  lea     rcx, [rbp+1Fh+hKey]
0x18001f02b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f030  mov     eax, ebx
0x18001f032  add     rsp, 98h
0x18001f039  pop     rdi
0x18001f03a  pop     rsi
0x18001f03b  pop     rbx
0x18001f03c  pop     rbp
0x18001f03d  retn
```
