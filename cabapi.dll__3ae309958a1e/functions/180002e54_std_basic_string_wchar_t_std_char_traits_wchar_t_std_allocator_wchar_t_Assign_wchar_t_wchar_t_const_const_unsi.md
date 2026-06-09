# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)

- ea: `0x180002e54`
- end: `0x180002f67`
- name: `??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z`
- size: `275`
- prototype: `void **__fastcall(void **, const void *, unsigned __int64)`
- caller_count: `15`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180006d20`
- `0x180008d80`
- `0x180008fd8`
- `0x18000b34c`
- `0x18000b4c0`
- `0x18000b84c`
- `0x18000bcac`
- `0x18000c8e0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d7f0`
- `0x18000e228`
- `0x18000e458`
- `0x1800104d4`

## callees

- `0x180001564`
- `0x180002ddc`
- `0x180002e54`
- `0x18000678c`
- `0x180013df8`
- `0x180013e04`

## pseudocode

```c
void **__fastcall std::wstring::_Assign<wchar_t>(void **a1, const void *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  char *v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rbp
  size_t v15; // rbx
  char *v16; // rax
  unsigned __int64 v17; // rdx
  _BYTE *v18; // rcx
  __int64 v20[7]; // [rsp+20h] [rbp-38h] BYREF

  v3 = (unsigned __int64)a1[3];
  if ( a3 > v3 )
  {
    v9 = 0x7FFFFFFFFFFFFFFELL;
    if ( a3 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v10 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v11 = v3 >> 1;
      if ( v3 <= 0x7FFFFFFFFFFFFFFELL - (v3 >> 1) )
      {
        v9 = v11 + v3;
        if ( v10 >= v11 + v3 )
          v9 = a3 | 7;
      }
    }
    v20[0] = v9;
    v12 = std::wstring::_Allocate_for_capacity<0>(v9, v20);
    v13 = v20[0];
    a1[2] = (void *)a3;
    v14 = v12;
    a1[3] = (void *)v13;
    v15 = 2 * a3;
    memcpy_0(v12, a2, v15);
    *(_WORD *)((char *)v14 + v15) = 0;
    if ( v3 > 7 )
    {
      v16 = (char *)*a1;
      v17 = 2 * v3 + 2;
      if ( v17 < 0x1000 )
      {
        v18 = *a1;
      }
      else
      {
        v18 = (_BYTE *)*((_QWORD *)v16 - 1);
        if ( (unsigned __int64)(v16 - v18 - 8) > 0x1F )
          __fastfail(5u);
        v17 = 2 * v3 + 41;
      }
      operator delete(v18, v17);
    }
    *a1 = v14;
  }
  else
  {
    if ( v3 <= 7 )
      v7 = (char *)a1;
    else
      v7 = (char *)*a1;
    a1[2] = (void *)a3;
    v8 = 2 * a3;
    memmove_0(v7, a2, 2 * a3);
    *(_WORD *)&v7[v8] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180002e54  push    rbx
0x180002e56  push    rbp
0x180002e57  push    rsi
0x180002e58  push    rdi
0x180002e59  push    r14
0x180002e5b  sub     rsp, 30h
0x180002e5f  mov     rsi, [rcx+18h]
0x180002e63  mov     rbx, r8
0x180002e66  mov     r14, rdx
0x180002e69  mov     rdi, rcx
0x180002e6c  cmp     r8, rsi
0x180002e6f  ja      short loc_180002E9C
0x180002e71  cmp     rsi, 7
0x180002e75  jbe     short loc_180002E7C
0x180002e77  mov     rsi, [rcx]
0x180002e7a  jmp     short loc_180002E7F
0x180002e7c  mov     rsi, rdi
0x180002e7f  mov     [rcx+10h], rbx
0x180002e83  add     rbx, rbx
0x180002e86  mov     r8, rbx; Size
0x180002e89  mov     rcx, rsi; void *
0x180002e8c  call    memmove_0
0x180002e91  xor     eax, eax
0x180002e93  mov     [rbx+rsi], ax
0x180002e97  jmp     loc_180002F53
0x180002e9c  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180002ea6  cmp     rbx, rcx
0x180002ea9  ja      loc_180002F61
0x180002eaf  mov     rdx, rbx
0x180002eb2  or      rdx, 7
0x180002eb6  cmp     rdx, rcx
0x180002eb9  ja      short loc_180002ED7
0x180002ebb  mov     r8, rsi
0x180002ebe  mov     rax, rcx
0x180002ec1  shr     r8, 1
0x180002ec4  sub     rax, r8
0x180002ec7  cmp     rsi, rax
0x180002eca  ja      short loc_180002ED7
0x180002ecc  lea     rcx, [r8+rsi]
0x180002ed0  cmp     rdx, rcx
0x180002ed3  cmovnb  rcx, rdx
0x180002ed7  lea     rdx, [rsp+58h+var_38]
0x180002edc  mov     [rsp+58h+var_38], rcx
0x180002ee1  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180002ee6  mov     rcx, [rsp+58h+var_38]
0x180002eeb  mov     rdx, r14; Src
0x180002eee  mov     [rdi+10h], rbx
0x180002ef2  mov     rbp, rax
0x180002ef5  mov     [rdi+18h], rcx
0x180002ef9  add     rbx, rbx
0x180002efc  mov     rcx, rax; void *
0x180002eff  mov     r8, rbx; Size
0x180002f02  call    memcpy_0
0x180002f07  xor     eax, eax
0x180002f09  mov     [rbx+rbp], ax
0x180002f0d  cmp     rsi, 7
0x180002f11  jbe     short loc_180002F4D
0x180002f13  mov     rax, [rdi]
0x180002f16  lea     rdx, ds:2[rsi*2]; unsigned __int64
0x180002f1e  cmp     rdx, 1000h
0x180002f25  jb      short loc_180002F45
0x180002f27  mov     rcx, [rax-8]
0x180002f2b  sub     rax, rcx
0x180002f2e  sub     rax, 8
0x180002f32  cmp     rax, 1Fh
0x180002f36  ja      short loc_180002F3E
0x180002f38  add     rdx, 27h ; '''
0x180002f3c  jmp     short loc_180002F48
0x180002f3e  mov     ecx, 5
0x180002f43  int     29h; Win8: RtlFailFast(ecx)
0x180002f45  mov     rcx, rax; void *
0x180002f48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002f4d  mov     rax, rdi
0x180002f50  mov     [rax], rbp
0x180002f53  mov     rax, rdi
0x180002f56  add     rsp, 30h
0x180002f5a  pop     r14
0x180002f5c  pop     rdi
0x180002f5d  pop     rsi
0x180002f5e  pop     rbp
0x180002f5f  pop     rbx
0x180002f60  retn
0x180002f61  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
