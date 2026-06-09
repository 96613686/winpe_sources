# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002db00`
- end: `0x18002dc9c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002da8c`

## callees

- `0x180027b10`
- `0x18002a8e4`
- `0x18002cedc`
- `0x18002cefc`
- `0x18002d5c4`
- `0x18002d70c`
- `0x18002db00`
- `0x180031680`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18002db64`
- `KERNEL32!OpenSemaphoreW` at `0x18002dbf4`
- `KERNEL32!OpenSemaphoreW` at `0x18002db64`
- `KERNEL32!OpenSemaphoreW` at `0x18002dbf4`
- `KERNEL32!GetLastError` at `0x18002db74`
- `KERNEL32!GetLastError` at `0x18002db74`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x18002db00  mov     [rsp-8+arg_8], rbx
0x18002db05  mov     [rsp-8+arg_18], rdi
0x18002db0a  push    rbp
0x18002db0b  lea     rbp, [rsp-170h]
0x18002db13  sub     rsp, 270h
0x18002db1a  mov     rax, cs:__security_cookie
0x18002db21  xor     rax, rsp
0x18002db24  mov     [rbp+170h+var_10], rax
0x18002db2b  mov     r9, rcx; pszSrc
0x18002db2e  mov     qword ptr [r8], 0
0x18002db35  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18002db3a  mov     edx, 104h; cchDest
0x18002db3f  mov     rdi, r8
0x18002db42  call    StringCopyWorkerW
0x18002db47  lea     r8, aP0; "_p0"
0x18002db4e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002db53  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002db58  lea     r8, [rsp+270h+pszDest]; lpName
0x18002db5d  xor     edx, edx; bInheritHandle
0x18002db5f  mov     ecx, 1F0003h; dwDesiredAccess
0x18002db64  call    cs:__imp_OpenSemaphoreW
0x18002db6a  mov     [rsp+270h+var_230], rax
0x18002db6f  test    rax, rax
0x18002db72  jnz     short loc_18002DB9B
0x18002db74  call    cs:__imp_GetLastError
0x18002db7a  cmp     eax, 2
0x18002db7d  jz      loc_18002DC6A
0x18002db83  mov     rcx, [rbp+178h]; this
0x18002db8a  mov     edx, 0D0h; void *
0x18002db8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002db94  mov     ebx, eax
0x18002db96  jmp     loc_18002DC6C
0x18002db9b  lea     rdx, [rsp+270h+var_23C]; int *
0x18002dba0  mov     [rsp+270h+var_23C], 0
0x18002dba8  mov     rcx, rax; hHandle
0x18002dbab  mov     [rsp+270h+var_240], 0
0x18002dbb3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002dbb8  mov     ebx, eax
0x18002dbba  test    eax, eax
0x18002dbbc  jns     short loc_18002DBD7
0x18002dbbe  mov     rcx, [rbp+178h]; this
0x18002dbc5  mov     r9d, eax; char *
0x18002dbc8  mov     edx, 0D6h; void *
0x18002dbcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbd2  jmp     loc_18002DC6C
0x18002dbd7  lea     r8, asc_180039068; "h"
0x18002dbde  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002dbe3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dbe8  lea     r8, [rsp+270h+pszDest]; lpName
0x18002dbed  xor     edx, edx; bInheritHandle
0x18002dbef  mov     ecx, 1F0003h; dwDesiredAccess
0x18002dbf4  call    cs:__imp_OpenSemaphoreW
0x18002dbfa  mov     [rsp+270h+var_238], rax
0x18002dbff  test    rax, rax
0x18002dc02  jnz     short loc_18002DC23
0x18002dc04  mov     rcx, [rbp+178h]; this
0x18002dc0b  mov     edx, 0DCh; void *
0x18002dc10  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dc15  mov     ebx, eax
0x18002dc17  lea     rcx, [rsp+270h+var_238]
0x18002dc1c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dc21  jmp     short loc_18002DC6C
0x18002dc23  lea     rdx, [rsp+270h+var_240]; int *
0x18002dc28  mov     rcx, rax; hHandle
0x18002dc2b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002dc30  mov     ebx, eax
0x18002dc32  test    eax, eax
0x18002dc34  jns     short loc_18002DC4C
0x18002dc36  mov     rcx, [rbp+178h]; this
0x18002dc3d  mov     r9d, eax; char *
0x18002dc40  mov     edx, 0DEh; void *
0x18002dc45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc4a  jmp     short loc_18002DC17
0x18002dc4c  lea     rcx, [rsp+270h+var_238]
0x18002dc51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dc56  movsxd  rcx, [rsp+270h+var_240]
0x18002dc5b  movsxd  rax, [rsp+270h+var_23C]
0x18002dc60  shl     rcx, 1Fh
0x18002dc64  or      rcx, rax
0x18002dc67  mov     [rdi], rcx
0x18002dc6a  xor     ebx, ebx
0x18002dc6c  lea     rcx, [rsp+270h+var_230]
0x18002dc71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dc76  mov     eax, ebx
0x18002dc78  mov     rcx, [rbp+170h+var_10]
0x18002dc7f  xor     rcx, rsp; StackCookie
0x18002dc82  call    __security_check_cookie
0x18002dc87  lea     r11, [rsp+270h+var_s0]
0x18002dc8f  mov     rbx, [r11+18h]
0x18002dc93  mov     rdi, [r11+28h]
0x18002dc97  mov     rsp, r11
0x18002dc9a  pop     rbp
0x18002dc9b  retn
```
