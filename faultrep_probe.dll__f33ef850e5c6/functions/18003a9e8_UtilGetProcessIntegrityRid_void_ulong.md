# UtilGetProcessIntegrityRid(void *,ulong *)

- ea: `0x18003a9e8`
- end: `0x18003ab1e`
- name: `?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004704c`

## callees

- `0x18000e30c`
- `0x180023ad8`
- `0x1800390e0`
- `0x18003a9e8`
- `0x18003af6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003aa51`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003aa51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aa78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aaad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aa78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aaad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab0b`

## string_xrefs

- `0x18003aa07`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18003aa87`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18003aad6`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
__int64 __fastcall UtilGetProcessIntegrityRid(HANDLE ProcessHandle, unsigned int *a2)
{
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  void **v7; // rax
  BOOL v8; // edi
  const char *v9; // r9
  void *v10; // rcx
  __int64 v11; // rdx
  void *v12; // [rsp+20h] [rbp-28h] BYREF
  void **v13; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF

  if ( !ProcessHandle )
  {
    v4 = 6018;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)0x80070057LL,
      (int)v12);
    return LastError;
  }
  if ( !a2 )
  {
    v4 = 6019;
    goto LABEL_3;
  }
  hObject = 0;
  v7 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v12, &hObject);
  v8 = OpenProcessToken(ProcessHandle, 8u, v7);
  if ( v12 )
  {
    v10 = *v13;
    *v13 = v12;
    if ( (unsigned __int64)v10 + 1 > 1 )
      CloseHandle(v10);
  }
  if ( !v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1786,
                  (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
                  v9);
    goto LABEL_12;
  }
  if ( (unsigned __int64)hObject + 1 <= 1 )
  {
    LastError = -2147418113;
    v11 = 6023;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)LastError,
      (int)v12);
LABEL_12:
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    return LastError;
  }
  LastError = UtilGetTokenIntegrityRid(hObject, a2);
  if ( (LastError & 0x80000000) != 0 )
  {
    v11 = 6025;
    goto LABEL_16;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x18003a9e8  mov     [rsp+arg_8], rbx
0x18003a9ed  push    rdi
0x18003a9ee  sub     rsp, 40h
0x18003a9f2  mov     rbx, rdx
0x18003a9f5  mov     rdi, rcx
0x18003a9f8  test    rcx, rcx
0x18003a9fb  jnz     short loc_18003AA22
0x18003a9fd  mov     edx, 1782h; void *
0x18003aa02  mov     rcx, [rsp+48h]; this
0x18003aa07  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18003aa0e  mov     ebx, 80070057h
0x18003aa13  mov     r9d, ebx; char *
0x18003aa16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa1b  mov     eax, ebx
0x18003aa1d  jmp     loc_18003AB13
0x18003aa22  test    rbx, rbx
0x18003aa25  jnz     short loc_18003AA2E
0x18003aa27  mov     edx, 1783h
0x18003aa2c  jmp     short loc_18003AA02
0x18003aa2e  lea     rdx, [rsp+48h+hObject]
0x18003aa33  mov     [rsp+48h+hObject], 0
0x18003aa3c  lea     rcx, [rsp+48h+var_28]
0x18003aa41  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003aa46  mov     r8, rax; TokenHandle
0x18003aa49  mov     edx, 8; DesiredAccess
0x18003aa4e  mov     rcx, rdi; ProcessHandle
0x18003aa51  call    cs:__imp_OpenProcessToken
0x18003aa57  mov     r8, [rsp+48h+var_28]
0x18003aa5c  mov     edi, eax
0x18003aa5e  test    r8, r8
0x18003aa61  jz      short loc_18003AA7E
0x18003aa63  mov     rdx, [rsp+48h+var_20]
0x18003aa68  mov     rcx, [rdx]; hObject
0x18003aa6b  mov     [rdx], r8
0x18003aa6e  lea     rdx, [rcx+1]
0x18003aa72  cmp     rdx, 1
0x18003aa76  jbe     short loc_18003AA7E
0x18003aa78  call    cs:__imp_CloseHandle
0x18003aa7e  test    edi, edi
0x18003aa80  jnz     short loc_18003AAB8
0x18003aa82  mov     rcx, [rsp+48h]; this
0x18003aa87  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18003aa8e  mov     edx, 1786h; void *
0x18003aa93  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003aa98  mov     ebx, eax
0x18003aa9a  mov     rcx, [rsp+48h+hObject]; hObject
0x18003aa9f  lea     rdx, [rcx+1]
0x18003aaa3  cmp     rdx, 1
0x18003aaa7  jbe     loc_18003AA1B
0x18003aaad  call    cs:__imp_CloseHandle
0x18003aab3  jmp     loc_18003AA1B
0x18003aab8  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x18003aabd  lea     rax, [rcx+1]
0x18003aac1  cmp     rax, 1
0x18003aac5  ja      short loc_18003AAE7
0x18003aac7  mov     ebx, 8000FFFFh
0x18003aacc  mov     edx, 1787h; void *
0x18003aad1  mov     rcx, [rsp+48h]; this
0x18003aad6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18003aadd  mov     r9d, ebx; char *
0x18003aae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aae5  jmp     short loc_18003AA9A
0x18003aae7  mov     rdx, rbx; unsigned int *
0x18003aaea  call    ?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z; UtilGetTokenIntegrityRid(void *,ulong *)
0x18003aaef  mov     ebx, eax
0x18003aaf1  test    eax, eax
0x18003aaf3  jns     short loc_18003AAFC
0x18003aaf5  mov     edx, 1789h
0x18003aafa  jmp     short loc_18003AAD1
0x18003aafc  mov     rcx, [rsp+48h+hObject]; hObject
0x18003ab01  lea     rax, [rcx+1]
0x18003ab05  cmp     rax, 1
0x18003ab09  jbe     short loc_18003AB11
0x18003ab0b  call    cs:__imp_CloseHandle
0x18003ab11  xor     eax, eax
0x18003ab13  mov     rbx, [rsp+48h+arg_8]
0x18003ab18  add     rsp, 40h
0x18003ab1c  pop     rdi
0x18003ab1d  retn
```
