# RfsAllocateCacheAwareRundownProtectionEx

- ea: `0x140051e3c`
- end: `0x140051f14`
- name: `RfsAllocateCacheAwareRundownProtectionEx`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140051e24`

## callees

- `0x140051e3c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140051e50`
- `ntoskrnl!ExAllocatePool2` at `0x140051ea8`
- `ntoskrnl!ExAllocatePool2` at `0x140051e50`
- `ntoskrnl!ExAllocatePool2` at `0x140051ea8`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140051e6d`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140051e6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051ec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051ec1`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140051e81`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140051e81`

## pseudocode

```c
__int64 *RfsAllocateCacheAwareRundownProtectionEx()
{
  __int64 *Pool2; // rbx
  ULONG MaximumProcessorCount; // eax
  ULONG RecommendedSharedDataAlignment; // eax
  __int64 v3; // rax
  unsigned int v5; // ecx
  unsigned int i; // r8d
  int v7; // edx

  Pool2 = (__int64 *)ExAllocatePool2(64, 32, 1984723026);
  if ( Pool2 )
  {
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    *((_DWORD *)Pool2 + 6) = MaximumProcessorCount;
    if ( MaximumProcessorCount <= 1 )
      RecommendedSharedDataAlignment = 8;
    else
      RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
    *((_DWORD *)Pool2 + 5) = RecommendedSharedDataAlignment;
    v3 = ExAllocatePool2(72, *((_DWORD *)Pool2 + 6) * RecommendedSharedDataAlignment, 1984723026);
    if ( !v3 )
    {
      ExFreePoolWithTag(Pool2, 0x764C7852u);
      return 0;
    }
    v5 = *((_DWORD *)Pool2 + 6);
    *((_DWORD *)Pool2 + 4) = 1984723026;
    Pool2[1] = v3;
    *Pool2 = v3;
    if ( v5 )
    {
      for ( i = 0; i < v5; ++i )
      {
        v7 = i % v5;
        *(_QWORD *)((unsigned int)(*((_DWORD *)Pool2 + 5) * v7) + *Pool2) = 0;
        v5 = *((_DWORD *)Pool2 + 6);
      }
    }
  }
  return Pool2;
}

```

## disassembly

```asm
0x140051e3c  push    rbx
0x140051e3e  sub     rsp, 20h
0x140051e42  mov     edx, 20h ; ' '
0x140051e47  mov     r8d, 764C7852h
0x140051e4d  lea     ecx, [rdx+20h]
0x140051e50  call    cs:__imp_ExAllocatePool2
0x140051e57  nop     dword ptr [rax+rax+00h]
0x140051e5c  mov     rbx, rax
0x140051e5f  test    rax, rax
0x140051e62  jz      loc_140051F0A
0x140051e68  mov     ecx, 0FFFFh; GroupNumber
0x140051e6d  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140051e74  nop     dword ptr [rax+rax+00h]
0x140051e79  mov     [rbx+18h], eax
0x140051e7c  cmp     eax, 1
0x140051e7f  jbe     short loc_140051E8F
0x140051e81  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140051e88  nop     dword ptr [rax+rax+00h]
0x140051e8d  jmp     short loc_140051E94
0x140051e8f  mov     eax, 8
0x140051e94  mov     [rbx+14h], eax
0x140051e97  mov     ecx, 48h ; 'H'
0x140051e9c  imul    eax, [rbx+18h]
0x140051ea0  mov     r8d, 764C7852h
0x140051ea6  mov     edx, eax
0x140051ea8  call    cs:__imp_ExAllocatePool2
0x140051eaf  nop     dword ptr [rax+rax+00h]
0x140051eb4  test    rax, rax
0x140051eb7  jnz     short loc_140051ED1
0x140051eb9  mov     edx, 764C7852h; Tag
0x140051ebe  mov     rcx, rbx; P
0x140051ec1  call    cs:__imp_ExFreePoolWithTag
0x140051ec8  nop     dword ptr [rax+rax+00h]
0x140051ecd  xor     eax, eax
0x140051ecf  jmp     short loc_140051F0D
0x140051ed1  mov     ecx, [rbx+18h]
0x140051ed4  mov     dword ptr [rbx+10h], 764C7852h
0x140051edb  mov     [rbx+8], rax
0x140051edf  mov     [rbx], rax
0x140051ee2  test    ecx, ecx
0x140051ee4  jz      short loc_140051F0A
0x140051ee6  xor     r8d, r8d
0x140051ee9  xor     edx, edx
0x140051eeb  mov     eax, r8d
0x140051eee  div     ecx
0x140051ef0  mov     rax, [rbx]
0x140051ef3  inc     r8d
0x140051ef6  imul    edx, [rbx+14h]
0x140051efa  mov     qword ptr [rdx+rax], 0
0x140051f02  mov     ecx, [rbx+18h]
0x140051f05  cmp     r8d, ecx
0x140051f08  jb      short loc_140051EE9
0x140051f0a  mov     rax, rbx
0x140051f0d  add     rsp, 20h
0x140051f11  pop     rbx
0x140051f12  retn
```
