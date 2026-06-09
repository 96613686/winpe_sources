# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180016230`
- end: `0x180016374`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180010e80`
- `0x180018bac`

## callees

- `0x180007a20`
- `0x180009948`
- `0x180011ad0`
- `0x1800137e4`
- `0x180016230`
- `0x18001704c`
- `0x180017a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800162ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800162ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016352`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016352`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016276`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016276`

## string_xrefs

- `0x18001628b`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  errno_t v6; // eax
  errno_t v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rbp
  wchar_t *v11; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = a3;
  v11 = a2;
  ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(
    a1 + 2,
    0);
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v4 = (wchar_t *)malloc(0x6Au);
  v5 = v4;
  if ( !v4 )
    return 1;
  v6 = memcpy_s(v4, 0x6Au, L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})", 0x6Au);
  ATL::AtlCrtErrorCheck(v6);
  v7 = _wcslwr_s(v5, 0x35u);
  ATL::AtlCrtErrorCheck(v7);
  v11 = v5;
  v8 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 16);
  v9 = v8;
  if ( v8 < 0 )
    return 1;
  if ( *v11 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 29) >= 0 )
      goto LABEL_7;
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 28) < 0 )
    return 1;
  ++v11;
LABEL_7:
  LOBYTE(v12) = 1;
  ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v11, &v12);
  if ( !*a1 )
  {
    *(_QWORD *)(ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
                  (_QWORD *)a1 + 1,
                  v9)
              + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 30) < 0 )
      return 1;
  }
  if ( v5 != L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v5);
  return *a1;
}

```

## disassembly

```asm
0x180016230  mov     rax, rsp
0x180016233  mov     [rax+8], rbx
0x180016237  mov     [rax+20h], rbp
0x18001623b  mov     [rax+18h], r8d
0x18001623f  mov     [rax+10h], rdx
0x180016243  push    rsi
0x180016244  push    rdi
0x180016245  push    r15
0x180016247  sub     rsp, 20h
0x18001624b  mov     rbx, rcx
0x18001624e  xor     edx, edx
0x180016250  add     rcx, 8
0x180016254  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x180016259  nop
0x18001625a  mov     qword ptr [rbx+28h], 0
0x180016262  mov     dword ptr [rbx], 0
0x180016268  mov     dword ptr [rbx+30h], 0
0x18001626f  mov     ebp, 6Ah ; 'j'
0x180016274  mov     ecx, ebp; Size
0x180016276  call    cs:__imp_malloc
0x18001627c  mov     rdi, rax
0x18001627f  test    rax, rax
0x180016282  jz      loc_18001635C
0x180016288  mov     r9d, ebp; SourceSize
0x18001628b  lea     r15, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180016292  mov     r8, r15; Source
0x180016295  mov     edx, ebp; DestinationSize
0x180016297  mov     rcx, rax; Destination
0x18001629a  call    memcpy_s
0x18001629f  mov     ecx, eax; int
0x1800162a1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800162a6  nop
0x1800162a7  lea     edx, [rbp-35h]; SizeInWords
0x1800162aa  mov     rcx, rdi; String
0x1800162ad  call    cs:__imp__wcslwr_s
0x1800162b3  mov     ecx, eax; int
0x1800162b5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800162ba  nop
0x1800162bb  mov     [rsp+38h+arg_8], rdi
0x1800162c0  lea     edx, [rbp-5Ah]
0x1800162c3  mov     rcx, rbx
0x1800162c6  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x1800162cb  movsxd  rbp, eax
0x1800162ce  test    eax, eax
0x1800162d0  js      loc_18001635C
0x1800162d6  mov     rcx, [rsp+38h+arg_8]
0x1800162db  cmp     word ptr [rcx], 5Eh ; '^'
0x1800162df  mov     rcx, rbx
0x1800162e2  jnz     short loc_1800162FA
0x1800162e4  mov     edx, 1Ch
0x1800162e9  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x1800162ee  test    eax, eax
0x1800162f0  js      short loc_18001635C
0x1800162f2  add     [rsp+38h+arg_8], 2
0x1800162f8  jmp     short loc_180016308
0x1800162fa  mov     edx, 1Dh
0x1800162ff  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016304  test    eax, eax
0x180016306  js      short loc_18001635C
0x180016308  mov     byte ptr [rsp+38h+arg_10], 1
0x18001630d  lea     r8, [rsp+38h+arg_10]
0x180016312  lea     rdx, [rsp+38h+arg_8]
0x180016317  mov     rcx, rbx
0x18001631a  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x18001631f  cmp     dword ptr [rbx], 0
0x180016322  jnz     short loc_18001634A
0x180016324  mov     rdx, rbp
0x180016327  lea     rcx, [rbx+8]
0x18001632b  call    ??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)
0x180016330  nop
0x180016331  mov     qword ptr [rax+8], 2
0x180016339  mov     edx, 1Eh
0x18001633e  mov     rcx, rbx
0x180016341  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016346  test    eax, eax
0x180016348  js      short loc_18001635C
0x18001634a  cmp     rdi, r15
0x18001634d  jz      short loc_180016358
0x18001634f  mov     rcx, rdi; Block
0x180016352  call    cs:__imp_free
0x180016358  mov     eax, [rbx]
0x18001635a  jmp     short loc_180016361
0x18001635c  mov     eax, 1
0x180016361  mov     rbx, [rsp+38h+arg_0]
0x180016366  mov     rbp, [rsp+38h+arg_18]
0x18001636b  add     rsp, 20h
0x18001636f  pop     r15
0x180016371  pop     rdi
0x180016372  pop     rsi
0x180016373  retn
```
