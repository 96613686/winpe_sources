# CJobSharedData::GetOwnerToken(void)

- ea: `0x180094218`
- end: `0x18009430a`
- name: `?GetOwnerToken@CJobSharedData@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081e20`
- `0x1800943c4`

## callees

- `0x180039b68`
- `0x180094218`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009428a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009428a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009429d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009429d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180094265`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180094265`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800942da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800942da`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800942c8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800942c8`

## string_xrefs

- `0x1800942f8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall CJobSharedData::GetOwnerToken(RTL_SRWLOCK *a1, void **a2)
{
  RTL_SRWLOCK *v4; // rbp
  void *v5; // rsi
  DWORD LastError; // ebx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a2 = 0;
  v4 = a1 + 34;
  AcquireSRWLockShared(a1 + 34);
  if ( (unsigned __int64)a1[20].Ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = *a2;
    if ( *a2 && v5 != (void *)-1LL )
    {
      LastError = GetLastError();
      CloseHandle(v5);
      SetLastError(LastError);
    }
    *a2 = 0;
    if ( !DuplicateTokenEx(a1[20].Ptr, 0xEu, 0, SecurityImpersonation, TokenImpersonation, a2) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA51,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        v7);
  }
  ReleaseSRWLockShared(v4);
  return a2;
}

```

## disassembly

```asm
0x180094218  mov     rax, rsp
0x18009421b  mov     [rax+18h], rbx
0x18009421f  mov     [rax+20h], rbp
0x180094223  push    rsi
0x180094224  push    rdi
0x180094225  push    r14
0x180094227  sub     rsp, 50h
0x18009422b  mov     rdi, rdx
0x18009422e  mov     r14, rcx
0x180094231  mov     [rax-20h], rdx
0x180094235  mov     dword ptr [rax-38h], 0
0x18009423c  xor     eax, eax
0x18009423e  mov     [rdx], rax
0x180094241  mov     [rsp+68h+var_38], 1
0x180094249  xorps   xmm0, xmm0
0x18009424c  movups  [rsp+68h+var_30], xmm0
0x180094251  lea     rbp, [rcx+110h]
0x180094258  mov     qword ptr [rsp+68h+var_30], rbp
0x18009425d  mov     byte ptr [rsp+68h+var_30+8], 1
0x180094262  mov     rcx, rbp; SRWLock
0x180094265  call    cs:__imp_AcquireSRWLockShared
0x18009426b  nop
0x18009426c  mov     rax, [r14+0A0h]
0x180094273  dec     rax
0x180094276  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009427a  ja      short loc_1800942D7
0x18009427c  mov     rsi, [rdi]
0x18009427f  test    rsi, rsi
0x180094282  jz      short loc_1800942A3
0x180094284  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180094288  jz      short loc_1800942A3
0x18009428a  call    cs:__imp_GetLastError
0x180094290  mov     ebx, eax
0x180094292  mov     rcx, rsi; hObject
0x180094295  call    cs:__imp_CloseHandle
0x18009429b  mov     ecx, ebx; dwErrCode
0x18009429d  call    cs:__imp_SetLastError
0x1800942a3  mov     qword ptr [rdi], 0
0x1800942aa  mov     [rsp+68h+phNewToken], rdi; phNewToken
0x1800942af  mov     r9d, 2; ImpersonationLevel
0x1800942b5  mov     [rsp+68h+TokenType], r9d; TokenType
0x1800942ba  xor     r8d, r8d; lpTokenAttributes
0x1800942bd  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800942c1  mov     rcx, [r14+0A0h]; hExistingToken
0x1800942c8  call    cs:__imp_DuplicateTokenEx
0x1800942ce  mov     rcx, [rsp+68h]; this
0x1800942d3  test    eax, eax
0x1800942d5  jz      short loc_1800942F8
0x1800942d7  mov     rcx, rbp; SRWLock
0x1800942da  call    cs:__imp_ReleaseSRWLockShared
0x1800942e0  mov     rax, rdi
0x1800942e3  lea     r11, [rsp+68h+var_18]
0x1800942e8  mov     rbx, [r11+30h]
0x1800942ec  mov     rbp, [r11+38h]
0x1800942f0  mov     rsp, r11
0x1800942f3  pop     r14
0x1800942f5  pop     rdi
0x1800942f6  pop     rsi
0x1800942f7  retn
0x1800942f8  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800942ff  mov     edx, 0A51h; void *
0x180094304  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
