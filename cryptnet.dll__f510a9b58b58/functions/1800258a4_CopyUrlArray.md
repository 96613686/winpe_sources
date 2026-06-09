# CopyUrlArray

- ea: `0x1800258a4`
- end: `0x180025978`
- name: `CopyUrlArray`
- size: `212`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x1800258a4`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002595f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002595f`

## pseudocode

```c
__int64 __fastcall CopyUrlArray(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  unsigned int v8; // r15d
  _WORD *v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // esi

  v6 = 8 * *(_DWORD *)a2;
  if ( a3 < v6 + 16 )
  {
LABEL_12:
    SetLastError(0x80070057);
    return 0;
  }
  else
  {
    *(_DWORD *)a1 = *(_DWORD *)a2;
    v7 = 0;
    *(_QWORD *)(a1 + 8) = a1 + 16;
    v8 = 0;
    while ( v7 < *(_DWORD *)a2 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * v7) = v8 + a1 + v6 + 16LL;
      v9 = *(_WORD **)(*(_QWORD *)(a2 + 8) + 8LL * v7);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
      }
      else
      {
        LODWORD(v10) = 0;
      }
      v11 = 2 * v10 + 2;
      if ( a3 < v8 + v11 + v6 + 16 )
        goto LABEL_12;
      memcpy_0(*(void **)(*(_QWORD *)(a1 + 8) + 8LL * v7), v9, v11);
      v8 += v11;
      ++v7;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1800258a4  push    rbx
0x1800258a6  push    rbp
0x1800258a7  push    rsi
0x1800258a8  push    rdi
0x1800258a9  push    r12
0x1800258ab  push    r13
0x1800258ad  push    r14
0x1800258af  push    r15
0x1800258b1  sub     rsp, 28h
0x1800258b5  mov     rbx, rcx
0x1800258b8  mov     r12d, r8d
0x1800258bb  mov     ecx, [rdx]
0x1800258bd  mov     rdi, rdx
0x1800258c0  lea     r14d, ds:0[rcx*8]
0x1800258c8  lea     eax, [r14+10h]
0x1800258cc  cmp     r8d, eax
0x1800258cf  jb      loc_18002595A
0x1800258d5  xor     r13d, r13d
0x1800258d8  mov     [rbx], ecx
0x1800258da  lea     rax, [rbx+10h]
0x1800258de  mov     ebp, r13d
0x1800258e1  mov     [rbx+8], rax
0x1800258e5  mov     r15d, r13d
0x1800258e8  cmp     ebp, [rdi]
0x1800258ea  jnb     short loc_180025953
0x1800258ec  mov     rax, [rbx+8]
0x1800258f0  mov     r9d, ebp
0x1800258f3  mov     edx, r14d
0x1800258f6  add     rdx, 10h
0x1800258fa  mov     ecx, r15d
0x1800258fd  add     rdx, rbx
0x180025900  add     rdx, rcx
0x180025903  mov     [rax+r9*8], rdx
0x180025907  mov     rax, [rdi+8]
0x18002590b  mov     rdx, [rax+r9*8]; Src
0x18002590f  test    rdx, rdx
0x180025912  jz      short loc_180025924
0x180025914  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025918  inc     rax
0x18002591b  cmp     [rdx+rax*2], r13w
0x180025920  jnz     short loc_180025918
0x180025922  jmp     short loc_180025927
0x180025924  mov     eax, r13d
0x180025927  lea     esi, ds:2[rax*2]
0x18002592e  lea     ecx, [r14+10h]
0x180025932  add     ecx, esi
0x180025934  add     ecx, r15d
0x180025937  cmp     r12d, ecx
0x18002593a  jb      short loc_18002595A
0x18002593c  mov     rcx, [rbx+8]
0x180025940  mov     r8d, esi; Size
0x180025943  mov     rcx, [rcx+r9*8]; void *
0x180025947  call    memcpy_0
0x18002594c  add     r15d, esi
0x18002594f  inc     ebp
0x180025951  jmp     short loc_1800258E8
0x180025953  mov     eax, 1
0x180025958  jmp     short loc_180025967
0x18002595a  mov     ecx, 80070057h; dwErrCode
0x18002595f  call    cs:__imp_SetLastError
0x180025965  xor     eax, eax
0x180025967  add     rsp, 28h
0x18002596b  pop     r15
0x18002596d  pop     r14
0x18002596f  pop     r13
0x180025971  pop     r12
0x180025973  pop     rdi
0x180025974  pop     rsi
0x180025975  pop     rbp
0x180025976  pop     rbx
0x180025977  retn
```
