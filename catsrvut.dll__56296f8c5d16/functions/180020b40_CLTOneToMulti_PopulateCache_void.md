# CLTOneToMulti::PopulateCache(void)

- ea: `0x180020b40`
- end: `0x180020f87`
- name: `?PopulateCache@CLTOneToMulti@@UEAAJXZ`
- size: `1095`
- prototype: `__int64 __fastcall(CLTOneToMulti *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180020b40`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020bdf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020c92`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTOneToMulti::PopulateCache(CLTOneToMulti *this)
{
  unsigned int v2; // r12d
  _DWORD *v3; // r14
  HRESULT v4; // ebx
  _QWORD *v5; // r15
  __int64 v6; // rcx
  int v7; // eax
  unsigned int i; // esi
  __int64 v9; // rdx
  int v10; // eax
  unsigned int j; // esi
  __int64 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // r8
  LPVOID ppv; // [rsp+50h] [rbp-18h] BYREF
  __int64 v17; // [rsp+58h] [rbp-10h] BYREF
  int v18; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+60h] BYREF

  v2 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  ppv = 0;
  v21 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 33)
    || (v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 6))(
               *((_QWORD *)this + 6),
               &IID_ISimpleTableControl,
               &v17),
        v4 >= 0)
    && (v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, 0), v4 >= 0) )
  {
    v4 = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
    if ( v4 >= 0 )
    {
      v5 = (_QWORD *)((char *)this + 40);
      v6 = *((_QWORD *)this + 5);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v4 = (*(__int64 (__fastcall **)(LPVOID, char *, char *, _QWORD, _QWORD, int, _DWORD, char *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             (char *)this + 76,
             (char *)this + 92,
             *((_QWORD *)this + 8),
             *((unsigned int *)this + 18),
             1,
             *((_DWORD *)this + 31),
             (char *)this + 40);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 24LL))(*v5);
        if ( v4 >= 0 )
        {
          if ( *((_DWORD *)this + 40) != *((_DWORD *)this + 44) )
          {
LABEL_10:
            v4 = -2147418113;
            goto LABEL_46;
          }
          v3 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 40), 0x18u));
          if ( v3 )
          {
            v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
            if ( v4 >= 0 )
            {
              while ( 1 )
              {
                v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 40LL))(*v5);
                v4 = v7;
                if ( v7 < 0 )
                  break;
                for ( i = 0; i < *((_DWORD *)this + 44); ++i )
                {
                  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)*v5 + 64LL))(
                         *v5,
                         *(unsigned int *)(*((_QWORD *)this + 21) + 4LL * i),
                         &v18,
                         &v19,
                         &v20);
                  if ( v4 < 0 )
                    goto LABEL_46;
                  if ( v20 )
                  {
                    v9 = 3LL * v2;
                    v3[2 * v9 + 2] = 0;
                    v3[2 * v9 + 4] = v18;
                    v3[2 * v9 + 5] = v19;
                    v3[2 * v9 + 3] = *(_DWORD *)(*((_QWORD *)this + 19) + 4LL * i);
                    *(_QWORD *)&v3[2 * v9] = v20;
                    ++v2;
                  }
                }
                if ( v21 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                v4 = (*(__int64 (__fastcall **)(LPVOID, char *, char *, _DWORD *, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       (char *)this + 76,
                       (char *)this + 108,
                       v3,
                       v2,
                       1,
                       *((_DWORD *)this + 32) | (*((_DWORD *)this + 40) != v2 ? 8 : 0),
                       &v21);
                v2 = 0;
                if ( v4 < 0 )
                  goto LABEL_46;
                v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
                if ( v4 < 0 )
                  goto LABEL_46;
                if ( !*((_DWORD *)this + 33) )
                {
                  while ( 1 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
                    if ( v10 < 0 )
                      break;
                    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 120LL))(*((_QWORD *)this + 6));
                    if ( v4 >= 0 )
                    {
                      for ( j = 0; j < *((_DWORD *)this + 50); ++j )
                      {
                        v12 = *((_QWORD *)this + 23);
                        if ( *(_DWORD *)(v12 + 8LL * j) )
                          v13 = *v5;
                        else
                          v13 = v21;
                        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)v13 + 64LL))(
                               v13,
                               *(unsigned int *)(v12 + 8LL * j + 4),
                               &v18,
                               &v19,
                               &v20);
                        if ( v4 < 0 )
                          goto LABEL_46;
                        v14 = v18 == 128 ? v19 : 0LL;
                        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 6)
                                                                                         + 160LL))(
                               *((_QWORD *)this + 6),
                               j,
                               v14,
                               v20);
                        if ( v4 < 0 )
                          goto LABEL_46;
                      }
                      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 144LL))(*((_QWORD *)this + 6));
                      if ( v4 >= 0 )
                        continue;
                    }
                    goto LABEL_46;
                  }
                  if ( v10 != -2146367487 )
                    goto LABEL_10;
                }
              }
              if ( v7 != -2146367487 )
                goto LABEL_10;
              if ( !*((_DWORD *)this + 33) )
                v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
            }
          }
          else
          {
            v4 = -2147024882;
          }
        }
      }
    }
  }
LABEL_46:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020b40  push    rbp
0x180020b42  push    rbx
0x180020b43  push    rsi
0x180020b44  push    rdi
0x180020b45  push    r12
0x180020b47  push    r13
0x180020b49  push    r14
0x180020b4b  push    r15
0x180020b4d  mov     rbp, rsp
0x180020b50  sub     rsp, 68h
0x180020b54  mov     rdi, rcx
0x180020b57  xor     r12d, r12d
0x180020b5a  mov     [rbp+arg_10], r12
0x180020b5e  mov     [rbp+arg_8], r12d
0x180020b62  mov     [rbp+arg_0], r12d
0x180020b66  mov     [rbp+var_10], r12
0x180020b6a  mov     [rbp+var_18], r12
0x180020b6e  mov     [rbp+arg_18], r12
0x180020b72  mov     r14d, r12d
0x180020b75  cmp     [rcx+84h], r12d
0x180020b7c  jnz     short loc_180020BBE
0x180020b7e  mov     rcx, [rcx+30h]
0x180020b82  mov     rax, [rcx]
0x180020b85  lea     r8, [rbp+var_10]
0x180020b89  lea     rdx, IID_ISimpleTableControl
0x180020b90  mov     rax, [rax]
0x180020b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b98  mov     ebx, eax
0x180020b9a  test    eax, eax
0x180020b9c  js      loc_180020F1A
0x180020ba2  mov     rcx, [rbp+var_10]
0x180020ba6  mov     rax, [rcx]
0x180020ba9  xor     edx, edx
0x180020bab  mov     rax, [rax+20h]
0x180020baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb4  mov     ebx, eax
0x180020bb6  test    eax, eax
0x180020bb8  js      loc_180020F1A
0x180020bbe  lea     rax, [rbp+var_18]
0x180020bc2  mov     [rsp+68h+ppv], rax; ppv
0x180020bc7  lea     r9, IID_ISimpleTableDispenser; riid
0x180020bce  mov     esi, 1
0x180020bd3  mov     r8d, esi; dwClsContext
0x180020bd6  xor     edx, edx; pUnkOuter
0x180020bd8  lea     rcx, clsidSTDISP; rclsid
0x180020bdf  call    cs:__imp_CoCreateInstance
0x180020be5  mov     ebx, eax
0x180020be7  test    eax, eax
0x180020be9  js      loc_180020F1A
0x180020bef  lea     r15, [rdi+28h]
0x180020bf3  mov     rcx, [r15]
0x180020bf6  test    rcx, rcx
0x180020bf9  jz      short loc_180020C07
0x180020bfb  mov     rax, [rcx]
0x180020bfe  mov     rax, [rax+10h]
0x180020c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c07  mov     rcx, [rbp+var_18]
0x180020c0b  mov     rax, [rcx]
0x180020c0e  mov     edx, [rdi+48h]
0x180020c11  lea     r8, [rdi+5Ch]
0x180020c15  mov     r10, [rax+18h]
0x180020c19  mov     [rsp+68h+var_30], r15
0x180020c1e  mov     eax, [rdi+7Ch]
0x180020c21  mov     [rsp+68h+var_38], eax
0x180020c25  mov     [rsp+68h+var_40], esi
0x180020c29  mov     [rsp+68h+ppv], rdx
0x180020c2e  mov     r9, [rdi+40h]
0x180020c32  lea     rdx, [rdi+4Ch]
0x180020c36  mov     rax, r10
0x180020c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c3e  mov     ebx, eax
0x180020c40  test    eax, eax
0x180020c42  js      loc_180020F1A
0x180020c48  mov     rcx, [r15]
0x180020c4b  mov     rax, [rcx]
0x180020c4e  mov     rax, [rax+18h]
0x180020c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c57  mov     ebx, eax
0x180020c59  test    eax, eax
0x180020c5b  js      loc_180020F1A
0x180020c61  mov     eax, [rdi+0A0h]
0x180020c67  cmp     eax, [rdi+0B0h]
0x180020c6d  jz      short loc_180020C79
0x180020c6f  mov     ebx, 8000FFFFh
0x180020c74  jmp     loc_180020F1A
0x180020c79  mov     rcx, rax
0x180020c7c  mov     eax, 18h
0x180020c81  mul     rcx
0x180020c84  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020c8b  cmovb   rax, rcx
0x180020c8f  mov     rcx, rax; cb
0x180020c92  call    cs:__imp_CoTaskMemAlloc
0x180020c98  mov     r14, rax
0x180020c9b  test    rax, rax
0x180020c9e  jnz     short loc_180020CAA
0x180020ca0  mov     ebx, 8007000Eh
0x180020ca5  jmp     loc_180020F1A
0x180020caa  mov     rcx, [r15]
0x180020cad  mov     rax, [rcx]
0x180020cb0  mov     rax, [rax+20h]
0x180020cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb9  mov     ebx, eax
0x180020cbb  test    eax, eax
0x180020cbd  js      loc_180020F1A
0x180020cc3  mov     rcx, [r15]
0x180020cc6  mov     rax, [rcx]
0x180020cc9  mov     rax, [rax+28h]
0x180020ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cd2  mov     ebx, eax
0x180020cd4  test    eax, eax
0x180020cd6  js      loc_180020EEF
0x180020cdc  mov     esi, r12d
0x180020cdf  cmp     esi, [rdi+0B0h]
0x180020ce5  jnb     loc_180020D6C
0x180020ceb  mov     rcx, [r15]
0x180020cee  mov     r13d, esi
0x180020cf1  mov     rax, [rcx]
0x180020cf4  mov     rdx, [rdi+0A8h]
0x180020cfb  lea     r8, [rbp+arg_10]
0x180020cff  mov     [rsp+68h+ppv], r8
0x180020d04  lea     r9, [rbp+arg_8]
0x180020d08  lea     r8, [rbp+arg_0]
0x180020d0c  mov     edx, [rdx+r13*4]
0x180020d10  mov     rax, [rax+40h]
0x180020d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d19  mov     ebx, eax
0x180020d1b  test    eax, eax
0x180020d1d  js      loc_180020F17
0x180020d23  cmp     [rbp+arg_10], 0
0x180020d28  jz      short loc_180020D65
0x180020d2a  mov     eax, r12d
0x180020d2d  lea     rdx, [rax+rax*2]
0x180020d31  mov     dword ptr [r14+rdx*8+8], 0
0x180020d3a  mov     eax, [rbp+arg_0]
0x180020d3d  mov     [r14+rdx*8+10h], eax
0x180020d42  mov     eax, [rbp+arg_8]
0x180020d45  mov     [r14+rdx*8+14h], eax
0x180020d4a  mov     rax, [rdi+98h]
0x180020d51  mov     ecx, [rax+r13*4]
0x180020d55  mov     [r14+rdx*8+0Ch], ecx
0x180020d5a  mov     rax, [rbp+arg_10]
0x180020d5e  mov     [r14+rdx*8], rax
0x180020d62  inc     r12d
0x180020d65  inc     esi
0x180020d67  jmp     loc_180020CDF
0x180020d6c  mov     rcx, [rbp+arg_18]
0x180020d70  test    rcx, rcx
0x180020d73  jz      short loc_180020D81
0x180020d75  mov     rax, [rcx]
0x180020d78  mov     rax, [rax+10h]
0x180020d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d81  mov     rcx, [rbp+var_18]
0x180020d85  mov     r10, [rcx]
0x180020d88  mov     eax, r12d
0x180020d8b  sub     eax, [rdi+0A0h]
0x180020d91  neg     eax
0x180020d93  sbb     r9d, r9d
0x180020d96  and     r9d, 8
0x180020d9a  or      r9d, [rdi+80h]
0x180020da1  mov     edx, r12d
0x180020da4  lea     r8, [rdi+6Ch]
0x180020da8  lea     rax, [rbp+arg_18]
0x180020dac  mov     [rsp+68h+var_30], rax
0x180020db1  mov     [rsp+68h+var_38], r9d
0x180020db6  mov     [rsp+68h+var_40], 1
0x180020dbe  mov     [rsp+68h+ppv], rdx
0x180020dc3  mov     r9, r14
0x180020dc6  lea     rdx, [rdi+4Ch]
0x180020dca  mov     rax, [r10+18h]
0x180020dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd3  mov     ebx, eax
0x180020dd5  xor     r12d, r12d
0x180020dd8  test    eax, eax
0x180020dda  js      loc_180020F1A
0x180020de0  mov     rcx, [rbp+arg_18]
0x180020de4  mov     rax, [rcx]
0x180020de7  mov     rax, [rax+18h]
0x180020deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020df0  mov     ebx, eax
0x180020df2  test    eax, eax
0x180020df4  js      loc_180020F1A
0x180020dfa  cmp     [rdi+84h], r12d
0x180020e01  jnz     loc_180020CC3
0x180020e07  mov     rcx, [rbp+arg_18]
0x180020e0b  mov     rax, [rcx]
0x180020e0e  mov     rax, [rax+28h]
0x180020e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e17  test    eax, eax
0x180020e19  js      loc_180020EDF
0x180020e1f  mov     rcx, [rdi+30h]
0x180020e23  mov     rax, [rcx]
0x180020e26  mov     rax, [rax+78h]
0x180020e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2f  mov     ebx, eax
0x180020e31  test    eax, eax
0x180020e33  js      loc_180020F1A
0x180020e39  mov     esi, r12d
0x180020e3c  cmp     esi, [rdi+0C8h]
0x180020e42  jnb     short loc_180020EC0
0x180020e44  mov     edx, esi
0x180020e46  mov     r10, [rdi+0B8h]
0x180020e4d  lea     r8, [rbp+arg_10]
0x180020e51  lea     r9, [rbp+arg_8]
0x180020e55  mov     [rsp+68h+ppv], r8
0x180020e5a  lea     r8, [rbp+arg_0]
0x180020e5e  cmp     [r10+rdx*8], r12d
0x180020e62  mov     edx, [r10+rdx*8+4]
0x180020e67  jz      short loc_180020E6E
0x180020e69  mov     rcx, [r15]
0x180020e6c  jmp     short loc_180020E72
0x180020e6e  mov     rcx, [rbp+arg_18]
0x180020e72  mov     rax, [rcx]
0x180020e75  mov     rax, [rax+40h]
0x180020e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e7e  test    eax, eax
0x180020e80  mov     ebx, eax
0x180020e82  js      loc_180020F1A
0x180020e88  mov     rcx, [rdi+30h]
0x180020e8c  mov     rax, [rcx]
0x180020e8f  mov     rax, [rax+0A0h]
0x180020e96  mov     r9, [rbp+arg_10]
0x180020e9a  mov     edx, esi
0x180020e9c  cmp     [rbp+arg_0], 80h
0x180020ea3  jnz     short loc_180020EAB
0x180020ea5  mov     r8d, [rbp+arg_8]
0x180020ea9  jmp     short loc_180020EAE
0x180020eab  xor     r8d, r8d
0x180020eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eb3  mov     ebx, eax
0x180020eb5  test    eax, eax
0x180020eb7  js      short loc_180020F1A
0x180020eb9  inc     esi
0x180020ebb  jmp     loc_180020E3C
0x180020ec0  mov     rcx, [rdi+30h]
0x180020ec4  mov     rax, [rcx]
0x180020ec7  mov     rax, [rax+90h]
0x180020ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ed3  mov     ebx, eax
0x180020ed5  test    eax, eax
0x180020ed7  jns     loc_180020E07
0x180020edd  jmp     short loc_180020F1A
0x180020edf  cmp     eax, 80110801h
0x180020ee4  jz      loc_180020CC3
0x180020eea  jmp     loc_180020C6F
0x180020eef  cmp     eax, 80110801h
0x180020ef4  jnz     loc_180020C6F
0x180020efa  cmp     [rdi+84h], r12d
0x180020f01  jnz     short loc_180020F1A
0x180020f03  mov     rcx, [rbp+var_10]
0x180020f07  mov     rax, [rcx]
0x180020f0a  mov     rax, [rax+28h]
0x180020f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f13  mov     ebx, eax
0x180020f15  jmp     short loc_180020F1A
0x180020f17  xor     r12d, r12d
0x180020f1a  mov     rcx, [rbp+var_18]
0x180020f1e  test    rcx, rcx
0x180020f21  jz      short loc_180020F33
0x180020f23  mov     rax, [rcx]
0x180020f26  mov     rax, [rax+10h]
0x180020f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f2f  mov     [rbp+var_18], r12
0x180020f33  mov     rcx, [rbp+var_10]
0x180020f37  test    rcx, rcx
0x180020f3a  jz      short loc_180020F4C
0x180020f3c  mov     rax, [rcx]
0x180020f3f  mov     rax, [rax+10h]
0x180020f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f48  mov     [rbp+var_10], r12
0x180020f4c  mov     rcx, [rbp+arg_18]
0x180020f50  test    rcx, rcx
0x180020f53  jz      short loc_180020F65
0x180020f55  mov     rax, [rcx]
0x180020f58  mov     rax, [rax+10h]
0x180020f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f61  mov     [rbp+arg_18], r12
0x180020f65  test    r14, r14
0x180020f68  jz      short loc_180020F74
0x180020f6a  mov     rcx, r14; pv
0x180020f6d  call    cs:__imp_CoTaskMemFree
0x180020f73  nop
0x180020f74  mov     eax, ebx
0x180020f76  add     rsp, 68h
0x180020f7a  pop     r15
0x180020f7c  pop     r14
0x180020f7e  pop     r13
0x180020f80  pop     r12
0x180020f82  pop     rdi
0x180020f83  pop     rsi
0x180020f84  pop     rbx
0x180020f85  pop     rbp
0x180020f86  retn
```
