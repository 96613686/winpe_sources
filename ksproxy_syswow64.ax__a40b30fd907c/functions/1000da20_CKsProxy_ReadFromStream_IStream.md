# CKsProxy::ReadFromStream(IStream *)

- ea: `0x1000da20`
- end: `0x1000dcb6`
- name: `?ReadFromStream@CKsProxy@@UAEJPAUIStream@@@Z`
- size: `662`
- prototype: `HRESULT __thiscall(CKsProxy *this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1000adfd`
- `0x1000aea8`
- `0x1000da20`
- `0x1002d510`
- `0x1003035c`
- `0x1003aba0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1000dbdc`
- `ole32!CoTaskMemAlloc` at `0x1000dbdc`
- `ole32!CoCreateInstance` at `0x1000da8d`
- `ole32!CoCreateInstance` at `0x1000da8d`

## pseudocode

```c
HRESULT __thiscall CKsProxy::ReadFromStream(CKsProxy *this, struct IStream *a2)
{
  IUnknown *m_pUnknown; // edi
  HRESULT v5; // edi
  LPVOID v6; // edx
  ISpecifyPropertyPages_vtbl *v7; // esi
  int Release; // edx
  int PinFactoryId; // eax
  struct _AMMediaType *v10; // [esp+64h] [ebp-78h]
  int v11; // [esp+70h] [ebp-6Ch] BYREF
  int v12; // [esp+74h] [ebp-68h] BYREF
  struct IStream *v13; // [esp+78h] [ebp-64h]
  LPVOID ppv; // [esp+7Ch] [ebp-60h] BYREF
  int v15; // [esp+80h] [ebp-5Ch]
  int v16; // [esp+84h] [ebp-58h] BYREF
  ISpecifyPropertyPages_vtbl *v17; // [esp+88h] [ebp-54h]
  _BYTE v18[64]; // [esp+8Ch] [ebp-50h] BYREF
  SIZE_T cb; // [esp+CCh] [ebp-10h]
  LPVOID v20; // [esp+D0h] [ebp-Ch]

  v13 = a2;
  if ( this->IAMDeviceRemoval::IUnknown::__vftable )
    return -2147023649;
  m_pUnknown = this->m_pUnknown;
  if ( (_AMOVIESETUP_FILTER *)m_pUnknown > this->GetSetupData(this) )
    return -2147024883;
  v5 = CoCreateInstance(&CLSID_CDeviceMoniker, 0, 0x401u, &IID_IPersistStream, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(int (__thiscall **)(_DWORD, LPVOID, struct IStream *))(*(_DWORD *)ppv + 20))(
           *(_DWORD *)(*(_DWORD *)ppv + 20),
           ppv,
           v13);
    if ( v5 >= 0 )
    {
      v5 = (**(int (__thiscall ***)(_DWORD, LPVOID, GUID *, int *))ppv)(**(_DWORD **)ppv, ppv, &IID_IPropertyBag, &v11);
      if ( v5 >= 0 )
      {
        v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IAMovieSetup *, int, _DWORD))this->CBaseFilter::IAMovieSetup::IUnknown::__vftable[1].QueryInterface)(
               this->CBaseFilter::IAMovieSetup::IUnknown::__vftable[1].QueryInterface,
               &this->IAMovieSetup,
               v11,
               0);
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v11 + 8))(*(_DWORD *)(*(_DWORD *)v11 + 8), v11);
      }
    }
    (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)ppv + 8))(*(_DWORD *)(*(_DWORD *)ppv + 8), ppv);
    if ( v5 >= 0 && this->m_pUnknown == (IUnknown *const)1 )
    {
      v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, void *, unsigned int, unsigned int *), struct IStream *, int *, int, int *))v13->Read)(
             v13->Read,
             v13,
             &v12,
             4,
             &v11);
      if ( v5 >= 0 )
      {
        if ( v11 == 4 )
        {
          do
          {
            if ( !v12 )
              break;
            v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, void *, unsigned int, unsigned int *), struct IStream *, int *, int, int *))v13->Read)(
                   v13->Read,
                   v13,
                   &v16,
                   4,
                   &v11);
            if ( v5 < 0 )
              break;
            v12 -= v11;
            v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, void *, unsigned int, unsigned int *), struct IStream *, _BYTE *, int, int *))v13->Read)(
                   v13->Read,
                   v13,
                   v18,
                   72,
                   &v11);
            if ( v5 < 0 )
              break;
            v12 -= v11;
            v6 = CoTaskMemAlloc(cb);
            v20 = v6;
            if ( !v6 )
              return -2147024882;
            v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, void *, unsigned int, unsigned int *), struct IStream *, LPVOID, SIZE_T, int *))v13->Read)(
                   v13->Read,
                   v13,
                   v6,
                   cb,
                   &v11);
            if ( v5 < 0 )
            {
              FreeMediaType(v10);
              return v5;
            }
            v12 -= v11;
            v7 = this->ISpecifyPropertyPages::IUnknown::__vftable;
            if ( v7 )
            {
              while ( 1 )
              {
                Release = (int)v7->Release;
                v7 = (ISpecifyPropertyPages_vtbl *)v7->AddRef;
                v15 = Release;
                v17 = v7;
                if ( !CKsProxy::GetPinHandle(Release, (CKsProxy *)v10) )
                {
                  PinFactoryId = CKsProxy::GetPinFactoryId(v15, (CKsProxy *)v10);
                  if ( v16 == PinFactoryId )
                    break;
                }
                if ( !v17 )
                  goto LABEL_24;
              }
              v5 = (*(int (__thiscall **)(_DWORD, int, _DWORD, _BYTE *))(*(_DWORD *)(v15 + 12) + 12))(
                     *(_DWORD *)(*(_DWORD *)(v15 + 12) + 12),
                     v15 + 12,
                     0,
                     v18);
            }
LABEL_24:
            FreeMediaType(v10);
          }
          while ( v5 >= 0 );
        }
        else
        {
          return -2147220925;
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1000da20  mov     edi, edi
0x1000da22  push    ebp
0x1000da23  mov     ebp, esp
0x1000da25  and     esp, 0FFFFFFF8h
0x1000da28  sub     esp, 6Ch
0x1000da2b  mov     eax, ___security_cookie
0x1000da30  xor     eax, esp
0x1000da32  mov     [esp+6Ch+var_4], eax
0x1000da36  mov     eax, [ebp+arg_0]
0x1000da39  push    ebx
0x1000da3a  mov     ebx, ecx
0x1000da3c  mov     [esp+70h+var_64], eax
0x1000da40  push    esi
0x1000da41  push    edi
0x1000da42  cmp     dword ptr [ebx+8Ch], 0
0x1000da49  jz      short loc_1000DA55
0x1000da4b  mov     eax, 800704DFh
0x1000da50  jmp     loc_1000DCA2
0x1000da55  mov     eax, [ebx]
0x1000da57  mov     edi, [ebx+4]
0x1000da5a  mov     esi, [eax+20h]
0x1000da5d  mov     ecx, esi; this
0x1000da5f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000da65  mov     ecx, ebx
0x1000da67  call    esi
0x1000da69  cmp     edi, eax
0x1000da6b  jbe     short loc_1000DA77
0x1000da6d  mov     eax, 8007000Dh
0x1000da72  jmp     loc_1000DCA2
0x1000da77  lea     eax, [esp+78h+ppv]
0x1000da7b  push    eax; ppv
0x1000da7c  push    offset _IID_IPersistStream; riid
0x1000da81  push    401h; dwClsContext
0x1000da86  push    0; pUnkOuter
0x1000da88  push    offset _CLSID_CDeviceMoniker; rclsid
0x1000da8d  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1000da93  mov     edi, eax
0x1000da95  test    edi, edi
0x1000da97  js      loc_1000DCA0
0x1000da9d  mov     ecx, [esp+78h+ppv]
0x1000daa1  push    [esp+78h+var_64]
0x1000daa5  push    ecx
0x1000daa6  mov     eax, [ecx]
0x1000daa8  mov     esi, [eax+14h]
0x1000daab  mov     ecx, esi; this
0x1000daad  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000dab3  call    esi
0x1000dab5  mov     edi, eax
0x1000dab7  test    edi, edi
0x1000dab9  js      short loc_1000DB0D
0x1000dabb  mov     ecx, [esp+78h+ppv]
0x1000dabf  mov     eax, [ecx]
0x1000dac1  mov     esi, [eax]
0x1000dac3  lea     eax, [esp+78h+var_6C]
0x1000dac7  push    eax
0x1000dac8  push    offset _IID_IPropertyBag
0x1000dacd  push    ecx
0x1000dace  mov     ecx, esi; this
0x1000dad0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000dad6  call    esi
0x1000dad8  mov     edi, eax
0x1000dada  test    edi, edi
0x1000dadc  js      short loc_1000DB0D
0x1000dade  lea     ecx, [ebx+10h]
0x1000dae1  mov     eax, [ecx]
0x1000dae3  push    0
0x1000dae5  push    [esp+7Ch+var_6C]
0x1000dae9  mov     esi, [eax+14h]
0x1000daec  push    ecx
0x1000daed  mov     ecx, esi; this
0x1000daef  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000daf5  call    esi
0x1000daf7  mov     edi, eax
0x1000daf9  mov     eax, [esp+78h+var_6C]
0x1000dafd  push    eax
0x1000dafe  mov     ecx, [eax]
0x1000db00  mov     esi, [ecx+8]
0x1000db03  mov     ecx, esi; this
0x1000db05  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000db0b  call    esi
0x1000db0d  mov     eax, [esp+78h+ppv]
0x1000db11  push    eax
0x1000db12  mov     ecx, [eax]
0x1000db14  mov     esi, [ecx+8]
0x1000db17  mov     ecx, esi; this
0x1000db19  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000db1f  call    esi
0x1000db21  test    edi, edi
0x1000db23  js      loc_1000DCA0
0x1000db29  mov     eax, [ebx+4]
0x1000db2c  sub     eax, 1
0x1000db2f  jnz     loc_1000DCA0
0x1000db35  mov     ecx, [esp+78h+var_64]
0x1000db39  mov     eax, [ecx]
0x1000db3b  mov     esi, [eax+0Ch]
0x1000db3e  lea     eax, [esp+78h+var_6C]
0x1000db42  push    eax
0x1000db43  push    4
0x1000db45  lea     eax, [esp+80h+var_68]
0x1000db49  push    eax
0x1000db4a  push    ecx
0x1000db4b  mov     ecx, esi; this
0x1000db4d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000db53  call    esi
0x1000db55  mov     edi, eax
0x1000db57  test    edi, edi
0x1000db59  js      loc_1000DCA0
0x1000db5f  cmp     [esp+78h+var_6C], 4
0x1000db64  jz      loc_1000DC83
0x1000db6a  mov     edi, 80040243h
0x1000db6f  jmp     loc_1000DCA0
0x1000db74  mov     ecx, [esp+78h+var_64]
0x1000db78  mov     eax, [ecx]
0x1000db7a  mov     esi, [eax+0Ch]
0x1000db7d  lea     eax, [esp+78h+var_6C]
0x1000db81  push    eax
0x1000db82  push    4
0x1000db84  lea     eax, [esp+80h+var_58]
0x1000db88  push    eax
0x1000db89  push    ecx
0x1000db8a  mov     ecx, esi; this
0x1000db8c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000db92  call    esi
0x1000db94  mov     edi, eax
0x1000db96  test    edi, edi
0x1000db98  js      loc_1000DCA0
0x1000db9e  mov     ecx, [esp+78h+var_64]
0x1000dba2  mov     eax, [esp+78h+var_6C]
0x1000dba6  sub     [esp+78h+var_68], eax
0x1000dbaa  mov     eax, [ecx]
0x1000dbac  mov     esi, [eax+0Ch]
0x1000dbaf  lea     eax, [esp+78h+var_6C]
0x1000dbb3  push    eax
0x1000dbb4  push    48h ; 'H'
0x1000dbb6  lea     eax, [esp+80h+var_50]
0x1000dbba  push    eax
0x1000dbbb  push    ecx
0x1000dbbc  mov     ecx, esi; this
0x1000dbbe  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000dbc4  call    esi
0x1000dbc6  mov     edi, eax
0x1000dbc8  test    edi, edi
0x1000dbca  js      loc_1000DCA0
0x1000dbd0  mov     eax, [esp+78h+var_6C]
0x1000dbd4  push    [esp+78h+cb]; cb
0x1000dbd8  sub     [esp+7Ch+var_68], eax
0x1000dbdc  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1000dbe2  mov     edx, eax
0x1000dbe4  mov     [esp+78h+var_C], edx
0x1000dbe8  test    edx, edx
0x1000dbea  jz      loc_1000DC9B
0x1000dbf0  mov     eax, [esp+78h+var_64]
0x1000dbf4  mov     ecx, [eax]
0x1000dbf6  mov     esi, [ecx+0Ch]
0x1000dbf9  lea     ecx, [esp+78h+var_6C]
0x1000dbfd  push    ecx
0x1000dbfe  push    [esp+7Ch+cb]
0x1000dc02  mov     ecx, esi; this
0x1000dc04  push    edx
0x1000dc05  push    eax
0x1000dc06  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000dc0c  call    esi
0x1000dc0e  mov     edi, eax
0x1000dc10  test    edi, edi
0x1000dc12  js      short loc_1000DC90
0x1000dc14  mov     eax, [esp+78h+var_6C]
0x1000dc18  sub     [esp+78h+var_68], eax
0x1000dc1c  mov     esi, [ebx+5Ch]
0x1000dc1f  test    esi, esi
0x1000dc21  jz      short loc_1000DC76
0x1000dc23  mov     eax, [esi+8]
0x1000dc26  mov     edx, eax
0x1000dc28  mov     ecx, [esi+4]
0x1000dc2b  mov     esi, ecx
0x1000dc2d  mov     [esp+78h+var_5C], eax
0x1000dc31  mov     [esp+78h+var_54], ecx
0x1000dc35  call    ?GetPinHandle@CKsProxy@@QAGPAXPAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x1000dc3a  test    eax, eax
0x1000dc3c  jnz     short loc_1000DC4D
0x1000dc3e  mov     edx, [esp+78h+var_5C]
0x1000dc42  call    ?GetPinFactoryId@CKsProxy@@QAGKPAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x1000dc47  cmp     [esp+78h+var_58], eax
0x1000dc4b  jz      short loc_1000DC56
0x1000dc4d  cmp     [esp+78h+var_54], 0
0x1000dc52  jnz     short loc_1000DC23
0x1000dc54  jmp     short loc_1000DC76
0x1000dc56  mov     ecx, [esp+78h+var_5C]
0x1000dc5a  add     ecx, 0Ch
0x1000dc5d  mov     eax, [ecx]
0x1000dc5f  mov     esi, [eax+0Ch]
0x1000dc62  lea     eax, [esp+78h+var_50]
0x1000dc66  push    eax
0x1000dc67  push    0
0x1000dc69  push    ecx
0x1000dc6a  mov     ecx, esi; this
0x1000dc6c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000dc72  call    esi
0x1000dc74  mov     edi, eax
0x1000dc76  lea     ecx, [esp+78h+var_50]
0x1000dc7a  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1000dc7f  test    edi, edi
0x1000dc81  js      short loc_1000DCA0
0x1000dc83  cmp     [esp+78h+var_68], 0
0x1000dc88  jnz     loc_1000DB74
0x1000dc8e  jmp     short loc_1000DCA0
0x1000dc90  lea     ecx, [esp+78h+var_50]
0x1000dc94  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1000dc99  jmp     short loc_1000DCA0
0x1000dc9b  mov     edi, 8007000Eh
0x1000dca0  mov     eax, edi
0x1000dca2  mov     ecx, [esp+78h+var_4]
0x1000dca6  pop     edi
0x1000dca7  pop     esi
0x1000dca8  pop     ebx
0x1000dca9  xor     ecx, esp; StackCookie
0x1000dcab  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000dcb0  mov     esp, ebp
0x1000dcb2  pop     ebp
0x1000dcb3  retn    4
```
