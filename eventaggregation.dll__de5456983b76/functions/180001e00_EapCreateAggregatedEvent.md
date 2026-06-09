# EapCreateAggregatedEvent

- ea: `0x180001e00`
- end: `0x180001ff4`
- name: `EapCreateAggregatedEvent`
- size: `500`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d50`

## callees

- `0x180001e00`
- `0x180002000`
- `0x1800022b0`
- `0x180003630`
- `0x1800085c4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001e68`
- `ntdll!RtlAllocateHeap` at `0x180001ed6`
- `ntdll!RtlAllocateHeap` at `0x180001e68`
- `ntdll!RtlAllocateHeap` at `0x180001ed6`

## pseudocode

```c
__int64 __fastcall EapCreateAggregatedEvent(__int64 a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  _OWORD *v8; // rax
  int BrokeredEvent; // r14d
  __int64 v11; // rax
  __int64 v12[2]; // [rsp+50h] [rbp-28h] BYREF
  __int128 v13; // [rsp+60h] [rbp-18h]

  *(_OWORD *)v12 = 0;
  v13 = 0;
  if ( !a1 || !a3 || !*(_QWORD *)a1 && !*(_QWORD *)(a1 + 8) )
    return 3221225485LL;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
  v7 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *(_OWORD *)Heap = 0;
  *((_OWORD *)Heap + 1) = 0;
  *((_OWORD *)Heap + 2) = 0;
  Heap[6] = 0;
  Heap[5] = *(_QWORD *)(a1 + 40);
  Heap[6] = *(_QWORD *)(a1 + 48);
  Heap[2] = *(_QWORD *)(a1 + 16);
  Heap[3] = *(_QWORD *)(a1 + 24);
  *((_DWORD *)Heap + 8) = *(_DWORD *)(a1 + 32);
  if ( *(_QWORD *)a1 )
  {
    v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
    *v7 = v8;
    if ( !v8 )
      goto LABEL_12;
    *v8 = 0;
    v8[1] = 0;
    *((_QWORD *)v8 + 4) = 0;
    BrokeredEvent = BriCreateBrokeredEventEx(*(void **)a1, a2, 0, *v7 + 8LL, (__int64)v12, 0);
    if ( BrokeredEvent < 0 )
      goto LABEL_13;
    *(_DWORD *)(*v7 + 16LL) = v12[0];
    *(_DWORD *)(*v7 + 20LL) = v12[1];
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    v11 = EaLibAllocate(56);
    v7[1] = v11;
    if ( v11 )
    {
      *(_OWORD *)v11 = 0;
      *(_OWORD *)(v11 + 16) = 0;
      *(_OWORD *)(v11 + 32) = 0;
      *(_QWORD *)(v11 + 48) = 0;
      BrokeredEvent = EapCreateAggregatedEventCondition(a1, a2, v7[1]);
      if ( BrokeredEvent >= 0 )
        goto LABEL_10;
LABEL_13:
      EapDeleteAggregatedEvent(v7);
      return (unsigned int)BrokeredEvent;
    }
LABEL_12:
    BrokeredEvent = -1073741801;
    goto LABEL_13;
  }
LABEL_10:
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x180001e00  mov     [rsp+arg_10], rbp
0x180001e05  mov     [rsp+arg_18], rsi
0x180001e0a  push    rdi
0x180001e0b  sub     rsp, 70h
0x180001e0f  xorps   xmm0, xmm0
0x180001e12  mov     rsi, r8
0x180001e15  mov     ebp, edx
0x180001e17  mov     rdi, rcx
0x180001e1a  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x180001e1f  movups  [rsp+78h+var_18], xmm0
0x180001e24  test    rcx, rcx
0x180001e27  jz      loc_180001FAB
0x180001e2d  test    r8, r8
0x180001e30  jz      loc_180001FAB
0x180001e36  cmp     qword ptr [rcx], 0
0x180001e3a  jz      loc_180001FA0
0x180001e40  mov     rcx, gs:60h
0x180001e49  mov     edx, 8; Flags
0x180001e4e  mov     [rsp+78h+arg_0], rbx
0x180001e56  mov     r8d, 38h ; '8'; Size
0x180001e5c  mov     [rsp+78h+arg_8], r14
0x180001e64  mov     rcx, [rcx+30h]; HeapHandle
0x180001e68  call    cs:__imp_RtlAllocateHeap
0x180001e6e  mov     rbx, rax
0x180001e71  test    rax, rax
0x180001e74  jz      loc_180001F99
0x180001e7a  xor     eax, eax
0x180001e7c  xorps   xmm0, xmm0
0x180001e7f  movups  xmmword ptr [rbx], xmm0
0x180001e82  movups  xmmword ptr [rbx+10h], xmm0
0x180001e86  movups  xmmword ptr [rbx+20h], xmm0
0x180001e8a  mov     [rbx+30h], rax
0x180001e8e  mov     rax, [rdi+28h]
0x180001e92  mov     [rbx+28h], rax
0x180001e96  mov     rax, [rdi+30h]
0x180001e9a  mov     [rbx+30h], rax
0x180001e9e  mov     rax, [rdi+10h]
0x180001ea2  mov     [rbx+10h], rax
0x180001ea6  mov     rax, [rdi+18h]
0x180001eaa  mov     [rbx+18h], rax
0x180001eae  mov     eax, [rdi+20h]
0x180001eb1  mov     [rbx+20h], eax
0x180001eb4  cmp     qword ptr [rdi], 0
0x180001eb8  jz      loc_180001F53
0x180001ebe  mov     rcx, gs:60h
0x180001ec7  mov     edx, 8; Flags
0x180001ecc  mov     r8d, 28h ; '('; Size
0x180001ed2  mov     rcx, [rcx+30h]; HeapHandle
0x180001ed6  call    cs:__imp_RtlAllocateHeap
0x180001edc  mov     [rbx], rax
0x180001edf  test    rax, rax
0x180001ee2  jz      loc_180001F81
0x180001ee8  mov     [rsp+78h+var_38], 0; __int64
0x180001ef1  lea     rdx, [rsp+78h+var_28]
0x180001ef6  mov     [rsp+78h+var_40], rdx; __int64
0x180001efb  xorps   xmm0, xmm0
0x180001efe  movups  xmmword ptr [rax], xmm0
0x180001f01  xor     ecx, ecx
0x180001f03  movups  xmmword ptr [rax+10h], xmm0
0x180001f07  mov     [rax+20h], rcx
0x180001f0b  mov     rcx, [rdi]; Source1
0x180001f0e  mov     rax, [rbx]
0x180001f11  mov     r8, [rdi+40h]
0x180001f15  add     rax, 8
0x180001f19  mov     rdx, [rdi+38h]
0x180001f1d  mov     [rsp+78h+var_48], rax; __int64
0x180001f22  lea     r9, [rcx+10h]
0x180001f26  mov     [rsp+78h+var_50], 0; __int64
0x180001f2f  mov     [rsp+78h+var_58], ebp; int
0x180001f33  call    BriCreateBrokeredEventEx
0x180001f38  mov     r14d, eax
0x180001f3b  test    eax, eax
0x180001f3d  js      short loc_180001F87
0x180001f3f  mov     rdx, [rbx]
0x180001f42  mov     eax, dword ptr [rsp+78h+var_28]
0x180001f46  mov     [rdx+10h], eax
0x180001f49  mov     rdx, [rbx]
0x180001f4c  mov     eax, dword ptr [rsp+78h+var_28+8]
0x180001f50  mov     [rdx+14h], eax
0x180001f53  cmp     qword ptr [rdi+8], 0
0x180001f58  jnz     short loc_180001FB2
0x180001f5a  mov     [rsi], rbx
0x180001f5d  xor     eax, eax
0x180001f5f  mov     rbx, [rsp+78h+arg_0]
0x180001f67  mov     r14, [rsp+78h+arg_8]
0x180001f6f  lea     r11, [rsp+78h+var_8]
0x180001f74  mov     rbp, [r11+20h]
0x180001f78  mov     rsi, [r11+28h]
0x180001f7c  mov     rsp, r11
0x180001f7f  pop     rdi
0x180001f80  retn
0x180001f81  mov     r14d, 0C0000017h
0x180001f87  and     ebp, 1
0x180001f8a  mov     rcx, rbx; P
0x180001f8d  mov     edx, ebp
0x180001f8f  call    EapDeleteAggregatedEvent
0x180001f94  mov     eax, r14d
0x180001f97  jmp     short loc_180001F5F
0x180001f99  mov     eax, 0C0000017h
0x180001f9e  jmp     short loc_180001F5F
0x180001fa0  cmp     qword ptr [rcx+8], 0
0x180001fa5  jnz     loc_180001E40
0x180001fab  mov     eax, 0C000000Dh
0x180001fb0  jmp     short loc_180001F6F
0x180001fb2  mov     ecx, 38h ; '8'
0x180001fb7  call    EaLibAllocate
0x180001fbc  mov     [rbx+8], rax
0x180001fc0  test    rax, rax
0x180001fc3  jz      short loc_180001F81
0x180001fc5  xorps   xmm0, xmm0
0x180001fc8  xor     ecx, ecx
0x180001fca  movups  xmmword ptr [rax], xmm0
0x180001fcd  mov     edx, ebp
0x180001fcf  movups  xmmword ptr [rax+10h], xmm0
0x180001fd3  movups  xmmword ptr [rax+20h], xmm0
0x180001fd7  mov     [rax+30h], rcx
0x180001fdb  mov     rcx, rdi
0x180001fde  mov     r8, [rbx+8]
0x180001fe2  call    EapCreateAggregatedEventCondition
0x180001fe7  mov     r14d, eax
0x180001fea  test    eax, eax
0x180001fec  jns     loc_180001F5A
0x180001ff2  jmp     short loc_180001F87
```
