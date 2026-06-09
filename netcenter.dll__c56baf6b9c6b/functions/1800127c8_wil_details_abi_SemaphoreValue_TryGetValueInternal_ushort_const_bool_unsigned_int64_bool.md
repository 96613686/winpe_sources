# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800127c8`
- end: `0x180012972`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800088d8`

## callees

- `0x180002270`
- `0x18000817c`
- `0x18000b0a8`
- `0x180010f24`
- `0x180010f44`
- `0x1800122bc`
- `0x180012408`
- `0x1800127c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001282c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800128c3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001282c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800128c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800127c8  mov     [rsp-8+arg_8], rbx
0x1800127cd  mov     [rsp-8+arg_18], rdi
0x1800127d2  push    rbp
0x1800127d3  lea     rbp, [rsp-160h]
0x1800127db  sub     rsp, 260h
0x1800127e2  mov     rax, cs:__security_cookie
0x1800127e9  xor     rax, rsp
0x1800127ec  mov     [rbp+160h+var_10], rax
0x1800127f3  mov     rdi, r8
0x1800127f6  mov     qword ptr [r8], 0
0x1800127fd  mov     r8, rcx; unsigned __int16 *
0x180012800  mov     edx, 104h; unsigned __int64
0x180012805  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001280a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001280f  lea     r8, aP0; "_p0"
0x180012816  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001281b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012820  lea     r8, [rsp+260h+Name]; lpName
0x180012825  xor     edx, edx; bInheritHandle
0x180012827  mov     ecx, 1F0003h; dwDesiredAccess
0x18001282c  call    cs:__imp_OpenSemaphoreW
0x180012832  mov     [rsp+260h+var_230], rax
0x180012837  test    rax, rax
0x18001283a  jnz     short loc_180012863
0x18001283c  call    cs:__imp_GetLastError
0x180012842  cmp     eax, 2
0x180012845  jz      loc_180012940
0x18001284b  mov     rcx, [rbp+168h]; this
0x180012852  mov     edx, 0D0h; void *
0x180012857  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001285c  mov     ebx, eax
0x18001285e  jmp     loc_180012942
0x180012863  lea     rdx, [rsp+260h+var_23C]; int *
0x180012868  mov     [rsp+260h+var_23C], 0
0x180012870  mov     rcx, rax; hHandle
0x180012873  mov     [rsp+260h+var_240], 0; int
0x18001287b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012880  mov     ebx, eax
0x180012882  test    eax, eax
0x180012884  jns     short loc_1800128A6
0x180012886  mov     rcx, [rbp+168h]; this
0x18001288d  lea     r8, aWil; "wil"
0x180012894  mov     r9d, eax; char *
0x180012897  mov     edx, 0D6h; void *
0x18001289c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128a1  jmp     loc_180012942
0x1800128a6  lea     r8, asc_180027CD8; "h"
0x1800128ad  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800128b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800128b7  lea     r8, [rsp+260h+Name]; lpName
0x1800128bc  xor     edx, edx; bInheritHandle
0x1800128be  mov     ecx, 1F0003h; dwDesiredAccess
0x1800128c3  call    cs:__imp_OpenSemaphoreW
0x1800128c9  mov     [rsp+260h+var_238], rax
0x1800128ce  test    rax, rax
0x1800128d1  jnz     short loc_1800128F2
0x1800128d3  mov     rcx, [rbp+168h]; this
0x1800128da  mov     edx, 0DCh; void *
0x1800128df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800128e4  mov     ebx, eax
0x1800128e6  lea     rcx, [rsp+260h+var_238]
0x1800128eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800128f0  jmp     short loc_180012942
0x1800128f2  lea     rdx, [rsp+260h+var_240]; int *
0x1800128f7  mov     rcx, rax; hHandle
0x1800128fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800128ff  mov     ebx, eax
0x180012901  test    eax, eax
0x180012903  jns     short loc_180012922
0x180012905  mov     rcx, [rbp+168h]; this
0x18001290c  lea     r8, aWil; "wil"
0x180012913  mov     r9d, eax; char *
0x180012916  mov     edx, 0DEh; void *
0x18001291b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012920  jmp     short loc_1800128E6
0x180012922  lea     rcx, [rsp+260h+var_238]
0x180012927  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001292c  movsxd  rcx, [rsp+260h+var_240]
0x180012931  movsxd  rax, [rsp+260h+var_23C]
0x180012936  shl     rcx, 1Fh
0x18001293a  or      rcx, rax
0x18001293d  mov     [rdi], rcx
0x180012940  xor     ebx, ebx
0x180012942  lea     rcx, [rsp+260h+var_230]
0x180012947  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001294c  mov     eax, ebx
0x18001294e  mov     rcx, [rbp+160h+var_10]
0x180012955  xor     rcx, rsp; StackCookie
0x180012958  call    __security_check_cookie
0x18001295d  lea     r11, [rsp+260h+var_s0]
0x180012965  mov     rbx, [r11+18h]
0x180012969  mov     rdi, [r11+28h]
0x18001296d  mov     rsp, r11
0x180012970  pop     rbp
0x180012971  retn
```
