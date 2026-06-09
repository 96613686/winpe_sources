# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015048`
- end: `0x1800151e4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014fd4`

## callees

- `0x18000b760`
- `0x18000b9f4`
- `0x18000da54`
- `0x18000e2f0`
- `0x18001204c`
- `0x180013614`
- `0x180014950`
- `0x180015048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800150ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001513c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800150ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001513c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150bc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180015048  mov     [rsp-8+arg_8], rbx
0x18001504d  mov     [rsp-8+arg_18], rdi
0x180015052  push    rbp
0x180015053  lea     rbp, [rsp-160h]
0x18001505b  sub     rsp, 260h
0x180015062  mov     rax, cs:__security_cookie
0x180015069  xor     rax, rsp
0x18001506c  mov     [rbp+160h+var_10], rax
0x180015073  mov     rdi, r8
0x180015076  mov     qword ptr [r8], 0
0x18001507d  mov     r8, rcx; unsigned __int16 *
0x180015080  mov     edx, 104h; unsigned __int64
0x180015085  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001508a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001508f  lea     r8, aP0; "_p0"
0x180015096  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001509b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800150a0  lea     r8, [rsp+260h+Name]; lpName
0x1800150a5  xor     edx, edx; bInheritHandle
0x1800150a7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800150ac  call    cs:__imp_OpenSemaphoreW
0x1800150b2  mov     [rsp+260h+var_230], rax
0x1800150b7  test    rax, rax
0x1800150ba  jnz     short loc_1800150E3
0x1800150bc  call    cs:__imp_GetLastError
0x1800150c2  cmp     eax, 2
0x1800150c5  jz      loc_1800151B2
0x1800150cb  mov     rcx, [rbp+168h]; this
0x1800150d2  mov     edx, 0D0h; void *
0x1800150d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800150dc  mov     ebx, eax
0x1800150de  jmp     loc_1800151B4
0x1800150e3  lea     rdx, [rsp+260h+var_23C]; int *
0x1800150e8  mov     [rsp+260h+var_23C], 0
0x1800150f0  mov     rcx, rax; hHandle
0x1800150f3  mov     [rsp+260h+var_240], 0; int
0x1800150fb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015100  mov     ebx, eax
0x180015102  test    eax, eax
0x180015104  jns     short loc_18001511F
0x180015106  mov     rcx, [rbp+168h]; this
0x18001510d  mov     r9d, eax; char *
0x180015110  mov     edx, 0D6h; void *
0x180015115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001511a  jmp     loc_1800151B4
0x18001511f  lea     r8, asc_18001B330; "h"
0x180015126  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001512b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015130  lea     r8, [rsp+260h+Name]; lpName
0x180015135  xor     edx, edx; bInheritHandle
0x180015137  mov     ecx, 1F0003h; dwDesiredAccess
0x18001513c  call    cs:__imp_OpenSemaphoreW
0x180015142  mov     [rsp+260h+var_238], rax
0x180015147  test    rax, rax
0x18001514a  jnz     short loc_18001516B
0x18001514c  mov     rcx, [rbp+168h]; this
0x180015153  mov     edx, 0DCh; void *
0x180015158  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001515d  mov     ebx, eax
0x18001515f  lea     rcx, [rsp+260h+var_238]
0x180015164  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015169  jmp     short loc_1800151B4
0x18001516b  lea     rdx, [rsp+260h+var_240]; int *
0x180015170  mov     rcx, rax; hHandle
0x180015173  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015178  mov     ebx, eax
0x18001517a  test    eax, eax
0x18001517c  jns     short loc_180015194
0x18001517e  mov     rcx, [rbp+168h]; this
0x180015185  mov     r9d, eax; char *
0x180015188  mov     edx, 0DEh; void *
0x18001518d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015192  jmp     short loc_18001515F
0x180015194  lea     rcx, [rsp+260h+var_238]
0x180015199  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001519e  movsxd  rcx, [rsp+260h+var_240]
0x1800151a3  movsxd  rax, [rsp+260h+var_23C]
0x1800151a8  shl     rcx, 1Fh
0x1800151ac  or      rcx, rax
0x1800151af  mov     [rdi], rcx
0x1800151b2  xor     ebx, ebx
0x1800151b4  lea     rcx, [rsp+260h+var_230]
0x1800151b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800151be  mov     eax, ebx
0x1800151c0  mov     rcx, [rbp+160h+var_10]
0x1800151c7  xor     rcx, rsp; StackCookie
0x1800151ca  call    __security_check_cookie
0x1800151cf  lea     r11, [rsp+260h+var_s0]
0x1800151d7  mov     rbx, [r11+18h]
0x1800151db  mov     rdi, [r11+28h]
0x1800151df  mov     rsp, r11
0x1800151e2  pop     rbp
0x1800151e3  retn
```
