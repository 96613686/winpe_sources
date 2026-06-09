# CiCheckSmartScreenClaim

- ea: `0x180073840`
- end: `0x180073944`
- name: `CiCheckSmartScreenClaim`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006466c`
- `0x1800b5098`

## callees

- `0x180073840`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180073874`
- `ntoskrnl!ExAllocatePool2` at `0x180073874`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800738d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073927`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800738d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073927`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800738b1`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800738b1`

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
0x180073840  mov     [rsp+arg_8], rbx
0x180073845  mov     [rsp+arg_10], rsi
0x18007384a  push    rdi
0x18007384b  sub     rsp, 30h
0x18007384f  mov     eax, [rcx]
0x180073851  xor     ebx, ebx
0x180073853  mov     [rsp+38h+arg_0], ebx
0x180073857  mov     rdi, rcx
0x18007385a  mov     esi, 2A6h
0x18007385f  test    al, 10h
0x180073861  jz      loc_180073910
0x180073867  mov     edx, esi
0x180073869  mov     ecx, 102h
0x18007386e  mov     r8d, 41746D73h
0x180073874  call    cs:__imp_ExAllocatePool2
0x18007387b  nop     dword ptr [rax+rax+00h]
0x180073880  mov     rbx, rax
0x180073883  test    rax, rax
0x180073886  jz      loc_180073910
0x18007388c  mov     rcx, [rdi+0BE0h]
0x180073893  lea     rax, [rsp+38h+arg_0]
0x180073898  mov     [rsp+38h+var_10], rax
0x18007389d  lea     rdx, aB_0; "`b"
0x1800738a4  mov     r9, rbx
0x1800738a7  mov     [rsp+38h+var_18], esi
0x1800738ab  mov     r8d, 1
0x1800738b1  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800738b8  nop     dword ptr [rax+rax+00h]
0x1800738bd  cmp     eax, 0C0000023h
0x1800738c2  jnz     short loc_1800738E4
0x1800738c4  cmp     esi, [rsp+38h+arg_0]
0x1800738c8  jnb     short loc_180073910
0x1800738ca  mov     esi, [rsp+38h+arg_0]
0x1800738ce  mov     edx, 41746D73h; Tag
0x1800738d3  mov     rcx, rbx; P
0x1800738d6  call    cs:__imp_ExFreePoolWithTag
0x1800738dd  nop     dword ptr [rax+rax+00h]
0x1800738e2  jmp     short loc_180073867
0x1800738e4  test    eax, eax
0x1800738e6  js      short loc_180073910
0x1800738e8  cmp     dword ptr [rbx+4], 0
0x1800738ec  jbe     short loc_180073910
0x1800738ee  mov     rax, [rbx+8]
0x1800738f2  cmp     word ptr [rax+10h], 10h
0x1800738f7  jnz     short loc_180073910
0x1800738f9  mov     rax, [rax+20h]
0x1800738fd  cmp     dword ptr [rax+8], 20Ch
0x180073904  jnz     short loc_180073910
0x180073906  mov     dword ptr [rdi+5F8h], 1
0x180073910  mov     dword ptr [rdi+5FCh], 1
0x18007391a  test    rbx, rbx
0x18007391d  jz      short loc_180073933
0x18007391f  mov     edx, 41746D73h; Tag
0x180073924  mov     rcx, rbx; P
0x180073927  call    cs:__imp_ExFreePoolWithTag
0x18007392e  nop     dword ptr [rax+rax+00h]
0x180073933  mov     rbx, [rsp+38h+arg_8]
0x180073938  mov     rsi, [rsp+38h+arg_10]
0x18007393d  add     rsp, 30h
0x180073941  pop     rdi
0x180073942  retn
```
