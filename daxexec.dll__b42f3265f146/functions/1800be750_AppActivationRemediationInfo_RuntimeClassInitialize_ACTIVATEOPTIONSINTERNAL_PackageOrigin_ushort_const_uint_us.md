# AppActivationRemediationInfo::RuntimeClassInitialize(ACTIVATEOPTIONSINTERNAL,_PackageOrigin,ushort const *,uint,ushort const *,unsigned __int64,IInspectable *,ACTIVATION_PHASE,uchar,uchar)

- ea: `0x1800be750`
- end: `0x1800be97e`
- name: `?RuntimeClassInitialize@AppActivationRemediationInfo@@QEAAJW4ACTIVATEOPTIONSINTERNAL@@W4_PackageOrigin@@PEBGI2_KPEAUIInspectable@@W4ACTIVATION_PHASE@@EE@Z`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bdb14`

## callees

- `0x18000ff24`
- `0x18002b6a8`
- `0x1800be750`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be7bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be876`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be7bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be7b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be7dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be7b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be7dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be893`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800be93a`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800be93a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppActivationRemediationInfo::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10,
        char a11)
{
  void **v13; // rsi
  LPVOID v14; // r14
  void *v15; // rbp
  DWORD LastError; // ebx
  void *v17; // rcx
  __int64 v18; // rdx
  int AgileReference; // ebx
  void **v20; // rsi
  LPVOID v21; // r14
  void *v22; // rbp
  DWORD v23; // ebx
  void *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  LPVOID v28[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a4 )
    return 2147942487LL;
  *(_DWORD *)(a1 + 56) = a2;
  *(_DWORD *)(a1 + 60) = a3;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    a4,
    -1);
  v13 = (void **)(a1 + 72);
  if ( (LPVOID *)(a1 + 72) == &pv )
  {
    v17 = pv;
  }
  else
  {
    v14 = pv;
    v15 = *v13;
    if ( *v13 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v15);
      SetLastError(LastError);
    }
    *v13 = v14;
    v17 = 0;
  }
  if ( v17 )
    CoTaskMemFree(v17);
  if ( !*v13 )
  {
    v18 = 42;
LABEL_12:
    AgileReference = -2147024882;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\private\\base\\inc\\appmodel\\execmodel\\appactivationremediationinfo.h",
      (const char *)(unsigned int)AgileReference,
      (int)pv);
    return (unsigned int)AgileReference;
  }
  *(_DWORD *)(a1 + 64) = a5;
  if ( a6 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v28,
      a6,
      -1);
    v20 = (void **)(a1 + 80);
    if ( (LPVOID *)(a1 + 80) == v28 )
    {
      v24 = v28[0];
    }
    else
    {
      v21 = v28[0];
      v22 = *v20;
      if ( *v20 )
      {
        v23 = GetLastError();
        CoTaskMemFree(v22);
        SetLastError(v23);
      }
      *v20 = v21;
      v24 = 0;
    }
    if ( v24 )
      CoTaskMemFree(v24);
    if ( !*v20 )
    {
      v18 = 47;
      goto LABEL_12;
    }
  }
  *(_QWORD *)(a1 + 88) = a7;
  *(_DWORD *)(a1 + 104) = a9;
  *(_BYTE *)(a1 + 108) = a10 != 0;
  *(_BYTE *)(a1 + 109) = a11 != 0;
  v25 = *(_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 96) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = *(_QWORD *)(a1 + 96);
  if ( a8 )
  {
    if ( v26 )
    {
      *(_QWORD *)(a1 + 96) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    AgileReference = RoGetAgileReference(0, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a8, a1 + 96);
    if ( AgileReference < 0 )
    {
      v18 = 54;
      goto LABEL_13;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 96) = 0;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x1800be750  push    rbx
0x1800be752  push    rbp
0x1800be753  push    rsi
0x1800be754  push    rdi
0x1800be755  push    r14
0x1800be757  sub     rsp, 30h
0x1800be75b  mov     rdi, rcx
0x1800be75e  test    r9, r9
0x1800be761  jnz     short loc_1800BE76D
0x1800be763  mov     eax, 80070057h
0x1800be768  jmp     loc_1800BE972
0x1800be76d  mov     [rcx+38h], edx
0x1800be770  mov     [rcx+3Ch], r8d
0x1800be774  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800be778  mov     rdx, r9
0x1800be77b  lea     rcx, [rsp+58h+pv]
0x1800be780  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800be785  lea     rsi, [rdi+48h]
0x1800be789  lea     rax, [rsp+58h+pv]
0x1800be78e  cmp     rsi, rax
0x1800be791  jz      short loc_1800BE7D2
0x1800be793  mov     r14, [rsp+58h+pv]
0x1800be798  mov     rbp, [rsi]
0x1800be79b  test    rbp, rbp
0x1800be79e  jz      short loc_1800BE7CB
0x1800be7a0  call    cs:__imp_GetLastError
0x1800be7a7  nop     dword ptr [rax+rax+00h]
0x1800be7ac  mov     ebx, eax
0x1800be7ae  mov     rcx, rbp; pv
0x1800be7b1  call    cs:__imp_CoTaskMemFree
0x1800be7b8  nop     dword ptr [rax+rax+00h]
0x1800be7bd  mov     ecx, ebx; dwErrCode
0x1800be7bf  call    cs:__imp_SetLastError
0x1800be7c6  nop     dword ptr [rax+rax+00h]
0x1800be7cb  mov     [rsi], r14
0x1800be7ce  xor     ecx, ecx
0x1800be7d0  jmp     short loc_1800BE7D7
0x1800be7d2  mov     rcx, [rsp+58h+pv]; pv
0x1800be7d7  test    rcx, rcx
0x1800be7da  jz      short loc_1800BE7E8
0x1800be7dc  call    cs:__imp_CoTaskMemFree
0x1800be7e3  nop     dword ptr [rax+rax+00h]
0x1800be7e8  cmp     qword ptr [rsi], 0
0x1800be7ec  jnz     short loc_1800BE813
0x1800be7ee  mov     edx, 2Ah ; '*'; void *
0x1800be7f3  mov     ebx, 8007000Eh
0x1800be7f8  mov     rcx, [rsp+58h]; this
0x1800be7fd  mov     r9d, ebx; char *
0x1800be800  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\appmode"...
0x1800be807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be80c  mov     eax, ebx
0x1800be80e  jmp     loc_1800BE972
0x1800be813  mov     eax, [rsp+58h+arg_20]
0x1800be81a  mov     [rdi+40h], eax
0x1800be81d  mov     rdx, [rsp+58h+arg_28]
0x1800be825  test    rdx, rdx
0x1800be828  jz      loc_1800BE8AF
0x1800be82e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800be832  lea     rcx, [rsp+58h+var_30]
0x1800be837  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800be83c  lea     rsi, [rdi+50h]
0x1800be840  lea     rax, [rsp+58h+var_30]
0x1800be845  cmp     rsi, rax
0x1800be848  jz      short loc_1800BE889
0x1800be84a  mov     r14, [rsp+58h+var_30]
0x1800be84f  mov     rbp, [rsi]
0x1800be852  test    rbp, rbp
0x1800be855  jz      short loc_1800BE882
0x1800be857  call    cs:__imp_GetLastError
0x1800be85e  nop     dword ptr [rax+rax+00h]
0x1800be863  mov     ebx, eax
0x1800be865  mov     rcx, rbp; pv
0x1800be868  call    cs:__imp_CoTaskMemFree
0x1800be86f  nop     dword ptr [rax+rax+00h]
0x1800be874  mov     ecx, ebx; dwErrCode
0x1800be876  call    cs:__imp_SetLastError
0x1800be87d  nop     dword ptr [rax+rax+00h]
0x1800be882  mov     [rsi], r14
0x1800be885  xor     ecx, ecx
0x1800be887  jmp     short loc_1800BE88E
0x1800be889  mov     rcx, [rsp+58h+var_30]; pv
0x1800be88e  test    rcx, rcx
0x1800be891  jz      short loc_1800BE89F
0x1800be893  call    cs:__imp_CoTaskMemFree
0x1800be89a  nop     dword ptr [rax+rax+00h]
0x1800be89f  cmp     qword ptr [rsi], 0
0x1800be8a3  jnz     short loc_1800BE8AF
0x1800be8a5  mov     edx, 2Fh ; '/'
0x1800be8aa  jmp     loc_1800BE7F3
0x1800be8af  mov     rax, [rsp+58h+arg_30]
0x1800be8b7  mov     [rdi+58h], rax
0x1800be8bb  mov     eax, [rsp+58h+arg_40]
0x1800be8c2  mov     [rdi+68h], eax
0x1800be8c5  cmp     [rsp+58h+arg_48], 0
0x1800be8cd  setnz   al
0x1800be8d0  mov     [rdi+6Ch], al
0x1800be8d3  cmp     [rsp+58h+arg_50], 0
0x1800be8db  setnz   al
0x1800be8de  mov     [rdi+6Dh], al
0x1800be8e1  mov     rcx, [rdi+60h]
0x1800be8e5  mov     qword ptr [rdi+60h], 0
0x1800be8ed  test    rcx, rcx
0x1800be8f0  jz      short loc_1800BE8FF
0x1800be8f2  mov     rax, [rcx]
0x1800be8f5  mov     rax, [rax+10h]
0x1800be8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8fe  nop
0x1800be8ff  mov     rcx, [rdi+60h]
0x1800be903  mov     rbx, [rsp+58h+arg_38]
0x1800be90b  test    rbx, rbx
0x1800be90e  jz      short loc_1800BE956
0x1800be910  test    rcx, rcx
0x1800be913  jz      short loc_1800BE92A
0x1800be915  mov     qword ptr [rdi+60h], 0
0x1800be91d  mov     rax, [rcx]
0x1800be920  mov     rax, [rax+10h]
0x1800be924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be929  nop
0x1800be92a  lea     r9, [rdi+60h]
0x1800be92e  mov     r8, rbx
0x1800be931  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800be938  xor     ecx, ecx
0x1800be93a  call    cs:__imp_RoGetAgileReference
0x1800be941  nop     dword ptr [rax+rax+00h]
0x1800be946  mov     ebx, eax
0x1800be948  test    eax, eax
0x1800be94a  jns     short loc_1800BE970
0x1800be94c  mov     edx, 36h ; '6'
0x1800be951  jmp     loc_1800BE7F8
0x1800be956  mov     qword ptr [rdi+60h], 0
0x1800be95e  test    rcx, rcx
0x1800be961  jz      short loc_1800BE970
0x1800be963  mov     rax, [rcx]
0x1800be966  mov     rax, [rax+10h]
0x1800be96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be96f  nop
0x1800be970  xor     eax, eax
0x1800be972  add     rsp, 30h
0x1800be976  pop     r14
0x1800be978  pop     rdi
0x1800be979  pop     rsi
0x1800be97a  pop     rbp
0x1800be97b  pop     rbx
0x1800be97c  retn
```
