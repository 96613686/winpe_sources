# CCOMComponentRegistrar::InstallMethods(CComPlusObject *,CRegDBProvider *,CRegDBProvider *,_GUID *,_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001,ulong,int,int,ulong *,int *)

- ea: `0x18000da24`
- end: `0x18000e056`
- name: `?InstallMethods@CCOMComponentRegistrar@@AEAAJPEAVCComPlusObject@@PEAVCRegDBProvider@@1PEAU_GUID@@2W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@KHHPEAKPEAH@Z`
- size: `1586`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000d7d8`

## callees

- `0x18000d9d4`
- `0x18000da24`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCOMComponentRegistrar::InstallMethods(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        unsigned int a9,
        int a10,
        _DWORD *a11,
        _DWORD *a12)
{
  __int64 v14; // r14
  __int64 v15; // r12
  _QWORD *v16; // rsi
  int v17; // ebx
  unsigned int v18; // edi
  unsigned int v19; // eax
  _QWORD *v20; // rax
  void *v21; // rax
  __int64 i; // rbx
  LPVOID v23; // rax
  __int64 j; // r14
  void *v25; // rcx
  __int64 k; // rdi
  void *v27; // rcx
  unsigned int v29; // [rsp+58h] [rbp-39h] BYREF
  int v30; // [rsp+60h] [rbp-31h] BYREF
  __int64 v31; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v32; // [rsp+70h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-19h] BYREF
  int v34; // [rsp+80h] [rbp-11h] BYREF
  int v35; // [rsp+84h] [rbp-Dh] BYREF
  unsigned int v36; // [rsp+88h] [rbp-9h] BYREF
  unsigned int v37; // [rsp+8Ch] [rbp-5h] BYREF
  _DWORD v38[14]; // [rsp+90h] [rbp-1h] BYREF
  unsigned int v41; // [rsp+108h] [rbp+77h]

  v14 = a2;
  v15 = a1;
  v36 = 0;
  v29 = 0;
  v34 = 0;
  v32 = 0;
  v35 = 0;
  v38[0] = a7;
  v16 = 0;
  pv = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &v36);
  if ( v17 < 0 )
    goto LABEL_63;
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 128LL))(v14, &v35);
  if ( v17 < 0 )
    goto LABEL_63;
  v18 = 0;
  if ( v35 )
    v18 = a10 != 0 ? 7 : 3;
  v41 = v18;
  while ( v18 < v36 )
  {
    v30 = 1;
    v31 = 0;
    v34 = 0;
    v32 = 0;
    v29 = 0;
    v16 = 0;
    pv = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 16LL))(v14, v18, &v31);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a3 + 24LL))(a3, 0, a5);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a3 + 24LL))(a3, 1, v15 + 144);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a3 + 24LL))(a3, 2, v15 + 160);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a3 + 24LL))(a3, 3, a6);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)a3 + 24LL))(a3, 5, v38);
    if ( v17 < 0 )
      goto LABEL_59;
    if ( (v37 = 0, a10) && !a9
      || (*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 160LL))(v31, &v37) )
    {
      v19 = v18 + *a11 - v41;
    }
    else
    {
      v19 = v37;
    }
    v32 = v19;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)a3 + 24LL))(a3, 4, &v32);
    if ( v17 < 0 )
      goto LABEL_59;
    if ( *a12 )
      (*(void (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v31 + 144LL))(v31, a9, a12);
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 136LL))(v31, &v34);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)a3 + 24LL))(a3, 9, &v34);
    if ( v17 < 0 )
      goto LABEL_59;
    v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 64LL))(v31, &v29);
    if ( v17 < 0 )
      goto LABEL_59;
    if ( v29 )
    {
      v20 = CoTaskMemAlloc(saturated_mul(v29, 8u));
      v16 = v20;
      if ( !v20 )
      {
        v17 = -2147024882;
LABEL_59:
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v30);
        goto LABEL_63;
      }
      memset_0(v20, 0, 8LL * v29);
      v21 = CoTaskMemAlloc(saturated_mul(v29, 8u));
      pv = v21;
      if ( !v21 )
        goto LABEL_57;
      memset_0(v21, 0, 8LL * v29);
      for ( i = 0; (unsigned int)i < v29; i = (unsigned int)(i + 1) )
      {
        v23 = CoTaskMemAlloc(0x3EAu);
        v16[i] = v23;
        if ( !v23 )
          goto LABEL_57;
        *((_QWORD *)pv + i) = v23;
        memset_0((void *)v16[i], 0, 0x3EAu);
      }
      if ( !pv )
      {
LABEL_57:
        v17 = -2147024882;
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v30);
        goto LABEL_64;
      }
    }
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, __int64, LPVOID *, int))(*(_QWORD *)a1 + 120LL))(
            a1,
            0,
            v31,
            0,
            0,
            a3,
            &pv,
            a8);
    if ( v17 < 0 )
      goto LABEL_60;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 32LL))(a3);
    if ( v17 < 0 )
      goto LABEL_60;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 48LL))(a3);
    if ( v17 < 0 )
      goto LABEL_60;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4);
    if ( v17 < 0 )
      goto LABEL_60;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a4 + 24LL))(a4, 0, a5);
    if ( v17 < 0
      || (v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, 1, v15 + 144), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, 2, v15 + 160), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, 3, a6), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)a4 + 24LL))(a4, 4, &v34), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)a4 + 24LL))(a4, 5, v38), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 32LL))(a4), v17 < 0)
      || (v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 48LL))(a4), v17 < 0) )
    {
LABEL_60:
      CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v30);
      goto LABEL_62;
    }
    for ( j = 0; (unsigned int)j < v29; j = (unsigned int)(j + 1) )
    {
      if ( v16 )
      {
        v25 = (void *)v16[j];
        if ( v25 )
        {
          CoTaskMemFree(v25);
          v16[j] = 0;
        }
      }
      if ( pv )
        *((_QWORD *)pv + j) = 0;
    }
    if ( v16 )
    {
      CoTaskMemFree(v16);
      v16 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v30);
    ++v18;
    v14 = a2;
    v15 = a1;
  }
  *a11 += v36 - v41;
LABEL_62:
  if ( !v16 )
  {
LABEL_63:
    if ( !pv )
      return (unsigned int)v17;
  }
LABEL_64:
  for ( k = 0; (unsigned int)k < v29; k = (unsigned int)(k + 1) )
  {
    if ( v16 )
    {
      v27 = (void *)v16[k];
      if ( v27 )
      {
        CoTaskMemFree(v27);
        v16[k] = 0;
      }
    }
    if ( pv )
      *((_QWORD *)pv + k) = 0;
  }
  if ( v16 )
    CoTaskMemFree(v16);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000da24  mov     rax, rsp
0x18000da27  mov     [rax+18h], rbx
0x18000da2b  mov     [rax+10h], rdx
0x18000da2f  mov     [rax+8], rcx
0x18000da33  push    rbp
0x18000da34  push    rsi
0x18000da35  push    rdi
0x18000da36  push    r12
0x18000da38  push    r13
0x18000da3a  push    r14
0x18000da3c  push    r15
0x18000da3e  lea     rbp, [rax-3Fh]
0x18000da42  sub     rsp, 90h
0x18000da49  mov     r13, r9
0x18000da4c  mov     r15, r8
0x18000da4f  mov     r14, rdx
0x18000da52  mov     r12, rcx
0x18000da55  xor     ecx, ecx
0x18000da57  mov     [rbp+37h+var_40], ecx
0x18000da5a  mov     [rbp+37h+var_70], ecx
0x18000da5d  mov     [rbp+37h+var_48], ecx
0x18000da60  mov     [rbp+37h+var_58], ecx
0x18000da63  mov     [rbp+37h+var_44], ecx
0x18000da66  mov     eax, [rbp+37h+arg_30]
0x18000da69  mov     [rbp+37h+var_38], eax
0x18000da6c  mov     esi, ecx
0x18000da6e  mov     [rbp+37h+pv], rcx
0x18000da72  mov     rax, [rdx]
0x18000da75  lea     rdx, [rbp+37h+var_40]
0x18000da79  mov     rcx, r14
0x18000da7c  mov     rax, [rax+20h]
0x18000da80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da85  mov     ebx, eax
0x18000da87  test    eax, eax
0x18000da89  js      loc_18000DFD7
0x18000da8f  mov     rax, [r14]
0x18000da92  lea     rdx, [rbp+37h+var_44]
0x18000da96  mov     rcx, r14
0x18000da99  mov     rax, [rax+80h]
0x18000daa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa5  mov     ebx, eax
0x18000daa7  test    eax, eax
0x18000daa9  js      loc_18000DFD7
0x18000daaf  xor     edi, edi
0x18000dab1  cmp     [rbp+37h+var_44], esi
0x18000dab4  jz      short loc_18000DAC6
0x18000dab6  mov     eax, [rbp+37h+arg_48]
0x18000dabc  neg     eax
0x18000dabe  sbb     edi, edi
0x18000dac0  and     edi, 4
0x18000dac3  add     edi, 3
0x18000dac6  mov     [rbp+37h+arg_30], edi
0x18000dac9  mov     eax, [rbp+37h+var_40]
0x18000dacc  cmp     edi, eax
0x18000dace  jnb     loc_18000DFC6
0x18000dad4  mov     [rbp+37h+var_68], 1
0x18000dadb  xor     eax, eax
0x18000dadd  mov     [rbp+37h+var_60], rax
0x18000dae1  mov     [rbp+37h+var_48], eax
0x18000dae4  mov     [rbp+37h+var_58], eax
0x18000dae7  mov     [rbp+37h+var_70], eax
0x18000daea  mov     esi, eax
0x18000daec  mov     [rbp+37h+pv], rax
0x18000daf0  mov     rax, [r14]
0x18000daf3  lea     r8, [rbp+37h+var_60]
0x18000daf7  mov     edx, edi
0x18000daf9  mov     rcx, r14
0x18000dafc  mov     rax, [rax+10h]
0x18000db00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db05  mov     ebx, eax
0x18000db07  test    eax, eax
0x18000db09  js      loc_18000DFB0
0x18000db0f  mov     rax, [r15]
0x18000db12  mov     rcx, r15
0x18000db15  mov     rax, [rax+10h]
0x18000db19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db1e  mov     ebx, eax
0x18000db20  test    eax, eax
0x18000db22  js      loc_18000DFB0
0x18000db28  mov     rax, [r15]
0x18000db2b  mov     r8, [rbp+37h+arg_20]
0x18000db2f  xor     edx, edx
0x18000db31  mov     rcx, r15
0x18000db34  mov     rax, [rax+18h]
0x18000db38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3d  mov     ebx, eax
0x18000db3f  test    eax, eax
0x18000db41  js      loc_18000DFB0
0x18000db47  lea     r14, [r12+90h]
0x18000db4f  mov     rax, [r15]
0x18000db52  mov     r8, r14
0x18000db55  lea     edx, [rsi+1]
0x18000db58  mov     rcx, r15
0x18000db5b  mov     rax, [rax+18h]
0x18000db5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db64  mov     ebx, eax
0x18000db66  test    eax, eax
0x18000db68  js      loc_18000DFB0
0x18000db6e  mov     rax, [r15]
0x18000db71  lea     r8, [r12+0A0h]
0x18000db79  lea     edx, [rsi+2]
0x18000db7c  mov     rcx, r15
0x18000db7f  mov     rax, [rax+18h]
0x18000db83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db88  mov     ebx, eax
0x18000db8a  test    eax, eax
0x18000db8c  js      loc_18000DFB0
0x18000db92  mov     rax, [r15]
0x18000db95  mov     r8, [rbp+37h+arg_28]
0x18000db99  lea     edx, [rsi+3]
0x18000db9c  mov     rcx, r15
0x18000db9f  mov     rax, [rax+18h]
0x18000dba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba8  mov     ebx, eax
0x18000dbaa  test    eax, eax
0x18000dbac  js      loc_18000DFB0
0x18000dbb2  mov     rax, [r15]
0x18000dbb5  lea     r8, [rbp+37h+var_38]
0x18000dbb9  lea     edx, [rsi+5]
0x18000dbbc  mov     rcx, r15
0x18000dbbf  mov     rax, [rax+18h]
0x18000dbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc8  mov     ebx, eax
0x18000dbca  xor     eax, eax
0x18000dbcc  test    ebx, ebx
0x18000dbce  js      loc_18000DFB0
0x18000dbd4  mov     [rbp+37h+var_3C], eax
0x18000dbd7  cmp     [rbp+37h+arg_48], eax
0x18000dbdd  jz      short loc_18000DBE7
0x18000dbdf  cmp     [rbp+37h+arg_40], eax
0x18000dbe5  jz      short loc_18000DC07
0x18000dbe7  mov     rcx, [rbp+37h+var_60]
0x18000dbeb  mov     rax, [rcx]
0x18000dbee  lea     rdx, [rbp+37h+var_3C]
0x18000dbf2  mov     rax, [rax+0A0h]
0x18000dbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbfe  test    eax, eax
0x18000dc00  jnz     short loc_18000DC07
0x18000dc02  mov     eax, [rbp+37h+var_3C]
0x18000dc05  jmp     short loc_18000DC15
0x18000dc07  mov     rax, [rbp+37h+arg_50]
0x18000dc0e  mov     eax, [rax]
0x18000dc10  sub     eax, [rbp+37h+arg_30]
0x18000dc13  add     eax, edi
0x18000dc15  mov     [rbp+37h+var_58], eax
0x18000dc18  mov     rax, [r15]
0x18000dc1b  lea     r8, [rbp+37h+var_58]
0x18000dc1f  mov     edx, 4
0x18000dc24  mov     rcx, r15
0x18000dc27  mov     rax, [rax+18h]
0x18000dc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc30  mov     ebx, eax
0x18000dc32  test    eax, eax
0x18000dc34  js      loc_18000DFB0
0x18000dc3a  mov     rdx, [rbp+37h+arg_58]
0x18000dc41  cmp     [rdx], esi
0x18000dc43  jz      short loc_18000DC61
0x18000dc45  mov     rcx, [rbp+37h+var_60]
0x18000dc49  mov     rax, [rcx]
0x18000dc4c  mov     r8, rdx
0x18000dc4f  mov     edx, [rbp+37h+arg_40]
0x18000dc55  mov     rax, [rax+90h]
0x18000dc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc61  mov     rcx, [rbp+37h+var_60]
0x18000dc65  mov     rax, [rcx]
0x18000dc68  lea     rdx, [rbp+37h+var_48]
0x18000dc6c  mov     rax, [rax+88h]
0x18000dc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc78  mov     ebx, eax
0x18000dc7a  test    eax, eax
0x18000dc7c  js      loc_18000DFB0
0x18000dc82  mov     rax, [r15]
0x18000dc85  lea     r8, [rbp+37h+var_48]
0x18000dc89  mov     edx, 9
0x18000dc8e  mov     rcx, r15
0x18000dc91  mov     rax, [rax+18h]
0x18000dc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc9a  mov     ebx, eax
0x18000dc9c  test    eax, eax
0x18000dc9e  js      loc_18000DFB0
0x18000dca4  mov     rcx, [rbp+37h+var_60]
0x18000dca8  mov     rax, [rcx]
0x18000dcab  lea     rdx, [rbp+37h+var_70]
0x18000dcaf  mov     rax, [rax+40h]
0x18000dcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcb8  mov     ebx, eax
0x18000dcba  test    eax, eax
0x18000dcbc  js      loc_18000DFB0
0x18000dcc2  mov     eax, [rbp+37h+var_70]
0x18000dcc5  test    eax, eax
0x18000dcc7  jz      loc_18000DD87
0x18000dccd  mov     ecx, eax
0x18000dccf  mov     ebx, 8
0x18000dcd4  mov     eax, ebx
0x18000dcd6  mul     rcx
0x18000dcd9  lea     rcx, [rbx-9]
0x18000dcdd  cmovb   rax, rcx
0x18000dce1  mov     rcx, rax; cb
0x18000dce4  call    cs:__imp_CoTaskMemAlloc
0x18000dcea  mov     rsi, rax
0x18000dced  test    rax, rax
0x18000dcf0  jz      loc_18000DFAB
0x18000dcf6  mov     r8d, [rbp+37h+var_70]
0x18000dcfa  shl     r8, 3; Size
0x18000dcfe  xor     edx, edx; Val
0x18000dd00  mov     rcx, rax; void *
0x18000dd03  call    memset_0
0x18000dd08  mov     ecx, [rbp+37h+var_70]
0x18000dd0b  mov     eax, ebx
0x18000dd0d  mul     rcx
0x18000dd10  lea     rcx, [rbx-9]
0x18000dd14  cmovb   rax, rcx
0x18000dd18  mov     rcx, rax; cb
0x18000dd1b  call    cs:__imp_CoTaskMemAlloc
0x18000dd21  mov     [rbp+37h+pv], rax
0x18000dd25  test    rax, rax
0x18000dd28  jz      loc_18000DF9B
0x18000dd2e  mov     r8d, [rbp+37h+var_70]
0x18000dd32  shl     r8, 3; Size
0x18000dd36  xor     edx, edx; Val
0x18000dd38  mov     rcx, rax; void *
0x18000dd3b  call    memset_0
0x18000dd40  xor     ebx, ebx
0x18000dd42  cmp     ebx, [rbp+37h+var_70]
0x18000dd45  jnb     short loc_18000DD7C
0x18000dd47  mov     ecx, 3EAh; cb
0x18000dd4c  call    cs:__imp_CoTaskMemAlloc
0x18000dd52  mov     [rsi+rbx*8], rax
0x18000dd56  test    rax, rax
0x18000dd59  jz      loc_18000DF9B
0x18000dd5f  mov     rcx, [rbp+37h+pv]
0x18000dd63  mov     [rcx+rbx*8], rax
0x18000dd67  xor     edx, edx; Val
0x18000dd69  mov     r8d, 3EAh; Size
0x18000dd6f  mov     rcx, [rsi+rbx*8]; void *
0x18000dd73  call    memset_0
0x18000dd78  inc     ebx
0x18000dd7a  jmp     short loc_18000DD42
0x18000dd7c  cmp     [rbp+37h+pv], 0
0x18000dd81  jz      loc_18000DF9B
0x18000dd87  mov     rcx, [rbp+37h+arg_0]
0x18000dd8b  mov     rax, [rcx]
0x18000dd8e  mov     edx, [rbp+37h+arg_38]
0x18000dd91  mov     [rsp+38h], edx
0x18000dd95  lea     rdx, [rbp+37h+pv]
0x18000dd99  mov     qword ptr [rsp+0C0h+var_90], rdx
0x18000dd9e  mov     [rsp+0C0h+var_98], r15
0x18000dda3  mov     [rsp+0C0h+var_A0], 0
0x18000ddac  xor     r9d, r9d
0x18000ddaf  mov     r8, [rbp+37h+var_60]
0x18000ddb3  xor     edx, edx
0x18000ddb5  mov     rax, [rax+78h]
0x18000ddb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddbe  mov     ebx, eax
0x18000ddc0  test    eax, eax
0x18000ddc2  js      loc_18000DFBB
0x18000ddc8  mov     rax, [r15]
0x18000ddcb  mov     rcx, r15
0x18000ddce  mov     rax, [rax+20h]
0x18000ddd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddd7  mov     ebx, eax
0x18000ddd9  test    eax, eax
0x18000dddb  js      loc_18000DFBB
0x18000dde1  mov     rax, [r15]
0x18000dde4  mov     rcx, r15
0x18000dde7  mov     rax, [rax+30h]
0x18000ddeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf0  mov     ebx, eax
0x18000ddf2  test    eax, eax
0x18000ddf4  js      loc_18000DFBB
0x18000ddfa  mov     rax, [r13+0]
0x18000ddfe  mov     rcx, r13
0x18000de01  mov     rax, [rax+10h]
0x18000de05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0a  mov     ebx, eax
0x18000de0c  test    eax, eax
0x18000de0e  js      loc_18000DFBB
0x18000de14  mov     rax, [r13+0]
0x18000de18  mov     r8, [rbp+37h+arg_20]
0x18000de1c  xor     edx, edx
0x18000de1e  mov     rcx, r13
0x18000de21  mov     rax, [rax+18h]
0x18000de25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de2a  mov     ebx, eax
0x18000de2c  test    eax, eax
0x18000de2e  js      loc_18000DFBB
0x18000de34  mov     rax, [r13+0]
0x18000de38  mov     r8, r14
0x18000de3b  mov     edx, 1
0x18000de40  mov     rcx, r13
0x18000de43  mov     rax, [rax+18h]
0x18000de47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de4c  mov     ebx, eax
0x18000de4e  test    eax, eax
0x18000de50  js      loc_18000DFBB
0x18000de56  mov     rax, [r13+0]
0x18000de5a  lea     r8, [r12+0A0h]
0x18000de62  mov     edx, 2
0x18000de67  mov     rcx, r13
0x18000de6a  mov     rax, [rax+18h]
  ... truncated ...
```
