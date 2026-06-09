# mwAllocMoreBlockNodes

- ea: `0x180003a44`
- end: `0x180003b28`
- name: `mwAllocMoreBlockNodes`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001db8`
- `0x180002320`
- `0x180003e60`
- `0x180004318`

## callees

- `0x180003a44`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003ab3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003ad3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003ab3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003ad3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180003aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180003aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003a92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003a92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003a7d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003a7d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003ac5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003ac5`

## pseudocode

```c
__int64 __fastcall mwAllocMoreBlockNodes(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v3; // esi
  unsigned __int64 v4; // rbx
  HGLOBAL v5; // rax
  void *v6; // rbp
  char *v7; // rbx
  HGLOBAL v8; // rax
  __int64 v9; // rax
  char *v10; // rbx
  int v11; // eax

  v1 = *(_DWORD *)(a1 + 128);
  v3 = -1;
  if ( v1 )
  {
    if ( v1 + 32 < v1 )
      goto LABEL_14;
    v4 = 16LL * (v1 + 32);
    if ( v4 > 0xFFFFFFFF )
      goto LABEL_14;
    v5 = GlobalHandle(*(LPCVOID *)(a1 + 104));
    v6 = v5;
    if ( !v5 )
    {
      v7 = 0;
      goto LABEL_10;
    }
    GlobalUnlock(v5);
    v8 = GlobalReAlloc(v6, (unsigned int)v4, 0x42u);
    if ( !v8 )
    {
      v7 = 0;
      GlobalLock(v6);
      goto LABEL_10;
    }
  }
  else
  {
    v7 = 0;
    v8 = GlobalAlloc(0x42u, 0x200u);
    if ( !v8 )
      goto LABEL_10;
  }
  v7 = (char *)GlobalLock(v8);
LABEL_10:
  if ( !v7 )
  {
LABEL_14:
    *(_DWORD *)(a1 + 140) = 264;
    return v3;
  }
  v9 = 16LL * *(unsigned int *)(a1 + 128);
  *(_QWORD *)(a1 + 104) = v7;
  v10 = &v7[v9];
  v11 = 32;
  do
  {
    *((_DWORD *)v10 + 1) = -1;
    v10 += 16;
    --v11;
  }
  while ( v11 );
  v3 = *(_DWORD *)(a1 + 128);
  *(_DWORD *)(a1 + 128) = v3 + 32;
  return v3;
}

```

## disassembly

```asm
0x180003a44  push    rbx
0x180003a46  push    rbp
0x180003a47  push    rsi
0x180003a48  push    rdi
0x180003a49  sub     rsp, 28h
0x180003a4d  mov     eax, [rcx+80h]
0x180003a53  mov     rdi, rcx
0x180003a56  mov     esi, 0FFFFFFFFh
0x180003a5b  test    eax, eax
0x180003a5d  jz      short loc_180003ABB
0x180003a5f  lea     ecx, [rax+20h]
0x180003a62  cmp     ecx, eax
0x180003a64  jb      loc_180003B13
0x180003a6a  mov     ebx, ecx
0x180003a6c  shl     rbx, 4
0x180003a70  cmp     rbx, rsi
0x180003a73  ja      loc_180003B13
0x180003a79  mov     rcx, [rdi+68h]; pMem
0x180003a7d  call    cs:__imp_GlobalHandle
0x180003a83  mov     rbp, rax
0x180003a86  test    rax, rax
0x180003a89  jnz     short loc_180003A8F
0x180003a8b  xor     ebx, ebx
0x180003a8d  jmp     short loc_180003ADC
0x180003a8f  mov     rcx, rbp; hMem
0x180003a92  call    cs:__imp_GlobalUnlock
0x180003a98  mov     edx, ebx; dwBytes
0x180003a9a  mov     r8d, 42h ; 'B'; uFlags
0x180003aa0  mov     rcx, rbp; hMem
0x180003aa3  call    cs:__imp_GlobalReAlloc
0x180003aa9  test    rax, rax
0x180003aac  jnz     short loc_180003AD0
0x180003aae  xor     ebx, ebx
0x180003ab0  mov     rcx, rbp; hMem
0x180003ab3  call    cs:__imp_GlobalLock
0x180003ab9  jmp     short loc_180003ADC
0x180003abb  xor     ebx, ebx
0x180003abd  mov     edx, 200h; dwBytes
0x180003ac2  lea     ecx, [rbx+42h]; uFlags
0x180003ac5  call    cs:__imp_GlobalAlloc
0x180003acb  test    rax, rax
0x180003ace  jz      short loc_180003ADC
0x180003ad0  mov     rcx, rax; hMem
0x180003ad3  call    cs:__imp_GlobalLock
0x180003ad9  mov     rbx, rax
0x180003adc  test    rbx, rbx
0x180003adf  jz      short loc_180003B13
0x180003ae1  mov     eax, [rdi+80h]
0x180003ae7  shl     rax, 4
0x180003aeb  mov     [rdi+68h], rbx
0x180003aef  add     rbx, rax
0x180003af2  mov     eax, 20h ; ' '
0x180003af7  mov     [rbx+4], esi
0x180003afa  lea     rbx, [rbx+10h]
0x180003afe  add     eax, esi
0x180003b00  jnz     short loc_180003AF7
0x180003b02  mov     esi, [rdi+80h]
0x180003b08  lea     eax, [rsi+20h]
0x180003b0b  mov     [rdi+80h], eax
0x180003b11  jmp     short loc_180003B1D
0x180003b13  mov     dword ptr [rdi+8Ch], 108h
0x180003b1d  mov     eax, esi
0x180003b1f  add     rsp, 28h
0x180003b23  pop     rdi
0x180003b24  pop     rsi
0x180003b25  pop     rbp
0x180003b26  pop     rbx
0x180003b27  retn
```
