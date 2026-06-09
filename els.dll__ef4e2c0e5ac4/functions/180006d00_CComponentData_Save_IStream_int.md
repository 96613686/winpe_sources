# CComponentData::Save(IStream *,int)

- ea: `0x180006d00`
- end: `0x180006f8e`
- name: `?Save@CComponentData@@UEAAJPEAUIStream@@H@Z`
- size: `654`
- prototype: `int(CComponentData *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006d00`
- `0x1800164d8`
- `0x18001658c`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::Save(CComponentData *this, struct IStream *a2, int a3)
{
  int v3; // ebp
  _QWORD *v4; // rdi
  _QWORD *v8; // r8
  int v9; // edx
  _DWORD *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned __int16 v13; // ax
  unsigned __int16 v14; // di
  __int64 v15; // rax
  CLogSet *v16; // rcx
  __int16 v17; // dx
  __int64 v18; // rcx
  CLogSet *v19; // rdi
  CLogSet *v20; // rcx
  _WORD v22[36]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v23; // [rsp+80h] [rbp+8h] BYREF
  __int16 v24; // [rsp+98h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 300);
  v4 = (_QWORD *)((char *)this + 1184);
  while ( v3 > 0 )
  {
    if ( *((_QWORD *)this + 151) < 4u )
      v8 = v4;
    else
      v8 = (_QWORD *)*v4;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 147) + 48LL))(
           *((_QWORD *)this + 147),
           *((unsigned int *)v8 + (unsigned int)v3 - 1));
    if ( v9 < 0 )
      return (unsigned int)v9;
    --v3;
  }
  if ( v4[3] < 4u )
    v10 = v4;
  else
    v10 = (_DWORD *)*v4;
  v4[2] = 0;
  *v10 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IStream *, const unsigned __int16 *, __int64))(*(_QWORD *)a2 + 32LL))(
         a2,
         &FILE_VERSION,
         2);
  if ( v9 >= 0 )
  {
    v22[0] = *((_WORD *)this + 28) & 0x40;
    v9 = (*(__int64 (__fastcall **)(struct IStream *, _WORD *, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, v22, 2, 0);
    if ( v9 >= 0 )
    {
      v11 = -1;
      if ( this == (CComponentData *)-88LL )
      {
        v13 = 0;
      }
      else
      {
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)this + v12 + 44) );
        v13 = v12 + 1;
      }
      v23 = v13;
      v9 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(
             a2,
             &v23,
             2,
             0);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct IStream *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
               a2,
               (char *)this + 88,
               2 * (unsigned int)v23,
               0);
        if ( v9 >= 0 )
        {
          if ( this == (CComponentData *)-612LL )
          {
            v14 = 0;
          }
          else
          {
            do
              ++v11;
            while ( *((_WORD *)this + v11 + 306) );
            v14 = v11 + 1;
          }
          v15 = *(_QWORD *)a2;
          v23 = v14;
          v9 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64, _QWORD))(v15 + 32))(
                 a2,
                 &v23,
                 2,
                 0);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(struct IStream *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   (char *)this + 612,
                   2 * (unsigned int)v23,
                   0);
            if ( v9 >= 0 )
            {
              v16 = (CLogSet *)*((_QWORD *)this + 10);
              v24 = 0;
              while ( v16 )
              {
                if ( CLogSet::ShouldSave(v16) )
                  v24 = v17 + 1;
                v16 = *(CLogSet **)(v18 + 8);
              }
              v9 = (*(__int64 (__fastcall **)(struct IStream *, __int16 *, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(
                     a2,
                     &v24,
                     2,
                     0);
              if ( v9 >= 0 )
              {
                v19 = (CLogSet *)*((_QWORD *)this + 10);
                if ( v19 )
                {
                  while ( 1 )
                  {
                    if ( CLogSet::ShouldSave(v19) )
                    {
                      v9 = CLogSet::Save(v20, a2, *((struct IStringTable **)this + 147));
                      if ( v9 < 0 )
                        break;
                    }
                    v19 = (CLogSet *)*((_QWORD *)v19 + 1);
                    if ( !v19 )
                    {
                      if ( v9 < 0 )
                        return (unsigned int)v9;
                      goto LABEL_37;
                    }
                  }
                }
                else
                {
LABEL_37:
                  if ( a3 )
                    *((_WORD *)this + 28) &= ~1u;
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006d00  mov     [rsp+arg_8], rbx
0x180006d05  push    rbp
0x180006d06  push    rsi
0x180006d07  push    rdi
0x180006d08  push    r12
0x180006d0a  push    r13
0x180006d0c  push    r14
0x180006d0e  push    r15
0x180006d10  sub     rsp, 40h
0x180006d14  mov     ebp, [rcx+4B0h]
0x180006d1a  lea     rdi, [rcx+4A0h]
0x180006d21  mov     r14d, r8d
0x180006d24  mov     rsi, rdx
0x180006d27  mov     rbx, rcx
0x180006d2a  mov     r12d, 1
0x180006d30  xor     r15d, r15d
0x180006d33  jmp     short loc_180006D6E
0x180006d35  cmp     qword ptr [rbx+4B8h], 4
0x180006d3d  jb      short loc_180006D44
0x180006d3f  mov     r8, [rdi]
0x180006d42  jmp     short loc_180006D47
0x180006d44  mov     r8, rdi
0x180006d47  mov     rcx, [rbx+498h]
0x180006d4e  mov     edx, ebp
0x180006d50  mov     rax, [rcx]
0x180006d53  mov     edx, [r8+rdx*4-4]
0x180006d58  mov     rax, [rax+30h]
0x180006d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d61  mov     edx, eax
0x180006d63  test    eax, eax
0x180006d65  js      loc_180006F74
0x180006d6b  sub     ebp, r12d
0x180006d6e  test    ebp, ebp
0x180006d70  jg      short loc_180006D35
0x180006d72  cmp     qword ptr [rdi+18h], 4
0x180006d77  jb      short loc_180006D7E
0x180006d79  mov     rax, [rdi]
0x180006d7c  jmp     short loc_180006D81
0x180006d7e  mov     rax, rdi
0x180006d81  mov     [rdi+10h], r15
0x180006d85  lea     rdx, ?FILE_VERSION@@3GB; ushort const FILE_VERSION
0x180006d8c  mov     [rax], r15d
0x180006d8f  xor     r9d, r9d
0x180006d92  mov     rax, [rsi]
0x180006d95  mov     rcx, rsi
0x180006d98  lea     r13d, [r9+2]
0x180006d9c  mov     rax, [rax+20h]
0x180006da0  mov     r8d, r13d
0x180006da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da8  mov     edx, eax
0x180006daa  test    eax, eax
0x180006dac  js      loc_180006F74
0x180006db2  movzx   eax, word ptr [rbx+38h]
0x180006db6  lea     rdx, [rsp+78h+var_48]
0x180006dbb  and     ax, 40h
0x180006dbf  xor     r9d, r9d
0x180006dc2  mov     [rsp+78h+var_48], ax
0x180006dc7  mov     r8d, r13d
0x180006dca  mov     rax, [rsi]
0x180006dcd  mov     rcx, rsi
0x180006dd0  mov     rax, [rax+20h]
0x180006dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd9  mov     edx, eax
0x180006ddb  test    eax, eax
0x180006ddd  js      loc_180006F74
0x180006de3  lea     rbp, [rbx+58h]
0x180006de7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006deb  test    rbp, rbp
0x180006dee  jz      short loc_180006E04
0x180006df0  mov     rax, rdi
0x180006df3  inc     rax
0x180006df6  cmp     [rbp+rax*2+0], r15w
0x180006dfc  jnz     short loc_180006DF3
0x180006dfe  add     ax, r12w
0x180006e02  jmp     short loc_180006E07
0x180006e04  mov     eax, r15d
0x180006e07  mov     [rsp+78h+arg_0], ax
0x180006e0f  lea     rdx, [rsp+78h+arg_0]
0x180006e17  mov     rax, [rsi]
0x180006e1a  xor     r9d, r9d
0x180006e1d  mov     r8d, r13d
0x180006e20  mov     rcx, rsi
0x180006e23  mov     rax, [rax+20h]
0x180006e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2c  mov     edx, eax
0x180006e2e  test    eax, eax
0x180006e30  js      loc_180006F74
0x180006e36  mov     rax, [rsi]
0x180006e39  xor     r9d, r9d
0x180006e3c  movzx   r8d, [rsp+78h+arg_0]
0x180006e45  mov     rdx, rbp
0x180006e48  add     r8d, r8d
0x180006e4b  mov     rcx, rsi
0x180006e4e  mov     rax, [rax+20h]
0x180006e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e57  mov     edx, eax
0x180006e59  test    eax, eax
0x180006e5b  js      loc_180006F74
0x180006e61  lea     rbp, [rbx+264h]
0x180006e68  test    rbp, rbp
0x180006e6b  jz      short loc_180006E7E
0x180006e6d  inc     rdi
0x180006e70  cmp     [rbp+rdi*2+0], r15w
0x180006e76  jnz     short loc_180006E6D
0x180006e78  add     di, r12w
0x180006e7c  jmp     short loc_180006E81
0x180006e7e  mov     edi, r15d
0x180006e81  mov     rax, [rsi]
0x180006e84  lea     rdx, [rsp+78h+arg_0]
0x180006e8c  xor     r9d, r9d
0x180006e8f  mov     [rsp+78h+arg_0], di
0x180006e97  mov     r8d, r13d
0x180006e9a  mov     rcx, rsi
0x180006e9d  mov     rax, [rax+20h]
0x180006ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea6  mov     edx, eax
0x180006ea8  test    eax, eax
0x180006eaa  js      loc_180006F74
0x180006eb0  mov     rax, [rsi]
0x180006eb3  xor     r9d, r9d
0x180006eb6  movzx   r8d, [rsp+78h+arg_0]
0x180006ebf  mov     rdx, rbp
0x180006ec2  add     r8d, r8d
0x180006ec5  mov     rcx, rsi
0x180006ec8  mov     rax, [rax+20h]
0x180006ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed1  mov     edx, eax
0x180006ed3  test    eax, eax
0x180006ed5  js      loc_180006F74
0x180006edb  mov     rcx, [rbx+50h]
0x180006edf  mov     edx, r15d
0x180006ee2  mov     [rsp+78h+arg_18], dx
0x180006eea  jmp     short loc_180006F05
0x180006eec  call    ?ShouldSave@CLogSet@@QEBA_NXZ; CLogSet::ShouldSave(void)
0x180006ef1  test    al, al
0x180006ef3  jz      short loc_180006F01
0x180006ef5  add     dx, r12w
0x180006ef9  mov     [rsp+78h+arg_18], dx
0x180006f01  mov     rcx, [rcx+8]; this
0x180006f05  test    rcx, rcx
0x180006f08  jnz     short loc_180006EEC
0x180006f0a  mov     rax, [rsi]
0x180006f0d  lea     rdx, [rsp+78h+arg_18]
0x180006f15  xor     r9d, r9d
0x180006f18  mov     r8d, r13d
0x180006f1b  mov     rcx, rsi
0x180006f1e  mov     rax, [rax+20h]
0x180006f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f27  mov     edx, eax
0x180006f29  test    eax, eax
0x180006f2b  js      short loc_180006F74
0x180006f2d  mov     rdi, [rbx+50h]
0x180006f31  test    rdi, rdi
0x180006f34  jz      short loc_180006F66
0x180006f36  mov     rcx, rdi; this
0x180006f39  call    ?ShouldSave@CLogSet@@QEBA_NXZ; CLogSet::ShouldSave(void)
0x180006f3e  test    al, al
0x180006f40  jz      short loc_180006F57
0x180006f42  mov     r8, [rbx+498h]; struct IStringTable *
0x180006f49  mov     rdx, rsi; struct IStream *
0x180006f4c  call    ?Save@CLogSet@@QEAAJPEAUIStream@@PEAUIStringTable@@@Z; CLogSet::Save(IStream *,IStringTable *)
0x180006f51  mov     edx, eax
0x180006f53  test    eax, eax
0x180006f55  js      short loc_180006F74
0x180006f57  mov     rdi, [rdi+8]
0x180006f5b  mov     eax, edx
0x180006f5d  test    rdi, rdi
0x180006f60  jnz     short loc_180006F36
0x180006f62  test    eax, eax
0x180006f64  js      short loc_180006F74
0x180006f66  test    r14d, r14d
0x180006f69  jz      short loc_180006F74
0x180006f6b  mov     eax, 0FFFEh
0x180006f70  and     [rbx+38h], ax
0x180006f74  mov     rbx, [rsp+78h+arg_8]
0x180006f7c  mov     eax, edx
0x180006f7e  add     rsp, 40h
0x180006f82  pop     r15
0x180006f84  pop     r14
0x180006f86  pop     r13
0x180006f88  pop     r12
0x180006f8a  pop     rdi
0x180006f8b  pop     rsi
0x180006f8c  pop     rbp
0x180006f8d  retn
```
