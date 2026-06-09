# StringReplaceAll(char const *,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>> const &,std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18005f140`
- end: `0x18005f38f`
- name: `?StringReplaceAll@@YAXPEBDAEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@2@@Z`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18007b750`
- `0x18007b860`

## callees

- `0x180004e20`
- `0x18003bb60`
- `0x18005eb84`
- `0x18005f140`

## import_xrefs

- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f2ee`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f309`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f34a`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f2ee`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f309`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18005f34a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StringReplaceAll(_BYTE *a1, __int64 a2, __int64 a3)
{
  __int64 ***v5; // rdx
  __int64 *v6; // rbx
  __int64 *v7; // r8
  __int64 v8; // r9
  __int64 v9; // r10
  unsigned __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 **v12; // rdx
  __int64 **v13; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned int v16; // r9d
  _BYTE *v17; // rbx
  __int64 **v18; // rdi
  __int64 **v19; // r14
  __int64 v20; // rdx
  __int64 *v21; // r10
  unsigned __int64 v22; // r11
  char *v23; // r8
  char *v24; // r8
  unsigned __int64 k; // rcx
  _QWORD *v26; // rax
  __int64 *v27; // rdx
  __int64 v28; // r8
  __int64 **v29; // rax
  __int64 **v30; // rcx
  __int64 **v31; // [rsp+20h] [rbp-40h] BYREF
  __int64 **v32; // [rsp+28h] [rbp-38h]
  __int64 **v33; // [rsp+30h] [rbp-30h]
  _QWORD v34[5]; // [rsp+38h] [rbp-28h] BYREF

  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&v31);
  v6 = **v5;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v7 = v6 + 4;
    v8 = 1;
    v9 = 0;
    if ( v6[6] )
    {
      v10 = 0;
      do
      {
        v8 *= 31;
        if ( (unsigned __int64)v6[7] <= 0xF )
          v11 = v6 + 4;
        else
          v11 = (__int64 *)*v7;
        v9 = *((char *)v11 + v10++) + 31 * v9;
      }
      while ( v10 < v6[6] );
    }
    v34[0] = v6 + 4;
    v34[1] = v9;
    v34[2] = 0;
    v34[3] = v8;
    v34[4] = v6 + 8;
    v12 = v32;
    if ( v32 == v33 )
    {
      std::vector<StringSearchEntry>::_Emplace_reallocate<StringSearchEntry>(&v31, v32, v34);
    }
    else
    {
      *v32 = v7;
      v12[1] = (__int64 *)v9;
      v12[2] = 0;
      v12[3] = (__int64 *)v8;
      v12[4] = v6 + 8;
      v32 += 5;
    }
    v13 = (__int64 **)v6[2];
    if ( *((_BYTE *)v13 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v13; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  v16 = 0;
  v17 = a1;
  if ( *a1 )
  {
    do
    {
      ++v16;
      v18 = v31;
      v19 = v32;
      while ( v18 != v19 )
      {
        v20 = (char)*v17 + 31LL * (_QWORD)v18[2];
        v18[2] = (__int64 *)v20;
        v21 = *v18;
        v22 = (*v18)[2];
        if ( v16 >= v22 )
        {
          v23 = &v17[-v22];
          if ( v16 > v22 )
          {
            v20 -= (_QWORD)v18[3] * *v23;
            v18[2] = (__int64 *)v20;
            v22 = v21[2];
          }
          if ( (__int64 *)v20 == v18[1] )
          {
            v24 = v23 + 1;
            for ( k = 0; k < v22; ++k )
            {
              if ( (unsigned __int64)v21[3] <= 0xF )
                v26 = v21;
              else
                v26 = (_QWORD *)*v21;
              if ( v24[k] != *((_BYTE *)v26 + k) )
                goto LABEL_35;
            }
            if ( v24 != a1 )
              std::ostream::write(a3, a1, v24 - a1);
            v27 = v18[4];
            v28 = v27[2];
            if ( (unsigned __int64)v27[3] > 0xF )
              v27 = (__int64 *)*v27;
            std::ostream::write(a3, v27, v28);
            a1 = v17 + 1;
            v16 = 0;
            v29 = v31;
            v30 = v32;
            while ( v29 != v30 )
            {
              v29[2] = 0;
              v29 += 5;
            }
            break;
          }
        }
LABEL_35:
        v18 += 5;
      }
      ++v17;
    }
    while ( *v17 );
    if ( a1 < v17 )
      std::ostream::write(a3, a1, v17 - a1);
  }
  if ( v31 )
    std::_Deallocate<16>(v31, 8 * (v33 - v31));
}

```

## disassembly

```asm
0x18005f140  push    rbp
0x18005f142  push    rbx
0x18005f143  push    rsi
0x18005f144  push    rdi
0x18005f145  push    r12
0x18005f147  push    r14
0x18005f149  push    r15
0x18005f14b  mov     rbp, rsp
0x18005f14e  sub     rsp, 60h
0x18005f152  mov     r15, r8
0x18005f155  mov     rsi, rcx
0x18005f158  lea     rcx, [rbp+var_40]; void *
0x18005f15c  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18005f161  nop
0x18005f162  mov     rbx, [rdx]
0x18005f165  mov     rbx, [rbx]
0x18005f168  xor     r12d, r12d
0x18005f16b  cmp     [rbx+19h], r12b
0x18005f16f  jnz     loc_18005F24B
0x18005f175  lea     r8, [rbx+20h]
0x18005f179  mov     r9d, 1
0x18005f17f  mov     r10, r12
0x18005f182  cmp     [r8+10h], r12
0x18005f186  jbe     short loc_18005F1B3
0x18005f188  mov     rdx, r12
0x18005f18b  imul    r9, 1Fh
0x18005f18f  cmp     qword ptr [r8+18h], 0Fh
0x18005f194  jbe     short loc_18005F19B
0x18005f196  mov     rax, [r8]
0x18005f199  jmp     short loc_18005F19E
0x18005f19b  mov     rax, r8
0x18005f19e  movsx   rcx, byte ptr [rax+rdx]
0x18005f1a3  imul    r10, 1Fh
0x18005f1a7  add     r10, rcx
0x18005f1aa  inc     rdx
0x18005f1ad  cmp     rdx, [r8+10h]
0x18005f1b1  jb      short loc_18005F18B
0x18005f1b3  mov     [rbp+var_28], r8
0x18005f1b7  mov     [rbp+var_20], r10
0x18005f1bb  mov     [rbp+var_18], r12
0x18005f1bf  mov     [rbp+var_10], r9
0x18005f1c3  lea     rax, [r8+20h]
0x18005f1c7  mov     [rbp+var_8], rax
0x18005f1cb  mov     rdx, [rbp+var_38]
0x18005f1cf  cmp     rdx, [rbp+var_30]
0x18005f1d3  jz      short loc_18005F1EF
0x18005f1d5  mov     [rdx], r8
0x18005f1d8  mov     [rdx+8], r10
0x18005f1dc  mov     [rdx+10h], r12
0x18005f1e0  mov     [rdx+18h], r9
0x18005f1e4  mov     [rdx+20h], rax
0x18005f1e8  add     [rbp+var_38], 28h ; '('
0x18005f1ed  jmp     short loc_18005F1FC
0x18005f1ef  lea     r8, [rbp+var_28]
0x18005f1f3  lea     rcx, [rbp+var_40]
0x18005f1f7  call    ??$_Emplace_reallocate@UStringSearchEntry@@@?$vector@UStringSearchEntry@@V?$allocator@UStringSearchEntry@@@std@@@std@@AEAAPEAUStringSearchEntry@@QEAU2@$$QEAU2@@Z; std::vector<StringSearchEntry>::_Emplace_reallocate<StringSearchEntry>(StringSearchEntry * const,StringSearchEntry &&)
0x18005f1fc  mov     rcx, [rbx+10h]
0x18005f200  cmp     [rcx+19h], r12b
0x18005f204  jz      short loc_18005F227
0x18005f206  mov     rax, [rbx+8]
0x18005f20a  jmp     short loc_18005F219
0x18005f20c  cmp     rbx, [rax+10h]
0x18005f210  jnz     short loc_18005F21F
0x18005f212  mov     rbx, rax
0x18005f215  mov     rax, [rax+8]
0x18005f219  cmp     [rax+19h], r12b
0x18005f21d  jz      short loc_18005F20C
0x18005f21f  mov     rbx, rax
0x18005f222  jmp     loc_18005F16B
0x18005f227  mov     rbx, rcx
0x18005f22a  mov     rcx, [rcx]
0x18005f22d  cmp     [rcx+19h], r12b
0x18005f231  jnz     loc_18005F16B
0x18005f237  mov     rbx, rcx
0x18005f23a  mov     rax, [rcx]
0x18005f23d  mov     rcx, rax
0x18005f240  cmp     [rax+19h], r12b
0x18005f244  jz      short loc_18005F237
0x18005f246  jmp     loc_18005F16B
0x18005f24b  mov     r9d, r12d
0x18005f24e  mov     rbx, rsi
0x18005f251  cmp     [rsi], r12b
0x18005f254  jz      loc_18005F351
0x18005f25a  inc     r9d
0x18005f25d  mov     rdi, [rbp+var_40]
0x18005f261  mov     r14, [rbp+var_38]
0x18005f265  cmp     rdi, r14
0x18005f268  jz      loc_18005F32D
0x18005f26e  imul    rdx, [rdi+10h], 1Fh
0x18005f273  movsx   rax, byte ptr [rbx]
0x18005f277  add     rdx, rax
0x18005f27a  mov     [rdi+10h], rdx
0x18005f27e  mov     r10, [rdi]
0x18005f281  mov     r11, [r10+10h]
0x18005f285  mov     eax, r9d
0x18005f288  cmp     rax, r11
0x18005f28b  jb      short loc_18005F2DA
0x18005f28d  mov     r8, rbx
0x18005f290  sub     r8, r11
0x18005f293  cmp     rax, r11
0x18005f296  jbe     short loc_18005F2AC
0x18005f298  movsx   rax, byte ptr [r8]
0x18005f29c  imul    rax, [rdi+18h]
0x18005f2a1  sub     rdx, rax
0x18005f2a4  mov     [rdi+10h], rdx
0x18005f2a8  mov     r11, [r10+10h]
0x18005f2ac  cmp     rdx, [rdi+8]
0x18005f2b0  jnz     short loc_18005F2DA
0x18005f2b2  inc     r8
0x18005f2b5  mov     rcx, r12
0x18005f2b8  cmp     rcx, r11
0x18005f2bb  jnb     short loc_18005F2E0
0x18005f2bd  cmp     qword ptr [r10+18h], 0Fh
0x18005f2c2  jbe     short loc_18005F2C9
0x18005f2c4  mov     rax, [r10]
0x18005f2c7  jmp     short loc_18005F2CC
0x18005f2c9  mov     rax, r10
0x18005f2cc  mov     al, [rax+rcx]
0x18005f2cf  cmp     [r8+rcx], al
0x18005f2d3  jnz     short loc_18005F2DA
0x18005f2d5  inc     rcx
0x18005f2d8  jmp     short loc_18005F2B8
0x18005f2da  add     rdi, 28h ; '('
0x18005f2de  jmp     short loc_18005F265
0x18005f2e0  cmp     r8, rsi
0x18005f2e3  jz      short loc_18005F2F4
0x18005f2e5  sub     r8, rsi
0x18005f2e8  mov     rdx, rsi
0x18005f2eb  mov     rcx, r15
0x18005f2ee  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x18005f2f4  mov     rdx, [rdi+20h]
0x18005f2f8  mov     r8, [rdx+10h]
0x18005f2fc  cmp     qword ptr [rdx+18h], 0Fh
0x18005f301  jbe     short loc_18005F306
0x18005f303  mov     rdx, [rdx]
0x18005f306  mov     rcx, r15
0x18005f309  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x18005f30f  lea     rsi, [rbx+1]
0x18005f313  mov     r9d, r12d
0x18005f316  mov     rax, [rbp+var_40]
0x18005f31a  mov     rcx, [rbp+var_38]
0x18005f31e  jmp     short loc_18005F328
0x18005f320  mov     [rax+10h], r12
0x18005f324  add     rax, 28h ; '('
0x18005f328  cmp     rax, rcx
0x18005f32b  jnz     short loc_18005F320
0x18005f32d  inc     rbx
0x18005f330  cmp     [rbx], r12b
0x18005f333  jnz     loc_18005F25A
0x18005f339  cmp     rsi, rbx
0x18005f33c  jnb     short loc_18005F351
0x18005f33e  sub     rbx, rsi
0x18005f341  mov     r8, rbx
0x18005f344  mov     rdx, rsi
0x18005f347  mov     rcx, r15
0x18005f34a  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x18005f350  nop
0x18005f351  mov     rcx, [rbp+var_40]
0x18005f355  test    rcx, rcx
0x18005f358  jz      short loc_18005F380
0x18005f35a  mov     rax, [rbp+var_30]
0x18005f35e  sub     rax, rcx
0x18005f361  sar     rax, 3
0x18005f365  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18005f36f  imul    rax, rdx
0x18005f373  lea     rdx, [rax+rax*4]
0x18005f377  shl     rdx, 3
0x18005f37b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f380  add     rsp, 60h
0x18005f384  pop     r15
0x18005f386  pop     r14
0x18005f388  pop     r12
0x18005f38a  pop     rdi
0x18005f38b  pop     rsi
0x18005f38c  pop     rbx
0x18005f38d  pop     rbp
0x18005f38e  retn
```
