# EtwpAllocateTraceHandle(ulong)

- ea: `0x180003fa8`
- end: `0x180004164`
- name: `?EtwpAllocateTraceHandle@@YAPEAU_TRACELOG_CONTEXT@@K@Z`
- size: `444`
- prototype: `struct _TRACELOG_CONTEXT *__fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180006740`
- `0x180006970`
- `0x180006c60`
- `0x180007060`

## callees

- `0x180001eb2`
- `0x180001ff0`
- `0x180002014`
- `0x180002020`
- `0x180003fa8`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004159`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004159`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004121`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004121`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040cb`

## pseudocode

```c
struct _TRACELOG_CONTEXT *__fastcall EtwpAllocateTraceHandle(unsigned int a1)
{
  unsigned __int64 v1; // rdi
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned __int64 v4; // rbp
  void *v5; // rax
  void *v6; // rsi
  __int64 **v7; // rdi
  __int64 *v8; // rcx
  __int64 *v9; // rdx
  __int64 v10; // rax
  __int64 *v11; // rcx
  HANDLE EventW; // rax
  __int64 *v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // rax
  struct _LIST_ENTRY *v17; // rax

  v1 = a1;
  v2 = operator new(0x408u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 0;
  memset_0(v2, 0, 0x408u);
  v3[84] = v3 + 84;
  v3[85] = v3 + 84;
  *((_BYTE *)v3 + 705) = 8;
  if ( (_DWORD)v1 )
  {
    v4 = 8 * v1;
    if ( !is_mul_ok(v1, 8u) )
      v4 = -1;
    v5 = operator new(v4, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( v5 )
      memset_0(v5, 0, v4);
    v3[94] = v6;
    if ( !v6 )
    {
      v7 = (__int64 **)(v3 + 84);
      while ( 1 )
      {
        v8 = *v7;
        if ( *v7 == (__int64 *)v7 )
          break;
        v9 = (__int64 *)v8[1];
        v10 = *v8;
        *v9 = *v8;
        *(_QWORD *)(v10 + 8) = v9;
        operator delete(v8);
      }
LABEL_11:
      v11 = v7[2];
      v7[3] = 0;
      if ( v11 )
        operator delete(v11);
      operator delete(v3);
      return 0;
    }
  }
  *((_DWORD *)v3 + 6) = 0;
  v3[104] = v3 + 103;
  v3[103] = v3 + 103;
  *((_DWORD *)v3 + 7) = v1;
  *((_DWORD *)v3 + 146) = -1;
  if ( !(_DWORD)v1 )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    v3[77] = EventW;
    if ( !EventW )
    {
      v7 = (__int64 **)(v3 + 84);
      while ( 1 )
      {
        v14 = *v7;
        if ( *v7 == (__int64 *)v7 )
          break;
        v15 = (__int64 *)v14[1];
        v16 = *v14;
        *v15 = *v14;
        *(_QWORD *)(v16 + 8) = v15;
        operator delete(v14);
      }
      goto LABEL_11;
    }
  }
  v3[2] = _InterlockedIncrement((volatile signed __int32 *)&EtwpTracelogHandleNumber);
  RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
  v17 = off_18001D018;
  if ( (struct _TRACELOG_CONTEXT **)off_18001D018->Flink != &EtwpTraceHandleList )
    __fastfail(3u);
  *v3 = &EtwpTraceHandleList;
  v3[1] = v17;
  v17->Flink = (struct _LIST_ENTRY *)v3;
  off_18001D018 = (struct _LIST_ENTRY *)v3;
  RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
  return (struct _TRACELOG_CONTEXT *)v3;
}

```

## disassembly

```asm
0x180003fa8  push    rbx
0x180003faa  push    rbp
0x180003fab  push    rsi
0x180003fac  push    rdi
0x180003fad  push    r12
0x180003faf  push    r15
0x180003fb1  sub     rsp, 28h
0x180003fb5  mov     edi, ecx
0x180003fb7  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180003fbe  mov     esi, 408h
0x180003fc3  mov     rdx, r15; struct std::nothrow_t *
0x180003fc6  mov     ecx, esi; unsigned __int64
0x180003fc8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003fcd  mov     rbx, rax
0x180003fd0  test    rax, rax
0x180003fd3  jz      loc_180004087
0x180003fd9  mov     r8d, esi; Size
0x180003fdc  xor     edx, edx; Val
0x180003fde  mov     rcx, rax; void *
0x180003fe1  call    memset_0
0x180003fe6  lea     rcx, [rbx+2A0h]
0x180003fed  or      r12, 0FFFFFFFFFFFFFFFFh
0x180003ff1  mov     [rcx], rcx
0x180003ff4  mov     [rcx+8], rcx
0x180003ff8  mov     byte ptr [rcx+21h], 8
0x180003ffc  test    edi, edi
0x180003ffe  jz      loc_180004099
0x180004004  lea     eax, [r12+9]
0x180004009  mul     rdi
0x18000400c  mov     rdx, r15; struct std::nothrow_t *
0x18000400f  mov     rbp, rax
0x180004012  cmovb   rbp, r12
0x180004016  mov     rcx, rbp; unsigned __int64
0x180004019  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000401e  mov     rsi, rax
0x180004021  test    rax, rax
0x180004024  jz      short loc_180004033
0x180004026  mov     r8, rbp; Size
0x180004029  xor     edx, edx; Val
0x18000402b  mov     rcx, rax; void *
0x18000402e  call    memset_0
0x180004033  mov     [rbx+2F0h], rsi
0x18000403a  test    rsi, rsi
0x18000403d  jnz     short loc_180004099
0x18000403f  lea     rdi, [rbx+2A0h]
0x180004046  mov     rcx, [rdi]; Block
0x180004049  cmp     rcx, rdi
0x18000404c  jz      short loc_180004066
0x18000404e  mov     rdx, [rcx+8]
0x180004052  mov     rax, [rcx]
0x180004055  mov     [rdx], rax
0x180004058  mov     [rax+8], rdx
0x18000405c  mov     rdx, r15
0x18000405f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004064  jmp     short loc_180004046
0x180004066  mov     rcx, [rdi+10h]; Block
0x18000406a  mov     qword ptr [rdi+18h], 0
0x180004072  test    rcx, rcx
0x180004075  jz      short loc_18000407F
0x180004077  mov     rdx, r15
0x18000407a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000407f  mov     rcx, rbx; Block
0x180004082  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004087  xor     ebx, ebx
0x180004089  mov     rax, rbx
0x18000408c  add     rsp, 28h
0x180004090  pop     r15
0x180004092  pop     r12
0x180004094  pop     rdi
0x180004095  pop     rsi
0x180004096  pop     rbp
0x180004097  pop     rbx
0x180004098  retn
0x180004099  mov     dword ptr [rbx+18h], 0
0x1800040a0  lea     rax, [rbx+338h]
0x1800040a7  mov     [rax+8], rax
0x1800040ab  mov     esi, 1
0x1800040b0  mov     [rax], rax
0x1800040b3  mov     [rbx+1Ch], edi
0x1800040b6  mov     [rbx+248h], r12d
0x1800040bd  test    edi, edi
0x1800040bf  jnz     short loc_180004108
0x1800040c1  xor     r9d, r9d; lpName
0x1800040c4  mov     r8d, esi; bInitialState
0x1800040c7  mov     edx, esi; bManualReset
0x1800040c9  xor     ecx, ecx; lpEventAttributes
0x1800040cb  call    cs:__imp_CreateEventW
0x1800040d1  mov     [rbx+268h], rax
0x1800040d8  test    rax, rax
0x1800040db  jnz     short loc_180004108
0x1800040dd  lea     rdi, [rbx+2A0h]
0x1800040e4  mov     rcx, [rdi]; Block
0x1800040e7  cmp     rcx, rdi
0x1800040ea  jz      loc_180004066
0x1800040f0  mov     rdx, [rcx+8]
0x1800040f4  mov     rax, [rcx]
0x1800040f7  mov     [rdx], rax
0x1800040fa  mov     [rax+8], rdx
0x1800040fe  mov     rdx, r15
0x180004101  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004106  jmp     short loc_1800040E4
0x180004108  mov     eax, esi
0x18000410a  lock xadd cs:?EtwpTracelogHandleNumber@@3KA, eax; ulong EtwpTracelogHandleNumber
0x180004112  add     eax, esi
0x180004114  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x18000411b  cdqe
0x18000411d  mov     [rbx+10h], rax
0x180004121  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004127  mov     rax, cs:off_18001D018
0x18000412e  lea     rcx, ?EtwpTraceHandleList@@3U_LIST_ENTRY@@A; _LIST_ENTRY EtwpTraceHandleList
0x180004135  cmp     [rax], rcx
0x180004138  jz      short loc_180004141
0x18000413a  mov     ecx, 3
0x18000413f  int     29h; Win8: RtlFailFast(ecx)
0x180004141  mov     [rbx], rcx
0x180004144  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x18000414b  mov     [rbx+8], rax
0x18000414f  mov     [rax], rbx
0x180004152  mov     cs:off_18001D018, rbx
0x180004159  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000415f  jmp     loc_180004089
```
