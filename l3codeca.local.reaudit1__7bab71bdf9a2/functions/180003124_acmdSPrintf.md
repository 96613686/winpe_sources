# acmdSPrintf

- ea: `0x180003124`
- end: `0x180003212`
- name: `acmdSPrintf`
- size: `238`
- prototype: `__int64 __fastcall(int, int, int, int, char Args)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b68`
- `0x180002da4`

## callees

- `0x180001400`
- `0x180001ce0`
- `0x180003124`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000315b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000315b`

## pseudocode

```c
__int64 acmdSPrintf(__int64 a1, UINT a2, _WORD *a3, unsigned int a4, ...)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  wchar_t *v7; // r8
  _WORD *v8; // rdx
  _WORD *v9; // rcx
  __int64 result; // rax
  wchar_t v11[256]; // [rsp+30h] [rbp-428h] BYREF
  WCHAR Buffer[256]; // [rsp+230h] [rbp-228h] BYREF
  va_list va; // [rsp+480h] [rbp+28h] BYREF

  va_start(va, a4);
  LoadStringW(*(HINSTANCE *)(a1 + 24), a2, Buffer, 256);
  if ( (unsigned int)vsnwprintf(v11, 0xFFu, Buffer, va) > 0xFE )
    v11[255] = 0;
  v5 = a4;
  if ( a4 )
  {
    if ( a4 <= 0x7FFFFFFFuLL )
    {
      v6 = 2147483646;
      v7 = v11;
      v8 = a3;
      do
      {
        if ( !v6 )
          break;
        if ( !*v7 )
          break;
        *v8++ = *v7++;
        --v6;
        --v5;
      }
      while ( v5 );
      v9 = v8 - 1;
      if ( v5 )
        v9 = v8;
      *v9 = 0;
    }
    else
    {
      *a3 = 0;
    }
  }
  result = -1;
  do
    ++result;
  while ( a3[result] );
  return result;
}

```

## disassembly

```asm
0x180003124  mov     [rsp+arg_18], r9d
0x180003129  push    rbx
0x18000312a  push    rdi
0x18000312b  sub     rsp, 448h
0x180003132  mov     rax, cs:__security_cookie
0x180003139  xor     rax, rsp
0x18000313c  mov     [rsp+458h+var_28], rax
0x180003144  mov     rcx, [rcx+18h]; hInstance
0x180003148  mov     rbx, r8
0x18000314b  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x180003153  mov     r9d, 100h; cchBufferMax
0x180003159  xor     edi, edi
0x18000315b  call    cs:__imp_LoadStringW
0x180003161  lea     r9, [rsp+458h+Args]; Args
0x180003169  mov     edx, 0FFh; BufferCount
0x18000316e  lea     r8, [rsp+458h+Buffer]; Format
0x180003176  lea     rcx, [rsp+458h+var_428]; Buffer
0x18000317b  call    _vsnwprintf
0x180003180  test    eax, eax
0x180003182  js      short loc_18000318B
0x180003184  cmp     eax, 0FFh
0x180003189  jb      short loc_180003193
0x18000318b  mov     [rsp+458h+var_22A], di
0x180003193  mov     eax, [rsp+458h+arg_18]
0x18000319a  test    rax, rax
0x18000319d  jz      short loc_1800031EB
0x18000319f  cmp     rax, 7FFFFFFFh
0x1800031a5  jbe     short loc_1800031AC
0x1800031a7  mov     [rbx], di
0x1800031aa  jmp     short loc_1800031EB
0x1800031ac  mov     ecx, 7FFFFFFEh
0x1800031b1  lea     r8, [rsp+458h+var_428]
0x1800031b6  mov     rdx, rbx
0x1800031b9  test    rcx, rcx
0x1800031bc  jz      short loc_1800031DD
0x1800031be  movzx   r9d, word ptr [r8]
0x1800031c2  test    r9w, r9w
0x1800031c6  jz      short loc_1800031DD
0x1800031c8  mov     [rdx], r9w
0x1800031cc  add     r8, 2
0x1800031d0  add     rdx, 2
0x1800031d4  dec     rcx
0x1800031d7  sub     rax, 1
0x1800031db  jnz     short loc_1800031B9
0x1800031dd  test    rax, rax
0x1800031e0  lea     rcx, [rdx-2]
0x1800031e4  cmovnz  rcx, rdx
0x1800031e8  mov     [rcx], di
0x1800031eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800031ef  inc     rax
0x1800031f2  cmp     [rbx+rax*2], di
0x1800031f6  jnz     short loc_1800031EF
0x1800031f8  mov     rcx, [rsp+458h+var_28]
0x180003200  xor     rcx, rsp; StackCookie
0x180003203  call    __security_check_cookie
0x180003208  add     rsp, 448h
0x18000320f  pop     rdi
0x180003210  pop     rbx
0x180003211  retn
```
