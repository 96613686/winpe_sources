# HvSocketXboxCreatePipe

- ea: `0x140025c64`
- end: `0x140025d4d`
- name: `HvSocketXboxCreatePipe`
- size: `233`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140025b20`
- `0x1400263d0`

## callees

- `0x1400098f4`
- `0x14000bfe0`
- `0x140025c64`

## string_xrefs

- `0x140025cbf`: `HvSocketXboxCreatePipe`

## pseudocode

```c
__int64 __fastcall HvSocketXboxCreatePipe(__int64 a1, char a2, _QWORD *a3)
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
      HvSocketXboxIndicateReceive);
    (*(void (__fastcall **)(_QWORD, __int64 (__fastcall *)(), __int64 (__fastcall *)()))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL)
                                                                                       + 32LL))(
      *a3,
      VmbusTlXPartOnPipePause,
      HvSocketXboxOnPipeClose);
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceEndpointGuidError((const int *)"HvSocketXboxCreatePipe", 517, (unsigned int)v6, v4, v4 + 140);
  }
  return v7;
}

```

## disassembly

```asm
0x140025c64  mov     [rsp+arg_0], rbx
0x140025c69  mov     [rsp+arg_8], rsi
0x140025c6e  push    rdi
0x140025c6f  sub     rsp, 30h
0x140025c73  mov     rax, [rcx+2E0h]
0x140025c7a  mov     r10b, dl
0x140025c7d  mov     rbx, rcx
0x140025c80  mov     rdx, r8
0x140025c83  mov     cl, r10b
0x140025c86  mov     rsi, r8
0x140025c89  mov     r9, [rax+1F8h]
0x140025c90  mov     rax, [r9]
0x140025c93  call    _guard_dispatch_icall
0x140025c98  mov     edi, eax
0x140025c9a  test    eax, eax
0x140025c9c  jns     short loc_140025CD2
0x140025c9e  mov     ecx, cs:dword_140013058
0x140025ca4  cmp     ecx, 2
0x140025ca7  jbe     loc_140025D3A
0x140025cad  lea     rcx, [rbx+8Ch]
0x140025cb4  mov     r9, rbx
0x140025cb7  mov     [rsp+38h+var_18], rcx
0x140025cbc  mov     r8d, eax
0x140025cbf  lea     rcx, aHvsocketxboxcr; "HvSocketXboxCreatePipe"
0x140025cc6  mov     edx, 205h
0x140025ccb  call    HvsocketTraceEndpointGuidError
0x140025cd0  jmp     short loc_140025D3A
0x140025cd2  mov     rax, [rbx+2E0h]
0x140025cd9  mov     rdx, rbx
0x140025cdc  mov     rcx, [rax+1F8h]
0x140025ce3  mov     rax, [rcx+10h]
0x140025ce7  mov     rcx, [rsi]
0x140025cea  call    _guard_dispatch_icall
0x140025cef  mov     rax, [rbx+2E0h]
0x140025cf6  lea     r8, HvSocketXboxIndicateReceive
0x140025cfd  mov     dl, 1
0x140025cff  mov     rcx, [rax+1F8h]
0x140025d06  mov     rax, [rcx+18h]
0x140025d0a  mov     rcx, [rsi]
0x140025d0d  call    _guard_dispatch_icall
0x140025d12  mov     rax, [rbx+2E0h]
0x140025d19  lea     r8, HvSocketXboxOnPipeClose
0x140025d20  lea     rdx, VmbusTlXPartOnPipePause
0x140025d27  mov     rcx, [rax+1F8h]
0x140025d2e  mov     rax, [rcx+20h]
0x140025d32  mov     rcx, [rsi]
0x140025d35  call    _guard_dispatch_icall
0x140025d3a  mov     rbx, [rsp+38h+arg_0]
0x140025d3f  mov     eax, edi
0x140025d41  mov     rsi, [rsp+38h+arg_8]
0x140025d46  add     rsp, 30h
0x140025d4a  pop     rdi
0x140025d4b  retn
```
