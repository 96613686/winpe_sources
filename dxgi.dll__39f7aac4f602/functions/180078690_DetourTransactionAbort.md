# DetourTransactionAbort

- ea: `0x180078690`
- end: `0x1800787f5`
- name: `DetourTransactionAbort`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180071ab8`

## callees

- `0x180076440`
- `0x180078690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007874c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007874c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078694`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800787b4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800787b4`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800786e5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078783`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800786e5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078783`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078795`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078795`

## pseudocode

```c
__int64 DetourTransactionAbort()
{
  __int64 result; // rax
  void *v1; // rbx
  __int64 v2; // rdx
  void *v3; // rdi
  HANDLE CurrentProcess; // rax
  _QWORD *v5; // rbx
  void *v6; // rdi
  HANDLE *v7; // rdi
  HANDLE *v8; // rbx
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180108E40 != GetCurrentThreadId() )
    return 4317;
  v1 = qword_180108E58;
  if ( qword_180108E58 )
  {
    do
    {
      VirtualProtect(
        *((LPVOID *)v1 + 3),
        *(unsigned __int8 *)(*((_QWORD *)v1 + 4) + 62LL),
        *((_DWORD *)v1 + 10),
        &flOldProtect);
      if ( !*((_DWORD *)v1 + 2) )
      {
        v2 = *((_QWORD *)v1 + 4);
        if ( v2 )
        {
          *(_OWORD *)v2 = 0;
          *(_OWORD *)(v2 + 16) = 0;
          *(_OWORD *)(v2 + 32) = 0;
          *(_OWORD *)(v2 + 48) = 0;
          *(_OWORD *)(v2 + 64) = 0;
          *(_OWORD *)(v2 + 80) = 0;
          *(_QWORD *)(v2 + 72) = *(_QWORD *)((v2 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
          *(_QWORD *)((v2 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v2;
          *((_QWORD *)v1 + 4) = 0;
        }
      }
      v3 = *(void **)v1;
      operator delete(v1, 0x30u);
      v1 = v3;
    }
    while ( v3 );
  }
  qword_180108E58 = 0;
  CurrentProcess = GetCurrentProcess();
  v5 = lpBaseAddress;
  v6 = CurrentProcess;
  if ( lpBaseAddress )
  {
    do
    {
      VirtualProtect(v5, 0x10000u, 0x20u, &flOldProtect);
      FlushInstructionCache(v6, v5, 0x10000u);
      v5 = (_QWORD *)v5[1];
    }
    while ( v5 );
  }
  v7 = (HANDLE *)qword_180108E50;
  if ( qword_180108E50 )
  {
    do
    {
      ResumeThread(v7[1]);
      v8 = (HANDLE *)*v7;
      operator delete(v7, 0x10u);
      v7 = v8;
    }
    while ( v8 );
  }
  result = 0;
  qword_180108E50 = 0;
  dword_180108E40 = 0;
  return result;
}

```

## disassembly

```asm
0x180078690  sub     rsp, 28h
0x180078694  call    cs:__imp_GetCurrentThreadId
0x18007869a  cmp     cs:dword_180108E40, eax
0x1800786a0  jz      short loc_1800786AC
0x1800786a2  mov     eax, 10DDh
0x1800786a7  add     rsp, 28h
0x1800786ab  retn
0x1800786ac  mov     [rsp+28h+arg_8], rbx
0x1800786b1  mov     rbx, cs:qword_180108E58
0x1800786b8  mov     [rsp+28h+arg_10], rsi
0x1800786bd  xor     esi, esi
0x1800786bf  mov     [rsp+28h+var_8], rdi
0x1800786c4  test    rbx, rbx
0x1800786c7  jz      short loc_180078745
0x1800786c9  nop     dword ptr [rax+00000000h]
0x1800786d0  mov     rax, [rbx+20h]
0x1800786d4  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800786d9  mov     r8d, [rbx+28h]; flNewProtect
0x1800786dd  mov     rcx, [rbx+18h]; lpAddress
0x1800786e1  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x1800786e5  call    cs:__imp_VirtualProtect
0x1800786eb  cmp     [rbx+8], esi
0x1800786ee  jnz     short loc_18007872D
0x1800786f0  mov     rdx, [rbx+20h]
0x1800786f4  test    rdx, rdx
0x1800786f7  jz      short loc_18007872D
0x1800786f9  xorps   xmm0, xmm0
0x1800786fc  mov     rcx, rdx
0x1800786ff  movups  xmmword ptr [rdx], xmm0
0x180078702  and     rcx, 0FFFFFFFFFFFF0000h
0x180078709  movups  xmmword ptr [rdx+10h], xmm0
0x18007870d  movups  xmmword ptr [rdx+20h], xmm0
0x180078711  movups  xmmword ptr [rdx+30h], xmm0
0x180078715  movups  xmmword ptr [rdx+40h], xmm0
0x180078719  movups  xmmword ptr [rdx+50h], xmm0
0x18007871d  mov     rax, [rcx+10h]
0x180078721  mov     [rdx+48h], rax
0x180078725  mov     [rcx+10h], rdx
0x180078729  mov     [rbx+20h], rsi
0x18007872d  mov     rdi, [rbx]
0x180078730  mov     edx, 30h ; '0'; unsigned __int64
0x180078735  mov     rcx, rbx; void *
0x180078738  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007873d  mov     rbx, rdi
0x180078740  test    rdi, rdi
0x180078743  jnz     short loc_1800786D0
0x180078745  mov     cs:qword_180108E58, rsi
0x18007874c  call    cs:__imp_GetCurrentProcess
0x180078752  mov     rbx, cs:lpBaseAddress
0x180078759  mov     rdi, rax
0x18007875c  test    rbx, rbx
0x18007875f  jz      short loc_1800787A4
0x180078761  nop     dword ptr [rax+00h]
0x180078765  nop     word ptr [rax+rax+00000000h]
0x180078770  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180078775  mov     edx, 10000h; dwSize
0x18007877a  mov     r8d, 20h ; ' '; flNewProtect
0x180078780  mov     rcx, rbx; lpAddress
0x180078783  call    cs:__imp_VirtualProtect
0x180078789  mov     r8d, 10000h; dwSize
0x18007878f  mov     rdx, rbx; lpBaseAddress
0x180078792  mov     rcx, rdi; hProcess
0x180078795  call    cs:__imp_FlushInstructionCache
0x18007879b  mov     rbx, [rbx+8]
0x18007879f  test    rbx, rbx
0x1800787a2  jnz     short loc_180078770
0x1800787a4  mov     rdi, cs:qword_180108E50
0x1800787ab  test    rdi, rdi
0x1800787ae  jz      short loc_1800787D2
0x1800787b0  mov     rcx, [rdi+8]; hThread
0x1800787b4  call    cs:__imp_ResumeThread
0x1800787ba  mov     rbx, [rdi]
0x1800787bd  mov     edx, 10h; unsigned __int64
0x1800787c2  mov     rcx, rdi; void *
0x1800787c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800787ca  mov     rdi, rbx
0x1800787cd  test    rbx, rbx
0x1800787d0  jnz     short loc_1800787B0
0x1800787d2  mov     rdi, [rsp+28h+var_8]
0x1800787d7  xor     eax, eax
0x1800787d9  mov     rbx, [rsp+28h+arg_8]
0x1800787de  mov     cs:qword_180108E50, rsi
0x1800787e5  mov     cs:dword_180108E40, esi
0x1800787eb  mov     rsi, [rsp+28h+arg_10]
0x1800787f0  add     rsp, 28h
0x1800787f4  retn
```
