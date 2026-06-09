# I_ValidatePageHashesBlob

- ea: `0x18008ec14`
- end: `0x18008ed06`
- name: `I_ValidatePageHashesBlob`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180059650`
- `0x18008edec`
- `0x180090318`

## callees

- `0x18008ec14`
- `0x18008ed10`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18008ec60`
- `ntoskrnl!RtlCompareMemory` at `0x18008ec83`
- `ntoskrnl!RtlCompareMemory` at `0x18008ece1`
- `ntoskrnl!RtlCompareMemory` at `0x18008ec60`
- `ntoskrnl!RtlCompareMemory` at `0x18008ec83`
- `ntoskrnl!RtlCompareMemory` at `0x18008ece1`

## pseudocode

```c
_BOOL8 __fastcall I_ValidatePageHashesBlob(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  bool v5; // zf
  __int64 v7; // rbp
  const void *v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int *v13; // r8
  const void **v14; // r9
  _BOOL8 result; // rax
  int Source1; // [rsp+50h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 32) == 10;
  v7 = a4;
  Source1 = 0;
  result = 0;
  if ( v5 )
  {
    v10 = *(const void **)(a1 + 40);
    if ( v10 )
    {
      if ( *(_QWORD *)(a1 + 56)
        && (RtlCompareMemory(qword_180031EB0, v10, 0xAu) == 10
         || RtlCompareMemory(qword_180031ED0, *(const void **)(a1 + 40), 0xAu) == 10) )
      {
        v11 = *(_QWORD *)(a1 + 56);
        if ( v11 >= a2 )
        {
          v12 = *(unsigned int *)(a1 + 48);
          if ( (unsigned int)v12 <= a3
            && (int)MinAsn1ExtractContent(v11, v12, a5, a5 + 8) >= 0
            && !(*v13 % (unsigned __int64)(v7 + 4))
            && *v13 / (unsigned __int64)(v7 + 4)
            && *v14
            && RtlCompareMemory(&Source1, *v14, 4u) == 4 )
          {
            return 1;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008ec14  push    rbx
0x18008ec16  push    rbp
0x18008ec17  push    rsi
0x18008ec18  push    rdi
0x18008ec19  sub     rsp, 28h
0x18008ec1d  cmp     dword ptr [rcx+20h], 0Ah
0x18008ec21  mov     edi, r8d
0x18008ec24  mov     ebp, r9d
0x18008ec27  mov     rsi, rdx
0x18008ec2a  mov     rbx, rcx
0x18008ec2d  mov     [rsp+48h+Source1], 0
0x18008ec35  jnz     loc_18008ED02
0x18008ec3b  mov     rdx, [rcx+28h]; Source2
0x18008ec3f  test    rdx, rdx
0x18008ec42  jz      loc_18008ED02
0x18008ec48  cmp     qword ptr [rcx+38h], 0
0x18008ec4d  jz      loc_18008ED02
0x18008ec53  mov     r8d, 0Ah; Length
0x18008ec59  lea     rcx, qword_180031EB0; Source1
0x18008ec60  call    cs:__imp_RtlCompareMemory
0x18008ec67  nop     dword ptr [rax+rax+00h]
0x18008ec6c  cmp     rax, 0Ah
0x18008ec70  jz      short loc_18008EC95
0x18008ec72  mov     rdx, [rbx+28h]; Source2
0x18008ec76  lea     rcx, qword_180031ED0; Source1
0x18008ec7d  mov     r8d, 0Ah; Length
0x18008ec83  call    cs:__imp_RtlCompareMemory
0x18008ec8a  nop     dword ptr [rax+rax+00h]
0x18008ec8f  cmp     rax, 0Ah
0x18008ec93  jnz     short loc_18008ED02
0x18008ec95  mov     rcx, [rbx+38h]
0x18008ec99  cmp     rcx, rsi
0x18008ec9c  jb      short loc_18008ED02
0x18008ec9e  mov     edx, [rbx+30h]
0x18008eca1  cmp     edx, edi
0x18008eca3  ja      short loc_18008ED02
0x18008eca5  mov     r8, [rsp+48h+arg_20]
0x18008ecaa  lea     r9, [r8+8]
0x18008ecae  call    MinAsn1ExtractContent
0x18008ecb3  test    eax, eax
0x18008ecb5  js      short loc_18008ED02
0x18008ecb7  mov     eax, [r8]
0x18008ecba  lea     rcx, [rbp+4]
0x18008ecbe  xor     edx, edx
0x18008ecc0  div     rcx
0x18008ecc3  test    rdx, rdx
0x18008ecc6  jnz     short loc_18008ED02
0x18008ecc8  cmp     rax, 1
0x18008eccc  jb      short loc_18008ED02
0x18008ecce  mov     rdx, [r9]; Source2
0x18008ecd1  test    rdx, rdx
0x18008ecd4  jz      short loc_18008ED02
0x18008ecd6  mov     r8d, 4; Length
0x18008ecdc  lea     rcx, [rsp+48h+Source1]; Source1
0x18008ece1  call    cs:__imp_RtlCompareMemory
0x18008ece8  nop     dword ptr [rax+rax+00h]
0x18008eced  cmp     rax, 4
0x18008ecf1  jnz     short loc_18008ED02
0x18008ecf3  mov     eax, 1
0x18008ecf8  add     rsp, 28h
0x18008ecfc  pop     rdi
0x18008ecfd  pop     rsi
0x18008ecfe  pop     rbp
0x18008ecff  pop     rbx
0x18008ed00  retn
0x18008ed02  xor     eax, eax
0x18008ed04  jmp     short loc_18008ECF8
```
