# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800391a8`
- end: `0x180039360`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003e22c`

## callees

- `0x180019afc`
- `0x180021980`
- `0x18002d2d8`
- `0x18002db38`
- `0x1800391a8`
- `0x180039368`
- `0x18003a730`
- `0x18003d634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003920c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800392aa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003920c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800392aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003921c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003921c`

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
0x1800391a8  mov     [rsp-8+arg_8], rbx
0x1800391ad  mov     [rsp-8+arg_18], rdi
0x1800391b2  push    rbp
0x1800391b3  lea     rbp, [rsp-160h]
0x1800391bb  sub     rsp, 260h
0x1800391c2  mov     rax, cs:__security_cookie
0x1800391c9  xor     rax, rsp
0x1800391cc  mov     [rbp+160h+var_10], rax
0x1800391d3  mov     rdi, r8
0x1800391d6  mov     qword ptr [r8], 0
0x1800391dd  mov     r8, rcx; unsigned __int16 *
0x1800391e0  mov     edx, 104h; unsigned __int64
0x1800391e5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800391ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800391ef  lea     r8, aP0; "_p0"
0x1800391f6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800391fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039200  lea     r8, [rsp+260h+Name]; lpName
0x180039205  xor     edx, edx; bInheritHandle
0x180039207  mov     ecx, 1F0003h; dwDesiredAccess
0x18003920c  call    cs:__imp_OpenSemaphoreW
0x180039212  mov     [rsp+260h+var_230], rax
0x180039217  test    rax, rax
0x18003921a  jnz     short loc_18003924A
0x18003921c  call    cs:__imp_GetLastError
0x180039222  cmp     eax, 2
0x180039225  jz      loc_18003932E
0x18003922b  mov     rcx, [rbp+168h]; this
0x180039232  lea     r8, aWil; "wil"
0x180039239  mov     edx, 0D0h; void *
0x18003923e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039243  mov     ebx, eax
0x180039245  jmp     loc_180039330
0x18003924a  lea     rdx, [rsp+260h+var_23C]; int *
0x18003924f  mov     [rsp+260h+var_23C], 0
0x180039257  mov     rcx, rax; hHandle
0x18003925a  mov     [rsp+260h+var_240], 0; int
0x180039262  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180039267  mov     ebx, eax
0x180039269  test    eax, eax
0x18003926b  jns     short loc_18003928D
0x18003926d  mov     rcx, [rbp+168h]; this
0x180039274  lea     r8, aWil; "wil"
0x18003927b  mov     r9d, eax; char *
0x18003927e  mov     edx, 0D6h; void *
0x180039283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039288  jmp     loc_180039330
0x18003928d  lea     r8, asc_180062668; "h"
0x180039294  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180039299  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003929e  lea     r8, [rsp+260h+Name]; lpName
0x1800392a3  xor     edx, edx; bInheritHandle
0x1800392a5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800392aa  call    cs:__imp_OpenSemaphoreW
0x1800392b0  mov     [rsp+260h+var_238], rax
0x1800392b5  test    rax, rax
0x1800392b8  jnz     short loc_1800392E0
0x1800392ba  mov     rcx, [rbp+168h]; this
0x1800392c1  lea     r8, aWil; "wil"
0x1800392c8  mov     edx, 0DCh; void *
0x1800392cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800392d2  mov     ebx, eax
0x1800392d4  lea     rcx, [rsp+260h+var_238]
0x1800392d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800392de  jmp     short loc_180039330
0x1800392e0  lea     rdx, [rsp+260h+var_240]; int *
0x1800392e5  mov     rcx, rax; hHandle
0x1800392e8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800392ed  mov     ebx, eax
0x1800392ef  test    eax, eax
0x1800392f1  jns     short loc_180039310
0x1800392f3  mov     rcx, [rbp+168h]; this
0x1800392fa  lea     r8, aWil; "wil"
0x180039301  mov     r9d, eax; char *
0x180039304  mov     edx, 0DEh; void *
0x180039309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003930e  jmp     short loc_1800392D4
0x180039310  lea     rcx, [rsp+260h+var_238]
0x180039315  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003931a  movsxd  rcx, [rsp+260h+var_240]
0x18003931f  movsxd  rax, [rsp+260h+var_23C]
0x180039324  shl     rcx, 1Fh
0x180039328  or      rcx, rax
0x18003932b  mov     [rdi], rcx
0x18003932e  xor     ebx, ebx
0x180039330  lea     rcx, [rsp+260h+var_230]
0x180039335  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003933a  mov     eax, ebx
0x18003933c  mov     rcx, [rbp+160h+var_10]
0x180039343  xor     rcx, rsp; StackCookie
0x180039346  call    __security_check_cookie
0x18003934b  lea     r11, [rsp+260h+var_s0]
0x180039353  mov     rbx, [r11+18h]
0x180039357  mov     rdi, [r11+28h]
0x18003935b  mov     rsp, r11
0x18003935e  pop     rbp
0x18003935f  retn
```
