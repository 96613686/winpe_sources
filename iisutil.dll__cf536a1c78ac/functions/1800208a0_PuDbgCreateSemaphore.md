# PuDbgCreateSemaphore

- ea: `0x1800208a0`
- end: `0x1800209c7`
- name: `PuDbgCreateSemaphore`
- size: `295`
- prototype: `__int64 __fastcall(char *, unsigned int, char *, void *, LONG lInitialCount, LONG lMaximumCount)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path`

## callees

- `0x1800034f0`
- `0x18001a700`
- `0x1800206b4`
- `0x1800208a0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002097b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002097b`

## pseudocode

```c
HANDLE __fastcall PuDbgCreateSemaphore(char *a1, int a2, char *a3, void *a4, LONG lInitialCount, LONG lMaximumCount)
{
  const WCHAR *v10; // r15
  __int64 v11; // rdx
  char *v12; // rax
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
0x1800208a0  push    rbp
0x1800208a2  push    rbx
0x1800208a3  push    rsi
0x1800208a4  push    rdi
0x1800208a5  push    r12
0x1800208a7  push    r13
0x1800208a9  push    r14
0x1800208ab  push    r15
0x1800208ad  lea     rbp, [rsp-288h]
0x1800208b5  sub     rsp, 388h
0x1800208bc  mov     rax, cs:__security_cookie
0x1800208c3  xor     rax, rsp
0x1800208c6  mov     [rbp+2C0h+var_50], rax
0x1800208cd  mov     r12d, [rbp+2C0h+lInitialCount]
0x1800208d4  mov     rsi, r8
0x1800208d7  mov     r13d, [rbp+2C0h+lMaximumCount]
0x1800208de  mov     edi, edx
0x1800208e0  mov     rbx, rcx
0x1800208e3  xor     edx, edx; Val
0x1800208e5  mov     r8d, 1FEh; Size
0x1800208eb  lea     rcx, [rbp+2C0h+var_24E]; void *
0x1800208ef  mov     r14, r9
0x1800208f2  xor     r15d, r15d
0x1800208f5  call    memset_0
0x1800208fa  lea     rax, [rbp+2C0h+var_250]
0x1800208fe  mov     [rsp+3C0h+var_368], 200h
0x180020906  mov     [rsp+3C0h+var_370], rax
0x18002090b  lea     rcx, [rsp+3C0h+Buffer]; void *
0x180020910  xor     eax, eax
0x180020912  mov     [rsp+3C0h+var_364], 100h
0x180020919  xor     edx, edx; Val
0x18002091b  mov     [rbp+2C0h+var_250], ax
0x18002091f  mov     r8d, 100h; Size
0x180020925  mov     [rsp+3C0h+var_360], r15d
0x18002092a  call    memset_0
0x18002092f  mov     r9d, edi; unsigned int
0x180020932  mov     qword ptr [rsp+3C0h+dwDesiredAccess], r14; void *
0x180020937  mov     r8, rbx; char *
0x18002093a  mov     qword ptr [rsp+3C0h+dwFlags], rsi; char *
0x18002093f  lea     rcx, [rsp+3C0h+Buffer]; Buffer
0x180020944  call    ?PuDbgpBuildObjectName@@YAPEADPEADK0K0PEAX@Z; PuDbgpBuildObjectName(char *,ulong,char *,ulong,char *,void *)
0x180020949  test    rax, rax
0x18002094c  jz      short loc_180020960
0x18002094e  mov     rdx, rax; char *
0x180020951  lea     rcx, [rsp+3C0h+var_390]; this
0x180020956  call    ?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002095b  mov     r15, [rsp+3C0h+var_370]
0x180020960  mov     [rsp+3C0h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180020968  mov     r9, r15; lpName
0x18002096b  mov     r8d, r13d; lMaximumCount
0x18002096e  mov     [rsp+3C0h+dwFlags], 0; dwFlags
0x180020976  mov     edx, r12d; lInitialCount
0x180020979  xor     ecx, ecx; lpSemaphoreAttributes
0x18002097b  call    cs:__imp_CreateSemaphoreExW
0x180020982  nop     dword ptr [rax+rax+00h]
0x180020987  mov     rbx, rax
0x18002098a  test    rax, rax
0x18002098d  jz      short loc_180020996
0x18002098f  lock inc cs:?g_PuDbgSemaphoresCreated@@3JA; long g_PuDbgSemaphoresCreated
0x180020996  lea     rcx, [rsp+3C0h+var_390]; this
0x18002099b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800209a0  mov     rax, rbx
0x1800209a3  mov     rcx, [rbp+2C0h+var_50]
0x1800209aa  xor     rcx, rsp; StackCookie
0x1800209ad  call    __security_check_cookie
0x1800209b2  add     rsp, 388h
0x1800209b9  pop     r15
0x1800209bb  pop     r14
0x1800209bd  pop     r13
0x1800209bf  pop     r12
0x1800209c1  pop     rdi
0x1800209c2  pop     rsi
0x1800209c3  pop     rbx
0x1800209c4  pop     rbp
0x1800209c5  retn
```
