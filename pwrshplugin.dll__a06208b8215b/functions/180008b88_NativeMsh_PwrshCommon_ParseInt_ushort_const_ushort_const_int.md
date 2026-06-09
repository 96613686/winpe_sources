# NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)

- ea: `0x180008b88`
- end: `0x180008c21`
- name: `?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z`
- size: `153`
- prototype: `char __fastcall(wchar_t *this, wchar_t *, wchar_t *, unsigned int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002170`
- `0x180003158`
- `0x180003a68`
- `0x180007c2c`
- `0x180008890`

## callees

- `0x180008b88`

## import_xrefs

- `msvcrt!wcstoul` at `0x180008bf7`
- `msvcrt!wcstoul` at `0x180008bf7`

## pseudocode

```c
char __fastcall NativeMsh::PwrshCommon::ParseInt(wchar_t *this, wchar_t *a2, wchar_t *a3, unsigned int *a4)
{
  char v4; // bl
  wchar_t *v7; // r10
  unsigned int v8; // eax
  wchar_t *EndPtr; // [rsp+30h] [rbp+8h] BYREF

  EndPtr = this;
  v4 = 0;
  v7 = a2;
  if ( (unsigned __int16)(*a3 - 48) > 9u && a2 && *a2 && a2 < a3 )
  {
    do
    {
      if ( *v7 != 48 )
        break;
      ++v7;
    }
    while ( v7 < a3 );
    if ( (__int64)(((char *)a3 - (char *)v7) & 0xFFFFFFFFFFFFFFFEuLL) <= 20 )
    {
      EndPtr = 0;
      v8 = wcstoul(v7, &EndPtr, 10);
      if ( a3 == EndPtr && v8 <= 0x7FFFFFFF )
      {
        v4 = 1;
        *a4 = v8;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180008b88  mov     [rsp+arg_8], rbx
0x180008b8d  mov     [rsp+arg_10], rsi
0x180008b92  mov     [rsp+EndPtr], rcx
0x180008b97  push    rdi
0x180008b98  sub     rsp, 20h
0x180008b9c  movzx   eax, word ptr [r8]
0x180008ba0  xor     ebx, ebx
0x180008ba2  sub     ax, 30h ; '0'
0x180008ba6  mov     rsi, r9
0x180008ba9  mov     rdi, r8
0x180008bac  mov     r10, rdx
0x180008baf  cmp     ax, 9
0x180008bb3  jbe     short loc_180008C0F
0x180008bb5  test    rdx, rdx
0x180008bb8  jz      short loc_180008C0F
0x180008bba  cmp     bx, [rdx]
0x180008bbd  jz      short loc_180008C0F
0x180008bbf  cmp     rdx, r8
0x180008bc2  jnb     short loc_180008C0F
0x180008bc4  cmp     word ptr [r10], 30h ; '0'
0x180008bc9  jnz     short loc_180008BD4
0x180008bcb  add     r10, 2
0x180008bcf  cmp     r10, rdi
0x180008bd2  jb      short loc_180008BC4
0x180008bd4  mov     rax, rdi
0x180008bd7  sub     rax, r10
0x180008bda  and     rax, 0FFFFFFFFFFFFFFFEh
0x180008bde  cmp     rax, 14h
0x180008be2  jg      short loc_180008C0F
0x180008be4  mov     r8d, 0Ah; Radix
0x180008bea  mov     [rsp+28h+EndPtr], rbx
0x180008bef  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x180008bf4  mov     rcx, r10; String
0x180008bf7  call    cs:__imp_wcstoul
0x180008bfd  cmp     rdi, [rsp+28h+EndPtr]
0x180008c02  jnz     short loc_180008C0F
0x180008c04  cmp     eax, 7FFFFFFFh
0x180008c09  ja      short loc_180008C0F
0x180008c0b  mov     bl, 1
0x180008c0d  mov     [rsi], eax
0x180008c0f  mov     rsi, [rsp+28h+arg_10]
0x180008c14  mov     al, bl
0x180008c16  mov     rbx, [rsp+28h+arg_8]
0x180008c1b  add     rsp, 20h
0x180008c1f  pop     rdi
0x180008c20  retn
```
