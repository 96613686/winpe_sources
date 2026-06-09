# GetPregenKeyState(ulong,NgcTimer *,ulong,_NgcPregenState *)

- ea: `0x18001bee8`
- end: `0x18001c079`
- name: `?GetPregenKeyState@@YAJKPEAVNgcTimer@@KPEAU_NgcPregenState@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(int, struct NgcTimer *, unsigned int, struct _NgcPregenState *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019ba4`

## callees

- `0x180007968`
- `0x18000b0fc`
- `0x18000c970`
- `0x18001069c`
- `0x18001a98c`
- `0x18001aae8`
- `0x18001bee8`
- `0x18001c508`

## string_xrefs

- `0x18001bf83`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c008`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c050`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall GetPregenKeyState(int a1, struct NgcTimer *a2, unsigned int a3, struct _NgcPregenState *a4)
{
  struct _PregenParms * near **i; // rdx
  const struct _PregenParms *v7; // rdi
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-58h]
  bool v15; // [rsp+40h] [rbp-38h] BYREF
  bool v16; // [rsp+41h] [rbp-37h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-34h] BYREF
  DelayRetryAction v18; // [rsp+48h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v20[2]; // [rsp+58h] [rbp-20h] BYREF
  __int16 v21; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  struct _NgcPregenState *v23; // [rsp+C8h] [rbp+50h] BYREF

  v23 = a4;
  v17 = 0;
  v20[0] = &v23;
  v20[1] = &v17;
  v21 = 256;
  for ( i = &s_params; ; ++i )
  {
    if ( i >= (struct _PregenParms * near **)&MS_PROVIDER_HFB_Context )
    {
      v13 = 1085;
      goto LABEL_16;
    }
    v7 = (const struct _PregenParms *)*i;
    if ( *(_DWORD *)a4 == *(_DWORD *)*i )
      break;
  }
  while ( 1 )
  {
    v18 = DelayRetryUnknown;
    v15 = 0;
    v8 = ClaimPregenKey(v7, &v18, &v16, 0, a4, &v15);
    v17 = v8;
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x453,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v8,
        v14);
    if ( a3 > *((_DWORD *)v7 + 2) )
      break;
    if ( a3 <= *((_DWORD *)v23 + 1) || !a1 )
    {
      v17 = 0;
      wil::details::ScopeExitFnGuard__lambda_b9d88c87c3dfe66357da8764237ceb95___::operator()(v20);
      return 0;
    }
    v19 = 0;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v19,
      0);
    LOBYTE(v9) = v15;
    v10 = PregenWait(1, v9, v17, *((_QWORD *)v7 + 3));
    v11 = v10;
    v17 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v10,
        a1);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
      goto LABEL_17;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    a4 = v23;
  }
  v13 = 1112;
LABEL_16:
  v11 = -2147024809;
  v17 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)0x80070057LL,
    v14);
LABEL_17:
  wil::details::ScopeExitFnGuard__lambda_b9d88c87c3dfe66357da8764237ceb95___::operator()(v20);
  return v11;
}

```

## disassembly

```asm
0x18001bee8  mov     [rsp-30h+arg_18], r9
0x18001beed  push    rbp
0x18001beee  push    rbx
0x18001beef  push    rsi
0x18001bef0  push    rdi
0x18001bef1  push    r14
0x18001bef3  push    r15
0x18001bef5  mov     rbp, rsp
0x18001bef8  sub     rsp, 78h
0x18001befc  mov     esi, r8d
0x18001beff  mov     r15, rdx
0x18001bf02  mov     r14d, ecx
0x18001bf05  mov     [rbp+var_34], 0
0x18001bf0c  lea     rax, [rbp+arg_18]
0x18001bf10  mov     [rbp+var_20], rax
0x18001bf14  lea     rax, [rbp+var_34]
0x18001bf18  mov     [rbp+var_18], rax
0x18001bf1c  mov     [rbp+var_10], 100h
0x18001bf22  lea     rdx, ?s_params@@3PAPEAU_PregenParms@@A; _PregenParms * near * s_params
0x18001bf29  lea     rax, MS_PROVIDER_HFB_Context
0x18001bf30  cmp     rdx, rax
0x18001bf33  jnb     loc_18001C040
0x18001bf39  mov     rdi, [rdx]
0x18001bf3c  mov     eax, [rdi]
0x18001bf3e  cmp     [r9], eax
0x18001bf41  jz      short loc_18001BF49
0x18001bf43  add     rdx, 8
0x18001bf47  jmp     short loc_18001BF29
0x18001bf49  mov     [rbp+var_30], 0
0x18001bf50  mov     [rbp+var_38], 0
0x18001bf54  lea     rax, [rbp+var_38]
0x18001bf58  mov     [rsp+78h+var_50], rax; bool *
0x18001bf5d  mov     [rsp+78h+var_58], r9; int
0x18001bf62  xor     r9d, r9d; unsigned __int16 **
0x18001bf65  lea     r8, [rbp+var_37]; bool *
0x18001bf69  lea     rdx, [rbp+var_30]; enum DelayRetryAction *
0x18001bf6d  mov     rcx, rdi; struct _PregenParms *
0x18001bf70  call    ?ClaimPregenKey@@YAJPEBU_PregenParms@@PEAW4DelayRetryAction@@PEA_NPEAPEAGPEAU_NgcPregenState@@2@Z; ClaimPregenKey(_PregenParms const *,DelayRetryAction *,bool *,ushort * *,_NgcPregenState *,bool *)
0x18001bf75  mov     [rbp+var_34], eax
0x18001bf78  mov     rcx, [rbp+30h]; this
0x18001bf7c  test    eax, eax
0x18001bf7e  jns     short loc_18001BF94
0x18001bf80  mov     r9d, eax; char *
0x18001bf83  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bf8a  mov     edx, 453h; void *
0x18001bf8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bf94  cmp     esi, [rdi+8]
0x18001bf97  ja      loc_18001C039
0x18001bf9d  mov     rax, [rbp+arg_18]
0x18001bfa1  cmp     esi, [rax+4]
0x18001bfa4  jbe     short loc_18001C025
0x18001bfa6  test    r14d, r14d
0x18001bfa9  jz      short loc_18001C025
0x18001bfab  mov     [rbp+var_28], 0
0x18001bfb3  xor     edx, edx
0x18001bfb5  lea     rcx, [rbp+var_28]
0x18001bfb9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001bfbe  lea     rax, [rbp+var_28]
0x18001bfc2  mov     [rsp+78h+var_48], rax
0x18001bfc7  mov     [rsp+78h+var_50], r15
0x18001bfcc  mov     dword ptr [rsp+78h+var_58], r14d; int
0x18001bfd1  mov     r9, [rdi+18h]
0x18001bfd5  mov     r8d, [rbp+var_34]
0x18001bfd9  mov     dl, [rbp+var_38]
0x18001bfdc  mov     ecx, 1
0x18001bfe1  call    ?PregenWait@@YAJW4PregenTaskType@@_NJPEBGKPEAVNgcTimer@@PEAPEAX@Z; PregenWait(PregenTaskType,bool,long,ushort const *,ulong,NgcTimer *,void * *)
0x18001bfe6  mov     ebx, eax
0x18001bfe8  mov     [rbp+var_34], eax
0x18001bfeb  test    eax, eax
0x18001bfed  js      short loc_18001C001
0x18001bfef  lea     rcx, [rbp+var_28]
0x18001bff3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bff8  mov     r9, [rbp+arg_18]
0x18001bffc  jmp     loc_18001BF49
0x18001c001  mov     rcx, [rbp+30h]; this
0x18001c005  mov     r9d, eax; char *
0x18001c008  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c00f  mov     edx, 46Ah; void *
0x18001c014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c019  nop
0x18001c01a  lea     rcx, [rbp+var_28]
0x18001c01e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c023  jmp     short loc_18001C061
0x18001c025  mov     [rbp+var_34], 0
0x18001c02c  lea     rcx, [rbp+var_20]
0x18001c030  call    wil__details__ScopeExitFnGuard__lambda_b9d88c87c3dfe66357da8764237ceb95_____operator__
0x18001c035  xor     eax, eax
0x18001c037  jmp     short loc_18001C06C
0x18001c039  mov     edx, 458h
0x18001c03e  jmp     short loc_18001C045
0x18001c040  mov     edx, 43Dh; void *
0x18001c045  mov     ebx, 80070057h
0x18001c04a  mov     [rbp+var_34], ebx
0x18001c04d  mov     r9d, ebx; char *
0x18001c050  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c057  mov     rcx, [rbp+30h]; this
0x18001c05b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c060  nop
0x18001c061  lea     rcx, [rbp+var_20]
0x18001c065  call    wil__details__ScopeExitFnGuard__lambda_b9d88c87c3dfe66357da8764237ceb95_____operator__
0x18001c06a  mov     eax, ebx
0x18001c06c  add     rsp, 78h
0x18001c070  pop     r15
0x18001c072  pop     r14
0x18001c074  pop     rdi
0x18001c075  pop     rsi
0x18001c076  pop     rbx
0x18001c077  pop     rbp
0x18001c078  retn
```
