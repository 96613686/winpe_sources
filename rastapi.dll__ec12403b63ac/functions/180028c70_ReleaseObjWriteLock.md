# ReleaseObjWriteLock

- ea: `0x180028c70`
- end: `0x180028d7c`
- name: `ReleaseObjWriteLock`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023610`
- `0x180023a14`
- `0x180023e24`
- `0x180025e40`
- `0x180027414`
- `0x180027ba4`

## callees

- `0x180028c70`
- `0x180028d84`
- `0x180028db8`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180028d50`
- `rtutils!TracePrintfA` at `0x180028d50`

## string_xrefs

- `0x180028d01`: `ReleaseObjWriteLock: Bad handle (0x%x)`
- `0x180028d49`: `ReleaseObjWriteLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall ReleaseObjWriteLock(unsigned int a1)
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
    ReleaseWriteLock(v3);
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
        FormatRRASErrorString(&v5, L"ReleaseObjWriteLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "ReleaseObjWriteLock: Bad handle (0x%x)", a1);
    }
    return 6;
  }
}

```

## disassembly

```asm
0x180028c70  mov     [rsp+arg_8], rbx
0x180028c75  push    rdi
0x180028c76  sub     rsp, 830h
0x180028c7d  mov     rax, cs:__security_cookie
0x180028c84  xor     rax, rsp
0x180028c87  mov     [rsp+838h+var_18], rax
0x180028c8f  mov     ebx, ecx
0x180028c91  mov     edi, ecx
0x180028c93  xor     eax, eax
0x180028c95  shr     ebx, 1
0x180028c97  lea     rcx, [rsp+838h+var_814]; void *
0x180028c9c  mov     [rsp+838h+var_818], eax
0x180028ca0  xor     edx, edx; Val
0x180028ca2  mov     r8d, 7FCh; Size
0x180028ca8  call    memset_0
0x180028cad  movzx   eax, bx
0x180028cb0  cmp     eax, cs:dword_18003EBBC
0x180028cb6  jnb     short loc_180028CEC
0x180028cb8  lea     rcx, [rax+rax*8]
0x180028cbc  shr     ebx, 10h
0x180028cbf  mov     rax, cs:lpMem
0x180028cc6  lea     rcx, [rax+rcx*8]
0x180028cca  cmp     bx, [rcx+40h]
0x180028cce  jnz     short loc_180028CEC
0x180028cd0  cmp     qword ptr [rcx+38h], 0
0x180028cd5  jz      short loc_180028CEC
0x180028cd7  call    ReleaseWriteLock
0x180028cdc  lea     rcx, CriticalSection
0x180028ce3  call    ReleaseReadLock
0x180028ce8  xor     eax, eax
0x180028cea  jmp     short loc_180028D5B
0x180028cec  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180028cf3  jz      short loc_180028D3B
0x180028cf5  cmp     cs:qword_18003EC40, 0
0x180028cfd  jz      short loc_180028D56
0x180028cff  xor     eax, eax
0x180028d01  lea     rdx, aReleaseobjwrit_0; "ReleaseObjWriteLock: Bad handle (0x%x)"
0x180028d08  mov     r8d, edi
0x180028d0b  mov     word ptr [rsp+838h+var_818], ax
0x180028d10  lea     rcx, [rsp+838h+var_818]
0x180028d15  call    FormatRRASErrorString
0x180028d1a  mov     rdx, cs:qword_18003EC40
0x180028d21  lea     r8, [rsp+838h+var_818]
0x180028d26  mov     rcx, cs:gNdpspEtwContext
0x180028d2d  mov     rax, cs:gNdpspTemplateFunc
0x180028d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d39  jmp     short loc_180028D56
0x180028d3b  mov     ecx, cs:dwTraceId; dwTraceID
0x180028d41  cmp     ecx, 0FFFFFFFFh
0x180028d44  jz      short loc_180028D56
0x180028d46  mov     r8d, edi
0x180028d49  lea     rdx, aReleaseobjwrit; "ReleaseObjWriteLock: Bad handle (0x%x)"
0x180028d50  call    cs:__imp_TracePrintfA
0x180028d56  mov     eax, 6
0x180028d5b  mov     rcx, [rsp+838h+var_18]
0x180028d63  xor     rcx, rsp; StackCookie
0x180028d66  call    __security_check_cookie
0x180028d6b  mov     rbx, [rsp+838h+arg_8]
0x180028d73  add     rsp, 830h
0x180028d7a  pop     rdi
0x180028d7b  retn
```
