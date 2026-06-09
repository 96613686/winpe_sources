# VmbusTlXPartCreatePipe

- ea: `0x140024e3c`
- end: `0x140024f25`
- name: `VmbusTlXPartCreatePipe`
- size: `233`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140024b9c`
- `0x140025610`

## callees

- `0x1400098f4`
- `0x14000bfe0`
- `0x140024e3c`

## string_xrefs

- `0x140024e97`: `VmbusTlXPartCreatePipe`

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
    (*(void (__fastcall **)(_QWORD, __int64, __int64 (__fastcall *)(__int64, __int64, int, unsigned int, __int64)))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL) + 24LL))(
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
    HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlXPartCreatePipe", 608, v6, v4, v4 + 140);
  }
  return v7;
}

```

## disassembly

```asm
0x140024e3c  mov     [rsp+arg_0], rbx
0x140024e41  mov     [rsp+arg_8], rsi
0x140024e46  push    rdi
0x140024e47  sub     rsp, 30h
0x140024e4b  mov     rax, [rcx+2E0h]
0x140024e52  mov     r10b, dl
0x140024e55  mov     rbx, rcx
0x140024e58  mov     rdx, r8
0x140024e5b  mov     cl, r10b
0x140024e5e  mov     rsi, r8
0x140024e61  mov     r9, [rax+1F8h]
0x140024e68  mov     rax, [r9]
0x140024e6b  call    _guard_dispatch_icall
0x140024e70  mov     edi, eax
0x140024e72  test    eax, eax
0x140024e74  jns     short loc_140024EAA
0x140024e76  mov     ecx, cs:dword_140013058
0x140024e7c  cmp     ecx, 2
0x140024e7f  jbe     loc_140024F12
0x140024e85  lea     rcx, [rbx+8Ch]
0x140024e8c  mov     r9, rbx
0x140024e8f  mov     [rsp+38h+var_18], rcx
0x140024e94  mov     r8d, eax
0x140024e97  lea     rcx, aVmbustlxpartcr; "VmbusTlXPartCreatePipe"
0x140024e9e  mov     edx, 260h
0x140024ea3  call    HvsocketTraceEndpointGuidError
0x140024ea8  jmp     short loc_140024F12
0x140024eaa  mov     rax, [rbx+2E0h]
0x140024eb1  mov     rdx, rbx
0x140024eb4  mov     rcx, [rax+1F8h]
0x140024ebb  mov     rax, [rcx+10h]
0x140024ebf  mov     rcx, [rsi]
0x140024ec2  call    _guard_dispatch_icall
0x140024ec7  mov     rax, [rbx+2E0h]
0x140024ece  lea     r8, VmbusTlXPartIndicateReceive
0x140024ed5  mov     dl, 1
0x140024ed7  mov     rcx, [rax+1F8h]
0x140024ede  mov     rax, [rcx+18h]
0x140024ee2  mov     rcx, [rsi]
0x140024ee5  call    _guard_dispatch_icall
0x140024eea  mov     rax, [rbx+2E0h]
0x140024ef1  lea     r8, VmbusTlXPartOnPipeClose
0x140024ef8  lea     rdx, VmbusTlXPartOnPipePause
0x140024eff  mov     rcx, [rax+1F8h]
0x140024f06  mov     rax, [rcx+20h]
0x140024f0a  mov     rcx, [rsi]
0x140024f0d  call    _guard_dispatch_icall
0x140024f12  mov     rbx, [rsp+38h+arg_0]
0x140024f17  mov     eax, edi
0x140024f19  mov     rsi, [rsp+38h+arg_8]
0x140024f1e  add     rsp, 30h
0x140024f22  pop     rdi
0x140024f23  retn
```
