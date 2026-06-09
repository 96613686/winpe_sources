# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18018d914`
- end: `0x18018db99`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18018d6fc`
- `0x1801a6d18`

## callees

- `0x18018d914`
- `0x18018dba0`
- `0x18019dd80`
- `0x1801a29fc`
- `0x1801a6d90`
- `0x1801aeffc`
- `0x1801cf2a0`
- `0x1803481f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018db3c`
- `KERNEL32!GetLastError` at `0x18018db3c`
- `KERNEL32!OpenSemaphoreW` at `0x18018da17`
- `KERNEL32!OpenSemaphoreW` at `0x18018da9a`
- `KERNEL32!OpenSemaphoreW` at `0x18018da17`
- `KERNEL32!OpenSemaphoreW` at `0x18018da9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        char a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  WCHAR *v9; // rax
  unsigned __int16 v10; // r9
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // r8
  wil::details *v15; // rax
  int v16; // esi
  int ValueFromSemaphore; // eax
  void *v18; // rdx
  unsigned int LastError; // ebx
  void *v20; // rdx
  wil::details *v21; // rax
  const char *v22; // r9
  int v23; // eax
  void *v24; // rdx
  void *v25; // rdx
  __int64 v26; // rax
  const char *v28; // r9
  size_t v29; // [rsp+28h] [rbp-E0h]
  int v30[2]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details *v31; // [rsp+40h] [rbp-C8h] BYREF
  wil::details *v32[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v32[1] = (wil::details *)-2LL;
  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  v6 = 2147483646;
  v7 = a1;
  v8 = 260;
  v9 = Name;
  do
  {
    if ( !v6 )
      break;
    v10 = *v7;
    if ( !*v7 )
      break;
    ++v7;
    *v9++ = v10;
    --v6;
    --v8;
  }
  while ( v8 );
  v11 = v9 - 1;
  if ( v8 )
    v11 = v9;
  *v11 = 0;
  v12 = 260;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  if ( v12 )
  {
    v14 = (260 - v12) & -(__int64)(v12 != 0);
    StringCopyWorkerW(&Name[v14], 260 - v14, (size_t *)v14, L"_p0", v29);
  }
  v15 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v32[0] = v15;
  if ( v15 )
  {
    v30[1] = 0;
    v16 = 0;
    v30[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v30[1]);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
LABEL_29:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        v32,
        v20);
      return LastError;
    }
    if ( a2 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v21 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v31 = v21;
      if ( !v21 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
        goto LABEL_26;
      }
      v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, v30);
      LastError = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v23);
LABEL_26:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v31,
          v25);
        goto LABEL_29;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v31,
        v24);
      v16 = v30[0];
    }
    v26 = v30[1];
    if ( a4 )
      *a4 = 1;
    *a3 = ((__int64)v16 << 31) | v26;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      v32,
      v18);
    return 0;
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      LastError = 0;
      goto LABEL_29;
    }
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v28);
  }
}

```

## disassembly

```asm
0x18018d914  mov     rax, rsp
0x18018d917  mov     [rax+20h], r9
0x18018d91b  mov     [rax+18h], r8
0x18018d91f  mov     [rax+10h], dl
0x18018d922  mov     [rax+8], rcx
0x18018d926  push    rbp
0x18018d927  push    rbx
0x18018d928  push    rsi
0x18018d929  push    rdi
0x18018d92a  push    r12
0x18018d92c  push    r14
0x18018d92e  push    r15
0x18018d930  lea     rbp, [rax-1A8h]
0x18018d937  sub     rsp, 270h
0x18018d93e  mov     qword ptr [rsp+2A0h+var_258], 0FFFFFFFFFFFFFFFEh
0x18018d947  mov     rax, cs:__security_cookie
0x18018d94e  xor     rax, rsp
0x18018d951  mov     [rbp+1A0h+var_40], rax
0x18018d958  mov     r14, [rbp+1A0h+arg_10]
0x18018d95f  mov     rdi, [rbp+1A0h+arg_18]
0x18018d966  xor     r15d, r15d
0x18018d969  test    rdi, rdi
0x18018d96c  jz      short loc_18018D971
0x18018d96e  mov     [rdi], r15b
0x18018d971  mov     [r14], r15
0x18018d974  mov     ecx, 7FFFFFFEh
0x18018d979  mov     r8, [rbp+1A0h+arg_0]
0x18018d980  mov     r12d, 104h
0x18018d986  mov     edx, r12d
0x18018d989  lea     rax, [rsp+2A0h+Name]
0x18018d98e  test    rcx, rcx
0x18018d991  jz      short loc_18018D9B2
0x18018d993  movzx   r9d, word ptr [r8]
0x18018d997  test    r9w, r9w
0x18018d99b  jz      short loc_18018D9B2
0x18018d99d  add     r8, 2
0x18018d9a1  mov     [rax], r9w
0x18018d9a5  add     rax, 2
0x18018d9a9  dec     rcx
0x18018d9ac  sub     rdx, 1
0x18018d9b0  jnz     short loc_18018D98E
0x18018d9b2  lea     rcx, [rax-2]
0x18018d9b6  test    rdx, rdx
0x18018d9b9  cmovnz  rcx, rax
0x18018d9bd  mov     [rcx], r15w
0x18018d9c1  mov     rdx, r12
0x18018d9c4  lea     rax, [rsp+2A0h+Name]
0x18018d9c9  cmp     [rax], r15w
0x18018d9cd  jz      short loc_18018D9D9
0x18018d9cf  add     rax, 2
0x18018d9d3  sub     rdx, 1
0x18018d9d7  jnz     short loc_18018D9C9
0x18018d9d9  mov     rax, rdx
0x18018d9dc  mov     rcx, r12
0x18018d9df  sub     rcx, rdx
0x18018d9e2  neg     rax
0x18018d9e5  sbb     r8, r8
0x18018d9e8  and     r8, rcx; pcchNewDestLength
0x18018d9eb  test    rdx, rdx
0x18018d9ee  jz      short loc_18018DA0B
0x18018d9f0  mov     rdx, r12
0x18018d9f3  sub     rdx, r8; cchDest
0x18018d9f6  lea     rcx, [rsp+2A0h+Name]
0x18018d9fb  lea     rcx, [rcx+r8*2]; pszDest
0x18018d9ff  lea     r9, aP0; "_p0"
0x18018da06  call    StringCopyWorkerW
0x18018da0b  lea     r8, [rsp+2A0h+Name]; lpName
0x18018da10  xor     edx, edx; bInheritHandle
0x18018da12  mov     ecx, 1F0003h; dwDesiredAccess
0x18018da17  call    cs:__imp_OpenSemaphoreW
0x18018da1e  nop     dword ptr [rax+rax+00h]
0x18018da23  mov     [rsp+2A0h+var_260], rax
0x18018da28  test    rax, rax
0x18018da2b  jz      loc_18018DB3C
0x18018da31  mov     [rsp+2A0h+var_270+4], r15d
0x18018da36  mov     esi, r15d
0x18018da39  mov     [rsp+2A0h+var_270], r15d
0x18018da3e  lea     rdx, [rsp+2A0h+var_270+4]; int *
0x18018da43  mov     rcx, rax; void *
0x18018da46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18018da4b  mov     ebx, eax
0x18018da4d  test    eax, eax
0x18018da4f  jns     short loc_18018DA71
0x18018da51  mov     rcx, [rbp+1A8h]; this
0x18018da58  mov     r9d, eax; char *
0x18018da5b  lea     r8, aWil; "wil"
0x18018da62  mov     edx, 0D6h; void *
0x18018da67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018da6c  jmp     loc_18018DB50
0x18018da71  cmp     [rbp+1A0h+arg_8], r15b
0x18018da78  jz      short loc_18018DAEE
0x18018da7a  lea     r8, asc_1803C0A34; "h"
0x18018da81  mov     rdx, r12; unsigned __int64
0x18018da84  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18018da89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18018da8e  lea     r8, [rsp+2A0h+Name]; lpName
0x18018da93  xor     edx, edx; bInheritHandle
0x18018da95  mov     ecx, 1F0003h; dwDesiredAccess
0x18018da9a  call    cs:__imp_OpenSemaphoreW
0x18018daa1  nop     dword ptr [rax+rax+00h]
0x18018daa6  mov     [rsp+2A0h+var_268], rax
0x18018daab  test    rax, rax
0x18018daae  jz      short loc_18018DB16
0x18018dab0  lea     rdx, [rsp+2A0h+var_270]; int *
0x18018dab5  mov     rcx, rax; void *
0x18018dab8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18018dabd  mov     ebx, eax
0x18018dabf  test    eax, eax
0x18018dac1  jns     short loc_18018DAE0
0x18018dac3  mov     rcx, [rbp+1A8h]; this
0x18018daca  mov     r9d, eax; char *
0x18018dacd  lea     r8, aWil; "wil"
0x18018dad4  mov     edx, 0DEh; void *
0x18018dad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018dade  jmp     short loc_18018DB30
0x18018dae0  lea     rcx, [rsp+2A0h+var_268]
0x18018dae5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018daea  mov     esi, [rsp+2A0h+var_270]
0x18018daee  movsxd  rcx, esi
0x18018daf1  shl     rcx, 1Fh
0x18018daf5  movsxd  rax, [rsp+2A0h+var_270+4]
0x18018dafa  test    rdi, rdi
0x18018dafd  jz      short loc_18018DB02
0x18018daff  mov     byte ptr [rdi], 1
0x18018db02  or      rax, rcx
0x18018db05  mov     [r14], rax
0x18018db08  lea     rcx, [rsp+2A0h+var_260]
0x18018db0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018db12  xor     eax, eax
0x18018db14  jmp     short loc_18018DB77
0x18018db16  mov     rcx, [rbp+1A8h]; this
0x18018db1d  lea     r8, aWil; "wil"
0x18018db24  mov     edx, 0DCh; void *
0x18018db29  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018db2e  mov     ebx, eax
0x18018db30  lea     rcx, [rsp+2A0h+var_268]
0x18018db35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018db3a  jmp     short loc_18018DB50
0x18018db3c  call    cs:__imp_GetLastError
0x18018db43  nop     dword ptr [rax+rax+00h]
0x18018db48  cmp     eax, 2
0x18018db4b  jnz     short loc_18018DB5E
0x18018db4d  mov     ebx, r15d
0x18018db50  lea     rcx, [rsp+2A0h+var_260]
0x18018db55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018db5a  mov     eax, ebx
0x18018db5c  jmp     short loc_18018DB77
0x18018db5e  mov     rcx, [rbp+1A8h]; this
0x18018db65  lea     r8, aWil; "wil"
0x18018db6c  mov     edx, 0D0h; void *
0x18018db71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018db76  nop
0x18018db77  mov     rcx, [rbp+1A0h+var_40]
0x18018db7e  xor     rcx, rsp; StackCookie
0x18018db81  call    __security_check_cookie
0x18018db86  add     rsp, 270h
0x18018db8d  pop     r15
0x18018db8f  pop     r14
0x18018db91  pop     r12
0x18018db93  pop     rdi
0x18018db94  pop     rsi
0x18018db95  pop     rbx
0x18018db96  pop     rbp
0x18018db97  retn
```
