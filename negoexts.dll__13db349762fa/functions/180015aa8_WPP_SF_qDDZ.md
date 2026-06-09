# WPP_SF_qDDZ

- ea: `0x180015aa8`
- end: `0x180015bb9`
- name: `WPP_SF_qDDZ`
- size: `273`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, char, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009db0`
- `0x18000a29c`
- `0x18000b7d0`
- `0x18000c7d0`
- `0x18000cc6c`
- `0x1800169d4`
- `0x18001cecc`

## callees

- `0x180015aa8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015ba2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015ba2`

## pseudocode

```c
ULONG WPP_SF_qDDZ(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, __int64 a4, ...)
{
  int *v4; // rax
  const wchar_t **v8; // r9
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  const wchar_t *v11; // r8
  __int64 v13; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v14; // [rsp+B0h] [rbp+28h] BYREF
  va_list va; // [rsp+B0h] [rbp+28h]
  __int64 v16; // [rsp+B8h] [rbp+30h] BYREF
  va_list va1; // [rsp+B8h] [rbp+30h]
  _WORD *v18; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  v18 = va_arg(va2, _WORD *);
  v13 = a4;
  v4 = (int *)v18;
  v8 = (const wchar_t **)(v18 + 4);
  if ( v18 && *v8 )
  {
    if ( *v18 )
      v9 = (unsigned __int16)*v18;
    else
      v9 = 16;
    v10 = *v8;
LABEL_9:
    v11 = L"(empty)";
    if ( *v18 )
      v11 = v10;
    goto LABEL_14;
  }
  v9 = 14;
  if ( v18 )
  {
    v10 = *v8;
    if ( *v8 )
      goto LABEL_9;
  }
  v11 = L"(null)";
  if ( !v18 || !*v8 )
  {
    v4 = &dword_180021E14;
    return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, &v13, 8, va, 4, va1, 4, v4, 2, v11, v9, 0);
  }
LABEL_14:
  if ( !*v18 )
    v4 = (int *)byte_180021E10;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, &v13, 8, va, 4, va1, 4, v4, 2, v11, v9, 0);
}

```

## disassembly

```asm
0x180015aa8  mov     [rsp+arg_0], rbx
0x180015aad  mov     [rsp+arg_18], r9
0x180015ab2  push    rdi
0x180015ab3  sub     rsp, 80h
0x180015aba  mov     rax, [rsp+88h+arg_30]
0x180015ac2  xor     edi, edi
0x180015ac4  movzx   r11d, dx
0x180015ac8  mov     r10, r8
0x180015acb  mov     rbx, rcx
0x180015ace  lea     r9, [rax+8]
0x180015ad2  test    rax, rax
0x180015ad5  jz      short loc_180015AF0
0x180015ad7  cmp     [r9], rdi
0x180015ada  jz      short loc_180015AF0
0x180015adc  cmp     [rax], di
0x180015adf  jz      short loc_180015AE6
0x180015ae1  movzx   ecx, word ptr [rax]
0x180015ae4  jmp     short loc_180015AEB
0x180015ae6  mov     ecx, 10h
0x180015aeb  mov     rdx, [r9]
0x180015aee  jmp     short loc_180015B02
0x180015af0  mov     ecx, 0Eh
0x180015af5  test    rax, rax
0x180015af8  jz      short loc_180015B12
0x180015afa  mov     rdx, [r9]
0x180015afd  test    rdx, rdx
0x180015b00  jz      short loc_180015B12
0x180015b02  cmp     [rax], di
0x180015b05  lea     r8, aEmpty; "(empty)"
0x180015b0c  cmovnz  r8, rdx
0x180015b10  jmp     short loc_180015B23
0x180015b12  lea     r8, aNull_0; "(null)"
0x180015b19  test    rax, rax
0x180015b1c  jz      short loc_180015B33
0x180015b1e  cmp     [r9], rdi
0x180015b21  jz      short loc_180015B33
0x180015b23  cmp     [rax], di
0x180015b26  lea     rdx, byte_180021E10
0x180015b2d  cmovz   rax, rdx
0x180015b31  jmp     short loc_180015B3A
0x180015b33  lea     rax, dword_180021E14
0x180015b3a  mov     [rsp+88h+var_18], rdi
0x180015b3f  mov     r9d, r11d; MessageNumber
0x180015b42  mov     [rsp+88h+var_20], rcx
0x180015b47  mov     ecx, 4
0x180015b4c  mov     [rsp+88h+var_28], r8
0x180015b51  mov     r8, r10; MessageGuid
0x180015b54  mov     [rsp+88h+var_30], 2
0x180015b5d  mov     [rsp+88h+var_38], rax
0x180015b62  lea     rax, [rsp+88h+arg_28]
0x180015b6a  mov     [rsp+88h+var_40], rcx
0x180015b6f  lea     edx, [rcx+27h]; MessageFlags
0x180015b72  mov     [rsp+88h+var_48], rax
0x180015b77  lea     rax, [rsp+88h+arg_20]
0x180015b7f  mov     [rsp+88h+var_50], rcx
0x180015b84  mov     rcx, rbx; LoggerHandle
0x180015b87  mov     [rsp+88h+var_58], rax
0x180015b8c  lea     rax, [rsp+88h+arg_18]
0x180015b94  mov     [rsp+88h+var_60], 8
0x180015b9d  mov     [rsp+88h+var_68], rax
0x180015ba2  call    cs:__imp_TraceMessage
0x180015ba8  mov     rbx, [rsp+88h+arg_0]
0x180015bb0  add     rsp, 80h
0x180015bb7  pop     rdi
0x180015bb8  retn
```
