# STRU::Copy(ushort const *,ulong)

- ea: `0x18000cf40`
- end: `0x18000d088`
- name: `?Copy@STRU@@QEAAJPEBGK@Z`
- size: `328`
- prototype: `int(STRU *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001c2d0`
- `0x18001c5a0`

## callees

- `0x18000cf40`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d05d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d063`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d050`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d042`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cffe`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cffe`

## pseudocode

```c
int __fastcall STRU::Copy(STRU *this, const unsigned __int16 *a2, int a3)
{
  unsigned __int64 v5; // rcx
  size_t v6; // r14
  __int64 v7; // rcx
  __int64 v8; // r14
  int result; // eax
  unsigned int v10; // r15d
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax

  if ( !a2 )
    return -2147024809;
  v5 = *((unsigned int *)this + 10);
  v6 = (unsigned int)(2 * a3);
  if ( v5 >= v6 + 2 )
    goto LABEL_3;
  v10 = v6 + 128;
  if ( v6 + 128 > 0xFFFFFFFF )
    return -2147024362;
  if ( v10 <= (unsigned int)v5 )
    goto LABEL_3;
  if ( *((_BYTE *)this + 44) )
  {
    v11 = (void *)*((_QWORD *)this + 4);
    ProcessHeap = GetProcessHeap();
    v13 = HeapReAlloc(ProcessHeap, 0, v11, v10);
  }
  else
  {
    v15 = GetProcessHeap();
    v13 = HeapAlloc(v15, 0, v10);
  }
  v14 = v13;
  if ( v13 )
  {
    if ( !*((_BYTE *)this + 44) )
    {
      memcpy_0(v13, *((const void **)this + 4), *((unsigned int *)this + 10));
      *((_BYTE *)this + 44) = 1;
    }
    *((_QWORD *)this + 4) = v14;
    *((_DWORD *)this + 10) = v10;
LABEL_3:
    memcpy_0(*((void **)this + 4), a2, v6);
    v7 = *((_QWORD *)this + 4);
    v8 = (unsigned int)v6 >> 1;
    result = 0;
    *((_DWORD *)this + 12) = v8;
    *(_WORD *)(v7 + 2 * v8) = 0;
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
0x18000cf40  push    rbx
0x18000cf42  push    rsi
0x18000cf43  sub     rsp, 38h
0x18000cf47  mov     rsi, rdx
0x18000cf4a  mov     rbx, rcx
0x18000cf4d  test    rdx, rdx
0x18000cf50  jz      loc_18000D07E
0x18000cf56  mov     ecx, [rcx+28h]
0x18000cf59  mov     [rsp+48h+arg_0], rbp
0x18000cf5e  mov     [rsp+48h+var_20], r14
0x18000cf63  lea     r14d, [r8+r8]
0x18000cf67  mov     [rsp+48h+arg_8], rdi
0x18000cf6c  lea     rax, [r14+2]
0x18000cf70  mov     [rsp+48h+arg_10], r12
0x18000cf75  mov     [rsp+48h+var_28], r15
0x18000cf7a  mov     ebp, r14d
0x18000cf7d  cmp     rcx, rax
0x18000cf80  jb      short loc_18000CFC5
0x18000cf82  mov     rcx, [rbx+20h]; void *
0x18000cf86  mov     r8, rbp; Size
0x18000cf89  mov     rdx, rsi; Src
0x18000cf8c  call    memcpy_0
0x18000cf91  mov     rcx, [rbx+20h]
0x18000cf95  shr     r14d, 1
0x18000cf98  mov     edx, r14d
0x18000cf9b  xor     eax, eax
0x18000cf9d  mov     [rbx+30h], edx
0x18000cfa0  mov     [rcx+r14*2], ax
0x18000cfa5  mov     r15, [rsp+48h+var_28]
0x18000cfaa  mov     r14, [rsp+48h+var_20]
0x18000cfaf  mov     r12, [rsp+48h+arg_10]
0x18000cfb4  mov     rdi, [rsp+48h+arg_8]
0x18000cfb9  mov     rbp, [rsp+48h+arg_0]
0x18000cfbe  add     rsp, 38h
0x18000cfc2  pop     rsi
0x18000cfc3  pop     rbx
0x18000cfc4  retn
0x18000cfc5  lea     r15, [r14+80h]
0x18000cfcc  mov     eax, 0FFFFFFFFh
0x18000cfd1  cmp     r15, rax
0x18000cfd4  ja      short loc_18000D038
0x18000cfd6  cmp     r15d, ecx
0x18000cfd9  jbe     short loc_18000CF82
0x18000cfdb  cmp     byte ptr [rbx+2Ch], 0
0x18000cfdf  mov     [rsp+48h+var_18], r13
0x18000cfe4  mov     r13d, r15d
0x18000cfe7  jz      short loc_18000D042
0x18000cfe9  mov     rdi, [rbx+20h]
0x18000cfed  call    cs:__imp_GetProcessHeap
0x18000cff3  mov     r9d, r13d; dwBytes
0x18000cff6  mov     r8, rdi; lpMem
0x18000cff9  mov     rcx, rax; hHeap
0x18000cffc  xor     edx, edx; dwFlags
0x18000cffe  call    cs:__imp_HeapReAlloc
0x18000d004  mov     r13, [rsp+48h+var_18]
0x18000d009  mov     rdi, rax
0x18000d00c  test    rax, rax
0x18000d00f  jz      short loc_18000D058
0x18000d011  cmp     byte ptr [rbx+2Ch], 0
0x18000d015  jnz     short loc_18000D02B
0x18000d017  mov     r8d, [rbx+28h]; Size
0x18000d01b  mov     rcx, rax; void *
0x18000d01e  mov     rdx, [rbx+20h]; Src
0x18000d022  call    memcpy_0
0x18000d027  mov     byte ptr [rbx+2Ch], 1
0x18000d02b  mov     [rbx+20h], rdi
0x18000d02f  mov     [rbx+28h], r15d
0x18000d033  jmp     loc_18000CF82
0x18000d038  mov     eax, 80070216h
0x18000d03d  jmp     loc_18000CFA5
0x18000d042  call    cs:__imp_GetProcessHeap
0x18000d048  mov     r8, r13; dwBytes
0x18000d04b  xor     edx, edx; dwFlags
0x18000d04d  mov     rcx, rax; hHeap
0x18000d050  call    cs:__imp_HeapAlloc
0x18000d056  jmp     short loc_18000D004
0x18000d058  mov     ecx, 8; dwErrCode
0x18000d05d  call    cs:__imp_SetLastError
0x18000d063  call    cs:__imp_GetLastError
0x18000d069  test    eax, eax
0x18000d06b  jle     loc_18000CFA5
0x18000d071  movzx   eax, ax
0x18000d074  or      eax, 80070000h
0x18000d079  jmp     loc_18000CFA5
0x18000d07e  mov     eax, 80070057h
0x18000d083  jmp     loc_18000CFBE
```
