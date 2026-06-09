# OpenPerformanceText

- ea: `0x18001aa60`
- end: `0x18001aabc`
- name: `OpenPerformanceText`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001aa60`
- `0x18001ac84`
- `0x18001acf4`

## pseudocode

```c
__int64 __fastcall OpenPerformanceText(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  *a3 = 0;
  v4 = RegSvcContextAllocate(&v8);
  if ( v4 )
  {
    v6 = v8;
  }
  else
  {
    v5 = v8;
    v6 = 0;
    *v8 = -2147483568;
    *a3 = v5;
  }
  if ( v6 )
    RegSvcContextFree(v6);
  return v4;
}

```

## disassembly

```asm
0x18001aa60  mov     [rsp+arg_0], rbx
0x18001aa65  push    rdi
0x18001aa66  sub     rsp, 20h
0x18001aa6a  lea     rcx, [rsp+28h+arg_10]
0x18001aa6f  mov     [rsp+28h+arg_10], 0
0x18001aa78  mov     rdi, r8
0x18001aa7b  mov     qword ptr [r8], 0
0x18001aa82  call    RegSvcContextAllocate
0x18001aa87  mov     ebx, eax
0x18001aa89  test    eax, eax
0x18001aa8b  jnz     short loc_18001AAA0
0x18001aa8d  mov     rax, [rsp+28h+arg_10]
0x18001aa92  xor     ecx, ecx
0x18001aa94  mov     qword ptr [rax], 0FFFFFFFF80000050h
0x18001aa9b  mov     [rdi], rax
0x18001aa9e  jmp     short loc_18001AAA5
0x18001aaa0  mov     rcx, [rsp+28h+arg_10]
0x18001aaa5  test    rcx, rcx
0x18001aaa8  jz      short loc_18001AAAF
0x18001aaaa  call    RegSvcContextFree
0x18001aaaf  mov     eax, ebx
0x18001aab1  mov     rbx, [rsp+28h+arg_0]
0x18001aab6  add     rsp, 20h
0x18001aaba  pop     rdi
0x18001aabb  retn
```
