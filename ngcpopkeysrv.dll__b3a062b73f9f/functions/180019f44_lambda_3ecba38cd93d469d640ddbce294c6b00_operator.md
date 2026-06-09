# _lambda_3ecba38cd93d469d640ddbce294c6b00_::operator()

- ea: `0x180019f44`
- end: `0x18001a116`
- name: `_lambda_3ecba38cd93d469d640ddbce294c6b00_::operator()`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019718`

## callees

- `0x180007968`
- `0x18000b0fc`
- `0x18000c970`
- `0x18001069c`
- `0x180019f44`
- `0x18001aae8`
- `0x18001c508`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a07b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a07b`

## string_xrefs

- `0x180019f73`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001a03d`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001a0e6`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_3ecba38cd93d469d640ddbce294c6b00_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  unsigned int v3; // ebx
  _DWORD *v5; // rcx
  int v6; // edx
  int v7; // edx
  void *v8; // rdi
  unsigned int v9; // r12d
  int v10; // eax
  int v11; // r14d
  const unsigned __int16 *v12; // r15
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD TickCount; // [rsp+80h] [rbp+40h] BYREF
  bool v19; // [rsp+88h] [rbp+48h] BYREF
  void *v20; // [rsp+90h] [rbp+50h] BYREF

  if ( !**(_QWORD **)a1 )
  {
    v2 = 642;
    goto LABEL_3;
  }
  v5 = **(_DWORD ***)(a1 + 8);
  if ( v5 )
  {
    *v5 = 0;
  }
  else if ( **(_DWORD **)(a1 + 16) == 1 )
  {
    v2 = 643;
LABEL_3:
    v3 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)v3,
      v15);
    return v3;
  }
  ***(_QWORD ***)a1 = 0;
  while ( 1 )
  {
    v6 = **(_DWORD **)(a1 + 16);
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 != 4 )
        {
          v3 = -2147024809;
          v2 = 705;
          goto LABEL_4;
        }
        v8 = &s_pregenParamsTokenBindingAik;
      }
      else
      {
        v8 = &s_pregenParamsAik;
      }
    }
    else
    {
      v8 = &s_pregenParamsSk;
      **(_QWORD **)(a1 + 8) = 0;
    }
    v9 = 1;
    LOBYTE(TickCount) = 0;
    v19 = 0;
    v10 = ClaimPregenKey(
            (const struct _PregenParms *)v8,
            **(enum DelayRetryAction ***)(a1 + 8),
            (bool *)&TickCount,
            **(unsigned __int16 ****)a1,
            0,
            &v19);
    v11 = v10;
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CE,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v10,
        v16);
    v12 = (const unsigned __int16 *)*((_QWORD *)v8 + 3);
    if ( *(_DWORD *)v8 == 1 )
    {
      if ( (_BYTE)TickCount )
      {
        v12 = L"AIKCertEnroll";
        v9 = 2;
      }
    }
    if ( v11 >= 0 )
      return 0;
    v20 = 0;
    TickCount = GetTickCount();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v20,
      0);
    v13 = PregenWait(v9, v19, v11, v12, **(_DWORD **)(a1 + 24), (int *)&TickCount, &v20);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v13,
        v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
      return v14;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  }
}

```

## disassembly

```asm
0x180019f44  push    rbp
0x180019f46  push    rbx
0x180019f47  push    rsi
0x180019f48  push    rdi
0x180019f49  push    r12
0x180019f4b  push    r14
0x180019f4d  push    r15
0x180019f4f  mov     rbp, rsp
0x180019f52  sub     rsp, 40h
0x180019f56  mov     rbx, rcx
0x180019f59  mov     rax, [rcx]
0x180019f5c  cmp     qword ptr [rax], 0
0x180019f60  jnz     short loc_180019F86
0x180019f62  mov     edx, 282h; void *
0x180019f67  mov     ebx, 80004003h
0x180019f6c  mov     rcx, [rbp+38h]; this
0x180019f70  mov     r9d, ebx; char *
0x180019f73  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f7f  mov     eax, ebx
0x180019f81  jmp     loc_18001A107
0x180019f86  mov     rax, [rcx+8]
0x180019f8a  mov     rcx, [rax]
0x180019f8d  test    rcx, rcx
0x180019f90  jnz     short loc_180019FA7
0x180019f92  mov     rax, [rbx+10h]
0x180019f96  cmp     dword ptr [rax], 1
0x180019f99  jnz     short loc_180019FA2
0x180019f9b  mov     edx, 283h
0x180019fa0  jmp     short loc_180019F67
0x180019fa2  test    rcx, rcx
0x180019fa5  jz      short loc_180019FAD
0x180019fa7  mov     dword ptr [rcx], 0
0x180019fad  mov     rax, [rbx]
0x180019fb0  mov     rcx, [rax]
0x180019fb3  mov     qword ptr [rcx], 0
0x180019fba  mov     rcx, [rbx+10h]
0x180019fbe  mov     edx, [rcx]
0x180019fc0  test    edx, edx
0x180019fc2  jz      short loc_180019FE4
0x180019fc4  sub     edx, 1
0x180019fc7  jz      short loc_180019FDB
0x180019fc9  cmp     edx, 4
0x180019fcc  jnz     loc_18001A0D0
0x180019fd2  lea     rdi, ?s_pregenParamsTokenBindingAik@@3U_PregenParms@@A; _PregenParms s_pregenParamsTokenBindingAik
0x180019fd9  jmp     short loc_180019FF6
0x180019fdb  lea     rdi, ?s_pregenParamsAik@@3U_PregenParms@@A; _PregenParms s_pregenParamsAik
0x180019fe2  jmp     short loc_180019FF6
0x180019fe4  lea     rdi, ?s_pregenParamsSk@@3U_PregenParms@@A; _PregenParms s_pregenParamsSk
0x180019feb  mov     rax, [rbx+8]
0x180019fef  mov     qword ptr [rax], 0
0x180019ff6  mov     r12d, 1
0x180019ffc  mov     byte ptr [rbp+arg_0], 0
0x18001a000  mov     [rbp+arg_8], 0
0x18001a004  mov     r9, [rbx]
0x18001a007  mov     rdx, [rbx+8]
0x18001a00b  lea     rax, [rbp+arg_8]
0x18001a00f  mov     [rsp+40h+var_18], rax; bool *
0x18001a014  mov     [rsp+40h+var_20], 0; int
0x18001a01d  mov     r9, [r9]; unsigned __int16 **
0x18001a020  lea     r8, [rbp+arg_0]; bool *
0x18001a024  mov     rdx, [rdx]; enum DelayRetryAction *
0x18001a027  mov     rcx, rdi; struct _PregenParms *
0x18001a02a  call    ?ClaimPregenKey@@YAJPEBU_PregenParms@@PEAW4DelayRetryAction@@PEA_NPEAPEAGPEAU_NgcPregenState@@2@Z; ClaimPregenKey(_PregenParms const *,DelayRetryAction *,bool *,ushort * *,_NgcPregenState *,bool *)
0x18001a02f  mov     r14d, eax
0x18001a032  mov     rcx, [rbp+38h]; this
0x18001a036  test    eax, eax
0x18001a038  jns     short loc_18001A04E
0x18001a03a  mov     r9d, eax; char *
0x18001a03d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a044  mov     edx, 2CEh; void *
0x18001a049  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a04e  mov     r15, [rdi+18h]
0x18001a052  cmp     [rdi], r12d
0x18001a055  jnz     short loc_18001A06A
0x18001a057  cmp     byte ptr [rbp+arg_0], 0
0x18001a05b  jz      short loc_18001A06A
0x18001a05d  lea     r15, aAikcertenroll; "AIKCertEnroll"
0x18001a064  mov     r12d, 2
0x18001a06a  test    r14d, r14d
0x18001a06d  jns     loc_18001A105
0x18001a073  mov     [rbp+arg_10], 0
0x18001a07b  call    cs:__imp_GetTickCount
0x18001a081  mov     [rbp+arg_0], eax
0x18001a084  xor     edx, edx
0x18001a086  lea     rcx, [rbp+arg_10]
0x18001a08a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001a08f  mov     rax, [rbx+18h]
0x18001a093  lea     rcx, [rbp+arg_10]
0x18001a097  mov     [rsp+40h+var_10], rcx
0x18001a09c  lea     rcx, [rbp+arg_0]
0x18001a0a0  mov     [rsp+40h+var_18], rcx
0x18001a0a5  mov     eax, [rax]
0x18001a0a7  mov     dword ptr [rsp+40h+var_20], eax; int
0x18001a0ab  mov     r9, r15
0x18001a0ae  mov     r8d, r14d
0x18001a0b1  mov     dl, [rbp+arg_8]
0x18001a0b4  mov     ecx, r12d
0x18001a0b7  call    ?PregenWait@@YAJW4PregenTaskType@@_NJPEBGKPEAVNgcTimer@@PEAPEAX@Z; PregenWait(PregenTaskType,bool,long,ushort const *,ulong,NgcTimer *,void * *)
0x18001a0bc  mov     edi, eax
0x18001a0be  test    eax, eax
0x18001a0c0  js      short loc_18001A0DF
0x18001a0c2  lea     rcx, [rbp+arg_10]
0x18001a0c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a0cb  jmp     loc_180019FBA
0x18001a0d0  mov     ebx, 80070057h
0x18001a0d5  mov     edx, 2C1h
0x18001a0da  jmp     loc_180019F6C
0x18001a0df  mov     rcx, [rbp+38h]; this
0x18001a0e3  mov     r9d, edi; char *
0x18001a0e6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a0ed  mov     edx, 2E6h; void *
0x18001a0f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0f7  nop
0x18001a0f8  lea     rcx, [rbp+arg_10]
0x18001a0fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a101  mov     eax, edi
0x18001a103  jmp     short loc_18001A107
0x18001a105  xor     eax, eax
0x18001a107  add     rsp, 40h
0x18001a10b  pop     r15
0x18001a10d  pop     r14
0x18001a10f  pop     r12
0x18001a111  pop     rdi
0x18001a112  pop     rsi
0x18001a113  pop     rbx
0x18001a114  pop     rbp
0x18001a115  retn
```
