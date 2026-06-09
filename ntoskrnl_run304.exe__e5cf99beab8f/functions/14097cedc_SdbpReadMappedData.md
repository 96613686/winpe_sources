# SdbpReadMappedData

- ea: `0x14097cedc`
- end: `0x14097cfda`
- name: `SdbpReadMappedData`
- size: `254`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x14081f9a4`
- `0x140824db8`
- `0x140978e20`
- `0x14097b4fc`
- `0x14097ca68`
- `0x14097cb0c`
- `0x14097ce8c`
- `0x14097d194`

## callees

- `0x1404058e0`
- `0x140519f7c`
- `0x1406f4480`
- `0x14071e310`
- `0x14073044c`
- `0x14097cedc`
- `0x14097d158`

## string_xrefs

- `0x14097cf67`: `SdbpReadMappedData`
- `0x14097cf99`: `SdbpReadMappedData`
- `0x14097cfc7`: `SdbpReadMappedData`
- `0x14097cf5a`: `Exception encountered reading SDB file [%x]`
- `0x14097cfba`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpReadMappedData(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  void *v6; // rbx
  char IsUserAddress; // r14

  if ( a2 + a4 < a4 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpReadMappedData",
      855,
      (unsigned int)"Offset and region size add up to cause an integer overflow or underflow");
    return 0;
  }
  if ( *(_DWORD *)(a1 + 20) < a2 + a4 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpReadMappedData",
      860,
      (unsigned int)"Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      a2,
      a4,
      *(_DWORD *)(a1 + 20));
    return 0;
  }
  v6 = (void *)(a2 + *(_QWORD *)(a1 + 8));
  IsUserAddress = MmIsUserAddress(a3);
  if ( (unsigned __int8)MmIsUserAddress(v6) )
  {
    if ( IsUserAddress )
      RtlCopyToUserFromUser(a3, v6, a4);
    else
      RtlCopyFromUser(a3, v6, a4);
  }
  else if ( IsUserAddress )
  {
    RtlCopyToUser(a3, v6, a4);
  }
  else
  {
    memmove(a3, v6, a4);
  }
  return 1;
}

```

## disassembly

```asm
0x14097cedc  push    rbx
0x14097cede  push    rsi
0x14097cedf  push    rdi
0x14097cee0  push    r14
0x14097cee2  sub     rsp, 78h
0x14097cee6  mov     esi, r9d
0x14097cee9  mov     rdi, r8
0x14097ceec  mov     r8, rcx
0x14097ceef  lea     ecx, [rdx+rsi]
0x14097cef2  cmp     ecx, r9d
0x14097cef5  jb      loc_14097CF8C
0x14097cefb  mov     eax, [r8+14h]
0x14097ceff  cmp     eax, ecx
0x14097cf01  jb      loc_14097CFAE
0x14097cf07  mov     ecx, edx
0x14097cf09  mov     rbx, [r8+8]
0x14097cf0d  add     rbx, rcx
0x14097cf10  mov     rcx, rdi
0x14097cf13  call    MmIsUserAddress
0x14097cf18  mov     r14b, al
0x14097cf1b  mov     rcx, rbx
0x14097cf1e  call    MmIsUserAddress
0x14097cf23  mov     r8d, esi; Size
0x14097cf26  mov     rdx, rbx; Src
0x14097cf29  mov     rcx, rdi; void *
0x14097cf2c  test    al, al
0x14097cf2e  jnz     short loc_14097CF3C
0x14097cf30  test    r14b, r14b
0x14097cf33  jnz     short loc_14097CF4F
0x14097cf35  call    memmove
0x14097cf3a  jmp     short loc_14097CF54
0x14097cf3c  test    r14b, r14b
0x14097cf3f  jnz     short loc_14097CF48
0x14097cf41  call    RtlCopyFromUser
0x14097cf46  jmp     short loc_14097CF54
0x14097cf48  call    RtlCopyToUserFromUser
0x14097cf4d  jmp     short loc_14097CF54
0x14097cf4f  call    RtlCopyToUser
0x14097cf54  jmp     short loc_14097CF7C
0x14097cf56  mov     [rsp+98h+var_78], eax
0x14097cf5a  lea     r9, aExceptionEncou; "Exception encountered reading SDB file "...
0x14097cf61  mov     r8d, 374h
0x14097cf67  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14097cf6e  mov     ecx, 1
0x14097cf73  call    AslLogCallPrintf
0x14097cf78  xor     eax, eax
0x14097cf7a  jmp     short loc_14097CF81
0x14097cf7c  mov     eax, 1
0x14097cf81  add     rsp, 78h
0x14097cf85  pop     r14
0x14097cf87  pop     rdi
0x14097cf88  pop     rsi
0x14097cf89  pop     rbx
0x14097cf8a  retn
0x14097cf8c  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x14097cf93  mov     r8d, 357h
0x14097cf99  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14097cfa0  mov     ecx, 1
0x14097cfa5  call    AslLogCallPrintf
0x14097cfaa  xor     eax, eax
0x14097cfac  jmp     short loc_14097CF81
0x14097cfae  mov     [rsp+98h+var_68], eax
0x14097cfb2  mov     [rsp+98h+var_70], esi
0x14097cfb6  mov     [rsp+98h+var_78], edx
0x14097cfba  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x14097cfc1  mov     r8d, 35Ch
0x14097cfc7  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14097cfce  mov     ecx, 1
0x14097cfd3  call    AslLogCallPrintf
0x14097cfd8  jmp     short loc_14097CFAA
0x140b443db  push    rbp
0x140b443dd  sub     rsp, 60h
0x140b443e1  mov     rbp, rdx
0x140b443e4  mov     [rbp+68h], rcx
0x140b443e8  mov     rax, [rbp+68h]
0x140b443ec  mov     r10, [rax+8]
0x140b443f0  mov     rax, [rbp+68h]
0x140b443f4  mov     r9, [rax]
0x140b443f7  mov     rax, [rbp+68h]
0x140b443fb  mov     rcx, [rax]
0x140b443fe  mov     r8d, [rcx+4]
0x140b44402  mov     rax, [rbp+68h]
0x140b44406  mov     rcx, [rax+8]
0x140b4440a  mov     rdx, [rcx+0F8h]
0x140b44411  mov     rax, [rbp+68h]
0x140b44415  mov     rax, [rax]
0x140b44418  mov     [rsp+68h+var_18], r10
0x140b4441d  mov     [rsp+68h+var_20], r9
0x140b44422  mov     [rsp+68h+var_28], r8d
0x140b44427  mov     [rsp+68h+var_30], rdx
0x140b4442c  mov     [rsp+68h+var_38], 0
0x140b44434  lea     rcx, word_14002FE4A
0x140b4443b  mov     [rsp+68h+var_40], rcx
0x140b44440  mov     eax, [rax]
0x140b44442  mov     [rsp+68h+var_48], eax
0x140b44446  lea     r9, aShimExceptionX; "Shim Exception %#x in module \"%hs\", l"...
0x140b4444d  mov     r8d, 0F5h
0x140b44453  lea     rdx, aShimexceptionh; "ShimExceptionHandler"
0x140b4445a  mov     ecx, 1
0x140b4445f  call    AslLogCallPrintf
0x140b44464  mov     dword ptr [rbp+60h], 1
0x140b4446b  mov     eax, [rbp+60h]
0x140b4446e  add     rsp, 60h
0x140b44472  pop     rbp
0x140b44473  retn
```
