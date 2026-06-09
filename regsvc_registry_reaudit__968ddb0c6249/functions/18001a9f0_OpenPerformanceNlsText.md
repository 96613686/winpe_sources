# OpenPerformanceNlsText

- ea: `0x18001a9f0`
- end: `0x18001aa4c`
- name: `OpenPerformanceNlsText`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a9f0`
- `0x18001ac84`
- `0x18001acf4`

## pseudocode

```c
__int64 __fastcall OpenPerformanceNlsText(__int64 a1, __int64 a2, _QWORD *a3)
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
    *v8 = -2147483552;
    *a3 = v5;
  }
  if ( v6 )
    RegSvcContextFree(v6);
  return v4;
}

```

## disassembly

```asm
0x18001a9f0  mov     [rsp+arg_0], rbx
0x18001a9f5  push    rdi
0x18001a9f6  sub     rsp, 20h
0x18001a9fa  lea     rcx, [rsp+28h+arg_10]
0x18001a9ff  mov     [rsp+28h+arg_10], 0
0x18001aa08  mov     rdi, r8
0x18001aa0b  mov     qword ptr [r8], 0
0x18001aa12  call    RegSvcContextAllocate
0x18001aa17  mov     ebx, eax
0x18001aa19  test    eax, eax
0x18001aa1b  jnz     short loc_18001AA30
0x18001aa1d  mov     rax, [rsp+28h+arg_10]
0x18001aa22  xor     ecx, ecx
0x18001aa24  mov     qword ptr [rax], 0FFFFFFFF80000060h
0x18001aa2b  mov     [rdi], rax
0x18001aa2e  jmp     short loc_18001AA35
0x18001aa30  mov     rcx, [rsp+28h+arg_10]
0x18001aa35  test    rcx, rcx
0x18001aa38  jz      short loc_18001AA3F
0x18001aa3a  call    RegSvcContextFree
0x18001aa3f  mov     eax, ebx
0x18001aa41  mov     rbx, [rsp+28h+arg_0]
0x18001aa46  add     rsp, 20h
0x18001aa4a  pop     rdi
0x18001aa4b  retn
```
