# SdbpReadMappedData

- ea: `0x1408c2d0c`
- end: `0x1408c2e0a`
- name: `SdbpReadMappedData`
- size: `254`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x140821914`
- `0x140826d28`
- `0x1408bebe8`
- `0x1408c132c`
- `0x1408c2898`
- `0x1408c293c`
- `0x1408c2cbc`
- `0x1408c2fc4`

## callees

- `0x14041a320`
- `0x14052039c`
- `0x1406f6f80`
- `0x140722300`
- `0x140734c10`
- `0x1408c2d0c`
- `0x1408c2f88`

## string_xrefs

- `0x1408c2d97`: `SdbpReadMappedData`
- `0x1408c2dc9`: `SdbpReadMappedData`
- `0x1408c2df7`: `SdbpReadMappedData`
- `0x1408c2d8a`: `Exception encountered reading SDB file [%x]`
- `0x1408c2dea`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

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
      853,
      (unsigned int)"Offset and region size add up to cause an integer overflow or underflow");
    return 0;
  }
  if ( *(_DWORD *)(a1 + 20) < a2 + a4 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpReadMappedData",
      858,
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
0x1408c2d0c  push    rbx
0x1408c2d0e  push    rsi
0x1408c2d0f  push    rdi
0x1408c2d10  push    r14
0x1408c2d12  sub     rsp, 78h
0x1408c2d16  mov     esi, r9d
0x1408c2d19  mov     rdi, r8
0x1408c2d1c  mov     r8, rcx
0x1408c2d1f  lea     ecx, [rdx+rsi]
0x1408c2d22  cmp     ecx, r9d
0x1408c2d25  jb      loc_1408C2DBC
0x1408c2d2b  mov     eax, [r8+14h]
0x1408c2d2f  cmp     eax, ecx
0x1408c2d31  jb      loc_1408C2DDE
0x1408c2d37  mov     ecx, edx
0x1408c2d39  mov     rbx, [r8+8]
0x1408c2d3d  add     rbx, rcx
0x1408c2d40  mov     rcx, rdi
0x1408c2d43  call    MmIsUserAddress
0x1408c2d48  mov     r14b, al
0x1408c2d4b  mov     rcx, rbx
0x1408c2d4e  call    MmIsUserAddress
0x1408c2d53  mov     r8d, esi; Size
0x1408c2d56  mov     rdx, rbx; Src
0x1408c2d59  mov     rcx, rdi; void *
0x1408c2d5c  test    al, al
0x1408c2d5e  jnz     short loc_1408C2D6C
0x1408c2d60  test    r14b, r14b
0x1408c2d63  jnz     short loc_1408C2D7F
0x1408c2d65  call    memmove
0x1408c2d6a  jmp     short loc_1408C2D84
0x1408c2d6c  test    r14b, r14b
0x1408c2d6f  jnz     short loc_1408C2D78
0x1408c2d71  call    RtlCopyFromUser
0x1408c2d76  jmp     short loc_1408C2D84
0x1408c2d78  call    RtlCopyToUserFromUser
0x1408c2d7d  jmp     short loc_1408C2D84
0x1408c2d7f  call    RtlCopyToUser
0x1408c2d84  jmp     short loc_1408C2DAC
0x1408c2d86  mov     [rsp+98h+var_78], eax
0x1408c2d8a  lea     r9, aExceptionEncou; "Exception encountered reading SDB file "...
0x1408c2d91  mov     r8d, 372h
0x1408c2d97  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x1408c2d9e  mov     ecx, 1
0x1408c2da3  call    AslLogCallPrintf
0x1408c2da8  xor     eax, eax
0x1408c2daa  jmp     short loc_1408C2DB1
0x1408c2dac  mov     eax, 1
0x1408c2db1  add     rsp, 78h
0x1408c2db5  pop     r14
0x1408c2db7  pop     rdi
0x1408c2db8  pop     rsi
0x1408c2db9  pop     rbx
0x1408c2dba  retn
0x1408c2dbc  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x1408c2dc3  mov     r8d, 355h
0x1408c2dc9  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x1408c2dd0  mov     ecx, 1
0x1408c2dd5  call    AslLogCallPrintf
0x1408c2dda  xor     eax, eax
0x1408c2ddc  jmp     short loc_1408C2DB1
0x1408c2dde  mov     [rsp+98h+var_68], eax
0x1408c2de2  mov     [rsp+98h+var_70], esi
0x1408c2de6  mov     [rsp+98h+var_78], edx
0x1408c2dea  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x1408c2df1  mov     r8d, 35Ah
0x1408c2df7  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x1408c2dfe  mov     ecx, 1
0x1408c2e03  call    AslLogCallPrintf
0x1408c2e08  jmp     short loc_1408C2DDA
0x140b43ecb  push    rbp
0x140b43ecd  sub     rsp, 60h
0x140b43ed1  mov     rbp, rdx
0x140b43ed4  mov     [rbp+68h], rcx
0x140b43ed8  mov     rax, [rbp+68h]
0x140b43edc  mov     r10, [rax+8]
0x140b43ee0  mov     rax, [rbp+68h]
0x140b43ee4  mov     r9, [rax]
0x140b43ee7  mov     rax, [rbp+68h]
0x140b43eeb  mov     rcx, [rax]
0x140b43eee  mov     r8d, [rcx+4]
0x140b43ef2  mov     rax, [rbp+68h]
0x140b43ef6  mov     rcx, [rax+8]
0x140b43efa  mov     rdx, [rcx+0F8h]
0x140b43f01  mov     rax, [rbp+68h]
0x140b43f05  mov     rax, [rax]
0x140b43f08  mov     [rsp+68h+var_18], r10
0x140b43f0d  mov     [rsp+68h+var_20], r9
0x140b43f12  mov     [rsp+68h+var_28], r8d
0x140b43f17  mov     [rsp+68h+var_30], rdx
0x140b43f1c  mov     [rsp+68h+var_38], 0
0x140b43f24  lea     rcx, byte_14002FEAF
0x140b43f2b  mov     [rsp+68h+var_40], rcx
0x140b43f30  mov     eax, [rax]
0x140b43f32  mov     [rsp+68h+var_48], eax
0x140b43f36  lea     r9, aShimExceptionX; "Shim Exception %#x in module \"%hs\", l"...
0x140b43f3d  mov     r8d, 0F5h
0x140b43f43  lea     rdx, aShimexceptionh; "ShimExceptionHandler"
0x140b43f4a  mov     ecx, 1
0x140b43f4f  call    AslLogCallPrintf
0x140b43f54  mov     dword ptr [rbp+60h], 1
0x140b43f5b  mov     eax, [rbp+60h]
0x140b43f5e  add     rsp, 60h
0x140b43f62  pop     rbp
0x140b43f63  retn
```
