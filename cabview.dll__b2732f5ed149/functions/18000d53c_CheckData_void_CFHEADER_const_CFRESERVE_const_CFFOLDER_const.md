# CheckData(void *,CFHEADER const &,CFRESERVE const &,CFFOLDER const *)

- ea: `0x18000d53c`
- end: `0x18000d66f`
- name: `?CheckData@@YAHPEAXAEBUCFHEADER@@AEBUCFRESERVE@@PEBUCFFOLDER@@@Z`
- size: `307`
- prototype: `_BOOL8 __fastcall(void *, const struct CFHEADER *, const struct CFRESERVE *, const struct CFFOLDER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f5cc`

## callees

- `0x180002620`
- `0x18000d53c`
- `0x18000e61c`
- `0x18000f4b4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d5e3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d5e3`

## pseudocode

```c
_BOOL8 __fastcall CheckData(void *a1, const struct CFHEADER *a2, const struct CFRESERVE *a3, const struct CFFOLDER *a4)
{
  unsigned __int64 i; // rbx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rdi
  unsigned int v14; // [rsp+30h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  for ( i = 0; ; ++i )
  {
    v9 = *((unsigned __int16 *)a2 + 13);
    v14 = 0;
    if ( i >= v9 )
      break;
    v10 = (unsigned int)GetFilePointer(a1, &v14) && v14 == *((_DWORD *)a4 + 2 * i);
    v11 = *((unsigned int *)a4 + 2 * i);
    v12 = 0;
    if ( v10 )
    {
      while ( v12 < *((unsigned __int16 *)a4 + 4 * i + 2) )
      {
        if ( !ReadFile(a1, &Buffer, 8u, &NumberOfBytesRead, 0) )
          return 0;
        if ( NumberOfBytesRead != 8 )
          return 0;
        v11 += WORD2(Buffer) + (unsigned int)*((unsigned __int8 *)a3 + 3);
        if ( v11 >= *((int *)a2 + 2)
          || !(unsigned int)SetFilePointerRelative(a1, WORD2(Buffer) + (unsigned int)*((unsigned __int8 *)a3 + 3)) )
        {
          return 0;
        }
        v10 = 1;
        ++v12;
      }
    }
    if ( !v10 )
      return v10;
  }
  return (unsigned int)GetFilePointer(a1, &v14) && v14 == *((_DWORD *)a2 + 2);
}

```

## disassembly

```asm
0x18000d53c  mov     [rsp-38h+arg_8], rbx
0x18000d541  push    rbp
0x18000d542  push    rsi
0x18000d543  push    rdi
0x18000d544  push    r12
0x18000d546  push    r13
0x18000d548  push    r14
0x18000d54a  push    r15
0x18000d54c  mov     rbp, rsp
0x18000d54f  sub     rsp, 50h
0x18000d553  mov     rax, cs:__security_cookie
0x18000d55a  xor     rax, rsp
0x18000d55d  mov     [rbp+var_10], rax
0x18000d561  mov     r15, r9
0x18000d564  mov     [rbp+NumberOfBytesRead], 0
0x18000d56b  mov     r13, r8
0x18000d56e  mov     [rbp+Buffer], 0
0x18000d576  mov     rsi, rdx
0x18000d579  mov     r14, rcx
0x18000d57c  xor     ebx, ebx
0x18000d57e  movzx   eax, word ptr [rsi+1Ah]
0x18000d582  lea     rdx, [rbp+var_20]; unsigned int *
0x18000d586  mov     [rbp+var_20], 0
0x18000d58d  mov     rcx, r14; void *
0x18000d590  cmp     rbx, rax
0x18000d593  jnb     loc_18000D62F
0x18000d599  call    ?GetFilePointer@@YAHPEAXPEAK@Z; GetFilePointer(void *,ulong *)
0x18000d59e  test    eax, eax
0x18000d5a0  jz      short loc_18000D5B2
0x18000d5a2  mov     eax, [r15+rbx*8]
0x18000d5a6  cmp     [rbp+var_20], eax
0x18000d5a9  jnz     short loc_18000D5B2
0x18000d5ab  mov     ecx, 1
0x18000d5b0  jmp     short loc_18000D5B4
0x18000d5b2  xor     ecx, ecx
0x18000d5b4  mov     r12d, [r15+rbx*8]
0x18000d5b8  xor     edi, edi
0x18000d5ba  test    ecx, ecx
0x18000d5bc  jz      short loc_18000D622
0x18000d5be  movzx   eax, word ptr [r15+rbx*8+4]
0x18000d5c4  cmp     rdi, rax
0x18000d5c7  jnb     short loc_18000D622
0x18000d5c9  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d5cd  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18000d5d6  mov     r8d, 8; nNumberOfBytesToRead
0x18000d5dc  lea     rdx, [rbp+Buffer]; lpBuffer
0x18000d5e0  mov     rcx, r14; hFile
0x18000d5e3  call    cs:__imp_ReadFile
0x18000d5e9  test    eax, eax
0x18000d5eb  jz      short loc_18000D647
0x18000d5ed  cmp     [rbp+NumberOfBytesRead], 8
0x18000d5f1  jnz     short loc_18000D647
0x18000d5f3  movzx   eax, word ptr [rbp+Buffer+4]
0x18000d5f7  movzx   edx, byte ptr [r13+3]
0x18000d5fc  add     edx, eax; int
0x18000d5fe  mov     eax, edx
0x18000d600  add     r12, rax
0x18000d603  movsxd  rax, dword ptr [rsi+8]
0x18000d607  cmp     r12, rax
0x18000d60a  jnb     short loc_18000D647
0x18000d60c  mov     rcx, r14; void *
0x18000d60f  call    ?SetFilePointerRelative@@YAHPEAXJ@Z; SetFilePointerRelative(void *,long)
0x18000d614  test    eax, eax
0x18000d616  jz      short loc_18000D647
0x18000d618  mov     ecx, 1
0x18000d61d  inc     rdi
0x18000d620  jmp     short loc_18000D5BE
0x18000d622  inc     rbx
0x18000d625  test    ecx, ecx
0x18000d627  jnz     loc_18000D57E
0x18000d62d  jmp     short loc_18000D649
0x18000d62f  call    ?GetFilePointer@@YAHPEAXPEAK@Z; GetFilePointer(void *,ulong *)
0x18000d634  test    eax, eax
0x18000d636  jz      short loc_18000D647
0x18000d638  mov     eax, [rsi+8]
0x18000d63b  cmp     [rbp+var_20], eax
0x18000d63e  jnz     short loc_18000D647
0x18000d640  mov     ecx, 1
0x18000d645  jmp     short loc_18000D649
0x18000d647  xor     ecx, ecx
0x18000d649  mov     eax, ecx
0x18000d64b  mov     rcx, [rbp+var_10]
0x18000d64f  xor     rcx, rsp; StackCookie
0x18000d652  call    __security_check_cookie
0x18000d657  mov     rbx, [rsp+50h+arg_8]
0x18000d65f  add     rsp, 50h
0x18000d663  pop     r15
0x18000d665  pop     r14
0x18000d667  pop     r13
0x18000d669  pop     r12
0x18000d66b  pop     rdi
0x18000d66c  pop     rsi
0x18000d66d  pop     rbp
0x18000d66e  retn
```
