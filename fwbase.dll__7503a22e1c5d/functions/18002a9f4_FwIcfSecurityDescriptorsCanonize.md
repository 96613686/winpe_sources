# FwIcfSecurityDescriptorsCanonize

- ea: `0x18002a9f4`
- end: `0x18002aa6c`
- name: `FwIcfSecurityDescriptorsCanonize`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001262c`

## callees

- `0x180029f30`
- `0x18002a9f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002aa3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002aa3a`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002aa19`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002aa19`

## pseudocode

```c
void __fastcall FwIcfSecurityDescriptorsCanonize(void **a1)
{
  unsigned int v2; // edi

  if ( *(_DWORD *)a1 > 1u )
  {
    qsort(a1[1], *(unsigned int *)a1, 0x10u, FwIcfSecurityDescriptorCompare);
    v2 = 1;
    while ( v2 < *(_DWORD *)a1 )
    {
      if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a1[1] + 2 * v2 - 2), *((_QWORD *)a1[1] + 2 * v2)) )
        ++v2;
      else
        FwArrayErase(16, FwIcfSecurityDescriptorDestroy, a1, v2);
    }
  }
}

```

## disassembly

```asm
0x18002a9f4  mov     [rsp+arg_0], rbx
0x18002a9f9  push    rdi
0x18002a9fa  sub     rsp, 20h
0x18002a9fe  cmp     dword ptr [rcx], 1
0x18002aa01  mov     rbx, rcx
0x18002aa04  jbe     short loc_18002AA61
0x18002aa06  mov     edx, [rcx]; NumOfElements
0x18002aa08  lea     r9, FwIcfSecurityDescriptorCompare; CompareFunction
0x18002aa0f  mov     rcx, [rcx+8]; Base
0x18002aa13  mov     r8d, 10h; SizeOfElements
0x18002aa19  call    cs:__imp_qsort
0x18002aa1f  mov     edi, 1
0x18002aa24  cmp     [rbx], edi
0x18002aa26  jbe     short loc_18002AA61
0x18002aa28  mov     rcx, [rbx+8]
0x18002aa2c  mov     eax, edi
0x18002aa2e  add     rax, rax
0x18002aa31  mov     rdx, [rcx+rax*8]
0x18002aa35  mov     rcx, [rcx+rax*8-10h]
0x18002aa3a  call    cs:__imp__o__wcsicmp
0x18002aa40  test    eax, eax
0x18002aa42  jnz     short loc_18002AA5B
0x18002aa44  mov     r9d, edi
0x18002aa47  lea     rdx, FwIcfSecurityDescriptorDestroy
0x18002aa4e  mov     r8, rbx
0x18002aa51  lea     ecx, [rax+10h]
0x18002aa54  call    FwArrayErase
0x18002aa59  jmp     short loc_18002AA5D
0x18002aa5b  inc     edi
0x18002aa5d  cmp     edi, [rbx]
0x18002aa5f  jb      short loc_18002AA28
0x18002aa61  mov     rbx, [rsp+28h+arg_0]
0x18002aa66  add     rsp, 20h
0x18002aa6a  pop     rdi
0x18002aa6b  retn
```
