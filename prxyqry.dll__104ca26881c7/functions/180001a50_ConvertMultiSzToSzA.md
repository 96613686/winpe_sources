# ConvertMultiSzToSzA

- ea: `0x180001a50`
- end: `0x180001b38`
- name: `ConvertMultiSzToSzA`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a50`
- `0x180002d10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001a98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001b1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001b1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001b2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001b2d`

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
0x180001a50  push    rbx
0x180001a52  push    rbp
0x180001a53  push    rsi
0x180001a54  push    rdi
0x180001a55  push    r14
0x180001a57  push    r15
0x180001a59  sub     rsp, 28h
0x180001a5d  xor     ebx, ebx
0x180001a5f  mov     r15, r9
0x180001a62  mov     [r9], rbx
0x180001a65  mov     r14, r8
0x180001a68  mov     rsi, rdx
0x180001a6b  mov     rdi, rcx
0x180001a6e  call    ValidateMultiSzA
0x180001a73  mov     ebp, eax
0x180001a75  test    eax, eax
0x180001a77  jnz     short loc_180001AA9
0x180001a79  cmp     [r14], ebx
0x180001a7c  jz      short loc_180001AA9
0x180001a7e  mov     ebx, [r14]
0x180001a81  shl     rbx, 3
0x180001a85  call    cs:__imp_GetProcessHeap
0x180001a8b  lea     r14d, [rbp+8]
0x180001a8f  mov     r8, rbx; dwBytes
0x180001a92  mov     rcx, rax; hHeap
0x180001a95  mov     edx, r14d; dwFlags
0x180001a98  call    cs:__imp_HeapAlloc
0x180001a9e  mov     rbx, rax
0x180001aa1  test    rax, rax
0x180001aa4  jnz     short loc_180001ABB
0x180001aa6  mov     ebp, r14d
0x180001aa9  mov     [r15], rbx
0x180001aac  mov     eax, ebp
0x180001aae  add     rsp, 28h
0x180001ab2  pop     r15
0x180001ab4  pop     r14
0x180001ab6  pop     rdi
0x180001ab7  pop     rsi
0x180001ab8  pop     rbp
0x180001ab9  pop     rbx
0x180001aba  retn
0x180001abb  xor     r8d, r8d
0x180001abe  jmp     short loc_180001B0D
0x180001ac0  test    rdi, rdi
0x180001ac3  jz      short loc_180001B1A
0x180001ac5  lea     rax, [rsi-1]
0x180001ac9  cmp     rax, 7FFFFFFFh
0x180001acf  ja      short loc_180001B1A
0x180001ad1  mov     rdx, rdi
0x180001ad4  mov     rcx, rax
0x180001ad7  test    rax, rax
0x180001ada  jz      short loc_180001AEA
0x180001adc  cmp     byte ptr [rdx], 0
0x180001adf  jz      short loc_180001B15
0x180001ae1  inc     rdx
0x180001ae4  sub     rax, 1
0x180001ae8  jnz     short loc_180001ADC
0x180001aea  xor     ecx, ecx
0x180001aec  test    rax, rax
0x180001aef  jz      short loc_180001B1A
0x180001af1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001af5  sub     rax, rcx
0x180001af8  add     rsi, rax
0x180001afb  test    rcx, rcx
0x180001afe  jz      short loc_180001B07
0x180001b00  mov     [rbx+r8*8], rdi
0x180001b04  inc     r8d
0x180001b07  inc     rdi
0x180001b0a  add     rdi, rcx
0x180001b0d  cmp     rsi, 1
0x180001b11  ja      short loc_180001AC0
0x180001b13  jmp     short loc_180001AA9
0x180001b15  sub     rcx, rax
0x180001b18  jmp     short loc_180001AEC
0x180001b1a  mov     ebp, 57h ; 'W'
0x180001b1f  call    cs:__imp_GetProcessHeap
0x180001b25  mov     r8, rbx; lpMem
0x180001b28  xor     edx, edx; dwFlags
0x180001b2a  mov     rcx, rax; hHeap
0x180001b2d  call    cs:__imp_HeapFree
0x180001b33  jmp     loc_180001AAC
```
