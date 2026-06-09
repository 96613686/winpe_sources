# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18006fbd0`
- end: `0x18006fdd8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `520`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006f9a0`
- `0x18007cad0`

## callees

- `0x18004e88c`
- `0x18006fbd0`
- `0x18006fde0`
- `0x18007c910`
- `0x18007c9b8`
- `0x18007cb34`
- `0x18007f800`
- `0x18008789c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd89`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006fc94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006fcff`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006fc94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006fcff`

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
0x18006fbd0  push    rbp
0x18006fbd2  push    rbx
0x18006fbd3  push    rsi
0x18006fbd4  push    rdi
0x18006fbd5  lea     rbp, [rsp-178h]
0x18006fbdd  sub     rsp, 278h
0x18006fbe4  mov     rax, cs:__security_cookie
0x18006fbeb  xor     rax, rsp
0x18006fbee  mov     [rbp+190h+var_30], rax
0x18006fbf5  mov     rdi, r8
0x18006fbf8  xor     esi, esi
0x18006fbfa  mov     [r8], rsi
0x18006fbfd  mov     edx, 104h
0x18006fc02  mov     r10d, 7FFFFFFEh
0x18006fc08  mov     r9d, edx
0x18006fc0b  lea     rax, [rsp+290h+Name]
0x18006fc10  test    r10, r10
0x18006fc13  jz      short loc_18006FC34
0x18006fc15  movzx   r8d, word ptr [rcx]
0x18006fc19  test    r8w, r8w
0x18006fc1d  jz      short loc_18006FC34
0x18006fc1f  add     rcx, 2
0x18006fc23  mov     [rax], r8w
0x18006fc27  add     rax, 2
0x18006fc2b  dec     r10
0x18006fc2e  sub     r9, 1
0x18006fc32  jnz     short loc_18006FC10
0x18006fc34  lea     rcx, [rax-2]
0x18006fc38  test    r9, r9
0x18006fc3b  cmovnz  rcx, rax
0x18006fc3f  mov     [rcx], si
0x18006fc42  mov     r8, rdx
0x18006fc45  lea     rax, [rsp+290h+Name]
0x18006fc4a  cmp     [rax], si
0x18006fc4d  jz      short loc_18006FC59
0x18006fc4f  add     rax, 2
0x18006fc53  sub     r8, 1; pcchNewDestLength
0x18006fc57  jnz     short loc_18006FC4A
0x18006fc59  mov     rax, r8
0x18006fc5c  mov     rcx, rdx
0x18006fc5f  sub     rcx, r8
0x18006fc62  neg     rax
0x18006fc65  sbb     r9, r9
0x18006fc68  and     r9, rcx
0x18006fc6b  test    r8, r8
0x18006fc6e  jz      short loc_18006FC88
0x18006fc70  sub     rdx, r9; cchDest
0x18006fc73  lea     rcx, [rsp+290h+Name]
0x18006fc78  lea     rcx, [rcx+r9*2]; pszDest
0x18006fc7c  lea     r9, aP0; "_p0"
0x18006fc83  call    StringCopyWorkerW_0
0x18006fc88  lea     r8, [rsp+290h+Name]; lpName
0x18006fc8d  xor     edx, edx; bInheritHandle
0x18006fc8f  mov     ecx, 1F0003h; dwDesiredAccess
0x18006fc94  call    cs:__imp_OpenSemaphoreW
0x18006fc9b  nop     dword ptr [rax+rax+00h]
0x18006fca0  mov     [rsp+290h+var_250], rax
0x18006fca5  test    rax, rax
0x18006fca8  jz      loc_18006FD89
0x18006fcae  mov     [rsp+290h+var_25C], esi
0x18006fcb2  mov     [rsp+290h+var_260], esi
0x18006fcb6  lea     rdx, [rsp+290h+var_25C]; int *
0x18006fcbb  mov     rcx, rax; hHandle
0x18006fcbe  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006fcc3  mov     ebx, eax
0x18006fcc5  test    eax, eax
0x18006fcc7  jns     short loc_18006FCE2
0x18006fcc9  mov     rcx, [rbp+198h]; this
0x18006fcd0  mov     r9d, eax; char *
0x18006fcd3  mov     edx, 0D6h; void *
0x18006fcd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fcdd  jmp     loc_18006FD9C
0x18006fce2  lea     r8, asc_1800C16CC; "h"
0x18006fce9  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18006fcee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006fcf3  lea     r8, [rsp+290h+Name]; lpName
0x18006fcf8  xor     edx, edx; bInheritHandle
0x18006fcfa  mov     ecx, 1F0003h; dwDesiredAccess
0x18006fcff  call    cs:__imp_OpenSemaphoreW
0x18006fd06  nop     dword ptr [rax+rax+00h]
0x18006fd0b  mov     [rsp+290h+var_258], rax
0x18006fd10  test    rax, rax
0x18006fd13  jz      short loc_18006FD6A
0x18006fd15  lea     rdx, [rsp+290h+var_260]; int *
0x18006fd1a  mov     rcx, rax; hHandle
0x18006fd1d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006fd22  mov     ebx, eax
0x18006fd24  test    eax, eax
0x18006fd26  jns     short loc_18006FD3E
0x18006fd28  mov     rcx, [rbp+198h]; this
0x18006fd2f  mov     r9d, eax; char *
0x18006fd32  mov     edx, 0DEh; void *
0x18006fd37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fd3c  jmp     short loc_18006FD7D
0x18006fd3e  lea     rcx, [rsp+290h+var_258]
0x18006fd43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fd48  movsxd  rcx, [rsp+290h+var_260]
0x18006fd4d  shl     rcx, 1Fh
0x18006fd51  movsxd  rax, [rsp+290h+var_25C]
0x18006fd56  or      rcx, rax
0x18006fd59  mov     [rdi], rcx
0x18006fd5c  lea     rcx, [rsp+290h+var_250]
0x18006fd61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fd66  xor     eax, eax
0x18006fd68  jmp     short loc_18006FDBC
0x18006fd6a  mov     rcx, [rbp+198h]; this
0x18006fd71  mov     edx, 0DCh; void *
0x18006fd76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006fd7b  mov     ebx, eax
0x18006fd7d  lea     rcx, [rsp+290h+var_258]
0x18006fd82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fd87  jmp     short loc_18006FD9C
0x18006fd89  call    cs:__imp_GetLastError
0x18006fd90  nop     dword ptr [rax+rax+00h]
0x18006fd95  cmp     eax, 2
0x18006fd98  jnz     short loc_18006FDAA
0x18006fd9a  mov     ebx, esi
0x18006fd9c  lea     rcx, [rsp+290h+var_250]
0x18006fda1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fda6  mov     eax, ebx
0x18006fda8  jmp     short loc_18006FDBC
0x18006fdaa  mov     rcx, [rbp+198h]; this
0x18006fdb1  mov     edx, 0D0h; void *
0x18006fdb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006fdbb  nop
0x18006fdbc  mov     rcx, [rbp+190h+var_30]
0x18006fdc3  xor     rcx, rsp; StackCookie
0x18006fdc6  call    __security_check_cookie
0x18006fdcb  add     rsp, 278h
0x18006fdd2  pop     rdi
0x18006fdd3  pop     rsi
0x18006fdd4  pop     rbx
0x18006fdd5  pop     rbp
0x18006fdd6  retn
```
