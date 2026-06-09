# CCatalogServer::GetComponentVersions(ushort const *,ulong *,_GUID * *,_GUID * *,int * *,long * *)

- ea: `0x1800218b0`
- end: `0x180022036`
- name: `?GetComponentVersions@CCatalogServer@@UEAAJPEBGPEAKPEAPEAU_GUID@@2PEAPEAHPEAPEAJ@Z`
- size: `1926`
- prototype: `int(CCatalogServer *__hidden this, const unsigned __int16 *, unsigned int *, struct _GUID **, struct _GUID **, int **, int **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004d60`
- `0x180004f48`
- `0x18001ece0`
- `0x1800218b0`
- `0x1800554f6`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021fd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021fd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022002`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800219b8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800219b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021a05`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021a05`

## pseudocode

```c
__int64 __fastcall CCatalogServer::GetComponentVersions(
        CCatalogServer *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        LPVOID *a4,
        struct _GUID **a5,
        int **a6,
        int **a7)
{
  UTSemReadWrite *v9; // rcx
  UTSemReadWrite *v10; // rcx
  int v11; // r14d
  void *v12; // rdi
  struct _GUID *v13; // r15
  void *v14; // r12
  int *v15; // rax
  int *v16; // rsi
  unsigned int v17; // edi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  UTSemReadWrite *v23; // rcx
  __int64 v24; // [rsp+0h] [rbp-148h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-128h]
  HRESULT v26; // [rsp+50h] [rbp-F8h]
  unsigned int v27; // [rsp+54h] [rbp-F4h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-F0h] BYREF
  __int64 *v29; // [rsp+60h] [rbp-E8h]
  int v30; // [rsp+68h] [rbp-E0h]
  __int64 v31; // [rsp+70h] [rbp-D8h] BYREF
  LPVOID v32; // [rsp+78h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-C8h]
  unsigned int i; // [rsp+88h] [rbp-C0h]
  int *v35; // [rsp+90h] [rbp-B8h] BYREF
  LPVOID v36; // [rsp+98h] [rbp-B0h]
  LPVOID v37; // [rsp+A0h] [rbp-A8h]
  LPVOID v38; // [rsp+A8h] [rbp-A0h]
  __int64 v39; // [rsp+B0h] [rbp-98h]
  unsigned int *v40; // [rsp+B8h] [rbp-90h]
  struct _GUID **v41; // [rsp+C0h] [rbp-88h]
  int **v42; // [rsp+C8h] [rbp-80h]
  int **v43; // [rsp+D0h] [rbp-78h]
  _QWORD v44[2]; // [rsp+D8h] [rbp-70h] BYREF
  int v45; // [rsp+E8h] [rbp-60h]
  int v46; // [rsp+ECh] [rbp-5Ch]
  GUID pclsid; // [rsp+F0h] [rbp-58h] BYREF

  v29 = &v24;
  v40 = a3;
  v41 = a5;
  v42 = a6;
  v43 = a7;
  if ( !a3 || !a4 || !a5 || !a6 || !a7 )
    return 2147942487LL;
  if ( !*((_DWORD *)this + 34) )
    return 2148598828LL;
  v26 = 0;
  v27 = 0;
  pv = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v32 = 0;
  v28 = 0;
  pclsid = 0;
  v30 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v26 = CLSIDFromString(a2, &pclsid);
  if ( v26 < 0 )
  {
    v26 = -2147024809;
    local_unwind_0(v29, &loc_180021FC8);
  }
  v26 = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &v32);
  if ( v26 < 0 )
    local_unwind_0(v29, &loc_180021FC8);
  v44[1] = 0;
  v45 = 72;
  v46 = 16;
  v44[0] = &pclsid;
  UTSemReadWrite::LockRead(v9);
  v30 = 1;
  v26 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 **))(*(_QWORD *)v32 + 24LL))(
          v32,
          didCOMSERVICES,
          &tidCOMSERVICES_CLASSES_INTERNAL,
          v44,
          1,
          1,
          1,
          &v28);
  if ( v26 < 0 )
    local_unwind_0(v29, &loc_180021FC8);
  v26 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 24))(v28);
  if ( v26 < 0 )
    local_unwind_0(v29, &loc_180021FC8);
  UTSemReadWrite::UnlockRead(v10);
  v11 = 0;
  v30 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*v28 + 72))(
          v28,
          0,
          0,
          0,
          0,
          0,
          0,
          &v27,
          0);
  if ( v26 < 0 )
    local_unwind_0(v29, &loc_180021FC8);
  if ( !v27 )
  {
    v26 = -2147221164;
    local_unwind_0(v29, &loc_180021FC8);
  }
  v12 = CoTaskMemAlloc(16LL * v27);
  pv = v12;
  v13 = (struct _GUID *)CoTaskMemAlloc(16LL * v27);
  v36 = v13;
  v14 = CoTaskMemAlloc(4LL * v27);
  v37 = v14;
  v15 = (int *)CoTaskMemAlloc(4LL * v27);
  v16 = v15;
  v38 = v15;
  if ( v12 && v13 && v14 && v15 )
  {
    v17 = 0;
    for ( i = 0; ; i = v17 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 40))(v28);
      if ( v26 )
        break;
      v31 = 0;
      v35 = 0;
      v18 = *v28;
      ppv = (LPVOID *)&v31;
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v18 + 64))(v28, 1, 0);
      if ( v26 < 0 )
        local_unwind_0(v29, &loc_180021FC8);
      v39 = 16LL * v17;
      *(_OWORD *)((char *)pv + v39) = *(_OWORD *)v31;
      v19 = *v28;
      ppv = (LPVOID *)&v31;
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v19 + 64))(v28, 4, 0);
      if ( v26 < 0 )
        local_unwind_0(v29, &loc_180021FC8);
      v13[(unsigned __int64)v39 / 0x10] = *(struct _GUID *)v31;
      v20 = *v28;
      ppv = (LPVOID *)&v31;
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v20 + 64))(v28, 2, 0);
      if ( v26 < 0 )
        local_unwind_0(v29, &loc_180021FC8);
      v21 = *(_QWORD *)v31 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)v31 == *(_QWORD *)&GUID_NULL.Data1 )
        v21 = *(_QWORD *)(v31 + 8) - *(_QWORD *)GUID_NULL.Data4;
      *((_DWORD *)v14 + v17) = v21 != 0;
      v22 = *v28;
      ppv = (LPVOID *)&v35;
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v22 + 64))(v28, 3, 0);
      if ( v26 < 0 )
        local_unwind_0(v29, &loc_180021FC8);
      v16[v17++] = *v35;
    }
    if ( v26 == -2146367487 )
      v26 = 0;
    if ( v26 < 0 )
      local_unwind_0(v29, &loc_180021FC8);
    v26 = 0;
    v23 = (UTSemReadWrite *)v40;
    *v40 = v27;
    *a4 = pv;
    *v41 = v13;
    *v42 = (int *)v14;
    *v43 = v16;
  }
  else
  {
    v26 = -2147024882;
    local_unwind_0(v29, &loc_180021FC8);
    v11 = v30;
  }
  if ( v11 )
    UTSemReadWrite::UnlockRead(v23);
  if ( v32 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    v28 = 0;
  }
  if ( v26 < 0 )
  {
    CoTaskMemFree(pv);
    CoTaskMemFree(v36);
    CoTaskMemFree(v37);
    CoTaskMemFree(v38);
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1800218b0  push    rbx
0x1800218b2  push    rsi
0x1800218b3  push    rdi
0x1800218b4  push    r12
0x1800218b6  push    r13
0x1800218b8  push    r14
0x1800218ba  push    r15
0x1800218bc  sub     rsp, 110h
0x1800218c3  mov     rax, cs:__security_cookie
0x1800218ca  xor     rax, rsp
0x1800218cd  mov     [rsp+148h+var_48], rax
0x1800218d5  mov     [rsp+148h+var_E8], rsp
0x1800218da  mov     r13, r9
0x1800218dd  mov     r10, r8
0x1800218e0  mov     [rsp+148h+var_90], r8
0x1800218e8  mov     r9, rdx
0x1800218eb  mov     rax, [rsp+148h+arg_20]
0x1800218f3  mov     [rsp+148h+var_88], rax
0x1800218fb  mov     rdx, [rsp+148h+arg_28]
0x180021903  mov     [rsp+148h+var_80], rdx
0x18002190b  mov     r8, [rsp+148h+arg_30]
0x180021913  mov     [rsp+148h+var_78], r8
0x18002191b  xor     ebx, ebx
0x18002191d  test    r10, r10
0x180021920  jz      loc_18002200E
0x180021926  test    r13, r13
0x180021929  jz      loc_18002200E
0x18002192f  test    rax, rax
0x180021932  jz      loc_18002200E
0x180021938  test    rdx, rdx
0x18002193b  jz      loc_18002200E
0x180021941  test    r8, r8
0x180021944  jz      loc_18002200E
0x18002194a  cmp     [rcx+88h], ebx
0x180021950  jnz     short loc_18002195C
0x180021952  mov     eax, 8011042Ch
0x180021957  jmp     loc_180022013
0x18002195c  mov     [rsp+148h+var_F8], ebx
0x180021960  mov     [rsp+148h+var_F4], ebx
0x180021964  mov     [rsp+148h+pv], rbx
0x18002196c  mov     [rsp+148h+var_B0], rbx
0x180021974  mov     [rsp+148h+var_A8], rbx
0x18002197c  mov     [rsp+148h+var_A0], rbx
0x180021984  mov     [rsp+148h+var_D0], rbx
0x180021989  mov     [rsp+148h+var_F0], rbx
0x18002198e  xorps   xmm0, xmm0
0x180021991  movups  xmmword ptr [rsp+148h+pclsid.Data1], xmm0
0x180021999  mov     [rsp+148h+var_E0], ebx
0x18002199d  mov     [r10], ebx
0x1800219a0  mov     [r13+0], rbx
0x1800219a4  mov     [rax], rbx
0x1800219a7  mov     [rdx], rbx
0x1800219aa  mov     [r8], rbx
0x1800219ad  lea     rdx, [rsp+148h+pclsid]; pclsid
0x1800219b5  mov     rcx, r9; lpsz
0x1800219b8  call    cs:__imp_CLSIDFromString
0x1800219be  mov     [rsp+148h+var_F8], eax
0x1800219c2  mov     eax, [rsp+148h+var_F8]
0x1800219c6  test    eax, eax
0x1800219c8  jns     short loc_1800219E3
0x1800219ca  mov     [rsp+148h+var_F8], 80070057h
0x1800219d2  lea     rdx, loc_180021FC8
0x1800219d9  mov     rcx, [rsp+148h+var_E8]
0x1800219de  call    _local_unwind_0
0x1800219e3  lea     rax, [rsp+148h+var_D0]
0x1800219e8  mov     [rsp+148h+ppv], rax; ppv
0x1800219ed  lea     r9, IID_ISimpleTableDispenser; riid
0x1800219f4  mov     edi, 1
0x1800219f9  mov     r8d, edi; dwClsContext
0x1800219fc  xor     edx, edx; pUnkOuter
0x1800219fe  lea     rcx, clsidSTDISP; rclsid
0x180021a05  call    cs:__imp_CoCreateInstance
0x180021a0b  mov     [rsp+148h+var_F8], eax
0x180021a0f  mov     eax, [rsp+148h+var_F8]
0x180021a13  test    eax, eax
0x180021a15  jns     short loc_180021A4D
0x180021a17  mov     eax, [rsp+148h+var_F8]
0x180021a1b  cmp     eax, 8007000Eh
0x180021a20  jz      short loc_180021A3C
0x180021a22  mov     eax, [rsp+148h+var_F8]
0x180021a26  cmp     eax, 800705AFh
0x180021a2b  jz      short loc_180021A3C
0x180021a2d  mov     eax, [rsp+148h+var_F8]
0x180021a31  cmp     eax, 8007045Bh
0x180021a36  jz      short loc_180021A3C
0x180021a38  mov     eax, [rsp+148h+var_F8]
0x180021a3c  lea     rdx, loc_180021FC8
0x180021a43  mov     rcx, [rsp+148h+var_E8]
0x180021a48  call    _local_unwind_0
0x180021a4d  mov     [rsp+148h+var_68], rbx
0x180021a55  mov     [rsp+148h+var_60], 48h ; 'H'
0x180021a60  mov     [rsp+148h+var_5C], 10h
0x180021a6b  lea     rax, [rsp+148h+pclsid]
0x180021a73  mov     [rsp+148h+var_70], rax
0x180021a7b  call    ?LockRead@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockRead(void)
0x180021a80  mov     [rsp+148h+var_E0], edi
0x180021a84  mov     rcx, [rsp+148h+var_D0]
0x180021a89  mov     rax, [rcx]
0x180021a8c  lea     rdx, [rsp+148h+var_F0]
0x180021a91  mov     [rsp+148h+var_110], rdx
0x180021a96  mov     dword ptr [rsp+148h+var_118], edi
0x180021a9a  mov     dword ptr [rsp+148h+var_120], edi
0x180021a9e  mov     [rsp+148h+ppv], rdi
0x180021aa3  lea     r9, [rsp+148h+var_70]
0x180021aab  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x180021ab2  lea     rdx, didCOMSERVICES
0x180021ab9  mov     rax, [rax+18h]
0x180021abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac2  mov     [rsp+148h+var_F8], eax
0x180021ac6  mov     eax, [rsp+148h+var_F8]
0x180021aca  test    eax, eax
0x180021acc  jns     short loc_180021B04
0x180021ace  mov     eax, [rsp+148h+var_F8]
0x180021ad2  cmp     eax, 8007000Eh
0x180021ad7  jz      short loc_180021AF3
0x180021ad9  mov     eax, [rsp+148h+var_F8]
0x180021add  cmp     eax, 800705AFh
0x180021ae2  jz      short loc_180021AF3
0x180021ae4  mov     eax, [rsp+148h+var_F8]
0x180021ae8  cmp     eax, 8007045Bh
0x180021aed  jz      short loc_180021AF3
0x180021aef  mov     eax, [rsp+148h+var_F8]
0x180021af3  lea     rdx, loc_180021FC8
0x180021afa  mov     rcx, [rsp+148h+var_E8]
0x180021aff  call    _local_unwind_0
0x180021b04  mov     rcx, [rsp+148h+var_F0]
0x180021b09  mov     rax, [rcx]
0x180021b0c  mov     rax, [rax+18h]
0x180021b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b15  mov     [rsp+148h+var_F8], eax
0x180021b19  mov     eax, [rsp+148h+var_F8]
0x180021b1d  test    eax, eax
0x180021b1f  jns     short loc_180021B57
0x180021b21  mov     eax, [rsp+148h+var_F8]
0x180021b25  cmp     eax, 8007000Eh
0x180021b2a  jz      short loc_180021B46
0x180021b2c  mov     eax, [rsp+148h+var_F8]
0x180021b30  cmp     eax, 800705AFh
0x180021b35  jz      short loc_180021B46
0x180021b37  mov     eax, [rsp+148h+var_F8]
0x180021b3b  cmp     eax, 8007045Bh
0x180021b40  jz      short loc_180021B46
0x180021b42  mov     eax, [rsp+148h+var_F8]
0x180021b46  lea     rdx, loc_180021FC8
0x180021b4d  mov     rcx, [rsp+148h+var_E8]
0x180021b52  call    _local_unwind_0
0x180021b57  call    ?UnlockRead@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::UnlockRead(void)
0x180021b5c  mov     r14d, ebx
0x180021b5f  mov     [rsp+148h+var_E0], ebx
0x180021b63  mov     rcx, [rsp+148h+var_F0]
0x180021b68  mov     rax, [rcx]
0x180021b6b  mov     [rsp+148h+var_108], rbx
0x180021b70  lea     rdx, [rsp+148h+var_F4]
0x180021b75  mov     [rsp+148h+var_110], rdx
0x180021b7a  mov     [rsp+148h+var_118], rbx
0x180021b7f  mov     [rsp+148h+var_120], rbx
0x180021b84  mov     [rsp+148h+ppv], rbx
0x180021b89  xor     r9d, r9d
0x180021b8c  xor     r8d, r8d
0x180021b8f  xor     edx, edx
0x180021b91  mov     rax, [rax+48h]
0x180021b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b9a  mov     [rsp+148h+var_F8], eax
0x180021b9e  mov     eax, [rsp+148h+var_F8]
0x180021ba2  test    eax, eax
0x180021ba4  jns     short loc_180021BDC
0x180021ba6  mov     eax, [rsp+148h+var_F8]
0x180021baa  cmp     eax, 8007000Eh
0x180021baf  jz      short loc_180021BCB
0x180021bb1  mov     eax, [rsp+148h+var_F8]
0x180021bb5  cmp     eax, 800705AFh
0x180021bba  jz      short loc_180021BCB
0x180021bbc  mov     eax, [rsp+148h+var_F8]
0x180021bc0  cmp     eax, 8007045Bh
0x180021bc5  jz      short loc_180021BCB
0x180021bc7  mov     eax, [rsp+148h+var_F8]
0x180021bcb  lea     rdx, loc_180021FC8
0x180021bd2  mov     rcx, [rsp+148h+var_E8]
0x180021bd7  call    _local_unwind_0
0x180021bdc  cmp     [rsp+148h+var_F4], ebx
0x180021be0  jnz     short loc_180021BFB
0x180021be2  mov     [rsp+148h+var_F8], 80040154h
0x180021bea  lea     rdx, loc_180021FC8
0x180021bf1  mov     rcx, [rsp+148h+var_E8]
0x180021bf6  call    _local_unwind_0
0x180021bfb  mov     ecx, [rsp+148h+var_F4]
0x180021bff  shl     rcx, 4; cb
0x180021c03  call    cs:__imp_CoTaskMemAlloc
0x180021c09  mov     rdi, rax
0x180021c0c  mov     [rsp+148h+pv], rax
0x180021c14  mov     ecx, [rsp+148h+var_F4]
0x180021c18  shl     rcx, 4; cb
0x180021c1c  call    cs:__imp_CoTaskMemAlloc
0x180021c22  mov     r15, rax
0x180021c25  mov     [rsp+148h+var_B0], rax
0x180021c2d  mov     ecx, [rsp+148h+var_F4]
0x180021c31  shl     rcx, 2; cb
0x180021c35  call    cs:__imp_CoTaskMemAlloc
0x180021c3b  mov     r12, rax
0x180021c3e  mov     [rsp+148h+var_A8], rax
0x180021c46  mov     ecx, [rsp+148h+var_F4]
0x180021c4a  shl     rcx, 2; cb
0x180021c4e  call    cs:__imp_CoTaskMemAlloc
0x180021c54  mov     rsi, rax
0x180021c57  mov     [rsp+148h+var_A0], rax
0x180021c5f  test    rdi, rdi
0x180021c62  jz      loc_180021F67
0x180021c68  test    r15, r15
0x180021c6b  jz      loc_180021F67
0x180021c71  test    r12, r12
0x180021c74  jz      loc_180021F67
0x180021c7a  test    rax, rax
0x180021c7d  jz      loc_180021F67
0x180021c83  mov     edi, ebx
0x180021c85  mov     [rsp+148h+var_C0], ebx
0x180021c8c  mov     rcx, [rsp+148h+var_F0]
0x180021c91  mov     rax, [rcx]
0x180021c94  mov     rax, [rax+28h]
0x180021c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c9d  mov     [rsp+148h+var_F8], eax
0x180021ca1  mov     eax, [rsp+148h+var_F8]
0x180021ca5  test    eax, eax
0x180021ca7  jnz     loc_180021ED9
0x180021cad  mov     [rsp+148h+var_D8], rbx
0x180021cb2  mov     [rsp+148h+var_B8], rbx
0x180021cba  mov     rcx, [rsp+148h+var_F0]
0x180021cbf  mov     rax, [rcx]
0x180021cc2  lea     rdx, [rsp+148h+var_D8]
0x180021cc7  mov     [rsp+148h+ppv], rdx
0x180021ccc  xor     r9d, r9d
0x180021ccf  xor     r8d, r8d
0x180021cd2  lea     edx, [r9+1]
0x180021cd6  mov     rax, [rax+40h]
0x180021cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cdf  mov     [rsp+148h+var_F8], eax
0x180021ce3  mov     eax, [rsp+148h+var_F8]
0x180021ce7  test    eax, eax
0x180021ce9  jns     short loc_180021D21
0x180021ceb  mov     eax, [rsp+148h+var_F8]
0x180021cef  cmp     eax, 8007000Eh
0x180021cf4  jz      short loc_180021D10
0x180021cf6  mov     eax, [rsp+148h+var_F8]
0x180021cfa  cmp     eax, 800705AFh
0x180021cff  jz      short loc_180021D10
0x180021d01  mov     eax, [rsp+148h+var_F8]
0x180021d05  cmp     eax, 8007045Bh
0x180021d0a  jz      short loc_180021D10
0x180021d0c  mov     eax, [rsp+148h+var_F8]
0x180021d10  lea     rdx, loc_180021FC8
0x180021d17  mov     rcx, [rsp+148h+var_E8]
0x180021d1c  call    _local_unwind_0
0x180021d21  mov     ecx, edi
0x180021d23  shl     rcx, 4
0x180021d27  mov     [rsp+148h+var_98], rcx
0x180021d2f  mov     rax, [rsp+148h+var_D8]
0x180021d34  movups  xmm0, xmmword ptr [rax]
0x180021d37  mov     rax, [rsp+148h+pv]
0x180021d3f  movdqu  xmmword ptr [rcx+rax], xmm0
0x180021d44  mov     rcx, [rsp+148h+var_F0]
0x180021d49  mov     rax, [rcx]
0x180021d4c  lea     rdx, [rsp+148h+var_D8]
0x180021d51  mov     [rsp+148h+ppv], rdx
0x180021d56  xor     r9d, r9d
0x180021d59  xor     r8d, r8d
0x180021d5c  lea     edx, [r9+4]
0x180021d60  mov     rax, [rax+40h]
0x180021d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d69  mov     [rsp+148h+var_F8], eax
0x180021d6d  mov     eax, [rsp+148h+var_F8]
0x180021d71  test    eax, eax
0x180021d73  jns     short loc_180021DAB
0x180021d75  mov     eax, [rsp+148h+var_F8]
0x180021d79  cmp     eax, 8007000Eh
0x180021d7e  jz      short loc_180021D9A
0x180021d80  mov     eax, [rsp+148h+var_F8]
0x180021d84  cmp     eax, 800705AFh
0x180021d89  jz      short loc_180021D9A
0x180021d8b  mov     eax, [rsp+148h+var_F8]
0x180021d8f  cmp     eax, 8007045Bh
0x180021d94  jz      short loc_180021D9A
0x180021d96  mov     eax, [rsp+148h+var_F8]
0x180021d9a  lea     rdx, loc_180021FC8
0x180021da1  mov     rcx, [rsp+148h+var_E8]
0x180021da6  call    _local_unwind_0
0x180021dab  mov     rax, [rsp+148h+var_D8]
0x180021db0  movups  xmm0, xmmword ptr [rax]
0x180021db3  mov     rax, [rsp+148h+var_98]
0x180021dbb  movdqu  xmmword ptr [rax+r15], xmm0
0x180021dc1  mov     rcx, [rsp+148h+var_F0]
0x180021dc6  mov     rax, [rcx]
0x180021dc9  lea     rdx, [rsp+148h+var_D8]
0x180021dce  mov     [rsp+148h+ppv], rdx
0x180021dd3  xor     r9d, r9d
0x180021dd6  xor     r8d, r8d
0x180021dd9  lea     edx, [r9+2]
0x180021ddd  mov     rax, [rax+40h]
0x180021de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021de6  mov     [rsp+148h+var_F8], eax
0x180021dea  mov     eax, [rsp+148h+var_F8]
0x180021dee  test    eax, eax
  ... truncated ...
```
