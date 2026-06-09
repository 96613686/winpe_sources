# DfscReplaceFileObjectInformation

- ea: `0x140024db4`
- end: `0x140024e2d`
- name: `DfscReplaceFileObjectInformation`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140024930`

## callees

- `0x140024db4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024dd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024dd8`

## pseudocode

```c
__int64 __fastcall DfscReplaceFileObjectInformation(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  __int64 result; // rax

  if ( (*(_BYTE *)(a1 + 288) & 1) != 0 )
  {
    v4 = *(void **)(a2 + 96);
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    *(_OWORD *)(a2 + 88) = *(_OWORD *)(a1 + 344);
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a1 + 360);
    *(_DWORD *)(a1 + 344) = 0;
    *(_QWORD *)(a1 + 360) = 0;
    result = 65534;
    *(_WORD *)(a1 + 288) &= ~1u;
    *(_QWORD *)(a1 + 352) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140024db4  mov     [rsp+arg_0], rbx
0x140024db9  push    rdi
0x140024dba  sub     rsp, 20h
0x140024dbe  test    byte ptr [rcx+120h], 1
0x140024dc5  mov     rdi, rdx
0x140024dc8  mov     rbx, rcx
0x140024dcb  jz      short loc_140024E21
0x140024dcd  mov     rcx, [rdx+60h]; P
0x140024dd1  test    rcx, rcx
0x140024dd4  jz      short loc_140024DE4
0x140024dd6  xor     edx, edx; Tag
0x140024dd8  call    cs:__imp_ExFreePoolWithTag
0x140024ddf  nop     dword ptr [rax+rax+00h]
0x140024de4  movups  xmm0, xmmword ptr [rbx+158h]
0x140024deb  movdqu  xmmword ptr [rdi+58h], xmm0
0x140024df0  mov     rax, [rbx+168h]
0x140024df7  mov     [rdi+40h], rax
0x140024dfb  xor     eax, eax
0x140024dfd  mov     [rbx+158h], eax
0x140024e03  mov     [rbx+168h], rax
0x140024e0a  mov     eax, 0FFFEh
0x140024e0f  and     [rbx+120h], ax
0x140024e16  mov     qword ptr [rbx+160h], 0
0x140024e21  mov     rbx, [rsp+28h+arg_0]
0x140024e26  add     rsp, 20h
0x140024e2a  pop     rdi
0x140024e2b  retn
```
