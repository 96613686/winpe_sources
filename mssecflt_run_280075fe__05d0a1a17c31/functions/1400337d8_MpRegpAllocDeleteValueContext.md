# MpRegpAllocDeleteValueContext

- ea: `0x1400337d8`
- end: `0x140033857`
- name: `MpRegpAllocDeleteValueContext`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400390b0`

## callees

- `0x140011610`
- `0x1400119c0`
- `0x1400337d8`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400337f6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400337f6`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocDeleteValueContext()
{
  char *v0; // rdi
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY v2; // rbx
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 512;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 512);
  ++*((_DWORD *)RegData + 133);
  v2 = ExpInterlockedPopEntrySList(v1);
  if ( v2
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (v2 = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    memset(v2, 0, 0x40u);
    LODWORD(v2->Next) = 4254466;
    *((_QWORD *)&v2->Next + 1) = MpRegpFreeDeleteValueContext;
  }
  return v2;
}

```

## disassembly

```asm
0x1400337d8  mov     [rsp+arg_0], rbx
0x1400337dd  push    rdi
0x1400337de  sub     rsp, 20h
0x1400337e2  mov     rdi, cs:RegData
0x1400337e9  add     rdi, 200h
0x1400337f0  mov     rcx, rdi; ListHead
0x1400337f3  inc     dword ptr [rdi+14h]
0x1400337f6  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400337fd  nop     dword ptr [rax+rax+00h]
0x140033802  mov     rbx, rax
0x140033805  test    rax, rax
0x140033808  jnz     short loc_140033829
0x14003380a  mov     edx, [rdi+2Ch]
0x14003380d  mov     rax, [rdi+30h]
0x140033811  mov     r8d, [rdi+28h]
0x140033815  mov     ecx, [rdi+24h]
0x140033818  inc     dword ptr [rdi+18h]
0x14003381b  call    cs:__guard_dispatch_icall_fptr
0x140033821  mov     rbx, rax
0x140033824  test    rax, rax
0x140033827  jz      short loc_140033848
0x140033829  xor     edx, edx; Val
0x14003382b  mov     rcx, rbx; void *
0x14003382e  lea     r8d, [rdx+40h]; Size
0x140033832  call    memset
0x140033837  lea     rax, MpRegpFreeDeleteValueContext
0x14003383e  mov     dword ptr [rbx], 40EB02h
0x140033844  mov     [rbx+8], rax
0x140033848  mov     rax, rbx
0x14003384b  mov     rbx, [rsp+28h+arg_0]
0x140033850  add     rsp, 20h
0x140033854  pop     rdi
0x140033855  retn
```
