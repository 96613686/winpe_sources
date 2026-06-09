# WcsCreateIccProfile

- ea: `0x18004fc60`
- end: `0x180050242`
- name: `WcsCreateIccProfile`
- size: `1506`
- prototype: `HPROFILE __stdcall(HPROFILE hWcsProfile, DWORD dwOptions)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006e34`
- `0x18000bce0`
- `0x18000fe30`
- `0x180017a50`
- `0x1800181a0`
- `0x180018eb0`
- `0x1800223b8`
- `0x18002e670`
- `0x18002ea84`
- `0x18003c820`
- `0x18004e278`
- `0x18004e544`
- `0x18004ee44`
- `0x18004f504`
- `0x18004f628`
- `0x18004f694`
- `0x18004f6d8`
- `0x18004fad8`
- `0x18004fc0c`
- `0x18004fc60`
- `0x18006657c`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800501f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800501f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050203`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff16`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff52`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff81`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff16`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff52`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004ff81`

## pseudocode

```c
HPROFILE __stdcall WcsCreateIccProfile(HPROFILE hWcsProfile, DWORD dwOptions)
{
  HLOCAL v2; // r15
  int v3; // r14d
  char v5; // si
  int IDeviceModel; // ebx
  int v7; // ecx
  CmmModels *v8; // r12
  CmmModels *v9; // rax
  CmmModels *v10; // rax
  int v11; // eax
  int DeviceModelType; // edi
  unsigned int v13; // r15d
  HPROFILE v14; // rsi
  int v15; // r14d
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  struct IColorAppearanceModel *v22; // rdi
  struct IDeviceModelData *v23; // r13
  PVOID *v24; // r13
  UINT v25; // eax
  OLECHAR *v26; // rcx
  UINT v27; // r15d
  UINT v28; // edx
  unsigned int v29; // edi
  UINT v30; // r9d
  UINT v31; // r10d
  UINT v32; // ebx
  OLECHAR *v33; // rcx
  UINT v34; // r13d
  unsigned int v35; // eax
  OLECHAR *v36; // rcx
  UINT v37; // eax
  int v38; // r8d
  int v39; // edx
  int v40; // edx
  int v41; // r14d
  unsigned int v42; // r15d
  unsigned int v43; // ecx
  HLOCAL hMem; // [rsp+70h] [rbp-59h] BYREF
  struct IColorAppearanceModel *v46; // [rsp+78h] [rbp-51h] BYREF
  struct IDeviceModelData *v47; // [rsp+80h] [rbp-49h] BYREF
  PVOID *v48; // [rsp+88h] [rbp-41h]
  int v49; // [rsp+90h] [rbp-39h] BYREF
  struct _GUID v50; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v51; // [rsp+A8h] [rbp-21h]
  int v52; // [rsp+B0h] [rbp-19h]
  _BYTE v53[4]; // [rsp+B4h] [rbp-15h] BYREF
  struct IDeviceModel *v54; // [rsp+B8h] [rbp-11h] BYREF
  struct IXMLDOMDocument2 *v55; // [rsp+C0h] [rbp-9h] BYREF
  struct IXMLDOMDocument2 *v56; // [rsp+C8h] [rbp-1h] BYREF
  struct IXMLDOMDocument2 *v57; // [rsp+D0h] [rbp+7h] BYREF
  HLOCAL v58; // [rsp+D8h] [rbp+Fh] BYREF
  void *Block; // [rsp+E0h] [rbp+17h] BYREF
  struct IXMLDOMDocument2 *v60; // [rsp+E8h] [rbp+1Fh] BYREF
  unsigned int v62; // [rsp+140h] [rbp+77h] BYREF
  HPROFILE hProfile; // [rsp+148h] [rbp+7Fh] BYREF

  v2 = 0;
  v3 = 0;
  hMem = 0;
  v58 = 0;
  Block = 0;
  v5 = dwOptions;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  FPUStateSSE<0>::FPUStateSSE<0>(v53);
  IDeviceModel = -2147024809;
  if ( (unsigned int)ValidHandle(hWcsProfile, 1129860428) )
  {
    v7 = 0;
    v48 = *(PVOID **)(((unsigned __int64)hWcsProfile ^ 0x49434D20) + 0x40);
    if ( !v48 )
      v7 = -2147024809;
    IDeviceModel = v7;
  }
  else
  {
    v48 = 0;
  }
  v8 = 0;
  v49 = 0;
  if ( IDeviceModel >= 0 )
  {
    IDeviceModel = COMInit::CoInitialize((COMInit *)&v49);
    if ( IDeviceModel >= 0 )
    {
      v9 = (CmmModels *)operator new(0xE0u);
      v10 = CmmModels::CmmModels(v9);
      v8 = v10;
      if ( v10 )
      {
        v11 = CmmModels::Initialize(v10, hWcsProfile, 1, 0, &v55, &v56, &v57);
        v3 = (int)v55;
        IDeviceModel = v11;
      }
      else
      {
        IDeviceModel = -2147024882;
      }
    }
  }
  v54 = 0;
  v62 = 0;
  if ( IDeviceModel >= 0 )
    IDeviceModel = CmmModels::GetIDeviceModel(v8, (int *)&v62, &v54);
  v47 = 0;
  if ( IDeviceModel >= 0 )
    IDeviceModel = CmmModels::GetIDeviceModelData(v8, &v47);
  v46 = 0;
  if ( IDeviceModel >= 0 )
    IDeviceModel = CmmModels::GetIColorAppearanceModel(v8, &v46);
  DeviceModelType = 1;
  if ( IDeviceModel >= 0 )
    DeviceModelType = CmmModels::GetDeviceModelType(v8);
  v60 = 0;
  v62 = 0;
  LODWORD(hProfile) = 0;
  v50 = 0;
  if ( IDeviceModel < 0
    || (IDeviceModel = CmmModels::GetGamutMapData(v8, (int *)&hProfile, &v50, &v62, &v60), IDeviceModel < 0) )
  {
    v14 = 0;
    goto LABEL_69;
  }
  v13 = 3;
  v62 = v5 & 3;
  v14 = 0;
  hProfile = 0;
  IDeviceModel = CreateProfileDescription(
                   v3,
                   (_DWORD)v56,
                   (_DWORD)v57,
                   (unsigned int)&hMem,
                   (__int64)&v58,
                   (__int64)&Block);
  if ( IDeviceModel >= 0 )
  {
    v15 = 4;
    if ( DeviceModelType )
    {
      v16 = DeviceModelType - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                v21 = v20 - 1;
                if ( v21 )
                {
                  if ( v21 == 1 )
                    v13 = 8;
                  else
                    v13 = 0;
                }
                else
                {
                  v13 = 5;
                }
              }
              else
              {
                v13 = 4;
              }
            }
          }
        }
        else
        {
          v13 = 6;
        }
      }
      else
      {
        v13 = 1;
      }
    }
    else
    {
      v13 = 2;
    }
    v22 = v46;
    v23 = v47;
    IDeviceModel = CreateICCProfileFromWCSProfile(v13, v54, v47, v46, v62);
    if ( IDeviceModel < 0 || (dwOptions & 0x10000) != 0 )
    {
      v14 = hProfile;
      v2 = hMem;
      goto LABEL_70;
    }
    v24 = v48;
    v25 = 0;
    v51 = 0;
    v50 = 0;
    v26 = (OLECHAR *)v48[16];
    if ( v26 )
    {
      v25 = SysStringByteLen(v26);
      v27 = 0;
      v28 = 0;
      v29 = v25;
      v30 = v25;
      v31 = v25;
      v32 = v25;
    }
    else
    {
      v29 = *(_DWORD *)&v50.Data2;
      v28 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v27 = 0;
    }
    v33 = (OLECHAR *)v24[17];
    v62 = v25;
    if ( v33 )
    {
      v34 = SysStringByteLen(v33);
      v28 = v34;
      LODWORD(v14) = v34;
      v35 = v62;
    }
    else
    {
      v34 = *(_DWORD *)&v50.Data4[4];
      v35 = v30;
      v32 = v31;
      v27 = 0;
    }
    v36 = (OLECHAR *)v48[18];
    if ( v36 )
    {
      v37 = SysStringByteLen(v36);
      v27 = v37;
    }
    else
    {
      v32 = v35;
      LODWORD(v14) = v28;
      v37 = HIDWORD(v51);
    }
    v38 = (_DWORD)v14 + 32;
    v62 = v37;
    v14 = hProfile;
    if ( SetColorProfileElementSize(hProfile, 0x4D533030u, v32 + v27 + v38) )
    {
      LODWORD(hProfile) = 808538957;
      IDeviceModel = WriteProfileTagData((int)v14, v39, 0, 4, &hProfile);
      if ( IDeviceModel >= 0 )
      {
        LODWORD(hProfile) = 0;
        IDeviceModel = WriteProfileTagData((int)v14, v40, 4, 4, &hProfile);
        v15 = 8;
      }
      if ( IDeviceModel < 0 )
        goto LABEL_50;
      v52 = v15;
      v41 = v15 + 24;
      if ( v29 )
      {
        LODWORD(hProfile) = v41;
        IDeviceModel = WriteProfileTagData((int)v14, v40, v41, v29, v48[16]);
        if ( IDeviceModel < 0 )
          goto LABEL_50;
        v41 += v29;
      }
      else
      {
        LODWORD(hProfile) = v50.Data1;
      }
      if ( v34 )
      {
        v42 = v41;
        IDeviceModel = WriteProfileTagData((int)v14, v40, v41, v34, v48[17]);
        if ( IDeviceModel < 0 )
          goto LABEL_50;
        v41 += v34;
      }
      else
      {
        v42 = *(_DWORD *)v50.Data4;
      }
      v43 = v62;
      if ( v62 )
      {
        IDeviceModel = WriteProfileTagData((int)v14, v40, v41, v62, v48[18]);
        if ( IDeviceModel < 0 )
          goto LABEL_50;
        v43 = v62;
      }
      else
      {
        v41 = v51;
      }
      v50.Data1 = _byteswap_ulong((unsigned int)hProfile);
      *(_DWORD *)&v50.Data2 = _byteswap_ulong(v29);
      *(_DWORD *)&v50.Data4[4] = _byteswap_ulong(v34);
      *(_DWORD *)v50.Data4 = _byteswap_ulong(v42);
      v51 = _byteswap_uint64(__PAIR64__(v41, v43));
      IDeviceModel = WriteProfileTagData((int)v14, v40, v52, 24, &v50);
      goto LABEL_50;
    }
    IDeviceModel = -2147467259;
  }
LABEL_50:
  v2 = hMem;
LABEL_69:
  v23 = v47;
  v22 = v46;
LABEL_70:
  if ( v60 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v60->lpVtbl->Release)(v60);
  if ( v54 )
    (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v54 + 16LL))(v54);
  if ( v23 )
    (*(void (__fastcall **)(struct IDeviceModelData *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v22 )
    (*(void (__fastcall **)(struct IColorAppearanceModel *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v55 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v55->lpVtbl->Release)(v55);
  if ( v56 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v56->lpVtbl->Release)(v56);
  if ( v57 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v57->lpVtbl->Release)(v57);
  if ( v8 )
    (**(void (__fastcall ***)(CmmModels *, __int64))v8)(v8, 1);
  if ( IDeviceModel < 0 )
  {
    if ( v14 )
    {
      CloseColorProfile(v14);
      v14 = 0;
    }
    SetLastErrorFromHRESULT((unsigned int)IDeviceModel, 2011);
  }
  if ( v2 )
    LocalFree(v2);
  if ( v58 )
    LocalFree(v58);
  operator delete(Block);
  COMInit::~COMInit((COMInit *)&v49);
  FPUStateSSE<0>::~FPUStateSSE<0>(v53);
  return v14;
}

```

## disassembly

```asm
0x18004fc60  mov     [rsp-8+arg_0], rbx
0x18004fc65  mov     [rsp-8+arg_8], edx
0x18004fc69  push    rbp
0x18004fc6a  push    rsi
0x18004fc6b  push    rdi
0x18004fc6c  push    r12
0x18004fc6e  push    r13
0x18004fc70  push    r14
0x18004fc72  push    r15
0x18004fc74  lea     rbp, [rsp-27h]
0x18004fc79  sub     rsp, 0F0h
0x18004fc80  xor     r15d, r15d
0x18004fc83  xor     r14d, r14d
0x18004fc86  mov     rdi, rcx
0x18004fc89  mov     [rbp+57h+hMem], r15
0x18004fc8d  lea     rcx, [rbp+57h+var_6C]
0x18004fc91  mov     [rbp+57h+var_48], r15
0x18004fc95  mov     [rbp+57h+Block], r15
0x18004fc99  mov     esi, edx
0x18004fc9b  mov     [rbp+57h+var_60], r14
0x18004fc9f  mov     [rbp+57h+var_58], r14
0x18004fca3  mov     [rbp+57h+var_50], r14
0x18004fca7  call    ??0?$FPUStateSSE@$0A@@@QEAA@XZ; FPUStateSSE<0>::FPUStateSSE<0>(void)
0x18004fcac  mov     edx, 43584D4Ch
0x18004fcb1  mov     rcx, rdi
0x18004fcb4  call    ValidHandle
0x18004fcb9  mov     ebx, 80070057h
0x18004fcbe  test    eax, eax
0x18004fcc0  jnz     short loc_18004FCC8
0x18004fcc2  mov     [rbp+57h+var_98], r14
0x18004fcc6  jmp     short loc_18004FCE3
0x18004fcc8  xor     ecx, ecx
0x18004fcca  mov     rax, rdi
0x18004fccd  xor     rax, 49434D20h
0x18004fcd3  mov     rax, [rax+40h]
0x18004fcd7  test    rax, rax
0x18004fcda  mov     [rbp+57h+var_98], rax
0x18004fcde  cmovz   ecx, ebx
0x18004fce1  mov     ebx, ecx
0x18004fce3  xor     r12d, r12d
0x18004fce6  mov     [rbp+57h+var_90], r12d
0x18004fcea  test    ebx, ebx
0x18004fcec  js      short loc_18004FD51
0x18004fcee  lea     rcx, [rbp+57h+var_90]; this
0x18004fcf2  call    ?CoInitialize@COMInit@@QEAAJXZ; COMInit::CoInitialize(void)
0x18004fcf7  mov     ebx, eax
0x18004fcf9  test    eax, eax
0x18004fcfb  js      short loc_18004FD51
0x18004fcfd  mov     ecx, 0E0h; Size
0x18004fd02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fd07  mov     rcx, rax; this
0x18004fd0a  call    ??0CmmModels@@QEAA@XZ; CmmModels::CmmModels(void)
0x18004fd0f  mov     r12, rax
0x18004fd12  test    rax, rax
0x18004fd15  jnz     short loc_18004FD1E
0x18004fd17  mov     ebx, 8007000Eh
0x18004fd1c  jmp     short loc_18004FD51
0x18004fd1e  lea     rax, [rbp+57h+var_50]
0x18004fd22  xor     r9d, r9d; unsigned int
0x18004fd25  mov     [rsp+120h+var_F0], rax; struct IXMLDOMDocument2 **
0x18004fd2a  mov     rdx, rdi; void *
0x18004fd2d  lea     rax, [rbp+57h+var_58]
0x18004fd31  mov     rcx, r12; this
0x18004fd34  mov     [rsp+120h+var_F8], rax; struct IXMLDOMDocument2 **
0x18004fd39  lea     rax, [rbp+57h+var_60]
0x18004fd3d  lea     r8d, [r9+1]; unsigned int
0x18004fd41  mov     [rsp+120h+var_100], rax; struct IXMLDOMDocument2 **
0x18004fd46  call    ?Initialize@CmmModels@@QEAAJPEAXIIPEAPEAUIXMLDOMDocument2@@11@Z; CmmModels::Initialize(void *,uint,uint,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *)
0x18004fd4b  mov     r14, [rbp+57h+var_60]
0x18004fd4f  mov     ebx, eax
0x18004fd51  xor     r13d, r13d
0x18004fd54  mov     [rbp+57h+var_68], r15
0x18004fd58  mov     [rbp+57h+arg_10], r13d
0x18004fd5c  test    ebx, ebx
0x18004fd5e  js      short loc_18004FD76
0x18004fd60  lea     r8, [rbp+57h+var_68]; struct IDeviceModel **
0x18004fd64  mov     rcx, r12; this
0x18004fd67  lea     rdx, [rbp+57h+arg_10]; int *
0x18004fd6b  call    ?GetIDeviceModel@CmmModels@@QEAAJPEAHPEAPEAVIDeviceModel@@@Z; CmmModels::GetIDeviceModel(int *,IDeviceModel * *)
0x18004fd70  mov     r13d, [rbp+57h+arg_10]
0x18004fd74  mov     ebx, eax
0x18004fd76  mov     [rbp+57h+var_A0], r15
0x18004fd7a  test    ebx, ebx
0x18004fd7c  js      short loc_18004FD8C
0x18004fd7e  lea     rdx, [rbp+57h+var_A0]; struct IDeviceModelData **
0x18004fd82  mov     rcx, r12; this
0x18004fd85  call    ?GetIDeviceModelData@CmmModels@@QEAAJPEAPEAVIDeviceModelData@@@Z; CmmModels::GetIDeviceModelData(IDeviceModelData * *)
0x18004fd8a  mov     ebx, eax
0x18004fd8c  mov     [rbp+57h+var_A8], r15
0x18004fd90  test    ebx, ebx
0x18004fd92  js      short loc_18004FDA2
0x18004fd94  lea     rdx, [rbp+57h+var_A8]; struct IColorAppearanceModel **
0x18004fd98  mov     rcx, r12; this
0x18004fd9b  call    ?GetIColorAppearanceModel@CmmModels@@QEAAJPEAPEAVIColorAppearanceModel@@@Z; CmmModels::GetIColorAppearanceModel(IColorAppearanceModel * *)
0x18004fda0  mov     ebx, eax
0x18004fda2  mov     edi, 1
0x18004fda7  test    ebx, ebx
0x18004fda9  js      short loc_18004FDB5
0x18004fdab  mov     rcx, r12
0x18004fdae  call    ?GetDeviceModelType@CmmModels@@QEAA?AW4Enum@CdmpBaselineDeviceType@@XZ; CmmModels::GetDeviceModelType(void)
0x18004fdb3  mov     edi, eax
0x18004fdb5  mov     [rbp+57h+var_38], r15
0x18004fdb9  xorps   xmm0, xmm0
0x18004fdbc  mov     [rbp+57h+arg_10], r15d
0x18004fdc0  mov     dword ptr [rbp+57h+hProfile], r15d
0x18004fdc4  movups  xmmword ptr [rbp+57h+var_88.Data1], xmm0
0x18004fdc8  test    ebx, ebx
0x18004fdca  js      loc_180050118
0x18004fdd0  lea     rax, [rbp+57h+var_38]
0x18004fdd4  mov     rcx, r12; this
0x18004fdd7  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x18004fddb  mov     [rsp+120h+var_100], rax; struct IXMLDOMDocument2 **
0x18004fde0  lea     r8, [rbp+57h+var_88]; struct _GUID *
0x18004fde4  lea     rdx, [rbp+57h+hProfile]; int *
0x18004fde8  call    ?GetGamutMapData@CmmModels@@QEAAJPEAHPEAU_GUID@@PEAKPEAPEAUIXMLDOMDocument2@@@Z; CmmModels::GetGamutMapData(int *,_GUID *,ulong *,IXMLDOMDocument2 * *)
0x18004fded  mov     ebx, eax
0x18004fdef  test    eax, eax
0x18004fdf1  js      loc_180050118
0x18004fdf7  mov     r8, [rbp+57h+var_50]
0x18004fdfb  lea     rax, [rbp+57h+Block]
0x18004fdff  mov     rdx, [rbp+57h+var_58]
0x18004fe03  lea     r9, [rbp+57h+hMem]
0x18004fe07  mov     [rsp+120h+var_F8], rax
0x18004fe0c  mov     r15d, 3
0x18004fe12  and     esi, r15d
0x18004fe15  lea     rax, [rbp+57h+var_48]
0x18004fe19  mov     [rbp+57h+arg_10], esi
0x18004fe1c  mov     rcx, r14
0x18004fe1f  xor     esi, esi
0x18004fe21  mov     [rsp+120h+var_100], rax
0x18004fe26  mov     [rbp+57h+hProfile], rsi
0x18004fe2a  call    CreateProfileDescription
0x18004fe2f  mov     ebx, eax
0x18004fe31  test    eax, eax
0x18004fe33  js      loc_18004FFBA
0x18004fe39  mov     rcx, [rbp+57h+var_48]
0x18004fe3d  lea     r14d, [r15+1]
0x18004fe41  test    edi, edi
0x18004fe43  jz      short loc_18004FE92
0x18004fe45  sub     edi, 1
0x18004fe48  jz      short loc_18004FE8A
0x18004fe4a  sub     edi, 1
0x18004fe4d  jz      short loc_18004FE82
0x18004fe4f  sub     edi, 1
0x18004fe52  jz      short loc_18004FE98
0x18004fe54  sub     edi, 1
0x18004fe57  jz      short loc_18004FE98
0x18004fe59  sub     edi, 1
0x18004fe5c  jz      short loc_18004FE7D
0x18004fe5e  sub     edi, 1
0x18004fe61  jz      short loc_18004FE75
0x18004fe63  cmp     edi, 1
0x18004fe66  jz      short loc_18004FE6D
0x18004fe68  xor     r15d, r15d
0x18004fe6b  jmp     short loc_18004FE98
0x18004fe6d  mov     r15d, 8
0x18004fe73  jmp     short loc_18004FE98
0x18004fe75  mov     r15d, 5
0x18004fe7b  jmp     short loc_18004FE98
0x18004fe7d  mov     r15d, r14d
0x18004fe80  jmp     short loc_18004FE98
0x18004fe82  mov     r15d, 6
0x18004fe88  jmp     short loc_18004FE98
0x18004fe8a  mov     r15d, 1
0x18004fe90  jmp     short loc_18004FE98
0x18004fe92  mov     r15d, 2
0x18004fe98  mov     rdi, [rbp+57h+var_A8]
0x18004fe9c  lea     rax, [rbp+57h+hProfile]
0x18004fea0  mov     rdx, [rbp+57h+var_68]
0x18004fea4  mov     r9, rdi
0x18004fea7  mov     [rsp+120h+var_C0], rax
0x18004feac  mov     rax, [rbp+57h+Block]
0x18004feb0  mov     [rsp+120h+var_C8], esi
0x18004feb4  mov     [rsp+120h+var_D0], r13d
0x18004feb9  mov     r13, [rbp+57h+var_A0]
0x18004febd  mov     [rsp+120h+var_D8], rax
0x18004fec2  mov     r8, r13
0x18004fec5  mov     rax, [rbp+57h+hMem]
0x18004fec9  mov     [rsp+120h+var_E0], rcx
0x18004fece  mov     ecx, r15d
0x18004fed1  mov     [rsp+120h+var_E8], rax
0x18004fed6  mov     eax, [rbp+57h+arg_10]
0x18004fed9  mov     dword ptr [rsp+120h+var_100], eax
0x18004fedd  call    ?CreateICCProfileFromWCSProfile@@YAJW4EDeviceModelType@@PEAVIDeviceModel@@PEAVIDeviceModelData@@PEAVIColorAppearanceModel@@KPEAVIGamutMapModel@@4PEBDPEBG6HHPEAPEAX@Z; CreateICCProfileFromWCSProfile(EDeviceModelType,IDeviceModel *,IDeviceModelData *,IColorAppearanceModel *,ulong,IGamutMapModel *,IGamutMapModel *,char const *,ushort const *,ushort const *,int,int,void * *)
0x18004fee2  mov     ebx, eax
0x18004fee4  test    eax, eax
0x18004fee6  js      loc_18005010E
0x18004feec  test    [rbp+57h+arg_8], 10000h
0x18004fef3  jnz     loc_18005010E
0x18004fef9  mov     r13, [rbp+57h+var_98]
0x18004fefd  xor     eax, eax
0x18004feff  xorps   xmm0, xmm0
0x18004ff02  mov     [rbp+57h+var_78], rax
0x18004ff06  movups  xmmword ptr [rbp+57h+var_88.Data1], xmm0
0x18004ff0a  mov     rcx, [r13+80h]; bstr
0x18004ff11  test    rcx, rcx
0x18004ff14  jz      short loc_18004FF30
0x18004ff16  call    cs:__imp_SysStringByteLen
0x18004ff1c  xor     r8d, r8d
0x18004ff1f  xor     r15d, r15d
0x18004ff22  xor     edx, edx
0x18004ff24  mov     edi, eax
0x18004ff26  mov     r9d, eax
0x18004ff29  mov     r10d, eax
0x18004ff2c  mov     ebx, eax
0x18004ff2e  jmp     short loc_18004FF43
0x18004ff30  mov     edi, dword ptr [rbp+57h+var_88.Data2]
0x18004ff33  xor     r8d, r8d
0x18004ff36  xor     edx, edx
0x18004ff38  xor     r9d, r9d
0x18004ff3b  xor     r10d, r10d
0x18004ff3e  xor     ebx, ebx
0x18004ff40  xor     r15d, r15d
0x18004ff43  mov     rcx, [r13+88h]; bstr
0x18004ff4a  mov     [rbp+57h+arg_10], eax
0x18004ff4d  test    rcx, rcx
0x18004ff50  jz      short loc_18004FF64
0x18004ff52  call    cs:__imp_SysStringByteLen
0x18004ff58  mov     r13d, eax
0x18004ff5b  mov     edx, eax
0x18004ff5d  mov     esi, eax
0x18004ff5f  mov     eax, [rbp+57h+arg_10]
0x18004ff62  jmp     short loc_18004FF71
0x18004ff64  mov     r13d, dword ptr [rbp+57h+var_88.Data4+4]
0x18004ff68  mov     eax, r9d
0x18004ff6b  mov     ebx, r10d
0x18004ff6e  mov     r15d, r8d
0x18004ff71  mov     rcx, [rbp+57h+var_98]
0x18004ff75  mov     rcx, [rcx+90h]; bstr
0x18004ff7c  test    rcx, rcx
0x18004ff7f  jz      short loc_18004FF8C
0x18004ff81  call    cs:__imp_SysStringByteLen
0x18004ff87  mov     r15d, eax
0x18004ff8a  jmp     short loc_18004FF93
0x18004ff8c  mov     ebx, eax
0x18004ff8e  mov     esi, edx
0x18004ff90  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18004ff93  lea     r8d, [rsi+20h]
0x18004ff97  mov     [rbp+57h+arg_10], eax
0x18004ff9a  mov     rsi, [rbp+57h+hProfile]
0x18004ff9e  add     r8d, r15d
0x18004ffa1  add     r8d, ebx; pcbElement
0x18004ffa4  mov     edx, 4D533030h; tagType
0x18004ffa9  mov     rcx, rsi; hProfile
0x18004ffac  call    SetColorProfileElementSize
0x18004ffb1  test    eax, eax
0x18004ffb3  jnz     short loc_18004FFC3
0x18004ffb5  mov     ebx, 80004005h
0x18004ffba  mov     r15, [rbp+57h+hMem]
0x18004ffbe  jmp     loc_18005011A
0x18004ffc3  lea     rax, [rbp+57h+hProfile]
0x18004ffc7  mov     dword ptr [rbp+57h+hProfile], 3031534Dh
0x18004ffce  mov     r9d, r14d; int
0x18004ffd1  mov     [rsp+120h+var_100], rax; PVOID
0x18004ffd6  xor     r8d, r8d; int
0x18004ffd9  mov     rcx, rsi; int
0x18004ffdc  call    WriteProfileTagData
0x18004ffe1  mov     ebx, eax
0x18004ffe3  test    eax, eax
0x18004ffe5  js      short loc_18005000D
0x18004ffe7  lea     rax, [rbp+57h+hProfile]
0x18004ffeb  mov     dword ptr [rbp+57h+hProfile], 0
0x18004fff2  mov     r9d, r14d; int
0x18004fff5  mov     [rsp+120h+var_100], rax; PVOID
0x18004fffa  mov     r8d, r14d; int
0x18004fffd  mov     rcx, rsi; int
0x180050000  call    WriteProfileTagData
0x180050005  mov     ebx, eax
0x180050007  mov     r14d, 8
0x18005000d  test    ebx, ebx
0x18005000f  js      short loc_18004FFBA
0x180050011  mov     [rbp+57h+var_70], r14d
0x180050015  add     r14d, 18h
0x180050019  test    edi, edi
0x18005001b  jz      short loc_18005004E
0x18005001d  mov     rax, [rbp+57h+var_98]
0x180050021  mov     r9d, edi; int
0x180050024  mov     r8d, r14d; int
0x180050027  mov     dword ptr [rbp+57h+hProfile], r14d
0x18005002b  mov     rcx, rsi; int
0x18005002e  mov     rax, [rax+80h]
0x180050035  mov     [rsp+120h+var_100], rax; PVOID
0x18005003a  call    WriteProfileTagData
0x18005003f  mov     ebx, eax
0x180050041  test    eax, eax
0x180050043  js      loc_18004FFBA
0x180050049  add     r14d, edi
0x18005004c  jmp     short loc_180050054
0x18005004e  mov     eax, [rbp+57h+var_88.Data1]
0x180050051  mov     dword ptr [rbp+57h+hProfile], eax
0x180050054  test    r13d, r13d
0x180050057  jz      short loc_180050089
0x180050059  mov     rax, [rbp+57h+var_98]
0x18005005d  mov     r9d, r13d; int
0x180050060  mov     r8d, r14d; int
0x180050063  mov     rcx, rsi; int
0x180050066  mov     r15d, r14d
0x180050069  mov     rax, [rax+88h]
0x180050070  mov     [rsp+120h+var_100], rax; PVOID
0x180050075  call    WriteProfileTagData
  ... truncated ...
```
