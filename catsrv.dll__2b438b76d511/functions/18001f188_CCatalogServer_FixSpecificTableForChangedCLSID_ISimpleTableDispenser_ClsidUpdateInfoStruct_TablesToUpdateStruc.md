# CCatalogServer::FixSpecificTableForChangedCLSID(ISimpleTableDispenser *,ClsidUpdateInfoStruct *,TablesToUpdateStruct const *)

- ea: `0x18001f188`
- end: `0x18001f5c8`
- name: `?FixSpecificTableForChangedCLSID@CCatalogServer@@AEAAJPEAUISimpleTableDispenser@@PEAUClsidUpdateInfoStruct@@PEBUTablesToUpdateStruct@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, struct ISimpleTableDispenser *, struct ClsidUpdateInfoStruct *, const struct TablesToUpdateStruct *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180020ec0`

## callees

- `0x18001f188`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f3b7`

## pseudocode

```c
__int64 __fastcall CCatalogServer::FixSpecificTableForChangedCLSID(
        CCatalogServer *this,
        struct ISimpleTableDispenser *a2,
        struct ClsidUpdateInfoStruct *a3,
        const struct TablesToUpdateStruct *a4)
{
  _DWORD *v4; // r14
  unsigned int *v6; // r12
  _QWORD *v7; // r15
  int v9; // eax
  __int64 v11; // rdx
  int v12; // r8d
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rcx
  int v16; // ebx
  int i; // edi
  int v18; // ecx
  int v19; // ecx
  unsigned __int64 v20; // rax
  unsigned int v21; // ebx
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 j; // rdi
  __int64 v25; // rax
  __int64 k; // rdi
  __int64 v27; // r8
  __int64 (*v28)(void); // rax
  __int64 *v30; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-51h] BYREF
  struct ClsidUpdateInfoStruct *v32; // [rsp+60h] [rbp-49h] BYREF
  int v33; // [rsp+68h] [rbp-41h]
  int v34; // [rsp+6Ch] [rbp-3Dh]
  int v35; // [rsp+70h] [rbp-39h]
  int v36; // [rsp+74h] [rbp-35h]
  char *v37; // [rsp+78h] [rbp-31h]
  int v38; // [rsp+80h] [rbp-29h]
  int v39; // [rsp+84h] [rbp-25h]
  int v40; // [rsp+88h] [rbp-21h]
  int v41; // [rsp+8Ch] [rbp-1Dh]

  v4 = 0;
  v32 = a3;
  v6 = 0;
  v7 = 0;
  v30 = 0;
  v33 = 0;
  v34 = *((_DWORD *)a4 + 2);
  v9 = *((_DWORD *)a4 + 3);
  v35 = 72;
  v36 = 16;
  v11 = 1;
  if ( v9 != -1 )
  {
    v39 = v9;
    v37 = (char *)a3 + 32;
    v38 = 0;
    v40 = 72;
    v41 = 16;
    v11 = 2;
  }
  v12 = *((_DWORD *)a4 + 4);
  if ( v12 != -1 )
  {
    v13 = 3 * v11;
    v11 = (unsigned int)(v11 + 1);
    *(&v33 + 2 * v13) = 0;
    *(&v35 + 2 * v13) = 72;
    *(&v36 + 2 * v13) = 16;
    *(&v34 + 2 * v13) = v12;
    *(&v32 + v13) = (struct ClsidUpdateInfoStruct *)((char *)a3 + 48);
  }
  v14 = *((_DWORD *)a4 + 5);
  if ( v14 != -1 )
  {
    v15 = 3 * v11;
    v11 = (unsigned int)(v11 + 1);
    *(&v33 + 2 * v15) = 0;
    *(&v35 + 2 * v15) = 19;
    *(&v36 + 2 * v15) = 4;
    *(&v34 + 2 * v15) = v14;
    *(&v32 + v15) = (struct ClsidUpdateInfoStruct *)((char *)a3 + 64);
  }
  v16 = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, _QWORD, struct ClsidUpdateInfoStruct **, __int64, int, _DWORD, __int64 **))(*(_QWORD *)a2 + 24LL))(
          a2,
          didCOMSERVICES,
          *(_QWORD *)a4,
          &v32,
          v11,
          1,
          0,
          &v30);
  if ( v16 >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 24))(v30);
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 32))(v30);
      if ( v16 >= 0 )
      {
        for ( i = 0; ; i = 1 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 40))(v30);
          if ( v16 < 0 )
          {
            if ( v16 == -2146367487 )
            {
              v16 = 0;
              if ( i )
                v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 96))(v30);
            }
            break;
          }
          v18 = *((_DWORD *)a4 + 6);
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              if ( v19 != 1 )
                continue;
              v31 = 0;
              v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*v30 + 72))(
                      v30,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      &v31);
              if ( v16 < 0 )
                break;
              if ( !v4 )
              {
                v20 = 4LL * v31;
                if ( v20 > 0xFFFFFFFF
                  || (v21 = 4 * v31,
                      v4 = CoTaskMemAlloc((unsigned int)v20),
                      v6 = (unsigned int *)CoTaskMemAlloc(v21),
                      v22 = 8LL * v31,
                      v22 > 0xFFFFFFFF) )
                {
                  v16 = -2147024362;
                  break;
                }
                v23 = CoTaskMemAlloc((unsigned int)v22);
                v7 = v23;
                if ( !v4 || !v6 || !v23 )
                {
                  v16 = -2147024882;
                  break;
                }
              }
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                v25 = *v30;
                if ( (unsigned int)j >= v31 )
                  break;
                v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _DWORD *, unsigned int *, _QWORD *))(v25 + 64))(
                        v30,
                        (unsigned int)j,
                        &v4[j],
                        &v6[j],
                        &v7[j]);
                if ( v16 < 0 )
                  goto LABEL_48;
              }
              v16 = (*(__int64 (**)(void))(v25 + 136))();
              if ( v16 < 0 )
                break;
              v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 120))(v30);
              if ( v16 < 0 )
                break;
              v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, char *))(*v30 + 160))(
                      v30,
                      *((unsigned int *)a4 + 2),
                      0,
                      (char *)a3 + 16);
              if ( v16 < 0 )
                break;
              for ( k = 0; (unsigned int)k < v31; k = (unsigned int)(k + 1) )
              {
                if ( (_DWORD)k != *((_DWORD *)a4 + 2) )
                {
                  v27 = v4[k] == 128 ? v6[k] : 0LL;
                  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(*v30 + 160))(
                          v30,
                          (unsigned int)k,
                          v27,
                          v7[k]);
                  if ( v16 < 0 )
                    goto LABEL_48;
                }
              }
            }
            else
            {
              v16 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 128))(v30);
              if ( v16 < 0 )
                break;
              v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, char *))(*v30 + 160))(
                      v30,
                      *((unsigned int *)a4 + 2),
                      0,
                      (char *)a3 + 16);
              if ( v16 < 0 )
                break;
            }
            v28 = *(__int64 (**)(void))(*v30 + 144);
          }
          else
          {
            v28 = *(__int64 (**)(void))(*v30 + 136);
          }
          v16 = v28();
          if ( v16 < 0 )
            break;
        }
      }
    }
  }
LABEL_48:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    v30 = 0;
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001f188  mov     [rsp-8+arg_0], rbx
0x18001f18d  push    rbp
0x18001f18e  push    rsi
0x18001f18f  push    rdi
0x18001f190  push    r12
0x18001f192  push    r13
0x18001f194  push    r14
0x18001f196  push    r15
0x18001f198  lea     rbp, [rsp-27h]
0x18001f19d  sub     rsp, 0D0h
0x18001f1a4  mov     rax, cs:__security_cookie
0x18001f1ab  xor     rax, rsp
0x18001f1ae  mov     [rbp+57h+var_40], rax
0x18001f1b2  xor     r14d, r14d
0x18001f1b5  mov     [rbp+57h+var_A0], r8
0x18001f1b9  mov     rsi, r9
0x18001f1bc  xor     r12d, r12d
0x18001f1bf  xor     r15d, r15d
0x18001f1c2  mov     [rbp+57h+var_B0], r12
0x18001f1c6  mov     edi, 0FFFFFFFFh
0x18001f1cb  mov     [rbp+57h+var_98], r12d
0x18001f1cf  lea     r9d, [r14+48h]
0x18001f1d3  mov     r10, rdx
0x18001f1d6  mov     eax, [rsi+8]
0x18001f1d9  lea     r11d, [r14+10h]
0x18001f1dd  mov     [rbp+57h+var_94], eax
0x18001f1e0  lea     ebx, [r14+1]
0x18001f1e4  mov     eax, [rsi+0Ch]
0x18001f1e7  mov     r13, r8
0x18001f1ea  mov     [rbp+57h+var_90], r9d
0x18001f1ee  mov     [rbp+57h+var_8C], r11d
0x18001f1f2  mov     edx, ebx
0x18001f1f4  cmp     eax, edi
0x18001f1f6  jz      short loc_18001F214
0x18001f1f8  mov     [rbp+57h+var_7C], eax
0x18001f1fb  lea     rax, [r8+20h]
0x18001f1ff  mov     [rbp+57h+var_88], rax
0x18001f203  mov     [rbp+57h+var_80], r12d
0x18001f207  mov     [rbp+57h+var_78], r9d
0x18001f20b  mov     [rbp+57h+var_74], r11d
0x18001f20f  mov     edx, 2
0x18001f214  mov     r8d, [rsi+10h]
0x18001f218  cmp     r8d, edi
0x18001f21b  jz      short loc_18001F240
0x18001f21d  lea     rcx, [rdx+rdx*2]
0x18001f221  add     edx, ebx
0x18001f223  lea     rax, [r13+30h]
0x18001f227  mov     [rbp+rcx*8+57h+var_98], r12d
0x18001f22c  mov     [rbp+rcx*8+57h+var_90], r9d
0x18001f231  mov     [rbp+rcx*8+57h+var_8C], r11d
0x18001f236  mov     [rbp+rcx*8+57h+var_94], r8d
0x18001f23b  mov     [rbp+rcx*8+57h+var_A0], rax
0x18001f240  mov     r8d, [rsi+14h]
0x18001f244  cmp     r8d, edi
0x18001f247  jz      short loc_18001F272
0x18001f249  lea     rcx, [rdx+rdx*2]
0x18001f24d  add     edx, ebx
0x18001f24f  lea     rax, [r13+40h]
0x18001f253  mov     [rbp+rcx*8+57h+var_98], r12d
0x18001f258  mov     [rbp+rcx*8+57h+var_90], 13h
0x18001f260  mov     [rbp+rcx*8+57h+var_8C], 4
0x18001f268  mov     [rbp+rcx*8+57h+var_94], r8d
0x18001f26d  mov     [rbp+rcx*8+57h+var_A0], rax
0x18001f272  mov     rax, [r10]
0x18001f275  lea     rcx, [rbp+57h+var_B0]
0x18001f279  mov     r8, [rsi]
0x18001f27c  lea     r9, [rbp+57h+var_A0]
0x18001f280  mov     [rsp+100h+var_C8], rcx
0x18001f285  mov     rcx, r10
0x18001f288  mov     dword ptr [rsp+100h+var_D0], r12d
0x18001f28d  mov     rax, [rax+18h]
0x18001f291  mov     dword ptr [rsp+100h+var_D8], ebx
0x18001f295  mov     [rsp+100h+var_E0], rdx
0x18001f29a  lea     rdx, didCOMSERVICES
0x18001f2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a6  mov     ebx, eax
0x18001f2a8  test    eax, eax
0x18001f2aa  js      loc_18001F558
0x18001f2b0  mov     rcx, [rbp+57h+var_B0]
0x18001f2b4  mov     rax, [rcx]
0x18001f2b7  mov     rax, [rax+18h]
0x18001f2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2c0  mov     ebx, eax
0x18001f2c2  test    eax, eax
0x18001f2c4  js      loc_18001F558
0x18001f2ca  mov     rcx, [rbp+57h+var_B0]
0x18001f2ce  mov     rax, [rcx]
0x18001f2d1  mov     rax, [rax+20h]
0x18001f2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2da  mov     ebx, eax
0x18001f2dc  test    eax, eax
0x18001f2de  js      loc_18001F558
0x18001f2e4  xor     edi, edi
0x18001f2e6  mov     rcx, [rbp+57h+var_B0]
0x18001f2ea  mov     rax, [rcx]
0x18001f2ed  mov     rax, [rax+28h]
0x18001f2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2f6  mov     ebx, eax
0x18001f2f8  test    eax, eax
0x18001f2fa  js      loc_18001F538
0x18001f300  mov     ecx, [rsi+18h]
0x18001f303  test    ecx, ecx
0x18001f305  jz      loc_18001F507
0x18001f30b  sub     ecx, 1
0x18001f30e  jz      loc_18001F4B7
0x18001f314  cmp     ecx, 1
0x18001f317  jnz     loc_18001F520
0x18001f31d  mov     rcx, [rbp+57h+var_B0]
0x18001f321  lea     rdx, [rbp+57h+var_A8]
0x18001f325  mov     [rsp+100h+var_C0], rdx
0x18001f32a  xor     r9d, r9d
0x18001f32d  mov     [rsp+100h+var_C8], 0
0x18001f336  xor     r8d, r8d
0x18001f339  mov     [rbp+57h+var_A8], 0
0x18001f340  xor     edx, edx
0x18001f342  mov     rax, [rcx]
0x18001f345  mov     [rsp+100h+var_D0], 0
0x18001f34e  mov     [rsp+100h+var_D8], 0
0x18001f357  mov     [rsp+100h+var_E0], 0
0x18001f360  mov     rax, [rax+48h]
0x18001f364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f369  mov     ebx, eax
0x18001f36b  test    eax, eax
0x18001f36d  js      loc_18001F558
0x18001f373  test    r14, r14
0x18001f376  jnz     short loc_18001F3DB
0x18001f378  mov     eax, [rbp+57h+var_A8]
0x18001f37b  mov     edi, 0FFFFFFFFh
0x18001f380  shl     rax, 2
0x18001f384  cmp     rax, rdi
0x18001f387  ja      loc_18001F531
0x18001f38d  mov     ecx, eax; cb
0x18001f38f  mov     ebx, eax
0x18001f391  call    cs:__imp_CoTaskMemAlloc
0x18001f397  mov     ecx, ebx; cb
0x18001f399  mov     r14, rax
0x18001f39c  call    cs:__imp_CoTaskMemAlloc
0x18001f3a2  mov     ecx, [rbp+57h+var_A8]
0x18001f3a5  mov     r12, rax
0x18001f3a8  shl     rcx, 3
0x18001f3ac  cmp     rcx, rdi
0x18001f3af  ja      loc_18001F531
0x18001f3b5  mov     ecx, ecx; cb
0x18001f3b7  call    cs:__imp_CoTaskMemAlloc
0x18001f3bd  mov     r15, rax
0x18001f3c0  test    r14, r14
0x18001f3c3  jz      loc_18001F52A
0x18001f3c9  test    r12, r12
0x18001f3cc  jz      loc_18001F52A
0x18001f3d2  test    rax, rax
0x18001f3d5  jz      loc_18001F52A
0x18001f3db  xor     edi, edi
0x18001f3dd  mov     rcx, [rbp+57h+var_B0]
0x18001f3e1  mov     rax, [rcx]
0x18001f3e4  cmp     edi, [rbp+57h+var_A8]
0x18001f3e7  jnb     short loc_18001F413
0x18001f3e9  mov     rax, [rax+40h]
0x18001f3ed  lea     rdx, [r15+rdi*8]
0x18001f3f1  mov     [rsp+100h+var_E0], rdx
0x18001f3f6  lea     r9, [r12+rdi*4]
0x18001f3fa  mov     edx, edi
0x18001f3fc  lea     r8, [r14+rdi*4]
0x18001f400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f405  mov     ebx, eax
0x18001f407  test    eax, eax
0x18001f409  js      loc_18001F558
0x18001f40f  inc     edi
0x18001f411  jmp     short loc_18001F3DD
0x18001f413  mov     rax, [rax+88h]
0x18001f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f41f  mov     ebx, eax
0x18001f421  test    eax, eax
0x18001f423  js      loc_18001F558
0x18001f429  mov     rcx, [rbp+57h+var_B0]
0x18001f42d  mov     rax, [rcx]
0x18001f430  mov     rax, [rax+78h]
0x18001f434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f439  mov     ebx, eax
0x18001f43b  test    eax, eax
0x18001f43d  js      loc_18001F558
0x18001f443  mov     rcx, [rbp+57h+var_B0]
0x18001f447  lea     r9, [r13+10h]
0x18001f44b  mov     edx, [rsi+8]
0x18001f44e  xor     r8d, r8d
0x18001f451  mov     rax, [rcx]
0x18001f454  mov     rax, [rax+0A0h]
0x18001f45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f460  mov     ebx, eax
0x18001f462  test    eax, eax
0x18001f464  js      loc_18001F558
0x18001f46a  xor     edi, edi
0x18001f46c  cmp     edi, [rbp+57h+var_A8]
0x18001f46f  jnb     loc_18001F4F7
0x18001f475  cmp     edi, [rsi+8]
0x18001f478  jz      short loc_18001F4B3
0x18001f47a  cmp     dword ptr [r14+rdi*4], 80h
0x18001f482  mov     rcx, [rbp+57h+var_B0]
0x18001f486  mov     r9, [r15+rdi*8]
0x18001f48a  mov     rax, [rcx]
0x18001f48d  mov     r10, [rax+0A0h]
0x18001f494  jz      short loc_18001F49B
0x18001f496  xor     r8d, r8d
0x18001f499  jmp     short loc_18001F49F
0x18001f49b  mov     r8d, [r12+rdi*4]
0x18001f49f  mov     edx, edi
0x18001f4a1  mov     rax, r10
0x18001f4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a9  mov     ebx, eax
0x18001f4ab  test    eax, eax
0x18001f4ad  js      loc_18001F558
0x18001f4b3  inc     edi
0x18001f4b5  jmp     short loc_18001F46C
0x18001f4b7  mov     rcx, [rbp+57h+var_B0]
0x18001f4bb  mov     rax, [rcx]
0x18001f4be  mov     rax, [rax+80h]
0x18001f4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ca  mov     ebx, eax
0x18001f4cc  test    eax, eax
0x18001f4ce  js      loc_18001F558
0x18001f4d4  mov     rcx, [rbp+57h+var_B0]
0x18001f4d8  lea     r9, [r13+10h]
0x18001f4dc  mov     edx, [rsi+8]
0x18001f4df  xor     r8d, r8d
0x18001f4e2  mov     rax, [rcx]
0x18001f4e5  mov     rax, [rax+0A0h]
0x18001f4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f1  mov     ebx, eax
0x18001f4f3  test    eax, eax
0x18001f4f5  js      short loc_18001F558
0x18001f4f7  mov     rcx, [rbp+57h+var_B0]
0x18001f4fb  mov     rax, [rcx]
0x18001f4fe  mov     rax, [rax+90h]
0x18001f505  jmp     short loc_18001F515
0x18001f507  mov     rcx, [rbp+57h+var_B0]
0x18001f50b  mov     rax, [rcx]
0x18001f50e  mov     rax, [rax+88h]
0x18001f515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f51a  mov     ebx, eax
0x18001f51c  test    eax, eax
0x18001f51e  js      short loc_18001F558
0x18001f520  mov     edi, 1
0x18001f525  jmp     loc_18001F2E6
0x18001f52a  mov     ebx, 8007000Eh
0x18001f52f  jmp     short loc_18001F558
0x18001f531  mov     ebx, 80070216h
0x18001f536  jmp     short loc_18001F558
0x18001f538  cmp     ebx, 80110801h
0x18001f53e  jnz     short loc_18001F558
0x18001f540  xor     ebx, ebx
0x18001f542  test    edi, edi
0x18001f544  jz      short loc_18001F558
0x18001f546  mov     rcx, [rbp+57h+var_B0]
0x18001f54a  mov     rax, [rcx]
0x18001f54d  mov     rax, [rax+60h]
0x18001f551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f556  mov     ebx, eax
0x18001f558  mov     rcx, [rbp+57h+var_B0]
0x18001f55c  test    rcx, rcx
0x18001f55f  jz      short loc_18001F575
0x18001f561  mov     rax, [rcx]
0x18001f564  mov     rax, [rax+10h]
0x18001f568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f56d  mov     [rbp+57h+var_B0], 0
0x18001f575  test    r14, r14
0x18001f578  jz      short loc_18001F583
0x18001f57a  mov     rcx, r14; pv
0x18001f57d  call    cs:__imp_CoTaskMemFree
0x18001f583  test    r12, r12
0x18001f586  jz      short loc_18001F591
0x18001f588  mov     rcx, r12; pv
0x18001f58b  call    cs:__imp_CoTaskMemFree
0x18001f591  test    r15, r15
0x18001f594  jz      short loc_18001F59F
0x18001f596  mov     rcx, r15; pv
0x18001f599  call    cs:__imp_CoTaskMemFree
0x18001f59f  mov     eax, ebx
0x18001f5a1  mov     rcx, [rbp+57h+var_40]
0x18001f5a5  xor     rcx, rsp; StackCookie
0x18001f5a8  call    __security_check_cookie
0x18001f5ad  mov     rbx, [rsp+100h+arg_0]
0x18001f5b5  add     rsp, 0D0h
0x18001f5bc  pop     r15
0x18001f5be  pop     r14
0x18001f5c0  pop     r13
0x18001f5c2  pop     r12
0x18001f5c4  pop     rdi
0x18001f5c5  pop     rsi
0x18001f5c6  pop     rbp
0x18001f5c7  retn
```
