# DetourAttachEx

- ea: `0x1400022d0`
- end: `0x1400026c1`
- name: `DetourAttachEx`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400022a0`

## callees

- `0x140001d40`
- `0x140001fd0`
- `0x140002020`
- `0x1400022d0`
- `0x1400026d0`
- `0x140003800`
- `0x1400038cc`
- `0x140003965`
- `0x140003978`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002327`
- `KERNEL32!GetCurrentThreadId` at `0x140002327`
- `KERNEL32!VirtualProtect` at `0x1400025f1`
- `KERNEL32!VirtualProtect` at `0x1400025f1`
- `KERNEL32!GetLastError` at `0x1400025fb`
- `KERNEL32!GetLastError` at `0x1400025fb`

## pseudocode

```c
__int64 __fastcall DetourAttachEx(_QWORD *a1, __int64 a2, __int64 *a3, unsigned __int8 **a4, __int64 *a5)
{
  __int64 *v9; // rdi
  __int64 result; // rax
  __int64 v11; // rbx
  unsigned __int8 *v12; // rbp
  __int64 v13; // rax
  DWORD LastError; // edi
  _DWORD *v15; // r14
  __int64 v16; // rax
  unsigned __int8 *v17; // rsi
  unsigned __int64 v18; // r12
  unsigned __int8 *v19; // rdi
  __int64 v20; // rax
  int v21; // r9d
  size_t v22; // r8
  unsigned int v23; // r9d
  unsigned __int64 v24; // rcx
  __int64 v25; // rdx
  bool v26; // zf
  unsigned __int64 v27; // rax
  signed int is_code_filler; // eax
  SIZE_T v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // [rsp+30h] [rbp-48h]
  int v33; // [rsp+88h] [rbp+10h] BYREF
  DWORD flOldProtect; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int8 *v35; // [rsp+98h] [rbp+20h] BYREF

  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
    return 87;
  if ( dword_140017728 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_14001772C;
  if ( !dword_14001772C )
  {
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      qword_140017730 = (__int64)a1;
      dword_14001772C = 6;
      return 6;
    }
    v11 = 0;
    v12 = (unsigned __int8 *)DetourCodeFromPointer(*a1, 0);
    v13 = DetourCodeFromPointer(a2, 0);
    v32 = v13;
    if ( (unsigned __int8 *)v13 == v12 )
    {
      LastError = 0;
      if ( !dword_140017720 )
      {
        v15 = 0;
        goto LABEL_57;
      }
      goto LABEL_62;
    }
    if ( a4 )
      *a4 = v12;
    if ( v9 )
      *v9 = v13;
    v15 = operator new(0x30u);
    if ( !v15 )
    {
      LastError = 8;
      goto LABEL_57;
    }
    v16 = detour_alloc_trampoline(v12);
    v11 = v16;
    if ( !v16 )
    {
      LastError = 8;
      goto LABEL_57;
    }
    if ( a3 )
      *a3 = v16;
    LODWORD(a5) = 0;
    *(_QWORD *)(v16 + 64) = 0;
    v17 = v12;
    v18 = v16;
    v35 = (unsigned __int8 *)(v16 + 30);
    while ( 1 )
    {
      v33 = 0;
      v19 = v17;
      v20 = DetourCopyInstruction(v18, (unsigned int)&v35, (_DWORD)v17, 0, (__int64)&v33);
      v21 = (int)a5;
      v17 = (unsigned __int8 *)v20;
      v22 = (unsigned int)(v20 - (_DWORD)v12);
      v18 += v20 + v33 - (_QWORD)v19;
      *(_BYTE *)((unsigned int)a5 + v11 + 64) = (v20 - (_BYTE)v12) & 7 | (8 * (v18 - v11));
      v23 = v21 + 1;
      LODWORD(a5) = v23;
      if ( v23 >= 8
        || (v24 = *v19, (unsigned __int8)(v24 + 62) <= 0x29u)
        && (v25 = 0x28040000403LL, _bittest64(&v25, (unsigned int)(v24 + 62))) )
      {
LABEL_44:
        if ( (unsigned int)v22 >= 5 )
        {
LABEL_48:
          if ( v23 <= 8 )
          {
LABEL_49:
            if ( v18 > (unsigned __int64)v35 )
              __debugbreak();
            *(_BYTE *)(v11 + 62) = v22;
            *(_BYTE *)(v11 + 30) = v18 - v11;
            v29 = (unsigned int)v22;
            memcpy_0((void *)(v11 + 32), v12, v22);
            if ( v29 > 0x19 )
            {
              LastError = 6;
              goto LABEL_57;
            }
            v30 = *(unsigned __int8 *)(v11 + 30);
            *(_QWORD *)(v11 + 72) = &v12[v29];
            v31 = v11 + v30;
            *(_QWORD *)(v11 + 80) = v32;
            *(_WORD *)v31 = 9727;
            *(_DWORD *)(v31 + 2) = v11 - v31 + 66;
            detour_gen_brk((unsigned __int8 *)(v31 + 6), v35);
            flOldProtect = 0;
            if ( !VirtualProtect(v12, v29, 0x40u, &flOldProtect) )
            {
              LastError = GetLastError();
              goto LABEL_57;
            }
            v15[2] = 0;
            *((_QWORD *)v15 + 2) = a1;
            *((_QWORD *)v15 + 4) = v11;
            *((_QWORD *)v15 + 3) = v12;
            v15[10] = flOldProtect;
            *(_QWORD *)v15 = qword_140017740;
            result = 0;
            qword_140017740 = v15;
            return result;
          }
        }
        else
        {
          while ( 1 )
          {
            is_code_filler = detour_is_code_filler(v17);
            if ( !is_code_filler )
              break;
            v17 += is_code_filler;
            v22 = (unsigned int)((_DWORD)v17 - (_DWORD)v12);
            if ( (unsigned int)v22 >= 5 )
            {
              v23 = (unsigned int)a5;
              goto LABEL_48;
            }
          }
        }
        LastError = 9;
        if ( dword_140017720 )
          goto LABEL_58;
LABEL_57:
        dword_14001772C = LastError;
        if ( v11 )
        {
LABEL_58:
          *(_OWORD *)v11 = 0;
          *(_OWORD *)(v11 + 16) = 0;
          *(_OWORD *)(v11 + 32) = 0;
          *(_OWORD *)(v11 + 48) = 0;
          *(_OWORD *)(v11 + 64) = 0;
          *(_OWORD *)(v11 + 80) = 0;
          *(_QWORD *)(v11 + 72) = *(_QWORD *)((v11 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
          *(_QWORD *)((v11 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v11;
          if ( a3 )
            *a3 = 0;
        }
        if ( v15 )
          operator delete(v15, 0x30u);
LABEL_62:
        qword_140017730 = (__int64)a1;
        return LastError;
      }
      if ( (_BYTE)v24 == 0xF3 )
      {
        v26 = v19[1] == 0xC3;
        goto LABEL_41;
      }
      if ( (_BYTE)v24 == 0xFF )
        break;
      LOBYTE(v24) = v24 - 38;
      if ( (unsigned __int8)v24 <= 0x3Fu )
      {
        v27 = 0xC000000001010101uLL;
        if ( _bittest64((const __int64 *)&v27, v24) )
        {
          if ( v19[1] == 0xFF )
          {
            v26 = v19[2] == 37;
LABEL_41:
            if ( v26 )
              goto LABEL_44;
          }
        }
      }
      if ( (unsigned int)v22 >= 5 )
        goto LABEL_49;
    }
    v26 = v19[1] == 37;
    goto LABEL_41;
  }
  return result;
}

```

## disassembly

```asm
0x1400022d0  push    rsi
0x1400022d2  push    rdi
0x1400022d3  push    r12
0x1400022d5  push    r13
0x1400022d7  push    r14
0x1400022d9  push    r15
0x1400022db  sub     rsp, 48h
0x1400022df  xor     r12d, r12d
0x1400022e2  mov     rsi, r9
0x1400022e5  mov     r15, r8
0x1400022e8  mov     r14, rdx
0x1400022eb  mov     r13, rcx
0x1400022ee  test    r8, r8
0x1400022f1  jz      short loc_1400022F6
0x1400022f3  mov     [r8], r12
0x1400022f6  test    rsi, rsi
0x1400022f9  jz      short loc_1400022FE
0x1400022fb  mov     [r9], r12
0x1400022fe  mov     rdi, [rsp+78h+arg_20]
0x140002306  test    rdi, rdi
0x140002309  jz      short loc_14000230E
0x14000230b  mov     [rdi], r12
0x14000230e  test    r14, r14
0x140002311  jnz     short loc_140002327
0x140002313  mov     eax, 57h ; 'W'
0x140002318  add     rsp, 48h
0x14000231c  pop     r15
0x14000231e  pop     r14
0x140002320  pop     r13
0x140002322  pop     r12
0x140002324  pop     rdi
0x140002325  pop     rsi
0x140002326  retn
0x140002327  call    cs:__imp_GetCurrentThreadId
0x14000232d  cmp     cs:dword_140017728, eax
0x140002333  jz      short loc_140002349
0x140002335  mov     eax, 10DDh
0x14000233a  add     rsp, 48h
0x14000233e  pop     r15
0x140002340  pop     r14
0x140002342  pop     r13
0x140002344  pop     r12
0x140002346  pop     rdi
0x140002347  pop     rsi
0x140002348  retn
0x140002349  mov     eax, cs:dword_14001772C
0x14000234f  test    eax, eax
0x140002351  jnz     loc_1400026B2
0x140002357  test    r13, r13
0x14000235a  jnz     short loc_140002370
0x14000235c  mov     eax, 6
0x140002361  add     rsp, 48h
0x140002365  pop     r15
0x140002367  pop     r14
0x140002369  pop     r13
0x14000236b  pop     r12
0x14000236d  pop     rdi
0x14000236e  pop     rsi
0x14000236f  retn
0x140002370  mov     rcx, [r13+0]
0x140002374  test    rcx, rcx
0x140002377  jnz     short loc_14000239C
0x140002379  mov     edi, 6
0x14000237e  mov     cs:qword_140017730, r13
0x140002385  mov     cs:dword_14001772C, edi
0x14000238b  mov     eax, edi
0x14000238d  add     rsp, 48h
0x140002391  pop     r15
0x140002393  pop     r14
0x140002395  pop     r13
0x140002397  pop     r12
0x140002399  pop     rdi
0x14000239a  pop     rsi
0x14000239b  retn
0x14000239c  mov     [rsp+78h+arg_0], rbx
0x1400023a4  xor     edx, edx
0x1400023a6  mov     [rsp+78h+var_38], rbp
0x1400023ab  mov     rbx, r12
0x1400023ae  call    DetourCodeFromPointer
0x1400023b3  xor     edx, edx
0x1400023b5  mov     rcx, r14
0x1400023b8  mov     rbp, rax
0x1400023bb  call    DetourCodeFromPointer
0x1400023c0  mov     [rsp+78h+var_48], rax
0x1400023c5  cmp     rax, rbp
0x1400023c8  jnz     short loc_1400023E1
0x1400023ca  cmp     cs:dword_140017720, ebx
0x1400023d0  mov     edi, r12d
0x1400023d3  jnz     loc_14000269C
0x1400023d9  mov     r14, r12
0x1400023dc  jmp     loc_140002643
0x1400023e1  test    rsi, rsi
0x1400023e4  jz      short loc_1400023E9
0x1400023e6  mov     [rsi], rbp
0x1400023e9  test    rdi, rdi
0x1400023ec  jz      short loc_1400023F1
0x1400023ee  mov     [rdi], rax
0x1400023f1  mov     ecx, 30h ; '0'; dwBytes
0x1400023f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400023fb  mov     r14, rax
0x1400023fe  test    rax, rax
0x140002401  jnz     short loc_14000240D
0x140002403  mov     edi, 8
0x140002408  jmp     loc_140002643
0x14000240d  mov     rcx, rbp
0x140002410  call    detour_alloc_trampoline
0x140002415  mov     rbx, rax
0x140002418  test    rax, rax
0x14000241b  jnz     short loc_140002427
0x14000241d  mov     edi, 8
0x140002422  jmp     loc_140002643
0x140002427  test    r15, r15
0x14000242a  jz      short loc_14000242F
0x14000242c  mov     [r15], rbx
0x14000242f  xor     eax, eax
0x140002431  mov     dword ptr [rsp+78h+arg_20], 0
0x14000243c  mov     [rbx+40h], rax
0x140002440  mov     rsi, rbp
0x140002443  lea     rax, [rbx+1Eh]
0x140002447  mov     r12, rbx
0x14000244a  mov     [rsp+78h+arg_18], rax
0x140002452  lea     rax, [rsp+78h+arg_8]
0x14000245a  mov     [rsp+78h+arg_8], 0
0x140002465  xor     r9d, r9d
0x140002468  mov     [rsp+78h+var_58], rax
0x14000246d  mov     r8, rsi
0x140002470  lea     rdx, [rsp+78h+arg_18]
0x140002478  mov     rcx, r12
0x14000247b  mov     rdi, rsi
0x14000247e  call    DetourCopyInstruction
0x140002483  mov     r9d, dword ptr [rsp+78h+arg_20]
0x14000248b  mov     rsi, rax
0x14000248e  movsxd  rax, [rsp+78h+arg_8]
0x140002496  mov     r8d, esi
0x140002499  sub     rax, rdi
0x14000249c  sub     r8d, ebp
0x14000249f  add     rax, rsi
0x1400024a2  add     r12, rax
0x1400024a5  movzx   eax, r8b
0x1400024a9  and     al, 7
0x1400024ab  movzx   ecx, r12b
0x1400024af  sub     cl, bl
0x1400024b1  shl     cl, 3
0x1400024b4  or      cl, al
0x1400024b6  mov     [r9+rbx+40h], cl
0x1400024bb  inc     r9d
0x1400024be  mov     dword ptr [rsp+78h+arg_20], r9d
0x1400024c6  cmp     r9d, 8
0x1400024ca  jnb     short loc_14000252C
0x1400024cc  movzx   ecx, byte ptr [rdi]
0x1400024cf  lea     eax, [rcx+3Eh]
0x1400024d2  cmp     al, 29h ; ')'
0x1400024d4  ja      short loc_1400024E6
0x1400024d6  mov     rdx, 28040000403h
0x1400024e0  bt      rdx, rax
0x1400024e4  jb      short loc_14000252C
0x1400024e6  cmp     cl, 0F3h
0x1400024e9  jnz     short loc_1400024F1
0x1400024eb  cmp     byte ptr [rdi+1], 0C3h
0x1400024ef  jmp     short loc_14000251E
0x1400024f1  cmp     cl, 0FFh
0x1400024f4  jnz     short loc_1400024FC
0x1400024f6  cmp     byte ptr [rdi+1], 25h ; '%'
0x1400024fa  jmp     short loc_14000251E
0x1400024fc  sub     cl, 26h ; '&'
0x1400024ff  cmp     cl, 3Fh ; '?'
0x140002502  ja      short loc_140002520
0x140002504  mov     rax, 0C000000001010101h
0x14000250e  bt      rax, rcx
0x140002512  jnb     short loc_140002520
0x140002514  cmp     byte ptr [rdi+1], 0FFh
0x140002518  jnz     short loc_140002520
0x14000251a  cmp     byte ptr [rdi+2], 25h ; '%'
0x14000251e  jz      short loc_14000252C
0x140002520  cmp     r8d, 5
0x140002524  jb      loc_140002452
0x14000252a  jmp     short loc_140002565
0x14000252c  cmp     r8d, 5
0x140002530  jnb     short loc_14000255B
0x140002532  mov     rcx, rsi; unsigned __int8 *
0x140002535  call    ?detour_is_code_filler@@YAKPEAE@Z; detour_is_code_filler(uchar *)
0x14000253a  test    eax, eax
0x14000253c  jz      loc_140002635
0x140002542  cdqe
0x140002544  add     rsi, rax
0x140002547  mov     r8d, esi
0x14000254a  sub     r8d, ebp; Size
0x14000254d  cmp     r8d, 5
0x140002551  jb      short loc_140002532
0x140002553  mov     r9d, dword ptr [rsp+78h+arg_20]
0x14000255b  cmp     r9d, 8
0x14000255f  ja      loc_140002635
0x140002565  cmp     r12, [rsp+78h+arg_18]
0x14000256d  jbe     short loc_140002570
0x14000256f  int     3; Trap to Debugger
0x140002570  sub     r12b, bl
0x140002573  mov     [rbx+3Eh], r8b
0x140002577  lea     rcx, [rbx+20h]; void *
0x14000257b  mov     [rbx+1Eh], r12b
0x14000257f  mov     rdx, rbp; Src
0x140002582  mov     edi, r8d
0x140002585  call    memcpy_0
0x14000258a  cmp     rdi, 19h
0x14000258e  jbe     short loc_14000259A
0x140002590  mov     edi, 6
0x140002595  jmp     loc_140002643
0x14000259a  movzx   ecx, byte ptr [rbx+1Eh]
0x14000259e  lea     rax, [rdi+rbp]
0x1400025a2  mov     [rbx+48h], rax
0x1400025a6  add     rcx, rbx
0x1400025a9  mov     rax, [rsp+78h+var_48]
0x1400025ae  mov     [rbx+50h], rax
0x1400025b2  mov     eax, ebx
0x1400025b4  sub     eax, ecx
0x1400025b6  mov     word ptr [rcx], 25FFh
0x1400025bb  add     eax, 42h ; 'B'
0x1400025be  mov     [rcx+2], eax
0x1400025c1  add     rcx, 6; unsigned __int8 *
0x1400025c5  mov     rdx, [rsp+78h+arg_18]; unsigned __int8 *
0x1400025cd  call    ?detour_gen_brk@@YAPEAEPEAE0@Z; detour_gen_brk(uchar *,uchar *)
0x1400025d2  xor     r12d, r12d
0x1400025d5  lea     r9, [rsp+78h+flOldProtect]; lpflOldProtect
0x1400025dd  mov     r8d, 40h ; '@'; flNewProtect
0x1400025e3  mov     [rsp+78h+flOldProtect], r12d
0x1400025eb  mov     rdx, rdi; dwSize
0x1400025ee  mov     rcx, rbp; lpAddress
0x1400025f1  call    cs:__imp_VirtualProtect
0x1400025f7  test    eax, eax
0x1400025f9  jnz     short loc_140002605
0x1400025fb  call    cs:__imp_GetLastError
0x140002601  mov     edi, eax
0x140002603  jmp     short loc_140002643
0x140002605  mov     [r14+8], r12d
0x140002609  mov     [r14+10h], r13
0x14000260d  mov     [r14+20h], rbx
0x140002611  mov     [r14+18h], rbp
0x140002615  mov     eax, [rsp+78h+flOldProtect]
0x14000261c  mov     [r14+28h], eax
0x140002620  mov     rax, cs:qword_140017740
0x140002627  mov     [r14], rax
0x14000262a  xor     eax, eax
0x14000262c  mov     cs:qword_140017740, r14
0x140002633  jmp     short loc_1400026A5
0x140002635  cmp     cs:dword_140017720, 0
0x14000263c  mov     edi, 9
0x140002641  jnz     short loc_14000264E
0x140002643  mov     cs:dword_14001772C, edi
0x140002649  test    rbx, rbx
0x14000264c  jz      short loc_14000268A
0x14000264e  xorps   xmm0, xmm0
0x140002651  mov     r8, rbx
0x140002654  movups  xmmword ptr [rbx], xmm0
0x140002657  and     r8, 0FFFFFFFFFFFF0000h
0x14000265e  movups  xmmword ptr [rbx+10h], xmm0
0x140002662  movups  xmmword ptr [rbx+20h], xmm0
0x140002666  movups  xmmword ptr [rbx+30h], xmm0
0x14000266a  movups  xmmword ptr [rbx+40h], xmm0
0x14000266e  movups  xmmword ptr [rbx+50h], xmm0
0x140002672  mov     rax, [r8+10h]
0x140002676  mov     [rbx+48h], rax
0x14000267a  mov     [r8+10h], rbx
0x14000267e  test    r15, r15
0x140002681  jz      short loc_14000268A
0x140002683  mov     qword ptr [r15], 0
0x14000268a  test    r14, r14
0x14000268d  jz      short loc_14000269C
0x14000268f  mov     edx, 30h ; '0'; unsigned __int64
0x140002694  mov     rcx, r14; void *
0x140002697  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000269c  mov     cs:qword_140017730, r13
0x1400026a3  mov     eax, edi
0x1400026a5  mov     rbx, [rsp+78h+arg_0]
0x1400026ad  mov     rbp, [rsp+78h+var_38]
0x1400026b2  add     rsp, 48h
0x1400026b6  pop     r15
0x1400026b8  pop     r14
0x1400026ba  pop     r13
0x1400026bc  pop     r12
0x1400026be  pop     rdi
0x1400026bf  pop     rsi
0x1400026c0  retn
```
