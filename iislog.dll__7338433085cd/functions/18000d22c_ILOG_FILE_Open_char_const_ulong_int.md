# ILOG_FILE::Open(char const *,ulong,int)

- ea: `0x18000d22c`
- end: `0x18000d2f1`
- name: `?Open@ILOG_FILE@@QEAAHPEBDKH@Z`
- size: `197`
- prototype: `__int64 __fastcall(ILOG_FILE *__hidden this, LPCSTR lpFileName, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180002c8c`

## callees

- `0x18000d22c`
- `0x18000d2f8`

## import_xrefs

- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000d275`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000d275`
- `KERNEL32!GetLastError` at `0x18000d29b`
- `KERNEL32!GetLastError` at `0x18000d29b`
- `KERNEL32!CloseHandle` at `0x18000d2d9`
- `KERNEL32!CloseHandle` at `0x18000d2d9`
- `KERNEL32!GetCurrentThread` at `0x18000d27b`
- `KERNEL32!GetCurrentThread` at `0x18000d27b`
- `ADVAPI32!SetThreadToken` at `0x18000d2ce`
- `ADVAPI32!SetThreadToken` at `0x18000d2ce`
- `ADVAPI32!RevertToSelf` at `0x18000d2ac`
- `ADVAPI32!RevertToSelf` at `0x18000d2ac`
- `ADVAPI32!OpenThreadToken` at `0x18000d291`
- `ADVAPI32!OpenThreadToken` at `0x18000d291`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::Open(ILOG_FILE *this, LPCSTR lpFileName, unsigned int a3, int a4)
{
  int v4; // eax
  HANDLE CurrentThread; // rax
  unsigned int v10; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0x20000;
  *((_DWORD *)this + 13) = 0;
  *((_DWORD *)this + 4) = 1;
  TokenHandle = 0;
  if ( a3 >= 0x20000 )
    v4 = a3;
  *((_DWORD *)this + 12) = v4;
  *((_QWORD *)this + 7) = *((unsigned int *)this + 5);
  STR::Copy((ILOG_FILE *)((char *)this + 64), lpFileName);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 0, &TokenHandle) )
  {
    RevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    return 0;
  }
  v10 = ILOG_FILE::OpenFile(this, lpFileName, a4);
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  return v10;
}

```

## disassembly

```asm
0x18000d22c  mov     [rsp+arg_8], rbx
0x18000d231  mov     [rsp+arg_10], rsi
0x18000d236  push    rdi
0x18000d237  sub     rsp, 20h
0x18000d23b  mov     eax, 20000h
0x18000d240  mov     dword ptr [rcx+34h], 0
0x18000d247  cmp     r8d, eax
0x18000d24a  mov     dword ptr [rcx+10h], 1
0x18000d251  mov     rbx, rcx
0x18000d254  mov     [rsp+28h+TokenHandle], 0
0x18000d25d  cmovnb  eax, r8d
0x18000d261  mov     esi, r9d
0x18000d264  mov     [rcx+30h], eax
0x18000d267  mov     rdi, rdx
0x18000d26a  mov     eax, [rcx+14h]
0x18000d26d  mov     [rcx+38h], rax
0x18000d271  add     rcx, 40h ; '@'
0x18000d275  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000d27b  call    cs:__imp_GetCurrentThread
0x18000d281  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000d286  xor     r8d, r8d; OpenAsSelf
0x18000d289  mov     rcx, rax; ThreadHandle
0x18000d28c  mov     edx, 0F01FFh; DesiredAccess
0x18000d291  call    cs:__imp_OpenThreadToken
0x18000d297  test    eax, eax
0x18000d299  jnz     short loc_18000D2AC
0x18000d29b  call    cs:__imp_GetLastError
0x18000d2a1  cmp     eax, 3F0h
0x18000d2a6  jz      short loc_18000D2B2
0x18000d2a8  xor     eax, eax
0x18000d2aa  jmp     short loc_18000D2E1
0x18000d2ac  call    cs:__imp_RevertToSelf
0x18000d2b2  mov     r8d, esi; int
0x18000d2b5  mov     rdx, rdi; lpFileName
0x18000d2b8  mov     rcx, rbx; this
0x18000d2bb  call    ?OpenFile@ILOG_FILE@@AEAAHPEBDH@Z; ILOG_FILE::OpenFile(char const *,int)
0x18000d2c0  mov     rdx, [rsp+28h+TokenHandle]; Token
0x18000d2c5  mov     ebx, eax
0x18000d2c7  test    rdx, rdx
0x18000d2ca  jz      short loc_18000D2DF
0x18000d2cc  xor     ecx, ecx; Thread
0x18000d2ce  call    cs:__imp_SetThreadToken
0x18000d2d4  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18000d2d9  call    cs:__imp_CloseHandle
0x18000d2df  mov     eax, ebx
0x18000d2e1  mov     rbx, [rsp+28h+arg_8]
0x18000d2e6  mov     rsi, [rsp+28h+arg_10]
0x18000d2eb  add     rsp, 20h
0x18000d2ef  pop     rdi
0x18000d2f0  retn
```
