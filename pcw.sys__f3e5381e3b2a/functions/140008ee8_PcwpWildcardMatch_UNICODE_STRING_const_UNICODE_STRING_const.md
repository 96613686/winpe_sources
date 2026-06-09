# PcwpWildcardMatch(_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x140008ee8`
- end: `0x140008fa9`
- name: `?PcwpWildcardMatch@@YA_NPEBU_UNICODE_STRING@@0@Z`
- size: `193`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400082ec`
- `0x1400089cc`
- `0x14000da40`

## callees

- `0x140008ee8`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140008f65`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140008f65`

## pseudocode

```c
char __fastcall PcwpWildcardMatch(const struct _UNICODE_STRING *a1, const struct _UNICODE_STRING *a2)
{
  wchar_t *v2; // r14
  wchar_t *Buffer; // rbx
  wchar_t *v4; // rsi
  wchar_t *v5; // rdi
  wchar_t *v6; // rbp
  wchar_t *v7; // r15

  v2 = 0;
  Buffer = a1->Buffer;
  v4 = 0;
  v5 = a2->Buffer;
  v6 = &Buffer[(unsigned __int64)a1->Length >> 1];
  v7 = &v5[(unsigned __int64)a2->Length >> 1];
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v5 >= v7 && Buffer >= v6 )
        return 1;
      if ( Buffer < v6 && *Buffer == 42 )
      {
        while ( 1 )
        {
          if ( ++Buffer >= v6 )
            return 1;
          if ( *Buffer != 42 )
          {
            v2 = Buffer;
            v4 = v5 + 1;
            break;
          }
        }
      }
      if ( v5 >= v7 || Buffer >= v6 || *Buffer != 63 && RtlCompareUnicodeStrings(Buffer, 1u, v5, 1u, 1u) )
        break;
      ++Buffer;
      ++v5;
    }
    if ( !v2 || v4 >= v7 )
      return 0;
    v5 = v4;
    Buffer = v2;
    ++v4;
  }
}

```

## disassembly

```asm
0x140008ee8  push    rbx
0x140008eea  push    rbp
0x140008eeb  push    rsi
0x140008eec  push    rdi
0x140008eed  push    r14
0x140008eef  push    r15
0x140008ef1  sub     rsp, 38h
0x140008ef5  movzx   eax, word ptr [rcx]
0x140008ef8  xor     r14d, r14d
0x140008efb  mov     rbx, [rcx+8]
0x140008eff  xor     esi, esi
0x140008f01  mov     rdi, [rdx+8]
0x140008f05  shr     rax, 1
0x140008f08  lea     rbp, [rbx+rax*2]
0x140008f0c  movzx   eax, word ptr [rdx]
0x140008f0f  shr     rax, 1
0x140008f12  lea     r15, [rdi+rax*2]
0x140008f16  cmp     rdi, r15
0x140008f19  jb      short loc_140008F20
0x140008f1b  cmp     rbx, rbp
0x140008f1e  jnb     short loc_140008F95
0x140008f20  cmp     rbx, rbp
0x140008f23  jnb     short loc_140008F41
0x140008f25  cmp     word ptr [rbx], 2Ah ; '*'
0x140008f29  jnz     short loc_140008F41
0x140008f2b  add     rbx, 2
0x140008f2f  cmp     rbx, rbp
0x140008f32  jnb     short loc_140008F95
0x140008f34  cmp     word ptr [rbx], 2Ah ; '*'
0x140008f38  jz      short loc_140008F2B
0x140008f3a  mov     r14, rbx
0x140008f3d  lea     rsi, [rdi+2]
0x140008f41  cmp     rdi, r15
0x140008f44  jnb     short loc_140008F7F
0x140008f46  cmp     rbx, rbp
0x140008f49  jnb     short loc_140008F7F
0x140008f4b  cmp     word ptr [rbx], 3Fh ; '?'
0x140008f4f  jz      short loc_140008F75
0x140008f51  mov     r9d, 1; String2Length
0x140008f57  mov     [rsp+68h+CaseInSensitive], 1; CaseInSensitive
0x140008f5c  mov     edx, r9d; String1Length
0x140008f5f  mov     r8, rdi; String2
0x140008f62  mov     rcx, rbx; String1
0x140008f65  call    cs:__imp_RtlCompareUnicodeStrings
0x140008f6c  nop     dword ptr [rax+rax+00h]
0x140008f71  test    eax, eax
0x140008f73  jnz     short loc_140008F7F
0x140008f75  add     rbx, 2
0x140008f79  add     rdi, 2
0x140008f7d  jmp     short loc_140008F16
0x140008f7f  test    r14, r14
0x140008f82  jz      short loc_140008F99
0x140008f84  cmp     rsi, r15
0x140008f87  jnb     short loc_140008F99
0x140008f89  mov     rdi, rsi
0x140008f8c  mov     rbx, r14
0x140008f8f  add     rsi, 2
0x140008f93  jmp     short loc_140008F16
0x140008f95  mov     al, 1
0x140008f97  jmp     short loc_140008F9B
0x140008f99  xor     al, al
0x140008f9b  add     rsp, 38h
0x140008f9f  pop     r15
0x140008fa1  pop     r14
0x140008fa3  pop     rdi
0x140008fa4  pop     rsi
0x140008fa5  pop     rbp
0x140008fa6  pop     rbx
0x140008fa7  retn
```
