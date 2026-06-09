# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x180008ac0`
- end: `0x180008b51`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `145`
- prototype: `int(unsigned __int16 **, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006160`
- `0x1800066c0`
- `0x180006970`
- `0x180009c80`
- `0x18000a38c`

## callees

- `0x180008a4c`
- `0x180008ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b16`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v5 = a2 - 1;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFF )
    return 2147942487LL;
  v6 = a2 - 1;
  v7 = a3;
  if ( v5 )
  {
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
        goto LABEL_7;
    }
    result = 0;
    v9 = v5 - v6;
  }
  else
  {
LABEL_7:
    result = 2147942487LL;
    v9 = 0;
  }
  if ( (int)result >= 0 )
  {
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9 + 2);
    *a1 = v10;
    if ( v10 )
      return StringCchCopyW(v10, v9 + 1, a3);
    else
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008ac0  push    rbx
0x180008ac2  push    rbp
0x180008ac3  push    rsi
0x180008ac4  push    rdi
0x180008ac5  sub     rsp, 28h
0x180008ac9  xor     ebp, ebp
0x180008acb  mov     rdi, r8
0x180008ace  mov     rsi, rcx
0x180008ad1  test    rcx, rcx
0x180008ad4  jz      short loc_180008B43
0x180008ad6  test    r8, r8
0x180008ad9  jz      short loc_180008B43
0x180008adb  lea     rbx, [rdx-1]
0x180008adf  cmp     rbx, 7FFFFFFFh
0x180008ae6  ja      short loc_180008B43
0x180008ae8  mov     rdx, rbx
0x180008aeb  mov     rax, r8
0x180008aee  test    rbx, rbx
0x180008af1  jz      short loc_180008B02
0x180008af3  cmp     [rax], bp
0x180008af6  jz      short loc_180008B2B
0x180008af8  add     rax, 2
0x180008afc  sub     rdx, 1
0x180008b00  jnz     short loc_180008AF3
0x180008b02  mov     eax, 80070057h
0x180008b07  mov     rbx, rbp
0x180008b0a  test    eax, eax
0x180008b0c  js      short loc_180008B48
0x180008b0e  lea     rcx, ds:2[rbx*2]; cb
0x180008b16  call    cs:__imp_CoTaskMemAlloc
0x180008b1c  mov     [rsi], rax
0x180008b1f  test    rax, rax
0x180008b22  jnz     short loc_180008B32
0x180008b24  mov     eax, 8007000Eh
0x180008b29  jmp     short loc_180008B48
0x180008b2b  mov     eax, ebp
0x180008b2d  sub     rbx, rdx
0x180008b30  jmp     short loc_180008B0A
0x180008b32  lea     rdx, [rbx+1]; unsigned __int64
0x180008b36  mov     r8, rdi; unsigned __int16 *
0x180008b39  mov     rcx, rax; unsigned __int16 *
0x180008b3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008b41  jmp     short loc_180008B48
0x180008b43  mov     eax, 80070057h
0x180008b48  add     rsp, 28h
0x180008b4c  pop     rdi
0x180008b4d  pop     rsi
0x180008b4e  pop     rbp
0x180008b4f  pop     rbx
0x180008b50  retn
```
