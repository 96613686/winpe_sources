# CAutoImpersonate::IsImpersonating(int *)

- ea: `0x180030ab4`
- end: `0x180030b37`
- name: `?IsImpersonating@CAutoImpersonate@@QEAAJPEAH@Z`
- size: `131`
- prototype: `__int64 __fastcall(CAutoImpersonate *__hidden this, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180030a50`
- `0x180030b40`

## callees

- `0x180030ab4`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180030aef`
- `ADVAPI32!OpenThreadToken` at `0x180030aef`
- `KERNEL32!GetLastError` at `0x180030b0c`
- `KERNEL32!GetLastError` at `0x180030b0c`
- `KERNEL32!CloseHandle` at `0x180030b04`
- `KERNEL32!CloseHandle` at `0x180030b04`
- `KERNEL32!GetCurrentThread` at `0x180030adb`
- `KERNEL32!GetCurrentThread` at `0x180030adb`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::IsImpersonating(CAutoImpersonate *this, int *a2)
{
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  void *v6; // rcx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = this;
  if ( !a2 )
    return 2147500035LL;
  v4 = 0;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    v6 = TokenHandle;
    *a2 = 1;
    CloseHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180030ab4  mov     [rsp+arg_8], rbx
0x180030ab9  mov     [rsp+TokenHandle], rcx
0x180030abe  push    rdi
0x180030abf  sub     rsp, 20h
0x180030ac3  mov     rdi, rdx
0x180030ac6  test    rdx, rdx
0x180030ac9  jnz     short loc_180030AD2
0x180030acb  mov     eax, 80004003h
0x180030ad0  jmp     short loc_180030B2C
0x180030ad2  xor     ebx, ebx
0x180030ad4  mov     [rdx], ebx
0x180030ad6  mov     [rsp+28h+TokenHandle], rbx
0x180030adb  call    cs:__imp_GetCurrentThread
0x180030ae1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180030ae6  xor     r8d, r8d; OpenAsSelf
0x180030ae9  mov     rcx, rax; ThreadHandle
0x180030aec  lea     edx, [rbx+8]; DesiredAccess
0x180030aef  call    cs:__imp_OpenThreadToken
0x180030af5  test    eax, eax
0x180030af7  jz      short loc_180030B0C
0x180030af9  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180030afe  mov     dword ptr [rdi], 1
0x180030b04  call    cs:__imp_CloseHandle
0x180030b0a  jmp     short loc_180030B2A
0x180030b0c  call    cs:__imp_GetLastError
0x180030b12  cmp     eax, 3F0h
0x180030b17  jz      short loc_180030B2A
0x180030b19  test    eax, eax
0x180030b1b  jg      short loc_180030B21
0x180030b1d  mov     ebx, eax
0x180030b1f  jmp     short loc_180030B2A
0x180030b21  movzx   ebx, ax
0x180030b24  or      ebx, 80070000h
0x180030b2a  mov     eax, ebx
0x180030b2c  mov     rbx, [rsp+28h+arg_8]
0x180030b31  add     rsp, 20h
0x180030b35  pop     rdi
0x180030b36  retn
```
