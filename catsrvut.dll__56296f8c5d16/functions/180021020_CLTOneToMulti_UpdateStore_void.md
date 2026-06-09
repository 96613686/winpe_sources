# CLTOneToMulti::UpdateStore(void)

- ea: `0x180021020`
- end: `0x18002167b`
- name: `?UpdateStore@CLTOneToMulti@@UEAAJXZ`
- size: `1627`
- prototype: `__int64 __fastcall(CLTOneToMulti *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180021020`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021090`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021185`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTOneToMulti::UpdateStore(CLTOneToMulti *this)
{
  void *v2; // r15
  void *v3; // r13
  _QWORD **v4; // rsi
  HRESULT v5; // ebx
  _QWORD *v6; // r12
  LPVOID v7; // rax
  __int64 i; // r14
  __int64 v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rcx
  int v12; // eax
  __int64 j; // r14
  __int64 (*v14)(void); // rax
  __int64 k; // r14
  __int64 v16; // r10
  __int64 v17; // rcx
  __int64 m; // r14
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  LPVOID ppv; // [rsp+50h] [rbp-28h] BYREF
  __int64 v24; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v25[3]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v26; // [rsp+C0h] [rbp+48h] BYREF
  int v27; // [rsp+C8h] [rbp+50h] BYREF
  int v28; // [rsp+D0h] [rbp+58h]
  void *v29; // [rsp+D8h] [rbp+60h]

  v26 = 0;
  v27 = 0;
  v24 = 0;
  ppv = 0;
  v2 = 0;
  v3 = 0;
  v4 = (_QWORD **)((char *)this - 8);
  if ( !*((_QWORD *)this + 5) )
  {
    *((_DWORD *)this + 33) = 1;
    (*(void (__fastcall **)(CLTOneToMulti *))(*(_QWORD *)this + 24LL))(this);
    *((_DWORD *)this + 33) = 0;
  }
  v5 = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
  if ( v5 >= 0 )
  {
    v6 = (_QWORD *)((char *)this + 56);
    v5 = (*(__int64 (__fastcall **)(LPVOID, char *, char *, _QWORD, _QWORD, int, _DWORD, char *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           (char *)this + 76,
           (char *)this + 108,
           0,
           0,
           1,
           *((_DWORD *)this + 32),
           (char *)this + 56);
    if ( v5 >= 0 )
    {
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 24LL))(*v6);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 104LL))(*((_QWORD *)this + 6));
        if ( v5 >= 0 )
        {
          v5 = ((__int64 (__fastcall *)(_QWORD **))(*v4)[6])(v4);
          if ( v5 >= 0 )
          {
            v2 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 36), 8u));
            v29 = v2;
            v7 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 45), 8u));
            v3 = v7;
            if ( v2 && v7 )
            {
              v28 = 0;
              while ( 1 )
              {
LABEL_13:
                if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 6) + 112LL))(
                       *((_QWORD *)this + 6),
                       &v26) < 0 )
                {
                  (*(void (__fastcall **)(_QWORD *))(*v4[6] + 96LL))(v4[6]);
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 96LL))(*v6);
                  v5 = 0;
                  ((void (__fastcall *)(_QWORD **))(*v4)[7])(v4);
                  if ( v28 )
                    v5 = -2147023596;
                  goto LABEL_70;
                }
                for ( i = 0; (unsigned int)i < *((_DWORD *)this + 36); i = (unsigned int)(i + 1) )
                {
                  v9 = 0;
                  v10 = *((_DWORD *)this + 50);
                  if ( v10 )
                  {
                    v11 = *((_QWORD *)this + 23);
                    do
                    {
                      if ( *(_DWORD *)(v11 + 8 * v9 + 4) == *(_DWORD *)(*((_QWORD *)this + 17) + 4 * i)
                        && *(_DWORD *)(v11 + 8 * v9) == 1 )
                      {
                        break;
                      }
                      v9 = (unsigned int)(v9 + 1);
                    }
                    while ( (unsigned int)v9 < v10 );
                  }
                  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 6) + 152LL))(
                         *((_QWORD *)this + 6),
                         v9,
                         0,
                         0,
                         0,
                         (__int64)v2 + 8 * i);
                  if ( v5 < 0 )
                    goto LABEL_70;
                }
                v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, void *))(*v4[6] + 56LL))(v4[6], 0, v2);
                v5 = v12;
                if ( v12 == -2146367487 )
                {
                  v5 = -2146367479;
                  goto LABEL_70;
                }
                if ( v12 < 0 )
                  goto LABEL_70;
                ((void (__fastcall *)(_QWORD **, _QWORD))(*v4)[9])(v4, v26);
                if ( v26 == 1 )
                  break;
                if ( v26 - 2 <= 1 )
                {
                  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 44); j = (unsigned int)(j + 1) )
                  {
                    v5 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, __int64))(*v4[6] + 64LL))(
                           v4[6],
                           *(unsigned int *)(*((_QWORD *)this + 21) + 4 * j),
                           0,
                           0,
                           (__int64)v3 + 8 * j);
                    if ( v5 < 0 )
                      goto LABEL_70;
                  }
                  ((void (__fastcall *)(_QWORD **, void *))(*v4)[8])(v4, v3);
                  v5 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, void *))(*v4[8] + 56LL))(v4[8], 0, v3);
                  if ( v5 < 0 )
                    goto LABEL_70;
                  if ( v26 == 3 )
                  {
                    v5 = ((__int64 (__fastcall *)(_QWORD **))(*v4)[11])(v4);
                    if ( v5 < 0 )
                      goto LABEL_70;
                    v14 = *(__int64 (**)(void))(*(_QWORD *)*v6 + 136LL);
                  }
                  else
                  {
                    v5 = (*(__int64 (__fastcall **)(_QWORD *))(*v4[8] + 128LL))(v4[8]);
                    if ( v5 < 0 )
                      goto LABEL_70;
                    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 128LL))(*((_QWORD *)this + 5));
                    if ( v5 < 0 )
                      goto LABEL_70;
                    for ( k = 0; (unsigned int)k < *((_DWORD *)this + 50); k = (unsigned int)(k + 1) )
                    {
                      v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 6) + 152LL))(
                             *((_QWORD *)this + 6),
                             (unsigned int)k,
                             &v27,
                             0,
                             0,
                             &v24);
                      if ( v5 < 0 )
                        goto LABEL_70;
                      if ( v27 == 2 )
                      {
                        v16 = *((_QWORD *)this + 23);
                        v17 = *(_DWORD *)(v16 + 8 * k) ? *((_QWORD *)this + 5) : *v6;
                        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v17 + 160LL))(
                               v17,
                               *(unsigned int *)(v16 + 8 * k + 4),
                               0,
                               v24);
                        if ( v5 < 0 )
                          goto LABEL_70;
                      }
                    }
                    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 144LL))(*v6);
                    if ( v5 < 0 )
                      goto LABEL_70;
                    v14 = *(__int64 (**)(void))(**((_QWORD **)this + 5) + 144LL);
                  }
                  v5 = v14();
                  if ( v5 < 0 )
                    goto LABEL_70;
                  ((void (__fastcall *)(_QWORD **, _QWORD))(*v4)[10])(v4, v26);
                }
              }
              v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 120LL))(*v6);
              if ( v5 >= 0 )
              {
                for ( m = 0; (unsigned int)m < *((_DWORD *)this + 50); m = (unsigned int)(m + 1) )
                {
                  if ( !*(_DWORD *)(*((_QWORD *)this + 23) + 8 * m) )
                  {
                    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 6) + 152LL))(
                           *((_QWORD *)this + 6),
                           (unsigned int)m,
                           0,
                           0,
                           0,
                           &v24);
                    if ( v5 < 0 )
                      goto LABEL_69;
                    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v6 + 160LL))(
                           *v6,
                           *(unsigned int *)(*((_QWORD *)this + 23) + 8 * m + 4),
                           0,
                           v24);
                    if ( v5 < 0 )
                      goto LABEL_69;
                  }
                }
                v19 = ((__int64 (__fastcall *)(_QWORD **, _QWORD))(*v4)[10])(v4, v26);
                v5 = v19;
                if ( v19 >= 0 )
                {
                  v20 = *v6;
                  if ( v19 == 1 )
                  {
                    v25[0] = 0;
                    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 144LL))(v20);
                    if ( v5 >= 0 )
                    {
                      v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v6)(
                             *v6,
                             &IID_ISimpleTableControl,
                             v25);
                      if ( v5 >= 0 )
                      {
                        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v25[0] + 64LL))(v25[0], 0);
                        if ( v5 >= 0 )
                        {
                          v28 = 1;
                          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 16LL))(v25[0]);
LABEL_64:
                          v2 = v29;
                          goto LABEL_13;
                        }
                      }
                    }
                  }
                  else
                  {
                    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 144LL))(v20);
                    if ( v5 >= 0 )
                      goto LABEL_64;
                  }
                }
LABEL_69:
                v2 = v29;
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
        }
      }
    }
  }
LABEL_70:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  v21 = *((_QWORD *)this + 7);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *((_QWORD *)this + 7) = 0;
  }
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021020  push    rbp
0x180021022  push    rbx
0x180021023  push    rsi
0x180021024  push    rdi
0x180021025  push    r12
0x180021027  push    r13
0x180021029  push    r14
0x18002102b  push    r15
0x18002102d  mov     rbp, rsp
0x180021030  sub     rsp, 78h
0x180021034  mov     rdi, rcx
0x180021037  xor     ebx, ebx
0x180021039  mov     [rbp+arg_0], ebx
0x18002103c  mov     [rbp+arg_8], ebx
0x18002103f  mov     [rbp+var_20], rbx
0x180021043  mov     [rbp+var_28], rbx
0x180021047  mov     r15d, ebx
0x18002104a  mov     r13d, ebx
0x18002104d  lea     rsi, [rcx-8]
0x180021051  lea     r14d, [rbx+1]
0x180021055  cmp     [rsi+30h], rbx
0x180021059  jnz     short loc_180021074
0x18002105b  mov     [rcx+84h], r14d
0x180021062  mov     rax, [rcx]
0x180021065  mov     rax, [rax+18h]
0x180021069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002106e  mov     [rdi+84h], ebx
0x180021074  lea     rax, [rbp+var_28]
0x180021078  mov     [rsp+78h+ppv], rax; ppv
0x18002107d  lea     r9, IID_ISimpleTableDispenser; riid
0x180021084  mov     r8d, r14d; dwClsContext
0x180021087  xor     edx, edx; pUnkOuter
0x180021089  lea     rcx, clsidSTDISP; rclsid
0x180021090  call    cs:__imp_CoCreateInstance
0x180021096  mov     ebx, eax
0x180021098  test    eax, eax
0x18002109a  js      loc_180021610
0x1800210a0  lea     r12, [rdi+38h]
0x1800210a4  mov     rcx, [rbp+var_28]
0x1800210a8  mov     rax, [rcx]
0x1800210ab  lea     r8, [rdi+6Ch]
0x1800210af  lea     rdx, [rdi+4Ch]
0x1800210b3  mov     r10, [rax+18h]
0x1800210b7  mov     [rsp+78h+var_40], r12
0x1800210bc  mov     eax, [rdi+80h]
0x1800210c2  mov     [rsp+78h+var_48], eax
0x1800210c6  mov     dword ptr [rsp+78h+var_50], r14d
0x1800210cb  mov     [rsp+78h+ppv], r13
0x1800210d0  xor     r9d, r9d
0x1800210d3  mov     rax, r10
0x1800210d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210db  mov     ebx, eax
0x1800210dd  test    eax, eax
0x1800210df  js      loc_180021610
0x1800210e5  mov     rcx, [rbp+var_28]
0x1800210e9  test    rcx, rcx
0x1800210ec  jz      short loc_1800210FE
0x1800210ee  mov     rax, [rcx]
0x1800210f1  mov     rax, [rax+10h]
0x1800210f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210fa  mov     [rbp+var_28], r13
0x1800210fe  mov     rcx, [r12]
0x180021102  mov     rax, [rcx]
0x180021105  mov     rax, [rax+18h]
0x180021109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002110e  mov     ebx, eax
0x180021110  test    eax, eax
0x180021112  js      loc_180021610
0x180021118  mov     rcx, [rdi+30h]
0x18002111c  mov     rax, [rcx]
0x18002111f  mov     rax, [rax+68h]
0x180021123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021128  mov     ebx, eax
0x18002112a  test    eax, eax
0x18002112c  js      loc_180021610
0x180021132  mov     rax, [rsi]
0x180021135  mov     rcx, rsi
0x180021138  mov     rax, [rax+30h]
0x18002113c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021141  mov     ebx, eax
0x180021143  test    eax, eax
0x180021145  js      loc_180021610
0x18002114b  mov     ecx, [rdi+90h]
0x180021151  mov     ebx, 8
0x180021156  mov     eax, ebx
0x180021158  mul     rcx
0x18002115b  lea     r14, [rbx-9]
0x18002115f  cmovb   rax, r14
0x180021163  mov     rcx, rax; cb
0x180021166  call    cs:__imp_CoTaskMemAlloc
0x18002116c  mov     r15, rax
0x18002116f  mov     [rbp+arg_18], rax
0x180021173  mov     ecx, [rdi+0B4h]
0x180021179  mov     eax, ebx
0x18002117b  mul     rcx
0x18002117e  cmovb   rax, r14
0x180021182  mov     rcx, rax; cb
0x180021185  call    cs:__imp_CoTaskMemAlloc
0x18002118b  mov     r13, rax
0x18002118e  test    r15, r15
0x180021191  jz      loc_180021605
0x180021197  test    rax, rax
0x18002119a  jz      loc_180021605
0x1800211a0  mov     [rbp+arg_10], 0
0x1800211a7  mov     rcx, [rdi+30h]
0x1800211ab  mov     rax, [rcx]
0x1800211ae  lea     rdx, [rbp+arg_0]
0x1800211b2  mov     rax, [rax+70h]
0x1800211b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211bb  test    eax, eax
0x1800211bd  js      loc_1800215C8
0x1800211c3  xor     r14d, r14d
0x1800211c6  cmp     r14d, [rdi+90h]
0x1800211cd  jnb     short loc_18002123D
0x1800211cf  xor     edx, edx
0x1800211d1  mov     r8d, [rdi+0C8h]
0x1800211d8  test    r8d, r8d
0x1800211db  jz      short loc_180021203
0x1800211dd  mov     rax, [rdi+88h]
0x1800211e4  mov     r9d, [rax+r14*4]
0x1800211e8  mov     rcx, [rdi+0B8h]
0x1800211ef  cmp     [rcx+rdx*8+4], r9d
0x1800211f4  jnz     short loc_1800211FC
0x1800211f6  cmp     dword ptr [rcx+rdx*8], 1
0x1800211fa  jz      short loc_180021203
0x1800211fc  inc     edx
0x1800211fe  cmp     edx, r8d
0x180021201  jb      short loc_1800211EF
0x180021203  mov     rcx, [rdi+30h]
0x180021207  mov     r8, [rcx]
0x18002120a  lea     r9, [r15+r14*8]
0x18002120e  mov     rax, [r8+98h]
0x180021215  mov     [rsp+78h+var_50], r9
0x18002121a  mov     [rsp+78h+ppv], 0
0x180021223  xor     r9d, r9d
0x180021226  xor     r8d, r8d
0x180021229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002122e  mov     ebx, eax
0x180021230  test    eax, eax
0x180021232  js      loc_180021610
0x180021238  inc     r14d
0x18002123b  jmp     short loc_1800211C6
0x18002123d  mov     rcx, [rsi+30h]
0x180021241  mov     rax, [rcx]
0x180021244  mov     r8, r15
0x180021247  xor     edx, edx
0x180021249  mov     rax, [rax+38h]
0x18002124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021252  mov     ebx, eax
0x180021254  cmp     eax, 80110801h
0x180021259  jz      loc_1800215C1
0x18002125f  test    eax, eax
0x180021261  js      loc_180021610
0x180021267  mov     rax, [rsi]
0x18002126a  mov     edx, [rbp+arg_0]
0x18002126d  mov     rcx, rsi
0x180021270  mov     rax, [rax+48h]
0x180021274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021279  mov     eax, [rbp+arg_0]
0x18002127c  sub     eax, 1
0x18002127f  jz      loc_180021460
0x180021285  sub     eax, 1
0x180021288  jz      short loc_180021293
0x18002128a  cmp     eax, 1
0x18002128d  jnz     loc_1800211A7
0x180021293  xor     r14d, r14d
0x180021296  cmp     r14d, [rdi+0B0h]
0x18002129d  jnb     short loc_1800212DF
0x18002129f  mov     rcx, [rsi+30h]
0x1800212a3  mov     rax, [rcx]
0x1800212a6  lea     r8, ds:0[r14*8]
0x1800212ae  add     r8, r13
0x1800212b1  mov     rdx, [rdi+0A8h]
0x1800212b8  mov     [rsp+78h+ppv], r8
0x1800212bd  xor     r9d, r9d
0x1800212c0  xor     r8d, r8d
0x1800212c3  mov     edx, [rdx+r14*4]
0x1800212c7  mov     rax, [rax+40h]
0x1800212cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212d0  mov     ebx, eax
0x1800212d2  test    eax, eax
0x1800212d4  js      loc_180021610
0x1800212da  inc     r14d
0x1800212dd  jmp     short loc_180021296
0x1800212df  mov     rax, [rsi]
0x1800212e2  mov     rdx, r13
0x1800212e5  mov     rcx, rsi
0x1800212e8  mov     rax, [rax+40h]
0x1800212ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212f1  mov     rcx, [rsi+40h]
0x1800212f5  mov     rax, [rcx]
0x1800212f8  mov     r8, r13
0x1800212fb  xor     edx, edx
0x1800212fd  mov     rax, [rax+38h]
0x180021301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021306  mov     ebx, eax
0x180021308  test    eax, eax
0x18002130a  js      loc_180021610
0x180021310  cmp     [rbp+arg_0], 3
0x180021314  jnz     short loc_180021342
0x180021316  mov     rax, [rsi]
0x180021319  mov     rcx, rsi
0x18002131c  mov     rax, [rax+58h]
0x180021320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021325  mov     ebx, eax
0x180021327  test    eax, eax
0x180021329  js      loc_180021610
0x18002132f  mov     rcx, [r12]
0x180021333  mov     rax, [rcx]
0x180021336  mov     rax, [rax+88h]
0x18002133d  jmp     loc_18002143A
0x180021342  mov     rcx, [rsi+40h]
0x180021346  mov     rax, [rcx]
0x180021349  mov     rax, [rax+80h]
0x180021350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021355  mov     ebx, eax
0x180021357  test    eax, eax
0x180021359  js      loc_180021610
0x18002135f  mov     rcx, [rdi+28h]
0x180021363  mov     rax, [rcx]
0x180021366  mov     rax, [rax+80h]
0x18002136d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021372  mov     ebx, eax
0x180021374  test    eax, eax
0x180021376  js      loc_180021610
0x18002137c  xor     r14d, r14d
0x18002137f  cmp     r14d, [rdi+0C8h]
0x180021386  jnb     loc_18002140F
0x18002138c  mov     rcx, [rdi+30h]
0x180021390  mov     rax, [rcx]
0x180021393  lea     rdx, [rbp+var_20]
0x180021397  mov     [rsp+78h+var_50], rdx
0x18002139c  mov     [rsp+78h+ppv], 0
0x1800213a5  xor     r9d, r9d
0x1800213a8  lea     r8, [rbp+arg_8]
0x1800213ac  mov     edx, r14d
0x1800213af  mov     rax, [rax+98h]
0x1800213b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213bb  mov     ebx, eax
0x1800213bd  test    eax, eax
0x1800213bf  js      loc_180021610
0x1800213c5  cmp     [rbp+arg_8], 2
0x1800213c9  jnz     short loc_180021407
0x1800213cb  mov     r10, [rdi+0B8h]
0x1800213d2  mov     r9, [rbp+var_20]
0x1800213d6  xor     r8d, r8d
0x1800213d9  mov     edx, [r10+r14*8+4]
0x1800213de  cmp     [r10+r14*8], r8d
0x1800213e2  jz      short loc_1800213EA
0x1800213e4  mov     rcx, [rdi+28h]
0x1800213e8  jmp     short loc_1800213EE
0x1800213ea  mov     rcx, [r12]
0x1800213ee  mov     rax, [rcx]
0x1800213f1  mov     rax, [rax+0A0h]
0x1800213f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213fd  test    eax, eax
0x1800213ff  mov     ebx, eax
0x180021401  js      loc_180021610
0x180021407  inc     r14d
0x18002140a  jmp     loc_18002137F
0x18002140f  mov     rcx, [r12]
0x180021413  mov     rax, [rcx]
0x180021416  mov     rax, [rax+90h]
0x18002141d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021422  mov     ebx, eax
0x180021424  test    eax, eax
0x180021426  js      loc_180021610
0x18002142c  mov     rcx, [rdi+28h]
0x180021430  mov     rax, [rcx]
0x180021433  mov     rax, [rax+90h]
0x18002143a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002143f  test    eax, eax
0x180021441  mov     ebx, eax
0x180021443  js      loc_180021610
0x180021449  mov     rax, [rsi]
0x18002144c  mov     edx, [rbp+arg_0]
0x18002144f  mov     rcx, rsi
0x180021452  mov     rax, [rax+50h]
0x180021456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002145b  jmp     loc_1800211A7
0x180021460  mov     rcx, [r12]
0x180021464  mov     rax, [rcx]
0x180021467  mov     rax, [rax+78h]
0x18002146b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021470  mov     ebx, eax
0x180021472  test    eax, eax
0x180021474  js      loc_180021610
0x18002147a  xor     r14d, r14d
0x18002147d  cmp     r14d, [rdi+0C8h]
0x180021484  jnb     short loc_180021504
0x180021486  mov     rax, [rdi+0B8h]
0x18002148d  cmp     dword ptr [rax+r14*8], 0
0x180021492  jnz     short loc_1800214FC
0x180021494  mov     rcx, [rdi+30h]
0x180021498  mov     rax, [rcx]
0x18002149b  lea     rdx, [rbp+var_20]
0x18002149f  mov     [rsp+78h+var_50], rdx
0x1800214a4  mov     [rsp+78h+ppv], 0
0x1800214ad  xor     r9d, r9d
0x1800214b0  xor     r8d, r8d
  ... truncated ...
```
