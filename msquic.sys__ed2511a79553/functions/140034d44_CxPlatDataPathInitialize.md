# CxPlatDataPathInitialize

- ea: `0x140034d44`
- end: `0x140034e00`
- name: `CxPlatDataPathInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140028a3c`

## callees

- `0x140034d44`
- `0x14003aea0`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140034db5`
- `ntoskrnl!_snprintf_s` at `0x140034db5`

## string_xrefs

- `0x140034da1`: `[  dp] Failed to initialize datapath, status:%d`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathInitialize(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  if ( a6 )
  {
    v7 = DataPathInitialize(a1, a2, a3, a4, a5, a6);
    v6 = v7;
    if ( v7 >= 0 )
    {
      *(_QWORD *)(*a6 + 64LL) = 0;
    }
    else if ( byte_14005C48E < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[  dp] Failed to initialize datapath, status:%d", v7);
      McTemplateU0s_EtwWriteTransfer(v8, QuicLogVerbose, DstBuf);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x140034d44  mov     [rsp+arg_0], rbx
0x140034d49  push    rdi
0x140034d4a  sub     rsp, 0C0h
0x140034d51  mov     rax, cs:__security_cookie
0x140034d58  xor     rax, rsp
0x140034d5b  mov     [rsp+0C8h+var_18], rax
0x140034d63  mov     rdi, [rsp+0C8h+arg_28]
0x140034d6b  mov     rax, [rsp+0C8h+arg_20]
0x140034d73  test    rdi, rdi
0x140034d76  jnz     short loc_140034D7F
0x140034d78  mov     ebx, 0C000000Dh
0x140034d7d  jmp     short loc_140034DDC
0x140034d7f  mov     [rsp+0C8h+var_A0], rdi
0x140034d84  mov     [rsp+0C8h+var_A8], rax
0x140034d89  call    DataPathInitialize
0x140034d8e  mov     ebx, eax
0x140034d90  test    eax, eax
0x140034d92  jns     short loc_140034DD4
0x140034d94  mov     edx, 80h; SizeInBytes
0x140034d99  test    cs:byte_14005C48E, dl
0x140034d9f  jz      short loc_140034DDC
0x140034da1  lea     r9, aDpFailedToInit; "[  dp] Failed to initialize datapath, s"...
0x140034da8  mov     dword ptr [rsp+0C8h+var_A8], eax
0x140034dac  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140034db0  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140034db5  call    cs:__imp__snprintf_s
0x140034dbc  nop     dword ptr [rax+rax+00h]
0x140034dc1  lea     r8, [rsp+0C8h+DstBuf]
0x140034dc6  lea     rdx, QuicLogVerbose
0x140034dcd  call    McTemplateU0s_EtwWriteTransfer
0x140034dd2  jmp     short loc_140034DDC
0x140034dd4  mov     rax, [rdi]
0x140034dd7  and     qword ptr [rax+40h], 0
0x140034ddc  mov     eax, ebx
0x140034dde  mov     rcx, [rsp+0C8h+var_18]
0x140034de6  xor     rcx, rsp; StackCookie
0x140034de9  call    __security_check_cookie
0x140034dee  mov     rbx, [rsp+0C8h+arg_0]
0x140034df6  add     rsp, 0C0h
0x140034dfd  pop     rdi
0x140034dfe  retn
```
