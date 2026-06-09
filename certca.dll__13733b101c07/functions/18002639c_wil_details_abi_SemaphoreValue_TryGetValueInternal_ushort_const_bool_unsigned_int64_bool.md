# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002639c`
- end: `0x18002654e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `434`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180026328`

## callees

- `0x180005f00`
- `0x180008420`
- `0x180023418`
- `0x180024568`
- `0x180025cb8`
- `0x180025cd8`
- `0x18002639c`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026405`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002649a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026405`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002649a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026415`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  void *v19; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v23; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v24; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 260, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v5;
  if ( v5 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v21);
      goto LABEL_12;
    }
    StringCchCatW(Name, 260, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v23 = v12;
    if ( !v12 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v23,
        v15);
      goto LABEL_12;
    }
    v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v21);
    LastError = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16, v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v23,
        v19);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v23,
      v17);
    *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v24,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18002639c  mov     [rsp-8+arg_8], rbx
0x1800263a1  push    rbp
0x1800263a2  push    rdi
0x1800263a3  push    r14
0x1800263a5  lea     rbp, [rsp-160h]
0x1800263ad  sub     rsp, 260h
0x1800263b4  mov     rax, cs:__security_cookie
0x1800263bb  xor     rax, rsp
0x1800263be  mov     [rbp+170h+var_20], rax
0x1800263c5  mov     rdi, r8
0x1800263c8  mov     qword ptr [r8], 0
0x1800263cf  mov     r8, rcx; unsigned __int16 *
0x1800263d2  mov     r14d, 104h
0x1800263d8  mov     edx, r14d; unsigned __int64
0x1800263db  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800263e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263e5  lea     r8, aP0; "_p0"
0x1800263ec  mov     edx, r14d; unsigned __int64
0x1800263ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800263f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800263f9  lea     r8, [rsp+270h+Name]; lpName
0x1800263fe  xor     edx, edx; bInheritHandle
0x180026400  mov     ecx, 1F0003h; dwDesiredAccess
0x180026405  call    cs:__imp_OpenSemaphoreW
0x18002640b  mov     [rsp+270h+var_240], rax
0x180026410  test    rax, rax
0x180026413  jnz     short loc_18002643D
0x180026415  call    cs:__imp_GetLastError
0x18002641b  cmp     eax, 2
0x18002641e  jnz     short loc_180026425
0x180026420  jmp     loc_18002651D
0x180026425  mov     rcx, [rbp+178h]; this
0x18002642c  mov     edx, 0D0h; void *
0x180026431  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026436  mov     ebx, eax
0x180026438  jmp     loc_18002651F
0x18002643d  mov     [rsp+270h+var_24C], 0
0x180026445  mov     [rsp+270h+var_250], 0; int
0x18002644d  lea     rdx, [rsp+270h+var_24C]; int *
0x180026452  mov     rcx, rax; hHandle
0x180026455  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002645a  mov     ebx, eax
0x18002645c  test    eax, eax
0x18002645e  jns     short loc_18002647A
0x180026460  mov     rcx, [rbp+178h]; this
0x180026467  mov     r9d, eax; char *
0x18002646a  mov     edx, 0D6h; void *
0x18002646f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026474  nop
0x180026475  jmp     loc_18002651F
0x18002647a  lea     r8, asc_18006AA60; "h"
0x180026481  mov     rdx, r14; unsigned __int64
0x180026484  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026489  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002648e  lea     r8, [rsp+270h+Name]; lpName
0x180026493  xor     edx, edx; bInheritHandle
0x180026495  mov     ecx, 1F0003h; dwDesiredAccess
0x18002649a  call    cs:__imp_OpenSemaphoreW
0x1800264a0  mov     [rsp+270h+var_248], rax
0x1800264a5  test    rax, rax
0x1800264a8  jnz     short loc_1800264CA
0x1800264aa  mov     rcx, [rbp+178h]; this
0x1800264b1  mov     edx, 0DCh; void *
0x1800264b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800264bb  mov     ebx, eax
0x1800264bd  lea     rcx, [rsp+270h+var_248]
0x1800264c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800264c7  nop
0x1800264c8  jmp     short loc_18002651F
0x1800264ca  lea     rdx, [rsp+270h+var_250]; int *
0x1800264cf  mov     rcx, rax; hHandle
0x1800264d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800264d7  mov     ebx, eax
0x1800264d9  test    eax, eax
0x1800264db  jns     short loc_1800264FF
0x1800264dd  mov     rcx, [rbp+178h]; this
0x1800264e4  mov     r9d, eax; char *
0x1800264e7  mov     edx, 0DEh; void *
0x1800264ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264f1  nop
0x1800264f2  lea     rcx, [rsp+270h+var_248]
0x1800264f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800264fc  nop
0x1800264fd  jmp     short loc_18002651F
0x1800264ff  lea     rcx, [rsp+270h+var_248]
0x180026504  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026509  movsxd  rcx, [rsp+270h+var_250]
0x18002650e  shl     rcx, 1Fh
0x180026512  movsxd  rax, [rsp+270h+var_24C]
0x180026517  or      rcx, rax
0x18002651a  mov     [rdi], rcx
0x18002651d  xor     ebx, ebx
0x18002651f  lea     rcx, [rsp+270h+var_240]
0x180026524  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026529  mov     eax, ebx
0x18002652b  mov     rcx, [rbp+170h+var_20]
0x180026532  xor     rcx, rsp; StackCookie
0x180026535  call    __security_check_cookie
0x18002653a  mov     rbx, [rsp+270h+arg_8]
0x180026542  add     rsp, 260h
0x180026549  pop     r14
0x18002654b  pop     rdi
0x18002654c  pop     rbp
0x18002654d  retn
```
