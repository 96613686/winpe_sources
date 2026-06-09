# AllocWorkItem

- ea: `0x140005234`
- end: `0x1400052af`
- name: `AllocWorkItem`
- size: `123`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400037c0`
- `0x140003d18`
- `0x140014d2c`
- `0x1400152f4`

## callees

- `0x140005234`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000524d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000524d`
- `NDIS!NdisAllocateIoWorkItem` at `0x140005292`
- `NDIS!NdisAllocateIoWorkItem` at `0x140005292`

## pseudocode

```c
_QWORD *__fastcall AllocWorkItem(__int64 a1, __int64 a2, __int64 a3, __int128 *a4, int a5)
{
  _QWORD *result; // rax
  _QWORD *v8; // rbx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  NDIS_HANDLE v11; // rcx

  result = ExAllocateFromNPagedLookasideList(&gl_llistWorkItems);
  v8 = result;
  if ( result )
  {
    result[8] = 0;
    v9 = *a4;
    *(_DWORD *)result = 0;
    v10 = a4[1];
    result[7] = 0;
    v11 = gl_NdisMiniportDriverHandle;
    *((_OWORD *)result + 1) = v9;
    *((_DWORD *)result + 1) = a5;
    *((_OWORD *)result + 2) = v10;
    result[1] = &gl_llistWorkItems;
    result[6] = a2;
    result[8] = NdisAllocateIoWorkItem(v11);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140005234  push    rbx
0x140005236  push    rbp
0x140005237  push    rsi
0x140005238  push    rdi
0x140005239  sub     rsp, 28h
0x14000523d  lea     rbp, gl_llistWorkItems
0x140005244  mov     rdi, r9
0x140005247  mov     rcx, rbp; Lookaside
0x14000524a  mov     rsi, rdx
0x14000524d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140005254  nop     dword ptr [rax+rax+00h]
0x140005259  xor     ecx, ecx
0x14000525b  mov     rbx, rax
0x14000525e  test    rax, rax
0x140005261  jz      short loc_1400052A5
0x140005263  mov     [rax+40h], rcx
0x140005267  movups  xmm0, xmmword ptr [rdi]
0x14000526a  mov     [rax], ecx
0x14000526c  movups  xmm1, xmmword ptr [rdi+10h]
0x140005270  mov     eax, [rsp+48h+arg_20]
0x140005274  mov     [rbx+38h], rcx
0x140005278  mov     rcx, cs:gl_NdisMiniportDriverHandle; NdisObjectHandle
0x14000527f  movups  xmmword ptr [rbx+10h], xmm0
0x140005283  mov     [rbx+4], eax
0x140005286  movups  xmmword ptr [rbx+20h], xmm1
0x14000528a  mov     [rbx+8], rbp
0x14000528e  mov     [rbx+30h], rsi
0x140005292  call    cs:__imp_NdisAllocateIoWorkItem
0x140005299  nop     dword ptr [rax+rax+00h]
0x14000529e  mov     [rbx+40h], rax
0x1400052a2  mov     rax, rbx
0x1400052a5  add     rsp, 28h
0x1400052a9  pop     rdi
0x1400052aa  pop     rsi
0x1400052ab  pop     rbp
0x1400052ac  pop     rbx
0x1400052ad  retn
```
