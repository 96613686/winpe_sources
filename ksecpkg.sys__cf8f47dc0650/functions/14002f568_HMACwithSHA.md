# HMACwithSHA

- ea: `0x14002f568`
- end: `0x14002f6a7`
- name: `HMACwithSHA`
- size: `319`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002eef0`

## callees

- `0x140010160`
- `0x14002f568`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f67e`
- `ntoskrnl!ExAllocatePool2` at `0x14002f5b2`
- `ntoskrnl!ExAllocatePool2` at `0x14002f5b2`
- `cng!BCryptCreateHash` at `0x14002f5f8`
- `cng!BCryptCreateHash` at `0x14002f5f8`
- `cng!BCryptHashData` at `0x14002f618`
- `cng!BCryptHashData` at `0x14002f618`
- `cng!BCryptDestroyHash` at `0x14002f668`
- `cng!BCryptDestroyHash` at `0x14002f668`
- `cng!BCryptFinishHash` at `0x14002f63b`
- `cng!BCryptFinishHash` at `0x14002f63b`

## pseudocode

```c
__int64 __fastcall HMACwithSHA(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, __int64 a5)
{
  UCHAR *Pool2; // rax
  UCHAR *v10; // rdi
  NTSTATUS v11; // ebx
  int v12; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-68h] BYREF
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-60h] BYREF
  int v16; // [rsp+58h] [rbp-50h]

  phHash = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(64, cshHmacShaObjectSize, 1887007299);
  v10 = Pool2;
  if ( Pool2 )
  {
    v11 = BCryptCreateHash(cshHmacShaAlgHandle, &phHash, Pool2, cshHmacShaObjectSize, pbSecret, cbSecret, 0);
    if ( v11 >= 0 )
    {
      v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( v11 >= 0 )
      {
        v11 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
        if ( v11 >= 0 )
        {
          v12 = v16;
          v11 = 0;
          *(_OWORD *)a5 = *(_OWORD *)pbOutput;
          *(_DWORD *)(a5 + 16) = v12;
        }
      }
    }
  }
  else
  {
    v11 = -1073741801;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002f568  push    rbx
0x14002f56a  push    rbp
0x14002f56b  push    rsi
0x14002f56c  push    rdi
0x14002f56d  push    r14
0x14002f56f  push    r15
0x14002f571  sub     rsp, 78h
0x14002f575  mov     rax, cs:__security_cookie
0x14002f57c  xor     rax, rsp
0x14002f57f  mov     [rsp+0A8h+var_48], rax
0x14002f584  mov     rsi, [rsp+0A8h+arg_20]
0x14002f58c  mov     rbp, r8
0x14002f58f  mov     r15d, edx
0x14002f592  mov     [rsp+0A8h+phHash], 0
0x14002f59b  mov     edx, cs:cshHmacShaObjectSize
0x14002f5a1  mov     rbx, rcx
0x14002f5a4  mov     ecx, 40h ; '@'
0x14002f5a9  mov     r8d, 70797243h
0x14002f5af  mov     r14d, r9d
0x14002f5b2  call    cs:__imp_ExAllocatePool2
0x14002f5b9  nop     dword ptr [rax+rax+00h]
0x14002f5be  mov     rdi, rax
0x14002f5c1  test    rax, rax
0x14002f5c4  jnz     short loc_14002F5D0
0x14002f5c6  mov     ebx, 0C0000017h
0x14002f5cb  jmp     loc_14002F65E
0x14002f5d0  mov     r9d, cs:cshHmacShaObjectSize; cbHashObject
0x14002f5d7  lea     rdx, [rsp+0A8h+phHash]; phHash
0x14002f5dc  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x14002f5e3  mov     r8, rdi; pbHashObject
0x14002f5e6  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x14002f5ee  mov     [rsp+0A8h+cbSecret], r15d; cbSecret
0x14002f5f3  mov     [rsp+0A8h+pbSecret], rbx; pbSecret
0x14002f5f8  call    cs:__imp_BCryptCreateHash
0x14002f5ff  nop     dword ptr [rax+rax+00h]
0x14002f604  mov     ebx, eax
0x14002f606  test    eax, eax
0x14002f608  js      short loc_14002F65E
0x14002f60a  mov     rcx, [rsp+0A8h+phHash]; hHash
0x14002f60f  xor     r9d, r9d; dwFlags
0x14002f612  mov     r8d, r14d; cbInput
0x14002f615  mov     rdx, rbp; pbInput
0x14002f618  call    cs:__imp_BCryptHashData
0x14002f61f  nop     dword ptr [rax+rax+00h]
0x14002f624  mov     ebx, eax
0x14002f626  test    eax, eax
0x14002f628  js      short loc_14002F65E
0x14002f62a  mov     rcx, [rsp+0A8h+phHash]; hHash
0x14002f62f  lea     rdx, [rsp+0A8h+pbOutput]; pbOutput
0x14002f634  xor     r9d, r9d; dwFlags
0x14002f637  lea     r8d, [r9+14h]; cbOutput
0x14002f63b  call    cs:__imp_BCryptFinishHash
0x14002f642  nop     dword ptr [rax+rax+00h]
0x14002f647  mov     ebx, eax
0x14002f649  test    eax, eax
0x14002f64b  js      short loc_14002F65E
0x14002f64d  movups  xmm0, xmmword ptr [rsp+0A8h+pbOutput]
0x14002f652  mov     eax, [rsp+0A8h+var_50]
0x14002f656  xor     ebx, ebx
0x14002f658  movups  xmmword ptr [rsi], xmm0
0x14002f65b  mov     [rsi+10h], eax
0x14002f65e  mov     rcx, [rsp+0A8h+phHash]; hHash
0x14002f663  test    rcx, rcx
0x14002f666  jz      short loc_14002F674
0x14002f668  call    cs:__imp_BCryptDestroyHash
0x14002f66f  nop     dword ptr [rax+rax+00h]
0x14002f674  test    rdi, rdi
0x14002f677  jz      short loc_14002F68A
0x14002f679  xor     edx, edx; Tag
0x14002f67b  mov     rcx, rdi; P
0x14002f67e  call    cs:__imp_ExFreePoolWithTag
0x14002f685  nop     dword ptr [rax+rax+00h]
0x14002f68a  mov     eax, ebx
0x14002f68c  mov     rcx, [rsp+0A8h+var_48]
0x14002f691  xor     rcx, rsp; StackCookie
0x14002f694  call    __security_check_cookie
0x14002f699  add     rsp, 78h
0x14002f69d  pop     r15
0x14002f69f  pop     r14
0x14002f6a1  pop     rdi
0x14002f6a2  pop     rsi
0x14002f6a3  pop     rbp
0x14002f6a4  pop     rbx
0x14002f6a5  retn
```
