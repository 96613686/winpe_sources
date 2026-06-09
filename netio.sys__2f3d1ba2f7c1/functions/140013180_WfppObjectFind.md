# WfppObjectFind

- ea: `0x140013180`
- end: `0x1400132ed`
- name: `WfppObjectFind`
- size: `365`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011d90`
- `0x140011e80`
- `0x140012040`
- `0x14003e960`
- `0x140041240`
- `0x140042bb0`
- `0x14004b200`

## callees

- `0x140013180`
- `0x140014b90`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400132c7`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400132c7`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400132dc`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400132dc`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140013226`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140013226`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001326b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001326b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013292`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013292`

## pseudocode

```c
struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *__fastcall WfppObjectFind(struct _LIST_ENTRY *a1, int a2, __int64 a3, char a4)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v4; // rbx
  ULONG_PTR v5; // rdi
  __int64 v8; // rdx
  __int64 v10; // rcx
  __int64 i; // rdx
  __int64 v12; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *j; // rax
  _DWORD *v14; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+88h] [rbp+38h]
  struct _LIST_ENTRY *v19; // [rsp+90h] [rbp+40h]

  v18 = a2;
  v19 = a1;
  v4 = 0;
  v5 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v8 = 0;
  memset(&Context, 0, sizeof(Context));
  do
  {
    v10 = *((unsigned __int8 *)&v19 + v8++);
    v5 = v10 + 37 * v5;
  }
  while ( v8 != 8 );
  for ( i = 0; i != 4; ++i )
  {
    v12 = *((unsigned __int8 *)&v18 + i);
    v5 = v12 + 37 * v5;
  }
  if ( HIBYTE(word_14009ABB0) )
    WfpAcquireSpinLock(&qword_14009ABE0, &LockHandle);
  if ( !v5 )
    v5 = -1;
  for ( j = RtlLookupEntryHashTable(&HashTable, v5, &Context); j; j = RtlGetNextEntryHashTable(&HashTable, &Context) )
  {
    v4 = j - 1;
    if ( LODWORD(j[-1].Linkage.Flink) == a2 && v4->Linkage.Blink == a1 )
    {
      if ( a4 )
        RtlRemoveEntryHashTable(&HashTable, j, 0);
      else
        _InterlockedIncrement((volatile signed __int32 *)&v4->Linkage.Flink + 1);
      break;
    }
  }
  if ( HIBYTE(word_14009ABB0) )
  {
    if ( gWfpPerProContext )
    {
      v14 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v14 == 4 )
        *v14 = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x140013180  mov     [rsp-28h+arg_0], rbx
0x140013185  mov     [rsp-28h+arg_10], r8
0x14001318a  mov     [rsp-28h+arg_8], edx
0x14001318e  push    rbp
0x14001318f  push    rsi
0x140013190  push    rdi
0x140013191  push    r14
0x140013193  push    r15
0x140013195  mov     rbp, rsp
0x140013198  sub     rsp, 50h
0x14001319c  xor     eax, eax
0x14001319e  mov     [rbp+arg_10], rcx
0x1400131a2  xor     ebx, ebx
0x1400131a4  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400131a8  xor     edi, edi
0x1400131aa  mov     [rbp+Context.Signature], rax
0x1400131ae  xorps   xmm0, xmm0
0x1400131b1  xorps   xmm1, xmm1
0x1400131b4  mov     esi, edx
0x1400131b6  mov     r15b, r9b
0x1400131b9  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400131bd  xor     edx, edx
0x1400131bf  mov     r14, rcx
0x1400131c2  movups  xmmword ptr [rbp+Context.ChainHead], xmm1
0x1400131c6  movzx   ecx, byte ptr [rbp+rdx+arg_10]
0x1400131cb  inc     rdx
0x1400131ce  imul    rdi, 25h ; '%'
0x1400131d2  add     rdi, rcx
0x1400131d5  cmp     rdx, 8
0x1400131d9  jnz     short loc_1400131C6
0x1400131db  xor     edx, edx
0x1400131dd  movzx   ecx, byte ptr [rbp+rdx+arg_8]
0x1400131e2  inc     rdx
0x1400131e5  imul    rdi, 25h ; '%'
0x1400131e9  add     rdi, rcx
0x1400131ec  cmp     rdx, 4
0x1400131f0  jnz     short loc_1400131DD
0x1400131f2  cmp     byte ptr cs:word_14009ABB0+1, al
0x1400131f8  jz      short loc_14001320A
0x1400131fa  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400131fe  lea     rcx, qword_14009ABE0; SpinLock
0x140013205  call    WfpAcquireSpinLock
0x14001320a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001320e  lea     r8, [rbp+Context]; Context
0x140013212  test    rdi, rdi
0x140013215  cmovz   rdi, rax
0x140013219  mov     rdx, rdi; Signature
0x14001321c  lea     rdi, HashTable
0x140013223  mov     rcx, rdi; HashTable
0x140013226  call    cs:__imp_RtlLookupEntryHashTable
0x14001322d  nop     dword ptr [rax+rax+00h]
0x140013232  test    rax, rax
0x140013235  jz      short loc_140013256
0x140013237  lea     rbx, [rax-18h]
0x14001323b  cmp     [rbx], esi
0x14001323d  jnz     loc_1400132D5
0x140013243  cmp     [rbx+8], r14
0x140013247  jnz     loc_1400132D5
0x14001324d  test    r15b, r15b
0x140013250  jnz     short loc_1400132BE
0x140013252  lock inc dword ptr [rbx+4]
0x140013256  cmp     byte ptr cs:word_14009ABB0+1, 0
0x14001325d  jz      short loc_14001329E
0x14001325f  cmp     cs:gWfpPerProContext, 0
0x140013267  jz      short loc_14001328E
0x140013269  xor     ecx, ecx; ProcNumber
0x14001326b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013272  nop     dword ptr [rax+rax+00h]
0x140013277  imul    eax, cs:gWfpPerProContextSize
0x14001327e  mov     rcx, cs:gWfpPerProContext
0x140013285  mov     rax, [rax+rcx]
0x140013289  cmp     dword ptr [rax], 4
0x14001328c  jz      short loc_1400132B6
0x14001328e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140013292  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013299  nop     dword ptr [rax+rax+00h]
0x14001329e  mov     rax, rbx
0x1400132a1  mov     rbx, [rsp+50h+arg_0]
0x1400132a9  add     rsp, 50h
0x1400132ad  pop     r15
0x1400132af  pop     r14
0x1400132b1  pop     rdi
0x1400132b2  pop     rsi
0x1400132b3  pop     rbp
0x1400132b4  retn
0x1400132b6  mov     dword ptr [rax], 0
0x1400132bc  jmp     short loc_14001328E
0x1400132be  xor     r8d, r8d; Context
0x1400132c1  mov     rdx, rax; Entry
0x1400132c4  mov     rcx, rdi; HashTable
0x1400132c7  call    cs:__imp_RtlRemoveEntryHashTable
0x1400132ce  nop     dword ptr [rax+rax+00h]
0x1400132d3  jmp     short loc_140013256
0x1400132d5  lea     rdx, [rbp+Context]; Context
0x1400132d9  mov     rcx, rdi; HashTable
0x1400132dc  call    cs:__imp_RtlGetNextEntryHashTable
0x1400132e3  nop     dword ptr [rax+rax+00h]
0x1400132e8  jmp     loc_140013232
```
