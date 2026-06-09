# PEDecoder::CheckILOnlyImportByNameTable(ulong)

- ea: `0x18003d794`
- end: `0x18003d874`
- name: `?CheckILOnlyImportByNameTable@PEDecoder@@AEBA?AVCHECK@@K@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d87c`

## callees

- `0x18000e83c`
- `0x180039e3c`
- `0x18003d794`
- `0x18003dd8c`
- `0x18003e0e0`

## string_xrefs

- `0x18003d827`: `_CorDllMain`

## pseudocode

```c
_QWORD *__fastcall PEDecoder::CheckILOnlyImportByNameTable(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v4; // edi
  int *RvaData; // rax
  int *v7; // rdi
  const char *v8; // rdi
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  char v12; // [rsp+58h] [rbp+20h] BYREF

  v4 = a3;
  *a2 = *(_QWORD *)PEDecoder::CheckRva(a1, &v12, a3, 8)
     || (RvaData = (int *)PEDecoder::GetRvaData(a1, v4), v7 = RvaData, !*RvaData)
     || RvaData[1]
     || *RvaData < 0
     || *(_QWORD *)PEDecoder::CheckRva(a1, &v12, (unsigned int)*RvaData, 14)
     || (v8 = (const char *)(PEDecoder::GetRvaData(a1, (unsigned int)*v7) + 2),
         (unsigned int)SString::CaseCompareHelperA(v8, "_CorDllMain", v9, v10, 0, 0))
     && stricmp(v8, "_CorExeMain");
  return a2;
}

```

## disassembly

```asm
0x18003d794  mov     rax, rsp
0x18003d797  mov     [rax+8], rbx
0x18003d79b  mov     [rax+10h], rsi
0x18003d79f  push    rdi
0x18003d7a0  sub     rsp, 30h
0x18003d7a4  mov     rbx, rdx
0x18003d7a7  mov     dword ptr [rax-10h], 0
0x18003d7ae  lea     rdx, [rax+20h]
0x18003d7b2  mov     dword ptr [rax-18h], 0
0x18003d7b9  mov     r9d, 8
0x18003d7bf  mov     edi, r8d
0x18003d7c2  mov     rsi, rcx
0x18003d7c5  call    ?CheckRva@PEDecoder@@QEBA?AVCHECK@@KIHW4IsNullOK@@@Z; PEDecoder::CheckRva(ulong,uint,int,IsNullOK)
0x18003d7ca  cmp     qword ptr [rax], 0
0x18003d7ce  jnz     loc_18003D85A
0x18003d7d4  mov     edx, edi
0x18003d7d6  mov     rcx, rsi
0x18003d7d9  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18003d7de  mov     rdi, rax
0x18003d7e1  cmp     dword ptr [rax], 0
0x18003d7e4  jz      short loc_18003D85A
0x18003d7e6  cmp     dword ptr [rax+4], 0
0x18003d7ea  jnz     short loc_18003D85A
0x18003d7ec  cmp     dword ptr [rax], 0
0x18003d7ef  jl      short loc_18003D85A
0x18003d7f1  mov     r8d, [rax]
0x18003d7f4  lea     rdx, [rsp+38h+arg_18]
0x18003d7f9  mov     [rsp+38h+var_10], 0; int
0x18003d801  mov     r9d, 0Eh
0x18003d807  mov     rcx, rsi
0x18003d80a  mov     [rsp+38h+var_18], 0; int
0x18003d812  call    ?CheckRva@PEDecoder@@QEBA?AVCHECK@@KIHW4IsNullOK@@@Z; PEDecoder::CheckRva(ulong,uint,int,IsNullOK)
0x18003d817  cmp     qword ptr [rax], 0
0x18003d81b  jnz     short loc_18003D85A
0x18003d81d  mov     edx, [rdi]
0x18003d81f  mov     rcx, rsi
0x18003d822  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18003d827  lea     rdx, aCordllmain_0; "_CorDllMain"
0x18003d82e  lea     rdi, [rax+2]
0x18003d832  mov     rcx, rdi; char *
0x18003d835  call    ?CaseCompareHelperA@SString@@CAHPEBD0IPEBGHH@Z; SString::CaseCompareHelperA(char const *,char const *,uint,ushort const *,int,int)
0x18003d83a  test    eax, eax
0x18003d83c  jz      short loc_18003D851
0x18003d83e  lea     rdx, aCorexemain_0; "_CorExeMain"
0x18003d845  mov     rcx, rdi; String1
0x18003d848  call    _stricmp
0x18003d84d  test    eax, eax
0x18003d84f  jnz     short loc_18003D85A
0x18003d851  mov     qword ptr [rbx], 0
0x18003d858  jmp     short loc_18003D861
0x18003d85a  mov     qword ptr [rbx], 1
0x18003d861  mov     rsi, [rsp+38h+arg_8]
0x18003d866  mov     rax, rbx
0x18003d869  mov     rbx, [rsp+38h+arg_0]
0x18003d86e  add     rsp, 30h
0x18003d872  pop     rdi
0x18003d873  retn
```
