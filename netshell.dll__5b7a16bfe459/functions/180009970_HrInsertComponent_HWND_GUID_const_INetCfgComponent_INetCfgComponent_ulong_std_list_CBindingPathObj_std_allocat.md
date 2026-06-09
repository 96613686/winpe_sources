# HrInsertComponent(HWND__ *,_GUID const *,INetCfgComponent *,INetCfgComponent *,ulong,std::list<CBindingPathObj *,std::allocator<CBindingPathObj *>> *,int *)

- ea: `0x180009970`
- end: `0x180009d12`
- name: `?HrInsertComponent@@YAJPEAUHWND__@@PEBU_GUID@@PEAUINetCfgComponent@@2KPEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@PEAH@Z`
- size: `930`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, struct _GUID *@<rdx>, struct INetCfgComponent *@<r8>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031580`

## callees

- `0x180002010`
- `0x180009970`
- `0x18000a45c`
- `0x18000a904`
- `0x180018d74`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x180033748`
- `0x180034b34`
- `0x18004030c`
- `0x180062124`
- `0x180065010`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180009ba2`
- `ntdll!RtlGetNtProductType` at `0x180009ba2`
- `USER32!GetWindowLongPtrW` at `0x1800099be`
- `USER32!GetWindowLongPtrW` at `0x1800099be`
- `USER32!SendMessageW` at `0x180009cc1`
- `USER32!SendMessageW` at `0x180009cc1`
- `USER32!GetParent` at `0x1800099b0`
- `USER32!GetParent` at `0x1800099b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009b8f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009b8f`
- `ole32!CoTaskMemFree` at `0x180009bb8`
- `ole32!CoTaskMemFree` at `0x180009cce`
- `ole32!CoTaskMemFree` at `0x180009cd9`
- `ole32!CoTaskMemFree` at `0x180009bb8`
- `ole32!CoTaskMemFree` at `0x180009cce`
- `ole32!CoTaskMemFree` at `0x180009cd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrInsertComponent(
        HWND hWnd,
        struct _GUID *a2,
        struct IUnknown *a3,
        __int64 a4,
        int a5,
        __int64 **a6,
        unsigned __int16 *a7)
{
  unsigned __int16 *v10; // rsi
  HWND Parent; // rax
  struct _SP_CLASSIMAGELIST_DATA *WindowLongPtrW; // rbx
  __int64 result; // rax
  int v14; // edi
  __int64 v15; // rax
  BOOL v16; // esi
  __int64 *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  struct IUnknown **v20; // rbx
  CComponentObj *v21; // rax
  int v22; // [rsp+20h] [rbp-B1h] BYREF
  _NT_PRODUCT_TYPE ProductType[2]; // [rsp+28h] [rbp-A9h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-A1h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-99h] BYREF
  struct IUnknown *v26; // [rsp+40h] [rbp-91h] BYREF
  int lParam; // [rsp+50h] [rbp-81h] BYREF
  _DWORD lParam_4[5]; // [rsp+54h] [rbp-7Dh] BYREF
  struct IUnknown *v29; // [rsp+68h] [rbp-69h]
  _NT_PRODUCT_TYPE v30; // [rsp+74h] [rbp-5Dh]
  struct IUnknown **v31; // [rsp+78h] [rbp-59h]
  __int128 Buf2; // [rsp+B0h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+C0h] [rbp-11h] BYREF

  v10 = a7;
  v25 = a7;
  Parent = GetParent(hWnd);
  WindowLongPtrW = (struct _SP_CLASSIMAGELIST_DATA *)GetWindowLongPtrW(Parent, -21);
  pv = WindowLongPtrW;
  v26 = 0;
  result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a3->lpVtbl->QueryInterface)(
             a3,
             &IID_INetCfgComponentBindings,
             &v26);
  if ( !(_DWORD)result )
  {
    v22 = 0;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, int *))a3->lpVtbl[2].AddRef)(a3, &v22);
    if ( v14 >= 0 && (v22 & 0x40400) != 0 )
      goto LABEL_7;
    v15 = *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 == *(_QWORD *)&a2->Data1 )
      v15 = *(_QWORD *)GUID_DEVCLASS_NETTRANS.Data4 - *(_QWORD *)a2->Data4;
    if ( !v15 )
    {
LABEL_7:
      v16 = 0;
      Buf2 = 0;
      ((void (__fastcall *)(struct IUnknown *, __int128 *))a3->lpVtbl[2].Release)(a3, &Buf2);
      v17 = *a6;
      while ( 1 )
      {
        v17 = (__int64 *)*v17;
        if ( v17 == *a6 )
          break;
        if ( v16 )
          goto LABEL_18;
        *(_QWORD *)ProductType = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _NT_PRODUCT_TYPE *))(**(_QWORD **)v17[2] + 64LL))(
                *(_QWORD *)v17[2],
                ProductType);
        if ( !v14 )
        {
          v18 = *(_QWORD *)ProductType;
          if ( *(struct IUnknown **)ProductType == a3 )
          {
            v16 = 1;
          }
          else
          {
            Buf1 = 0;
            (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)ProductType + 64LL))(
              *(_QWORD *)ProductType,
              &Buf1);
            v16 = memcmp_0(&Buf1, &Buf2, 0x10u) == 0;
            v18 = *(_QWORD *)ProductType;
          }
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
      if ( !v16 )
      {
        v14 = 1;
        goto LABEL_40;
      }
LABEL_18:
      WindowLongPtrW = (struct _SP_CLASSIMAGELIST_DATA *)pv;
      v10 = v25;
    }
    if ( !v14 )
    {
      v25 = 0;
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 **))a3->lpVtbl[1].QueryInterface)(a3, &v25);
      if ( v14 >= 0 )
      {
        pv = 0;
        v19 = *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 - *(_QWORD *)&a2->Data1;
        if ( *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 == *(_QWORD *)&a2->Data1 )
          v19 = *(_QWORD *)GUID_DEVCLASS_NETTRANS.Data4 - *(_QWORD *)a2->Data4;
        if ( !v19 )
        {
          *(_QWORD *)&Buf2 = 0;
          if ( ((int (__fastcall *)(struct IUnknown *, __int128 *))a3->lpVtbl[2].QueryInterface)(a3, &Buf2) >= 0 )
          {
            if ( !lstrcmpiW(L"ms_tcpip", (LPCWSTR)Buf2) )
            {
              ProductType[0] = 0;
              RtlGetNtProductType(ProductType);
              if ( ProductType[0] == NtProductLanManNt )
                v22 |= 0x20u;
            }
            CoTaskMemFree((LPVOID)Buf2);
          }
        }
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))a3->lpVtbl[1].Release)(a3, &pv);
        if ( v14 >= 0 )
        {
          memset_0(lParam_4, 0, 0x54u);
          lParam = 15;
          if ( WindowLongPtrW )
          {
            ProductType[0] = 0;
            HrSetupDiGetClassImageIndex(WindowLongPtrW, a2, (int *)ProductType);
            v30 = ProductType[0];
          }
          lParam_4[0] = *(_DWORD *)v10;
          v20 = (struct IUnknown **)MemAlloc(0x28u);
          if ( v20 )
          {
            v20[2] = (struct IUnknown *)SzDupSz(v25);
            v20[3] = (struct IUnknown *)SzDupSz((const unsigned __int16 *)pv);
            *((_DWORD *)v20 + 8) = v22;
            *v20 = a3;
            AddRefObj(a3);
            v21 = (CComponentObj *)MemAlloc(0x28u);
            *(_QWORD *)&Buf2 = v21;
            if ( v21 )
              v21 = CComponentObj::CComponentObj(v21, (struct INetCfgComponent *)a3);
            v20[1] = (struct IUnknown *)v21;
            if ( v21 )
            {
              v14 = CComponentObj::HrInit(v21, a6);
              if ( v14 < 0 )
                v14 = 0;
            }
            v31 = v20;
            v29 = v20[2];
            lParam_4[2] = 0x2000;
            SendMessageW(hWnd, 0x104Du, 0, (LPARAM)&lParam);
            ++*(_DWORD *)v10;
            CoTaskMemFree(pv);
          }
        }
        CoTaskMemFree(v25);
      }
    }
LABEL_40:
    ReleaseObj(v26);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x180009970  mov     [rsp-8+arg_18], rbx
0x180009975  push    rbp
0x180009976  push    rsi
0x180009977  push    rdi
0x180009978  push    r12
0x18000997a  push    r13
0x18000997c  push    r14
0x18000997e  push    r15
0x180009980  lea     rbp, [rsp-0Fh]
0x180009985  sub     rsp, 0E0h
0x18000998c  mov     rax, cs:__security_cookie
0x180009993  xor     rax, rsp
0x180009996  mov     [rbp+3Fh+var_40], rax
0x18000999a  mov     r15, r8
0x18000999d  mov     r12, rdx
0x1800099a0  mov     r13, rcx
0x1800099a3  mov     r14, [rbp+3Fh+arg_28]
0x1800099a7  mov     rsi, [rbp+3Fh+arg_30]
0x1800099ab  mov     [rsp+110h+var_D8], rsi
0x1800099b0  call    cs:__imp_GetParent
0x1800099b6  mov     rcx, rax; hWnd
0x1800099b9  mov     edx, 0FFFFFFEBh; nIndex
0x1800099be  call    cs:__imp_GetWindowLongPtrW
0x1800099c4  mov     rbx, rax
0x1800099c7  mov     [rsp+110h+pv], rax
0x1800099cc  xor     edi, edi
0x1800099ce  mov     [rsp+110h+var_D0], rdi
0x1800099d3  mov     rcx, [r15]
0x1800099d6  mov     rax, [rcx]
0x1800099d9  lea     r8, [rsp+110h+var_D0]
0x1800099de  lea     rdx, IID_INetCfgComponentBindings
0x1800099e5  mov     rcx, r15
0x1800099e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ed  test    eax, eax
0x1800099ef  jnz     loc_180009CEB
0x1800099f5  mov     [rsp+110h+var_F0], edi
0x1800099f9  mov     rax, [r15]
0x1800099fc  lea     rdx, [rsp+110h+var_F0]
0x180009a01  mov     rcx, r15
0x180009a04  mov     rax, [rax+38h]
0x180009a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a0d  mov     edi, eax
0x180009a0f  test    eax, eax
0x180009a11  js      short loc_180009A1D
0x180009a13  test    [rsp+110h+var_F0], 40400h
0x180009a1b  jnz     short loc_180009A3F
0x180009a1d  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data1
0x180009a24  sub     rax, [r12]
0x180009a28  jnz     short loc_180009A36
0x180009a2a  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data4
0x180009a31  sub     rax, [r12+8]
0x180009a36  test    rax, rax
0x180009a39  jnz     loc_180009B15
0x180009a3f  xor     esi, esi
0x180009a41  xorps   xmm0, xmm0
0x180009a44  movups  [rbp+3Fh+Buf2], xmm0
0x180009a48  mov     rax, [r15]
0x180009a4b  lea     rdx, [rbp+3Fh+Buf2]
0x180009a4f  mov     rcx, r15
0x180009a52  mov     rax, [rax+40h]
0x180009a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5b  mov     rbx, [r14]
0x180009a5e  mov     rbx, [rbx]
0x180009a61  cmp     rbx, [r14]
0x180009a64  jz      loc_180009AFD
0x180009a6a  test    esi, esi
0x180009a6c  jnz     loc_180009B0B
0x180009a72  mov     qword ptr [rsp+110h+ProductType], 0
0x180009a7b  mov     rax, [rbx+10h]
0x180009a7f  mov     rcx, [rax]
0x180009a82  mov     rax, [rcx]
0x180009a85  lea     rdx, [rsp+110h+ProductType]
0x180009a8a  mov     rax, [rax+40h]
0x180009a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a93  mov     edi, eax
0x180009a95  test    eax, eax
0x180009a97  jnz     short loc_180009A5E
0x180009a99  mov     rcx, qword ptr [rsp+110h+ProductType]
0x180009a9e  cmp     rcx, r15
0x180009aa1  jnz     short loc_180009AAA
0x180009aa3  mov     esi, 1
0x180009aa8  jmp     short loc_180009AE3
0x180009aaa  xorps   xmm0, xmm0
0x180009aad  movups  [rbp+3Fh+Buf1], xmm0
0x180009ab1  mov     rax, [rcx]
0x180009ab4  lea     rdx, [rbp+3Fh+Buf1]
0x180009ab8  mov     rax, [rax+40h]
0x180009abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac1  mov     r8d, 10h; Size
0x180009ac7  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x180009acb  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x180009acf  call    memcmp_0
0x180009ad4  test    eax, eax
0x180009ad6  mov     eax, 1
0x180009adb  cmovz   esi, eax
0x180009ade  mov     rcx, qword ptr [rsp+110h+ProductType]
0x180009ae3  test    rcx, rcx
0x180009ae6  jz      loc_180009A5E
0x180009aec  mov     rax, [rcx]
0x180009aef  mov     rax, [rax+10h]
0x180009af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009af8  jmp     loc_180009A5E
0x180009afd  test    esi, esi
0x180009aff  jnz     short loc_180009B0B
0x180009b01  mov     edi, 1
0x180009b06  jmp     loc_180009CDF
0x180009b0b  mov     rbx, [rsp+110h+pv]
0x180009b10  mov     rsi, [rsp+110h+var_D8]
0x180009b15  test    edi, edi
0x180009b17  jnz     loc_180009CDF
0x180009b1d  mov     [rsp+110h+var_D8], 0
0x180009b26  mov     rax, [r15]
0x180009b29  lea     rdx, [rsp+110h+var_D8]
0x180009b2e  mov     rcx, r15
0x180009b31  mov     rax, [rax+18h]
0x180009b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3a  mov     edi, eax
0x180009b3c  test    eax, eax
0x180009b3e  js      loc_180009CDF
0x180009b44  xor     edi, edi
0x180009b46  mov     [rsp+110h+pv], rdi
0x180009b4b  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data1
0x180009b52  sub     rax, [r12]
0x180009b56  jnz     short loc_180009B64
0x180009b58  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data4
0x180009b5f  sub     rax, [r12+8]
0x180009b64  test    rax, rax
0x180009b67  jnz     short loc_180009BBE
0x180009b69  mov     qword ptr [rbp+3Fh+Buf2], rdi
0x180009b6d  mov     rax, [r15]
0x180009b70  lea     rdx, [rbp+3Fh+Buf2]
0x180009b74  mov     rcx, r15
0x180009b77  mov     rax, [rax+30h]
0x180009b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b80  test    eax, eax
0x180009b82  js      short loc_180009BBE
0x180009b84  mov     rdx, qword ptr [rbp+3Fh+Buf2]; lpString2
0x180009b88  lea     rcx, String1; "ms_tcpip"
0x180009b8f  call    cs:__imp_lstrcmpiW
0x180009b95  test    eax, eax
0x180009b97  jnz     short loc_180009BB4
0x180009b99  mov     [rsp+110h+ProductType], edi
0x180009b9d  lea     rcx, [rsp+110h+ProductType]; ProductType
0x180009ba2  call    cs:__imp_RtlGetNtProductType
0x180009ba8  cmp     [rsp+110h+ProductType], 2
0x180009bad  jnz     short loc_180009BB4
0x180009baf  or      [rsp+110h+var_F0], 20h
0x180009bb4  mov     rcx, qword ptr [rbp+3Fh+Buf2]; pv
0x180009bb8  call    cs:__imp_CoTaskMemFree
0x180009bbe  mov     rax, [r15]
0x180009bc1  lea     rdx, [rsp+110h+pv]
0x180009bc6  mov     rcx, r15
0x180009bc9  mov     rax, [rax+28h]
0x180009bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd2  mov     edi, eax
0x180009bd4  test    eax, eax
0x180009bd6  js      loc_180009CD4
0x180009bdc  xor     edx, edx; Val
0x180009bde  mov     r8d, 54h ; 'T'; Size
0x180009be4  lea     rcx, [rbp+3Fh+lParam+4]; void *
0x180009be8  call    memset_0
0x180009bed  mov     dword ptr [rsp+110h+lParam], 0Fh
0x180009bf5  test    rbx, rbx
0x180009bf8  jz      short loc_180009C19
0x180009bfa  mov     [rsp+110h+ProductType], 0
0x180009c02  lea     r8, [rsp+110h+ProductType]; int *
0x180009c07  mov     rdx, r12; struct _GUID *
0x180009c0a  mov     rcx, rbx; struct _SP_CLASSIMAGELIST_DATA *
0x180009c0d  call    ?HrSetupDiGetClassImageIndex@@YAJPEAU_SP_CLASSIMAGELIST_DATA@@PEBU_GUID@@PEAH@Z; HrSetupDiGetClassImageIndex(_SP_CLASSIMAGELIST_DATA *,_GUID const *,int *)
0x180009c12  mov     eax, [rsp+110h+ProductType]
0x180009c16  mov     [rbp+3Fh+var_9C], eax
0x180009c19  mov     eax, [rsi]
0x180009c1b  mov     dword ptr [rbp+3Fh+lParam+4], eax
0x180009c1e  mov     ecx, 28h ; '('; unsigned __int64
0x180009c23  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180009c28  mov     rbx, rax
0x180009c2b  test    rax, rax
0x180009c2e  jz      loc_180009CD4
0x180009c34  mov     rcx, [rsp+110h+var_D8]; unsigned __int16 *
0x180009c39  call    ?SzDupSz@@YAPEAGPEBG@Z; SzDupSz(ushort const *)
0x180009c3e  mov     [rbx+10h], rax
0x180009c42  mov     rcx, [rsp+110h+pv]; unsigned __int16 *
0x180009c47  call    ?SzDupSz@@YAPEAGPEBG@Z; SzDupSz(ushort const *)
0x180009c4c  mov     [rbx+18h], rax
0x180009c50  mov     ecx, [rsp+110h+var_F0]
0x180009c54  mov     [rbx+20h], ecx
0x180009c57  mov     [rbx], r15
0x180009c5a  mov     rcx, r15; struct IUnknown *
0x180009c5d  call    ?AddRefObj@@YAKPEAUIUnknown@@@Z; AddRefObj(IUnknown *)
0x180009c62  mov     ecx, 28h ; '('; unsigned __int64
0x180009c67  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180009c6c  mov     qword ptr [rbp+3Fh+Buf2], rax
0x180009c70  test    rax, rax
0x180009c73  jz      short loc_180009C81
0x180009c75  mov     rdx, r15; struct INetCfgComponent *
0x180009c78  mov     rcx, rax; this
0x180009c7b  call    ??0CComponentObj@@QEAA@PEAUINetCfgComponent@@@Z; CComponentObj::CComponentObj(INetCfgComponent *)
0x180009c80  nop
0x180009c81  mov     [rbx+8], rax
0x180009c85  test    rax, rax
0x180009c88  jz      short loc_180009C9E
0x180009c8a  mov     rdx, r14
0x180009c8d  mov     rcx, rax
0x180009c90  call    ?HrInit@CComponentObj@@QEAAJPEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@@Z; CComponentObj::HrInit(std::list<CBindingPathObj *> *)
0x180009c95  mov     edi, eax
0x180009c97  xor     eax, eax
0x180009c99  test    edi, edi
0x180009c9b  cmovs   edi, eax
0x180009c9e  mov     [rbp+3Fh+var_98], rbx
0x180009ca2  mov     rax, [rbx+10h]
0x180009ca6  mov     [rbp+3Fh+var_A8], rax
0x180009caa  mov     [rbp+3Fh+var_B4], 2000h
0x180009cb1  lea     r9, [rsp+110h+lParam]; lParam
0x180009cb6  xor     r8d, r8d; wParam
0x180009cb9  mov     edx, 104Dh; Msg
0x180009cbe  mov     rcx, r13; hWnd
0x180009cc1  call    cs:__imp_SendMessageW
0x180009cc7  inc     dword ptr [rsi]
0x180009cc9  mov     rcx, [rsp+110h+pv]; pv
0x180009cce  call    cs:__imp_CoTaskMemFree
0x180009cd4  mov     rcx, [rsp+110h+var_D8]; pv
0x180009cd9  call    cs:__imp_CoTaskMemFree
0x180009cdf  mov     rcx, [rsp+110h+var_D0]; struct IUnknown *
0x180009ce4  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180009ce9  mov     eax, edi
0x180009ceb  mov     rcx, [rbp+3Fh+var_40]
0x180009cef  xor     rcx, rsp; StackCookie
0x180009cf2  call    __security_check_cookie
0x180009cf7  mov     rbx, [rsp+110h+arg_18]
0x180009cff  add     rsp, 0E0h
0x180009d06  pop     r15
0x180009d08  pop     r14
0x180009d0a  pop     r13
0x180009d0c  pop     r12
0x180009d0e  pop     rdi
0x180009d0f  pop     rsi
0x180009d10  pop     rbp
0x180009d11  retn
```
