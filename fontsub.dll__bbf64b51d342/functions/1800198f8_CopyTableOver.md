# CopyTableOver

- ea: `0x1800198f8`
- end: `0x180019a3a`
- name: `CopyTableOver`
- size: `322`
- prototype: ``
- caller_count: `14`
- callee_count: `10`
- tags: ``

## callers

- `0x180007800`
- `0x180007fa4`
- `0x18000fd08`
- `0x180010088`
- `0x180010284`
- `0x180010454`
- `0x1800105d0`
- `0x18001077c`
- `0x1800108e4`
- `0x1800109fc`
- `0x180010fd4`
- `0x1800118bc`
- `0x180013364`
- `0x180013ee0`

## callees

- `0x1800198f8`
- `0x180019b9c`
- `0x180019e04`
- `0x180019e64`
- `0x18001a060`
- `0x18001a208`
- `0x18001a234`
- `0x18001a380`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall CopyTableOver(_QWORD *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int TTDirectory; // r13d
  unsigned int v9; // r15d
  unsigned int v10; // edi
  __int64 result; // rax
  unsigned int v12; // ebx
  unsigned __int16 Bytes; // dx
  _WORD v14[2]; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-64h] BYREF
  __int128 v16; // [rsp+38h] [rbp-60h] BYREF

  v15 = 0;
  v14[0] = 0;
  v16 = 0;
  TTDirectory = GetTTDirectory(a1, a3, &v16);
  if ( !TTDirectory )
    return 1006;
  v9 = TTTableOffset(a2, a3);
  v10 = TTTableLength(a2, a3);
  if ( !v9 )
    return 1006;
  result = ZeroLongWordAlign(a1, (unsigned int)*a4, &v15);
  if ( (_WORD)result )
    return result;
  v12 = v15;
  *((_QWORD *)&v16 + 1) = __PAIR64__(v10, v15);
  if ( !v10 )
    goto LABEL_8;
  result = CheckInOffset(a2, v9, v10);
  if ( !(_WORD)result )
  {
    result = CheckOutOffset(a1, v12);
    if ( !(_WORD)result )
    {
      Bytes = ReadBytes(a2, *a1 + v12, v9, v10);
      if ( Bytes )
        return Bytes;
LABEL_8:
      Bytes = WriteGeneric((__int64)a1, (__int64)&v16, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, v14);
      if ( !Bytes )
        *a4 = v10 + v12;
      return Bytes;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800198f8  push    rbx
0x1800198fa  push    rbp
0x1800198fb  push    rsi
0x1800198fc  push    rdi
0x1800198fd  push    r12
0x1800198ff  push    r13
0x180019901  push    r14
0x180019903  push    r15
0x180019905  sub     rsp, 58h
0x180019909  mov     rax, cs:__security_cookie
0x180019910  xor     rax, rsp
0x180019913  mov     [rsp+98h+var_50], rax
0x180019918  mov     rbx, r8
0x18001991b  mov     r14, rdx
0x18001991e  xor     ebp, ebp
0x180019920  lea     r8, [rsp+98h+var_60]
0x180019925  xorps   xmm0, xmm0
0x180019928  mov     [rsp+98h+var_64], ebp
0x18001992c  mov     rdx, rbx
0x18001992f  mov     [rsp+98h+var_68], bp
0x180019934  mov     r12, r9
0x180019937  mov     rsi, rcx
0x18001993a  movups  [rsp+98h+var_60], xmm0
0x18001993f  call    GetTTDirectory
0x180019944  mov     r13d, eax
0x180019947  test    eax, eax
0x180019949  jz      loc_180019A17
0x18001994f  mov     rdx, rbx
0x180019952  mov     rcx, r14
0x180019955  call    TTTableOffset
0x18001995a  mov     rdx, rbx
0x18001995d  mov     rcx, r14
0x180019960  mov     r15d, eax
0x180019963  call    TTTableLength
0x180019968  mov     edi, eax
0x18001996a  test    r15d, r15d
0x18001996d  jz      loc_180019A17
0x180019973  mov     edx, [r12]
0x180019977  lea     r8, [rsp+98h+var_64]
0x18001997c  mov     rcx, rsi
0x18001997f  call    ZeroLongWordAlign
0x180019984  test    ax, ax
0x180019987  jnz     loc_180019A1C
0x18001998d  mov     ebx, [rsp+98h+var_64]
0x180019991  mov     dword ptr [rsp+98h+var_60+8], ebx
0x180019995  mov     dword ptr [rsp+98h+var_60+0Ch], edi
0x180019999  test    edi, edi
0x18001999b  jz      short loc_1800199DA
0x18001999d  mov     r8d, edi
0x1800199a0  mov     edx, r15d
0x1800199a3  mov     rcx, r14
0x1800199a6  call    CheckInOffset
0x1800199ab  test    ax, ax
0x1800199ae  jnz     short loc_180019A1C
0x1800199b0  mov     edx, ebx
0x1800199b2  mov     rcx, rsi
0x1800199b5  call    CheckOutOffset
0x1800199ba  test    ax, ax
0x1800199bd  jnz     short loc_180019A1C
0x1800199bf  mov     edx, ebx
0x1800199c1  mov     r9d, edi
0x1800199c4  add     rdx, [rsi]
0x1800199c7  mov     r8d, r15d
0x1800199ca  mov     rcx, r14
0x1800199cd  call    ReadBytes
0x1800199d2  movzx   edx, ax
0x1800199d5  test    ax, ax
0x1800199d8  jnz     short loc_180019A12
0x1800199da  lea     rax, [rsp+98h+var_68]
0x1800199df  mov     r8d, 10h
0x1800199e5  mov     [rsp+98h+var_70], rax
0x1800199ea  lea     r9, DIRECTORY_CONTROL
0x1800199f1  lea     rdx, [rsp+98h+var_60]
0x1800199f6  mov     [rsp+98h+var_78], r13d
0x1800199fb  mov     rcx, rsi
0x1800199fe  call    WriteGeneric
0x180019a03  movzx   edx, ax
0x180019a06  test    ax, ax
0x180019a09  jnz     short loc_180019A12
0x180019a0b  lea     eax, [rdi+rbx]
0x180019a0e  mov     [r12], eax
0x180019a12  movzx   eax, dx
0x180019a15  jmp     short loc_180019A1C
0x180019a17  mov     eax, 3EEh
0x180019a1c  mov     rcx, [rsp+98h+var_50]
0x180019a21  xor     rcx, rsp; StackCookie
0x180019a24  call    __security_check_cookie
0x180019a29  add     rsp, 58h
0x180019a2d  pop     r15
0x180019a2f  pop     r14
0x180019a31  pop     r13
0x180019a33  pop     r12
0x180019a35  pop     rdi
0x180019a36  pop     rsi
0x180019a37  pop     rbp
0x180019a38  pop     rbx
0x180019a39  retn
```
