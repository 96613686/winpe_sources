# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18001ce90`
- end: `0x18001d046`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001c684`
- `0x18001ca7c`

## callees

- `0x18001ce90`
- `0x18001dd08`
- `0x180024f68`
- `0x180025528`
- `0x180026388`
- `0x18002667c`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001cf52`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001cfd1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001cf52`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001cfd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cffa`

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
  unsigned int v18; // r8d
  unsigned int v19; // ebx
  __int64 v20; // rdx
  wil::details *v21; // rcx
  HANDLE v22; // rbx
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
    v22 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v22 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v22);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v21);
      v19 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v20 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v19 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v20 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v20, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v19;
}

```

## disassembly

```asm
0x18001ce90  mov     [rsp+arg_8], rbx
0x18001ce95  mov     [rsp+arg_18], rbp
0x18001ce9a  push    rsi
0x18001ce9b  push    rdi
0x18001ce9c  push    r14
0x18001ce9e  sub     rsp, 250h
0x18001cea5  mov     rax, cs:__security_cookie
0x18001ceac  xor     rax, rsp
0x18001ceaf  mov     [rsp+268h+var_28], rax
0x18001ceb7  mov     rbx, r8
0x18001ceba  mov     rbp, rcx
0x18001cebd  mov     r8, rdx
0x18001cec0  test    bl, 3
0x18001cec3  jnz     loc_18001D040
0x18001cec9  lea     rax, [rsp+268h+Name]
0x18001cece  shr     rbx, 2
0x18001ced2  sub     r8, rax
0x18001ced5  lea     rcx, [rsp+268h+Name]
0x18001ceda  xor     r14d, r14d
0x18001cedd  mov     edx, 104h
0x18001cee2  lea     edi, [r14+1]
0x18001cee6  lea     rax, [rdx+7FFFFEFAh]
0x18001ceed  test    rax, rax
0x18001cef0  jz      short loc_18001CF08
0x18001cef2  movzx   eax, word ptr [r8+rcx]
0x18001cef7  test    ax, ax
0x18001cefa  jz      short loc_18001CF08
0x18001cefc  mov     [rcx], ax
0x18001ceff  add     rcx, 2
0x18001cf03  sub     rdx, rdi; unsigned __int64
0x18001cf06  jnz     short loc_18001CEE6
0x18001cf08  lea     rax, [rcx-2]
0x18001cf0c  test    rdx, rdx
0x18001cf0f  lea     r8, aP0; "_p0"
0x18001cf16  cmovnz  rax, rcx
0x18001cf1a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001cf1f  mov     [rax], r14w
0x18001cf23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cf28  mov     rsi, rbx
0x18001cf2b  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001cf33  mov     r8d, edi
0x18001cf36  shr     rsi, 1Fh
0x18001cf3a  and     ebx, 7FFFFFFFh
0x18001cf40  mov     [rsp+268h+dwFlags], r14d; int
0x18001cf45  lea     r9, [rsp+268h+Name]; lpName
0x18001cf4a  mov     edx, ebx; lInitialCount
0x18001cf4c  cmova   r8d, ebx; lMaximumCount
0x18001cf50  xor     ecx, ecx; lpSemaphoreAttributes
0x18001cf52  call    cs:__imp_CreateSemaphoreExW
0x18001cf59  nop     dword ptr [rax+rax+00h]
0x18001cf5e  mov     rbx, rax
0x18001cf61  test    rax, rax
0x18001cf64  jnz     short loc_18001CF8B
0x18001cf66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001cf6b  mov     ebx, eax
0x18001cf6d  test    eax, eax
0x18001cf6f  jns     short loc_18001CFA2
0x18001cf71  mov     edx, 88h; void *
0x18001cf76  mov     rcx, [rsp+268h]; this
0x18001cf7e  mov     r9d, eax; char *
0x18001cf81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf86  jmp     loc_18001D015
0x18001cf8b  call    cs:__imp_GetLastError
0x18001cf92  nop     dword ptr [rax+rax+00h]
0x18001cf97  mov     rdx, rbx
0x18001cf9a  mov     rcx, rbp
0x18001cf9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001cfa2  lea     r8, asc_180035100; "h"
0x18001cfa9  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001cfae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cfb3  test    esi, esi
0x18001cfb5  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001cfbd  lea     r9, [rsp+268h+Name]; lpName
0x18001cfc2  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x18001cfc7  cmovnz  edi, esi
0x18001cfca  mov     edx, esi; lInitialCount
0x18001cfcc  mov     r8d, edi; lMaximumCount
0x18001cfcf  xor     ecx, ecx; lpSemaphoreAttributes
0x18001cfd1  call    cs:__imp_CreateSemaphoreExW
0x18001cfd8  nop     dword ptr [rax+rax+00h]
0x18001cfdd  mov     rbx, rax
0x18001cfe0  test    rax, rax
0x18001cfe3  jnz     short loc_18001CFFA
0x18001cfe5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001cfea  mov     ebx, eax
0x18001cfec  test    eax, eax
0x18001cfee  jns     short loc_18001D012
0x18001cff0  mov     edx, 8Dh
0x18001cff5  jmp     loc_18001CF76
0x18001cffa  call    cs:__imp_GetLastError
0x18001d001  nop     dword ptr [rax+rax+00h]
0x18001d006  mov     rdx, rbx
0x18001d009  lea     rcx, [rbp+8]
0x18001d00d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001d012  mov     ebx, r14d
0x18001d015  mov     eax, ebx
0x18001d017  mov     rcx, [rsp+268h+var_28]
0x18001d01f  xor     rcx, rsp; StackCookie
0x18001d022  call    __security_check_cookie
0x18001d027  lea     r11, [rsp+268h+var_18]
0x18001d02f  mov     rbx, [r11+28h]
0x18001d033  mov     rbp, [r11+38h]
0x18001d037  mov     rsp, r11
0x18001d03a  pop     r14
0x18001d03c  pop     rdi
0x18001d03d  pop     rsi
0x18001d03e  retn
0x18001d040  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
