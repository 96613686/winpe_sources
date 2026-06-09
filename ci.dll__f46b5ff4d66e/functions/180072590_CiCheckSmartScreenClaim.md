# CiCheckSmartScreenClaim

- ea: `0x180072590`
- end: `0x180072694`
- name: `CiCheckSmartScreenClaim`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180063d3c`
- `0x1800b3c18`

## callees

- `0x180072590`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800725c4`
- `ntoskrnl!ExAllocatePool2` at `0x1800725c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072626`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072677`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072626`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072677`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180072601`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180072601`

## pseudocode

```c
void __fastcall CiCheckSmartScreenClaim(int *a1)
{
  int v1; // eax
  __int64 Pool2; // rbx
  unsigned int v4; // esi
  int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1;
  Pool2 = 0;
  v7 = 0;
  v4 = 678;
  if ( (v1 & 0x10) != 0 )
  {
    while ( 1 )
    {
      Pool2 = ExAllocatePool2(258, v4, 1098149235);
      if ( !Pool2 )
        break;
      v5 = SeQuerySecurityAttributesToken(*((_QWORD *)a1 + 380), L"`b", 1, Pool2, v4, &v7);
      if ( v5 != -1073741789 )
      {
        if ( v5 >= 0 )
        {
          if ( *(_DWORD *)(Pool2 + 4) )
          {
            v6 = *(_QWORD *)(Pool2 + 8);
            if ( *(_WORD *)(v6 + 16) == 16 && *(_DWORD *)(*(_QWORD *)(v6 + 32) + 8LL) == 524 )
              a1[382] = 1;
          }
        }
        break;
      }
      if ( v4 >= v7 )
        break;
      v4 = v7;
      ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    }
  }
  a1[383] = 1;
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
}

```

## disassembly

```asm
0x180072590  mov     [rsp+arg_8], rbx
0x180072595  mov     [rsp+arg_10], rsi
0x18007259a  push    rdi
0x18007259b  sub     rsp, 30h
0x18007259f  mov     eax, [rcx]
0x1800725a1  xor     ebx, ebx
0x1800725a3  mov     [rsp+38h+arg_0], ebx
0x1800725a7  mov     rdi, rcx
0x1800725aa  mov     esi, 2A6h
0x1800725af  test    al, 10h
0x1800725b1  jz      loc_180072660
0x1800725b7  mov     edx, esi
0x1800725b9  mov     ecx, 102h
0x1800725be  mov     r8d, 41746D73h
0x1800725c4  call    cs:__imp_ExAllocatePool2
0x1800725cb  nop     dword ptr [rax+rax+00h]
0x1800725d0  mov     rbx, rax
0x1800725d3  test    rax, rax
0x1800725d6  jz      loc_180072660
0x1800725dc  mov     rcx, [rdi+0BE0h]
0x1800725e3  lea     rax, [rsp+38h+arg_0]
0x1800725e8  mov     [rsp+38h+var_10], rax
0x1800725ed  lea     rdx, aB_0; "`b"
0x1800725f4  mov     r9, rbx
0x1800725f7  mov     [rsp+38h+var_18], esi
0x1800725fb  mov     r8d, 1
0x180072601  call    cs:__imp_SeQuerySecurityAttributesToken
0x180072608  nop     dword ptr [rax+rax+00h]
0x18007260d  cmp     eax, 0C0000023h
0x180072612  jnz     short loc_180072634
0x180072614  cmp     esi, [rsp+38h+arg_0]
0x180072618  jnb     short loc_180072660
0x18007261a  mov     esi, [rsp+38h+arg_0]
0x18007261e  mov     edx, 41746D73h; Tag
0x180072623  mov     rcx, rbx; P
0x180072626  call    cs:__imp_ExFreePoolWithTag
0x18007262d  nop     dword ptr [rax+rax+00h]
0x180072632  jmp     short loc_1800725B7
0x180072634  test    eax, eax
0x180072636  js      short loc_180072660
0x180072638  cmp     dword ptr [rbx+4], 0
0x18007263c  jbe     short loc_180072660
0x18007263e  mov     rax, [rbx+8]
0x180072642  cmp     word ptr [rax+10h], 10h
0x180072647  jnz     short loc_180072660
0x180072649  mov     rax, [rax+20h]
0x18007264d  cmp     dword ptr [rax+8], 20Ch
0x180072654  jnz     short loc_180072660
0x180072656  mov     dword ptr [rdi+5F8h], 1
0x180072660  mov     dword ptr [rdi+5FCh], 1
0x18007266a  test    rbx, rbx
0x18007266d  jz      short loc_180072683
0x18007266f  mov     edx, 41746D73h; Tag
0x180072674  mov     rcx, rbx; P
0x180072677  call    cs:__imp_ExFreePoolWithTag
0x18007267e  nop     dword ptr [rax+rax+00h]
0x180072683  mov     rbx, [rsp+38h+arg_8]
0x180072688  mov     rsi, [rsp+38h+arg_10]
0x18007268d  add     rsp, 30h
0x180072691  pop     rdi
0x180072692  retn
```
