# _cgets_s

- ea: `0x18001dba0`
- end: `0x18001dcc7`
- name: `_cgets_s`
- size: `295`
- prototype: `errno_t __cdecl(char *Buffer, size_t BufferCount, size_t *SizeRead)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001db20`

## callees

- `0x180005d70`
- `0x180007e80`
- `0x180007f00`
- `0x18001dba0`
- `0x18001dd50`
- `0x18002f050`
- `0x18003e6c0`
- `0x18003e8e0`

## pseudocode

```c
errno_t __cdecl cgets_s(char *Buffer, size_t BufferCount, size_t *SizeRead)
{
  char *v4; // rbx
  rsize_t v5; // r14
  errno_t v6; // edi
  __int64 v7; // rax
  wchar_t Buffera[2]; // [rsp+30h] [rbp-38h] BYREF
  errno_t v10; // [rsp+34h] [rbp-34h]
  size_t SizeReada[3]; // [rsp+38h] [rbp-30h] BYREF
  int SizeConverted; // [rsp+88h] [rbp+20h] BYREF

  v4 = Buffer;
  if ( !Buffer || !BufferCount || (*Buffer = 0, !SizeRead) )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v5 = BufferCount - 1;
  lock(3);
  *SizeRead = 0;
  do
  {
    SizeReada[0] = 0;
    v6 = cgetws_s(Buffera, 2u, SizeReada);
    v10 = v6;
    if ( v6 )
      break;
    SizeConverted = 0;
    if ( !Buffera[0] )
      break;
    v6 = wctomb_s(&SizeConverted, v4, v5, Buffera[0]);
    v10 = v6;
    if ( v6 )
    {
      _console_wchar_buffer = Buffera[0];
      _console_wchar_buffer_used = 1;
      break;
    }
    v7 = SizeConverted;
    v4 += SizeConverted;
    *SizeRead += SizeConverted;
    v5 -= v7;
    SizeReada[1] = v5;
  }
  while ( v5 );
  unlock(3);
  *v4 = 0;
  if ( v6 )
    *errno() = v6;
  return v6;
}

```

## disassembly

```asm
0x18001dba0  mov     [rsp+arg_8], rbx
0x18001dba5  mov     [rsp+arg_10], rsi
0x18001dbaa  push    rdi
0x18001dbab  push    r14
0x18001dbad  push    r15
0x18001dbaf  sub     rsp, 50h
0x18001dbb3  mov     rsi, r8
0x18001dbb6  mov     rbx, rcx
0x18001dbb9  xor     r15d, r15d
0x18001dbbc  test    rcx, rcx
0x18001dbbf  jnz     short loc_18001DC01
0x18001dbc1  call    __doserrno
0x18001dbc6  mov     [rax], r15d
0x18001dbc9  call    _errno
0x18001dbce  mov     ebx, 16h
0x18001dbd3  mov     [rax], ebx
0x18001dbd5  mov     [rsp+68h+Reserved], r15; Reserved
0x18001dbda  xor     r9d, r9d; LineNo
0x18001dbdd  xor     r8d, r8d; FileName
0x18001dbe0  xor     edx, edx; FunctionName
0x18001dbe2  xor     ecx, ecx; Expression
0x18001dbe4  call    _invalid_parameter
0x18001dbe9  mov     eax, ebx
0x18001dbeb  lea     r11, [rsp+68h+var_18]
0x18001dbf0  mov     rbx, [r11+28h]
0x18001dbf4  mov     rsi, [r11+30h]
0x18001dbf8  mov     rsp, r11
0x18001dbfb  pop     r15
0x18001dbfd  pop     r14
0x18001dbff  pop     rdi
0x18001dc00  retn
0x18001dc01  test    rdx, rdx
0x18001dc04  jz      short loc_18001DBC1
0x18001dc06  mov     [rcx], r15b
0x18001dc09  test    rsi, rsi
0x18001dc0c  jz      short loc_18001DBC1
0x18001dc0e  lea     r14, [rdx-1]
0x18001dc12  mov     ecx, 3
0x18001dc17  call    _lock
0x18001dc1c  nop
0x18001dc1d  mov     [rsi], r15
0x18001dc20  mov     [rsp+68h+SizeRead], r15
0x18001dc25  lea     r8, [rsp+68h+SizeRead]; SizeRead
0x18001dc2a  mov     edx, 2; BufferCount
0x18001dc2f  lea     rcx, [rsp+68h+Buffer]; Buffer
0x18001dc34  call    _cgetws_s
0x18001dc39  mov     edi, eax
0x18001dc3b  mov     [rsp+68h+var_34], eax
0x18001dc3f  test    eax, eax
0x18001dc41  jnz     short loc_18001DCA8
0x18001dc43  mov     [rsp+68h+SizeConverted], r15d
0x18001dc4b  mov     r9d, dword ptr [rsp+68h+Buffer]; WCh
0x18001dc50  test    r9w, r9w
0x18001dc54  jz      short loc_18001DCA8
0x18001dc56  mov     r8, r14; SizeInBytes
0x18001dc59  mov     rdx, rbx; MbCh
0x18001dc5c  lea     rcx, [rsp+68h+SizeConverted]; SizeConverted
0x18001dc64  call    wctomb_s
0x18001dc69  mov     edi, eax
0x18001dc6b  mov     [rsp+68h+var_34], eax
0x18001dc6f  test    eax, eax
0x18001dc71  jnz     short loc_18001DC92
0x18001dc73  movsxd  rax, [rsp+68h+SizeConverted]
0x18001dc7b  add     rbx, rax
0x18001dc7e  mov     [rsp+68h+arg_0], rbx
0x18001dc83  add     [rsi], rax
0x18001dc86  sub     r14, rax
0x18001dc89  mov     [rsp+68h+var_28], r14
0x18001dc8e  jnz     short loc_18001DC20
0x18001dc90  jmp     short loc_18001DCA8
0x18001dc92  movzx   eax, [rsp+68h+Buffer]
0x18001dc97  mov     cs:__console_wchar_buffer, ax
0x18001dc9e  mov     cs:__console_wchar_buffer_used, 1
0x18001dca8  mov     ecx, 3
0x18001dcad  call    _unlock
0x18001dcb2  mov     [rbx], r15b
0x18001dcb5  test    edi, edi
0x18001dcb7  jz      short loc_18001DCC0
0x18001dcb9  call    _errno
0x18001dcbe  mov     [rax], edi
0x18001dcc0  mov     eax, edi
0x18001dcc2  jmp     loc_18001DBEB
0x18007b80c  push    rbp
0x18007b80e  sub     rsp, 30h
0x18007b812  mov     rbp, rdx
0x18007b815  mov     ecx, 3
0x18007b81a  add     rsp, 30h
0x18007b81e  pop     rbp
0x18007b81f  jmp     _unlock
```
