# MpRegpAllocDeleteKeyContext

- ea: `0x140033764`
- end: `0x1400337d7`
- name: `MpRegpAllocDeleteKeyContext`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140038f74`

## callees

- `0x140011610`
- `0x140033764`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003377e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003377e`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocDeleteKeyContext()
{
  char *v0; // rbx
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 384;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 384);
  ++*((_DWORD *)RegData + 101);
  result = ExpInterlockedPopEntrySList(v1);
  if ( result
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    *result = 0;
    result[1] = 0;
    result[2] = 0;
    result[3].Next = 0;
    *((_QWORD *)&result->Next + 1) = MpRegpFreeDeleteKeyContext;
    LODWORD(result->Next) = 3730182;
  }
  return result;
}

```

## disassembly

```asm
0x140033764  push    rbx
0x140033766  sub     rsp, 20h
0x14003376a  mov     rbx, cs:RegData
0x140033771  add     rbx, 180h
0x140033778  mov     rcx, rbx; ListHead
0x14003377b  inc     dword ptr [rbx+14h]
0x14003377e  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033785  nop     dword ptr [rax+rax+00h]
0x14003378a  test    rax, rax
0x14003378d  jnz     short loc_1400337AB
0x14003378f  mov     edx, [rbx+2Ch]
0x140033792  mov     rax, [rbx+30h]
0x140033796  mov     r8d, [rbx+28h]
0x14003379a  mov     ecx, [rbx+24h]
0x14003379d  inc     dword ptr [rbx+18h]
0x1400337a0  call    cs:__guard_dispatch_icall_fptr
0x1400337a6  test    rax, rax
0x1400337a9  jz      short loc_1400337D0
0x1400337ab  xorps   xmm0, xmm0
0x1400337ae  xor     ecx, ecx
0x1400337b0  movups  xmmword ptr [rax], xmm0
0x1400337b3  movups  xmmword ptr [rax+10h], xmm0
0x1400337b7  movups  xmmword ptr [rax+20h], xmm0
0x1400337bb  mov     [rax+30h], rcx
0x1400337bf  lea     rcx, MpRegpFreeDeleteKeyContext
0x1400337c6  mov     [rax+8], rcx
0x1400337ca  mov     dword ptr [rax], 38EB06h
0x1400337d0  add     rsp, 20h
0x1400337d4  pop     rbx
0x1400337d5  retn
```
