# VmbusTlCreateWildcardDescriptor

- ea: `0x140026734`
- end: `0x1400267c6`
- name: `VmbusTlCreateWildcardDescriptor`
- size: `146`
- prototype: `__int64 __fastcall(_OWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140023b40`
- `0x140026868`

## callees

- `0x140001350`
- `0x140009df0`
- `0x140026734`

## string_xrefs

- `0x140026777`: `VmbusTlCreateWildcardDescriptor`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateWildcardDescriptor(_OWORD *a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v4 = VmbusTlCreateObject(0xBu, 136, &v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = v8;
    *a2 = v8;
    *(_QWORD *)(v6 + 80) = VmbusTlWildcardDescriptorDestructor;
    *(_OWORD *)(v6 + 112) = *a1;
    *(_QWORD *)(v6 + 128) = 0;
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceGuidError((const int *)"VmbusTlCreateWildcardDescriptor", 59, (unsigned int)v4, (__int64)a1);
  }
  return v5;
}

```

## disassembly

```asm
0x140026734  mov     rax, rsp
0x140026737  mov     [rax+8], rbx
0x14002673b  mov     [rax+10h], rsi
0x14002673f  push    rdi
0x140026740  sub     rsp, 20h
0x140026744  mov     rsi, rdx
0x140026747  mov     qword ptr [rax+18h], 0
0x14002674f  mov     edx, 88h
0x140026754  lea     r8, [rax+18h]
0x140026758  mov     rdi, rcx
0x14002675b  lea     ecx, [rdx-7Dh]
0x14002675e  call    VmbusTlCreateObject
0x140026763  mov     ebx, eax
0x140026765  test    eax, eax
0x140026767  jns     short loc_14002678D
0x140026769  mov     edx, cs:dword_140013058
0x14002676f  cmp     edx, 2
0x140026772  jbe     short loc_1400267B3
0x140026774  mov     r9, rdi
0x140026777  lea     rcx, aVmbustlcreatew; "VmbusTlCreateWildcardDescriptor"
0x14002677e  mov     r8d, eax
0x140026781  mov     edx, 3Bh ; ';'
0x140026786  call    HvsocketTraceGuidError
0x14002678b  jmp     short loc_1400267B3
0x14002678d  mov     rax, [rsp+28h+arg_10]
0x140026792  lea     rcx, VmbusTlWildcardDescriptorDestructor
0x140026799  mov     [rsi], rax
0x14002679c  mov     [rax+50h], rcx
0x1400267a0  movups  xmm0, xmmword ptr [rdi]
0x1400267a3  movdqu  xmmword ptr [rax+70h], xmm0
0x1400267a8  mov     qword ptr [rax+80h], 0
0x1400267b3  mov     rsi, [rsp+28h+arg_8]
0x1400267b8  mov     eax, ebx
0x1400267ba  mov     rbx, [rsp+28h+arg_0]
0x1400267bf  add     rsp, 20h
0x1400267c3  pop     rdi
0x1400267c4  retn
```
