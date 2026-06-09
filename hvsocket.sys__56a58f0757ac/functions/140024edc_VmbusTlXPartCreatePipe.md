# VmbusTlXPartCreatePipe

- ea: `0x140024edc`
- end: `0x140024fc5`
- name: `VmbusTlXPartCreatePipe`
- size: `233`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140024c3c`
- `0x1400256b0`

## callees

- `0x1400098f4`
- `0x14000bfe0`
- `0x140024edc`

## string_xrefs

- `0x140024f37`: `VmbusTlXPartCreatePipe`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartCreatePipe(__int64 a1, char a2, _QWORD *a3)
{
  __int64 v3; // rax
  __int64 v4; // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx

  v3 = *(_QWORD *)(a1 + 736);
  v4 = a1;
  LOBYTE(a1) = a2;
  v6 = (**(__int64 (__fastcall ***)(__int64, _QWORD *))(v3 + 504))(a1, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL) + 16LL))(*a3, v4);
    LOBYTE(v8) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, __int64 (__fastcall *)(int, int, int, int, __int64)))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL)
                                                                                                 + 24LL))(
      *a3,
      v8,
      VmbusTlXPartIndicateReceive);
    (*(void (__fastcall **)(_QWORD, __int64 (__fastcall *)(), __int64 (__fastcall *)()))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL)
                                                                                       + 32LL))(
      *a3,
      VmbusTlXPartOnPipePause,
      VmbusTlXPartOnPipeClose);
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceEndpointGuidError((const int *)"VmbusTlXPartCreatePipe", 608, (unsigned int)v6, v4, v4 + 140);
  }
  return v7;
}

```

## disassembly

```asm
0x140024edc  mov     [rsp+arg_0], rbx
0x140024ee1  mov     [rsp+arg_8], rsi
0x140024ee6  push    rdi
0x140024ee7  sub     rsp, 30h
0x140024eeb  mov     rax, [rcx+2E0h]
0x140024ef2  mov     r10b, dl
0x140024ef5  mov     rbx, rcx
0x140024ef8  mov     rdx, r8
0x140024efb  mov     cl, r10b
0x140024efe  mov     rsi, r8
0x140024f01  mov     r9, [rax+1F8h]
0x140024f08  mov     rax, [r9]
0x140024f0b  call    _guard_dispatch_icall
0x140024f10  mov     edi, eax
0x140024f12  test    eax, eax
0x140024f14  jns     short loc_140024F4A
0x140024f16  mov     ecx, cs:dword_140013058
0x140024f1c  cmp     ecx, 2
0x140024f1f  jbe     loc_140024FB2
0x140024f25  lea     rcx, [rbx+8Ch]
0x140024f2c  mov     r9, rbx
0x140024f2f  mov     [rsp+38h+var_18], rcx
0x140024f34  mov     r8d, eax
0x140024f37  lea     rcx, aVmbustlxpartcr; "VmbusTlXPartCreatePipe"
0x140024f3e  mov     edx, 260h
0x140024f43  call    HvsocketTraceEndpointGuidError
0x140024f48  jmp     short loc_140024FB2
0x140024f4a  mov     rax, [rbx+2E0h]
0x140024f51  mov     rdx, rbx
0x140024f54  mov     rcx, [rax+1F8h]
0x140024f5b  mov     rax, [rcx+10h]
0x140024f5f  mov     rcx, [rsi]
0x140024f62  call    _guard_dispatch_icall
0x140024f67  mov     rax, [rbx+2E0h]
0x140024f6e  lea     r8, VmbusTlXPartIndicateReceive
0x140024f75  mov     dl, 1
0x140024f77  mov     rcx, [rax+1F8h]
0x140024f7e  mov     rax, [rcx+18h]
0x140024f82  mov     rcx, [rsi]
0x140024f85  call    _guard_dispatch_icall
0x140024f8a  mov     rax, [rbx+2E0h]
0x140024f91  lea     r8, VmbusTlXPartOnPipeClose
0x140024f98  lea     rdx, VmbusTlXPartOnPipePause
0x140024f9f  mov     rcx, [rax+1F8h]
0x140024fa6  mov     rax, [rcx+20h]
0x140024faa  mov     rcx, [rsi]
0x140024fad  call    _guard_dispatch_icall
0x140024fb2  mov     rbx, [rsp+38h+arg_0]
0x140024fb7  mov     eax, edi
0x140024fb9  mov     rsi, [rsp+38h+arg_8]
0x140024fbe  add     rsp, 30h
0x140024fc2  pop     rdi
0x140024fc3  retn
```
