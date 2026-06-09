# Dfdll::CVariantArray::AddNewItem(tagVARIANT * &)

- ea: `0x180001f38`
- end: `0x180001fc6`
- name: `?AddNewItem@CVariantArray@Dfdll@@IEAAJAEAPEAUtagVARIANT@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(Dfdll::CVariantArray *__hidden this, struct tagVARIANT **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001e84`
- `0x180005010`
- `0x180005130`

## callees

- `0x180001f38`
- `0x180003a90`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CVariantArray::AddNewItem(Dfdll::CVariantArray *this, struct tagVARIANT **a2)
{
  int v2; // edi
  __int64 result; // rax
  unsigned int v6; // edi
  unsigned int v7; // edx
  __int64 v8; // rdx
  __int64 v9; // rax
  struct tagVARIANT *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 8);
  if ( v2 == -1 )
    return 2147942934LL;
  v6 = v2 + 1;
  v7 = *((_DWORD *)this + 6);
  if ( v7 >= v6 )
  {
LABEL_8:
    v8 = *((unsigned int *)this + 8);
    v9 = *((_QWORD *)this + 1);
    v10 = 0;
    result = (*(__int64 (__fastcall **)(char *, __int64, struct tagVARIANT **))(v9 + 64))((char *)this + 8, v8, &v10);
    if ( (int)result >= 0 )
    {
      *a2 = v10;
      result = 0;
      *((_DWORD *)this + 8) = v6;
    }
    return result;
  }
  if ( v7 > 0xFFFFFFFB )
    return 2147942934LL;
  result = Dfdll::CBufferBase::Reallocate((Dfdll::CVariantArray *)((char *)this + 8), v7 + 4);
  if ( (int)result >= 0 )
  {
    if ( *((_DWORD *)this + 6) < v6 )
      return 2147942413LL;
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x180001f38  mov     [rsp+arg_8], rbx
0x180001f3d  mov     [rsp+arg_10], rsi
0x180001f42  push    rdi
0x180001f43  sub     rsp, 20h
0x180001f47  mov     edi, [rcx+20h]
0x180001f4a  mov     rsi, rdx
0x180001f4d  mov     rbx, rcx
0x180001f50  cmp     edi, 0FFFFFFFEh
0x180001f53  jbe     short loc_180001F5C
0x180001f55  mov     eax, 80070216h
0x180001f5a  jmp     short loc_180001FB6
0x180001f5c  inc     edi
0x180001f5e  mov     edx, [rcx+18h]
0x180001f61  cmp     edx, edi
0x180001f63  jnb     short loc_180001F86
0x180001f65  cmp     edx, 0FFFFFFFBh
0x180001f68  ja      short loc_180001F55
0x180001f6a  add     edx, 4; unsigned int
0x180001f6d  add     rcx, 8; this
0x180001f71  call    ?Reallocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Reallocate(uint)
0x180001f76  test    eax, eax
0x180001f78  js      short loc_180001FB6
0x180001f7a  cmp     [rbx+18h], edi
0x180001f7d  jnb     short loc_180001F86
0x180001f7f  mov     eax, 8007000Dh
0x180001f84  jmp     short loc_180001FB6
0x180001f86  mov     edx, [rbx+20h]
0x180001f89  lea     rcx, [rbx+8]
0x180001f8d  mov     rax, [rcx]
0x180001f90  lea     r8, [rsp+28h+arg_0]
0x180001f95  and     [rsp+28h+arg_0], 0
0x180001f9b  mov     rax, [rax+40h]
0x180001f9f  call    cs:__guard_dispatch_icall_fptr
0x180001fa5  test    eax, eax
0x180001fa7  js      short loc_180001FB6
0x180001fa9  mov     rax, [rsp+28h+arg_0]
0x180001fae  mov     [rsi], rax
0x180001fb1  xor     eax, eax
0x180001fb3  mov     [rbx+20h], edi
0x180001fb6  mov     rbx, [rsp+28h+arg_8]
0x180001fbb  mov     rsi, [rsp+28h+arg_10]
0x180001fc0  add     rsp, 20h
0x180001fc4  pop     rdi
0x180001fc5  retn
```
