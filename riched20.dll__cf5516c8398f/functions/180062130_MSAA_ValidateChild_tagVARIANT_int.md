# MSAA::ValidateChild(tagVARIANT *,int)

- ea: `0x180062130`
- end: `0x1800621d2`
- name: `?ValidateChild@MSAA@@YAHPEAUtagVARIANT@@H@Z`
- size: `162`
- prototype: `__int64 __fastcall(MSAA *__hidden this, struct tagVARIANT *, int)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x180062220`
- `0x1800622a0`
- `0x180062730`
- `0x180062890`
- `0x180062990`
- `0x180062b70`
- `0x180062cc0`
- `0x180062d10`
- `0x180062ea0`
- `0x180062f60`
- `0x180062fe0`
- `0x1800630f0`
- `0x180063170`
- `0x1800631e0`
- `0x180063270`
- `0x180063440`
- `0x1800634d0`
- `0x180063680`
- `0x180063870`
- `0x1800639e0`

## callees

- `0x180062130`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x180062171`: `VariantCopy`

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
  v4 = (void (__fastcall *)(MSAA *, __int64))qword_1800A4490;
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
      SetProcAddr((FARPROC *)&qword_1800A4490, 0, "VariantCopy");
      v4 = (void (__fastcall *)(MSAA *, __int64))qword_1800A4490;
      if ( !qword_1800A4490 )
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
0x180062130  push    rbx
0x180062132  push    rbp
0x180062133  push    rsi
0x180062134  push    rdi
0x180062135  push    r14
0x180062137  sub     rsp, 20h
0x18006213b  xor     ebp, ebp
0x18006213d  mov     esi, edx
0x18006213f  mov     rbx, rcx
0x180062142  lea     r14d, [rbp+3]
0x180062146  mov     rax, cs:qword_1800A4490
0x18006214d  cmp     [rbx], bp
0x180062150  jz      short loc_1800621A8
0x180062152  cmp     [rbx], r14w
0x180062156  jz      short loc_1800621BF
0x180062158  cmp     word ptr [rbx], 0Ah
0x18006215c  jz      short loc_18006219F
0x18006215e  mov     ecx, 400Ch
0x180062163  cmp     [rbx], cx
0x180062166  jnz     short loc_1800621CE
0x180062168  mov     rdi, [rbx+8]
0x18006216c  test    rax, rax
0x18006216f  jnz     short loc_180062192
0x180062171  lea     r8, aVariantcopy; "VariantCopy"
0x180062178  xor     edx, edx
0x18006217a  lea     rcx, qword_1800A4490
0x180062181  call    SetProcAddr
0x180062186  mov     rax, cs:qword_1800A4490
0x18006218d  test    rax, rax
0x180062190  jz      short loc_18006214D
0x180062192  mov     rdx, rdi
0x180062195  mov     rcx, rbx
0x180062198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006219d  jmp     short loc_180062146
0x18006219f  cmp     dword ptr [rbx+8], 80020004h
0x1800621a6  jnz     short loc_1800621CE
0x1800621a8  mov     [rbx], r14w
0x1800621ac  mov     eax, 1
0x1800621b1  mov     [rbx+8], ebp
0x1800621b4  add     rsp, 20h
0x1800621b8  pop     r14
0x1800621ba  pop     rdi
0x1800621bb  pop     rsi
0x1800621bc  pop     rbp
0x1800621bd  pop     rbx
0x1800621be  retn
0x1800621bf  cmp     [rbx+8], ebp
0x1800621c2  jl      short loc_1800621CE
0x1800621c4  cmp     [rbx+8], esi
0x1800621c7  mov     eax, ebp
0x1800621c9  setle   al
0x1800621cc  jmp     short loc_1800621B4
0x1800621ce  xor     eax, eax
0x1800621d0  jmp     short loc_1800621B4
```
