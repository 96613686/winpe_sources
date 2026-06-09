# CscDriverpOpenControl

- ea: `0x180002cd0`
- end: `0x180002da9`
- name: `CscDriverpOpenControl`
- size: `217`
- prototype: `__int64 __fastcall(PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b70`

## callees

- `0x180002cd0`
- `0x180002db0`
- `0x180008fec`

## pseudocode

```c
__int64 __fastcall CscDriverpOpenControl(PHANDLE FileHandle, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v5; // r8
  unsigned int v6; // ebx
  int v7; // [rsp+30h] [rbp-28h]
  UNICODE_STRING v8; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)&v8.Length = 262146;
  v8.Buffer = L"\\";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, a3, FileHandle, 0, 0);
  }
  *FileHandle = 0;
  result = CscDriverOpenItemWithDispositionEx(FileHandle, a2, &v8, 53, 1179785, 7u, v7, 0);
  v6 = result;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, v5, FileHandle, *FileHandle, result);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180002cd0  mov     [rsp+arg_0], rbx
0x180002cd5  mov     [rsp+arg_8], rsi
0x180002cda  push    rdi
0x180002cdb  sub     rsp, 50h
0x180002cdf  lea     rax, asc_18000B65C; "\\"
0x180002ce6  mov     [rsp+58h+var_18], 40002h
0x180002cef  mov     [rsp+58h+var_10], rax
0x180002cf4  mov     rdi, rcx
0x180002cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cfe  lea     rsi, WPP_GLOBAL_Control
0x180002d05  xor     ebx, ebx
0x180002d07  cmp     rcx, rsi
0x180002d0a  jnz     short loc_180002D54
0x180002d0c  mov     [rsp+58h+var_20], ebx; int
0x180002d10  lea     r8, [rsp+58h+var_18]
0x180002d15  mov     [rsp+58h+var_30], 7; ULONG
0x180002d1d  mov     r9d, 35h ; '5'
0x180002d23  mov     rcx, rdi; FileHandle
0x180002d26  mov     [rsp+58h+var_38], 120089h; int
0x180002d2e  mov     [rdi], rbx
0x180002d31  call    CscDriverOpenItemWithDispositionEx
0x180002d36  mov     ebx, eax
0x180002d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d3f  cmp     rcx, rsi
0x180002d42  jnz     short loc_180002D7C
0x180002d44  mov     rbx, [rsp+58h+arg_0]
0x180002d49  mov     rsi, [rsp+58h+arg_8]
0x180002d4e  add     rsp, 50h
0x180002d52  pop     rdi
0x180002d53  retn
0x180002d54  test    byte ptr [rcx+44h], 8
0x180002d58  jz      short loc_180002D0C
0x180002d5a  cmp     byte ptr [rcx+41h], 4
0x180002d5e  jb      short loc_180002D0C
0x180002d60  mov     rcx, [rcx+38h]
0x180002d64  mov     edx, 14h
0x180002d69  mov     [rsp+58h+var_30], ebx
0x180002d6d  mov     r9, rdi
0x180002d70  mov     qword ptr [rsp+58h+var_38], rbx
0x180002d75  call    WPP_SF_qqD
0x180002d7a  jmp     short loc_180002D0C
0x180002d7c  test    byte ptr [rcx+44h], 8
0x180002d80  jz      short loc_180002D44
0x180002d82  cmp     byte ptr [rcx+41h], 4
0x180002d86  jb      short loc_180002D44
0x180002d88  mov     rax, [rdi]
0x180002d8b  mov     edx, 15h
0x180002d90  mov     rcx, [rcx+38h]
0x180002d94  mov     r9, rdi
0x180002d97  mov     [rsp+58h+var_30], ebx
0x180002d9b  mov     qword ptr [rsp+58h+var_38], rax
0x180002da0  call    WPP_SF_qqD
0x180002da5  mov     eax, ebx
0x180002da7  jmp     short loc_180002D44
```
