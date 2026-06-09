# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006038`
- end: `0x1800061f5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `445`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003d7c`

## callees

- `0x1800015b0`
- `0x180003c24`
- `0x180004a80`
- `0x180005884`
- `0x1800058a4`
- `0x180005de0`
- `0x180005e60`
- `0x180006038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000609c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000613f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000609c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000613f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060b2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
0x180006038  mov     [rsp-8+arg_8], rbx
0x18000603d  mov     [rsp-8+arg_18], rdi
0x180006042  push    rbp
0x180006043  lea     rbp, [rsp-160h]
0x18000604b  sub     rsp, 260h
0x180006052  mov     rax, cs:__security_cookie
0x180006059  xor     rax, rsp
0x18000605c  mov     [rbp+160h+var_10], rax
0x180006063  mov     rdi, r8
0x180006066  mov     qword ptr [r8], 0
0x18000606d  mov     r8, rcx; wchar_t *
0x180006070  mov     edx, 104h; unsigned __int64
0x180006075  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000607a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000607f  lea     r8, aP0; "_p0"
0x180006086  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000608b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006090  lea     r8, [rsp+260h+Name]; lpName
0x180006095  xor     edx, edx; bInheritHandle
0x180006097  mov     ecx, 1F0003h; dwDesiredAccess
0x18000609c  call    cs:__imp_OpenSemaphoreW
0x1800060a3  nop     dword ptr [rax+rax+00h]
0x1800060a8  mov     [rsp+260h+var_230], rax
0x1800060ad  test    rax, rax
0x1800060b0  jnz     short loc_1800060DF
0x1800060b2  call    cs:__imp_GetLastError
0x1800060b9  nop     dword ptr [rax+rax+00h]
0x1800060be  cmp     eax, 2
0x1800060c1  jz      loc_1800061C2
0x1800060c7  mov     rcx, [rbp+168h]; this
0x1800060ce  mov     edx, 0D0h; void *
0x1800060d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800060d8  mov     ebx, eax
0x1800060da  jmp     loc_1800061C4
0x1800060df  lea     rdx, [rsp+260h+var_23C]; int *
0x1800060e4  mov     [rsp+260h+var_23C], 0
0x1800060ec  mov     rcx, rax; hHandle
0x1800060ef  mov     [rsp+260h+var_240], 0; int
0x1800060f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800060fc  mov     ebx, eax
0x1800060fe  test    eax, eax
0x180006100  jns     short loc_180006122
0x180006102  mov     rcx, [rbp+168h]; this
0x180006109  lea     r8, aWil; "wil"
0x180006110  mov     r9d, eax; char *
0x180006113  mov     edx, 0D6h; void *
0x180006118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000611d  jmp     loc_1800061C4
0x180006122  lea     r8, asc_18001C720; "h"
0x180006129  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000612e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006133  lea     r8, [rsp+260h+Name]; lpName
0x180006138  xor     edx, edx; bInheritHandle
0x18000613a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000613f  call    cs:__imp_OpenSemaphoreW
0x180006146  nop     dword ptr [rax+rax+00h]
0x18000614b  mov     [rsp+260h+var_238], rax
0x180006150  test    rax, rax
0x180006153  jnz     short loc_180006174
0x180006155  mov     rcx, [rbp+168h]; this
0x18000615c  mov     edx, 0DCh; void *
0x180006161  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006166  mov     ebx, eax
0x180006168  lea     rcx, [rsp+260h+var_238]
0x18000616d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006172  jmp     short loc_1800061C4
0x180006174  lea     rdx, [rsp+260h+var_240]; int *
0x180006179  mov     rcx, rax; hHandle
0x18000617c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006181  mov     ebx, eax
0x180006183  test    eax, eax
0x180006185  jns     short loc_1800061A4
0x180006187  mov     rcx, [rbp+168h]; this
0x18000618e  lea     r8, aWil; "wil"
0x180006195  mov     r9d, eax; char *
0x180006198  mov     edx, 0DEh; void *
0x18000619d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061a2  jmp     short loc_180006168
0x1800061a4  lea     rcx, [rsp+260h+var_238]
0x1800061a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800061ae  movsxd  rcx, [rsp+260h+var_240]
0x1800061b3  movsxd  rax, [rsp+260h+var_23C]
0x1800061b8  shl     rcx, 1Fh
0x1800061bc  or      rcx, rax
0x1800061bf  mov     [rdi], rcx
0x1800061c2  xor     ebx, ebx
0x1800061c4  lea     rcx, [rsp+260h+var_230]
0x1800061c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800061ce  mov     eax, ebx
0x1800061d0  mov     rcx, [rbp+160h+var_10]
0x1800061d7  xor     rcx, rsp; StackCookie
0x1800061da  call    __security_check_cookie
0x1800061df  lea     r11, [rsp+260h+var_s0]
0x1800061e7  mov     rbx, [r11+18h]
0x1800061eb  mov     rdi, [r11+28h]
0x1800061ef  mov     rsp, r11
0x1800061f2  pop     rbp
0x1800061f3  retn
```
