# SecurityHelper::OpenThreadToken(void *,ulong,void * *)

- ea: `0x14005c024`
- end: `0x14005c081`
- name: `?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z`
- size: `93`
- prototype: `unsigned int __fastcall(HANDLE ThreadHandle, DWORD DesiredAccess, PHANDLE TokenHandle, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b500`
- `0x140012404`
- `0x140016740`
- `0x1400194a0`

## callees

- `0x14005c024`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14005c03d`
- `ADVAPI32!OpenThreadToken` at `0x14005c064`
- `ADVAPI32!OpenThreadToken` at `0x14005c03d`
- `ADVAPI32!OpenThreadToken` at `0x14005c064`
- `KERNEL32!GetLastError` at `0x14005c047`
- `KERNEL32!GetLastError` at `0x14005c06e`
- `KERNEL32!GetLastError` at `0x14005c047`
- `KERNEL32!GetLastError` at `0x14005c06e`

## pseudocode

```c
__int64 __fastcall SecurityHelper::OpenThreadToken(
        HANDLE ThreadHandle,
        DWORD DesiredAccess,
        PHANDLE TokenHandle,
        void **a4)
{
  DWORD LastError; // ebx

  LastError = 0;
  if ( !OpenThreadToken(ThreadHandle, DesiredAccess, 0, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      LastError = 0;
      if ( !OpenThreadToken(ThreadHandle, DesiredAccess, 1, TokenHandle) )
        return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x14005c024  push    rbx
0x14005c026  push    rbp
0x14005c027  push    rsi
0x14005c028  push    rdi
0x14005c029  sub     rsp, 28h
0x14005c02d  mov     rdi, r8
0x14005c030  mov     r9, r8; TokenHandle
0x14005c033  xor     r8d, r8d; OpenAsSelf
0x14005c036  mov     esi, edx
0x14005c038  mov     rbp, rcx
0x14005c03b  xor     ebx, ebx
0x14005c03d  call    cs:__imp_OpenThreadToken
0x14005c043  test    eax, eax
0x14005c045  jnz     short loc_14005C076
0x14005c047  call    cs:__imp_GetLastError
0x14005c04d  mov     ebx, eax
0x14005c04f  cmp     eax, 3F0h
0x14005c054  jz      short loc_14005C076
0x14005c056  xor     ebx, ebx
0x14005c058  mov     r9, rdi; TokenHandle
0x14005c05b  mov     edx, esi; DesiredAccess
0x14005c05d  mov     rcx, rbp; ThreadHandle
0x14005c060  lea     r8d, [rbx+1]; OpenAsSelf
0x14005c064  call    cs:__imp_OpenThreadToken
0x14005c06a  test    eax, eax
0x14005c06c  jnz     short loc_14005C076
0x14005c06e  call    cs:__imp_GetLastError
0x14005c074  mov     ebx, eax
0x14005c076  mov     eax, ebx
0x14005c078  add     rsp, 28h
0x14005c07c  pop     rdi
0x14005c07d  pop     rsi
0x14005c07e  pop     rbp
0x14005c07f  pop     rbx
0x14005c080  retn
```
