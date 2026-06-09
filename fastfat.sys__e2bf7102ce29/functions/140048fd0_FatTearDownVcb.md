# FatTearDownVcb

- ea: `0x140048fd0`
- end: `0x14004909f`
- name: `FatTearDownVcb`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006350`

## callees

- `0x140023cc4`
- `0x140048fd0`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x140048ff3`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14004905c`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140048ff3`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14004905c`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140049002`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140049002`
- `ntoskrnl!ObfDereferenceObject` at `0x140049015`
- `ntoskrnl!ObfDereferenceObject` at `0x14004907d`
- `ntoskrnl!ObfDereferenceObject` at `0x140049015`
- `ntoskrnl!ObfDereferenceObject` at `0x14004907d`

## pseudocode

```c
LONG_PTR __fastcall FatTearDownVcb(__int64 a1, __int64 a2)
{
  struct _FILE_OBJECT *v2; // rcx
  LONG_PTR result; // rax
  __int64 v5; // rdi
  struct _FILE_OBJECT *v6; // rdi

  v2 = *(struct _FILE_OBJECT **)(a2 + 728);
  if ( v2 )
  {
    CcUninitializeCacheMap(v2, &FatLargeZero, 0);
    FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)a2);
    ObfDereferenceObject(*(PVOID *)(a2 + 728));
    *(_QWORD *)(a2 + 728) = 0;
  }
  result = FatCloseEaFile(v2, a2, 0);
  v5 = *(_QWORD *)(a2 + 208);
  if ( v5 )
  {
    v6 = *(struct _FILE_OBJECT **)(v5 + 344);
    if ( v6 )
    {
      CcUninitializeCacheMap(v6, &FatLargeZero, 0);
      *(_QWORD *)(*(_QWORD *)(a2 + 208) + 344LL) = 0;
      result = ObfDereferenceObject(v6);
    }
  }
  *(_DWORD *)(a2 + 204) = 3;
  return result;
}

```

## disassembly

```asm
0x140048fd0  mov     [rsp+arg_0], rbx
0x140048fd5  push    rdi
0x140048fd6  sub     rsp, 20h
0x140048fda  mov     rcx, [rdx+2D8h]; FileObject
0x140048fe1  mov     rbx, rdx
0x140048fe4  test    rcx, rcx
0x140048fe7  jz      short loc_14004902C
0x140048fe9  xor     r8d, r8d; UninitializeEvent
0x140048fec  lea     rdx, FatLargeZero; TruncateSize
0x140048ff3  call    cs:__imp_CcUninitializeCacheMap
0x140048ffa  nop     dword ptr [rax+rax+00h]
0x140048fff  mov     rcx, rbx; AdvancedHeader
0x140049002  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140049009  nop     dword ptr [rax+rax+00h]
0x14004900e  mov     rcx, [rbx+2D8h]; Object
0x140049015  call    cs:__imp_ObfDereferenceObject
0x14004901c  nop     dword ptr [rax+rax+00h]
0x140049021  mov     qword ptr [rbx+2D8h], 0
0x14004902c  xor     r8d, r8d
0x14004902f  mov     rdx, rbx
0x140049032  call    FatCloseEaFile
0x140049037  mov     rdi, [rbx+0D0h]
0x14004903e  test    rdi, rdi
0x140049041  jz      short loc_140049089
0x140049043  mov     rdi, [rdi+158h]
0x14004904a  test    rdi, rdi
0x14004904d  jz      short loc_140049089
0x14004904f  xor     r8d, r8d; UninitializeEvent
0x140049052  lea     rdx, FatLargeZero; TruncateSize
0x140049059  mov     rcx, rdi; FileObject
0x14004905c  call    cs:__imp_CcUninitializeCacheMap
0x140049063  nop     dword ptr [rax+rax+00h]
0x140049068  mov     rax, [rbx+0D0h]
0x14004906f  mov     rcx, rdi; Object
0x140049072  mov     qword ptr [rax+158h], 0
0x14004907d  call    cs:__imp_ObfDereferenceObject
0x140049084  nop     dword ptr [rax+rax+00h]
0x140049089  mov     dword ptr [rbx+0CCh], 3
0x140049093  mov     rbx, [rsp+28h+arg_0]
0x140049098  add     rsp, 20h
0x14004909c  pop     rdi
0x14004909d  retn
```
