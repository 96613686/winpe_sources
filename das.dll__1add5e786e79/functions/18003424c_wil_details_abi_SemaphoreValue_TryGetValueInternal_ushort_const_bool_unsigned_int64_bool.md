# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003424c`
- end: `0x180034404`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180040c28`

## callees

- `0x18001b0fc`
- `0x18002a948`
- `0x18002aa34`
- `0x18003424c`
- `0x18003440c`
- `0x180034494`
- `0x18003bc80`
- `0x18003eedc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800342b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003434e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800342b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003434e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342c0`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18003424c  mov     [rsp-8+arg_8], rbx
0x180034251  mov     [rsp-8+arg_18], rdi
0x180034256  push    rbp
0x180034257  lea     rbp, [rsp-160h]
0x18003425f  sub     rsp, 260h
0x180034266  mov     rax, cs:__security_cookie
0x18003426d  xor     rax, rsp
0x180034270  mov     [rbp+160h+var_10], rax
0x180034277  mov     rdi, r8
0x18003427a  mov     qword ptr [r8], 0
0x180034281  mov     r8, rcx; unsigned __int16 *
0x180034284  mov     edx, 104h; unsigned __int64
0x180034289  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003428e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034293  lea     r8, aP0; "_p0"
0x18003429a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003429f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800342a4  lea     r8, [rsp+260h+Name]; lpName
0x1800342a9  xor     edx, edx; bInheritHandle
0x1800342ab  mov     ecx, 1F0003h; dwDesiredAccess
0x1800342b0  call    cs:__imp_OpenSemaphoreW
0x1800342b6  mov     [rsp+260h+var_230], rax
0x1800342bb  test    rax, rax
0x1800342be  jnz     short loc_1800342EE
0x1800342c0  call    cs:__imp_GetLastError
0x1800342c6  cmp     eax, 2
0x1800342c9  jz      loc_1800343D2
0x1800342cf  mov     rcx, [rbp+168h]; this
0x1800342d6  lea     r8, aWil; "wil"
0x1800342dd  mov     edx, 0D0h; void *
0x1800342e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800342e7  mov     ebx, eax
0x1800342e9  jmp     loc_1800343D4
0x1800342ee  lea     rdx, [rsp+260h+var_23C]; int *
0x1800342f3  mov     [rsp+260h+var_23C], 0
0x1800342fb  mov     rcx, rax; hHandle
0x1800342fe  mov     [rsp+260h+var_240], 0; int
0x180034306  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003430b  mov     ebx, eax
0x18003430d  test    eax, eax
0x18003430f  jns     short loc_180034331
0x180034311  mov     rcx, [rbp+168h]; this
0x180034318  lea     r8, aWil; "wil"
0x18003431f  mov     r9d, eax; char *
0x180034322  mov     edx, 0D6h; void *
0x180034327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003432c  jmp     loc_1800343D4
0x180034331  lea     r8, asc_18008D8A0; "h"
0x180034338  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003433d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034342  lea     r8, [rsp+260h+Name]; lpName
0x180034347  xor     edx, edx; bInheritHandle
0x180034349  mov     ecx, 1F0003h; dwDesiredAccess
0x18003434e  call    cs:__imp_OpenSemaphoreW
0x180034354  mov     [rsp+260h+var_238], rax
0x180034359  test    rax, rax
0x18003435c  jnz     short loc_180034384
0x18003435e  mov     rcx, [rbp+168h]; this
0x180034365  lea     r8, aWil; "wil"
0x18003436c  mov     edx, 0DCh; void *
0x180034371  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034376  mov     ebx, eax
0x180034378  lea     rcx, [rsp+260h+var_238]
0x18003437d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034382  jmp     short loc_1800343D4
0x180034384  lea     rdx, [rsp+260h+var_240]; int *
0x180034389  mov     rcx, rax; hHandle
0x18003438c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180034391  mov     ebx, eax
0x180034393  test    eax, eax
0x180034395  jns     short loc_1800343B4
0x180034397  mov     rcx, [rbp+168h]; this
0x18003439e  lea     r8, aWil; "wil"
0x1800343a5  mov     r9d, eax; char *
0x1800343a8  mov     edx, 0DEh; void *
0x1800343ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800343b2  jmp     short loc_180034378
0x1800343b4  lea     rcx, [rsp+260h+var_238]
0x1800343b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800343be  movsxd  rcx, [rsp+260h+var_240]
0x1800343c3  movsxd  rax, [rsp+260h+var_23C]
0x1800343c8  shl     rcx, 1Fh
0x1800343cc  or      rcx, rax
0x1800343cf  mov     [rdi], rcx
0x1800343d2  xor     ebx, ebx
0x1800343d4  lea     rcx, [rsp+260h+var_230]
0x1800343d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800343de  mov     eax, ebx
0x1800343e0  mov     rcx, [rbp+160h+var_10]
0x1800343e7  xor     rcx, rsp; StackCookie
0x1800343ea  call    __security_check_cookie
0x1800343ef  lea     r11, [rsp+260h+var_s0]
0x1800343f7  mov     rbx, [r11+18h]
0x1800343fb  mov     rdi, [r11+28h]
0x1800343ff  mov     rsp, r11
0x180034402  pop     rbp
0x180034403  retn
```
