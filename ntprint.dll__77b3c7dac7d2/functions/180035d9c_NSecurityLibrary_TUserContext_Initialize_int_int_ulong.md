# NSecurityLibrary::TUserContext::Initialize(int,int,ulong)

- ea: `0x180035d9c`
- end: `0x180035e18`
- name: `?Initialize@TUserContext@NSecurityLibrary@@AEAAJHHK@Z`
- size: `124`
- prototype: `__int64 __fastcall(NSecurityLibrary::TUserContext *__hidden this, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800356a8`

## callees

- `0x180018d18`
- `0x180035d9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035da9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035da9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035de0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035de0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035df2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035df2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035dbf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035dbf`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TUserContext::Initialize(void **this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  int v4; // r9d
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 8u, 1, this + 2);
  v4 = *((_DWORD *)this + 7);
  if ( v3 )
  {
    *((_DWORD *)this + 7) = v4 & 0xFFFFFFFB;
  }
  else
  {
    if ( (v4 & 4) == 0 )
      return GetLastErrorAsHResult();
    if ( GetLastError() != 1008 )
      return GetLastErrorAsHResult();
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, this + 2) )
      return GetLastErrorAsHResult();
  }
  return 0;
}

```

## disassembly

```asm
0x180035d9c  mov     [rsp+arg_0], rbx
0x180035da1  push    rdi
0x180035da2  sub     rsp, 20h
0x180035da6  mov     rbx, rcx
0x180035da9  call    cs:__imp_GetCurrentThread
0x180035daf  mov     edx, 8; DesiredAccess
0x180035db4  lea     r9, [rbx+10h]; TokenHandle
0x180035db8  mov     rcx, rax; ThreadHandle
0x180035dbb  lea     r8d, [rdx-7]; OpenAsSelf
0x180035dbf  call    cs:__imp_OpenThreadToken
0x180035dc5  mov     r9d, [rbx+1Ch]
0x180035dc9  test    eax, eax
0x180035dcb  jnz     short loc_180035E03
0x180035dcd  test    r9b, 4
0x180035dd1  jz      short loc_180035DFC
0x180035dd3  call    cs:__imp_GetLastError
0x180035dd9  cmp     eax, 3F0h
0x180035dde  jnz     short loc_180035DFC
0x180035de0  call    cs:__imp_GetCurrentProcess
0x180035de6  lea     r8, [rbx+10h]; TokenHandle
0x180035dea  mov     edx, 8; DesiredAccess
0x180035def  mov     rcx, rax; ProcessHandle
0x180035df2  call    cs:__imp_OpenProcessToken
0x180035df8  test    eax, eax
0x180035dfa  jnz     short loc_180035E0B
0x180035dfc  call    GetLastErrorAsHResult
0x180035e01  jmp     short loc_180035E0D
0x180035e03  and     r9d, 0FFFFFFFBh
0x180035e07  mov     [rbx+1Ch], r9d
0x180035e0b  xor     eax, eax
0x180035e0d  mov     rbx, [rsp+28h+arg_0]
0x180035e12  add     rsp, 20h
0x180035e16  pop     rdi
0x180035e17  retn
```
