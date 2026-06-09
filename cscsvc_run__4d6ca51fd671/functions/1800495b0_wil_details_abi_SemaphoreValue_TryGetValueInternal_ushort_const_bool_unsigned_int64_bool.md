# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800495b0`
- end: `0x18004974c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004953c`

## callees

- `0x180018810`
- `0x180039610`
- `0x180047830`
- `0x1800486c8`
- `0x180049140`
- `0x180049160`
- `0x180049428`
- `0x1800495b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049624`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180049614`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800496a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180049614`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800496a4`

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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800495b0  mov     [rsp-8+arg_8], rbx
0x1800495b5  mov     [rsp-8+arg_18], rdi
0x1800495ba  push    rbp
0x1800495bb  lea     rbp, [rsp-160h]
0x1800495c3  sub     rsp, 260h
0x1800495ca  mov     rax, cs:__security_cookie
0x1800495d1  xor     rax, rsp
0x1800495d4  mov     [rbp+160h+var_10], rax
0x1800495db  mov     rdi, r8
0x1800495de  mov     qword ptr [r8], 0
0x1800495e5  mov     r8, rcx; unsigned __int16 *
0x1800495e8  mov     edx, 104h; unsigned __int64
0x1800495ed  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800495f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800495f7  lea     r8, aP0; "_p0"
0x1800495fe  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180049603  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180049608  lea     r8, [rsp+260h+Name]; lpName
0x18004960d  xor     edx, edx; bInheritHandle
0x18004960f  mov     ecx, 1F0003h; dwDesiredAccess
0x180049614  call    cs:__imp_OpenSemaphoreW
0x18004961a  mov     [rsp+260h+var_230], rax
0x18004961f  test    rax, rax
0x180049622  jnz     short loc_18004964B
0x180049624  call    cs:__imp_GetLastError
0x18004962a  cmp     eax, 2
0x18004962d  jz      loc_18004971A
0x180049633  mov     rcx, [rbp+168h]; this
0x18004963a  mov     edx, 0D0h; void *
0x18004963f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049644  mov     ebx, eax
0x180049646  jmp     loc_18004971C
0x18004964b  lea     rdx, [rsp+260h+var_23C]; int *
0x180049650  mov     [rsp+260h+var_23C], 0
0x180049658  mov     rcx, rax; hHandle
0x18004965b  mov     [rsp+260h+var_240], 0; int
0x180049663  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180049668  mov     ebx, eax
0x18004966a  test    eax, eax
0x18004966c  jns     short loc_180049687
0x18004966e  mov     rcx, [rbp+168h]; this
0x180049675  mov     r9d, eax; char *
0x180049678  mov     edx, 0D6h; void *
0x18004967d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049682  jmp     loc_18004971C
0x180049687  lea     r8, asc_180092078; "h"
0x18004968e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180049693  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180049698  lea     r8, [rsp+260h+Name]; lpName
0x18004969d  xor     edx, edx; bInheritHandle
0x18004969f  mov     ecx, 1F0003h; dwDesiredAccess
0x1800496a4  call    cs:__imp_OpenSemaphoreW
0x1800496aa  mov     [rsp+260h+var_238], rax
0x1800496af  test    rax, rax
0x1800496b2  jnz     short loc_1800496D3
0x1800496b4  mov     rcx, [rbp+168h]; this
0x1800496bb  mov     edx, 0DCh; void *
0x1800496c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800496c5  mov     ebx, eax
0x1800496c7  lea     rcx, [rsp+260h+var_238]
0x1800496cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800496d1  jmp     short loc_18004971C
0x1800496d3  lea     rdx, [rsp+260h+var_240]; int *
0x1800496d8  mov     rcx, rax; hHandle
0x1800496db  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800496e0  mov     ebx, eax
0x1800496e2  test    eax, eax
0x1800496e4  jns     short loc_1800496FC
0x1800496e6  mov     rcx, [rbp+168h]; this
0x1800496ed  mov     r9d, eax; char *
0x1800496f0  mov     edx, 0DEh; void *
0x1800496f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800496fa  jmp     short loc_1800496C7
0x1800496fc  lea     rcx, [rsp+260h+var_238]
0x180049701  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180049706  movsxd  rcx, [rsp+260h+var_240]
0x18004970b  movsxd  rax, [rsp+260h+var_23C]
0x180049710  shl     rcx, 1Fh
0x180049714  or      rcx, rax
0x180049717  mov     [rdi], rcx
0x18004971a  xor     ebx, ebx
0x18004971c  lea     rcx, [rsp+260h+var_230]
0x180049721  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180049726  mov     eax, ebx
0x180049728  mov     rcx, [rbp+160h+var_10]
0x18004972f  xor     rcx, rsp; StackCookie
0x180049732  call    __security_check_cookie
0x180049737  lea     r11, [rsp+260h+var_s0]
0x18004973f  mov     rbx, [r11+18h]
0x180049743  mov     rdi, [r11+28h]
0x180049747  mov     rsp, r11
0x18004974a  pop     rbp
0x18004974b  retn
```
