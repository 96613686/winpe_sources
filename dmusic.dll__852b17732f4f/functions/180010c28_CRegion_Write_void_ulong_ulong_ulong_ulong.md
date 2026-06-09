# CRegion::Write(void *,ulong *,ulong *,ulong *,ulong)

- ea: `0x180010c28`
- end: `0x180010e94`
- name: `?Write@CRegion@@QEAAJPEAXPEAK11K@Z`
- size: `620`
- prototype: `__int64 __fastcall(CRegion *this, char *, unsigned int *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7e0`

## callees

- `0x180009e94`
- `0x180010c28`
- `0x1800217bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegion::Write(
        CRegion *this,
        char *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int *v6; // r11
  CRegion *v9; // rbp
  unsigned int v11; // r10d
  __int64 *v12; // r13
  unsigned int v13; // eax
  unsigned int v14; // ecx
  int v15; // r15d
  unsigned int v16; // edi
  unsigned int v17; // ebp
  unsigned int v18; // eax
  __int64 v19; // rax
  char *v20; // rbx
  unsigned int v21; // ecx
  unsigned int v22; // edx
  __int64 *v23; // rcx
  int v24; // r9d
  _QWORD *v25; // rax
  int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  __int64 *v29; // rdi
  int v30; // eax
  int v31; // eax
  int v32; // edx
  __int64 v33; // rax
  unsigned int v34; // ebx
  int v35; // [rsp+30h] [rbp-48h]
  unsigned int v36; // [rsp+38h] [rbp-40h]

  v6 = a4;
  v9 = this;
  if ( !*((_DWORD *)this + 18) )
    return 0;
  v11 = 72;
  *(_QWORD *)a2 = *(_QWORD *)((char *)this + 12);
  *((_DWORD *)a2 + 2) = *((_DWORD *)this + 5);
  *((_QWORD *)a2 + 3) = *((_QWORD *)this + 3);
  *((_DWORD *)a2 + 8) = *((_DWORD *)this + 8);
  v35 = 72;
  *(_OWORD *)(a2 + 36) = *(_OWORD *)((char *)this + 36);
  *((_DWORD *)a2 + 13) = *((_DWORD *)this + 13);
  *(_OWORD *)(a2 + 56) = *(_OWORD *)((char *)this + 56);
  *((_DWORD *)a2 + 4) = a6;
  v12 = (__int64 *)*((_QWORD *)this + 13);
  v13 = *a3 + 72;
  *a3 = v13;
  v14 = v13;
  v36 = v13;
  if ( v12 )
  {
    v15 = *((_DWORD *)v9 + 28);
    v16 = *a5;
    v17 = *a5;
    *((_DWORD *)a2 + 5) = *a5;
    do
    {
      if ( !v15 )
        break;
      v18 = v16 + 1;
      v16 = 0;
      if ( v15 != 1 )
        v16 = v18;
      v19 = v17;
      v20 = &a2[v11];
      *a5 = ++v17;
      v6[v19] = v14;
      memcpy_0(v20, (const void *)v12[1], (*((_DWORD *)v12 + 4) + 23) & 0xFFFFFFF8);
      v21 = (*((_DWORD *)v12 + 4) + 23) & 0xFFFFFFF8;
      v6 = a4;
      v11 = v21 + v35;
      *((_DWORD *)v20 + 1) = v16;
      v12 = (__int64 *)*v12;
      --v15;
      *a3 = v21 + v36;
      v35 += v21;
      v14 = v21 + v36;
      v36 = v14;
    }
    while ( v12 );
    v9 = this;
  }
  else
  {
    *((_DWORD *)a2 + 5) = 0;
  }
  *((_DWORD *)a2 + 3) = 0;
  v22 = 0;
  v23 = (__int64 *)*((_QWORD *)v9 + 12);
  v24 = 0;
  v25 = v23;
  if ( v23 )
  {
    do
    {
      v25 = (_QWORD *)*v25;
      ++v24;
    }
    while ( v25 );
    v26 = 0;
    do
    {
      if ( *((_DWORD *)v23 + 12) )
      {
        v27 = *((_DWORD *)v23 + 10);
        if ( v23[3] )
          ++v27;
        if ( v27 != -1 )
          break;
      }
      v23 = (__int64 *)*v23;
      ++v26;
    }
    while ( v23 );
    if ( v23 && v26 < v24 )
    {
      do
      {
        v28 = 0;
        if ( *((_DWORD *)v9 + 29) )
        {
          v29 = (__int64 *)*v23;
          if ( *v23 )
          {
            do
            {
              if ( *((_DWORD *)v29 + 12) )
              {
                v30 = *((_DWORD *)v29 + 10);
                if ( v29[3] )
                  ++v30;
                if ( v30 != -1 )
                  break;
              }
              v29 = (__int64 *)*v29;
            }
            while ( v29 );
            if ( v29 )
            {
              if ( *((_DWORD *)v23 + 12) )
              {
                v31 = *((_DWORD *)v23 + 10);
                if ( v23[3] )
                  ++v31;
                v32 = v31 + 1;
              }
              else
              {
                v32 = 0;
              }
              v28 = v32 + *a5;
            }
          }
        }
        else
        {
          v29 = 0;
        }
        if ( !*((_DWORD *)a2 + 3) )
          *((_DWORD *)a2 + 3) = *a5;
        v33 = *a5;
        v34 = *a3;
        v6[v33] = *a3;
        *a5 = v33 + 1;
        v22 = CArticulation::Write((CArticulation *)v23, &a2[v11], a3, v6, a5, v28);
        v6 = a4;
        v11 = *a3 - v34 + v35;
        v35 = v11;
        v23 = v29;
      }
      while ( v29 );
    }
  }
  return v22;
}

```

## disassembly

```asm
0x180010c28  mov     [rsp+arg_8], rbx
0x180010c2d  mov     [rsp+arg_18], r9
0x180010c32  mov     [rsp+arg_0], rcx
0x180010c37  push    rbp
0x180010c38  push    rsi
0x180010c39  push    rdi
0x180010c3a  push    r12
0x180010c3c  push    r13
0x180010c3e  push    r14
0x180010c40  push    r15
0x180010c42  sub     rsp, 40h
0x180010c46  xor     ebx, ebx
0x180010c48  mov     r11, r9
0x180010c4b  mov     r12, r8
0x180010c4e  mov     rsi, rdx
0x180010c51  mov     rbp, rcx
0x180010c54  cmp     [rcx+48h], ebx
0x180010c57  jnz     short loc_180010C60
0x180010c59  xor     eax, eax
0x180010c5b  jmp     loc_180010E7C
0x180010c60  movsd   xmm0, qword ptr [rcx+0Ch]
0x180010c65  mov     r10d, 48h ; 'H'
0x180010c6b  mov     r14, [rsp+78h+arg_20]
0x180010c73  movsd   qword ptr [rdx], xmm0
0x180010c77  mov     eax, [rcx+14h]
0x180010c7a  mov     [rdx+8], eax
0x180010c7d  movsd   xmm0, qword ptr [rcx+18h]
0x180010c82  movsd   qword ptr [rdx+18h], xmm0
0x180010c87  mov     eax, [rcx+20h]
0x180010c8a  mov     [rdx+20h], eax
0x180010c8d  movups  xmm0, xmmword ptr [rcx+24h]
0x180010c91  mov     [rsp+78h+var_48], r10d
0x180010c96  movups  xmmword ptr [rdx+24h], xmm0
0x180010c9a  mov     eax, [rcx+34h]
0x180010c9d  mov     [rdx+34h], eax
0x180010ca0  movups  xmm0, xmmword ptr [rcx+38h]
0x180010ca4  mov     eax, [rsp+78h+arg_28]
0x180010cab  movdqu  xmmword ptr [rdx+38h], xmm0
0x180010cb0  mov     [rdx+10h], eax
0x180010cb3  mov     eax, [r8]
0x180010cb6  mov     r13, [rbp+68h]
0x180010cba  add     eax, 48h ; 'H'
0x180010cbd  mov     [r8], eax
0x180010cc0  mov     ecx, eax
0x180010cc2  mov     qword ptr [rsp+78h+var_40], rcx
0x180010cc7  test    r13, r13
0x180010cca  jz      loc_180010D6A
0x180010cd0  mov     r15d, [rbp+70h]
0x180010cd4  mov     edi, [r14]
0x180010cd7  mov     ebp, edi
0x180010cd9  mov     [rdx+14h], edi
0x180010cdc  mov     edx, 0FFFFFFF8h
0x180010ce1  test    r15d, r15d
0x180010ce4  jz      short loc_180010D60
0x180010ce6  lea     eax, [rdi+1]
0x180010ce9  cmp     r15d, 1
0x180010ced  mov     edi, ebx
0x180010cef  mov     ebx, r10d
0x180010cf2  cmovnz  edi, eax
0x180010cf5  mov     eax, ebp
0x180010cf7  add     rbx, rsi
0x180010cfa  inc     ebp
0x180010cfc  mov     [r14], ebp
0x180010cff  mov     [r11+rax*4], ecx
0x180010d03  mov     rcx, rbx; void *
0x180010d06  mov     r8d, [r13+10h]
0x180010d0a  add     r8d, 17h
0x180010d0e  and     r8, rdx; Size
0x180010d11  mov     rdx, [r13+8]; Src
0x180010d15  call    memcpy_0
0x180010d1a  mov     ecx, [r13+10h]
0x180010d1e  mov     edx, 0FFFFFFF8h
0x180010d23  mov     rax, qword ptr [rsp+78h+var_40]
0x180010d28  add     ecx, 17h
0x180010d2b  mov     r10d, [rsp+78h+var_48]
0x180010d30  and     ecx, edx
0x180010d32  mov     r11, [rsp+78h+arg_18]
0x180010d3a  add     eax, ecx
0x180010d3c  add     r10d, ecx
0x180010d3f  mov     [rbx+4], edi
0x180010d42  mov     r13, [r13+0]
0x180010d46  dec     r15d
0x180010d49  xor     ebx, ebx
0x180010d4b  mov     [r12], eax
0x180010d4f  mov     [rsp+78h+var_48], r10d
0x180010d54  mov     ecx, eax
0x180010d56  mov     qword ptr [rsp+78h+var_40], rcx
0x180010d5b  test    r13, r13
0x180010d5e  jnz     short loc_180010CE1
0x180010d60  mov     rbp, [rsp+78h+arg_0]
0x180010d68  jmp     short loc_180010D6D
0x180010d6a  mov     [rsi+14h], ebx
0x180010d6d  mov     [rsi+0Ch], ebx
0x180010d70  mov     edx, ebx
0x180010d72  mov     rcx, [rbp+60h]
0x180010d76  mov     r9d, ebx
0x180010d79  mov     rax, rcx
0x180010d7c  test    rcx, rcx
0x180010d7f  jz      loc_180010E7A
0x180010d85  mov     rax, [rax]
0x180010d88  inc     r9d
0x180010d8b  test    rax, rax
0x180010d8e  jnz     short loc_180010D85
0x180010d90  mov     r8d, ebx
0x180010d93  cmp     [rcx+30h], ebx
0x180010d96  jz      short loc_180010DA8
0x180010d98  mov     eax, [rcx+28h]
0x180010d9b  cmp     [rcx+18h], rbx
0x180010d9f  jz      short loc_180010DA3
0x180010da1  inc     eax
0x180010da3  add     eax, 1
0x180010da6  jnz     short loc_180010DB3
0x180010da8  mov     rcx, [rcx]; this
0x180010dab  inc     r8d
0x180010dae  test    rcx, rcx
0x180010db1  jnz     short loc_180010D93
0x180010db3  test    rcx, rcx
0x180010db6  jz      loc_180010E7A
0x180010dbc  cmp     r8d, r9d
0x180010dbf  jge     loc_180010E7A
0x180010dc5  mov     r8d, ebx
0x180010dc8  cmp     [rbp+74h], ebx
0x180010dcb  jz      short loc_180010E16
0x180010dcd  mov     rdi, [rcx]
0x180010dd0  test    rdi, rdi
0x180010dd3  jz      short loc_180010E19
0x180010dd5  cmp     [rdi+30h], ebx
0x180010dd8  jz      short loc_180010DEA
0x180010dda  mov     eax, [rdi+28h]
0x180010ddd  cmp     [rdi+18h], rbx
0x180010de1  jz      short loc_180010DE5
0x180010de3  inc     eax
0x180010de5  add     eax, 1
0x180010de8  jnz     short loc_180010DF2
0x180010dea  mov     rdi, [rdi]
0x180010ded  test    rdi, rdi
0x180010df0  jnz     short loc_180010DD5
0x180010df2  test    rdi, rdi
0x180010df5  jz      short loc_180010E19
0x180010df7  cmp     [rcx+30h], ebx
0x180010dfa  jz      short loc_180010E0C
0x180010dfc  mov     eax, [rcx+28h]
0x180010dff  cmp     [rcx+18h], rbx
0x180010e03  jz      short loc_180010E07
0x180010e05  inc     eax
0x180010e07  lea     edx, [rax+1]
0x180010e0a  jmp     short loc_180010E0E
0x180010e0c  mov     edx, ebx
0x180010e0e  mov     r8d, [r14]
0x180010e11  add     r8d, edx
0x180010e14  jmp     short loc_180010E19
0x180010e16  mov     rdi, rbx
0x180010e19  cmp     [rsi+0Ch], ebx
0x180010e1c  jnz     short loc_180010E24
0x180010e1e  mov     eax, [r14]
0x180010e21  mov     [rsi+0Ch], eax
0x180010e24  mov     eax, [r14]
0x180010e27  mov     r9, r11; unsigned int *
0x180010e2a  mov     ebx, [r12]
0x180010e2e  mov     [rsp+78h+var_50], r8d; unsigned int
0x180010e33  mov     r8, r12; unsigned int *
0x180010e36  mov     edx, r10d
0x180010e39  mov     [r11+rax*4], ebx
0x180010e3d  add     rdx, rsi; void *
0x180010e40  inc     eax
0x180010e42  mov     [rsp+78h+var_58], r14; unsigned int *
0x180010e47  mov     [r14], eax
0x180010e4a  call    ?Write@CArticulation@@QEAAJPEAXPEAK11K@Z; CArticulation::Write(void *,ulong *,ulong *,ulong *,ulong)
0x180010e4f  mov     ecx, [r12]
0x180010e53  mov     edx, eax
0x180010e55  mov     r10d, [rsp+78h+var_48]
0x180010e5a  sub     ecx, ebx
0x180010e5c  mov     r11, [rsp+78h+arg_18]
0x180010e64  add     r10d, ecx
0x180010e67  xor     ebx, ebx
0x180010e69  mov     [rsp+78h+var_48], r10d
0x180010e6e  mov     rcx, rdi
0x180010e71  test    rdi, rdi
0x180010e74  jnz     loc_180010DC5
0x180010e7a  mov     eax, edx
0x180010e7c  mov     rbx, [rsp+78h+arg_8]
0x180010e84  add     rsp, 40h
0x180010e88  pop     r15
0x180010e8a  pop     r14
0x180010e8c  pop     r13
0x180010e8e  pop     r12
0x180010e90  pop     rdi
0x180010e91  pop     rsi
0x180010e92  pop     rbp
0x180010e93  retn
```
