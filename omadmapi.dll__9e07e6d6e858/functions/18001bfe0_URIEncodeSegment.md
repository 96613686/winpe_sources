# URIEncodeSegment

- ea: `0x18001bfe0`
- end: `0x18001c385`
- name: `URIEncodeSegment`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800098a8`
- `0x18000a064`
- `0x18001bfe0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c32f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c32f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ba`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x18001c0a7`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x18001c12d`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x18001c0a7`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x18001c12d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall URIEncodeSegment(const unsigned __int16 *a1, _QWORD *a2)
{
  char *v4; // rsi
  _WORD *v5; // rdi
  __int16 *v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rax
  __int64 v10; // r15
  int v11; // eax
  int v12; // r12d
  signed int LastError; // eax
  char *v14; // rax
  unsigned int v15; // r12d
  unsigned int i; // edi
  unsigned __int64 v17; // rax
  __int16 v18; // ax
  __int16 *v19; // rdx
  __int16 *v20; // r8
  __int16 *v21; // rdx
  __int16 *v22; // r8
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // r8d
  __int128 v28; // [rsp+40h] [rbp-58h] BYREF
  __int16 *v29; // [rsp+50h] [rbp-48h]
  int v30; // [rsp+A0h] [rbp+8h] BYREF
  char *v31; // [rsp+B0h] [rbp+18h]
  _WORD *v32; // [rsp+B8h] [rbp+20h]

  v4 = 0;
  v31 = 0;
  v5 = 0;
  v32 = 0;
  v28 = 0;
  v6 = 0;
  v29 = 0;
  if ( !a1 || !a2 )
  {
    v7 = -2147024809;
    goto LABEL_33;
  }
  *a2 = 0;
  v8 = 0x7FFFFFFF;
  v9 = a1;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v7 = v8 == 0 ? 0x80070057 : 0;
  v10 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
  if ( v8 )
  {
    if ( v10 )
    {
      v11 = SafeWideCharToMultiByte(0xFDE9u, 0, a1, -1, 0, 0, 0, 0);
      v12 = v11;
      if ( v11 <= 0 )
        goto LABEL_10;
      v14 = (char *)LocalAlloc(0, (unsigned int)v11);
      v4 = v14;
      v31 = v14;
      if ( !v14 )
      {
LABEL_13:
        v7 = -2147024882;
        goto LABEL_33;
      }
      if ( (int)SafeWideCharToMultiByte(0xFDE9u, 0, a1, v10, v14, v12, 0, 0) <= 0 )
      {
LABEL_10:
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_33;
      }
      v15 = v12 - 1;
      for ( i = 0; i < v15; ++i )
      {
        try
        {
          v17 = v4[i];
          if ( v17 < 0x80 && dword_18002A2F0[v17] )
          {
            v18 = v4[i];
            LOWORD(v30) = v18;
            if ( *((__int16 **)&v28 + 1) == v29 )
            {
              std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(
                &v28,
                *((_QWORD *)&v28 + 1),
                &v30);
            }
            else
            {
              **((_WORD **)&v28 + 1) = v18;
              *((_QWORD *)&v28 + 1) += 2LL;
            }
          }
          else
          {
            LOWORD(v30) = 37;
            if ( *((__int16 **)&v28 + 1) == v29 )
            {
              std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(
                &v28,
                *((_QWORD *)&v28 + 1),
                &v30);
              v19 = (__int16 *)*((_QWORD *)&v28 + 1);
            }
            else
            {
              **((_WORD **)&v28 + 1) = 37;
              v19 = (__int16 *)(*((_QWORD *)&v28 + 1) + 2LL);
              *((_QWORD *)&v28 + 1) += 2LL;
            }
            v20 = &_ImageBase[((unsigned __int64)(unsigned __int8)v4[i] >> 4) + 86372];
            if ( v19 == v29 )
            {
              std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(&v28, v19, v20);
              v21 = (__int16 *)*((_QWORD *)&v28 + 1);
            }
            else
            {
              *v19 = *v20;
              v21 = (__int16 *)(*((_QWORD *)&v28 + 1) + 2LL);
              *((_QWORD *)&v28 + 1) += 2LL;
            }
            v22 = &_ImageBase[(v4[i] & 0xF) + 86372];
            if ( v21 == v29 )
            {
              std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(&v28, v21, v22);
            }
            else
            {
              *v21 = *v22;
              *((_QWORD *)&v28 + 1) += 2LL;
            }
          }
        }
        catch ( std::bad_alloc )
        {
          v30 = -2147024882;
          v5 = v32;
          v4 = v31;
          v7 = -2147024882;
          goto LABEL_33;
        }
      }
      v6 = v29;
    }
    LOWORD(v30) = 0;
    if ( *((__int16 **)&v28 + 1) == v6 )
    {
      try
      {
        std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(&v28, *((_QWORD *)&v28 + 1), &v30);
        v24 = *((_QWORD *)&v28 + 1);
      }
      catch ( std::bad_alloc )
      {
        v30 = -2147024882;
        v5 = v32;
        v4 = v31;
        v7 = -2147024882;
        goto LABEL_33;
      }
    }
    else
    {
      **((_WORD **)&v28 + 1) = 0;
      v24 = *((_QWORD *)&v28 + 1) + 2LL;
      *((_QWORD *)&v28 + 1) += 2LL;
    }
    v5 = LocalAlloc(0, 2 * ((v24 - (__int64)v28) >> 1));
    if ( !v5 )
      goto LABEL_13;
    v25 = v28;
    v26 = (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 1;
    v27 = 0;
    if ( (int)v26 > 0 )
    {
      while ( 1 )
      {
        v5[v27] = *(_WORD *)(v25 + 2LL * v27);
        if ( (int)++v27 >= (int)v26 )
          break;
        v25 = v28;
      }
    }
    *a2 = v5;
    v5 = 0;
  }
LABEL_33:
  LocalFree(v4);
  LocalFree(v5);
  std::vector<unsigned short>::~vector<unsigned short>(&v28);
  return v7;
}

```

## disassembly

```asm
0x18001bfe0  push    rbx
0x18001bfe2  push    rsi
0x18001bfe3  push    rdi
0x18001bfe4  push    r12
0x18001bfe6  push    r13
0x18001bfe8  push    r14
0x18001bfea  push    r15
0x18001bfec  sub     rsp, 60h
0x18001bff0  mov     r13, rdx
0x18001bff3  mov     r14, rcx
0x18001bff6  xor     r12d, r12d
0x18001bff9  mov     esi, r12d
0x18001bffc  mov     [rsp+98h+arg_10], r12
0x18001c004  mov     edi, r12d
0x18001c007  mov     [rsp+98h+arg_18], r12
0x18001c00f  xorps   xmm0, xmm0
0x18001c012  movdqu  [rsp+98h+var_58], xmm0
0x18001c018  mov     r8d, r12d
0x18001c01b  mov     [rsp+98h+var_48], r12
0x18001c020  test    rcx, rcx
0x18001c023  jnz     short loc_18001C02F
0x18001c025  mov     ebx, 80070057h
0x18001c02a  jmp     loc_18001C2A0
0x18001c02f  test    r13, r13
0x18001c032  jz      short loc_18001C025
0x18001c034  mov     [rdx], r12
0x18001c037  mov     r9d, 7FFFFFFFh
0x18001c03d  mov     edx, r9d
0x18001c040  mov     rax, r14
0x18001c043  cmp     [rax], r12w
0x18001c047  jz      short loc_18001C053
0x18001c049  add     rax, 2
0x18001c04d  sub     rdx, 1
0x18001c051  jnz     short loc_18001C043
0x18001c053  mov     rax, rdx
0x18001c056  neg     rax
0x18001c059  sbb     ecx, ecx
0x18001c05b  not     ecx
0x18001c05d  mov     ebx, 80070057h
0x18001c062  and     ebx, ecx
0x18001c064  mov     rax, rdx
0x18001c067  sub     r9, rdx
0x18001c06a  neg     rax
0x18001c06d  sbb     r15, r15
0x18001c070  and     r15, r9
0x18001c073  test    rdx, rdx
0x18001c076  jz      loc_18001C2A0
0x18001c07c  test    r15, r15
0x18001c07f  jz      loc_18001C2E4
0x18001c085  mov     [rsp+98h+var_60], r12
0x18001c08a  mov     [rsp+98h+var_68], r12
0x18001c08f  mov     [rsp+98h+var_70], r12d
0x18001c094  mov     [rsp+98h+var_78], r12
0x18001c099  or      r9d, 0FFFFFFFFh
0x18001c09d  mov     r8, r14
0x18001c0a0  xor     edx, edx
0x18001c0a2  mov     ecx, 0FDE9h
0x18001c0a7  call    cs:__imp_?SafeWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; SafeWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18001c0ae  nop     dword ptr [rax+rax+00h]
0x18001c0b3  mov     r12d, eax
0x18001c0b6  test    eax, eax
0x18001c0b8  jg      short loc_18001C0DE
0x18001c0ba  call    cs:__imp_GetLastError
0x18001c0c1  nop     dword ptr [rax+rax+00h]
0x18001c0c6  mov     ebx, eax
0x18001c0c8  test    eax, eax
0x18001c0ca  jle     loc_18001C2A0
0x18001c0d0  movzx   ebx, ax
0x18001c0d3  or      ebx, 80070000h
0x18001c0d9  jmp     loc_18001C2A0
0x18001c0de  mov     rdx, r12; uBytes
0x18001c0e1  xor     ecx, ecx; uFlags
0x18001c0e3  call    cs:__imp_LocalAlloc
0x18001c0ea  nop     dword ptr [rax+rax+00h]
0x18001c0ef  mov     rsi, rax
0x18001c0f2  mov     [rsp+98h+arg_10], rax
0x18001c0fa  test    rax, rax
0x18001c0fd  jnz     short loc_18001C109
0x18001c0ff  mov     ebx, 8007000Eh
0x18001c104  jmp     loc_18001C2A0
0x18001c109  mov     r9d, r15d
0x18001c10c  xor     r15d, r15d
0x18001c10f  mov     [rsp+98h+var_60], r15
0x18001c114  mov     [rsp+98h+var_68], r15
0x18001c119  mov     [rsp+98h+var_70], r12d
0x18001c11e  mov     [rsp+98h+var_78], rsi
0x18001c123  mov     r8, r14
0x18001c126  xor     edx, edx
0x18001c128  mov     ecx, 0FDE9h
0x18001c12d  call    cs:__imp_?SafeWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; SafeWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18001c134  nop     dword ptr [rax+rax+00h]
0x18001c139  test    eax, eax
0x18001c13b  jle     loc_18001C0BA
0x18001c141  dec     r12d
0x18001c144  mov     edi, r15d
0x18001c147  lea     rcx, __ImageBase
0x18001c14e  lea     r8d, [r15+25h]
0x18001c152  cmp     edi, r12d
0x18001c155  jnb     loc_18001C2DC
0x18001c15b  mov     r14d, edi
0x18001c15e  movsx   rax, byte ptr [r14+rsi]
0x18001c163  cmp     rax, 80h
0x18001c169  jnb     short loc_18001C1B3
0x18001c16b  cmp     ds:rva dword_18002A2F0[rcx+rax*4], r15d
0x18001c173  jz      short loc_18001C1B3
0x18001c175  movsx   eax, byte ptr [r14+rsi]
0x18001c17a  mov     word ptr [rsp+98h+arg_0], ax
0x18001c182  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c187  cmp     rdx, [rsp+98h+var_48]
0x18001c18c  jz      short loc_18001C19C
0x18001c18e  mov     [rdx], ax
0x18001c191  add     qword ptr [rsp+98h+var_58+8], 2
0x18001c197  jmp     loc_18001C282
0x18001c19c  lea     r8, [rsp+98h+arg_0]
0x18001c1a4  lea     rcx, [rsp+98h+var_58]
0x18001c1a9  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18001c1ae  jmp     loc_18001C275
0x18001c1b3  mov     word ptr [rsp+98h+arg_0], r8w
0x18001c1bc  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c1c1  cmp     rdx, [rsp+98h+var_48]
0x18001c1c6  jz      short loc_18001C1DC
0x18001c1c8  mov     [rdx], r8w
0x18001c1cc  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c1d1  add     rdx, 2
0x18001c1d5  mov     qword ptr [rsp+98h+var_58+8], rdx
0x18001c1da  jmp     short loc_18001C1FA
0x18001c1dc  lea     r8, [rsp+98h+arg_0]
0x18001c1e4  lea     rcx, [rsp+98h+var_58]
0x18001c1e9  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18001c1ee  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c1f3  lea     rcx, __ImageBase
0x18001c1fa  movzx   eax, byte ptr [r14+rsi]
0x18001c1ff  shr     rax, 4
0x18001c203  lea     r8, ds:2A2C8h[rax*2]
0x18001c20b  add     r8, rcx
0x18001c20e  cmp     rdx, [rsp+98h+var_48]
0x18001c213  jz      short loc_18001C22C
0x18001c215  movzx   eax, word ptr [r8]
0x18001c219  mov     [rdx], ax
0x18001c21c  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c221  add     rdx, 2
0x18001c225  mov     qword ptr [rsp+98h+var_58+8], rdx
0x18001c22a  jmp     short loc_18001C242
0x18001c22c  lea     rcx, [rsp+98h+var_58]
0x18001c231  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18001c236  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c23b  lea     rcx, __ImageBase
0x18001c242  movsx   rax, byte ptr [r14+rsi]
0x18001c247  and     eax, 0Fh
0x18001c24a  lea     r8, ds:2A2C8h[rax*2]
0x18001c252  add     r8, rcx
0x18001c255  cmp     rdx, [rsp+98h+var_48]
0x18001c25a  jz      short loc_18001C26B
0x18001c25c  movzx   eax, word ptr [r8]
0x18001c260  mov     [rdx], ax
0x18001c263  add     qword ptr [rsp+98h+var_58+8], 2
0x18001c269  jmp     short loc_18001C27C
0x18001c26b  lea     rcx, [rsp+98h+var_58]
0x18001c270  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18001c275  lea     rcx, __ImageBase
0x18001c27c  mov     r8d, 25h ; '%'
0x18001c282  inc     edi
0x18001c284  jmp     loc_18001C152
0x18001c289  mov     rdi, [rsp+98h+arg_18]
0x18001c291  mov     rsi, [rsp+98h+arg_10]
0x18001c299  mov     ebx, [rsp+98h+arg_0]
0x18001c2a0  mov     rcx, rsi; hMem
0x18001c2a3  call    cs:__imp_LocalFree
0x18001c2aa  nop     dword ptr [rax+rax+00h]
0x18001c2af  mov     rcx, rdi; hMem
0x18001c2b2  call    cs:__imp_LocalFree
0x18001c2b9  nop     dword ptr [rax+rax+00h]
0x18001c2be  nop
0x18001c2bf  lea     rcx, [rsp+98h+var_58]
0x18001c2c4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001c2c9  mov     eax, ebx
0x18001c2cb  add     rsp, 60h
0x18001c2cf  pop     r15
0x18001c2d1  pop     r14
0x18001c2d3  pop     r13
0x18001c2d5  pop     r12
0x18001c2d7  pop     rdi
0x18001c2d8  pop     rsi
0x18001c2d9  pop     rbx
0x18001c2da  retn
0x18001c2dc  mov     r8, [rsp+98h+var_48]
0x18001c2e1  xor     r12d, r12d
0x18001c2e4  mov     word ptr [rsp+98h+arg_0], r12w
0x18001c2ed  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c2f2  cmp     rdx, r8
0x18001c2f5  jz      short loc_18001C30B
0x18001c2f7  mov     [rdx], r12w
0x18001c2fb  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c300  add     rdx, 2
0x18001c304  mov     qword ptr [rsp+98h+var_58+8], rdx
0x18001c309  jmp     short loc_18001C322
0x18001c30b  lea     r8, [rsp+98h+arg_0]
0x18001c313  lea     rcx, [rsp+98h+var_58]
0x18001c318  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18001c31d  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c322  sub     rdx, qword ptr [rsp+98h+var_58]
0x18001c327  sar     rdx, 1
0x18001c32a  add     rdx, rdx; uBytes
0x18001c32d  xor     ecx, ecx; uFlags
0x18001c32f  call    cs:__imp_LocalAlloc
0x18001c336  nop     dword ptr [rax+rax+00h]
0x18001c33b  mov     rdi, rax
0x18001c33e  test    rax, rax
0x18001c341  jz      loc_18001C0FF
0x18001c347  mov     rdx, qword ptr [rsp+98h+var_58+8]
0x18001c34c  mov     rax, qword ptr [rsp+98h+var_58]
0x18001c351  sub     rdx, rax
0x18001c354  sar     rdx, 1
0x18001c357  mov     r8d, r12d
0x18001c35a  test    edx, edx
0x18001c35c  jle     short loc_18001C378
0x18001c35e  mov     ecx, r8d
0x18001c361  movzx   eax, word ptr [rax+rcx*2]
0x18001c365  mov     [rdi+rcx*2], ax
0x18001c369  inc     r8d
0x18001c36c  cmp     r8d, edx
0x18001c36f  jge     short loc_18001C378
0x18001c371  mov     rax, qword ptr [rsp+98h+var_58]
0x18001c376  jmp     short loc_18001C35E
0x18001c378  mov     [r13+0], rdi
0x18001c37c  mov     rdi, r12
0x18001c37f  jmp     loc_18001C2A0
```
