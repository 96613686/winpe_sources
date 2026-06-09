# CFreeList<CallStackContextNode,16>::Free(CallStackContextNode *)

- ea: `0x1800046e8`
- end: `0x18000474d`
- name: `?Free@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAXPEAVCallStackContextNode@@@Z`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024d0`
- `0x180004460`

## callees

- `0x180004438`
- `0x1800046e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004737`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004706`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004706`

## pseudocode

```c
void __fastcall CFreeList<CallStackContextNode,16>::Free(__int64 a1, CallStackContextNode *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r8
  void (*v6)(void *); // r9

  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( *(_DWORD *)(a1 + 64) >= *(_DWORD *)(a1 + 8) )
    {
      --*(_DWORD *)(a1 + 68);
      CallStackContextNode::`scalar deleting destructor'(a2, v4, v5, v6);
    }
    else
    {
      *((_QWORD *)a2 + 254) = *(_QWORD *)(a1 + 56);
      ++*(_DWORD *)(a1 + 64);
      *(_QWORD *)(a1 + 56) = a2;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x1800046e8  test    rdx, rdx
0x1800046eb  jz      short locret_18000474C
0x1800046ed  mov     [rsp+arg_0], rbx
0x1800046f2  mov     [rsp+arg_8], rsi
0x1800046f7  push    rdi
0x1800046f8  sub     rsp, 20h
0x1800046fc  mov     rbx, rcx
0x1800046ff  mov     rdi, rdx
0x180004702  add     rcx, 10h; lpCriticalSection
0x180004706  call    cs:__imp_EnterCriticalSection
0x18000470c  mov     eax, [rbx+8]
0x18000470f  cmp     [rbx+40h], eax
0x180004712  jge     short loc_180004728
0x180004714  mov     rax, [rbx+38h]
0x180004718  mov     [rdi+7F0h], rax
0x18000471f  inc     dword ptr [rbx+40h]
0x180004722  mov     [rbx+38h], rdi
0x180004726  jmp     short loc_180004733
0x180004728  dec     dword ptr [rbx+44h]
0x18000472b  mov     rcx, rdi; this
0x18000472e  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x180004733  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004737  call    cs:__imp_LeaveCriticalSection
0x18000473d  mov     rbx, [rsp+28h+arg_0]
0x180004742  mov     rsi, [rsp+28h+arg_8]
0x180004747  add     rsp, 20h
0x18000474b  pop     rdi
0x18000474c  retn
```
