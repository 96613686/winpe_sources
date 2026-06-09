# ReleaseObjReadLock

- ea: `0x180028b5c`
- end: `0x180028c68`
- name: `ReleaseObjReadLock`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `6`
- tags: ``

## callers

- `0x180020f80`
- `0x1800226f0`
- `0x1800231f8`
- `0x180023404`
- `0x180023a14`
- `0x180023e24`
- `0x1800244ec`
- `0x180024b38`
- `0x180025244`
- `0x1800257e4`
- `0x180025e40`
- `0x180026a2c`
- `0x180027270`
- `0x1800275b8`
- `0x180027888`
- `0x180027a10`
- `0x180027d38`

## callees

- `0x180028b5c`
- `0x180028d84`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180028c3c`
- `rtutils!TracePrintfA` at `0x180028c3c`

## string_xrefs

- `0x180028bed`: `ReleaseObjReadLock: Bad handle (0x%x)`
- `0x180028c35`: `ReleaseObjReadLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall ReleaseObjReadLock(unsigned int a1)
{
  unsigned int v2; // ebx
  char *v3; // rcx
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = a1 >> 1;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (unsigned __int16)v2 < (unsigned int)dword_18003EBBC
    && (v3 = (char *)lpMem + 72 * (unsigned __int16)v2, HIWORD(v2) == *((_WORD *)v3 + 32))
    && *((_QWORD *)v3 + 7) )
  {
    ReleaseReadLock(v3);
    ReleaseReadLock(&CriticalSection);
    return 0;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"ReleaseObjReadLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "ReleaseObjReadLock: Bad handle (0x%x)", a1);
    }
    return 6;
  }
}

```

## disassembly

```asm
0x180028b5c  mov     [rsp+arg_8], rbx
0x180028b61  push    rdi
0x180028b62  sub     rsp, 830h
0x180028b69  mov     rax, cs:__security_cookie
0x180028b70  xor     rax, rsp
0x180028b73  mov     [rsp+838h+var_18], rax
0x180028b7b  mov     ebx, ecx
0x180028b7d  mov     edi, ecx
0x180028b7f  xor     eax, eax
0x180028b81  shr     ebx, 1
0x180028b83  lea     rcx, [rsp+838h+var_814]; void *
0x180028b88  mov     [rsp+838h+var_818], eax
0x180028b8c  xor     edx, edx; Val
0x180028b8e  mov     r8d, 7FCh; Size
0x180028b94  call    memset_0
0x180028b99  movzx   eax, bx
0x180028b9c  cmp     eax, cs:dword_18003EBBC
0x180028ba2  jnb     short loc_180028BD8
0x180028ba4  lea     rcx, [rax+rax*8]
0x180028ba8  shr     ebx, 10h
0x180028bab  mov     rax, cs:lpMem
0x180028bb2  lea     rcx, [rax+rcx*8]
0x180028bb6  cmp     bx, [rcx+40h]
0x180028bba  jnz     short loc_180028BD8
0x180028bbc  cmp     qword ptr [rcx+38h], 0
0x180028bc1  jz      short loc_180028BD8
0x180028bc3  call    ReleaseReadLock
0x180028bc8  lea     rcx, CriticalSection
0x180028bcf  call    ReleaseReadLock
0x180028bd4  xor     eax, eax
0x180028bd6  jmp     short loc_180028C47
0x180028bd8  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180028bdf  jz      short loc_180028C27
0x180028be1  cmp     cs:qword_18003EC40, 0
0x180028be9  jz      short loc_180028C42
0x180028beb  xor     eax, eax
0x180028bed  lea     rdx, aReleaseobjread_0; "ReleaseObjReadLock: Bad handle (0x%x)"
0x180028bf4  mov     r8d, edi
0x180028bf7  mov     word ptr [rsp+838h+var_818], ax
0x180028bfc  lea     rcx, [rsp+838h+var_818]
0x180028c01  call    FormatRRASErrorString
0x180028c06  mov     rdx, cs:qword_18003EC40
0x180028c0d  lea     r8, [rsp+838h+var_818]
0x180028c12  mov     rcx, cs:gNdpspEtwContext
0x180028c19  mov     rax, cs:gNdpspTemplateFunc
0x180028c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c25  jmp     short loc_180028C42
0x180028c27  mov     ecx, cs:dwTraceId; dwTraceID
0x180028c2d  cmp     ecx, 0FFFFFFFFh
0x180028c30  jz      short loc_180028C42
0x180028c32  mov     r8d, edi
0x180028c35  lea     rdx, aReleaseobjread; "ReleaseObjReadLock: Bad handle (0x%x)"
0x180028c3c  call    cs:__imp_TracePrintfA
0x180028c42  mov     eax, 6
0x180028c47  mov     rcx, [rsp+838h+var_18]
0x180028c4f  xor     rcx, rsp; StackCookie
0x180028c52  call    __security_check_cookie
0x180028c57  mov     rbx, [rsp+838h+arg_8]
0x180028c5f  add     rsp, 830h
0x180028c66  pop     rdi
0x180028c67  retn
```
