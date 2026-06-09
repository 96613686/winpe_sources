# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18006b2f0`
- end: `0x18006b4e5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006b0cc`
- `0x18007800c`

## callees

- `0x180048848`
- `0x18006b2f0`
- `0x18006b4ec`
- `0x180077e58`
- `0x180077efc`
- `0x180078070`
- `0x18007ac50`
- `0x180082870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b49d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b49d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006b3b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006b419`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006b3b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006b419`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r10
  __int64 v6; // r9
  WCHAR *v7; // rax
  WCHAR v8; // r8
  WCHAR *v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // r9
  HANDLE v13; // rax
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  unsigned int v16; // r8d
  unsigned int LastError; // ebx
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v24; // r8d
  const char *v25; // r9
  size_t v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v29; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v5 = 2147483646;
  v6 = 260;
  v7 = Name;
  do
  {
    if ( !v5 )
      break;
    v8 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v7++ = v8;
    --v5;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 1;
  if ( v6 )
    v9 = v7;
  *v9 = 0;
  v10 = 260;
  v11 = Name;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW_0(&Name[v12], 260 - v12, (size_t *)v10, L"_p0", v26);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v30[0] = v13;
  if ( v13 )
  {
    v28 = 0;
    v27 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v28);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, v15, L"h");
      v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v29 = v18;
      if ( v18 )
      {
        v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v27);
        LastError = v21;
        if ( v21 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
          *a3 = v28 | (unsigned __int64)((__int64)v27 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v26);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v16, (const char *)(unsigned int)ValueFromSemaphore, v26);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v24, v25);
}

```

## disassembly

```asm
0x18006b2f0  push    rbp
0x18006b2f2  push    rbx
0x18006b2f3  push    rsi
0x18006b2f4  push    rdi
0x18006b2f5  lea     rbp, [rsp-178h]
0x18006b2fd  sub     rsp, 278h
0x18006b304  mov     rax, cs:__security_cookie
0x18006b30b  xor     rax, rsp
0x18006b30e  mov     [rbp+190h+var_30], rax
0x18006b315  mov     rdi, r8
0x18006b318  xor     esi, esi
0x18006b31a  mov     [r8], rsi
0x18006b31d  mov     edx, 104h
0x18006b322  mov     r10d, 7FFFFFFEh
0x18006b328  mov     r9d, edx
0x18006b32b  lea     rax, [rsp+290h+Name]
0x18006b330  test    r10, r10
0x18006b333  jz      short loc_18006B354
0x18006b335  movzx   r8d, word ptr [rcx]
0x18006b339  test    r8w, r8w
0x18006b33d  jz      short loc_18006B354
0x18006b33f  add     rcx, 2
0x18006b343  mov     [rax], r8w
0x18006b347  add     rax, 2
0x18006b34b  dec     r10
0x18006b34e  sub     r9, 1
0x18006b352  jnz     short loc_18006B330
0x18006b354  lea     rcx, [rax-2]
0x18006b358  test    r9, r9
0x18006b35b  cmovnz  rcx, rax
0x18006b35f  mov     [rcx], si
0x18006b362  mov     r8, rdx
0x18006b365  lea     rax, [rsp+290h+Name]
0x18006b36a  cmp     [rax], si
0x18006b36d  jz      short loc_18006B379
0x18006b36f  add     rax, 2
0x18006b373  sub     r8, 1; pcchNewDestLength
0x18006b377  jnz     short loc_18006B36A
0x18006b379  mov     rax, r8
0x18006b37c  mov     rcx, rdx
0x18006b37f  sub     rcx, r8
0x18006b382  neg     rax
0x18006b385  sbb     r9, r9
0x18006b388  and     r9, rcx
0x18006b38b  test    r8, r8
0x18006b38e  jz      short loc_18006B3A8
0x18006b390  sub     rdx, r9; cchDest
0x18006b393  lea     rcx, [rsp+290h+Name]
0x18006b398  lea     rcx, [rcx+r9*2]; pszDest
0x18006b39c  lea     r9, aP0; "_p0"
0x18006b3a3  call    StringCopyWorkerW_0
0x18006b3a8  lea     r8, [rsp+290h+Name]; lpName
0x18006b3ad  xor     edx, edx; bInheritHandle
0x18006b3af  mov     ecx, 1F0003h; dwDesiredAccess
0x18006b3b4  call    cs:__imp_OpenSemaphoreW
0x18006b3ba  mov     [rsp+290h+var_250], rax
0x18006b3bf  test    rax, rax
0x18006b3c2  jz      loc_18006B49D
0x18006b3c8  mov     [rsp+290h+var_25C], esi
0x18006b3cc  mov     [rsp+290h+var_260], esi
0x18006b3d0  lea     rdx, [rsp+290h+var_25C]; int *
0x18006b3d5  mov     rcx, rax; hHandle
0x18006b3d8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006b3dd  mov     ebx, eax
0x18006b3df  test    eax, eax
0x18006b3e1  jns     short loc_18006B3FC
0x18006b3e3  mov     rcx, [rbp+198h]; this
0x18006b3ea  mov     r9d, eax; char *
0x18006b3ed  mov     edx, 0D6h; void *
0x18006b3f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b3f7  jmp     loc_18006B4AA
0x18006b3fc  lea     r8, asc_1800BE6AC; "h"
0x18006b403  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18006b408  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006b40d  lea     r8, [rsp+290h+Name]; lpName
0x18006b412  xor     edx, edx; bInheritHandle
0x18006b414  mov     ecx, 1F0003h; dwDesiredAccess
0x18006b419  call    cs:__imp_OpenSemaphoreW
0x18006b41f  mov     [rsp+290h+var_258], rax
0x18006b424  test    rax, rax
0x18006b427  jz      short loc_18006B47E
0x18006b429  lea     rdx, [rsp+290h+var_260]; int *
0x18006b42e  mov     rcx, rax; hHandle
0x18006b431  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006b436  mov     ebx, eax
0x18006b438  test    eax, eax
0x18006b43a  jns     short loc_18006B452
0x18006b43c  mov     rcx, [rbp+198h]; this
0x18006b443  mov     r9d, eax; char *
0x18006b446  mov     edx, 0DEh; void *
0x18006b44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b450  jmp     short loc_18006B491
0x18006b452  lea     rcx, [rsp+290h+var_258]
0x18006b457  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006b45c  movsxd  rcx, [rsp+290h+var_260]
0x18006b461  shl     rcx, 1Fh
0x18006b465  movsxd  rax, [rsp+290h+var_25C]
0x18006b46a  or      rcx, rax
0x18006b46d  mov     [rdi], rcx
0x18006b470  lea     rcx, [rsp+290h+var_250]
0x18006b475  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006b47a  xor     eax, eax
0x18006b47c  jmp     short loc_18006B4CA
0x18006b47e  mov     rcx, [rbp+198h]; this
0x18006b485  mov     edx, 0DCh; void *
0x18006b48a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b48f  mov     ebx, eax
0x18006b491  lea     rcx, [rsp+290h+var_258]
0x18006b496  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006b49b  jmp     short loc_18006B4AA
0x18006b49d  call    cs:__imp_GetLastError
0x18006b4a3  cmp     eax, 2
0x18006b4a6  jnz     short loc_18006B4B8
0x18006b4a8  mov     ebx, esi
0x18006b4aa  lea     rcx, [rsp+290h+var_250]
0x18006b4af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006b4b4  mov     eax, ebx
0x18006b4b6  jmp     short loc_18006B4CA
0x18006b4b8  mov     rcx, [rbp+198h]; this
0x18006b4bf  mov     edx, 0D0h; void *
0x18006b4c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b4c9  nop
0x18006b4ca  mov     rcx, [rbp+190h+var_30]
0x18006b4d1  xor     rcx, rsp; StackCookie
0x18006b4d4  call    __security_check_cookie
0x18006b4d9  add     rsp, 278h
0x18006b4e0  pop     rdi
0x18006b4e1  pop     rsi
0x18006b4e2  pop     rbx
0x18006b4e3  pop     rbp
0x18006b4e4  retn
```
