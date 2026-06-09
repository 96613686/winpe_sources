# ClusterGlobalData::ComputeSQMHash(void)

- ea: `0x1800331f0`
- end: `0x1800332b1`
- name: `?ComputeSQMHash@ClusterGlobalData@@AEAAKXZ`
- size: `193`
- prototype: `unsigned int __fastcall(ClusterGlobalData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003be68`
- `0x18007ab58`

## callees

- `0x180002f50`
- `0x1800331f0`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18003328f`
- `bcrypt!BCryptDestroyHash` at `0x18003328f`
- `bcrypt!BCryptHashData` at `0x18003325b`
- `bcrypt!BCryptHashData` at `0x18003325b`
- `bcrypt!BCryptFinishHash` at `0x18003327b`
- `bcrypt!BCryptFinishHash` at `0x18003327b`
- `bcrypt!BCryptCreateHash` at `0x180033235`
- `bcrypt!BCryptCreateHash` at `0x180033235`

## pseudocode

```c
__int64 __fastcall ClusterGlobalData::ComputeSQMHash(PUCHAR *this)
{
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v4; // [rsp+50h] [rbp-18h]

  *(_OWORD *)hHash = 0;
  v4 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash[0], this[2], *((_DWORD *)this + 6) - (unsigned int)this[2], 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(hHash[0], (PUCHAR)&hHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash[0]);
  return LODWORD(hHash[1]);
}

```

## disassembly

```asm
0x1800331f0  mov     r11, rsp
0x1800331f3  mov     [r11+10h], rbx
0x1800331f7  push    rdi
0x1800331f8  sub     rsp, 60h
0x1800331fc  mov     rax, cs:__security_cookie
0x180033203  xor     rax, rsp
0x180033206  mov     [rsp+68h+var_10], rax
0x18003320b  xor     eax, eax
0x18003320d  lea     rdx, [r11-28h]; phHash
0x180033211  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180033215  xorps   xmm0, xmm0
0x180033218  mov     rbx, rcx
0x18003321b  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18003321f  movups  xmmword ptr [rsp+68h+hHash], xmm0
0x180033224  lea     ecx, [rax+21h]; hAlgorithm
0x180033227  mov     [r11-18h], rax
0x18003322b  xor     r9d, r9d; cbHashObject
0x18003322e  mov     [r11-48h], rax
0x180033232  xor     r8d, r8d; pbHashObject
0x180033235  call    cs:__imp_BCryptCreateHash
0x18003323b  mov     edi, 7
0x180033240  test    eax, eax
0x180033242  jns     short loc_180033248
0x180033244  mov     ecx, edi
0x180033246  int     29h; Win8: RtlFailFast(ecx)
0x180033248  mov     rdx, [rbx+10h]; pbInput
0x18003324c  xor     r9d, r9d; dwFlags
0x18003324f  mov     r8d, [rbx+18h]
0x180033253  mov     rcx, [rsp+68h+hHash]; hHash
0x180033258  sub     r8d, edx; cbInput
0x18003325b  call    cs:__imp_BCryptHashData
0x180033261  test    eax, eax
0x180033263  jns     short loc_18003326A
0x180033265  mov     rcx, rdi
0x180033268  int     29h; Win8: RtlFailFast(ecx)
0x18003326a  mov     rcx, [rsp+68h+hHash]; hHash
0x18003326f  lea     rdx, [rsp+68h+hHash+8]; pbOutput
0x180033274  xor     r9d, r9d; dwFlags
0x180033277  lea     r8d, [r9+10h]; cbOutput
0x18003327b  call    cs:__imp_BCryptFinishHash
0x180033281  test    eax, eax
0x180033283  jns     short loc_18003328A
0x180033285  mov     rcx, rdi
0x180033288  int     29h; Win8: RtlFailFast(ecx)
0x18003328a  mov     rcx, [rsp+68h+hHash]; hHash
0x18003328f  call    cs:__imp_BCryptDestroyHash
0x180033295  mov     eax, dword ptr [rsp+68h+hHash+8]
0x180033299  mov     rcx, [rsp+68h+var_10]
0x18003329e  xor     rcx, rsp; StackCookie
0x1800332a1  call    __security_check_cookie
0x1800332a6  mov     rbx, [rsp+68h+arg_8]
0x1800332ab  add     rsp, 60h
0x1800332af  pop     rdi
0x1800332b0  retn
```
