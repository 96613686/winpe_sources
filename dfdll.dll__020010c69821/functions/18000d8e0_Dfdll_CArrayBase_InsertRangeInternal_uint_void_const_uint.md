# Dfdll::CArrayBase::InsertRangeInternal(uint,void const *,uint)

- ea: `0x18000d8e0`
- end: `0x18000d9b8`
- name: `?InsertRangeInternal@CArrayBase@Dfdll@@IEAAJIPEBXI@Z`
- size: `216`
- prototype: `int(Dfdll::CArrayBase *__hidden this, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800122cc`

## callees

- `0x18000d500`
- `0x18000d8e0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CArrayBase::InsertRangeInternal(
        Dfdll::CArrayBase *this,
        unsigned int a2,
        const void *a3,
        unsigned int a4)
{
  __int64 result; // rax
  unsigned int v9; // ebx
  __int64 v10; // rax
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF

  if ( !a4 )
    return 0;
  v9 = *((_DWORD *)this + 2);
  if ( a2 > v9 )
    return 2147942487LL;
  result = Dfdll::CArrayBase::GrowArray(this, a4);
  if ( (int)result >= 0 )
  {
    if ( a2 >= v9 )
      goto LABEL_11;
    v10 = *(_QWORD *)this;
    v11[0] = 0;
    result = (*(__int64 (__fastcall **)(Dfdll::CArrayBase *, _QWORD *))(v10 + 40))(this, v11);
    if ( (int)result < 0 )
      return result;
    if ( !v9 )
      return 2147942934LL;
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v11[0] + 56LL))(
               v11[0],
               a2,
               v9 - 1,
               a4,
               2);
    if ( (int)result >= 0 )
    {
LABEL_11:
      result = (*(__int64 (__fastcall **)(Dfdll::CArrayBase *, _QWORD, const void *, _QWORD))(*(_QWORD *)this + 48LL))(
                 this,
                 a2,
                 a3,
                 a4);
      if ( (int)result >= 0 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d8e0  mov     [rsp+arg_0], rbx
0x18000d8e5  mov     [rsp+arg_8], rbp
0x18000d8ea  mov     [rsp+arg_10], rsi
0x18000d8ef  push    rdi
0x18000d8f0  push    r14
0x18000d8f2  push    r15
0x18000d8f4  sub     rsp, 40h
0x18000d8f8  xor     r15d, r15d
0x18000d8fb  mov     ebp, r9d
0x18000d8fe  mov     r14, r8
0x18000d901  mov     esi, edx
0x18000d903  mov     rdi, rcx
0x18000d906  test    r9d, r9d
0x18000d909  jnz     short loc_18000D913
0x18000d90b  mov     eax, r15d
0x18000d90e  jmp     loc_18000D99F
0x18000d913  mov     ebx, [rcx+8]
0x18000d916  cmp     esi, ebx
0x18000d918  jbe     short loc_18000D921
0x18000d91a  mov     eax, 80070057h
0x18000d91f  jmp     short loc_18000D99F
0x18000d921  mov     edx, ebp; unsigned int
0x18000d923  call    ?GrowArray@CArrayBase@Dfdll@@QEAAJI@Z; Dfdll::CArrayBase::GrowArray(uint)
0x18000d928  test    eax, eax
0x18000d92a  js      short loc_18000D99F
0x18000d92c  cmp     esi, ebx
0x18000d92e  jnb     short loc_18000D981
0x18000d930  mov     rax, [rdi]
0x18000d933  lea     rdx, [rsp+58h+var_28]
0x18000d938  mov     rcx, rdi
0x18000d93b  mov     [rsp+58h+var_28], r15
0x18000d940  mov     rax, [rax+28h]
0x18000d944  call    cs:__guard_dispatch_icall_fptr
0x18000d94a  test    eax, eax
0x18000d94c  js      short loc_18000D99F
0x18000d94e  cmp     ebx, 1
0x18000d951  jnb     short loc_18000D95A
0x18000d953  mov     eax, 80070216h
0x18000d958  jmp     short loc_18000D99F
0x18000d95a  lea     r8d, [rbx-1]
0x18000d95e  mov     rcx, [rsp+58h+var_28]
0x18000d963  mov     r9d, ebp
0x18000d966  mov     edx, esi
0x18000d968  mov     [rsp+58h+var_38], 2
0x18000d970  mov     rax, [rcx]
0x18000d973  mov     rax, [rax+38h]
0x18000d977  call    cs:__guard_dispatch_icall_fptr
0x18000d97d  test    eax, eax
0x18000d97f  js      short loc_18000D99F
0x18000d981  mov     rax, [rdi]
0x18000d984  mov     r9d, ebp
0x18000d987  mov     r8, r14
0x18000d98a  mov     edx, esi
0x18000d98c  mov     rcx, rdi
0x18000d98f  mov     rax, [rax+30h]
0x18000d993  call    cs:__guard_dispatch_icall_fptr
0x18000d999  test    eax, eax
0x18000d99b  cmovns  eax, r15d
0x18000d99f  mov     rbx, [rsp+58h+arg_0]
0x18000d9a4  mov     rbp, [rsp+58h+arg_8]
0x18000d9a9  mov     rsi, [rsp+58h+arg_10]
0x18000d9ae  add     rsp, 40h
0x18000d9b2  pop     r15
0x18000d9b4  pop     r14
0x18000d9b6  pop     rdi
0x18000d9b7  retn
```
