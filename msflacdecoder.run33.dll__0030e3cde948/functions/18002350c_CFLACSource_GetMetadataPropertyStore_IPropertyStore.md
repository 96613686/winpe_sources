# CFLACSource::GetMetadataPropertyStore(IPropertyStore * *)

- ea: `0x18002350c`
- end: `0x180023744`
- name: `?GetMetadataPropertyStore@CFLACSource@@AEAAJPEAPEAUIPropertyStore@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023830`

## callees

- `0x180020398`
- `0x180020484`
- `0x1800223b8`
- `0x18002350c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800236da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800236da`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180023615`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180023615`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::GetMetadataPropertyStore(CFLACSource *this, struct IPropertyStore **a2)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v5; // ecx
  __int64 v6; // rdx
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  IStream *ppstm[4]; // [rsp+38h] [rbp-20h] BYREF
  HRESULT OnlyPropertyStore; // [rsp+80h] [rbp+28h] BYREF
  int v11; // [rsp+88h] [rbp+30h] BYREF
  __int64 v12; // [rsp+90h] [rbp+38h] BYREF
  LPCWSTR pszFile; // [rsp+98h] [rbp+40h] BYREF

  OnlyPropertyStore = 0;
  ppstm[1] = (IStream *)this;
  ppstm[2] = (IStream *)&OnlyPropertyStore;
  *a2 = 0;
  pszFile = 0;
  v8 = 0;
  v12 = 0;
  ppstm[0] = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 39);
  if ( !v4 )
  {
    OnlyPropertyStore = -1072875845;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)OnlyPropertyStore;
    v6 = 60;
    goto LABEL_17;
  }
  if ( *((_QWORD *)this + 40) )
    goto LABEL_14;
  v11 = 0;
  OnlyPropertyStore = (**v4)(v4, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, &v8);
  if ( OnlyPropertyStore >= 0 )
  {
    OnlyPropertyStore = (*(__int64 (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v8 + 104LL))(
                          v8,
                          &MF_BYTESTREAM_ORIGIN_NAME,
                          &pszFile,
                          &v11);
    if ( OnlyPropertyStore >= 0 )
    {
      OnlyPropertyStore = (*(__int64 (__fastcall **)(char *, const IID *, GUID *, __int64 *))(*((_QWORD *)this + 11)
                                                                                            + 24LL))(
                            (char *)this + 88,
                            &MF_PROPERTY_HANDLER_SERVICE,
                            &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
                            &v12);
      if ( OnlyPropertyStore >= 0 )
      {
        OnlyPropertyStore = SHCreateStreamOnFileW(pszFile, 0, ppstm);
        if ( OnlyPropertyStore >= 0 )
        {
          OnlyPropertyStore = (*(__int64 (__fastcall **)(__int64, IStream *, _QWORD))(*(_QWORD *)v12 + 24LL))(
                                v12,
                                ppstm[0],
                                0);
          if ( OnlyPropertyStore >= 0 )
          {
            OnlyPropertyStore = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v12)(
                                  v12,
                                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                                  (char *)this + 320);
            if ( OnlyPropertyStore >= 0 )
              goto LABEL_14;
          }
        }
      }
    }
  }
  OnlyPropertyStore = CFLACSource::CreateReadOnlyPropertyStore(this, (struct IPropertyStore **)this + 40);
  if ( OnlyPropertyStore >= 0 )
  {
LABEL_14:
    OnlyPropertyStore = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IPropertyStore **))this + 40))(
                          *((_QWORD *)this + 40),
                          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                          a2);
    if ( OnlyPropertyStore >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_18;
    v6 = 62;
    goto LABEL_17;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v6 = 61;
LABEL_17:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v5);
  }
LABEL_18:
  if ( pszFile )
  {
    CoTaskMemFree((LPVOID)pszFile);
    pszFile = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( ppstm[0] )
    ((void (__fastcall *)(IStream *))ppstm[0]->lpVtbl->Release)(ppstm[0]);
  return (unsigned int)OnlyPropertyStore;
}

```

## disassembly

```asm
0x18002350c  push    rbp
0x18002350e  push    rbx
0x18002350f  push    rsi
0x180023510  push    rdi
0x180023511  mov     rbp, rsp
0x180023514  sub     rsp, 58h
0x180023518  mov     rsi, rdx
0x18002351b  mov     rbx, rcx
0x18002351e  mov     [rbp+arg_0], 0
0x180023525  mov     [rbp+var_18], rcx
0x180023529  lea     rax, [rbp+arg_0]
0x18002352d  mov     [rbp+var_10], rax
0x180023531  mov     qword ptr [rdx], 0
0x180023538  mov     [rbp+pszFile], 0
0x180023540  mov     [rbp+var_28], 0
0x180023548  mov     [rbp+arg_10], 0
0x180023550  mov     [rbp+ppstm], 0
0x180023558  mov     rcx, [rcx+138h]
0x18002355f  test    rcx, rcx
0x180023562  jnz     short loc_180023583
0x180023564  mov     ecx, 0C00D36BBh
0x180023569  mov     [rbp+arg_0], ecx
0x18002356c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023571  cmp     al, 1
0x180023573  jb      loc_180023738
0x180023579  mov     edx, 3Ch ; '<'
0x18002357e  jmp     loc_1800236B3
0x180023583  lea     rdi, [rbx+140h]
0x18002358a  cmp     qword ptr [rdi], 0
0x18002358e  jnz     loc_180023684
0x180023594  mov     [rbp+arg_8], 0
0x18002359b  mov     rax, [rcx]
0x18002359e  lea     r8, [rbp+var_28]
0x1800235a2  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800235a9  mov     rax, [rax]
0x1800235ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235b1  mov     [rbp+arg_0], eax
0x1800235b4  test    eax, eax
0x1800235b6  js      loc_180023660
0x1800235bc  mov     rcx, [rbp+var_28]
0x1800235c0  mov     rax, [rcx]
0x1800235c3  lea     r9, [rbp+arg_8]
0x1800235c7  lea     r8, [rbp+pszFile]
0x1800235cb  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x1800235d2  mov     rax, [rax+68h]
0x1800235d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235db  mov     [rbp+arg_0], eax
0x1800235de  test    eax, eax
0x1800235e0  js      short loc_180023660
0x1800235e2  lea     rcx, [rbx+58h]
0x1800235e6  mov     rax, [rcx]
0x1800235e9  lea     r9, [rbp+arg_10]
0x1800235ed  lea     r8, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x1800235f4  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x1800235fb  mov     rax, [rax+18h]
0x1800235ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023604  mov     [rbp+arg_0], eax
0x180023607  test    eax, eax
0x180023609  js      short loc_180023660
0x18002360b  lea     r8, [rbp+ppstm]; ppstm
0x18002360f  xor     edx, edx; grfMode
0x180023611  mov     rcx, [rbp+pszFile]; pszFile
0x180023615  call    cs:__imp_SHCreateStreamOnFileW
0x18002361b  mov     [rbp+arg_0], eax
0x18002361e  test    eax, eax
0x180023620  js      short loc_180023660
0x180023622  mov     rcx, [rbp+arg_10]
0x180023626  mov     rax, [rcx]
0x180023629  xor     r8d, r8d
0x18002362c  mov     rdx, [rbp+ppstm]
0x180023630  mov     rax, [rax+18h]
0x180023634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023639  mov     [rbp+arg_0], eax
0x18002363c  test    eax, eax
0x18002363e  js      short loc_180023660
0x180023640  mov     rcx, [rbp+arg_10]
0x180023644  mov     rax, [rcx]
0x180023647  mov     r8, rdi
0x18002364a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180023651  mov     rax, [rax]
0x180023654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023659  mov     [rbp+arg_0], eax
0x18002365c  test    eax, eax
0x18002365e  jns     short loc_180023684
0x180023660  mov     rdx, rdi; struct IPropertyStore **
0x180023663  mov     rcx, rbx; this
0x180023666  call    ?CreateReadOnlyPropertyStore@CFLACSource@@AEAAJPEAPEAUIPropertyStore@@@Z; CFLACSource::CreateReadOnlyPropertyStore(IPropertyStore * *)
0x18002366b  mov     ecx, eax
0x18002366d  mov     [rbp+arg_0], eax
0x180023670  test    eax, eax
0x180023672  jns     short loc_180023684
0x180023674  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023679  cmp     al, 1
0x18002367b  jb      short loc_1800236D1
0x18002367d  mov     edx, 3Dh ; '='
0x180023682  jmp     short loc_1800236B3
0x180023684  mov     rcx, [rdi]
0x180023687  mov     rax, [rcx]
0x18002368a  mov     r8, rsi
0x18002368d  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180023694  mov     rax, [rax]
0x180023697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002369c  mov     ecx, eax
0x18002369e  mov     [rbp+arg_0], eax
0x1800236a1  test    eax, eax
0x1800236a3  jns     short loc_1800236D1
0x1800236a5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800236aa  cmp     al, 1
0x1800236ac  jb      short loc_1800236D1
0x1800236ae  mov     edx, 3Eh ; '>'
0x1800236b3  mov     [rsp+58h+var_38], ecx
0x1800236b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236be  mov     r9, rbx
0x1800236c1  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800236c8  mov     rcx, [rcx+10h]
0x1800236cc  call    WPP_SF_qd
0x1800236d1  mov     rcx, [rbp+pszFile]; pv
0x1800236d5  test    rcx, rcx
0x1800236d8  jz      short loc_1800236E8
0x1800236da  call    cs:__imp_CoTaskMemFree
0x1800236e0  mov     [rbp+pszFile], 0
0x1800236e8  mov     rcx, [rbp+var_28]
0x1800236ec  test    rcx, rcx
0x1800236ef  jz      short loc_180023705
0x1800236f1  mov     rax, [rcx]
0x1800236f4  mov     rax, [rax+10h]
0x1800236f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236fd  mov     [rbp+var_28], 0
0x180023705  mov     rcx, [rbp+arg_10]
0x180023709  test    rcx, rcx
0x18002370c  jz      short loc_180023722
0x18002370e  mov     rax, [rcx]
0x180023711  mov     rax, [rax+10h]
0x180023715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002371a  mov     [rbp+arg_10], 0
0x180023722  mov     rcx, [rbp+ppstm]
0x180023726  test    rcx, rcx
0x180023729  jz      short loc_180023738
0x18002372b  mov     rax, [rcx]
0x18002372e  mov     rax, [rax+10h]
0x180023732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023737  nop
0x180023738  mov     eax, [rbp+arg_0]
0x18002373b  add     rsp, 58h
0x18002373f  pop     rdi
0x180023740  pop     rsi
0x180023741  pop     rbx
0x180023742  pop     rbp
0x180023743  retn
```
