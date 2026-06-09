# GetTargetDirectory

- ea: `0x18000829c`
- end: `0x18000833f`
- name: `GetTargetDirectory`
- size: `163`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int16, _WORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006184`
- `0x180007628`
- `0x1800091f0`

## callees

- `0x18000829c`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wfullpath` at `0x1800082fe`
- `msvcrt!_wfullpath` at `0x1800082fe`
- `KERNEL32!GetSystemDirectoryW` at `0x1800082e9`
- `KERNEL32!GetSystemDirectoryW` at `0x1800082e9`

## pseudocode

```c
__int64 __fastcall GetTargetDirectory(wchar_t *Buffer, unsigned __int16 a2, _WORD *a3)
{
  unsigned int v4; // esi
  __int64 result; // rax
  WCHAR Buffera; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v8[526]; // [rsp+22h] [rbp-236h] BYREF

  v4 = a2;
  Buffera = 0;
  memset_0(v8, 0, 0x206u);
  if ( !GetSystemDirectoryW(&Buffera, 0x104u) || !_wfullpath(Buffer, &Buffera, v4) )
    *Buffer = 0;
  result = -1;
  do
    ++result;
  while ( Buffer[result] );
  *a3 = result;
  return result;
}

```

## disassembly

```asm
0x18000829c  mov     [rsp+arg_18], rbx
0x1800082a1  push    rbp
0x1800082a2  push    rsi
0x1800082a3  push    rdi
0x1800082a4  sub     rsp, 240h
0x1800082ab  mov     rax, cs:__security_cookie
0x1800082b2  xor     rax, rsp
0x1800082b5  mov     [rsp+258h+var_28], rax
0x1800082bd  mov     rdi, r8
0x1800082c0  movzx   esi, dx
0x1800082c3  mov     rbx, rcx
0x1800082c6  xor     ebp, ebp
0x1800082c8  xor     edx, edx; Val
0x1800082ca  mov     [rsp+258h+Buffer], bp
0x1800082cf  mov     r8d, 206h; Size
0x1800082d5  lea     rcx, [rsp+258h+var_236]; void *
0x1800082da  call    memset_0
0x1800082df  mov     edx, 104h; uSize
0x1800082e4  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800082e9  call    cs:__imp_GetSystemDirectoryW
0x1800082ef  test    eax, eax
0x1800082f1  jz      short loc_180008309
0x1800082f3  mov     r8d, esi; BufferCount
0x1800082f6  lea     rdx, [rsp+258h+Buffer]; Path
0x1800082fb  mov     rcx, rbx; Buffer
0x1800082fe  call    cs:__imp__wfullpath
0x180008304  test    rax, rax
0x180008307  jnz     short loc_18000830C
0x180008309  mov     [rbx], bp
0x18000830c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008310  inc     rax
0x180008313  cmp     [rbx+rax*2], bp
0x180008317  jnz     short loc_180008310
0x180008319  mov     [rdi], ax
0x18000831c  mov     rcx, [rsp+258h+var_28]
0x180008324  xor     rcx, rsp; StackCookie
0x180008327  call    __security_check_cookie
0x18000832c  mov     rbx, [rsp+258h+arg_18]
0x180008334  add     rsp, 240h
0x18000833b  pop     rdi
0x18000833c  pop     rsi
0x18000833d  pop     rbp
0x18000833e  retn
```
