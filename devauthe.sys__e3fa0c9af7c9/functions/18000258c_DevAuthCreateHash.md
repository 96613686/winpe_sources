# DevAuthCreateHash

- ea: `0x18000258c`
- end: `0x18000269a`
- name: `DevAuthCreateHash`
- size: `270`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001020`
- `0x180002740`

## callees

- `0x18000258c`
- `0x180002e00`
- `0x180003320`

## import_xrefs

- `cng!BCryptCreateHash` at `0x180002660`
- `cng!BCryptCreateHash` at `0x180002660`
- `cng!BCryptGetProperty` at `0x180002622`
- `cng!BCryptGetProperty` at `0x180002622`
- `cng!BCryptOpenAlgorithmProvider` at `0x1800025e5`
- `cng!BCryptOpenAlgorithmProvider` at `0x1800025e5`

## pseudocode

```c
__int64 __fastcall DevAuthCreateHash(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_HANDLE **a3)
{
  BCRYPT_ALG_HANDLE *v6; // rax
  BCRYPT_HANDLE *v7; // rbx
  ULONG *v8; // rsi
  UCHAR *v9; // rax
  unsigned int v10; // edi
  ULONG pcbResult; // [rsp+68h] [rbp+10h] BYREF

  pcbResult = 0;
  *a3 = 0;
  v6 = (BCRYPT_ALG_HANDLE *)DevAuthAlloc(0x20u);
  v7 = v6;
  if ( v6
    && BCryptOpenAlgorithmProvider(v6, L"SHA256", 0, cbSecret != 0 ? 8 : 0) >= 0
    && (v8 = (ULONG *)(v7 + 3), BCryptGetProperty(*v7, L"ObjectLength", (PUCHAR)v7 + 24, 4u, &pcbResult, 0) >= 0)
    && (v9 = (UCHAR *)DevAuthAlloc(*v8), (v7[2] = v9) != 0)
    && BCryptCreateHash(*v7, v7 + 1, v9, *v8, pbSecret, cbSecret, 0) >= 0 )
  {
    *a3 = v7;
    return 1;
  }
  else
  {
    v10 = 0;
    DevAuthHashCleanup(v7);
  }
  return v10;
}

```

## disassembly

```asm
0x18000258c  mov     [rsp+arg_0], rbx
0x180002591  mov     [rsp+arg_10], rbp
0x180002596  push    rsi
0x180002597  push    rdi
0x180002598  push    r14
0x18000259a  sub     rsp, 40h
0x18000259e  mov     r14, rcx
0x1800025a1  mov     [rsp+58h+arg_8], 0
0x1800025a9  mov     ecx, 20h ; ' '; Size
0x1800025ae  mov     qword ptr [r8], 0
0x1800025b5  mov     rdi, r8
0x1800025b8  mov     ebp, edx
0x1800025ba  call    DevAuthAlloc
0x1800025bf  mov     rbx, rax
0x1800025c2  test    rax, rax
0x1800025c5  jz      loc_18000267A
0x1800025cb  mov     r9d, ebp
0x1800025ce  lea     rdx, pszAlgId; "SHA256"
0x1800025d5  neg     r9d
0x1800025d8  mov     rcx, rax; phAlgorithm
0x1800025db  sbb     r9d, r9d
0x1800025de  xor     r8d, r8d; pszImplementation
0x1800025e1  and     r9d, 8; dwFlags
0x1800025e5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800025ec  nop     dword ptr [rax+rax+00h]
0x1800025f1  test    eax, eax
0x1800025f3  js      loc_18000267A
0x1800025f9  mov     rcx, [rbx]; hObject
0x1800025fc  lea     rax, [rsp+58h+arg_8]
0x180002601  lea     rsi, [rbx+18h]
0x180002605  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000260d  mov     r8, rsi; pbOutput
0x180002610  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180002615  mov     r9d, 4; cbOutput
0x18000261b  lea     rdx, pszProperty; "ObjectLength"
0x180002622  call    cs:__imp_BCryptGetProperty
0x180002629  nop     dword ptr [rax+rax+00h]
0x18000262e  test    eax, eax
0x180002630  js      short loc_18000267A
0x180002632  mov     ecx, [rsi]; Size
0x180002634  call    DevAuthAlloc
0x180002639  mov     [rbx+10h], rax
0x18000263d  test    rax, rax
0x180002640  jz      short loc_18000267A
0x180002642  mov     r9d, [rsi]; cbHashObject
0x180002645  lea     rdx, [rbx+8]; phHash
0x180002649  mov     rcx, [rbx]; hAlgorithm
0x18000264c  mov     r8, rax; pbHashObject
0x18000264f  mov     [rsp+58h+var_28], 0; dwFlags
0x180002657  mov     [rsp+58h+dwFlags], ebp; cbSecret
0x18000265b  mov     [rsp+58h+pcbResult], r14; pbSecret
0x180002660  call    cs:__imp_BCryptCreateHash
0x180002667  nop     dword ptr [rax+rax+00h]
0x18000266c  test    eax, eax
0x18000266e  js      short loc_18000267A
0x180002670  mov     [rdi], rbx
0x180002673  mov     edi, 1
0x180002678  jmp     short loc_180002684
0x18000267a  xor     edi, edi
0x18000267c  mov     rcx, rbx; P
0x18000267f  call    _DevAuthHashCleanup
0x180002684  mov     rbx, [rsp+58h+arg_0]
0x180002689  mov     eax, edi
0x18000268b  mov     rbp, [rsp+58h+arg_10]
0x180002690  add     rsp, 40h
0x180002694  pop     r14
0x180002696  pop     rdi
0x180002697  pop     rsi
0x180002698  retn
```
