# STRU::Copy(ushort const *)

- ea: `0x180001b60`
- end: `0x180001cc0`
- name: `?Copy@STRU@@QEAAJPEBG@Z`
- size: `352`
- prototype: `int(STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001930`
- `0x180001f50`
- `0x18001daa0`
- `0x180022dd0`
- `0x180029690`

## callees

- `0x180001b60`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c7a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180001c36`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180001c36`

## pseudocode

```c
int __fastcall STRU::Copy(STRU *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rbp
  int result; // eax
  unsigned int v11; // r15d
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  void *v14; // rax
  void *v15; // rbx
  HANDLE v16; // rax

  if ( !a2 )
    return -2147024809;
  v4 = -1;
  while ( a2[++v4] != 0 )
    ;
  v6 = *((unsigned int *)this + 10);
  v7 = (unsigned int)(2 * v4);
  if ( v6 >= v7 + 2 )
    goto LABEL_5;
  v11 = v7 + 128;
  if ( (unsigned __int64)(v7 + 128) > 0xFFFFFFFF )
    return -2147024362;
  if ( v11 <= (unsigned int)v6 )
    goto LABEL_5;
  if ( *((_BYTE *)this + 44) )
  {
    v12 = (void *)*((_QWORD *)this + 4);
    ProcessHeap = GetProcessHeap();
    v14 = HeapReAlloc(ProcessHeap, 0, v12, v11);
  }
  else
  {
    v16 = GetProcessHeap();
    v14 = HeapAlloc(v16, 0, v11);
  }
  v15 = v14;
  if ( v14 )
  {
    if ( !*((_BYTE *)this + 44) )
    {
      memcpy_0(v14, *((const void **)this + 4), *((unsigned int *)this + 10));
      *((_BYTE *)this + 44) = 1;
    }
    *((_QWORD *)this + 4) = v15;
    *((_DWORD *)this + 10) = v11;
LABEL_5:
    memcpy_0(*((void **)this + 4), a2, (unsigned int)v7);
    v8 = *((_QWORD *)this + 4);
    v9 = (unsigned int)v7 >> 1;
    result = 0;
    *((_DWORD *)this + 12) = v9;
    *(_WORD *)(v8 + 2 * v9) = 0;
    return result;
  }
  SetLastError(8u);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180001b60  push    rsi
0x180001b62  push    rdi
0x180001b63  sub     rsp, 38h
0x180001b67  mov     rdi, rdx
0x180001b6a  mov     rsi, rcx
0x180001b6d  test    rdx, rdx
0x180001b70  jz      loc_180001CB6
0x180001b76  mov     [rsp+48h+arg_8], rbp
0x180001b7b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001b82  mov     [rsp+48h+var_20], r14
0x180001b87  nop     word ptr [rax+rax+00000000h]
0x180001b90  cmp     word ptr [rdx+rax*2+2], 0
0x180001b96  lea     rax, [rax+1]
0x180001b9a  jnz     short loc_180001B90
0x180001b9c  mov     ecx, [rcx+28h]
0x180001b9f  lea     ebp, [rax+rax]
0x180001ba2  mov     [rsp+48h+arg_0], rbx
0x180001ba7  lea     rax, [rbp+2]
0x180001bab  mov     [rsp+48h+arg_10], r12
0x180001bb0  mov     [rsp+48h+var_28], r15
0x180001bb5  mov     r14d, ebp
0x180001bb8  cmp     rcx, rax
0x180001bbb  jb      short loc_180001BFD
0x180001bbd  mov     rcx, [rsi+20h]; void *
0x180001bc1  mov     r8, r14; Size
0x180001bc4  mov     rdx, rdi; Src
0x180001bc7  call    memcpy_0
0x180001bcc  mov     rcx, [rsi+20h]
0x180001bd0  shr     ebp, 1
0x180001bd2  mov     edx, ebp
0x180001bd4  xor     eax, eax
0x180001bd6  mov     [rsi+30h], edx
0x180001bd9  mov     [rcx+rbp*2], ax
0x180001bdd  mov     r15, [rsp+48h+var_28]
0x180001be2  mov     r14, [rsp+48h+var_20]
0x180001be7  mov     r12, [rsp+48h+arg_10]
0x180001bec  mov     rbp, [rsp+48h+arg_8]
0x180001bf1  mov     rbx, [rsp+48h+arg_0]
0x180001bf6  add     rsp, 38h
0x180001bfa  pop     rdi
0x180001bfb  pop     rsi
0x180001bfc  retn
0x180001bfd  lea     r15, [rbp+80h]
0x180001c04  mov     eax, 0FFFFFFFFh
0x180001c09  cmp     r15, rax
0x180001c0c  ja      short loc_180001C70
0x180001c0e  cmp     r15d, ecx
0x180001c11  jbe     short loc_180001BBD
0x180001c13  cmp     byte ptr [rsi+2Ch], 0
0x180001c17  mov     [rsp+48h+var_18], r13
0x180001c1c  mov     r13d, r15d
0x180001c1f  jz      short loc_180001C7A
0x180001c21  mov     rbx, [rsi+20h]
0x180001c25  call    cs:__imp_GetProcessHeap
0x180001c2b  mov     r9d, r13d; dwBytes
0x180001c2e  mov     r8, rbx; lpMem
0x180001c31  mov     rcx, rax; hHeap
0x180001c34  xor     edx, edx; dwFlags
0x180001c36  call    cs:__imp_HeapReAlloc
0x180001c3c  mov     r13, [rsp+48h+var_18]
0x180001c41  mov     rbx, rax
0x180001c44  test    rax, rax
0x180001c47  jz      short loc_180001C90
0x180001c49  cmp     byte ptr [rsi+2Ch], 0
0x180001c4d  jnz     short loc_180001C63
0x180001c4f  mov     r8d, [rsi+28h]; Size
0x180001c53  mov     rcx, rax; void *
0x180001c56  mov     rdx, [rsi+20h]; Src
0x180001c5a  call    memcpy_0
0x180001c5f  mov     byte ptr [rsi+2Ch], 1
0x180001c63  mov     [rsi+20h], rbx
0x180001c67  mov     [rsi+28h], r15d
0x180001c6b  jmp     loc_180001BBD
0x180001c70  mov     eax, 80070216h
0x180001c75  jmp     loc_180001BDD
0x180001c7a  call    cs:__imp_GetProcessHeap
0x180001c80  mov     r8, r13; dwBytes
0x180001c83  xor     edx, edx; dwFlags
0x180001c85  mov     rcx, rax; hHeap
0x180001c88  call    cs:__imp_HeapAlloc
0x180001c8e  jmp     short loc_180001C3C
0x180001c90  mov     ecx, 8; dwErrCode
0x180001c95  call    cs:__imp_SetLastError
0x180001c9b  call    cs:__imp_GetLastError
0x180001ca1  test    eax, eax
0x180001ca3  jle     loc_180001BDD
0x180001ca9  movzx   eax, ax
0x180001cac  or      eax, 80070000h
0x180001cb1  jmp     loc_180001BDD
0x180001cb6  mov     eax, 80070057h
0x180001cbb  jmp     loc_180001BF6
```
