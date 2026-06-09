# NameTbl::CreateVval(SYM *,VVAL * *,long *)

- ea: `0x180012bc0`
- end: `0x180012e99`
- name: `?CreateVval@NameTbl@@IEAAJPEAUSYM@@PEAPEAUVVAL@@PEAJ@Z`
- size: `729`
- prototype: `__int64 __fastcall(NameTbl *this, struct SYM *, struct VVAL **, int *)`
- caller_count: `41`
- callee_count: `7`
- tags: ``

## callers

- `0x180011d30`
- `0x180012b60`
- `0x1800131e0`
- `0x180013ce0`
- `0x180014da0`
- `0x18002fdb0`
- `0x18003f330`
- `0x1800433c0`
- `0x1800436d0`
- `0x1800457e0`
- `0x180045bc0`
- `0x180047330`
- `0x180047d40`
- `0x180049644`
- `0x18004af70`
- `0x18004b220`
- `0x18004c2f0`
- `0x18004c4d0`
- `0x18004c5f0`
- `0x18004c860`
- `0x18004c980`
- `0x180050080`
- `0x18005e850`
- `0x1800610e0`
- `0x180061190`
- `0x180061290`
- `0x180061340`
- `0x180061600`
- `0x1800616b0`
- `0x180061760`
- `0x180061810`
- `0x180063150`
- `0x1800634b0`
- `0x180068990`
- `0x18006a910`
- `0x18006a9c0`
- `0x18006aa70`
- `0x18006ad70`
- `0x18006fa80`
- `0x180070030`
- `0x180070190`

## callees

- `0x180012bc0`
- `0x180012ea0`
- `0x18002f230`
- `0x18002f434`
- `0x180096692`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `msvcrt!malloc` at `0x180012c11`
- `msvcrt!malloc` at `0x180012d8a`
- `msvcrt!malloc` at `0x180012e55`
- `msvcrt!malloc` at `0x180012c11`
- `msvcrt!malloc` at `0x180012d8a`
- `msvcrt!malloc` at `0x180012e55`

## pseudocode

```c
__int64 __fastcall NameTbl::CreateVval(NameTbl *this, struct SYM *a2, struct VVAL **a3, int *a4)
{
  int *v4; // r12
  __int64 v7; // rbx
  size_t v8; // rdi
  void *v9; // rax
  unsigned int v10; // ebp
  NameList::NME **v11; // r14
  NameList::NME **v12; // rsi
  NameList::NME *v13; // rdi
  int v14; // edi
  int v15; // r12d
  int v16; // ebp
  _QWORD *v17; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 result; // rax
  int v21; // esi
  int v22; // ecx
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  _QWORD *v26; // rdx

  v4 = a4;
  if ( *((_QWORD *)this + 2)
    || (result = (*(__int64 (__fastcall **)(NameTbl *))(*(_QWORD *)this + 416LL))(this), (int)result >= 0) )
  {
    v7 = *((_QWORD *)this + 2);
    if ( *(_QWORD *)(v7 + 56) )
    {
      if ( *(_DWORD *)(v7 + 12) >= *(_DWORD *)(v7 + 68) )
        NameList::Rehash(*((NameList **)this + 2));
    }
    else
    {
      v8 = 8 * *(_DWORD *)(v7 + 64) + 8;
      v9 = malloc(v8);
      *(_QWORD *)(v7 + 56) = v9;
      if ( !v9 )
        return 2147942414LL;
      memset_0(v9, 0, v8);
    }
    v10 = *((_DWORD *)a2 + 3);
    v11 = (NameList::NME **)(*(_QWORD *)(v7 + 56) + 8LL * (v10 & *(_DWORD *)(v7 + 64)));
    v12 = v11;
    while ( 1 )
    {
      v13 = *v12;
      if ( !*v12 )
        break;
      if ( *((_DWORD *)v13 + 8) == v10 )
      {
        if ( (unsigned int)NameList::NME::FEqualRgch(*v12, a2) )
        {
          if ( v12 != v11 )
          {
            *v12 = (NameList::NME *)*((_QWORD *)v13 + 6);
            *((_QWORD *)v13 + 6) = *v11;
            *v11 = v13;
          }
          *(_WORD *)v13 = 0;
          *((_DWORD *)v13 + 6) = 0;
LABEL_15:
          *a3 = v13;
          if ( v4 )
            *v4 = *((_DWORD *)v13 + 14);
          ++*(_DWORD *)(v7 + 8);
          GcContext::RecordVValAlloc(*((GcContext **)this + 9));
          return 0;
        }
        v12 = (NameList::NME **)((char *)v13 + 48);
        v11 = (NameList::NME **)((char *)v13 + 48);
      }
      else
      {
        v12 = (NameList::NME **)((char *)v13 + 48);
      }
    }
    v14 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v14 <= 0 )
      return 2147942414LL;
    v15 = *(_DWORD *)(v7 + 28);
    v16 = *(_DWORD *)(v7 + 24);
    if ( v14 <= v15 - v16 )
      goto LABEL_9;
    v21 = *(_DWORD *)(v7 + 36);
    if ( v14 >= v21 )
    {
      if ( 2 * *((_DWORD *)a2 + 2) + 74 <= 2 * *((_DWORD *)a2 + 2) + 66 )
        return 2147942414LL;
      v17 = malloc(v14 + 8LL);
      if ( !v17 )
        return 2147942414LL;
      v26 = *(_QWORD **)(v7 + 16);
      if ( v16 >= v15 )
      {
        *v17 = v26;
        *(_QWORD *)(v7 + 16) = v17;
      }
      else
      {
        *v17 = *v26;
        *v26 = v17;
      }
      goto LABEL_10;
    }
    v22 = *(_DWORD *)(v7 + 32);
    v23 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v15 > v14 )
      v23 = *(_DWORD *)(v7 + 28);
    v24 = 2 * v23;
    if ( v22 <= v24 )
      v22 = v24;
    if ( v22 <= v21 )
    {
      if ( v14 > v22 )
        return 2147942414LL;
      v21 = v22;
    }
    if ( v21 + 8 > v21 && v21 + 8 >= v14 )
    {
      v25 = malloc(v21 + 8LL);
      if ( v25 )
      {
        v16 = 0;
        *v25 = *(_QWORD *)(v7 + 16);
        *(_QWORD *)(v7 + 16) = v25;
        *(_DWORD *)(v7 + 28) = v21;
LABEL_9:
        *(_DWORD *)(v7 + 24) = v16 + ((v14 + 7) & 0xFFFFFFF8);
        v17 = (_QWORD *)(*(_QWORD *)(v7 + 16) + v16);
LABEL_10:
        v13 = (NameList::NME *)(v17 + 1);
        if ( v17 == (_QWORD *)-8LL )
          return 2147942414LL;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 48LL))(v7, v17 + 1);
        *((_DWORD *)v13 + 14) = v18;
        if ( !v18 )
          return 2147942414LL;
        *(_WORD *)v13 = 0;
        *((_DWORD *)v13 + 6) = 0;
        *((_DWORD *)v13 + 8) = *((_DWORD *)a2 + 3);
        *((_DWORD *)v13 + 9) = 2 * *((_DWORD *)a2 + 2);
        memcpy_0((char *)v13 + 64, *(const void **)a2, 2 * *((_DWORD *)a2 + 2) + 2LL);
        v19 = (_QWORD *)((char *)v13 + 40);
        *((_QWORD *)v13 + 6) = *v11;
        *v11 = v13;
        ++*(_DWORD *)(v7 + 12);
        if ( *(_QWORD *)(v7 + 40) )
          **(_QWORD **)(v7 + 48) = v13;
        else
          *(_QWORD *)(v7 + 40) = v13;
        *(_QWORD *)(v7 + 48) = v19;
        *v19 = 0;
        v4 = a4;
        goto LABEL_15;
      }
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180012bc0  mov     [rsp+arg_0], rbx
0x180012bc5  mov     [rsp+arg_18], r9
0x180012bca  mov     [rsp+arg_10], r8
0x180012bcf  push    rbp
0x180012bd0  push    rsi
0x180012bd1  push    rdi
0x180012bd2  push    r12
0x180012bd4  push    r13
0x180012bd6  push    r14
0x180012bd8  push    r15
0x180012bda  sub     rsp, 20h
0x180012bde  cmp     qword ptr [rcx+10h], 0
0x180012be3  mov     r12, r9
0x180012be6  mov     r13, rdx
0x180012be9  mov     r15, rcx
0x180012bec  jz      loc_180012DC9
0x180012bf2  mov     rbx, [r15+10h]
0x180012bf6  cmp     qword ptr [rbx+38h], 0
0x180012bfb  jnz     loc_180012DB0
0x180012c01  mov     eax, [rbx+40h]
0x180012c04  lea     eax, ds:8[rax*8]
0x180012c0b  movsxd  rdi, eax
0x180012c0e  mov     rcx, rdi; Size
0x180012c11  call    cs:__imp_malloc
0x180012c18  nop     dword ptr [rax+rax+00h]
0x180012c1d  mov     [rbx+38h], rax
0x180012c21  test    rax, rax
0x180012c24  jz      loc_180012DE5
0x180012c2a  mov     r8, rdi; Size
0x180012c2d  xor     edx, edx; Val
0x180012c2f  mov     rcx, rax; void *
0x180012c32  call    memset_0
0x180012c37  mov     ebp, [r13+0Ch]
0x180012c3b  mov     ecx, [rbx+40h]
0x180012c3e  mov     rax, [rbx+38h]
0x180012c42  and     rcx, rbp
0x180012c45  lea     r14, [rax+rcx*8]
0x180012c49  mov     rsi, r14
0x180012c4c  mov     rdi, [rsi]
0x180012c4f  test    rdi, rdi
0x180012c52  jnz     loc_180012DFB
0x180012c58  mov     eax, [r13+8]
0x180012c5c  lea     edi, ds:42h[rax*2]
0x180012c63  test    edi, edi
0x180012c65  jle     loc_180012DE5
0x180012c6b  mov     r12d, [rbx+1Ch]
0x180012c6f  mov     eax, r12d
0x180012c72  mov     ebp, [rbx+18h]
0x180012c75  sub     eax, ebp
0x180012c77  cmp     edi, eax
0x180012c79  jg      loc_180012D50
0x180012c7f  lea     eax, [rdi+7]
0x180012c82  and     eax, 0FFFFFFF8h
0x180012c85  add     eax, ebp
0x180012c87  mov     [rbx+18h], eax
0x180012c8a  movsxd  rax, ebp
0x180012c8d  add     rax, [rbx+10h]
0x180012c91  lea     rdi, [rax+8]
0x180012c95  test    rdi, rdi
0x180012c98  jz      loc_180012DE5
0x180012c9e  mov     rax, [rbx]
0x180012ca1  mov     rdx, rdi
0x180012ca4  mov     rcx, rbx
0x180012ca7  mov     rax, [rax+30h]
0x180012cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb0  mov     [rdi+38h], eax
0x180012cb3  test    eax, eax
0x180012cb5  jz      loc_180012DE5
0x180012cbb  xor     eax, eax
0x180012cbd  lea     rcx, [rdi+40h]; void *
0x180012cc1  mov     [rdi], ax
0x180012cc4  mov     [rdi+18h], eax
0x180012cc7  mov     eax, [r13+0Ch]
0x180012ccb  mov     [rdi+20h], eax
0x180012cce  mov     eax, [r13+8]
0x180012cd2  add     eax, eax
0x180012cd4  mov     [rdi+24h], eax
0x180012cd7  mov     eax, [r13+8]
0x180012cdb  mov     rdx, [r13+0]; Src
0x180012cdf  add     eax, eax
0x180012ce1  movsxd  r8, eax
0x180012ce4  add     r8, 2; Size
0x180012ce8  call    memcpy_0
0x180012ced  mov     rax, [r14]
0x180012cf0  lea     rcx, [rdi+28h]
0x180012cf4  mov     [rdi+30h], rax
0x180012cf8  mov     [r14], rdi
0x180012cfb  inc     dword ptr [rbx+0Ch]
0x180012cfe  cmp     qword ptr [rbx+28h], 0
0x180012d03  jnz     loc_180012DEF
0x180012d09  mov     [rbx+28h], rdi
0x180012d0d  mov     [rbx+30h], rcx
0x180012d11  xor     eax, eax
0x180012d13  mov     [rcx], rax
0x180012d16  mov     r12, [rsp+58h+arg_18]
0x180012d1b  mov     rax, [rsp+58h+arg_10]
0x180012d20  mov     [rax], rdi
0x180012d23  test    r12, r12
0x180012d26  jnz     loc_180012E3B
0x180012d2c  inc     dword ptr [rbx+8]
0x180012d2f  mov     rcx, [r15+48h]; this
0x180012d33  call    ?RecordVValAlloc@GcContext@@QEAAXXZ; GcContext::RecordVValAlloc(void)
0x180012d38  xor     eax, eax
0x180012d3a  mov     rbx, [rsp+58h+arg_0]
0x180012d3f  add     rsp, 20h
0x180012d43  pop     r15
0x180012d45  pop     r14
0x180012d47  pop     r13
0x180012d49  pop     r12
0x180012d4b  pop     rdi
0x180012d4c  pop     rsi
0x180012d4d  pop     rbp
0x180012d4e  retn
0x180012d50  mov     esi, [rbx+24h]
0x180012d53  cmp     edi, esi
0x180012d55  jge     loc_180012E47
0x180012d5b  mov     ecx, [rbx+20h]
0x180012d5e  cmp     r12d, edi
0x180012d61  mov     eax, edi
0x180012d63  cmovg   eax, r12d
0x180012d67  add     eax, eax
0x180012d69  cmp     ecx, eax
0x180012d6b  cmovle  ecx, eax
0x180012d6e  cmp     ecx, esi
0x180012d70  jg      short loc_180012D78
0x180012d72  cmp     edi, ecx
0x180012d74  jg      short loc_180012DE5
0x180012d76  mov     esi, ecx
0x180012d78  lea     eax, [rsi+8]
0x180012d7b  cmp     eax, esi
0x180012d7d  jl      short loc_180012DE5
0x180012d7f  cmp     eax, edi
0x180012d81  jl      short loc_180012DE5
0x180012d83  movsxd  rcx, esi
0x180012d86  add     rcx, 8; Size
0x180012d8a  call    cs:__imp_malloc
0x180012d91  nop     dword ptr [rax+rax+00h]
0x180012d96  test    rax, rax
0x180012d99  jz      short loc_180012DE5
0x180012d9b  mov     rcx, [rbx+10h]
0x180012d9f  xor     ebp, ebp
0x180012da1  mov     [rax], rcx
0x180012da4  mov     [rbx+10h], rax
0x180012da8  mov     [rbx+1Ch], esi
0x180012dab  jmp     loc_180012C7F
0x180012db0  mov     eax, [rbx+44h]
0x180012db3  cmp     [rbx+0Ch], eax
0x180012db6  jl      loc_180012C37
0x180012dbc  mov     rcx, rbx; this
0x180012dbf  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x180012dc4  jmp     loc_180012C37
0x180012dc9  mov     rax, [rcx]
0x180012dcc  mov     rax, [rax+1A0h]
0x180012dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dd8  test    eax, eax
0x180012dda  jns     loc_180012BF2
0x180012de0  jmp     loc_180012D3A
0x180012de5  mov     eax, 8007000Eh
0x180012dea  jmp     loc_180012D3A
0x180012def  mov     rax, [rbx+30h]
0x180012df3  mov     [rax], rdi
0x180012df6  jmp     loc_180012D0D
0x180012dfb  cmp     [rdi+20h], ebp
0x180012dfe  jz      short loc_180012E09
0x180012e00  lea     rsi, [rdi+30h]
0x180012e04  jmp     loc_180012C4C
0x180012e09  mov     rdx, r13; struct SYM *
0x180012e0c  mov     rcx, rdi; this
0x180012e0f  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x180012e14  test    eax, eax
0x180012e16  jz      short loc_180012E8D
0x180012e18  cmp     rsi, r14
0x180012e1b  jz      short loc_180012E2E
0x180012e1d  mov     rax, [rdi+30h]
0x180012e21  mov     [rsi], rax
0x180012e24  mov     rax, [r14]
0x180012e27  mov     [rdi+30h], rax
0x180012e2b  mov     [r14], rdi
0x180012e2e  xor     eax, eax
0x180012e30  mov     [rdi], ax
0x180012e33  mov     [rdi+18h], eax
0x180012e36  jmp     loc_180012D1B
0x180012e3b  mov     eax, [rdi+38h]
0x180012e3e  mov     [r12], eax
0x180012e42  jmp     loc_180012D2C
0x180012e47  lea     eax, [rdi+8]
0x180012e4a  cmp     eax, edi
0x180012e4c  jl      short loc_180012DE5
0x180012e4e  movsxd  rcx, edi
0x180012e51  add     rcx, 8; Size
0x180012e55  call    cs:__imp_malloc
0x180012e5c  nop     dword ptr [rax+rax+00h]
0x180012e61  test    rax, rax
0x180012e64  jz      loc_180012DE5
0x180012e6a  mov     rdx, [rbx+10h]
0x180012e6e  cmp     ebp, r12d
0x180012e71  jge     short loc_180012E81
0x180012e73  mov     rcx, [rdx]
0x180012e76  mov     [rax], rcx
0x180012e79  mov     [rdx], rax
0x180012e7c  jmp     loc_180012C91
0x180012e81  mov     [rax], rdx
0x180012e84  mov     [rbx+10h], rax
0x180012e88  jmp     loc_180012C91
0x180012e8d  lea     rsi, [rdi+30h]
0x180012e91  mov     r14, rsi
0x180012e94  jmp     loc_180012C4C
```
