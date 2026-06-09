# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x180007b38`
- end: `0x180007be5`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180007dd4`
- `0x1800083ec`
- `0x180008520`
- `0x180008940`
- `0x18000a2a4`
- `0x18000a8a8`
- `0x18000ac08`
- `0x18000be00`
- `0x18000c214`
- `0x18000c740`
- `0x18000de8c`
- `0x18000e284`
- `0x18000eae0`
- `0x18000ee18`
- `0x18000f5c4`
- `0x180010170`
- `0x180010864`

## callees

- `0x1800035e6`
- `0x180007ac0`
- `0x180007b38`
- `0x18000974c`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007b38  push    rbx
0x180007b3a  push    rbp
0x180007b3b  push    rsi
0x180007b3c  push    rdi
0x180007b3d  sub     rsp, 28h
0x180007b41  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007b4b  mov     rbx, r8
0x180007b4e  mov     rbp, rdx
0x180007b51  mov     rsi, rcx
0x180007b54  cmp     r8, rax
0x180007b57  ja      loc_180007BDF
0x180007b5d  cmp     rbx, 7
0x180007b61  ja      short loc_180007B82
0x180007b63  mov     [rcx+10h], rbx
0x180007b67  add     rbx, rbx
0x180007b6a  mov     r8, rbx; Size
0x180007b6d  mov     qword ptr [rcx+18h], 7
0x180007b75  call    memcpy_0
0x180007b7a  xor     eax, eax
0x180007b7c  mov     [rbx+rsi], ax
0x180007b80  jmp     short loc_180007BD6
0x180007b82  mov     rcx, rbx
0x180007b85  or      rcx, 7
0x180007b89  cmp     rcx, rax
0x180007b8c  ja      short loc_180007B9D
0x180007b8e  mov     edx, 0Ah
0x180007b93  mov     rax, rcx
0x180007b96  cmp     rcx, rdx
0x180007b99  cmovb   rax, rdx
0x180007b9d  lea     rdx, [rsp+48h+arg_0]
0x180007ba2  mov     [rsp+48h+arg_0], rax
0x180007ba7  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180007bac  mov     rcx, [rsp+48h+arg_0]
0x180007bb1  mov     rdx, rbp; Src
0x180007bb4  mov     [rsi+10h], rbx
0x180007bb8  mov     rdi, rax
0x180007bbb  mov     [rsi+18h], rcx
0x180007bbf  add     rbx, rbx
0x180007bc2  mov     rcx, rax; void *
0x180007bc5  mov     [rsi], rax
0x180007bc8  mov     r8, rbx; Size
0x180007bcb  call    memcpy_0
0x180007bd0  xor     eax, eax
0x180007bd2  mov     [rbx+rdi], ax
0x180007bd6  add     rsp, 28h
0x180007bda  pop     rdi
0x180007bdb  pop     rsi
0x180007bdc  pop     rbp
0x180007bdd  pop     rbx
0x180007bde  retn
0x180007bdf  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
