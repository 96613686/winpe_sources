# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000ad08`
- end: `0x18000ae17`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64 *, const void *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800092dc`
- `0x18000946c`
- `0x180009e04`

## callees

- `0x18000374c`
- `0x18000aad8`
- `0x18000ad08`
- `0x180011010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ade1`
- `msvcrt!memcpy_s` at `0x18000ade1`
- `msvcrt!memmove_s` at `0x18000add6`
- `msvcrt!memmove_s` at `0x18000add6`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  volatile signed __int32 *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rbp
  char *v11; // rcx
  rsize_t v12; // r9
  rsize_t v13; // rdx

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      goto LABEL_20;
    v9 = *(unsigned int *)(*a1 - 16);
    v10 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v11 = (char *)*a1;
    v12 = 2 * v3;
    v13 = 2 * v3;
    if ( v10 > v9 )
      memcpy_s(v11, v13, a2, v12);
    else
      memmove_s(v11, v13, &v11[2 * v10], v12);
    if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
LABEL_20:
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a1 - 16) = v3;
    result = 0;
    *(_WORD *)(2 * v3 + *a1) = 0;
  }
  else
  {
    result = *a1;
    v7 = (volatile signed __int32 *)(*a1 - 24);
    if ( *((_DWORD *)v7 + 2) )
    {
      if ( *((int *)v7 + 4) >= 0 )
      {
        v8 = *(_QWORD *)v7;
        if ( _InterlockedExchangeAdd(v7 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24;
        *a1 = result;
      }
      else
      {
        if ( *(int *)(result - 12) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(result - 16) = 0;
        result = 0;
        *(_WORD *)*a1 = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad08  push    rbx
0x18000ad0a  push    rbp
0x18000ad0b  push    rsi
0x18000ad0c  push    rdi
0x18000ad0d  push    r14
0x18000ad0f  push    r15
0x18000ad11  sub     rsp, 28h
0x18000ad15  movsxd  rdi, r8d
0x18000ad18  mov     r14, rdx
0x18000ad1b  mov     rbx, rcx
0x18000ad1e  test    r8d, r8d
0x18000ad21  jnz     short loc_18000AD90
0x18000ad23  mov     rax, [rcx]
0x18000ad26  lea     rdx, [rax-18h]
0x18000ad2a  cmp     [rdx+8], r8d
0x18000ad2e  jz      short loc_18000AD83
0x18000ad30  cmp     [rdx+10h], r8d
0x18000ad34  jge     short loc_18000AD4E
0x18000ad36  cmp     [rax-0Ch], r8d
0x18000ad3a  jl      loc_18000AE01
0x18000ad40  mov     [rax-10h], r8d
0x18000ad44  mov     rcx, [rcx]
0x18000ad47  xor     eax, eax
0x18000ad49  mov     [rcx], ax
0x18000ad4c  jmp     short loc_18000AD83
0x18000ad4e  mov     rdi, [rdx]
0x18000ad51  or      eax, 0FFFFFFFFh
0x18000ad54  lock xadd [rdx+10h], eax
0x18000ad59  sub     eax, 1
0x18000ad5c  jg      short loc_18000AD6D
0x18000ad5e  mov     rcx, [rdx]
0x18000ad61  mov     rax, [rcx]
0x18000ad64  mov     rax, [rax+8]
0x18000ad68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad6d  mov     rax, [rdi]
0x18000ad70  mov     rcx, rdi
0x18000ad73  mov     rax, [rax+18h]
0x18000ad77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7c  add     rax, 18h
0x18000ad80  mov     [rbx], rax
0x18000ad83  add     rsp, 28h
0x18000ad87  pop     r15
0x18000ad89  pop     r14
0x18000ad8b  pop     rdi
0x18000ad8c  pop     rsi
0x18000ad8d  pop     rbp
0x18000ad8e  pop     rbx
0x18000ad8f  retn
0x18000ad90  test    r14, r14
0x18000ad93  jz      short loc_18000AE0C
0x18000ad95  mov     rax, [rcx]
0x18000ad98  mov     r15d, [rax-10h]
0x18000ad9c  mov     rbp, r14
0x18000ad9f  sub     rbp, rax
0x18000ada2  sar     rbp, 1
0x18000ada5  mov     ecx, 1
0x18000adaa  sub     ecx, [rax-8]
0x18000adad  mov     eax, [rax-0Ch]
0x18000adb0  sub     eax, edi
0x18000adb2  or      ecx, eax
0x18000adb4  jge     short loc_18000ADC0
0x18000adb6  mov     edx, edi
0x18000adb8  mov     rcx, rbx
0x18000adbb  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000adc0  mov     rcx, [rbx]; Destination
0x18000adc3  lea     rsi, [rdi+rdi]
0x18000adc7  mov     r9, rsi; SourceSize
0x18000adca  mov     rdx, rsi; DestinationSize
0x18000adcd  cmp     rbp, r15
0x18000add0  ja      short loc_18000ADDE
0x18000add2  lea     r8, [rcx+rbp*2]; Source
0x18000add6  call    cs:__imp_memmove_s
0x18000addc  jmp     short loc_18000ADE7
0x18000adde  mov     r8, r14; Source
0x18000ade1  call    cs:__imp_memcpy_s
0x18000ade7  test    edi, edi
0x18000ade9  js      short loc_18000AE0C
0x18000adeb  mov     rax, [rbx]
0x18000adee  cmp     edi, [rax-0Ch]
0x18000adf1  jg      short loc_18000AE0C
0x18000adf3  mov     [rax-10h], edi
0x18000adf6  mov     rcx, [rbx]
0x18000adf9  xor     eax, eax
0x18000adfb  mov     [rsi+rcx], ax
0x18000adff  jmp     short loc_18000AD83
0x18000ae01  mov     ecx, 80070057h; int
0x18000ae06  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ae0c  mov     ecx, 80070057h; int
0x18000ae11  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
