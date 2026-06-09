# DetourAttachEx

- ea: `0x180078050`
- end: `0x180078441`
- name: `DetourAttachEx`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180078020`

## callees

- `0x18001b22c`
- `0x180076440`
- `0x180076f08`
- `0x180077ac0`
- `0x180077d50`
- `0x180077da0`
- `0x180078050`
- `0x180078450`
- `0x180079770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007837b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007837b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800780a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800780a7`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078371`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078371`

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
  if ( dword_180108E40 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_180108E44;
  if ( !dword_180108E44 )
  {
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      qword_180108E48 = (__int64)a1;
      dword_180108E44 = 6;
      return 6;
    }
    v11 = 0;
    v12 = (unsigned __int8 *)DetourCodeFromPointer(*a1, 0);
    v13 = DetourCodeFromPointer(a2, 0);
    v32 = v13;
    if ( (unsigned __int8 *)v13 == v12 )
    {
      LastError = 0;
      if ( !dword_180108E38 )
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
            *(_QWORD *)v15 = qword_180108E58;
            result = 0;
            qword_180108E58 = v15;
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
        if ( dword_180108E38 )
          goto LABEL_58;
LABEL_57:
        dword_180108E44 = LastError;
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
        qword_180108E48 = (__int64)a1;
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
0x180078050  push    rsi
0x180078052  push    rdi
0x180078053  push    r12
0x180078055  push    r13
0x180078057  push    r14
0x180078059  push    r15
0x18007805b  sub     rsp, 48h
0x18007805f  xor     r12d, r12d
0x180078062  mov     rsi, r9
0x180078065  mov     r15, r8
0x180078068  mov     r14, rdx
0x18007806b  mov     r13, rcx
0x18007806e  test    r8, r8
0x180078071  jz      short loc_180078076
0x180078073  mov     [r8], r12
0x180078076  test    rsi, rsi
0x180078079  jz      short loc_18007807E
0x18007807b  mov     [r9], r12
0x18007807e  mov     rdi, [rsp+78h+arg_20]
0x180078086  test    rdi, rdi
0x180078089  jz      short loc_18007808E
0x18007808b  mov     [rdi], r12
0x18007808e  test    r14, r14
0x180078091  jnz     short loc_1800780A7
0x180078093  mov     eax, 57h ; 'W'
0x180078098  add     rsp, 48h
0x18007809c  pop     r15
0x18007809e  pop     r14
0x1800780a0  pop     r13
0x1800780a2  pop     r12
0x1800780a4  pop     rdi
0x1800780a5  pop     rsi
0x1800780a6  retn
0x1800780a7  call    cs:__imp_GetCurrentThreadId
0x1800780ad  cmp     cs:dword_180108E40, eax
0x1800780b3  jz      short loc_1800780C9
0x1800780b5  mov     eax, 10DDh
0x1800780ba  add     rsp, 48h
0x1800780be  pop     r15
0x1800780c0  pop     r14
0x1800780c2  pop     r13
0x1800780c4  pop     r12
0x1800780c6  pop     rdi
0x1800780c7  pop     rsi
0x1800780c8  retn
0x1800780c9  mov     eax, cs:dword_180108E44
0x1800780cf  test    eax, eax
0x1800780d1  jnz     loc_180078432
0x1800780d7  test    r13, r13
0x1800780da  jnz     short loc_1800780F0
0x1800780dc  mov     eax, 6
0x1800780e1  add     rsp, 48h
0x1800780e5  pop     r15
0x1800780e7  pop     r14
0x1800780e9  pop     r13
0x1800780eb  pop     r12
0x1800780ed  pop     rdi
0x1800780ee  pop     rsi
0x1800780ef  retn
0x1800780f0  mov     rcx, [r13+0]
0x1800780f4  test    rcx, rcx
0x1800780f7  jnz     short loc_18007811C
0x1800780f9  mov     edi, 6
0x1800780fe  mov     cs:qword_180108E48, r13
0x180078105  mov     cs:dword_180108E44, edi
0x18007810b  mov     eax, edi
0x18007810d  add     rsp, 48h
0x180078111  pop     r15
0x180078113  pop     r14
0x180078115  pop     r13
0x180078117  pop     r12
0x180078119  pop     rdi
0x18007811a  pop     rsi
0x18007811b  retn
0x18007811c  mov     [rsp+78h+arg_0], rbx
0x180078124  xor     edx, edx
0x180078126  mov     [rsp+78h+var_38], rbp
0x18007812b  mov     rbx, r12
0x18007812e  call    DetourCodeFromPointer
0x180078133  xor     edx, edx
0x180078135  mov     rcx, r14
0x180078138  mov     rbp, rax
0x18007813b  call    DetourCodeFromPointer
0x180078140  mov     [rsp+78h+var_48], rax
0x180078145  cmp     rax, rbp
0x180078148  jnz     short loc_180078161
0x18007814a  cmp     cs:dword_180108E38, ebx
0x180078150  mov     edi, r12d
0x180078153  jnz     loc_18007841C
0x180078159  mov     r14, r12
0x18007815c  jmp     loc_1800783C3
0x180078161  test    rsi, rsi
0x180078164  jz      short loc_180078169
0x180078166  mov     [rsi], rbp
0x180078169  test    rdi, rdi
0x18007816c  jz      short loc_180078171
0x18007816e  mov     [rdi], rax
0x180078171  mov     ecx, 30h ; '0'; dwBytes
0x180078176  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007817b  mov     r14, rax
0x18007817e  test    rax, rax
0x180078181  jnz     short loc_18007818D
0x180078183  mov     edi, 8
0x180078188  jmp     loc_1800783C3
0x18007818d  mov     rcx, rbp
0x180078190  call    detour_alloc_trampoline
0x180078195  mov     rbx, rax
0x180078198  test    rax, rax
0x18007819b  jnz     short loc_1800781A7
0x18007819d  mov     edi, 8
0x1800781a2  jmp     loc_1800783C3
0x1800781a7  test    r15, r15
0x1800781aa  jz      short loc_1800781AF
0x1800781ac  mov     [r15], rbx
0x1800781af  xor     eax, eax
0x1800781b1  mov     dword ptr [rsp+78h+arg_20], 0
0x1800781bc  mov     [rbx+40h], rax
0x1800781c0  mov     rsi, rbp
0x1800781c3  lea     rax, [rbx+1Eh]
0x1800781c7  mov     r12, rbx
0x1800781ca  mov     [rsp+78h+arg_18], rax
0x1800781d2  lea     rax, [rsp+78h+arg_8]
0x1800781da  mov     [rsp+78h+arg_8], 0
0x1800781e5  xor     r9d, r9d
0x1800781e8  mov     [rsp+78h+var_58], rax
0x1800781ed  mov     r8, rsi
0x1800781f0  lea     rdx, [rsp+78h+arg_18]
0x1800781f8  mov     rcx, r12
0x1800781fb  mov     rdi, rsi
0x1800781fe  call    DetourCopyInstruction
0x180078203  mov     r9d, dword ptr [rsp+78h+arg_20]
0x18007820b  mov     rsi, rax
0x18007820e  movsxd  rax, [rsp+78h+arg_8]
0x180078216  mov     r8d, esi
0x180078219  sub     rax, rdi
0x18007821c  sub     r8d, ebp
0x18007821f  add     rax, rsi
0x180078222  add     r12, rax
0x180078225  movzx   eax, r8b
0x180078229  and     al, 7
0x18007822b  movzx   ecx, r12b
0x18007822f  sub     cl, bl
0x180078231  shl     cl, 3
0x180078234  or      cl, al
0x180078236  mov     [r9+rbx+40h], cl
0x18007823b  inc     r9d
0x18007823e  mov     dword ptr [rsp+78h+arg_20], r9d
0x180078246  cmp     r9d, 8
0x18007824a  jnb     short loc_1800782AC
0x18007824c  movzx   ecx, byte ptr [rdi]
0x18007824f  lea     eax, [rcx+3Eh]
0x180078252  cmp     al, 29h ; ')'
0x180078254  ja      short loc_180078266
0x180078256  mov     rdx, 28040000403h
0x180078260  bt      rdx, rax
0x180078264  jb      short loc_1800782AC
0x180078266  cmp     cl, 0F3h
0x180078269  jnz     short loc_180078271
0x18007826b  cmp     byte ptr [rdi+1], 0C3h
0x18007826f  jmp     short loc_18007829E
0x180078271  cmp     cl, 0FFh
0x180078274  jnz     short loc_18007827C
0x180078276  cmp     byte ptr [rdi+1], 25h ; '%'
0x18007827a  jmp     short loc_18007829E
0x18007827c  sub     cl, 26h ; '&'
0x18007827f  cmp     cl, 3Fh ; '?'
0x180078282  ja      short loc_1800782A0
0x180078284  mov     rax, 0C000000001010101h
0x18007828e  bt      rax, rcx
0x180078292  jnb     short loc_1800782A0
0x180078294  cmp     byte ptr [rdi+1], 0FFh
0x180078298  jnz     short loc_1800782A0
0x18007829a  cmp     byte ptr [rdi+2], 25h ; '%'
0x18007829e  jz      short loc_1800782AC
0x1800782a0  cmp     r8d, 5
0x1800782a4  jb      loc_1800781D2
0x1800782aa  jmp     short loc_1800782E5
0x1800782ac  cmp     r8d, 5
0x1800782b0  jnb     short loc_1800782DB
0x1800782b2  mov     rcx, rsi; unsigned __int8 *
0x1800782b5  call    ?detour_is_code_filler@@YAKPEAE@Z; detour_is_code_filler(uchar *)
0x1800782ba  test    eax, eax
0x1800782bc  jz      loc_1800783B5
0x1800782c2  cdqe
0x1800782c4  add     rsi, rax
0x1800782c7  mov     r8d, esi
0x1800782ca  sub     r8d, ebp; Size
0x1800782cd  cmp     r8d, 5
0x1800782d1  jb      short loc_1800782B2
0x1800782d3  mov     r9d, dword ptr [rsp+78h+arg_20]
0x1800782db  cmp     r9d, 8
0x1800782df  ja      loc_1800783B5
0x1800782e5  cmp     r12, [rsp+78h+arg_18]
0x1800782ed  jbe     short loc_1800782F0
0x1800782ef  int     3; Trap to Debugger
0x1800782f0  sub     r12b, bl
0x1800782f3  mov     [rbx+3Eh], r8b
0x1800782f7  lea     rcx, [rbx+20h]; void *
0x1800782fb  mov     [rbx+1Eh], r12b
0x1800782ff  mov     rdx, rbp; Src
0x180078302  mov     edi, r8d
0x180078305  call    memcpy_0
0x18007830a  cmp     rdi, 19h
0x18007830e  jbe     short loc_18007831A
0x180078310  mov     edi, 6
0x180078315  jmp     loc_1800783C3
0x18007831a  movzx   ecx, byte ptr [rbx+1Eh]
0x18007831e  lea     rax, [rdi+rbp]
0x180078322  mov     [rbx+48h], rax
0x180078326  add     rcx, rbx
0x180078329  mov     rax, [rsp+78h+var_48]
0x18007832e  mov     [rbx+50h], rax
0x180078332  mov     eax, ebx
0x180078334  sub     eax, ecx
0x180078336  mov     word ptr [rcx], 25FFh
0x18007833b  add     eax, 42h ; 'B'
0x18007833e  mov     [rcx+2], eax
0x180078341  add     rcx, 6; unsigned __int8 *
0x180078345  mov     rdx, [rsp+78h+arg_18]; unsigned __int8 *
0x18007834d  call    ?detour_gen_brk@@YAPEAEPEAE0@Z; detour_gen_brk(uchar *,uchar *)
0x180078352  xor     r12d, r12d
0x180078355  lea     r9, [rsp+78h+flOldProtect]; lpflOldProtect
0x18007835d  mov     r8d, 40h ; '@'; flNewProtect
0x180078363  mov     [rsp+78h+flOldProtect], r12d
0x18007836b  mov     rdx, rdi; dwSize
0x18007836e  mov     rcx, rbp; lpAddress
0x180078371  call    cs:__imp_VirtualProtect
0x180078377  test    eax, eax
0x180078379  jnz     short loc_180078385
0x18007837b  call    cs:__imp_GetLastError
0x180078381  mov     edi, eax
0x180078383  jmp     short loc_1800783C3
0x180078385  mov     [r14+8], r12d
0x180078389  mov     [r14+10h], r13
0x18007838d  mov     [r14+20h], rbx
0x180078391  mov     [r14+18h], rbp
0x180078395  mov     eax, [rsp+78h+flOldProtect]
0x18007839c  mov     [r14+28h], eax
0x1800783a0  mov     rax, cs:qword_180108E58
0x1800783a7  mov     [r14], rax
0x1800783aa  xor     eax, eax
0x1800783ac  mov     cs:qword_180108E58, r14
0x1800783b3  jmp     short loc_180078425
0x1800783b5  cmp     cs:dword_180108E38, 0
0x1800783bc  mov     edi, 9
0x1800783c1  jnz     short loc_1800783CE
0x1800783c3  mov     cs:dword_180108E44, edi
0x1800783c9  test    rbx, rbx
0x1800783cc  jz      short loc_18007840A
0x1800783ce  xorps   xmm0, xmm0
0x1800783d1  mov     r8, rbx
0x1800783d4  movups  xmmword ptr [rbx], xmm0
0x1800783d7  and     r8, 0FFFFFFFFFFFF0000h
0x1800783de  movups  xmmword ptr [rbx+10h], xmm0
0x1800783e2  movups  xmmword ptr [rbx+20h], xmm0
0x1800783e6  movups  xmmword ptr [rbx+30h], xmm0
0x1800783ea  movups  xmmword ptr [rbx+40h], xmm0
0x1800783ee  movups  xmmword ptr [rbx+50h], xmm0
0x1800783f2  mov     rax, [r8+10h]
0x1800783f6  mov     [rbx+48h], rax
0x1800783fa  mov     [r8+10h], rbx
0x1800783fe  test    r15, r15
0x180078401  jz      short loc_18007840A
0x180078403  mov     qword ptr [r15], 0
0x18007840a  test    r14, r14
0x18007840d  jz      short loc_18007841C
0x18007840f  mov     edx, 30h ; '0'; unsigned __int64
0x180078414  mov     rcx, r14; void *
0x180078417  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007841c  mov     cs:qword_180108E48, r13
0x180078423  mov     eax, edi
0x180078425  mov     rbx, [rsp+78h+arg_0]
0x18007842d  mov     rbp, [rsp+78h+var_38]
0x180078432  add     rsp, 48h
0x180078436  pop     r15
0x180078438  pop     r14
0x18007843a  pop     r13
0x18007843c  pop     r12
0x18007843e  pop     rdi
0x18007843f  pop     rsi
0x180078440  retn
```
