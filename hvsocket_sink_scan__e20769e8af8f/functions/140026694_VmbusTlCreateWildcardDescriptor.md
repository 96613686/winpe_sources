# VmbusTlCreateWildcardDescriptor

- ea: `0x140026694`
- end: `0x140026726`
- name: `VmbusTlCreateWildcardDescriptor`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140023b40`
- `0x1400267c8`

## callees

- `0x140001350`
- `0x140009df0`
- `0x140026694`

## string_xrefs

- `0x1400266d7`: `VmbusTlCreateWildcardDescriptor`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateWildcardDescriptor(_OWORD *a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int *v6; // rax
  int *v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v4 = VmbusTlCreateObject(11, 0x88u, &v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = v8;
    *a2 = v8;
    *((_QWORD *)v6 + 10) = VmbusTlWildcardDescriptorDestructor;
    *((_OWORD *)v6 + 7) = *a1;
    *((_QWORD *)v6 + 16) = 0;
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceGuidError("VmbusTlCreateWildcardDescriptor", 59, (unsigned int)v4, a1);
  }
  return v5;
}

```

## disassembly

```asm
0x140026694  mov     rax, rsp
0x140026697  mov     [rax+8], rbx
0x14002669b  mov     [rax+10h], rsi
0x14002669f  push    rdi
0x1400266a0  sub     rsp, 20h
0x1400266a4  mov     rsi, rdx
0x1400266a7  mov     qword ptr [rax+18h], 0
0x1400266af  mov     edx, 88h
0x1400266b4  lea     r8, [rax+18h]
0x1400266b8  mov     rdi, rcx
0x1400266bb  lea     ecx, [rdx-7Dh]
0x1400266be  call    VmbusTlCreateObject
0x1400266c3  mov     ebx, eax
0x1400266c5  test    eax, eax
0x1400266c7  jns     short loc_1400266ED
0x1400266c9  mov     edx, cs:dword_140013058
0x1400266cf  cmp     edx, 2
0x1400266d2  jbe     short loc_140026713
0x1400266d4  mov     r9, rdi
0x1400266d7  lea     rcx, aVmbustlcreatew; "VmbusTlCreateWildcardDescriptor"
0x1400266de  mov     r8d, eax
0x1400266e1  mov     edx, 3Bh ; ';'
0x1400266e6  call    HvsocketTraceGuidError
0x1400266eb  jmp     short loc_140026713
0x1400266ed  mov     rax, [rsp+28h+arg_10]
0x1400266f2  lea     rcx, VmbusTlWildcardDescriptorDestructor
0x1400266f9  mov     [rsi], rax
0x1400266fc  mov     [rax+50h], rcx
0x140026700  movups  xmm0, xmmword ptr [rdi]
0x140026703  movdqu  xmmword ptr [rax+70h], xmm0
0x140026708  mov     qword ptr [rax+80h], 0
0x140026713  mov     rsi, [rsp+28h+arg_8]
0x140026718  mov     eax, ebx
0x14002671a  mov     rbx, [rsp+28h+arg_0]
0x14002671f  add     rsp, 20h
0x140026723  pop     rdi
0x140026724  retn
```
