# PpfEvtLogCreateSingleDigestTable

- ea: `0x180028344`
- end: `0x180028454`
- name: `PpfEvtLogCreateSingleDigestTable`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180041df0`

## callees

- `0x180028344`
- `0x1800290f4`
- `0x18002919c`
- `0x1800570b0`
- `0x180059010`

## string_xrefs

- `0x18002838e`: `PpfEvtLogCreateSingleDigestTable`

## pseudocode

```c
__int64 __fastcall PpfEvtLogCreateSingleDigestTable(
        __int64 a1,
        const void *a2,
        unsigned __int16 a3,
        _QWORD *a4,
        unsigned int *a5)
{
  size_t v6; // rbp
  __int16 v8; // r14
  int Size; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  _WORD *v12; // rax
  _WORD *v13; // rsi
  _WORD v15[36]; // [rsp+30h] [rbp-48h] BYREF

  v6 = a3;
  v15[0] = 0;
  v8 = a1;
  Size = PpfEvtLogValidateDigestAlgIDAndGetSize(a1, v15);
  v10 = Size;
  if ( Size >= 0 )
  {
    if ( v15[0] == (_WORD)v6 )
    {
      if ( AllocFn )
      {
        v11 = v15[0] + 2;
        v12 = (_WORD *)AllocFn(v11);
        v13 = v12;
        if ( v12 )
        {
          v10 = 0;
          *v12 = v8;
          memcpy_0(v12 + 1, a2, v6);
          *a4 = v13;
          *a5 = v11;
        }
        else
        {
          v10 = -1073741801;
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
            1163,
            (int)"PpfEvtLogCreateSingleDigestTable",
            1,
            "Error: 0x%x",
            23);
        }
      }
      else
      {
        v10 = -1073741595;
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
          1152,
          (int)"PpfEvtLogCreateSingleDigestTable",
          1,
          "Error: 0x%x",
          229);
      }
    }
    else
    {
      v10 = -1073741811;
      PpfEvtLogTraceHelper(
        (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
        1148,
        (int)"PpfEvtLogCreateSingleDigestTable",
        1,
        "Error: 0x%x",
        13);
    }
  }
  else
  {
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      1144,
      (int)"PpfEvtLogCreateSingleDigestTable",
      1,
      "Error: 0x%x",
      Size);
  }
  return v10;
}

```

## disassembly

```asm
0x180028344  push    rbx
0x180028346  push    rbp
0x180028347  push    rsi
0x180028348  push    rdi
0x180028349  push    r12
0x18002834b  push    r14
0x18002834d  push    r15
0x18002834f  sub     rsp, 40h
0x180028353  mov     r12, rdx
0x180028356  movzx   ebp, r8w
0x18002835a  xor     eax, eax
0x18002835c  lea     rdx, [rsp+78h+var_48]
0x180028361  mov     [rsp+78h+var_48], ax
0x180028366  mov     r15, r9
0x180028369  movzx   r14d, cx
0x18002836d  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180028372  mov     ebx, eax
0x180028374  test    eax, eax
0x180028376  jns     short loc_1800283AB
0x180028378  mov     dword ptr [rsp+78h+var_50], eax; char
0x18002837c  mov     edx, 478h; int
0x180028381  lea     rax, aError0xX; "Error: 0x%x"
0x180028388  mov     r9d, 1; int
0x18002838e  lea     r8, aPpfevtlogcreat_0; "PpfEvtLogCreateSingleDigestTable"
0x180028395  mov     [rsp+78h+Format], rax; Format
0x18002839a  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x1800283a1  call    PpfEvtLogTraceHelper
0x1800283a6  jmp     loc_180028442
0x1800283ab  cmp     [rsp+78h+var_48], bp
0x1800283b0  jz      short loc_1800283C2
0x1800283b2  mov     ebx, 0C000000Dh
0x1800283b7  mov     edx, 47Ch
0x1800283bc  mov     dword ptr [rsp+78h+var_50], ebx
0x1800283c0  jmp     short loc_180028381
0x1800283c2  mov     rdx, cs:_AllocFn
0x1800283c9  test    rdx, rdx
0x1800283cc  jnz     short loc_1800283DE
0x1800283ce  mov     ebx, 0C00000E5h
0x1800283d3  mov     edx, 480h
0x1800283d8  mov     dword ptr [rsp+78h+var_50], ebx
0x1800283dc  jmp     short loc_180028381
0x1800283de  movzx   edi, [rsp+78h+var_48]
0x1800283e3  add     edi, 2
0x1800283e6  cmp     edi, 2
0x1800283e9  jnb     short loc_1800283FB
0x1800283eb  mov     ebx, 0C0000095h
0x1800283f0  mov     edx, 486h
0x1800283f5  mov     dword ptr [rsp+78h+var_50], ebx
0x1800283f9  jmp     short loc_180028381
0x1800283fb  mov     ecx, edi
0x1800283fd  mov     rax, rdx
0x180028400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028405  mov     rsi, rax
0x180028408  test    rax, rax
0x18002840b  jnz     short loc_180028420
0x18002840d  mov     ebx, 0C0000017h
0x180028412  mov     edx, 48Bh
0x180028417  mov     dword ptr [rsp+78h+var_50], ebx
0x18002841b  jmp     loc_180028381
0x180028420  xor     ebx, ebx
0x180028422  mov     [rax], r14w
0x180028426  mov     r8, rbp; Size
0x180028429  lea     rcx, [rax+2]; void *
0x18002842d  mov     rdx, r12; Src
0x180028430  call    memcpy_0
0x180028435  mov     rax, [rsp+78h+arg_20]
0x18002843d  mov     [r15], rsi
0x180028440  mov     [rax], edi
0x180028442  mov     eax, ebx
0x180028444  add     rsp, 40h
0x180028448  pop     r15
0x18002844a  pop     r14
0x18002844c  pop     r12
0x18002844e  pop     rdi
0x18002844f  pop     rsi
0x180028450  pop     rbp
0x180028451  pop     rbx
0x180028452  retn
```
