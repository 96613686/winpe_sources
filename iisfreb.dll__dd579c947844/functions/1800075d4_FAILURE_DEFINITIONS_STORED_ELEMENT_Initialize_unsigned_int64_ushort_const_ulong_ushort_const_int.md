# FAILURE_DEFINITIONS_STORED_ELEMENT::Initialize(unsigned __int64,ushort const *,ulong,ushort const *,int)

- ea: `0x1800075d4`
- end: `0x18000787a`
- name: `?Initialize@FAILURE_DEFINITIONS_STORED_ELEMENT@@QEAAJ_KPEBGK1H@Z`
- size: `678`
- prototype: `__int64 __fastcall(FAILURE_DEFINITIONS_STORED_ELEMENT *this, unsigned __int64, const unsigned __int16 *, int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007e6c`

## callees

- `0x180001008`
- `0x180005974`
- `0x1800075d4`
- `0x180007880`
- `0x18000a4dc`

## import_xrefs

- `msvcrt!iswspace` at `0x1800076e5`
- `msvcrt!iswspace` at `0x1800076f6`
- `msvcrt!iswspace` at `0x180007719`
- `msvcrt!iswspace` at `0x180007738`
- `msvcrt!iswspace` at `0x180007801`
- `msvcrt!iswspace` at `0x1800076e5`
- `msvcrt!iswspace` at `0x1800076f6`
- `msvcrt!iswspace` at `0x180007719`
- `msvcrt!iswspace` at `0x180007738`
- `msvcrt!iswspace` at `0x180007801`

## pseudocode

```c
__int64 __fastcall FAILURE_DEFINITIONS_STORED_ELEMENT::Initialize(
        FAILURE_DEFINITIONS_STORED_ELEMENT *this,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  int v6; // eax
  int v7; // r12d
  const unsigned __int16 *v8; // r15
  int i; // ecx
  int v11; // eax
  unsigned __int16 v12; // dx
  unsigned __int64 v13; // rdi
  TRACE_AREAS_STORED_ENTRY *v14; // rax
  FAILURE_DEFINITIONS_STORED_ELEMENT *v15; // rcx
  TRACE_AREAS_STORED_ENTRY *v16; // rbx
  TRACE_AREAS_STORED_ENTRY *j; // rsi
  signed int v18; // ebx
  bool v19; // zf
  unsigned int v20; // r13d
  unsigned __int16 *k; // rbx
  unsigned int v22; // edi
  unsigned int v23; // esi
  unsigned __int16 *v24; // rbx
  FAILURE_DEFINITIONS_STORED_ELEMENT *v25; // rcx
  unsigned __int16 *v26; // rdi
  __int16 v27; // r8
  __int16 v28; // dx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int16 *v33[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v34; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v36; // [rsp+B0h] [rbp+58h] BYREF
  unsigned int v37; // [rsp+B8h] [rbp+60h] BYREF

  *((_DWORD *)this + 5) = a4;
  v6 = a6;
  v7 = 0;
  v8 = a3;
  *(_DWORD *)this = a2 / 0x989680;
  *((_DWORD *)this + 6) = v6;
  if ( a3 )
  {
    for ( i = 0; ; i = v11 )
    {
      v12 = *a3;
      if ( !*a3 )
        break;
      v11 = i + 1;
      ++a3;
      if ( v12 != 44 )
        v11 = i;
    }
    v13 = (unsigned int)(i + 1);
    v14 = (TRACE_AREAS_STORED_ENTRY *)operator new(saturated_mul(v13, 0xCu));
    v16 = v14;
    if ( v14 )
    {
      for ( j = v14; v13; --v13 )
      {
        TRACE_AREAS_STORED_ENTRY::TRACE_AREAS_STORED_ENTRY(j);
        j = (TRACE_AREAS_STORED_ENTRY *)((char *)j + 12);
      }
    }
    else
    {
      v16 = 0;
    }
    *((_QWORD *)this + 1) = v16;
    if ( v16 )
    {
      v19 = *v8 == 0;
      v20 = 0;
      for ( k = (unsigned __int16 *)v8; ; v19 = *k == 0 )
      {
        v36 = k;
        if ( v19 )
        {
          *((_DWORD *)this + 4) = v20;
          return 0;
        }
        v34 = 0;
        v22 = 0xFFFF;
        v37 = 0xFFFF;
        v35 = 0xFFFF;
        a6 = 0;
        v23 = 0;
        v18 = FAILURE_DEFINITIONS_STORED_ELEMENT::ParseStatusSubStatus(
                v15,
                k,
                &v34,
                &v35,
                (const unsigned __int16 **)&v36);
        if ( v18 < 0 )
          goto LABEL_48;
        k = v36;
        if ( iswspace(*v36) )
        {
          do
            ++k;
          while ( iswspace(*k) );
          v36 = k;
        }
        if ( *k == 45 )
        {
          v24 = k + 1;
          v36 = v24;
          if ( iswspace(*v24) )
          {
            v26 = v24 + 1;
            do
            {
              v24 = v26++;
              v36 = v24;
            }
            while ( iswspace(*v24) );
          }
          if ( !*v24 )
          {
            v18 = -2147024883;
            goto LABEL_48;
          }
          v7 = 1;
          v18 = FAILURE_DEFINITIONS_STORED_ELEMENT::ParseStatusSubStatus(
                  v25,
                  v24,
                  &a6,
                  &v37,
                  (const unsigned __int16 **)&v36);
          if ( v18 < 0 )
            goto LABEL_48;
          k = v36;
          v23 = a6;
          v22 = v37;
        }
        v27 = v34;
        if ( v34 - 1 > 0x3E6 )
          break;
        v28 = v35;
        if ( v35 != 0xFFFF && v35 - 1 > 0x3E6 )
          break;
        if ( v7 && (v23 - 1 > 0x3E6 || v22 != 0xFFFF && v22 - 1 > 0x3E6 || v23 < v34 || v23 == v34 && v22 < v35) )
          break;
        v29 = v20++;
        v30 = 3 * v29;
        v31 = *((_QWORD *)this + 1);
        *(_DWORD *)(v31 + 4 * v30) = v7;
        v7 = 0;
        *(_WORD *)(v31 + 4 * v30 + 4) = v27;
        *(_WORD *)(v31 + 4 * v30 + 6) = v28;
        *(_WORD *)(v31 + 4 * v30 + 8) = v23;
        *(_WORD *)(v31 + 4 * v30 + 10) = v22;
        while ( iswspace(*k) || *k == 44 )
          ++k;
      }
      v18 = -2147024883;
    }
    else
    {
      v18 = -2147024888;
    }
LABEL_48:
    v33[3] = a5;
    v33[0] = 0;
    v33[1] = 0;
    v33[2] = (unsigned __int16 *)v8;
    FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008EE, 4u, (const unsigned __int16 **const)v33, v18);
  }
  else
  {
    *((_DWORD *)this + 4) = 0;
    return 0;
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800075d4  push    rbp
0x1800075d6  push    rbx
0x1800075d7  push    rsi
0x1800075d8  push    rdi
0x1800075d9  push    r12
0x1800075db  push    r13
0x1800075dd  push    r14
0x1800075df  push    r15
0x1800075e1  mov     rbp, rsp
0x1800075e4  sub     rsp, 58h
0x1800075e8  mov     rax, 0D6BF94D5E57A42BDh
0x1800075f2  mov     [rcx+14h], r9d
0x1800075f6  mul     rdx
0x1800075f9  mov     eax, [rbp+arg_28]
0x1800075fc  xor     r12d, r12d
0x1800075ff  shr     rdx, 17h
0x180007603  mov     r15, r8
0x180007606  mov     [rcx], edx
0x180007608  mov     r14, rcx
0x18000760b  mov     [rcx+18h], eax
0x18000760e  test    r8, r8
0x180007611  jnz     short loc_18000761C
0x180007613  mov     [rcx+10h], r12d
0x180007617  jmp     loc_180007829
0x18000761c  mov     ecx, r12d
0x18000761f  jmp     short loc_180007631
0x180007621  lea     eax, [rcx+1]
0x180007624  cmp     dx, 2Ch ; ','
0x180007628  lea     r8, [r8+2]
0x18000762c  cmovnz  eax, ecx
0x18000762f  mov     ecx, eax
0x180007631  movzx   edx, word ptr [r8]
0x180007635  test    dx, dx
0x180007638  jnz     short loc_180007621
0x18000763a  lea     edi, [rcx+1]
0x18000763d  mov     eax, 0Ch
0x180007642  mul     rdi
0x180007645  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000764c  cmovb   rax, rcx
0x180007650  mov     rcx, rax; Size
0x180007653  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007658  mov     rbx, rax
0x18000765b  test    rax, rax
0x18000765e  jz      short loc_18000767C
0x180007660  mov     rsi, rax
0x180007663  test    rdi, rdi
0x180007666  jz      short loc_18000767F
0x180007668  mov     rcx, rsi; this
0x18000766b  call    ??0TRACE_AREAS_STORED_ENTRY@@QEAA@XZ; TRACE_AREAS_STORED_ENTRY::TRACE_AREAS_STORED_ENTRY(void)
0x180007670  add     rsi, 0Ch
0x180007674  sub     rdi, 1
0x180007678  jnz     short loc_180007668
0x18000767a  jmp     short loc_18000767F
0x18000767c  mov     rbx, r12
0x18000767f  mov     [r14+8], rbx
0x180007683  test    rbx, rbx
0x180007686  jnz     short loc_180007692
0x180007688  mov     ebx, 80070008h
0x18000768d  jmp     loc_18000784E
0x180007692  cmp     [r15], r12w
0x180007696  mov     r13d, r12d
0x180007699  mov     rbx, r15
0x18000769c  jmp     loc_18000781B
0x1800076a1  lea     rax, [rbp+arg_10]
0x1800076a5  mov     [rbp+arg_0], r12d
0x1800076a9  mov     edi, 0FFFFh
0x1800076ae  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x1800076b3  lea     r9, [rbp+arg_8]; unsigned int *
0x1800076b7  mov     [rbp+arg_18], edi
0x1800076ba  lea     r8, [rbp+arg_0]; unsigned int *
0x1800076be  mov     [rbp+arg_8], 0FFFFh
0x1800076c5  mov     rdx, rbx; unsigned __int16 *
0x1800076c8  mov     [rbp+arg_28], r12d
0x1800076cc  mov     esi, r12d
0x1800076cf  call    ?ParseStatusSubStatus@FAILURE_DEFINITIONS_STORED_ELEMENT@@AEAAJPEBGPEAK1PEAPEBG@Z; FAILURE_DEFINITIONS_STORED_ELEMENT::ParseStatusSubStatus(ushort const *,ulong *,ulong *,ushort const * *)
0x1800076d4  mov     ebx, eax
0x1800076d6  test    eax, eax
0x1800076d8  js      loc_18000784E
0x1800076de  mov     rbx, [rbp+arg_10]
0x1800076e2  movzx   ecx, word ptr [rbx]; C
0x1800076e5  call    cs:__imp_iswspace
0x1800076eb  test    eax, eax
0x1800076ed  jz      short loc_180007704
0x1800076ef  add     rbx, 2
0x1800076f3  movzx   ecx, word ptr [rbx]; C
0x1800076f6  call    cs:__imp_iswspace
0x1800076fc  test    eax, eax
0x1800076fe  jnz     short loc_1800076EF
0x180007700  mov     [rbp+arg_10], rbx
0x180007704  mov     eax, 2Dh ; '-'
0x180007709  cmp     ax, [rbx]
0x18000770c  jnz     short loc_18000777F
0x18000770e  add     rbx, 2
0x180007712  mov     [rbp+arg_10], rbx
0x180007716  movzx   ecx, word ptr [rbx]; C
0x180007719  call    cs:__imp_iswspace
0x18000771f  xor     r12d, r12d
0x180007722  test    eax, eax
0x180007724  jz      short loc_180007742
0x180007726  lea     rdi, [rbx+2]
0x18000772a  mov     rbx, rdi
0x18000772d  add     rdi, 2
0x180007731  mov     [rbp+arg_10], rbx
0x180007735  movzx   ecx, word ptr [rbx]; C
0x180007738  call    cs:__imp_iswspace
0x18000773e  test    eax, eax
0x180007740  jnz     short loc_18000772A
0x180007742  cmp     r12w, [rbx]
0x180007746  jz      loc_18000783F
0x18000774c  lea     rax, [rbp+arg_10]
0x180007750  mov     rdx, rbx; unsigned __int16 *
0x180007753  lea     r9, [rbp+arg_18]; unsigned int *
0x180007757  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x18000775c  lea     r8, [rbp+arg_28]; unsigned int *
0x180007760  mov     r12d, 1
0x180007766  call    ?ParseStatusSubStatus@FAILURE_DEFINITIONS_STORED_ELEMENT@@AEAAJPEBGPEAK1PEAPEBG@Z; FAILURE_DEFINITIONS_STORED_ELEMENT::ParseStatusSubStatus(ushort const *,ulong *,ulong *,ushort const * *)
0x18000776b  mov     ebx, eax
0x18000776d  test    eax, eax
0x18000776f  js      loc_18000784B
0x180007775  mov     rbx, [rbp+arg_10]
0x180007779  mov     esi, [rbp+arg_28]
0x18000777c  mov     edi, [rbp+arg_18]
0x18000777f  mov     r8d, [rbp+arg_0]
0x180007783  mov     ecx, 3E6h
0x180007788  lea     eax, [r8-1]
0x18000778c  cmp     eax, ecx
0x18000778e  ja      loc_180007846
0x180007794  mov     edx, [rbp+arg_8]
0x180007797  mov     r9d, 0FFFFh
0x18000779d  cmp     edx, r9d
0x1800077a0  jz      short loc_1800077AD
0x1800077a2  lea     eax, [rdx-1]
0x1800077a5  cmp     eax, ecx
0x1800077a7  ja      loc_180007846
0x1800077ad  test    r12d, r12d
0x1800077b0  jz      short loc_1800077D4
0x1800077b2  lea     eax, [rsi-1]
0x1800077b5  cmp     eax, ecx
0x1800077b7  ja      loc_180007846
0x1800077bd  cmp     edi, r9d
0x1800077c0  jz      short loc_1800077C9
0x1800077c2  lea     eax, [rdi-1]
0x1800077c5  cmp     eax, ecx
0x1800077c7  ja      short loc_180007846
0x1800077c9  cmp     esi, r8d
0x1800077cc  jb      short loc_180007846
0x1800077ce  jnz     short loc_1800077D4
0x1800077d0  cmp     edi, edx
0x1800077d2  jb      short loc_180007846
0x1800077d4  mov     eax, r13d
0x1800077d7  inc     r13d
0x1800077da  lea     rcx, [rax+rax*2]
0x1800077de  mov     rax, [r14+8]
0x1800077e2  mov     [rax+rcx*4], r12d
0x1800077e6  xor     r12d, r12d
0x1800077e9  mov     [rax+rcx*4+4], r8w
0x1800077ef  mov     [rax+rcx*4+6], dx
0x1800077f4  mov     [rax+rcx*4+8], si
0x1800077f9  mov     [rax+rcx*4+0Ah], di
0x1800077fe  movzx   ecx, word ptr [rbx]; C
0x180007801  call    cs:__imp_iswspace
0x180007807  test    eax, eax
0x180007809  jnz     short loc_180007811
0x18000780b  cmp     word ptr [rbx], 2Ch ; ','
0x18000780f  jnz     short loc_180007817
0x180007811  add     rbx, 2
0x180007815  jmp     short loc_1800077FE
0x180007817  cmp     [rbx], r12w
0x18000781b  mov     [rbp+arg_10], rbx
0x18000781f  jnz     loc_1800076A1
0x180007825  mov     [r14+10h], r13d
0x180007829  mov     ebx, r12d
0x18000782c  mov     eax, ebx
0x18000782e  add     rsp, 58h
0x180007832  pop     r15
0x180007834  pop     r14
0x180007836  pop     r13
0x180007838  pop     r12
0x18000783a  pop     rdi
0x18000783b  pop     rsi
0x18000783c  pop     rbx
0x18000783d  pop     rbp
0x18000783e  retn
0x18000783f  mov     ebx, 8007000Dh
0x180007844  jmp     short loc_18000784E
0x180007846  mov     ebx, 8007000Dh
0x18000784b  xor     r12d, r12d
0x18000784e  mov     rax, [rbp+arg_20]
0x180007852  lea     r8, [rbp+var_28]; unsigned __int16 **
0x180007856  mov     edx, 4; unsigned __int16
0x18000785b  mov     [rbp+var_10], rax
0x18000785f  mov     r9d, ebx; unsigned int
0x180007862  mov     [rbp+var_28], r12
0x180007866  mov     ecx, 800008EEh; unsigned int
0x18000786b  mov     [rbp+var_20], r12
0x18000786f  mov     [rbp+var_18], r15
0x180007873  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007878  jmp     short loc_18000782C
```
