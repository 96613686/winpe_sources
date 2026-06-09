# SHILCombineParentAndFirst

- ea: `0x1800481b0`
- end: `0x180048254`
- name: `SHILCombineParentAndFirst`
- size: `164`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afa0`
- `0x180012150`
- `0x180033470`
- `0x180035420`

## callees

- `0x1800481b0`
- `0x18004c61e`
- `0x18004c636`

## import_xrefs

- `SHELL32!__imp_ILGetSize` at `0x1800481dc`
- `SHELL32!__imp_ILGetSize` at `0x1800481dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800481f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800481f4`

## pseudocode

```c
__int64 __fastcall SHILCombineParentAndFirst(const ITEMIDLIST *Src, void *a2, int a3, char **a4)
{
  __int64 result; // rax
  unsigned int v8; // edi
  UINT v9; // r14d
  char *v10; // rax
  char *v11; // rsi

  *a4 = 0;
  result = 2147942487LL;
  if ( Src )
  {
    v8 = a3 - (_DWORD)a2;
    v9 = ILGetSize(Src);
    if ( v8 + v9 < v9 )
    {
      return 2147942934LL;
    }
    else
    {
      v10 = (char *)CoTaskMemAlloc(v8 + v9);
      *a4 = v10;
      v11 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, v8 + v9);
        memcpy_0(v11, Src, v9 - 2);
        memcpy_0(&v11[v9 - 2], a2, v8);
        return 0;
      }
      else
      {
        return 2147942414LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800481b0  push    rbx
0x1800481b2  push    rbp
0x1800481b3  push    rsi
0x1800481b4  push    rdi
0x1800481b5  push    r12
0x1800481b7  push    r14
0x1800481b9  push    r15
0x1800481bb  sub     rsp, 20h
0x1800481bf  mov     qword ptr [r9], 0
0x1800481c6  mov     rbx, r9
0x1800481c9  mov     rdi, r8
0x1800481cc  mov     r12, rdx
0x1800481cf  mov     rbp, rcx
0x1800481d2  mov     eax, 80070057h
0x1800481d7  test    rcx, rcx
0x1800481da  jz      short loc_180048245
0x1800481dc  call    cs:__imp_ILGetSize
0x1800481e2  sub     edi, r12d
0x1800481e5  mov     r14d, eax
0x1800481e8  add     eax, edi
0x1800481ea  cmp     eax, r14d
0x1800481ed  jb      short loc_180048240
0x1800481ef  mov     ecx, eax; cb
0x1800481f1  mov     r15d, eax
0x1800481f4  call    cs:__imp_CoTaskMemAlloc
0x1800481fa  mov     [rbx], rax
0x1800481fd  mov     rsi, rax
0x180048200  test    rax, rax
0x180048203  jz      short loc_180048239
0x180048205  mov     r8d, r15d; Size
0x180048208  xor     edx, edx; Val
0x18004820a  mov     rcx, rax; void *
0x18004820d  call    memset_0
0x180048212  lea     eax, [r14-2]
0x180048216  mov     rdx, rbp; Src
0x180048219  mov     r8d, eax; Size
0x18004821c  mov     rcx, rsi; void *
0x18004821f  mov     ebx, eax
0x180048221  call    memcpy_0
0x180048226  mov     r8d, edi; Size
0x180048229  lea     rcx, [rbx+rsi]; void *
0x18004822d  mov     rdx, r12; Src
0x180048230  call    memcpy_0
0x180048235  xor     eax, eax
0x180048237  jmp     short loc_180048245
0x180048239  mov     eax, 8007000Eh
0x18004823e  jmp     short loc_180048245
0x180048240  mov     eax, 80070216h
0x180048245  add     rsp, 20h
0x180048249  pop     r15
0x18004824b  pop     r14
0x18004824d  pop     r12
0x18004824f  pop     rdi
0x180048250  pop     rsi
0x180048251  pop     rbp
0x180048252  pop     rbx
0x180048253  retn
```
