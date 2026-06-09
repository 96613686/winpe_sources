# CNgscbToken::GetFullToken(CNgscbToken &)

- ea: `0x18002b768`
- end: `0x18002b84f`
- name: `?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z`
- size: `231`
- prototype: `__int64 __fastcall(HANDLE *this, struct CNgscbToken *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028380`

## callees

- `0x18002969c`
- `0x18002b768`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002b816`
- `KERNEL32!CloseHandle` at `0x18002b816`
- `KERNEL32!GetLastError` at `0x18002b7b7`
- `KERNEL32!GetLastError` at `0x18002b7b7`
- `ADVAPI32!DuplicateTokenEx` at `0x18002b847`
- `ADVAPI32!DuplicateTokenEx` at `0x18002b847`
- `ADVAPI32!GetTokenInformation` at `0x18002b7ad`
- `ADVAPI32!GetTokenInformation` at `0x18002b7ee`
- `ADVAPI32!GetTokenInformation` at `0x18002b7ad`
- `ADVAPI32!GetTokenInformation` at `0x18002b7ee`

## pseudocode

```c
__int64 __fastcall CNgscbToken::GetFullToken(HANDLE *this, struct CNgscbToken *a2)
{
  signed int LastError; // eax
  unsigned int v5; // edi
  HANDLE v6; // rcx
  BOOL v7; // eax
  HANDLE v8; // rbx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation = 0;
  hObject = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(*this, TokenElevationType, &TokenInformation, 4u, &ReturnLength)
    && ((v6 = *this, TokenInformation != 3)
      ? (v7 = DuplicateTokenEx(v6, 0, 0, SecurityImpersonation, TokenPrimary, &hObject))
      : (v7 = GetTokenInformation(v6, TokenLinkedToken, &hObject, 8u, &ReturnLength)),
        v7) )
  {
    v8 = hObject;
    v5 = 0;
    SH<void *,SH_HANDLE>::Reset(a2);
    *(_QWORD *)a2 = v8;
    hObject = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hObject )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x18002b768  mov     [rsp-18h+arg_8], rbx
0x18002b76d  push    rbp
0x18002b76e  push    rsi
0x18002b76f  push    rdi
0x18002b770  mov     rbp, rsp
0x18002b773  sub     rsp, 30h
0x18002b777  mov     r9d, 4; TokenInformationLength
0x18002b77d  mov     [rbp+TokenInformation], 0
0x18002b784  mov     rsi, rdx
0x18002b787  mov     [rbp+hObject], 0
0x18002b78f  mov     rbx, rcx
0x18002b792  mov     [rbp+arg_10], 0
0x18002b799  mov     rcx, [rcx]; TokenHandle
0x18002b79c  lea     rax, [rbp+arg_10]
0x18002b7a0  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002b7a4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002b7a9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002b7ad  call    cs:__imp_GetTokenInformation
0x18002b7b3  test    eax, eax
0x18002b7b5  jnz     short loc_18002B7CE
0x18002b7b7  call    cs:__imp_GetLastError
0x18002b7bd  mov     edi, eax
0x18002b7bf  test    eax, eax
0x18002b7c1  jle     short loc_18002B80D
0x18002b7c3  movzx   edi, ax
0x18002b7c6  or      edi, 80070000h
0x18002b7cc  jmp     short loc_18002B80D
0x18002b7ce  cmp     [rbp+TokenInformation], 3
0x18002b7d2  mov     rcx, [rbx]; hExistingToken
0x18002b7d5  jnz     short loc_18002B82B
0x18002b7d7  mov     r9d, 8; TokenInformationLength
0x18002b7dd  lea     rax, [rbp+arg_10]
0x18002b7e1  lea     r8, [rbp+hObject]; TokenInformation
0x18002b7e5  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002b7ea  lea     edx, [r9+0Bh]; TokenInformationClass
0x18002b7ee  call    cs:__imp_GetTokenInformation
0x18002b7f4  test    eax, eax
0x18002b7f6  jz      short loc_18002B7B7
0x18002b7f8  mov     rbx, [rbp+hObject]
0x18002b7fc  xor     edi, edi
0x18002b7fe  mov     rcx, rsi
0x18002b801  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002b806  mov     [rsi], rbx
0x18002b809  mov     [rbp+hObject], rdi
0x18002b80d  mov     rcx, [rbp+hObject]; hObject
0x18002b811  test    rcx, rcx
0x18002b814  jz      short loc_18002B81C
0x18002b816  call    cs:__imp_CloseHandle
0x18002b81c  mov     rbx, [rsp+30h+arg_8]
0x18002b821  mov     eax, edi
0x18002b823  add     rsp, 30h
0x18002b827  pop     rdi
0x18002b828  pop     rsi
0x18002b829  pop     rbp
0x18002b82a  retn
0x18002b82b  lea     rax, [rbp+hObject]
0x18002b82f  mov     r9d, 2; ImpersonationLevel
0x18002b835  mov     [rsp+30h+phNewToken], rax; phNewToken
0x18002b83a  xor     r8d, r8d; lpTokenAttributes
0x18002b83d  xor     edx, edx; dwDesiredAccess
0x18002b83f  mov     dword ptr [rsp+30h+ReturnLength], 1; TokenType
0x18002b847  call    cs:__imp_DuplicateTokenEx
0x18002b84d  jmp     short loc_18002B7F4
```
