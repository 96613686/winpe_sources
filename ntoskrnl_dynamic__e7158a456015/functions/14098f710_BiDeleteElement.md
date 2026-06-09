# BiDeleteElement

- ea: `0x14098f710`
- end: `0x14098f8f5`
- name: `BiDeleteElement`
- size: `485`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1407a00dc`
- `0x1407a3e94`
- `0x1407cb4e4`
- `0x140832824`
- `0x14098f690`
- `0x140990054`
- `0x1409923b4`

## callees

- `0x140549550`
- `0x1406dc8c0`
- `0x14098f710`
- `0x1409913a0`
- `0x140992e34`
- `0x140993038`
- `0x1409934f0`
- `0x140993780`
- `0x1409937e0`
- `0x140994f7c`
- `0x140995510`

## string_xrefs

- `0x14098f7f2`: `Failed to open element %ws key for delete. Status: %x`
- `0x14098f858`: `Failed to open element %ws key for delete. Status: %x`
- `0x14098f892`: `Failed to open key for all object's elements. Status: %x`
- `0x14098f879`: `BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteElement(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r15d
  __int64 v5; // rcx
  int v6; // eax
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  HANDLE v11; // rdi
  int v12; // eax
  unsigned int v14; // r8d
  HANDLE v15; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+30h] [rbp-40h] BYREF
  wchar_t DstBuf[24]; // [rsp+38h] [rbp-38h] BYREF

  v16 = a2;
  v2 = 2;
  BiLogMessage(2, L"Deleting element %08x", a2);
  LOBYTE(v5) = a1 & 1;
  v6 = BiAcquireBcdSyncMutant(v5);
  if ( v6 < 0 )
  {
    BiLogMessage(4, L"BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v6);
    return v14;
  }
  else
  {
    v15 = 0;
    Handle = 0;
    v7 = BiOpenKey(a1, L"Elements", 131097, &v15);
    v8 = v7;
    if ( v7 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for all object's elements. Status: %x", (unsigned int)v7);
    }
    else if ( ultow_s(a2, DstBuf, 0x16u, 16) )
    {
      v8 = -1073741823;
    }
    else
    {
      v10 = BiOpenKey(v15, DstBuf, 0x10000, &Handle);
      if ( v10 < 0 )
      {
        if ( v10 != -1073741772 )
          v2 = 4;
        BiLogMessage(v2, L"Failed to open element %ws key for delete. Status: %x", DstBuf, (unsigned int)v10);
        v11 = Handle;
        v8 = -1073741275;
      }
      else
      {
        v11 = Handle;
        v12 = BiDeleteKey(Handle);
        v8 = v12;
        if ( v12 >= 0 )
          v11 = 0;
        else
          BiLogMessage(4, L"Failed to open element %ws key for delete. Status: %x", DstBuf, (unsigned int)v12);
      }
      if ( v11 )
        BiCloseKey(v11);
    }
    if ( v15 )
      BiCloseKey(v15);
    if ( v8 >= 0 )
    {
      if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v16) )
        BiSetFirmwareModifiedFromObject(a1);
    }
    LOBYTE(v9) = a1 & 1;
    BiReleaseBcdSyncMutant(v9);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x14098f710  mov     [rsp-28h+arg_10], rbx
0x14098f715  push    rbp
0x14098f716  push    rdi
0x14098f717  push    r12
0x14098f719  push    r14
0x14098f71b  push    r15
0x14098f71d  mov     rbp, rsp
0x14098f720  sub     rsp, 70h
0x14098f724  mov     rax, cs:__security_cookie
0x14098f72b  xor     rax, rsp
0x14098f72e  mov     [rbp+var_8], rax
0x14098f732  mov     r8d, edx
0x14098f735  mov     [rbp+var_48], edx
0x14098f738  mov     r15d, 2
0x14098f73e  mov     edi, edx
0x14098f740  mov     r14, rcx
0x14098f743  lea     rdx, aDeletingElemen; "Deleting element %08x"
0x14098f74a  mov     ecx, r15d
0x14098f74d  call    BiLogMessage
0x14098f752  mov     r12b, r14b
0x14098f755  and     r12b, 1
0x14098f759  mov     cl, r12b
0x14098f75c  call    BiAcquireBcdSyncMutant
0x14098f761  mov     r8d, eax
0x14098f764  test    eax, eax
0x14098f766  js      loc_14098F879
0x14098f76c  lea     r9, [rbp+var_50]
0x14098f770  mov     [rbp+var_50], 0
0x14098f778  mov     r8d, 20019h
0x14098f77e  mov     [rbp+Handle], 0
0x14098f786  lea     rdx, aElements; "Elements"
0x14098f78d  mov     rcx, r14
0x14098f790  call    BiOpenKey
0x14098f795  mov     ebx, eax
0x14098f797  test    eax, eax
0x14098f799  js      loc_14098F88F
0x14098f79f  lea     r9d, [r15+0Eh]; Radix
0x14098f7a3  mov     ecx, edi; Val
0x14098f7a5  lea     r8d, [r15+14h]; SizeInWords
0x14098f7a9  lea     rdx, [rbp+DstBuf]; DstBuf
0x14098f7ad  call    _ultow_s
0x14098f7b2  test    eax, eax
0x14098f7b4  jnz     loc_14098F8A8
0x14098f7ba  mov     rcx, [rbp+var_50]
0x14098f7be  lea     r9, [rbp+Handle]
0x14098f7c2  mov     r8d, 10000h
0x14098f7c8  lea     rdx, [rbp+DstBuf]
0x14098f7cc  call    BiOpenKey
0x14098f7d1  test    eax, eax
0x14098f7d3  js      short loc_14098F84A
0x14098f7d5  mov     rdi, [rbp+Handle]
0x14098f7d9  mov     rcx, rdi
0x14098f7dc  call    BiDeleteKey
0x14098f7e1  mov     ebx, eax
0x14098f7e3  test    eax, eax
0x14098f7e5  jns     loc_14098F8B2
0x14098f7eb  mov     r9d, eax
0x14098f7ee  lea     r8, [rbp+DstBuf]
0x14098f7f2  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x14098f7f9  lea     ecx, [r15+2]
0x14098f7fd  call    BiLogMessage
0x14098f802  test    rdi, rdi
0x14098f805  jnz     loc_14098F8B9
0x14098f80b  cmp     [rbp+var_50], 0
0x14098f810  jnz     loc_14098F8C6
0x14098f816  test    ebx, ebx
0x14098f818  jns     loc_14098F8D4
0x14098f81e  mov     cl, r12b
0x14098f821  call    BiReleaseBcdSyncMutant
0x14098f826  mov     eax, ebx
0x14098f828  mov     rcx, [rbp+var_8]
0x14098f82c  xor     rcx, rsp; StackCookie
0x14098f82f  call    __security_check_cookie
0x14098f834  mov     rbx, [rsp+70h+arg_10]
0x14098f83c  add     rsp, 70h
0x14098f840  pop     r15
0x14098f842  pop     r14
0x14098f844  pop     r12
0x14098f846  pop     rdi
0x14098f847  pop     rbp
0x14098f848  retn
0x14098f84a  cmp     eax, 0C0000034h
0x14098f84f  lea     r8, [rbp+DstBuf]
0x14098f853  mov     ecx, 4
0x14098f858  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x14098f85f  cmovnz  r15d, ecx
0x14098f863  mov     r9d, eax
0x14098f866  mov     ecx, r15d
0x14098f869  call    BiLogMessage
0x14098f86e  mov     rdi, [rbp+Handle]
0x14098f872  mov     ebx, 0C0000225h
0x14098f877  jmp     short loc_14098F802
0x14098f879  lea     rdx, aBideleteelemen; "BiDeleteElement: Failed to acquire BCD "...
0x14098f880  mov     ecx, 4
0x14098f885  call    BiLogMessage
0x14098f88a  mov     eax, r8d
0x14098f88d  jmp     short loc_14098F828
0x14098f88f  mov     r8d, eax
0x14098f892  lea     rdx, aFailedToOpenKe_0; "Failed to open key for all object's ele"...
0x14098f899  mov     ecx, 4
0x14098f89e  call    BiLogMessage
0x14098f8a3  jmp     loc_14098F80B
0x14098f8a8  mov     ebx, 0C0000001h
0x14098f8ad  jmp     loc_14098F80B
0x14098f8b2  xor     edi, edi
0x14098f8b4  jmp     loc_14098F802
0x14098f8b9  mov     rcx, rdi; Handle
0x14098f8bc  call    BiCloseKey
0x14098f8c1  jmp     loc_14098F80B
0x14098f8c6  mov     rcx, [rbp+var_50]; Handle
0x14098f8ca  call    BiCloseKey
0x14098f8cf  jmp     loc_14098F816
0x14098f8d4  lea     rdx, [rbp+var_48]
0x14098f8d8  mov     rcx, r14
0x14098f8db  call    BiIsLinkedToFirmwareVariable
0x14098f8e0  test    al, al
0x14098f8e2  jz      loc_14098F81E
0x14098f8e8  mov     rcx, r14
0x14098f8eb  call    BiSetFirmwareModifiedFromObject
0x14098f8f0  jmp     loc_14098F81E
```
