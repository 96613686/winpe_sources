# CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)

- ea: `0x180002470`
- end: `0x1800024c8`
- name: `??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002420`
- `0x180004400`

## callees

- `0x180002470`
- `0x180004438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800024c1`

## pseudocode

```c
void __fastcall CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(__int64 a1, unsigned int a2)
{
  CallStackContextNode *v3; // rcx
  CallStackContextNode *v4; // rdi

  *(_QWORD *)a1 = &CFreeList<CallStackContextNode,16>::`vftable';
  v3 = *(CallStackContextNode **)(a1 + 56);
  if ( v3 )
  {
    do
    {
      v4 = (CallStackContextNode *)*((_QWORD *)v3 + 254);
      --*(_DWORD *)(a1 + 68);
      CallStackContextNode::`scalar deleting destructor'(v3, a2);
      *(_QWORD *)(a1 + 56) = v4;
      v3 = v4;
    }
    while ( v4 );
  }
  *(_DWORD *)(a1 + 64) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
}

```

## disassembly

```asm
0x180002470  push    rbx
0x180002472  sub     rsp, 20h
0x180002476  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x18000247d  mov     rbx, rcx
0x180002480  mov     [rcx], rax
0x180002483  mov     rcx, [rcx+38h]; this
0x180002487  test    rcx, rcx
0x18000248a  jz      short loc_1800024B1
0x18000248c  mov     [rsp+28h+arg_0], rdi
0x180002491  mov     rdi, [rcx+7F0h]
0x180002498  dec     dword ptr [rbx+44h]
0x18000249b  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x1800024a0  mov     [rbx+38h], rdi
0x1800024a4  mov     rcx, rdi
0x1800024a7  test    rdi, rdi
0x1800024aa  jnz     short loc_180002491
0x1800024ac  mov     rdi, [rsp+28h+arg_0]
0x1800024b1  lea     rcx, [rbx+10h]
0x1800024b5  mov     dword ptr [rbx+40h], 0
0x1800024bc  add     rsp, 20h
0x1800024c0  pop     rbx
0x1800024c1  jmp     cs:__imp_DeleteCriticalSection
```
