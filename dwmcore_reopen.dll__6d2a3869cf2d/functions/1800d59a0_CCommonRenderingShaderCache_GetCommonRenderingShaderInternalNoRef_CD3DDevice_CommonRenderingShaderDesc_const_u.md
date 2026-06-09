# CCommonRenderingShaderCache::GetCommonRenderingShaderInternalNoRef(CD3DDevice *,CommonRenderingShaderDesc const &,uint *,ID3D11PixelShader * *)

- ea: `0x1800d59a0`
- end: `0x1800d6133`
- name: `?GetCommonRenderingShaderInternalNoRef@CCommonRenderingShaderCache@@AEAAJPEAVCD3DDevice@@AEBUCommonRenderingShaderDesc@@PEAIPEAPEAUID3D11PixelShader@@@Z`
- size: `1939`
- prototype: `__int64 __fastcall(CCommonRenderingShaderCache *__hidden this, struct CD3DDevice *, const struct CommonRenderingShaderDesc *, unsigned int *, struct ID3D11PixelShader **)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046338`
- `0x1800d4dd0`

## callees

- `0x180026eac`
- `0x180040930`
- `0x180050270`
- `0x180086120`
- `0x180086360`
- `0x1800d59a0`
- `0x1800d6140`
- `0x1800d6664`
- `0x1800d6704`
- `0x1800d6aa0`
- `0x1800d6b18`
- `0x1800da5f8`
- `0x180202b80`
- `0x1802284b0`
- `0x180229444`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5ea1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5ea1`
- `D3DCOMPILER_47!D3DCreateBlob` at `0x1800d5cdc`
- `D3DCOMPILER_47!D3DCreateBlob` at `0x1800d5cdc`

## string_xrefs

- `0x1800d5b3e`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d5b81`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d5d49`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d5d6c`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d5d8f`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CCommonRenderingShaderCache::GetCommonRenderingShaderInternalNoRef(
        CCommonRenderingShaderCache *this,
        struct CD3DDevice *a2,
        const struct CommonRenderingShaderDesc *a3,
        unsigned int *a4,
        struct ID3D11PixelShader **a5)
{
  int v5; // r14d
  volatile signed __int32 *v6; // rsi
  bool v8; // cc
  char v9; // al
  char v10; // al
  __int128 v11; // xmm0
  unsigned __int8 v12; // r12
  bool v13; // al
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  struct CD3DPixelShader *v16; // r9
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // edi
  int v21; // edi
  struct CD3DDevice *v22; // r12
  __int64 i; // rdi
  __int64 v24; // rcx
  struct CD3DPixelShader *v25; // rdi
  unsigned int v26; // r14d
  volatile signed __int32 *v28; // rax
  SIZE_T v29; // rdi
  const void *v30; // rsi
  HRESULT v31; // eax
  unsigned int v32; // ebx
  CLinkedShader *v33; // rcx
  int Resource; // eax
  void *v35; // rax
  HANDLE ProcessHeap; // rax
  char *v37; // rax
  ID3DBlob *v38; // rdx
  __int64 *v39; // rcx
  int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  _OWORD *ShaderLinkingBody; // rax
  int LinkedShader; // eax
  unsigned int v45; // ebx
  __int64 v46; // rdx
  int v47; // [rsp+20h] [rbp-E0h]
  struct CD3DPixelShader *v48[2]; // [rsp+30h] [rbp-D0h] BYREF
  ID3DBlob *ppBlob[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct CD3DDevice *v50; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v51; // [rsp+58h] [rbp-A8h]
  struct ID3D11PixelShader **v52; // [rsp+60h] [rbp-A0h]
  _OWORD v53[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v54[56]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v56; // [rsp+E0h] [rbp-20h]
  __int128 v57; // [rsp+F0h] [rbp-10h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  __int128 v59; // [rsp+110h] [rbp+10h]
  __int128 v60; // [rsp+120h] [rbp+20h]
  __int128 v61; // [rsp+130h] [rbp+30h]
  __int128 v62; // [rsp+140h] [rbp+40h]
  int v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+154h] [rbp+54h]
  int v65; // [rsp+15Ch] [rbp+5Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v5 = *(_DWORD *)a3;
  v52 = a5;
  v6 = 0;
  v51 = a4;
  v64 = 0;
  v65 = 0;
  v56 = 0;
  *(_DWORD *)((char *)&v56 + 10) = 0;
  HIWORD(v56) = 0;
  v58 = 0;
  *(_DWORD *)((char *)&v58 + 10) = 0;
  HIWORD(v58) = 0;
  v60 = 0;
  *(_DWORD *)((char *)&v60 + 10) = 0;
  HIWORD(v60) = 0;
  v62 = 0;
  *(_DWORD *)((char *)&v62 + 10) = 0;
  HIWORD(v62) = 0;
  v50 = a2;
  BYTE8(v56) = (v5 & 4) != 0;
  v63 = -1;
  *(_DWORD *)((char *)&v64 + 1) = (v5 & 0x10) != 0;
  v8 = *((_DWORD *)a2 + 156) < 37632;
  v57 = 0;
  LOBYTE(v64) = (v5 & 8) != 0;
  v9 = *((_BYTE *)a3 + 28);
  v59 = 0;
  BYTE4(v64) = v9;
  v10 = *((_BYTE *)a3 + 29);
  v61 = 0;
  BYTE5(v64) = v10;
  v11 = *(_OWORD *)((char *)a3 + 8);
  *(_QWORD *)&v57 = "NoOp";
  DWORD2(v57) = 0;
  *(_QWORD *)&v59 = "NoOp";
  DWORD2(v59) = 0;
  *(_QWORD *)&v61 = "NoOp";
  DWORD2(v61) = 0;
  v55 = v11;
  if ( v8 )
  {
    v15 = v5 & 3;
    v14 = v15 | 4;
    v12 = 0;
  }
  else
  {
    v12 = 1;
    v63 = *((_DWORD *)a3 + 6);
    v13 = (v5 & 0x20) != 0;
    v14 = v5 & 3;
    BYTE5(v56) = v13;
    v15 = v14;
  }
  ShaderLinkingConfig::GetLookupKey(&v55, v48, v14);
  v16 = v48[0];
  v17 = 0;
  v18 = qword_1803B99E0;
  while ( 1 )
  {
    if ( v17 >= (int)qword_1803B99E0 )
      goto LABEL_30;
    v19 = v17;
    if ( *(struct CD3DPixelShader **)(g_commonRenderingShaderCache + 16LL * v17) == v48[0]
      && *(_DWORD *)(g_commonRenderingShaderCache + 16LL * v17 + 8) == LODWORD(v48[1]) )
    {
      break;
    }
    ++v17;
  }
  if ( v17 == -1 )
  {
LABEL_30:
    v48[0] = 0;
    v28 = 0;
    goto LABEL_31;
  }
  v6 = *(volatile signed __int32 **)(qword_1803B99D8 + 8LL * v17);
  if ( !v6 )
    goto LABEL_45;
  if ( _InterlockedAdd(v6 + 2, 1u) <= 0 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  v20 = _InterlockedDecrement(v6 + 2);
  if ( v20 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  if ( v20 )
    goto LABEL_45;
  if ( _InterlockedAdd(v6 + 2, 1u) <= 0 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, struct CD3DPixelShader *))(*(_QWORD *)v6 + 24LL))(
    v6,
    v19,
    v18,
    v16);
  v21 = _InterlockedDecrement(v6 + 2);
  if ( v21 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  if ( v21 )
  {
LABEL_45:
    v48[0] = (struct CD3DPixelShader *)v6;
    if ( v6 )
      goto LABEL_23;
    v28 = 0;
LABEL_31:
    if ( *((_DWORD *)a3 + 4) <= 1u && *((_DWORD *)a3 + 6) == -1 && !*((_BYTE *)a3 + 29) )
    {
      switch ( *(_DWORD *)a3 )
      {
        case 5:
          v29 = 856;
          v30 = &unk_1802D4E80;
LABEL_36:
          v48[0] = 0;
          ppBlob[0] = 0;
          v31 = D3DCreateBlob(v29, ppBlob);
          v32 = v31;
          if ( v31 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v31, 0x47u, 0);
            if ( ppBlob[0] )
              ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
            return v32;
          }
          v35 = (void *)((__int64 (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->GetBufferPointer)(ppBlob[0]);
          memcpy_0(v35, v30, v29);
          ProcessHeap = GetProcessHeap();
          v37 = (char *)HeapAlloc(ProcessHeap, 0, 0x58u);
          v6 = (volatile signed __int32 *)v37;
          if ( !v37 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x4Du, 0);
            if ( ppBlob[0] )
              ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
            return 2147942414LL;
          }
          v38 = ppBlob[0];
          v39 = (__int64 *)(v37 + 16);
          *((_DWORD *)v37 + 2) = 0;
          v40 = 0;
          if ( BYTE2(v48[0]) )
            v40 = 2;
          *(_QWORD *)v37 = &CLinkedShader::`vftable';
          *v39 = (__int64)v38;
          Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(v39);
          *((_DWORD *)v6 + 6) = v40;
          *((_QWORD *)v6 + 4) = &CDeviceResourceTable<CD3DPixelShader,CLinkedShader>::`vftable';
          *((_QWORD *)v6 + 5) = v6;
          *((_QWORD *)v6 + 6) = v6 + 18;
          *((_QWORD *)v6 + 7) = v6 + 18;
          *((_QWORD *)v6 + 8) = v6 + 22;
          CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v6 + 2));
          ShaderLinkingConfig::GetLookupKey(&v55, v48, v14);
          v41 = CShaderCache::AddLinkedShader(&g_commonRenderingShaderCache, v48, v6);
          v42 = v41;
          if ( v41 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v41, 0x50u, 0);
            CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v6);
            wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(ppBlob);
            return v42;
          }
          v48[0] = (struct CD3DPixelShader *)v6;
          CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v6);
          if ( ppBlob[0] )
            ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
          v28 = v6;
          break;
        case 1:
          v29 = 800;
          v30 = &unk_180361CF0;
          goto LABEL_36;
        case 2:
          v29 = 824;
          v30 = &unk_180360D80;
          goto LABEL_36;
      }
    }
    if ( !v28 )
    {
      ShaderLinkingBody = (_OWORD *)CommonRenderingShaderBody::GetShaderLinkingBody(v54, v15, v12, v16);
      ppBlob[0] = 0;
      ppBlob[1] = 0;
      v53[0] = *ShaderLinkingBody;
      v53[1] = ShaderLinkingBody[1];
      v53[2] = ShaderLinkingBody[2];
      LinkedShader = CShaderCache::CreateLinkedShader(
                       (unsigned int)&g_commonRenderingShaderCache,
                       v14,
                       (unsigned int)&v55,
                       (unsigned int)v53,
                       (__int64)ppBlob,
                       (__int64)v48);
      v45 = LinkedShader;
      if ( LinkedShader < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, LinkedShader, 0x61u, 0);
        return v45;
      }
      v6 = (volatile signed __int32 *)v48[0];
    }
    goto LABEL_23;
  }
  if ( _InterlockedDecrement(v6 + 2) < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v6 + 16LL))(v6, 1);
LABEL_23:
  v22 = v50;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v24 = *((_QWORD *)v6 + 6);
    if ( (unsigned int)i >= (unsigned __int64)((*((_QWORD *)v6 + 7) - v24) >> 3) )
      goto LABEL_41;
    if ( v22 == (struct CD3DDevice *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(8 * i + v24) + 40LL))(*(_QWORD *)(8 * i + v24)) )
      break;
  }
  v25 = *(struct CD3DPixelShader **)(8 * i + *((_QWORD *)v6 + 6));
  if ( v25 )
  {
    v26 = 0;
LABEL_28:
    *v51 = *((_DWORD *)v6 + 6);
    *v52 = (struct ID3D11PixelShader *)*((_QWORD *)v25 + 15);
    return v26;
  }
LABEL_41:
  v33 = (CLinkedShader *)*((_QWORD *)v6 + 5);
  v48[0] = 0;
  Resource = CLinkedShader::CreateResource(v33, v22, v48);
  v26 = Resource;
  if ( Resource >= 0 )
  {
    v25 = v48[0];
    (*(void (__fastcall **)(struct CD3DPixelShader *, volatile signed __int32 *))(*(_QWORD *)v48[0] + 72LL))(
      v48[0],
      v6 + 8);
    v46 = (__int64)(*((_QWORD *)v6 + 7) - *((_QWORD *)v6 + 6)) >> 3;
    v48[0] = 0;
    v50 = 0;
    *(_QWORD *)detail::vector_facade<wil::com_ptr_t<CD3DPixelShader,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CD3DPixelShader,wil::err_returncode_policy>,2,1,detail::liberal_expansion_policy>>::reserve_region(
                 v6 + 12,
                 v46) = v25;
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v50);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(v48);
    goto LABEL_28;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Resource, 0x52u, 0);
  if ( v48[0] )
    (*(void (__fastcall **)(struct CD3DPixelShader *))(*(_QWORD *)v48[0] + 16LL))(v48[0]);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x11u, 0);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x65u, 0);
  return v26;
}

```

## disassembly

```asm
0x1800d59a0  push    rbp
0x1800d59a2  push    rsi
0x1800d59a3  push    r12
0x1800d59a5  push    r13
0x1800d59a7  push    r14
0x1800d59a9  push    r15
0x1800d59ab  lea     rbp, [rsp-78h]
0x1800d59b0  sub     rsp, 178h
0x1800d59b7  mov     rax, cs:__security_cookie
0x1800d59be  xor     rax, rsp
0x1800d59c1  mov     [rbp+0A0h+var_40], rax
0x1800d59c5  mov     r14d, [r8]
0x1800d59c8  lea     rcx, aNoop; "NoOp"
0x1800d59cf  mov     rax, [rbp+0A0h+arg_20]
0x1800d59d6  xorps   xmm0, xmm0
0x1800d59d9  mov     [rsp+1A0h+var_140], rax
0x1800d59de  xor     esi, esi
0x1800d59e0  xor     eax, eax
0x1800d59e2  mov     [rsp+1A0h+var_148], r9
0x1800d59e7  mov     dword ptr [rbp+0A0h+var_46], eax
0x1800d59ea  mov     r13, r8
0x1800d59ed  mov     [rbp+54h], rax
0x1800d59f1  mov     dword ptr [rbp+0A0h+var_46+2], eax
0x1800d59f4  movups  [rbp+0A0h+var_C0], xmm0
0x1800d59f8  mov     dword ptr [rbp+0A0h+var_C0+0Ah], eax
0x1800d59fb  mov     word ptr [rbp+0A0h+var_C0+0Eh], ax
0x1800d59ff  movups  [rbp+0A0h+var_A0], xmm0
0x1800d5a03  mov     dword ptr [rbp+0A0h+var_A0+0Ah], eax
0x1800d5a06  mov     word ptr [rbp+0A0h+var_A0+0Eh], ax
0x1800d5a0a  movups  [rbp+0A0h+var_80], xmm0
0x1800d5a0e  mov     dword ptr [rbp+0A0h+var_80+0Ah], eax
0x1800d5a11  mov     word ptr [rbp+0A0h+var_80+0Eh], ax
0x1800d5a15  movups  [rbp+0A0h+var_60], xmm0
0x1800d5a19  mov     dword ptr [rbp+0A0h+var_60+0Ah], eax
0x1800d5a1c  mov     word ptr [rbp+0A0h+var_60+0Eh], ax
0x1800d5a20  mov     eax, r14d
0x1800d5a23  shr     eax, 2
0x1800d5a26  and     al, 1
0x1800d5a28  mov     [rsp+1A0h+var_150], rdx
0x1800d5a2d  mov     byte ptr [rbp+0A0h+var_C0+8], al
0x1800d5a30  movzx   eax, r14b
0x1800d5a34  shr     al, 4
0x1800d5a37  and     al, 1
0x1800d5a39  mov     [rbp+0A0h+var_50], 0FFFFFFFFh
0x1800d5a40  mov     byte ptr [rbp+0A0h+var_4B], al
0x1800d5a43  movzx   eax, r14b
0x1800d5a47  shr     al, 3
0x1800d5a4a  and     al, 1
0x1800d5a4c  cmp     dword ptr [rdx+270h], 9300h
0x1800d5a56  movups  [rbp+0A0h+var_B0], xmm0
0x1800d5a5a  mov     [rbp+0A0h+var_4C], al
0x1800d5a5d  movzx   eax, byte ptr [r8+1Ch]
0x1800d5a62  movups  [rbp+0A0h+var_90], xmm0
0x1800d5a66  mov     byte ptr [rbp+0A0h+var_4B+3], al
0x1800d5a69  movzx   eax, byte ptr [r8+1Dh]
0x1800d5a6e  movups  [rbp+0A0h+var_70], xmm0
0x1800d5a72  mov     [rbp+0A0h+var_47], al
0x1800d5a75  movups  xmm0, xmmword ptr [r8+8]
0x1800d5a7a  mov     qword ptr [rbp+0A0h+var_B0], rcx
0x1800d5a7e  mov     dword ptr [rbp+0A0h+var_B0+8], esi
0x1800d5a81  mov     qword ptr [rbp+0A0h+var_90], rcx
0x1800d5a85  mov     dword ptr [rbp+0A0h+var_90+8], esi
0x1800d5a88  mov     qword ptr [rbp+0A0h+var_70], rcx
0x1800d5a8c  mov     dword ptr [rbp+0A0h+var_70+8], esi
0x1800d5a8f  movaps  [rbp+0A0h+var_D0], xmm0
0x1800d5a93  jl      loc_1800D5D2C
0x1800d5a99  mov     eax, [r8+18h]
0x1800d5a9d  mov     r12b, 1
0x1800d5aa0  mov     [rbp+0A0h+var_50], eax
0x1800d5aa3  mov     eax, r14d
0x1800d5aa6  shr     eax, 5
0x1800d5aa9  and     al, 1
0x1800d5aab  and     r14d, 3
0x1800d5aaf  mov     byte ptr [rbp+0A0h+var_C0+5], al
0x1800d5ab2  mov     r15d, r14d
0x1800d5ab5  mov     r8d, r14d
0x1800d5ab8  lea     rdx, [rsp+1A0h+var_170]
0x1800d5abd  lea     rcx, [rbp+0A0h+var_D0]
0x1800d5ac1  call    ?GetLookupKey@ShaderLinkingConfig@@QEBA?AULookupKey@1@I@Z; ShaderLinkingConfig::GetLookupKey(uint)
0x1800d5ac6  mov     r9, [rsp+1A0h+var_170]
0x1800d5acb  mov     eax, esi
0x1800d5acd  mov     r11d, dword ptr [rsp+1A0h+var_170+8]
0x1800d5ad2  mov     r8, cs:qword_1803B99E0
0x1800d5ad9  mov     r10, cs:?g_commonRenderingShaderCache@@3VCCommonRenderingShaderCache@@A; CCommonRenderingShaderCache g_commonRenderingShaderCache
0x1800d5ae0  mov     [rsp+1A0h+arg_0], rbx
0x1800d5ae8  mov     [rsp+1A0h+var_30], rdi
0x1800d5af0  cmp     eax, r8d
0x1800d5af3  jge     loc_1800D5C81
0x1800d5af9  movsxd  rdx, eax
0x1800d5afc  mov     rcx, rdx
0x1800d5aff  add     rcx, rcx
0x1800d5b02  cmp     [r10+rcx*8], r9
0x1800d5b06  jz      short loc_1800D5B0C
0x1800d5b08  inc     eax
0x1800d5b0a  jmp     short loc_1800D5AF0
0x1800d5b0c  cmp     [r10+rcx*8+8], r11d
0x1800d5b11  jnz     short loc_1800D5B08
0x1800d5b13  cmp     eax, 0FFFFFFFFh
0x1800d5b16  jz      loc_1800D5C81
0x1800d5b1c  mov     rax, cs:qword_1803B99D8
0x1800d5b23  mov     rsi, [rax+rdx*8]
0x1800d5b27  test    rsi, rsi
0x1800d5b2a  jz      loc_1800D5E54
0x1800d5b30  lock add dword ptr [rsi+8], 1
0x1800d5b35  jg      short loc_1800D5B55
0x1800d5b37  mov     rcx, [rbp+0A8h]; this
0x1800d5b3e  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d5b45  mov     r9d, 8007029Ch; char *
0x1800d5b4b  mov     edx, 18h; void *
0x1800d5b50  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d5b55  mov     ebx, 0FFFFFFFFh
0x1800d5b5a  mov     edi, ebx
0x1800d5b5c  lock xadd [rsi+8], edi
0x1800d5b61  dec     edi
0x1800d5b63  cmp     edi, ebx
0x1800d5b65  jl      loc_1800D5D42
0x1800d5b6b  test    edi, edi
0x1800d5b6d  jnz     loc_1800D5E54
0x1800d5b73  lock add dword ptr [rsi+8], 1
0x1800d5b78  jg      short loc_1800D5B98
0x1800d5b7a  mov     rcx, [rbp+0A8h]; this
0x1800d5b81  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d5b88  mov     r9d, 8007029Ch; char *
0x1800d5b8e  mov     edx, 18h; void *
0x1800d5b93  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d5b98  mov     rax, [rsi]
0x1800d5b9b  mov     rcx, rsi
0x1800d5b9e  mov     rax, [rax+18h]
0x1800d5ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5ba7  mov     edi, ebx
0x1800d5ba9  lock xadd [rsi+8], edi
0x1800d5bae  dec     edi
0x1800d5bb0  cmp     edi, ebx
0x1800d5bb2  jl      loc_1800D5D65
0x1800d5bb8  test    edi, edi
0x1800d5bba  jnz     loc_1800D5E54
0x1800d5bc0  lock xadd [rsi+8], ebx
0x1800d5bc5  dec     ebx
0x1800d5bc7  cmp     ebx, 0FFFFFFFFh
0x1800d5bca  jl      loc_1800D5D88
0x1800d5bd0  mov     rax, [rsi]
0x1800d5bd3  mov     edx, 1
0x1800d5bd8  mov     rcx, rsi
0x1800d5bdb  mov     rax, [rax+10h]
0x1800d5bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5be4  mov     r12, [rsp+1A0h+var_150]
0x1800d5be9  xor     edi, edi
0x1800d5beb  mov     rcx, [rsi+30h]
0x1800d5bef  mov     rax, [rsi+38h]
0x1800d5bf3  sub     rax, rcx
0x1800d5bf6  mov     edx, edi
0x1800d5bf8  sar     rax, 3
0x1800d5bfc  cmp     rdx, rax
0x1800d5bff  jnb     loc_1800D5DAB
0x1800d5c05  lea     r14, ds:0[rdi*8]
0x1800d5c0d  mov     rcx, [r14+rcx]
0x1800d5c11  mov     rax, [rcx]
0x1800d5c14  mov     rax, [rax+28h]
0x1800d5c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5c1d  cmp     r12, rax
0x1800d5c20  jnz     loc_1800D5E6A
0x1800d5c26  mov     rax, [rsi+30h]
0x1800d5c2a  mov     rdi, [r14+rax]
0x1800d5c2e  test    rdi, rdi
0x1800d5c31  jz      loc_1800D5DAB
0x1800d5c37  xor     r14d, r14d
0x1800d5c3a  mov     eax, [rsi+18h]
0x1800d5c3d  mov     rcx, [rsp+1A0h+var_148]
0x1800d5c42  mov     [rcx], eax
0x1800d5c44  mov     rcx, [rsp+1A0h+var_140]
0x1800d5c49  mov     rax, [rdi+78h]
0x1800d5c4d  mov     [rcx], rax
0x1800d5c50  mov     eax, r14d
0x1800d5c53  mov     rdi, [rsp+1A0h+var_30]
0x1800d5c5b  mov     rbx, [rsp+1A0h+arg_0]
0x1800d5c63  mov     rcx, [rbp+0A0h+var_40]
0x1800d5c67  xor     rcx, rsp; StackCookie
0x1800d5c6a  call    __security_check_cookie
0x1800d5c6f  add     rsp, 178h
0x1800d5c76  pop     r15
0x1800d5c78  pop     r14
0x1800d5c7a  pop     r13
0x1800d5c7c  pop     r12
0x1800d5c7e  pop     rsi
0x1800d5c7f  pop     rbp
0x1800d5c80  retn
0x1800d5c81  mov     [rsp+1A0h+var_170], rsi
0x1800d5c86  xor     eax, eax
0x1800d5c88  cmp     dword ptr [r13+10h], 1
0x1800d5c8d  ja      loc_1800D5F86
0x1800d5c93  cmp     dword ptr [r13+18h], 0FFFFFFFFh
0x1800d5c98  jnz     loc_1800D5F86
0x1800d5c9e  cmp     byte ptr [r13+1Dh], 0
0x1800d5ca3  jnz     loc_1800D5F86
0x1800d5ca9  mov     ecx, [r13+0]
0x1800d5cad  cmp     ecx, 5
0x1800d5cb0  jnz     loc_1800D5F74
0x1800d5cb6  mov     edi, 358h
0x1800d5cbb  lea     rsi, unk_1802D4E80
0x1800d5cc2  lea     rdx, [rsp+1A0h+ppBlob]; ppBlob
0x1800d5cc7  mov     [rsp+1A0h+var_170], 0
0x1800d5cd0  mov     rcx, rdi; Size
0x1800d5cd3  mov     [rsp+1A0h+ppBlob], 0
0x1800d5cdc  call    cs:__imp_D3DCreateBlob
0x1800d5ce2  mov     ebx, eax
0x1800d5ce4  test    eax, eax
0x1800d5ce6  jns     loc_1800D5E71
0x1800d5cec  mov     [rsp+1A0h+var_178], 0; void *
0x1800d5cf5  mov     r9d, eax; int
0x1800d5cf8  xor     r8d, r8d; unsigned int
0x1800d5cfb  mov     [rsp+1A0h+var_180], 47h ; 'G'; unsigned int
0x1800d5d03  xor     edx, edx; int *
0x1800d5d05  mov     ecx, 14h; unsigned int
0x1800d5d0a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d5d0f  mov     rcx, [rsp+1A0h+ppBlob]
0x1800d5d14  test    rcx, rcx
0x1800d5d17  jz      short loc_1800D5D25
0x1800d5d19  mov     rax, [rcx]
0x1800d5d1c  mov     rax, [rax+10h]
0x1800d5d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5d25  mov     eax, ebx
0x1800d5d27  jmp     loc_1800D5C53
0x1800d5d2c  mov     r15d, r14d
0x1800d5d2f  and     r15d, 3
0x1800d5d33  mov     r14d, r15d
0x1800d5d36  or      r14d, 4
0x1800d5d3a  xor     r12b, r12b
0x1800d5d3d  jmp     loc_1800D5AB5
0x1800d5d42  mov     rcx, [rbp+0A8h]; this
0x1800d5d49  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d5d50  mov     r9d, 8007029Ch; char *
0x1800d5d56  mov     edx, 26h ; '&'; void *
0x1800d5d5b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d5d60  jmp     loc_1800D5B6B
0x1800d5d65  mov     rcx, [rbp+0A8h]; this
0x1800d5d6c  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d5d73  mov     r9d, 8007029Ch; char *
0x1800d5d79  mov     edx, 26h ; '&'; void *
0x1800d5d7e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d5d83  jmp     loc_1800D5BB8
0x1800d5d88  mov     rcx, [rbp+0A8h]; this
0x1800d5d8f  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d5d96  mov     r9d, 8007029Ch; char *
0x1800d5d9c  mov     edx, 26h ; '&'; void *
0x1800d5da1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d5da6  jmp     loc_1800D5BD0
0x1800d5dab  mov     rcx, [rsi+28h]; this
0x1800d5daf  lea     r8, [rsp+1A0h+var_170]; struct CD3DPixelShader **
0x1800d5db4  mov     rdx, r12; struct CD3DDevice *
0x1800d5db7  mov     [rsp+1A0h+var_170], 0
0x1800d5dc0  call    ?CreateResource@CLinkedShader@@QEAAJPEAVCD3DDevice@@PEAPEAVCD3DPixelShader@@@Z; CLinkedShader::CreateResource(CD3DDevice *,CD3DPixelShader * *)
0x1800d5dc5  mov     r14d, eax
0x1800d5dc8  test    eax, eax
0x1800d5dca  jns     loc_1800D6050
0x1800d5dd0  mov     [rsp+1A0h+var_178], 0; void *
0x1800d5dd9  mov     r9d, eax; int
0x1800d5ddc  xor     r8d, r8d; unsigned int
0x1800d5ddf  mov     [rsp+1A0h+var_180], 52h ; 'R'; unsigned int
0x1800d5de7  xor     edx, edx; int *
0x1800d5de9  mov     ecx, 14h; unsigned int
0x1800d5dee  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d5df3  mov     rcx, [rsp+1A0h+var_170]
0x1800d5df8  test    rcx, rcx
0x1800d5dfb  jz      short loc_1800D5E09
0x1800d5dfd  mov     rax, [rcx]
0x1800d5e00  mov     rax, [rax+10h]
0x1800d5e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5e09  mov     [rsp+1A0h+var_178], 0; void *
0x1800d5e12  mov     r9d, r14d; int
0x1800d5e15  xor     r8d, r8d; unsigned int
0x1800d5e18  mov     [rsp+1A0h+var_180], 11h; unsigned int
0x1800d5e20  xor     edx, edx; int *
0x1800d5e22  mov     ecx, 14h; unsigned int
0x1800d5e27  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d5e2c  mov     r9d, r14d; int
0x1800d5e2f  mov     [rsp+1A0h+var_178], 0; void *
0x1800d5e38  xor     r8d, r8d; unsigned int
0x1800d5e3b  mov     [rsp+1A0h+var_180], 65h ; 'e'; unsigned int
0x1800d5e43  xor     edx, edx; int *
0x1800d5e45  mov     ecx, 14h; unsigned int
0x1800d5e4a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d5e4f  jmp     loc_1800D5C50
0x1800d5e54  mov     [rsp+1A0h+var_170], rsi
0x1800d5e59  test    rsi, rsi
0x1800d5e5c  jnz     loc_1800D5BE4
0x1800d5e62  mov     rax, rsi
0x1800d5e65  jmp     loc_1800D5C88
0x1800d5e6a  inc     edi
0x1800d5e6c  jmp     loc_1800D5BEB
0x1800d5e71  mov     rcx, [rsp+1A0h+ppBlob]
0x1800d5e76  mov     rax, [rcx]
0x1800d5e79  mov     rax, [rax+18h]
0x1800d5e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5e82  mov     r8, rdi; Size
0x1800d5e85  mov     rdx, rsi; Src
0x1800d5e88  mov     rcx, rax; void *
0x1800d5e8b  call    memcpy_0
0x1800d5e90  call    cs:__imp_GetProcessHeap
0x1800d5e96  xor     edx, edx; dwFlags
0x1800d5e98  mov     r8d, 58h ; 'X'; dwBytes
  ... truncated ...
```
