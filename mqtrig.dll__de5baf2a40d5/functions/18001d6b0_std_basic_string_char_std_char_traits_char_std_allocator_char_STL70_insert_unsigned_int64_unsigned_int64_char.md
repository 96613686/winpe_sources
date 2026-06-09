# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::insert(unsigned __int64,unsigned __int64,char)

- ea: `0x18001d6b0`
- end: `0x18001d771`
- name: `?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0D@Z`
- size: `193`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ab60`

## callees

- `0x1800011d4`
- `0x180001230`
- `0x180003d50`
- `0x18001a8dc`
- `0x18001d6b0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d737`
- `msvcrt!memmove_s` at `0x18001d737`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::string::insert(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3, char a4)
{
  unsigned __int64 v8; // r14
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // r9

  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  if ( ~a1[3] <= a3 )
    std::_String_base::_Xlen();
  if ( a3 )
  {
    v8 = a3 + a1[3];
    if ( (unsigned __int8)std::string::_Grow(a1, v8, 0) )
    {
      v9 = a1 + 1;
      v10 = a1[4];
      if ( v10 < 0x10 )
      {
        v11 = a1 + 1;
        v12 = a1 + 1;
      }
      else
      {
        v11 = (_QWORD *)*v9;
        v12 = (_QWORD *)*v9;
      }
      memmove_s((char *)v11 + a2 + a3, v10 - a2 - a3, (char *)v12 + a2, a1[3] - a2);
      LOBYTE(v13) = a4;
      std::string::_Chassign(a1, a2, a3, v13);
      if ( a1[4] >= 0x10u )
        v9 = (_QWORD *)*v9;
      a1[3] = v8;
      *((_BYTE *)v9 + v8) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001d6b0  push    rbx
0x18001d6b2  push    rbp
0x18001d6b3  push    rsi
0x18001d6b4  push    rdi
0x18001d6b5  push    r14
0x18001d6b7  push    r15
0x18001d6b9  sub     rsp, 28h
0x18001d6bd  mov     r15b, r9b
0x18001d6c0  mov     rsi, r8
0x18001d6c3  mov     rbp, rdx
0x18001d6c6  mov     rbx, rcx
0x18001d6c9  cmp     [rcx+18h], rdx
0x18001d6cd  jnb     short loc_18001D6D4
0x18001d6cf  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18001d6d4  mov     rax, [rbx+18h]
0x18001d6d8  not     rax
0x18001d6db  cmp     rax, rsi
0x18001d6de  ja      short loc_18001D6E5
0x18001d6e0  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18001d6e5  test    rsi, rsi
0x18001d6e8  jz      short loc_18001D761
0x18001d6ea  mov     r14, [rbx+18h]
0x18001d6ee  xor     r8d, r8d
0x18001d6f1  add     r14, rsi
0x18001d6f4  mov     rcx, rbx
0x18001d6f7  mov     rdx, r14
0x18001d6fa  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x18001d6ff  test    al, al
0x18001d701  jz      short loc_18001D761
0x18001d703  mov     r9, [rbx+18h]
0x18001d707  lea     rdi, [rbx+8]
0x18001d70b  mov     rdx, [rbx+20h]
0x18001d70f  sub     r9, rbp; SourceSize
0x18001d712  cmp     rdx, 10h
0x18001d716  jb      short loc_18001D720
0x18001d718  mov     rax, [rdi]
0x18001d71b  mov     rcx, rax
0x18001d71e  jmp     short loc_18001D726
0x18001d720  mov     rax, rdi
0x18001d723  mov     rcx, rdi
0x18001d726  lea     r8, [rcx+rbp]; Source
0x18001d72a  sub     rdx, rbp
0x18001d72d  lea     rcx, [rax+rbp]
0x18001d731  sub     rdx, rsi; DestinationSize
0x18001d734  add     rcx, rsi; Destination
0x18001d737  call    cs:__imp_memmove_s
0x18001d73d  mov     r9b, r15b
0x18001d740  mov     r8, rsi
0x18001d743  mov     rdx, rbp
0x18001d746  mov     rcx, rbx
0x18001d749  call    ?_Chassign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0D@Z; std::string::_Chassign(unsigned __int64,unsigned __int64,char)
0x18001d74e  cmp     qword ptr [rbx+20h], 10h
0x18001d753  jb      short loc_18001D758
0x18001d755  mov     rdi, [rdi]
0x18001d758  mov     [rbx+18h], r14
0x18001d75c  mov     byte ptr [r14+rdi], 0
0x18001d761  mov     rax, rbx
0x18001d764  add     rsp, 28h
0x18001d768  pop     r15
0x18001d76a  pop     r14
0x18001d76c  pop     rdi
0x18001d76d  pop     rsi
0x18001d76e  pop     rbp
0x18001d76f  pop     rbx
0x18001d770  retn
```
