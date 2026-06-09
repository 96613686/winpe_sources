# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180002044`
- end: `0x1800022e9`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180001b2c`

## callees

- `0x180002044`
- `0x1800022f0`
- `0x180002630`
- `0x18000265c`
- `0x180002b00`
- `0x180002b2c`
- `0x180007830`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  unsigned __int64 v25; // r8
  char *v26; // rdx
  char *v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // r15
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // r14
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  _QWORD *v41; // rdx
  unsigned __int64 v43; // [rsp+70h] [rbp+8h]

  v7 = a4;
  v8 = a1[2];
  v9 = a3;
  if ( v8 < a2 || (v11 = a4[2], v12 = a5, v11 < a5) )
    std::_Xout_of_range("invalid string position");
  v13 = a6;
  if ( v8 - a2 < a3 )
    v9 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v13 = v14;
  if ( ~v13 <= v8 - v9 )
    std::_Xlength_error("string too long");
  v15 = v8 - a2 - v9;
  v16 = v13 - v9;
  v43 = v8 + v13 - v9;
  if ( v8 < v43 )
    std::wstring::_Grow(a1, v8 + v13 - v9, 0);
  v17 = a1[3];
  if ( a1 == v7 )
  {
    if ( v13 > v9 )
    {
      if ( a5 > a2 )
      {
        v32 = a2 + v9;
        if ( a2 + v9 > a5 )
        {
          if ( v17 < 8 )
          {
            v35 = a1;
            v36 = a1;
          }
          else
          {
            v35 = (_QWORD *)*a1;
            v36 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v35 + 2 * a2, (char *)v36 + 2 * a5, v9);
          v37 = 2 * v32;
          if ( a1[3] < 8u )
          {
            v39 = a1;
            v38 = a1;
          }
          else
          {
            v38 = (_QWORD *)*a1;
            v39 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v39 + 2 * a2 + 2 * v13, (char *)v38 + v37, v15);
          if ( a1[3] < 8u )
          {
            v40 = a1;
            v41 = a1;
          }
          else
          {
            v40 = (_QWORD *)*a1;
            v41 = (_QWORD *)*a1;
          }
          v27 = (char *)v40 + v37;
          v26 = (char *)v41 + 2 * a5 + 2 * v13;
          v25 = v16;
          goto LABEL_55;
        }
        if ( v17 < 8 )
        {
          v33 = a1;
          v34 = a1;
        }
        else
        {
          v33 = (_QWORD *)*a1;
          v34 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v33 + 2 * a2 + 2 * v13, (char *)v34 + 2 * v32, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
        v12 = v13 + a5 - v9;
      }
      else
      {
        if ( v17 < 8 )
        {
          v28 = a1;
          v29 = a1;
        }
        else
        {
          v28 = (_QWORD *)*a1;
          v29 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v28 + 2 * a2 + 2 * v13, (char *)v29 + 2 * a2 + 2 * v9, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
      }
      v26 = (char *)v31 + 2 * v12;
      v25 = v13;
      v27 = (char *)v30 + 2 * a2;
    }
    else
    {
      if ( v17 < 8 )
      {
        v21 = a1;
        v22 = a1;
      }
      else
      {
        v21 = (_QWORD *)*a1;
        v22 = (_QWORD *)*a1;
      }
      std::char_traits<unsigned short>::move((char *)v21 + 2 * a2, (char *)v22 + 2 * a5, v13);
      if ( a1[3] < 8u )
      {
        v23 = a1;
        v24 = a1;
      }
      else
      {
        v23 = (_QWORD *)*a1;
        v24 = (_QWORD *)*a1;
      }
      v25 = v15;
      v26 = (char *)v24 + 2 * a2 + 2 * v9;
      v27 = (char *)v23 + 2 * a2 + 2 * v13;
    }
LABEL_55:
    std::char_traits<unsigned short>::move(v27, v26, v25);
    goto LABEL_56;
  }
  if ( v17 < 8 )
  {
    v18 = a1;
    v19 = a1;
  }
  else
  {
    v18 = (_QWORD *)*a1;
    v19 = (_QWORD *)*a1;
  }
  std::char_traits<unsigned short>::move((char *)v18 + 2 * a2 + 2 * v13, (char *)v19 + 2 * a2 + 2 * v9, v15);
  if ( v7[3] >= 8u )
    v7 = (_QWORD *)*v7;
  if ( a1[3] < 8u )
    v20 = a1;
  else
    v20 = (_QWORD *)*a1;
  std::char_traits<unsigned short>::copy((char *)v20 + 2 * a2, (char *)v7 + 2 * a5, v13);
LABEL_56:
  std::wstring::_Eos(a1, v43);
  return a1;
}

```

## disassembly

```asm
0x180002044  push    rbx
0x180002046  push    rbp
0x180002047  push    rsi
0x180002048  push    rdi
0x180002049  push    r12
0x18000204b  push    r13
0x18000204d  push    r14
0x18000204f  push    r15
0x180002051  sub     rsp, 28h
0x180002055  mov     rdi, rdx
0x180002058  mov     r15, r9
0x18000205b  mov     rdx, [rcx+10h]
0x18000205f  mov     r14, r8
0x180002062  mov     rbx, rcx
0x180002065  cmp     rdx, rdi
0x180002068  jb      loc_1800022DC
0x18000206e  mov     rax, [r9+10h]
0x180002072  mov     rsi, [rsp+68h+arg_20]
0x18000207a  cmp     rax, rsi
0x18000207d  jb      loc_1800022DC
0x180002083  mov     rbp, [rsp+68h+arg_28]
0x18000208b  mov     r12, rdx
0x18000208e  sub     r12, rdi
0x180002091  mov     rcx, rdx
0x180002094  cmp     r12, r8
0x180002097  cmovb   r14, r12
0x18000209b  sub     rax, rsi
0x18000209e  cmp     rax, rbp
0x1800020a1  cmovb   rbp, rax
0x1800020a5  sub     rcx, r14
0x1800020a8  mov     rax, rbp
0x1800020ab  not     rax
0x1800020ae  cmp     rax, rcx
0x1800020b1  ja      short loc_1800020C0
0x1800020b3  lea     rcx, aStringTooLong; "string too long"
0x1800020ba  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800020c0  mov     r13, rbp
0x1800020c3  sub     r12, r14
0x1800020c6  sub     r13, r14
0x1800020c9  lea     rax, [rdx+r13]
0x1800020cd  mov     [rsp+68h+arg_0], rax
0x1800020d2  cmp     rdx, rax
0x1800020d5  jnb     short loc_1800020E5
0x1800020d7  xor     r8d, r8d
0x1800020da  mov     rdx, rax
0x1800020dd  mov     rcx, rbx
0x1800020e0  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800020e5  mov     rax, [rbx+18h]
0x1800020e9  cmp     rbx, r15
0x1800020ec  jz      short loc_180002148
0x1800020ee  cmp     rax, 8
0x1800020f2  jb      short loc_1800020FC
0x1800020f4  mov     rcx, [rbx]
0x1800020f7  mov     rdx, rcx
0x1800020fa  jmp     short loc_180002102
0x1800020fc  mov     rcx, rbx
0x1800020ff  mov     rdx, rbx
0x180002102  lea     rax, [rdi+r14]
0x180002106  mov     r8, r12
0x180002109  lea     rdx, [rdx+rax*2]
0x18000210d  lea     rax, [rdi+rbp]
0x180002111  lea     rcx, [rcx+rax*2]
0x180002115  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000211a  cmp     qword ptr [r15+18h], 8
0x18000211f  jb      short loc_180002124
0x180002121  mov     r15, [r15]
0x180002124  cmp     qword ptr [rbx+18h], 8
0x180002129  jb      short loc_180002130
0x18000212b  mov     rax, [rbx]
0x18000212e  jmp     short loc_180002133
0x180002130  mov     rax, rbx
0x180002133  lea     rdx, [r15+rsi*2]
0x180002137  mov     r8, rbp
0x18000213a  lea     rcx, [rax+rdi*2]
0x18000213e  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180002143  jmp     loc_1800022BB
0x180002148  cmp     rbp, r14
0x18000214b  ja      short loc_18000219E
0x18000214d  cmp     rax, 8
0x180002151  jb      short loc_18000215B
0x180002153  mov     rax, [rbx]
0x180002156  mov     rcx, rax
0x180002159  jmp     short loc_180002161
0x18000215b  mov     rax, rbx
0x18000215e  mov     rcx, rbx
0x180002161  lea     rdx, [rcx+rsi*2]
0x180002165  mov     r8, rbp
0x180002168  lea     rcx, [rax+rdi*2]
0x18000216c  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180002171  cmp     qword ptr [rbx+18h], 8
0x180002176  jb      short loc_180002180
0x180002178  mov     rcx, [rbx]
0x18000217b  mov     rdx, rcx
0x18000217e  jmp     short loc_180002186
0x180002180  mov     rcx, rbx
0x180002183  mov     rdx, rbx
0x180002186  lea     rax, [rdi+r14]
0x18000218a  mov     r8, r12
0x18000218d  lea     rdx, [rdx+rax*2]
0x180002191  lea     rax, [rdi+rbp]
0x180002195  lea     rcx, [rcx+rax*2]
0x180002199  jmp     loc_1800022B6
0x18000219e  cmp     rsi, rdi
0x1800021a1  ja      short loc_1800021F4
0x1800021a3  cmp     rax, 8
0x1800021a7  jb      short loc_1800021B1
0x1800021a9  mov     rcx, [rbx]
0x1800021ac  mov     rdx, rcx
0x1800021af  jmp     short loc_1800021B7
0x1800021b1  mov     rcx, rbx
0x1800021b4  mov     rdx, rbx
0x1800021b7  lea     rax, [rdi+r14]
0x1800021bb  mov     r8, r12
0x1800021be  lea     rdx, [rdx+rax*2]
0x1800021c2  lea     rax, [rdi+rbp]
0x1800021c6  lea     rcx, [rcx+rax*2]
0x1800021ca  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x1800021cf  cmp     qword ptr [rbx+18h], 8
0x1800021d4  jb      short loc_1800021DE
0x1800021d6  mov     rax, [rbx]
0x1800021d9  mov     rcx, rax
0x1800021dc  jmp     short loc_1800021E4
0x1800021de  mov     rax, rbx
0x1800021e1  mov     rcx, rbx
0x1800021e4  lea     rdx, [rcx+rsi*2]
0x1800021e8  mov     r8, rbp
0x1800021eb  lea     rcx, [rax+rdi*2]
0x1800021ef  jmp     loc_1800022B6
0x1800021f4  lea     r15, [rdi+r14]
0x1800021f8  cmp     r15, rsi
0x1800021fb  ja      short loc_180002242
0x1800021fd  cmp     rax, 8
0x180002201  jb      short loc_18000220B
0x180002203  mov     rcx, [rbx]
0x180002206  mov     rax, rcx
0x180002209  jmp     short loc_180002211
0x18000220b  mov     rcx, rbx
0x18000220e  mov     rax, rbx
0x180002211  lea     rdx, [rax+r15*2]
0x180002215  mov     r8, r12
0x180002218  lea     rax, [rdi+rbp]
0x18000221c  lea     rcx, [rcx+rax*2]
0x180002220  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180002225  cmp     qword ptr [rbx+18h], 8
0x18000222a  jb      short loc_180002234
0x18000222c  mov     rax, [rbx]
0x18000222f  mov     rcx, rax
0x180002232  jmp     short loc_18000223A
0x180002234  mov     rax, rbx
0x180002237  mov     rcx, rbx
0x18000223a  sub     rsi, r14
0x18000223d  add     rsi, rbp
0x180002240  jmp     short loc_1800021E4
0x180002242  cmp     rax, 8
0x180002246  jb      short loc_180002250
0x180002248  mov     rax, [rbx]
0x18000224b  mov     rcx, rax
0x18000224e  jmp     short loc_180002256
0x180002250  mov     rax, rbx
0x180002253  mov     rcx, rbx
0x180002256  lea     rdx, [rcx+rsi*2]
0x18000225a  mov     r8, r14
0x18000225d  lea     rcx, [rax+rdi*2]
0x180002261  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180002266  cmp     qword ptr [rbx+18h], 8
0x18000226b  lea     r14, [r15+r15]
0x18000226f  jb      short loc_180002279
0x180002271  mov     rax, [rbx]
0x180002274  mov     rcx, rax
0x180002277  jmp     short loc_18000227F
0x180002279  mov     rcx, rbx
0x18000227c  mov     rax, rbx
0x18000227f  lea     rdx, [r14+rax]
0x180002283  mov     r8, r12
0x180002286  lea     rax, [rdi+rbp]
0x18000228a  lea     rcx, [rcx+rax*2]
0x18000228e  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180002293  cmp     qword ptr [rbx+18h], 8
0x180002298  jb      short loc_1800022A2
0x18000229a  mov     rcx, [rbx]
0x18000229d  mov     rdx, rcx
0x1800022a0  jmp     short loc_1800022A8
0x1800022a2  mov     rcx, rbx
0x1800022a5  mov     rdx, rbx
0x1800022a8  lea     rax, [rsi+rbp]
0x1800022ac  add     rcx, r14
0x1800022af  lea     rdx, [rdx+rax*2]
0x1800022b3  mov     r8, r13
0x1800022b6  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x1800022bb  mov     rdx, [rsp+68h+arg_0]
0x1800022c0  mov     rcx, rbx
0x1800022c3  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800022c8  mov     rax, rbx
0x1800022cb  add     rsp, 28h
0x1800022cf  pop     r15
0x1800022d1  pop     r14
0x1800022d3  pop     r13
0x1800022d5  pop     r12
0x1800022d7  pop     rdi
0x1800022d8  pop     rsi
0x1800022d9  pop     rbp
0x1800022da  pop     rbx
0x1800022db  retn
0x1800022dc  lea     rcx, aInvalidStringP; "invalid string position"
0x1800022e3  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
