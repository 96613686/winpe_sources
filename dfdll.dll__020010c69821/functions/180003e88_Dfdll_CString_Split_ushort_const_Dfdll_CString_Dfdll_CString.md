# Dfdll::CString::Split(ushort const *,Dfdll::CString &,Dfdll::CString &)

- ea: `0x180003e88`
- end: `0x1800043d8`
- name: `?Split@CString@Dfdll@@QEAAJPEBGAEAV12@1@Z`
- size: `1360`
- prototype: `int(Dfdll::CString *__hidden this, const unsigned __int16 *, struct Dfdll::CString *, struct Dfdll::CString *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180004580`
- `0x180005400`
- `0x18000c954`

## callees

- `0x180001fc8`
- `0x180002238`
- `0x180002604`
- `0x180002ce0`
- `0x180003a90`
- `0x180003e88`
- `0x180012b30`
- `0x1800140a0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CString::Split(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        struct Dfdll::CString *a3,
        struct Dfdll::CString *a4)
{
  unsigned int v7; // r14d
  signed int v8; // ebx
  __int64 v9; // rdx
  char *v10; // r14
  struct std::nothrow_t *v11; // r12
  int v12; // eax
  char *v13; // rcx
  _DWORD *v14; // rdi
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // r15
  unsigned int v19; // edi
  char *v20; // rax
  char *v21; // r15
  unsigned int v22; // r8d
  unsigned int v23; // ecx
  int v24; // ecx
  char v25; // al
  struct std::nothrow_t *v26; // rdx
  struct std::nothrow_t *v27; // rcx
  struct std::nothrow_t *v28; // r8
  const struct std::nothrow_t *v29; // rdx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // r9d
  unsigned int v33; // r13d
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  void *v38; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h] BYREF
  void **v40; // [rsp+40h] [rbp-20h] BYREF
  struct std::nothrow_t *v41; // [rsp+48h] [rbp-18h]
  unsigned int v42; // [rsp+50h] [rbp-10h]

  LODWORD(v38) = 0;
  if ( (int)Dfdll::CString::Find((Dfdll::CString *)this, 0, a2, (unsigned int *)&v38) < 0 )
  {
    v8 = Dfdll::CString::Assign(a3, this[2]);
    if ( v8 < 0 )
      return (unsigned int)v8;
    goto LABEL_86;
  }
  v7 = (unsigned int)v38;
  if ( !(_DWORD)v38 )
  {
    if ( *((_DWORD *)a3 + 8) )
    {
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a3 + 1) + 40LL))((char *)a3 + 8, 0);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
    *((_DWORD *)a3 + 8) = 0;
    goto LABEL_6;
  }
  v11 = (struct std::nothrow_t *)this[2];
  v12 = *((_DWORD *)a3 + 8);
  if ( !v11 )
  {
    if ( !v12
      || (v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a3 + 1) + 40LL))((char *)a3 + 8, 0), v8 >= 0) )
    {
      *((_DWORD *)a3 + 8) = 0;
      v13 = (char *)a3 + 8;
      v14 = (_DWORD *)((char *)a3 + 24);
      v15 = v13 + 8;
      (*(void (__fastcall **)(char *, char *, _DWORD *))(*(_QWORD *)v13 + 88LL))(v13, v13 + 8, v14);
      *v15 = 0;
      *v14 = 0;
      v8 = 0;
    }
LABEL_19:
    if ( v8 < 0 )
      return (unsigned int)v8;
    goto LABEL_20;
  }
  if ( v12 )
  {
    v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a3 + 1) + 40LL))((char *)a3 + 8, 0);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  *((_DWORD *)a3 + 8) = 0;
  v8 = Dfdll::CString::Append(a3, v11, v7);
  if ( v8 < 0 )
    goto LABEL_19;
LABEL_20:
  if ( v7 == -1 )
    return (unsigned int)-2147024362;
LABEL_6:
  v9 = v7 + 1;
  if ( (unsigned int)v9 < *((_DWORD *)this + 8) )
  {
    Src = 0;
    v8 = (*((__int64 (__fastcall **)(char *, __int64, void **))this[1] + 8))((char *)this + 8, v9, &Src);
    if ( v8 < 0 )
      return (unsigned int)v8;
    v10 = (char *)Src;
    if ( !Src )
    {
      if ( !*((_DWORD *)a4 + 8)
        || (v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a4 + 1) + 40LL))((char *)a4 + 8, 0), v8 >= 0) )
      {
        *((_DWORD *)a4 + 8) = 0;
        (*(void (__fastcall **)(char *, char *, char *))(*((_QWORD *)a4 + 1) + 88LL))(
          (char *)a4 + 8,
          (char *)a4 + 16,
          (char *)a4 + 24);
        *((_QWORD *)a4 + 2) = 0;
        *((_DWORD *)a4 + 6) = 0;
        v8 = 0;
      }
      goto LABEL_67;
    }
    v16 = 0x7FFFFFFF;
    v17 = Src;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    v8 = v16 == 0 ? 0x80070057 : 0;
    v18 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
    if ( !v16 )
      return (unsigned int)v8;
    if ( *((_DWORD *)a4 + 8) )
    {
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a4 + 1) + 40LL))((char *)a4 + 8, 0);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
    *((_DWORD *)a4 + 8) = 0;
    v19 = 0;
    if ( !(_DWORD)v18 )
      goto LABEL_33;
    v20 = v10;
    do
    {
      if ( !*(_WORD *)v20 )
        break;
      ++v19;
      v20 += 2;
    }
    while ( v19 < (unsigned int)v18 );
    if ( v19 <= 0x7FFFFFFF )
    {
LABEL_33:
      v21 = (char *)a4 + 8;
      if ( !(2 * v19) || !*((_DWORD *)a4 + 6) )
        goto LABEL_41;
      v38 = 0;
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD, void **))(*(_QWORD *)v21 + 64LL))((char *)a4 + 8, 0, &v38);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v21 + 72LL))((char *)a4 + 8);
      v23 = *((_DWORD *)a4 + 6);
      if ( v22 )
      {
        if ( v23 <= 0xFFFFFFFF / v22 )
        {
          v24 = v22 * v23;
          if ( v24 )
          {
            if ( &v10[2 * v19 - 1] >= v38 )
            {
              v25 = 1;
              if ( v10 <= (char *)v38 + (unsigned int)(v24 - 1) )
              {
LABEL_42:
                v26 = 0;
                v41 = 0;
                v42 = 0;
                v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                v27 = 0;
                v28 = 0;
                if ( !v25 )
                {
LABEL_62:
                  v32 = *((_DWORD *)a4 + 8);
                  if ( v32 <= ~v19 )
                  {
                    v33 = v32 + v19;
                    if ( v32 + v19 != -1 )
                    {
                      if ( v33 + 1 <= *((_DWORD *)a4 + 6)
                        || (v8 = Dfdll::CBufferBase::Reallocate((struct Dfdll::CString *)((char *)a4 + 8), v33 + 1),
                            v8 >= 0) )
                      {
                        v8 = (*(__int64 (__fastcall **)(char *, char *, _QWORD, _QWORD))(*(_QWORD *)v21 + 104LL))(
                               (char *)a4 + 8,
                               v10,
                               *((unsigned int *)a4 + 8),
                               v19);
                        if ( v8 >= 0 )
                        {
                          v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v21 + 40LL))((char *)a4 + 8, v33);
                          if ( v8 >= 0 )
                          {
                            *((_DWORD *)a4 + 8) = v33;
                            v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                            if ( v41 )
                              operator delete(v41, v36);
                            return 0;
                          }
                          v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                          if ( v41 )
                            operator delete(v41, v36);
                        }
                        else
                        {
                          v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                          if ( v41 )
                            operator delete(v41, v35);
                        }
                      }
                      else
                      {
                        v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                        if ( v41 )
                          operator delete(v41, v34);
                      }
                      return (unsigned int)v8;
                    }
                    v27 = v28;
                  }
                  v8 = -2147024362;
                  v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                  if ( v27 )
                    operator delete(v26, v26);
                  goto LABEL_67;
                }
                v8 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v40, v19);
                if ( v8 < 0 )
                {
                  v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                  if ( v41 )
                    operator delete(v41, v29);
                  return (unsigned int)v8;
                }
                if ( !v19 )
                {
LABEL_61:
                  v26 = v41;
                  v10 = (char *)v41;
                  v27 = v41;
                  v28 = v41;
                  goto LABEL_62;
                }
                if ( v42 && v42 >= v19 )
                {
                  v38 = 0;
                  v8 = ((__int64 (__fastcall *)(void ***, _QWORD, void **))v40[8])(&v40, 0, &v38);
                  if ( v8 >= 0 )
                  {
                    v30 = ((__int64 (__fastcall *)(void ***))v40[9])(&v40);
                    if ( !v30 )
                    {
                      v31 = 0;
LABEL_60:
                      memmove(v38, v10, v31);
                      goto LABEL_61;
                    }
                    v29 = (const struct std::nothrow_t *)(0xFFFFFFFF % v30);
                    if ( v19 <= 0xFFFFFFFF / v30 )
                    {
                      v31 = v19 * v30;
                      goto LABEL_60;
                    }
                    v8 = -2147024362;
                  }
                }
                else
                {
                  v8 = -2147024809;
                }
                v40 = &Dfdll::CBuffer<unsigned short>::`vftable';
                if ( v41 )
                  operator delete(v41, v29);
LABEL_67:
                if ( v8 >= 0 )
                  return 0;
                return (unsigned int)v8;
              }
            }
LABEL_41:
            v25 = 0;
            goto LABEL_42;
          }
        }
      }
    }
    return (unsigned int)-2147024362;
  }
LABEL_86:
  if ( !*((_DWORD *)a4 + 8)
    || (v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a4 + 1) + 40LL))((char *)a4 + 8, 0), v8 >= 0) )
  {
    *((_DWORD *)a4 + 8) = 0;
    return 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003e88  mov     [rsp-28h+arg_0], rbx
0x180003e8d  mov     [rsp-28h+arg_8], rsi
0x180003e92  mov     [rsp-28h+arg_10], rdi
0x180003e97  push    rbp
0x180003e98  push    r12
0x180003e9a  push    r13
0x180003e9c  push    r14
0x180003e9e  push    r15
0x180003ea0  mov     rbp, rsp
0x180003ea3  sub     rsp, 60h
0x180003ea7  mov     rsi, r9
0x180003eaa  mov     rdi, r8
0x180003ead  mov     r15, rcx
0x180003eb0  xor     r12d, r12d
0x180003eb3  mov     dword ptr [rbp+var_30], r12d
0x180003eb7  lea     r9, [rbp+var_30]; unsigned int *
0x180003ebb  mov     r8, rdx; unsigned __int16 *
0x180003ebe  xor     edx, edx; unsigned int
0x180003ec0  call    ?Find@CString@Dfdll@@QEAAJIPEBGAEAI@Z; Dfdll::CString::Find(uint,ushort const *,uint &)
0x180003ec5  test    eax, eax
0x180003ec7  js      loc_180004380
0x180003ecd  mov     r14d, dword ptr [rbp+var_30]
0x180003ed1  test    r14d, r14d
0x180003ed4  jnz     loc_180003F93
0x180003eda  cmp     [rdi+20h], r12d
0x180003ede  jbe     short loc_180003EFD
0x180003ee0  lea     rcx, [rdi+8]
0x180003ee4  mov     rax, [rcx]
0x180003ee7  xor     edx, edx
0x180003ee9  mov     rax, [rax+28h]
0x180003eed  call    cs:__guard_dispatch_icall_fptr
0x180003ef3  mov     ebx, eax
0x180003ef5  test    eax, eax
0x180003ef7  js      loc_1800043B8
0x180003efd  mov     [rdi+20h], r12d
0x180003f01  lea     edx, [r14+1]
0x180003f05  cmp     edx, [r15+20h]
0x180003f09  jnb     loc_180004392
0x180003f0f  mov     [rbp+Src], r12
0x180003f13  lea     rcx, [r15+8]
0x180003f17  mov     rax, [rcx]
0x180003f1a  lea     r8, [rbp+Src]
0x180003f1e  mov     rax, [rax+40h]
0x180003f22  call    cs:__guard_dispatch_icall_fptr
0x180003f28  mov     ebx, eax
0x180003f2a  test    eax, eax
0x180003f2c  js      loc_1800043B8
0x180003f32  mov     r14, [rbp+Src]
0x180003f36  test    r14, r14
0x180003f39  jnz     loc_180004042
0x180003f3f  cmp     [rsi+20h], r12d
0x180003f43  jbe     short loc_180003F62
0x180003f45  lea     rcx, [rsi+8]
0x180003f49  mov     rax, [rcx]
0x180003f4c  xor     edx, edx
0x180003f4e  mov     rax, [rax+28h]
0x180003f52  call    cs:__guard_dispatch_icall_fptr
0x180003f58  mov     ebx, eax
0x180003f5a  test    eax, eax
0x180003f5c  js      loc_1800042A9
0x180003f62  mov     [rsi+20h], r12d
0x180003f66  lea     rcx, [rsi+8]
0x180003f6a  lea     rdi, [rcx+10h]
0x180003f6e  lea     rbx, [rcx+8]
0x180003f72  mov     rax, [rcx]
0x180003f75  mov     r8, rdi
0x180003f78  mov     rdx, rbx
0x180003f7b  mov     rax, [rax+58h]
0x180003f7f  call    cs:__guard_dispatch_icall_fptr
0x180003f85  mov     [rbx], r12
0x180003f88  mov     [rdi], r12d
0x180003f8b  mov     ebx, r12d
0x180003f8e  jmp     loc_1800042A9
0x180003f93  mov     r12, [r15+10h]
0x180003f97  mov     eax, [rdi+20h]
0x180003f9a  test    r12, r12
0x180003f9d  jnz     short loc_180003FEA
0x180003f9f  test    eax, eax
0x180003fa1  jz      short loc_180003FBC
0x180003fa3  lea     rcx, [rdi+8]
0x180003fa7  mov     rax, [rcx]
0x180003faa  xor     edx, edx
0x180003fac  mov     rax, [rax+28h]
0x180003fb0  call    cs:__guard_dispatch_icall_fptr
0x180003fb6  mov     ebx, eax
0x180003fb8  test    eax, eax
0x180003fba  js      short loc_180004026
0x180003fbc  mov     [rdi+20h], r12d
0x180003fc0  lea     rcx, [rdi+8]
0x180003fc4  lea     rdi, [rcx+10h]
0x180003fc8  lea     rbx, [rcx+8]
0x180003fcc  mov     rax, [rcx]
0x180003fcf  mov     r8, rdi
0x180003fd2  mov     rdx, rbx
0x180003fd5  mov     rax, [rax+58h]
0x180003fd9  call    cs:__guard_dispatch_icall_fptr
0x180003fdf  mov     [rbx], r12
0x180003fe2  mov     [rdi], r12d
0x180003fe5  mov     ebx, r12d
0x180003fe8  jmp     short loc_180004026
0x180003fea  test    eax, eax
0x180003fec  jz      short loc_18000400B
0x180003fee  lea     rcx, [rdi+8]
0x180003ff2  mov     rax, [rcx]
0x180003ff5  xor     edx, edx
0x180003ff7  mov     rax, [rax+28h]
0x180003ffb  call    cs:__guard_dispatch_icall_fptr
0x180004001  mov     ebx, eax
0x180004003  test    eax, eax
0x180004005  js      loc_1800043B8
0x18000400b  and     dword ptr [rdi+20h], 0
0x18000400f  mov     r8d, r14d; unsigned int
0x180004012  mov     rdx, r12; unsigned __int16 *
0x180004015  mov     rcx, rdi; this
0x180004018  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18000401d  mov     ebx, eax
0x18000401f  xor     r12d, r12d
0x180004022  test    eax, eax
0x180004024  jns     short loc_18000402E
0x180004026  test    ebx, ebx
0x180004028  js      loc_1800043B8
0x18000402e  cmp     r14d, 0FFFFFFFEh
0x180004032  jbe     loc_180003F01
0x180004038  mov     ebx, 80070216h
0x18000403d  jmp     loc_1800043B8
0x180004042  mov     r13d, 7FFFFFFFh
0x180004048  mov     edx, r13d
0x18000404b  mov     rax, r14
0x18000404e  cmp     [rax], r12w
0x180004052  jz      short loc_18000405E
0x180004054  add     rax, 2
0x180004058  sub     rdx, 1
0x18000405c  jnz     short loc_18000404E
0x18000405e  mov     rax, rdx
0x180004061  neg     rax
0x180004064  sbb     ebx, ebx
0x180004066  not     ebx
0x180004068  and     ebx, 80070057h
0x18000406e  mov     rax, rdx
0x180004071  mov     rcx, r13
0x180004074  sub     rcx, rdx
0x180004077  neg     rax
0x18000407a  sbb     r15, r15
0x18000407d  and     r15, rcx
0x180004080  test    rdx, rdx
0x180004083  jz      loc_1800043B8
0x180004089  cmp     [rsi+20h], r12d
0x18000408d  jbe     short loc_1800040AC
0x18000408f  lea     rcx, [rsi+8]
0x180004093  mov     rax, [rcx]
0x180004096  xor     edx, edx
0x180004098  mov     rax, [rax+28h]
0x18000409c  call    cs:__guard_dispatch_icall_fptr
0x1800040a2  mov     ebx, eax
0x1800040a4  test    eax, eax
0x1800040a6  js      loc_1800043B8
0x1800040ac  mov     [rsi+20h], r12d
0x1800040b0  mov     edi, r12d
0x1800040b3  test    r15d, r15d
0x1800040b6  jz      short loc_1800040D5
0x1800040b8  mov     rax, r14
0x1800040bb  cmp     [rax], r12w
0x1800040bf  jz      short loc_1800040CC
0x1800040c1  inc     edi
0x1800040c3  add     rax, 2
0x1800040c7  cmp     edi, r15d
0x1800040ca  jb      short loc_1800040BB
0x1800040cc  cmp     edi, r13d
0x1800040cf  ja      loc_180004038
0x1800040d5  lea     r13d, [rdi+rdi]
0x1800040d9  lea     r15, [rsi+8]
0x1800040dd  test    r13d, r13d
0x1800040e0  jz      loc_180004175
0x1800040e6  cmp     [r15+10h], r12d
0x1800040ea  jz      loc_180004175
0x1800040f0  mov     [rbp+var_30], r12
0x1800040f4  mov     rax, [r15]
0x1800040f7  lea     r8, [rbp+var_30]
0x1800040fb  xor     edx, edx
0x1800040fd  mov     rcx, r15
0x180004100  mov     rax, [rax+40h]
0x180004104  call    cs:__guard_dispatch_icall_fptr
0x18000410a  mov     ebx, eax
0x18000410c  test    eax, eax
0x18000410e  js      loc_1800043B8
0x180004114  mov     rax, [r15]
0x180004117  mov     rcx, r15
0x18000411a  mov     rax, [rax+48h]
0x18000411e  call    cs:__guard_dispatch_icall_fptr
0x180004124  mov     r8d, eax
0x180004127  mov     ecx, [r15+10h]
0x18000412b  test    eax, eax
0x18000412d  jz      loc_180004038
0x180004133  xor     edx, edx
0x180004135  or      eax, 0FFFFFFFFh
0x180004138  div     r8d
0x18000413b  cmp     ecx, eax
0x18000413d  ja      loc_180004038
0x180004143  imul    ecx, r8d
0x180004147  cmp     ecx, 1
0x18000414a  jb      loc_180004038
0x180004150  lea     edx, [rcx-1]
0x180004153  add     rdx, [rbp+var_30]
0x180004157  cmp     r13d, 1
0x18000415b  jb      loc_180004038
0x180004161  lea     ecx, [r13-1]
0x180004165  add     rcx, r14
0x180004168  cmp     rcx, [rbp+var_30]
0x18000416c  jb      short loc_180004175
0x18000416e  cmp     r14, rdx
0x180004171  mov     al, 1
0x180004173  jbe     short loc_180004178
0x180004175  mov     al, r12b
0x180004178  mov     rdx, r12
0x18000417b  mov     [rbp+var_18], rdx
0x18000417f  mov     [rbp+var_10], r12d
0x180004183  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000418a  mov     [rbp+var_20], r13
0x18000418e  mov     rcx, r12
0x180004191  mov     r8, r12
0x180004194  test    al, al
0x180004196  jz      loc_180004265
0x18000419c  mov     edx, edi; unsigned int
0x18000419e  lea     rcx, [rbp+var_20]; this
0x1800041a2  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x1800041a7  mov     ebx, eax
0x1800041a9  test    eax, eax
0x1800041ab  jns     short loc_1800041C5
0x1800041ad  mov     [rbp+var_20], r13
0x1800041b1  mov     rcx, [rbp+var_18]; void *
0x1800041b5  test    rcx, rcx
0x1800041b8  jz      short loc_1800041C0
0x1800041ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800041bf  nop
0x1800041c0  jmp     loc_1800043B8
0x1800041c5  test    edi, edi
0x1800041c7  jz      loc_180004258
0x1800041cd  mov     eax, [rbp+var_10]
0x1800041d0  test    eax, eax
0x1800041d2  jnz     short loc_1800041F1
0x1800041d4  mov     ebx, 80070057h
0x1800041d9  mov     [rbp+var_20], r13
0x1800041dd  mov     rcx, [rbp+var_18]; void *
0x1800041e1  test    rcx, rcx
0x1800041e4  jz      short loc_1800041EC
0x1800041e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800041eb  nop
0x1800041ec  jmp     loc_1800042A9
0x1800041f1  cmp     eax, edi
0x1800041f3  jb      short loc_1800041D4
0x1800041f5  mov     [rbp+var_30], r12
0x1800041f9  mov     rax, [rbp+var_20]
0x1800041fd  lea     r8, [rbp+var_30]
0x180004201  xor     edx, edx
0x180004203  lea     rcx, [rbp+var_20]
0x180004207  mov     rax, [rax+40h]
0x18000420b  call    cs:__guard_dispatch_icall_fptr
0x180004211  mov     ebx, eax
0x180004213  test    eax, eax
0x180004215  js      short loc_1800041D9
0x180004217  mov     rax, [rbp+var_20]
0x18000421b  lea     rcx, [rbp+var_20]
0x18000421f  mov     rax, [rax+48h]
0x180004223  call    cs:__guard_dispatch_icall_fptr
0x180004229  mov     ecx, eax
0x18000422b  test    eax, eax
0x18000422d  jnz     short loc_180004234
0x18000422f  mov     ecx, r12d
0x180004232  jmp     short loc_180004249
0x180004234  xor     edx, edx
0x180004236  or      eax, 0FFFFFFFFh
0x180004239  div     ecx
0x18000423b  cmp     edi, eax
0x18000423d  jbe     short loc_180004246
0x18000423f  mov     ebx, 80070216h
0x180004244  jmp     short loc_1800041D9
0x180004246  imul    ecx, edi
0x180004249  mov     r8d, ecx; Size
0x18000424c  mov     rdx, r14; Src
0x18000424f  mov     rcx, [rbp+var_30]; void *
0x180004253  call    memmove
0x180004258  mov     rdx, [rbp+var_18]; struct std::nothrow_t *
0x18000425c  mov     r14, rdx
0x18000425f  mov     rcx, rdx
0x180004262  mov     r8, rdx
0x180004265  mov     r9d, [rsi+20h]
0x180004269  mov     eax, edi
0x18000426b  not     eax
0x18000426d  cmp     r9d, eax
0x180004270  ja      short loc_18000428A
0x180004272  lea     r13d, [r9+rdi]
0x180004276  mov     eax, r13d
0x180004279  not     eax
0x18000427b  cmp     eax, 1
0x18000427e  jnb     short loc_1800042B6
0x180004280  mov     rcx, r8
0x180004283  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000428a  mov     ebx, 80070216h
0x18000428f  mov     [rbp+var_20], r13
0x180004293  test    rcx, rcx
  ... truncated ...
```
