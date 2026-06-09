# LdrpInitializeApplicationVerifierPackage

- ea: `0x1800d5428`
- end: `0x1800d5618`
- name: `LdrpInitializeApplicationVerifierPackage`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d36e4`

## callees

- `0x18001eb80`
- `0x180029480`
- `0x1800c4700`
- `0x1800d4620`
- `0x1800d5428`
- `0x180113878`

## string_xrefs

- `0x1800d55c7`: `Per-DLL page heap is disabled since fast fill heap is enabled\n`

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
            8996,
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
0x1800d5428  push    rbx
0x1800d542a  push    rbp
0x1800d542b  push    rsi
0x1800d542c  push    rdi
0x1800d542d  push    r12
0x1800d542f  push    r14
0x1800d5431  push    r15
0x1800d5433  sub     rsp, 40h
0x1800d5437  cmp     byte ptr ds:7FFE02ECh, 0
0x1800d543f  xorps   xmm0, xmm0
0x1800d5442  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800d5447  mov     r14, r9
0x1800d544a  mov     r12b, r8b
0x1800d544d  mov     rbx, rdx
0x1800d5450  mov     rbp, rcx
0x1800d5453  jz      short loc_1800D5464
0x1800d5455  and     dword ptr [rdx+0BCh], 0FDFFFEFFh
0x1800d545f  jmp     loc_1800D5606
0x1800d5464  test    r12b, r12b
0x1800d5467  jz      short loc_1800D54D6
0x1800d5469  movzx   r15d, word ptr [rcx]
0x1800d546d  mov     edi, r15d
0x1800d5470  mov     esi, r15d
0x1800d5473  add     rdi, [rcx+8]
0x1800d5477  test    r15d, r15d
0x1800d547a  jz      short loc_1800D548C
0x1800d547c  cmp     word ptr [rdi-2], 5Ch ; '\'
0x1800d5481  jz      short loc_1800D548C
0x1800d5483  add     rdi, 0FFFFFFFFFFFFFFFEh
0x1800d5487  add     esi, 0FFFFFFFEh
0x1800d548a  jnz     short loc_1800D547C
0x1800d548c  lea     rdx, aSppsvcExe; "SPPsvc.exe"
0x1800d5493  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800d5498  call    RtlInitUnicodeString
0x1800d549d  movzx   r9d, [rsp+78h+DestinationString.Length]
0x1800d54a3  sub     r15w, si
0x1800d54a7  mov     r8, [rsp+78h+DestinationString.Buffer]
0x1800d54ac  mov     rcx, rdi
0x1800d54af  movzx   edx, r15w
0x1800d54b3  shr     rdx, 1
0x1800d54b6  shr     r9, 1
0x1800d54b9  mov     byte ptr [rsp+78h+Format], 1
0x1800d54be  call    RtlCompareUnicodeStrings
0x1800d54c3  test    eax, eax
0x1800d54c5  jnz     short loc_1800D54D6
0x1800d54c7  and     dword ptr [rbx+0BCh], 0FDFFFEFFh
0x1800d54d1  jmp     loc_1800D5606
0x1800d54d6  test    dword ptr [rbx+0BCh], 2000100h
0x1800d54e0  mov     r8, r14
0x1800d54e3  mov     rax, [rsp+78h+arg_28]
0x1800d54eb  mov     rdx, rbp
0x1800d54ee  mov     qword ptr [rsp+78h+ArgList], rax
0x1800d54f3  setnz   cs:LdrpShouldCreateStackTraceDb
0x1800d54fa  mov     rax, [rsp+78h+arg_20]
0x1800d5502  xor     r9d, r9d
0x1800d5505  mov     cl, r12b
0x1800d5508  mov     [rsp+78h+Format], rax
0x1800d550d  call    AVrfInitializeVerifier
0x1800d5512  mov     ecx, [rbx+0BCh]
0x1800d5518  test    eax, eax
0x1800d551a  jns     short loc_1800D5544
0x1800d551c  and     ecx, 0FDFFFEFFh
0x1800d5522  mov     cs:dword_1801C4588, 0
0x1800d552c  mov     [rbx+0BCh], ecx
0x1800d5532  mov     rcx, cs:RtlpDebugPageHeapTable
0x1800d5539  mov     dword ptr [rcx], 0
0x1800d553f  jmp     loc_1800D5608
0x1800d5544  bt      ecx, 19h
0x1800d5548  jnb     loc_1800D5606
0x1800d554e  mov     rax, cs:RtlpDebugPageHeapTable
0x1800d5555  and     ecx, 0FFFF670Fh
0x1800d555b  or      esi, 0FFFFFFFFh
0x1800d555e  mov     [rbx+0BCh], ecx
0x1800d5564  mov     cs:LdrpShouldCreateStackTraceDb, 1
0x1800d556b  mov     edi, [rax]
0x1800d556d  mov     [rax], esi
0x1800d556f  test    r14, r14
0x1800d5572  jz      short loc_1800D55A7
0x1800d5574  mov     r8d, 4
0x1800d557a  mov     qword ptr [rsp+78h+ArgList], 0; ArgList
0x1800d5583  mov     r9, rax
0x1800d5586  mov     dword ptr [rsp+78h+Format], r8d
0x1800d558b  lea     rdx, aPageheapflags; "PageHeapFlags"
0x1800d5592  mov     rcx, r14
0x1800d5595  call    RtlQueryImageFileKeyOption
0x1800d559a  test    eax, eax
0x1800d559c  mov     rax, cs:RtlpDebugPageHeapTable
0x1800d55a3  jns     short loc_1800D55A7
0x1800d55a5  mov     [rax], esi
0x1800d55a7  cmp     [rax], esi
0x1800d55a9  jnz     short loc_1800D55AF
0x1800d55ab  mov     [rax], edi
0x1800d55ad  jmp     short loc_1800D55B1
0x1800d55af  mov     edi, [rax]
0x1800d55b1  bt      edi, 0Ah
0x1800d55b5  setb    cl
0x1800d55b8  bt      cs:AVrfpVerifierFlags, 0Fh
0x1800d55c0  setb    al
0x1800d55c3  test    al, cl
0x1800d55c5  jz      short loc_1800D55FC
0x1800d55c7  lea     rax, aPerDllPageHeap; "Per-DLL page heap is disabled since fas"...
0x1800d55ce  mov     r9d, 2; int
0x1800d55d4  lea     r8, aLdrpinitialize_0; "LdrpInitializeApplicationVerifierPackag"...
0x1800d55db  mov     [rsp+78h+Format], rax; Format
0x1800d55e0  mov     edx, 2324h; int
0x1800d55e5  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d55ec  call    LdrpLogInternal
0x1800d55f1  mov     rax, cs:RtlpDebugPageHeapTable
0x1800d55f8  btr     dword ptr [rax], 0Ah
0x1800d55fc  mov     cs:dword_1801C4588, 1
0x1800d5606  xor     eax, eax
0x1800d5608  add     rsp, 40h
0x1800d560c  pop     r15
0x1800d560e  pop     r14
0x1800d5610  pop     r12
0x1800d5612  pop     rdi
0x1800d5613  pop     rsi
0x1800d5614  pop     rbp
0x1800d5615  pop     rbx
0x1800d5616  retn
```
