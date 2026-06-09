# CreateAppContainerWorker(ushort const *,_APPCONTAINER_POLICY *,void * *)

- ea: `0x18001dcb0`
- end: `0x18001de3a`
- name: `?CreateAppContainerWorker@@YAJPEBGPEAU_APPCONTAINER_POLICY@@PEAPEAX@Z`
- size: `394`
- prototype: `__int64 __fastcall(char *, struct _APPCONTAINER_POLICY *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001dbe0`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x18001d834`
- `0x18001d8ec`
- `0x18001dcb0`
- `0x18001e520`
- `0x18001f390`

## string_xrefs

- `0x18001dce2`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001dd74`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001dde2`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001ddd3`: `Failed to create AppContainer profile for %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateAppContainerWorker(char *a1, struct _APPCONTAINER_POLICY *a2, void **a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  int appended; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // ecx
  void *v12; // rax
  int v14; // [rsp+20h] [rbp-50h]
  unsigned int v15; // [rsp+30h] [rbp-40h]
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  struct _SID_AND_ATTRIBUTES *v17[2]; // [rsp+50h] [rbp-20h]
  __int128 v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  void *v20; // [rsp+90h] [rbp+20h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v6 = 47;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v6 = 48;
      goto LABEL_3;
    }
    v16 = 0;
    *(_OWORD *)v17 = 0;
    v18 = 0;
    appended = LpacCapabilityStore::AppendCapabilityArray(
                 (LpacCapabilityStore *)&v16,
                 *((const struct _APPCONTAINER_CAPABILITY **)a2 + 1),
                 *(_DWORD *)a2);
    v7 = appended;
    if ( appended < 0 )
    {
      v9 = (unsigned int)appended;
      v10 = 55;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
        (const char *)v9,
        v14);
LABEL_19:
      LpacCapabilityStore::~LpacCapabilityStore((LpacCapabilityStore *)&v16);
      return (unsigned int)v7;
    }
    v11 = *((_DWORD *)a2 + 6);
    if ( v11 )
    {
      if ( v11 != 1 )
      {
        v7 = -2147024809;
LABEL_14:
        v9 = (unsigned int)v7;
        v10 = 56;
        goto LABEL_15;
      }
      v7 = LpacCapabilityStore::AppendCapabilityArray(
             (LpacCapabilityStore *)&v16,
             (const struct _APPCONTAINER_CAPABILITY *)&LpacCapabilityStore::m_IpcCapabilitiesComRpc,
             2u);
      if ( v7 < 0 )
        goto LABEL_14;
    }
    v20 = 0;
    v7 = LpacRegHelper::CreateLpacProfile(
           a1,
           (const unsigned __int16 *)a1,
           (const unsigned __int16 *)a1,
           v17[1],
           (__int64)(v18 - (unsigned __int64)v17[1]) >> 4,
           *((const unsigned __int64 **)a2 + 2),
           v15,
           &v20);
    if ( v7 >= 0 )
    {
      v12 = v20;
      v20 = 0;
      *a3 = v12;
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
        (const char *)(unsigned int)v7,
        (int)"Failed to create AppContainer profile for %ls",
        a1);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
    }
    goto LABEL_19;
  }
  v6 = 46;
LABEL_3:
  v7 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
    (const char *)0x80070057LL,
    v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001dcb0  mov     [rsp-18h+arg_8], rbx
0x18001dcb5  mov     [rsp-18h+arg_10], rsi
0x18001dcba  push    rbp
0x18001dcbb  push    rdi
0x18001dcbc  push    r14
0x18001dcbe  mov     rbp, rsp
0x18001dcc1  sub     rsp, 70h
0x18001dcc5  mov     r14, r8
0x18001dcc8  mov     rdi, rdx
0x18001dccb  mov     rsi, rcx
0x18001dcce  test    rcx, rcx
0x18001dcd1  jnz     short loc_18001DCF3
0x18001dcd3  lea     edx, [rcx+2Eh]; void *
0x18001dcd6  mov     ebx, 80070057h
0x18001dcdb  mov     rcx, [rbp+18h]; this
0x18001dcdf  mov     r9d, ebx; char *
0x18001dce2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcee  jmp     loc_18001DE22
0x18001dcf3  test    rdi, rdi
0x18001dcf6  jnz     short loc_18001DCFD
0x18001dcf8  lea     edx, [rdi+2Fh]
0x18001dcfb  jmp     short loc_18001DCD6
0x18001dcfd  test    r14, r14
0x18001dd00  jnz     short loc_18001DD08
0x18001dd02  lea     edx, [r14+30h]
0x18001dd06  jmp     short loc_18001DCD6
0x18001dd08  xorps   xmm0, xmm0
0x18001dd0b  movdqu  [rbp+var_30], xmm0
0x18001dd10  xorps   xmm1, xmm1
0x18001dd13  movdqu  xmmword ptr [rbp+var_20], xmm1
0x18001dd18  movdqu  [rbp+var_10], xmm0
0x18001dd1d  mov     r8d, [rdx]; unsigned int
0x18001dd20  mov     rdx, [rdx+8]; struct _APPCONTAINER_CAPABILITY *
0x18001dd24  lea     rcx, [rbp+var_30]; this
0x18001dd28  call    ?AppendCapabilityArray@LpacCapabilityStore@@QEAAJPEBU_APPCONTAINER_CAPABILITY@@K@Z; LpacCapabilityStore::AppendCapabilityArray(_APPCONTAINER_CAPABILITY const *,ulong)
0x18001dd2d  mov     ebx, eax
0x18001dd2f  test    eax, eax
0x18001dd31  jns     short loc_18001DD3D
0x18001dd33  mov     r9d, eax
0x18001dd36  mov     edx, 37h ; '7'
0x18001dd3b  jmp     short loc_18001DD74
0x18001dd3d  mov     ecx, [rdi+18h]
0x18001dd40  test    ecx, ecx
0x18001dd42  jz      short loc_18001DD89
0x18001dd44  cmp     ecx, 1
0x18001dd47  jz      short loc_18001DD50
0x18001dd49  mov     ebx, 80070057h
0x18001dd4e  jmp     short loc_18001DD6C
0x18001dd50  mov     r8d, 2; unsigned int
0x18001dd56  lea     rdx, ?m_IpcCapabilitiesComRpc@LpacCapabilityStore@@0QBU_APPCONTAINER_CAPABILITY@@B; struct _APPCONTAINER_CAPABILITY *
0x18001dd5d  lea     rcx, [rbp+var_30]; this
0x18001dd61  call    ?AppendCapabilityArray@LpacCapabilityStore@@QEAAJPEBU_APPCONTAINER_CAPABILITY@@K@Z; LpacCapabilityStore::AppendCapabilityArray(_APPCONTAINER_CAPABILITY const *,ulong)
0x18001dd66  mov     ebx, eax
0x18001dd68  test    eax, eax
0x18001dd6a  jns     short loc_18001DD89
0x18001dd6c  mov     r9d, ebx; char *
0x18001dd6f  mov     edx, 38h ; '8'; void *
0x18001dd74  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dd7b  mov     rcx, [rbp+18h]; this
0x18001dd7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd84  jmp     loc_18001DE19
0x18001dd89  mov     [rbp+arg_0], 0
0x18001dd91  mov     r9, [rbp+var_20+8]; struct _SID_AND_ATTRIBUTES *
0x18001dd95  mov     rcx, qword ptr [rbp+var_10]
0x18001dd99  sub     rcx, r9
0x18001dd9c  sar     rcx, 4
0x18001dda0  lea     rax, [rbp+arg_0]
0x18001dda4  mov     [rsp+70h+var_38], rax; void **
0x18001dda9  mov     rax, [rdi+10h]
0x18001ddad  mov     [rsp+70h+var_48], rax; unsigned __int64 *
0x18001ddb2  mov     [rsp+70h+var_50], ecx; unsigned int
0x18001ddb6  mov     r8, rsi; unsigned __int16 *
0x18001ddb9  mov     rdx, rsi; unsigned __int16 *
0x18001ddbc  mov     rcx, rsi; char *
0x18001ddbf  call    ?CreateLpacProfile@LpacRegHelper@@SAJPEBG00PEAU_SID_AND_ATTRIBUTES@@KPEB_KKPEAPEAX@Z; LpacRegHelper::CreateLpacProfile(ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,unsigned __int64 const *,ulong,void * *)
0x18001ddc4  mov     ebx, eax
0x18001ddc6  test    eax, eax
0x18001ddc8  jns     short loc_18001DDFF
0x18001ddca  mov     rcx, [rbp+18h]; this
0x18001ddce  mov     [rsp+70h+var_48], rsi; char *
0x18001ddd3  lea     rax, aFailedToCreate; "Failed to create AppContainer profile f"...
0x18001ddda  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001dddf  mov     r9d, ebx; char *
0x18001dde2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dde9  mov     edx, 48h ; 'H'; void *
0x18001ddee  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ddf3  nop
0x18001ddf4  lea     rcx, [rbp+arg_0]
0x18001ddf8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ddfd  jmp     short loc_18001DE19
0x18001ddff  mov     rax, [rbp+arg_0]
0x18001de03  mov     [rbp+arg_0], 0
0x18001de0b  mov     [r14], rax
0x18001de0e  lea     rcx, [rbp+arg_0]
0x18001de12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001de17  xor     ebx, ebx
0x18001de19  lea     rcx, [rbp+var_30]; this
0x18001de1d  call    ??1LpacCapabilityStore@@QEAA@XZ; LpacCapabilityStore::~LpacCapabilityStore(void)
0x18001de22  mov     eax, ebx
0x18001de24  lea     r11, [rsp+70h+var_s0]
0x18001de29  mov     rbx, [r11+28h]
0x18001de2d  mov     rsi, [r11+30h]
0x18001de31  mov     rsp, r11
0x18001de34  pop     r14
0x18001de36  pop     rdi
0x18001de37  pop     rbp
0x18001de38  retn
```
