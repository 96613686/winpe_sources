# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::insert(unsigned __int64,unsigned __int64,char)

- ea: `0x140015140`
- end: `0x140015201`
- name: `?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0D@Z`
- size: `193`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400127c0`

## callees

- `0x1400014d4`
- `0x140001530`
- `0x140004b18`
- `0x140012540`
- `0x140015140`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400151c7`
- `msvcrt!memmove_s` at `0x1400151c7`

## pseudocode

```c
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
0x140015140  push    rbx
0x140015142  push    rbp
0x140015143  push    rsi
0x140015144  push    rdi
0x140015145  push    r14
0x140015147  push    r15
0x140015149  sub     rsp, 28h
0x14001514d  mov     r15b, r9b
0x140015150  mov     rsi, r8
0x140015153  mov     rbp, rdx
0x140015156  mov     rbx, rcx
0x140015159  cmp     [rcx+18h], rdx
0x14001515d  jnb     short loc_140015164
0x14001515f  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x140015164  mov     rax, [rbx+18h]
0x140015168  not     rax
0x14001516b  cmp     rax, rsi
0x14001516e  ja      short loc_140015175
0x140015170  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x140015175  test    rsi, rsi
0x140015178  jz      short loc_1400151F1
0x14001517a  mov     r14, [rbx+18h]
0x14001517e  xor     r8d, r8d
0x140015181  add     r14, rsi
0x140015184  mov     rcx, rbx
0x140015187  mov     rdx, r14
0x14001518a  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x14001518f  test    al, al
0x140015191  jz      short loc_1400151F1
0x140015193  mov     r9, [rbx+18h]
0x140015197  lea     rdi, [rbx+8]
0x14001519b  mov     rdx, [rbx+20h]
0x14001519f  sub     r9, rbp; SourceSize
0x1400151a2  cmp     rdx, 10h
0x1400151a6  jb      short loc_1400151B0
0x1400151a8  mov     rax, [rdi]
0x1400151ab  mov     rcx, rax
0x1400151ae  jmp     short loc_1400151B6
0x1400151b0  mov     rax, rdi
0x1400151b3  mov     rcx, rdi
0x1400151b6  lea     r8, [rcx+rbp]; Source
0x1400151ba  sub     rdx, rbp
0x1400151bd  lea     rcx, [rax+rbp]
0x1400151c1  sub     rdx, rsi; DestinationSize
0x1400151c4  add     rcx, rsi; Destination
0x1400151c7  call    cs:__imp_memmove_s
0x1400151cd  mov     r9b, r15b
0x1400151d0  mov     r8, rsi
0x1400151d3  mov     rdx, rbp
0x1400151d6  mov     rcx, rbx
0x1400151d9  call    ?_Chassign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0D@Z; std::string::_Chassign(unsigned __int64,unsigned __int64,char)
0x1400151de  cmp     qword ptr [rbx+20h], 10h
0x1400151e3  jb      short loc_1400151E8
0x1400151e5  mov     rdi, [rdi]
0x1400151e8  mov     [rbx+18h], r14
0x1400151ec  mov     byte ptr [r14+rdi], 0
0x1400151f1  mov     rax, rbx
0x1400151f4  add     rsp, 28h
0x1400151f8  pop     r15
0x1400151fa  pop     r14
0x1400151fc  pop     rdi
0x1400151fd  pop     rsi
0x1400151fe  pop     rbp
0x1400151ff  pop     rbx
0x140015200  retn
```
