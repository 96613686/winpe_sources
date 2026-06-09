# XpressReallocateWorkspace

- ea: `0x180013240`
- end: `0x1800132d9`
- name: `XpressReallocateWorkspace`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800131b4`
- `0x180017890`

## callees

- `0x180013240`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18001326e`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18001326e`

## pseudocode

```c
__int64 __fastcall XpressReallocateWorkspace(__int64 a1, int a2)
{
  __int16 v3; // cx
  ULONG v5; // eax
  __int64 v6; // rdi
  ULONG v8; // [rsp+30h] [rbp+8h] BYREF
  ULONG v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  v3 = *(_WORD *)(a1 + 2);
  v8 = 0;
  if ( RtlGetCompressionWorkSpaceSize(*(_WORD *)a1 | v3, &v9, &v8) )
    return 1627;
  v5 = v8;
  if ( a2 )
    v5 = v9;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 8))(*(_QWORD *)(a1 + 24), v5);
    if ( !v6 )
      return 8;
  }
  else
  {
    v6 = 0;
  }
  if ( *(_QWORD *)(a1 + 32) )
    (*(void (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 24));
  *(_QWORD *)(a1 + 32) = v6;
  return 0;
}

```

## disassembly

```asm
0x180013240  mov     rax, rsp
0x180013243  mov     [rax+10h], rbx
0x180013247  push    rdi
0x180013248  sub     rsp, 20h
0x18001324c  mov     rbx, rcx
0x18001324f  mov     dword ptr [rax+18h], 0
0x180013256  movzx   ecx, word ptr [rcx+2]
0x18001325a  lea     r8, [rax+8]; CompressFragmentWorkSpaceSize
0x18001325e  mov     edi, edx
0x180013260  mov     dword ptr [rax+8], 0
0x180013267  lea     rdx, [rax+18h]; CompressBufferWorkSpaceSize
0x18001326b  or      cx, [rbx]; CompressionFormatAndEngine
0x18001326e  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x180013274  test    eax, eax
0x180013276  jnz     short loc_1800132C3
0x180013278  mov     eax, [rsp+28h+arg_0]
0x18001327c  test    edi, edi
0x18001327e  cmovnz  eax, [rsp+28h+arg_10]
0x180013283  test    eax, eax
0x180013285  jz      short loc_1800132BF
0x180013287  mov     rcx, [rbx+18h]
0x18001328b  mov     edx, eax
0x18001328d  mov     rax, [rbx+8]
0x180013291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013296  mov     rdi, rax
0x180013299  test    rax, rax
0x18001329c  jz      short loc_1800132B8
0x18001329e  mov     rdx, [rbx+20h]
0x1800132a2  test    rdx, rdx
0x1800132a5  jnz     short loc_1800132CA
0x1800132a7  mov     [rbx+20h], rdi
0x1800132ab  xor     eax, eax
0x1800132ad  mov     rbx, [rsp+28h+arg_8]
0x1800132b2  add     rsp, 20h
0x1800132b6  pop     rdi
0x1800132b7  retn
0x1800132b8  mov     eax, 8
0x1800132bd  jmp     short loc_1800132AD
0x1800132bf  xor     edi, edi
0x1800132c1  jmp     short loc_18001329E
0x1800132c3  mov     eax, 65Bh
0x1800132c8  jmp     short loc_1800132AD
0x1800132ca  mov     rcx, [rbx+18h]
0x1800132ce  mov     rax, [rbx+10h]
0x1800132d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d7  jmp     short loc_1800132A7
```
