# CThreadContext::ImpersonateSelf(void)

- ea: `0x180016960`
- end: `0x1800169d8`
- name: `?ImpersonateSelf@CThreadContext@@QEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ccec`

## callees

- `0x1800063e0`
- `0x180016960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001698b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001698b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800169ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800169ba`

## pseudocode

```c
__int64 __fastcall CThreadContext::ImpersonateSelf(CThreadContext *this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  __int64 result; // rax
  BOOL v5; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle);
  result = ResultFromWin32Bool(v3);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -2147023888 )
    {
      v5 = ImpersonateSelf(SecurityImpersonation);
      result = ResultFromWin32Bool(v5);
      if ( (int)result >= 0 )
        *((_DWORD *)this + 4) = 1;
    }
  }
  else
  {
    CloseHandle(TokenHandle);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180016960  push    rbx
0x180016962  sub     rsp, 20h
0x180016966  mov     rbx, rcx
0x180016969  mov     [rsp+28h+TokenHandle], 0
0x180016972  call    cs:__imp_GetCurrentThread
0x180016978  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001697d  mov     edx, 2000Ch; DesiredAccess
0x180016982  mov     rcx, rax; ThreadHandle
0x180016985  mov     r8d, 1; OpenAsSelf
0x18001698b  call    cs:__imp_OpenThreadToken
0x180016991  mov     ecx, eax; int
0x180016993  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180016998  test    eax, eax
0x18001699a  js      short loc_1800169AE
0x18001699c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800169a1  call    cs:__imp_CloseHandle
0x1800169a7  mov     eax, 1
0x1800169ac  jmp     short loc_1800169D2
0x1800169ae  cmp     eax, 800703F0h
0x1800169b3  jnz     short loc_1800169D2
0x1800169b5  mov     ecx, 2; ImpersonationLevel
0x1800169ba  call    cs:__imp_ImpersonateSelf
0x1800169c0  mov     ecx, eax; int
0x1800169c2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800169c7  test    eax, eax
0x1800169c9  js      short loc_1800169D2
0x1800169cb  mov     dword ptr [rbx+10h], 1
0x1800169d2  add     rsp, 20h
0x1800169d6  pop     rbx
0x1800169d7  retn
```
