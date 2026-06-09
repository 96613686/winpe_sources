# CredProtectAlloc(ushort const *,ushort * *)

- ea: `0x18002d89c`
- end: `0x18002dac1`
- name: `?CredProtectAlloc@@YAJPEBGPEAPEAG@Z`
- size: `549`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020040`

## callees

- `0x18002d7f8`
- `0x18002d89c`
- `0x18002dc98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da9a`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18002d92c`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18002d92c`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18002d980`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18002da03`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18002d980`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18002da03`

## pseudocode

```c
__int64 __fastcall CredProtectAlloc(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v3; // r14
  unsigned __int64 v4; // rdi
  unsigned __int64 v6; // rsi
  signed int v7; // ebx
  unsigned __int64 v8; // r9
  unsigned __int16 *v9; // rdi
  unsigned __int64 v10; // rax
  DWORD v11; // r12d
  signed int LastError; // eax
  void *v13; // rcx
  unsigned __int16 *v14; // rsi
  signed int v15; // eax
  unsigned __int16 *v16; // rcx
  __int64 i; // rax
  __int64 v18; // rcx
  unsigned __int16 *j; // rax
  unsigned __int16 **pcchMaxChars; // [rsp+20h] [rbp-20h]
  unsigned __int64 *ProtectionType; // [rsp+28h] [rbp-18h]
  unsigned int v23; // [rsp+30h] [rbp-10h]
  LPWSTR pszProtectedCredentials; // [rsp+88h] [rbp+48h] BYREF
  __int64 pProtectionType; // [rsp+90h] [rbp+50h] BYREF
  LPWSTR v26; // [rsp+98h] [rbp+58h] BYREF

  v3 = -1;
  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v6 = v4 + 1;
  if ( v4 + 1 >= v4 && (pszProtectedCredentials = 0, pProtectionType = 0, is_mul_ok(v6, 2u)) )
  {
    v7 = CTCoAllocPolicy::Alloc(a1, (v6 * (unsigned __int128)2uLL) >> 64, 2 * v6, (void **)&pszProtectedCredentials);
    if ( v7 >= 0 )
    {
      v8 = v4;
      v9 = pszProtectedCredentials;
      StringCchCopyNExW(pszProtectedCredentials, v6, a1, v8, pcchMaxChars, ProtectionType, v23);
      LODWORD(pProtectionType) = 0;
      if ( CredIsProtectedW(v9, (CRED_PROTECTION_TYPE *)&pProtectionType) && (_DWORD)pProtectionType )
      {
        *a2 = v9;
      }
      else
      {
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
        if ( v10 > 0xFFFFFFFF )
        {
          v7 = -2147024362;
        }
        else
        {
          v11 = v10 + 1;
          LODWORD(pszProtectedCredentials) = 0;
          if ( CredProtectW(0, v9, v10 + 1, 0, (DWORD *)&pszProtectedCredentials, 0) )
          {
            v7 = -2147418113;
          }
          else
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( v7 < 0 )
            {
              if ( v7 == -2147024774 )
              {
                v26 = 0;
                v7 = CTCoAllocPolicy::Alloc(v13, 1u, 2LL * (unsigned int)pszProtectedCredentials, (void **)&v26);
                if ( v7 >= 0 )
                {
                  v14 = v26;
                  if ( CredProtectW(0, v9, v11, v26, (DWORD *)&pszProtectedCredentials, 0) )
                  {
                    v7 = 0;
                    v14[(_DWORD)pszProtectedCredentials - 1] = 0;
                    *a2 = v14;
                  }
                  else
                  {
                    v15 = GetLastError();
                    v7 = v15;
                    if ( v15 > 0 )
                      v7 = (unsigned __int16)v15 | 0x80070000;
                    if ( v7 >= 0 )
                      v7 = -2147467259;
                    if ( v14 )
                    {
                      v16 = v14;
                      for ( i = 2LL * (unsigned int)pszProtectedCredentials; i; --i )
                      {
                        *(_BYTE *)v16 = 0;
                        v16 = (unsigned __int16 *)((char *)v16 + 1);
                      }
                      CoTaskMemFree(v14);
                    }
                  }
                }
              }
            }
            else
            {
              v7 = -2147467259;
            }
          }
        }
        if ( v9 && *v9 )
        {
          do
            ++v3;
          while ( v9[v3] );
          v18 = 2 * v3;
          for ( j = v9; v18; --v18 )
          {
            *(_BYTE *)j = 0;
            j = (unsigned __int16 *)((char *)j + 1);
          }
        }
        CoTaskMemFree(v9);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d89c  mov     [rsp-38h+arg_0], rbx
0x18002d8a1  push    rbp
0x18002d8a2  push    rsi
0x18002d8a3  push    rdi
0x18002d8a4  push    r12
0x18002d8a6  push    r13
0x18002d8a8  push    r14
0x18002d8aa  push    r15
0x18002d8ac  mov     rbp, rsp
0x18002d8af  sub     rsp, 40h
0x18002d8b3  xor     r13d, r13d
0x18002d8b6  mov     r15, rdx
0x18002d8b9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002d8bd  mov     [rdx], r13
0x18002d8c0  mov     rdi, r14
0x18002d8c3  mov     r12, rcx
0x18002d8c6  inc     rdi
0x18002d8c9  cmp     [rcx+rdi*2], r13w
0x18002d8ce  jnz     short loc_18002D8C6
0x18002d8d0  lea     rsi, [rdi+1]
0x18002d8d4  cmp     rsi, rdi
0x18002d8d7  jb      loc_18002DAA2
0x18002d8dd  mov     eax, 2
0x18002d8e2  mov     [rbp+pszProtectedCredentials], r13
0x18002d8e6  mul     rsi
0x18002d8e9  mov     [rbp+pProtectionType], r13
0x18002d8ed  test    rdx, rdx
0x18002d8f0  jnz     loc_18002DAA2
0x18002d8f6  lea     r9, [rbp+pszProtectedCredentials]; void **
0x18002d8fa  mov     r8, rax; unsigned __int64
0x18002d8fd  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002d902  mov     ebx, eax
0x18002d904  test    eax, eax
0x18002d906  js      loc_18002DAA7
0x18002d90c  mov     r9, rdi; unsigned __int64
0x18002d90f  mov     r8, r12; unsigned __int16 *
0x18002d912  mov     rdi, [rbp+pszProtectedCredentials]
0x18002d916  mov     rdx, rsi; unsigned __int64
0x18002d919  mov     rcx, rdi; unsigned __int16 *
0x18002d91c  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18002d921  lea     rdx, [rbp+pProtectionType]; pProtectionType
0x18002d925  mov     dword ptr [rbp+pProtectionType], r13d
0x18002d929  mov     rcx, rdi; pszProtectedCredentials
0x18002d92c  call    cs:__imp_CredIsProtectedW
0x18002d932  test    eax, eax
0x18002d934  jz      short loc_18002D944
0x18002d936  cmp     dword ptr [rbp+pProtectionType], r13d
0x18002d93a  jz      short loc_18002D944
0x18002d93c  mov     [r15], rdi
0x18002d93f  jmp     loc_18002DAA7
0x18002d944  mov     rax, r14
0x18002d947  inc     rax
0x18002d94a  cmp     [rdi+rax*2], r13w
0x18002d94f  jnz     short loc_18002D947
0x18002d951  mov     ecx, 0FFFFFFFFh
0x18002d956  cmp     rax, rcx
0x18002d959  ja      loc_18002DA65
0x18002d95f  lea     r12d, [rax+1]
0x18002d963  mov     [rsp+40h+ProtectionType], r13; ProtectionType
0x18002d968  lea     rax, [rbp+pszProtectedCredentials]
0x18002d96c  mov     dword ptr [rbp+pszProtectedCredentials], r13d
0x18002d970  mov     r8d, r12d; cchCredentials
0x18002d973  mov     [rsp+40h+pcchMaxChars], rax; pcchMaxChars
0x18002d978  xor     r9d, r9d; pszProtectedCredentials
0x18002d97b  mov     rdx, rdi; pszCredentials
0x18002d97e  xor     ecx, ecx; fAsSelf
0x18002d980  call    cs:__imp_CredProtectW
0x18002d986  test    eax, eax
0x18002d988  jz      short loc_18002D994
0x18002d98a  mov     ebx, 8000FFFFh
0x18002d98f  jmp     loc_18002DA6A
0x18002d994  call    cs:__imp_GetLastError
0x18002d99a  mov     ebx, eax
0x18002d99c  test    eax, eax
0x18002d99e  jle     short loc_18002D9A9
0x18002d9a0  movzx   ebx, ax
0x18002d9a3  or      ebx, 80070000h
0x18002d9a9  test    ebx, ebx
0x18002d9ab  js      short loc_18002D9B7
0x18002d9ad  mov     ebx, 80004005h
0x18002d9b2  jmp     loc_18002DA6A
0x18002d9b7  cmp     ebx, 8007007Ah
0x18002d9bd  jnz     loc_18002DA6A
0x18002d9c3  mov     r8d, dword ptr [rbp+pszProtectedCredentials]
0x18002d9c7  lea     r9, [rbp+arg_18]; void **
0x18002d9cb  add     r8, r8; unsigned __int64
0x18002d9ce  mov     [rbp+arg_18], r13
0x18002d9d2  mov     edx, 1; unsigned int
0x18002d9d7  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002d9dc  mov     ebx, eax
0x18002d9de  test    eax, eax
0x18002d9e0  js      loc_18002DA6A
0x18002d9e6  mov     rsi, [rbp+arg_18]
0x18002d9ea  lea     rax, [rbp+pszProtectedCredentials]
0x18002d9ee  mov     r9, rsi; pszProtectedCredentials
0x18002d9f1  mov     [rsp+40h+ProtectionType], r13; ProtectionType
0x18002d9f6  mov     r8d, r12d; cchCredentials
0x18002d9f9  mov     [rsp+40h+pcchMaxChars], rax; pcchMaxChars
0x18002d9fe  mov     rdx, rdi; pszCredentials
0x18002da01  xor     ecx, ecx; fAsSelf
0x18002da03  call    cs:__imp_CredProtectW
0x18002da09  test    eax, eax
0x18002da0b  jnz     short loc_18002DA53
0x18002da0d  call    cs:__imp_GetLastError
0x18002da13  mov     ebx, eax
0x18002da15  test    eax, eax
0x18002da17  jle     short loc_18002DA22
0x18002da19  movzx   ebx, ax
0x18002da1c  or      ebx, 80070000h
0x18002da22  test    ebx, ebx
0x18002da24  mov     eax, 80004005h
0x18002da29  cmovns  ebx, eax
0x18002da2c  test    rsi, rsi
0x18002da2f  jz      short loc_18002DA6A
0x18002da31  mov     eax, dword ptr [rbp+pszProtectedCredentials]
0x18002da34  mov     rcx, rsi
0x18002da37  add     rax, rax
0x18002da3a  jz      short loc_18002DA48
0x18002da3c  mov     [rcx], r13b
0x18002da3f  inc     rcx
0x18002da42  sub     rax, 1
0x18002da46  jnz     short loc_18002DA3C
0x18002da48  mov     rcx, rsi; pv
0x18002da4b  call    cs:__imp_CoTaskMemFree
0x18002da51  jmp     short loc_18002DA6A
0x18002da53  mov     eax, dword ptr [rbp+pszProtectedCredentials]
0x18002da56  mov     ebx, r13d
0x18002da59  dec     eax
0x18002da5b  mov     [rsi+rax*2], r13w
0x18002da60  mov     [r15], rsi
0x18002da63  jmp     short loc_18002DA6A
0x18002da65  mov     ebx, 80070216h
0x18002da6a  test    rdi, rdi
0x18002da6d  jz      short loc_18002DA97
0x18002da6f  cmp     [rdi], r13w
0x18002da73  jz      short loc_18002DA97
0x18002da75  inc     r14
0x18002da78  cmp     [rdi+r14*2], r13w
0x18002da7d  jnz     short loc_18002DA75
0x18002da7f  lea     rcx, [r14+r14]
0x18002da83  mov     rax, rdi
0x18002da86  test    rcx, rcx
0x18002da89  jz      short loc_18002DA97
0x18002da8b  mov     [rax], r13b
0x18002da8e  inc     rax
0x18002da91  sub     rcx, 1
0x18002da95  jnz     short loc_18002DA8B
0x18002da97  mov     rcx, rdi; pv
0x18002da9a  call    cs:__imp_CoTaskMemFree
0x18002daa0  jmp     short loc_18002DAA7
0x18002daa2  mov     ebx, 80070216h
0x18002daa7  mov     eax, ebx
0x18002daa9  mov     rbx, [rsp+40h+arg_0]
0x18002dab1  add     rsp, 40h
0x18002dab5  pop     r15
0x18002dab7  pop     r14
0x18002dab9  pop     r13
0x18002dabb  pop     r12
0x18002dabd  pop     rdi
0x18002dabe  pop     rsi
0x18002dabf  pop     rbp
0x18002dac0  retn
```
