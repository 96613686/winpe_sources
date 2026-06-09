# DevAuthGetHashAllInOne

- ea: `0x180002740`
- end: `0x1800027d6`
- name: `DevAuthGetHashAllInOne`
- size: `150`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001700`
- `0x180002888`
- `0x18000325c`
- `0x1800036a0`
- `0x1800037ac`
- `0x180004594`
- `0x1800047d0`
- `0x18000489c`

## callees

- `0x18000258c`
- `0x1800026a0`
- `0x180002740`

## import_xrefs

- `cng!BCryptHashData` at `0x18000278a`
- `cng!BCryptHashData` at `0x18000278a`

## pseudocode

```c
__int64 __fastcall DevAuthGetHashAllInOne(UCHAR *a1, ULONG a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned int v6; // ebx
  BCRYPT_HASH_HANDLE *v8; // r14
  int v9; // esi
  __int64 v10; // rdi
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  v6 = 0;
  P = 0;
  if ( (unsigned int)DevAuthCreateHash(a1, a2, (BCRYPT_HANDLE **)&P) )
  {
    v8 = (BCRYPT_HASH_HANDLE *)P;
    v9 = 0;
    v10 = 0;
    if ( a5 )
    {
      while ( BCryptHashData(v8[1], *(PUCHAR *)(a3 + 8 * v10), *(_DWORD *)(a4 + 4 * v10), 0) >= 0 )
      {
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= a5 )
          goto LABEL_7;
      }
      v9 = 1;
    }
LABEL_7:
    if ( (unsigned int)DevAuthFinishHash(v8) )
      LOBYTE(v6) = v9 == 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180002740  push    rbx
0x180002742  push    rsi
0x180002743  push    rdi
0x180002744  push    r12
0x180002746  push    r14
0x180002748  push    r15
0x18000274a  sub     rsp, 28h
0x18000274e  mov     r12, r8
0x180002751  xor     ebx, ebx
0x180002753  lea     r8, [rsp+58h+P]
0x180002758  mov     [rsp+58h+P], rbx
0x18000275d  mov     r15, r9
0x180002760  call    DevAuthCreateHash
0x180002765  test    eax, eax
0x180002767  jz      short loc_1800027C5
0x180002769  mov     r14, [rsp+58h+P]
0x18000276e  xor     esi, esi
0x180002770  xor     edi, edi
0x180002772  cmp     [rsp+58h+arg_20], ebx
0x180002779  jbe     short loc_1800027AC
0x18000277b  mov     r8d, [r15+rdi*4]; cbInput
0x18000277f  xor     r9d, r9d; dwFlags
0x180002782  mov     rdx, [r12+rdi*8]; pbInput
0x180002786  mov     rcx, [r14+8]; hHash
0x18000278a  call    cs:__imp_BCryptHashData
0x180002791  nop     dword ptr [rax+rax+00h]
0x180002796  test    eax, eax
0x180002798  js      short loc_1800027A7
0x18000279a  inc     edi
0x18000279c  cmp     edi, [rsp+58h+arg_20]
0x1800027a3  jb      short loc_18000277B
0x1800027a5  jmp     short loc_1800027AC
0x1800027a7  mov     esi, 1
0x1800027ac  mov     rdx, [rsp+58h+arg_28]
0x1800027b4  mov     rcx, r14; P
0x1800027b7  call    DevAuthFinishHash
0x1800027bc  test    eax, eax
0x1800027be  jz      short loc_1800027C5
0x1800027c0  test    esi, esi
0x1800027c2  setz    bl
0x1800027c5  mov     eax, ebx
0x1800027c7  add     rsp, 28h
0x1800027cb  pop     r15
0x1800027cd  pop     r14
0x1800027cf  pop     r12
0x1800027d1  pop     rdi
0x1800027d2  pop     rsi
0x1800027d3  pop     rbx
0x1800027d4  retn
```
