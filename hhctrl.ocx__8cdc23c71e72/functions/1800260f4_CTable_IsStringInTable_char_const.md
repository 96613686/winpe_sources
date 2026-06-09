# CTable::IsStringInTable(char const *)

- ea: `0x1800260f4`
- end: `0x1800261a3`
- name: `?IsStringInTable@CTable@@QEBAHPEBD@Z`
- size: `175`
- prototype: `int(CTable *__hidden this, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013868`
- `0x18001d978`
- `0x18002108c`
- `0x1800399ec`
- `0x18003c050`
- `0x18003e1a0`
- `0x180044904`
- `0x180054bb0`
- `0x180055a40`
- `0x180055f10`
- `0x180060080`

## callees

- `0x1800260f4`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180026145`
- `KERNEL32!lstrcmpiA` at `0x180026145`
- `KERNEL32!CompareStringA` at `0x180026187`
- `KERNEL32!CompareStringA` at `0x180026187`
- `USER32!CharLowerA` at `0x18002610e`
- `USER32!CharLowerA` at `0x18002610e`
- `USER32!CharUpperA` at `0x18002611a`
- `USER32!CharUpperA` at `0x18002611a`

## pseudocode

```c
__int64 __fastcall CTable::IsStringInTable(CTable *this, const char *a2)
{
  unsigned __int8 v4; // r14
  unsigned __int8 v5; // bp
  int i; // ebx
  const CHAR *v7; // rcx

  if ( *((_DWORD *)this + 15) )
  {
    for ( i = 1; i < *((_DWORD *)this + 8); ++i )
    {
      if ( CompareStringA(
             *((_DWORD *)this + 15),
             *((_DWORD *)this + 16) | 1,
             a2,
             -1,
             *(PCNZCH *)(*((_QWORD *)this + 2) + 8LL * i),
             -1) == 1 )
        return (unsigned int)i;
    }
  }
  else
  {
    v4 = (unsigned __int8)CharLowerA((LPSTR)*(unsigned __int8 *)a2);
    v5 = (unsigned __int8)CharUpperA((LPSTR)*(unsigned __int8 *)a2);
    for ( i = 1; i < *((_DWORD *)this + 8); ++i )
    {
      v7 = *(const CHAR **)(*((_QWORD *)this + 2) + 8LL * i);
      if ( (*v7 == v4 || *v7 == v5) && !lstrcmpiA(v7, a2) )
        return (unsigned int)i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800260f4  push    rbx
0x1800260f6  push    rbp
0x1800260f7  push    rsi
0x1800260f8  push    rdi
0x1800260f9  push    r14
0x1800260fb  sub     rsp, 30h
0x1800260ff  cmp     dword ptr [rcx+3Ch], 0
0x180026103  mov     rsi, rdx
0x180026106  mov     rdi, rcx
0x180026109  jnz     short loc_180026157
0x18002610b  movzx   ecx, byte ptr [rdx]; lpsz
0x18002610e  call    cs:__imp_CharLowerA
0x180026114  movzx   ecx, byte ptr [rsi]; lpsz
0x180026117  mov     r14, rax
0x18002611a  call    cs:__imp_CharUpperA
0x180026120  mov     rbp, rax
0x180026123  mov     ebx, 1
0x180026128  cmp     ebx, [rdi+20h]
0x18002612b  jge     short loc_180026196
0x18002612d  mov     rcx, [rdi+10h]
0x180026131  movsxd  rdx, ebx
0x180026134  mov     rcx, [rcx+rdx*8]; lpString1
0x180026138  cmp     [rcx], r14b
0x18002613b  jz      short loc_180026142
0x18002613d  cmp     [rcx], bpl
0x180026140  jnz     short loc_18002614F
0x180026142  mov     rdx, rsi; lpString2
0x180026145  call    cs:__imp_lstrcmpiA
0x18002614b  test    eax, eax
0x18002614d  jz      short loc_180026153
0x18002614f  inc     ebx
0x180026151  jmp     short loc_180026128
0x180026153  mov     eax, ebx
0x180026155  jmp     short loc_180026198
0x180026157  mov     ebx, 1
0x18002615c  or      ebp, 0FFFFFFFFh
0x18002615f  cmp     ebx, [rdi+20h]
0x180026162  jge     short loc_180026196
0x180026164  mov     rax, [rdi+10h]
0x180026168  mov     r9d, ebp; cchCount1
0x18002616b  mov     edx, [rdi+40h]
0x18002616e  mov     r8, rsi; lpString1
0x180026171  movsxd  rcx, ebx
0x180026174  or      edx, 1; dwCmpFlags
0x180026177  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18002617b  mov     rax, [rax+rcx*8]
0x18002617f  mov     ecx, [rdi+3Ch]; Locale
0x180026182  mov     [rsp+58h+lpString2], rax; lpString2
0x180026187  call    cs:__imp_CompareStringA
0x18002618d  cmp     eax, 1
0x180026190  jz      short loc_180026153
0x180026192  inc     ebx
0x180026194  jmp     short loc_18002615F
0x180026196  xor     eax, eax
0x180026198  add     rsp, 30h
0x18002619c  pop     r14
0x18002619e  pop     rdi
0x18002619f  pop     rsi
0x1800261a0  pop     rbp
0x1800261a1  pop     rbx
0x1800261a2  retn
```
