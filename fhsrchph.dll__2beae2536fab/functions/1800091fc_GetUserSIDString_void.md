# GetUserSIDString(void)

- ea: `0x1800091fc`
- end: `0x1800093ae`
- name: `?GetUserSIDString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `434`
- prototype: `_QWORD *__fastcall(_QWORD *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180007a40`

## callees

- `0x18000278c`
- `0x1800067b4`
- `0x180007a1c`
- `0x1800091fc`
- `0x18000a62c`
- `0x18000a824`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009362`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009362`
- `ADVAPI32!GetTokenInformation` at `0x18000926c`
- `ADVAPI32!GetTokenInformation` at `0x1800092cc`
- `ADVAPI32!GetTokenInformation` at `0x18000926c`
- `ADVAPI32!GetTokenInformation` at `0x1800092cc`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800092e9`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800092e9`
- `ADVAPI32!OpenProcessToken` at `0x180009232`
- `ADVAPI32!OpenProcessToken` at `0x180009232`
- `KERNEL32!CloseHandle` at `0x180009377`
- `KERNEL32!CloseHandle` at `0x180009377`
- `KERNEL32!GetCurrentProcess` at `0x180009220`
- `KERNEL32!GetCurrentProcess` at `0x180009220`
- `KERNEL32!LocalFree` at `0x180009358`
- `KERNEL32!LocalFree` at `0x180009358`
- `KERNEL32!GetLastError` at `0x18000927a`
- `KERNEL32!GetLastError` at `0x18000927a`

## pseudocode

```c
_QWORD *__fastcall GetUserSIDString(_QWORD *Src)
{
  HANDLE CurrentProcess; // rax
  HANDLE v3; // rbx
  PSID *v4; // rsi
  HANDLE v5; // r14
  LPVOID TokenInformation[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-18h]
  DWORD TokenInformationLength; // [rsp+98h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+A0h] [rbp+40h] BYREF
  HANDLE v11; // [rsp+A8h] [rbp+48h]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    ATL::AtlThrowLastWin32();
  v3 = TokenHandle;
  v11 = TokenHandle;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    ATL::AtlThrowLastWin32();
  *(_OWORD *)TokenInformation = 0;
  v8 = 0;
  std::vector<unsigned char>::resize(TokenInformation, TokenInformationLength);
  v4 = (PSID *)TokenInformation[0];
  if ( TokenInformation[0] == TokenInformation[1] )
    ATL::AtlThrowImpl(-2147483637);
  if ( !GetTokenInformation(v3, TokenUser, TokenInformation[0], TokenInformationLength, &TokenInformationLength) )
    ATL::AtlThrowLastWin32();
  TokenHandle = 0;
  if ( !ConvertSidToStringSidW(*v4, (LPWSTR *)&TokenHandle) )
    ATL::AtlThrowLastWin32();
  v5 = TokenHandle;
  Src[3] = 7;
  Src[2] = 0;
  *(_WORD *)Src = 0;
  std::wstring::assign(Src, L"{");
  std::wstring::append(Src, v5);
  std::wstring::append(Src, L"}");
  if ( v5 )
    LocalFree(v5);
  operator delete(v4);
  if ( v3 && v3 != (HANDLE)-1LL )
    CloseHandle(v3);
  return Src;
}

```

## disassembly

```asm
0x1800091fc  mov     [rsp-28h+arg_0], rcx
0x180009201  push    rbp
0x180009202  push    rbx
0x180009203  push    rsi
0x180009204  push    rdi
0x180009205  push    r14
0x180009207  mov     rbp, rsp
0x18000920a  sub     rsp, 60h
0x18000920e  mov     rdi, rcx
0x180009211  mov     [rbp+var_30], 0
0x180009218  mov     [rbp+TokenHandle], 0
0x180009220  call    cs:__imp_GetCurrentProcess
0x180009226  mov     rcx, rax; ProcessHandle
0x180009229  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000922d  mov     edx, 8; DesiredAccess
0x180009232  call    cs:__imp_OpenProcessToken
0x180009238  test    eax, eax
0x18000923a  jz      loc_180009397
0x180009240  mov     rbx, [rbp+TokenHandle]
0x180009244  mov     [rbp+arg_18], rbx
0x180009248  mov     [rbp+var_30], 2
0x18000924f  mov     [rbp+TokenInformationLength], 0
0x180009256  lea     rax, [rbp+TokenInformationLength]
0x18000925a  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000925f  xor     r9d, r9d; TokenInformationLength
0x180009262  xor     r8d, r8d; TokenInformation
0x180009265  lea     edx, [r9+1]; TokenInformationClass
0x180009269  mov     rcx, rbx; TokenHandle
0x18000926c  call    cs:__imp_GetTokenInformation
0x180009272  test    eax, eax
0x180009274  jnz     loc_180009391
0x18000927a  call    cs:__imp_GetLastError
0x180009280  cmp     eax, 7Ah ; 'z'
0x180009283  jnz     loc_180009391
0x180009289  xorps   xmm0, xmm0
0x18000928c  movdqu  xmmword ptr [rbp+TokenInformation], xmm0
0x180009291  mov     [rbp+var_18], 0
0x180009299  mov     edx, [rbp+TokenInformationLength]
0x18000929c  lea     rcx, [rbp+TokenInformation]
0x1800092a0  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800092a5  nop
0x1800092a6  mov     rsi, [rbp+TokenInformation]
0x1800092aa  cmp     rsi, [rbp+TokenInformation+8]
0x1800092ae  jz      loc_18000939D
0x1800092b4  lea     rax, [rbp+TokenInformationLength]
0x1800092b8  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800092bd  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800092c1  mov     r8, rsi; TokenInformation
0x1800092c4  mov     edx, 1; TokenInformationClass
0x1800092c9  mov     rcx, rbx; TokenHandle
0x1800092cc  call    cs:__imp_GetTokenInformation
0x1800092d2  test    eax, eax
0x1800092d4  jz      loc_1800093A8
0x1800092da  mov     [rbp+TokenHandle], 0
0x1800092e2  lea     rdx, [rbp+TokenHandle]; StringSid
0x1800092e6  mov     rcx, [rsi]; Sid
0x1800092e9  call    cs:__imp_ConvertSidToStringSidW
0x1800092ef  test    eax, eax
0x1800092f1  jz      loc_18000938B
0x1800092f7  mov     r14, [rbp+TokenHandle]
0x1800092fb  mov     [rbp+TokenHandle], r14
0x1800092ff  mov     [rbp+var_30], 6
0x180009306  mov     qword ptr [rdi+18h], 7
0x18000930e  mov     qword ptr [rdi+10h], 0
0x180009316  xor     eax, eax
0x180009318  mov     [rdi], ax
0x18000931b  lea     r8d, [rax+1]
0x18000931f  lea     rdx, asc_18000E440; "{"
0x180009326  mov     rcx, rdi; Src
0x180009329  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000932e  mov     [rbp+var_30], 7
0x180009335  mov     rdx, r14; void *
0x180009338  mov     rcx, rdi; Src
0x18000933b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180009340  lea     rdx, asc_18000E444; "}"
0x180009347  mov     rcx, rdi; Src
0x18000934a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000934f  nop
0x180009350  test    r14, r14
0x180009353  jz      short loc_18000935F
0x180009355  mov     rcx, r14; hMem
0x180009358  call    cs:__imp_LocalFree
0x18000935e  nop
0x18000935f  mov     rcx, rsi
0x180009362  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009368  nop
0x180009369  test    rbx, rbx
0x18000936c  jz      short loc_18000937D
0x18000936e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180009372  jz      short loc_18000937D
0x180009374  mov     rcx, rbx; hObject
0x180009377  call    cs:__imp_CloseHandle
0x18000937d  mov     rax, rdi
0x180009380  add     rsp, 60h
0x180009384  pop     r14
0x180009386  pop     rdi
0x180009387  pop     rsi
0x180009388  pop     rbx
0x180009389  pop     rbp
0x18000938a  retn
0x18000938b  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180009391  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180009397  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18000939d  mov     ecx, 8000000Bh; int
0x1800093a2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800093a8  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
