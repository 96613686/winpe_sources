# BiTranslateFilePath

- ea: `0x180037e68`
- end: `0x180037fbc`
- name: `BiTranslateFilePath`
- size: `340`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180035f38`
- `0x180036540`
- `0x180037358`

## callees

- `0x180034254`
- `0x180034db0`
- `0x1800350ac`
- `0x1800352f8`
- `0x180037e68`
- `0x180049010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180037f9a`
- `ntdll!RtlFreeHeap` at `0x180037f9a`
- `ntdll!RtlAllocateHeap` at `0x180037f16`
- `ntdll!RtlAllocateHeap` at `0x180037f16`

## string_xrefs

- `0x180037f6f`: `BiTranslateFilePath failed. File type: %lu. Status: %x`
- `0x180037e9b`: `ZwTranslateFilePath`

## pseudocode

```c
__int64 __fastcall BiTranslateFilePath(__int64 a1, unsigned int a2, _QWORD *a3)
{
  void *v6; // rdi
  NTSTATUS v7; // ebx
  int v8; // eax
  PVOID Heap; // rax
  __int64 (__fastcall *v11)(__int64, _QWORD, PVOID, SIZE_T *); // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12[8]; // [rsp+38h] [rbp-20h] BYREF
  SIZE_T Size; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  v11 = 0;
  *(_QWORD *)v12 = 0;
  v6 = 0;
  if ( (int)BiLookupNtdllProcedureAddress("ZwTranslateFilePath", (PVOID *)&v11) < 0 )
  {
    v7 = -1073741637;
LABEL_14:
    BiLogMessage(
      4,
      L"BiTranslateFilePath failed. File type: %lu. Status: %x",
      *(unsigned int *)(a1 + 8),
      (unsigned int)v7);
    goto LABEL_15;
  }
  v7 = BiAcquirePrivilege(0x16u, (__int64)v12);
  if ( v7 >= 0 )
  {
    LODWORD(Size) = 0;
    v8 = v11(a1, a2, 0, &Size);
    v7 = v8;
    if ( v8 == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      v6 = Heap;
      v7 = Heap ? v11(a1, a2, Heap, &Size) : -1073741670;
    }
    else if ( v8 >= 0 )
    {
      v7 = -1073741811;
    }
    BiReleasePrivilege(v12);
    if ( v7 >= 0 )
    {
      *a3 = v6;
      return (unsigned int)v7;
    }
  }
  if ( v7 != -1073741811 || *(_DWORD *)(a1 + 8) != 4 )
    goto LABEL_14;
LABEL_15:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180037e68  mov     rax, rsp
0x180037e6b  mov     [rax+8], rbx
0x180037e6f  mov     [rax+10h], rbp
0x180037e73  push    rsi
0x180037e74  push    rdi
0x180037e75  push    r14
0x180037e77  sub     rsp, 40h
0x180037e7b  mov     ebp, edx
0x180037e7d  mov     dword ptr [rax+20h], 0
0x180037e84  mov     rsi, rcx
0x180037e87  mov     qword ptr [rax-28h], 0
0x180037e8f  lea     rdx, [rax-28h]
0x180037e93  mov     qword ptr [rax-20h], 0
0x180037e9b  lea     rcx, aZwtranslatefil; "ZwTranslateFilePath"
0x180037ea2  mov     r14, r8
0x180037ea5  xor     edi, edi
0x180037ea7  call    BiLookupNtdllProcedureAddress
0x180037eac  test    eax, eax
0x180037eae  jns     short loc_180037EBA
0x180037eb0  mov     ebx, 0C00000BBh
0x180037eb5  jmp     loc_180037F6B
0x180037eba  lea     rdx, [rsp+58h+var_20]
0x180037ebf  mov     ecx, 16h
0x180037ec4  call    BiAcquirePrivilege
0x180037ec9  mov     ebx, eax
0x180037ecb  test    eax, eax
0x180037ecd  js      loc_180037F5D
0x180037ed3  mov     rax, [rsp+58h+var_28]
0x180037ed8  lea     r9, [rsp+58h+Size]
0x180037edd  xor     r8d, r8d
0x180037ee0  mov     dword ptr [rsp+58h+Size], edi
0x180037ee4  mov     edx, ebp
0x180037ee6  mov     rcx, rsi
0x180037ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037eee  mov     ebx, eax
0x180037ef0  cmp     eax, 0C0000023h
0x180037ef5  jz      short loc_180037F02
0x180037ef7  test    eax, eax
0x180037ef9  js      short loc_180037F4A
0x180037efb  mov     ebx, 0C000000Dh
0x180037f00  jmp     short loc_180037F4A
0x180037f02  mov     rcx, gs:60h
0x180037f0b  xor     edx, edx; Flags
0x180037f0d  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x180037f12  mov     rcx, [rcx+30h]; HeapHandle
0x180037f16  call    cs:__imp_RtlAllocateHeap
0x180037f1d  nop     dword ptr [rax+rax+00h]
0x180037f22  mov     rdi, rax
0x180037f25  test    rax, rax
0x180037f28  jnz     short loc_180037F31
0x180037f2a  mov     ebx, 0C000009Ah
0x180037f2f  jmp     short loc_180037F4A
0x180037f31  mov     r8, rax
0x180037f34  lea     r9, [rsp+58h+Size]
0x180037f39  mov     rax, [rsp+58h+var_28]
0x180037f3e  mov     edx, ebp
0x180037f40  mov     rcx, rsi
0x180037f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f48  mov     ebx, eax
0x180037f4a  lea     rcx, [rsp+58h+var_20]
0x180037f4f  call    BiReleasePrivilege
0x180037f54  test    ebx, ebx
0x180037f56  js      short loc_180037F5D
0x180037f58  mov     [r14], rdi
0x180037f5b  jmp     short loc_180037FA6
0x180037f5d  cmp     ebx, 0C000000Dh
0x180037f63  jnz     short loc_180037F6B
0x180037f65  cmp     dword ptr [rsi+8], 4
0x180037f69  jz      short loc_180037F83
0x180037f6b  mov     r8d, [rsi+8]
0x180037f6f  lea     rdx, aBitranslatefil; "BiTranslateFilePath failed. File type: "...
0x180037f76  mov     r9d, ebx
0x180037f79  mov     ecx, 4
0x180037f7e  call    BiLogMessage
0x180037f83  test    rdi, rdi
0x180037f86  jz      short loc_180037FA6
0x180037f88  mov     rcx, gs:60h
0x180037f91  mov     r8, rdi; P
0x180037f94  xor     edx, edx; Flags
0x180037f96  mov     rcx, [rcx+30h]; HeapHandle
0x180037f9a  call    cs:__imp_RtlFreeHeap
0x180037fa1  nop     dword ptr [rax+rax+00h]
0x180037fa6  mov     rbp, [rsp+58h+arg_8]
0x180037fab  mov     eax, ebx
0x180037fad  mov     rbx, [rsp+58h+arg_0]
0x180037fb2  add     rsp, 40h
0x180037fb6  pop     r14
0x180037fb8  pop     rdi
0x180037fb9  pop     rsi
0x180037fba  retn
```
