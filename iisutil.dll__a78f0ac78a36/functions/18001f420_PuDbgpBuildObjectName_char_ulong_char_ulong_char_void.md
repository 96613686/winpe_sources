# PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)

- ea: `0x18001f420`
- end: `0x18001f4f4`
- name: `?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z`
- size: `212`
- prototype: `char *__usercall@<rax>(char *Buffer@<rcx>, unsigned int@<edx>, char *@<r8>, unsigned int@<r9d>, char *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18001f530`
- `0x18001f5d0`

## callees

- `0x18001f420`

## import_xrefs

- `msvcrt!strrchr` at `0x18001f43c`
- `msvcrt!strrchr` at `0x18001f450`
- `msvcrt!strrchr` at `0x18001f464`
- `msvcrt!strrchr` at `0x18001f43c`
- `msvcrt!strrchr` at `0x18001f450`
- `msvcrt!strrchr` at `0x18001f464`
- `msvcrt!sprintf_s` at `0x18001f4dd`
- `msvcrt!sprintf_s` at `0x18001f4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f4aa`

## pseudocode

```c
char *__fastcall PuDbgpBuildObjectName(char *Buffer, __int64 a2, char *a3, int a4, char *a5, void *a6)
{
  __int64 v7; // rsi
  char *v10; // rbx
  const char *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  DWORD CurrentProcessId; // eax

  v7 = 0;
  v10 = strrchr(a3, 92);
  if ( v10 || (v10 = strrchr(a3, 47)) != 0 || (v10 = strrchr(a3, 58)) != 0 )
    v11 = v10 + 1;
  else
    v11 = a3;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a5[v13] );
  do
    ++v12;
  while ( v11[v12] );
  if ( (unsigned __int64)(v13 + v12 + 37) < 0x100 )
  {
    CurrentProcessId = GetCurrentProcessId();
    sprintf_s(Buffer, 0x100u, "%s:%lu %s:%08p PID:%lu", v11, a4, a5, a6, CurrentProcessId);
    return Buffer;
  }
  return (char *)v7;
}

```

## disassembly

```asm
0x18001f420  push    rbx
0x18001f422  push    rbp
0x18001f423  push    rsi
0x18001f424  push    rdi
0x18001f425  push    r14
0x18001f427  sub     rsp, 40h
0x18001f42b  mov     rbp, rcx
0x18001f42e  xor     esi, esi
0x18001f430  mov     rcx, r8; Str
0x18001f433  mov     r14d, r9d
0x18001f436  mov     rdi, r8
0x18001f439  lea     edx, [rsi+5Ch]; Ch
0x18001f43c  call    cs:__imp_strrchr
0x18001f442  mov     rbx, rax
0x18001f445  test    rax, rax
0x18001f448  jnz     short loc_18001F477
0x18001f44a  lea     edx, [rsi+2Fh]; Ch
0x18001f44d  mov     rcx, rdi; Str
0x18001f450  call    cs:__imp_strrchr
0x18001f456  mov     rbx, rax
0x18001f459  test    rax, rax
0x18001f45c  jnz     short loc_18001F477
0x18001f45e  lea     edx, [rsi+3Ah]; Ch
0x18001f461  mov     rcx, rdi; Str
0x18001f464  call    cs:__imp_strrchr
0x18001f46a  mov     rbx, rax
0x18001f46d  test    rax, rax
0x18001f470  jnz     short loc_18001F477
0x18001f472  mov     rbx, rdi
0x18001f475  jmp     short loc_18001F47A
0x18001f477  inc     rbx
0x18001f47a  mov     rdi, [rsp+68h+arg_20]
0x18001f482  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f486  mov     rcx, rax
0x18001f489  inc     rcx
0x18001f48c  cmp     [rdi+rcx], sil
0x18001f490  jnz     short loc_18001F489
0x18001f492  inc     rax
0x18001f495  cmp     [rbx+rax], sil
0x18001f499  jnz     short loc_18001F492
0x18001f49b  add     rax, 25h ; '%'
0x18001f49f  add     rax, rcx
0x18001f4a2  cmp     rax, 100h
0x18001f4a8  jnb     short loc_18001F4E6
0x18001f4aa  call    cs:__imp_GetCurrentProcessId
0x18001f4b0  mov     [rsp+68h+var_30], eax
0x18001f4b4  mov     r9, rbx
0x18001f4b7  mov     rax, [rsp+68h+arg_28]
0x18001f4bf  lea     r8, aSLuS08pPidLu; "%s:%lu %s:%08p PID:%lu"
0x18001f4c6  mov     [rsp+68h+var_38], rax
0x18001f4cb  mov     edx, 100h; BufferCount
0x18001f4d0  mov     [rsp+68h+var_40], rdi
0x18001f4d5  mov     rcx, rbp; Buffer
0x18001f4d8  mov     [rsp+68h+var_48], r14d
0x18001f4dd  call    cs:__imp_sprintf_s
0x18001f4e3  mov     rsi, rbp
0x18001f4e6  mov     rax, rsi
0x18001f4e9  add     rsp, 40h
0x18001f4ed  pop     r14
0x18001f4ef  pop     rdi
0x18001f4f0  pop     rsi
0x18001f4f1  pop     rbp
0x18001f4f2  pop     rbx
0x18001f4f3  retn
```
