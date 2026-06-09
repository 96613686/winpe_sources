# SockDestroySocket

- ea: `0x180008250`
- end: `0x18000830e`
- name: `SockDestroySocket`
- size: `190`
- prototype: ``
- caller_count: `80`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002240`
- `0x180004700`
- `0x180005810`
- `0x180006d00`
- `0x180007080`
- `0x180008190`
- `0x180008320`
- `0x1800087c0`
- `0x180008870`
- `0x180008cb0`
- `0x180009d20`
- `0x18000a2a0`
- `0x18000a6b0`
- `0x18000c2b0`
- `0x18000d000`
- `0x18000de00`
- `0x18000f540`
- `0x18000faa0`
- `0x180010030`
- `0x180011e60`
- `0x180012600`
- `0x180013670`
- `0x180014030`
- `0x180014420`
- `0x180014c00`
- `0x180014e38`
- `0x180016b30`
- `0x1800172b0`
- `0x1800182d0`
- `0x180018ba0`
- `0x1800198a0`
- `0x18001d990`
- `0x1800216a8`
- `0x180021800`
- `0x180021b90`
- `0x1800248fc`
- `0x180025530`
- `0x180026800`
- `0x1800269e0`
- `0x180026d70`
- `0x180026eb8`
- `0x180027140`
- `0x180029144`
- `0x18003b344`
- `0x18003d540`
- `0x18003dbe4`
- `0x18003ec84`
- `0x18003f2e0`
- `0x180040d78`
- `0x180041b44`

## callees

- `0x180008250`
- `0x18000fa40`
- `0x18004d1d8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800082e5`
- `ntdll!RtlFreeHeap` at `0x1800082fd`
- `ntdll!RtlFreeHeap` at `0x1800082b1`
- `ntdll!RtlFreeHeap` at `0x1800082e5`
- `ntdll!RtlFreeHeap` at `0x1800082fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000828f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000828f`

## pseudocode

```c
BOOLEAN __fastcall SockDestroySocket(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  PVOID *v5; // rdi

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 152) + 16LL), 0xFFFFFFFF) == 1 )
    SockFreeHelperDll(*(_QWORD *)(a1 + 152), a2, a3);
  v4 = *(_QWORD *)(a1 + 264);
  if ( v4 && *(_QWORD *)(v4 + 8) == a1 )
    SockSanDestroySocket((char *)v4);
  v5 = *(PVOID **)(a1 + 16);
  if ( v5 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v5[4]);
    RtlFreeHeap(SockPrivateHeap, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
  return RtlFreeHeap(SockPrivateHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x180008250  mov     [rsp+arg_0], rbx
0x180008255  push    rdi
0x180008256  sub     rsp, 20h
0x18000825a  mov     rbx, rcx
0x18000825d  mov     eax, 0FFFFFFFFh
0x180008262  mov     rcx, [rcx+98h]
0x180008269  lock xadd [rcx+10h], eax
0x18000826e  cmp     eax, 1
0x180008271  jz      short loc_1800082BD
0x180008273  mov     rcx, [rbx+108h]; P
0x18000827a  test    rcx, rcx
0x18000827d  jnz     short loc_1800082CB
0x18000827f  mov     rdi, [rbx+10h]
0x180008283  test    rdi, rdi
0x180008286  jnz     short loc_1800082D8
0x180008288  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18000828f  call    cs:__imp_DeleteCriticalSection
0x180008296  nop     dword ptr [rax+rax+00h]
0x18000829b  mov     rcx, cs:SockPrivateHeap
0x1800082a2  mov     r8, rbx
0x1800082a5  xor     edx, edx
0x1800082a7  mov     rbx, [rsp+28h+arg_0]
0x1800082ac  add     rsp, 20h
0x1800082b0  pop     rdi
0x1800082b1  jmp     cs:__imp_RtlFreeHeap
0x1800082bd  mov     rcx, [rbx+98h]
0x1800082c4  call    SockFreeHelperDll
0x1800082c9  jmp     short loc_180008273
0x1800082cb  cmp     [rcx+8], rbx
0x1800082cf  jnz     short loc_18000827F
0x1800082d1  call    SockSanDestroySocket
0x1800082d6  jmp     short loc_18000827F
0x1800082d8  mov     r8, [rdi+20h]; P
0x1800082dc  xor     edx, edx; Flags
0x1800082de  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800082e5  call    cs:__imp_RtlFreeHeap
0x1800082ec  nop     dword ptr [rax+rax+00h]
0x1800082f1  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800082f8  mov     r8, rdi; P
0x1800082fb  xor     edx, edx; Flags
0x1800082fd  call    cs:__imp_RtlFreeHeap
0x180008304  nop     dword ptr [rax+rax+00h]
0x180008309  jmp     loc_180008288
```
