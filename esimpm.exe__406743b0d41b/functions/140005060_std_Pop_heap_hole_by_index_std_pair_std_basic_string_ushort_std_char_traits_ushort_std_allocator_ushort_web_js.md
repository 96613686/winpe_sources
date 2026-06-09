# std::_Pop_heap_hole_by_index<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &)>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,__int64,__int64,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> &&,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &))

- ea: `0x140005060`
- end: `0x1400052ae`
- name: `??$_Pop_heap_hole_by_index@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@U12@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@_J1$$QEAU10@P6A_NAEBU10@3@Z@Z`
- size: `590`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, __int64, unsigned __int8 (__fastcall *)(__int64, __int64))`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400057b0`
- `0x140005960`

## callees

- `0x140003244`
- `0x1400041b0`
- `0x140005060`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 (__fastcall *a5)(__int64, __int64))
{
  __int64 v5; // rbx
  __int64 v7; // rdi
  __int64 v8; // rbp
  __int64 v11; // r14
  __int64 v12; // rbx
  __int64 v13; // rsi
  _QWORD *v14; // rbx
  unsigned __int64 v15; // rdx
  char *v16; // rax
  char *v17; // rcx
  __int64 *v18; // rdx
  __int64 *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rsi
  _QWORD *v23; // rbx
  unsigned __int64 v24; // rdx
  char *v25; // rax
  char *v26; // rcx
  __int64 *v27; // rsi
  __int64 *v28; // rbx
  __int64 v29; // rcx

  v5 = a3 - 1;
  v7 = a2;
  v8 = (a3 - 1) >> 1;
  v11 = a2;
  if ( a2 < v8 )
  {
    do
    {
      v12 = 2 * v11 + 2;
      v11 = 2 * v11 + 1;
      if ( !a5(a1 + 40 * v12, a1 - 40 + 40 * v12) )
        v11 = v12;
      v13 = a1 + 40 * v11;
      v14 = (_QWORD *)(a1 + 40 * v7);
      if ( v14 != (_QWORD *)v13 )
      {
        v15 = v14[3];
        if ( v15 > 7 )
        {
          v16 = (char *)*v14;
          if ( 2 * v15 + 2 < 0x1000 )
          {
            v17 = (char *)*v14;
          }
          else
          {
            v17 = (char *)*((_QWORD *)v16 - 1);
            if ( (unsigned __int64)(v16 - v17 - 8) > 0x1F )
LABEL_33:
              __fastfail(5u);
          }
          operator delete(v17);
        }
        v14[3] = 7;
        v14[2] = 0;
        *(_WORD *)v14 = 0;
        *(_OWORD *)v14 = *(_OWORD *)v13;
        *((_OWORD *)v14 + 1) = *(_OWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 7;
        *(_WORD *)v13 = 0;
      }
      v18 = (__int64 *)(v13 + 32);
      v19 = v14 + 4;
      if ( v19 != (__int64 *)(v13 + 32) )
      {
        v20 = *v19;
        *v19 = *v18;
        *v18 = v20;
      }
      v7 = v11;
    }
    while ( v11 < v8 );
    v5 = a3 - 1;
  }
  if ( v11 == v8 && (a3 & 1) == 0 )
  {
    std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(
      (_QWORD *)(a1 + 40 * v7),
      a1 + 40 * (a3 - 1));
    v7 = v5;
  }
  if ( a2 < v7 )
  {
    do
    {
      v21 = (v7 - 1) >> 1;
      v22 = a1 + 40 * v21;
      if ( !a5(v22, a4) )
        break;
      v23 = (_QWORD *)(a1 + 40 * v7);
      if ( v23 != (_QWORD *)v22 )
      {
        v24 = v23[3];
        if ( v24 > 7 )
        {
          v25 = (char *)*v23;
          if ( 2 * v24 + 2 < 0x1000 )
          {
            v26 = (char *)*v23;
          }
          else
          {
            v26 = (char *)*((_QWORD *)v25 - 1);
            if ( (unsigned __int64)(v25 - v26 - 8) > 0x1F )
              goto LABEL_33;
          }
          operator delete(v26);
        }
        v23[3] = 7;
        v23[2] = 0;
        *(_WORD *)v23 = 0;
        *(_OWORD *)v23 = *(_OWORD *)v22;
        *((_OWORD *)v23 + 1) = *(_OWORD *)(v22 + 16);
        *(_QWORD *)(v22 + 16) = 0;
        *(_QWORD *)(v22 + 24) = 7;
        *(_WORD *)v22 = 0;
      }
      v27 = (__int64 *)(v22 + 32);
      v28 = v23 + 4;
      if ( v28 != v27 )
      {
        v29 = *v28;
        *v28 = *v27;
        *v27 = v29;
      }
      v7 = (v7 - 1) >> 1;
    }
    while ( a2 < v21 );
  }
  return std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(
           (_QWORD *)(a1 + 40 * v7),
           a4);
}

```

## disassembly

```asm
0x140005060  mov     [rsp+arg_18], r9
0x140005065  push    rbx
0x140005066  push    rbp
0x140005067  push    rsi
0x140005068  push    rdi
0x140005069  push    r12
0x14000506b  push    r13
0x14000506d  push    r14
0x14000506f  push    r15
0x140005071  sub     rsp, 28h
0x140005075  lea     rbx, [r8-1]
0x140005079  mov     r12, r8
0x14000507c  mov     rbp, rbx
0x14000507f  mov     rdi, rdx
0x140005082  sar     rbp, 1
0x140005085  mov     r15, rcx
0x140005088  mov     r13, rdx
0x14000508b  mov     r14, rdx
0x14000508e  cmp     rdx, rbp
0x140005091  jge     loc_140005180
0x140005097  nop     word ptr [rax+rax+00000000h]
0x1400050a0  lea     rbx, ds:2[r14*2]
0x1400050a8  lea     rax, [rbx+rbx*4]
0x1400050ac  lea     rcx, [r15+rax*8]
0x1400050b0  lea     rdx, [r15-28h]
0x1400050b4  lea     rdx, [rdx+rax*8]
0x1400050b8  mov     rax, [rsp+68h+arg_20]
0x1400050c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050c5  test    al, al
0x1400050c7  lea     r14, [rbx-1]
0x1400050cb  cmovz   r14, rbx
0x1400050cf  lea     rax, [r14+r14*4]
0x1400050d3  lea     rsi, [r15+rax*8]
0x1400050d7  lea     rax, [rdi+rdi*4]
0x1400050db  lea     rbx, [r15+rax*8]
0x1400050df  cmp     rbx, rsi
0x1400050e2  jz      short loc_140005156
0x1400050e4  mov     rdx, [rbx+18h]
0x1400050e8  cmp     rdx, 7
0x1400050ec  jbe     short loc_140005125
0x1400050ee  mov     rax, [rbx]
0x1400050f1  lea     rdx, ds:2[rdx*2]
0x1400050f9  cmp     rdx, 1000h
0x140005100  jb      short loc_14000511D
0x140005102  mov     rcx, [rax-8]
0x140005106  sub     rax, rcx
0x140005109  sub     rax, 8
0x14000510d  cmp     rax, 1Fh
0x140005111  ja      loc_1400052A7
0x140005117  add     rdx, 27h ; '''
0x14000511b  jmp     short loc_140005120
0x14000511d  mov     rcx, rax; Block
0x140005120  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005125  mov     qword ptr [rbx+18h], 7
0x14000512d  xor     r8d, r8d
0x140005130  mov     [rbx+10h], r8
0x140005134  mov     [rbx], r8w
0x140005138  movups  xmm0, xmmword ptr [rsi]
0x14000513b  movups  xmmword ptr [rbx], xmm0
0x14000513e  movups  xmm1, xmmword ptr [rsi+10h]
0x140005142  movups  xmmword ptr [rbx+10h], xmm1
0x140005146  mov     [rsi+10h], r8
0x14000514a  mov     qword ptr [rsi+18h], 7
0x140005152  mov     [rsi], r8w
0x140005156  lea     rdx, [rsi+20h]
0x14000515a  add     rbx, 20h ; ' '
0x14000515e  cmp     rbx, rdx
0x140005161  jz      short loc_14000516F
0x140005163  mov     rax, [rdx]
0x140005166  mov     rcx, [rbx]
0x140005169  mov     [rbx], rax
0x14000516c  mov     [rdx], rcx
0x14000516f  mov     rdi, r14
0x140005172  cmp     r14, rbp
0x140005175  jl      loc_1400050A0
0x14000517b  lea     rbx, [r12-1]
0x140005180  cmp     r14, rbp
0x140005183  jnz     short loc_1400051A8
0x140005185  test    r12b, 1
0x140005189  jnz     short loc_1400051A8
0x14000518b  lea     rax, [r12-1]
0x140005190  lea     rax, [rax+rax*4]
0x140005194  lea     rdx, [r15+rax*8]
0x140005198  lea     rax, [rdi+rdi*4]
0x14000519c  lea     rcx, [r15+rax*8]
0x1400051a0  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(std::pair<std::wstring,web::json::value> &&)
0x1400051a5  mov     rdi, rbx
0x1400051a8  mov     r12, [rsp+68h+arg_18]
0x1400051b0  cmp     r13, rdi
0x1400051b3  jge     loc_140005287
0x1400051b9  mov     rbp, [rsp+68h+arg_20]
0x1400051c1  lea     r14, [rdi-1]
0x1400051c5  mov     rdx, r12
0x1400051c8  sar     r14, 1
0x1400051cb  lea     rax, [r14+r14*4]
0x1400051cf  lea     rsi, [r15+rax*8]
0x1400051d3  mov     rax, rbp
0x1400051d6  mov     rcx, rsi
0x1400051d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051de  test    al, al
0x1400051e0  jz      loc_140005287
0x1400051e6  lea     rax, [rdi+rdi*4]
0x1400051ea  lea     rbx, [r15+rax*8]
0x1400051ee  cmp     rbx, rsi
0x1400051f1  jz      short loc_140005262
0x1400051f3  mov     rdx, [rbx+18h]
0x1400051f7  cmp     rdx, 7
0x1400051fb  jbe     short loc_140005234
0x1400051fd  mov     rax, [rbx]
0x140005200  lea     rdx, ds:2[rdx*2]
0x140005208  cmp     rdx, 1000h
0x14000520f  jb      short loc_14000522C
0x140005211  mov     rcx, [rax-8]
0x140005215  sub     rax, rcx
0x140005218  sub     rax, 8
0x14000521c  cmp     rax, 1Fh
0x140005220  ja      loc_1400052A7
0x140005226  add     rdx, 27h ; '''
0x14000522a  jmp     short loc_14000522F
0x14000522c  mov     rcx, rax; Block
0x14000522f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005234  mov     qword ptr [rbx+18h], 7
0x14000523c  xor     ecx, ecx
0x14000523e  mov     [rbx+10h], rcx
0x140005242  mov     [rbx], cx
0x140005245  movups  xmm0, xmmword ptr [rsi]
0x140005248  movups  xmmword ptr [rbx], xmm0
0x14000524b  movups  xmm1, xmmword ptr [rsi+10h]
0x14000524f  movups  xmmword ptr [rbx+10h], xmm1
0x140005253  mov     [rsi+10h], rcx
0x140005257  mov     qword ptr [rsi+18h], 7
0x14000525f  mov     [rsi], cx
0x140005262  add     rsi, 20h ; ' '
0x140005266  add     rbx, 20h ; ' '
0x14000526a  cmp     rbx, rsi
0x14000526d  jz      short loc_14000527B
0x14000526f  mov     rax, [rsi]
0x140005272  mov     rcx, [rbx]
0x140005275  mov     [rbx], rax
0x140005278  mov     [rsi], rcx
0x14000527b  mov     rdi, r14
0x14000527e  cmp     r13, r14
0x140005281  jl      loc_1400051C1
0x140005287  lea     rax, [rdi+rdi*4]
0x14000528b  mov     rdx, r12
0x14000528e  lea     rcx, [r15+rax*8]
0x140005292  add     rsp, 28h
0x140005296  pop     r15
0x140005298  pop     r14
0x14000529a  pop     r13
0x14000529c  pop     r12
0x14000529e  pop     rdi
0x14000529f  pop     rsi
0x1400052a0  pop     rbp
0x1400052a1  pop     rbx
0x1400052a2  jmp     ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(std::pair<std::wstring,web::json::value> &&)
0x1400052a7  mov     ecx, 5
0x1400052ac  int     29h; Win8: RtlFailFast(ecx)
```
