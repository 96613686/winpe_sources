# CHttpAgent::SetDecompression(bool)

- ea: `0x1800cc3c0`
- end: `0x1800cc47d`
- name: `?SetDecompression@CHttpAgent@@UEAAJ_N@Z`
- size: `189`
- prototype: `__int64 __fastcall(CHttpAgent *__hidden this, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008618`
- `0x180009ab4`
- `0x1800cc3c0`
- `0x1800cf144`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc457`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cc445`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cc445`
- `WINHTTP!WinHttpSetOption` at `0x1800cc40f`
- `WINHTTP!WinHttpSetOption` at `0x1800cc40f`

## string_xrefs

- `0x1800cc41e`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
__int64 __fastcall CHttpAgent::SetDecompression(CHttpAgent *this, char a2)
{
  void *v4; // rcx
  const char *v5; // r9
  int Buffer; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CHttpAgent::_ImpersonateUserToken((__int64)this);
  v4 = (void *)*((_QWORD *)this + 1);
  Buffer = a2 != 0 ? 3 : 0;
  if ( WinHttpSetOption(v4, 0x76u, &Buffer, 4u) )
    return 0;
  else
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x20A,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                           v5);
}

```

## disassembly

```asm
0x1800cc3c0  mov     [rsp+arg_10], rbx
0x1800cc3c5  push    rdi
0x1800cc3c6  sub     rsp, 40h
0x1800cc3ca  mov     rax, cs:__security_cookie
0x1800cc3d1  xor     rax, rsp
0x1800cc3d4  mov     [rsp+48h+var_18], rax
0x1800cc3d9  mov     bl, dl
0x1800cc3db  mov     [rsp+48h+Token], 0FFFFFFFFFFFFFFFFh
0x1800cc3e4  lea     rdx, [rsp+48h+Token]
0x1800cc3e9  mov     rdi, rcx
0x1800cc3ec  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cc3f1  mov     rcx, [rdi+8]; hInternet
0x1800cc3f5  lea     r8, [rsp+48h+Buffer]; lpBuffer
0x1800cc3fa  mov     r9d, 4; dwBufferLength
0x1800cc400  neg     bl
0x1800cc402  sbb     eax, eax
0x1800cc404  and     eax, 3
0x1800cc407  lea     edx, [r9+72h]; dwOption
0x1800cc40b  mov     [rsp+48h+Buffer], eax
0x1800cc40f  call    cs:__imp_WinHttpSetOption
0x1800cc415  test    eax, eax
0x1800cc417  jnz     short loc_1800CC433
0x1800cc419  mov     rcx, [rsp+48h]; this
0x1800cc41e  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cc425  mov     edx, 20Ah; void *
0x1800cc42a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc42f  mov     edi, eax
0x1800cc431  jmp     short loc_1800CC435
0x1800cc433  xor     edi, edi
0x1800cc435  mov     rbx, [rsp+48h+Token]
0x1800cc43a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc43e  jz      short loc_1800CC45D
0x1800cc440  mov     rdx, rbx; Token
0x1800cc443  xor     ecx, ecx; Thread
0x1800cc445  call    cs:__imp_SetThreadToken
0x1800cc44b  test    eax, eax
0x1800cc44d  jz      short loc_1800CC477
0x1800cc44f  test    rbx, rbx
0x1800cc452  jz      short loc_1800CC45D
0x1800cc454  mov     rcx, rbx; hObject
0x1800cc457  call    cs:__imp_CloseHandle
0x1800cc45d  mov     eax, edi
0x1800cc45f  mov     rcx, [rsp+48h+var_18]
0x1800cc464  xor     rcx, rsp; StackCookie
0x1800cc467  call    __security_check_cookie
0x1800cc46c  mov     rbx, [rsp+48h+arg_10]
0x1800cc471  add     rsp, 40h
0x1800cc475  pop     rdi
0x1800cc476  retn
0x1800cc477  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
