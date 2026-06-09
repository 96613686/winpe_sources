# NsiAllocateAndGetPersistentDataWithMaskTable

- ea: `0x180002bd0`
- end: `0x180002e35`
- name: `NsiAllocateAndGetPersistentDataWithMaskTable`
- size: `613`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002bd0`
- `0x180002ea0`
- `0x180002f60`
- `0x1800030e1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ca9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ca9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d15`

## pseudocode

```c
__int64 __fastcall NsiAllocateAndGetPersistentDataWithMaskTable(
        int a1,
        int a2,
        _QWORD *a3,
        unsigned int a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned int v8; // r10d
  unsigned int v9; // r15d
  __int64 BytesReturned; // r13
  int v11; // eax
  void *v12; // rbp
  void *v13; // rsi
  void *v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // r14d
  unsigned int v19; // eax
  unsigned int v20; // ebx
  void *v21; // rax
  void *v22; // rax
  unsigned int v23; // eax
  _DWORD v25[18]; // [rsp+50h] [rbp-48h] BYREF
  int v26; // [rsp+A0h] [rbp+8h]

  v26 = a1;
  v8 = 0;
  v9 = 0;
  BytesReturned = a4;
  v11 = a2;
  while ( 1 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    if ( v9 >= 3 )
      goto LABEL_27;
    v25[0] = 0;
    v15 = NsiEnumerateObjectsAllPersistentParametersWithMask(1, a1, v11, 0, 0, 0, 0, 0, (__int64)v25);
    v16 = v15;
    if ( v15 && v15 != 234 )
      goto LABEL_25;
    v17 = v25[0] >> 3;
    if ( v25[0] >> 3 < 0xAu )
      v17 = 10;
    v18 = -1;
    v19 = v25[0] + v17;
    if ( v19 >= v25[0] )
      v18 = v19;
    v25[0] = v18;
    if ( (_DWORD)BytesReturned )
    {
      if ( (unsigned __int64)v18 * BytesReturned > 0xFFFFFFFF )
        goto LABEL_21;
      v12 = HeapAlloc(g_NsiHeap, 0, (unsigned int)BytesReturned * v18);
      if ( !v12 )
      {
LABEL_20:
        v16 = 8;
LABEL_25:
        NsiFreePersistentDataWithMaskTable(v12, v13, v14);
        return v16;
      }
    }
    if ( !a7 )
      goto LABEL_17;
    if ( v18 * (unsigned __int64)a7 > 0xFFFFFFFF )
    {
LABEL_21:
      v16 = 534;
      goto LABEL_25;
    }
    v20 = a7 * v18;
    v21 = HeapAlloc(g_NsiHeap, 0, a7 * v18);
    v13 = v21;
    if ( !v21 )
      goto LABEL_20;
    memset_0(v21, 0, v20);
    v22 = HeapAlloc(g_NsiHeap, 0, v20);
    v14 = v22;
    if ( !v22 )
      goto LABEL_20;
    memset_0(v22, 0, v20);
LABEL_17:
    v23 = NsiEnumerateObjectsAllPersistentParametersWithMask(
            1,
            v26,
            a2,
            (int)v12,
            BytesReturned,
            (__int64)v13,
            (__int64)v14,
            a7,
            (__int64)v25);
    v16 = v23;
    if ( v23 != 234 )
      break;
    if ( v9 == 2 )
    {
      v8 = v25[0];
      if ( v25[0] > v18 )
        v8 = v18;
      goto LABEL_27;
    }
    NsiFreePersistentDataWithMaskTable(v12, v13, v14);
    v8 = v25[0];
    ++v9;
    v11 = a2;
    a1 = v26;
  }
  if ( v23 )
    goto LABEL_25;
  v8 = v25[0];
LABEL_27:
  *a8 = v8;
  if ( v12 )
    *a3 = v12;
  if ( v13 )
    *a5 = v13;
  if ( v14 )
    *a6 = v14;
  return 0;
}

```

## disassembly

```asm
0x180002bd0  mov     rax, rsp
0x180002bd3  mov     [rax+20h], rbx
0x180002bd7  mov     [rax+18h], r8
0x180002bdb  mov     [rax+10h], edx
0x180002bde  mov     [rax+8], rcx
0x180002be2  push    rbp
0x180002be3  push    rsi
0x180002be4  push    rdi
0x180002be5  push    r12
0x180002be7  push    r13
0x180002be9  push    r14
0x180002beb  push    r15
0x180002bed  sub     rsp, 60h
0x180002bf1  mov     r12d, [rsp+98h+arg_30]
0x180002bf9  xor     r10d, r10d
0x180002bfc  xor     r15d, r15d
0x180002bff  mov     r13d, r9d
0x180002c02  mov     eax, edx
0x180002c04  xor     ebp, ebp
0x180002c06  xor     esi, esi
0x180002c08  xor     edi, edi
0x180002c0a  mov     r14d, 0Ah
0x180002c10  cmp     r15d, 3
0x180002c14  jnb     loc_180002DE0
0x180002c1a  lea     rdx, [rsp+98h+var_48]
0x180002c1f  mov     [rsp+98h+var_48], edi
0x180002c23  mov     [rsp+98h+var_58], rdx; __int64
0x180002c28  xor     r9d, r9d; int
0x180002c2b  mov     [rsp+98h+var_60], edi; int
0x180002c2f  mov     rdx, rcx; int
0x180002c32  mov     [rsp+98h+var_68], rdi; __int64
0x180002c37  lea     ecx, [rbp+1]; int
0x180002c3a  mov     [rsp+98h+var_70], rdi; __int64
0x180002c3f  mov     r8d, eax; int
0x180002c42  mov     [rsp+98h+BytesReturned], edi; BytesReturned
0x180002c46  call    NsiEnumerateObjectsAllPersistentParametersWithMask
0x180002c4b  mov     ebx, eax
0x180002c4d  test    eax, eax
0x180002c4f  jz      short loc_180002C5C
0x180002c51  cmp     eax, 0EAh
0x180002c56  jnz     loc_180002DC9
0x180002c5c  mov     ecx, [rsp+98h+var_48]
0x180002c60  mov     edx, 0FFFFFFFFh
0x180002c65  mov     eax, ecx
0x180002c67  shr     eax, 3
0x180002c6a  cmp     eax, r14d
0x180002c6d  cmovb   eax, r14d
0x180002c71  mov     r14d, edx
0x180002c74  add     eax, ecx
0x180002c76  cmp     eax, ecx
0x180002c78  cmovnb  r14d, eax
0x180002c7c  mov     [rsp+98h+var_48], r14d
0x180002c81  mov     ebx, r14d
0x180002c84  test    r13d, r13d
0x180002c87  jz      short loc_180002CC0
0x180002c89  mov     rax, r13
0x180002c8c  imul    rax, rbx
0x180002c90  cmp     rax, rdx
0x180002c93  ja      loc_180002DAF
0x180002c99  mov     rcx, cs:g_NsiHeap; hHeap
0x180002ca0  mov     r8d, r14d
0x180002ca3  imul    r8d, r13d; dwBytes
0x180002ca7  xor     edx, edx; dwFlags
0x180002ca9  call    cs:__imp_HeapAlloc
0x180002caf  mov     rbp, rax
0x180002cb2  test    rax, rax
0x180002cb5  jz      loc_180002DA8
0x180002cbb  mov     edx, 0FFFFFFFFh
0x180002cc0  test    r12d, r12d
0x180002cc3  jz      short loc_180002D34
0x180002cc5  mov     rax, r12
0x180002cc8  imul    rax, rbx
0x180002ccc  cmp     rax, rdx
0x180002ccf  ja      loc_180002DAF
0x180002cd5  mov     rcx, cs:g_NsiHeap; hHeap
0x180002cdc  mov     eax, r14d
0x180002cdf  imul    eax, r12d
0x180002ce3  xor     edx, edx; dwFlags
0x180002ce5  mov     r8d, eax; dwBytes
0x180002ce8  mov     ebx, eax
0x180002cea  call    cs:__imp_HeapAlloc
0x180002cf0  mov     rsi, rax
0x180002cf3  test    rax, rax
0x180002cf6  jz      loc_180002DA8
0x180002cfc  mov     r8d, ebx; Size
0x180002cff  xor     edx, edx; Val
0x180002d01  mov     rcx, rax; void *
0x180002d04  call    memset_0
0x180002d09  mov     rcx, cs:g_NsiHeap; hHeap
0x180002d10  mov     r8d, ebx; dwBytes
0x180002d13  xor     edx, edx; dwFlags
0x180002d15  call    cs:__imp_HeapAlloc
0x180002d1b  mov     rdi, rax
0x180002d1e  test    rax, rax
0x180002d21  jz      loc_180002DA8
0x180002d27  mov     r8d, ebx; Size
0x180002d2a  xor     edx, edx; Val
0x180002d2c  mov     rcx, rax; void *
0x180002d2f  call    memset_0
0x180002d34  mov     r8d, [rsp+98h+arg_8]; int
0x180002d3c  lea     rax, [rsp+98h+var_48]
0x180002d41  mov     rdx, qword ptr [rsp+98h+arg_0]; int
0x180002d49  mov     r9, rbp; int
0x180002d4c  mov     [rsp+98h+var_58], rax; __int64
0x180002d51  mov     ecx, 1; int
0x180002d56  mov     [rsp+98h+var_60], r12d; int
0x180002d5b  mov     [rsp+98h+var_68], rdi; __int64
0x180002d60  mov     [rsp+98h+var_70], rsi; __int64
0x180002d65  mov     [rsp+98h+BytesReturned], r13d; BytesReturned
0x180002d6a  call    NsiEnumerateObjectsAllPersistentParametersWithMask
0x180002d6f  mov     ebx, eax
0x180002d71  cmp     eax, 0EAh
0x180002d76  jnz     short loc_180002DC5
0x180002d78  cmp     r15d, 2
0x180002d7c  jz      short loc_180002DB6
0x180002d7e  mov     r8, rdi; LPVOID
0x180002d81  mov     rdx, rsi; LPVOID
0x180002d84  mov     rcx, rbp; lpMem
0x180002d87  call    NsiFreePersistentDataWithMaskTable
0x180002d8c  mov     r10d, [rsp+98h+var_48]
0x180002d91  inc     r15d
0x180002d94  mov     eax, [rsp+98h+arg_8]
0x180002d9b  mov     rcx, qword ptr [rsp+98h+arg_0]
0x180002da3  jmp     loc_180002C04
0x180002da8  mov     ebx, 8
0x180002dad  jmp     short loc_180002DC9
0x180002daf  mov     ebx, 216h
0x180002db4  jmp     short loc_180002DC9
0x180002db6  mov     r10d, [rsp+98h+var_48]
0x180002dbb  cmp     r10d, r14d
0x180002dbe  jbe     short loc_180002DE0
0x180002dc0  mov     r10d, r14d
0x180002dc3  jmp     short loc_180002DE0
0x180002dc5  test    eax, eax
0x180002dc7  jz      short loc_180002DDB
0x180002dc9  mov     r8, rdi; LPVOID
0x180002dcc  mov     rdx, rsi; LPVOID
0x180002dcf  mov     rcx, rbp; lpMem
0x180002dd2  call    NsiFreePersistentDataWithMaskTable
0x180002dd7  mov     eax, ebx
0x180002dd9  jmp     short loc_180002E1D
0x180002ddb  mov     r10d, [rsp+98h+var_48]
0x180002de0  mov     rax, [rsp+98h+arg_38]
0x180002de8  mov     [rax], r10d
0x180002deb  test    rbp, rbp
0x180002dee  jz      short loc_180002DFB
0x180002df0  mov     rax, [rsp+98h+arg_10]
0x180002df8  mov     [rax], rbp
0x180002dfb  test    rsi, rsi
0x180002dfe  jz      short loc_180002E0B
0x180002e00  mov     rax, [rsp+98h+arg_20]
0x180002e08  mov     [rax], rsi
0x180002e0b  test    rdi, rdi
0x180002e0e  jz      short loc_180002E1B
0x180002e10  mov     rax, [rsp+98h+arg_28]
0x180002e18  mov     [rax], rdi
0x180002e1b  xor     eax, eax
0x180002e1d  mov     rbx, [rsp+98h+arg_18]
0x180002e25  add     rsp, 60h
0x180002e29  pop     r15
0x180002e2b  pop     r14
0x180002e2d  pop     r13
0x180002e2f  pop     r12
0x180002e31  pop     rdi
0x180002e32  pop     rsi
0x180002e33  pop     rbp
0x180002e34  retn
```
