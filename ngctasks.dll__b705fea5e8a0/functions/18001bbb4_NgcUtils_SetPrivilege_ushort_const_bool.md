# NgcUtils::SetPrivilege(ushort const *,bool)

- ea: `0x18001bbb4`
- end: `0x18001bc96`
- name: `?SetPrivilege@NgcUtils@@YAJPEBG_N@Z`
- size: `226`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f0f4`

## callees

- `0x180006330`
- `0x18000cc14`
- `0x1800102ec`
- `0x18001bbb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bbe8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bbe8`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001bc64`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001bc64`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bc0f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bc0f`

## string_xrefs

- `0x18001bc01`: `SeShutdownPrivilege`
- `0x18001bc23`: `onecore\ds\security\ngc\utils\common\lib\tokenutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::SetPrivilege(NgcUtils *this, const unsigned __int16 *a2)
{
  int v2; // ebx
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (unsigned __int8)a2;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState = 0;
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &NewState.Privileges[0].Luid) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2 * v2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        LastError = 0;
        goto LABEL_9;
      }
      v5 = 253;
    }
    else
    {
      v5 = 243;
    }
  }
  else
  {
    v5 = 237;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tokenutils.cpp",
                v4);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001bbb4  push    rbx
0x18001bbb6  sub     rsp, 50h
0x18001bbba  mov     rax, cs:__security_cookie
0x18001bbc1  xor     rax, rsp
0x18001bbc4  mov     [rsp+58h+var_10], rax
0x18001bbc9  movzx   ebx, dl
0x18001bbcc  mov     [rsp+58h+TokenHandle], 0
0x18001bbd5  call    cs:__imp_GetCurrentProcess
0x18001bbdb  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001bbe0  mov     edx, 28h ; '('; DesiredAccess
0x18001bbe5  mov     rcx, rax; ProcessHandle
0x18001bbe8  call    cs:__imp_OpenProcessToken
0x18001bbee  test    eax, eax
0x18001bbf0  jnz     short loc_18001BBF9
0x18001bbf2  mov     edx, 0EDh
0x18001bbf7  jmp     short loc_18001BC1E
0x18001bbf9  xorps   xmm0, xmm0
0x18001bbfc  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x18001bc01  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18001bc08  xor     ecx, ecx; lpSystemName
0x18001bc0a  movups  xmmword ptr [rsp+38h], xmm0
0x18001bc0f  call    cs:__imp_LookupPrivilegeValueW
0x18001bc15  test    eax, eax
0x18001bc17  jnz     short loc_18001BC33
0x18001bc19  mov     edx, 0F3h; void *
0x18001bc1e  mov     rcx, [rsp+58h]; this
0x18001bc23  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001bc2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bc2f  mov     ebx, eax
0x18001bc31  jmp     short loc_18001BC77
0x18001bc33  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18001bc38  lea     r8, [rsp+58h+NewState]; NewState
0x18001bc3d  mov     eax, ebx
0x18001bc3f  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18001bc48  add     eax, eax
0x18001bc4a  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18001bc52  xor     r9d, r9d; BufferLength
0x18001bc55  mov     [rsp+58h+NewState.Privileges.Attributes], eax
0x18001bc59  xor     edx, edx; DisableAllPrivileges
0x18001bc5b  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18001bc64  call    cs:__imp_AdjustTokenPrivileges
0x18001bc6a  test    eax, eax
0x18001bc6c  jnz     short loc_18001BC75
0x18001bc6e  mov     edx, 0FDh
0x18001bc73  jmp     short loc_18001BC1E
0x18001bc75  xor     ebx, ebx
0x18001bc77  lea     rcx, [rsp+58h+TokenHandle]
0x18001bc7c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001bc81  mov     eax, ebx
0x18001bc83  mov     rcx, [rsp+58h+var_10]
0x18001bc88  xor     rcx, rsp; StackCookie
0x18001bc8b  call    __security_check_cookie
0x18001bc90  add     rsp, 50h
0x18001bc94  pop     rbx
0x18001bc95  retn
```
