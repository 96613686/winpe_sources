# fc::registry_store::load_experiments(fc::vector_nothrow<fc::experiment> &,fc::store_kind,_GUID &,fc::experiment_flags)

- ea: `0x1800168e4`
- end: `0x180016a2f`
- name: `?load_experiments@registry_store@fc@@QEAAJAEAV?$vector_nothrow@Uexperiment@fc@@@2@W4store_kind@2@AEAU_GUID@@W4experiment_flags@2@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180014608`

## callees

- `0x18001674c`
- `0x1800168e4`
- `0x180016a38`
- `0x180017988`
- `0x18005cfb8`
- `0x180064230`
- `0x18006425c`
- `0x180069ec4`
- `0x18006cae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001690f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001690f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a12`

## string_xrefs

- `0x18001698d`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x1800169e6`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall fc::registry_store::load_experiments(__int64 a1, __int64 a2, __int64 a3, GUID *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // ebx
  HKEY v19; // rbx
  int store_id; // eax
  int v21; // edi
  unsigned int v23[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  wil::init_once_nothrow<_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_>((LPINIT_ONCE)(a1 + 8), (_QWORD *)a1, a3);
  if ( *(_QWORD *)a1 )
  {
    v9 = WaitForSingleObject(*(HANDLE *)a1, 0x1388u);
    switch ( v9 )
    {
      case 0x80u:
        v13 = 66;
        v14 = 735;
        break;
      case 0x102u:
        v13 = 63;
        v14 = 1460;
        break;
      case 0xFFFFFFFF:
        wil::details::in1diag3::Log_GetLastError(retaddr, v10, v11, v12);
        goto LABEL_10;
      default:
        v13 = 69;
        v14 = 1;
        break;
    }
    wil::details::in1diag3::Log_Win32(retaddr, (void *)v13, v11, (const char *)v14, v23[0]);
  }
LABEL_10:
  *(_QWORD *)v23 = 0;
  hKey = 0;
  v15 = fc::try_open_store_key_for_reading(*(HKEY *)(a1 + 1384), v7, v8, &hKey);
  v18 = v15;
  if ( v15 >= 0 )
  {
    v19 = hKey;
    if ( hKey )
      fc::registry_store::enumerate_experiments(a1, hKey, v17, a2, *(_QWORD *)v23);
    store_id = fc::get_store_id(*(HKEY *)(a1 + 1384), v16, a4);
    v21 = store_id;
    if ( store_id >= 0 )
    {
      if ( v19 )
        RegCloseKey(v19);
      v18 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
        (const char *)(unsigned int)store_id,
        v23[0]);
      if ( v19 )
        RegCloseKey(v19);
      v18 = v21;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
      (const char *)(unsigned int)v15,
      v23[0]);
    if ( hKey )
      RegCloseKey(hKey);
  }
  __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(v23);
  return v18;
}

```

## disassembly

```asm
0x1800168e4  push    rbx
0x1800168e6  push    rbp
0x1800168e7  push    rsi
0x1800168e8  push    rdi
0x1800168e9  sub     rsp, 38h
0x1800168ed  mov     rbp, r9
0x1800168f0  mov     rsi, rdx
0x1800168f3  mov     rdi, rcx
0x1800168f6  add     rcx, 8; lpInitOnce
0x1800168fa  mov     rdx, rdi
0x1800168fd  call    ??$init_once_nothrow@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@PEA_N@Z; wil::init_once_nothrow<_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_>(_RTL_RUN_ONCE &,_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_,bool *)
0x180016902  mov     rcx, [rdi]; hHandle
0x180016905  test    rcx, rcx
0x180016908  jz      short loc_18001695C
0x18001690a  mov     edx, 1388h; dwMilliseconds
0x18001690f  call    cs:__imp_WaitForSingleObject
0x180016915  mov     rcx, [rsp+58h]; this
0x18001691a  cmp     eax, 80h
0x18001691f  jz      short loc_18001694C
0x180016921  cmp     eax, 102h
0x180016926  jz      short loc_18001693F
0x180016928  cmp     eax, 0FFFFFFFFh
0x18001692b  jz      short loc_180016938
0x18001692d  mov     edx, 45h ; 'E'
0x180016932  lea     r9d, [rdx-44h]
0x180016936  jmp     short loc_180016957
0x180016938  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001693d  jmp     short loc_18001695C
0x18001693f  mov     edx, 3Fh ; '?'
0x180016944  mov     r9d, 5B4h
0x18001694a  jmp     short loc_180016957
0x18001694c  mov     edx, 42h ; 'B'; void *
0x180016951  mov     r9d, 2DFh; char *
0x180016957  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001695c  mov     qword ptr [rsp+58h+var_38], 0; int
0x180016965  mov     [rsp+58h+hKey], 0
0x18001696e  lea     r9, [rsp+58h+hKey]
0x180016973  mov     rcx, [rdi+568h]
0x18001697a  call    ?try_open_store_key_for_reading@fc@@YAJPEAUHKEY__@@W4store_type@1@W4store_kind@1@PEAPEAU2@@Z; fc::try_open_store_key_for_reading(HKEY__ *,fc::store_type,fc::store_kind,HKEY__ * *)
0x18001697f  mov     ebx, eax
0x180016981  test    eax, eax
0x180016983  jns     short loc_1800169B1
0x180016985  mov     rcx, [rsp+58h]; this
0x18001698a  mov     r9d, eax; char *
0x18001698d  lea     r8, aOnecoreInterna_11; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180016994  mov     edx, 1B5h; void *
0x180016999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001699e  nop
0x18001699f  mov     rcx, [rsp+58h+hKey]; hKey
0x1800169a4  test    rcx, rcx
0x1800169a7  jz      short loc_180016A1A
0x1800169a9  call    cs:__imp_RegCloseKey
0x1800169af  jmp     short loc_180016A1A
0x1800169b1  mov     rbx, [rsp+58h+hKey]
0x1800169b6  test    rbx, rbx
0x1800169b9  jz      short loc_1800169C9
0x1800169bb  mov     r9, rsi
0x1800169be  mov     rdx, rbx
0x1800169c1  mov     rcx, rdi
0x1800169c4  call    ?enumerate_experiments@registry_store@fc@@AEBAJPEAUHKEY__@@W4experiment_flags@2@AEAV?$vector_nothrow@Uexperiment@fc@@@2@@Z; fc::registry_store::enumerate_experiments(HKEY__ *,fc::experiment_flags,fc::vector_nothrow<fc::experiment> &)
0x1800169c9  mov     r8, rbp
0x1800169cc  mov     rcx, [rdi+568h]
0x1800169d3  call    ?get_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEAU_GUID@@@Z; fc::get_store_id(HKEY__ *,fc::store_type,_GUID &)
0x1800169d8  mov     edi, eax
0x1800169da  test    eax, eax
0x1800169dc  jns     short loc_180016A0A
0x1800169de  mov     rcx, [rsp+58h]; this
0x1800169e3  mov     r9d, eax; char *
0x1800169e6  lea     r8, aOnecoreInterna_11; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800169ed  mov     edx, 1BFh; void *
0x1800169f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800169f7  nop
0x1800169f8  test    rbx, rbx
0x1800169fb  jz      short loc_180016A06
0x1800169fd  mov     rcx, rbx; hKey
0x180016a00  call    cs:__imp_RegCloseKey
0x180016a06  mov     ebx, edi
0x180016a08  jmp     short loc_180016A1A
0x180016a0a  test    rbx, rbx
0x180016a0d  jz      short loc_180016A18
0x180016a0f  mov     rcx, rbx; hKey
0x180016a12  call    cs:__imp_RegCloseKey
0x180016a18  xor     ebx, ebx
0x180016a1a  lea     rcx, [rsp+58h+var_38]
0x180016a1f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180016a24  mov     eax, ebx
0x180016a26  add     rsp, 38h
0x180016a2a  pop     rdi
0x180016a2b  pop     rsi
0x180016a2c  pop     rbp
0x180016a2d  pop     rbx
0x180016a2e  retn
```
