# PuDbgCreateMutex

- ea: `0x18001f530`
- end: `0x18001f5c5`
- name: `PuDbgCreateMutex`
- size: `149`
- prototype: `__int64 __fastcall(char *, unsigned int, char *, void *, BOOL bInitialOwner)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x18001f420`
- `0x18001f530`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001f595`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001f595`

## pseudocode

```c
HANDLE __fastcall PuDbgCreateMutex(char *a1, unsigned int a2, char *a3, void *a4, BOOL bInitialOwner)
{
  unsigned int v9; // edx
  const CHAR *v10; // rax
  HANDLE result; // rax
  char Buffer[256]; // [rsp+30h] [rbp-138h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  v10 = PuDbgpBuildObjectName(Buffer, v9, a1, a2, a3, a4);
  result = CreateMutexA(0, bInitialOwner, v10);
  if ( result )
    _InterlockedIncrement(&g_PuDbgMutexesCreated);
  return result;
}

```

## disassembly

```asm
0x18001f530  push    rbx
0x18001f532  push    rbp
0x18001f533  push    rsi
0x18001f534  push    rdi
0x18001f535  push    r14
0x18001f537  sub     rsp, 140h
0x18001f53e  mov     rax, cs:__security_cookie
0x18001f545  xor     rax, rsp
0x18001f548  mov     [rsp+168h+var_38], rax
0x18001f550  mov     ebx, [rsp+168h+bInitialOwner]
0x18001f557  mov     rbp, r8
0x18001f55a  mov     esi, edx
0x18001f55c  mov     rdi, rcx
0x18001f55f  xor     edx, edx; Val
0x18001f561  lea     rcx, [rsp+168h+Buffer]; void *
0x18001f566  mov     r8d, 100h; Size
0x18001f56c  mov     r14, r9
0x18001f56f  call    memset_0
0x18001f574  mov     r9d, esi; unsigned int
0x18001f577  mov     [rsp+168h+var_140], r14; void *
0x18001f57c  mov     r8, rdi; char *
0x18001f57f  mov     [rsp+168h+var_148], rbp; char *
0x18001f584  lea     rcx, [rsp+168h+Buffer]; Buffer
0x18001f589  call    ?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z; PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)
0x18001f58e  mov     r8, rax; lpName
0x18001f591  mov     edx, ebx; bInitialOwner
0x18001f593  xor     ecx, ecx; lpMutexAttributes
0x18001f595  call    cs:__imp_CreateMutexA
0x18001f59b  test    rax, rax
0x18001f59e  jz      short loc_18001F5A7
0x18001f5a0  lock inc cs:?g_PuDbgMutexesCreated@@3JA; long g_PuDbgMutexesCreated
0x18001f5a7  mov     rcx, [rsp+168h+var_38]
0x18001f5af  xor     rcx, rsp; StackCookie
0x18001f5b2  call    __security_check_cookie
0x18001f5b7  add     rsp, 140h
0x18001f5be  pop     r14
0x18001f5c0  pop     rdi
0x18001f5c1  pop     rsi
0x18001f5c2  pop     rbp
0x18001f5c3  pop     rbx
0x18001f5c4  retn
```
