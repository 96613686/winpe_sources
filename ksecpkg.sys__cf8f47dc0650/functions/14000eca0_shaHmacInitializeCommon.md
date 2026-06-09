# shaHmacInitializeCommon

- ea: `0x14000eca0`
- end: `0x14000ed5a`
- name: `shaHmacInitializeCommon`
- size: `186`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ed60`
- `0x14002e2c0`

## callees

- `0x14000eca0`
- `0x14002e260`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ecd6`
- `ntoskrnl!ExAllocatePool2` at `0x14000ecd6`
- `cng!BCryptCreateHash` at `0x14000ed2a`
- `cng!BCryptCreateHash` at `0x14000ed2a`

## pseudocode

```c
__int64 __fastcall shaHmacInitializeCommon(PUCHAR pbSecret, ULONG cbSecret, __int64 *a3)
{
  NTSTATUS Hash; // ebx
  __int64 Pool2; // rax
  __int64 v8; // rdi
  ULONG v9; // r9d
  BCRYPT_ALG_HANDLE v10; // rcx
  __int64 v12; // [rsp+88h] [rbp+20h] BYREF

  if ( cshHmacShaObjectSize < 0xFFFFFFF0 )
  {
    Pool2 = ExAllocatePool2(64, cshHmacShaObjectSize + 16, 1887007299);
    v12 = Pool2;
    v8 = Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = 0;
      v9 = cshHmacShaObjectSize;
      v10 = cshHmacShaAlgHandle;
      *(_QWORD *)(Pool2 + 8) = Pool2 + 16;
      Hash = BCryptCreateHash(v10, (BCRYPT_HASH_HANDLE *)Pool2, (PUCHAR)(Pool2 + 16), v9, pbSecret, cbSecret, 0);
      if ( Hash < 0 )
        shaHmacFinish(&v12);
      else
        *a3 = v8;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x14000eca0  push    rbx
0x14000eca2  push    rbp
0x14000eca3  push    rsi
0x14000eca4  push    rdi
0x14000eca5  sub     rsp, 48h
0x14000eca9  mov     eax, cs:cshHmacShaObjectSize
0x14000ecaf  mov     rsi, r8
0x14000ecb2  add     eax, 10h
0x14000ecb5  mov     ebx, edx
0x14000ecb7  mov     rbp, rcx
0x14000ecba  cmp     eax, 10h
0x14000ecbd  jnb     short loc_14000ECC9
0x14000ecbf  mov     ebx, 0C000000Dh
0x14000ecc4  jmp     loc_14000ED4E
0x14000ecc9  mov     edx, eax
0x14000eccb  mov     ecx, 40h ; '@'
0x14000ecd0  mov     r8d, 70797243h
0x14000ecd6  call    cs:__imp_ExAllocatePool2
0x14000ecdd  nop     dword ptr [rax+rax+00h]
0x14000ece2  mov     [rsp+68h+arg_18], rax
0x14000ecea  mov     rdi, rax
0x14000eced  test    rax, rax
0x14000ecf0  jnz     short loc_14000ECF9
0x14000ecf2  mov     ebx, 0C000009Ah
0x14000ecf7  jmp     short loc_14000ED4E
0x14000ecf9  mov     qword ptr [rax], 0
0x14000ed00  lea     r8, [rax+10h]; pbHashObject
0x14000ed04  mov     r9d, cs:cshHmacShaObjectSize; cbHashObject
0x14000ed0b  mov     rdx, rdi; phHash
0x14000ed0e  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x14000ed15  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14000ed1d  mov     [rsp+68h+cbSecret], ebx; cbSecret
0x14000ed21  mov     [rax+8], r8
0x14000ed25  mov     [rsp+68h+pbSecret], rbp; pbSecret
0x14000ed2a  call    cs:__imp_BCryptCreateHash
0x14000ed31  nop     dword ptr [rax+rax+00h]
0x14000ed36  mov     ebx, eax
0x14000ed38  test    eax, eax
0x14000ed3a  js      short loc_14000ED41
0x14000ed3c  mov     [rsi], rdi
0x14000ed3f  jmp     short loc_14000ED4E
0x14000ed41  lea     rcx, [rsp+68h+arg_18]
0x14000ed49  call    shaHmacFinish
0x14000ed4e  mov     eax, ebx
0x14000ed50  add     rsp, 48h
0x14000ed54  pop     rdi
0x14000ed55  pop     rsi
0x14000ed56  pop     rbp
0x14000ed57  pop     rbx
0x14000ed58  retn
```
