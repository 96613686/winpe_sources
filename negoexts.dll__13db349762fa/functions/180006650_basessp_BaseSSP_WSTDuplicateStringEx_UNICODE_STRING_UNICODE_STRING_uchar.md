# basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)

- ea: `0x180006650`
- end: `0x180006763`
- name: `?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z`
- size: `275`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012dc`
- `0x180004404`
- `0x180005998`
- `0x180005bc0`
- `0x1800063e4`
- `0x18000676c`
- `0x18000d388`
- `0x180018964`
- `0x18001d92c`
- `0x18001e134`

## callees

- `0x180006650`
- `0x18001ece2`
- `0x18001ecee`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTDuplicateStringEx(
        basessp::BaseSSP *this,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  int Length; // eax
  __int64 result; // rax
  size_t v7; // rbp
  WCHAR *v8; // rsi
  WCHAR *v9; // rax

  if ( !a3 || !a3->Buffer )
  {
    a2->Buffer = 0;
    result = 0;
    *(_DWORD *)&a2->Length = 0;
    return result;
  }
  Length = a3->Length;
  if ( (unsigned __int16)Length > 0xFFFCu )
  {
    result = 3221225734LL;
    a2->Buffer = 0;
    return result;
  }
  v7 = (unsigned int)(Length + 2);
  if ( *((_DWORD *)this + 52) == 1 )
  {
    v8 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 30) + 384LL))((unsigned int)v7);
  }
  else
  {
    v9 = (WCHAR *)(**((__int64 (__fastcall ***)(_QWORD))this + 31))((unsigned int)v7);
    v8 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, v7);
      a2->Buffer = v8;
      goto LABEL_6;
    }
  }
  a2->Buffer = v8;
  if ( !v8 )
    return 3221225626LL;
LABEL_6:
  a2->Length = a3->Length;
  a2->MaximumLength = v7;
  memcpy_0(v8, a3->Buffer, a3->Length);
  a2->Buffer[(unsigned __int64)a3->Length >> 1] = 0;
  return 0;
}

```

## disassembly

```asm
0x180006650  mov     [rsp+arg_10], rbx
0x180006655  push    rdi
0x180006656  sub     rsp, 20h
0x18000665a  mov     rbx, r8
0x18000665d  mov     rdi, rdx
0x180006660  test    r8, r8
0x180006663  jz      short loc_1800066DE
0x180006665  cmp     qword ptr [r8+8], 0
0x18000666a  jz      short loc_1800066DE
0x18000666c  movzx   eax, word ptr [r8]
0x180006670  mov     edx, 0FFFCh
0x180006675  cmp     ax, dx
0x180006678  jbe     short loc_1800066F3
0x18000667a  xor     edx, edx
0x18000667c  mov     eax, 0C0000106h
0x180006681  mov     [rdi+8], rdx
0x180006685  mov     rbx, [rsp+28h+arg_10]
0x18000668a  add     rsp, 20h
0x18000668e  pop     rdi
0x18000668f  retn
0x180006690  mov     [rdi+8], rsi
0x180006694  test    rsi, rsi
0x180006697  jz      loc_180006759
0x18000669d  movzx   eax, word ptr [rbx]
0x1800066a0  mov     rcx, rsi; void *
0x1800066a3  mov     [rdi], ax
0x1800066a6  mov     [rdi+2], bp
0x1800066aa  movzx   r8d, word ptr [rbx]; Size
0x1800066ae  mov     rdx, [rbx+8]; Src
0x1800066b2  call    memcpy_0
0x1800066b7  movzx   ecx, word ptr [rbx]
0x1800066ba  xor     edx, edx
0x1800066bc  mov     rax, [rdi+8]
0x1800066c0  shr     rcx, 1
0x1800066c3  mov     [rax+rcx*2], dx
0x1800066c7  xor     eax, eax
0x1800066c9  mov     rbp, [rsp+28h+arg_0]
0x1800066ce  mov     rsi, [rsp+28h+arg_8]
0x1800066d3  mov     rbx, [rsp+28h+arg_10]
0x1800066d8  add     rsp, 20h
0x1800066dc  pop     rdi
0x1800066dd  retn
0x1800066de  mov     rbx, [rsp+28h+arg_10]
0x1800066e3  xor     edx, edx
0x1800066e5  mov     [rdi+8], rdx
0x1800066e9  xor     eax, eax
0x1800066eb  mov     [rdi], edx
0x1800066ed  add     rsp, 20h
0x1800066f1  pop     rdi
0x1800066f2  retn
0x1800066f3  mov     [rsp+28h+arg_0], rbp
0x1800066f8  lea     ebp, [rax+2]
0x1800066fb  mov     [rsp+28h+arg_8], rsi
0x180006700  cmp     dword ptr [rcx+0D0h], 1
0x180006707  jnz     short loc_180006726
0x180006709  mov     rax, [rcx+0F0h]
0x180006710  mov     ecx, ebp
0x180006712  mov     rax, [rax+180h]
0x180006719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671e  mov     rsi, rax
0x180006721  jmp     loc_180006690
0x180006726  mov     rax, [rcx+0F8h]
0x18000672d  mov     ecx, ebp
0x18000672f  mov     rax, [rax]
0x180006732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006737  mov     rsi, rax
0x18000673a  test    rax, rax
0x18000673d  jz      loc_180006690
0x180006743  mov     r8, rbp; Size
0x180006746  xor     edx, edx; Val
0x180006748  mov     rcx, rax; void *
0x18000674b  call    memset_0
0x180006750  mov     [rdi+8], rsi
0x180006754  jmp     loc_18000669D
0x180006759  mov     eax, 0C000009Ah
0x18000675e  jmp     loc_1800066C9
```
