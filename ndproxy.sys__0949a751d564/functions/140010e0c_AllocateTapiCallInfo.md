# AllocateTapiCallInfo

- ea: `0x140010e0c`
- end: `0x140010ec4`
- name: `AllocateTapiCallInfo`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013bc0`
- `0x140015b50`

## callees

- `0x1400081c0`
- `0x140010e0c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010e5f`
- `ntoskrnl!ExAllocatePool2` at `0x140010e5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010e29`

## pseudocode

```c
__int64 __fastcall AllocateTapiCallInfo(__int64 a1, _DWORD *a2)
{
  void *v4; // rcx
  unsigned int v5; // esi
  __int64 v6; // rbp
  unsigned int *Pool2; // rax

  v4 = *(void **)(a1 + 304);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( a2 )
    v5 = a2[2];
  else
    v5 = 1024;
  v6 = (__int64)(a2 + 2);
  if ( !a2 )
    v6 = 8;
  Pool2 = (unsigned int *)ExAllocatePool2(64, v5, 6707280);
  *(_QWORD *)(a1 + 304) = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_DWORD *)(a1 + 288) = 0;
  if ( a2 )
  {
    memmove(Pool2, a2, *(unsigned int *)v6);
  }
  else
  {
    *Pool2 = v5;
    *(_DWORD *)(*(_QWORD *)(a1 + 304) + 4LL) = v5;
    *(_DWORD *)(*(_QWORD *)(a1 + 304) + 8LL) = 344;
  }
  return 0;
}

```

## disassembly

```asm
0x140010e0c  push    rbx
0x140010e0e  push    rbp
0x140010e0f  push    rsi
0x140010e10  push    rdi
0x140010e11  sub     rsp, 28h
0x140010e15  mov     rdi, rcx
0x140010e18  mov     rbx, rdx
0x140010e1b  mov     rcx, [rcx+130h]; P
0x140010e22  test    rcx, rcx
0x140010e25  jz      short loc_140010E35
0x140010e27  xor     edx, edx; Tag
0x140010e29  call    cs:__imp_ExFreePoolWithTag
0x140010e30  nop     dword ptr [rax+rax+00h]
0x140010e35  test    rbx, rbx
0x140010e38  jz      short loc_140010E3F
0x140010e3a  mov     esi, [rbx+8]
0x140010e3d  jmp     short loc_140010E44
0x140010e3f  mov     esi, 400h
0x140010e44  mov     eax, 8
0x140010e49  mov     edx, esi
0x140010e4b  test    rbx, rbx
0x140010e4e  lea     rbp, [rbx+8]
0x140010e52  mov     r8d, 665850h
0x140010e58  cmovz   rbp, rax
0x140010e5c  lea     ecx, [rax+38h]
0x140010e5f  call    cs:__imp_ExAllocatePool2
0x140010e66  nop     dword ptr [rax+rax+00h]
0x140010e6b  mov     [rdi+130h], rax
0x140010e72  test    rax, rax
0x140010e75  jnz     short loc_140010E7E
0x140010e77  mov     eax, 0C000009Ah
0x140010e7c  jmp     short loc_140010EBA
0x140010e7e  mov     dword ptr [rdi+120h], 0
0x140010e88  test    rbx, rbx
0x140010e8b  jz      short loc_140010E9E
0x140010e8d  mov     r8d, [rbp+0]; Size
0x140010e91  mov     rdx, rbx; Src
0x140010e94  mov     rcx, rax; void *
0x140010e97  call    memmove
0x140010e9c  jmp     short loc_140010EB8
0x140010e9e  mov     [rax], esi
0x140010ea0  mov     rax, [rdi+130h]
0x140010ea7  mov     [rax+4], esi
0x140010eaa  mov     rax, [rdi+130h]
0x140010eb1  mov     dword ptr [rax+8], 158h
0x140010eb8  xor     eax, eax
0x140010eba  add     rsp, 28h
0x140010ebe  pop     rdi
0x140010ebf  pop     rsi
0x140010ec0  pop     rbp
0x140010ec1  pop     rbx
0x140010ec2  retn
```
