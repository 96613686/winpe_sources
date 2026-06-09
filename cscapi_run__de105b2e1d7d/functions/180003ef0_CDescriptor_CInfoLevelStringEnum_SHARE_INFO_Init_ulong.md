# CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::Init(ulong)

- ea: `0x180003ef0`
- end: `0x180003f3e`
- name: `?Init@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAEK@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002080`

## callees

- `0x180009462`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::Init(__int64 a1, unsigned int a2)
{
  size_t v2; // r8
  __int64 result; // rax

  v2 = *(unsigned int *)(a1 + 16);
  *(_DWORD *)(a1 + 64) = a2;
  *(_DWORD *)(a1 + 68) = 0;
  memset_0(*(void **)(a1 + 8), 0, v2);
  *(_QWORD *)(a1 + 20) = -1;
  result = (**(__int64 (__fastcall ***)(__int64, _QWORD))a1)(a1, a2);
  *(_BYTE *)(a1 + 72) = result;
  return result;
}

```

## disassembly

```asm
0x180003ef0  mov     [rsp+arg_0], rbx
0x180003ef5  push    rdi
0x180003ef6  sub     rsp, 20h
0x180003efa  mov     r8d, [rcx+10h]; Size
0x180003efe  mov     ebx, edx
0x180003f00  mov     [rcx+40h], edx
0x180003f03  mov     rdi, rcx
0x180003f06  mov     dword ptr [rcx+44h], 0
0x180003f0d  xor     edx, edx; Val
0x180003f0f  mov     rcx, [rcx+8]; void *
0x180003f13  call    memset_0
0x180003f18  mov     qword ptr [rdi+14h], 0FFFFFFFFFFFFFFFFh
0x180003f20  mov     edx, ebx
0x180003f22  mov     rax, [rdi]
0x180003f25  mov     rcx, rdi
0x180003f28  mov     rax, [rax]
0x180003f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f30  mov     rbx, [rsp+28h+arg_0]
0x180003f35  mov     [rdi+48h], al
0x180003f38  add     rsp, 20h
0x180003f3c  pop     rdi
0x180003f3d  retn
```
