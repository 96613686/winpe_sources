# UACCheckProviderSSO_CreateInstance(IUnknown * *)

- ea: `0x180004550`
- end: `0x1800045ba`
- name: `?UACCheckProviderSSO_CreateInstance@@YAJPEAPEAUIUnknown@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004550`
- `0x180004fc8`
- `0x180008990`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall UACCheckProviderSSO_CreateInstance(struct IUnknown **a1)
{
  CUACCheckProviderSSO *v2; // rax
  CUACCheckProviderSSO *v3; // rax
  CUACCheckProviderSSO *v4; // rbx
  unsigned int v5; // edi

  v2 = (CUACCheckProviderSSO *)operator new(0x28u);
  if ( v2 && (v3 = CUACCheckProviderSSO::CUACCheckProviderSSO(v2), (v4 = v3) != 0) )
  {
    v5 = (**(__int64 (__fastcall ***)(CUACCheckProviderSSO *, GUID *, struct IUnknown **))v3)(
           v3,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(CUACCheckProviderSSO *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v5;
}

```

## disassembly

```asm
0x180004550  mov     [rsp+arg_0], rbx
0x180004555  push    rdi
0x180004556  sub     rsp, 20h
0x18000455a  mov     rdi, rcx
0x18000455d  mov     ecx, 28h ; '('; Size
0x180004562  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004567  test    rax, rax
0x18000456a  jz      short loc_1800045A7
0x18000456c  mov     rcx, rax; this
0x18000456f  call    ??0CUACCheckProviderSSO@@AEAA@XZ; CUACCheckProviderSSO::CUACCheckProviderSSO(void)
0x180004574  mov     rbx, rax
0x180004577  test    rax, rax
0x18000457a  jz      short loc_1800045A7
0x18000457c  mov     rcx, [rax]
0x18000457f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004586  mov     r8, rdi
0x180004589  mov     rax, [rcx]
0x18000458c  mov     rcx, rbx
0x18000458f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004594  mov     rcx, [rbx]
0x180004597  mov     edi, eax
0x180004599  mov     rax, [rcx+10h]
0x18000459d  mov     rcx, rbx
0x1800045a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a5  jmp     short loc_1800045AC
0x1800045a7  mov     edi, 8007000Eh
0x1800045ac  mov     rbx, [rsp+28h+arg_0]
0x1800045b1  mov     eax, edi
0x1800045b3  add     rsp, 20h
0x1800045b7  pop     rdi
0x1800045b8  retn
```
