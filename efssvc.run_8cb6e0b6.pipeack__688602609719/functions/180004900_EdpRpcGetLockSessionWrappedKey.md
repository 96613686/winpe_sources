# EdpRpcGetLockSessionWrappedKey

- ea: `0x180004900`
- end: `0x180004ac7`
- name: `EdpRpcGetLockSessionWrappedKey`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180003a60`
- `0x180004900`
- `0x18000d192`
- `0x18000d1c0`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x180004a5d`
- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x180004a5d`

## pseudocode

```c
__int64 __fastcall EdpRpcGetLockSessionWrappedKey(
        void *a1,
        UCHAR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  signed int v11; // eax
  __int64 v12; // rcx
  signed int v13; // edi
  unsigned int v14; // ebx
  signed int v15; // eax
  __int64 v16; // rcx
  _OWORD *v17; // r9
  _OWORD *v18; // r8
  signed int LockSessionWrappedKey; // eax
  __int64 v20; // rcx
  _BYTE v24[112]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v25[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v26[2]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(v24, 0, sizeof(v24));
  memset(v26, 0, sizeof(v26));
  memset(v25, 0, sizeof(v25));
  if ( a2 && a3 && a4 )
  {
    if ( a5 && a6 && a7 && a8 )
    {
      v11 = EdpResolveAppHashForAppKeyCaching(a1, a2, (__int64)v26, (__int64)v25);
      v13 = v11;
      if ( v11 >= 0 )
      {
        v15 = EdpBeginLocalOnlyRpcCall((__int64)v24);
        v14 = v15;
        if ( v15 >= 0 )
        {
          v17 = v25;
          v18 = v26;
          if ( v13 )
          {
            v17 = 0;
            v18 = 0;
          }
          LockSessionWrappedKey = EdpDllGetLockSessionWrappedKey(v24, a2, v18, v17, a3, a4, a5, a6, a7, a8);
          v14 = LockSessionWrappedKey;
          if ( LockSessionWrappedKey < 0 )
            fnEfsLogTrace1(v20, (__int64)EFS_API_ERROR, LockSessionWrappedKey, 6, 44);
          EdpCleanupLocalOnlyRpcCall((__int64)v24);
        }
        else
        {
          fnEfsLogTrace1(v16, (__int64)EFS_API_ERROR, v15, 6, 27);
        }
      }
      else
      {
        v14 = 0;
        fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 21);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v14;
}

```

## disassembly

```asm
0x180004900  push    rbp
0x180004902  push    rbx
0x180004903  push    rsi
0x180004904  push    rdi
0x180004905  push    r12
0x180004907  push    r13
0x180004909  push    r14
0x18000490b  push    r15
0x18000490d  lea     rbp, [rsp-38h]
0x180004912  sub     rsp, 138h
0x180004919  mov     rax, cs:__security_cookie
0x180004920  xor     rax, rsp
0x180004923  mov     [rbp+70h+var_50], rax
0x180004927  mov     rbx, [rbp+70h+arg_38]
0x18000492e  mov     rdi, rdx
0x180004931  mov     r15, [rbp+70h+arg_20]
0x180004938  mov     rsi, r8
0x18000493b  mov     r12, [rbp+70h+arg_28]
0x180004942  mov     r14d, r9d
0x180004945  mov     r13, [rbp+70h+arg_30]
0x18000494c  mov     [rsp+170h+var_110], rdx
0x180004951  xor     edx, edx; Val
0x180004953  mov     [rsp+170h+var_120], rcx
0x180004958  lea     rcx, [rsp+170h+var_100]; void *
0x18000495d  mov     [rsp+170h+var_118], rbx
0x180004962  lea     r8d, [rdx+70h]; Size
0x180004966  call    memset_0
0x18000496b  xorps   xmm0, xmm0
0x18000496e  xorps   xmm1, xmm1
0x180004971  movups  [rbp+70h+var_70], xmm0
0x180004975  movups  [rbp+70h+var_60], xmm0
0x180004979  movups  [rbp+70h+var_90], xmm1
0x18000497d  movups  [rbp+70h+var_80], xmm1
0x180004981  test    rdi, rdi
0x180004984  jz      loc_180004A9F
0x18000498a  test    rsi, rsi
0x18000498d  jz      loc_180004A9F
0x180004993  test    r14d, r14d
0x180004996  jz      loc_180004A9F
0x18000499c  test    r15, r15
0x18000499f  jz      loc_180004A98
0x1800049a5  test    r12, r12
0x1800049a8  jz      loc_180004A98
0x1800049ae  test    r13, r13
0x1800049b1  jz      loc_180004A98
0x1800049b7  test    rbx, rbx
0x1800049ba  jz      loc_180004A98
0x1800049c0  mov     rcx, [rsp+170h+var_120]
0x1800049c5  lea     r9, [rbp+70h+var_90]
0x1800049c9  lea     r8, [rbp+70h+var_70]
0x1800049cd  mov     rdx, rdi
0x1800049d0  call    EdpResolveAppHashForAppKeyCaching
0x1800049d5  mov     edi, eax
0x1800049d7  test    eax, eax
0x1800049d9  jns     short loc_1800049FF
0x1800049db  xor     ebx, ebx
0x1800049dd  mov     dword ptr [rsp+170h+var_150], 0C15h
0x1800049e5  mov     r8d, eax
0x1800049e8  mov     r9d, 6
0x1800049ee  lea     rdx, EFS_API_ERROR
0x1800049f5  call    fnEfsLogTrace1
0x1800049fa  jmp     loc_180004AA4
0x1800049ff  lea     rcx, [rsp+170h+var_100]
0x180004a04  call    EdpBeginLocalOnlyRpcCall
0x180004a09  mov     ebx, eax
0x180004a0b  test    eax, eax
0x180004a0d  jns     short loc_180004A1C
0x180004a0f  mov     dword ptr [rsp+170h+var_150], 0C1Bh
0x180004a17  mov     r8d, eax
0x180004a1a  jmp     short loc_1800049E8
0x180004a1c  mov     rdx, [rsp+170h+var_110]
0x180004a21  lea     r9, [rbp+70h+var_90]
0x180004a25  xor     eax, eax
0x180004a27  lea     r8, [rbp+70h+var_70]
0x180004a2b  test    edi, edi
0x180004a2d  lea     rcx, [rsp+170h+var_100]
0x180004a32  cmovnz  r9, rax
0x180004a36  cmovnz  r8, rax
0x180004a3a  mov     rax, [rsp+170h+var_118]
0x180004a3f  mov     [rsp+170h+var_128], rax
0x180004a44  mov     [rsp+170h+var_130], r13
0x180004a49  mov     [rsp+170h+var_138], r12
0x180004a4e  mov     [rsp+170h+var_140], r15
0x180004a53  mov     [rsp+170h+var_148], r14d
0x180004a58  mov     [rsp+170h+var_150], rsi
0x180004a5d  call    cs:__imp_EdpDllGetLockSessionWrappedKey
0x180004a64  nop     dword ptr [rax+rax+00h]
0x180004a69  mov     ebx, eax
0x180004a6b  test    eax, eax
0x180004a6d  jns     short loc_180004A8C
0x180004a6f  mov     r9d, 6
0x180004a75  mov     dword ptr [rsp+170h+var_150], 0C2Ch
0x180004a7d  mov     r8d, eax
0x180004a80  lea     rdx, EFS_API_ERROR
0x180004a87  call    fnEfsLogTrace1
0x180004a8c  lea     rcx, [rsp+170h+var_100]
0x180004a91  call    EdpCleanupLocalOnlyRpcCall
0x180004a96  jmp     short loc_180004AA4
0x180004a98  mov     ebx, 80004003h
0x180004a9d  jmp     short loc_180004AA4
0x180004a9f  mov     ebx, 80070057h
0x180004aa4  mov     eax, ebx
0x180004aa6  mov     rcx, [rbp+70h+var_50]
0x180004aaa  xor     rcx, rsp; StackCookie
0x180004aad  call    __security_check_cookie
0x180004ab2  add     rsp, 138h
0x180004ab9  pop     r15
0x180004abb  pop     r14
0x180004abd  pop     r13
0x180004abf  pop     r12
0x180004ac1  pop     rdi
0x180004ac2  pop     rsi
0x180004ac3  pop     rbx
0x180004ac4  pop     rbp
0x180004ac5  retn
```
