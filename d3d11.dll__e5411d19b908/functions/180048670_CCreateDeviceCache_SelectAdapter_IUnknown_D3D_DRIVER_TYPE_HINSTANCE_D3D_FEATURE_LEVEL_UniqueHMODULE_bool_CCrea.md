# CCreateDeviceCache::SelectAdapter(IUnknown *,D3D_DRIVER_TYPE,HINSTANCE__ *,D3D_FEATURE_LEVEL,UniqueHMODULE &,bool,CCreateDeviceCache::CAdapterCache * *)

- ea: `0x180048670`
- end: `0x180048b2d`
- name: `?SelectAdapter@CCreateDeviceCache@@QEAAJPEAUIUnknown@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@W4D3D_FEATURE_LEVEL@@AEAVUniqueHMODULE@@_NPEAPEAVCAdapterCache@1@@Z`
- size: `1213`
- prototype: `__int64 __usercall@<rax>(CCreateDeviceCache *__hidden this@<rcx>, struct IUnknown *@<rdx>, enum D3D_DRIVER_TYPE@<r8d>, HINSTANCE@<r9>, enum D3D_FEATURE_LEVEL, struct UniqueHMODULE *, bool, struct CCreateDeviceCache::CAdapterCache **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047a80`
- `0x180049020`

## callees

- `0x180022400`
- `0x180034550`
- `0x180048670`
- `0x18005e200`
- `0x18005e38c`
- `0x18005e4a0`
- `0x1800a4174`
- `0x1800a69dc`
- `0x1800b01a0`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180048716`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180048716`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180048795`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180048795`

## string_xrefs

- `0x1800487ea`: `D3D11.dll`
- `0x18004870a`: `D3D10Warp.dll`
- `0x18004882e`: `d3d11ref.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCreateDeviceCache::SelectAdapter(
        struct IDXGIAdapter **this,
        struct IUnknown *a2,
        enum D3D_DRIVER_TYPE a3,
        const CHAR *a4,
        enum D3D_FEATURE_LEVEL a5,
        struct UniqueHMODULE *a6,
        bool a7,
        struct CCreateDeviceCache::CAdapterCache **a8)
{
  struct CCreateDeviceCache::CAdapterCache **v10; // r15
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  const CHAR *v15; // rcx
  HMODULE Library; // rax
  HMODULE v17; // r8
  struct CCreateDeviceCache::CAdapterCache *Software; // rax
  enum D3D_FEATURE_LEVEL v20; // edi
  int v21; // eax
  UniqueHMODULE *v22; // rsi
  int v23; // eax
  struct CCreateDeviceCache::CAdapterCache *Level9; // rbx
  enum D3D_FEATURE_LEVEL v25; // esi
  UniqueHMODULE *v26; // r14
  unsigned int v27; // edi
  struct CCreateDeviceCache::CAdapterCache *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // [rsp+30h] [rbp-30h] BYREF
  struct IDXCoreAdapter *v31; // [rsp+38h] [rbp-28h] BYREF
  __int64 v32; // [rsp+40h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-18h] BYREF
  HINSTANCE v34[2]; // [rsp+50h] [rbp-10h] BYREF
  enum D3D_DRIVER_TYPE v35; // [rsp+A0h] [rbp+40h] BYREF

  v35 = a3;
  if ( dword_18022B910 < 2 )
    dword_18022B914 = 2;
  dword_18022B910 = 2;
  v10 = a8;
  *a8 = 0;
  v31 = 0;
  if ( a3 )
  {
    v11 = a3 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( !v14 )
          {
            if ( a5 != D3D_FEATURE_LEVEL_9_1
              && a5 != D3D_FEATURE_LEVEL_9_2
              && a5 != D3D_FEATURE_LEVEL_9_3
              && a5 != D3D_FEATURE_LEVEL_10_0
              && a5 != D3D_FEATURE_LEVEL_10_1
              && a5 != D3D_FEATURE_LEVEL_11_0
              && a5 != D3D_FEATURE_LEVEL_11_1
              && a5 != D3D_FEATURE_LEVEL_12_0
              && a5 != D3D_FEATURE_LEVEL_12_1 )
            {
              ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v31);
              return 2289696772LL;
            }
            phModule = 0;
            GetModuleHandleExA(4u, a4, &phModule);
            v17 = phModule;
            goto LABEL_14;
          }
          if ( v14 != 1 )
          {
            ThrowFailure(-2147024809);
LABEL_81:
            v27 = -2005270524;
            goto LABEL_88;
          }
          if ( a5 == (D3D_FEATURE_LEVEL_12_0|0x200) )
            goto LABEL_81;
          v15 = "D3D10Warp.dll";
        }
        else
        {
          if ( a5 != D3D_FEATURE_LEVEL_9_1
            && a5 != D3D_FEATURE_LEVEL_9_2
            && a5 != D3D_FEATURE_LEVEL_9_3
            && a5 != D3D_FEATURE_LEVEL_10_0
            && a5 != D3D_FEATURE_LEVEL_10_1
            && a5 != D3D_FEATURE_LEVEL_11_0
            && a5 != D3D_FEATURE_LEVEL_11_1
            && a5 != D3D_FEATURE_LEVEL_12_0
            && a5 != D3D_FEATURE_LEVEL_12_1 )
          {
            goto LABEL_81;
          }
          v15 = "D3D11.dll";
        }
        Library = LoadLibraryExA(v15, 0, 0);
      }
      else
      {
        if ( a5 != D3D_FEATURE_LEVEL_9_1
          && a5 != D3D_FEATURE_LEVEL_9_2
          && a5 != D3D_FEATURE_LEVEL_9_3
          && a5 != D3D_FEATURE_LEVEL_10_0
          && a5 != D3D_FEATURE_LEVEL_10_1
          && a5 != D3D_FEATURE_LEVEL_11_0
          && a5 != D3D_FEATURE_LEVEL_11_1 )
        {
          goto LABEL_81;
        }
        Library = CModule::SDKLoadLibraryW((CModule *)&g_Module, L"d3d11ref.dll");
      }
      v17 = Library;
LABEL_14:
      Software = CCreateDeviceCache::CAdapterCache::CreateSoftware(
                   (CCreateDeviceCache::CAdapterCache *)(this + 2),
                   (struct CCreateDeviceCache *)this,
                   v17);
LABEL_61:
      Level9 = Software;
      goto LABEL_80;
    }
    v20 = a5;
    if ( ((a5 - 37120) & 0xFFFFFCFF) != 0 || a5 == 37888 )
    {
      if ( a5 != D3D_FEATURE_LEVEL_10_0
        && a5 != D3D_FEATURE_LEVEL_10_1
        && a5 != D3D_FEATURE_LEVEL_11_0
        && a5 != D3D_FEATURE_LEVEL_11_1
        && a5 != D3D_FEATURE_LEVEL_12_0
        && a5 != D3D_FEATURE_LEVEL_12_1 )
      {
        goto LABEL_81;
      }
    }
    else
    {
      if ( !CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(
              (CCreateDeviceCache::CAdapterCache *)(this + 2),
              (struct CCreateDeviceCache *)this,
              0) )
        goto LABEL_81;
      if ( a7 )
      {
        v32 = 0;
        v21 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, GUID *, __int64 *))this[5]->lpVtbl->QueryInterface)(
                this[5],
                &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf,
                &v32);
        ThrowFailure(v21);
        v22 = a6;
        if ( !*(_QWORD *)a6 )
        {
          a8 = 0;
          v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CCreateDeviceCache::CAdapterCache ***))(*(_QWORD *)v32 + 32LL))(
                  v32,
                  0,
                  &a8);
          ThrowFailure(v23);
          UniqueHMODULE::attach(v22, (HINSTANCE)a8);
        }
        Level9 = CCreateDeviceCache::CAdapterCache::CreateLevel9(
                   (CCreateDeviceCache::CAdapterCache *)(this + 27),
                   v20,
                   this[5]);
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v32);
LABEL_80:
        if ( Level9 )
        {
          if ( !*((_QWORD *)Level9 + 2) )
          {
            v29 = *((_QWORD *)Level9 + 3);
            if ( v29 )
            {
              if ( v35 )
                (*(void (__fastcall **)(__int64, GUID *, __int64, enum D3D_DRIVER_TYPE *))(*(_QWORD *)v29 + 24LL))(
                  v29,
                  &GUID_DeviceType,
                  4,
                  &v35);
              (***((void (__fastcall ****)(_QWORD, GUID *, __int64))Level9 + 3))(
                *((_QWORD *)Level9 + 3),
                &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf,
                (__int64)Level9 + 16);
            }
          }
          *v10 = Level9;
          v27 = 0;
          goto LABEL_88;
        }
        goto LABEL_81;
      }
    }
    Software = CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(
                 (CCreateDeviceCache::CAdapterCache *)(this + 2),
                 (struct CCreateDeviceCache *)this,
                 0);
    goto LABEL_61;
  }
  if ( a2
    && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDXCoreAdapter **, const CHAR *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
         &v31,
         a4) >= 0 )
  {
    Software = CCreateDeviceCache::CAdapterCache::ChooseDXCoreAdapter(
                 (CCreateDeviceCache::CAdapterCache *)(this + 2),
                 (struct CCreateDeviceCache *)this,
                 v31);
    goto LABEL_61;
  }
  a8 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct CCreateDeviceCache::CAdapterCache ***, const CHAR *))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0,
    &a8,
    a4);
  v25 = a5;
  if ( ((a5 - 37120) & 0xFFFFFCFF) != 0 || a5 == 37888 )
  {
    if ( a5 != D3D_FEATURE_LEVEL_10_0
      && a5 != D3D_FEATURE_LEVEL_10_1
      && a5 != D3D_FEATURE_LEVEL_11_0
      && a5 != D3D_FEATURE_LEVEL_11_1
      && a5 != D3D_FEATURE_LEVEL_12_0
      && a5 != D3D_FEATURE_LEVEL_12_1 )
    {
      v27 = -2005270524;
      goto LABEL_77;
    }
    goto LABEL_78;
  }
  if ( !a7 )
  {
LABEL_78:
    v28 = CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(
            (CCreateDeviceCache::CAdapterCache *)(this + 2),
            (struct CCreateDeviceCache *)this,
            (struct IDXGIAdapter *)a8);
    goto LABEL_79;
  }
  v26 = a6;
  if ( *(_QWORD *)a6 )
  {
LABEL_69:
    v28 = CCreateDeviceCache::CAdapterCache::CreateLevel9(
            (CCreateDeviceCache::CAdapterCache *)(this + 27),
            v25,
            (struct IDXGIAdapter *)a8);
LABEL_79:
    Level9 = v28;
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&a8);
    goto LABEL_80;
  }
  v34[0] = 0;
  v30 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf,
    &v30);
  v27 = -2005270523;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, HINSTANCE *))(*(_QWORD *)v30 + 32LL))(v30, 0, v34) != -2005270523 )
  {
    UniqueHMODULE::attach(v26, v34[0]);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v30);
    if ( *(_QWORD *)v26 )
      goto LABEL_69;
    goto LABEL_78;
  }
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v30);
LABEL_77:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&a8);
LABEL_88:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v31);
  return v27;
}

```

## disassembly

```asm
0x180048670  mov     [rsp-28h+arg_0], rbx
0x180048675  mov     [rsp-28h+arg_8], rsi
0x18004867a  mov     [rsp-28h+arg_10], r8d
0x18004867f  push    rbp
0x180048680  push    rdi
0x180048681  push    r12
0x180048683  push    r14
0x180048685  push    r15
0x180048687  mov     rbp, rsp
0x18004868a  sub     rsp, 60h
0x18004868e  mov     rdi, rdx
0x180048691  mov     rbx, rcx
0x180048694  mov     eax, 2
0x180048699  cmp     cs:dword_18022B910, eax
0x18004869f  jge     short loc_1800486A7
0x1800486a1  mov     cs:dword_18022B914, eax
0x1800486a7  mov     cs:dword_18022B910, eax
0x1800486ad  xor     r12d, r12d
0x1800486b0  mov     r15, [rbp+arg_38]
0x1800486b4  mov     [r15], r12
0x1800486b7  mov     [rbp+var_28], r12
0x1800486bb  test    r8d, r8d
0x1800486be  jz      loc_18004894B
0x1800486c4  sub     r8d, 1
0x1800486c8  jz      loc_180048846
0x1800486ce  sub     r8d, 1
0x1800486d2  jz      loc_1800487F6
0x1800486d8  sub     r8d, 1
0x1800486dc  jz      loc_1800487A4
0x1800486e2  sub     r8d, 1
0x1800486e6  jz      short loc_180048730
0x1800486e8  cmp     r8d, 1
0x1800486ec  jz      short loc_1800486FD
0x1800486ee  mov     ecx, 80070057h; int
0x1800486f3  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800486f8  jmp     loc_180048AB0
0x1800486fd  cmp     [rbp+arg_20], 0C200h
0x180048704  jz      loc_180048AB0
0x18004870a  lea     rcx, LibFileName; "D3D10Warp.dll"
0x180048711  xor     r8d, r8d; dwFlags
0x180048714  xor     edx, edx; hFile
0x180048716  call    cs:__imp_LoadLibraryExA
0x18004871c  mov     r8, rax; HINSTANCE
0x18004871f  lea     rcx, [rbx+10h]; this
0x180048723  mov     rdx, rbx; struct CCreateDeviceCache *
0x180048726  call    ?CreateSoftware@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@PEAV2@PEAUHINSTANCE__@@@Z; CCreateDeviceCache::CAdapterCache::CreateSoftware(CCreateDeviceCache *,HINSTANCE__ *)
0x18004872b  jmp     loc_18004897D
0x180048730  mov     eax, [rbp+arg_20]
0x180048733  cmp     eax, 9100h
0x180048738  jz      short loc_180048785
0x18004873a  cmp     eax, 9200h
0x18004873f  jz      short loc_180048785
0x180048741  cmp     eax, 9300h
0x180048746  jz      short loc_180048785
0x180048748  cmp     eax, 0A000h
0x18004874d  jz      short loc_180048785
0x18004874f  cmp     eax, 0A100h
0x180048754  jz      short loc_180048785
0x180048756  cmp     eax, 0B000h
0x18004875b  jz      short loc_180048785
0x18004875d  cmp     eax, 0B100h
0x180048762  jz      short loc_180048785
0x180048764  cmp     eax, 0C000h
0x180048769  jz      short loc_180048785
0x18004876b  cmp     eax, 0C100h
0x180048770  jz      short loc_180048785
0x180048772  lea     rcx, [rbp+var_28]
0x180048776  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18004877b  mov     eax, 887A0004h
0x180048780  jmp     loc_180048B14
0x180048785  mov     [rbp+phModule], r12
0x180048789  lea     r8, [rbp+phModule]; phModule
0x18004878d  mov     rdx, r9; lpModuleName
0x180048790  mov     ecx, 4; dwFlags
0x180048795  call    cs:__imp_GetModuleHandleExA
0x18004879b  mov     r8, [rbp+phModule]
0x18004879f  jmp     loc_18004871F
0x1800487a4  mov     eax, [rbp+arg_20]
0x1800487a7  cmp     eax, 9100h
0x1800487ac  jz      short loc_1800487EA
0x1800487ae  cmp     eax, 9200h
0x1800487b3  jz      short loc_1800487EA
0x1800487b5  cmp     eax, 9300h
0x1800487ba  jz      short loc_1800487EA
0x1800487bc  cmp     eax, 0A000h
0x1800487c1  jz      short loc_1800487EA
0x1800487c3  cmp     eax, 0A100h
0x1800487c8  jz      short loc_1800487EA
0x1800487ca  cmp     eax, 0B000h
0x1800487cf  jz      short loc_1800487EA
0x1800487d1  cmp     eax, 0B100h
0x1800487d6  jz      short loc_1800487EA
0x1800487d8  cmp     eax, 0C000h
0x1800487dd  jz      short loc_1800487EA
0x1800487df  cmp     eax, 0C100h
0x1800487e4  jnz     loc_180048AB0
0x1800487ea  lea     rcx, aD3d11Dll_0; "D3D11.dll"
0x1800487f1  jmp     loc_180048711
0x1800487f6  mov     eax, [rbp+arg_20]
0x1800487f9  cmp     eax, 9100h
0x1800487fe  jz      short loc_18004882E
0x180048800  cmp     eax, 9200h
0x180048805  jz      short loc_18004882E
0x180048807  cmp     eax, 9300h
0x18004880c  jz      short loc_18004882E
0x18004880e  cmp     eax, 0A000h
0x180048813  jz      short loc_18004882E
0x180048815  cmp     eax, 0A100h
0x18004881a  jz      short loc_18004882E
0x18004881c  cmp     eax, 0B000h
0x180048821  jz      short loc_18004882E
0x180048823  cmp     eax, 0B100h
0x180048828  jnz     loc_180048AB0
0x18004882e  lea     rdx, aD3d11refDll; "d3d11ref.dll"
0x180048835  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18004883c  call    ?SDKLoadLibraryW@CModule@@QEAAPEAUHINSTANCE__@@PEBG@Z; CModule::SDKLoadLibraryW(ushort const *)
0x180048841  jmp     loc_18004871C
0x180048846  mov     edi, [rbp+arg_20]
0x180048849  lea     eax, [rdi-9100h]
0x18004884f  test    eax, 0FFFFFCFFh
0x180048854  jnz     loc_180048906
0x18004885a  cmp     edi, 9400h
0x180048860  jz      loc_180048906
0x180048866  add     rcx, 10h; this
0x18004886a  xor     r8d, r8d; struct IDXGIAdapter *
0x18004886d  mov     rdx, rbx; struct CCreateDeviceCache *
0x180048870  call    ?ChooseHardwareAdapter@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@PEAV2@PEAUIDXGIAdapter@@@Z; CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(CCreateDeviceCache *,IDXGIAdapter *)
0x180048875  test    rax, rax
0x180048878  jz      loc_180048AB0
0x18004887e  cmp     [rbp+arg_30], r12b
0x180048882  jz      loc_18004893A
0x180048888  mov     [rbp+var_20], r12
0x18004888c  mov     rcx, [rbx+28h]
0x180048890  mov     rax, [rcx]
0x180048893  lea     r8, [rbp+var_20]
0x180048897  lea     rdx, _GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf
0x18004889e  mov     rax, [rax]
0x1800488a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488a6  mov     ecx, eax; int
0x1800488a8  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800488ad  mov     rsi, [rbp+arg_28]
0x1800488b1  cmp     [rsi], r12
0x1800488b4  jnz     short loc_1800488E3
0x1800488b6  mov     [rbp+arg_38], r12
0x1800488ba  mov     rcx, [rbp+var_20]
0x1800488be  mov     rax, [rcx]
0x1800488c1  lea     r8, [rbp+arg_38]
0x1800488c5  xor     edx, edx
0x1800488c7  mov     rax, [rax+20h]
0x1800488cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488d0  mov     ecx, eax; int
0x1800488d2  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800488d7  mov     rdx, [rbp+arg_38]; HINSTANCE
0x1800488db  mov     rcx, rsi; this
0x1800488de  call    ?attach@UniqueHMODULE@@QEAAXPEAUHINSTANCE__@@@Z; UniqueHMODULE::attach(HINSTANCE__ *)
0x1800488e3  lea     rcx, [rbx+0D8h]; this
0x1800488ea  mov     r8, [rbx+28h]; struct IDXGIAdapter *
0x1800488ee  mov     edx, edi; enum D3D_FEATURE_LEVEL
0x1800488f0  call    ?CreateLevel9@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@W4D3D_FEATURE_LEVEL@@PEAUIDXGIAdapter@@@Z; CCreateDeviceCache::CAdapterCache::CreateLevel9(D3D_FEATURE_LEVEL,IDXGIAdapter *)
0x1800488f5  mov     rbx, rax
0x1800488f8  lea     rcx, [rbp+var_20]
0x1800488fc  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048901  jmp     loc_180048AAB
0x180048906  cmp     edi, 0A000h
0x18004890c  jz      short loc_18004893A
0x18004890e  cmp     edi, 0A100h
0x180048914  jz      short loc_18004893A
0x180048916  cmp     edi, 0B000h
0x18004891c  jz      short loc_18004893A
0x18004891e  cmp     edi, 0B100h
0x180048924  jz      short loc_18004893A
0x180048926  cmp     edi, 0C000h
0x18004892c  jz      short loc_18004893A
0x18004892e  cmp     edi, 0C100h
0x180048934  jnz     loc_180048AB0
0x18004893a  lea     rcx, [rbx+10h]; this
0x18004893e  xor     r8d, r8d; struct IDXGIAdapter *
0x180048941  mov     rdx, rbx; struct CCreateDeviceCache *
0x180048944  call    ?ChooseHardwareAdapter@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@PEAV2@PEAUIDXGIAdapter@@@Z; CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(CCreateDeviceCache *,IDXGIAdapter *)
0x180048949  jmp     short loc_18004897D
0x18004894b  test    rdi, rdi
0x18004894e  jz      short loc_180048985
0x180048950  mov     rax, [rdx]
0x180048953  lea     r8, [rbp+var_28]
0x180048957  lea     rdx, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18004895e  mov     rcx, rdi
0x180048961  mov     rax, [rax]
0x180048964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048969  test    eax, eax
0x18004896b  js      short loc_180048985
0x18004896d  lea     rcx, [rbx+10h]; this
0x180048971  mov     r8, [rbp+var_28]; struct IDXCoreAdapter *
0x180048975  mov     rdx, rbx; struct CCreateDeviceCache *
0x180048978  call    ?ChooseDXCoreAdapter@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@PEAV2@PEAUIDXCoreAdapter@@@Z; CCreateDeviceCache::CAdapterCache::ChooseDXCoreAdapter(CCreateDeviceCache *,IDXCoreAdapter *)
0x18004897d  mov     rbx, rax
0x180048980  jmp     loc_180048AAB
0x180048985  mov     [rbp+arg_38], r12
0x180048989  mov     rax, [rdi]
0x18004898c  lea     r8, [rbp+arg_38]
0x180048990  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180048997  mov     rcx, rdi
0x18004899a  mov     rax, [rax]
0x18004899d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489a2  mov     esi, [rbp+arg_20]
0x1800489a5  lea     eax, [rsi-9100h]
0x1800489ab  test    eax, 0FFFFFCFFh
0x1800489b0  jnz     loc_180048A4F
0x1800489b6  cmp     esi, 9400h
0x1800489bc  jz      loc_180048A4F
0x1800489c2  cmp     [rbp+arg_30], r12b
0x1800489c6  jz      loc_180048A8F
0x1800489cc  mov     r14, [rbp+arg_28]
0x1800489d0  cmp     [r14], r12
0x1800489d3  jnz     short loc_180048A3B
0x1800489d5  mov     [rbp+var_10], r12
0x1800489d9  mov     [rbp+var_30], r12
0x1800489dd  mov     rax, [rdi]
0x1800489e0  lea     r8, [rbp+var_30]
0x1800489e4  lea     rdx, _GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf
0x1800489eb  mov     rcx, rdi
0x1800489ee  mov     rax, [rax]
0x1800489f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489f6  mov     rcx, [rbp+var_30]
0x1800489fa  mov     rax, [rcx]
0x1800489fd  lea     r8, [rbp+var_10]
0x180048a01  xor     edx, edx
0x180048a03  mov     rax, [rax+20h]
0x180048a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a0c  mov     edi, 887A0005h
0x180048a11  cmp     eax, edi
0x180048a13  jnz     short loc_180048A20
0x180048a15  lea     rcx, [rbp+var_30]
0x180048a19  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048a1e  jmp     short loc_180048A84
0x180048a20  mov     rdx, [rbp+var_10]; HINSTANCE
0x180048a24  mov     rcx, r14; this
0x180048a27  call    ?attach@UniqueHMODULE@@QEAAXPEAUHINSTANCE__@@@Z; UniqueHMODULE::attach(HINSTANCE__ *)
0x180048a2c  nop
0x180048a2d  lea     rcx, [rbp+var_30]
0x180048a31  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048a36  cmp     [r14], r12
0x180048a39  jz      short loc_180048A8F
0x180048a3b  lea     rcx, [rbx+0D8h]; this
0x180048a42  mov     r8, [rbp+arg_38]; struct IDXGIAdapter *
0x180048a46  mov     edx, esi; enum D3D_FEATURE_LEVEL
0x180048a48  call    ?CreateLevel9@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@W4D3D_FEATURE_LEVEL@@PEAUIDXGIAdapter@@@Z; CCreateDeviceCache::CAdapterCache::CreateLevel9(D3D_FEATURE_LEVEL,IDXGIAdapter *)
0x180048a4d  jmp     short loc_180048A9F
0x180048a4f  cmp     esi, 0A000h
0x180048a55  jz      short loc_180048A8F
0x180048a57  cmp     esi, 0A100h
0x180048a5d  jz      short loc_180048A8F
0x180048a5f  cmp     esi, 0B000h
0x180048a65  jz      short loc_180048A8F
0x180048a67  cmp     esi, 0B100h
0x180048a6d  jz      short loc_180048A8F
0x180048a6f  cmp     esi, 0C000h
0x180048a75  jz      short loc_180048A8F
0x180048a77  cmp     esi, 0C100h
0x180048a7d  jz      short loc_180048A8F
0x180048a7f  mov     edi, 887A0004h
0x180048a84  lea     rcx, [rbp+arg_38]
0x180048a88  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048a8d  jmp     short loc_180048B09
0x180048a8f  mov     r8, [rbp+arg_38]; struct IDXGIAdapter *
0x180048a93  mov     rdx, rbx; struct CCreateDeviceCache *
0x180048a96  lea     rcx, [rbx+10h]; this
0x180048a9a  call    ?ChooseHardwareAdapter@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@PEAV2@PEAUIDXGIAdapter@@@Z; CCreateDeviceCache::CAdapterCache::ChooseHardwareAdapter(CCreateDeviceCache *,IDXGIAdapter *)
0x180048a9f  mov     rbx, rax
0x180048aa2  lea     rcx, [rbp+arg_38]
0x180048aa6  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048aab  test    rbx, rbx
0x180048aae  jnz     short loc_180048AB7
0x180048ab0  mov     edi, 887A0004h
0x180048ab5  jmp     short loc_180048B09
0x180048ab7  cmp     [rbx+10h], r12
0x180048abb  jnz     short loc_180048B03
0x180048abd  mov     rcx, [rbx+18h]
0x180048ac1  test    rcx, rcx
0x180048ac4  jz      short loc_180048B03
0x180048ac6  cmp     [rbp+arg_10], r12d
0x180048aca  jz      short loc_180048AE9
0x180048acc  mov     rax, [rcx]
0x180048acf  lea     r9, [rbp+arg_10]
0x180048ad3  mov     r8d, 4
0x180048ad9  lea     rdx, GUID_DeviceType
0x180048ae0  mov     rax, [rax+18h]
0x180048ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ae9  mov     rcx, [rbx+18h]
0x180048aed  mov     rax, [rcx]
0x180048af0  lea     r8, [rbx+10h]
0x180048af4  lea     rdx, _GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf
0x180048afb  mov     rax, [rax]
0x180048afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b03  mov     [r15], rbx
0x180048b06  mov     edi, r12d
0x180048b09  lea     rcx, [rbp+var_28]
0x180048b0d  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180048b12  mov     eax, edi
0x180048b14  lea     r11, [rsp+60h+var_s0]
0x180048b19  mov     rbx, [r11+30h]
  ... truncated ...
```
