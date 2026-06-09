# NgcKeyTransportKey::CreateKeyAndAddNewKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180018eec`
- end: `0x1800190c0`
- name: `?CreateKeyAndAddNewKeyMapping@NgcKeyTransportKey@@AEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `468`
- prototype: `__int64 __fastcall(NgcKeyTransportKey *this, NgcUtils **, NgcUtils *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012858`

## callees

- `0x18000671c`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x1800177f4`
- `0x180018e60`
- `0x180018eec`
- `0x180022ef4`
- `0x18002336c`
- `0x180028010`

## string_xrefs

- `0x180018f6d`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180018fd4`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180019019`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcKeyTransportKey::CreateKeyAndAddNewKeyMapping(
        NgcKeyTransportKey *this,
        NgcUtils **a2,
        NgcUtils *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        unsigned int a5)
{
  unsigned __int16 **v9; // r15
  const unsigned __int16 *v10; // rdx
  NgcUtils *v11; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned __int16 **v15; // rcx
  __int64 (__fastcall *v16)(NgcKeyTransportKey *, LPVOID, _QWORD, __int64 *); // rbx
  LPVOID lpSecurityDescriptor; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rsi
  struct _SECURITY_ATTRIBUTES *v23; // rax
  int v24; // eax
  __int64 v25; // rax
  unsigned __int16 **v27; // [rsp+20h] [rbp-48h]
  unsigned __int8 *v28; // [rsp+30h] [rbp-38h]
  unsigned int v29; // [rsp+38h] [rbp-30h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-28h] BYREF
  __int64 v31; // [rsp+48h] [rbp-20h] BYREF
  __int16 v32; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  __int64 v34; // [rsp+B0h] [rbp+48h] BYREF

  v9 = (unsigned __int16 **)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
    goto LABEL_8;
  v30 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v30,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v11,
                                        v10,
                                        L"KeyTransportKey",
                                        (const unsigned __int16 *)&v30,
                                        v27);
  v13 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    NgcStateSeparatedRegistryLocation = GetPopRegLocationForKeyMapping(a2, a3, v30, L"PerDeviceKeyTransportKey", v9);
    v13 = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation < 0 )
    {
      v14 = 174;
      goto LABEL_6;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
LABEL_8:
    v34 = 0;
    v16 = *(__int64 (__fastcall **)(NgcKeyTransportKey *, LPVOID, _QWORD, __int64 *))(*(_QWORD *)this + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    if ( a4 )
      lpSecurityDescriptor = a4->lpSecurityDescriptor;
    else
      lpSecurityDescriptor = 0;
    v18 = v16(this, lpSecurityDescriptor, a5, &v34);
    v13 = v18;
    if ( v18 >= 0 )
    {
      v31 = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                         &v30,
                         this);
      v32 = 256;
      v19 = v34;
      if ( v34 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v34 + 2 * v22) );
        v23 = (struct _SECURITY_ATTRIBUTES *)(*(__int64 (__fastcall **)(NgcKeyTransportKey *))(*(_QWORD *)this + 24LL))(this);
        LODWORD(v28) = 2 * v22 + 2;
        LODWORD(v27) = 1;
        v24 = NgcUtils::SetRegistryValue(
                (NgcUtils *)(unsigned int)v28,
                (HKEY)*v9,
                (const unsigned __int16 *)a4,
                v23,
                (const unsigned __int16 *)v27,
                v19,
                v28,
                v29);
        v13 = v24;
        if ( v24 >= 0 )
        {
          HIBYTE(v32) = 0;
          v25 = v34;
          v34 = 0;
          *((_QWORD *)this + 4) = v25;
          wil::details::ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6___::operator()(&v31);
          v13 = 0;
          goto LABEL_21;
        }
        v20 = (unsigned int)v24;
        v21 = 202;
      }
      else
      {
        v13 = -2147467261;
        v20 = 2147500035LL;
        v21 = 193;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)v20,
        (int)v27);
      wil::details::ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6___::operator()(&v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v18,
        (int)v27);
    }
LABEL_21:
    v15 = (unsigned __int16 **)&v34;
    goto LABEL_22;
  }
  v14 = 167;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    (int)v27);
  v15 = &v30;
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
  return v13;
}

```

## disassembly

```asm
0x180018eec  push    rbp
0x180018eee  push    rbx
0x180018eef  push    rsi
0x180018ef0  push    rdi
0x180018ef1  push    r12
0x180018ef3  push    r13
0x180018ef5  push    r14
0x180018ef7  push    r15
0x180018ef9  mov     rbp, rsp
0x180018efc  sub     rsp, 68h
0x180018f00  mov     r14, r9
0x180018f03  mov     rsi, r8
0x180018f06  mov     r12, rdx
0x180018f09  mov     rdi, rcx
0x180018f0c  lea     r15, [rcx+18h]
0x180018f10  xor     r13d, r13d
0x180018f13  cmp     [r15], r13
0x180018f16  jnz     short loc_180018F90
0x180018f18  mov     [rbp+var_28], r13
0x180018f1c  xor     edx, edx
0x180018f1e  lea     rcx, [rbp+var_28]
0x180018f22  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018f27  lea     r9, [rbp+var_28]; unsigned __int16 *
0x180018f2b  lea     r8, aKeytransportke; "KeyTransportKey"
0x180018f32  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180018f37  mov     ebx, eax
0x180018f39  test    eax, eax
0x180018f3b  jns     short loc_180018F44
0x180018f3d  mov     edx, 0A7h
0x180018f42  jmp     short loc_180018F6A
0x180018f44  mov     [rsp+68h+var_48], r15; int
0x180018f49  lea     r9, aPerdevicekeytr; "PerDeviceKeyTransportKey"
0x180018f50  mov     r8, [rbp+var_28]; unsigned __int16 *
0x180018f54  mov     rdx, rsi; unsigned __int16 *
0x180018f57  mov     rcx, r12; struct _NGC_IDP_ACCOUNT_INFO *
0x180018f5a  call    ?GetPopRegLocationForKeyMapping@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG11PEAPEAG@Z; GetPopRegLocationForKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ushort const *,ushort const *,ushort * *)
0x180018f5f  mov     ebx, eax
0x180018f61  test    eax, eax
0x180018f63  jns     short loc_180018F87
0x180018f65  mov     edx, 0AEh; void *
0x180018f6a  mov     r9d, eax; char *
0x180018f6d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018f74  mov     rcx, [rbp+40h]; this
0x180018f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f7d  nop
0x180018f7e  lea     rcx, [rbp+var_28]
0x180018f82  jmp     loc_1800190A8
0x180018f87  lea     rcx, [rbp+var_28]
0x180018f8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018f90  mov     [rbp+arg_0], r13
0x180018f94  mov     rax, [rdi]
0x180018f97  mov     rbx, [rax+28h]
0x180018f9b  xor     edx, edx
0x180018f9d  lea     rcx, [rbp+arg_0]
0x180018fa1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018fa6  test    r14, r14
0x180018fa9  jz      short loc_180018FB1
0x180018fab  mov     rdx, [r14+8]
0x180018faf  jmp     short loc_180018FB4
0x180018fb1  mov     rdx, r13
0x180018fb4  lea     r9, [rbp+arg_0]
0x180018fb8  mov     r8d, [rbp+arg_20]
0x180018fbc  mov     rcx, rdi
0x180018fbf  mov     rax, rbx
0x180018fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fc7  mov     ebx, eax
0x180018fc9  test    eax, eax
0x180018fcb  jns     short loc_180018FEA
0x180018fcd  mov     rcx, [rbp+40h]; this
0x180018fd1  mov     r9d, eax; char *
0x180018fd4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018fdb  mov     edx, 0B5h; void *
0x180018fe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fe5  jmp     loc_1800190A4
0x180018fea  mov     rdx, rdi
0x180018fed  lea     rcx, [rbp+var_28]
0x180018ff1  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180018ff6  mov     rcx, [rax]
0x180018ff9  mov     [rbp+var_20], rcx
0x180018ffd  mov     [rbp+var_18], 100h
0x180019003  mov     rbx, [rbp+arg_0]
0x180019007  test    rbx, rbx
0x18001900a  jnz     short loc_180019035
0x18001900c  mov     ebx, 80004003h
0x180019011  mov     r9d, ebx; char *
0x180019014  mov     edx, 0C1h; void *
0x180019019  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019020  mov     rcx, [rbp+40h]; this
0x180019024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019029  nop
0x18001902a  lea     rcx, [rbp+var_20]
0x18001902e  call    wil__details__ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6_____operator__
0x180019033  jmp     short loc_1800190A4
0x180019035  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180019039  inc     rsi
0x18001903c  cmp     [rbx+rsi*2], r13w
0x180019041  jnz     short loc_180019039
0x180019043  mov     rax, [rdi]
0x180019046  mov     rcx, rdi
0x180019049  mov     rax, [rax+18h]
0x18001904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019052  lea     ecx, ds:2[rsi*2]; this
0x180019059  mov     dword ptr [rsp+68h+var_38], ecx; unsigned __int8 *
0x18001905d  mov     qword ptr [rsp+68h+var_40], rbx; unsigned int
0x180019062  mov     dword ptr [rsp+68h+var_48], 1; unsigned __int16 *
0x18001906a  mov     r9, rax; struct _SECURITY_ATTRIBUTES *
0x18001906d  mov     r8, r14; unsigned __int16 *
0x180019070  mov     rdx, [r15]; HKEY
0x180019073  call    ?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z; NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)
0x180019078  mov     ebx, eax
0x18001907a  test    eax, eax
0x18001907c  jns     short loc_180019088
0x18001907e  mov     r9d, eax
0x180019081  mov     edx, 0CAh
0x180019086  jmp     short loc_180019019
0x180019088  mov     byte ptr [rbp+var_18+1], r13b
0x18001908c  mov     rax, [rbp+arg_0]
0x180019090  mov     [rbp+arg_0], r13
0x180019094  mov     [rdi+20h], rax
0x180019098  lea     rcx, [rbp+var_20]
0x18001909c  call    wil__details__ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6_____operator__
0x1800190a1  mov     ebx, r13d
0x1800190a4  lea     rcx, [rbp+arg_0]
0x1800190a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800190ad  mov     eax, ebx
0x1800190af  add     rsp, 68h
0x1800190b3  pop     r15
0x1800190b5  pop     r14
0x1800190b7  pop     r13
0x1800190b9  pop     r12
0x1800190bb  pop     rdi
0x1800190bc  pop     rsi
0x1800190bd  pop     rbx
0x1800190be  pop     rbp
0x1800190bf  retn
```
