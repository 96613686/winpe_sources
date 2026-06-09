# sub_1801BDEC0

- ea: `0x1801bdec0`
- end: `0x1801be253`
- name: `sub_1801BDEC0`
- size: `915`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `30`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1801a8d20`
- `0x1801a934c`
- `0x1801bd7b8`
- `0x1801c58ac`
- `0x18021d1f0`
- `0x1802267d0`
- `0x180228b88`
- `0x180228c50`
- `0x180228fbc`
- `0x18022a430`
- `0x18022b0d0`
- `0x18022b400`
- `0x18022bc80`
- `0x18022cca8`
- `0x18022d950`
- `0x180234b74`
- `0x180241334`
- `0x18024189c`
- `0x180243100`
- `0x1802443a8`
- `0x180245254`
- `0x18034986a`
- `0x180349886`
- `0x18034ac23`
- `0x18035666e`
- `0x18035721e`
- `0x180357256`
- `0x180357272`
- `0x180357b66`
- `0x18035b665`

## callees

- `0x180021e18`
- `0x180022508`
- `0x180026f10`
- `0x18003bbbc`
- `0x180068c64`
- `0x1800ee930`
- `0x18010e564`
- `0x1801bdec0`
- `0x1801c09d0`
- `0x1801c989b`
- `0x1802254b4`
- `0x180226224`
- `0x18024b8e8`
- `0x18024c780`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801bdf40`
- `KERNEL32!LoadLibraryExW` at `0x1801bdf40`

## pseudocode

```c
__int64 __fastcall sub_1801BDEC0(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  _QWORD *i; // rsi
  __int64 v5; // rax
  __int64 v6; // rsi
  const WCHAR *v7; // rax
  __int64 j; // rbp
  __int64 v9; // rax
  __int64 k; // r14
  __int64 m; // r14
  __int64 n; // rbp
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 jj; // rsi
  __int64 v16; // rax
  __int64 kk; // rsi
  __int64 v18; // rcx
  __int64 mm; // rsi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // r11
  unsigned int v24; // r9d
  __int64 v25; // r8
  __int64 v26; // r10
  unsigned int v27; // r9d
  __int64 v28; // rax
  __int64 v29; // r11
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 ii; // rax
  _BYTE v37[96]; // [rsp+28h] [rbp-60h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]

  v2 = a1;
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 112LL);
  for ( i = *(_QWORD **)(a1 + 40); i; i = (_QWORD *)i[1] )
  {
    LOBYTE(a1) = 1;
    sub_1802254B4(a1, a2);
    sub_18010E564(*(_QWORD *)(v3 + 2280), *i, 0);
  }
  v5 = *(_QWORD *)(v2 + 16);
  v6 = *(_QWORD *)(v5 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v5 + 96) + 8424LL) )
  {
    v7 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)(v5 + 96) + 8408LL);
    *(_QWORD *)(v6 + 8) = LoadLibraryExW(v7, 0, 0x800u);
    *(_BYTE *)(v6 + 16) = 1;
  }
  for ( j = *(_QWORD *)(v2 + 24); j; j = *(_QWORD *)(j + 8) )
  {
    v9 = sub_180226224(j);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v9);
  }
  if ( *(_BYTE *)(v2 + 101) )
  {
    for ( k = *(_QWORD *)(v2 + 48); k; k = *(_QWORD *)(k + 8) )
    {
      LOBYTE(a1) = 1;
      sub_1802254B4(a1, a2);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, **(_QWORD **)k);
    }
  }
  if ( *(_BYTE *)(v2 + 102) )
  {
    for ( m = *(_QWORD *)(v2 + 80); m; m = *(_QWORD *)(m + 16) )
    {
      LOBYTE(a1) = 1;
      sub_1802254B4(a1, a2);
      memset(*(void **)m, 0, *(_QWORD *)(m + 8));
    }
    for ( n = *(_QWORD *)(v2 + 64); n; n = *(_QWORD *)(n + 8) )
    {
      v13 = sub_180226224(n);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v13);
    }
  }
  if ( *(_QWORD *)(v2 + 32)
    || *(_BYTE *)(v2 + 101) && *(_QWORD *)(v2 + 56)
    || *(_BYTE *)(v2 + 102) && *(_QWORD *)(v2 + 72) )
  {
    if ( !(unsigned __int8)sub_180026F10(*(_QWORD *)(v3 + 1184), 33008) )
    {
      v29 = sub_1801C09D0(*(_QWORD *)(v2 + 16));
      v30 = *(_QWORD *)(v2 + 8);
      if ( *(_BYTE *)(v2 + 101) )
        v31 = *(_QWORD *)(v2 + 56);
      else
        v31 = 0;
      if ( *(_BYTE *)(v2 + 102) )
      {
        v32 = *(_QWORD *)(v2 + 72);
        v33 = *(_QWORD *)(v2 + 32);
        if ( v33 )
        {
          if ( v32 )
          {
            v34 = *(_QWORD *)(v2 + 72);
            for ( ii = v34; ii; ii = *(_QWORD *)(ii + 8) )
              v34 = ii;
            *(_QWORD *)(v34 + 8) = v33;
          }
          else
          {
            v32 = *(_QWORD *)(v2 + 32);
          }
        }
      }
      else
      {
        v32 = *(_QWORD *)(v2 + 32);
      }
      sub_18024C780(v29, v32, v31, v30, -2);
      return sub_18003BBBC(*(_QWORD *)(v3 + 1184), *(_QWORD *)v2);
    }
    if ( v14 )
    {
      sub_180068C64(v37, v3, retaddr);
      for ( jj = *(_QWORD *)(v2 + 32); jj; jj = *(_QWORD *)(jj + 8) )
      {
        v16 = sub_180226224(jj);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      sub_180021E18(*(_QWORD *)(v3 + 1184));
      sub_180022508(v37);
    }
  }
  if ( *(_BYTE *)(v2 + 101) && *(_QWORD *)(v2 + 56) )
  {
    sub_180068C64(v37, v3, retaddr);
    for ( kk = *(_QWORD *)(v2 + 56); kk; kk = *(_QWORD *)(kk + 8) )
    {
      v18 = *(_QWORD *)sub_180226224(kk);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( v3 )
      sub_180021E18(*(_QWORD *)(v3 + 1184));
    sub_180022508(v37);
  }
  if ( *(_BYTE *)(v2 + 102) && *(_QWORD *)(v2 + 72) )
  {
    sub_180068C64(v37, v3, retaddr);
    for ( mm = *(_QWORD *)(v2 + 72); mm; mm = *(_QWORD *)(mm + 8) )
    {
      v20 = sub_180226224(mm);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    if ( v3 )
      sub_180021E18(*(_QWORD *)(v3 + 1184));
    sub_180022508(v37);
  }
  v21 = sub_1801C09D0(*(_QWORD *)(v2 + 16));
  v22 = sub_1800EE930(
          *(_QWORD *)(*(_QWORD *)(v21 + 144) + 56LL),
          (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 144) + 56LL) + 8LL) - 1));
  v24 = 0;
  v26 = *(_QWORD *)(v25 + 64);
  while ( (signed int)v24 < *(_DWORD *)(v26 + 8) )
  {
    if ( !sub_1800EE930(v26, v24) )
    {
      *(_QWORD *)sub_18024B8E8(v26, v27) = v22;
      break;
    }
    v24 = v27 + 1;
  }
  v28 = *(_QWORD *)(*(_QWORD *)(v23 + 144) + 56LL);
  *(_QWORD *)(*(_QWORD *)v28 + 8LL * (int)--*(_DWORD *)(v28 + 8)) = 0;
  return sub_18003BBBC(*(_QWORD *)(v3 + 1184), *(_QWORD *)v2);
}

```

## disassembly

```asm
0x1801bdec0  mov     rax, rsp
0x1801bdec3  mov     [rax+8], rcx
0x1801bdec7  push    rbx
0x1801bdec8  push    rbp
0x1801bdec9  push    rsi
0x1801bdeca  push    rdi
0x1801bdecb  push    r14
0x1801bdecd  push    r15
0x1801bdecf  sub     rsp, 58h
0x1801bded3  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x1801bdedb  mov     rbx, rcx
0x1801bdede  mov     rax, [rcx+10h]
0x1801bdee2  mov     rdi, [rax+70h]
0x1801bdee6  mov     rsi, [rcx+28h]
0x1801bdeea  xor     r15d, r15d
0x1801bdeed  test    rsi, rsi
0x1801bdef0  jz      short loc_1801BDF11
0x1801bdef2  mov     cl, 1
0x1801bdef4  call    sub_1802254B4
0x1801bdef9  xor     r8d, r8d
0x1801bdefc  mov     rdx, [rsi]
0x1801bdeff  mov     rcx, [rdi+8E8h]
0x1801bdf06  call    sub_18010E564
0x1801bdf0b  mov     rsi, [rsi+8]
0x1801bdf0f  jmp     short loc_1801BDEED
0x1801bdf11  mov     rax, [rbx+10h]
0x1801bdf15  mov     rsi, [rax+60h]
0x1801bdf19  add     rsi, 20D8h
0x1801bdf20  cmp     [rsi+10h], r15b
0x1801bdf24  jnz     short loc_1801BDF4E
0x1801bdf26  mov     rax, [rsi]
0x1801bdf29  mov     rcx, rsi
0x1801bdf2c  mov     rax, [rax+8]
0x1801bdf30  call    j_j__guard_dispatch_icall_nop
0x1801bdf35  mov     rcx, rax; lpLibFileName
0x1801bdf38  xor     edx, edx; hFile
0x1801bdf3a  mov     r8d, 800h; dwFlags
0x1801bdf40  call    cs:LoadLibraryExW
0x1801bdf46  mov     [rsi+8], rax
0x1801bdf4a  mov     byte ptr [rsi+10h], 1
0x1801bdf4e  mov     rbp, [rbx+18h]
0x1801bdf52  test    rbp, rbp
0x1801bdf55  jz      short loc_1801BDF7A
0x1801bdf57  mov     rcx, rbp
0x1801bdf5a  call    sub_180226224
0x1801bdf5f  mov     rcx, [rsi]
0x1801bdf62  mov     r8, [rcx+20h]
0x1801bdf66  mov     rdx, rax
0x1801bdf69  mov     rcx, rsi
0x1801bdf6c  mov     rax, r8
0x1801bdf6f  call    j_j__guard_dispatch_icall_nop
0x1801bdf74  mov     rbp, [rbp+8]
0x1801bdf78  jmp     short loc_1801BDF52
0x1801bdf7a  cmp     [rbx+65h], r15b
0x1801bdf7e  jz      short loc_1801BDFAB
0x1801bdf80  mov     r14, [rbx+30h]
0x1801bdf84  test    r14, r14
0x1801bdf87  jz      short loc_1801BDFAB
0x1801bdf89  mov     cl, 1
0x1801bdf8b  call    sub_1802254B4
0x1801bdf90  mov     rax, [rsi]
0x1801bdf93  mov     rdx, [r14]
0x1801bdf96  mov     rdx, [rdx]
0x1801bdf99  mov     rcx, rsi
0x1801bdf9c  mov     rax, [rax+20h]
0x1801bdfa0  call    j_j__guard_dispatch_icall_nop
0x1801bdfa5  mov     r14, [r14+8]
0x1801bdfa9  jmp     short loc_1801BDF84
0x1801bdfab  cmp     [rbx+66h], r15b
0x1801bdfaf  jz      short loc_1801BE001
0x1801bdfb1  mov     r14, [rbx+50h]
0x1801bdfb5  test    r14, r14
0x1801bdfb8  jz      short loc_1801BDFD5
0x1801bdfba  mov     cl, 1
0x1801bdfbc  call    sub_1802254B4
0x1801bdfc1  mov     r8, [r14+8]; Size
0x1801bdfc5  xor     edx, edx; Val
0x1801bdfc7  mov     rcx, [r14]; void *
0x1801bdfca  call    memset
0x1801bdfcf  mov     r14, [r14+10h]
0x1801bdfd3  jmp     short loc_1801BDFB5
0x1801bdfd5  mov     rbp, [rbx+40h]
0x1801bdfd9  test    rbp, rbp
0x1801bdfdc  jz      short loc_1801BE001
0x1801bdfde  mov     rcx, rbp
0x1801bdfe1  call    sub_180226224
0x1801bdfe6  mov     rcx, [rsi]
0x1801bdfe9  mov     r8, [rcx+20h]
0x1801bdfed  mov     rdx, rax
0x1801bdff0  mov     rcx, rsi
0x1801bdff3  mov     rax, r8
0x1801bdff6  call    j_j__guard_dispatch_icall_nop
0x1801bdffb  mov     rbp, [rbp+8]
0x1801bdfff  jmp     short loc_1801BDFD9
0x1801be001  mov     r8, [rbx+20h]
0x1801be005  test    r8, r8
0x1801be008  jnz     short loc_1801BE022
0x1801be00a  cmp     [rbx+65h], r15b
0x1801be00e  jz      short loc_1801BE016
0x1801be010  cmp     [rbx+38h], r15
0x1801be014  jnz     short loc_1801BE022
0x1801be016  cmp     [rbx+66h], r15b
0x1801be01a  jz      short loc_1801BE094
0x1801be01c  cmp     [rbx+48h], r15
0x1801be020  jz      short loc_1801BE094
0x1801be022  mov     edx, 80F0h
0x1801be027  mov     rcx, [rdi+4A0h]
0x1801be02e  call    sub_180026F10
0x1801be033  test    al, al
0x1801be035  jz      loc_1801BE1D1
0x1801be03b  test    r8, r8
0x1801be03e  jz      short loc_1801BE094
0x1801be040  mov     r8, [rsp+88h]
0x1801be048  mov     rdx, rdi
0x1801be04b  lea     rcx, [rsp+88h+var_60]
0x1801be050  call    sub_180068C64
0x1801be055  mov     rsi, [rbx+20h]
0x1801be059  test    rsi, rsi
0x1801be05c  jz      short loc_1801BE07E
0x1801be05e  mov     rcx, rsi
0x1801be061  call    sub_180226224
0x1801be066  mov     rdx, rax
0x1801be069  mov     rcx, [rax]
0x1801be06c  mov     rax, [rcx+10h]
0x1801be070  mov     rcx, rdx
0x1801be073  call    j_j__guard_dispatch_icall_nop
0x1801be078  mov     rsi, [rsi+8]
0x1801be07c  jmp     short loc_1801BE059
0x1801be07e  mov     rcx, [rdi+4A0h]
0x1801be085  call    sub_180021E18
0x1801be08a  lea     rcx, [rsp+88h+var_60]
0x1801be08f  call    sub_180022508
0x1801be094  cmp     [rbx+65h], r15b
0x1801be098  jz      short loc_1801BE0FB
0x1801be09a  cmp     [rbx+38h], r15
0x1801be09e  jz      short loc_1801BE0FB
0x1801be0a0  mov     r8, [rsp+88h]
0x1801be0a8  mov     rdx, rdi
0x1801be0ab  lea     rcx, [rsp+88h+var_60]
0x1801be0b0  call    sub_180068C64
0x1801be0b5  mov     rsi, [rbx+38h]
0x1801be0b9  test    rsi, rsi
0x1801be0bc  jz      short loc_1801BE0E0
0x1801be0be  mov     rcx, rsi
0x1801be0c1  call    sub_180226224
0x1801be0c6  mov     rcx, [rax]
0x1801be0c9  test    rcx, rcx
0x1801be0cc  jz      short loc_1801BE0DA
0x1801be0ce  mov     rax, [rcx]
0x1801be0d1  mov     rax, [rax+10h]
0x1801be0d5  call    j_j__guard_dispatch_icall_nop
0x1801be0da  mov     rsi, [rsi+8]
0x1801be0de  jmp     short loc_1801BE0B9
0x1801be0e0  test    rdi, rdi
0x1801be0e3  jz      short loc_1801BE0F1
0x1801be0e5  mov     rcx, [rdi+4A0h]
0x1801be0ec  call    sub_180021E18
0x1801be0f1  lea     rcx, [rsp+88h+var_60]
0x1801be0f6  call    sub_180022508
0x1801be0fb  cmp     [rbx+66h], r15b
0x1801be0ff  jz      short loc_1801BE160
0x1801be101  cmp     [rbx+48h], r15
0x1801be105  jz      short loc_1801BE160
0x1801be107  mov     r8, [rsp+88h]
0x1801be10f  mov     rdx, rdi
0x1801be112  lea     rcx, [rsp+88h+var_60]
0x1801be117  call    sub_180068C64
0x1801be11c  mov     rsi, [rbx+48h]
0x1801be120  test    rsi, rsi
0x1801be123  jz      short loc_1801BE145
0x1801be125  mov     rcx, rsi
0x1801be128  call    sub_180226224
0x1801be12d  mov     rdx, rax
0x1801be130  mov     rcx, [rax]
0x1801be133  mov     rax, [rcx+10h]
0x1801be137  mov     rcx, rdx
0x1801be13a  call    j_j__guard_dispatch_icall_nop
0x1801be13f  mov     rsi, [rsi+8]
0x1801be143  jmp     short loc_1801BE120
0x1801be145  test    rdi, rdi
0x1801be148  jz      short loc_1801BE156
0x1801be14a  mov     rcx, [rdi+4A0h]
0x1801be151  call    sub_180021E18
0x1801be156  lea     rcx, [rsp+88h+var_60]
0x1801be15b  call    sub_180022508
0x1801be160  mov     rcx, [rbx+10h]
0x1801be164  call    sub_1801C09D0
0x1801be169  mov     r11, rax
0x1801be16c  mov     r8, [rax+90h]
0x1801be173  mov     rcx, [r8+38h]
0x1801be177  mov     edx, [rcx+8]
0x1801be17a  dec     edx
0x1801be17c  call    sub_1800EE930
0x1801be181  mov     rsi, rax
0x1801be184  mov     r9d, r15d
0x1801be187  mov     r10, [r8+40h]
0x1801be18b  cmp     r9d, [r10+8]
0x1801be18f  jge     short loc_1801BE1B4
0x1801be191  mov     edx, r9d
0x1801be194  mov     rcx, r10
0x1801be197  call    sub_1800EE930
0x1801be19c  test    rax, rax
0x1801be19f  jz      short loc_1801BE1A6
0x1801be1a1  inc     r9d
0x1801be1a4  jmp     short loc_1801BE18B
0x1801be1a6  mov     edx, r9d
0x1801be1a9  mov     rcx, r10
0x1801be1ac  call    sub_18024B8E8
0x1801be1b1  mov     [rax], rsi
0x1801be1b4  mov     rax, [r11+90h]
0x1801be1bb  mov     rax, [rax+38h]
0x1801be1bf  dec     dword ptr [rax+8]
0x1801be1c2  movsxd  rcx, dword ptr [rax+8]
0x1801be1c6  mov     rax, [rax]
0x1801be1c9  xor     edx, edx
0x1801be1cb  mov     [rax+rcx*8], rdx
0x1801be1cf  jmp     short loc_1801BE236
0x1801be1d1  mov     rcx, [rbx+10h]
0x1801be1d5  call    sub_1801C09D0
0x1801be1da  mov     r11, rax
0x1801be1dd  mov     r9, [rbx+8]
0x1801be1e1  cmp     [rbx+65h], r15b
0x1801be1e5  jz      short loc_1801BE1ED
0x1801be1e7  mov     r10, [rbx+38h]
0x1801be1eb  jmp     short loc_1801BE1F0
0x1801be1ed  mov     r10, r15
0x1801be1f0  cmp     [rbx+66h], r15b
0x1801be1f4  jz      short loc_1801BE227
0x1801be1f6  mov     rdx, [rbx+48h]
0x1801be1fa  mov     rcx, [rbx+20h]
0x1801be1fe  test    rcx, rcx
0x1801be201  jz      short loc_1801BE22B
0x1801be203  test    rdx, rdx
0x1801be206  jnz     short loc_1801BE20D
0x1801be208  mov     rdx, rcx
0x1801be20b  jmp     short loc_1801BE22B
0x1801be20d  mov     r8, rdx
0x1801be210  mov     rax, rdx
0x1801be213  test    rax, rax
0x1801be216  jz      short loc_1801BE221
0x1801be218  mov     r8, rax
0x1801be21b  mov     rax, [rax+8]
0x1801be21f  jmp     short loc_1801BE213
0x1801be221  mov     [r8+8], rcx
0x1801be225  jmp     short loc_1801BE22B
0x1801be227  mov     rdx, [rbx+20h]
0x1801be22b  mov     r8, r10
0x1801be22e  mov     rcx, r11
0x1801be231  call    sub_18024C780
0x1801be236  mov     rdx, [rbx]
0x1801be239  mov     rcx, [rdi+4A0h]
0x1801be240  call    sub_18003BBBC
0x1801be245  nop
0x1801be246  add     rsp, 58h
0x1801be24a  pop     r15
0x1801be24c  pop     r14
0x1801be24e  pop     rdi
0x1801be24f  pop     rsi
0x1801be250  pop     rbp
0x1801be251  pop     rbx
0x1801be252  retn
```
