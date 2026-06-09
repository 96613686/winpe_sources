# InsertVarDataString

- ea: `0x180003980`
- end: `0x1800039f2`
- name: `InsertVarDataString`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003488`
- `0x180004fe0`
- `0x180005550`

## callees

- `0x180003980`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800039c7`
- `KERNEL32!MultiByteToWideChar` at `0x1800039c7`

## pseudocode

```c
__int64 __fastcall InsertVarDataString(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v4; // ebx
  __int64 v7; // r10
  __int64 result; // rax
  int cchWideChar; // [rsp+28h] [rbp-10h]

  v4 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 )
  {
    v7 = *(unsigned int *)(a2 + 4);
    cchWideChar = *(_DWORD *)a2;
    *(_BYTE *)((unsigned int)(v4 + v7 - 1) + a1) = 0;
    MultiByteToWideChar(0, 1u, (LPCCH)(a1 + v7), v4, (LPWSTR)(a3 + *(unsigned int *)(a3 + 8)), cchWideChar);
    *a4 = 2 * v4;
    result = *(unsigned int *)(a3 + 8);
    a4[1] = result;
    *(_DWORD *)(a3 + 8) += 2 * v4;
  }
  return result;
}

```

## disassembly

```asm
0x180003980  mov     [rsp+arg_0], rbx
0x180003985  mov     [rsp+arg_8], rsi
0x18000398a  push    rdi
0x18000398b  sub     rsp, 30h
0x18000398f  mov     ebx, [rdx]
0x180003991  mov     rsi, r9
0x180003994  mov     rdi, r8
0x180003997  test    ebx, ebx
0x180003999  jz      short loc_1800039E1
0x18000399b  mov     r10d, [rdx+4]
0x18000399f  mov     r9d, ebx; cbMultiByte
0x1800039a2  mov     [rsp+38h+cchWideChar], ebx; cchWideChar
0x1800039a6  mov     edx, 1; dwFlags
0x1800039ab  lea     eax, [r10-1]
0x1800039af  add     eax, ebx
0x1800039b1  mov     byte ptr [rax+rcx], 0
0x1800039b5  mov     eax, [r8+8]
0x1800039b9  add     rax, r8
0x1800039bc  lea     r8, [rcx+r10]; lpMultiByteStr
0x1800039c0  xor     ecx, ecx; CodePage
0x1800039c2  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x1800039c7  call    cs:__imp_MultiByteToWideChar
0x1800039ce  nop     dword ptr [rax+rax+00h]
0x1800039d3  lea     ecx, [rbx+rbx]
0x1800039d6  mov     [rsi], ecx
0x1800039d8  mov     eax, [rdi+8]
0x1800039db  mov     [rsi+4], eax
0x1800039de  add     [rdi+8], ecx
0x1800039e1  mov     rbx, [rsp+38h+arg_0]
0x1800039e6  mov     rsi, [rsp+38h+arg_8]
0x1800039eb  add     rsp, 30h
0x1800039ef  pop     rdi
0x1800039f0  retn
```
