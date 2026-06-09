# ConvertMultiSzToSzA

- ea: `0x180001a60`
- end: `0x180001b61`
- name: `ConvertMultiSzToSzA`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a60`
- `0x180002ea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001aae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001aae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001b3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001b50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001b50`

## pseudocode

```c
__int64 __fastcall ConvertMultiSzToSzA(_BYTE *a1, unsigned __int64 a2, _DWORD *a3, _QWORD *a4)
{
  void *v4; // rbx
  unsigned int v9; // ebp
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  _BYTE *v15; // rdx
  unsigned __int64 v16; // rcx
  HANDLE v17; // rax

  v4 = 0;
  *a4 = 0;
  v9 = ValidateMultiSzA();
  if ( !v9 && *a3 )
  {
    v10 = 8LL * (unsigned int)*a3;
    ProcessHeap = GetProcessHeap();
    v4 = HeapAlloc(ProcessHeap, 8u, v10);
    if ( v4 )
    {
      v13 = 0;
      while ( a2 > 1 )
      {
        if ( !a1 )
          goto LABEL_21;
        v14 = a2 - 1;
        if ( a2 - 1 > 0x7FFFFFFF )
          goto LABEL_21;
        v15 = a1;
        while ( *v15 )
        {
          ++v15;
          if ( !--v14 )
          {
            v16 = 0;
            goto LABEL_14;
          }
        }
        v16 = a2 - 1 - v14;
LABEL_14:
        if ( !v14 )
        {
LABEL_21:
          v9 = 87;
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v4);
          return v9;
        }
        a2 += -1LL - v16;
        if ( v16 )
        {
          *((_QWORD *)v4 + v13) = a1;
          v13 = (unsigned int)(v13 + 1);
        }
        a1 += v16 + 1;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  *a4 = v4;
  return v9;
}

```

## disassembly

```asm
0x180001a60  push    rbx
0x180001a62  push    rbp
0x180001a63  push    rsi
0x180001a64  push    rdi
0x180001a65  push    r14
0x180001a67  push    r15
0x180001a69  sub     rsp, 28h
0x180001a6d  xor     ebx, ebx
0x180001a6f  mov     r15, r9
0x180001a72  mov     [r9], rbx
0x180001a75  mov     r14, r8
0x180001a78  mov     rsi, rdx
0x180001a7b  mov     rdi, rcx
0x180001a7e  call    ValidateMultiSzA
0x180001a83  mov     ebp, eax
0x180001a85  test    eax, eax
0x180001a87  jnz     short loc_180001AC5
0x180001a89  cmp     [r14], ebx
0x180001a8c  jz      short loc_180001AC5
0x180001a8e  mov     ebx, [r14]
0x180001a91  shl     rbx, 3
0x180001a95  call    cs:__imp_GetProcessHeap
0x180001a9c  nop     dword ptr [rax+rax+00h]
0x180001aa1  lea     r14d, [rbp+8]
0x180001aa5  mov     r8, rbx; dwBytes
0x180001aa8  mov     rcx, rax; hHeap
0x180001aab  mov     edx, r14d; dwFlags
0x180001aae  call    cs:__imp_HeapAlloc
0x180001ab5  nop     dword ptr [rax+rax+00h]
0x180001aba  mov     rbx, rax
0x180001abd  test    rax, rax
0x180001ac0  jnz     short loc_180001AD8
0x180001ac2  mov     ebp, r14d
0x180001ac5  mov     [r15], rbx
0x180001ac8  mov     eax, ebp
0x180001aca  add     rsp, 28h
0x180001ace  pop     r15
0x180001ad0  pop     r14
0x180001ad2  pop     rdi
0x180001ad3  pop     rsi
0x180001ad4  pop     rbp
0x180001ad5  pop     rbx
0x180001ad6  retn
0x180001ad8  xor     r8d, r8d
0x180001adb  jmp     short loc_180001B2A
0x180001add  test    rdi, rdi
0x180001ae0  jz      short loc_180001B37
0x180001ae2  lea     rax, [rsi-1]
0x180001ae6  cmp     rax, 7FFFFFFFh
0x180001aec  ja      short loc_180001B37
0x180001aee  mov     rdx, rdi
0x180001af1  mov     rcx, rax
0x180001af4  test    rax, rax
0x180001af7  jz      short loc_180001B07
0x180001af9  cmp     byte ptr [rdx], 0
0x180001afc  jz      short loc_180001B32
0x180001afe  inc     rdx
0x180001b01  sub     rax, 1
0x180001b05  jnz     short loc_180001AF9
0x180001b07  xor     ecx, ecx
0x180001b09  test    rax, rax
0x180001b0c  jz      short loc_180001B37
0x180001b0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b12  sub     rax, rcx
0x180001b15  add     rsi, rax
0x180001b18  test    rcx, rcx
0x180001b1b  jz      short loc_180001B24
0x180001b1d  mov     [rbx+r8*8], rdi
0x180001b21  inc     r8d
0x180001b24  inc     rdi
0x180001b27  add     rdi, rcx
0x180001b2a  cmp     rsi, 1
0x180001b2e  ja      short loc_180001ADD
0x180001b30  jmp     short loc_180001AC5
0x180001b32  sub     rcx, rax
0x180001b35  jmp     short loc_180001B09
0x180001b37  mov     ebp, 57h ; 'W'
0x180001b3c  call    cs:__imp_GetProcessHeap
0x180001b43  nop     dword ptr [rax+rax+00h]
0x180001b48  mov     r8, rbx; lpMem
0x180001b4b  xor     edx, edx; dwFlags
0x180001b4d  mov     rcx, rax; hHeap
0x180001b50  call    cs:__imp_HeapFree
0x180001b57  nop     dword ptr [rax+rax+00h]
0x180001b5c  jmp     loc_180001AC8
```
