# CMVEngine::RetrieveKeys(ulong,std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> *)

- ea: `0x18001d924`
- end: `0x18001dee7`
- name: `?RetrieveKeys@CMVEngine@@AEAAJKPEAV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@Z`
- size: `1475`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015740`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x18000aef0`
- `0x18001d924`
- `0x180020450`
- `0x180021904`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001dac1`
- `msvcrt!_wcsicmp` at `0x18001dac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001deac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001deac`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMVEngine::RetrieveKeys(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  __int64 v6; // rax
  wchar_t **v7; // rsi
  wchar_t **v8; // r14
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r15d
  unsigned int v12; // r13d
  wchar_t *v13; // rax
  _QWORD *v14; // rdi
  unsigned int v15; // r15d
  __int64 j; // rbx
  __int64 v17; // rcx
  __int64 v18; // r13
  unsigned int m; // ebx
  _QWORD *v20; // rbx
  _QWORD *v21; // rdi
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdi
  __int64 v26; // rcx
  _QWORD *v27; // rdi
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // r8
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // r15
  __int64 kk; // rdi
  __int64 v37; // rcx
  _QWORD *v38; // rdi
  unsigned int v39; // esi
  unsigned int i; // ebx
  __int64 v41; // rcx
  _QWORD *v43; // rdi
  unsigned int v44; // esi
  __int64 jj; // rbx
  __int64 v46; // rcx
  _QWORD *v47; // rdi
  unsigned int v48; // esi
  __int64 ii; // rbx
  __int64 v50; // rcx
  _QWORD *v51; // rdi
  unsigned int v52; // esi
  __int64 n; // rbx
  __int64 v54; // rcx
  _QWORD *v55; // rdi
  unsigned int v56; // esi
  __int64 k; // rbx
  __int64 v58; // rcx
  int v59; // [rsp+20h] [rbp-79h]
  unsigned int v60; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+34h] [rbp-65h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-61h] BYREF
  int v63; // [rsp+48h] [rbp-51h]
  wchar_t *String2; // [rsp+50h] [rbp-49h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-41h] BYREF
  __int64 v66; // [rsp+60h] [rbp-39h]
  _BYTE v67[32]; // [rsp+70h] [rbp-29h] BYREF
  unsigned int *v68; // [rsp+90h] [rbp-9h]
  __int64 v69; // [rsp+98h] [rbp-1h]
  unsigned int *v70; // [rsp+A0h] [rbp+7h]
  __int64 v71; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = a2;
  v61 = a2;
  v5 = a1;
  v66 = a1;
  v6 = 0;
  v7 = *(wchar_t ***)(a1 + 56);
  v8 = *(wchar_t ***)(a1 + 64);
  while ( 1 )
  {
    v63 = v6;
    if ( v7 == v8 )
      return 0;
    v9 = 2 * v6;
    v10 = *(_QWORD *)(v5 + 48);
    if ( *(_DWORD *)(v10 + 8 * v9) )
    {
      *(_OWORD *)pv = 0;
      if ( *(_DWORD *)(v10 + 8 * v9 + 8) == 1 )
      {
        v11 = (*(__int64 (__fastcall **)(wchar_t *, _QWORD))(*(_QWORD *)*v7 + 48LL))(*v7, v4);
        if ( (v11 & 0x80000000) != 0 )
        {
          if ( (unsigned int)dword_18005A000 > 2 )
          {
            v61 = v11;
            v60 = v4;
            v70 = &v61;
            v71 = 4;
            v68 = &v60;
            v69 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &word_18004F20E, 0, 0, 4, v67);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B1,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)v11,
            v59);
          v38 = pv[0];
          if ( pv[0] )
          {
            v39 = (unsigned int)pv[1];
            for ( i = 0; i < v39; ++i )
            {
              v41 = v38[i];
              if ( v41 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                v38[i] = 0;
              }
            }
            CoTaskMemFree(v38);
          }
          return v11;
        }
        v12 = v4;
      }
      else
      {
        v12 = 0;
      }
      CMVEngine::UpdateSessionStateForContext(v5, 0);
      String2 = *v7;
      v13 = *(wchar_t **)(*(_QWORD *)String2 + 56LL);
      String1 = v13;
      v14 = pv[0];
      if ( pv[0] )
      {
        v15 = (unsigned int)pv[1];
        for ( j = 0; (unsigned int)j < v15; j = (unsigned int)(j + 1) )
        {
          v17 = v14[j];
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v14[j] = 0;
          }
        }
        CoTaskMemFree(v14);
        v13 = String1;
      }
      *(_OWORD *)pv = 0;
      v11 = ((__int64 (__fastcall *)(wchar_t *, LPVOID *, LPVOID *))v13)(String2, pv, &pv[1]);
      if ( (v11 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_18005A000 > 2 )
        {
          v61 = v11;
          v60 = v12;
          v70 = &v61;
          v71 = 4;
          v68 = &v60;
          v69 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F853, 0, 0, 4, v67);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C5,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
          (const char *)v11,
          v59);
        v55 = pv[0];
        if ( pv[0] )
        {
          v56 = (unsigned int)pv[1];
          for ( k = 0; (unsigned int)k < v56; k = (unsigned int)(k + 1) )
          {
            v58 = v55[k];
            if ( v58 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              v55[k] = 0;
            }
          }
          CoTaskMemFree(v55);
        }
        return v11;
      }
      v18 = 0;
      for ( m = (unsigned int)pv[1]; (unsigned int)v18 < LODWORD(pv[1]); m = (unsigned int)pv[1] )
      {
        if ( v63 )
        {
          v20 = *(_QWORD **)a3;
          v21 = *(_QWORD **)(a3 + 8);
          while ( v20 != v21 )
          {
            String1 = 0;
            String2 = 0;
            v22 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(*(_QWORD *)*v20 + 40LL))(*v20, &String1);
            v11 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D4,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                (const char *)(unsigned int)v22,
                v59);
              v51 = pv[0];
              if ( pv[0] )
              {
                v52 = (unsigned int)pv[1];
                for ( n = 0; (unsigned int)n < v52; n = (unsigned int)(n + 1) )
                {
                  v54 = v51[n];
                  if ( v54 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                    v51[n] = 0;
                  }
                }
                CoTaskMemFree(v51);
              }
              return v11;
            }
            v23 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)pv[0] + v18) + 40LL))(
                    *((_QWORD *)pv[0] + v18),
                    &String2);
            v11 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D5,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                (const char *)(unsigned int)v23,
                v59);
              v47 = pv[0];
              if ( pv[0] )
              {
                v48 = (unsigned int)pv[1];
                for ( ii = 0; (unsigned int)ii < v48; ii = (unsigned int)(ii + 1) )
                {
                  v50 = v47[ii];
                  if ( v50 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                    v47[ii] = 0;
                  }
                }
                CoTaskMemFree(v47);
              }
              return v11;
            }
            if ( !_wcsicmp(String1, String2) )
            {
              v60 = 0;
              v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v20 + 64LL))(*v20, &v60);
              v11 = v24;
              if ( v24 >= 0 )
              {
                if ( !v60 )
                {
                  v25 = *((_QWORD *)pv[0] + v18);
                  if ( *v20 != v25 )
                  {
                    if ( v25 )
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*((_QWORD *)pv[0] + v18));
                    v26 = *v20;
                    *v20 = v25;
                    if ( v26 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                  }
                }
                goto LABEL_42;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D9,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                (const char *)(unsigned int)v24,
                v59);
              v43 = pv[0];
              if ( pv[0] )
              {
                v44 = (unsigned int)pv[1];
                for ( jj = 0; (unsigned int)jj < v44; jj = (unsigned int)(jj + 1) )
                {
                  v46 = v43[jj];
                  if ( v46 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                    v43[jj] = 0;
                  }
                }
                CoTaskMemFree(v43);
              }
              return v11;
            }
            ++v20;
          }
        }
        v27 = pv[0];
        v28 = *(_QWORD *)(a3 + 16);
        v29 = *(_QWORD *)(a3 + 8);
        if ( v29 == v28 && !((v28 - v29) >> 3) )
        {
          v30 = (v29 - *(_QWORD *)a3) >> 3;
          if ( v30 == 0x1FFFFFFFFFFFFFFFLL )
            std::vector<ProvSource *>::_Xlen();
          v31 = v30 + 1;
          v32 = (v28 - *(_QWORD *)a3) >> 3;
          v33 = 0;
          if ( 0x1FFFFFFFFFFFFFFFLL - (v32 >> 1) >= v32 )
            v33 = v32 + (v32 >> 1);
          if ( v33 < v31 )
            v33 = v31;
          std::vector<Microsoft::WRL::ComPtr<IMVHandler>>::_Reallocate(a3, v33);
        }
        v34 = v27[v18];
        **(_QWORD **)(a3 + 8) = v34;
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
        *(_QWORD *)(a3 + 8) += 8LL;
LABEL_42:
        v18 = (unsigned int)(v18 + 1);
      }
      v35 = pv[0];
      if ( pv[0] )
      {
        for ( kk = 0; (unsigned int)kk < m; kk = (unsigned int)(kk + 1) )
        {
          v37 = v35[kk];
          if ( v37 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v35[kk] = 0;
          }
        }
        CoTaskMemFree(v35);
      }
      v5 = v66;
      v4 = v61;
    }
    ++v7;
    v6 = (unsigned int)(v63 + 1);
  }
}

```

## disassembly

```asm
0x18001d924  mov     [rsp-8+arg_18], rbx
0x18001d929  push    rbp
0x18001d92a  push    rsi
0x18001d92b  push    rdi
0x18001d92c  push    r12
0x18001d92e  push    r13
0x18001d930  push    r14
0x18001d932  push    r15
0x18001d934  lea     rbp, [rsp-27h]
0x18001d939  sub     rsp, 0C0h
0x18001d940  mov     rax, cs:__security_cookie
0x18001d947  xor     rax, rsp
0x18001d94a  mov     [rbp+57h+var_40], rax
0x18001d94e  mov     r12, r8
0x18001d951  mov     edi, edx
0x18001d953  mov     [rbp+57h+var_BC], edx
0x18001d956  mov     rbx, rcx
0x18001d959  mov     [rbp+57h+var_90], rcx
0x18001d95d  xor     eax, eax
0x18001d95f  mov     rsi, [rcx+38h]
0x18001d963  mov     r14, [rcx+40h]
0x18001d967  mov     [rbp+57h+var_A8], eax
0x18001d96a  cmp     rsi, r14
0x18001d96d  jz      loc_18001DEB8
0x18001d973  add     rax, rax
0x18001d976  mov     rcx, [rbx+30h]
0x18001d97a  cmp     dword ptr [rcx+rax*8], 0
0x18001d97e  jz      loc_18001DC2E
0x18001d984  xorps   xmm0, xmm0
0x18001d987  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18001d98b  cmp     dword ptr [rcx+rax*8+8], 1
0x18001d990  jnz     short loc_18001D9B6
0x18001d992  mov     rcx, [rsi]
0x18001d995  mov     rax, [rcx]
0x18001d998  mov     edx, edi
0x18001d99a  mov     rax, [rax+30h]
0x18001d99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a3  mov     r15d, eax
0x18001d9a6  xor     r13d, r13d
0x18001d9a9  test    eax, eax
0x18001d9ab  js      loc_18001DC3C
0x18001d9b1  mov     r13d, edi
0x18001d9b4  jmp     short loc_18001D9B9
0x18001d9b6  xor     r13d, r13d
0x18001d9b9  xor     edx, edx
0x18001d9bb  mov     rcx, rbx
0x18001d9be  call    ?UpdateSessionStateForContext@CMVEngine@@AEAAXW4ProvisioningResult@@@Z; CMVEngine::UpdateSessionStateForContext(ProvisioningResult)
0x18001d9c3  mov     rax, [rsi]
0x18001d9c6  mov     [rbp+57h+String2], rax
0x18001d9ca  mov     rax, [rax]
0x18001d9cd  mov     rax, [rax+38h]
0x18001d9d1  mov     [rbp+57h+String1], rax
0x18001d9d5  mov     rdi, [rbp+57h+pv]
0x18001d9d9  test    rdi, rdi
0x18001d9dc  jz      short loc_18001DA1A
0x18001d9de  mov     r15d, dword ptr [rbp+57h+pv+8]
0x18001d9e2  xor     ebx, ebx
0x18001d9e4  test    r15d, r15d
0x18001d9e7  jz      short loc_18001DA0D
0x18001d9e9  mov     rcx, [rdi+rbx*8]
0x18001d9ed  test    rcx, rcx
0x18001d9f0  jz      short loc_18001DA06
0x18001d9f2  mov     rax, [rcx]
0x18001d9f5  mov     rax, [rax+10h]
0x18001d9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9fe  mov     qword ptr [rdi+rbx*8], 0
0x18001da06  inc     ebx
0x18001da08  cmp     ebx, r15d
0x18001da0b  jb      short loc_18001D9E9
0x18001da0d  mov     rcx, rdi; pv
0x18001da10  call    cs:__imp_CoTaskMemFree
0x18001da16  mov     rax, [rbp+57h+String1]
0x18001da1a  xorps   xmm0, xmm0
0x18001da1d  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18001da21  lea     r8, [rbp+57h+pv+8]
0x18001da25  lea     rdx, [rbp+57h+pv]
0x18001da29  mov     rcx, [rbp+57h+String2]
0x18001da2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da32  mov     r15d, eax
0x18001da35  test    eax, eax
0x18001da37  js      loc_18001DE05
0x18001da3d  xor     r13d, r13d
0x18001da40  mov     rbx, [rbp+57h+pv+8]
0x18001da44  test    ebx, ebx
0x18001da46  jz      loc_18001DBEB
0x18001da4c  cmp     [rbp+57h+var_A8], 0
0x18001da50  jbe     loc_18001DB43
0x18001da56  mov     rbx, [r12]
0x18001da5a  mov     rdi, [r12+8]
0x18001da5f  cmp     rbx, rdi
0x18001da62  jz      loc_18001DB43
0x18001da68  mov     [rbp+57h+String1], 0
0x18001da70  mov     [rbp+57h+String2], 0
0x18001da78  mov     rcx, [rbx]
0x18001da7b  mov     rax, [rcx]
0x18001da7e  lea     rdx, [rbp+57h+String1]
0x18001da82  mov     rax, [rax+28h]
0x18001da86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da8b  mov     r15d, eax
0x18001da8e  test    eax, eax
0x18001da90  js      loc_18001DDA8
0x18001da96  mov     rax, [rbp+57h+pv]
0x18001da9a  mov     rcx, [rax+r13*8]
0x18001da9e  mov     rax, [rcx]
0x18001daa1  lea     rdx, [rbp+57h+String2]
0x18001daa5  mov     rax, [rax+28h]
0x18001daa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daae  mov     r15d, eax
0x18001dab1  test    eax, eax
0x18001dab3  js      loc_18001DD4B
0x18001dab9  mov     rdx, [rbp+57h+String2]; String2
0x18001dabd  mov     rcx, [rbp+57h+String1]; String1
0x18001dac1  call    cs:__imp__wcsicmp
0x18001dac7  test    eax, eax
0x18001dac9  jz      short loc_18001DAD1
0x18001dacb  add     rbx, 8
0x18001dacf  jmp     short loc_18001DA5F
0x18001dad1  mov     [rbp+57h+var_C0], 0
0x18001dad8  mov     rcx, [rbx]
0x18001dadb  mov     rax, [rcx]
0x18001dade  lea     rdx, [rbp+57h+var_C0]
0x18001dae2  mov     rax, [rax+40h]
0x18001dae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daeb  mov     r15d, eax
0x18001daee  test    eax, eax
0x18001daf0  js      loc_18001DCF1
0x18001daf6  cmp     [rbp+57h+var_C0], 0
0x18001dafa  jnz     loc_18001DBDB
0x18001db00  mov     rax, [rbp+57h+pv]
0x18001db04  mov     rdi, [rax+r13*8]
0x18001db08  cmp     [rbx], rdi
0x18001db0b  jz      loc_18001DBDB
0x18001db11  test    rdi, rdi
0x18001db14  jz      short loc_18001DB26
0x18001db16  mov     rax, [rdi]
0x18001db19  mov     rcx, rdi
0x18001db1c  mov     rax, [rax+8]
0x18001db20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db25  nop
0x18001db26  mov     rcx, [rbx]
0x18001db29  mov     [rbx], rdi
0x18001db2c  test    rcx, rcx
0x18001db2f  jz      short loc_18001DB3E
0x18001db31  mov     rax, [rcx]
0x18001db34  mov     rax, [rax+10h]
0x18001db38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db3d  nop
0x18001db3e  jmp     loc_18001DBDB
0x18001db43  mov     rdi, [rbp+57h+pv]
0x18001db47  mov     r9, [r12+10h]
0x18001db4c  mov     r8, [r12+8]
0x18001db51  cmp     r8, r9
0x18001db54  jnz     short loc_18001DBB7
0x18001db56  mov     rax, r9
0x18001db59  sub     rax, r8
0x18001db5c  sar     rax, 3
0x18001db60  cmp     rax, 1
0x18001db64  jnb     short loc_18001DBB7
0x18001db66  sub     r8, [r12]
0x18001db6a  sar     r8, 3
0x18001db6e  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18001db78  mov     rax, rcx
0x18001db7b  sub     rax, r8
0x18001db7e  cmp     rax, 1
0x18001db82  jb      loc_18001DEE1
0x18001db88  inc     r8
0x18001db8b  sub     r9, [r12]
0x18001db8f  sar     r9, 3
0x18001db93  mov     rax, r9
0x18001db96  shr     rax, 1
0x18001db99  sub     rcx, rax
0x18001db9c  add     rax, r9
0x18001db9f  xor     edx, edx
0x18001dba1  cmp     rcx, r9
0x18001dba4  cmovnb  rdx, rax
0x18001dba8  cmp     rdx, r8
0x18001dbab  cmovb   rdx, r8
0x18001dbaf  mov     rcx, r12
0x18001dbb2  call    ?_Reallocate@?$vector@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z; std::vector<Microsoft::WRL::ComPtr<IMVHandler>>::_Reallocate(unsigned __int64)
0x18001dbb7  mov     rcx, [rdi+r13*8]
0x18001dbbb  mov     rax, [r12+8]
0x18001dbc0  mov     [rax], rcx
0x18001dbc3  test    rcx, rcx
0x18001dbc6  jz      short loc_18001DBD5
0x18001dbc8  mov     rax, [rcx]
0x18001dbcb  mov     rax, [rax+8]
0x18001dbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd4  nop
0x18001dbd5  add     qword ptr [r12+8], 8
0x18001dbdb  inc     r13d
0x18001dbde  mov     rbx, [rbp+57h+pv+8]
0x18001dbe2  cmp     r13d, ebx
0x18001dbe5  jb      loc_18001DA4C
0x18001dbeb  mov     r15, [rbp+57h+pv]
0x18001dbef  test    r15, r15
0x18001dbf2  jz      short loc_18001DC27
0x18001dbf4  xor     edi, edi
0x18001dbf6  test    ebx, ebx
0x18001dbf8  jz      short loc_18001DC1D
0x18001dbfa  mov     rcx, [r15+rdi*8]
0x18001dbfe  test    rcx, rcx
0x18001dc01  jz      short loc_18001DC17
0x18001dc03  mov     rax, [rcx]
0x18001dc06  mov     rax, [rax+10h]
0x18001dc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc0f  mov     qword ptr [r15+rdi*8], 0
0x18001dc17  inc     edi
0x18001dc19  cmp     edi, ebx
0x18001dc1b  jb      short loc_18001DBFA
0x18001dc1d  mov     rcx, r15; pv
0x18001dc20  call    cs:__imp_CoTaskMemFree
0x18001dc26  nop
0x18001dc27  mov     rbx, [rbp+57h+var_90]
0x18001dc2b  mov     edi, [rbp+57h+var_BC]
0x18001dc2e  add     rsi, 8
0x18001dc32  mov     eax, [rbp+57h+var_A8]
0x18001dc35  inc     eax
0x18001dc37  jmp     loc_18001D967
0x18001dc3c  mov     eax, cs:dword_18005A000
0x18001dc42  cmp     eax, 2
0x18001dc45  jbe     short loc_18001DC91
0x18001dc47  mov     [rbp+57h+var_BC], r15d
0x18001dc4b  mov     [rbp+57h+var_C0], edi
0x18001dc4e  lea     rax, [rbp+57h+var_BC]
0x18001dc52  mov     [rbp+57h+var_50], rax
0x18001dc56  mov     eax, 4
0x18001dc5b  mov     [rbp+57h+var_48], rax
0x18001dc5f  lea     rcx, [rbp+57h+var_C0]
0x18001dc63  mov     [rbp+57h+var_60], rcx
0x18001dc67  mov     [rbp+57h+var_58], rax
0x18001dc6b  lea     rcx, [rbp+57h+var_80]
0x18001dc6f  mov     [rsp+0F0h+var_C8], rcx
0x18001dc74  mov     [rsp+0F0h+var_D0], eax; int
0x18001dc78  xor     r9d, r9d
0x18001dc7b  xor     r8d, r8d
0x18001dc7e  lea     rdx, word_18004F20E
0x18001dc85  lea     rcx, dword_18005A000
0x18001dc8c  call    _tlgWriteTransfer_EventWriteTransfer
0x18001dc91  mov     rcx, [rbp+5Fh]; this
0x18001dc95  mov     r9d, r15d; char *
0x18001dc98  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001dc9f  mov     edx, 2B1h; void *
0x18001dca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dca9  nop
0x18001dcaa  mov     rdi, [rbp+57h+pv]
0x18001dcae  test    rdi, rdi
0x18001dcb1  jz      short loc_18001DCE9
0x18001dcb3  mov     esi, dword ptr [rbp+57h+pv+8]
0x18001dcb6  mov     ebx, r13d
0x18001dcb9  test    esi, esi
0x18001dcbb  jz      short loc_18001DCDF
0x18001dcbd  mov     r14d, ebx
0x18001dcc0  mov     rcx, [rdi+r14*8]
0x18001dcc4  test    rcx, rcx
0x18001dcc7  jz      short loc_18001DCD9
0x18001dcc9  mov     rax, [rcx]
0x18001dccc  mov     rax, [rax+10h]
0x18001dcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcd5  mov     [rdi+r14*8], r13
0x18001dcd9  inc     ebx
0x18001dcdb  cmp     ebx, esi
0x18001dcdd  jb      short loc_18001DCBD
0x18001dcdf  mov     rcx, rdi; pv
0x18001dce2  call    cs:__imp_CoTaskMemFree
0x18001dce8  nop
0x18001dce9  mov     eax, r15d
0x18001dcec  jmp     loc_18001DEBA
0x18001dcf1  mov     rcx, [rbp+5Fh]; this
0x18001dcf5  mov     r9d, r15d; char *
0x18001dcf8  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001dcff  mov     edx, 2D9h; void *
0x18001dd04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd09  nop
0x18001dd0a  mov     rdi, [rbp+57h+pv]
0x18001dd0e  test    rdi, rdi
0x18001dd11  jz      short loc_18001DD49
0x18001dd13  mov     esi, dword ptr [rbp+57h+pv+8]
0x18001dd16  xor     ebx, ebx
0x18001dd18  test    esi, esi
0x18001dd1a  jz      short loc_18001DD3F
0x18001dd1c  mov     rcx, [rdi+rbx*8]
0x18001dd20  test    rcx, rcx
0x18001dd23  jz      short loc_18001DD39
0x18001dd25  mov     rax, [rcx]
0x18001dd28  mov     rax, [rax+10h]
0x18001dd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd31  mov     qword ptr [rdi+rbx*8], 0
0x18001dd39  inc     ebx
0x18001dd3b  cmp     ebx, esi
0x18001dd3d  jb      short loc_18001DD1C
0x18001dd3f  mov     rcx, rdi; pv
0x18001dd42  call    cs:__imp_CoTaskMemFree
0x18001dd48  nop
0x18001dd49  jmp     short loc_18001DCE9
0x18001dd4b  mov     rcx, [rbp+5Fh]; this
0x18001dd4f  mov     r9d, r15d; char *
0x18001dd52  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001dd59  mov     edx, 2D5h; void *
0x18001dd5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd63  nop
  ... truncated ...
```
