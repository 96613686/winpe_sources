# shaHmacInitializeEx

- ea: `0x180001660`
- end: `0x1800017b7`
- name: `shaHmacInitializeEx`
- size: `343`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001660`
- `0x180002240`
- `0x1800022c0`
- `0x180002750`
- `0x1800027a0`
- `0x180004c40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800016bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800016bd`
- `bcrypt!BCryptCreateHash` at `0x1800016ff`
- `bcrypt!BCryptCreateHash` at `0x1800016ff`

## pseudocode

```c
__int64 __fastcall shaHmacInitializeEx(PUCHAR pbSecret, ULONG cbSecret, int a3, _QWORD *a4)
{
  NTSTATUS Hash; // ebx
  _QWORD *v8; // rdi
  __int64 result; // rax
  _QWORD *v10; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v11[16]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-50h] BYREF

  if ( a3 )
  {
    BYTE3(v10) = a3;
    LOBYTE(v10) = HIBYTE(a3);
    BYTE4(v10) = -103;
    BYTE1(v10) = BYTE2(a3);
    BYTE2(v10) = BYTE1(a3);
    fold_40_to_128(&v10, v11);
    result = aesDR(v11, pbSecret, cbSecret, v12);
    if ( (int)result < 0 )
      return result;
    pbSecret = v12;
  }
  Hash = CheckCNG();
  if ( Hash >= 0 )
  {
    if ( (unsigned int)cshHmacShaObjectSize >= 0xFFFFFFF0 )
    {
      return (unsigned int)-1073741811;
    }
    else
    {
      v10 = LocalAlloc(0, (unsigned int)(cshHmacShaObjectSize + 16));
      v8 = v10;
      if ( v10 )
      {
        *v10 = 0;
        v8[1] = v8 + 2;
        Hash = BCryptCreateHash(
                 cshHmacShaAlgHandle,
                 (BCRYPT_HASH_HANDLE *)v8,
                 (PUCHAR)v8 + 16,
                 cshHmacShaObjectSize,
                 pbSecret,
                 cbSecret,
                 0);
        if ( Hash < 0 )
          shaHmacFinish(&v10);
        else
          *a4 = v8;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x180001660  push    rbp
0x180001662  push    rsi
0x180001663  push    r14
0x180001665  sub     rsp, 90h
0x18000166c  mov     rax, cs:__security_cookie
0x180001673  xor     rax, rsp
0x180001676  mov     [rsp+0A8h+var_30], rax
0x18000167b  mov     r14, r9
0x18000167e  mov     ebp, edx
0x180001680  mov     rsi, rcx
0x180001683  test    r8d, r8d
0x180001686  jnz     loc_180001744
0x18000168c  mov     [rsp+0A8h+var_20], rbx
0x180001694  call    CheckCNG
0x180001699  mov     ebx, eax
0x18000169b  test    eax, eax
0x18000169d  js      short loc_18000171A
0x18000169f  mov     eax, cs:cshHmacShaObjectSize
0x1800016a5  add     eax, 10h
0x1800016a8  cmp     eax, 10h
0x1800016ab  jb      loc_18000173D
0x1800016b1  mov     edx, eax; uBytes
0x1800016b3  xor     ecx, ecx; uFlags
0x1800016b5  mov     [rsp+0A8h+var_28], rdi
0x1800016bd  call    cs:__imp_LocalAlloc
0x1800016c3  mov     [rsp+0A8h+var_68], rax
0x1800016c8  mov     rdi, rax
0x1800016cb  test    rax, rax
0x1800016ce  jz      loc_1800017AD
0x1800016d4  xor     eax, eax
0x1800016d6  lea     r8, [rdi+10h]; pbHashObject
0x1800016da  mov     [rdi], rax
0x1800016dd  mov     rdx, rdi; phHash
0x1800016e0  mov     [rdi+8], r8
0x1800016e4  mov     r9d, cs:cshHmacShaObjectSize; cbHashObject
0x1800016eb  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x1800016f2  mov     [rsp+0A8h+dwFlags], eax; dwFlags
0x1800016f6  mov     [rsp+0A8h+cbSecret], ebp; cbSecret
0x1800016fa  mov     [rsp+0A8h+pbSecret], rsi; pbSecret
0x1800016ff  call    cs:__imp_BCryptCreateHash
0x180001705  mov     ebx, eax
0x180001707  test    eax, eax
0x180001709  js      loc_18000179E
0x18000170f  mov     [r14], rdi
0x180001712  mov     rdi, [rsp+0A8h+var_28]
0x18000171a  mov     eax, ebx
0x18000171c  mov     rbx, [rsp+0A8h+var_20]
0x180001724  mov     rcx, [rsp+0A8h+var_30]
0x180001729  xor     rcx, rsp; StackCookie
0x18000172c  call    __security_check_cookie
0x180001731  add     rsp, 90h
0x180001738  pop     r14
0x18000173a  pop     rsi
0x18000173b  pop     rbp
0x18000173c  retn
0x18000173d  mov     ebx, 0C000000Dh
0x180001742  jmp     short loc_18000171A
0x180001744  mov     eax, r8d
0x180001747  mov     byte ptr [rsp+0A8h+var_68+3], r8b
0x18000174c  shr     eax, 18h
0x18000174f  lea     rdx, [rsp+0A8h+var_60]
0x180001754  mov     byte ptr [rsp+0A8h+var_68], al
0x180001758  lea     rcx, [rsp+0A8h+var_68]
0x18000175d  mov     eax, r8d
0x180001760  mov     byte ptr [rsp+0A8h+var_68+4], 99h
0x180001765  shr     eax, 10h
0x180001768  mov     byte ptr [rsp+0A8h+var_68+1], al
0x18000176c  mov     eax, r8d
0x18000176f  shr     eax, 8
0x180001772  mov     byte ptr [rsp+0A8h+var_68+2], al
0x180001776  call    fold_40_to_128
0x18000177b  lea     r9, [rsp+0A8h+var_50]
0x180001780  mov     r8d, ebp
0x180001783  mov     rdx, rsi
0x180001786  lea     rcx, [rsp+0A8h+var_60]
0x18000178b  call    aesDR
0x180001790  test    eax, eax
0x180001792  js      short loc_180001724
0x180001794  lea     rsi, [rsp+0A8h+var_50]
0x180001799  jmp     loc_18000168C
0x18000179e  lea     rcx, [rsp+0A8h+var_68]
0x1800017a3  call    shaHmacFinish
0x1800017a8  jmp     loc_180001712
0x1800017ad  mov     ebx, 0C000009Ah
0x1800017b2  jmp     loc_180001712
```
