# pStrBufGrow

- ea: `0x1800082fc`
- end: `0x18000841e`
- name: `pStrBufGrow`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008128`
- `0x18000828c`

## callees

- `0x1800082fc`
- `0x18000a16e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008351`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008402`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008351`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008402`
- `KERNEL32!HeapFree` at `0x1800083d9`
- `KERNEL32!HeapFree` at `0x180008414`
- `KERNEL32!HeapFree` at `0x1800083d9`
- `KERNEL32!HeapFree` at `0x180008414`
- `KERNEL32!HeapAlloc` at `0x18000833e`
- `KERNEL32!HeapAlloc` at `0x18000833e`

## pseudocode

```c
__int64 __fastcall pStrBufGrow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v5; // ebp
  __int64 v6; // rdi
  _BYTE *v7; // rax
  _BYTE *v8; // rsi
  _BYTE *v9; // rax
  unsigned int v10; // ecx
  __int64 v11; // rcx
  _BYTE *v12; // rdx
  _BYTE *v13; // rax

  v2 = 1;
  v3 = 1;
  if ( a2 )
    v3 = a2;
  if ( *(_DWORD *)a1 < v3 )
  {
    v5 = ((v3 + 1023) & 0xFFFFFC00) + 1024;
    v6 = v5;
    v7 = HeapAlloc(hHeap, 0, v5);
    v8 = v7;
    if ( !v7 )
    {
      v2 = 0;
      SetLastError(8u);
      return v2;
    }
    memset_0(v7, 0, v5);
    v9 = *(_BYTE **)(a1 + 8);
    if ( v9 )
    {
      if ( !v5 )
      {
        LOWORD(v10) = 87;
        goto LABEL_21;
      }
      if ( v5 > 0x7FFFFFFFuLL )
      {
        LOWORD(v10) = 87;
        *v8 = 0;
LABEL_21:
        SetLastError((unsigned __int16)v10);
        HeapFree(hHeap, 0, v8);
        return 0;
      }
      v11 = 2147483646;
      v12 = v8;
      do
      {
        if ( !v11 )
          break;
        if ( !*v9 )
          break;
        *v12++ = *v9++;
        --v11;
        --v6;
      }
      while ( v6 );
      v13 = v12 - 1;
      v10 = v6 == 0 ? 0x8007007A : 0;
      if ( v6 )
        v13 = v12;
      *v13 = 0;
      if ( !v6 )
        goto LABEL_21;
      HeapFree(hHeap, 0, *(LPVOID *)(a1 + 8));
    }
    *(_QWORD *)(a1 + 8) = v8;
    *(_DWORD *)a1 = v5;
  }
  return v2;
}

```

## disassembly

```asm
0x1800082fc  push    rbx
0x1800082fe  push    rbp
0x1800082ff  push    rsi
0x180008300  push    rdi
0x180008301  push    r14
0x180008303  sub     rsp, 20h
0x180008307  test    edx, edx
0x180008309  mov     ebx, 1
0x18000830e  mov     eax, ebx
0x180008310  mov     r14, rcx
0x180008313  cmovnz  eax, edx
0x180008316  cmp     [rcx], eax
0x180008318  jnb     loc_1800083E6
0x18000831e  mov     rcx, cs:hHeap; hHeap
0x180008325  lea     ebp, [rax+3FFh]
0x18000832b  and     ebp, 0FFFFFC00h
0x180008331  xor     edx, edx; dwFlags
0x180008333  add     ebp, 400h
0x180008339  mov     r8d, ebp; dwBytes
0x18000833c  mov     edi, ebp
0x18000833e  call    cs:__imp_HeapAlloc
0x180008344  mov     rsi, rax
0x180008347  test    rax, rax
0x18000834a  jnz     short loc_18000835C
0x18000834c  xor     ebx, ebx
0x18000834e  lea     ecx, [rax+8]; dwErrCode
0x180008351  call    cs:__imp_SetLastError
0x180008357  jmp     loc_1800083E6
0x18000835c  mov     r8, rdi; Size
0x18000835f  xor     edx, edx; Val
0x180008361  mov     rcx, rsi; void *
0x180008364  call    memset_0
0x180008369  mov     rax, [r14+8]
0x18000836d  test    rax, rax
0x180008370  jz      short loc_1800083DF
0x180008372  test    ebp, ebp
0x180008374  jz      short loc_1800083F3
0x180008376  cmp     rdi, 7FFFFFFFh
0x18000837d  jbe     short loc_180008386
0x18000837f  mov     ecx, 80070057h
0x180008384  jmp     short loc_1800083FC
0x180008386  mov     ecx, 7FFFFFFEh
0x18000838b  mov     rdx, rsi
0x18000838e  test    rcx, rcx
0x180008391  jz      short loc_1800083AC
0x180008393  mov     r8b, [rax]
0x180008396  test    r8b, r8b
0x180008399  jz      short loc_1800083AC
0x18000839b  mov     [rdx], r8b
0x18000839e  add     rax, rbx
0x1800083a1  add     rdx, rbx
0x1800083a4  sub     rcx, rbx
0x1800083a7  sub     rdi, rbx
0x1800083aa  jnz     short loc_18000838E
0x1800083ac  mov     rax, rdi
0x1800083af  neg     rax
0x1800083b2  lea     rax, [rdx-1]
0x1800083b6  sbb     ecx, ecx
0x1800083b8  not     ecx
0x1800083ba  and     ecx, 8007007Ah
0x1800083c0  test    rdi, rdi
0x1800083c3  cmovnz  rax, rdx
0x1800083c7  mov     byte ptr [rax], 0
0x1800083ca  jz      short loc_1800083FF
0x1800083cc  mov     r8, [r14+8]; lpMem
0x1800083d0  xor     edx, edx; dwFlags
0x1800083d2  mov     rcx, cs:hHeap; hHeap
0x1800083d9  call    cs:__imp_HeapFree
0x1800083df  mov     [r14+8], rsi
0x1800083e3  mov     [r14], ebp
0x1800083e6  mov     eax, ebx
0x1800083e8  add     rsp, 20h
0x1800083ec  pop     r14
0x1800083ee  pop     rdi
0x1800083ef  pop     rsi
0x1800083f0  pop     rbp
0x1800083f1  pop     rbx
0x1800083f2  retn
0x1800083f3  mov     ecx, 80070057h
0x1800083f8  test    ebp, ebp
0x1800083fa  jz      short loc_1800083FF
0x1800083fc  mov     byte ptr [rsi], 0
0x1800083ff  movzx   ecx, cx; dwErrCode
0x180008402  call    cs:__imp_SetLastError
0x180008408  mov     rcx, cs:hHeap; hHeap
0x18000840f  mov     r8, rsi; lpMem
0x180008412  xor     edx, edx; dwFlags
0x180008414  call    cs:__imp_HeapFree
0x18000841a  xor     ebx, ebx
0x18000841c  jmp     short loc_1800083E6
```
