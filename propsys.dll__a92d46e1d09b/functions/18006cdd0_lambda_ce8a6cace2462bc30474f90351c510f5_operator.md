# _lambda_ce8a6cace2462bc30474f90351c510f5_::operator()

- ea: `0x18006cdd0`
- end: `0x18006d19c`
- name: `_lambda_ce8a6cace2462bc30474f90351c510f5_::operator()`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006cbe0`

## callees

- `0x180004148`
- `0x180025dd4`
- `0x18002cfd0`
- `0x180062d94`
- `0x18006a0b8`
- `0x18006cdd0`
- `0x18006ed20`
- `0x18007ce3c`
- `0x18009522c`
- `0x180095cd0`

## import_xrefs

- `icu!udat_close` at `0x18006d013`
- `icu!udat_close` at `0x18006d10a`
- `icu!udat_close` at `0x18006d150`
- `icu!udat_close` at `0x18006d013`
- `icu!udat_close` at `0x18006d10a`
- `icu!udat_close` at `0x18006d150`
- `icu!u_errorName` at `0x18006ce47`
- `icu!u_errorName` at `0x18006ce99`
- `icu!u_errorName` at `0x18006cfdf`
- `icu!u_errorName` at `0x18006d057`
- `icu!u_errorName` at `0x18006ce47`
- `icu!u_errorName` at `0x18006ce99`
- `icu!u_errorName` at `0x18006cfdf`
- `icu!u_errorName` at `0x18006d057`
- `icu!udatpg_open` at `0x18006ce30`
- `icu!udatpg_open` at `0x18006ce30`
- `icu!udatpg_close` at `0x18006cf48`
- `icu!udatpg_close` at `0x18006d03a`
- `icu!udatpg_close` at `0x18006d177`
- `icu!udatpg_close` at `0x18006cf48`
- `icu!udatpg_close` at `0x18006d03a`
- `icu!udatpg_close` at `0x18006d177`
- `icu!udat_open` at `0x18006cfc8`
- `icu!udat_open` at `0x18006cfc8`

## pseudocode

```c
__int64 __fastcall lambda_ce8a6cace2462bc30474f90351c510f5_::operator()(int **a1)
{
  int v2; // ecx
  const wchar_t *v3; // rax
  __int64 v4; // rax
  int v5; // edi
  const char *v6; // rax
  const char *v7; // rax
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // edi
  const char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall **v31)(); // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 **v32; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall ***v33)(); // [rsp+E0h] [rbp-20h]
  const wchar_t *v34; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-10h] BYREF
  int v36; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v37; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v2 = **a1;
  if ( v2 == 4 )
  {
    v3 = L"EEEE";
  }
  else
  {
    v3 = L"MMMMd";
    if ( v2 != 5 )
      v3 = L"MMMMdyyyy";
  }
  v34 = v3;
  v36 = 0;
  v4 = udatpg_open(0, &v36);
  v5 = v36;
  v35 = v4;
  v36 = 0;
  if ( v5 > 0 )
  {
    v6 = (const char *)u_errorName((unsigned int)v5);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)0x80070057LL,
      (int)"%hs",
      v6);
LABEL_23:
    v18 = v35;
    v35 = 0;
    if ( v18 )
      udatpg_close();
    return 2147942487LL;
  }
  if ( (unsigned int)(v5 + 128) > 1 )
  {
    v7 = (const char *)u_errorName((unsigned int)v5);
    LOBYTE(v24) = v5 != 0;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)0x80070057LL,
      v24,
      (bool)"%hs",
      v7);
  }
  v26 = 0;
  v28[0] = (unsigned __int16 *)&v35;
  v28[1] = (unsigned __int16 *)&v34;
  v31 = off_1800B48A0;
  v32 = v28;
  v33 = &v31;
  v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         &v26,
         v30);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v30);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)(unsigned int)v8,
      v24);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
    v10 = v35;
    v35 = 0;
    if ( v10 )
      udatpg_close();
    return (unsigned int)v8;
  }
  LOBYTE(v9) = 0;
  v27 = 0;
  v12 = wil::GetStringFromICUFunction__lambda_a54b16ce839d703ecb63ab56c80bd81f__wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t_______(
          &v27,
          v9);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)(unsigned int)v12,
      v24);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
    goto LABEL_11;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v26 + 2 * v13) );
  v25 = -1;
  v14 = udat_open(4294967294LL, 4294967294LL, 0, v27);
  v15 = v36;
  v37 = v14;
  v36 = 0;
  if ( v15 > 0 )
  {
    v16 = (const char *)u_errorName((unsigned int)v15);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)0x80070057LL,
      (int)"%hs",
      v16);
    v17 = v37;
    v37 = 0;
    if ( v17 )
      udat_close();
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
    goto LABEL_23;
  }
  if ( (unsigned int)(v15 + 128) > 1 )
  {
    v19 = (const char *)u_errorName((unsigned int)v15);
    LOBYTE(v25) = v15 != 0;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)0x80070057LL,
      v25,
      (bool)"%hs",
      v19);
  }
  v28[0] = 0;
  v29[0] = &v37;
  v29[1] = a1[1];
  v31 = off_1800B48F0;
  v32 = (unsigned __int16 **)v29;
  v33 = &v31;
  v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         v28,
         v30);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v30);
  if ( v8 < 0 )
  {
    v20 = 297;
    goto LABEL_30;
  }
  v8 = StringCchCopyW(*(unsigned __int16 **)a1[2], (unsigned int)*a1[3], v28[0]);
  if ( v8 < 0 )
  {
    v20 = 299;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\propsys\\time.cpp",
      (const char *)(unsigned int)v8,
      v25);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v28);
    v21 = v37;
    v37 = 0;
    if ( v21 )
      udat_close();
    goto LABEL_16;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v28);
  v22 = v37;
  v37 = 0;
  if ( v22 )
    udat_close();
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
  v23 = v35;
  v35 = 0;
  if ( v23 )
    udatpg_close();
  return 0;
}

```

## disassembly

```asm
0x18006cdd0  push    rbp
0x18006cdd2  push    rbx
0x18006cdd3  push    rdi
0x18006cdd4  push    r12
0x18006cdd6  push    r14
0x18006cdd8  push    r15
0x18006cdda  lea     rbp, [rsp-18h]
0x18006cddf  sub     rsp, 118h
0x18006cde6  mov     rax, cs:__security_cookie
0x18006cded  xor     rax, rsp
0x18006cdf0  mov     [rbp+40h+var_38], rax
0x18006cdf4  mov     rax, [rcx]
0x18006cdf7  mov     r14, rcx
0x18006cdfa  mov     ecx, [rax]
0x18006cdfc  cmp     ecx, 4
0x18006cdff  jnz     short loc_18006CE0A
0x18006ce01  lea     rax, aEeee; "EEEE"
0x18006ce08  jmp     short loc_18006CE1F
0x18006ce0a  cmp     ecx, 5
0x18006ce0d  lea     rdx, aMmmmdyyyy; "MMMMdyyyy"
0x18006ce14  lea     rax, aMmmmd; "MMMMd"
0x18006ce1b  cmovnz  rax, rdx
0x18006ce1f  xor     r12d, r12d
0x18006ce22  mov     [rbp+40h+var_58], rax
0x18006ce26  lea     rdx, [rbp+40h+var_48]
0x18006ce2a  mov     [rbp+40h+var_48], r12d
0x18006ce2e  xor     ecx, ecx
0x18006ce30  call    cs:__imp_udatpg_open
0x18006ce36  mov     edi, [rbp+40h+var_48]
0x18006ce39  mov     [rbp+40h+var_50], rax
0x18006ce3d  mov     [rbp+40h+var_48], r12d
0x18006ce41  test    edi, edi
0x18006ce43  jle     short loc_18006CE7E
0x18006ce45  mov     ecx, edi
0x18006ce47  call    cs:__imp_u_errorName
0x18006ce4d  mov     rcx, [rbp+48h]; this
0x18006ce51  lea     r15, aHs; "%hs"
0x18006ce58  mov     [rsp+140h+var_118], rax; char *
0x18006ce5d  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\propsys\\time.cpp"
0x18006ce64  mov     r9d, 80070057h; char *
0x18006ce6a  mov     qword ptr [rsp+140h+var_120], r15; int
0x18006ce6f  mov     edx, 10Ah; void *
0x18006ce74  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006ce79  jmp     loc_18006D02D
0x18006ce7e  lea     eax, [rdi+80h]
0x18006ce84  lea     r15, aHs; "%hs"
0x18006ce8b  lea     rbx, aOnecoreuapShel_8; "onecoreuap\\shell\\propsys\\time.cpp"
0x18006ce92  cmp     eax, 1
0x18006ce95  jbe     short loc_18006CEC9
0x18006ce97  mov     ecx, edi
0x18006ce99  call    cs:__imp_u_errorName
0x18006ce9f  mov     rcx, [rbp+48h]; this
0x18006cea3  test    edi, edi
0x18006cea5  mov     [rsp+140h+var_110], rax; char *
0x18006ceaa  mov     r9d, 80070057h; char *
0x18006ceb0  setnz   dl
0x18006ceb3  mov     [rsp+140h+var_118], r15; bool
0x18006ceb8  mov     byte ptr [rsp+140h+var_120], dl; int
0x18006cebc  mov     r8, rbx; unsigned int
0x18006cebf  mov     edx, 10Ah; void *
0x18006cec4  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18006cec9  lea     rax, [rbp+40h+var_50]
0x18006cecd  mov     [rsp+140h+var_100], r12
0x18006ced2  mov     [rsp+140h+var_F0], rax
0x18006ced7  lea     rdx, [rsp+140h+var_D0]
0x18006cedc  lea     rax, [rbp+40h+var_58]
0x18006cee0  mov     [rsp+140h+var_E8], rax
0x18006cee5  lea     rcx, [rsp+140h+var_100]
0x18006ceea  lea     rax, off_1800B48A0
0x18006cef1  mov     [rsp+140h+var_C8], rax
0x18006cef6  lea     rax, [rsp+140h+var_F0]
0x18006cefb  mov     [rbp+40h+var_C0], rax
0x18006ceff  lea     rax, [rsp+140h+var_C8]
0x18006cf04  mov     [rbp+40h+var_60], rax
0x18006cf08  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18006cf0d  lea     rcx, [rsp+140h+var_D0]
0x18006cf12  mov     edi, eax
0x18006cf14  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18006cf19  test    edi, edi
0x18006cf1b  jns     short loc_18006CF55
0x18006cf1d  mov     rcx, [rbp+48h]; this
0x18006cf21  mov     r9d, edi; char *
0x18006cf24  mov     r8, rbx; unsigned int
0x18006cf27  mov     edx, 112h; void *
0x18006cf2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf31  lea     rcx, [rsp+140h+var_100]
0x18006cf36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006cf3b  mov     rcx, [rbp+40h+var_50]
0x18006cf3f  mov     [rbp+40h+var_50], r12
0x18006cf43  test    rcx, rcx
0x18006cf46  jz      short loc_18006CF4E
0x18006cf48  call    cs:__imp_udatpg_close
0x18006cf4e  mov     eax, edi
0x18006cf50  jmp     loc_18006D17F
0x18006cf55  mov     dl, r12b
0x18006cf58  mov     [rsp+140h+var_F8], r12
0x18006cf5d  lea     rcx, [rsp+140h+var_F8]
0x18006cf62  call    wil__GetStringFromICUFunction__lambda_a54b16ce839d703ecb63ab56c80bd81f__wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd__integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std__nullptr_t_______
0x18006cf67  mov     edi, eax
0x18006cf69  test    eax, eax
0x18006cf6b  jns     short loc_18006CF8D
0x18006cf6d  mov     rcx, [rbp+48h]; this
0x18006cf71  mov     r9d, eax; char *
0x18006cf74  mov     r8, rbx; unsigned int
0x18006cf77  mov     edx, 11Ah; void *
0x18006cf7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf81  lea     rcx, [rsp+140h+var_F8]
0x18006cf86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006cf8b  jmp     short loc_18006CF31
0x18006cf8d  mov     rax, [rsp+140h+var_100]
0x18006cf92  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006cf96  mov     rcx, r8
0x18006cf99  inc     rcx
0x18006cf9c  cmp     [rax+rcx*2], r12w
0x18006cfa1  jnz     short loc_18006CF99
0x18006cfa3  mov     r9, [rsp+140h+var_F8]
0x18006cfa8  lea     rdx, [rbp+40h+var_48]
0x18006cfac  mov     [rsp+140h+var_108], rdx
0x18006cfb1  mov     dword ptr [rsp+140h+var_110], ecx
0x18006cfb5  mov     [rsp+140h+var_118], rax
0x18006cfba  mov     [rsp+140h+var_120], r8d
0x18006cfbf  xor     r8d, r8d
0x18006cfc2  lea     ecx, [r8-2]
0x18006cfc6  mov     edx, ecx
0x18006cfc8  call    cs:__imp_udat_open
0x18006cfce  mov     edi, [rbp+40h+var_48]
0x18006cfd1  mov     [rbp+40h+var_40], rax
0x18006cfd5  mov     [rbp+40h+var_48], r12d
0x18006cfd9  test    edi, edi
0x18006cfdb  jle     short loc_18006D04A
0x18006cfdd  mov     ecx, edi
0x18006cfdf  call    cs:__imp_u_errorName
0x18006cfe5  mov     rcx, [rbp+48h]; this
0x18006cfe9  mov     r9d, 80070057h; char *
0x18006cfef  mov     [rsp+140h+var_118], rax; char *
0x18006cff4  mov     r8, rbx; unsigned int
0x18006cff7  mov     edx, 121h; void *
0x18006cffc  mov     qword ptr [rsp+140h+var_120], r15; int
0x18006d001  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006d006  mov     rcx, [rbp+40h+var_40]
0x18006d00a  mov     [rbp+40h+var_40], r12
0x18006d00e  test    rcx, rcx
0x18006d011  jz      short loc_18006D019
0x18006d013  call    cs:__imp_udat_close
0x18006d019  lea     rcx, [rsp+140h+var_F8]
0x18006d01e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d023  lea     rcx, [rsp+140h+var_100]
0x18006d028  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d02d  mov     rcx, [rbp+40h+var_50]
0x18006d031  mov     [rbp+40h+var_50], r12
0x18006d035  test    rcx, rcx
0x18006d038  jz      short loc_18006D040
0x18006d03a  call    cs:__imp_udatpg_close
0x18006d040  mov     eax, 80070057h
0x18006d045  jmp     loc_18006D17F
0x18006d04a  lea     eax, [rdi+80h]
0x18006d050  cmp     eax, 1
0x18006d053  jbe     short loc_18006D087
0x18006d055  mov     ecx, edi
0x18006d057  call    cs:__imp_u_errorName
0x18006d05d  mov     rcx, [rbp+48h]; this
0x18006d061  test    edi, edi
0x18006d063  mov     [rsp+140h+var_110], rax; char *
0x18006d068  mov     r9d, 80070057h; char *
0x18006d06e  setnz   dl
0x18006d071  mov     [rsp+140h+var_118], r15; bool
0x18006d076  mov     byte ptr [rsp+140h+var_120], dl; int
0x18006d07a  mov     r8, rbx; unsigned int
0x18006d07d  mov     edx, 121h; void *
0x18006d082  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18006d087  lea     rax, [rbp+40h+var_40]
0x18006d08b  mov     [rsp+140h+var_F0], r12
0x18006d090  mov     [rsp+140h+var_E0], rax
0x18006d095  lea     rdx, [rsp+140h+var_D0]
0x18006d09a  mov     rax, [r14+8]
0x18006d09e  lea     rcx, [rsp+140h+var_F0]
0x18006d0a3  mov     [rsp+140h+var_D8], rax
0x18006d0a8  lea     rax, off_1800B48F0
0x18006d0af  mov     [rsp+140h+var_C8], rax
0x18006d0b4  lea     rax, [rsp+140h+var_E0]
0x18006d0b9  mov     [rbp+40h+var_C0], rax
0x18006d0bd  lea     rax, [rsp+140h+var_C8]
0x18006d0c2  mov     [rbp+40h+var_60], rax
0x18006d0c6  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18006d0cb  lea     rcx, [rsp+140h+var_D0]
0x18006d0d0  mov     edi, eax
0x18006d0d2  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18006d0d7  test    edi, edi
0x18006d0d9  jns     short loc_18006D115
0x18006d0db  mov     edx, 129h; void *
0x18006d0e0  mov     rcx, [rbp+48h]; this
0x18006d0e4  mov     r8, rbx; unsigned int
0x18006d0e7  mov     r9d, edi; char *
0x18006d0ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d0ef  lea     rcx, [rsp+140h+var_F0]
0x18006d0f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d0f9  mov     rcx, [rbp+40h+var_40]
0x18006d0fd  mov     [rbp+40h+var_40], r12
0x18006d101  test    rcx, rcx
0x18006d104  jz      loc_18006CF81
0x18006d10a  call    cs:__imp_udat_close
0x18006d110  jmp     loc_18006CF81
0x18006d115  mov     rax, [r14+18h]
0x18006d119  mov     rcx, [r14+10h]
0x18006d11d  mov     r8, [rsp+140h+var_F0]; unsigned __int16 *
0x18006d122  mov     edx, [rax]; unsigned __int64
0x18006d124  mov     rcx, [rcx]; unsigned __int16 *
0x18006d127  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006d12c  mov     edi, eax
0x18006d12e  test    eax, eax
0x18006d130  jns     short loc_18006D139
0x18006d132  mov     edx, 12Bh
0x18006d137  jmp     short loc_18006D0E0
0x18006d139  lea     rcx, [rsp+140h+var_F0]
0x18006d13e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d143  mov     rcx, [rbp+40h+var_40]
0x18006d147  mov     [rbp+40h+var_40], r12
0x18006d14b  test    rcx, rcx
0x18006d14e  jz      short loc_18006D156
0x18006d150  call    cs:__imp_udat_close
0x18006d156  lea     rcx, [rsp+140h+var_F8]
0x18006d15b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d160  lea     rcx, [rsp+140h+var_100]
0x18006d165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d16a  mov     rcx, [rbp+40h+var_50]
0x18006d16e  mov     [rbp+40h+var_50], r12
0x18006d172  test    rcx, rcx
0x18006d175  jz      short loc_18006D17D
0x18006d177  call    cs:__imp_udatpg_close
0x18006d17d  xor     eax, eax
0x18006d17f  mov     rcx, [rbp+40h+var_38]
0x18006d183  xor     rcx, rsp; StackCookie
0x18006d186  call    __security_check_cookie
0x18006d18b  add     rsp, 118h
0x18006d192  pop     r15
0x18006d194  pop     r14
0x18006d196  pop     r12
0x18006d198  pop     rdi
0x18006d199  pop     rbx
0x18006d19a  pop     rbp
0x18006d19b  retn
```
