# AslpTelemetryProcessError

- ea: `0x180017eec`
- end: `0x18001805b`
- name: `AslpTelemetryProcessError`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008f90`

## callees

- `0x180015e60`
- `0x180017eec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017f13`
- `KERNEL32!GetCurrentThreadId` at `0x180017f13`
- `ntdll!RtlLeaveCriticalSection` at `0x180018054`
- `ntdll!RtlEnterCriticalSection` at `0x180017f26`
- `ntdll!RtlEnterCriticalSection` at `0x180017f26`
- `ntdll!RtlInitAnsiString` at `0x18001800e`
- `ntdll!RtlInitAnsiString` at `0x18001800e`
- `ntdll!RtlAllocateHeap` at `0x180017fc3`
- `ntdll!RtlAllocateHeap` at `0x180017fc3`

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
0x180017eec  mov     [rsp+arg_10], rbx
0x180017ef1  mov     [rsp+arg_18], r9d
0x180017ef6  mov     [rsp+arg_8], rdx
0x180017efb  push    rbp
0x180017efc  push    rsi
0x180017efd  push    rdi
0x180017efe  push    r12
0x180017f00  push    r13
0x180017f02  push    r14
0x180017f04  push    r15
0x180017f06  sub     rsp, 30h
0x180017f0a  mov     r12, r8
0x180017f0d  mov     rdi, rdx
0x180017f10  mov     rsi, rcx
0x180017f13  call    cs:__imp_GetCurrentThreadId
0x180017f19  lea     rcx, [rsi+58h]; CriticalSection
0x180017f1d  mov     [rsp+68h+arg_18], eax
0x180017f24  mov     ebp, eax
0x180017f26  call    cs:__imp_RtlEnterCriticalSection
0x180017f2c  mov     r9, [rsi+0C0h]
0x180017f33  test    r9, r9
0x180017f36  jz      loc_180018039
0x180017f3c  xor     r14d, r14d
0x180017f3f  xor     ebx, ebx
0x180017f41  mov     eax, r14d
0x180017f44  cmp     rax, r9
0x180017f47  jnb     short loc_180017F67
0x180017f49  mul     qword ptr [rsi+0B8h]
0x180017f50  test    rdx, rdx
0x180017f53  jnz     short loc_180017F65
0x180017f55  mov     rcx, [rsi+0D8h]
0x180017f5c  lea     rbx, [rcx+rax]
0x180017f60  cmp     rbx, rcx
0x180017f63  jnb     short loc_180017F67
0x180017f65  xor     ebx, ebx
0x180017f67  cmp     [rbx], ebp
0x180017f69  jnz     loc_180018023
0x180017f6f  cmp     qword ptr [rbx+20h], 0
0x180017f74  jnz     loc_180018020
0x180017f7a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017f7e  inc     rcx
0x180017f81  cmp     byte ptr [rdi+rcx], 0
0x180017f85  jnz     short loc_180017F7E
0x180017f87  test    r12, r12
0x180017f8a  jz      short loc_180017F9F
0x180017f8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017f90  inc     rax
0x180017f93  cmp     byte ptr [r12+rax], 0
0x180017f98  jnz     short loc_180017F90
0x180017f9a  movzx   edx, ax
0x180017f9d  jmp     short loc_180017FA4
0x180017f9f  mov     edx, 10h
0x180017fa4  movzx   ebp, cx
0x180017fa7  mov     rcx, gs:60h
0x180017fb0  add     rbp, 2
0x180017fb4  add     rbp, rdx
0x180017fb7  mov     edx, 8; Flags
0x180017fbc  mov     r8, rbp; Size
0x180017fbf  mov     rcx, [rcx+30h]; HeapHandle
0x180017fc3  call    cs:__imp_RtlAllocateHeap
0x180017fc9  mov     rdi, rax
0x180017fcc  test    rax, rax
0x180017fcf  jz      short loc_180018039
0x180017fd1  mov     r9, [rsp+68h+arg_8]
0x180017fd6  mov     rdx, rbp; unsigned __int64
0x180017fd9  mov     rcx, rax; char *
0x180017fdc  test    r12, r12
0x180017fdf  jz      short loc_180017FEF
0x180017fe1  mov     [rsp+68h+var_48], r12
0x180017fe6  lea     r8, aSS; "%s#%s"
0x180017fed  jmp     short loc_180017FFE
0x180017fef  mov     dword ptr [rsp+68h+var_48], 0
0x180017ff7  lea     r8, aSD; "%s#%d"
0x180017ffe  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018003  test    eax, eax
0x180018005  js      short loc_180018039
0x180018007  mov     rdx, rdi; SourceString
0x18001800a  lea     rcx, [rbx+18h]; DestinationString
0x18001800e  call    cs:__imp_RtlInitAnsiString
0x180018014  mov     rdi, [rsp+68h+arg_8]
0x180018019  mov     ebp, [rsp+68h+arg_18]
0x180018020  inc     dword ptr [rbx+28h]
0x180018023  mov     r9, [rsi+0C0h]
0x18001802a  inc     r14d
0x18001802d  mov     eax, r14d
0x180018030  cmp     rax, r9
0x180018033  jb      loc_180017F3F
0x180018039  lea     rcx, [rsi+58h]
0x18001803d  mov     rbx, [rsp+68h+arg_10]
0x180018045  add     rsp, 30h
0x180018049  pop     r15
0x18001804b  pop     r14
0x18001804d  pop     r13
0x18001804f  pop     r12
0x180018051  pop     rdi
0x180018052  pop     rsi
0x180018053  pop     rbp
0x180018054  jmp     cs:__imp_RtlLeaveCriticalSection
```
