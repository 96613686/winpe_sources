# HMACwithSHA

- ea: `0x180001520`
- end: `0x18000165a`
- name: `HMACwithSHA`
- size: `314`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, void *, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007d40`

## callees

- `0x180001520`
- `0x180002240`
- `0x180004c40`
- `0x180008415`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001636`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001574`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001574`
- `bcrypt!BCryptFinishHash` at `0x1800015ed`
- `bcrypt!BCryptFinishHash` at `0x1800015ed`
- `bcrypt!BCryptDestroyHash` at `0x180001628`
- `bcrypt!BCryptDestroyHash` at `0x180001628`
- `bcrypt!BCryptHashData` at `0x1800015ce`
- `bcrypt!BCryptHashData` at `0x1800015ce`
- `bcrypt!BCryptCreateHash` at `0x1800015b4`
- `bcrypt!BCryptCreateHash` at `0x1800015b4`

## pseudocode

```c
__int64 __fastcall HMACwithSHA(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, void *a5, size_t Size)
{
  UCHAR *v10; // rbx
  NTSTATUS v11; // edi
  UCHAR *v12; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-68h] BYREF
  UCHAR pbOutput[24]; // [rsp+48h] [rbp-60h] BYREF

  phHash = 0;
  v10 = 0;
  v11 = CheckCNG();
  if ( v11 >= 0 )
  {
    v12 = (UCHAR *)LocalAlloc(0, (unsigned int)cshHmacShaObjectSize);
    v10 = v12;
    if ( v12 )
    {
      v11 = BCryptCreateHash(cshHmacShaAlgHandle, &phHash, v12, cshHmacShaObjectSize, pbSecret, cbSecret, 0);
      if ( v11 >= 0 )
      {
        v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v11 >= 0 )
        {
          v11 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
          if ( v11 >= 0 )
          {
            if ( (unsigned int)Size <= 0x14 )
            {
              memcpy_0(a5, pbOutput, (unsigned int)Size);
              v11 = 0;
            }
            else
            {
              v11 = -1073741811;
            }
          }
        }
      }
    }
    else
    {
      v11 = -1073741801;
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v10 )
    LocalFree(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180001520  push    rbx
0x180001522  push    rbp
0x180001523  push    rsi
0x180001524  push    rdi
0x180001525  push    r12
0x180001527  push    r14
0x180001529  push    r15
0x18000152b  sub     rsp, 70h
0x18000152f  mov     rax, cs:__security_cookie
0x180001536  xor     rax, rsp
0x180001539  mov     [rsp+0A8h+var_48], rax
0x18000153e  mov     r14, [rsp+0A8h+arg_20]
0x180001546  mov     ebp, r9d
0x180001549  mov     rsi, r8
0x18000154c  mov     [rsp+0A8h+phHash], 0
0x180001555  mov     r12d, edx
0x180001558  mov     r15, rcx
0x18000155b  xor     ebx, ebx
0x18000155d  call    CheckCNG
0x180001562  mov     edi, eax
0x180001564  test    eax, eax
0x180001566  js      loc_18000161E
0x18000156c  mov     edx, cs:cshHmacShaObjectSize; uBytes
0x180001572  xor     ecx, ecx; uFlags
0x180001574  call    cs:__imp_LocalAlloc
0x18000157a  mov     rbx, rax
0x18000157d  test    rax, rax
0x180001580  jnz     short loc_18000158C
0x180001582  mov     edi, 0C0000017h
0x180001587  jmp     loc_18000161E
0x18000158c  mov     r9d, cs:cshHmacShaObjectSize; cbHashObject
0x180001593  lea     rdx, [rsp+0A8h+phHash]; phHash
0x180001598  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x18000159f  mov     r8, rax; pbHashObject
0x1800015a2  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x1800015aa  mov     [rsp+0A8h+cbSecret], r12d; cbSecret
0x1800015af  mov     [rsp+0A8h+pbSecret], r15; pbSecret
0x1800015b4  call    cs:__imp_BCryptCreateHash
0x1800015ba  mov     edi, eax
0x1800015bc  test    eax, eax
0x1800015be  js      short loc_18000161E
0x1800015c0  mov     rcx, [rsp+0A8h+phHash]; hHash
0x1800015c5  xor     r9d, r9d; dwFlags
0x1800015c8  mov     r8d, ebp; cbInput
0x1800015cb  mov     rdx, rsi; pbInput
0x1800015ce  call    cs:__imp_BCryptHashData
0x1800015d4  mov     edi, eax
0x1800015d6  test    eax, eax
0x1800015d8  js      short loc_18000161E
0x1800015da  mov     rcx, [rsp+0A8h+phHash]; hHash
0x1800015df  lea     rdx, [rsp+0A8h+pbOutput]; pbOutput
0x1800015e4  xor     r9d, r9d; dwFlags
0x1800015e7  mov     r8d, 14h; cbOutput
0x1800015ed  call    cs:__imp_BCryptFinishHash
0x1800015f3  mov     edi, eax
0x1800015f5  test    eax, eax
0x1800015f7  js      short loc_18000161E
0x1800015f9  mov     eax, dword ptr [rsp+0A8h+Size]
0x180001600  cmp     eax, 14h
0x180001603  jbe     short loc_18000160C
0x180001605  mov     edi, 0C000000Dh
0x18000160a  jmp     short loc_18000161E
0x18000160c  mov     r8, rax; Size
0x18000160f  lea     rdx, [rsp+0A8h+pbOutput]; Src
0x180001614  mov     rcx, r14; void *
0x180001617  call    memcpy_0
0x18000161c  xor     edi, edi
0x18000161e  mov     rcx, [rsp+0A8h+phHash]; hHash
0x180001623  test    rcx, rcx
0x180001626  jz      short loc_18000162E
0x180001628  call    cs:__imp_BCryptDestroyHash
0x18000162e  test    rbx, rbx
0x180001631  jz      short loc_18000163C
0x180001633  mov     rcx, rbx; hMem
0x180001636  call    cs:__imp_LocalFree
0x18000163c  mov     eax, edi
0x18000163e  mov     rcx, [rsp+0A8h+var_48]
0x180001643  xor     rcx, rsp; StackCookie
0x180001646  call    __security_check_cookie
0x18000164b  add     rsp, 70h
0x18000164f  pop     r15
0x180001651  pop     r14
0x180001653  pop     r12
0x180001655  pop     rdi
0x180001656  pop     rsi
0x180001657  pop     rbp
0x180001658  pop     rbx
0x180001659  retn
```
