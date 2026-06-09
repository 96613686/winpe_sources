# _StringResourceStringCoAllocCopy

- ea: `0x180005380`
- end: `0x180005423`
- name: `_StringResourceStringCoAllocCopy`
- size: `163`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800028b8`
- `0x180003be0`
- `0x180003e40`
- `0x180003fa0`
- `0x1800040f0`

## callees

- `0x180005380`
- `0x180008ab0`
- `0x18000b0c2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800053db`
- `ole32!CoTaskMemAlloc` at `0x1800053db`

## pseudocode

```c
__int64 __fastcall StringResourceStringCoAllocCopy(__int64 a1, _QWORD *a2)
{
  const void *v3; // rbp
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // edi
  void *v9; // rax
  size_t v10; // rbx
  unsigned int v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v3 = (const void *)PszLoadStringPcch(a1, (unsigned int)a1, &v12);
  if ( v3 && (v4 = (int)v12, v12) )
  {
    v5 = v12 + 1;
    if ( (unsigned int)v5 < v12 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v6 = 2 * v5;
      v7 = v6;
      if ( v6 > 0xFFFFFFFF )
        v7 = -1;
      v8 = v6 > 0xFFFFFFFF ? 0x80070216 : 0;
      if ( v6 <= 0xFFFFFFFF )
      {
        v9 = CoTaskMemAlloc(v7);
        *a2 = v9;
        if ( v9 )
        {
          v10 = 2 * v4;
          memcpy_0(v9, v3, v10);
          *(_WORD *)(v10 + *a2) = 0;
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x180005380  push    rbx
0x180005382  push    rbp
0x180005383  push    rsi
0x180005384  push    rdi
0x180005385  sub     rsp, 28h
0x180005389  mov     rsi, rdx
0x18000538c  mov     [rsp+48h+arg_10], 0
0x180005394  mov     edx, ecx
0x180005396  lea     r8, [rsp+48h+arg_10]
0x18000539b  call    PszLoadStringPcch
0x1800053a0  mov     rbp, rax
0x1800053a3  test    rax, rax
0x1800053a6  jz      short loc_180005413
0x1800053a8  movsxd  rbx, [rsp+48h+arg_10]
0x1800053ad  test    ebx, ebx
0x1800053af  jz      short loc_180005413
0x1800053b1  lea     ecx, [rbx+1]
0x1800053b4  cmp     ecx, ebx
0x1800053b6  jb      short loc_18000540C
0x1800053b8  add     rcx, rcx
0x1800053bb  mov     edx, 0FFFFFFFFh
0x1800053c0  mov     eax, ecx
0x1800053c2  cmp     rcx, rdx
0x1800053c5  jbe     short loc_1800053C9
0x1800053c7  mov     eax, edx
0x1800053c9  cmp     rdx, rcx
0x1800053cc  sbb     edi, edi
0x1800053ce  and     edi, 80070216h
0x1800053d4  cmp     rcx, rdx
0x1800053d7  ja      short loc_180005418
0x1800053d9  mov     ecx, eax; cb
0x1800053db  call    cs:__imp_CoTaskMemAlloc
0x1800053e1  mov     [rsi], rax
0x1800053e4  test    rax, rax
0x1800053e7  jz      short loc_180005405
0x1800053e9  add     rbx, rbx
0x1800053ec  mov     rdx, rbp; Src
0x1800053ef  mov     r8, rbx; Size
0x1800053f2  mov     rcx, rax; void *
0x1800053f5  call    memcpy_0
0x1800053fa  mov     rcx, [rsi]
0x1800053fd  xor     eax, eax
0x1800053ff  mov     [rbx+rcx], ax
0x180005403  jmp     short loc_180005418
0x180005405  mov     edi, 8007000Eh
0x18000540a  jmp     short loc_180005418
0x18000540c  mov     edi, 80070216h
0x180005411  jmp     short loc_180005418
0x180005413  mov     edi, 80004005h
0x180005418  mov     eax, edi
0x18000541a  add     rsp, 28h
0x18000541e  pop     rdi
0x18000541f  pop     rsi
0x180005420  pop     rbp
0x180005421  pop     rbx
0x180005422  retn
```
