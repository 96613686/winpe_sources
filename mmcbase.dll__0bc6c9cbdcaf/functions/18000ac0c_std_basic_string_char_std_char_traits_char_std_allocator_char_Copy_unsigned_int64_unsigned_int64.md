# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000ac0c`
- end: `0x18000ace5`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000acec`

## callees

- `0x18000a506`
- `0x18000aaf8`
- `0x18000ac0c`
- `0x18000adac`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ac0c  mov     [rsp+arg_10], r8
0x18000ac11  mov     [rsp+arg_8], rdx
0x18000ac16  mov     [rsp+arg_0], rcx
0x18000ac1b  push    rbx
0x18000ac1c  push    rsi
0x18000ac1d  push    rdi
0x18000ac1e  push    r14
0x18000ac20  sub     rsp, 28h
0x18000ac24  mov     rsi, r8
0x18000ac27  mov     rdi, rdx
0x18000ac2a  mov     rbx, rcx
0x18000ac2d  or      rdx, 0Fh
0x18000ac31  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000ac38  cmp     rdx, r9
0x18000ac3b  ja      short loc_18000AC71
0x18000ac3d  mov     rdi, rdx
0x18000ac40  mov     r8, [rcx+18h]
0x18000ac44  mov     rcx, r8
0x18000ac47  shr     rcx, 1
0x18000ac4a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ac54  mul     rdx
0x18000ac57  shr     rdx, 1
0x18000ac5a  cmp     rcx, rdx
0x18000ac5d  jbe     short loc_18000AC71
0x18000ac5f  mov     rax, r9
0x18000ac62  sub     rax, rcx
0x18000ac65  cmp     r8, rax
0x18000ac68  lea     rdi, [rcx+r8]
0x18000ac6c  jbe     short loc_18000AC71
0x18000ac6e  mov     rdi, r9
0x18000ac71  lea     rcx, [rdi+1]
0x18000ac75  xor     edx, edx
0x18000ac77  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000ac7c  mov     r14, rax
0x18000ac7f  jmp     short loc_18000AC95
0x18000ac81  mov     rbx, [rsp+48h+arg_0]
0x18000ac86  mov     rsi, [rsp+48h+arg_10]
0x18000ac8b  mov     rdi, [rsp+48h+arg_8]
0x18000ac90  mov     r14, [rsp+48h+arg_18]
0x18000ac95  test    rsi, rsi
0x18000ac98  jz      short loc_18000ACB4
0x18000ac9a  cmp     qword ptr [rbx+18h], 10h
0x18000ac9f  jb      short loc_18000ACA6
0x18000aca1  mov     rdx, [rbx]
0x18000aca4  jmp     short loc_18000ACA9
0x18000aca6  mov     rdx, rbx; Src
0x18000aca9  mov     r8, rsi; Size
0x18000acac  mov     rcx, r14; void *
0x18000acaf  call    memcpy_0
0x18000acb4  xor     r8d, r8d
0x18000acb7  mov     dl, 1
0x18000acb9  mov     rcx, rbx
0x18000acbc  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000acc1  mov     [rbx], r14
0x18000acc4  mov     [rbx+18h], rdi
0x18000acc8  mov     rax, rbx
0x18000accb  cmp     rdi, 10h
0x18000accf  cmovnb  rax, r14
0x18000acd3  mov     [rbx+10h], rsi
0x18000acd7  mov     byte ptr [rax+rsi], 0
0x18000acdb  add     rsp, 28h
0x18000acdf  pop     r14
0x18000ace1  pop     rdi
0x18000ace2  pop     rsi
0x18000ace3  pop     rbx
0x18000ace4  retn
```
