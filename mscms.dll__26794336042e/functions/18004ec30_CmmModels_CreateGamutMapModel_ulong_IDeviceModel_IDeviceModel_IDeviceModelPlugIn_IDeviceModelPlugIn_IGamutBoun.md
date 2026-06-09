# CmmModels::CreateGamutMapModel(ulong,IDeviceModel *,IDeviceModel *,IDeviceModelPlugIn *,IDeviceModelPlugIn *,IGamutBoundaryDescription *,IGamutBoundaryDescription *,IGamutMapModel * *,int *)

- ea: `0x18004ec30`
- end: `0x18004ee3d`
- name: `?CreateGamutMapModel@CmmModels@@QEAAJKPEAVIDeviceModel@@0PEAUIDeviceModelPlugIn@@1PEAVIGamutBoundaryDescription@@2PEAPEAVIGamutMapModel@@PEAH@Z`
- size: `525`
- prototype: `__int64 __fastcall(CmmModels *__hidden this, unsigned int, struct IDeviceModel *, struct IDeviceModel *, struct IDeviceModelPlugIn *, struct IDeviceModelPlugIn *, struct IGamutBoundaryDescription *, struct IGamutBoundaryDescription *, struct IGamutMapModel **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18005082c`

## callees

- `0x18002e5f0`
- `0x18004ec30`
- `0x18004f524`
- `0x180064518`
- `0x1800653b8`
- `0x180065828`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004ecae`
- `ntdll!EtwEventWrite` at `0x18004edcf`
- `ntdll!EtwEventWrite` at `0x18004ee18`
- `ntdll!EtwEventWrite` at `0x18004ecae`
- `ntdll!EtwEventWrite` at `0x18004edcf`
- `ntdll!EtwEventWrite` at `0x18004ee18`

## pseudocode

```c
__int64 __fastcall CmmModels::CreateGamutMapModel(
        CmmModels *this,
        unsigned int a2,
        struct IDeviceModel *a3,
        struct IDeviceModel *a4,
        struct IDeviceModelPlugIn *a5,
        struct IDeviceModelPlugIn *a6,
        struct IGamutBoundaryDescription *a7,
        struct IGamutBoundaryDescription *a8,
        struct IGamutMapModel **a9,
        int *a10)
{
  int v10; // ebx
  struct IGamutMapModel **v12; // r14
  int *v13; // rdi
  struct IGamutBoundaryDescription *v15; // r13
  int GamutMapData; // eax
  struct IXMLDOMDocument2 *v18; // rcx
  __int64 v19; // rcx
  int SGCKGamutMapModel; // eax
  struct IXMLDOMDocument2 *v21; // rdi
  unsigned int v23; // [rsp+30h] [rbp-48h] BYREF
  struct _GUID v24; // [rsp+38h] [rbp-40h] BYREF
  struct IXMLDOMDocument2 *v25[2]; // [rsp+48h] [rbp-30h] BYREF
  struct IGamutBoundaryDescription *v26; // [rsp+58h] [rbp-20h] BYREF
  __int64 v27; // [rsp+60h] [rbp-18h]
  unsigned int v28; // [rsp+C8h] [rbp+50h] BYREF

  v28 = a2;
  v10 = *((_DWORD *)this + 2);
  v12 = a9;
  v13 = a10;
  v15 = a7;
  v26 = a8;
  *a9 = 0;
  *v13 = 0;
  v23 = 0;
  v25[0] = (struct IXMLDOMDocument2 *)&v28;
  v25[1] = (struct IXMLDOMDocument2 *)4;
  EtwEventWrite(g_etwHandle, CREATING_GAMUT_MAP_MODEL, 1, v25);
  if ( v10 < 0 )
    goto LABEL_21;
  v25[0] = 0;
  v24 = 0;
  GamutMapData = CmmModels::GetGamutMapData(this, v28, v13, &v24, &v23, v25);
  v18 = v25[0];
  v10 = GamutMapData;
  *v13 = 0;
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v18->lpVtbl->Release)(v18);
  if ( v10 < 0 )
    goto LABEL_21;
  v25[0] = 0;
  switch ( v23 )
  {
    case 0u:
      SGCKGamutMapModel = CreateSGCKGamutMapModel((struct IGamutMapModel **)v25);
      goto LABEL_15;
    case 1u:
      v19 = 1;
      break;
    case 2u:
      SGCKGamutMapModel = CreateHueMapGamutMapModel((struct IGamutMapModel **)v25);
      goto LABEL_15;
    case 3u:
      v19 = 0;
      break;
    default:
      v10 = -2147467259;
LABEL_21:
      v26 = (struct IGamutBoundaryDescription *)v25;
      LODWORD(v25[0]) = v10;
      v27 = 4;
      EtwEventWrite(g_etwHandle, GAMUT_MAP_MODEL_CREATION_FAILED, 1, &v26);
      return (unsigned int)v10;
  }
  SGCKGamutMapModel = CreateMinDEObject(v19, v25);
LABEL_15:
  v21 = v25[0];
  v10 = SGCKGamutMapModel;
  if ( SGCKGamutMapModel >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IDeviceModel *, struct IDeviceModel *, struct IGamutBoundaryDescription *, struct IGamutBoundaryDescription *))v25[0]->lpVtbl->GetTypeInfoCount)(
            v25[0],
            a3,
            a4,
            v15,
            v26);
    if ( v10 >= 0 )
    {
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21->lpVtbl->AddRef)(v21);
      *v12 = (struct IGamutMapModel *)v21;
      v26 = (struct IGamutBoundaryDescription *)&v23;
      v27 = 4;
      EtwEventWrite(g_etwHandle, CREATED_STANDARD_GAMUT_MAP_MODEL, 1, &v26);
    }
  }
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21->lpVtbl->Release)(v21);
  if ( v10 < 0 )
    goto LABEL_21;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004ec30  mov     [rsp-40h+arg_8], edx
0x18004ec34  push    rbp
0x18004ec35  push    rbx
0x18004ec36  push    rsi
0x18004ec37  push    rdi
0x18004ec38  push    r12
0x18004ec3a  push    r13
0x18004ec3c  push    r14
0x18004ec3e  push    r15
0x18004ec40  mov     rbp, rsp
0x18004ec43  sub     rsp, 78h
0x18004ec47  mov     rax, cs:__security_cookie
0x18004ec4e  xor     rax, rsp
0x18004ec51  mov     [rbp+var_10], rax
0x18004ec55  mov     ebx, [rcx+8]
0x18004ec58  lea     rdx, CREATING_GAMUT_MAP_MODEL
0x18004ec5f  mov     rax, [rbp+arg_38]
0x18004ec66  mov     rsi, rcx
0x18004ec69  mov     r14, [rbp+arg_40]
0x18004ec70  xor     ecx, ecx
0x18004ec72  mov     rdi, [rbp+arg_48]
0x18004ec79  mov     r15, r8
0x18004ec7c  mov     r13, [rbp+arg_30]
0x18004ec80  mov     r12, r9
0x18004ec83  mov     [rbp+var_20], rax
0x18004ec87  lea     r9, [rbp+var_30]
0x18004ec8b  mov     [r14], rcx
0x18004ec8e  lea     r8d, [rcx+1]
0x18004ec92  mov     [rdi], ecx
0x18004ec94  lea     rax, [rbp+arg_8]
0x18004ec98  mov     [rbp+var_48], ecx
0x18004ec9b  mov     rcx, cs:g_etwHandle
0x18004eca2  mov     [rbp+var_30], rax
0x18004eca6  mov     [rbp+var_28], 4
0x18004ecae  call    cs:__imp_EtwEventWrite
0x18004ecb4  test    ebx, ebx
0x18004ecb6  js      loc_18004EDED
0x18004ecbc  mov     edx, [rbp+arg_8]; unsigned int
0x18004ecbf  lea     rax, [rbp+var_30]
0x18004ecc3  mov     [rsp+78h+var_50], rax; struct IXMLDOMDocument2 **
0x18004ecc8  lea     r9, [rbp+var_40]; struct _GUID *
0x18004eccc  lea     rax, [rbp+var_48]
0x18004ecd0  mov     [rbp+var_30], 0
0x18004ecd8  xorps   xmm0, xmm0
0x18004ecdb  mov     [rsp+78h+var_58], rax; unsigned int *
0x18004ece0  mov     r8, rdi; int *
0x18004ece3  mov     rcx, rsi; this
0x18004ece6  movups  xmmword ptr [rbp+var_40.Data1], xmm0
0x18004ecea  call    ?GetGamutMapData@CmmModels@@AEAAJKPEAHPEAU_GUID@@PEAKPEAPEAUIXMLDOMDocument2@@@Z; CmmModels::GetGamutMapData(ulong,int *,_GUID *,ulong *,IXMLDOMDocument2 * *)
0x18004ecef  mov     rcx, [rbp+var_30]
0x18004ecf3  mov     ebx, eax
0x18004ecf5  mov     dword ptr [rdi], 0
0x18004ecfb  test    rcx, rcx
0x18004ecfe  jz      short loc_18004ED0C
0x18004ed00  mov     rdx, [rcx]
0x18004ed03  mov     rax, [rdx+10h]
0x18004ed07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed0c  test    ebx, ebx
0x18004ed0e  js      loc_18004EDED
0x18004ed14  mov     eax, [rbp+var_48]
0x18004ed17  mov     [rbp+var_30], 0
0x18004ed1f  test    eax, eax
0x18004ed21  jz      short loc_18004ED5B
0x18004ed23  sub     eax, 1
0x18004ed26  jz      short loc_18004ED54
0x18004ed28  sub     eax, 1
0x18004ed2b  jz      short loc_18004ED49
0x18004ed2d  cmp     eax, 1
0x18004ed30  jz      short loc_18004ED3C
0x18004ed32  mov     ebx, 80004005h
0x18004ed37  jmp     loc_18004EDED
0x18004ed3c  xor     ecx, ecx
0x18004ed3e  lea     rdx, [rbp+var_30]
0x18004ed42  call    CreateMinDEObject
0x18004ed47  jmp     short loc_18004ED64
0x18004ed49  lea     rcx, [rbp+var_30]; struct IGamutMapModel **
0x18004ed4d  call    ?CreateHueMapGamutMapModel@@YAJPEAPEAVIGamutMapModel@@@Z; CreateHueMapGamutMapModel(IGamutMapModel * *)
0x18004ed52  jmp     short loc_18004ED64
0x18004ed54  mov     ecx, 1
0x18004ed59  jmp     short loc_18004ED3E
0x18004ed5b  lea     rcx, [rbp+var_30]; struct IGamutMapModel **
0x18004ed5f  call    ?CreateSGCKGamutMapModel@@YAJPEAPEAVIGamutMapModel@@@Z; CreateSGCKGamutMapModel(IGamutMapModel * *)
0x18004ed64  mov     rdi, [rbp+var_30]
0x18004ed68  mov     ebx, eax
0x18004ed6a  test    eax, eax
0x18004ed6c  js      short loc_18004EDD5
0x18004ed6e  mov     rax, [rdi]
0x18004ed71  mov     r9, r13
0x18004ed74  mov     rcx, [rbp+var_20]
0x18004ed78  mov     r8, r12
0x18004ed7b  mov     [rsp+78h+var_58], rcx
0x18004ed80  mov     rdx, r15
0x18004ed83  mov     rcx, rdi
0x18004ed86  mov     rax, [rax+18h]
0x18004ed8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed8f  mov     ebx, eax
0x18004ed91  test    eax, eax
0x18004ed93  js      short loc_18004EDD5
0x18004ed95  mov     rax, [rdi]
0x18004ed98  mov     rcx, rdi
0x18004ed9b  mov     rax, [rax+8]
0x18004ed9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eda4  lea     rax, [rbp+var_48]
0x18004eda8  mov     [r14], rdi
0x18004edab  mov     rcx, cs:g_etwHandle
0x18004edb2  lea     r9, [rbp+var_20]
0x18004edb6  mov     r8d, 1
0x18004edbc  mov     [rbp+var_20], rax
0x18004edc0  lea     rdx, CREATED_STANDARD_GAMUT_MAP_MODEL
0x18004edc7  mov     [rbp+var_18], 4
0x18004edcf  call    cs:__imp_EtwEventWrite
0x18004edd5  test    rdi, rdi
0x18004edd8  jz      short loc_18004EDE9
0x18004edda  mov     rax, [rdi]
0x18004eddd  mov     rcx, rdi
0x18004ede0  mov     rax, [rax+10h]
0x18004ede4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ede9  test    ebx, ebx
0x18004edeb  jns     short loc_18004EE1E
0x18004eded  mov     rcx, cs:g_etwHandle
0x18004edf4  lea     rax, [rbp+var_30]
0x18004edf8  lea     r9, [rbp+var_20]
0x18004edfc  mov     [rbp+var_20], rax
0x18004ee00  mov     r8d, 1
0x18004ee06  mov     dword ptr [rbp+var_30], ebx
0x18004ee09  lea     rdx, GAMUT_MAP_MODEL_CREATION_FAILED
0x18004ee10  mov     [rbp+var_18], 4
0x18004ee18  call    cs:__imp_EtwEventWrite
0x18004ee1e  mov     eax, ebx
0x18004ee20  mov     rcx, [rbp+var_10]
0x18004ee24  xor     rcx, rsp; StackCookie
0x18004ee27  call    __security_check_cookie
0x18004ee2c  add     rsp, 78h
0x18004ee30  pop     r15
0x18004ee32  pop     r14
0x18004ee34  pop     r13
0x18004ee36  pop     r12
0x18004ee38  pop     rdi
0x18004ee39  pop     rsi
0x18004ee3a  pop     rbx
0x18004ee3b  pop     rbp
0x18004ee3c  retn
```
