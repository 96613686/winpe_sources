# RealtimeProtection::CThreadImpersonation::GetProcessToken(ulong,void * *)

- ea: `0x180183428`
- end: `0x18018353f`
- name: `?GetProcessToken@CThreadImpersonation@RealtimeProtection@@AEAAJKPEAPEAX@Z`
- size: `279`
- prototype: `int(RealtimeProtection::CThreadImpersonation *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180183540`

## callees

- `0x1800809d0`
- `0x180105f50`
- `0x18010cb40`
- `0x180183428`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x18018344e`
- `KERNEL32!OpenProcess` at `0x18018344e`
- `KERNEL32!CloseHandle` at `0x180183501`
- `KERNEL32!CloseHandle` at `0x18018351f`
- `KERNEL32!CloseHandle` at `0x180183501`
- `KERNEL32!CloseHandle` at `0x18018351f`
- `ADVAPI32!OpenProcessToken` at `0x1801834b5`
- `ADVAPI32!OpenProcessToken` at `0x1801834b5`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CThreadImpersonation::GetProcessToken(
        RealtimeProtection::CThreadImpersonation *this,
        DWORD a2,
        void **a3)
{
  HANDLE v4; // rax
  void *v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int LastFailure; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  v4 = OpenProcess(0x410u, 0, a2);
  v5 = v4;
  if ( v4 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v4, 6u, &TokenHandle) )
    {
      *a3 = TokenHandle;
      v7 = 0;
      TokenHandle = 0;
    }
    else
    {
      LastFailure = HrGetLastFailure();
      v7 = LastFailure;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, LastFailure);
      if ( TokenHandle )
        CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  else
  {
    v6 = HrGetLastFailure();
    v7 = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180183428  mov     [rsp+arg_0], rbx
0x18018342d  push    rdi
0x18018342e  sub     rsp, 30h
0x180183432  mov     rax, cs:__security_cookie
0x180183439  xor     rax, rsp
0x18018343c  mov     [rsp+38h+var_10], rax
0x180183441  mov     rbx, r8
0x180183444  mov     ecx, 410h; dwDesiredAccess
0x180183449  mov     r8d, edx; dwProcessId
0x18018344c  xor     edx, edx; bInheritHandle
0x18018344e  call    cs:__imp_OpenProcess
0x180183454  mov     rdi, rax
0x180183457  test    rax, rax
0x18018345a  jnz     short loc_18018349F
0x18018345c  call    HrGetLastFailure
0x180183461  mov     ebx, eax
0x180183463  mov     rcx, cs:WPP_GLOBAL_Control
0x18018346a  lea     rdx, WPP_GLOBAL_Control
0x180183471  cmp     rcx, rdx
0x180183474  jz      loc_180183525
0x18018347a  test    byte ptr [rcx+1Ch], 4
0x18018347e  jz      loc_180183525
0x180183484  mov     rcx, [rcx+10h]
0x180183488  lea     edx, [rdi+29h]
0x18018348b  mov     r9d, eax
0x18018348e  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183495  call    WPP_SF_d
0x18018349a  jmp     loc_180183525
0x18018349f  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1801834a4  mov     [rsp+38h+TokenHandle], 0
0x1801834ad  mov     edx, 6; DesiredAccess
0x1801834b2  mov     rcx, rdi; ProcessHandle
0x1801834b5  call    cs:__imp_OpenProcessToken
0x1801834bb  test    eax, eax
0x1801834bd  jnz     short loc_180183509
0x1801834bf  call    HrGetLastFailure
0x1801834c4  mov     ebx, eax
0x1801834c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801834cd  lea     rdx, WPP_GLOBAL_Control
0x1801834d4  cmp     rcx, rdx
0x1801834d7  jz      short loc_1801834F7
0x1801834d9  test    byte ptr [rcx+1Ch], 1
0x1801834dd  jz      short loc_1801834F7
0x1801834df  mov     rcx, [rcx+10h]
0x1801834e3  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x1801834ea  mov     edx, 2Ah ; '*'
0x1801834ef  mov     r9d, eax
0x1801834f2  call    WPP_SF_d
0x1801834f7  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1801834fc  test    rcx, rcx
0x1801834ff  jz      short loc_18018351C
0x180183501  call    cs:__imp_CloseHandle
0x180183507  jmp     short loc_18018351C
0x180183509  mov     rax, [rsp+38h+TokenHandle]
0x18018350e  mov     [rbx], rax
0x180183511  xor     ebx, ebx
0x180183513  mov     [rsp+38h+TokenHandle], 0
0x18018351c  mov     rcx, rdi; hObject
0x18018351f  call    cs:__imp_CloseHandle
0x180183525  mov     eax, ebx
0x180183527  mov     rcx, [rsp+38h+var_10]
0x18018352c  xor     rcx, rsp; StackCookie
0x18018352f  call    __security_check_cookie
0x180183534  mov     rbx, [rsp+38h+arg_0]
0x180183539  add     rsp, 30h
0x18018353d  pop     rdi
0x18018353e  retn
```
