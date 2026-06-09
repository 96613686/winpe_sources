# GetConnectivityCapability(_CONNECTIVITY_CAPABILITY *,_CONNECTIVITY_CAPABILITY *,ulong *,ulong *)

- ea: `0x180024a6c`
- end: `0x180024d7a`
- name: `?GetConnectivityCapability@@YAKPEAW4_CONNECTIVITY_CAPABILITY@@0PEAK1@Z`
- size: `782`
- prototype: `__int64 __fastcall(enum _CONNECTIVITY_CAPABILITY *, enum _CONNECTIVITY_CAPABILITY *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002503c`

## callees

- `0x180008c84`
- `0x180024a6c`
- `0x1800261b0`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024b06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024b06`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180024aa9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180024aa9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024b30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024cfd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024d56`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024b30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024cfd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024d56`

## pseudocode

```c
__int64 __fastcall GetConnectivityCapability(
        enum _CONNECTIVITY_CAPABILITY *a1,
        enum _CONNECTIVITY_CAPABILITY *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  char v6; // bl
  HRESULT v7; // eax
  unsigned int v8; // ecx
  HRESULT v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // esi
  __int64 *v15; // rdi
  __int64 *v16; // r15
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  _QWORD *v20; // rdi
  _QWORD *v21; // rdi
  _QWORD *v22; // rdi
  _QWORD *v23; // rdi
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v28; // [rsp+50h] [rbp-B0h]
  char v29; // [rsp+58h] [rbp-A8h]
  _QWORD v30[20]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[8]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( !a1 )
    return 13;
  v6 = 1;
  v7 = CoInitializeEx(0, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    v6 = 0;
    if ( v7 != -2147417850 )
    {
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v7;
      return v8;
    }
  }
  *(_DWORD *)a1 = 0;
  ppv = 0;
  v9 = CoCreateInstance(
         &GUID_a47979d2_c419_11d9_a5b4_001185ad2b89,
         0,
         4u,
         &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
         &ppv);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
LABEL_11:
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&ppv);
    if ( v6 )
      CoUninitialize();
    return v10;
  }
  v25 = 0;
  v11 = *(_QWORD *)ppv;
  v25 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(v11 + 232))(ppv, 1, &v25);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v12;
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v25);
    goto LABEL_11;
  }
  while ( 1 )
  {
    memset_0(v30, 0, sizeof(v30));
    v28 = v30;
    v29 = 1;
    v27 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, int *))(*(_QWORD *)v25 + 24LL))(v25, 20, v30, &v27);
    v14 = v13;
    if ( v13 < 0 )
      break;
    if ( !v27 )
    {
      v22 = v30;
      do
      {
        if ( *v22 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 16LL))(*v22);
        ++v22;
      }
      while ( v22 != v31 );
      goto LABEL_44;
    }
    v15 = v30;
    v16 = &v30[v27];
    if ( v30 != v16 )
    {
      do
      {
        v17 = *v15;
        v24 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v24);
        if ( v18 >= 0 )
        {
          if ( (v24 & 8) != 0 )
          {
            *(_DWORD *)a1 = 2;
          }
          else if ( *(_DWORD *)a1 != 2 && (v24 & 4) != 0 )
          {
            *(_DWORD *)a1 = 1;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x58, v19, (const char *)(unsigned int)v18);
        }
        ++v15;
      }
      while ( v15 != v16 );
    }
    if ( v14 == 1 )
    {
      v21 = v30;
      do
      {
        if ( *v21 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 16LL))(*v21);
        ++v21;
      }
      while ( v21 != v31 );
LABEL_44:
      ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v25);
      ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&ppv);
      if ( v6 )
        CoUninitialize();
      return 0;
    }
    v20 = v30;
    do
    {
      if ( *v20 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 16LL))(*v20);
      ++v20;
    }
    while ( v20 != v31 );
  }
  if ( (v13 & 0x1FFF0000) == 0x70000 )
    v14 = (unsigned __int16)v13;
  v23 = v30;
  do
  {
    if ( *v23 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 16LL))(*v23);
    ++v23;
  }
  while ( v23 != v31 );
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v25);
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&ppv);
  if ( v6 )
    CoUninitialize();
  return v14;
}

```

## disassembly

```asm
0x180024a6c  push    rbp
0x180024a6e  push    rbx
0x180024a6f  push    rsi
0x180024a70  push    rdi
0x180024a71  push    r14
0x180024a73  push    r15
0x180024a75  lea     rbp, [rsp-18h]
0x180024a7a  sub     rsp, 118h
0x180024a81  mov     rax, cs:__security_cookie
0x180024a88  xor     rax, rsp
0x180024a8b  mov     [rbp+40h+var_40], rax
0x180024a8f  mov     r14, rcx
0x180024a92  test    rcx, rcx
0x180024a95  jnz     short loc_180024A9F
0x180024a97  lea     eax, [rcx+0Dh]
0x180024a9a  jmp     loc_180024D5E
0x180024a9f  mov     bl, 1
0x180024aa1  mov     [rsp+140h+var_110], bl
0x180024aa5  xor     edx, edx; dwCoInit
0x180024aa7  xor     ecx, ecx; pvReserved
0x180024aa9  call    cs:__imp_CoInitializeEx
0x180024aaf  mov     ecx, eax
0x180024ab1  test    eax, eax
0x180024ab3  jns     short loc_180024AD8
0x180024ab5  xor     bl, bl
0x180024ab7  mov     [rsp+140h+var_110], bl
0x180024abb  cmp     eax, 80010106h
0x180024ac0  jz      short loc_180024AD8
0x180024ac2  and     eax, 1FFF0000h
0x180024ac7  cmp     eax, 70000h
0x180024acc  jnz     short loc_180024AD1
0x180024ace  movzx   ecx, cx
0x180024ad1  mov     eax, ecx
0x180024ad3  jmp     loc_180024D5E
0x180024ad8  mov     dword ptr [r14], 0
0x180024adf  mov     [rsp+140h+var_100], 0
0x180024ae8  lea     rax, [rsp+140h+var_100]
0x180024aed  mov     [rsp+140h+ppv], rax; int
0x180024af2  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180024af9  xor     edx, edx; pUnkOuter
0x180024afb  lea     r8d, [rdx+4]; dwClsContext
0x180024aff  lea     rcx, _GUID_a47979d2_c419_11d9_a5b4_001185ad2b89; rclsid
0x180024b06  call    cs:__imp_CoCreateInstance
0x180024b0c  mov     edi, eax
0x180024b0e  test    eax, eax
0x180024b10  jns     short loc_180024B3D
0x180024b12  and     eax, 1FFF0000h
0x180024b17  cmp     eax, 70000h
0x180024b1c  jnz     short loc_180024B21
0x180024b1e  movzx   edi, di
0x180024b21  lea     rcx, [rsp+140h+var_100]
0x180024b26  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024b2b  nop
0x180024b2c  test    bl, bl
0x180024b2e  jz      short loc_180024B36
0x180024b30  call    cs:__imp_CoUninitialize
0x180024b36  mov     eax, edi
0x180024b38  jmp     loc_180024D5E
0x180024b3d  mov     [rsp+140h+var_108], 0
0x180024b46  mov     rcx, [rsp+140h+var_100]
0x180024b4b  mov     rax, [rcx]
0x180024b4e  mov     [rsp+140h+var_108], 0
0x180024b57  lea     r8, [rsp+140h+var_108]
0x180024b5c  mov     edx, 1
0x180024b61  mov     rax, [rax+0E8h]
0x180024b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b6d  mov     edi, eax
0x180024b6f  test    eax, eax
0x180024b71  jns     short loc_180024B8E
0x180024b73  and     eax, 1FFF0000h
0x180024b78  cmp     eax, 70000h
0x180024b7d  jnz     short loc_180024B82
0x180024b7f  movzx   edi, di
0x180024b82  lea     rcx, [rsp+140h+var_108]
0x180024b87  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024b8c  jmp     short loc_180024B21
0x180024b8e  xor     edx, edx; Val
0x180024b90  mov     r8d, 0A0h; Size
0x180024b96  lea     rcx, [rsp+140h+var_E0]; void *
0x180024b9b  call    memset_0
0x180024ba0  lea     rax, [rsp+140h+var_E0]
0x180024ba5  mov     [rsp+140h+var_F0], rax
0x180024baa  mov     [rsp+140h+var_E8], 1
0x180024baf  mov     [rsp+140h+var_F8], 0
0x180024bb7  mov     rcx, [rsp+140h+var_108]
0x180024bbc  mov     rax, [rcx]
0x180024bbf  lea     r9, [rsp+140h+var_F8]
0x180024bc4  lea     r8, [rsp+140h+var_E0]
0x180024bc9  mov     edx, 14h
0x180024bce  mov     rax, [rax+18h]
0x180024bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd7  mov     esi, eax
0x180024bd9  test    eax, eax
0x180024bdb  js      loc_180024D07
0x180024be1  mov     eax, [rsp+140h+var_F8]
0x180024be5  test    eax, eax
0x180024be7  jz      loc_180024CBD
0x180024bed  lea     rdi, [rsp+140h+var_E0]
0x180024bf2  lea     r15, [rsp+140h+var_E0]
0x180024bf7  lea     r15, [r15+rax*8]
0x180024bfb  lea     rax, [rsp+140h+var_E0]
0x180024c00  cmp     rax, r15
0x180024c03  jz      short loc_180024C65
0x180024c05  mov     rcx, [rdi]
0x180024c08  mov     [rsp+140h+var_10C], 0
0x180024c10  mov     rax, [rcx]
0x180024c13  lea     rdx, [rsp+140h+var_10C]
0x180024c18  mov     rax, [rax+38h]
0x180024c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c21  mov     rcx, [rbp+48h]; this
0x180024c25  test    eax, eax
0x180024c27  jns     short loc_180024C38
0x180024c29  mov     r9d, eax; char *
0x180024c2c  mov     edx, 58h ; 'X'; void *
0x180024c31  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024c36  jmp     short loc_180024C5C
0x180024c38  test    byte ptr [rsp+140h+var_10C], 8
0x180024c3d  jz      short loc_180024C48
0x180024c3f  mov     dword ptr [r14], 2
0x180024c46  jmp     short loc_180024C5C
0x180024c48  cmp     dword ptr [r14], 2
0x180024c4c  jz      short loc_180024C5C
0x180024c4e  test    byte ptr [rsp+140h+var_10C], 4
0x180024c53  jz      short loc_180024C5C
0x180024c55  mov     dword ptr [r14], 1
0x180024c5c  add     rdi, 8
0x180024c60  cmp     rdi, r15
0x180024c63  jnz     short loc_180024C05
0x180024c65  cmp     esi, 1
0x180024c68  jz      short loc_180024C95
0x180024c6a  lea     rdi, [rsp+140h+var_E0]
0x180024c6f  mov     rcx, [rdi]
0x180024c72  test    rcx, rcx
0x180024c75  jz      short loc_180024C83
0x180024c77  mov     rax, [rcx]
0x180024c7a  mov     rax, [rax+10h]
0x180024c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c83  add     rdi, 8
0x180024c87  lea     rax, [rbp+40h+var_40]
0x180024c8b  cmp     rdi, rax
0x180024c8e  jnz     short loc_180024C6F
0x180024c90  jmp     loc_180024B8E
0x180024c95  lea     rdi, [rsp+140h+var_E0]
0x180024c9a  mov     rcx, [rdi]
0x180024c9d  test    rcx, rcx
0x180024ca0  jz      short loc_180024CAE
0x180024ca2  mov     rax, [rcx]
0x180024ca5  mov     rax, [rax+10h]
0x180024ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cae  add     rdi, 8
0x180024cb2  lea     rax, [rbp+40h+var_40]
0x180024cb6  cmp     rdi, rax
0x180024cb9  jnz     short loc_180024C9A
0x180024cbb  jmp     short loc_180024CE3
0x180024cbd  lea     rdi, [rsp+140h+var_E0]
0x180024cc2  mov     rcx, [rdi]
0x180024cc5  test    rcx, rcx
0x180024cc8  jz      short loc_180024CD6
0x180024cca  mov     rax, [rcx]
0x180024ccd  mov     rax, [rax+10h]
0x180024cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd6  add     rdi, 8
0x180024cda  lea     rax, [rbp+40h+var_40]
0x180024cde  cmp     rdi, rax
0x180024ce1  jnz     short loc_180024CC2
0x180024ce3  lea     rcx, [rsp+140h+var_108]
0x180024ce8  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024ced  nop
0x180024cee  lea     rcx, [rsp+140h+var_100]
0x180024cf3  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024cf8  nop
0x180024cf9  test    bl, bl
0x180024cfb  jz      short loc_180024D03
0x180024cfd  call    cs:__imp_CoUninitialize
0x180024d03  xor     eax, eax
0x180024d05  jmp     short loc_180024D5E
0x180024d07  and     eax, 1FFF0000h
0x180024d0c  cmp     eax, 70000h
0x180024d11  jnz     short loc_180024D16
0x180024d13  movzx   esi, si
0x180024d16  lea     rdi, [rsp+140h+var_E0]
0x180024d1b  mov     rcx, [rdi]
0x180024d1e  test    rcx, rcx
0x180024d21  jz      short loc_180024D2F
0x180024d23  mov     rax, [rcx]
0x180024d26  mov     rax, [rax+10h]
0x180024d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d2f  add     rdi, 8
0x180024d33  lea     rax, [rbp+40h+var_40]
0x180024d37  cmp     rdi, rax
0x180024d3a  jnz     short loc_180024D1B
0x180024d3c  lea     rcx, [rsp+140h+var_108]
0x180024d41  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024d46  nop
0x180024d47  lea     rcx, [rsp+140h+var_100]
0x180024d4c  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180024d51  nop
0x180024d52  test    bl, bl
0x180024d54  jz      short loc_180024D5C
0x180024d56  call    cs:__imp_CoUninitialize
0x180024d5c  mov     eax, esi
0x180024d5e  mov     rcx, [rbp+40h+var_40]
0x180024d62  xor     rcx, rsp; StackCookie
0x180024d65  call    __security_check_cookie
0x180024d6a  add     rsp, 118h
0x180024d71  pop     r15
0x180024d73  pop     r14
0x180024d75  pop     rdi
0x180024d76  pop     rsi
0x180024d77  pop     rbx
0x180024d78  pop     rbp
0x180024d79  retn
```
