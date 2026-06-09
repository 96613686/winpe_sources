# CThreadContext::ImpersonateUser(void *)

- ea: `0x18001a8a8`
- end: `0x18001a933`
- name: `?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z`
- size: `139`
- prototype: `__int64 __fastcall(CThreadContext *this, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800190f4`
- `0x18001a634`
- `0x18002b6b8`
- `0x180032ce0`
- `0x18003735c`
- `0x180039d6c`

## callees

- `0x180006580`
- `0x18001a8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a8d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a8d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a91b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a91b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a8f8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a8f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThreadContext::ImpersonateUser(CThreadContext *this, void *a2)
{
  void **v3; // rdi
  HANDLE CurrentThread; // rax
  BOOL v6; // eax
  int v7; // ebx
  BOOL v8; // eax

  v3 = (void **)((char *)this + 8);
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, v3);
  v7 = ResultFromWin32Bool(v6);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023888 )
  {
    v8 = ImpersonateLoggedOnUser(a2);
    v7 = ResultFromWin32Bool(v8);
    if ( v7 < 0 )
    {
      if ( *v3 )
      {
        CloseHandle(*v3);
        *v3 = 0;
      }
    }
    else
    {
      *(_DWORD *)this = 1;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a8a8  push    rbx
0x18001a8aa  push    rbp
0x18001a8ab  push    rsi
0x18001a8ac  push    rdi
0x18001a8ad  sub     rsp, 28h
0x18001a8b1  mov     rbp, rdx
0x18001a8b4  lea     rdi, [rcx+8]
0x18001a8b8  mov     rsi, rcx
0x18001a8bb  call    cs:__imp_GetCurrentThread
0x18001a8c1  mov     r9, rdi; TokenHandle
0x18001a8c4  mov     edx, 2000Ch; DesiredAccess
0x18001a8c9  mov     rcx, rax; ThreadHandle
0x18001a8cc  mov     r8d, 1; OpenAsSelf
0x18001a8d2  call    cs:__imp_OpenThreadToken
0x18001a8d8  mov     ecx, eax; int
0x18001a8da  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001a8df  mov     ebx, eax
0x18001a8e1  mov     eax, 80000000h
0x18001a8e6  lea     ecx, [rbx+rax]
0x18001a8e9  test    eax, ecx
0x18001a8eb  jnz     short loc_18001A8F5
0x18001a8ed  cmp     ebx, 800703F0h
0x18001a8f3  jnz     short loc_18001A928
0x18001a8f5  mov     rcx, rbp; hToken
0x18001a8f8  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a8fe  mov     ecx, eax; int
0x18001a900  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001a905  mov     ebx, eax
0x18001a907  test    eax, eax
0x18001a909  js      short loc_18001A913
0x18001a90b  mov     dword ptr [rsi], 1
0x18001a911  jmp     short loc_18001A928
0x18001a913  mov     rcx, [rdi]; hObject
0x18001a916  test    rcx, rcx
0x18001a919  jz      short loc_18001A928
0x18001a91b  call    cs:__imp_CloseHandle
0x18001a921  mov     qword ptr [rdi], 0
0x18001a928  mov     eax, ebx
0x18001a92a  add     rsp, 28h
0x18001a92e  pop     rdi
0x18001a92f  pop     rsi
0x18001a930  pop     rbp
0x18001a931  pop     rbx
0x18001a932  retn
```
