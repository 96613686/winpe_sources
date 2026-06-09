# CDropImpersonation::Drop(void)

- ea: `0x180043fac`
- end: `0x18004404b`
- name: `?Drop@CDropImpersonation@@QEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CDropImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180096390`

## callees

- `0x180043fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180043fc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180043fc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180043fdf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180043fdf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180044036`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180044036`

## pseudocode

```c
__int64 __fastcall CDropImpersonation::Drop(CDropImpersonation *this)
{
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  v1 = 0;
  if ( *((_QWORD *)this + 1)
    || (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 4u, 0, (PHANDLE)this + 1)) )
  {
    if ( *(_BYTE *)this || RevertToSelf() )
    {
      *(_BYTE *)this = 1;
      return v1;
    }
  }
  else if ( GetLastError() == 1008 )
  {
    return v1;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v1;
}

```

## disassembly

```asm
0x180043fac  mov     [rsp+arg_0], rbx
0x180043fb1  mov     [rsp+arg_8], rsi
0x180043fb6  push    rdi
0x180043fb7  sub     rsp, 20h
0x180043fbb  xor     ebx, ebx
0x180043fbd  mov     rdi, rcx
0x180043fc0  cmp     [rcx+8], rbx
0x180043fc4  jnz     short loc_180044032
0x180043fc6  call    cs:__imp_GetCurrentThread
0x180043fcd  nop     dword ptr [rax+rax+00h]
0x180043fd2  lea     r9, [rdi+8]; TokenHandle
0x180043fd6  xor     r8d, r8d; OpenAsSelf
0x180043fd9  mov     rcx, rax; ThreadHandle
0x180043fdc  lea     edx, [rbx+4]; DesiredAccess
0x180043fdf  call    cs:__imp_OpenThreadToken
0x180043fe6  nop     dword ptr [rax+rax+00h]
0x180043feb  test    eax, eax
0x180043fed  jnz     short loc_180044032
0x180043fef  call    cs:__imp_GetLastError
0x180043ff6  nop     dword ptr [rax+rax+00h]
0x180043ffb  cmp     eax, 3F0h
0x180044000  jnz     short loc_180044015
0x180044002  mov     rsi, [rsp+28h+arg_8]
0x180044007  mov     eax, ebx
0x180044009  mov     rbx, [rsp+28h+arg_0]
0x18004400e  add     rsp, 20h
0x180044012  pop     rdi
0x180044013  retn
0x180044015  call    cs:__imp_GetLastError
0x18004401c  nop     dword ptr [rax+rax+00h]
0x180044021  mov     ebx, eax
0x180044023  test    eax, eax
0x180044025  jle     short loc_180044002
0x180044027  movzx   ebx, ax
0x18004402a  or      ebx, 80070000h
0x180044030  jmp     short loc_180044002
0x180044032  cmp     [rdi], bl
0x180044034  jnz     short loc_180044046
0x180044036  call    cs:__imp_RevertToSelf
0x18004403d  nop     dword ptr [rax+rax+00h]
0x180044042  test    eax, eax
0x180044044  jz      short loc_180044015
0x180044046  mov     byte ptr [rdi], 1
0x180044049  jmp     short loc_180044002
```
