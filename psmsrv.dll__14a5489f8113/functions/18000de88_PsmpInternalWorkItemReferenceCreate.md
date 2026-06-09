# PsmpInternalWorkItemReferenceCreate

- ea: `0x18000de88`
- end: `0x18000def6`
- name: `PsmpInternalWorkItemReferenceCreate`
- size: `110`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c7b0`

## callees

- `0x18000de88`
- `0x18000defc`
- `0x18000e2cc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000deb2`
- `ntdll!RtlAllocateHeap` at `0x18000deb2`

## pseudocode

```c
__int64 __fastcall PsmpInternalWorkItemReferenceCreate(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  _QWORD *Heap; // rbx
  __int64 result; // rax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
  if ( !Heap )
    return 3221225495LL;
  PsmpReferenceApplication(a1);
  if ( a2 )
    PsmpReferenceHostContext(a2);
  *Heap = a1;
  result = 0;
  Heap[1] = a2;
  *((_DWORD *)Heap + 4) = a3;
  *a4 = Heap;
  return result;
}

```

## disassembly

```asm
0x18000de88  push    rbx
0x18000de8a  push    rbp
0x18000de8b  push    rsi
0x18000de8c  push    rdi
0x18000de8d  push    r14
0x18000de8f  sub     rsp, 20h
0x18000de93  mov     rsi, rcx
0x18000de96  mov     rdi, rdx
0x18000de99  mov     rcx, gs:60h
0x18000dea2  xor     edx, edx; Flags
0x18000dea4  mov     ebp, r8d
0x18000dea7  mov     r14, r9
0x18000deaa  mov     rcx, [rcx+30h]; HeapHandle
0x18000deae  lea     r8d, [rdx+18h]; Size
0x18000deb2  call    cs:__imp_RtlAllocateHeap
0x18000deb8  mov     rbx, rax
0x18000debb  test    rax, rax
0x18000debe  jz      short loc_18000DEEF
0x18000dec0  mov     rcx, rsi
0x18000dec3  call    PsmpReferenceApplication
0x18000dec8  test    rdi, rdi
0x18000decb  jz      short loc_18000DED5
0x18000decd  mov     rcx, rdi
0x18000ded0  call    PsmpReferenceHostContext
0x18000ded5  mov     [rbx], rsi
0x18000ded8  xor     eax, eax
0x18000deda  mov     [rbx+8], rdi
0x18000dede  mov     [rbx+10h], ebp
0x18000dee1  mov     [r14], rbx
0x18000dee4  add     rsp, 20h
0x18000dee8  pop     r14
0x18000deea  pop     rdi
0x18000deeb  pop     rsi
0x18000deec  pop     rbp
0x18000deed  pop     rbx
0x18000deee  retn
0x18000deef  mov     eax, 0C0000017h
0x18000def4  jmp     short loc_18000DEE4
```
