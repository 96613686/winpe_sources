# PrepareAsyncRequest

- ea: `0x1800039f8`
- end: `0x180003ae7`
- name: `PrepareAsyncRequest`
- size: `239`
- prototype: `__int64 __fastcall(int, int, int, unsigned int, _QWORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180004310`
- `0x180004400`
- `0x1800049a0`
- `0x180004bc0`
- `0x180004d30`
- `0x1800063b0`
- `0x180006d40`
- `0x180006fb0`
- `0x1800071b0`

## callees

- `0x18000274c`
- `0x1800039f8`
- `0x180007df8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180003a6c`
- `KERNEL32!InitializeCriticalSection` at `0x180003a6c`
- `KERNEL32!LeaveCriticalSection` at `0x180003ac5`
- `KERNEL32!LeaveCriticalSection` at `0x180003ac5`
- `KERNEL32!EnterCriticalSection` at `0x180003a90`
- `KERNEL32!EnterCriticalSection` at `0x180003a90`

## pseudocode

```c
__int64 __fastcall PrepareAsyncRequest(int a1, int a2, int a3, unsigned int a4, _QWORD *a5)
{
  const char *v9; // rdx
  __int64 v11; // rax
  _DWORD *v12; // rbx
  unsigned int v13; // eax

  if ( a4 + 128 < a4 )
  {
    v9 = "PrepareAsyncRequest: Arithmatic Overflow error.Failed to alloc async req for oid(%x)";
LABEL_3:
    TspLog(1, v9);
    return 2147483716LL;
  }
  v11 = AllocRequest();
  v12 = (_DWORD *)v11;
  if ( !v11 )
  {
    v9 = "PrepareAsyncRequest: failed to alloc async req for oid(%x)";
    goto LABEL_3;
  }
  *(_QWORD *)(v11 + 24) = 0;
  *(_DWORD *)(v11 + 32) = 1095915339;
  *(_DWORD *)(v11 + 36) = a3;
  *(_QWORD *)(v11 + 40) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
  v12[22] = 1;
  v12[27] = a1;
  v12[28] = a2;
  v12[29] = a4;
  EnterCriticalSection(&gRequestIDCritSec);
  v13 = gdwRequestID + 1;
  gdwRequestID = v13;
  v12[30] = v13;
  if ( v13 >= 0x7FFFFFFF )
    gdwRequestID = 1;
  LeaveCriticalSection(&gRequestIDCritSec);
  *a5 = v12;
  return 0;
}

```

## disassembly

```asm
0x1800039f8  push    rbx
0x1800039fa  push    rbp
0x1800039fb  push    rsi
0x1800039fc  push    rdi
0x1800039fd  push    r14
0x1800039ff  sub     rsp, 20h
0x180003a03  mov     edi, ecx
0x180003a05  mov     esi, r9d
0x180003a08  lea     ecx, [r9+80h]
0x180003a0f  mov     ebp, r8d
0x180003a12  mov     r14d, edx
0x180003a15  cmp     ecx, r9d
0x180003a18  jnb     short loc_180003A38
0x180003a1a  lea     rdx, aPrepareasyncre_0; "PrepareAsyncRequest: Arithmatic Overflo"...
0x180003a21  mov     r8d, edi
0x180003a24  mov     ecx, 1
0x180003a29  call    TspLog
0x180003a2e  mov     eax, 80000044h
0x180003a33  jmp     loc_180003ADB
0x180003a38  call    AllocRequest
0x180003a3d  mov     rbx, rax
0x180003a40  test    rax, rax
0x180003a43  jnz     short loc_180003A4E
0x180003a45  lea     rdx, aPrepareasyncre; "PrepareAsyncRequest: failed to alloc as"...
0x180003a4c  jmp     short loc_180003A21
0x180003a4e  lea     rcx, [rax+30h]; lpCriticalSection
0x180003a52  mov     qword ptr [rax+18h], 0
0x180003a5a  mov     dword ptr [rax+20h], 4152574Bh
0x180003a61  mov     [rax+24h], ebp
0x180003a64  mov     qword ptr [rax+28h], 0
0x180003a6c  call    cs:__imp_InitializeCriticalSection
0x180003a73  nop     dword ptr [rax+rax+00h]
0x180003a78  lea     rcx, gRequestIDCritSec; lpCriticalSection
0x180003a7f  mov     dword ptr [rbx+58h], 1
0x180003a86  mov     [rbx+6Ch], edi
0x180003a89  mov     [rbx+70h], r14d
0x180003a8d  mov     [rbx+74h], esi
0x180003a90  call    cs:__imp_EnterCriticalSection
0x180003a97  nop     dword ptr [rax+rax+00h]
0x180003a9c  mov     eax, cs:gdwRequestID
0x180003aa2  inc     eax
0x180003aa4  mov     cs:gdwRequestID, eax
0x180003aaa  mov     [rbx+78h], eax
0x180003aad  cmp     eax, 7FFFFFFFh
0x180003ab2  jb      short loc_180003ABE
0x180003ab4  mov     cs:gdwRequestID, 1
0x180003abe  lea     rcx, gRequestIDCritSec; lpCriticalSection
0x180003ac5  call    cs:__imp_LeaveCriticalSection
0x180003acc  nop     dword ptr [rax+rax+00h]
0x180003ad1  mov     rax, [rsp+48h+arg_20]
0x180003ad6  mov     [rax], rbx
0x180003ad9  xor     eax, eax
0x180003adb  add     rsp, 20h
0x180003adf  pop     r14
0x180003ae1  pop     rdi
0x180003ae2  pop     rsi
0x180003ae3  pop     rbp
0x180003ae4  pop     rbx
0x180003ae5  retn
```
