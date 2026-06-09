# PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)

- ea: `0x1800206b4`
- end: `0x1800207a7`
- name: `?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z`
- size: `243`
- prototype: `char *__fastcall(char *Buffer, __int64, char *, int, char *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x1800207f0`
- `0x1800208a0`

## callees

- `0x1800206b4`

## import_xrefs

- `msvcrt!strrchr` at `0x1800206d0`
- `msvcrt!strrchr` at `0x1800206ea`
- `msvcrt!strrchr` at `0x180020704`
- `msvcrt!strrchr` at `0x1800206d0`
- `msvcrt!strrchr` at `0x1800206ea`
- `msvcrt!strrchr` at `0x180020704`
- `msvcrt!sprintf_s` at `0x180020789`
- `msvcrt!sprintf_s` at `0x180020789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020750`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020750`

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
0x1800206b4  push    rbx
0x1800206b6  push    rbp
0x1800206b7  push    rsi
0x1800206b8  push    rdi
0x1800206b9  push    r14
0x1800206bb  sub     rsp, 40h
0x1800206bf  mov     rbp, rcx
0x1800206c2  xor     esi, esi
0x1800206c4  mov     rcx, r8; Str
0x1800206c7  mov     r14d, r9d
0x1800206ca  mov     rdi, r8
0x1800206cd  lea     edx, [rsi+5Ch]; Ch
0x1800206d0  call    cs:__imp_strrchr
0x1800206d7  nop     dword ptr [rax+rax+00h]
0x1800206dc  mov     rbx, rax
0x1800206df  test    rax, rax
0x1800206e2  jnz     short loc_18002071D
0x1800206e4  lea     edx, [rsi+2Fh]; Ch
0x1800206e7  mov     rcx, rdi; Str
0x1800206ea  call    cs:__imp_strrchr
0x1800206f1  nop     dword ptr [rax+rax+00h]
0x1800206f6  mov     rbx, rax
0x1800206f9  test    rax, rax
0x1800206fc  jnz     short loc_18002071D
0x1800206fe  lea     edx, [rsi+3Ah]; Ch
0x180020701  mov     rcx, rdi; Str
0x180020704  call    cs:__imp_strrchr
0x18002070b  nop     dword ptr [rax+rax+00h]
0x180020710  mov     rbx, rax
0x180020713  test    rax, rax
0x180020716  jnz     short loc_18002071D
0x180020718  mov     rbx, rdi
0x18002071b  jmp     short loc_180020720
0x18002071d  inc     rbx
0x180020720  mov     rdi, [rsp+68h+arg_20]
0x180020728  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002072c  mov     rcx, rax
0x18002072f  inc     rcx
0x180020732  cmp     [rdi+rcx], sil
0x180020736  jnz     short loc_18002072F
0x180020738  inc     rax
0x18002073b  cmp     [rbx+rax], sil
0x18002073f  jnz     short loc_180020738
0x180020741  add     rax, 25h ; '%'
0x180020745  add     rax, rcx
0x180020748  cmp     rax, 100h
0x18002074e  jnb     short loc_180020798
0x180020750  call    cs:__imp_GetCurrentProcessId
0x180020757  nop     dword ptr [rax+rax+00h]
0x18002075c  mov     [rsp+68h+var_30], eax
0x180020760  mov     r9, rbx
0x180020763  mov     rax, [rsp+68h+arg_28]
0x18002076b  lea     r8, aSLuS08pPidLu; "%s:%lu %s:%08p PID:%lu"
0x180020772  mov     [rsp+68h+var_38], rax
0x180020777  mov     edx, 100h; BufferCount
0x18002077c  mov     [rsp+68h+var_40], rdi
0x180020781  mov     rcx, rbp; Buffer
0x180020784  mov     [rsp+68h+var_48], r14d
0x180020789  call    cs:__imp_sprintf_s
0x180020790  nop     dword ptr [rax+rax+00h]
0x180020795  mov     rsi, rbp
0x180020798  mov     rax, rsi
0x18002079b  add     rsp, 40h
0x18002079f  pop     r14
0x1800207a1  pop     rdi
0x1800207a2  pop     rsi
0x1800207a3  pop     rbp
0x1800207a4  pop     rbx
0x1800207a5  retn
```
