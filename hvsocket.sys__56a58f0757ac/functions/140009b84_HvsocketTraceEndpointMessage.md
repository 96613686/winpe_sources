# HvsocketTraceEndpointMessage

- ea: `0x140009b84`
- end: `0x140009c31`
- name: `HvsocketTraceEndpointMessage`
- size: `173`
- prototype: `NTSTATUS __fastcall(const int *, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400020c4`
- `0x140003fe0`
- `0x1400051b0`
- `0x140005280`
- `0x1400056e0`
- `0x140005d74`
- `0x14001c2d0`

## callees

- `0x140001008`
- `0x140009b84`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointMessage(const int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-58h] BYREF
  const int *v9; // [rsp+60h] [rbp-38h]
  int v10; // [rsp+68h] [rbp-30h]
  int v11; // [rsp+6Ch] [rbp-2Ch]
  __int64 *v12; // [rsp+70h] [rbp-28h]
  __int64 v13; // [rsp+78h] [rbp-20h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_BYTE *)a1 + v5) );
      v6 = v5 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v6 = 1;
    }
    v10 = v6;
    v12 = &v7;
    v9 = a1;
    v7 = a2;
    v11 = 0;
    v13 = 8;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&word_14001185A,
             0,
             a4,
             4u,
             &v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009b84  sub     rsp, 98h
0x140009b8b  mov     rax, cs:__security_cookie
0x140009b92  xor     rax, rsp
0x140009b95  mov     [rsp+98h+var_18], rax
0x140009b9d  mov     eax, cs:dword_140013058
0x140009ba3  cmp     eax, 4
0x140009ba6  jbe     short loc_140009C18
0x140009ba8  xor     r8d, r8d; int
0x140009bab  test    rcx, rcx
0x140009bae  jz      short loc_140009BC1
0x140009bb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009bb4  inc     rax
0x140009bb7  cmp     [rcx+rax], r8b
0x140009bbb  jnz     short loc_140009BB4
0x140009bbd  inc     eax
0x140009bbf  jmp     short loc_140009BCD
0x140009bc1  lea     rcx, byte_14000E6BD
0x140009bc8  mov     eax, 1
0x140009bcd  mov     [rsp+98h+var_30], eax
0x140009bd1  lea     rax, [rsp+98h+var_68]
0x140009bd6  mov     [rsp+98h+var_28], rax
0x140009bdb  lea     rax, [rsp+98h+var_58]
0x140009be0  mov     [rsp+98h+var_38], rcx
0x140009be5  lea     rcx, dword_140013058; int
0x140009bec  mov     [rsp+98h+var_68], rdx
0x140009bf1  lea     rdx, word_14001185A; int
0x140009bf8  mov     [rsp+98h+var_70], rax; __int64
0x140009bfd  mov     [rsp+98h+var_78], 4; ULONG
0x140009c05  mov     [rsp+98h+var_2C], r8d
0x140009c0a  mov     [rsp+98h+var_20], 8
0x140009c13  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009c18  mov     rcx, [rsp+98h+var_18]
0x140009c20  xor     rcx, rsp; StackCookie
0x140009c23  call    __security_check_cookie
0x140009c28  add     rsp, 98h
0x140009c2f  retn
```
