# MakePathCanonicalizationProofNt(ushort const *,STRU *)

- ea: `0x180001cd0`
- end: `0x180001f47`
- name: `?MakePathCanonicalizationProofNt@@YAJPEBGPEAVSTRU@@@Z`
- size: `631`
- prototype: `int(const unsigned __int16 *, struct STRU *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001cd0`
- `0x180002470`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f1e`

## pseudocode

```c
int __fastcall MakePathCanonicalizationProofNt(const unsigned __int16 *a1, struct STRU *a2)
{
  const unsigned __int16 *v3; // rbx
  unsigned __int16 v4; // ax
  unsigned int *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rax
  unsigned int v10; // r14d
  __int64 v11; // rcx
  __int64 v12; // rdx
  int result; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  bool v17; // sf
  bool v18; // sf
  bool v19; // sf

  v3 = a1;
  if ( *(_DWORD *)a1 == 6029404 )
  {
    v4 = a1[2];
    if ( (v4 == 63 || v4 == 46) && a1[3] == 92 )
    {
      v5 = (unsigned int *)((char *)a2 + 40);
      if ( *((_DWORD *)a2 + 10) >= 0xAu || BUFFER::Resize(a2, 0x88u) )
      {
        **((_QWORD **)a2 + 4) = 0x5C003F003F005CLL;
        v6 = *((_QWORD *)a2 + 4);
        *((_DWORD *)a2 + 12) = 4;
        *(_WORD *)(v6 + 8) = 0;
      }
      else
      {
        result = GetLastError();
        v17 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v17 = result < 0;
        }
        if ( v17 )
          return result;
      }
      v3 += 4;
    }
    else
    {
      v5 = (unsigned int *)((char *)a2 + 40);
      v3 = a1 + 2;
      if ( *((_DWORD *)a2 + 10) >= 0x12u || BUFFER::Resize(a2, 0x90u) )
      {
        *(_OWORD *)*((_QWORD *)a2 + 4) = *(_OWORD *)L"\\??\\UNC\\";
        v15 = *((_QWORD *)a2 + 4);
        *((_DWORD *)a2 + 12) = 8;
        *(_WORD *)(v15 + 16) = 0;
      }
      else
      {
        result = GetLastError();
        v19 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v19 = result < 0;
        }
        if ( v19 )
          return result;
      }
    }
    if ( !v3 )
      return 0;
  }
  else
  {
    v5 = (unsigned int *)((char *)a2 + 40);
    if ( *((_DWORD *)a2 + 10) >= 0xAu || BUFFER::Resize(a2, 0x88u) )
    {
      **((_QWORD **)a2 + 4) = 0x5C003F003F005CLL;
      v14 = *((_QWORD *)a2 + 4);
      *((_DWORD *)a2 + 12) = 4;
      *(_WORD *)(v14 + 8) = 0;
    }
    else
    {
      result = GetLastError();
      v18 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v18 = result < 0;
      }
      if ( v18 )
        return result;
    }
  }
  v7 = (unsigned int)(2 * *((_DWORD *)a2 + 12));
  v8 = -1;
  while ( v3[++v8] != 0 )
    ;
  v10 = 2 * v8;
  if ( *v5 >= (unsigned __int64)(unsigned int)(2 * v8) + v7 + 2 )
    goto LABEL_11;
  v16 = v10 + v7 + 128;
  if ( v16 > 0xFFFFFFFF )
    return -2147024362;
  if ( BUFFER::Resize(a2, v16) )
  {
LABEL_11:
    memcpy_0((void *)((unsigned int)v7 + *((_QWORD *)a2 + 4)), v3, v10);
    v11 = *((_QWORD *)a2 + 4);
    v12 = (v10 + (unsigned int)v7) >> 1;
    result = 0;
    *((_DWORD *)a2 + 12) = v12;
    *(_WORD *)(v11 + 2 * v12) = 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180001cd0  push    rbx
0x180001cd2  push    rsi
0x180001cd3  push    rdi
0x180001cd4  sub     rsp, 20h
0x180001cd8  cmp     word ptr [rcx], 5Ch ; '\'
0x180001cdc  mov     rdi, rdx
0x180001cdf  mov     rbx, rcx
0x180001ce2  jnz     loc_180001DD9
0x180001ce8  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180001ced  jnz     loc_180001DD9
0x180001cf3  movzx   eax, word ptr [rcx+4]
0x180001cf7  cmp     ax, 3Fh ; '?'
0x180001cfb  jnz     loc_180001E0E
0x180001d01  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180001d06  jnz     loc_180001E18
0x180001d0c  cmp     dword ptr [rdx+28h], 0Ah
0x180001d10  lea     rsi, [rdx+28h]
0x180001d14  jb      loc_180001E91
0x180001d1a  mov     rax, [rdi+20h]
0x180001d1e  mov     rcx, 5C003F003F005Ch
0x180001d28  mov     [rax], rcx
0x180001d2b  xor     eax, eax
0x180001d2d  mov     rcx, [rdi+20h]
0x180001d31  mov     dword ptr [rdi+30h], 4
0x180001d38  mov     [rcx+8], ax
0x180001d3c  add     rbx, 8
0x180001d40  test    rbx, rbx
0x180001d43  jz      loc_180001EFF
0x180001d49  mov     eax, [rdi+30h]
0x180001d4c  mov     [rsp+38h+arg_0], rbp
0x180001d51  mov     [rsp+38h+arg_8], r12
0x180001d56  mov     [rsp+38h+arg_10], r14
0x180001d5b  lea     ebp, [rax+rax]
0x180001d5e  mov     [rsp+38h+arg_18], r15
0x180001d63  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001d6a  nop     word ptr [rax+rax+00h]
0x180001d70  cmp     word ptr [rbx+rax*2+2], 0
0x180001d76  lea     rax, [rax+1]
0x180001d7a  jnz     short loc_180001D70
0x180001d7c  lea     r14d, [rax+rax]
0x180001d80  mov     r15d, ebp
0x180001d83  mov     eax, [rsi]
0x180001d85  lea     rcx, [rbp+2]
0x180001d89  mov     r12d, r14d
0x180001d8c  add     rcx, r12
0x180001d8f  cmp     rax, rcx
0x180001d92  jb      loc_180001E4E
0x180001d98  mov     rcx, [rdi+20h]
0x180001d9c  mov     r8, r12; Size
0x180001d9f  add     rcx, r15; void *
0x180001da2  mov     rdx, rbx; Src
0x180001da5  call    memcpy_0
0x180001daa  mov     rcx, [rdi+20h]
0x180001dae  lea     edx, [r14+rbp]
0x180001db2  shr     edx, 1
0x180001db4  xor     eax, eax
0x180001db6  mov     [rdi+30h], edx
0x180001db9  mov     [rcx+rdx*2], ax
0x180001dbd  mov     r14, [rsp+38h+arg_10]
0x180001dc2  mov     r12, [rsp+38h+arg_8]
0x180001dc7  mov     rbp, [rsp+38h+arg_0]
0x180001dcc  mov     r15, [rsp+38h+arg_18]
0x180001dd1  add     rsp, 20h
0x180001dd5  pop     rdi
0x180001dd6  pop     rsi
0x180001dd7  pop     rbx
0x180001dd8  retn
0x180001dd9  cmp     dword ptr [rdx+28h], 0Ah
0x180001ddd  lea     rsi, [rdx+28h]
0x180001de1  jb      loc_180001EC8
0x180001de7  mov     rax, [rdi+20h]
0x180001deb  mov     rcx, 5C003F003F005Ch
0x180001df5  mov     [rax], rcx
0x180001df8  xor     eax, eax
0x180001dfa  mov     rcx, [rdi+20h]
0x180001dfe  mov     dword ptr [rdi+30h], 4
0x180001e05  mov     [rcx+8], ax
0x180001e09  jmp     loc_180001D49
0x180001e0e  cmp     ax, 2Eh ; '.'
0x180001e12  jz      loc_180001D01
0x180001e18  cmp     dword ptr [rdx+28h], 12h
0x180001e1c  lea     rsi, [rdx+28h]
0x180001e20  lea     rbx, [rcx+4]
0x180001e24  jb      loc_180001F09
0x180001e2a  mov     rax, [rdi+20h]
0x180001e2e  movups  xmm0, xmmword ptr cs:aUnc; "\\??\\UNC\\"
0x180001e35  movups  xmmword ptr [rax], xmm0
0x180001e38  mov     rcx, [rdi+20h]
0x180001e3c  xor     eax, eax
0x180001e3e  mov     dword ptr [rdi+30h], 8
0x180001e45  mov     [rcx+10h], ax
0x180001e49  jmp     loc_180001D40
0x180001e4e  lea     rdx, [rbp+80h]
0x180001e55  mov     eax, 0FFFFFFFFh
0x180001e5a  add     rdx, r12; unsigned int
0x180001e5d  cmp     rdx, rax
0x180001e60  ja      loc_180001F3D
0x180001e66  mov     rcx, rdi; this
0x180001e69  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001e6e  test    al, al
0x180001e70  jnz     loc_180001D98
0x180001e76  call    cs:__imp_GetLastError
0x180001e7c  test    eax, eax
0x180001e7e  jle     loc_180001DBD
0x180001e84  movzx   eax, ax
0x180001e87  or      eax, 80070000h
0x180001e8c  jmp     loc_180001DBD
0x180001e91  mov     edx, 88h; unsigned int
0x180001e96  mov     rcx, rdi; this
0x180001e99  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001e9e  test    al, al
0x180001ea0  jnz     loc_180001D1A
0x180001ea6  call    cs:__imp_GetLastError
0x180001eac  test    eax, eax
0x180001eae  jle     short loc_180001EBA
0x180001eb0  movzx   eax, ax
0x180001eb3  or      eax, 80070000h
0x180001eb8  test    eax, eax
0x180001eba  jns     loc_180001D3C
0x180001ec0  add     rsp, 20h
0x180001ec4  pop     rdi
0x180001ec5  pop     rsi
0x180001ec6  pop     rbx
0x180001ec7  retn
0x180001ec8  mov     edx, 88h; unsigned int
0x180001ecd  mov     rcx, rdi; this
0x180001ed0  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001ed5  test    al, al
0x180001ed7  jnz     loc_180001DE7
0x180001edd  call    cs:__imp_GetLastError
0x180001ee3  test    eax, eax
0x180001ee5  jle     short loc_180001EF1
0x180001ee7  movzx   eax, ax
0x180001eea  or      eax, 80070000h
0x180001eef  test    eax, eax
0x180001ef1  jns     loc_180001D49
0x180001ef7  add     rsp, 20h
0x180001efb  pop     rdi
0x180001efc  pop     rsi
0x180001efd  pop     rbx
0x180001efe  retn
0x180001eff  xor     eax, eax
0x180001f01  add     rsp, 20h
0x180001f05  pop     rdi
0x180001f06  pop     rsi
0x180001f07  pop     rbx
0x180001f08  retn
0x180001f09  mov     edx, 90h; unsigned int
0x180001f0e  mov     rcx, rdi; this
0x180001f11  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001f16  test    al, al
0x180001f18  jnz     loc_180001E2A
0x180001f1e  call    cs:__imp_GetLastError
0x180001f24  test    eax, eax
0x180001f26  jle     short loc_180001F32
0x180001f28  movzx   eax, ax
0x180001f2b  or      eax, 80070000h
0x180001f30  test    eax, eax
0x180001f32  js      loc_180001DD1
0x180001f38  jmp     loc_180001D40
0x180001f3d  mov     eax, 80070216h
0x180001f42  jmp     loc_180001DBD
```
