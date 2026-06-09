# _GetKeyFromFile

- ea: `0x18000d358`
- end: `0x18000d4ba`
- name: `_GetKeyFromFile`
- size: `354`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b00`

## callees

- `0x180001bb0`
- `0x18000d358`

## import_xrefs

- `KERNEL32!HeapSize` at `0x18000d463`
- `KERNEL32!HeapSize` at `0x18000d463`
- `KERNEL32!HeapFree` at `0x18000d491`
- `KERNEL32!HeapFree` at `0x18000d491`
- `KERNEL32!HeapAlloc` at `0x18000d3fd`
- `KERNEL32!HeapAlloc` at `0x18000d3fd`
- `KERNEL32!GetProcessHeap` at `0x18000d3ec`
- `KERNEL32!GetProcessHeap` at `0x18000d455`
- `KERNEL32!GetProcessHeap` at `0x18000d483`
- `KERNEL32!GetProcessHeap` at `0x18000d3ec`
- `KERNEL32!GetProcessHeap` at `0x18000d455`
- `KERNEL32!GetProcessHeap` at `0x18000d483`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x18000d3c7`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x18000d444`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x18000d3c7`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x18000d444`

## pseudocode

```c
__int64 __fastcall GetKeyFromFile(__int64 a1, _QWORD *a2)
{
  int v4; // edi
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  _OWORD *v7; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  SIZE_T v10; // rax
  _BYTE *i; // rcx
  HANDLE v12; // rax
  SIZE_T dwBytes; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int128 v16; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  __int128 v18; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+60h] [rbp-10h]

  dwBytes = 0;
  v15 = 0;
  v19 = 0;
  *(_QWORD *)&v16 = 0x100000038LL;
  *((_QWORD *)&v16 + 1) = 262149;
  v17 = 0;
  v18 = 0;
  v4 = FveAuthElementReadExternalKeyW(a1, &v16, 56, &dwBytes);
  if ( v4 == -2147024774 )
  {
    v5 = dwBytes;
    if ( dwBytes >= 0x38 )
    {
      ProcessHeap = GetProcessHeap();
      v7 = HeapAlloc(ProcessHeap, 8u, v5);
      v8 = v7;
      if ( v7 )
      {
        *v7 = v16;
        v7[1] = v17;
        v7[2] = v18;
        *((_QWORD *)v7 + 6) = v19;
        v4 = FveAuthElementReadExternalKeyW(a1, v7, dwBytes, &v15);
        if ( v4 < 0 )
        {
          v9 = GetProcessHeap();
          v10 = HeapSize(v9, 0, v8);
          if ( v10 != -1 )
          {
            for ( i = v8; v10; --v10 )
              *i++ = 0;
            v12 = GetProcessHeap();
            HeapFree(v12, 0, v8);
          }
        }
        else
        {
          *a2 = v8;
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024883;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d358  mov     [rsp-18h+arg_10], rbx
0x18000d35d  mov     [rsp-18h+arg_18], rsi
0x18000d362  push    rbp
0x18000d363  push    rdi
0x18000d364  push    r14
0x18000d366  mov     rbp, rsp
0x18000d369  sub     rsp, 70h
0x18000d36d  mov     rax, cs:__security_cookie
0x18000d374  xor     rax, rsp
0x18000d377  mov     [rbp+var_8], rax
0x18000d37b  xorps   xmm0, xmm0
0x18000d37e  mov     [rbp+dwBytes], 0
0x18000d386  movups  [rbp+var_40], xmm0
0x18000d38a  xor     eax, eax
0x18000d38c  mov     [rbp+var_48], 0
0x18000d394  mov     rsi, rdx
0x18000d397  mov     [rbp+var_10], rax
0x18000d39b  lea     r9, [rbp+dwBytes]
0x18000d39f  mov     dword ptr [rbp+var_40], 38h ; '8'
0x18000d3a6  lea     rdx, [rbp+var_40]
0x18000d3aa  mov     dword ptr [rbp+var_40+4], 1
0x18000d3b1  lea     r8d, [rax+38h]
0x18000d3b5  mov     dword ptr [rbp+var_40+8], 40005h
0x18000d3bc  mov     r14, rcx
0x18000d3bf  movups  [rbp+var_30], xmm0
0x18000d3c3  movups  [rbp+var_20], xmm0
0x18000d3c7  call    cs:__imp_FveAuthElementReadExternalKeyW
0x18000d3cd  mov     edi, eax
0x18000d3cf  cmp     eax, 8007007Ah
0x18000d3d4  jnz     loc_18000D497
0x18000d3da  mov     rbx, [rbp+dwBytes]
0x18000d3de  cmp     rbx, 38h ; '8'
0x18000d3e2  jnb     short loc_18000D3EC
0x18000d3e4  lea     edi, [rax-6Dh]
0x18000d3e7  jmp     loc_18000D497
0x18000d3ec  call    cs:__imp_GetProcessHeap
0x18000d3f2  mov     r8, rbx; dwBytes
0x18000d3f5  mov     edx, 8; dwFlags
0x18000d3fa  mov     rcx, rax; hHeap
0x18000d3fd  call    cs:__imp_HeapAlloc
0x18000d403  mov     rbx, rax
0x18000d406  test    rax, rax
0x18000d409  jnz     short loc_18000D415
0x18000d40b  mov     edi, 8007000Eh
0x18000d410  jmp     loc_18000D497
0x18000d415  movups  xmm0, [rbp+var_40]
0x18000d419  lea     r9, [rbp+var_48]
0x18000d41d  mov     rdx, rbx
0x18000d420  mov     rcx, r14
0x18000d423  movups  xmmword ptr [rax], xmm0
0x18000d426  movups  xmm1, [rbp+var_30]
0x18000d42a  movups  xmmword ptr [rax+10h], xmm1
0x18000d42e  movups  xmm0, [rbp+var_20]
0x18000d432  movups  xmmword ptr [rax+20h], xmm0
0x18000d436  movsd   xmm1, [rbp+var_10]
0x18000d43b  movsd   qword ptr [rax+30h], xmm1
0x18000d440  mov     r8, [rbp+dwBytes]
0x18000d444  call    cs:__imp_FveAuthElementReadExternalKeyW
0x18000d44a  mov     edi, eax
0x18000d44c  test    eax, eax
0x18000d44e  js      short loc_18000D455
0x18000d450  mov     [rsi], rbx
0x18000d453  jmp     short loc_18000D497
0x18000d455  call    cs:__imp_GetProcessHeap
0x18000d45b  mov     r8, rbx; lpMem
0x18000d45e  xor     edx, edx; dwFlags
0x18000d460  mov     rcx, rax; hHeap
0x18000d463  call    cs:__imp_HeapSize
0x18000d469  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d46d  jz      short loc_18000D497
0x18000d46f  mov     rcx, rbx
0x18000d472  test    rax, rax
0x18000d475  jz      short loc_18000D483
0x18000d477  mov     byte ptr [rcx], 0
0x18000d47a  inc     rcx
0x18000d47d  sub     rax, 1
0x18000d481  jnz     short loc_18000D477
0x18000d483  call    cs:__imp_GetProcessHeap
0x18000d489  mov     r8, rbx; lpMem
0x18000d48c  xor     edx, edx; dwFlags
0x18000d48e  mov     rcx, rax; hHeap
0x18000d491  call    cs:__imp_HeapFree
0x18000d497  mov     eax, edi
0x18000d499  mov     rcx, [rbp+var_8]
0x18000d49d  xor     rcx, rsp; StackCookie
0x18000d4a0  call    __security_check_cookie
0x18000d4a5  lea     r11, [rsp+70h+var_s0]
0x18000d4aa  mov     rbx, [r11+30h]
0x18000d4ae  mov     rsi, [r11+38h]
0x18000d4b2  mov     rsp, r11
0x18000d4b5  pop     r14
0x18000d4b7  pop     rdi
0x18000d4b8  pop     rbp
0x18000d4b9  retn
```
