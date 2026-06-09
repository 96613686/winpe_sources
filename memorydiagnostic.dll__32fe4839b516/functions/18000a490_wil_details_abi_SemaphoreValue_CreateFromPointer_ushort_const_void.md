# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000a490`
- end: `0x18000a64d`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `445`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008cc4`
- `0x1800090b8`

## callees

- `0x1800026b0`
- `0x18000a490`
- `0x18000d7a8`
- `0x1800113a4`
- `0x180013fb8`
- `0x1800162d8`
- `0x1800188bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a592`
- `KERNEL32!GetLastError` at `0x18000a601`
- `KERNEL32!GetLastError` at `0x18000a592`
- `KERNEL32!GetLastError` at `0x18000a601`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a552`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a5d8`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a552`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a5d8`

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
0x18000a490  mov     [rsp+arg_8], rbx
0x18000a495  mov     [rsp+arg_18], rbp
0x18000a49a  push    rsi
0x18000a49b  push    rdi
0x18000a49c  push    r14
0x18000a49e  sub     rsp, 250h
0x18000a4a5  mov     rax, cs:__security_cookie
0x18000a4ac  xor     rax, rsp
0x18000a4af  mov     [rsp+268h+var_28], rax
0x18000a4b7  mov     rbx, r8
0x18000a4ba  mov     rbp, rcx
0x18000a4bd  mov     r8, rdx
0x18000a4c0  test    bl, 3
0x18000a4c3  jnz     loc_18000A647
0x18000a4c9  lea     rax, [rsp+268h+Name]
0x18000a4ce  shr     rbx, 2
0x18000a4d2  sub     r8, rax
0x18000a4d5  lea     rcx, [rsp+268h+Name]
0x18000a4da  xor     r14d, r14d
0x18000a4dd  mov     edx, 104h
0x18000a4e2  lea     edi, [r14+1]
0x18000a4e6  lea     rax, [rdx+7FFFFEFAh]
0x18000a4ed  test    rax, rax
0x18000a4f0  jz      short loc_18000A508
0x18000a4f2  movzx   eax, word ptr [r8+rcx]
0x18000a4f7  test    ax, ax
0x18000a4fa  jz      short loc_18000A508
0x18000a4fc  mov     [rcx], ax
0x18000a4ff  add     rcx, 2
0x18000a503  sub     rdx, rdi; unsigned __int64
0x18000a506  jnz     short loc_18000A4E6
0x18000a508  lea     rax, [rcx-2]
0x18000a50c  test    rdx, rdx
0x18000a50f  lea     r8, aP0; "_p0"
0x18000a516  cmovnz  rax, rcx
0x18000a51a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000a51f  mov     [rax], r14w
0x18000a523  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a528  mov     rsi, rbx
0x18000a52b  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a533  mov     r8d, edi
0x18000a536  shr     rsi, 1Fh
0x18000a53a  and     ebx, 7FFFFFFFh
0x18000a540  mov     [rsp+268h+dwFlags], r14d; int
0x18000a545  lea     r9, [rsp+268h+Name]; lpName
0x18000a54a  mov     edx, ebx; lInitialCount
0x18000a54c  cmova   r8d, ebx; lMaximumCount
0x18000a550  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a552  call    cs:__imp_CreateSemaphoreExW
0x18000a559  nop     dword ptr [rax+rax+00h]
0x18000a55e  mov     rbx, rax
0x18000a561  test    rax, rax
0x18000a564  jnz     short loc_18000A592
0x18000a566  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a56b  mov     ebx, eax
0x18000a56d  test    eax, eax
0x18000a56f  jns     short loc_18000A5A9
0x18000a571  mov     edx, 88h; void *
0x18000a576  mov     rcx, [rsp+268h]; this
0x18000a57e  lea     r8, aWil; "wil"
0x18000a585  mov     r9d, eax; char *
0x18000a588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a58d  jmp     loc_18000A61C
0x18000a592  call    cs:__imp_GetLastError
0x18000a599  nop     dword ptr [rax+rax+00h]
0x18000a59e  mov     rdx, rbx
0x18000a5a1  mov     rcx, rbp
0x18000a5a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a5a9  lea     r8, asc_1800264F8; "h"
0x18000a5b0  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000a5b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a5ba  test    esi, esi
0x18000a5bc  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a5c4  lea     r9, [rsp+268h+Name]; lpName
0x18000a5c9  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x18000a5ce  cmovnz  edi, esi
0x18000a5d1  mov     edx, esi; lInitialCount
0x18000a5d3  mov     r8d, edi; lMaximumCount
0x18000a5d6  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a5d8  call    cs:__imp_CreateSemaphoreExW
0x18000a5df  nop     dword ptr [rax+rax+00h]
0x18000a5e4  mov     rbx, rax
0x18000a5e7  test    rax, rax
0x18000a5ea  jnz     short loc_18000A601
0x18000a5ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a5f1  mov     ebx, eax
0x18000a5f3  test    eax, eax
0x18000a5f5  jns     short loc_18000A619
0x18000a5f7  mov     edx, 8Dh
0x18000a5fc  jmp     loc_18000A576
0x18000a601  call    cs:__imp_GetLastError
0x18000a608  nop     dword ptr [rax+rax+00h]
0x18000a60d  mov     rdx, rbx
0x18000a610  lea     rcx, [rbp+8]
0x18000a614  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a619  mov     ebx, r14d
0x18000a61c  mov     eax, ebx
0x18000a61e  mov     rcx, [rsp+268h+var_28]
0x18000a626  xor     rcx, rsp; StackCookie
0x18000a629  call    __security_check_cookie
0x18000a62e  lea     r11, [rsp+268h+var_18]
0x18000a636  mov     rbx, [r11+28h]
0x18000a63a  mov     rbp, [r11+38h]
0x18000a63e  mov     rsp, r11
0x18000a641  pop     r14
0x18000a643  pop     rdi
0x18000a644  pop     rsi
0x18000a645  retn
0x18000a647  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
