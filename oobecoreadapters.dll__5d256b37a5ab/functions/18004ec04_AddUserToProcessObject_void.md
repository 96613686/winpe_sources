# AddUserToProcessObject(void *)

- ea: `0x18004ec04`
- end: `0x18004ed3f`
- name: `?AddUserToProcessObject@@YAJPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004cc5c`
- `0x18004ce04`
- `0x18005d084`
- `0x18005f3cc`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x1800175bc`
- `0x18004ea00`
- `0x18004ec04`
- `0x180054340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ecb5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ecb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec16`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004ec26`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004ec26`

## string_xrefs

- `0x18004ec44`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004ec78`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004ecc4`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004ed01`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall AddUserToProcessObject(void *a1)
{
  DWORD CurrentProcessId; // eax
  HANDLE v3; // rbx
  const char *v4; // r9
  unsigned int LastError; // ebx
  int v6; // eax
  __int64 v7; // r8
  int v8; // edi
  const char *v9; // r9
  int v10; // eax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE v15; // [rsp+40h] [rbp+18h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v3 = OpenProcess(0x60400u, 0, CurrentProcessId);
  v15 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = AddUserToHandle(v3, a1, 0x101400u);
    v8 = v6;
    if ( v6 >= 0 )
    {
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0,
        v7);
      if ( OpenProcessToken(v3, 0x60008u, &TokenHandle) )
      {
        v10 = AddUserToHandle(TokenHandle, a1, 0xEu);
        LastError = v10;
        if ( v10 >= 0 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          LastError = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
          (const char *)(unsigned int)v10,
          v12);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x85,
                      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                      v9);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
        (const char *)(unsigned int)v6,
        v12);
      LastError = v8;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x80,
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                  v4);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x18004ec04  mov     [rsp+arg_0], rbx
0x18004ec09  mov     [rsp+arg_18], rsi
0x18004ec0e  push    rdi; int
0x18004ec0f  sub     rsp, 20h
0x18004ec13  mov     rsi, rcx
0x18004ec16  call    cs:__imp_GetCurrentProcessId
0x18004ec1c  xor     edx, edx; bInheritHandle
0x18004ec1e  mov     ecx, 60400h; dwDesiredAccess
0x18004ec23  mov     r8d, eax; dwProcessId
0x18004ec26  call    cs:__imp_OpenProcess
0x18004ec2c  mov     rbx, rax
0x18004ec2f  mov     [rsp+28h+arg_10], rax
0x18004ec34  inc     rax
0x18004ec37  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004ec3d  jnz     short loc_18004EC5C
0x18004ec3f  mov     rcx, [rsp+28h]; this
0x18004ec44  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ec4b  mov     edx, 80h; void *
0x18004ec50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ec55  mov     ebx, eax
0x18004ec57  jmp     loc_18004ED23
0x18004ec5c  mov     r8d, 101400h; unsigned int
0x18004ec62  mov     rdx, rsi; void *
0x18004ec65  mov     rcx, rbx; Handle
0x18004ec68  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x18004ec6d  mov     edi, eax
0x18004ec6f  test    eax, eax
0x18004ec71  jns     short loc_18004EC93
0x18004ec73  mov     rcx, [rsp+28h]; this
0x18004ec78  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ec7f  mov     r9d, eax; char *
0x18004ec82  mov     edx, 82h; void *
0x18004ec87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec8c  mov     ebx, edi
0x18004ec8e  jmp     loc_18004ED23
0x18004ec93  xor     edx, edx
0x18004ec95  mov     [rsp+28h+TokenHandle], 0
0x18004ec9e  lea     rcx, [rsp+28h+TokenHandle]
0x18004eca3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004eca8  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18004ecad  mov     edx, 60008h; DesiredAccess
0x18004ecb2  mov     rcx, rbx; ProcessHandle
0x18004ecb5  call    cs:__imp_OpenProcessToken
0x18004ecbb  test    eax, eax
0x18004ecbd  jnz     short loc_18004ECE3
0x18004ecbf  mov     rcx, [rsp+28h]; this
0x18004ecc4  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004eccb  mov     edx, 85h; void *
0x18004ecd0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ecd5  mov     ebx, eax
0x18004ecd7  lea     rcx, [rsp+28h+TokenHandle]
0x18004ecdc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ece1  jmp     short loc_18004ED23
0x18004ece3  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x18004ece8  mov     r8d, 0Eh; unsigned int
0x18004ecee  mov     rdx, rsi; void *
0x18004ecf1  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x18004ecf6  mov     ebx, eax
0x18004ecf8  test    eax, eax
0x18004ecfa  jns     short loc_18004ED17
0x18004ecfc  mov     rcx, [rsp+28h]; this
0x18004ed01  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ed08  mov     r9d, eax; char *
0x18004ed0b  mov     edx, 87h; void *
0x18004ed10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed15  jmp     short loc_18004ECD7
0x18004ed17  lea     rcx, [rsp+28h+TokenHandle]
0x18004ed1c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ed21  xor     ebx, ebx
0x18004ed23  lea     rcx, [rsp+28h+arg_10]
0x18004ed28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ed2d  mov     rsi, [rsp+28h+arg_18]
0x18004ed32  mov     eax, ebx
0x18004ed34  mov     rbx, [rsp+28h+arg_0]
0x18004ed39  add     rsp, 20h
0x18004ed3d  pop     rdi
0x18004ed3e  retn
```
