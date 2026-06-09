# STRA::Copy(char const *,ulong)

- ea: `0x18000dc20`
- end: `0x18000dda2`
- name: `?Copy@STRA@@QEAAJPEBDK@Z`
- size: `386`
- prototype: `int(STRA *__hidden this, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001d00`
- `0x18001e0f0`
- `0x18001e1a0`
- `0x18001e330`
- `0x18001e3c0`

## callees

- `0x18000dc20`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dcc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dcc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd4b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000dcdd`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000dcdd`

## pseudocode

```c
int __fastcall STRA::Copy(void **this, const char *a2, unsigned int a3)
{
  size_t v3; // rbp
  unsigned __int64 v6; // rcx
  _BYTE *v7; // rax
  int result; // eax
  unsigned int v9; // r15d
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  void *v12; // rax
  void *v13; // rdi
  HANDLE v14; // rax

  v3 = a3;
  if ( !a2 && a3 )
    return -2147024809;
  v6 = *((unsigned int *)this + 10);
  if ( v6 >= (unsigned __int64)a3 + 1 )
    goto LABEL_3;
  v9 = a3 + 128;
  if ( (unsigned __int64)a3 + 128 > 0xFFFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  if ( v9 <= (unsigned int)v6 )
  {
LABEL_3:
    memcpy_0(this[4], a2, v3);
    v7 = this[4];
    *((_DWORD *)this + 12) = v3;
    v7[v3] = 0;
    return 0;
  }
  if ( *((_BYTE *)this + 44) )
  {
    v10 = this[4];
    ProcessHeap = GetProcessHeap();
    v12 = HeapReAlloc(ProcessHeap, 0, v10, v9);
  }
  else
  {
    v14 = GetProcessHeap();
    v12 = HeapAlloc(v14, 0, v9);
  }
  v13 = v12;
  if ( v12 )
  {
    if ( !*((_BYTE *)this + 44) )
    {
      memcpy_0(v12, this[4], *((unsigned int *)this + 10));
      *((_BYTE *)this + 44) = 1;
    }
    this[4] = v13;
    *((_DWORD *)this + 10) = v9;
    goto LABEL_3;
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
0x18000dc20  push    rbx
0x18000dc22  push    rbp
0x18000dc23  push    r14
0x18000dc25  sub     rsp, 30h
0x18000dc29  mov     ebp, r8d
0x18000dc2c  mov     r14, rdx
0x18000dc2f  mov     rbx, rcx
0x18000dc32  test    rdx, rdx
0x18000dc35  jz      loc_18000DD1D
0x18000dc3b  mov     ecx, [rcx+28h]
0x18000dc3e  lea     rax, [rbp+1]
0x18000dc42  mov     [rsp+48h+arg_0], rsi
0x18000dc47  mov     [rsp+48h+arg_8], rdi
0x18000dc4c  mov     [rsp+48h+arg_10], r12
0x18000dc51  mov     [rsp+48h+var_28], r15
0x18000dc56  cmp     rcx, rax
0x18000dc59  jb      short loc_18000DC96
0x18000dc5b  mov     rcx, [rbx+20h]; void *
0x18000dc5f  mov     r8, rbp; Size
0x18000dc62  mov     rdx, r14; Src
0x18000dc65  call    memcpy_0
0x18000dc6a  mov     rax, [rbx+20h]
0x18000dc6e  mov     [rbx+30h], ebp
0x18000dc71  mov     byte ptr [rbp+rax+0], 0
0x18000dc76  xor     eax, eax
0x18000dc78  mov     r15, [rsp+48h+var_28]
0x18000dc7d  mov     r12, [rsp+48h+arg_10]
0x18000dc82  mov     rdi, [rsp+48h+arg_8]
0x18000dc87  mov     rsi, [rsp+48h+arg_0]
0x18000dc8c  add     rsp, 30h
0x18000dc90  pop     r14
0x18000dc92  pop     rbp
0x18000dc93  pop     rbx
0x18000dc94  retn
0x18000dc96  lea     r15, [rbp+80h]
0x18000dc9d  mov     eax, 0FFFFFFFFh
0x18000dca2  cmp     r15, rax
0x18000dca5  ja      loc_18000DD35
0x18000dcab  cmp     r15d, ecx
0x18000dcae  jbe     short loc_18000DC5B
0x18000dcb0  cmp     byte ptr [rbx+2Ch], 0
0x18000dcb4  mov     [rsp+48h+var_20], r13
0x18000dcb9  mov     r13d, r15d
0x18000dcbc  jz      loc_18000DD4B
0x18000dcc2  mov     rdi, [rbx+20h]
0x18000dcc6  call    cs:__imp_GetProcessHeap
0x18000dccd  nop     dword ptr [rax+rax+00h]
0x18000dcd2  mov     r9d, r13d; dwBytes
0x18000dcd5  mov     r8, rdi; lpMem
0x18000dcd8  mov     rcx, rax; hHeap
0x18000dcdb  xor     edx, edx; dwFlags
0x18000dcdd  call    cs:__imp_HeapReAlloc
0x18000dce4  nop     dword ptr [rax+rax+00h]
0x18000dce9  mov     r13, [rsp+48h+var_20]
0x18000dcee  mov     rdi, rax
0x18000dcf1  test    rax, rax
0x18000dcf4  jz      short loc_18000DD70
0x18000dcf6  cmp     byte ptr [rbx+2Ch], 0
0x18000dcfa  jnz     short loc_18000DD10
0x18000dcfc  mov     r8d, [rbx+28h]; Size
0x18000dd00  mov     rcx, rax; void *
0x18000dd03  mov     rdx, [rbx+20h]; Src
0x18000dd07  call    memcpy_0
0x18000dd0c  mov     byte ptr [rbx+2Ch], 1
0x18000dd10  mov     [rbx+20h], rdi
0x18000dd14  mov     [rbx+28h], r15d
0x18000dd18  jmp     loc_18000DC5B
0x18000dd1d  test    r8d, r8d
0x18000dd20  jz      loc_18000DC3B
0x18000dd26  mov     eax, 80070057h
0x18000dd2b  add     rsp, 30h
0x18000dd2f  pop     r14
0x18000dd31  pop     rbp
0x18000dd32  pop     rbx
0x18000dd33  retn
0x18000dd35  mov     ecx, 216h; dwErrCode
0x18000dd3a  call    cs:__imp_SetLastError
0x18000dd41  nop     dword ptr [rax+rax+00h]
0x18000dd46  jmp     loc_18000DC76
0x18000dd4b  call    cs:__imp_GetProcessHeap
0x18000dd52  nop     dword ptr [rax+rax+00h]
0x18000dd57  mov     r8, r13; dwBytes
0x18000dd5a  xor     edx, edx; dwFlags
0x18000dd5c  mov     rcx, rax; hHeap
0x18000dd5f  call    cs:__imp_HeapAlloc
0x18000dd66  nop     dword ptr [rax+rax+00h]
0x18000dd6b  jmp     loc_18000DCE9
0x18000dd70  mov     ecx, 8; dwErrCode
0x18000dd75  call    cs:__imp_SetLastError
0x18000dd7c  nop     dword ptr [rax+rax+00h]
0x18000dd81  call    cs:__imp_GetLastError
0x18000dd88  nop     dword ptr [rax+rax+00h]
0x18000dd8d  test    eax, eax
0x18000dd8f  jle     loc_18000DC78
0x18000dd95  movzx   eax, ax
0x18000dd98  or      eax, 80070000h
0x18000dd9d  jmp     loc_18000DC78
```
