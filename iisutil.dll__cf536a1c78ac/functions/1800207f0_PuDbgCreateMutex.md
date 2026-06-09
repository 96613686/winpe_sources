# PuDbgCreateMutex

- ea: `0x1800207f0`
- end: `0x18002088c`
- name: `PuDbgCreateMutex`
- size: `156`
- prototype: `__int64 __fastcall(char *, unsigned int, char *, void *, BOOL bInitialOwner)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x1800206b4`
- `0x1800207f0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180020855`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180020855`

## pseudocode

```c
HANDLE __fastcall PuDbgCreateMutex(char *a1, int a2, char *a3, void *a4, BOOL bInitialOwner)
{
  __int64 v9; // rdx
  char *v10; // rax
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
0x1800207f0  push    rbx
0x1800207f2  push    rbp
0x1800207f3  push    rsi
0x1800207f4  push    rdi
0x1800207f5  push    r14
0x1800207f7  sub     rsp, 140h
0x1800207fe  mov     rax, cs:__security_cookie
0x180020805  xor     rax, rsp
0x180020808  mov     [rsp+168h+var_38], rax
0x180020810  mov     ebx, [rsp+168h+bInitialOwner]
0x180020817  mov     rbp, r8
0x18002081a  mov     esi, edx
0x18002081c  mov     rdi, rcx
0x18002081f  xor     edx, edx; Val
0x180020821  lea     rcx, [rsp+168h+Buffer]; void *
0x180020826  mov     r8d, 100h; Size
0x18002082c  mov     r14, r9
0x18002082f  call    memset_0
0x180020834  mov     r9d, esi; unsigned int
0x180020837  mov     [rsp+168h+var_140], r14; void *
0x18002083c  mov     r8, rdi; char *
0x18002083f  mov     [rsp+168h+var_148], rbp; char *
0x180020844  lea     rcx, [rsp+168h+Buffer]; Buffer
0x180020849  call    ?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z; PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)
0x18002084e  mov     r8, rax; lpName
0x180020851  mov     edx, ebx; bInitialOwner
0x180020853  xor     ecx, ecx; lpMutexAttributes
0x180020855  call    cs:__imp_CreateMutexA
0x18002085c  nop     dword ptr [rax+rax+00h]
0x180020861  test    rax, rax
0x180020864  jz      short loc_18002086D
0x180020866  lock inc cs:?g_PuDbgMutexesCreated@@3JA; long g_PuDbgMutexesCreated
0x18002086d  mov     rcx, [rsp+168h+var_38]
0x180020875  xor     rcx, rsp; StackCookie
0x180020878  call    __security_check_cookie
0x18002087d  add     rsp, 140h
0x180020884  pop     r14
0x180020886  pop     rdi
0x180020887  pop     rsi
0x180020888  pop     rbp
0x180020889  pop     rbx
0x18002088a  retn
```
