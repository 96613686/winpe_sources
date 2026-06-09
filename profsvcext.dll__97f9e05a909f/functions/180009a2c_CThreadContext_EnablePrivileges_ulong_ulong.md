# CThreadContext::EnablePrivileges(ulong *,ulong)

- ea: `0x180009a2c`
- end: `0x180009bce`
- name: `?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z`
- size: `418`
- prototype: `__int64 __fastcall(CThreadContext *this, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009770`

## callees

- `0x1800045d0`
- `0x1800055c8`
- `0x180009a2c`
- `0x18000f97c`
- `0x18000f9c8`
- `0x18000fc28`
- `0x18001044c`
- `0x18001997c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009af9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009af9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b0e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b25`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180009b3c`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180009b3c`
- `ntdll!RtlAdjustPrivilege` at `0x180009b73`
- `ntdll!RtlAdjustPrivilege` at `0x180009b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThreadContext::EnablePrivileges(CThreadContext *this, unsigned int *a2, int a3)
{
  void **v3; // rdi
  int v6; // ebx
  CThreadContext **v7; // r14
  _DWORD *v8; // rcx
  int v9; // eax
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  int v12; // eax
  CThreadContext *v13; // rcx
  BOOL v14; // eax
  __int64 v15; // rdi
  ULONG v16; // ecx
  NTSTATUS v17; // eax
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF
  int OldValue; // [rsp+60h] [rbp+40h] BYREF

  OldValue = a3;
  v3 = (void **)((char *)this + 32);
  TokenHandle = 0;
  *((_QWORD *)this + 4) = 0;
  v6 = ULongLongMult(1u, 4u, (unsigned __int64 *)&TokenHandle);
  if ( v6 >= 0 )
  {
    v6 = ResultFromHeapAlloc((SIZE_T)TokenHandle, v3);
    if ( v6 >= 0 )
    {
      v7 = (CThreadContext **)((char *)this + 40);
      TokenHandle = 0;
      *((_QWORD *)this + 5) = 0;
      v6 = ULongLongMult(1u, 4u, (unsigned __int64 *)&TokenHandle);
      if ( v6 < 0 || (v6 = ResultFromHeapAlloc((SIZE_T)TokenHandle, (void **)this + 5), v6 < 0) )
      {
        ResultFromHeapFree(*v3);
        *v3 = 0;
        return (unsigned int)v6;
      }
      v8 = *v3;
      *((_DWORD *)this + 6) = 1;
      v9 = *a2;
      TokenHandle = 0;
      *v8 = v9;
      *(_DWORD *)*v7 = 0;
      CurrentThread = GetCurrentThread();
      v11 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle);
      v12 = ResultFromWin32Bool(v11);
      v6 = v12;
      if ( v12 >= 0 )
      {
        CloseHandle(TokenHandle);
        v6 = 1;
LABEL_10:
        v15 = 0;
        while ( 1 )
        {
          if ( !(unsigned int)CThreadContext::PrivilegeEnabled(v13, a2[v15]) )
          {
            v16 = a2[v15];
            LOBYTE(OldValue) = 0;
            v17 = RtlAdjustPrivilege(v16, 1u, 1u, (PBOOLEAN)&OldValue);
            v6 = ResultFromWin32FromStatus(v17);
            if ( v6 < 0 )
            {
              CThreadContext::RevertPrivileges(this);
              return (unsigned int)v6;
            }
            if ( !(_BYTE)OldValue )
            {
              v13 = *v7;
              *((_DWORD *)*v7 + v15) = 1;
            }
          }
          v15 = (unsigned int)(v15 + 1);
          if ( (_DWORD)v15 )
            return (unsigned int)v6;
        }
      }
      if ( v12 == -2147023888 )
      {
        v14 = ImpersonateSelf(SecurityImpersonation);
        v6 = ResultFromWin32Bool(v14);
        if ( v6 >= 0 )
        {
          *((_DWORD *)this + 4) = 1;
          goto LABEL_10;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009a2c  mov     [rsp-28h+arg_8], rbx
0x180009a31  mov     [rsp-28h+arg_18], rsi
0x180009a36  mov     [rsp-28h+OldValue], r8d
0x180009a3b  push    rbp
0x180009a3c  push    rdi
0x180009a3d  push    r12
0x180009a3f  push    r14
0x180009a41  push    r15
0x180009a43  mov     rbp, rsp
0x180009a46  sub     rsp, 20h
0x180009a4a  lea     rdi, [rcx+20h]
0x180009a4e  mov     [rbp+TokenHandle], 0
0x180009a56  mov     r12, rdx
0x180009a59  mov     qword ptr [rdi], 0
0x180009a60  mov     edx, 4; unsigned __int64
0x180009a65  lea     r8, [rbp+TokenHandle]; unsigned __int64 *
0x180009a69  mov     rsi, rcx
0x180009a6c  lea     r15d, [rdx-3]
0x180009a70  mov     ecx, r15d; unsigned __int64
0x180009a73  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180009a78  mov     ebx, eax
0x180009a7a  test    eax, eax
0x180009a7c  js      loc_180009BB5
0x180009a82  mov     rcx, [rbp+TokenHandle]; dwBytes
0x180009a86  mov     rdx, rdi; void **
0x180009a89  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180009a8e  mov     ebx, eax
0x180009a90  test    eax, eax
0x180009a92  js      loc_180009BB5
0x180009a98  lea     r14, [rsi+28h]
0x180009a9c  mov     [rbp+TokenHandle], 0
0x180009aa4  lea     r8, [rbp+TokenHandle]; unsigned __int64 *
0x180009aa8  mov     qword ptr [r14], 0
0x180009aaf  lea     edx, [r15+3]; unsigned __int64
0x180009ab3  mov     ecx, r15d; unsigned __int64
0x180009ab6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180009abb  mov     ebx, eax
0x180009abd  test    eax, eax
0x180009abf  js      loc_180009BA6
0x180009ac5  mov     rcx, [rbp+TokenHandle]; dwBytes
0x180009ac9  mov     rdx, r14; void **
0x180009acc  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180009ad1  mov     ebx, eax
0x180009ad3  test    eax, eax
0x180009ad5  js      loc_180009BA6
0x180009adb  mov     rcx, [rdi]
0x180009ade  mov     [rsi+18h], r15d
0x180009ae2  mov     eax, [r12]
0x180009ae6  mov     [rbp+TokenHandle], 0
0x180009aee  mov     [rcx], eax
0x180009af0  mov     rax, [r14]
0x180009af3  mov     dword ptr [rax], 0
0x180009af9  call    cs:__imp_GetCurrentThread
0x180009aff  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180009b03  mov     r8d, r15d; OpenAsSelf
0x180009b06  mov     rcx, rax; ThreadHandle
0x180009b09  mov     edx, 2000Ch; DesiredAccess
0x180009b0e  call    cs:__imp_OpenThreadToken
0x180009b14  mov     ecx, eax; int
0x180009b16  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180009b1b  mov     ebx, eax
0x180009b1d  test    eax, eax
0x180009b1f  js      short loc_180009B30
0x180009b21  mov     rcx, [rbp+TokenHandle]; hObject
0x180009b25  call    cs:__imp_CloseHandle
0x180009b2b  mov     ebx, r15d
0x180009b2e  jmp     short loc_180009B53
0x180009b30  cmp     eax, 800703F0h
0x180009b35  jnz     short loc_180009BB5
0x180009b37  mov     ecx, 2; ImpersonationLevel
0x180009b3c  call    cs:__imp_ImpersonateSelf
0x180009b42  mov     ecx, eax; int
0x180009b44  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180009b49  mov     ebx, eax
0x180009b4b  test    eax, eax
0x180009b4d  js      short loc_180009BB5
0x180009b4f  mov     [rsi+10h], r15d
0x180009b53  xor     edi, edi
0x180009b55  mov     edx, [r12+rdi*4]; unsigned int
0x180009b59  call    ?PrivilegeEnabled@CThreadContext@@QEAAHK@Z; CThreadContext::PrivilegeEnabled(ulong)
0x180009b5e  test    eax, eax
0x180009b60  jnz     short loc_180009B93
0x180009b62  mov     ecx, [r12+rdi*4]; Privilege
0x180009b66  lea     r9, [rbp+OldValue]; OldValue
0x180009b6a  mov     r8b, r15b; ForThread
0x180009b6d  mov     byte ptr [rbp+OldValue], al
0x180009b70  mov     dl, r15b; NewValue
0x180009b73  call    cs:__imp_RtlAdjustPrivilege
0x180009b79  mov     ecx, eax; int
0x180009b7b  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180009b80  mov     ebx, eax
0x180009b82  test    eax, eax
0x180009b84  js      short loc_180009B9C
0x180009b86  cmp     byte ptr [rbp+OldValue], 0
0x180009b8a  jnz     short loc_180009B93
0x180009b8c  mov     rcx, [r14]
0x180009b8f  mov     [rcx+rdi*4], r15d
0x180009b93  inc     edi
0x180009b95  cmp     edi, r15d
0x180009b98  jb      short loc_180009B55
0x180009b9a  jmp     short loc_180009BB5
0x180009b9c  mov     rcx, rsi; this
0x180009b9f  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180009ba4  jmp     short loc_180009BB5
0x180009ba6  mov     rcx, [rdi]; lpMem
0x180009ba9  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180009bae  mov     qword ptr [rdi], 0
0x180009bb5  mov     rsi, [rsp+20h+arg_18]
0x180009bba  mov     eax, ebx
0x180009bbc  mov     rbx, [rsp+20h+arg_8]
0x180009bc1  add     rsp, 20h
0x180009bc5  pop     r15
0x180009bc7  pop     r14
0x180009bc9  pop     r12
0x180009bcb  pop     rdi
0x180009bcc  pop     rbp
0x180009bcd  retn
```
