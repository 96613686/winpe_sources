# CloudAPProfileDeleted(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180041820`
- end: `0x180041b2d`
- name: `?CloudAPProfileDeleted@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `781`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, _DWORD *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180011294`
- `0x180011424`
- `0x18003ff84`
- `0x180041820`
- `0x180041b34`
- `0x180041d58`
- `0x180042410`
- `0x18004317c`
- `0x18004c600`
- `0x18007f9fc`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800419b8`
- `ntdll!RtlValidSid` at `0x1800419b8`

## string_xrefs

- `0x1800418b5`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004192a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004196c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800419c2`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041a2e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041a5f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041a8c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041ac6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004198a`: `InvalidArg:pvProtocolSubmitBuffer`
- `0x180041aaa`: `InvalidArg:pvProtocolSubmitBuffer`
- `0x1800419e5`: `Input buffer contains an invalid SID`

## pseudocode

```c
__int64 __fastcall CloudAPProfileDeleted(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        _DWORD *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  unsigned int v8; // edx
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  int v19; // eax
  int v20; // eax
  const char *v21; // r9
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  int v26; // [rsp+20h] [rbp-98h]
  int v27; // [rsp+20h] [rbp-98h]
  int v28; // [rsp+20h] [rbp-98h]
  int v29; // [rsp+20h] [rbp-98h]
  int v30; // [rsp+20h] [rbp-98h]
  int v31; // [rsp+20h] [rbp-98h]
  bool v32; // [rsp+40h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  memset_0(Sid, 0, 0x44u);
  v32 = 0;
  if ( a3 && a6 && a7 && a5 >= 0x14 )
  {
    *a6 = 0;
    *a7 = 0;
    v8 = a3[3];
    if ( v8 < 0xFFFFFFED )
    {
      if ( v8
        && a5 == v8 + 19
        && (v12 = a3[2], v8 >= v12)
        && (v13 = (unsigned int)a3[1], (unsigned int)v13 <= a5)
        && v12 <= 0x44 )
      {
        if ( (unsigned int)v13 + v12 >= v12 )
        {
          if ( (unsigned int)v13 + v12 <= a5 )
          {
            memcpy_0(Sid, (char *)a3 + v13, (unsigned int)a3[2]);
            if ( RtlValidSid(Sid) )
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
              if ( !IsLoadAadCredKeyFromProfileEnabled() )
                goto LABEL_24;
              v19 = ShouldSkipUserCacheCleanup(Sid, &v32);
              if ( v19 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x71F,
                  (int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
                  (const char *)(unsigned int)v19);
              if ( v32 )
              {
                v20 = _AddSidForDeferredCacheCleanup(Sid);
                if ( v20 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x725,
                    (int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
                    (const char *)(unsigned int)v20);
              }
              else
              {
LABEL_24:
                CleanupUserCacheFromPackages(Sid);
              }
              return 0;
            }
            else
            {
              v9 = -1073741704;
              v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              v29 = 1816;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                3221225592LL,
                v18,
                v29,
                "Input buffer contains an invalid SID",
                &Class);
            }
          }
          else
          {
            v9 = -1073741811;
            v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            v28 = 1803;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v16, v28, "InvalidArg:pvProtocolSubmitBuffer", &Class);
          }
        }
        else
        {
          v9 = -1073741675;
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v27 = 1798;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, v27, "RtlDWordAdd", &Class);
        }
      }
      else
      {
        v9 = -1073741811;
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v30 = 1794;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v22, v21, v30, "InvalidArg:pvProtocolSubmitBuffer", &Class);
      }
    }
    else
    {
      v9 = -1073741675;
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = 1784;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v10, v26, "RtlDWordAdd", &Class);
    }
  }
  else
  {
    v9 = -1073741811;
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v31 = 1775;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v23, v31, "InvalidArg(s)", &Class);
  }
  return v9;
}

```

## disassembly

```asm
0x180041820  mov     [rsp+arg_0], rbx
0x180041825  mov     [rsp+arg_8], rsi
0x18004182a  push    rdi
0x18004182b  sub     rsp, 0B0h
0x180041832  mov     rax, cs:__security_cookie
0x180041839  xor     rax, rsp
0x18004183c  mov     [rsp+0B8h+var_18], rax
0x180041844  mov     rdi, [rsp+0B8h+arg_28]
0x18004184c  lea     rcx, [rsp+0B8h+Sid]; void *
0x180041851  mov     rsi, [rsp+0B8h+arg_30]
0x180041859  xor     edx, edx; Val
0x18004185b  mov     rbx, r8
0x18004185e  lea     r8d, [rdx+44h]; Size
0x180041862  call    memset_0
0x180041867  mov     [rsp+0B8h+var_78], 0
0x18004186c  test    rbx, rbx
0x18004186f  jz      loc_180041AC0
0x180041875  test    rdi, rdi
0x180041878  jz      loc_180041AC0
0x18004187e  test    rsi, rsi
0x180041881  jz      loc_180041AC0
0x180041887  mov     ecx, [rsp+0B8h+arg_20]
0x18004188e  cmp     ecx, 14h
0x180041891  jb      loc_180041AC0
0x180041897  mov     qword ptr [rdi], 0
0x18004189e  mov     dword ptr [rsi], 0
0x1800418a4  mov     edx, [rbx+0Ch]
0x1800418a7  lea     eax, [rdx+13h]
0x1800418aa  cmp     eax, 13h
0x1800418ad  jnb     short loc_1800418EC
0x1800418af  mov     r8d, 0C0000095h
0x1800418b5  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800418bc  mov     ebx, r8d
0x1800418bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800418c4  mov     r9, rax
0x1800418c7  lea     rax, Class
0x1800418ce  mov     [rsp+0B8h+var_88], rax
0x1800418d3  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x1800418da  mov     [rsp+0B8h+var_90], rax
0x1800418df  mov     [rsp+0B8h+var_98], 6F8h
0x1800418e7  jmp     loc_180041AF8
0x1800418ec  test    edx, edx
0x1800418ee  jz      loc_180041A86
0x1800418f4  cmp     ecx, eax
0x1800418f6  jnz     loc_180041A86
0x1800418fc  mov     eax, [rbx+8]
0x1800418ff  cmp     edx, eax
0x180041901  jb      loc_180041A86
0x180041907  mov     edx, [rbx+4]
0x18004190a  cmp     edx, ecx
0x18004190c  ja      loc_180041A86
0x180041912  cmp     eax, 44h ; 'D'
0x180041915  ja      loc_180041A86
0x18004191b  lea     r8d, [rdx+rax]
0x18004191f  cmp     r8d, eax
0x180041922  jnb     short loc_180041961
0x180041924  mov     r8d, 0C0000095h
0x18004192a  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041931  mov     ebx, r8d
0x180041934  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180041939  mov     r9, rax
0x18004193c  lea     rax, Class
0x180041943  mov     [rsp+0B8h+var_88], rax
0x180041948  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18004194f  mov     [rsp+0B8h+var_90], rax
0x180041954  mov     [rsp+0B8h+var_98], 706h
0x18004195c  jmp     loc_180041AF8
0x180041961  cmp     r8d, ecx
0x180041964  jbe     short loc_1800419A3
0x180041966  mov     r8d, 0C000000Dh
0x18004196c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041973  mov     ebx, r8d
0x180041976  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004197b  mov     r9, rax
0x18004197e  lea     rax, Class
0x180041985  mov     [rsp+0B8h+var_88], rax
0x18004198a  lea     rax, aInvalidargPvpr; "InvalidArg:pvProtocolSubmitBuffer"
0x180041991  mov     [rsp+0B8h+var_90], rax
0x180041996  mov     [rsp+0B8h+var_98], 70Bh
0x18004199e  jmp     loc_180041AF8
0x1800419a3  mov     r8, rax; Size
0x1800419a6  lea     rcx, [rsp+0B8h+Sid]; void *
0x1800419ab  add     rdx, rbx; Src
0x1800419ae  call    memcpy_0
0x1800419b3  lea     rcx, [rsp+0B8h+Sid]; Sid
0x1800419b8  call    cs:__imp_RtlValidSid
0x1800419be  test    al, al
0x1800419c0  jnz     short loc_1800419FE
0x1800419c2  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800419c9  mov     ebx, 0C0000078h
0x1800419ce  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800419d3  mov     r9, rax
0x1800419d6  mov     r8d, ebx
0x1800419d9  lea     rax, Class
0x1800419e0  mov     [rsp+0B8h+var_88], rax
0x1800419e5  lea     rax, aInputBufferCon; "Input buffer contains an invalid SID"
0x1800419ec  mov     [rsp+0B8h+var_90], rax
0x1800419f1  mov     [rsp+0B8h+var_98], 718h
0x1800419f9  jmp     loc_180041AF8
0x1800419fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile> `wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl(void)'::`2'::impl
0x180041a05  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180041a0a  call    ?IsLoadAadCredKeyFromProfileEnabled@@YA_NXZ; IsLoadAadCredKeyFromProfileEnabled(void)
0x180041a0f  test    al, al
0x180041a11  jz      short loc_180041A75
0x180041a13  lea     rdx, [rsp+0B8h+var_78]; bool *
0x180041a18  lea     rcx, [rsp+0B8h+Sid]; Sid2
0x180041a1d  call    ?ShouldSkipUserCacheCleanup@@YAJPEAXPEA_N@Z; ShouldSkipUserCacheCleanup(void *,bool *)
0x180041a22  test    eax, eax
0x180041a24  jns     short loc_180041A42
0x180041a26  mov     rcx, [rsp+0B8h]; this
0x180041a2e  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041a35  mov     r9d, eax; char *
0x180041a38  mov     edx, 71Fh; void *
0x180041a3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041a42  cmp     [rsp+0B8h+var_78], 0
0x180041a47  jz      short loc_180041A75
0x180041a49  lea     rcx, [rsp+0B8h+Sid]; void *
0x180041a4e  call    ?_AddSidForDeferredCacheCleanup@@YAJPEAX@Z; _AddSidForDeferredCacheCleanup(void *)
0x180041a53  test    eax, eax
0x180041a55  jns     short loc_180041A7F
0x180041a57  mov     rcx, [rsp+0B8h]; this
0x180041a5f  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041a66  mov     r9d, eax; char *
0x180041a69  mov     edx, 725h; void *
0x180041a6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041a73  jmp     short loc_180041A7F
0x180041a75  lea     rcx, [rsp+0B8h+Sid]; void *
0x180041a7a  call    ?CleanupUserCacheFromPackages@@YAXPEAX@Z; CleanupUserCacheFromPackages(void *)
0x180041a7f  xor     ebx, ebx
0x180041a81  jmp     loc_180041B06
0x180041a86  mov     r8d, 0C000000Dh
0x180041a8c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041a93  mov     ebx, r8d
0x180041a96  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180041a9b  mov     r9, rax
0x180041a9e  lea     rax, Class
0x180041aa5  mov     [rsp+0B8h+var_88], rax
0x180041aaa  lea     rax, aInvalidargPvpr; "InvalidArg:pvProtocolSubmitBuffer"
0x180041ab1  mov     [rsp+0B8h+var_90], rax
0x180041ab6  mov     [rsp+0B8h+var_98], 702h
0x180041abe  jmp     short loc_180041AF8
0x180041ac0  mov     r8d, 0C000000Dh
0x180041ac6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041acd  mov     ebx, r8d
0x180041ad0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180041ad5  mov     r9, rax
0x180041ad8  lea     rax, Class
0x180041adf  mov     [rsp+0B8h+var_88], rax
0x180041ae4  lea     rax, aInvalidargS; "InvalidArg(s)"
0x180041aeb  mov     [rsp+0B8h+var_90], rax
0x180041af0  mov     [rsp+0B8h+var_98], 6EFh
0x180041af8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180041aff  xor     ecx, ecx
0x180041b01  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180041b06  mov     eax, ebx
0x180041b08  mov     rcx, [rsp+0B8h+var_18]
0x180041b10  xor     rcx, rsp; StackCookie
0x180041b13  call    __security_check_cookie
0x180041b18  lea     r11, [rsp+0B8h+var_8]
0x180041b20  mov     rbx, [r11+10h]
0x180041b24  mov     rsi, [r11+18h]
0x180041b28  mov     rsp, r11
0x180041b2b  pop     rdi
0x180041b2c  retn
```
