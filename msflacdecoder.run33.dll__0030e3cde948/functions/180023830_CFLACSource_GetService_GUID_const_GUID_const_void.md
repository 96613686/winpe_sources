# CFLACSource::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x180023830`
- end: `0x180023a67`
- name: `?GetService@CFLACSource@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `567`
- prototype: `int(CFLACSource *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002350c`
- `0x180023830`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023970`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023970`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACSource::GetService(
        CFLACSource *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **ppv)
{
  char *v4; // rbx
  int v5; // ecx
  int v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  unsigned int MetadataPropertyStore; // [rsp+60h] [rbp+10h]

  MetadataPropertyStore = 0;
  v4 = (char *)this - 88;
  if ( !ppv )
  {
    MetadataPropertyStore = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = (unsigned int)(v6 + 52);
LABEL_38:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, v4, v5);
      return MetadataPropertyStore;
    }
    return MetadataPropertyStore;
  }
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4;
  if ( v8 )
  {
    v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1 )
      v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)MF_PROPERTY_HANDLER_SERVICE.Data4;
    if ( v12 )
    {
      *ppv = 0;
      MetadataPropertyStore = -1072875846;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 58;
        goto LABEL_38;
      }
    }
    else
    {
      v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInitializeWithStream.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInitializeWithStream.Data1 )
        v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInitializeWithStream.Data4;
      if ( v13 )
      {
        v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
          v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
        if ( v14 )
        {
          MetadataPropertyStore = -2147467262;
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v7 = 57;
            goto LABEL_38;
          }
        }
        else
        {
          MetadataPropertyStore = CFLACSource::GetMetadataPropertyStore(
                                    (CFLACSource *)((char *)this - 88),
                                    (struct IPropertyStore **)ppv);
          if ( (MetadataPropertyStore & 0x80000000) != 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
              v4,
              v15);
        }
      }
      else
      {
        MetadataPropertyStore = CoCreateInstance(&CLSID_MFFLACPropertyHandler, 0, 1u, &IID_IInitializeWithStream, ppv);
        if ( (MetadataPropertyStore & 0x80000000) != 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 54;
          goto LABEL_38;
        }
      }
    }
    return MetadataPropertyStore;
  }
  v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_0a9ccdbc_d797_4563_9667_94ec5d79292d.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_0a9ccdbc_d797_4563_9667_94ec5d79292d.Data1 )
    v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_0a9ccdbc_d797_4563_9667_94ec5d79292d.Data4;
  if ( !v9 )
  {
    v10 = (unsigned __int64)this + 8;
LABEL_15:
    *ppv = (void *)(v10 & -(__int64)(this != (CFLACSource *)88));
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))((char *)this - 88);
    return MetadataPropertyStore;
  }
  v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_88ddcd21_03c3_4275_91ed_55ee3929328f.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_88ddcd21_03c3_4275_91ed_55ee3929328f.Data1 )
    v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_88ddcd21_03c3_4275_91ed_55ee3929328f.Data4;
  if ( !v11 )
  {
    v10 = (unsigned __int64)this + 16;
    goto LABEL_15;
  }
  MetadataPropertyStore = -2147467262;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v7 = 53;
    goto LABEL_38;
  }
  return MetadataPropertyStore;
}

```

## disassembly

```asm
0x180023830  mov     [rsp-8+arg_8], rbx
0x180023835  push    rbp
0x180023836  mov     rbp, rsp
0x180023839  sub     rsp, 50h
0x18002383d  mov     [rbp+arg_0], 0
0x180023844  lea     rbx, [rcx-58h]
0x180023848  mov     [rbp+var_20], rbx
0x18002384c  lea     rax, [rbp+arg_0]
0x180023850  mov     [rbp+var_18], rax
0x180023854  test    r9, r9
0x180023857  jnz     short loc_180023877
0x180023859  mov     ecx, 80004003h
0x18002385e  mov     [rbp+arg_0], ecx
0x180023861  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023866  cmp     al, 1
0x180023868  jb      loc_180023A59
0x18002386e  lea     edx, [r9+34h]
0x180023872  jmp     loc_180023A3A
0x180023877  mov     rax, [rdx]
0x18002387a  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x180023881  jnz     short loc_18002388E
0x180023883  mov     rax, [rdx+8]
0x180023887  sub     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x18002388e  test    rax, rax
0x180023891  jnz     loc_18002391B
0x180023897  mov     rax, [r8]
0x18002389a  sub     rax, qword ptr cs:_GUID_0a9ccdbc_d797_4563_9667_94ec5d79292d.Data1
0x1800238a1  jnz     short loc_1800238AE
0x1800238a3  mov     rax, [r8+8]
0x1800238a7  sub     rax, qword ptr cs:_GUID_0a9ccdbc_d797_4563_9667_94ec5d79292d.Data4
0x1800238ae  test    rax, rax
0x1800238b1  jnz     short loc_1800238B9
0x1800238b3  lea     rdx, [rcx+8]
0x1800238b7  jmp     short loc_1800238D9
0x1800238b9  mov     rax, [r8]
0x1800238bc  sub     rax, qword ptr cs:_GUID_88ddcd21_03c3_4275_91ed_55ee3929328f.Data1
0x1800238c3  jnz     short loc_1800238D0
0x1800238c5  mov     rax, [r8+8]
0x1800238c9  sub     rax, qword ptr cs:_GUID_88ddcd21_03c3_4275_91ed_55ee3929328f.Data4
0x1800238d0  test    rax, rax
0x1800238d3  jnz     short loc_1800238FC
0x1800238d5  lea     rdx, [rcx+10h]
0x1800238d9  mov     rax, rbx
0x1800238dc  neg     rax
0x1800238df  sbb     rcx, rcx
0x1800238e2  and     rcx, rdx
0x1800238e5  mov     [r9], rcx
0x1800238e8  mov     rax, [rbx]
0x1800238eb  mov     rcx, rbx
0x1800238ee  mov     rax, [rax+8]
0x1800238f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238f7  jmp     loc_180023A59
0x1800238fc  mov     ecx, 80004002h
0x180023901  mov     [rbp+arg_0], ecx
0x180023904  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023909  cmp     al, 1
0x18002390b  jb      loc_180023A59
0x180023911  mov     edx, 35h ; '5'
0x180023916  jmp     loc_180023A3A
0x18002391b  mov     rax, [rdx]
0x18002391e  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data1
0x180023925  jnz     short loc_180023932
0x180023927  mov     rax, [rdx+8]
0x18002392b  sub     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data4
0x180023932  test    rax, rax
0x180023935  jnz     loc_180023A1D
0x18002393b  mov     rax, [r8]
0x18002393e  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data1
0x180023945  jnz     short loc_180023952
0x180023947  mov     rax, [r8+8]
0x18002394b  sub     rax, qword ptr cs:IID_IInitializeWithStream.Data4
0x180023952  test    rax, rax
0x180023955  jnz     short loc_18002399A
0x180023957  mov     [rsp+50h+ppv], r9; ppv
0x18002395c  lea     r9, IID_IInitializeWithStream; riid
0x180023963  xor     edx, edx; pUnkOuter
0x180023965  lea     r8d, [rax+1]; dwClsContext
0x180023969  lea     rcx, CLSID_MFFLACPropertyHandler; rclsid
0x180023970  call    cs:__imp_CoCreateInstance
0x180023976  mov     ecx, eax
0x180023978  mov     [rbp+arg_0], eax
0x18002397b  test    eax, eax
0x18002397d  jns     loc_180023A59
0x180023983  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023988  cmp     al, 1
0x18002398a  jb      loc_180023A59
0x180023990  mov     edx, 36h ; '6'
0x180023995  jmp     loc_180023A3A
0x18002399a  mov     rax, [r8]
0x18002399d  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x1800239a4  jnz     short loc_1800239B1
0x1800239a6  mov     rax, [r8+8]
0x1800239aa  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x1800239b1  test    rax, rax
0x1800239b4  jnz     short loc_180023A05
0x1800239b6  mov     [rbp+var_10], rbx
0x1800239ba  lea     rax, [rbp+arg_0]
0x1800239be  mov     [rbp+var_8], rax
0x1800239c2  mov     rdx, r9; struct IPropertyStore **
0x1800239c5  mov     rcx, rbx; this
0x1800239c8  call    ?GetMetadataPropertyStore@CFLACSource@@AEAAJPEAPEAUIPropertyStore@@@Z; CFLACSource::GetMetadataPropertyStore(IPropertyStore * *)
0x1800239cd  mov     ecx, eax
0x1800239cf  mov     [rbp+arg_0], eax
0x1800239d2  test    eax, eax
0x1800239d4  jns     short loc_180023A03
0x1800239d6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800239db  cmp     al, 1
0x1800239dd  jb      short loc_180023A03
0x1800239df  mov     edx, 38h ; '8'
0x1800239e4  mov     dword ptr [rsp+50h+ppv], ecx
0x1800239e8  mov     r9, rbx
0x1800239eb  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800239f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239f9  mov     rcx, [rcx+10h]
0x1800239fd  call    WPP_SF_qd
0x180023a02  nop
0x180023a03  jmp     short loc_180023A59
0x180023a05  mov     ecx, 80004002h
0x180023a0a  mov     [rbp+arg_0], ecx
0x180023a0d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023a12  cmp     al, 1
0x180023a14  jb      short loc_180023A59
0x180023a16  mov     edx, 39h ; '9'
0x180023a1b  jmp     short loc_180023A3A
0x180023a1d  mov     qword ptr [r9], 0
0x180023a24  mov     ecx, 0C00D36BAh
0x180023a29  mov     [rbp+arg_0], ecx
0x180023a2c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023a31  cmp     al, 1
0x180023a33  jb      short loc_180023A59
0x180023a35  mov     edx, 3Ah ; ':'
0x180023a3a  mov     dword ptr [rsp+50h+ppv], ecx
0x180023a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a45  mov     r9, rbx
0x180023a48  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180023a4f  mov     rcx, [rcx+10h]
0x180023a53  call    WPP_SF_qd
0x180023a58  nop
0x180023a59  mov     eax, [rbp+arg_0]
0x180023a5c  mov     rbx, [rsp+50h+arg_8]
0x180023a61  add     rsp, 50h
0x180023a65  pop     rbp
0x180023a66  retn
```
