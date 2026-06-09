# MSAA::ValidateChild(tagVARIANT *,int)

- ea: `0x180063ac4`
- end: `0x180063b67`
- name: `?ValidateChild@MSAA@@YAHPEAUtagVARIANT@@H@Z`
- size: `163`
- prototype: `__int64 __fastcall(MSAA *__hidden this, struct tagVARIANT *, int)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x180063bc0`
- `0x180063c40`
- `0x180064130`
- `0x1800642a0`
- `0x1800643b0`
- `0x180064590`
- `0x1800646e0`
- `0x180064730`
- `0x1800648c0`
- `0x180064980`
- `0x180064a10`
- `0x180064b30`
- `0x180064bb0`
- `0x180064c20`
- `0x180064cb0`
- `0x180064e80`
- `0x180064f10`
- `0x1800650c0`
- `0x1800652b0`
- `0x180065430`

## callees

- `0x180063ac4`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x180063b05`: `VariantCopy`

## pseudocode

```c
_BOOL8 __fastcall MSAA::ValidateChild(MSAA *this, struct tagVARIANT *a2)
{
  int v2; // esi
  void (__fastcall *v4)(MSAA *, __int64); // rax
  __int64 v5; // rdi
  _BOOL8 result; // rax

  v2 = (int)a2;
LABEL_2:
  v4 = (void (__fastcall *)(MSAA *, __int64))qword_1800A7570;
  while ( 1 )
  {
    if ( !*(_WORD *)this )
      goto LABEL_11;
    if ( *(_WORD *)this == 3 )
      break;
    if ( *(_WORD *)this == 10 )
    {
      if ( *((_DWORD *)this + 2) == -2147352572 )
      {
LABEL_11:
        *(_WORD *)this = 3;
        result = 1;
        *((_DWORD *)this + 2) = 0;
        return result;
      }
      return 0;
    }
    if ( *(_WORD *)this != 16396 )
      return 0;
    v5 = *((_QWORD *)this + 1);
    if ( !v4 )
    {
      SetProcAddr((FARPROC *)&qword_1800A7570, 0, "VariantCopy");
      v4 = (void (__fastcall *)(MSAA *, __int64))qword_1800A7570;
      if ( !qword_1800A7570 )
        continue;
    }
    v4(this, v5);
    goto LABEL_2;
  }
  if ( *((int *)this + 2) >= 0 )
    return *((_DWORD *)this + 2) <= v2;
  return 0;
}

```

## disassembly

```asm
0x180063ac4  push    rbx
0x180063ac6  push    rbp
0x180063ac7  push    rsi
0x180063ac8  push    rdi
0x180063ac9  push    r14
0x180063acb  sub     rsp, 20h
0x180063acf  xor     ebp, ebp
0x180063ad1  mov     esi, edx
0x180063ad3  mov     rbx, rcx
0x180063ad6  lea     r14d, [rbp+3]
0x180063ada  mov     rax, cs:qword_1800A7570
0x180063ae1  cmp     [rbx], bp
0x180063ae4  jz      short loc_180063B3C
0x180063ae6  cmp     [rbx], r14w
0x180063aea  jz      short loc_180063B54
0x180063aec  cmp     word ptr [rbx], 0Ah
0x180063af0  jz      short loc_180063B33
0x180063af2  mov     ecx, 400Ch
0x180063af7  cmp     [rbx], cx
0x180063afa  jnz     short loc_180063B63
0x180063afc  mov     rdi, [rbx+8]
0x180063b00  test    rax, rax
0x180063b03  jnz     short loc_180063B26
0x180063b05  lea     r8, aVariantcopy; "VariantCopy"
0x180063b0c  xor     edx, edx
0x180063b0e  lea     rcx, qword_1800A7570
0x180063b15  call    SetProcAddr
0x180063b1a  mov     rax, cs:qword_1800A7570
0x180063b21  test    rax, rax
0x180063b24  jz      short loc_180063AE1
0x180063b26  mov     rdx, rdi
0x180063b29  mov     rcx, rbx
0x180063b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b31  jmp     short loc_180063ADA
0x180063b33  cmp     dword ptr [rbx+8], 80020004h
0x180063b3a  jnz     short loc_180063B63
0x180063b3c  mov     [rbx], r14w
0x180063b40  mov     eax, 1
0x180063b45  mov     [rbx+8], ebp
0x180063b48  add     rsp, 20h
0x180063b4c  pop     r14
0x180063b4e  pop     rdi
0x180063b4f  pop     rsi
0x180063b50  pop     rbp
0x180063b51  pop     rbx
0x180063b52  retn
0x180063b54  cmp     [rbx+8], ebp
0x180063b57  jl      short loc_180063B63
0x180063b59  cmp     [rbx+8], esi
0x180063b5c  mov     eax, ebp
0x180063b5e  setle   al
0x180063b61  jmp     short loc_180063B48
0x180063b63  xor     eax, eax
0x180063b65  jmp     short loc_180063B48
```
