# GetStringFromBSTR(ushort *,char * *,ulong *,int)

- ea: `0x18000c55c`
- end: `0x18000c5e6`
- name: `?GetStringFromBSTR@@YAJPEAGPEAPEADPEAKH@Z`
- size: `138`
- prototype: `__int64 __fastcall(OLECHAR *lpWideCharStr, char **, unsigned int *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000c5ec`
- `0x18000d81c`

## callees

- `0x18000c55c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000c595`
- `KERNEL32!LocalAlloc` at `0x18000c595`
- `KERNEL32!WideCharToMultiByte` at `0x18000c5d0`
- `KERNEL32!WideCharToMultiByte` at `0x18000c5d0`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c573`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c573`

## pseudocode

```c
__int64 __fastcall GetStringFromBSTR(OLECHAR *lpWideCharStr, char **a2, unsigned int *a3, int a4)
{
  UINT v8; // esi
  CHAR *lpMultiByteStr; // rax
  char *v10; // rbx
  __int64 result; // rax

  v8 = SysStringLen(lpWideCharStr);
  *a3 = v8 + (a4 != 0);
  lpMultiByteStr = (CHAR *)LocalAlloc(0, 2 * v8 + 1);
  v10 = lpMultiByteStr;
  if ( !lpMultiByteStr )
    return 2147942414LL;
  WideCharToMultiByte(0, 0, lpWideCharStr, v8 + 1, lpMultiByteStr, 2 * v8 + 1, 0, 0);
  result = 0;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x18000c55c  push    rbx
0x18000c55e  push    rbp
0x18000c55f  push    rsi
0x18000c560  push    rdi
0x18000c561  push    r14
0x18000c563  sub     rsp, 40h
0x18000c567  mov     ebx, r9d
0x18000c56a  mov     rdi, r8
0x18000c56d  mov     r14, rdx
0x18000c570  mov     rbp, rcx
0x18000c573  call    cs:__imp_SysStringLen
0x18000c579  xor     r10d, r10d
0x18000c57c  mov     esi, eax
0x18000c57e  test    ebx, ebx
0x18000c580  setnz   r10b
0x18000c584  xor     ecx, ecx; uFlags
0x18000c586  add     r10d, eax
0x18000c589  mov     [rdi], r10d
0x18000c58c  lea     edi, ds:1[rax*2]
0x18000c593  mov     edx, edi; uBytes
0x18000c595  call    cs:__imp_LocalAlloc
0x18000c59b  mov     rbx, rax
0x18000c59e  test    rax, rax
0x18000c5a1  jnz     short loc_18000C5AA
0x18000c5a3  mov     eax, 8007000Eh
0x18000c5a8  jmp     short loc_18000C5DB
0x18000c5aa  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000c5b3  lea     r9d, [rsi+1]; cchWideChar
0x18000c5b7  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18000c5c0  mov     r8, rbp; lpWideCharStr
0x18000c5c3  mov     [rsp+68h+cbMultiByte], edi; cbMultiByte
0x18000c5c7  xor     edx, edx; dwFlags
0x18000c5c9  xor     ecx, ecx; CodePage
0x18000c5cb  mov     [rsp+68h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000c5d0  call    cs:__imp_WideCharToMultiByte
0x18000c5d6  xor     eax, eax
0x18000c5d8  mov     [r14], rbx
0x18000c5db  add     rsp, 40h
0x18000c5df  pop     r14
0x18000c5e1  pop     rdi
0x18000c5e2  pop     rsi
0x18000c5e3  pop     rbp
0x18000c5e4  pop     rbx
0x18000c5e5  retn
```
