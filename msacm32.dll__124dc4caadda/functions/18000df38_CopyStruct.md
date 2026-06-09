# CopyStruct

- ea: `0x18000df38`
- end: `0x18000dff2`
- name: `CopyStruct`
- size: `186`
- prototype: `__int64 __fastcall(LPCVOID pMem, void *Src)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800074d0`
- `0x18000e520`
- `0x18000ef10`
- `0x180010cd0`

## callees

- `0x18000df38`
- `0x1800126b9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000dfb6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000dfb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000df83`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000df95`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000df83`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000df95`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000df8c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000df8c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000dfa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000dfa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000dfbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000dfbf`

## pseudocode

```c
void *__fastcall CopyStruct(LPCVOID pMem, unsigned __int16 *Src, int a3)
{
  unsigned int v5; // eax
  size_t v6; // rsi
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  HGLOBAL v9; // rax
  void *v10; // rax
  void *v11; // rdi

  if ( !Src )
    return 0;
  v5 = 0;
  if ( a3 )
  {
    if ( a3 == 1 )
    {
      if ( *Src == 1 )
        v5 = 16;
      else
        v5 = Src[8] + 18;
    }
  }
  else
  {
    v5 = *(_DWORD *)Src;
  }
  v6 = v5;
  if ( pMem )
  {
    v7 = GlobalHandle(pMem);
    GlobalUnlock(v7);
    v8 = GlobalHandle(pMem);
    v9 = GlobalReAlloc(v8, (unsigned int)v6, 0x42u);
  }
  else
  {
    v9 = GlobalAlloc(0x42u, v5);
  }
  v10 = GlobalLock(v9);
  v11 = v10;
  if ( !v10 )
    return 0;
  memcpy_0(v10, Src, v6);
  return v11;
}

```

## disassembly

```asm
0x18000df38  mov     [rsp+arg_0], rbx
0x18000df3d  mov     [rsp+arg_8], rsi
0x18000df42  push    rdi
0x18000df43  sub     rsp, 20h
0x18000df47  mov     rbx, rdx
0x18000df4a  mov     rdi, rcx
0x18000df4d  test    rdx, rdx
0x18000df50  jz      loc_18000DFE0
0x18000df56  xor     eax, eax
0x18000df58  test    r8d, r8d
0x18000df5b  jz      short loc_18000DF7A
0x18000df5d  cmp     r8d, 1
0x18000df61  jnz     short loc_18000DF7C
0x18000df63  mov     eax, r8d
0x18000df66  cmp     ax, [rdx]
0x18000df69  jnz     short loc_18000DF71
0x18000df6b  lea     eax, [r8+0Fh]
0x18000df6f  jmp     short loc_18000DF7C
0x18000df71  movzx   eax, word ptr [rdx+10h]
0x18000df75  add     eax, 12h
0x18000df78  jmp     short loc_18000DF7C
0x18000df7a  mov     eax, [rdx]
0x18000df7c  mov     esi, eax
0x18000df7e  test    rdi, rdi
0x18000df81  jz      short loc_18000DFAE
0x18000df83  call    cs:__imp_GlobalHandle
0x18000df89  mov     rcx, rax; hMem
0x18000df8c  call    cs:__imp_GlobalUnlock
0x18000df92  mov     rcx, rdi; pMem
0x18000df95  call    cs:__imp_GlobalHandle
0x18000df9b  mov     r8d, 42h ; 'B'; uFlags
0x18000dfa1  mov     edx, esi; dwBytes
0x18000dfa3  mov     rcx, rax; hMem
0x18000dfa6  call    cs:__imp_GlobalReAlloc
0x18000dfac  jmp     short loc_18000DFBC
0x18000dfae  mov     rdx, rsi; dwBytes
0x18000dfb1  mov     ecx, 42h ; 'B'; uFlags
0x18000dfb6  call    cs:__imp_GlobalAlloc
0x18000dfbc  mov     rcx, rax; hMem
0x18000dfbf  call    cs:__imp_GlobalLock
0x18000dfc5  mov     rdi, rax
0x18000dfc8  test    rax, rax
0x18000dfcb  jz      short loc_18000DFE0
0x18000dfcd  mov     r8, rsi; Size
0x18000dfd0  mov     rdx, rbx; Src
0x18000dfd3  mov     rcx, rax; void *
0x18000dfd6  call    memcpy_0
0x18000dfdb  mov     rax, rdi
0x18000dfde  jmp     short loc_18000DFE2
0x18000dfe0  xor     eax, eax
0x18000dfe2  mov     rbx, [rsp+28h+arg_0]
0x18000dfe7  mov     rsi, [rsp+28h+arg_8]
0x18000dfec  add     rsp, 20h
0x18000dff0  pop     rdi
0x18000dff1  retn
```
