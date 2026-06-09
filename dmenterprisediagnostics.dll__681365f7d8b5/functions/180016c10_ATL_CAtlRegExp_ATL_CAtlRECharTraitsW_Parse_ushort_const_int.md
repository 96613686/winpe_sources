# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180016c10`
- end: `0x180016d67`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180011618`
- `0x1800195c0`

## callees

- `0x180007d7c`
- `0x180009e24`
- `0x1800122a0`
- `0x180013fcc`
- `0x180016c10`
- `0x180017a40`
- `0x18001841c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180016c93`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180016c93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d3e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016c56`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016c56`

## string_xrefs

- `0x180016c71`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

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
  __int64 v9; // rbp
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
  v8 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v9 = v8;
  if ( v8 < 0 )
    return 1;
  if ( *v11 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) >= 0 )
      goto LABEL_7;
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) < 0 )
    return 1;
  ++v11;
LABEL_7:
  LOBYTE(v12) = 1;
  ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v11, &v12);
  if ( !*a1 )
  {
    *(_QWORD *)(ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
                  a1 + 2,
                  v9)
              + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
      return 1;
  }
  if ( v5 != L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v5);
  return *a1;
}

```

## disassembly

```asm
0x180016c10  mov     rax, rsp
0x180016c13  mov     [rax+8], rbx
0x180016c17  mov     [rax+20h], rbp
0x180016c1b  mov     [rax+18h], r8d
0x180016c1f  mov     [rax+10h], rdx
0x180016c23  push    rsi
0x180016c24  push    rdi
0x180016c25  push    r15
0x180016c27  sub     rsp, 20h
0x180016c2b  mov     rbx, rcx
0x180016c2e  xor     edx, edx
0x180016c30  add     rcx, 8
0x180016c34  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x180016c39  nop
0x180016c3a  mov     qword ptr [rbx+28h], 0
0x180016c42  mov     dword ptr [rbx], 0
0x180016c48  mov     dword ptr [rbx+30h], 0
0x180016c4f  mov     ebp, 6Ah ; 'j'
0x180016c54  mov     ecx, ebp; Size
0x180016c56  call    cs:__imp_malloc
0x180016c5d  nop     dword ptr [rax+rax+00h]
0x180016c62  mov     rdi, rax
0x180016c65  test    rax, rax
0x180016c68  jz      loc_180016D4E
0x180016c6e  mov     r9d, ebp; SourceSize
0x180016c71  lea     r15, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180016c78  mov     r8, r15; Source
0x180016c7b  mov     edx, ebp; DestinationSize
0x180016c7d  mov     rcx, rax; Destination
0x180016c80  call    memcpy_s
0x180016c85  mov     ecx, eax; int
0x180016c87  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016c8c  nop
0x180016c8d  lea     edx, [rbp-35h]; SizeInWords
0x180016c90  mov     rcx, rdi; String
0x180016c93  call    cs:__imp__wcslwr_s
0x180016c9a  nop     dword ptr [rax+rax+00h]
0x180016c9f  mov     ecx, eax; int
0x180016ca1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016ca6  nop
0x180016ca7  mov     [rsp+38h+arg_8], rdi
0x180016cac  lea     edx, [rbp-5Ah]
0x180016caf  mov     rcx, rbx
0x180016cb2  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016cb7  movsxd  rbp, eax
0x180016cba  test    eax, eax
0x180016cbc  js      loc_180016D4E
0x180016cc2  mov     rcx, [rsp+38h+arg_8]
0x180016cc7  cmp     word ptr [rcx], 5Eh ; '^'
0x180016ccb  mov     rcx, rbx
0x180016cce  jnz     short loc_180016CE6
0x180016cd0  mov     edx, 1Ch
0x180016cd5  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016cda  test    eax, eax
0x180016cdc  js      short loc_180016D4E
0x180016cde  add     [rsp+38h+arg_8], 2
0x180016ce4  jmp     short loc_180016CF4
0x180016ce6  mov     edx, 1Dh
0x180016ceb  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016cf0  test    eax, eax
0x180016cf2  js      short loc_180016D4E
0x180016cf4  mov     byte ptr [rsp+38h+arg_10], 1
0x180016cf9  lea     r8, [rsp+38h+arg_10]
0x180016cfe  lea     rdx, [rsp+38h+arg_8]
0x180016d03  mov     rcx, rbx
0x180016d06  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180016d0b  cmp     dword ptr [rbx], 0
0x180016d0e  jnz     short loc_180016D36
0x180016d10  mov     rdx, rbp
0x180016d13  lea     rcx, [rbx+8]
0x180016d17  call    ??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)
0x180016d1c  nop
0x180016d1d  mov     qword ptr [rax+8], 2
0x180016d25  mov     edx, 1Eh
0x180016d2a  mov     rcx, rbx
0x180016d2d  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180016d32  test    eax, eax
0x180016d34  js      short loc_180016D4E
0x180016d36  cmp     rdi, r15
0x180016d39  jz      short loc_180016D4A
0x180016d3b  mov     rcx, rdi; Block
0x180016d3e  call    cs:__imp_free
0x180016d45  nop     dword ptr [rax+rax+00h]
0x180016d4a  mov     eax, [rbx]
0x180016d4c  jmp     short loc_180016D53
0x180016d4e  mov     eax, 1
0x180016d53  mov     rbx, [rsp+38h+arg_0]
0x180016d58  mov     rbp, [rsp+38h+arg_18]
0x180016d5d  add     rsp, 20h
0x180016d61  pop     r15
0x180016d63  pop     rdi
0x180016d64  pop     rsi
0x180016d65  retn
```
