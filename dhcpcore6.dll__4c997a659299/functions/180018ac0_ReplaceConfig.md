# ReplaceConfig

- ea: `0x180018ac0`
- end: `0x180018c66`
- name: `ReplaceConfig`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800062e8`

## callees

- `0x180018ac0`
- `0x18001d62c`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018b2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018c07`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018b2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018c07`

## pseudocode

```c
__int64 __fastcall ReplaceConfig(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  unsigned int v7; // r12d
  __int64 v8; // rbx
  unsigned int v10; // esi
  unsigned int i; // r15d
  unsigned int v12; // r10d
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  LSTATUS v18; // eax

  if ( !a3 || !a2 || a3 < 8 )
    return 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  do
  {
    if ( time((time_t *const)a1) > *(_QWORD *)(a2 + 24 * v8 + 8) )
    {
      v5 = RegDeleteKeyExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)(a2 + 24 * v8), 0, 0);
      ++v6;
      *(_QWORD *)(a2 + 24 * v8 + 16) = 0x7FFFFFFFFFFFFFFFLL;
    }
    ++v7;
    ++v8;
  }
  while ( v7 < a3 );
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 84, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v6);
  if ( a3 < 0x80 )
    return 0;
  if ( v6 < 8 )
  {
    v10 = 8 - v6;
    for ( i = 0; i < v10; v5 = v18 )
    {
      v12 = i;
      v13 = 0;
      v14 = *(_QWORD *)(a2 + 24LL * i + 16);
      do
      {
        v15 = (unsigned int)v13;
        v16 = *(_QWORD *)(a2 + 24 * v13 + 16);
        if ( v14 <= v16 )
          v15 = v12;
        v13 = (unsigned int)(v13 + 1);
        v12 = v15;
        if ( v14 <= v16 )
          v16 = v14;
        v14 = v16;
      }
      while ( (unsigned int)v13 < a3 );
      v17 = 3 * v15;
      v18 = RegDeleteKeyExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)(a2 + 24 * v15), 0, 0);
      ++i;
      *(_QWORD *)(a2 + 8 * v17 + 16) = 0x7FFFFFFFFFFFFFFFLL;
    }
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_d(1028, 85, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v10);
  }
  return v5;
}

```

## disassembly

```asm
0x180018ac0  mov     [rsp+arg_0], rcx
0x180018ac5  push    rbx
0x180018ac6  push    rbp
0x180018ac7  push    rsi
0x180018ac8  push    rdi
0x180018ac9  push    r12
0x180018acb  push    r13
0x180018acd  push    r14
0x180018acf  push    r15
0x180018ad1  sub     rsp, 28h
0x180018ad5  mov     ebp, r8d
0x180018ad8  mov     rdi, rdx
0x180018adb  test    r8d, r8d
0x180018ade  jz      loc_180018C52
0x180018ae4  test    rdx, rdx
0x180018ae7  jz      loc_180018C52
0x180018aed  mov     esi, 8
0x180018af2  cmp     r8d, esi
0x180018af5  jb      loc_180018C52
0x180018afb  mov     rsi, [rsp+68h+arg_0]
0x180018b00  xor     r14d, r14d
0x180018b03  xor     r15d, r15d
0x180018b06  xor     r12d, r12d
0x180018b09  xor     ebx, ebx
0x180018b0b  call    time
0x180018b10  lea     r13, [rbx+rbx*2]
0x180018b14  cmp     rax, [rdi+r13*8+8]
0x180018b19  jle     short loc_180018B4D
0x180018b1b  mov     rdx, [rdi+r13*8]; lpSubKey
0x180018b1f  xor     r9d, r9d; Reserved
0x180018b22  mov     rcx, [rsi+288h]; hKey
0x180018b29  xor     r8d, r8d; samDesired
0x180018b2c  call    cs:__imp_RegDeleteKeyExW
0x180018b33  nop     dword ptr [rax+rax+00h]
0x180018b38  mov     r14d, eax
0x180018b3b  inc     r15d
0x180018b3e  mov     rax, 7FFFFFFFFFFFFFFFh
0x180018b48  mov     [rdi+r13*8+10h], rax
0x180018b4d  inc     r12d
0x180018b50  inc     rbx
0x180018b53  cmp     r12d, ebp
0x180018b56  jb      short loc_180018B0B
0x180018b58  test    byte ptr cs:xmmword_1800423E0, 10h
0x180018b5f  mov     r12d, 404h
0x180018b65  mov     esi, 8
0x180018b6a  jz      short loc_180018B81
0x180018b6c  lea     edx, [rsi+4Ch]
0x180018b6f  mov     ecx, r12d
0x180018b72  mov     r9d, r15d
0x180018b75  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180018b7c  call    WPP_SF_d
0x180018b81  cmp     ebp, 80h
0x180018b87  jb      loc_180018C52
0x180018b8d  cmp     r15d, esi
0x180018b90  jb      short loc_180018B9A
0x180018b92  mov     eax, r14d
0x180018b95  jmp     loc_180018C54
0x180018b9a  sub     esi, r15d
0x180018b9d  mov     r15d, 0
0x180018ba3  jz      loc_180018C29
0x180018ba9  mov     r12, 7FFFFFFFFFFFFFFFh
0x180018bb3  mov     eax, r15d
0x180018bb6  mov     r10d, r15d
0x180018bb9  xor     r8d, r8d
0x180018bbc  lea     rcx, [rax+rax*2]
0x180018bc0  mov     r9, [rdi+rcx*8+10h]
0x180018bc5  lea     rcx, [r8+r8*2]
0x180018bc9  mov     eax, r8d
0x180018bcc  mov     rdx, [rdi+rcx*8+10h]
0x180018bd1  cmp     r9, rdx
0x180018bd4  cmovle  eax, r10d
0x180018bd8  inc     r8d
0x180018bdb  cmp     r9, rdx
0x180018bde  mov     r10d, eax
0x180018be1  cmovle  rdx, r9
0x180018be5  mov     r9, rdx
0x180018be8  cmp     r8d, ebp
0x180018beb  jb      short loc_180018BC5
0x180018bed  lea     rbx, [rax+rax*2]
0x180018bf1  xor     r9d, r9d; Reserved
0x180018bf4  mov     rax, [rsp+68h+arg_0]
0x180018bf9  xor     r8d, r8d; samDesired
0x180018bfc  mov     rdx, [rdi+rbx*8]; lpSubKey
0x180018c00  mov     rcx, [rax+288h]; hKey
0x180018c07  call    cs:__imp_RegDeleteKeyExW
0x180018c0e  nop     dword ptr [rax+rax+00h]
0x180018c13  inc     r15d
0x180018c16  mov     [rdi+rbx*8+10h], r12
0x180018c1b  mov     r14d, eax
0x180018c1e  cmp     r15d, esi
0x180018c21  jb      short loc_180018BB3
0x180018c23  mov     r12d, 404h
0x180018c29  test    byte ptr cs:xmmword_1800423E0, 10h
0x180018c30  jz      loc_180018B92
0x180018c36  mov     edx, 55h ; 'U'
0x180018c3b  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180018c42  mov     ecx, r12d
0x180018c45  mov     r9d, esi
0x180018c48  call    WPP_SF_d
0x180018c4d  jmp     loc_180018B92
0x180018c52  xor     eax, eax
0x180018c54  add     rsp, 28h
0x180018c58  pop     r15
0x180018c5a  pop     r14
0x180018c5c  pop     r13
0x180018c5e  pop     r12
0x180018c60  pop     rdi
0x180018c61  pop     rsi
0x180018c62  pop     rbp
0x180018c63  pop     rbx
0x180018c64  retn
```
