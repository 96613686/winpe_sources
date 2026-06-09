# DeleteSecurityContextMarshalParams

- ea: `0x1800265e0`
- end: `0x180026669`
- name: `DeleteSecurityContextMarshalParams`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800265e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18002660f`
- `ntoskrnl!ExAllocatePool2` at `0x18002660f`

## pseudocode

```c
__int64 __fastcall DeleteSecurityContextMarshalParams(_QWORD *a1, __int64 *a2, _DWORD *a3)
{
  __int64 Pool2; // rax
  _QWORD *v7; // rdx
  __int64 result; // rax

  *a3 = 80;
  Pool2 = ExAllocatePool2(256, 80, 1131180883);
  if ( Pool2 )
  {
    *a2 = Pool2;
    v7 = (_QWORD *)a1[5];
    if ( v7 )
    {
      *(_QWORD *)(Pool2 + 56) = *v7;
      *(_QWORD *)(Pool2 + 64) = v7[1];
    }
    *(_DWORD *)(Pool2 + 72) = *a1 != 0;
    return 0;
  }
  else
  {
    result = 3221225626LL;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800265e0  mov     [rsp+arg_0], rbx
0x1800265e5  mov     [rsp+arg_8], rsi
0x1800265ea  push    rdi
0x1800265eb  sub     rsp, 20h
0x1800265ef  mov     rsi, r8
0x1800265f2  mov     dword ptr [r8], 50h ; 'P'
0x1800265f9  mov     rdi, rdx
0x1800265fc  mov     rbx, rcx
0x1800265ff  mov     edx, 50h ; 'P'
0x180026604  mov     ecx, 100h
0x180026609  mov     r8d, 436C7353h
0x18002660f  call    cs:__imp_ExAllocatePool2
0x180026616  nop     dword ptr [rax+rax+00h]
0x18002661b  test    rax, rax
0x18002661e  jz      short loc_18002665E
0x180026620  mov     [rdi], rax
0x180026623  mov     rdx, [rbx+28h]
0x180026627  test    rdx, rdx
0x18002662a  jz      short loc_18002663B
0x18002662c  mov     rcx, [rdx]
0x18002662f  mov     [rax+38h], rcx
0x180026633  mov     rcx, [rdx+8]
0x180026637  mov     [rax+40h], rcx
0x18002663b  xor     ecx, ecx
0x18002663d  mov     edx, 1
0x180026642  cmp     [rbx], rcx
0x180026645  cmovnz  ecx, edx
0x180026648  mov     [rax+48h], ecx
0x18002664b  xor     eax, eax
0x18002664d  mov     rbx, [rsp+28h+arg_0]
0x180026652  mov     rsi, [rsp+28h+arg_8]
0x180026657  add     rsp, 20h
0x18002665b  pop     rdi
0x18002665c  retn
0x18002665e  xor     ecx, ecx
0x180026660  mov     eax, 0C000009Ah
0x180026665  mov     [rsi], ecx
0x180026667  jmp     short loc_18002664D
```
