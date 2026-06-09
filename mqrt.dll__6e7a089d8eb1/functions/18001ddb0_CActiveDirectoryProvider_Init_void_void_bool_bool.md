# CActiveDirectoryProvider::Init(void (*)(void),bool,bool)

- ea: `0x18001ddb0`
- end: `0x18001dde9`
- name: `?Init@CActiveDirectoryProvider@@UEAAJP6AXXZ_N1@Z`
- size: `57`
- prototype: `__int64 __fastcall(CActiveDirectoryProvider *__hidden this, void (*)(void), bool, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001ddb0`
- `0x18001ddf0`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall CActiveDirectoryProvider::Init(CActiveDirectoryProvider *this, void (*a2)(void), char a3, char a4)
{
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // r8

  result = CActiveDirectoryProvider::LoadDll(this);
  if ( (int)result >= 0 )
  {
    LOBYTE(v10) = a4;
    LOBYTE(v9) = a3;
    return (*((__int64 (__fastcall **)(void (*)(void), __int64, __int64))this + 11))(a2, v9, v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001ddb0  push    rbx
0x18001ddb2  push    rbp
0x18001ddb3  push    rsi
0x18001ddb4  push    rdi
0x18001ddb5  sub     rsp, 28h
0x18001ddb9  mov     dil, r9b
0x18001ddbc  mov     sil, r8b
0x18001ddbf  mov     rbp, rdx
0x18001ddc2  mov     rbx, rcx
0x18001ddc5  call    ?LoadDll@CActiveDirectoryProvider@@AEAAJXZ; CActiveDirectoryProvider::LoadDll(void)
0x18001ddca  test    eax, eax
0x18001ddcc  js      short loc_18001DDE0
0x18001ddce  mov     rax, [rbx+58h]
0x18001ddd2  mov     r8b, dil
0x18001ddd5  mov     dl, sil
0x18001ddd8  mov     rcx, rbp
0x18001dddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dde0  add     rsp, 28h
0x18001dde4  pop     rdi
0x18001dde5  pop     rsi
0x18001dde6  pop     rbp
0x18001dde7  pop     rbx
0x18001dde8  retn
```
