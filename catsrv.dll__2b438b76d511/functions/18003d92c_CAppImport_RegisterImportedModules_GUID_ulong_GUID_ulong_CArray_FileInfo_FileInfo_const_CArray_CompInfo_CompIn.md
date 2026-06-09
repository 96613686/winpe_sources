# CAppImport::RegisterImportedModules(_GUID,ulong,_GUID *,ulong,CArray<FileInfo *,FileInfo * const &> *,CArray<CompInfo *,CompInfo * const &> *,__MIDL___MIDL_itf_registrar_0000_0000_0001)

- ea: `0x18003d92c`
- end: `0x18003de45`
- name: `?RegisterImportedModules@CAppImport@@QEAAJU_GUID@@KPEAU2@KPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `1305`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003caa0`
- `0x1800474b0`

## callees

- `0x18000a01c`
- `0x18000fb94`
- `0x180030044`
- `0x180030e28`
- `0x18003d92c`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dc7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dc7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d9a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d9a9`

## pseudocode

```c
__int64 __fastcall CAppImport::RegisterImportedModules(
        __int64 a1,
        __int128 *a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8)
{
  __int64 v8; // r12
  __int64 v9; // rsi
  __int64 v10; // r15
  _QWORD *v11; // r14
  HRESULT v12; // ebx
  unsigned int v13; // eax
  size_t v14; // rbx
  _QWORD *v15; // rax
  signed int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // r13
  _QWORD *v19; // rdx
  int v20; // eax
  int v21; // eax
  bool v22; // sf
  __int64 v23; // r8
  __int64 v24; // rcx
  HRESULT v25; // eax
  __int64 v26; // r8
  __int128 *v27; // r13
  __int64 v28; // rcx
  unsigned int k; // edi
  void *v30; // rcx
  unsigned int m; // edi
  void *v32; // rcx
  __int64 v34; // rax
  unsigned __int64 v35; // rbx
  SIZE_T v36; // rsi
  void *v37; // rax
  __int128 v38; // xmm1
  __int64 (__fastcall *v39)(__int64, _OWORD *, __int128 *, _QWORD *, unsigned int, int, __int64, int, LPVOID *, unsigned int *, LPVOID *, LPVOID *, LPVOID *, LPVOID *); // rax
  unsigned int i; // r8d
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned int j; // edi
  __int64 v44; // r9
  unsigned int v45; // [rsp+88h] [rbp-71h] BYREF
  int v46; // [rsp+8Ch] [rbp-6Dh] BYREF
  __int64 v47; // [rsp+90h] [rbp-69h] BYREF
  LPVOID v48; // [rsp+98h] [rbp-61h] BYREF
  signed int v49; // [rsp+A0h] [rbp-59h]
  LPVOID ppv; // [rsp+A8h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-49h] BYREF
  LPVOID v52; // [rsp+B8h] [rbp-41h] BYREF
  LPVOID v53; // [rsp+C0h] [rbp-39h] BYREF
  LPVOID v54[2]; // [rsp+C8h] [rbp-31h] BYREF
  __int128 v55; // [rsp+D8h] [rbp-21h] BYREF
  _OWORD v56[5]; // [rsp+E8h] [rbp-11h] BYREF

  v8 = a6;
  v9 = a1;
  v46 = 0;
  ppv = 0;
  v10 = *(unsigned int *)(a6 + 16);
  v47 = 0;
  v45 = 0;
  v11 = 0;
  pv = 0;
  v48 = 0;
  v54[0] = 0;
  v52 = 0;
  v53 = 0;
  v12 = CoCreateInstance(&CLSID_COMComponentRegistrar, 0, 0x15u, &IID_IRegister, &ppv);
  if ( v12 )
    goto LABEL_29;
  if ( !ppv )
  {
    v12 = -2147024882;
    goto LABEL_31;
  }
  v13 = 8 * v10;
  if ( (unsigned __int64)(8 * v10) > 0xFFFFFFFF )
  {
    v12 = -2147024362;
    goto LABEL_29;
  }
  v14 = v13;
  v15 = CoTaskMemAlloc(v13);
  v11 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    goto LABEL_29;
  }
  memset_0(v15, 0, v14);
  v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IRegister2, &v47);
  if ( v12 < 0 )
    goto LABEL_29;
  v12 = CheckIfCLRPresent(*(struct ISimpleTableDispenser **)(v9 + 72), &v46);
  if ( v12 < 0 )
    goto LABEL_29;
  v16 = 0;
  v17 = 0;
  v49 = 0;
  if ( !(_DWORD)v10 )
  {
    LODWORD(v10) = 0;
    goto LABEL_67;
  }
  do
  {
    v18 = v16;
    v19 = *(_QWORD **)(*(_QWORD *)(v8 + 8) + 8LL * v16);
    v20 = *((_DWORD *)v19 + 2);
    switch ( v20 )
    {
      case 3:
LABEL_11:
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 48LL))(v47, *v19);
LABEL_12:
        v12 = v21;
        v22 = v21 < 0;
        goto LABEL_13;
      case 4:
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 56LL))(v47, *v19);
        goto LABEL_12;
      case 6:
        goto LABEL_11;
      case 7:
        if ( v46 )
        {
          v23 = *v19;
          v24 = *(_QWORD *)(v9 + 72);
          v55 = *a2;
          v25 = RegisterRuntimeAssembly(v24, &v55, v23, 7, a8);
          v12 = v25;
          if ( v25 != -2146234344 && v25 != -2147024885 )
            goto LABEL_24;
          v12 = 0;
        }
        else
        {
          if ( (a3 & 0x200) == 0 )
            goto LABEL_21;
LABEL_24:
          v22 = v12 < 0;
LABEL_13:
          if ( v22 )
            goto LABEL_29;
        }
LABEL_60:
        v27 = a2;
        goto LABEL_61;
    }
    if ( v20 != 8 )
    {
      if ( ((v20 - 5) & 0xFFFFFFFB) != 0 )
      {
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(*v19 + 2 * v34) );
        v35 = v34 + 1;
        v36 = 2 * (v34 + 1);
        v37 = CoTaskMemAlloc(v36);
        v11[v17] = v37;
        if ( !v37 )
        {
          v12 = -2147024882;
          goto LABEL_29;
        }
        memset_0(v37, 0, v36);
        v12 = StringCchCopyW(
                (unsigned __int16 *)v11[v17],
                v35,
                **(const unsigned __int16 ***)(*(_QWORD *)(a6 + 8) + 8 * v18));
        if ( v12 < 0 )
          goto LABEL_29;
        v9 = a1;
        ++v17;
        v8 = a6;
      }
      goto LABEL_60;
    }
    if ( !v46 )
    {
LABEL_21:
      v12 = -2147467224;
      goto LABEL_29;
    }
    v26 = *v19;
    v27 = a2;
    v28 = *(_QWORD *)(v9 + 72);
    v55 = *a2;
    v12 = RegisterRuntimeAssembly(v28, &v55, v26, 8, a8);
    if ( v12 < 0 )
      goto LABEL_29;
LABEL_61:
    v16 = v49 + 1;
    v49 = v16;
  }
  while ( v16 < (unsigned int)v10 );
  LODWORD(v10) = v17;
  if ( v17 )
  {
    v38 = *v27;
    v39 = *(__int64 (__fastcall **)(__int64, _OWORD *, __int128 *, _QWORD *, unsigned int, int, __int64, int, LPVOID *, unsigned int *, LPVOID *, LPVOID *, LPVOID *, LPVOID *))(*(_QWORD *)v47 + 64LL);
    v55 = *(_OWORD *)(v9 + 96);
    v56[0] = v38;
    v12 = v39(v47, v56, &v55, v11, v17, a3, a4, a5, v54, &v45, &pv, &v48, &v52, &v53);
  }
LABEL_67:
  if ( v54[0] )
  {
    for ( i = 0; i < v17; *(_DWORD *)(v41 + 12) |= *((_DWORD *)v54[0] + v42) )
    {
      v41 = *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL * (int)i);
      v42 = i++;
    }
  }
  if ( pv )
  {
    if ( v48 )
    {
      if ( v52 )
      {
        if ( v53 )
        {
          for ( j = 0; j < v45; ++j )
          {
            v44 = *((_QWORD *)v48 + j);
            v56[0] = *((_OWORD *)pv + j);
            if ( (unsigned int)CAppImport::AddCLSIDInternal(
                                 *((unsigned int *)v52 + j),
                                 a7,
                                 v56,
                                 v44,
                                 *((_DWORD *)v52 + j),
                                 *((_DWORD *)v53 + j)) )
              break;
          }
        }
      }
    }
  }
LABEL_29:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
LABEL_31:
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  for ( k = 0; k < v45; ++k )
  {
    v30 = (void *)*((_QWORD *)v48 + k);
    if ( v30 )
    {
      CoTaskMemFree(v30);
      *((_QWORD *)v48 + k) = 0;
    }
  }
  if ( v48 )
  {
    CoTaskMemFree(v48);
    v48 = 0;
  }
  if ( v52 )
  {
    CoTaskMemFree(v52);
    v52 = 0;
  }
  if ( v53 )
  {
    CoTaskMemFree(v53);
    v53 = 0;
  }
  for ( m = 0; m < (unsigned int)v10; ++m )
  {
    v32 = (void *)v11[m];
    if ( v32 )
    {
      CoTaskMemFree(v32);
      v11[m] = 0;
    }
  }
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v54[0] )
    CoTaskMemFree(v54[0]);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003d92c  mov     rax, rsp
0x18003d92f  mov     [rax+20h], r9
0x18003d933  mov     [rax+18h], r8d
0x18003d937  mov     [rax+10h], rdx
0x18003d93b  mov     [rax+8], rcx
0x18003d93f  push    rbp
0x18003d940  push    rbx
0x18003d941  push    rsi
0x18003d942  push    rdi
0x18003d943  push    r12
0x18003d945  push    r13
0x18003d947  push    r14
0x18003d949  push    r15
0x18003d94b  lea     rbp, [rax-47h]
0x18003d94f  sub     rsp, 0F8h
0x18003d956  mov     r12, [rbp+3Fh+arg_28]
0x18003d95a  lea     rax, [rbp+3Fh+var_90]
0x18003d95e  xor     r13d, r13d
0x18003d961  mov     [rsp+130h+ppv], rax; ppv
0x18003d966  mov     rsi, rcx
0x18003d969  mov     [rbp+3Fh+var_AC], r13d
0x18003d96d  lea     r9, IID_IRegister; riid
0x18003d974  mov     [rbp+3Fh+var_90], r13
0x18003d978  mov     r15d, [r12+10h]
0x18003d97d  lea     rcx, CLSID_COMComponentRegistrar; rclsid
0x18003d984  lea     r8d, [r13+15h]; dwClsContext
0x18003d988  mov     [rbp+3Fh+var_A8], r13
0x18003d98c  xor     edx, edx; pUnkOuter
0x18003d98e  mov     [rbp+3Fh+var_B0], r13d
0x18003d992  mov     r14d, r13d
0x18003d995  mov     [rbp+3Fh+pv], r13
0x18003d999  mov     [rbp+3Fh+var_A0], r13
0x18003d99d  mov     [rbp+3Fh+var_70], r13
0x18003d9a1  mov     [rbp+3Fh+var_80], r13
0x18003d9a5  mov     [rbp+3Fh+var_78], r13
0x18003d9a9  call    cs:__imp_CoCreateInstance
0x18003d9af  mov     ebx, eax
0x18003d9b1  test    eax, eax
0x18003d9b3  jnz     loc_18003DB54
0x18003d9b9  cmp     [rbp+3Fh+var_90], r13
0x18003d9bd  jnz     short loc_18003D9C9
0x18003d9bf  mov     ebx, 8007000Eh
0x18003d9c4  jmp     loc_18003DB6D
0x18003d9c9  mov     rax, r15
0x18003d9cc  mov     ecx, 0FFFFFFFFh
0x18003d9d1  shl     rax, 3
0x18003d9d5  cmp     rax, rcx
0x18003d9d8  ja      loc_18003DE3B
0x18003d9de  mov     ecx, eax; cb
0x18003d9e0  mov     ebx, eax
0x18003d9e2  call    cs:__imp_CoTaskMemAlloc
0x18003d9e8  mov     r14, rax
0x18003d9eb  test    rax, rax
0x18003d9ee  jnz     short loc_18003D9FA
0x18003d9f0  mov     ebx, 8007000Eh
0x18003d9f5  jmp     loc_18003DB54
0x18003d9fa  mov     r8, rbx; Size
0x18003d9fd  xor     edx, edx; Val
0x18003d9ff  mov     rcx, r14; void *
0x18003da02  call    memset_0
0x18003da07  mov     rcx, [rbp+3Fh+var_90]
0x18003da0b  lea     r8, [rbp+3Fh+var_A8]
0x18003da0f  lea     rdx, IID_IRegister2
0x18003da16  mov     rax, [rcx]
0x18003da19  mov     rax, [rax]
0x18003da1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da21  mov     ebx, eax
0x18003da23  test    eax, eax
0x18003da25  js      loc_18003DB54
0x18003da2b  mov     rcx, [rsi+48h]; struct ISimpleTableDispenser *
0x18003da2f  lea     rdx, [rbp+3Fh+var_AC]; int *
0x18003da33  call    ?CheckIfCLRPresent@@YAJPEAUISimpleTableDispenser@@PEAH@Z; CheckIfCLRPresent(ISimpleTableDispenser *,int *)
0x18003da38  mov     ebx, eax
0x18003da3a  test    eax, eax
0x18003da3c  js      loc_18003DB54
0x18003da42  mov     eax, r13d
0x18003da45  mov     edi, r13d
0x18003da48  mov     [rbp+3Fh+var_98], eax
0x18003da4b  test    r15d, r15d
0x18003da4e  jz      loc_18003DD82
0x18003da54  movsxd  r13, eax
0x18003da57  mov     rax, [r12+8]
0x18003da5c  mov     rdx, [rax+r13*8]
0x18003da60  mov     eax, [rdx+8]
0x18003da63  cmp     eax, 3
0x18003da66  jnz     short loc_18003DA8D
0x18003da68  mov     rcx, [rbp+3Fh+var_A8]
0x18003da6c  mov     rax, [rcx]
0x18003da6f  mov     rax, [rax+30h]
0x18003da73  mov     rdx, [rdx]
0x18003da76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da7b  xor     r13d, r13d
0x18003da7e  mov     ebx, eax
0x18003da80  test    eax, eax
0x18003da82  js      loc_18003DB54
0x18003da88  jmp     loc_18003DCD2
0x18003da8d  cmp     eax, 4
0x18003da90  jnz     short loc_18003DA9F
0x18003da92  mov     rcx, [rbp+3Fh+var_A8]
0x18003da96  mov     rax, [rcx]
0x18003da99  mov     rax, [rax+38h]
0x18003da9d  jmp     short loc_18003DA73
0x18003da9f  cmp     eax, 6
0x18003daa2  jz      short loc_18003DA68
0x18003daa4  cmp     eax, 7
0x18003daa7  jnz     short loc_18003DB0A
0x18003daa9  xor     r13d, r13d
0x18003daac  cmp     [rbp+3Fh+var_AC], r13d
0x18003dab0  jnz     short loc_18003DAC5
0x18003dab2  test    [rbp+3Fh+arg_10], 200h
0x18003dab9  jnz     short loc_18003DAFE
0x18003dabb  mov     ebx, 80004028h
0x18003dac0  jmp     loc_18003DB54
0x18003dac5  mov     rcx, [rbp+3Fh+arg_8]
0x18003dac9  mov     r9d, eax
0x18003dacc  mov     r8, [rdx]
0x18003dacf  lea     rdx, [rbp+3Fh+var_60]
0x18003dad3  movaps  xmm0, xmmword ptr [rcx]
0x18003dad6  mov     ecx, [rbp+3Fh+arg_38]
0x18003dadc  mov     dword ptr [rsp+130h+ppv], ecx
0x18003dae0  mov     rcx, [rsi+48h]
0x18003dae4  movdqa  [rbp+3Fh+var_60], xmm0
0x18003dae9  call    ?RegisterRuntimeAssembly@@YAJPEAUISimpleTableDispenser@@U_GUID@@PEAGW4EFileType@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; RegisterRuntimeAssembly(ISimpleTableDispenser *,_GUID,ushort *,EFileType,__MIDL___MIDL_itf_registrar_0000_0000_0001)
0x18003daee  mov     ebx, eax
0x18003daf0  cmp     eax, 80131018h
0x18003daf5  jz      short loc_18003DB02
0x18003daf7  cmp     eax, 8007000Bh
0x18003dafc  jz      short loc_18003DB02
0x18003dafe  test    ebx, ebx
0x18003db00  jmp     short loc_18003DA82
0x18003db02  mov     ebx, r13d
0x18003db05  jmp     loc_18003DCD2
0x18003db0a  cmp     eax, 8
0x18003db0d  jnz     loc_18003DC56
0x18003db13  xor     r13d, r13d
0x18003db16  cmp     [rbp+3Fh+var_AC], r13d
0x18003db1a  jz      short loc_18003DABB
0x18003db1c  mov     ecx, [rbp+3Fh+arg_38]
0x18003db22  mov     r9d, eax
0x18003db25  mov     r8, [rdx]
0x18003db28  lea     rdx, [rbp+3Fh+var_60]
0x18003db2c  mov     r13, [rbp+3Fh+arg_8]
0x18003db30  mov     dword ptr [rsp+130h+ppv], ecx
0x18003db34  mov     rcx, [rsi+48h]
0x18003db38  movaps  xmm0, xmmword ptr [r13+0]
0x18003db3d  movdqa  [rbp+3Fh+var_60], xmm0
0x18003db42  call    ?RegisterRuntimeAssembly@@YAJPEAUISimpleTableDispenser@@U_GUID@@PEAGW4EFileType@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; RegisterRuntimeAssembly(ISimpleTableDispenser *,_GUID,ushort *,EFileType,__MIDL___MIDL_itf_registrar_0000_0000_0001)
0x18003db47  mov     ebx, eax
0x18003db49  test    eax, eax
0x18003db4b  jns     loc_18003DCD6
0x18003db51  xor     r13d, r13d
0x18003db54  mov     rcx, [rbp+3Fh+var_90]
0x18003db58  test    rcx, rcx
0x18003db5b  jz      short loc_18003DB6D
0x18003db5d  mov     rax, [rcx]
0x18003db60  mov     rax, [rax+10h]
0x18003db64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db69  mov     [rbp+3Fh+var_90], r13
0x18003db6d  mov     rcx, [rbp+3Fh+var_A8]
0x18003db71  test    rcx, rcx
0x18003db74  jz      short loc_18003DB86
0x18003db76  mov     rax, [rcx]
0x18003db79  mov     rax, [rax+10h]
0x18003db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db82  mov     [rbp+3Fh+var_A8], r13
0x18003db86  mov     rcx, [rbp+3Fh+pv]; pv
0x18003db8a  test    rcx, rcx
0x18003db8d  jz      short loc_18003DB99
0x18003db8f  call    cs:__imp_CoTaskMemFree
0x18003db95  mov     [rbp+3Fh+pv], r13
0x18003db99  mov     edi, r13d
0x18003db9c  cmp     [rbp+3Fh+var_B0], r13d
0x18003dba0  jbe     short loc_18003DBC6
0x18003dba2  mov     rax, [rbp+3Fh+var_A0]
0x18003dba6  mov     esi, edi
0x18003dba8  mov     rcx, [rax+rsi*8]; pv
0x18003dbac  test    rcx, rcx
0x18003dbaf  jz      short loc_18003DBBF
0x18003dbb1  call    cs:__imp_CoTaskMemFree
0x18003dbb7  mov     rax, [rbp+3Fh+var_A0]
0x18003dbbb  mov     [rax+rsi*8], r13
0x18003dbbf  inc     edi
0x18003dbc1  cmp     edi, [rbp+3Fh+var_B0]
0x18003dbc4  jb      short loc_18003DBA2
0x18003dbc6  mov     rcx, [rbp+3Fh+var_A0]; pv
0x18003dbca  test    rcx, rcx
0x18003dbcd  jz      short loc_18003DBD9
0x18003dbcf  call    cs:__imp_CoTaskMemFree
0x18003dbd5  mov     [rbp+3Fh+var_A0], r13
0x18003dbd9  mov     rcx, [rbp+3Fh+var_80]; pv
0x18003dbdd  test    rcx, rcx
0x18003dbe0  jz      short loc_18003DBEC
0x18003dbe2  call    cs:__imp_CoTaskMemFree
0x18003dbe8  mov     [rbp+3Fh+var_80], r13
0x18003dbec  mov     rcx, [rbp+3Fh+var_78]; pv
0x18003dbf0  test    rcx, rcx
0x18003dbf3  jz      short loc_18003DBFF
0x18003dbf5  call    cs:__imp_CoTaskMemFree
0x18003dbfb  mov     [rbp+3Fh+var_78], r13
0x18003dbff  mov     edi, r13d
0x18003dc02  test    r15d, r15d
0x18003dc05  jz      short loc_18003DC23
0x18003dc07  mov     esi, edi
0x18003dc09  mov     rcx, [r14+rsi*8]; pv
0x18003dc0d  test    rcx, rcx
0x18003dc10  jz      short loc_18003DC1C
0x18003dc12  call    cs:__imp_CoTaskMemFree
0x18003dc18  mov     [r14+rsi*8], r13
0x18003dc1c  inc     edi
0x18003dc1e  cmp     edi, r15d
0x18003dc21  jb      short loc_18003DC07
0x18003dc23  test    r14, r14
0x18003dc26  jz      short loc_18003DC31
0x18003dc28  mov     rcx, r14; pv
0x18003dc2b  call    cs:__imp_CoTaskMemFree
0x18003dc31  mov     rcx, [rbp+3Fh+var_70]; pv
0x18003dc35  test    rcx, rcx
0x18003dc38  jz      short loc_18003DC40
0x18003dc3a  call    cs:__imp_CoTaskMemFree
0x18003dc40  mov     eax, ebx
0x18003dc42  add     rsp, 0F8h
0x18003dc49  pop     r15
0x18003dc4b  pop     r14
0x18003dc4d  pop     r13
0x18003dc4f  pop     r12
0x18003dc51  pop     rdi
0x18003dc52  pop     rsi
0x18003dc53  pop     rbx
0x18003dc54  pop     rbp
0x18003dc55  retn
0x18003dc56  add     eax, 0FFFFFFFBh
0x18003dc59  test    eax, 0FFFFFFFBh
0x18003dc5e  jz      short loc_18003DCD2
0x18003dc60  mov     rcx, [rdx]
0x18003dc63  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003dc67  xor     edx, edx
0x18003dc69  inc     rax
0x18003dc6c  cmp     [rcx+rax*2], dx
0x18003dc70  jnz     short loc_18003DC69
0x18003dc72  lea     rbx, [rax+1]
0x18003dc76  lea     rsi, [rbx+rbx]
0x18003dc7a  mov     rcx, rsi; cb
0x18003dc7d  call    cs:__imp_CoTaskMemAlloc
0x18003dc83  mov     r12d, edi
0x18003dc86  mov     [r14+r12*8], rax
0x18003dc8a  test    rax, rax
0x18003dc8d  jz      loc_18003DD78
0x18003dc93  mov     r8, rsi; Size
0x18003dc96  xor     edx, edx; Val
0x18003dc98  mov     rcx, rax; void *
0x18003dc9b  call    memset_0
0x18003dca0  mov     rcx, [rbp+3Fh+arg_28]
0x18003dca4  mov     rdx, rbx; unsigned __int64
0x18003dca7  mov     rax, [rcx+8]
0x18003dcab  mov     rcx, [r14+r12*8]; unsigned __int16 *
0x18003dcaf  mov     r8, [rax+r13*8]
0x18003dcb3  mov     r8, [r8]; unsigned __int16 *
0x18003dcb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003dcbb  xor     r13d, r13d
0x18003dcbe  mov     ebx, eax
0x18003dcc0  test    eax, eax
0x18003dcc2  js      loc_18003DB54
0x18003dcc8  mov     rsi, [rbp+3Fh+arg_0]
0x18003dccc  inc     edi
0x18003dcce  mov     r12, [rbp+3Fh+arg_28]
0x18003dcd2  mov     r13, [rbp+3Fh+arg_8]
0x18003dcd6  mov     eax, [rbp+3Fh+var_98]
0x18003dcd9  inc     eax
0x18003dcdb  mov     [rbp+3Fh+var_98], eax
0x18003dcde  cmp     eax, r15d
0x18003dce1  jb      loc_18003DA54
0x18003dce7  mov     r15d, edi
0x18003dcea  test    edi, edi
0x18003dcec  jz      loc_18003DD73
0x18003dcf2  mov     rcx, [rbp+3Fh+var_A8]
0x18003dcf6  lea     rdx, [rbp+3Fh+var_78]
0x18003dcfa  movups  xmm0, xmmword ptr [rsi+60h]
0x18003dcfe  lea     r8, [rbp+3Fh+var_60]
0x18003dd02  mov     [rsp+68h], rdx
0x18003dd07  movaps  xmm1, xmmword ptr [r13+0]
0x18003dd0c  lea     rdx, [rbp+3Fh+var_80]
0x18003dd10  mov     rax, [rcx]
0x18003dd13  mov     r9, r14
0x18003dd16  mov     [rsp+130h+var_D0], rdx
0x18003dd1b  lea     rdx, [rbp+3Fh+var_A0]
0x18003dd1f  mov     [rsp+130h+var_D8], rdx
0x18003dd24  lea     rdx, [rbp+3Fh+pv]
0x18003dd28  mov     [rsp+130h+var_E0], rdx
0x18003dd2d  lea     rdx, [rbp+3Fh+var_B0]
0x18003dd31  mov     rax, [rax+40h]
0x18003dd35  mov     [rsp+130h+var_E8], rdx
0x18003dd3a  lea     rdx, [rbp+3Fh+var_70]
0x18003dd3e  mov     [rsp+130h+var_F0], rdx
0x18003dd43  mov     edx, [rbp+3Fh+arg_20]
0x18003dd46  mov     dword ptr [rsp+130h+var_F8], edx
0x18003dd4a  mov     rdx, [rbp+3Fh+arg_18]
0x18003dd4e  mov     qword ptr [rsp+130h+var_100], rdx
0x18003dd53  mov     edx, [rbp+3Fh+arg_10]
0x18003dd56  mov     dword ptr [rsp+130h+var_108], edx
0x18003dd5a  lea     rdx, [rbp+3Fh+var_50]
  ... truncated ...
```
