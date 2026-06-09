# EventInterface::GetMethodInfo(ITypeInfo *,tagTYPEATTR *,ushort,DescendentInterface *)

- ea: `0x180006b10`
- end: `0x1800073b0`
- name: `?GetMethodInfo@EventInterface@@QEAAGPEAUITypeInfo@@PEAUtagTYPEATTR@@GPEAVDescendentInterface@@@Z`
- size: `2208`
- prototype: `unsigned __int16 __usercall@<ax>(EventInterface *__hidden this@<rcx>, struct ITypeInfo *@<rdx>, struct tagTYPEATTR *@<r8>, unsigned __int16@<r9w>, struct DescendentInterface *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000685c`
- `0x180006b10`

## callees

- `0x180003d54`
- `0x180006b10`
- `0x1800073c0`
- `0x1800079e8`
- `0x180007b00`
- `0x180007dc8`
- `0x180008938`
- `0x180012654`
- `0x180023804`
- `0x180026364`
- `0x18002c084`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000706d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000706d`

## string_xrefs

- `0x180006caa`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007026`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007102`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000716c`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007187`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800071b3`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800071d6`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800071f4`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007217`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007236`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007254`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007277`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007296`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800072b5`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800072e0`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800072fb`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007360`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000737f`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall EventInterface::GetMethodInfo(
        EventInterface *this,
        struct ITypeInfo *a2,
        struct tagTYPEATTR *a3,
        unsigned __int16 a4,
        struct DescendentInterface *a5)
{
  __int64 v5; // rax
  unsigned __int16 MethodInfo; // di
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  _QWORD *i; // rdx
  __int64 v14; // rax
  unsigned __int16 *v15; // rbx
  char *v16; // rax
  char *v17; // r15
  GUID guid; // xmm0
  struct DescendentInterface *v19; // rax
  struct DescendentInterface *v20; // rdi
  __int64 v21; // rbx
  unsigned int v22; // r9d
  unsigned int v23; // edi
  _QWORD *v24; // r8
  int v25; // ecx
  __int64 v26; // rax
  LPVOID v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  struct ITypeInfoVtbl *lpVtbl; // rax
  int v31; // eax
  struct ITypeInfoVtbl *v32; // rax
  int v33; // eax
  int v34; // eax
  __int16 v35; // bx
  int v36; // edi
  WORD v37; // bx
  int v38; // eax
  int v39; // eax
  struct ITypeInfo *v40; // rcx
  int v41; // eax
  unsigned __int16 v42; // r9
  EventMethod *v43; // rax
  EventMethod *v44; // rdx
  __int64 v45; // rcx
  LPVOID v47; // rax
  __int64 v48; // rcx
  __int64 v49; // r8
  _QWORD *j; // rax
  char *v51; // rax
  char *v52; // rbx
  int v53; // eax
  unsigned int v54; // edx
  LPVOID v55; // rax
  __int64 v56; // r8
  unsigned int v57; // ecx
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // r9
  _DWORD *v61; // rdx
  int v62; // eax
  unsigned int v63; // [rsp+30h] [rbp-48h] BYREF
  struct ITypeInfo *v64; // [rsp+38h] [rbp-40h] BYREF
  struct ITypeInfo *v65; // [rsp+40h] [rbp-38h] BYREF
  __int64 v66; // [rsp+48h] [rbp-30h] BYREF
  struct tagTYPEATTR *v67; // [rsp+50h] [rbp-28h] BYREF
  __int64 v68; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v69[2]; // [rsp+60h] [rbp-18h] BYREF
  int inited; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int16 v71; // [rsp+C8h] [rbp+50h]

  v71 = a4;
  v5 = *(_QWORD *)&a3->guid.Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  MethodInfo = 0;
  if ( *(_QWORD *)&a3->guid.Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)a3->guid.Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v5 )
  {
    *((_DWORD *)this + 11) = 3;
    *((_DWORD *)this + 10) = a4;
    v27 = CoTaskMemAlloc(saturated_mul(a4, 8u));
    *((_QWORD *)this + 6) = v27;
    if ( !v27 )
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16ABu, 0xC0001204, 0x12u);
    return MethodInfo;
  }
  v10 = *(_QWORD *)&a3->guid.Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a3->guid.Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v10 = *(_QWORD *)a3->guid.Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 2);
    v12 = *(_QWORD *)(v11 + 56);
    if ( v12 )
    {
      for ( i = *(_QWORD **)(v12 + 8LL * (a3->guid.Data1 % *(_DWORD *)(v11 + 64))); i; i = (_QWORD *)*i )
      {
        v14 = *(_QWORD *)((char *)i + 12) - *(_QWORD *)&a3->guid.Data1;
        if ( !v14 )
          v14 = *(_QWORD *)((char *)i + 20) - *(_QWORD *)a3->guid.Data4;
        if ( !v14 )
        {
          v15 = (unsigned __int16 *)i[4];
          if ( !v15 )
            break;
          v54 = a4 + v15[12];
          *((_DWORD *)this + 10) = v54;
          *((_DWORD *)this + 11) = *(_DWORD *)(*(_QWORD *)v15 + 44LL);
          v55 = CoTaskMemAlloc(saturated_mul(v54, 8u));
          *((_QWORD *)this + 6) = v55;
          if ( !v55 )
            InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16F7u, 0xC0001204, 0x12u);
          v56 = *(_QWORD *)v15;
          v57 = v15[12];
          if ( v57 > *(_DWORD *)(*(_QWORD *)v15 + 40LL) )
            return (unsigned __int16)v57;
          if ( (_WORD)v57 )
          {
            v60 = 0;
            do
            {
              ++v60;
              ++MethodInfo;
              *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v60 - 8) = *(_QWORD *)(*(_QWORD *)(v56 + 48) + 8 * v60 - 8);
              v61 = *(_DWORD **)(*((_QWORD *)this + 6) + 8 * v60 - 8);
              ++*v61;
            }
            while ( MethodInfo < (unsigned __int16)v57 );
          }
          v62 = InterfaceInfo::AddDescendents((InterfaceInfo *)v15, a5);
          if ( v62 < 0 )
            InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1707u, 0x12u, v62);
          return MethodInfo;
        }
      }
    }
    v16 = (char *)CoTaskMemAlloc(0x50u);
    v17 = v16;
    if ( v16 )
    {
      *(_QWORD *)v16 = this;
      guid = a3->guid;
      *((_WORD *)v16 + 12) = 0;
      *(GUID *)(v16 + 8) = guid;
      *((_DWORD *)v16 + 12) = 0;
      *((_QWORD *)v16 + 7) = 0;
      *((_QWORD *)v16 + 5) = 0;
      *((_QWORD *)v16 + 4) = 0;
      *((_QWORD *)v16 + 8) = 0;
      *((_DWORD *)v16 + 18) = 10;
      v19 = a5;
      v20 = a5;
      while ( v20 )
      {
        v59 = CList<InterfaceInfo *,InterfaceInfo *>::AddTail(v17 + 32, *(_QWORD *)v19);
        if ( v59 < 0 )
        {
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x167Au, 0x12u, v59);
          break;
        }
        v20 = (struct DescendentInterface *)*((_QWORD *)v20 + 1);
        v19 = a5;
      }
    }
    else
    {
      v17 = 0;
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16CAu, 0xC0001204, 0x12u);
    }
    v21 = *((_QWORD *)this + 2) + 56LL;
    v22 = *(_DWORD *)(*((_QWORD *)this + 2) + 64LL);
    v23 = *((_DWORD *)v17 + 2) % v22;
    if ( *(_QWORD *)v21 )
    {
      v24 = *(_QWORD **)(*(_QWORD *)v21 + 8LL * (*((_DWORD *)v17 + 2) % v22));
      v25 = 0;
      inited = 0;
      while ( v24 )
      {
        v26 = *(_QWORD *)((char *)v24 + 12) - *((_QWORD *)v17 + 1);
        if ( !v26 )
          v26 = *(_QWORD *)((char *)v24 + 20) - *((_QWORD *)v17 + 2);
        if ( !v26 )
          goto LABEL_30;
        v24 = (_QWORD *)*v24;
      }
      if ( *(_DWORD *)(v21 + 12) >= v22 )
      {
        CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::GrowHashTable(v21);
        v23 = *((_DWORD *)v17 + 2) % *(_DWORD *)(v21 + 8);
      }
    }
    else
    {
      inited = CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::InitHashTable(
                 *((_QWORD *)this + 2) + 56LL,
                 v22);
      v25 = inited;
      if ( inited < 0 )
        goto LABEL_85;
    }
    v28 = CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::NewAssoc(v21);
    v24 = (_QWORD *)v28;
    if ( v28 )
    {
      *(_DWORD *)(v28 + 8) = v23;
      *(_OWORD *)(v28 + 12) = *(_OWORD *)(v17 + 8);
      v29 = 8LL * v23;
      *(_QWORD *)v28 = *(_QWORD *)(v29 + *(_QWORD *)v21);
      v25 = inited;
      *(_QWORD *)(v29 + *(_QWORD *)v21) = v28;
LABEL_30:
      v24[4] = v17;
      if ( v25 >= 0 )
        goto LABEL_31;
    }
    else
    {
      v25 = -2147024882;
    }
LABEL_85:
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16CDu, 0x12u, v25);
LABEL_31:
    lpVtbl = a2->lpVtbl;
    v63 = 0;
    v31 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int *))lpVtbl->GetRefTypeOfImplType)(
            a2,
            0,
            &v63);
    if ( v31 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16D3u, 0x12u, v31);
    v32 = a2->lpVtbl;
    v64 = 0;
    v33 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v32->GetRefTypeInfo)(a2, v63, &v64);
    if ( v33 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16D7u, 0x12u, v33);
    v68 = 0;
    v34 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))v64->lpVtbl->GetTypeAttr)(v64, &v68);
    if ( v34 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x17CDu, 0x12u, v34);
    v35 = *(_WORD *)(v68 + 58);
    v36 = *(_DWORD *)(v68 + 44);
    ((void (__fastcall *)(struct ITypeInfo *))v64->lpVtbl->ReleaseTypeAttr)(v64);
    if ( (v35 & 0x40) != 0 && v36 == 4 )
    {
      v37 = 0;
      inited = 0;
      v65 = 0;
      v38 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, int *))v64->lpVtbl->GetRefTypeOfImplType)(
              v64,
              0xFFFFFFFFLL,
              &inited);
      if ( v38 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x17DAu, 0x12u, v38);
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v64->lpVtbl->GetRefTypeInfo)(
             v64,
             (unsigned int)inited,
             &v65) >= 0 )
      {
        v66 = 0;
        v39 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))v65->lpVtbl->GetTypeAttr)(v65, &v66);
        if ( v39 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x17E0u, 0x12u, v39);
        if ( *(_DWORD *)(v66 + 44) != 3 )
          InternalAssert(
            L"com\\complus\\src\\events\\tier1\\agent.cpp",
            0x17E1u,
            0x12u,
            L"refTypeAttr->typekind == TKIND_INTERFACE");
        ((void (__fastcall *)(struct ITypeInfo *))v65->lpVtbl->ReleaseTypeAttr)(v65);
      }
      ((void (__fastcall *)(struct ITypeInfo *))v64->lpVtbl->Release)(v64);
      v40 = v65;
      v64 = v65;
    }
    else
    {
      v40 = v64;
      v37 = 0;
    }
    v67 = 0;
    v41 = ((__int64 (__fastcall *)(struct ITypeInfo *, struct tagTYPEATTR **))v40->lpVtbl->GetTypeAttr)(v40, &v67);
    if ( v41 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16DEu, 0x12u, v41);
    v42 = a3->cFuncs + v71;
    v69[1] = a5;
    v69[0] = v17;
    MethodInfo = EventInterface::GetMethodInfo(this, v64, v67, v42, (struct DescendentInterface *)v69);
    ((void (__fastcall *)(struct ITypeInfo *, struct tagTYPEATTR *))v64->lpVtbl->ReleaseTypeAttr)(v64, v67);
    ((void (__fastcall *)(struct ITypeInfo *))v64->lpVtbl->Release)(v64);
    if ( a3->cFuncs )
    {
      do
      {
        v43 = (EventMethod *)CoTaskMemAlloc(0x70u);
        if ( v43 )
          v44 = EventMethod::EventMethod(v43, v37, this, (const struct _GUID *)(v17 + 8), a2);
        else
          v44 = 0;
        v45 = 8LL * MethodInfo;
        *(_QWORD *)(v45 + *((_QWORD *)this + 6)) = v44;
        if ( !*(_QWORD *)(v45 + *((_QWORD *)this + 6)) )
          InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16EAu, 0xC0001204, 0x12u);
        ++MethodInfo;
        ++v37;
      }
      while ( v37 < a3->cFuncs );
    }
    *((_WORD *)v17 + 12) = MethodInfo;
    return MethodInfo;
  }
  *((_DWORD *)this + 11) = 7;
  *((_DWORD *)this + 10) = a4;
  v47 = CoTaskMemAlloc(saturated_mul(a4, 8u));
  *((_QWORD *)this + 6) = v47;
  if ( !v47 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16B5u, 0xC0001204, 0x12u);
  v48 = *((_QWORD *)this + 2);
  v49 = *(_QWORD *)(v48 + 56);
  if ( v49 )
  {
    for ( j = *(_QWORD **)(v49 + 8LL * (IID_IDispatch.Data1 % *(_DWORD *)(v48 + 64))); j; j = (_QWORD *)*j )
    {
      v58 = *(_QWORD *)((char *)j + 12) - *(_QWORD *)&IID_IDispatch.Data1;
      if ( !v58 )
        v58 = *(_QWORD *)((char *)j + 20) - *(_QWORD *)IID_IDispatch.Data4;
      if ( !v58 )
      {
        if ( j[4] )
          return MethodInfo;
        break;
      }
    }
  }
  v51 = (char *)CoTaskMemAlloc(0x50u);
  v52 = v51;
  if ( v51 )
  {
    *(_QWORD *)v51 = this;
    *((_WORD *)v51 + 12) = 0;
    *(GUID *)(v51 + 8) = IID_IDispatch;
    *((_DWORD *)v51 + 12) = 0;
    *((_QWORD *)v51 + 7) = 0;
    *((_QWORD *)v51 + 5) = 0;
    *((_QWORD *)v51 + 4) = 0;
    *((_QWORD *)v51 + 8) = 0;
    *((_DWORD *)v51 + 18) = 10;
  }
  else
  {
    v52 = 0;
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16BCu, 0xC0001204, 0x12u);
  }
  v53 = CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::SetAt(*((_QWORD *)this + 2) + 56LL, v52 + 8, v52);
  if ( v53 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x16BFu, 0x12u, v53);
  return MethodInfo;
}

```

## disassembly

```asm
0x180006b10  mov     [rsp-30h+arg_18], r9w
0x180006b16  push    rbp
0x180006b17  push    rsi
0x180006b18  push    rdi
0x180006b19  push    r12
0x180006b1b  push    r13
0x180006b1d  push    r14
0x180006b1f  mov     rbp, rsp
0x180006b22  sub     rsp, 78h
0x180006b26  mov     rax, [r8]
0x180006b29  xor     r12d, r12d
0x180006b2c  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006b33  mov     r14, r8
0x180006b36  mov     r13, rdx
0x180006b39  mov     rsi, rcx
0x180006b3c  mov     edi, r12d
0x180006b3f  jnz     short loc_180006B4C
0x180006b41  mov     rax, [r8+8]
0x180006b45  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180006b4c  mov     [rsp+78h+arg_0], rbx
0x180006b54  mov     [rsp+78h+var_8], r15
0x180006b59  test    rax, rax
0x180006b5c  jz      loc_180006C6A
0x180006b62  mov     rax, [r8]
0x180006b65  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180006b6c  jnz     short loc_180006B79
0x180006b6e  mov     rax, [r8+8]
0x180006b72  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180006b79  test    rax, rax
0x180006b7c  jz      loc_180006F4F
0x180006b82  mov     rcx, [rcx+10h]
0x180006b86  mov     r8, [rcx+38h]
0x180006b8a  test    r8, r8
0x180006b8d  jz      short loc_180006BC7
0x180006b8f  mov     eax, [r14]
0x180006b92  xor     edx, edx
0x180006b94  div     dword ptr [rcx+40h]
0x180006b97  mov     rdx, [r8+rdx*8]
0x180006b9b  test    rdx, rdx
0x180006b9e  jz      short loc_180006BC7
0x180006ba0  mov     rax, [rdx+0Ch]
0x180006ba4  sub     rax, [r14]
0x180006ba7  jnz     short loc_180006BB1
0x180006ba9  mov     rax, [rdx+14h]
0x180006bad  sub     rax, [r14+8]
0x180006bb1  test    rax, rax
0x180006bb4  jnz     loc_180007099
0x180006bba  mov     rbx, [rdx+20h]
0x180006bbe  test    rbx, rbx
0x180006bc1  jnz     loc_18000703F
0x180006bc7  mov     ecx, 50h ; 'P'; cb
0x180006bcc  call    cs:__imp_CoTaskMemAlloc
0x180006bd2  mov     r15, rax
0x180006bd5  test    rax, rax
0x180006bd8  jz      loc_1800070FD
0x180006bde  mov     [rax], rsi
0x180006be1  movups  xmm0, xmmword ptr [r14]
0x180006be5  mov     [rax+18h], r12w
0x180006bea  movups  xmmword ptr [rax+8], xmm0
0x180006bee  mov     [rax+30h], r12d
0x180006bf2  mov     [rax+38h], r12
0x180006bf6  mov     [rax+28h], r12
0x180006bfa  mov     [rax+20h], r12
0x180006bfe  mov     [rax+40h], r12
0x180006c02  mov     dword ptr [rax+48h], 0Ah
0x180006c09  mov     rax, [rbp+arg_20]
0x180006c0d  mov     rdi, rax
0x180006c10  test    rdi, rdi
0x180006c13  jnz     loc_1800070CD
0x180006c19  mov     rbx, [rsi+10h]
0x180006c1d  xor     edx, edx
0x180006c1f  mov     eax, [r15+8]
0x180006c23  add     rbx, 38h ; '8'
0x180006c27  mov     r9d, [rbx+8]
0x180006c2b  mov     r8, [rbx]
0x180006c2e  div     r9d
0x180006c31  mov     edi, edx
0x180006c33  test    r8, r8
0x180006c36  jz      loc_180007144
0x180006c3c  mov     r8, [r8+rdx*8]
0x180006c40  xor     ecx, ecx
0x180006c42  mov     [rbp+arg_10], ecx
0x180006c45  test    r8, r8
0x180006c48  jz      short loc_180006CC7
0x180006c4a  mov     rax, [r8+0Ch]
0x180006c4e  sub     rax, [r15+8]
0x180006c52  jnz     short loc_180006C5C
0x180006c54  mov     rax, [r8+14h]
0x180006c58  sub     rax, [r15+10h]
0x180006c5c  test    rax, rax
0x180006c5f  jz      loc_180006D0F
0x180006c65  mov     r8, [r8]
0x180006c68  jmp     short loc_180006C45
0x180006c6a  mov     dword ptr [rcx+2Ch], 3
0x180006c71  movzx   eax, r9w
0x180006c75  mov     [rcx+28h], eax
0x180006c78  mov     eax, 8
0x180006c7d  movzx   ecx, r9w
0x180006c81  mul     rcx
0x180006c84  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006c8b  cmovb   rax, rcx
0x180006c8f  mov     rcx, rax; cb
0x180006c92  call    cs:__imp_CoTaskMemAlloc
0x180006c98  mov     [rsi+30h], rax
0x180006c9c  test    rax, rax
0x180006c9f  jnz     loc_180006F31
0x180006ca5  mov     edx, 16ABh; unsigned int
0x180006caa  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180006cb1  mov     r9d, 12h; unsigned __int16
0x180006cb7  mov     r8d, 0C0001204h; unsigned int
0x180006cbd  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180006cc2  jmp     loc_180006F31
0x180006cc7  cmp     [rbx+0Ch], r9d
0x180006ccb  jnb     loc_180007398
0x180006cd1  mov     rcx, rbx
0x180006cd4  call    ?NewAssoc@?$CMap@U_GUID@@AEBU1@PEAVInterfaceInfo@@PEAV2@@@IEAAPEAUCAssoc@1@XZ; CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::NewAssoc(void)
0x180006cd9  mov     r8, rax
0x180006cdc  test    rax, rax
0x180006cdf  jz      loc_18000715E
0x180006ce5  mov     [rax+8], edi
0x180006ce8  movups  xmm0, xmmword ptr [r15+8]
0x180006ced  movups  xmmword ptr [rax+0Ch], xmm0
0x180006cf1  mov     eax, edi
0x180006cf3  lea     rdx, ds:0[rax*8]
0x180006cfb  mov     rax, [rbx]
0x180006cfe  mov     rcx, [rdx+rax]
0x180006d02  mov     [r8], rcx
0x180006d05  mov     rax, [rbx]
0x180006d08  mov     ecx, [rbp+arg_10]
0x180006d0b  mov     [rdx+rax], r8
0x180006d0f  mov     [r8+20h], r15
0x180006d13  test    ecx, ecx
0x180006d15  js      loc_180007163
0x180006d1b  mov     rax, [r13+0]
0x180006d1f  lea     r8, [rbp+var_48]
0x180006d23  xor     ebx, ebx
0x180006d25  xor     edx, edx
0x180006d27  mov     rcx, r13
0x180006d2a  mov     [rbp+var_48], ebx
0x180006d2d  mov     rax, [rax+40h]
0x180006d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d36  test    eax, eax
0x180006d38  js      loc_1800071D0
0x180006d3e  mov     rax, [r13+0]
0x180006d42  lea     r8, [rbp+var_40]
0x180006d46  mov     edx, [rbp+var_48]
0x180006d49  mov     rcx, r13
0x180006d4c  mov     [rbp+var_40], rbx
0x180006d50  mov     rax, [rax+70h]
0x180006d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d59  test    eax, eax
0x180006d5b  js      loc_180007211
0x180006d61  mov     rcx, [rbp+var_40]
0x180006d65  lea     rdx, [rbp+var_20]
0x180006d69  mov     [rbp+var_20], rbx
0x180006d6d  mov     rax, [rcx]
0x180006d70  mov     rax, [rax+18h]
0x180006d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d79  test    eax, eax
0x180006d7b  js      loc_180007271
0x180006d81  mov     rdx, [rbp+var_20]
0x180006d85  mov     rcx, [rbp+var_40]
0x180006d89  movzx   ebx, word ptr [rdx+3Ah]
0x180006d8d  mov     rax, [rcx]
0x180006d90  mov     edi, [rdx+2Ch]
0x180006d93  mov     rax, [rax+98h]
0x180006d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9f  test    bl, 40h
0x180006da2  jz      loc_1800070C2
0x180006da8  cmp     edi, 4
0x180006dab  jnz     loc_1800070C2
0x180006db1  mov     rcx, [rbp+var_40]
0x180006db5  lea     r8, [rbp+arg_10]
0x180006db9  xor     ebx, ebx
0x180006dbb  mov     edx, 0FFFFFFFFh
0x180006dc0  mov     [rbp+arg_10], ebx
0x180006dc3  mov     [rbp+var_38], rbx
0x180006dc7  mov     rax, [rcx]
0x180006dca  mov     rax, [rax+40h]
0x180006dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd3  test    eax, eax
0x180006dd5  js      loc_180007290
0x180006ddb  mov     rcx, [rbp+var_40]
0x180006ddf  lea     r8, [rbp+var_38]
0x180006de3  mov     edx, [rbp+arg_10]
0x180006de6  mov     rax, [rcx]
0x180006de9  mov     rax, [rax+70h]
0x180006ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df2  test    eax, eax
0x180006df4  js      short loc_180006E37
0x180006df6  mov     rcx, [rbp+var_38]
0x180006dfa  lea     rdx, [rbp+var_30]
0x180006dfe  mov     [rbp+var_30], rbx
0x180006e02  mov     rax, [rcx]
0x180006e05  mov     rax, [rax+18h]
0x180006e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0e  test    eax, eax
0x180006e10  js      loc_1800072AF
0x180006e16  mov     rdx, [rbp+var_30]
0x180006e1a  cmp     dword ptr [rdx+2Ch], 3
0x180006e1e  jnz     loc_1800072CE
0x180006e24  mov     rcx, [rbp+var_38]
0x180006e28  mov     rax, [rcx]
0x180006e2b  mov     rax, [rax+98h]
0x180006e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e37  mov     rcx, [rbp+var_40]
0x180006e3b  mov     rax, [rcx]
0x180006e3e  mov     rax, [rax+10h]
0x180006e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e47  mov     rcx, [rbp+var_38]
0x180006e4b  mov     [rbp+var_40], rcx
0x180006e4f  mov     [rbp+var_28], rbx
0x180006e53  lea     rdx, [rbp+var_28]
0x180006e57  mov     rax, [rcx]
0x180006e5a  mov     rax, [rax+18h]
0x180006e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e63  test    eax, eax
0x180006e65  js      loc_180007230
0x180006e6b  mov     rax, [rbp+arg_20]
0x180006e6f  mov     rcx, rsi; this
0x180006e72  movzx   r9d, [rbp+arg_18]
0x180006e77  add     r9w, [r14+30h]; unsigned __int16
0x180006e7c  mov     r8, [rbp+var_28]; struct tagTYPEATTR *
0x180006e80  mov     rdx, [rbp+var_40]; struct ITypeInfo *
0x180006e84  mov     [rbp+var_10], rax
0x180006e88  lea     rax, [rbp+var_18]
0x180006e8c  mov     [rsp+78h+var_58], rax; struct DescendentInterface *
0x180006e91  mov     [rbp+var_18], r15
0x180006e95  call    ?GetMethodInfo@EventInterface@@QEAAGPEAUITypeInfo@@PEAUtagTYPEATTR@@GPEAVDescendentInterface@@@Z; EventInterface::GetMethodInfo(ITypeInfo *,tagTYPEATTR *,ushort,DescendentInterface *)
0x180006e9a  mov     rcx, [rbp+var_40]
0x180006e9e  movzx   edi, ax
0x180006ea1  mov     rdx, [rcx]
0x180006ea4  mov     rax, [rdx+98h]
0x180006eab  mov     rdx, [rbp+var_28]
0x180006eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb4  mov     rcx, [rbp+var_40]
0x180006eb8  mov     rdx, [rcx]
0x180006ebb  mov     rax, [rdx+10h]
0x180006ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec4  xor     eax, eax
0x180006ec6  cmp     ax, [r14+30h]
0x180006ecb  jnb     short loc_180006F2C
0x180006ecd  nop     dword ptr [rax]
0x180006ed0  mov     ecx, 70h ; 'p'; cb
0x180006ed5  call    cs:__imp_CoTaskMemAlloc
0x180006edb  test    rax, rax
0x180006ede  jz      loc_1800071A7
0x180006ee4  movzx   edx, bx; unsigned int
0x180006ee7  lea     r9, [r15+8]; struct _GUID *
0x180006eeb  mov     r8, rsi; struct EventInterface *
0x180006eee  mov     [rsp+78h+var_58], r13; struct ITypeInfo *
0x180006ef3  mov     rcx, rax; this
0x180006ef6  call    ??0EventMethod@@QEAA@KAEAVEventInterface@@AEBU_GUID@@PEAUITypeInfo@@@Z; EventMethod::EventMethod(ulong,EventInterface &,_GUID const &,ITypeInfo *)
0x180006efb  mov     rdx, rax
0x180006efe  movzx   eax, di
0x180006f01  lea     rcx, ds:0[rax*8]
0x180006f09  mov     rax, [rsi+30h]
0x180006f0d  mov     [rcx+rax], rdx
0x180006f11  mov     rax, [rsi+30h]
0x180006f15  cmp     [rcx+rax], r12
0x180006f19  jz      loc_1800071EF
0x180006f1f  inc     di
0x180006f22  inc     bx
0x180006f25  cmp     bx, [r14+30h]
0x180006f2a  jb      short loc_180006ED0
0x180006f2c  mov     [r15+18h], di
0x180006f31  movzx   eax, di
0x180006f34  mov     r15, [rsp+78h+var_8]
0x180006f39  mov     rbx, [rsp+78h+arg_0]
0x180006f41  add     rsp, 78h
0x180006f45  pop     r14
0x180006f47  pop     r13
0x180006f49  pop     r12
0x180006f4b  pop     rdi
0x180006f4c  pop     rsi
0x180006f4d  pop     rbp
0x180006f4e  retn
0x180006f4f  mov     dword ptr [rcx+2Ch], 7
0x180006f56  movzx   eax, r9w
0x180006f5a  mov     [rcx+28h], eax
0x180006f5d  mov     eax, 8
0x180006f62  movzx   ecx, r9w
0x180006f66  mul     rcx
0x180006f69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006f70  cmovb   rax, rcx
0x180006f74  mov     rcx, rax; cb
0x180006f77  call    cs:__imp_CoTaskMemAlloc
0x180006f7d  mov     [rsi+30h], rax
0x180006f81  test    rax, rax
0x180006f84  jz      loc_1800071AE
0x180006f8a  mov     rcx, [rsi+10h]
0x180006f8e  mov     r8, [rcx+38h]
0x180006f92  test    r8, r8
0x180006f95  jz      short loc_180006FB3
0x180006f97  mov     r9, qword ptr cs:IID_IDispatch.Data1
0x180006f9e  xor     edx, edx
0x180006fa0  mov     eax, r9d
0x180006fa3  div     dword ptr [rcx+40h]
0x180006fa6  mov     rax, [r8+rdx*8]
0x180006faa  test    rax, rax
  ... truncated ...
```
