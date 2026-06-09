# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180004bf0`
- end: `0x180004dad`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `445`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800043ec`
- `0x1800047e4`

## callees

- `0x1800017a0`
- `0x180004bf0`
- `0x1800058f8`
- `0x180007fb4`
- `0x180008a50`
- `0x180009934`
- `0x180009ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004cb2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d38`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004cb2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d61`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        char *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v4; // rbx
  signed __int64 v5; // r8
  WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rsi
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned __int64 v17; // rdx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  wil::details *v20; // rcx
  HANDLE v21; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v4 = a3 >> 2;
  v5 = a2 - (char *)Name;
  v6 = Name;
  v7 = 260;
  v8 = 1;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v5);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v7;
  }
  while ( v7 );
  v10 = v6 - 1;
  if ( v7 )
    v10 = v6;
  *v10 = 0;
  StringCchCatW(Name, v7, L"_p0");
  v11 = 1;
  v12 = v4 >> 31;
  v13 = v4 & 0x7FFFFFFF;
  if ( v13 )
    v11 = v13;
  Semaphore = CreateSemaphoreExW(0, v13, v11, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
LABEL_15:
    StringCchCatW(Name, v17, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v21 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v21 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v21);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v20);
      v18 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v19 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v19 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"wil",
    (const char *)(unsigned int)LastErrorFailHr,
    dwFlags);
  return v18;
}

```

## disassembly

```asm
0x180004bf0  mov     [rsp+arg_8], rbx
0x180004bf5  mov     [rsp+arg_18], rbp
0x180004bfa  push    rsi
0x180004bfb  push    rdi
0x180004bfc  push    r14
0x180004bfe  sub     rsp, 250h
0x180004c05  mov     rax, cs:__security_cookie
0x180004c0c  xor     rax, rsp
0x180004c0f  mov     [rsp+268h+var_28], rax
0x180004c17  mov     rbx, r8
0x180004c1a  mov     rbp, rcx
0x180004c1d  mov     r8, rdx
0x180004c20  test    bl, 3
0x180004c23  jnz     loc_180004DA7
0x180004c29  lea     rax, [rsp+268h+Name]
0x180004c2e  shr     rbx, 2
0x180004c32  sub     r8, rax
0x180004c35  lea     rcx, [rsp+268h+Name]
0x180004c3a  xor     r14d, r14d
0x180004c3d  mov     edx, 104h
0x180004c42  lea     edi, [r14+1]
0x180004c46  lea     rax, [rdx+7FFFFEFAh]
0x180004c4d  test    rax, rax
0x180004c50  jz      short loc_180004C68
0x180004c52  movzx   eax, word ptr [r8+rcx]
0x180004c57  test    ax, ax
0x180004c5a  jz      short loc_180004C68
0x180004c5c  mov     [rcx], ax
0x180004c5f  add     rcx, 2
0x180004c63  sub     rdx, rdi; unsigned __int64
0x180004c66  jnz     short loc_180004C46
0x180004c68  lea     rax, [rcx-2]
0x180004c6c  test    rdx, rdx
0x180004c6f  lea     r8, aP0; "_p0"
0x180004c76  cmovnz  rax, rcx
0x180004c7a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180004c7f  mov     [rax], r14w
0x180004c83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004c88  mov     rsi, rbx
0x180004c8b  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004c93  mov     r8d, edi
0x180004c96  shr     rsi, 1Fh
0x180004c9a  and     ebx, 7FFFFFFFh
0x180004ca0  mov     [rsp+268h+dwFlags], r14d; int
0x180004ca5  lea     r9, [rsp+268h+Name]; lpName
0x180004caa  mov     edx, ebx; lInitialCount
0x180004cac  cmova   r8d, ebx; lMaximumCount
0x180004cb0  xor     ecx, ecx; lpSemaphoreAttributes
0x180004cb2  call    cs:__imp_CreateSemaphoreExW
0x180004cb9  nop     dword ptr [rax+rax+00h]
0x180004cbe  mov     rbx, rax
0x180004cc1  test    rax, rax
0x180004cc4  jnz     short loc_180004CF2
0x180004cc6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ccb  mov     ebx, eax
0x180004ccd  test    eax, eax
0x180004ccf  jns     short loc_180004D09
0x180004cd1  mov     edx, 88h; void *
0x180004cd6  mov     rcx, [rsp+268h]; this
0x180004cde  lea     r8, aWil; "wil"
0x180004ce5  mov     r9d, eax; char *
0x180004ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ced  jmp     loc_180004D7C
0x180004cf2  call    cs:__imp_GetLastError
0x180004cf9  nop     dword ptr [rax+rax+00h]
0x180004cfe  mov     rdx, rbx
0x180004d01  mov     rcx, rbp
0x180004d04  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004d09  lea     r8, asc_18003CCF0; "h"
0x180004d10  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180004d15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004d1a  test    esi, esi
0x180004d1c  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004d24  lea     r9, [rsp+268h+Name]; lpName
0x180004d29  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x180004d2e  cmovnz  edi, esi
0x180004d31  mov     edx, esi; lInitialCount
0x180004d33  mov     r8d, edi; lMaximumCount
0x180004d36  xor     ecx, ecx; lpSemaphoreAttributes
0x180004d38  call    cs:__imp_CreateSemaphoreExW
0x180004d3f  nop     dword ptr [rax+rax+00h]
0x180004d44  mov     rbx, rax
0x180004d47  test    rax, rax
0x180004d4a  jnz     short loc_180004D61
0x180004d4c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d51  mov     ebx, eax
0x180004d53  test    eax, eax
0x180004d55  jns     short loc_180004D79
0x180004d57  mov     edx, 8Dh
0x180004d5c  jmp     loc_180004CD6
0x180004d61  call    cs:__imp_GetLastError
0x180004d68  nop     dword ptr [rax+rax+00h]
0x180004d6d  mov     rdx, rbx
0x180004d70  lea     rcx, [rbp+8]
0x180004d74  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004d79  mov     ebx, r14d
0x180004d7c  mov     eax, ebx
0x180004d7e  mov     rcx, [rsp+268h+var_28]
0x180004d86  xor     rcx, rsp; StackCookie
0x180004d89  call    __security_check_cookie
0x180004d8e  lea     r11, [rsp+268h+var_18]
0x180004d96  mov     rbx, [r11+28h]
0x180004d9a  mov     rbp, [r11+38h]
0x180004d9e  mov     rsp, r11
0x180004da1  pop     r14
0x180004da3  pop     rdi
0x180004da4  pop     rsi
0x180004da5  retn
0x180004da7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
