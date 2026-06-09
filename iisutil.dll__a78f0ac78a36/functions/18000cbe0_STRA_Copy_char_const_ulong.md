# STRA::Copy(char const *,ulong)

- ea: `0x18000cbe0`
- end: `0x18000cd2b`
- name: `?Copy@STRA@@QEAAJPEBDK@Z`
- size: `331`
- prototype: `int(STRA *__hidden this, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001610`
- `0x18001d050`
- `0x18001d0e0`
- `0x18001d270`
- `0x18001d2f0`

## callees

- `0x18000cbe0`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cce4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cce4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ccfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ccfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccef`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cc8e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cc8e`

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
0x18000cbe0  push    rbx
0x18000cbe2  push    rbp
0x18000cbe3  push    r14
0x18000cbe5  sub     rsp, 30h
0x18000cbe9  mov     ebp, r8d
0x18000cbec  mov     r14, rdx
0x18000cbef  mov     rbx, rcx
0x18000cbf2  test    rdx, rdx
0x18000cbf5  jz      loc_18000CCC8
0x18000cbfb  mov     ecx, [rcx+28h]
0x18000cbfe  lea     rax, [rbp+1]
0x18000cc02  mov     [rsp+48h+arg_0], rsi
0x18000cc07  mov     [rsp+48h+arg_8], rdi
0x18000cc0c  mov     [rsp+48h+arg_10], r12
0x18000cc11  mov     [rsp+48h+var_28], r15
0x18000cc16  cmp     rcx, rax
0x18000cc19  jb      short loc_18000CC55
0x18000cc1b  mov     rcx, [rbx+20h]; void *
0x18000cc1f  mov     r8, rbp; Size
0x18000cc22  mov     rdx, r14; Src
0x18000cc25  call    memcpy_0
0x18000cc2a  mov     rax, [rbx+20h]
0x18000cc2e  mov     [rbx+30h], ebp
0x18000cc31  mov     byte ptr [rbp+rax+0], 0
0x18000cc36  xor     eax, eax
0x18000cc38  mov     r15, [rsp+48h+var_28]
0x18000cc3d  mov     r12, [rsp+48h+arg_10]
0x18000cc42  mov     rdi, [rsp+48h+arg_8]
0x18000cc47  mov     rsi, [rsp+48h+arg_0]
0x18000cc4c  add     rsp, 30h
0x18000cc50  pop     r14
0x18000cc52  pop     rbp
0x18000cc53  pop     rbx
0x18000cc54  retn
0x18000cc55  lea     r15, [rbp+80h]
0x18000cc5c  mov     eax, 0FFFFFFFFh
0x18000cc61  cmp     r15, rax
0x18000cc64  ja      short loc_18000CCDF
0x18000cc66  cmp     r15d, ecx
0x18000cc69  jbe     short loc_18000CC1B
0x18000cc6b  cmp     byte ptr [rbx+2Ch], 0
0x18000cc6f  mov     [rsp+48h+var_20], r13
0x18000cc74  mov     r13d, r15d
0x18000cc77  jz      short loc_18000CCEF
0x18000cc79  mov     rdi, [rbx+20h]
0x18000cc7d  call    cs:__imp_GetProcessHeap
0x18000cc83  mov     r9d, r13d; dwBytes
0x18000cc86  mov     r8, rdi; lpMem
0x18000cc89  mov     rcx, rax; hHeap
0x18000cc8c  xor     edx, edx; dwFlags
0x18000cc8e  call    cs:__imp_HeapReAlloc
0x18000cc94  mov     r13, [rsp+48h+var_20]
0x18000cc99  mov     rdi, rax
0x18000cc9c  test    rax, rax
0x18000cc9f  jz      short loc_18000CD05
0x18000cca1  cmp     byte ptr [rbx+2Ch], 0
0x18000cca5  jnz     short loc_18000CCBB
0x18000cca7  mov     r8d, [rbx+28h]; Size
0x18000ccab  mov     rcx, rax; void *
0x18000ccae  mov     rdx, [rbx+20h]; Src
0x18000ccb2  call    memcpy_0
0x18000ccb7  mov     byte ptr [rbx+2Ch], 1
0x18000ccbb  mov     [rbx+20h], rdi
0x18000ccbf  mov     [rbx+28h], r15d
0x18000ccc3  jmp     loc_18000CC1B
0x18000ccc8  test    r8d, r8d
0x18000cccb  jz      loc_18000CBFB
0x18000ccd1  mov     eax, 80070057h
0x18000ccd6  add     rsp, 30h
0x18000ccda  pop     r14
0x18000ccdc  pop     rbp
0x18000ccdd  pop     rbx
0x18000ccde  retn
0x18000ccdf  mov     ecx, 216h; dwErrCode
0x18000cce4  call    cs:__imp_SetLastError
0x18000ccea  jmp     loc_18000CC36
0x18000ccef  call    cs:__imp_GetProcessHeap
0x18000ccf5  mov     r8, r13; dwBytes
0x18000ccf8  xor     edx, edx; dwFlags
0x18000ccfa  mov     rcx, rax; hHeap
0x18000ccfd  call    cs:__imp_HeapAlloc
0x18000cd03  jmp     short loc_18000CC94
0x18000cd05  mov     ecx, 8; dwErrCode
0x18000cd0a  call    cs:__imp_SetLastError
0x18000cd10  call    cs:__imp_GetLastError
0x18000cd16  test    eax, eax
0x18000cd18  jle     loc_18000CC38
0x18000cd1e  movzx   eax, ax
0x18000cd21  or      eax, 80070000h
0x18000cd26  jmp     loc_18000CC38
```
