# PuDbgCreateSemaphore

- ea: `0x18001f5d0`
- end: `0x18001f6f0`
- name: `PuDbgCreateSemaphore`
- size: `288`
- prototype: `__int64 __fastcall(char *, unsigned int, char *, void *, LONG lInitialCount, LONG lMaximumCount)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path`

## callees

- `0x180002b60`
- `0x180019890`
- `0x18001f420`
- `0x18001f5d0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f6ab`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f6ab`

## pseudocode

```c
HANDLE __fastcall PuDbgCreateSemaphore(
        char *a1,
        unsigned int a2,
        char *a3,
        void *a4,
        LONG lInitialCount,
        LONG lMaximumCount)
{
  const WCHAR *v10; // r15
  unsigned int v11; // edx
  const char *v12; // rax
  HANDLE Semaphore; // rbx
  _BYTE v15[32]; // [rsp+30h] [rbp-D0h] BYREF
  const WCHAR *v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  __int16 v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h]
  char Buffer[256]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v21; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v22[510]; // [rsp+172h] [rbp+72h] BYREF

  v10 = 0;
  memset_0(v22, 0, sizeof(v22));
  v17 = 512;
  v16 = (const WCHAR *)&v21;
  v18 = 256;
  v21 = 0;
  v19 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v12 = PuDbgpBuildObjectName(Buffer, v11, a1, a2, a3, a4);
  if ( v12 )
  {
    STRU::CopyA((STRU *)v15, v12);
    v10 = v16;
  }
  Semaphore = CreateSemaphoreExW(0, lInitialCount, lMaximumCount, v10, 0, 0x1F0003u);
  if ( Semaphore )
    _InterlockedIncrement(&g_PuDbgSemaphoresCreated);
  BUFFER::~BUFFER((BUFFER *)v15);
  return Semaphore;
}

```

## disassembly

```asm
0x18001f5d0  push    rbp
0x18001f5d2  push    rbx
0x18001f5d3  push    rsi
0x18001f5d4  push    rdi
0x18001f5d5  push    r12
0x18001f5d7  push    r13
0x18001f5d9  push    r14
0x18001f5db  push    r15
0x18001f5dd  lea     rbp, [rsp-288h]
0x18001f5e5  sub     rsp, 388h
0x18001f5ec  mov     rax, cs:__security_cookie
0x18001f5f3  xor     rax, rsp
0x18001f5f6  mov     [rbp+2C0h+var_50], rax
0x18001f5fd  mov     r12d, [rbp+2C0h+lInitialCount]
0x18001f604  mov     rsi, r8
0x18001f607  mov     r13d, [rbp+2C0h+lMaximumCount]
0x18001f60e  mov     edi, edx
0x18001f610  mov     rbx, rcx
0x18001f613  xor     edx, edx; Val
0x18001f615  mov     r8d, 1FEh; Size
0x18001f61b  lea     rcx, [rbp+2C0h+var_24E]; void *
0x18001f61f  mov     r14, r9
0x18001f622  xor     r15d, r15d
0x18001f625  call    memset_0
0x18001f62a  lea     rax, [rbp+2C0h+var_250]
0x18001f62e  mov     [rsp+3C0h+var_368], 200h
0x18001f636  mov     [rsp+3C0h+var_370], rax
0x18001f63b  lea     rcx, [rsp+3C0h+Buffer]; void *
0x18001f640  xor     eax, eax
0x18001f642  mov     [rsp+3C0h+var_364], 100h
0x18001f649  xor     edx, edx; Val
0x18001f64b  mov     [rbp+2C0h+var_250], ax
0x18001f64f  mov     r8d, 100h; Size
0x18001f655  mov     [rsp+3C0h+var_360], r15d
0x18001f65a  call    memset_0
0x18001f65f  mov     r9d, edi; unsigned int
0x18001f662  mov     qword ptr [rsp+3C0h+dwDesiredAccess], r14; void *
0x18001f667  mov     r8, rbx; char *
0x18001f66a  mov     qword ptr [rsp+3C0h+dwFlags], rsi; char *
0x18001f66f  lea     rcx, [rsp+3C0h+Buffer]; Buffer
0x18001f674  call    ?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z; PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)
0x18001f679  test    rax, rax
0x18001f67c  jz      short loc_18001F690
0x18001f67e  mov     rdx, rax; char *
0x18001f681  lea     rcx, [rsp+3C0h+var_390]; this
0x18001f686  call    ?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18001f68b  mov     r15, [rsp+3C0h+var_370]
0x18001f690  mov     [rsp+3C0h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001f698  mov     r9, r15; lpName
0x18001f69b  mov     r8d, r13d; lMaximumCount
0x18001f69e  mov     [rsp+3C0h+dwFlags], 0; dwFlags
0x18001f6a6  mov     edx, r12d; lInitialCount
0x18001f6a9  xor     ecx, ecx; lpSemaphoreAttributes
0x18001f6ab  call    cs:__imp_CreateSemaphoreExW
0x18001f6b1  mov     rbx, rax
0x18001f6b4  test    rax, rax
0x18001f6b7  jz      short loc_18001F6C0
0x18001f6b9  lock inc cs:?g_PuDbgSemaphoresCreated@@3JA; long g_PuDbgSemaphoresCreated
0x18001f6c0  lea     rcx, [rsp+3C0h+var_390]; this
0x18001f6c5  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001f6ca  mov     rax, rbx
0x18001f6cd  mov     rcx, [rbp+2C0h+var_50]
0x18001f6d4  xor     rcx, rsp; StackCookie
0x18001f6d7  call    __security_check_cookie
0x18001f6dc  add     rsp, 388h
0x18001f6e3  pop     r15
0x18001f6e5  pop     r14
0x18001f6e7  pop     r13
0x18001f6e9  pop     r12
0x18001f6eb  pop     rdi
0x18001f6ec  pop     rsi
0x18001f6ed  pop     rbx
0x18001f6ee  pop     rbp
0x18001f6ef  retn
```
