# STRU::Copy(ushort const *,ulong)

- ea: `0x18000e000`
- end: `0x18000e16d`
- name: `?Copy@STRU@@QEAAJPEBGK@Z`
- size: `365`
- prototype: `int(STRU *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d2b0`
- `0x18001d5a0`

## callees

- `0x18000e000`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e136`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e142`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e123`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e123`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e10f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e10f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000e0c5`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000e0c5`

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
0x18000e000  push    rbx
0x18000e002  push    rsi
0x18000e003  sub     rsp, 38h
0x18000e007  mov     rsi, rdx
0x18000e00a  mov     rbx, rcx
0x18000e00d  test    rdx, rdx
0x18000e010  jz      loc_18000E163
0x18000e016  mov     ecx, [rcx+28h]
0x18000e019  mov     [rsp+48h+arg_0], rbp
0x18000e01e  mov     [rsp+48h+var_20], r14
0x18000e023  lea     r14d, [r8+r8]
0x18000e027  mov     [rsp+48h+arg_8], rdi
0x18000e02c  lea     rax, [r14+2]
0x18000e030  mov     [rsp+48h+arg_10], r12
0x18000e035  mov     [rsp+48h+var_28], r15
0x18000e03a  mov     ebp, r14d
0x18000e03d  cmp     rcx, rax
0x18000e040  jb      short loc_18000E086
0x18000e042  mov     rcx, [rbx+20h]; void *
0x18000e046  mov     r8, rbp; Size
0x18000e049  mov     rdx, rsi; Src
0x18000e04c  call    memcpy_0
0x18000e051  mov     rcx, [rbx+20h]
0x18000e055  shr     r14d, 1
0x18000e058  mov     edx, r14d
0x18000e05b  xor     eax, eax
0x18000e05d  mov     [rbx+30h], edx
0x18000e060  mov     [rcx+r14*2], ax
0x18000e065  mov     r15, [rsp+48h+var_28]
0x18000e06a  mov     r14, [rsp+48h+var_20]
0x18000e06f  mov     r12, [rsp+48h+arg_10]
0x18000e074  mov     rdi, [rsp+48h+arg_8]
0x18000e079  mov     rbp, [rsp+48h+arg_0]
0x18000e07e  add     rsp, 38h
0x18000e082  pop     rsi
0x18000e083  pop     rbx
0x18000e084  retn
0x18000e086  lea     r15, [r14+80h]
0x18000e08d  mov     eax, 0FFFFFFFFh
0x18000e092  cmp     r15, rax
0x18000e095  ja      short loc_18000E105
0x18000e097  cmp     r15d, ecx
0x18000e09a  jbe     short loc_18000E042
0x18000e09c  cmp     byte ptr [rbx+2Ch], 0
0x18000e0a0  mov     [rsp+48h+var_18], r13
0x18000e0a5  mov     r13d, r15d
0x18000e0a8  jz      short loc_18000E10F
0x18000e0aa  mov     rdi, [rbx+20h]
0x18000e0ae  call    cs:__imp_GetProcessHeap
0x18000e0b5  nop     dword ptr [rax+rax+00h]
0x18000e0ba  mov     r9d, r13d; dwBytes
0x18000e0bd  mov     r8, rdi; lpMem
0x18000e0c0  mov     rcx, rax; hHeap
0x18000e0c3  xor     edx, edx; dwFlags
0x18000e0c5  call    cs:__imp_HeapReAlloc
0x18000e0cc  nop     dword ptr [rax+rax+00h]
0x18000e0d1  mov     r13, [rsp+48h+var_18]
0x18000e0d6  mov     rdi, rax
0x18000e0d9  test    rax, rax
0x18000e0dc  jz      short loc_18000E131
0x18000e0de  cmp     byte ptr [rbx+2Ch], 0
0x18000e0e2  jnz     short loc_18000E0F8
0x18000e0e4  mov     r8d, [rbx+28h]; Size
0x18000e0e8  mov     rcx, rax; void *
0x18000e0eb  mov     rdx, [rbx+20h]; Src
0x18000e0ef  call    memcpy_0
0x18000e0f4  mov     byte ptr [rbx+2Ch], 1
0x18000e0f8  mov     [rbx+20h], rdi
0x18000e0fc  mov     [rbx+28h], r15d
0x18000e100  jmp     loc_18000E042
0x18000e105  mov     eax, 80070216h
0x18000e10a  jmp     loc_18000E065
0x18000e10f  call    cs:__imp_GetProcessHeap
0x18000e116  nop     dword ptr [rax+rax+00h]
0x18000e11b  mov     r8, r13; dwBytes
0x18000e11e  xor     edx, edx; dwFlags
0x18000e120  mov     rcx, rax; hHeap
0x18000e123  call    cs:__imp_HeapAlloc
0x18000e12a  nop     dword ptr [rax+rax+00h]
0x18000e12f  jmp     short loc_18000E0D1
0x18000e131  mov     ecx, 8; dwErrCode
0x18000e136  call    cs:__imp_SetLastError
0x18000e13d  nop     dword ptr [rax+rax+00h]
0x18000e142  call    cs:__imp_GetLastError
0x18000e149  nop     dword ptr [rax+rax+00h]
0x18000e14e  test    eax, eax
0x18000e150  jle     loc_18000E065
0x18000e156  movzx   eax, ax
0x18000e159  or      eax, 80070000h
0x18000e15e  jmp     loc_18000E065
0x18000e163  mov     eax, 80070057h
0x18000e168  jmp     loc_18000E07E
```
