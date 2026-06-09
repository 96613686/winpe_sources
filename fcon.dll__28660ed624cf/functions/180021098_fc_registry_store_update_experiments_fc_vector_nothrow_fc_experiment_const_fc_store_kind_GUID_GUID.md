# fc::registry_store::update_experiments(fc::vector_nothrow<fc::experiment> const &,fc::store_kind,_GUID,_GUID *)

- ea: `0x180021098`
- end: `0x180021398`
- name: `?update_experiments@registry_store@fc@@QEAAJAEBV?$vector_nothrow@Uexperiment@fc@@@2@W4store_kind@2@U_GUID@@PEAU5@@Z`
- size: `768`
- prototype: `__int64 __usercall@<rax>(fc::registry_store *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x18002100c`

## callees

- `0x180003220`
- `0x1800040f4`
- `0x180005fe8`
- `0x18000949c`
- `0x180016698`
- `0x1800196d4`
- `0x18001b944`
- `0x18001c6e0`
- `0x18001cb30`
- `0x18001e014`
- `0x18001e820`
- `0x18001f850`
- `0x180021098`
- `0x1800214d8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180021300`
- `RPCRT4!UuidCreate` at `0x180021300`

## string_xrefs

- `0x180021101`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x18002118e`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x180021230`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x180021261`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x1800212ab`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x1800212db`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x180021322`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

## pseudocode

```c
__int64 __fastcall fc::registry_store::update_experiments(
        fc::registry_store *this,
        __int64 a2,
        unsigned int a3,
        const void *a4,
        UUID *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // r8
  int store_id; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  fc::registry_store *v17; // rcx
  __int64 v18; // r8
  const struct fc::experiment *v19; // rbx
  __int64 v20; // rsi
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  HKEY v26; // [rsp+20h] [rbp-40h] BYREF
  HKEY v27; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v28[8]; // [rsp+30h] [rbp-30h] BYREF
  __int128 Buf2; // [rsp+38h] [rbp-28h] BYREF
  UUID Buf1; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  if ( *(_QWORD *)(a2 + 16) )
  {
    fc::details::registry_store_lock::lock_exclusive(this, v28);
    v26 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v26,
      0,
      v12);
    store_id = fc::open_store_key_for_readwrite(*((_QWORD *)this + 173), 0, a3, &v26);
    v10 = store_id;
    if ( store_id >= 0 )
    {
      v15 = *((_QWORD *)this + 173);
      Buf1 = 0;
      store_id = fc::get_store_id(v15, 0, &Buf1);
      v10 = store_id;
      if ( store_id >= 0 )
      {
        Buf2 = 0;
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) || !memcmp_0(&Buf1, a4, 0x10u) || (Buf2 = 0, !memcmp_0(a4, &Buf2, 0x10u)) )
        {
          v19 = *(const struct fc::experiment **)a2;
          v20 = *(_QWORD *)a2 + 32LL * *(_QWORD *)(a2 + 16);
          v27 = 0;
          while ( v19 != (const struct fc::experiment *)v20 )
          {
            if ( (*((_BYTE *)v19 + 16) & 1) != 0 )
            {
              v21 = fc::registry_store::update_or_add_experiment(v17, v26, v19);
              if ( v21 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1E4,
                  (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
                  (const char *)(unsigned int)v21,
                  (int)v26);
            }
            if ( (*((_BYTE *)v19 + 16) & 2) != 0 )
            {
              v22 = fc::registry_store::remove_from_store(this, v26, v19);
              if ( v22 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1E8,
                  (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
                  (const char *)(unsigned int)v22,
                  (int)v26);
            }
            if ( (*((_BYTE *)v19 + 16) & 4) != 0 )
            {
              if ( !v27 )
              {
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                  &v27,
                  0,
                  v18);
                v23 = fc::open_store_key_for_readwrite(*((_QWORD *)this + 173), 0, 1, &v27);
                if ( v23 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x1EE,
                    (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
                    (const char *)(unsigned int)v23,
                    (int)v26);
              }
              if ( v27 )
              {
                v24 = fc::registry_store::remove_from_store(this, v27, v19);
                if ( v24 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x1F3,
                    (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
                    (const char *)(unsigned int)v24,
                    (int)v26);
              }
            }
            v19 = (const struct fc::experiment *)((char *)v19 + 32);
          }
          UuidCreate(&Buf1);
          v25 = fc::set_store_id(*((_QWORD *)this + 173), 0, &Buf1);
          v10 = v25;
          if ( v25 >= 0 )
          {
            if ( a5 )
              *a5 = Buf1;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
LABEL_38:
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F9,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
            (const char *)(unsigned int)v25,
            (int)v26);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
LABEL_34:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
          goto LABEL_5;
        }
        v10 = -2147023727;
        v14 = 476;
        v16 = 2147943569LL;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
          (const char *)v16,
          (int)v26);
        goto LABEL_34;
      }
      v14 = 474;
    }
    else
    {
      v14 = 471;
    }
    v16 = (unsigned int)store_id;
    goto LABEL_11;
  }
  if ( a5 )
  {
    fc::details::registry_store_lock::lock_exclusive(this, v28);
    v9 = fc::get_store_id(*((_QWORD *)this + 173), 0, a5);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
        (const char *)(unsigned int)v9,
        (int)v26);
LABEL_5:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
      return v10;
    }
    goto LABEL_38;
  }
  return 0;
}

```

## disassembly

```asm
0x180021098  mov     [rsp-28h+arg_18], rbx
0x18002109d  push    rbp
0x18002109e  push    rsi
0x18002109f  push    rdi
0x1800210a0  push    r14
0x1800210a2  push    r15
0x1800210a4  mov     rbp, rsp
0x1800210a7  sub     rsp, 60h
0x1800210ab  mov     rax, cs:__security_cookie
0x1800210b2  xor     rax, rsp
0x1800210b5  mov     [rbp+var_8], rax
0x1800210b9  cmp     qword ptr [rdx+10h], 0
0x1800210be  mov     r15, r9
0x1800210c1  mov     r14, [rbp+arg_20]
0x1800210c5  mov     ebx, r8d
0x1800210c8  mov     rsi, rdx
0x1800210cb  mov     rdi, rcx
0x1800210ce  jnz     short loc_180021125
0x1800210d0  test    r14, r14
0x1800210d3  jz      loc_180021376
0x1800210d9  lea     rdx, [rbp+var_30]
0x1800210dd  call    ?lock_exclusive@registry_store_lock@details@fc@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ
0x1800210e2  mov     rcx, [rdi+568h]
0x1800210e9  mov     r8, r14
0x1800210ec  xor     edx, edx
0x1800210ee  call    ?get_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEAU_GUID@@@Z; fc::get_store_id(HKEY__ *,fc::store_type,_GUID &)
0x1800210f3  mov     ebx, eax
0x1800210f5  test    eax, eax
0x1800210f7  jns     loc_18002136D
0x1800210fd  mov     rcx, [rbp+28h]; this
0x180021101  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021108  mov     r9d, eax; char *
0x18002110b  mov     edx, 1CDh; void *
0x180021110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021115  lea     rcx, [rbp+var_30]
0x180021119  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002111e  mov     eax, ebx
0x180021120  jmp     loc_180021378
0x180021125  lea     rdx, [rbp+var_30]
0x180021129  call    ?lock_exclusive@registry_store_lock@details@fc@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ
0x18002112e  xor     edx, edx
0x180021130  mov     [rbp+var_40], 0
0x180021138  lea     rcx, [rbp+var_40]
0x18002113c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180021141  mov     rcx, [rdi+568h]
0x180021148  lea     r9, [rbp+var_40]
0x18002114c  mov     r8d, ebx
0x18002114f  xor     edx, edx
0x180021151  call    ?open_store_key_for_readwrite@fc@@YAJPEAUHKEY__@@W4store_type@1@W4store_kind@1@PEAPEAU2@@Z; fc::open_store_key_for_readwrite(HKEY__ *,fc::store_type,fc::store_kind,HKEY__ * *)
0x180021156  mov     ebx, eax
0x180021158  test    eax, eax
0x18002115a  jns     short loc_180021163
0x18002115c  mov     edx, 1D7h
0x180021161  jmp     short loc_180021187
0x180021163  mov     rcx, [rdi+568h]
0x18002116a  lea     r8, [rbp+Buf1]
0x18002116e  xorps   xmm0, xmm0
0x180021171  xor     edx, edx
0x180021173  movups  [rbp+Buf1], xmm0
0x180021177  call    ?get_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEAU_GUID@@@Z; fc::get_store_id(HKEY__ *,fc::store_type,_GUID &)
0x18002117c  mov     ebx, eax
0x18002117e  test    eax, eax
0x180021180  jns     short loc_18002119F
0x180021182  mov     edx, 1DAh; void *
0x180021187  mov     r9d, eax; char *
0x18002118a  mov     rcx, [rbp+28h]; this
0x18002118e  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002119a  jmp     loc_18002133F
0x18002119f  xorps   xmm0, xmm0
0x1800211a2  lea     rdx, [rbp+Buf2]; Buf2
0x1800211a6  mov     ebx, 10h
0x1800211ab  lea     rcx, [rbp+Buf1]; Buf1
0x1800211af  mov     r8d, ebx; Size
0x1800211b2  movups  [rbp+Buf2], xmm0
0x1800211b6  call    memcmp_0
0x1800211bb  test    eax, eax
0x1800211bd  jz      short loc_1800211FB
0x1800211bf  mov     r8d, ebx; Size
0x1800211c2  lea     rcx, [rbp+Buf1]; Buf1
0x1800211c6  mov     rdx, r15; Buf2
0x1800211c9  call    memcmp_0
0x1800211ce  test    eax, eax
0x1800211d0  jz      short loc_1800211FB
0x1800211d2  xorps   xmm0, xmm0
0x1800211d5  lea     rdx, [rbp+Buf2]; Buf2
0x1800211d9  mov     r8d, ebx; Size
0x1800211dc  mov     rcx, r15; Buf1
0x1800211df  movups  [rbp+Buf2], xmm0
0x1800211e3  call    memcmp_0
0x1800211e8  test    eax, eax
0x1800211ea  jz      short loc_1800211FB
0x1800211ec  mov     ebx, 80070491h
0x1800211f1  mov     edx, 1DCh
0x1800211f6  mov     r9d, ebx
0x1800211f9  jmp     short loc_18002118A
0x1800211fb  mov     rbx, [rsi]
0x1800211fe  mov     rsi, [rsi+10h]
0x180021202  shl     rsi, 5
0x180021206  add     rsi, rbx
0x180021209  mov     [rbp+var_38], 0
0x180021211  jmp     loc_1800212F3
0x180021216  test    byte ptr [rbx+10h], 1
0x18002121a  jz      short loc_180021244
0x18002121c  mov     rdx, [rbp+var_40]; HKEY
0x180021220  mov     r8, rbx; struct fc::experiment *
0x180021223  call    ?update_or_add_experiment@registry_store@fc@@AEBAJPEAUHKEY__@@AEBUexperiment@2@@Z; fc::registry_store::update_or_add_experiment(HKEY__ *,fc::experiment const &)
0x180021228  test    eax, eax
0x18002122a  jns     short loc_180021244
0x18002122c  mov     rcx, [rbp+28h]; this
0x180021230  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021237  mov     r9d, eax; char *
0x18002123a  mov     edx, 1E4h; void *
0x18002123f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021244  test    byte ptr [rbx+10h], 2
0x180021248  jz      short loc_180021275
0x18002124a  mov     rdx, [rbp+var_40]; HKEY
0x18002124e  mov     r8, rbx; struct fc::experiment *
0x180021251  mov     rcx, rdi; this
0x180021254  call    ?remove_from_store@registry_store@fc@@AEBAJPEAUHKEY__@@AEBUexperiment@2@@Z; fc::registry_store::remove_from_store(HKEY__ *,fc::experiment const &)
0x180021259  test    eax, eax
0x18002125b  jns     short loc_180021275
0x18002125d  mov     rcx, [rbp+28h]; this
0x180021261  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021268  mov     r9d, eax; char *
0x18002126b  mov     edx, 1E8h; void *
0x180021270  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021275  test    byte ptr [rbx+10h], 4
0x180021279  jz      short loc_1800212EF
0x18002127b  cmp     [rbp+var_38], 0
0x180021280  jnz     short loc_1800212BF
0x180021282  xor     edx, edx
0x180021284  lea     rcx, [rbp+var_38]
0x180021288  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002128d  mov     rcx, [rdi+568h]
0x180021294  lea     r9, [rbp+var_38]
0x180021298  xor     edx, edx
0x18002129a  lea     r8d, [rdx+1]
0x18002129e  call    ?open_store_key_for_readwrite@fc@@YAJPEAUHKEY__@@W4store_type@1@W4store_kind@1@PEAPEAU2@@Z; fc::open_store_key_for_readwrite(HKEY__ *,fc::store_type,fc::store_kind,HKEY__ * *)
0x1800212a3  test    eax, eax
0x1800212a5  jns     short loc_1800212BF
0x1800212a7  mov     rcx, [rbp+28h]; this
0x1800212ab  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800212b2  mov     r9d, eax; char *
0x1800212b5  mov     edx, 1EEh; void *
0x1800212ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800212bf  mov     rdx, [rbp+var_38]; HKEY
0x1800212c3  test    rdx, rdx
0x1800212c6  jz      short loc_1800212EF
0x1800212c8  mov     r8, rbx; struct fc::experiment *
0x1800212cb  mov     rcx, rdi; this
0x1800212ce  call    ?remove_from_store@registry_store@fc@@AEBAJPEAUHKEY__@@AEBUexperiment@2@@Z; fc::registry_store::remove_from_store(HKEY__ *,fc::experiment const &)
0x1800212d3  test    eax, eax
0x1800212d5  jns     short loc_1800212EF
0x1800212d7  mov     rcx, [rbp+28h]; this
0x1800212db  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800212e2  mov     r9d, eax; char *
0x1800212e5  mov     edx, 1F3h; void *
0x1800212ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800212ef  add     rbx, 20h ; ' '
0x1800212f3  cmp     rbx, rsi
0x1800212f6  jnz     loc_180021216
0x1800212fc  lea     rcx, [rbp+Buf1]; Uuid
0x180021300  call    cs:__imp_UuidCreate
0x180021306  mov     rcx, [rdi+568h]
0x18002130d  lea     r8, [rbp+Buf1]
0x180021311  xor     edx, edx
0x180021313  call    ?set_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEBU_GUID@@@Z; fc::set_store_id(HKEY__ *,fc::store_type,_GUID const &)
0x180021318  mov     ebx, eax
0x18002131a  test    eax, eax
0x18002131c  jns     short loc_18002134D
0x18002131e  mov     rcx, [rbp+28h]; this
0x180021322  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021329  mov     r9d, eax; char *
0x18002132c  mov     edx, 1F9h; void *
0x180021331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021336  lea     rcx, [rbp+var_38]
0x18002133a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002133f  lea     rcx, [rbp+var_40]
0x180021343  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021348  jmp     loc_180021115
0x18002134d  test    r14, r14
0x180021350  jz      short loc_18002135B
0x180021352  movups  xmm0, [rbp+Buf1]
0x180021356  movdqu  xmmword ptr [r14], xmm0
0x18002135b  lea     rcx, [rbp+var_38]
0x18002135f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021364  lea     rcx, [rbp+var_40]
0x180021368  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002136d  lea     rcx, [rbp+var_30]
0x180021371  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021376  xor     eax, eax
0x180021378  mov     rcx, [rbp+var_8]
0x18002137c  xor     rcx, rsp; StackCookie
0x18002137f  call    __security_check_cookie
0x180021384  mov     rbx, [rsp+60h+arg_18]
0x18002138c  add     rsp, 60h
0x180021390  pop     r15
0x180021392  pop     r14
0x180021394  pop     rdi
0x180021395  pop     rsi
0x180021396  pop     rbp
0x180021397  retn
```
