# HvSocketXboxCreatePipe

- ea: `0x140025bc4`
- end: `0x140025cad`
- name: `HvSocketXboxCreatePipe`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140025a80`
- `0x140026330`

## callees

- `0x1400098f4`
- `0x14000bfe0`
- `0x140025bc4`

## string_xrefs

- `0x140025c1f`: `HvSocketXboxCreatePipe`

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
    (*(void (__fastcall **)(_QWORD, __int64, __int64 (__fastcall *)(__int64, __int64, int, unsigned int, __int64)))(*(_QWORD *)(*(_QWORD *)(v4 + 736) + 504LL) + 24LL))(
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
    HvsocketTraceEndpointGuidError((unsigned int)"HvSocketXboxCreatePipe", 517, v6, v4, v4 + 140);
  }
  return v7;
}

```

## disassembly

```asm
0x140025bc4  mov     [rsp+arg_0], rbx
0x140025bc9  mov     [rsp+arg_8], rsi
0x140025bce  push    rdi
0x140025bcf  sub     rsp, 30h
0x140025bd3  mov     rax, [rcx+2E0h]
0x140025bda  mov     r10b, dl
0x140025bdd  mov     rbx, rcx
0x140025be0  mov     rdx, r8
0x140025be3  mov     cl, r10b
0x140025be6  mov     rsi, r8
0x140025be9  mov     r9, [rax+1F8h]
0x140025bf0  mov     rax, [r9]
0x140025bf3  call    _guard_dispatch_icall
0x140025bf8  mov     edi, eax
0x140025bfa  test    eax, eax
0x140025bfc  jns     short loc_140025C32
0x140025bfe  mov     ecx, cs:dword_140013058
0x140025c04  cmp     ecx, 2
0x140025c07  jbe     loc_140025C9A
0x140025c0d  lea     rcx, [rbx+8Ch]
0x140025c14  mov     r9, rbx
0x140025c17  mov     [rsp+38h+var_18], rcx
0x140025c1c  mov     r8d, eax
0x140025c1f  lea     rcx, aHvsocketxboxcr; "HvSocketXboxCreatePipe"
0x140025c26  mov     edx, 205h
0x140025c2b  call    HvsocketTraceEndpointGuidError
0x140025c30  jmp     short loc_140025C9A
0x140025c32  mov     rax, [rbx+2E0h]
0x140025c39  mov     rdx, rbx
0x140025c3c  mov     rcx, [rax+1F8h]
0x140025c43  mov     rax, [rcx+10h]
0x140025c47  mov     rcx, [rsi]
0x140025c4a  call    _guard_dispatch_icall
0x140025c4f  mov     rax, [rbx+2E0h]
0x140025c56  lea     r8, HvSocketXboxIndicateReceive
0x140025c5d  mov     dl, 1
0x140025c5f  mov     rcx, [rax+1F8h]
0x140025c66  mov     rax, [rcx+18h]
0x140025c6a  mov     rcx, [rsi]
0x140025c6d  call    _guard_dispatch_icall
0x140025c72  mov     rax, [rbx+2E0h]
0x140025c79  lea     r8, HvSocketXboxOnPipeClose
0x140025c80  lea     rdx, VmbusTlXPartOnPipePause
0x140025c87  mov     rcx, [rax+1F8h]
0x140025c8e  mov     rax, [rcx+20h]
0x140025c92  mov     rcx, [rsi]
0x140025c95  call    _guard_dispatch_icall
0x140025c9a  mov     rbx, [rsp+38h+arg_0]
0x140025c9f  mov     eax, edi
0x140025ca1  mov     rsi, [rsp+38h+arg_8]
0x140025ca6  add     rsp, 30h
0x140025caa  pop     rdi
0x140025cab  retn
```
