# CThreadContext::ImpersonateUser(void *)

- ea: `0x18001378c`
- end: `0x180013830`
- name: `?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z`
- size: `164`
- prototype: `int(CThreadContext *__hidden this, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013144`
- `0x18001bdd8`
- `0x18002e1dc`
- `0x18002e63c`
- `0x180038798`
- `0x18003b26c`

## callees

- `0x180011c00`
- `0x18001378c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800137bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800137bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001379f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001379f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013811`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800137e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800137e8`

## pseudocode

```c
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
0x18001378c  push    rbx
0x18001378e  push    rbp
0x18001378f  push    rsi
0x180013790  push    rdi
0x180013791  sub     rsp, 28h
0x180013795  mov     rbp, rdx
0x180013798  lea     rdi, [rcx+8]
0x18001379c  mov     rsi, rcx
0x18001379f  call    cs:__imp_GetCurrentThread
0x1800137a6  nop     dword ptr [rax+rax+00h]
0x1800137ab  mov     r9, rdi; TokenHandle
0x1800137ae  mov     edx, 2000Ch; DesiredAccess
0x1800137b3  mov     rcx, rax; ThreadHandle
0x1800137b6  mov     r8d, 1; OpenAsSelf
0x1800137bc  call    cs:__imp_OpenThreadToken
0x1800137c3  nop     dword ptr [rax+rax+00h]
0x1800137c8  mov     ecx, eax; int
0x1800137ca  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800137cf  mov     ebx, eax
0x1800137d1  mov     eax, 80000000h
0x1800137d6  lea     ecx, [rbx+rax]
0x1800137d9  test    eax, ecx
0x1800137db  jnz     short loc_1800137E5
0x1800137dd  cmp     ebx, 800703F0h
0x1800137e3  jnz     short loc_180013824
0x1800137e5  mov     rcx, rbp; hToken
0x1800137e8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800137ef  nop     dword ptr [rax+rax+00h]
0x1800137f4  mov     ecx, eax; int
0x1800137f6  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800137fb  mov     ebx, eax
0x1800137fd  test    eax, eax
0x1800137ff  js      short loc_180013809
0x180013801  mov     dword ptr [rsi], 1
0x180013807  jmp     short loc_180013824
0x180013809  mov     rcx, [rdi]; hObject
0x18001380c  test    rcx, rcx
0x18001380f  jz      short loc_180013824
0x180013811  call    cs:__imp_CloseHandle
0x180013818  nop     dword ptr [rax+rax+00h]
0x18001381d  mov     qword ptr [rdi], 0
0x180013824  mov     eax, ebx
0x180013826  add     rsp, 28h
0x18001382a  pop     rdi
0x18001382b  pop     rsi
0x18001382c  pop     rbp
0x18001382d  pop     rbx
0x18001382e  retn
```
