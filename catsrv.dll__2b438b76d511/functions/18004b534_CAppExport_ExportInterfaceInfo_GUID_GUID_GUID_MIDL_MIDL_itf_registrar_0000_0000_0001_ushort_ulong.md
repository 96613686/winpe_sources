# CAppExport::ExportInterfaceInfo(_GUID,_GUID,_GUID,__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort *,ulong)

- ea: `0x18004b534`
- end: `0x18004ba45`
- name: `?ExportInterfaceInfo@CAppExport@@AEAAJU_GUID@@00W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAGK@Z`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fe08`

## callees

- `0x18000b748`
- `0x18001a6c8`
- `0x18004a354`
- `0x18004b534`
- `0x18004ba4c`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b60d`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b735`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b60d`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b807`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportInterfaceInfo(
        __int64 a1,
        __int128 *a2,
        __int128 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 *a6,
        char a7)
{
  unsigned int v7; // edi
  int SimpleTableDispenser; // ebx
  int v10; // eax
  int v11; // eax
  _QWORD *v12; // r15
  bool v13; // zf
  __int64 v14; // rax
  int v15; // r12d
  __int64 *v16; // r14
  __int64 v18; // r8
  __int64 *v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v23; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 *v24; // [rsp+78h] [rbp-88h]
  __int128 *v25; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v26; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v27; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  __int128 v32; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v35[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F4h] [rbp-Ch]
  __int128 *v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+100h] [rbp+0h]
  int v40; // [rsp+104h] [rbp+4h]
  int v41; // [rsp+108h] [rbp+8h]
  int v42; // [rsp+10Ch] [rbp+Ch]
  __int64 v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+118h] [rbp+18h]
  int v45; // [rsp+11Ch] [rbp+1Ch]
  int v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+124h] [rbp+24h]
  unsigned int *v48; // [rsp+128h] [rbp+28h]
  int v49; // [rsp+130h] [rbp+30h]
  int v50; // [rsp+134h] [rbp+34h]
  int v51; // [rsp+138h] [rbp+38h]
  int v52; // [rsp+13Ch] [rbp+3Ch]

  v7 = 0;
  v24 = a3;
  v25 = a2;
  v26 = a6;
  v36 = 72;
  v41 = 72;
  v46 = 72;
  v48 = &v23;
  v19 = 0;
  v34 = 0;
  v23 = a5;
  v35[0] = a2;
  v35[1] = 0;
  v37 = 16;
  v38 = a3;
  v39 = 0;
  v40 = 1;
  v42 = 16;
  v43 = a4;
  v44 = 0;
  v45 = 2;
  v47 = 16;
  v49 = 0;
  v50 = 4;
  v51 = 19;
  v52 = 4;
  v20 = 0;
  if ( *(_QWORD *)(a1 + 176) )
  {
LABEL_5:
    v10 = memcmp_0(&tidCOMSERVICES_CLASSINTERFACE, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 176) + 24LL))(
                             *(_QWORD *)(a1 + 176),
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSINTERFACE,
                             v35,
                             4,
                             1,
                             v10 != 0 ? 7 : 5,
                             &v20);
    goto LABEL_6;
  }
  *(_QWORD *)&v21 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v21);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v21, 0) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 16LL))(v21);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_29;
  if ( !v20 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_31;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_29;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_29;
  v27 = a6;
  v28 = 0;
  v29 = -268435455;
  v30 = 130;
  v19 = 0;
  v31 = 2 * safe_lstrlenW(a6) + 2;
  if ( *(_QWORD *)(a1 + 176) )
    goto LABEL_15;
  *(_QWORD *)&v21 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v21);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v21, 0) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_15:
    v11 = memcmp_0(tidCOMSERVICES_CLASSINTERFACE_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 **))(**(_QWORD **)(a1 + 176) + 24LL))(
                             *(_QWORD *)(a1 + 176),
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSINTERFACE_EXPORT,
                             &v27,
                             1,
                             1,
                             v11 != 0 ? 6 : 4,
                             &v19);
  }
  if ( SimpleTableDispenser < 0 )
    goto LABEL_29;
  if ( !v19 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v19 + 24))(v19);
  if ( SimpleTableDispenser >= 0 )
  {
    v12 = CoTaskMemAlloc(0x60u);
    if ( v12 )
    {
      while ( 1 )
      {
        v13 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 40LL))(v20) == -2146367487;
        v14 = *v19;
        if ( v13 )
          break;
        SimpleTableDispenser = (*(__int64 (**)(void))(v14 + 120))();
        if ( SimpleTableDispenser >= 0 )
        {
          *v12 = 0;
          v15 = 0;
          v34 = 0;
          while ( v7 < 0xC )
          {
            v22 = 0;
            LODWORD(v21) = 0;
            v16 = &v12[v7];
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int128 *, __int64 *))(*(_QWORD *)v20 + 64LL))(
                                     v20,
                                     v7,
                                     &v22,
                                     &v21,
                                     v16);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_28;
            if ( v7 == 3 )
            {
              SimpleTableDispenser = CAppExport::AddTLBFileName(a1, *v16, a5);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_28;
            }
            else if ( v7 - 1 <= 1 )
            {
              *v16 = (__int64)&GUID_NULL;
            }
            else if ( v7 == 8 )
            {
              v15 = *(_DWORD *)*v16;
            }
            if ( *v16 )
            {
              v18 = 0;
              if ( v22 == 128 )
                v18 = (unsigned int)v21;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v19 + 160))(v19, v7, v18);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_28;
              if ( v7 == 3 )
                v34 = *(_OWORD *)*v16;
            }
            ++v7;
          }
          v7 = 0;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v19 + 144))(v19);
          if ( SimpleTableDispenser >= 0 )
          {
            v21 = v34;
            v32 = *v24;
            v33 = *v25;
            SimpleTableDispenser = CAppExport::ExportMethodInfo(
                                     a1,
                                     (__int64)&v33,
                                     (__int64)&v32,
                                     (__int64)&v21,
                                     a5,
                                     v26,
                                     v15,
                                     a7);
            if ( SimpleTableDispenser >= 0 )
            {
              SimpleTableDispenser = CAppExport::GetProxyStubDll(a1, &v34, a5);
              if ( SimpleTableDispenser >= 0 )
                continue;
            }
          }
        }
        goto LABEL_28;
      }
      SimpleTableDispenser = (*(__int64 (**)(void))(v14 + 96))();
LABEL_28:
      *v12 = 0;
      CoTaskMemFree(v12);
      goto LABEL_29;
    }
LABEL_18:
    SimpleTableDispenser = -2147024882;
  }
LABEL_29:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
LABEL_31:
  if ( v19 )
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004b534  mov     [rsp-8+arg_18], rbx
0x18004b539  push    rbp
0x18004b53a  push    rsi
0x18004b53b  push    rdi
0x18004b53c  push    r12
0x18004b53e  push    r13
0x18004b540  push    r14
0x18004b542  push    r15
0x18004b544  lea     rbp, [rsp-50h]
0x18004b549  sub     rsp, 150h
0x18004b550  mov     rax, cs:__security_cookie
0x18004b557  xor     rax, rsp
0x18004b55a  mov     [rbp+80h+var_40], rax
0x18004b55e  mov     r14, [rbp+80h+arg_28]
0x18004b565  xor     edi, edi
0x18004b567  xorps   xmm0, xmm0
0x18004b56a  mov     r13d, [rbp+80h+arg_20]
0x18004b571  mov     rsi, rcx
0x18004b574  mov     [rsp+180h+var_108], r8
0x18004b579  mov     [rbp+80h+var_100], rdx
0x18004b57d  lea     eax, [rdi+48h]
0x18004b580  mov     [rbp+80h+var_F8], r14
0x18004b584  lea     r15d, [rdi+10h]
0x18004b588  mov     [rbp+80h+var_90], eax
0x18004b58b  lea     r12d, [rdi+4]
0x18004b58f  mov     [rbp+80h+var_78], eax
0x18004b592  mov     [rbp+80h+var_60], eax
0x18004b595  lea     rax, [rsp+180h+var_10C]
0x18004b59a  mov     [rbp+80h+var_58], rax
0x18004b59e  mov     [rsp+180h+var_130], rdi
0x18004b5a3  movups  [rbp+80h+var_B0], xmm0
0x18004b5a7  mov     [rsp+180h+var_10C], r13d
0x18004b5ac  mov     [rbp+80h+var_A0], rdx
0x18004b5b0  mov     [rbp+80h+var_98], rdi
0x18004b5b4  mov     [rbp+80h+var_8C], r15d
0x18004b5b8  mov     [rbp+80h+var_88], r8
0x18004b5bc  mov     [rbp+80h+var_80], edi
0x18004b5bf  mov     [rbp+80h+var_7C], 1
0x18004b5c6  mov     [rbp+80h+var_74], r15d
0x18004b5ca  mov     [rbp+80h+var_70], r9
0x18004b5ce  mov     [rbp+80h+var_68], edi
0x18004b5d1  mov     [rbp+80h+var_64], 2
0x18004b5d8  mov     [rbp+80h+var_5C], r15d
0x18004b5dc  mov     [rbp+80h+var_50], edi
0x18004b5df  mov     [rbp+80h+var_4C], r12d
0x18004b5e3  mov     [rbp+80h+var_48], 13h
0x18004b5ea  mov     [rbp+80h+var_44], r12d
0x18004b5ee  mov     [rsp+180h+var_128], rdi
0x18004b5f3  cmp     [rcx+0B0h], rdi
0x18004b5fa  jnz     short loc_18004B640
0x18004b5fc  lea     rdx, [rsp+180h+var_120]
0x18004b601  mov     qword ptr [rsp+180h+var_120], rdi
0x18004b606  lea     rcx, IID_ISimpleTableDispenser
0x18004b60d  call    cs:__imp_GetSimpleTableDispenser
0x18004b613  mov     ebx, eax
0x18004b615  test    eax, eax
0x18004b617  js      loc_18004B6A2
0x18004b61d  mov     rcx, qword ptr [rsp+180h+var_120]
0x18004b622  xor     eax, eax
0x18004b624  lock cmpxchg [rsi+0B0h], rcx
0x18004b62d  jz      short loc_18004B640
0x18004b62f  mov     rcx, qword ptr [rsp+180h+var_120]
0x18004b634  mov     rax, [rcx]
0x18004b637  mov     rax, [rax+10h]
0x18004b63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b640  mov     r8, r15; Size
0x18004b643  lea     rdx, TID_APPLICATION; Buf2
0x18004b64a  lea     rcx, tidCOMSERVICES_CLASSINTERFACE; Buf1
0x18004b651  call    memcmp_0
0x18004b656  mov     rcx, [rsi+0B0h]
0x18004b65d  lea     r9, [rsp+180h+var_128]
0x18004b662  mov     [rsp+180h+var_148], r9
0x18004b667  lea     r8, tidCOMSERVICES_CLASSINTERFACE
0x18004b66e  neg     eax
0x18004b670  lea     r9, [rbp+80h+var_A0]
0x18004b674  mov     rax, [rcx]
0x18004b677  sbb     edx, edx
0x18004b679  and     edx, 2
0x18004b67c  add     edx, 5
0x18004b67f  mov     [rsp+180h+var_150], edx
0x18004b683  lea     rdx, didCOMSERVICES
0x18004b68a  mov     rax, [rax+18h]
0x18004b68e  mov     dword ptr [rsp+180h+var_158], 1
0x18004b696  mov     [rsp+180h+var_160], r12
0x18004b69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6a0  mov     ebx, eax
0x18004b6a2  test    ebx, ebx
0x18004b6a4  js      loc_18004B8CF
0x18004b6aa  mov     rcx, [rsp+180h+var_128]
0x18004b6af  test    rcx, rcx
0x18004b6b2  jnz     short loc_18004B6BE
0x18004b6b4  mov     ebx, 8007000Eh
0x18004b6b9  jmp     loc_18004B8EA
0x18004b6be  mov     rax, [rcx]
0x18004b6c1  mov     rax, [rax+18h]
0x18004b6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6ca  mov     ebx, eax
0x18004b6cc  test    eax, eax
0x18004b6ce  js      loc_18004B8CF
0x18004b6d4  mov     rcx, [rsp+180h+var_128]
0x18004b6d9  mov     rax, [rcx]
0x18004b6dc  mov     rax, [rax+20h]
0x18004b6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6e5  mov     ebx, eax
0x18004b6e7  test    eax, eax
0x18004b6e9  js      loc_18004B8CF
0x18004b6ef  mov     rcx, r14; unsigned __int16 *
0x18004b6f2  mov     [rbp+80h+var_F0], r14
0x18004b6f6  mov     [rbp+80h+var_E8], edi
0x18004b6f9  mov     [rbp+80h+var_E4], 0F0000001h
0x18004b700  mov     [rbp+80h+var_E0], 82h
0x18004b707  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004b70c  mov     [rsp+180h+var_130], rdi
0x18004b711  lea     eax, ds:2[rax*2]
0x18004b718  mov     [rbp+80h+var_DC], eax
0x18004b71b  cmp     [rsi+0B0h], rdi
0x18004b722  jnz     short loc_18004B768
0x18004b724  lea     rdx, [rsp+180h+var_120]
0x18004b729  mov     qword ptr [rsp+180h+var_120], rdi
0x18004b72e  lea     rcx, IID_ISimpleTableDispenser
0x18004b735  call    cs:__imp_GetSimpleTableDispenser
0x18004b73b  mov     ebx, eax
0x18004b73d  test    eax, eax
0x18004b73f  js      loc_18004B7CE
0x18004b745  mov     rcx, qword ptr [rsp+180h+var_120]
0x18004b74a  xor     eax, eax
0x18004b74c  lock cmpxchg [rsi+0B0h], rcx
0x18004b755  jz      short loc_18004B768
0x18004b757  mov     rcx, qword ptr [rsp+180h+var_120]
0x18004b75c  mov     rax, [rcx]
0x18004b75f  mov     rax, [rax+10h]
0x18004b763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b768  mov     r8, r15; Size
0x18004b76b  lea     rdx, TID_APPLICATION; Buf2
0x18004b772  lea     rcx, tidCOMSERVICES_CLASSINTERFACE_EXPORT; Buf1
0x18004b779  call    memcmp_0
0x18004b77e  mov     rcx, [rsi+0B0h]
0x18004b785  lea     r10, [rsp+180h+var_130]
0x18004b78a  neg     eax
0x18004b78c  mov     [rsp+180h+var_148], r10
0x18004b791  mov     edx, 1
0x18004b796  lea     r8, tidCOMSERVICES_CLASSINTERFACE_EXPORT
0x18004b79d  sbb     r9d, r9d
0x18004b7a0  mov     rax, [rcx]
0x18004b7a3  and     r9d, 2
0x18004b7a7  add     r9d, r12d
0x18004b7aa  mov     [rsp+180h+var_150], r9d
0x18004b7af  lea     r9, [rbp+80h+var_F0]
0x18004b7b3  mov     dword ptr [rsp+180h+var_158], edx
0x18004b7b7  mov     rax, [rax+18h]
0x18004b7bb  mov     [rsp+180h+var_160], rdx
0x18004b7c0  lea     rdx, didCOMSERVICES
0x18004b7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7cc  mov     ebx, eax
0x18004b7ce  test    ebx, ebx
0x18004b7d0  js      loc_18004B8CF
0x18004b7d6  cmp     [rsp+180h+var_130], rdi
0x18004b7db  jnz     short loc_18004B7E7
0x18004b7dd  mov     ebx, 8007000Eh
0x18004b7e2  jmp     loc_18004B8CF
0x18004b7e7  mov     rcx, [rsp+180h+var_130]
0x18004b7ec  mov     rax, [rcx]
0x18004b7ef  mov     rax, [rax+18h]
0x18004b7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7f8  mov     ebx, eax
0x18004b7fa  test    eax, eax
0x18004b7fc  js      loc_18004B8CF
0x18004b802  mov     ecx, 60h ; '`'; cb
0x18004b807  call    cs:__imp_CoTaskMemAlloc
0x18004b80d  mov     r15, rax
0x18004b810  test    rax, rax
0x18004b813  jz      short loc_18004B7DD
0x18004b815  mov     rcx, [rsp+180h+var_128]
0x18004b81a  mov     rax, [rcx]
0x18004b81d  mov     rax, [rax+28h]
0x18004b821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b826  mov     rcx, [rsp+180h+var_130]
0x18004b82b  cmp     eax, 80110801h
0x18004b830  mov     rax, [rcx]
0x18004b833  jz      loc_18004BA35
0x18004b839  mov     rax, [rax+78h]
0x18004b83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b842  mov     ebx, eax
0x18004b844  test    eax, eax
0x18004b846  js      short loc_18004B8C1
0x18004b848  xor     eax, eax
0x18004b84a  xorps   xmm0, xmm0
0x18004b84d  mov     [r15], rax
0x18004b850  mov     r12d, edi
0x18004b853  movups  [rbp+80h+var_B0], xmm0
0x18004b857  cmp     edi, 0Ch
0x18004b85a  jnb     loc_18004B998
0x18004b860  mov     rcx, [rsp+180h+var_128]
0x18004b865  lea     r9, [rsp+180h+var_120]
0x18004b86a  mov     eax, edi
0x18004b86c  lea     r8, [rsp+180h+var_110]
0x18004b871  mov     [rsp+180h+var_110], 0
0x18004b879  mov     edx, edi
0x18004b87b  mov     dword ptr [rsp+180h+var_120], 0
0x18004b883  lea     r14, [r15+rax*8]
0x18004b887  mov     rax, [rcx]
0x18004b88a  mov     [rsp+180h+var_160], r14
0x18004b88f  mov     rax, [rax+40h]
0x18004b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b898  mov     ebx, eax
0x18004b89a  test    eax, eax
0x18004b89c  js      short loc_18004B8BF
0x18004b89e  cmp     edi, 3
0x18004b8a1  jnz     loc_18004B929
0x18004b8a7  mov     rdx, [r14]
0x18004b8aa  mov     r8d, r13d
0x18004b8ad  mov     rcx, rsi
0x18004b8b0  call    ?AddTLBFileName@CAppExport@@AEAAJPEAU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; CAppExport::AddTLBFileName(_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001)
0x18004b8b5  mov     ebx, eax
0x18004b8b7  test    eax, eax
0x18004b8b9  jns     loc_18004B948
0x18004b8bf  xor     edi, edi
0x18004b8c1  xor     eax, eax
0x18004b8c3  mov     rcx, r15; pv
0x18004b8c6  mov     [r15], rax
0x18004b8c9  call    cs:__imp_CoTaskMemFree
0x18004b8cf  mov     rcx, [rsp+180h+var_128]
0x18004b8d4  test    rcx, rcx
0x18004b8d7  jz      short loc_18004B8EA
0x18004b8d9  mov     rax, [rcx]
0x18004b8dc  mov     rax, [rax+10h]
0x18004b8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8e5  mov     [rsp+180h+var_128], rdi
0x18004b8ea  mov     rcx, [rsp+180h+var_130]
0x18004b8ef  test    rcx, rcx
0x18004b8f2  jz      short loc_18004B900
0x18004b8f4  mov     rax, [rcx]
0x18004b8f7  mov     rax, [rax+10h]
0x18004b8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b900  mov     eax, ebx
0x18004b902  mov     rcx, [rbp+80h+var_40]
0x18004b906  xor     rcx, rsp; StackCookie
0x18004b909  call    __security_check_cookie
0x18004b90e  mov     rbx, [rsp+180h+arg_18]
0x18004b916  add     rsp, 150h
0x18004b91d  pop     r15
0x18004b91f  pop     r14
0x18004b921  pop     r13
0x18004b923  pop     r12
0x18004b925  pop     rdi
0x18004b926  pop     rsi
0x18004b927  pop     rbp
0x18004b928  retn
0x18004b929  lea     eax, [rdi-1]
0x18004b92c  cmp     eax, 1
0x18004b92f  jbe     short loc_18004B93E
0x18004b931  cmp     edi, 8
0x18004b934  jnz     short loc_18004B948
0x18004b936  mov     rax, [r14]
0x18004b939  mov     r12d, [rax]
0x18004b93c  jmp     short loc_18004B948
0x18004b93e  lea     rax, GUID_NULL
0x18004b945  mov     [r14], rax
0x18004b948  mov     r9, [r14]
0x18004b94b  test    r9, r9
0x18004b94e  jz      short loc_18004B991
0x18004b950  mov     rcx, [rsp+180h+var_130]
0x18004b955  xor     r8d, r8d
0x18004b958  cmp     [rsp+180h+var_110], 80h
0x18004b960  mov     edx, edi
0x18004b962  cmovz   r8d, dword ptr [rsp+180h+var_120]
0x18004b968  mov     rax, [rcx]
0x18004b96b  mov     rax, [rax+0A0h]
0x18004b972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b977  mov     ebx, eax
0x18004b979  test    eax, eax
0x18004b97b  js      loc_18004B8BF
0x18004b981  cmp     edi, 3
0x18004b984  jnz     short loc_18004B991
0x18004b986  mov     rax, [r14]
0x18004b989  movups  xmm0, xmmword ptr [rax]
0x18004b98c  movdqu  [rbp+80h+var_B0], xmm0
0x18004b991  inc     edi
0x18004b993  jmp     loc_18004B857
0x18004b998  mov     rcx, [rsp+180h+var_130]
0x18004b99d  mov     rax, [rcx]
0x18004b9a0  mov     rax, [rax+90h]
0x18004b9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9ac  xor     edi, edi
0x18004b9ae  mov     ebx, eax
0x18004b9b0  test    eax, eax
0x18004b9b2  js      loc_18004B8C1
0x18004b9b8  movaps  xmm0, [rbp+80h+var_B0]
0x18004b9bc  lea     r9, [rsp+180h+var_120]
0x18004b9c1  mov     rax, [rsp+180h+var_108]
0x18004b9c6  lea     r8, [rbp+80h+var_D0]
0x18004b9ca  movdqa  [rsp+180h+var_120], xmm0
0x18004b9d0  lea     rdx, [rbp+80h+var_C0]
0x18004b9d4  mov     rcx, rsi
0x18004b9d7  movaps  xmm1, xmmword ptr [rax]
0x18004b9da  mov     rax, [rbp+80h+var_100]
0x18004b9de  movdqa  [rbp+80h+var_D0], xmm1
0x18004b9e3  movaps  xmm0, xmmword ptr [rax]
0x18004b9e6  mov     eax, [rbp+80h+arg_30]
0x18004b9ec  mov     dword ptr [rsp+180h+var_148], eax
  ... truncated ...
```
