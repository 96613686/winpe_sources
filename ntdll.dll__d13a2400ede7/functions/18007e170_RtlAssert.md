# RtlAssert

- ea: `0x18007e170`
- end: `0x18007e28f`
- name: `RtlAssert`
- size: `287`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18001ae70`
- `0x18001bcb0`
- `0x18007e01c`

## callees

- `0x18001a080`
- `0x18007e170`
- `0x18007e298`
- `0x180126650`
- `0x18013b400`
- `0x18015f060`
- `0x18015f540`
- `0x180162810`

## string_xrefs

- `0x18007e1ec`: `Break repeatedly, break Once, Ignore, terminate Process, or terminate Thread (boipt)? `

## pseudocode

```c
__int64 __fastcall RtlAssert(const char *a1, const char *a2, int a3, const char *a4)
{
  __int64 result; // rax
  bool v9; // zf
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  char v13[16]; // [rsp+40h] [rbp-518h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+50h] [rbp-508h] BYREF

  RtlCaptureContext(&ContextRecord);
  if ( !a4 )
    a4 = byte_180175FF3;
  while ( 1 )
  {
    DbgPrintEx(101, 0, "\n*** Assertion failed: %s%s\n***   Source File: %s, line %ld\n\n", a4, a1, a2, a3);
    result = RtlIsAnyDebuggerPresent();
    if ( !(_BYTE)result )
      return result;
    result = DbgPrompt("Break repeatedly, break Once, Ignore, terminate Process, or terminate Thread (boipt)? ", v13, 2);
    if ( !(_DWORD)result )
    {
      __debugbreak();
      return ZwTerminateProcess(-1, 3221225473LL);
    }
    if ( v13[0] > 98 )
    {
      v10 = v13[0] - 105;
      v9 = v13[0] == 105;
    }
    else
    {
      if ( v13[0] == 98 || v13[0] == 66 )
        goto LABEL_15;
      v10 = v13[0] - 73;
      v9 = v13[0] == 73;
    }
    if ( v9 )
      return result;
    v11 = v10 - 6;
    if ( !v11 )
    {
LABEL_15:
      DbgPrintEx(101, 0, "Execute '.cxr %p' to dump context\n", &ContextRecord);
      __debugbreak();
    }
    v12 = v11 - 1;
    if ( !v12 )
      return ZwTerminateProcess(-1, 3221225473LL);
    if ( v12 == 4 )
      NtTerminateThread(-2, 3221225473LL);
  }
}

```

## disassembly

```asm
0x18007e170  push    rbx
0x18007e172  push    rbp
0x18007e173  push    rsi
0x18007e174  push    rdi
0x18007e175  sub     rsp, 538h
0x18007e17c  mov     rax, cs:__security_cookie
0x18007e183  xor     rax, rsp
0x18007e186  mov     [rsp+558h+var_38], rax
0x18007e18e  mov     rdi, rcx
0x18007e191  mov     rbx, r9
0x18007e194  lea     rcx, [rsp+558h+ContextRecord]; ContextRecord
0x18007e199  mov     ebp, r8d
0x18007e19c  mov     rsi, rdx
0x18007e19f  call    RtlCaptureContext
0x18007e1a4  test    rbx, rbx
0x18007e1a7  lea     rax, byte_180175FF3
0x18007e1ae  cmovz   rbx, rax
0x18007e1b2  xor     edx, edx
0x18007e1b4  mov     [rsp+558h+var_528], ebp
0x18007e1b8  mov     [rsp+558h+var_530], rsi
0x18007e1bd  lea     r8, aAssertionFaile; "\n*** Assertion failed: %s%s\n***   Sou"...
0x18007e1c4  mov     r9, rbx
0x18007e1c7  mov     [rsp+558h+var_538], rdi
0x18007e1cc  lea     ecx, [rdx+65h]
0x18007e1cf  call    DbgPrintEx
0x18007e1d4  call    RtlIsAnyDebuggerPresent
0x18007e1d9  test    al, al
0x18007e1db  jz      loc_18007E272
0x18007e1e1  mov     r8d, 2
0x18007e1e7  lea     rdx, [rsp+558h+var_518]
0x18007e1ec  lea     rcx, aBreakRepeatedl_0; "Break repeatedly, break Once, Ignore, t"...
0x18007e1f3  call    DbgPrompt
0x18007e1f8  test    eax, eax
0x18007e1fa  jz      short loc_18007E263
0x18007e1fc  movsx   ecx, [rsp+558h+var_518]
0x18007e201  cmp     ecx, 62h ; 'b'
0x18007e204  jg      short loc_18007E212
0x18007e206  jz      short loc_18007E23C
0x18007e208  sub     ecx, 42h ; 'B'
0x18007e20b  jz      short loc_18007E23C
0x18007e20d  sub     ecx, 7
0x18007e210  jmp     short loc_18007E215
0x18007e212  sub     ecx, 69h ; 'i'
0x18007e215  jz      short loc_18007E272
0x18007e217  sub     ecx, 6
0x18007e21a  jz      short loc_18007E23C
0x18007e21c  sub     ecx, 1
0x18007e21f  jz      short loc_18007E264
0x18007e221  cmp     ecx, 4
0x18007e224  jnz     short loc_18007E1B2
0x18007e226  mov     edx, 0C0000001h
0x18007e22b  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18007e232  call    NtTerminateThread
0x18007e237  jmp     loc_18007E1B2
0x18007e23c  xor     edx, edx
0x18007e23e  lea     r9, [rsp+558h+ContextRecord]
0x18007e243  lea     r8, aExecuteCxrPToD; "Execute '.cxr %p' to dump context\n"
0x18007e24a  lea     ecx, [rdx+65h]
0x18007e24d  call    DbgPrintEx
0x18007e252  int     3; Trap to Debugger
0x18007e253  mov     al, [rsp+558h+var_518]
0x18007e257  sub     al, 4Fh ; 'O'
0x18007e259  test    al, 0DFh
0x18007e25b  jnz     loc_18007E1B2
0x18007e261  jmp     short loc_18007E272
0x18007e263  int     3; Trap to Debugger
0x18007e264  mov     edx, 0C0000001h
0x18007e269  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007e26d  call    ZwTerminateProcess
0x18007e272  mov     rcx, [rsp+558h+var_38]
0x18007e27a  xor     rcx, rsp; StackCookie
0x18007e27d  call    __security_check_cookie
0x18007e282  add     rsp, 538h
0x18007e289  pop     rdi
0x18007e28a  pop     rsi
0x18007e28b  pop     rbp
0x18007e28c  pop     rbx
0x18007e28d  retn
```
