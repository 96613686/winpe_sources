# CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)

- ea: `0x18000f02c`
- end: `0x18000f1b7`
- name: `?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z`
- size: `395`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `12`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e408`
- `0x18000e83c`
- `0x18000ec68`
- `0x18000ee40`
- `0x18000f298`
- `0x18000f478`
- `0x18000f674`
- `0x18000f908`
- `0x18000fb88`
- `0x18000fd64`
- `0x180010218`
- `0x1800103ac`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000f02c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CSecConLib::GetMultiSZPropVal(
        CSecConLib *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  __int64 v7; // rcx
  int v9; // edi
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edx
  void *v13; // rax
  void *v14; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // [rsp+40h] [rbp-38h] BYREF
  __int128 v20; // [rsp+48h] [rbp-30h] BYREF
  __int128 v21; // [rsp+58h] [rbp-20h]
  __int64 v22; // [rsp+68h] [rbp-10h]
  unsigned __int64 v23; // [rsp+B0h] [rbp+38h] BYREF

  LODWORD(v23) = 0;
  v22 = 0;
  v19 = 0;
  v7 = *((_QWORD *)this + 7);
  v20 = 0;
  v21 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)v7 + 136LL))(
         v7,
         0,
         a2,
         1,
         30000,
         &v19);
  if ( v9 < 0 )
    goto LABEL_5;
  v10 = *((_QWORD *)this + 7);
  LODWORD(v21) = v23;
  v20 = a3;
  *((_QWORD *)&v21 + 1) = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int128 *, unsigned __int64 *))(*(_QWORD *)v10 + 80LL))(
          v10,
          v19,
          &hMem,
          &v20,
          &v23);
  v12 = v23;
  v9 = v11;
  if ( (_DWORD)v23 )
  {
    *a5 = (unsigned int)v23 >> 1;
    v13 = operator new[](v12);
    v14 = v13;
    if ( !v13 )
    {
      v9 = -2147024882;
LABEL_5:
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 144LL))(*((_QWORD *)this + 7), v19);
      return (unsigned int)v9;
    }
    v16 = *((_QWORD *)this + 7);
    LODWORD(v21) = v23;
    v20 = a3;
    *((_QWORD *)&v21 + 1) = v13;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int128 *, unsigned __int64 *))(*(_QWORD *)v16 + 80LL))(
           v16,
           v19,
           &hMem,
           &v20,
           &v23);
  }
  else
  {
    v14 = 0;
  }
  if ( v9 < 0 )
  {
    if ( v14 )
      operator delete(v14);
    goto LABEL_5;
  }
  v17 = *((_QWORD *)this + 7);
  v18 = v19;
  *a4 = (unsigned __int16 *)v14;
  return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 144LL))(v17, v18);
}

```

## disassembly

```asm
0x18000f02c  push    rbp
0x18000f02e  push    rbx
0x18000f02f  push    rsi
0x18000f030  push    rdi
0x18000f031  push    r14
0x18000f033  push    r15
0x18000f035  mov     rbp, rsp
0x18000f038  sub     rsp, 78h
0x18000f03c  xor     eax, eax
0x18000f03e  mov     dword ptr [rbp+arg_0], 0
0x18000f045  xorps   xmm0, xmm0
0x18000f048  mov     [rbp+var_10], rax
0x18000f04c  mov     [rbp+var_38], eax
0x18000f04f  mov     r14d, r8d
0x18000f052  mov     rsi, rcx
0x18000f055  lea     r8, [rbp+var_38]
0x18000f059  mov     rcx, [rcx+38h]
0x18000f05d  mov     r15, r9
0x18000f060  mov     [rsp+78h+var_50], r8
0x18000f065  mov     r9d, 1
0x18000f06b  movups  [rbp+var_30], xmm0
0x18000f06f  mov     r8, rdx
0x18000f072  xor     edx, edx
0x18000f074  movups  [rbp+var_20], xmm0
0x18000f078  mov     rax, [rcx]
0x18000f07b  mov     dword ptr [rsp+78h+var_58], 7530h
0x18000f083  mov     rax, [rax+88h]
0x18000f08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08f  mov     edi, eax
0x18000f091  test    eax, eax
0x18000f093  js      short loc_18000F10E
0x18000f095  mov     eax, dword ptr [rbp+arg_0]
0x18000f098  lea     rdx, [rbp+arg_0]
0x18000f09c  mov     rcx, [rsi+38h]
0x18000f0a0  lea     r9, [rbp+var_30]
0x18000f0a4  mov     dword ptr [rbp+var_20], eax
0x18000f0a7  lea     r8, hMem
0x18000f0ae  mov     dword ptr [rbp+var_30], r14d
0x18000f0b2  mov     dword ptr [rbp+var_30+4], 0
0x18000f0b9  mov     dword ptr [rbp+var_30+8], 1
0x18000f0c0  mov     dword ptr [rbp+var_30+0Ch], 5
0x18000f0c7  mov     qword ptr [rbp+var_20+8], 0
0x18000f0cf  mov     rax, [rcx]
0x18000f0d2  mov     [rsp+78h+var_58], rdx
0x18000f0d7  mov     edx, [rbp+var_38]
0x18000f0da  mov     rax, [rax+50h]
0x18000f0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e3  mov     edx, dword ptr [rbp+arg_0]
0x18000f0e6  mov     edi, eax
0x18000f0e8  test    edx, edx
0x18000f0ea  jz      loc_18000F181
0x18000f0f0  mov     rax, [rbp+arg_20]
0x18000f0f4  mov     ecx, edx
0x18000f0f6  shr     ecx, 1
0x18000f0f8  mov     [rax], ecx
0x18000f0fa  mov     ecx, edx; unsigned __int64
0x18000f0fc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f101  mov     rbx, rax
0x18000f104  test    rax, rax
0x18000f107  jnz     short loc_18000F133
0x18000f109  mov     edi, 8007000Eh
0x18000f10e  mov     rcx, [rsi+38h]
0x18000f112  mov     edx, [rbp+var_38]
0x18000f115  mov     rax, [rcx]
0x18000f118  mov     rax, [rax+90h]
0x18000f11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f124  mov     eax, edi
0x18000f126  add     rsp, 78h
0x18000f12a  pop     r15
0x18000f12c  pop     r14
0x18000f12e  pop     rdi
0x18000f12f  pop     rsi
0x18000f130  pop     rbx
0x18000f131  pop     rbp
0x18000f132  retn
0x18000f133  mov     eax, dword ptr [rbp+arg_0]
0x18000f136  lea     rdx, [rbp+arg_0]
0x18000f13a  mov     rcx, [rsi+38h]
0x18000f13e  lea     r9, [rbp+var_30]
0x18000f142  mov     dword ptr [rbp+var_20], eax
0x18000f145  lea     r8, hMem
0x18000f14c  mov     dword ptr [rbp+var_30], r14d
0x18000f150  mov     dword ptr [rbp+var_30+4], 0
0x18000f157  mov     dword ptr [rbp+var_30+8], 1
0x18000f15e  mov     dword ptr [rbp+var_30+0Ch], 5
0x18000f165  mov     qword ptr [rbp+var_20+8], rbx
0x18000f169  mov     rax, [rcx]
0x18000f16c  mov     [rsp+78h+var_58], rdx
0x18000f171  mov     edx, [rbp+var_38]
0x18000f174  mov     rax, [rax+50h]
0x18000f178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f17d  mov     edi, eax
0x18000f17f  jmp     short loc_18000F183
0x18000f181  xor     ebx, ebx
0x18000f183  test    edi, edi
0x18000f185  jns     short loc_18000F199
0x18000f187  test    rbx, rbx
0x18000f18a  jz      short loc_18000F10E
0x18000f18c  mov     rcx, rbx; Block
0x18000f18f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f194  jmp     loc_18000F10E
0x18000f199  mov     rcx, [rsi+38h]
0x18000f19d  mov     edx, [rbp+var_38]
0x18000f1a0  mov     [r15], rbx
0x18000f1a3  mov     rax, [rcx]
0x18000f1a6  mov     rax, [rax+90h]
0x18000f1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1b2  jmp     loc_18000F126
```
