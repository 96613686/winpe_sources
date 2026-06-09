# SecRtlFindUnicodeSubstring

- ea: `0x14002b220`
- end: `0x14002b2bc`
- name: `SecRtlFindUnicodeSubstring`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002cddc`
- `0x14003e2c8`

## callees

- `0x14002b220`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14002b271`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14002b271`

## pseudocode

```c
const WCHAR *__fastcall SecRtlFindUnicodeSubstring(unsigned __int16 *a1, PCWCH *a2, BOOLEAN a3)
{
  __int64 v3; // rbx
  unsigned __int16 v7; // dx
  const WCHAR *v8; // rbp
  __int64 v9; // r14

  v3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v7 = *(_WORD *)a2;
      v8 = (const WCHAR *)*((_QWORD *)a1 + 1);
      if ( *a1 >= v7 )
      {
        v9 = 0;
        while ( RtlCompareUnicodeStrings(v8, (unsigned __int64)v7 >> 1, a2[1], (unsigned __int64)v7 >> 1, a3) )
        {
          v9 += 2;
          ++v8;
          v7 = *(_WORD *)a2;
          if ( (unsigned __int64)*a1 - v9 < *(unsigned __int16 *)a2 )
            return (const WCHAR *)v3;
        }
        return v8;
      }
    }
  }
  return (const WCHAR *)v3;
}

```

## disassembly

```asm
0x14002b220  mov     [rsp+arg_0], rbx
0x14002b225  mov     [rsp+arg_8], rbp
0x14002b22a  mov     [rsp+arg_10], rsi
0x14002b22f  push    rdi
0x14002b230  push    r14
0x14002b232  push    r15
0x14002b234  sub     rsp, 30h
0x14002b238  xor     ebx, ebx
0x14002b23a  mov     r15b, r8b
0x14002b23d  mov     rsi, rdx
0x14002b240  mov     rdi, rcx
0x14002b243  test    rcx, rcx
0x14002b246  jz      short loc_14002B29F
0x14002b248  test    rdx, rdx
0x14002b24b  jz      short loc_14002B29F
0x14002b24d  movzx   edx, word ptr [rdx]
0x14002b250  mov     rbp, [rcx+8]
0x14002b254  cmp     [rcx], dx
0x14002b257  jb      short loc_14002B29F
0x14002b259  mov     r14d, ebx
0x14002b25c  mov     r8, [rsi+8]; String2
0x14002b260  mov     rcx, rbp; String1
0x14002b263  movzx   edx, dx
0x14002b266  shr     rdx, 1; String1Length
0x14002b269  mov     r9, rdx; String2Length
0x14002b26c  mov     [rsp+48h+CaseInSensitive], r15b; CaseInSensitive
0x14002b271  call    cs:__imp_RtlCompareUnicodeStrings
0x14002b278  nop     dword ptr [rax+rax+00h]
0x14002b27d  test    eax, eax
0x14002b27f  jz      short loc_14002B29C
0x14002b281  movzx   ecx, word ptr [rsi]
0x14002b284  add     r14, 2
0x14002b288  movzx   eax, word ptr [rdi]
0x14002b28b  add     rbp, 2
0x14002b28f  sub     rax, r14
0x14002b292  movzx   edx, cx
0x14002b295  cmp     rax, rcx
0x14002b298  jnb     short loc_14002B25C
0x14002b29a  jmp     short loc_14002B29F
0x14002b29c  mov     rbx, rbp
0x14002b29f  mov     rbp, [rsp+48h+arg_8]
0x14002b2a4  mov     rax, rbx
0x14002b2a7  mov     rbx, [rsp+48h+arg_0]
0x14002b2ac  mov     rsi, [rsp+48h+arg_10]
0x14002b2b1  add     rsp, 30h
0x14002b2b5  pop     r15
0x14002b2b7  pop     r14
0x14002b2b9  pop     rdi
0x14002b2ba  retn
```
