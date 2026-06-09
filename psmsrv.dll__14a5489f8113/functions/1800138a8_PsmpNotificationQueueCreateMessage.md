# PsmpNotificationQueueCreateMessage

- ea: `0x1800138a8`
- end: `0x180013959`
- name: `PsmpNotificationQueueCreateMessage`
- size: `177`
- prototype: `__int64 __fastcall(int, int, void *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b4d8`
- `0x1800114d0`

## callees

- `0x1800138a8`
- `0x18001c10c`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180013913`
- `ntdll!RtlCopySid` at `0x180013913`
- `ntdll!RtlAllocateHeap` at `0x1800138e9`
- `ntdll!RtlAllocateHeap` at `0x1800138e9`

## pseudocode

```c
__int64 __fastcall PsmpNotificationQueueCreateMessage(int a1, int a2, void *a3, _WORD *a4, _QWORD *a5)
{
  __int64 v5; // rbx
  _DWORD *Heap; // rax
  _DWORD *v11; // rdi

  v5 = -1;
  do
    ++v5;
  while ( a4[v5] );
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x238u);
  v11 = Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, 0x238u);
  RtlCopySid(0x44u, v11 + 6, a3);
  memcpy_0(v11 + 23, a4, (unsigned int)(2 * v5 + 2));
  v11[5] = a2;
  v11[4] = a1;
  *a5 = v11;
  return 0;
}

```

## disassembly

```asm
0x1800138a8  push    rbx
0x1800138aa  push    rbp
0x1800138ab  push    rsi
0x1800138ac  push    rdi
0x1800138ad  push    r12
0x1800138af  push    r14
0x1800138b1  push    r15
0x1800138b3  sub     rsp, 20h
0x1800138b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800138bb  mov     rsi, r9
0x1800138be  xor     r12d, r12d
0x1800138c1  mov     rbp, r8
0x1800138c4  mov     r14d, edx
0x1800138c7  mov     r15d, ecx
0x1800138ca  inc     rbx
0x1800138cd  cmp     [r9+rbx*2], r12w
0x1800138d2  jnz     short loc_1800138CA
0x1800138d4  mov     rcx, gs:60h
0x1800138dd  xor     edx, edx; Flags
0x1800138df  mov     r8d, 238h; Size
0x1800138e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800138e9  call    cs:__imp_RtlAllocateHeap
0x1800138ef  mov     rdi, rax
0x1800138f2  test    rax, rax
0x1800138f5  jz      short loc_180013952
0x1800138f7  xor     edx, edx; Val
0x1800138f9  mov     r8d, 238h; Size
0x1800138ff  mov     rcx, rax; void *
0x180013902  call    memset_0
0x180013907  lea     rdx, [rdi+18h]; DestinationSid
0x18001390b  mov     r8, rbp; SourceSid
0x18001390e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180013913  call    cs:__imp_RtlCopySid
0x180013919  lea     r8d, ds:2[rbx*2]; Size
0x180013921  mov     rdx, rsi; Src
0x180013924  lea     rcx, [rdi+5Ch]; void *
0x180013928  call    memcpy_0
0x18001392d  mov     rax, [rsp+58h+arg_20]
0x180013935  mov     [rdi+14h], r14d
0x180013939  mov     [rdi+10h], r15d
0x18001393d  mov     [rax], rdi
0x180013940  mov     eax, r12d
0x180013943  add     rsp, 20h
0x180013947  pop     r15
0x180013949  pop     r14
0x18001394b  pop     r12
0x18001394d  pop     rdi
0x18001394e  pop     rsi
0x18001394f  pop     rbp
0x180013950  pop     rbx
0x180013951  retn
0x180013952  mov     eax, 0C0000017h
0x180013957  jmp     short loc_180013943
```
