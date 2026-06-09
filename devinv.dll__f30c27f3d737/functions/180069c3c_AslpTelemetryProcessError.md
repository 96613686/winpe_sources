# AslpTelemetryProcessError

- ea: `0x180069c3c`
- end: `0x180069dab`
- name: `AslpTelemetryProcessError`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800613a0`

## callees

- `0x180068990`
- `0x180069c3c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180069da4`
- `ntdll!RtlEnterCriticalSection` at `0x180069c76`
- `ntdll!RtlEnterCriticalSection` at `0x180069c76`
- `ntdll!RtlAllocateHeap` at `0x180069d13`
- `ntdll!RtlAllocateHeap` at `0x180069d13`
- `ntdll!RtlInitAnsiString` at `0x180069d5e`
- `ntdll!RtlInitAnsiString` at `0x180069d5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069c63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069c63`

## pseudocode

```c
NTSTATUS __fastcall AslpTelemetryProcessError(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  DWORD v6; // ebp
  unsigned __int64 v7; // r9
  unsigned int i; // r14d
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  SIZE_T v15; // rbp
  char *Heap; // rax
  const char *v17; // rdi
  int v18; // eax
  __int64 v20; // [rsp+20h] [rbp-48h]
  DWORD CurrentThreadId; // [rsp+88h] [rbp+20h]

  v4 = a2;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CurrentThreadId;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
  v7 = *(_QWORD *)(a1 + 192);
  if ( v7 )
  {
    for ( i = 0; i < v7; ++i )
    {
      v9 = 0;
      if ( i < v7 )
      {
        v10 = *(_QWORD *)(a1 + 184) * i;
        if ( !is_mul_ok(*(_QWORD *)(a1 + 184), i) || (v11 = *(_QWORD *)(a1 + 216), v9 = v11 + v10, v11 + v10 < v11) )
          v9 = 0;
      }
      if ( *(_DWORD *)v9 == v6 )
      {
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_BYTE *)(v4 + v12) );
          if ( a3 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *(_BYTE *)(a3 + v13) );
            v14 = (unsigned __int16)v13;
          }
          else
          {
            v14 = 16;
          }
          v15 = v14 + (unsigned __int16)v12 + 2LL;
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
          v17 = Heap;
          if ( !Heap )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          if ( a3 )
          {
            v18 = RtlStringCchPrintfA(Heap, v15, "%s#%s", a2, a3);
          }
          else
          {
            LODWORD(v20) = 0;
            v18 = RtlStringCchPrintfA(Heap, v15, "%s#%d", a2, v20);
          }
          if ( v18 < 0 )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          RtlInitAnsiString((PANSI_STRING)(v9 + 24), v17);
          v4 = a2;
          v6 = CurrentThreadId;
        }
        ++*(_DWORD *)(v9 + 40);
      }
      v7 = *(_QWORD *)(a1 + 192);
    }
  }
  return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
}

```

## disassembly

```asm
0x180069c3c  mov     [rsp+arg_10], rbx
0x180069c41  mov     [rsp+arg_18], r9d
0x180069c46  mov     [rsp+arg_8], rdx
0x180069c4b  push    rbp
0x180069c4c  push    rsi
0x180069c4d  push    rdi
0x180069c4e  push    r12
0x180069c50  push    r13
0x180069c52  push    r14
0x180069c54  push    r15
0x180069c56  sub     rsp, 30h
0x180069c5a  mov     r12, r8
0x180069c5d  mov     rdi, rdx
0x180069c60  mov     rsi, rcx
0x180069c63  call    cs:__imp_GetCurrentThreadId
0x180069c69  lea     rcx, [rsi+58h]; CriticalSection
0x180069c6d  mov     [rsp+68h+arg_18], eax
0x180069c74  mov     ebp, eax
0x180069c76  call    cs:__imp_RtlEnterCriticalSection
0x180069c7c  mov     r9, [rsi+0C0h]
0x180069c83  test    r9, r9
0x180069c86  jz      loc_180069D89
0x180069c8c  xor     r14d, r14d
0x180069c8f  xor     ebx, ebx
0x180069c91  mov     eax, r14d
0x180069c94  cmp     rax, r9
0x180069c97  jnb     short loc_180069CB7
0x180069c99  mul     qword ptr [rsi+0B8h]
0x180069ca0  test    rdx, rdx
0x180069ca3  jnz     short loc_180069CB5
0x180069ca5  mov     rcx, [rsi+0D8h]
0x180069cac  lea     rbx, [rcx+rax]
0x180069cb0  cmp     rbx, rcx
0x180069cb3  jnb     short loc_180069CB7
0x180069cb5  xor     ebx, ebx
0x180069cb7  cmp     [rbx], ebp
0x180069cb9  jnz     loc_180069D73
0x180069cbf  cmp     qword ptr [rbx+20h], 0
0x180069cc4  jnz     loc_180069D70
0x180069cca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180069cce  inc     rcx
0x180069cd1  cmp     byte ptr [rdi+rcx], 0
0x180069cd5  jnz     short loc_180069CCE
0x180069cd7  test    r12, r12
0x180069cda  jz      short loc_180069CEF
0x180069cdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180069ce0  inc     rax
0x180069ce3  cmp     byte ptr [r12+rax], 0
0x180069ce8  jnz     short loc_180069CE0
0x180069cea  movzx   edx, ax
0x180069ced  jmp     short loc_180069CF4
0x180069cef  mov     edx, 10h
0x180069cf4  movzx   ebp, cx
0x180069cf7  mov     rcx, gs:60h
0x180069d00  add     rbp, 2
0x180069d04  add     rbp, rdx
0x180069d07  mov     edx, 8; Flags
0x180069d0c  mov     r8, rbp; Size
0x180069d0f  mov     rcx, [rcx+30h]; HeapHandle
0x180069d13  call    cs:__imp_RtlAllocateHeap
0x180069d19  mov     rdi, rax
0x180069d1c  test    rax, rax
0x180069d1f  jz      short loc_180069D89
0x180069d21  mov     r9, [rsp+68h+arg_8]
0x180069d26  mov     rdx, rbp; unsigned __int64
0x180069d29  mov     rcx, rax; char *
0x180069d2c  test    r12, r12
0x180069d2f  jz      short loc_180069D3F
0x180069d31  mov     [rsp+68h+var_48], r12
0x180069d36  lea     r8, aSS_0; "%s#%s"
0x180069d3d  jmp     short loc_180069D4E
0x180069d3f  mov     dword ptr [rsp+68h+var_48], 0
0x180069d47  lea     r8, aSD_0; "%s#%d"
0x180069d4e  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180069d53  test    eax, eax
0x180069d55  js      short loc_180069D89
0x180069d57  mov     rdx, rdi; SourceString
0x180069d5a  lea     rcx, [rbx+18h]; DestinationString
0x180069d5e  call    cs:__imp_RtlInitAnsiString
0x180069d64  mov     rdi, [rsp+68h+arg_8]
0x180069d69  mov     ebp, [rsp+68h+arg_18]
0x180069d70  inc     dword ptr [rbx+28h]
0x180069d73  mov     r9, [rsi+0C0h]
0x180069d7a  inc     r14d
0x180069d7d  mov     eax, r14d
0x180069d80  cmp     rax, r9
0x180069d83  jb      loc_180069C8F
0x180069d89  lea     rcx, [rsi+58h]
0x180069d8d  mov     rbx, [rsp+68h+arg_10]
0x180069d95  add     rsp, 30h
0x180069d99  pop     r15
0x180069d9b  pop     r14
0x180069d9d  pop     r13
0x180069d9f  pop     r12
0x180069da1  pop     rdi
0x180069da2  pop     rsi
0x180069da3  pop     rbp
0x180069da4  jmp     cs:__imp_RtlLeaveCriticalSection
```
