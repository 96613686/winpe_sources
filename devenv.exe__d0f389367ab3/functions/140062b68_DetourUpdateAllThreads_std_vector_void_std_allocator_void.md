# DetourUpdateAllThreads(std::vector<void *,std::allocator<void *>> &)

- ea: `0x140062b68`
- end: `0x140062cc6`
- name: `?DetourUpdateAllThreads@@YAJAEAV?$vector@PEAXV?$allocator@PEAX@std@@@std@@@Z`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140031e3c`
- `0x140062cc8`

## callees

- `0x140001020`
- `0x1400414b8`
- `0x140062b68`
- `0x14006780c`

## import_xrefs

- `KERNEL32!Thread32Next` at `0x140062c73`
- `KERNEL32!Thread32Next` at `0x140062c73`
- `KERNEL32!OpenThread` at `0x140062c0e`
- `KERNEL32!OpenThread` at `0x140062c0e`
- `KERNEL32!Thread32First` at `0x140062bea`
- `KERNEL32!Thread32First` at `0x140062bea`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140062b92`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140062b92`
- `KERNEL32!GetCurrentProcessId` at `0x140062bb7`
- `KERNEL32!GetCurrentProcessId` at `0x140062bb7`
- `KERNEL32!GetCurrentThreadId` at `0x140062bc0`
- `KERNEL32!GetCurrentThreadId` at `0x140062bc0`
- `KERNEL32!CloseHandle` at `0x140062c54`
- `KERNEL32!CloseHandle` at `0x140062c84`
- `KERNEL32!CloseHandle` at `0x140062c9b`
- `KERNEL32!CloseHandle` at `0x140062c54`
- `KERNEL32!CloseHandle` at `0x140062c84`
- `KERNEL32!CloseHandle` at `0x140062c9b`
- `KERNEL32!GetLastError` at `0x140062c8e`
- `KERNEL32!GetLastError` at `0x140062c8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DetourUpdateAllThreads(__int64 a1)
{
  DWORD CurrentProcessId; // r14d
  DWORD CurrentThreadId; // r15d
  HANDLE v5; // rax
  HANDLE v6; // rsi
  _QWORD *v7; // rdx
  DWORD LastError; // ebx
  HANDLE v9; // [rsp+20h] [rbp-58h] BYREF
  HANDLE *p_hSnapshot; // [rsp+28h] [rbp-50h]
  HANDLE hSnapshot; // [rsp+30h] [rbp-48h] BYREF
  THREADENTRY32 te; // [rsp+38h] [rbp-40h] BYREF

  hSnapshot = CreateToolhelp32Snapshot(4u, 0);
  if ( hSnapshot == (HANDLE)-1LL )
    return 6;
  p_hSnapshot = &hSnapshot;
  CurrentProcessId = GetCurrentProcessId();
  CurrentThreadId = GetCurrentThreadId();
  memset(&te.cntUsage, 0, 24);
  te.dwSize = 28;
  if ( Thread32First(hSnapshot, &te) )
  {
    do
    {
      if ( te.th32OwnerProcessID == CurrentProcessId && te.th32ThreadID != CurrentThreadId )
      {
        v5 = OpenThread(2u, 0, te.th32ThreadID);
        v6 = v5;
        v9 = v5;
        if ( v5 )
        {
          DetourUpdateThread(v5);
          v7 = *(_QWORD **)(a1 + 8);
          if ( v7 == *(_QWORD **)(a1 + 16) )
          {
            try
            {
              std::vector<void *>::_Emplace_reallocate<void * const &>(a1, v7, &v9);
            }
            catch ( std::bad_alloc )
            {
              CloseHandle(v9);
              CloseHandle(*p_hSnapshot);
              return 14;
            }
          }
          else
          {
            *v7 = v6;
            *(_QWORD *)(a1 + 8) += 8LL;
          }
        }
      }
      te.dwSize = 28;
    }
    while ( Thread32Next(hSnapshot, &te) );
    CloseHandle(hSnapshot);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    CloseHandle(hSnapshot);
    return LastError;
  }
}

```

## disassembly

```asm
0x140062b68  mov     [rsp+arg_8], rbx
0x140062b6d  mov     [rsp+arg_10], rsi
0x140062b72  push    rdi
0x140062b73  push    r14
0x140062b75  push    r15
0x140062b77  sub     rsp, 60h
0x140062b7b  mov     rax, cs:__security_cookie
0x140062b82  xor     rax, rsp
0x140062b85  mov     [rsp+78h+var_20], rax
0x140062b8a  mov     rdi, rcx
0x140062b8d  xor     edx, edx; th32ProcessID
0x140062b8f  lea     ecx, [rdx+4]; dwFlags
0x140062b92  call    cs:__imp_CreateToolhelp32Snapshot
0x140062b98  mov     [rsp+78h+hSnapshot], rax
0x140062b9d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140062ba1  jnz     short loc_140062BAD
0x140062ba3  mov     eax, 6
0x140062ba8  jmp     loc_140062CA3
0x140062bad  lea     rbx, [rsp+78h+hSnapshot]
0x140062bb2  mov     [rsp+78h+var_50], rbx
0x140062bb7  call    cs:__imp_GetCurrentProcessId
0x140062bbd  mov     r14d, eax
0x140062bc0  call    cs:__imp_GetCurrentThreadId
0x140062bc6  mov     r15d, eax
0x140062bc9  xorps   xmm0, xmm0
0x140062bcc  movdqu  xmmword ptr [rsp+78h+te.cntUsage], xmm0
0x140062bd2  and     qword ptr [rsp+78h+te.tpDeltaPri], 0
0x140062bd8  mov     [rsp+78h+te.dwSize], 1Ch
0x140062be0  lea     rdx, [rsp+78h+te]; lpte
0x140062be5  mov     rcx, [rsp+78h+hSnapshot]; hSnapshot
0x140062bea  call    cs:__imp_Thread32First
0x140062bf0  test    eax, eax
0x140062bf2  jz      loc_140062C8E
0x140062bf8  cmp     [rsp+78h+te.th32OwnerProcessID], r14d
0x140062bfd  jnz     short loc_140062C61
0x140062bff  mov     r8d, [rsp+78h+te.th32ThreadID]; dwThreadId
0x140062c04  cmp     r8d, r15d
0x140062c07  jz      short loc_140062C61
0x140062c09  xor     edx, edx; bInheritHandle
0x140062c0b  lea     ecx, [rdx+2]; dwDesiredAccess
0x140062c0e  call    cs:__imp_OpenThread
0x140062c14  mov     rsi, rax
0x140062c17  mov     [rsp+78h+var_58], rax
0x140062c1c  test    rax, rax
0x140062c1f  jz      short loc_140062C61
0x140062c21  mov     rcx, rax; hThread
0x140062c24  call    DetourUpdateThread
0x140062c29  mov     rdx, [rdi+8]
0x140062c2d  cmp     rdx, [rdi+10h]
0x140062c31  jz      short loc_140062C3D
0x140062c33  mov     [rdx], rsi
0x140062c36  add     qword ptr [rdi+8], 8
0x140062c3b  jmp     short loc_140062C4A
0x140062c3d  lea     r8, [rsp+78h+var_58]
0x140062c42  mov     rcx, rdi
0x140062c45  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x140062c4a  jmp     short loc_140062C61
0x140062c4c  mov     rcx, [rsp+78h+var_50]
0x140062c51  mov     rcx, [rcx]; hObject
0x140062c54  call    cs:__imp_CloseHandle
0x140062c5a  mov     eax, 0Eh
0x140062c5f  jmp     short loc_140062CA3
0x140062c61  mov     [rsp+78h+te.dwSize], 1Ch
0x140062c69  lea     rdx, [rsp+78h+te]; lpte
0x140062c6e  mov     rcx, [rsp+78h+hSnapshot]; hSnapshot
0x140062c73  call    cs:__imp_Thread32Next
0x140062c79  test    eax, eax
0x140062c7b  jnz     loc_140062BF8
0x140062c81  mov     rcx, [rbx]; hObject
0x140062c84  call    cs:__imp_CloseHandle
0x140062c8a  xor     eax, eax
0x140062c8c  jmp     short loc_140062CA3
0x140062c8e  call    cs:__imp_GetLastError
0x140062c94  mov     ebx, eax
0x140062c96  mov     rcx, [rsp+78h+hSnapshot]; hObject
0x140062c9b  call    cs:__imp_CloseHandle
0x140062ca1  mov     eax, ebx
0x140062ca3  mov     rcx, [rsp+78h+var_20]
0x140062ca8  xor     rcx, rsp; StackCookie
0x140062cab  call    __security_check_cookie
0x140062cb0  lea     r11, [rsp+78h+var_18]
0x140062cb5  mov     rbx, [r11+28h]
0x140062cb9  mov     rsi, [r11+30h]
0x140062cbd  mov     rsp, r11
0x140062cc0  pop     r15
0x140062cc2  pop     r14
0x140062cc4  pop     rdi
0x140062cc5  retn
```
