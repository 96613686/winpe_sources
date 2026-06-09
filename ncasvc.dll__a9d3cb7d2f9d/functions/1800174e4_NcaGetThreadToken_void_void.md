# NcaGetThreadToken(void *,void * *)

- ea: `0x1800174e4`
- end: `0x1800175c2`
- name: `?NcaGetThreadToken@@YAKPEAXPEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180017708`

## callees

- `0x180004f34`
- `0x1800174e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017569`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017559`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001753e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001753e`
- `RPCRT4!RpcImpersonateClient` at `0x1800174f1`
- `RPCRT4!RpcImpersonateClient` at `0x1800174f1`
- `RPCRT4!RpcRevertToSelf` at `0x1800175a8`
- `RPCRT4!RpcRevertToSelf` at `0x1800175a8`

## pseudocode

```c
__int64 __fastcall NcaGetThreadToken(void *a1, void **a2)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax

  LastError = RpcImpersonateClient(a1);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, LastError);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xFu, 1, a2) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, LastError);
    }
    RpcRevertToSelf();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800174e4  mov     [rsp+arg_0], rbx
0x1800174e9  push    rdi
0x1800174ea  sub     rsp, 20h
0x1800174ee  mov     rdi, rdx
0x1800174f1  call    cs:__imp_RpcImpersonateClient
0x1800174f8  nop     dword ptr [rax+rax+00h]
0x1800174fd  mov     ebx, eax
0x1800174ff  test    eax, eax
0x180017501  jz      short loc_18001753E
0x180017503  mov     rcx, cs:WPP_GLOBAL_Control
0x18001750a  lea     rax, WPP_GLOBAL_Control
0x180017511  cmp     rcx, rax
0x180017514  jz      loc_1800175B4
0x18001751a  test    byte ptr [rcx+1Ch], 1
0x18001751e  jz      loc_1800175B4
0x180017524  mov     rcx, [rcx+10h]
0x180017528  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x18001752f  mov     edx, 0Ch
0x180017534  mov     r9d, ebx
0x180017537  call    WPP_SF_d
0x18001753c  jmp     short loc_1800175B4
0x18001753e  call    cs:__imp_GetCurrentThread
0x180017545  nop     dword ptr [rax+rax+00h]
0x18001754a  mov     edx, 0Fh; DesiredAccess
0x18001754f  mov     r9, rdi; TokenHandle
0x180017552  mov     rcx, rax; ThreadHandle
0x180017555  lea     r8d, [rdx-0Eh]; OpenAsSelf
0x180017559  call    cs:__imp_OpenThreadToken
0x180017560  nop     dword ptr [rax+rax+00h]
0x180017565  test    eax, eax
0x180017567  jnz     short loc_1800175A8
0x180017569  call    cs:__imp_GetLastError
0x180017570  nop     dword ptr [rax+rax+00h]
0x180017575  mov     ebx, eax
0x180017577  mov     rcx, cs:WPP_GLOBAL_Control
0x18001757e  lea     rax, WPP_GLOBAL_Control
0x180017585  cmp     rcx, rax
0x180017588  jz      short loc_1800175A8
0x18001758a  test    byte ptr [rcx+1Ch], 1
0x18001758e  jz      short loc_1800175A8
0x180017590  mov     rcx, [rcx+10h]
0x180017594  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x18001759b  mov     edx, 0Dh
0x1800175a0  mov     r9d, ebx
0x1800175a3  call    WPP_SF_d
0x1800175a8  call    cs:__imp_RpcRevertToSelf
0x1800175af  nop     dword ptr [rax+rax+00h]
0x1800175b4  mov     eax, ebx
0x1800175b6  mov     rbx, [rsp+28h+arg_0]
0x1800175bb  add     rsp, 20h
0x1800175bf  pop     rdi
0x1800175c0  retn
```
