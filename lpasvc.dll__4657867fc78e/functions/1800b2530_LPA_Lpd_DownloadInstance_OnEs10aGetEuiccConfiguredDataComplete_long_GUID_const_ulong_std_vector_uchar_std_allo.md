# LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete(long,_GUID const &,ulong,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<std::vector<uchar,std::allocator<uchar>>,std::allocator<std::vector<uchar,std::allocator<uchar>>>> const &)

- ea: `0x1800b2530`
- end: `0x1800b2d1d`
- name: `?OnEs10aGetEuiccConfiguredDataComplete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@KAEBV?$vector@EV?$allocator@E@std@@@std@@11AEBV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@6@@Z`
- size: `2029`
- prototype: `__int64 __usercall@<rax>(LPA::Lpd::DownloadInstance *this@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180005898`
- `0x180005c64`
- `0x18000df90`
- `0x18005f8a0`
- `0x180071320`
- `0x180071610`
- `0x18008222c`
- `0x180084c14`
- `0x180085868`
- `0x180098260`
- `0x180099598`
- `0x1800a1c24`
- `0x1800a2db0`
- `0x1800a73b4`
- `0x1800b0e38`
- `0x1800b1768`
- `0x1800b2530`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b28bf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b28cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b297d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2b9b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2ba9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b28bf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b28cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b297d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2b9b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b2ba9`

## string_xrefs

- `0x1800b256d`: `LpaServiceLpd`
- `0x1800b2adb`: `LpaServiceLpd`
- `0x1800b25ac`: `OnEs10aGetEuiccConfiguredDataComplete`
- `0x1800b2683`: `OnEs10aGetEuiccConfiguredDataComplete`
- `0x1800b2566`: `LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete`
- `0x1800b2ad0`: `LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete(
        LPA::Lpd::DownloadInstance *this,
        int a2,
        __int64 a3,
        int a4,
        __int64 *a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8)
{
  int v8; // r14d
  __int64 v10; // rdx
  unsigned int v11; // r13d
  __int64 v12; // rax
  __int64 v13; // rbx
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  char *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // r9
  unsigned int v27; // edi
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rbx
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  char *v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rbx
  _QWORD *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 *v43; // rdx
  __int64 v44; // rcx
  const char *v45; // rdi
  const char *v46; // rbx
  const char *v47; // rax
  int v48; // [rsp+70h] [rbp-90h] BYREF
  const char *v49; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+98h] [rbp-68h] BYREF
  int v54; // [rsp+9Ch] [rbp-64h] BYREF
  int v55; // [rsp+A0h] [rbp-60h] BYREF
  const char *v56; // [rsp+A8h] [rbp-58h] BYREF
  const char *v57; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v58; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v59; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  _BYTE v63[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v64[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v65[16]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v66; // [rsp+150h] [rbp+50h]
  _BYTE v67[64]; // [rsp+160h] [rbp+60h] BYREF

  v8 = a2;
  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v48 = a2;
      v55 = 2;
      v49 = "OnEs10aGetEuiccConfiguredDataComplete";
      v54 = *((_DWORD *)this + 228);
      v53 = 5;
      v60 = *a7;
      v61 = *((_WORD *)a7 + 4) - v60;
      v58 = *a6;
      v59 = *((_WORD *)a6 + 4) - v58;
      v51 = *a5;
      LOWORD(v52) = *((_WORD *)a5 + 4) - v51;
      v57 = "LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete";
      v56 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v51,
        (unsigned int)&dword_180130D74,
        (unsigned int)"LpaServiceLpd",
        a4,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v51,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v53,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&v55,
        (__int64)&v48);
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v53 = a2;
    v54 = 2;
    v56 = "OnEs10aGetEuiccConfiguredDataComplete";
    v55 = *((_DWORD *)this + 228);
    v48 = 5;
    v51 = *a7;
    LOWORD(v52) = *((_WORD *)a7 + 4) - v51;
    v58 = *a6;
    v59 = *((_WORD *)a6 + 4) - v58;
    v60 = *a5;
    v61 = *((_WORD *)a5 + 4) - v60;
    v57 = "LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete";
    v49 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v60,
      (unsigned int)&unk_180130E08,
      (unsigned int)"LpaServiceLpd",
      a4,
      (__int64)&v49,
      (__int64)&v57,
      (__int64)&v60,
      (__int64)&v58,
      (__int64)&v51,
      (__int64)&v48,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)&v54,
      (__int64)&v53);
  }
  if ( v8 < 0 )
    goto LABEL_39;
  v10 = *((_QWORD *)this + 106);
  if ( (*((_QWORD *)this + 107) - v10) >> 5 )
  {
    v11 = 0;
    do
    {
      v12 = std::make_tuple<char const (&)[1],std::string &>(&v58, v10, v10 + 32LL * v11);
      std::tuple<std::string,std::string>::tuple<std::string,std::string>(v63, v12);
      if ( *((_QWORD *)this + 118) == 0x333333333333333LL )
        std::_Xlength_error("list too long");
      v13 = *((_QWORD *)this + 117);
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
        &v49,
        (char *)this + 936,
        v63);
      ++*((_QWORD *)this + 118);
      v14 = *(_QWORD **)(v13 + 8);
      *v50 = v13;
      v50[1] = v14;
      v15 = v50;
      v50 = 0;
      *(_QWORD *)(v13 + 8) = v15;
      *v14 = v15;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v49);
      std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v63);
      std::string::_Tidy_deallocate(&v58);
      ++v11;
      v10 = *((_QWORD *)this + 106);
    }
    while ( v11 < (unsigned __int64)((*((_QWORD *)this + 107) - v10) >> 5) );
  }
  std::string::assign<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,0>(
    (char *)this + 960,
    *a7,
    a7[1]);
  std::string::string(v65, *a5, a5[1]);
  std::string::string(&v60, *a6, a6[1]);
  if ( v62 && *((_BYTE *)this + 877) )
  {
    v17 = (char *)this + 936;
    v18 = std::make_tuple<char const (&)[1],std::string &>(&v58, v16, &v60);
    std::tuple<std::string,std::string>::tuple<std::string,std::string>(v63, v18);
    if ( *((_QWORD *)this + 118) == 0x333333333333333LL )
      std::_Xlength_error("list too long");
    v19 = *(_QWORD *)v17;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
      &v49,
      (char *)this + 936,
      v63);
    ++*((_QWORD *)this + 118);
    v20 = *(_QWORD **)(v19 + 8);
    *v50 = v19;
    v50[1] = v20;
    v21 = v50;
    v50 = 0;
    *(_QWORD *)(v19 + 8) = v21;
    *v20 = v21;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v49);
    std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v63);
    std::string::_Tidy_deallocate(&v58);
    *((_QWORD *)this + 119) = *(_QWORD *)(*(_QWORD *)v17 + 8LL);
  }
  if ( v66 )
  {
    v22 = std::make_tuple<char const (&)[1],std::string &>(&v58, v16, v65);
    std::tuple<std::string,std::string>::tuple<std::string,std::string>(v63, v22);
    if ( *((_QWORD *)this + 118) == 0x333333333333333LL )
      std::_Xlength_error("list too long");
    v23 = *((_QWORD *)this + 117);
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
      &v49,
      (char *)this + 936,
      v63);
    ++*((_QWORD *)this + 118);
    v24 = *(_QWORD **)(v23 + 8);
    *v50 = v23;
    v50[1] = v24;
    v25 = v50;
    v50 = 0;
    *(_QWORD *)(v23 + 8) = v25;
    *v24 = v25;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v49);
    std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v63);
    std::string::_Tidy_deallocate(&v58);
  }
  v26 = *a8;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((a8[1] - *a8) >> 3) )
  {
    v27 = 0;
    do
    {
      std::string::string(&v58, *(_QWORD *)(v26 + 24LL * v27), *(_QWORD *)(v26 + 24LL * v27 + 8));
      v29 = std::make_tuple<char const (&)[1],std::string &>(v63, v28, &v58);
      std::tuple<std::string,std::string>::tuple<std::string,std::string>(v67, v29);
      if ( *((_QWORD *)this + 118) == 0x333333333333333LL )
        std::_Xlength_error("list too long");
      v30 = *((_QWORD *)this + 117);
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
        &v51,
        (char *)this + 936,
        v67);
      ++*((_QWORD *)this + 118);
      v31 = *(_QWORD **)(v30 + 8);
      *v52 = v30;
      v52[1] = v31;
      v32 = v52;
      v52 = 0;
      *(_QWORD *)(v30 + 8) = v32;
      *v31 = v32;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v51);
      std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v67);
      std::string::_Tidy_deallocate(v63);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v49 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v58);
        v48 = v27;
        v57 = "LPA::Lpd::DownloadInstance::OnEs10aGetEuiccConfiguredDataComplete";
        v56 = "LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v33,
          (unsigned int)byte_180130D1B,
          v34,
          v35,
          (__int64)&v56,
          (__int64)&v57,
          (__int64)&v48,
          (__int64)&v49);
      }
      std::string::_Tidy_deallocate(&v58);
      ++v27;
      v26 = *a8;
    }
    while ( v27 < 0xAAAAAAAAAAAAAAABuLL * ((a8[1] - *a8) >> 3) );
  }
  if ( v62 && !*((_BYTE *)this + 877) )
  {
    v36 = (char *)this + 936;
    v37 = std::make_tuple<char const (&)[1],std::string &>(v63, v16, &v60);
    std::tuple<std::string,std::string>::tuple<std::string,std::string>(v67, v37);
    if ( *((_QWORD *)this + 118) == 0x333333333333333LL )
      std::_Xlength_error("list too long");
    v38 = *(_QWORD *)v36;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(
      &v51,
      (char *)this + 936,
      v67);
    ++*((_QWORD *)this + 118);
    v39 = *(_QWORD **)(v38 + 8);
    *v52 = v38;
    v52[1] = v39;
    v40 = v52;
    v52 = 0;
    *(_QWORD *)(v38 + 8) = v40;
    *v39 = v40;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(&v51);
    std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v67);
    std::string::_Tidy_deallocate(v63);
    *((_QWORD *)this + 119) = *(_QWORD *)(*(_QWORD *)v36 + 8LL);
  }
  if ( *((_QWORD *)this + 118) )
  {
    v41 = **((_QWORD **)this + 117);
    v42 = *((_QWORD *)this + 119);
    std::tuple<std::string,std::string>::tuple<std::string,std::string>(v63, v41 + 16);
    v43 = (__int64 *)**((_QWORD **)this + 117);
    v44 = *v43;
    --*((_QWORD *)this + 118);
    *(_QWORD *)v43[1] = v44;
    *(_QWORD *)(v44 + 8) = v43[1];
    std::_List_node<std::tuple<std::string,std::string>,void *>::_Freenode<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>();
    if ( v41 == v42 )
    {
      *((_QWORD *)this + 119) = *((_QWORD *)this + 117);
      v45 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 960);
    }
    else
    {
      v45 = 0;
    }
    v46 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v64);
    v47 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v63);
    v8 = LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication(this, v47, v46, 0, 0, v45, 0);
    std::tuple<std::string,std::string>::~tuple<std::string,std::string>(v63);
  }
  std::string::_Tidy_deallocate(&v60);
  std::string::_Tidy_deallocate(v65);
  if ( v8 < 0 )
LABEL_39:
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted((__int64)this, v8, 0);
}

```

## disassembly

```asm
0x1800b2530  mov     [rsp-8+arg_10], rbx
0x1800b2535  push    rbp
0x1800b2536  push    rsi
0x1800b2537  push    rdi
0x1800b2538  push    r12
0x1800b253a  push    r13
0x1800b253c  push    r14
0x1800b253e  push    r15
0x1800b2540  lea     rbp, [rsp-0B0h]
0x1800b2548  sub     rsp, 1B0h
0x1800b254f  mov     rax, cs:__security_cookie
0x1800b2556  xor     rax, rsp
0x1800b2559  mov     [rbp+0E0h+var_40], rax
0x1800b2560  mov     r14d, edx
0x1800b2563  mov     rsi, rcx
0x1800b2566  lea     rdx, aLpaLpdDownload_22; "LPA::Lpd::DownloadInstance::OnEs10aGetE"...
0x1800b256d  lea     r8, aLpaservicelpd; "LpaServiceLpd"
0x1800b2574  mov     rdi, [rbp+0E0h+arg_30]
0x1800b257b  mov     r15, [rbp+0E0h+arg_28]
0x1800b2582  mov     r12, [rbp+0E0h+arg_20]
0x1800b2589  mov     eax, cs:CallbackContext
0x1800b258f  test    r14d, r14d
0x1800b2592  js      loc_1800B266E
0x1800b2598  cmp     eax, 4
0x1800b259b  jbe     loc_1800B2749
0x1800b25a1  mov     [rbp+0E0h+var_148], r14d
0x1800b25a5  mov     [rbp+0E0h+var_144], 2
0x1800b25ac  lea     rax, aOnes10ageteuic; "OnEs10aGetEuiccConfiguredDataComplete"
0x1800b25b3  mov     [rbp+0E0h+var_138], rax
0x1800b25b7  mov     eax, [rcx+390h]
0x1800b25bd  mov     [rbp+0E0h+var_140], eax
0x1800b25c0  mov     [rsp+1E0h+var_170], 5
0x1800b25c8  mov     rcx, [rdi]
0x1800b25cb  mov     [rbp+0E0h+var_158], rcx
0x1800b25cf  movzx   eax, word ptr [rdi+8]
0x1800b25d3  sub     ax, cx
0x1800b25d6  mov     word ptr [rbp+0E0h+var_150], ax
0x1800b25da  mov     rcx, [r15]
0x1800b25dd  mov     [rbp+0E0h+var_128], rcx
0x1800b25e1  movzx   eax, word ptr [r15+8]
0x1800b25e6  sub     ax, cx
0x1800b25e9  mov     [rbp+0E0h+var_120], ax
0x1800b25ed  mov     rcx, [r12]
0x1800b25f1  mov     [rbp+0E0h+var_100], rcx
0x1800b25f5  movzx   eax, word ptr [r12+8]
0x1800b25fb  sub     ax, cx
0x1800b25fe  mov     [rbp+0E0h+var_F8], ax
0x1800b2602  mov     [rbp+0E0h+var_130], rdx
0x1800b2606  mov     [rsp+1E0h+var_168], r8
0x1800b260b  lea     rax, [rbp+0E0h+var_148]
0x1800b260f  mov     [rsp+1E0h+var_178], rax
0x1800b2614  lea     rax, [rbp+0E0h+var_144]
0x1800b2618  mov     [rsp+1E0h+var_180], rax
0x1800b261d  lea     rax, [rbp+0E0h+var_138]
0x1800b2621  mov     [rsp+1E0h+var_188], rax
0x1800b2626  lea     rax, [rbp+0E0h+var_140]
0x1800b262a  mov     [rsp+1E0h+var_190], rax
0x1800b262f  lea     rax, [rsp+1E0h+var_170]
0x1800b2634  mov     [rsp+1E0h+var_198], rax
0x1800b2639  lea     rax, [rbp+0E0h+var_158]
0x1800b263d  mov     [rsp+1E0h+var_1A0], rax
0x1800b2642  lea     rax, [rbp+0E0h+var_128]
0x1800b2646  mov     [rsp+1E0h+var_1A8], rax
0x1800b264b  lea     rax, [rbp+0E0h+var_100]
0x1800b264f  mov     [rsp+1E0h+var_1B0], rax
0x1800b2654  lea     rax, [rbp+0E0h+var_130]
0x1800b2658  mov     [rsp+1E0h+var_1B8], rax
0x1800b265d  lea     rax, [rsp+1E0h+var_168]
0x1800b2662  lea     rdx, unk_180130E08
0x1800b2669  jmp     loc_1800B273F
0x1800b266e  cmp     eax, 2
0x1800b2671  jbe     loc_1800B2749
0x1800b2677  mov     [rsp+1E0h+var_170], r14d
0x1800b267c  mov     [rbp+0E0h+var_140], 2
0x1800b2683  lea     rax, aOnes10ageteuic; "OnEs10aGetEuiccConfiguredDataComplete"
0x1800b268a  mov     [rsp+1E0h+var_168], rax
0x1800b268f  mov     eax, [rcx+390h]
0x1800b2695  mov     [rbp+0E0h+var_144], eax
0x1800b2698  mov     [rbp+0E0h+var_148], 5
0x1800b269f  mov     rcx, [rdi]
0x1800b26a2  mov     [rbp+0E0h+var_100], rcx
0x1800b26a6  movzx   eax, word ptr [rdi+8]
0x1800b26aa  sub     ax, cx
0x1800b26ad  mov     [rbp+0E0h+var_F8], ax
0x1800b26b1  mov     rcx, [r15]
0x1800b26b4  mov     [rbp+0E0h+var_128], rcx
0x1800b26b8  movzx   eax, word ptr [r15+8]
0x1800b26bd  sub     ax, cx
0x1800b26c0  mov     [rbp+0E0h+var_120], ax
0x1800b26c4  mov     rcx, [r12]
0x1800b26c8  mov     [rbp+0E0h+var_158], rcx
0x1800b26cc  movzx   eax, word ptr [r12+8]
0x1800b26d2  sub     ax, cx
0x1800b26d5  mov     word ptr [rbp+0E0h+var_150], ax
0x1800b26d9  mov     [rbp+0E0h+var_130], rdx
0x1800b26dd  mov     [rbp+0E0h+var_138], r8
0x1800b26e1  lea     rax, [rsp+1E0h+var_170]
0x1800b26e6  mov     [rsp+1E0h+var_178], rax
0x1800b26eb  lea     rax, [rbp+0E0h+var_140]
0x1800b26ef  mov     [rsp+1E0h+var_180], rax
0x1800b26f4  lea     rax, [rsp+1E0h+var_168]
0x1800b26f9  mov     [rsp+1E0h+var_188], rax
0x1800b26fe  lea     rax, [rbp+0E0h+var_144]
0x1800b2702  mov     [rsp+1E0h+var_190], rax
0x1800b2707  lea     rax, [rbp+0E0h+var_148]
0x1800b270b  mov     [rsp+1E0h+var_198], rax
0x1800b2710  lea     rax, [rbp+0E0h+var_100]
0x1800b2714  mov     [rsp+1E0h+var_1A0], rax
0x1800b2719  lea     rax, [rbp+0E0h+var_128]
0x1800b271d  mov     [rsp+1E0h+var_1A8], rax
0x1800b2722  lea     rax, [rbp+0E0h+var_158]
0x1800b2726  mov     [rsp+1E0h+var_1B0], rax
0x1800b272b  lea     rax, [rbp+0E0h+var_130]
0x1800b272f  mov     [rsp+1E0h+var_1B8], rax
0x1800b2734  lea     rax, [rbp+0E0h+var_138]
0x1800b2738  lea     rdx, dword_180130D74
0x1800b273f  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x1800b2744  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperArray@$00@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U1@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperArray@$00@@44AEBU?$_tlgWrapperByVal@$03@@5355@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b2749  test    r14d, r14d
0x1800b274c  js      loc_1800B2CE5
0x1800b2752  mov     rdx, [rsi+350h]
0x1800b2759  mov     rax, [rsi+358h]
0x1800b2760  sub     rax, rdx
0x1800b2763  sar     rax, 5
0x1800b2767  mov     rbx, 333333333333333h
0x1800b2771  test    rax, rax
0x1800b2774  jz      loc_1800B283C
0x1800b277a  xor     r13d, r13d
0x1800b277d  mov     r8d, r13d
0x1800b2780  shl     r8, 5
0x1800b2784  add     r8, rdx
0x1800b2787  lea     rcx, [rbp+0E0h+var_128]
0x1800b278b  call    ??$make_tuple@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_tuple<char const (&)[1],std::string &>(char const (&)[1],std::string &)
0x1800b2790  nop
0x1800b2791  mov     rdx, rax
0x1800b2794  lea     rcx, [rbp+0E0h+var_E0]
0x1800b2798  call    ??$?0PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@$$QEAV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::tuple<std::string,std::string>::tuple<std::string,std::string>(std::tuple<char const *,std::string> &&)
0x1800b279d  nop
0x1800b279e  cmp     [rsi+3B0h], rbx
0x1800b27a5  jz      loc_1800B28C6
0x1800b27ab  lea     rdx, [rsi+3A8h]
0x1800b27b2  mov     rbx, [rdx]
0x1800b27b5  lea     r8, [rbp+0E0h+var_E0]
0x1800b27b9  lea     rcx, [rsp+1E0h+var_168]
0x1800b27be  call    ??$?0V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>> &,std::tuple<std::string,std::string> &&)
0x1800b27c3  inc     qword ptr [rsi+3B0h]
0x1800b27ca  mov     rcx, [rbx+8]
0x1800b27ce  mov     rax, [rbp+0E0h+var_160]
0x1800b27d2  mov     [rax], rbx
0x1800b27d5  mov     rax, [rbp+0E0h+var_160]
0x1800b27d9  mov     [rax+8], rcx
0x1800b27dd  mov     rax, [rbp+0E0h+var_160]
0x1800b27e1  mov     [rbp+0E0h+var_160], 0
0x1800b27e9  mov     [rbx+8], rax
0x1800b27ed  mov     [rcx], rax
0x1800b27f0  lea     rcx, [rsp+1E0h+var_168]
0x1800b27f5  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(void)
0x1800b27fa  nop
0x1800b27fb  lea     rcx, [rbp+0E0h+var_E0]
0x1800b27ff  call    ??1?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::string,std::string>::~tuple<std::string,std::string>(void)
0x1800b2804  nop
0x1800b2805  lea     rcx, [rbp+0E0h+var_128]
0x1800b2809  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b280e  inc     r13d
0x1800b2811  mov     rdx, [rsi+350h]
0x1800b2818  mov     rcx, [rsi+358h]
0x1800b281f  sub     rcx, rdx
0x1800b2822  sar     rcx, 5
0x1800b2826  mov     eax, r13d
0x1800b2829  cmp     rax, rcx
0x1800b282c  mov     rbx, 333333333333333h
0x1800b2836  jb      loc_1800B277D
0x1800b283c  lea     r13, [rsi+3C0h]
0x1800b2843  mov     r8, [rdi+8]
0x1800b2847  mov     rdx, [rdi]
0x1800b284a  mov     rcx, r13
0x1800b284d  call    ??$assign@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0@Z; std::string::assign<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>)
0x1800b2852  mov     r8, [r12+8]
0x1800b2857  mov     rdx, [r12]
0x1800b285b  lea     rcx, [rbp+0E0h+var_A0]
0x1800b285f  call    ??$?0PEAE$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAE0AEBV?$allocator@D@1@@Z; std::string::string(uchar *,uchar *,std::allocator<char> const &)
0x1800b2864  nop
0x1800b2865  mov     r8, [r15+8]
0x1800b2869  mov     rdx, [r15]
0x1800b286c  lea     rcx, [rbp+0E0h+var_100]
0x1800b2870  call    ??$?0PEAE$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAE0AEBV?$allocator@D@1@@Z; std::string::string(uchar *,uchar *,std::allocator<char> const &)
0x1800b2875  nop
0x1800b2876  xor     r12d, r12d
0x1800b2879  cmp     [rbp+0E0h+var_F0], r12
0x1800b287d  jbe     loc_1800B293A
0x1800b2883  cmp     [rsi+36Dh], r12b
0x1800b288a  jz      loc_1800B293A
0x1800b2890  lea     rdi, [rsi+3A8h]
0x1800b2897  lea     r8, [rbp+0E0h+var_100]
0x1800b289b  lea     rcx, [rbp+0E0h+var_128]
0x1800b289f  call    ??$make_tuple@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_tuple<char const (&)[1],std::string &>(char const (&)[1],std::string &)
0x1800b28a4  nop
0x1800b28a5  mov     rdx, rax
0x1800b28a8  lea     rcx, [rbp+0E0h+var_E0]
0x1800b28ac  call    ??$?0PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@$$QEAV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::tuple<std::string,std::string>::tuple<std::string,std::string>(std::tuple<char const *,std::string> &&)
0x1800b28b1  nop
0x1800b28b2  cmp     [rdi+8], rbx
0x1800b28b6  jnz     short loc_1800B28D4
0x1800b28b8  lea     rcx, aListTooLong; "list too long"
0x1800b28bf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b28c6  lea     rcx, aListTooLong; "list too long"
0x1800b28cd  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b28d4  mov     rbx, [rdi]
0x1800b28d7  lea     r8, [rbp+0E0h+var_E0]
0x1800b28db  mov     rdx, rdi
0x1800b28de  lea     rcx, [rsp+1E0h+var_168]
0x1800b28e3  call    ??$?0V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>> &,std::tuple<std::string,std::string> &&)
0x1800b28e8  inc     qword ptr [rdi+8]
0x1800b28ec  mov     rcx, [rbx+8]
0x1800b28f0  mov     rax, [rbp+0E0h+var_160]
0x1800b28f4  mov     [rax], rbx
0x1800b28f7  mov     rax, [rbp+0E0h+var_160]
0x1800b28fb  mov     [rax+8], rcx
0x1800b28ff  mov     rax, [rbp+0E0h+var_160]
0x1800b2903  mov     [rbp+0E0h+var_160], r12
0x1800b2907  mov     [rbx+8], rax
0x1800b290b  mov     [rcx], rax
0x1800b290e  lea     rcx, [rsp+1E0h+var_168]
0x1800b2913  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(void)
0x1800b2918  nop
0x1800b2919  lea     rcx, [rbp+0E0h+var_E0]
0x1800b291d  call    ??1?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::string,std::string>::~tuple<std::string,std::string>(void)
0x1800b2922  nop
0x1800b2923  lea     rcx, [rbp+0E0h+var_128]
0x1800b2927  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b292c  mov     rax, [rdi]
0x1800b292f  mov     rcx, [rax+8]
0x1800b2933  mov     [rsi+3B8h], rcx
0x1800b293a  cmp     [rbp+0E0h+var_90], r12
0x1800b293e  jbe     loc_1800B29DC
0x1800b2944  lea     rdi, [rsi+3A8h]
0x1800b294b  lea     r8, [rbp+0E0h+var_A0]
0x1800b294f  lea     rcx, [rbp+0E0h+var_128]
0x1800b2953  call    ??$make_tuple@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_tuple<char const (&)[1],std::string &>(char const (&)[1],std::string &)
0x1800b2958  nop
0x1800b2959  mov     rdx, rax
0x1800b295c  lea     rcx, [rbp+0E0h+var_E0]
0x1800b2960  call    ??$?0PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@$$QEAV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::tuple<std::string,std::string>::tuple<std::string,std::string>(std::tuple<char const *,std::string> &&)
0x1800b2965  nop
0x1800b2966  mov     rax, 333333333333333h
0x1800b2970  cmp     [rdi+8], rax
0x1800b2974  jnz     short loc_1800B2984
0x1800b2976  lea     rcx, aListTooLong; "list too long"
0x1800b297d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b2984  mov     rbx, [rdi]
0x1800b2987  lea     r8, [rbp+0E0h+var_E0]
0x1800b298b  mov     rdx, rdi
0x1800b298e  lea     rcx, [rsp+1E0h+var_168]
0x1800b2993  call    ??$?0V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>> &,std::tuple<std::string,std::string> &&)
0x1800b2998  inc     qword ptr [rdi+8]
0x1800b299c  mov     rcx, [rbx+8]
0x1800b29a0  mov     rax, [rbp+0E0h+var_160]
0x1800b29a4  mov     [rax], rbx
0x1800b29a7  mov     rax, [rbp+0E0h+var_160]
0x1800b29ab  mov     [rax+8], rcx
0x1800b29af  mov     rax, [rbp+0E0h+var_160]
0x1800b29b3  mov     [rbp+0E0h+var_160], r12
0x1800b29b7  mov     [rbx+8], rax
0x1800b29bb  mov     [rcx], rax
0x1800b29be  lea     rcx, [rsp+1E0h+var_168]
0x1800b29c3  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>(void)
0x1800b29c8  nop
0x1800b29c9  lea     rcx, [rbp+0E0h+var_E0]
0x1800b29cd  call    ??1?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::string,std::string>::~tuple<std::string,std::string>(void)
0x1800b29d2  nop
0x1800b29d3  lea     rcx, [rbp+0E0h+var_128]
0x1800b29d7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b29dc  mov     r15, [rbp+0E0h+arg_38]
0x1800b29e3  mov     r9, [r15]
0x1800b29e6  mov     rax, [r15+8]
0x1800b29ea  sub     rax, r9
0x1800b29ed  sar     rax, 3
0x1800b29f1  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800b29fb  imul    rax, rcx
0x1800b29ff  test    rax, rax
0x1800b2a02  jz      loc_1800B2B4B
0x1800b2a08  mov     edi, r12d
0x1800b2a0b  mov     eax, edi
0x1800b2a0d  lea     rdx, [rax+rax*2]
0x1800b2a11  mov     r8, [r9+rdx*8+8]
0x1800b2a16  mov     rdx, [r9+rdx*8]
0x1800b2a1a  lea     rcx, [rbp+0E0h+var_128]
0x1800b2a1e  call    ??$?0PEAE$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAE0AEBV?$allocator@D@1@@Z; std::string::string(uchar *,uchar *,std::allocator<char> const &)
0x1800b2a23  nop
0x1800b2a24  lea     r8, [rbp+0E0h+var_128]
0x1800b2a28  lea     rcx, [rbp+0E0h+var_E0]
0x1800b2a2c  call    ??$make_tuple@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@AEAY00$$CBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_tuple<char const (&)[1],std::string &>(char const (&)[1],std::string &)
0x1800b2a31  nop
0x1800b2a32  mov     rdx, rax
0x1800b2a35  lea     rcx, [rbp+0E0h+var_80]
0x1800b2a39  call    ??$?0PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@$$QEAV?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::tuple<std::string,std::string>::tuple<std::string,std::string>(std::tuple<char const *,std::string> &&)
0x1800b2a3e  nop
0x1800b2a3f  mov     rax, 333333333333333h
0x1800b2a49  cmp     [rsi+3B0h], rax
0x1800b2a50  jz      loc_1800B2BA2
  ... truncated ...
```
