# LdrpInitializeApplicationVerifierPackage

- ea: `0x1800741c8`
- end: `0x1800743b8`
- name: `LdrpInitializeApplicationVerifierPackage`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007248c`

## callees

- `0x18001eb80`
- `0x180029590`
- `0x1800733c0`
- `0x1800741c8`
- `0x1800c0420`
- `0x180112488`

## string_xrefs

- `0x180074367`: `Per-DLL page heap is disabled since fast fill heap is enabled\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeApplicationVerifierPackage(
        unsigned __int16 *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  __int16 v10; // r15
  int v11; // esi
  __int64 v12; // rdi
  __int64 result; // rax
  int v14; // ecx
  char *v15; // rax
  int v16; // edi
  bool v17; // sf
  char ArgList; // [rsp+28h] [rbp-50h]
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  DestinationString = 0;
  if ( MEMORY[0x7FFE02EC] )
  {
    *(_DWORD *)(a2 + 188) &= 0xFDFFFEFF;
  }
  else
  {
    if ( !a3 )
      goto LABEL_9;
    v10 = *a1;
    v11 = *a1;
    v12 = *((_QWORD *)a1 + 1) + *a1;
    if ( *a1 )
    {
      do
      {
        if ( *(_WORD *)(v12 - 2) == 92 )
          break;
        v12 -= 2;
        v11 -= 2;
      }
      while ( v11 );
    }
    RtlInitUnicodeString(&DestinationString, L"SPPsvc.exe");
    if ( (unsigned int)RtlCompareUnicodeStrings(
                         v12,
                         (unsigned __int64)(unsigned __int16)(v10 - v11) >> 1,
                         DestinationString.Buffer,
                         (unsigned __int64)DestinationString.Length >> 1,
                         1) )
    {
LABEL_9:
      LdrpShouldCreateStackTraceDb = (*(_DWORD *)(a2 + 188) & 0x2000100) != 0;
      result = AVrfInitializeVerifier(a3, (__int64)a1, a4, 0, a5, a6);
      v14 = *(_DWORD *)(a2 + 188);
      if ( (int)result < 0 )
      {
        dword_1801C4588 = 0;
        *(_DWORD *)(a2 + 188) = v14 & 0xFDFFFEFF;
        *(_DWORD *)RtlpDebugPageHeapTable = 0;
        return result;
      }
      if ( (v14 & 0x2000000) != 0 )
      {
        v15 = (char *)RtlpDebugPageHeapTable;
        *(_DWORD *)(a2 + 188) = v14 & 0xFFFF670F;
        LdrpShouldCreateStackTraceDb = 1;
        v16 = *(_DWORD *)v15;
        *(_DWORD *)v15 = -1;
        if ( a4 )
        {
          v17 = (int)RtlQueryImageFileKeyOption(a4, L"PageHeapFlags", 4, v15, 4, 0) < 0;
          v15 = (char *)RtlpDebugPageHeapTable;
          if ( v17 )
            *(_DWORD *)RtlpDebugPageHeapTable = -1;
        }
        if ( *(_DWORD *)v15 == -1 )
          *(_DWORD *)v15 = v16;
        else
          v16 = *(_DWORD *)v15;
        if ( (((v16 & 0x400) != 0) & _bittest(&AVrfpVerifierFlags, 0xFu)) != 0 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            9140,
            (int)"LdrpInitializeApplicationVerifierPackage",
            2,
            "Per-DLL page heap is disabled since fast fill heap is enabled\n",
            ArgList);
          *(_DWORD *)RtlpDebugPageHeapTable &= ~0x400u;
        }
        dword_1801C4588 = 1;
      }
    }
    else
    {
      *(_DWORD *)(a2 + 188) &= 0xFDFFFEFF;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800741c8  push    rbx
0x1800741ca  push    rbp
0x1800741cb  push    rsi
0x1800741cc  push    rdi
0x1800741cd  push    r12
0x1800741cf  push    r14
0x1800741d1  push    r15
0x1800741d3  sub     rsp, 40h
0x1800741d7  cmp     byte ptr ds:7FFE02ECh, 0
0x1800741df  xorps   xmm0, xmm0
0x1800741e2  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800741e7  mov     r14, r9
0x1800741ea  mov     r12b, r8b
0x1800741ed  mov     rbx, rdx
0x1800741f0  mov     rbp, rcx
0x1800741f3  jz      short loc_180074204
0x1800741f5  and     dword ptr [rdx+0BCh], 0FDFFFEFFh
0x1800741ff  jmp     loc_1800743A6
0x180074204  test    r12b, r12b
0x180074207  jz      short loc_180074276
0x180074209  movzx   r15d, word ptr [rcx]
0x18007420d  mov     edi, r15d
0x180074210  mov     esi, r15d
0x180074213  add     rdi, [rcx+8]
0x180074217  test    r15d, r15d
0x18007421a  jz      short loc_18007422C
0x18007421c  cmp     word ptr [rdi-2], 5Ch ; '\'
0x180074221  jz      short loc_18007422C
0x180074223  add     rdi, 0FFFFFFFFFFFFFFFEh
0x180074227  add     esi, 0FFFFFFFEh
0x18007422a  jnz     short loc_18007421C
0x18007422c  lea     rdx, SourceString; "SPPsvc.exe"
0x180074233  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180074238  call    RtlInitUnicodeString
0x18007423d  movzx   r9d, [rsp+78h+DestinationString.Length]
0x180074243  sub     r15w, si
0x180074247  mov     r8, [rsp+78h+DestinationString.Buffer]
0x18007424c  mov     rcx, rdi
0x18007424f  movzx   edx, r15w
0x180074253  shr     rdx, 1
0x180074256  shr     r9, 1
0x180074259  mov     byte ptr [rsp+78h+Format], 1
0x18007425e  call    RtlCompareUnicodeStrings
0x180074263  test    eax, eax
0x180074265  jnz     short loc_180074276
0x180074267  and     dword ptr [rbx+0BCh], 0FDFFFEFFh
0x180074271  jmp     loc_1800743A6
0x180074276  test    dword ptr [rbx+0BCh], 2000100h
0x180074280  mov     r8, r14
0x180074283  mov     rax, [rsp+78h+arg_28]
0x18007428b  mov     rdx, rbp
0x18007428e  mov     qword ptr [rsp+78h+ArgList], rax
0x180074293  setnz   cs:LdrpShouldCreateStackTraceDb
0x18007429a  mov     rax, [rsp+78h+arg_20]
0x1800742a2  xor     r9d, r9d
0x1800742a5  mov     cl, r12b
0x1800742a8  mov     [rsp+78h+Format], rax
0x1800742ad  call    AVrfInitializeVerifier
0x1800742b2  mov     ecx, [rbx+0BCh]
0x1800742b8  test    eax, eax
0x1800742ba  jns     short loc_1800742E4
0x1800742bc  and     ecx, 0FDFFFEFFh
0x1800742c2  mov     cs:dword_1801C4588, 0
0x1800742cc  mov     [rbx+0BCh], ecx
0x1800742d2  mov     rcx, cs:RtlpDebugPageHeapTable
0x1800742d9  mov     dword ptr [rcx], 0
0x1800742df  jmp     loc_1800743A8
0x1800742e4  bt      ecx, 19h
0x1800742e8  jnb     loc_1800743A6
0x1800742ee  mov     rax, cs:RtlpDebugPageHeapTable
0x1800742f5  and     ecx, 0FFFF670Fh
0x1800742fb  or      esi, 0FFFFFFFFh
0x1800742fe  mov     [rbx+0BCh], ecx
0x180074304  mov     cs:LdrpShouldCreateStackTraceDb, 1
0x18007430b  mov     edi, [rax]
0x18007430d  mov     [rax], esi
0x18007430f  test    r14, r14
0x180074312  jz      short loc_180074347
0x180074314  mov     r8d, 4
0x18007431a  mov     qword ptr [rsp+78h+ArgList], 0; ArgList
0x180074323  mov     r9, rax
0x180074326  mov     dword ptr [rsp+78h+Format], r8d
0x18007432b  lea     rdx, aPageheapflags; "PageHeapFlags"
0x180074332  mov     rcx, r14
0x180074335  call    RtlQueryImageFileKeyOption
0x18007433a  test    eax, eax
0x18007433c  mov     rax, cs:RtlpDebugPageHeapTable
0x180074343  jns     short loc_180074347
0x180074345  mov     [rax], esi
0x180074347  cmp     [rax], esi
0x180074349  jnz     short loc_18007434F
0x18007434b  mov     [rax], edi
0x18007434d  jmp     short loc_180074351
0x18007434f  mov     edi, [rax]
0x180074351  bt      edi, 0Ah
0x180074355  setb    cl
0x180074358  bt      cs:AVrfpVerifierFlags, 0Fh
0x180074360  setb    al
0x180074363  test    al, cl
0x180074365  jz      short loc_18007439C
0x180074367  lea     rax, aPerDllPageHeap; "Per-DLL page heap is disabled since fas"...
0x18007436e  mov     r9d, 2; int
0x180074374  lea     r8, aLdrpinitialize_0; "LdrpInitializeApplicationVerifierPackag"...
0x18007437b  mov     [rsp+78h+Format], rax; Format
0x180074380  mov     edx, 23B4h; int
0x180074385  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18007438c  call    LdrpLogInternal
0x180074391  mov     rax, cs:RtlpDebugPageHeapTable
0x180074398  btr     dword ptr [rax], 0Ah
0x18007439c  mov     cs:dword_1801C4588, 1
0x1800743a6  xor     eax, eax
0x1800743a8  add     rsp, 40h
0x1800743ac  pop     r15
0x1800743ae  pop     r14
0x1800743b0  pop     r12
0x1800743b2  pop     rdi
0x1800743b3  pop     rsi
0x1800743b4  pop     rbp
0x1800743b5  pop     rbx
0x1800743b6  retn
```
