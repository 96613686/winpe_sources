# CProviderImpersonation::ImpersonateClient(void)

- ea: `0x140018ff0`
- end: `0x14001904f`
- name: `?ImpersonateClient@CProviderImpersonation@@UEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CProviderImpersonation *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140018ff0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001902b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001902b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140019021`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140019021`

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::ImpersonateClient(CProviderImpersonation *this)
{
  int v1; // ebx
  signed int LastError; // eax
  HANDLE Token; // [rsp+30h] [rbp+8h] BYREF

  Token = 0;
  v1 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &Token);
  if ( v1 < 0 )
  {
    return (unsigned int)-2147467259;
  }
  else if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140018ff0  push    rbx
0x140018ff2  sub     rsp, 20h
0x140018ff6  mov     [rsp+28h+Token], 0
0x140018fff  mov     rcx, [rcx+10h]
0x140019003  mov     rax, [rcx]
0x140019006  lea     rdx, [rsp+28h+Token]
0x14001900b  mov     rax, [rax+18h]
0x14001900f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019014  mov     ebx, eax
0x140019016  test    eax, eax
0x140019018  js      short loc_140019042
0x14001901a  mov     rdx, [rsp+28h+Token]; Token
0x14001901f  xor     ecx, ecx; Thread
0x140019021  call    cs:__imp_SetThreadToken
0x140019027  test    eax, eax
0x140019029  jnz     short loc_140019047
0x14001902b  call    cs:__imp_GetLastError
0x140019031  mov     ebx, eax
0x140019033  test    eax, eax
0x140019035  jle     short loc_140019047
0x140019037  movzx   ebx, ax
0x14001903a  or      ebx, 80070000h
0x140019040  jmp     short loc_140019047
0x140019042  mov     ebx, 80004005h
0x140019047  mov     eax, ebx
0x140019049  add     rsp, 20h
0x14001904d  pop     rbx
0x14001904e  retn
```
