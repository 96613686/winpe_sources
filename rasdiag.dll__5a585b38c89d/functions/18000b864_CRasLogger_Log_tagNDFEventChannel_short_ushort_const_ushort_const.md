# CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)

- ea: `0x18000b864`
- end: `0x18000b920`
- name: `?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ`
- size: `188`
- prototype: `__int64(_QWORD *, unsigned int, unsigned __int16, __int64, const wchar_t *, ...)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a30`
- `0x180006fec`
- `0x1800075e0`
- `0x180007828`
- `0x180007b70`
- `0x180007f20`
- `0x180008620`
- `0x180009250`
- `0x180009440`
- `0x180009630`
- `0x1800097d0`
- `0x180009dd0`
- `0x180009e60`
- `0x18000a710`
- `0x18000ad60`
- `0x18000b610`

## callees

- `0x18000b864`
- `0x18000df10`
- `0x18000f010`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000b8b7`
- `msvcrt!_vsnwprintf` at `0x18000b8b7`

## pseudocode

```c
__int64 CRasLogger::Log(_QWORD *a1, unsigned int a2, unsigned __int16 a3, __int64 a4, const wchar_t *a5, ...)
{
  __int64 result; // rax
  const wchar_t *v10; // r8
  unsigned int v11; // eax
  wchar_t Buffer[264]; // [rsp+40h] [rbp-248h] BYREF
  va_list va; // [rsp+2B8h] [rbp+30h] BYREF

  va_start(va, a5);
  result = 0;
  if ( *a1 )
  {
    v10 = &qword_1800132F0;
    if ( a5 )
      v10 = a5;
    v11 = _vsnwprintf(Buffer, 0x103u, v10, va);
    if ( v11 >= 0x104 )
    {
      return 2147942522LL;
    }
    else
    {
      if ( v11 == 259 )
        Buffer[259] = 0;
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, wchar_t *))(*(_QWORD *)*a1 + 24LL))(
               *a1,
               a2,
               a3,
               a4,
               Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b864  mov     r11, rsp
0x18000b867  push    rbx
0x18000b868  push    rbp
0x18000b869  push    rsi
0x18000b86a  push    rdi
0x18000b86b  sub     rsp, 268h
0x18000b872  mov     rax, cs:__security_cookie
0x18000b879  xor     rax, rsp
0x18000b87c  mov     [rsp+288h+var_38], rax
0x18000b884  xor     eax, eax
0x18000b886  mov     rbp, r9
0x18000b889  movzx   esi, r8w
0x18000b88d  mov     edi, edx
0x18000b88f  mov     rbx, rcx
0x18000b892  cmp     [rcx], rax
0x18000b895  jz      short loc_18000B903
0x18000b897  mov     rax, [r11+28h]
0x18000b89b  lea     r8, qword_1800132F0
0x18000b8a2  test    rax, rax
0x18000b8a5  lea     r9, [r11+30h]; Args
0x18000b8a9  mov     edx, 103h; BufferCount
0x18000b8ae  lea     rcx, [rsp+288h+Buffer]; Buffer
0x18000b8b3  cmovnz  r8, rax; Format
0x18000b8b7  call    cs:__imp__vsnwprintf
0x18000b8be  nop     dword ptr [rax+rax+00h]
0x18000b8c3  test    eax, eax
0x18000b8c5  js      short loc_18000B8FE
0x18000b8c7  cmp     eax, 103h
0x18000b8cc  ja      short loc_18000B8FE
0x18000b8ce  jnz     short loc_18000B8DA
0x18000b8d0  xor     eax, eax
0x18000b8d2  mov     [rsp+288h+var_42], ax
0x18000b8da  mov     rcx, [rbx]
0x18000b8dd  lea     rdx, [rsp+288h+Buffer]
0x18000b8e2  mov     [rsp+288h+var_268], rdx
0x18000b8e7  mov     r9, rbp
0x18000b8ea  movzx   r8d, si
0x18000b8ee  mov     edx, edi
0x18000b8f0  mov     rax, [rcx]
0x18000b8f3  mov     rax, [rax+18h]
0x18000b8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8fc  jmp     short loc_18000B903
0x18000b8fe  mov     eax, 8007007Ah
0x18000b903  mov     rcx, [rsp+288h+var_38]
0x18000b90b  xor     rcx, rsp; StackCookie
0x18000b90e  call    __security_check_cookie
0x18000b913  add     rsp, 268h
0x18000b91a  pop     rdi
0x18000b91b  pop     rsi
0x18000b91c  pop     rbp
0x18000b91d  pop     rbx
0x18000b91e  retn
```
