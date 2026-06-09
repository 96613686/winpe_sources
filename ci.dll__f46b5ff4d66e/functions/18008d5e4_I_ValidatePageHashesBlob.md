# I_ValidatePageHashesBlob

- ea: `0x18008d5e4`
- end: `0x18008d6d6`
- name: `I_ValidatePageHashesBlob`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180058938`
- `0x18008d7bc`
- `0x18008ece8`

## callees

- `0x18008d5e4`
- `0x18008d6e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18008d630`
- `ntoskrnl!RtlCompareMemory` at `0x18008d653`
- `ntoskrnl!RtlCompareMemory` at `0x18008d6b1`
- `ntoskrnl!RtlCompareMemory` at `0x18008d630`
- `ntoskrnl!RtlCompareMemory` at `0x18008d653`
- `ntoskrnl!RtlCompareMemory` at `0x18008d6b1`

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
        && (RtlCompareMemory(qword_180031DB0, v10, 0xAu) == 10
         || RtlCompareMemory(qword_180031DD0, *(const void **)(a1 + 40), 0xAu) == 10) )
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
0x18008d5e4  push    rbx
0x18008d5e6  push    rbp
0x18008d5e7  push    rsi
0x18008d5e8  push    rdi
0x18008d5e9  sub     rsp, 28h
0x18008d5ed  cmp     dword ptr [rcx+20h], 0Ah
0x18008d5f1  mov     edi, r8d
0x18008d5f4  mov     ebp, r9d
0x18008d5f7  mov     rsi, rdx
0x18008d5fa  mov     rbx, rcx
0x18008d5fd  mov     [rsp+48h+Source1], 0
0x18008d605  jnz     loc_18008D6D2
0x18008d60b  mov     rdx, [rcx+28h]; Source2
0x18008d60f  test    rdx, rdx
0x18008d612  jz      loc_18008D6D2
0x18008d618  cmp     qword ptr [rcx+38h], 0
0x18008d61d  jz      loc_18008D6D2
0x18008d623  mov     r8d, 0Ah; Length
0x18008d629  lea     rcx, qword_180031DB0; Source1
0x18008d630  call    cs:__imp_RtlCompareMemory
0x18008d637  nop     dword ptr [rax+rax+00h]
0x18008d63c  cmp     rax, 0Ah
0x18008d640  jz      short loc_18008D665
0x18008d642  mov     rdx, [rbx+28h]; Source2
0x18008d646  lea     rcx, qword_180031DD0; Source1
0x18008d64d  mov     r8d, 0Ah; Length
0x18008d653  call    cs:__imp_RtlCompareMemory
0x18008d65a  nop     dword ptr [rax+rax+00h]
0x18008d65f  cmp     rax, 0Ah
0x18008d663  jnz     short loc_18008D6D2
0x18008d665  mov     rcx, [rbx+38h]
0x18008d669  cmp     rcx, rsi
0x18008d66c  jb      short loc_18008D6D2
0x18008d66e  mov     edx, [rbx+30h]
0x18008d671  cmp     edx, edi
0x18008d673  ja      short loc_18008D6D2
0x18008d675  mov     r8, [rsp+48h+arg_20]
0x18008d67a  lea     r9, [r8+8]
0x18008d67e  call    MinAsn1ExtractContent
0x18008d683  test    eax, eax
0x18008d685  js      short loc_18008D6D2
0x18008d687  mov     eax, [r8]
0x18008d68a  lea     rcx, [rbp+4]
0x18008d68e  xor     edx, edx
0x18008d690  div     rcx
0x18008d693  test    rdx, rdx
0x18008d696  jnz     short loc_18008D6D2
0x18008d698  cmp     rax, 1
0x18008d69c  jb      short loc_18008D6D2
0x18008d69e  mov     rdx, [r9]; Source2
0x18008d6a1  test    rdx, rdx
0x18008d6a4  jz      short loc_18008D6D2
0x18008d6a6  mov     r8d, 4; Length
0x18008d6ac  lea     rcx, [rsp+48h+Source1]; Source1
0x18008d6b1  call    cs:__imp_RtlCompareMemory
0x18008d6b8  nop     dword ptr [rax+rax+00h]
0x18008d6bd  cmp     rax, 4
0x18008d6c1  jnz     short loc_18008D6D2
0x18008d6c3  mov     eax, 1
0x18008d6c8  add     rsp, 28h
0x18008d6cc  pop     rdi
0x18008d6cd  pop     rsi
0x18008d6ce  pop     rbp
0x18008d6cf  pop     rbx
0x18008d6d0  retn
0x18008d6d2  xor     eax, eax
0x18008d6d4  jmp     short loc_18008D6C8
```
