# FCGI_BUFFER::Alloc(ulong)

- ea: `0x180008f90`
- end: `0x18000911f`
- name: `?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z`
- size: `399`
- prototype: `struct FCGI_BUFFER *__fastcall(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031c0`
- `0x1800035f8`
- `0x1800036b8`
- `0x180003c08`
- `0x180006a0c`
- `0x18000b3ac`

## callees

- `0x180008f50`
- `0x180008f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009106`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009038`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009083`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009038`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009083`

## pseudocode

```c
struct FCGI_BUFFER *__fastcall FCGI_BUFFER::Alloc(int a1)
{
  unsigned int v1; // edi
  FCGI_BUFFER *v2; // rbx
  unsigned int v3; // esi
  int *v4; // rdx
  int v5; // r8d
  struct _LIST_ENTRY near **v6; // rcx
  struct _LIST_ENTRY near *v7; // rbx
  struct _LIST_ENTRY *Flink; // rax
  FCGI_BUFFER *v9; // rax
  bool v10; // zf
  char *v11; // rax

  v1 = a1 + 8;
  v2 = 0;
  v3 = (unsigned int)(a1 + 1031) >> 10;
  EnterCriticalSection(&FCGI_BUFFER::sm_csLock);
  if ( v3 >= 0x46 )
    goto LABEL_13;
  ++FCGI_BUFFER::sm_cTotalAllocEntries;
  v4 = (int *)&FCGI_BUFFER::sm_cFreeEntries + v3;
  v5 = *v4;
  if ( !*v4 )
  {
    v9 = (FCGI_BUFFER *)HeapAlloc(FCGI_BUFFER::sm_hHeap, 1u, 0x30u);
    v2 = v9;
    if ( v9 )
    {
      v10 = FCGI_BUFFER::sm_fPageheap == 0;
      *(_QWORD *)v9 = 0;
      *((_DWORD *)v9 + 2) = 0;
      *((_QWORD *)v9 + 2) = 0;
      *((_DWORD *)v9 + 6) = 0;
      if ( v10 )
        v1 = v3 << 10;
      *((_DWORD *)v9 + 2) = v1;
      v11 = (char *)HeapAlloc(FCGI_BUFFER::sm_hHeap, 1u, v1);
      *(_QWORD *)v2 = v11;
      if ( v11 )
      {
        *((_DWORD *)v2 + 2) -= 8;
        *(_QWORD *)v2 = v11 + 8;
        goto LABEL_13;
      }
      FCGI_BUFFER::~FCGI_BUFFER(v2);
      HeapFree(FCGI_BUFFER::sm_hHeap, 1u, v2);
    }
    v2 = 0;
    goto LABEL_13;
  }
  v6 = &(&FCGI_BUFFER::sm_FreeList)[2 * v3];
  v7 = *v6;
  if ( (struct _LIST_ENTRY near **)(*v6)->Blink != v6 || (Flink = v7->Flink, v7->Flink->Blink != v7) )
    __fastfail(3u);
  --FCGI_BUFFER::sm_cTotalFreeEntries;
  *v6 = Flink;
  v2 = (FCGI_BUFFER *)&v7[-2];
  Flink->Blink = (struct _LIST_ENTRY *)v6;
  *v4 = v5 - 1;
LABEL_13:
  LeaveCriticalSection(&FCGI_BUFFER::sm_csLock);
  if ( v2 )
  {
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 5) = (char *)v2 + 32;
    *((_QWORD *)v2 + 4) = (char *)v2 + 32;
    *((_QWORD *)v2 + 3) = 0;
  }
  else
  {
    EnterCriticalSection(&FCGI_BUFFER::sm_csLock);
    --FCGI_BUFFER::sm_cTotalAllocEntries;
    LeaveCriticalSection(&FCGI_BUFFER::sm_csLock);
  }
  return v2;
}

```

## disassembly

```asm
0x180008f90  mov     [rsp+arg_0], rbx
0x180008f95  mov     [rsp+arg_8], rsi
0x180008f9a  push    rdi
0x180008f9b  sub     rsp, 20h
0x180008f9f  lea     edi, [rcx+8]
0x180008fa2  xor     ebx, ebx
0x180008fa4  lea     esi, [rdi+3FFh]
0x180008faa  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008fb1  shr     esi, 0Ah
0x180008fb4  call    cs:__imp_EnterCriticalSection
0x180008fba  cmp     esi, 46h ; 'F'
0x180008fbd  jnb     loc_1800090B0
0x180008fc3  inc     cs:?sm_cTotalAllocEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalAllocEntries
0x180008fc9  lea     rcx, __ImageBase
0x180008fd0  lea     rdx, rva ?sm_cFreeEntries@FCGI_BUFFER@@0PAKA[rcx]; ulong near * FCGI_BUFFER::sm_cFreeEntries ...
0x180008fd7  mov     eax, esi
0x180008fd9  lea     rdx, [rdx+rsi*4]
0x180008fdd  mov     r8d, [rdx]
0x180008fe0  test    r8d, r8d
0x180008fe3  jz      short loc_180009028
0x180008fe5  shl     rax, 4
0x180008fe9  lea     rcx, rva ?sm_FreeList@FCGI_BUFFER@@0PAU_LIST_ENTRY@@A[rcx]; _LIST_ENTRY near * FCGI_BUFFER::sm_FreeList ...
0x180008ff0  add     rcx, rax
0x180008ff3  mov     rbx, [rcx]
0x180008ff6  cmp     [rbx+8], rcx
0x180008ffa  jnz     short loc_180009021
0x180008ffc  mov     rax, [rbx]
0x180008fff  cmp     [rax+8], rbx
0x180009003  jnz     short loc_180009021
0x180009005  dec     cs:?sm_cTotalFreeEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalFreeEntries
0x18000900b  mov     [rcx], rax
0x18000900e  add     rbx, 0FFFFFFFFFFFFFFE0h
0x180009012  mov     [rax+8], rcx
0x180009016  lea     eax, [r8-1]
0x18000901a  mov     [rdx], eax
0x18000901c  jmp     loc_1800090B0
0x180009021  mov     ecx, 3
0x180009026  int     29h; Win8: RtlFailFast(ecx)
0x180009028  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x18000902f  mov     edx, 1; dwFlags
0x180009034  lea     r8d, [rdx+2Fh]; dwBytes
0x180009038  call    cs:__imp_HeapAlloc
0x18000903e  mov     rbx, rax
0x180009041  test    rax, rax
0x180009044  jz      short loc_1800090AE
0x180009046  cmp     cs:?sm_fPageheap@FCGI_BUFFER@@0HA, 0; int FCGI_BUFFER::sm_fPageheap
0x18000904d  mov     qword ptr [rax], 0
0x180009054  mov     dword ptr [rax+8], 0
0x18000905b  mov     qword ptr [rax+10h], 0
0x180009063  mov     dword ptr [rax+18h], 0
0x18000906a  jnz     short loc_180009071
0x18000906c  mov     edi, esi
0x18000906e  shl     edi, 0Ah
0x180009071  mov     [rax+8], edi
0x180009074  mov     edx, 1; dwFlags
0x180009079  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x180009080  mov     r8d, edi; dwBytes
0x180009083  call    cs:__imp_HeapAlloc
0x180009089  mov     [rbx], rax
0x18000908c  test    rax, rax
0x18000908f  jnz     short loc_1800090DF
0x180009091  mov     rcx, rbx; this
0x180009094  call    ??1FCGI_BUFFER@@AEAA@XZ; FCGI_BUFFER::~FCGI_BUFFER(void)
0x180009099  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x1800090a0  mov     r8, rbx; lpMem
0x1800090a3  mov     edx, 1; dwFlags
0x1800090a8  call    cs:__imp_HeapFree
0x1800090ae  xor     ebx, ebx
0x1800090b0  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800090b7  call    cs:__imp_LeaveCriticalSection
0x1800090bd  test    rbx, rbx
0x1800090c0  jz      short loc_1800090EC
0x1800090c2  lea     rax, [rbx+20h]
0x1800090c6  mov     qword ptr [rbx+10h], 0
0x1800090ce  mov     [rax+8], rax
0x1800090d2  mov     [rax], rax
0x1800090d5  mov     qword ptr [rbx+18h], 0
0x1800090dd  jmp     short loc_18000910C
0x1800090df  add     dword ptr [rbx+8], 0FFFFFFF8h
0x1800090e3  add     rax, 8
0x1800090e7  mov     [rbx], rax
0x1800090ea  jmp     short loc_1800090B0
0x1800090ec  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800090f3  call    cs:__imp_EnterCriticalSection
0x1800090f9  dec     cs:?sm_cTotalAllocEntries@FCGI_BUFFER@@0KA; ulong FCGI_BUFFER::sm_cTotalAllocEntries
0x1800090ff  lea     rcx, ?sm_csLock@FCGI_BUFFER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009106  call    cs:__imp_LeaveCriticalSection
0x18000910c  mov     rsi, [rsp+28h+arg_8]
0x180009111  mov     rax, rbx
0x180009114  mov     rbx, [rsp+28h+arg_0]
0x180009119  add     rsp, 20h
0x18000911d  pop     rdi
0x18000911e  retn
```
